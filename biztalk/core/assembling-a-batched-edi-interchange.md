---
title: 装配批处理的 EDI 交换 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 18f64595-935e-4d52-9ec2-5edf7c2b9e83
caps.latest.revision: 45
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee608cf1b842fc205951038285f3c32dfca29f82
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358836"
---
# <a name="assembling-a-batched-edi-interchange"></a>装配批处理的 EDI 交换
若要将各个事务集批元素组装成 EDI 交换， [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI 和 AS2 执行以下操作：  
  
- 标识批处理的批处理元素  
  
- 验证和缓冲收到各个批元素  
  
- 检索特定批元素，并组装批的交换时满足发布条件  
  
  由批处理激活标准确定收集各个消息以组合成批的开始时间。 由批处理发布条件确定的发布批的时间。 有关这两个条件集的详细信息，请参阅[配置传出批](../core/configuring-an-outgoing-batch.md)。  
  
## <a name="message-flow-for-outgoing-batched-messages"></a>传出批处理的消息的消息流  
 当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]配置对传出消息进行批处理[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组件将执行以下一系列步骤来准备要批处理的消息发送。 这一系列的步骤介绍了在其中具有 BatchMarker 管道组件的 EDIReceive 管道处理收到的交换包含要进行批处理以备发送的事务集的这种情况。  
  
1. EDIReceive 管道中的 BatchMarker 管道组件确定哪些消息需要进行批处理的参与方属性中的 EDI 批处理筛选器设置。 （这是唯一的批处理组件，查看批处理筛选器设置并作用于它们）。  
  
2. 如果只有一个批配置的筛选器设置订阅的消息，BatchMarker 组件将升级该属性`EDI.ToBeBatched = True`。 这可确保批处理业务流程将提取该消息。  
  
3. 如果多个批配置的筛选器设置匹配的消息上下文，BatchMarker 组件升级的属性`EDI.ToBeRouted = True`，并设置`EDI.BatchIds`属性设置为一个空格分隔列表，包含匹配批 Id。  这可确保路由业务流程将订阅消息。  
  
   > [!NOTE]
   >  你可以升级自定义接收管道或自定义业务流程中相应的上下文属性。 自定义接收管道可以使用 BatchMarker 管道组件，也可以不使用 BatchMarker 管道组件升级的属性。  
  
4. 路由业务流程提取为其设置的任何事务`EDI.ToBeRouted = True`并`EDI.BatchIds`进行升级，然后再创建的事务集，确保每个批 ID 包含在复制副本`EDI.BatchIds`。 路由业务流程将设置`EDI.ToBeBatched = True`和`EDI.BatchId`设置为匹配批配置为每个副本的事务集的批处理 ID。 这可确保将进行批处理的批处理业务流程提取事务集。  
  
5. 批处理业务流程提取已升级下列属性的所有消息：  
  
   - `EDI.ToBeBatched = True` 和 EDI。BatchId = 与批处理业务流程的此实例关联的批处理的批处理 id。  
  
   - `EDI.ToBeBatched = True` 和 EDI。BatchName = 已配置的批和 EDI 的名称。DestinationPartyName = 包含此批配置的参与方名称。  
  
     批处理业务流程 （具有 BatchMarker 管道组件） 的 EDIReceive 管道处理传入消息后，将批处理仅对 X12-或 EDIFACT-编码的事务集。  
  
   > [!NOTE]
   >  将有一个实例的批处理业务流程的每个活动批配置，每个订阅一个具体的批处理 id。 创建新的批处理配置中时自动设置批 ID 值**标识**一部分**批处理配置**页的单向协议选项卡的**协议属性**对话框。  
  
6. 批处理业务流程会验证每个事务集要进行批处理。 如果事务集未能通过验证，则将设置`EDI.BatchItemValidationFailure`上下文属性设置为"True"。 **BatchSuspend**业务流程提取消息根据该上下文属性，发布错误信息，且然后暂停。  
  
7. 当已满足批发布条件时，批处理业务流程将批元素组装为一个批，并创建信封。  
  
8. 批处理业务流程完成的批处理交换后，它将升级该交换的以下属性：EDI。DestinationPartyName = %partyname%，EDI。BatchEncodingType = X12 或 EDIFACT，并且 EDI。ToBeBatched = False。  
  
9. 发送端口提取基于 EDI 的批处理的事务集。DestinationPartyName = \<PartyName\>，EDI。BatchEncodingType = EDIFACT 或 X12 以及 EDI。ToBeBatched = False。  
  
## <a name="batching-orchestration-control-messages"></a>批处理业务流程控制消息  
 激活批处理业务流程、 将其终止，或由下列控制消息重写：  
  
- **BatchActivation**:业务流程收到此消息，创建的批处理业务流程实例和业务流程处于活动状态以接收批元素 （如果符合批处理激活条件）。 单击，即可发送此控制消息**启动**批配置上的按钮**批处理配置**页的单向协议选项卡的**协议属性**对话框。  
  
- **BatchTermination**:业务流程收到此消息，它基于现有批元素创建批、 将消息发布到 MessageBox，并终止。 单击，即可发送此控制消息**停止**批配置上的按钮**批处理配置**页的单向协议选项卡的**协议属性**对话框。  
  
  > [!NOTE]
  >  如果达到指定的时间，则也会终止该业务流程**最终由**属性中的**终止**一部分**批处理配置**页单向协议选项卡**协议属性**对话框。  
  
- **BatchOverride**:业务流程收到此消息，它根据现有元素创建批、 将消息发布到 MessageBox，然后等待下一批消息。 单击，即可发送此控制消息**重写**批配置上的按钮**批处理配置**页的单向协议选项卡的**协议属性**对话框。  
  
  批处理业务流程接收控制消息通过 BatchControlMessageRecvLoc 接收位置。 该 SQL 接收位置的轮询间隔为 30 秒，默认情况下设置，但可以在中更改**SQL 传输属性**接收位置对话框。 缩短轮询间隔可确保 BatchControlMessageRecvLoc 接收位置将接收控制消息后执行的操作的控制消息 （如启动批处理业务流程） 发送。  
  
  在启动批处理业务流程时，将执行以下步骤：  
  
1. 当您单击**启动**按钮，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]一个数据表，说明你正在激活的批处理业务流程的参与方和批 id 创建一条记录。  
  
