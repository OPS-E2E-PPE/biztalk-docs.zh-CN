---
title: "组合批处理的 EDI 交换 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 18f64595-935e-4d52-9ec2-5edf7c2b9e83
caps.latest.revision: "45"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43d7a54305443d35aba5b363983b17157780fe4b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="assembling-a-batched-edi-interchange"></a>装配批处理的 EDI 交换
为了将各个事务集批元素组装成 EDI 交换，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI 和 AS2 将执行下列操作：  
  
-   标识要进行批处理的批元素  
  
-   收到各个批元素后对其进行验证和缓冲  
  
-   检索特定批元素，如果满足发布标准，则组装批交换  
  
 收集各个消息以组合成批的开始时间是根据批处理激活标准确定的， 批的发布时间是根据批发布标准确定的。 有关条件这两个集的详细信息，请参阅[配置传出批处理](../core/configuring-an-outgoing-batch.md)。  
  
## <a name="message-flow-for-outgoing-batched-messages"></a>传出批处理消息的消息流  
 当 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置为对传出消息进行批处理时，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 组件将执行下面的一系列步骤，来准备要发送的批处理消息。 这一系列的步骤描述了这样一种情况：具有 BatchMarker 管道组件的 EDIReceive 管道处理收到的交换，这些交换包含要成批进行发送的事务集。  
  
1.  EDIReceive 管道中的 BatchMarker 管道组件通过参与方属性中的 EDI 批处理筛选器设置，确定需要进行批处理的消息。 （该组件是唯一一个查看批处理筛选器设置并根据这些设置进行处理的批处理组件。）  
  
2.  如果仅一个批配置的筛选器设置订阅消息，则 BatchMarker 组件将升级属性 `EDI.ToBeBatched = True`。 这样可确保批处理业务流程将提取该消息。  
  
3.  如果多个批配置的筛选器设置与消息上下文匹配，则 BatchMarker 组件将升级属性 `EDI.ToBeRouted = True`，并将 `EDI.BatchIds` 属性设置为以空格分隔的匹配批 ID 列表。  这样可确保路由业务流程将订阅该消息。  
  
    > [!NOTE]
    >  您可以在自定义接收管道或自定义业务流程中升级相应的上下文属性。 自定义接收管道可使用 BatchMarker 管道组件，或者在不使用 BatchMarker 管道组件的情况下升级属性。  
  
4.  路由业务流程提取为其升级了 `EDI.ToBeRouted = True` 和 `EDI.BatchIds` 的任何事务集，然后创建该事务集的副本，以确保 `EDI.BatchIds` 中包含每个批 ID 的一个副本。 路由业务流程将设置 `EDI.ToBeBatched = True`，且每个事务集副本的 `EDI.BatchId` 将设置为匹配批配置的批 ID。 这样可确保批处理业务流程会提取事务集以便进行批处理。  
  
5.  批处理业务流程提取已升级下列属性的所有消息：  
  
    -   与此批处理业务流程实例相关的批的 `EDI.ToBeBatched = True` 和 EDI.BatchId = 批 ID。  
  
    -   `EDI.ToBeBatched = True` 和 EDI.BatchName = 已配置批的名称，且 EDI.DestinationPartyName = 包含此批配置的参与方名称。  
  
     当具有 BatchMarker 管道组件的 EDIReceive 管道处理传入消息时，批处理业务流程将仅对 X12 或 EDIFACT 编码的事务集进行批处理。  
  
    > [!NOTE]
    >  对于每个活动批配置，都将有一个批处理业务流程的实例，并且每个实例订阅一个特定的批 ID。 创建新的批处理配置中时自动设置批次 ID 值**标识**部分**批处理配置**的单向协议选项卡页**协议属性**对话框。  
  
6.  批处理业务流程会验证要进行批处理的每个事务集。 如果事务集未能通过验证，则会将 `EDI.BatchItemValidationFailure` 上下文属性设置为“True”。 **BatchSuspend** orchestration 拾取基于该上下文属性的消息，发送错误信息，然后已挂起。  
  
7.  当满足批发布条件时，批处理业务流程将批元素组装为一个批，并创建信封。  
  
8.  在批处理业务流程完成某个交换的批处理之后，它将升级该交换的以下属性：EDI.DestinationPartyName = %PartyName%，EDI.BatchEncodingType = X12 或 EDIFACT，并且 EDI.ToBeBatched = False。  
  
9. 发送端口选取基于 EDI 的批处理的事务集。DestinationPartyName = \<PartyName >，EDI。BatchEncodingType = EDIFACT 或 X12，和 EDI。ToBeBatched = False。  
  
## <a name="batching-orchestration-control-messages"></a>批处理业务流程控制消息  
 批处理业务流程由下列控制消息激活、终止或重写：  
  
-   **BatchActivation**： 时业务流程会收到此消息，将创建批处理的业务流程的实例并且业务流程是活动状态，以接收批处理元素 （如果它满足批激活条件）。 通过单击发送此控件消息**启动**按钮上的批处理配置**批处理配置**的单向协议选项卡页**协议属性**对话框。  
  
-   **BatchTermination**： 当业务流程收到此消息时，它创建从现有的批处理元素的一批、 将消息发布到 MessageBox，并终止。 通过单击发送此控件消息**停止**按钮上的批处理配置**批处理配置**的单向协议选项卡页**协议属性**对话框。  
  
    > [!NOTE]
    >  如果达到指定的时间，也会被终止业务流程**结束于**中的属性**终止**部分**批处理配置**页单向协议选项卡**协议属性**对话框。  
  
-   **BatchOverride**： 当业务流程收到此消息时，它创建从现有元素的一批，将消息发布到 MessageBox，，然后等待下一批消息。 通过单击发送此控件消息**重写**按钮上的批处理配置**批处理配置**的单向协议选项卡页**协议属性**对话框。  
  
 批处理业务流程通过 BatchControlMessageRecvLoc 接收位置接收控制消息。 此 SQL 接收位置的轮询间隔为 30 秒的默认设置，但可以更改在**SQL 传输属性**接收位置的对话框。 缩短轮询间隔可确保 BatchControlMessageRecvLoc 接收位置将在您执行控制消息发送操作之后（如启动批处理业务流程时）会立即收到控制消息。  
  
 当您启动批处理业务流程时，将执行下列步骤：  
  