2. SQL 适配器与 BatchControlMessageRecvLoc 接收位置轮询，以查看是否在数据库中存在该记录。  
  
3. 如果存在记录，SQL 适配器生成控制消息，使用该记录中的信息。  
  
   > [!NOTE]
   >  生成控制消息以这种方式可确保无效控制消息，不能启动业务流程。  
  
4. BatchControlMessageRecvLoc 接收位置接收控制消息和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]激活批处理业务流程实例。  
  
## <a name="batch-components"></a>批组件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI XML 事务集批处理成 EDI 交换使用以下组件：  
  
- EDI 中的 BatchMarkerReceivePipelineComponent 接收管道  
  
- 路由业务流程  
  
- 批处理业务流程  
  
- 升级批处理业务流程  
  
- BatchSuspend 业务流程  
  
- EDI 发送管道  
  
  安装和配置时作为 Dll 安装这些组件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]EDI 和 AS2。  
  
> [!NOTE]
>  中的批处理组件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]EDI 和 AS2 并不能保证批处理中事务的排序集。  
  
### <a name="batchmarkerreceivepipelinecomponent"></a>BatchMarkerReceivePipelineComponent  
 EDI 中的 BatchMarkerReceivePipelineComponent 接收管道批处理业务流程中，选取要进行批处理消息。 在 EDI 接收管道的拆装器之后应用此管道组件。 该组件中设置的筛选器条件的计算结果**筛选器**一部分**批处理配置**的单向协议选项卡的页面**协议属性**对话框中，并将标记的事务集与用于处理由路由和批处理业务流程的以下上下文属性  
  
- 如果某一参与方订阅要进行批处理的消息，它会升级`ToBeBatched = True`并将 BatchId 设置为匹配批配置的批 id 值。 这样，批处理业务流程即可进行提取。  
  
- 如果多个批订阅要进行批处理的消息，它会升级`ToBeRouted = True`，并设置`EDI.BatchIds`属性设置为以空格分隔的批 Id 列表。 这样，路由业务流程即可进行提取。  
  
- 如果不存在任何订阅，它不会升级上下文属性。 这表示事务集是不是要进行批处理。  
  
  管道组件将忽略 XML 以外的消息和消息`ReuseEnvelope`属性 （保留批）。 如果确认是不是要进行批处理，管道组件将忽略 ACK 消息类型 （CONTRL、 TA1 和 997）。 若要优化处理的路由和批处理业务流程，batchmarkerpipelinecomponent 应将消息传递到 MessageBox 如果消息上下文属性`MessageDestination`拆装器设置为"SuspendedQueue"。  
  
  如果使用自定义管道，而不是 EDIReceive 管道，可以在自定义管道中使用 BatchMarker 组件。 如果您使用不 EDIReceive 管道，并且要发布来自业务流程的消息，你必须升级`ToBeBatched = True`和`BatchID`的其中一个组件中的活动批 id。  
  
### <a name="routing-orchestration"></a>路由业务流程  
 订阅具有上下文属性的任何消息，路由业务流程`ToBeRouted = True`的上下文属性`EDI.BatchIds`设置为以空格分隔的批 Id 列表。 多个批处理筛选器订阅要进行批处理的消息时，将发生这种情况。 路由业务流程将使每个批 ID 包含在消息的副本`EDI.BatchIds`。 它使用两个新的上下文属性标记每个副本：  
  
- `EDI.BatchID`它设置为此消息适用于的批处理 ID。  
  
- `EDI.ToBeBatched`它设置为 True。  
  
  然后将副本路由到 MessageBox，以拾取批处理业务流程。 每个目标批 ID 上特定的批处理 id。 在筛选器使用同一业务流程的单一实例  
  
### <a name="batching-orchestration"></a>批处理业务流程  
 批处理业务流程是缓冲时间段内，批元素 （事务集） 的有状态服务组合成一个交换，，然后将交换发布到发送管道根据发布标准。  
  
 正在激活后，批处理业务流程的实例即可开始到给定参与方将特定编码类型的消息批处理 (如果**启动**日期时间已过)。 在任何时候都可以有多个实例的每个参与方，每个活动批配置的其中一个批处理业务流程。 批处理业务流程的单个实例可以发布单个批配置的多个批。 符合结束标准后，将终止批处理业务流程实例。 批处理业务流程的新实例将需要手动从贸易合作伙伴管理 (TPM) 创建使用**启动**按钮。  
  
 如果批处理业务流程开始之前开始日期时间中所示**激活**部分上的**批处理配置**页的单向协议选项卡的**协议属性**对话框中，它将仅接收在激活范围内指定的消息。 它不会收到消息开始日期时间之前发送。  
  
 批处理业务流程将执行以下操作：  
  
-   订阅具有上下文属性的 XML 批元素`EDI.ToBeBatched = True`并`EDI.BatchId`批配置 ID 或`EDI.ToBeBatched = True`和 EDI。BatchName = 已配置的批和 EDI 的名称。DestinationPartyName = 包含此批配置的参与方名称。 接收批元素使用**接收**在循环中的操作。  
  
    > [!NOTE]
    >  批处理业务流程不会批处理事务集的筛选器部分中设置的筛选器条件基于**批处理配置**页的单向协议选项卡的**的协议属性**对话框。 订阅具有上述上下文属性设置它们的事务集。 BatchMarker 管道组件设置，并将根据参与方属性中的筛选器设置这些上下文属性升级。  
  
-   检索批处理的配置设置中标识的参与方`BatchId`上下文属性。  
  
-   验证基于参与方设置的批元素 （事务集）。  
  
-   如果批元素时出现错误，批处理业务流程将升级该事务集的以下属性： `EDI.BatchItemValidationFailure = True`。 **BatchElementSuspend**业务流程订阅已升级此属性设置任何事务。 此业务流程将提供详细的错误信息在批处理交换中遇到的第一个错误。  
  
-   如果批处理元素中没有错误，保留对该批元素的引用。  
  
-   当收到相应控制消息或符合批处理发布标准时，跳出**接收**操作循环，从 MessageBox 检索所有批元素，并组装交换。  
  
-   将上下文属性设置`ToBeBatched = False`对交换的上下文属性 DestinationPartyName = %partyname%，其中 %partyname%是消息面向的参与方的名称。  
  
    > [!NOTE]
    >  如果发送端口订阅一个或两个属性`EDI.ToBeBatched = False`和 EDI。DestinationPartyName = %partyname%，该发送端口可以提取批处理交换。 请确保发送端口的筛选器的配置，以便最多的批交换它仅是发送端口提取应提取。  
  
    > [!NOTE]
    >  批处理业务流程到 MessageBox 的交换具有仅属性`EDI.ToBeBatched = False`，EDI。DestinationPartyName = %partyname%和 EDI。BatchEncodingType ="X12"或"EDIFACT"升级到上下文。 原始事务集的所有上下文属性都都将丢失。  
  
-   对于 X12 编码的交换，向信封应用下列属性：  
  
    -   ISA6:交换发送方 ID  
  
    -   ISA8:交换接收方 ID  
  
    -   ISA15:用法指示符  
  
    -   ISA_Blob （写入到上下文）  
  
-   对于 EDIFACT 编码的交换，向信封应用下列属性：  
  
    -   UNB2.1:交换发送方 ID  
  
    -   UNB3.1:交换接收方 ID  
  
    -   UNB2.3:反向路由地址  
  
    -   UNB11:用法指示符  
  
    -   UNA_Blob （写入到上下文）  
  
    -   UNB_Blob （写入到上下文）  
  
-   通过 EDI 发送管道将批的交换传送到 MessageBox 进行选取。  
  