1.  当你单击**启动**按钮， [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ，该值指示你正在激活的批处理业务流程的当事方和批处理 id 表中创建一条记录。  
  
2.  与 BatchControlMessageRecvLoc 接收位置关联的 SQL 适配器将进行轮询，以查看数据库中是否存在该记录。  
  
3.  如果该记录存在，SQL 适配器将使用该记录中的信息生成一条控制消息。  
  
    > [!NOTE]
    >  通过此种方式生成控制消息可确保无效控制消息无法启动业务流程。  
  
4.  BatchControlMessageRecvLoc 接收位置接收控制消息后，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 会激活批处理业务流程实例。  
  
## <a name="batch-components"></a>批组件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI 使用下列组件将 XML 事务集批处理成 EDI 交换：  
  
-   EDI 接收管道中的 BatchMarkerReceivePipelineComponent  
  
-   路由业务流程  
  
-   批处理业务流程  
  
-   升级批处理业务流程  
  
-   BatchSuspend 业务流程  
  
-   EDI 发送管道  
  
 这些组件在您安装和配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI 及 AS2 时作为 DLL 安装。  
  
> [!NOTE]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI 和 AS2 中的批处理组件无法保证批处理中事务集的排序。  
  
### <a name="batchmarkerreceivepipelinecomponent"></a>BatchMarkerReceivePipelineComponent  
 通过 EDI 接收管道中的 BatchMarkerReceivePipelineComponent，批处理业务流程可以提取要进行批处理的消息。 应用 EDI 接收管道中的拆装器之后即可应用该管道组件。 该组件的计算结果中设置的筛选器条件**筛选器**部分**批处理配置**的单向协议选项卡页**协议属性**对话框中，以及标记事务集具有处理的路由和批处理业务流程的以下上下文属性  
  
-   如果只有一个参与方订阅要进行批处理的消息，则它会升级 `ToBeBatched = True`，并将 BatchId 设置为匹配批配置的批 ID 值。 这样，批处理业务流程即可进行提取。  
  
-   如果多个批订阅要进行批处理的消息，则它会升级 `ToBeRouted = True`，并将 `EDI.BatchIds` 属性集设置为以空格分隔的批 ID 列表。 这样，路由业务流程即可进行提取。  
  
-   如果不存在任何订阅，则不会升级上下文属性。 这表示不会对事务集进行批处理。  
  
 管道组件将忽略除 XML 和具有 `ReuseEnvelope` 属性的消息（保留批）之外的消息。 如果不对确认进行批处理，则管道组件将忽略确认类型的消息（CONTRL、TA1 和 997）。 若要优化路由和批处理业务流程的处理过程，BatchMarkerPipelineComponent 应将消息传递到 MessageBox（如果拆装器将消息上下文属性 `MessageDestination` 设置为“SuspendedQueue”）。  
  
 如果您使用的是自定义管道，而不是 EDIReceive 管道，那么您可以在自定义管道中使用 BatchMarker 组件。 如果您使用的不是 EDIReceive 管道，并且要发布来自业务流程的消息，则必须将 `ToBeBatched = True` 和 `BatchID` 升级到其中一个组件中的活动批 ID。  
  
### <a name="routing-orchestration"></a>路由业务流程  
 路由业务流程订阅任何具有以下特性的消息：上下文属性 `ToBeRouted = True`，并且上下文属性 `EDI.BatchIds` 设置为以空格分隔的批 ID 列表。 当多个批处理筛选器订阅要进行批处理的消息时会出现此情况。 路由业务流程将为 `EDI.BatchIds` 中包含的每个批 ID 生成此消息的一个副本， 并使用以下两个新上下文属性标记每个副本：  
  
-   `EDI.BatchID`，将此属性设置为此消息要使用的批 ID。  
  
-   `EDI.ToBeBatched`，将此属性设置为 True。  
  
 然后再将副本路由到 MessageBox，以供批处理业务流程提取。 每个目标批 ID 使用同一业务流程的单个实例，并在具体批 ID 上包含一个筛选器。  
  
### <a name="batching-orchestration"></a>批处理业务流程  
 批处理业务流程是具有状态的服务，它在一段时间内缓冲批元素（事务集），将其组装为交换，然后再根据发布标准将交换发布到发送管道。  
  
 正在激活后，批处理的业务流程的实例可以启动对特定的编码类型到给定方的消息进行批处理 (如果**启动**日期时间已过)。 在任何时候，每个参与方都可以有许多批处理业务流程实例，每个活动批配置有一个实例。 一个批处理业务流程实例可以为一个批配置发布多个批。 符合结束标准后，批处理业务流程实例将终止。 批处理的业务流程的新实例将需要手动从贸易合作伙伴管理 (TPM) 中创建使用**启动**按钮。  
  
 如果批处理业务流程将启动早于开始日期中所示的日期时间**激活**部分上的**批处理配置**的单向协议选项卡页**协议属性**对话框中，它将仅收到激活范围中指定的消息。 而不会接收在此开始日期时间之前发送的消息。  
  
 批处理业务流程可执行下列操作：  
  
-   订阅具有以下上下文属性的 XML 批元素：`EDI.ToBeBatched = True` 和 `EDI.BatchId` = 批配置 ID；或者 `EDI.ToBeBatched = True` 和 EDI.BatchName = 已配置批的名称，且 EDI.DestinationPartyName = 包含此批配置的参与方名称。 收到批处理元素使用**接收**操作在循环中的操作。  
  
    > [!NOTE]
    >  批处理的业务流程不批处理事务集基于设置的筛选器部分中的筛选器条件**批处理配置**的单向协议选项卡页**协议属性**对话框。 该业务流程会订阅设置了上述上下文属性的事务集。 BatchMarker 管道组件根据参与方属性中的筛选器设置来设置和升级这些上下文属性。  
  
-   为 `BatchId` 上下文属性中标识的参与方检索批处理的配置设置。  
  
-   根据参与方设置验证批元素（事务集）。  
  
-   如果批元素发生错误，则批处理业务流程将升级该事务集的以下属性： `EDI.BatchItemValidationFailure = True`。 **BatchElementSuspend** orchestration 订阅为已提升此属性设置的任何事务。 此业务流程将提供在批处理交换中遇到的第一个错误的详细错误信息。  
  
-   如果批元素中没有任何错误，则会保留对该批元素的引用。  
  
-   当接收到相应的控件消息或满足批处理版本条件时，将中断外**接收**操作循环，从消息框中，检索所有批处理元素和组装交换。  
  
-   对交换的上下文属性进行如下设置：`ToBeBatched = False`，且 DestinationPartyName = %PartyName%，其中 %PartyName% 是消息面向的参与方的名称。  
  
    > [!NOTE]
    >  如果发送端口订阅属性 `EDI.ToBeBatched = False` 和 EDI.DestinationPartyName = %PartyName% 中的一个，或者同时订阅两个属性，该发送端口可提取批交换。 请确保配置发送端口的筛选器，使该筛选器仅提取应提取的批交换。  
  
    > [!NOTE]
    >  批处理业务流程放到 MessageBox 中的交换只将属性 `EDI.ToBeBatched = False`、EDI.DestinationPartyName = %PartyName% 和 EDI.BatchEncodingType = "X12" 或 "EDIFACT" 升级到上下文。 原始事务集的所有上下文属性将丢失。  
  
-   对于 X12 编码的交换，请向信封应用下列属性：  
  
    -   ISA6：交换发送方 ID  
  
    -   ISA8：交换接收方 ID  
  
    -   ISA15：用法指示符  
  
    -   ISA_Blob（写入到上下文）  
  
-   对于 EDIFACT 编码的交换，请向信封应用下列属性：  
  
    -   UNB2.1：交换发送方 ID  
  
    -   UNB3.1：交换接收方 ID  
  
    -   UNB2.3：反向路由的地址  
  
    -   UNB11：用法指示符  
  
    -   UNA_Blob（写入到上下文）  
  
    -   UNB_Blob（写入到上下文）  
  
-   将批交换传送给 MessageBox，以供 EDI 发送管道提取。  
  
### <a name="upgradebatching-orchestration"></a>UpgradeBatching 业务流程  
 UpgradeBatching 业务流程处理 `EDI.ToBeBatched` 属性设置为 True，但是没有设置 `EDI.BatchID` 属性的消息。  
  
 在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的早期版本中，每个参与方只能有一个批配置。  当处理 `EDI.ToBeBatched` 设置为 True 的消息时，`EDI.DestinationPartyId` 用于确定参与方，然后从协议属性读取批配置。  
  
 在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，每个参与方可以有多个关联的批配置，因此 `EDI.DestinationPartyId` 不会提供足够的信息用于确定应该使用哪个批配置。  当 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 收到消息时，`EDI.BatchId` 属性将用于识别处理消息时具体应该使用哪个批配置。  
  
 升级到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 以后，您仍然有使用 `EDI.DestinationPartyId` 属性指定参与方配置的自定义管道。 当收到将 `EDI.ToBeBatched` 设置为 True 的消息，且设置了 `EDI.DestinationPartyID` 而不是 EDI.BatchID 时，UpgradeBatching 业务流程会尝试确定应该使用哪个批配置。  
  
 UpgradeBatching 业务流程使用以下订阅筛选器来订阅标记为批处理，但未指定批 ID 的文档：  
  
-   `EDI.ToBeBatched=True`  
  
-   `EDI.EncodingType` exists  
  
-   `EDI.DestinationPartyId` exists  
  
 当业务流程收到消息时，它会尝试使用参与方名称和编码类型为此消息查找匹配的批设置。  `EDI.DestinationPartyID`属性用于确定当事方名称，并随后业务流程查找相匹配的批处理名称\<PartyName > +\<EncodingType > + 默认。  例如，如果参与方名称为 Contoso，且 `EDI.EncodingType` 的值为 X12，则业务流程将查找名为 ContosoX12Default 的批。  
  
 如果找到匹配的批配置，则会将此消息以及下列属性放回消息框：  
  
-   `EDI.ToBeBatched = True`  
  
-   `EDI.ToBeRouted = False`  
  
-   EDI.BatchId = 匹配批的批 ID  
  
 然后，批处理业务流程将处理该消息  
  
> [!NOTE]
>  如果没有找到匹配的批，则会出现以下情况：  
>   
>  -   不会将此消息发送给 BatchSuspend 业务流程。  
> -   UpgradeBatching 业务流程实例和消息将被挂起。  
> -   事件日志中将记录一个错误，说明找不到批。  
  
### <a name="batchsuspend-orchestration"></a>BatchSuspend 业务流程  
 BatchSuspend 业务流程处理批处理业务流程收到的无效消息。 需要 BatchSuspend 业务流程的原因是：无法在不停止执行业务流程实例的情况下直接挂起业务流程（在本示例中为批处理业务流程）中的消息。  
  
 当批处理业务流程实例收到消息时，会尝试验证该消息。 如果消息验证失败，批处理业务流程将创建一个 BatchSuspend 业务流程实例，并将 `EDI.BatchItemValidationFailure` 上下文属性设置为 True。 BatchSuspend 业务流程订阅该上下文属性设置为 True 的所有消息。 在将无效事务集路由到 BatchSuspend 业务流程后，BatchSuspend 业务流程实例将挂起。  
  
 此 BatchSuspend 业务流程将提供遇到的第一个错误的详细错误信息。  
  
 您可以创建自定义业务流程，使用筛选器中的 `EDI.BatchElementValidationFailure` 属性处理未通过批处理业务流程验证的事务集。  
  
### <a name="edi-send-pipeline"></a>EDI 发送管道  
 从批处理业务流程收到批交换后，EDI 发送管道将执行下列操作：  
  
-   对于 X12 编码的交换，发送管道会向信封应用下列属性：  
  
    -   ISA2：授权信息  
  
    -   ISA4：安全信息  
  
    -   ISA9：交换日期  
  
    -   ISA10：交换时间  
  
    -   ISA13：交换控制编号  
  
    -   GS4：日期  
  
    -   GS5：时间  
  
    -   GS6：组控制编号  
  
    -   ST2：事务集控制编号  
  
-   对于 EDIFACT 编码的交换，发送管道会向信封应用下列属性：  
  
    -   UNB4.1：日期  
  
    -   UNB4.2：时间  
  
    -   UNB5：交换控制参考  
  
    -   UNB6.1：收件人引用密码  
  
    -   UNG4.1：日期  
  
    -   UNG4.2：时间  
  
    -   UNG5：功能组参考  
  
    -   UNG8：应用程序密码  
  
-   通过关联适配器传送消息  
  
## <a name="see-also"></a>另请参阅  
 [对传出的 EDI 消息进行批处理](../core/batching-outgoing-edi-messages.md)