### <a name="upgradebatching-orchestration"></a>UpgradeBatching 业务流程  
 UpgradeBatching 业务流程处理消息`EDI.ToBeBatched`属性设置为 true，但不是具有`EDI.BatchID`属性集。  
  
 在以前版本的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，每个参与方可以只有一个批配置。  当处理消息时`EDI.ToBeBatched`设置为 true，`EDI.DestinationPartyId`用于确定参与方，然后从协议属性读取批配置。  
  
 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，每个参与方可以有多个批处理配置与之关联，因此`EDI.DestinationPartyId`不提供足够的信息来确定应使用哪个批配置。  当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收消息，消息`EDI.BatchId`属性用于标识处理某个消息时，应使用哪个特定批配置。  
  
 升级到之后[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，你可能仍需要使用的自定义管道`EDI.DestinationPartyId`属性指定参与方配置。 当收到消息具有`EDI.ToBeBatched`设置为 true，并且具有`EDI.DestinationPartyID`而不是 EDI 设置。BatchID，UpgradeBatching 业务流程尝试确定应使用哪个批配置。  
  
 UpgradeBatching 业务流程使用以下订阅筛选器来订阅标记为批处理，但未指定批 ID 的文档：  
  
- `EDI.ToBeBatched=True`  
  
- `EDI.EncodingType` 存在  
  
- `EDI.DestinationPartyId` 存在  
  
  业务流程收到一条消息，它将尝试通过使用参与方名称和编码类型查找的消息匹配的批配置。  `EDI.DestinationPartyID`属性用于确定参与方名称，然后业务流程查找匹配的批名称\<PartyName\>+\<EncodingType\>+ Default。  例如，如果参与方名称是 Contoso 和的值为`EDI.EncodingType`为 X12，则该业务流程将查找名为 ContosoX12Default 的批。  
  
  如果找到匹配的批配置，则将消息放在消息框具有以下属性：  
  
- `EDI.ToBeBatched = True`  
  
- `EDI.ToBeRouted = False`  
  
- EDI。BatchId = 匹配批的批 ID  
  
  然后，批处理业务流程将处理该消息  
  
> [!NOTE]
>  如果找到任何匹配的批处理，则将发生以下情况：  
> 
> - 消息不会发送给 BatchSuspend 业务流程中。  
>   -   UpgradeBatching 业务流程实例和消息将被挂起。  
>   -   错误将记录到事件日志消息指出找不到一批。  
  
### <a name="batchsuspend-orchestration"></a>BatchSuspend 业务流程  
 BatchSuspend 业务流程处理收到的批处理业务流程无效消息。 需要 BatchSuspend 业务流程，因为没有直接方法而无需停止业务流程的实例的执行挂起业务流程 （在此情况下，批处理业务流程） 中的消息。  
  
 当批处理业务流程实例收到消息时，它会尝试对其进行验证。 如果消息验证失败，批处理业务流程创建一个 BatchSuspend 业务流程，实例并设置`EDI.BatchItemValidationFailure`上下文属性设为 True。 BatchSuspend 业务流程订阅的所有消息，该上下文属性设置为 True。 无效的事务集路由到 BatchSuspend 业务流程后，BatchSuspend 业务流程实例已挂起。  
  
 BatchSuspend 业务流程提供了详细的错误信息时遇到的第一个错误。  
  
 可以创建自定义业务流程处理事务集未能通过验证由批处理业务流程，使用的`EDI.BatchElementValidationFailure`筛选器中的属性。  
  
### <a name="edi-send-pipeline"></a>EDI 发送管道  
 后从批处理业务流程收到批的交换，EDI 发送管道执行以下任务：  
  
-   对于 X12 编码的交换，发送管道会向信封应用下列属性：  
  
    -   ISA2:授权信息  
  
    -   ISA4:安全信息  
  
    -   ISA9:交换日期  
  
    -   ISA10:交换时间  
  
    -   ISA13:交换控制编号  
  
    -   GS4:Date  
  
    -   GS5:Time  
  
    -   GS6:组控制编号  
  
    -   ST2:事务集控制编号  
  
-   对于 EDIFACT 编码的交换，发送管道会向信封应用下列属性：  
  
    -   UNB4.1:Date  
  
    -   UNB4.2:Time  
  
    -   UNB5:交换控制参考  
  
    -   UNB6.1:收件人引用密码  
  
    -   UNG4.1:Date  
  
    -   UNG4.2:Time  
  
    -   UNG5:功能组参考  
  
    -   UNG8:应用程序密码  
  
-   通过关联适配器的消息传递  
  
## <a name="see-also"></a>请参阅  
 [对传出 EDI 消息进行批处理](../core/batching-outgoing-edi-messages.md)