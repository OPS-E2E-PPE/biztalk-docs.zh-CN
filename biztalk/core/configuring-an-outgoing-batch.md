---
title: 配置传出批处理 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 75e6f41a-0e24-47bf-9234-125791c62044
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de6b7ef0a8683374322d4b6f720bc1ebd1ed4b06
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22234613"
---
# <a name="configuring-an-outgoing-batch"></a>配置传出批
若要定义 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将事务集批处理成 EDI 交换的方式，必须为协议创建一个或多个批配置。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 与该协议关联并且符合批筛选条件的所有交换，将遵循该批配置的发布条件进行批处理和发布。  
  
 批配置由批名称、 批次 ID、 筛选器定义、 组定义、 批释放条件和批激活条件组成。 所有属性和与批处理相关的选项都位于**批配置**页中的单向协议选项卡**协议属性**对话框。 若要创建协议某个批配置，请参阅[配置批处理 (X12)](../core/configuring-batching-x12.md)。  
  
> [!NOTE]
>  标准批处理文档被确定从协议属性本身。 例如，如果协议用于 X12 消息，文档标准，用于批处理将 X12。  
  
## <a name="batch-categories"></a>批处理类别  
 使用右上角的下拉列表**批配置**页后，可以确定显示哪些批处理配置的。  
  
-   **所有**： 显示所有批处理配置。  
  
-   **Active**： 显示仅 active 批处理配置。  
  
-   **非活动**： 显示仅非活动的批处理配置。  
  
## <a name="batch-identification"></a>批处理标识  
 批处理标识包含批名称、 描述、 批次 ID 和批处理的业务流程实例 id。  
  
### <a name="batch-name"></a>批名称  
 根据中指定的批处理名称创建某个批配置**批配置**页中的单向协议选项卡**协议属性**对话框。 多个批处理可以共享相同的配置设置，但必须具有唯一的批次的名称。  
  
### <a name="batch-description"></a>批说明  
 批处理说明文本框中提供的批配置的说明。  
  
### <a name="batch-id"></a>批次 ID  
 自动生成批次 ID[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]中创建新的批配置时**批配置**页。 此值是 BatchMarker 管道组件用于标记某个特定批配置的批处理筛选器匹配的传入交换。 此值还用作批处理业务流程与特定的批处理配置关联的订阅筛选器。  
  
### <a name="orchestration-instance-id"></a>业务流程实例 ID  
 为此批配置激活批处理 orchestration 实例的业务流程实例 ID。  
  
## <a name="batch-filter"></a>批处理筛选器  
 并且创建一个批处理在应用中的批处理筛选器定义的基础**批配置**页中的单向协议选项卡**协议属性**对话框。 在此筛选器中，可确定批处理哪些事务集或消息。 激活批处理业务流程实例后，可以更改此筛选器的值。 更改筛选器不会影响批释放条件。  
  
> [!NOTE]
>  如果你更改的活动的批次的批次筛选器，它将需要为新的筛选条件，要变为活动状态，因为此信息由 Biztalk Server 缓存 15 分钟。 此刷新时间间隔不能修改。  
>   
>  若要强制新的筛选器要立即变为活动状态，重新启动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]主机进程。  
  
 传出批处理可以包括多个组，但只有一个组，每个事务类型。 一个组可以包含多个事务集，但每个必须具有相同的事务类型。  
  
 多个批处理配置可以共享相同的批处理筛选器，如果文档与它将路由到匹配的所有批的多个批处理筛选器匹配。  
  
## <a name="group-definition"></a>组定义  
 你确定如何组将通过批处理输出通过定义功能组标头 (对于 X12 GS) 和 UNG 对于 EDIFACT 协议属性中。 对组的定义则依据其事务集标识符 (ST1)（针对 X12）或消息类型 (UNH2.1)（针对 EDIFACT）、版本及其目标命名空间进行。 例如，交换可包含两个组，一个由一种消息类型构成，另一个由另一种消息类型构成。 有关配置组的详细信息，请参阅[配置 EDI 属性](../core/configuring-edi-properties.md)。  
  
> [!NOTE]
>  对于组在交换中的顺序，则不定义。  
  
## <a name="batch-release-criteria"></a>批释放条件  
 将根据在中设置的条件发布批**批配置**页中的单向协议选项卡**协议属性**对话框。 可按以下任一方式发布批处理：  
  
-   按照计划，在每小时、 每天或每周的基础上。  
  
-   当为一组可用时特定数量的事务集。  
  
-   特定数量的事务集时可用的交换。  
  
-   特定数量的字符何时可用于批处理。  
  
-   一个外部触发器执行的外部的应用程序的时间[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
 如果你选择**发送空批处理信号**属性**批处理计划**对话框中，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]批处理计划即使没有消息已发送时将发送一条空批处理消息收到批处理业务流程。  
  
## <a name="batch-activation-criteria"></a>批次激活条件  
 仅当已满足批处理激活条件时，将根据批释放条件发布批。 若要激活的业务流程的实例，必须按**启动**按钮**批配置**页中的单向协议选项卡**协议属性**对话框。 这将创建批配置业务流程的实例。 如果**启动**按钮可用于单击，批配置业务流程的实例当前未被激活。  
  
 按后**启动**按钮，将会收集一批消息，仅当满足以下条件：  
  
-   消息符合批处理筛选器中规定的条件。  
  
-   日期和时间后进入的日期时间**启动**字段。  
  
-   日期和时间是在输入中的值之前**结束**字段或处理的批处理的数字是小于或等于的中的出现次数 **（匹配项） 后的结束**字段或**无结束日期**选项。 所有三个选项下有**终止**部分。  
  
 在中设置激活条件**批配置**页中的单向协议选项卡**协议属性**对话框。  
  
 已按下后**启动**按钮激活批处理的业务流程的实例，直到时间提到的消息将不进行批处理会收集**启动**属性已通过。  在**批配置**页上，如果**立即开始**未选择和**启动**日期时间设置为之前选项可在按时所处的时间值**启动**按钮，批处理将立即开始业务流程处于活动状态。 如果激活日期时间在将来，则将在该时间启动批处理。  
  
 你可以设置**启动**日期时间在将来为日期时间。 但是，如果你单击**启动**按钮时**启动**日期时间是将来，将激活业务流程实例，但将会收集任何消息，直到开始日期时间发生。 BatchMarker 管道组件将不提升将消息路由到路由业务流程或直到开始日期时间批处理业务流程所需的相应属性。 因此不会对消息进行批处理。 但是，任何单独订阅这些消息的发送端口或业务流程仍会提取消息。 有关 BatchMarker 管道组件的作用的详细信息，请参阅[组合批处理的 EDI 交换](../core/assembling-a-batched-edi-interchange.md)。  
  
## <a name="batch-termination-criteria"></a>批处理终止条件  
 消息将停止对收集的一批后**结束**日期时间或之后的中的出现次数 **（匹配项） 后的结束**属性。 如果您不希望批处理的业务流程，以将其停用，则选择**无结束日期**选项。  
  
> [!NOTE]
>  如果 **（匹配项） 后的结束**属性已被选中，空批处理发出信号将计入的批次激活范围终点的所需的出现次数。 如果出现在正常情况下可导致空的批处理信号的条件（在计划应发送批处理时批处理业务流程尚未收到任何消息），出现次数也将递增，但因为未配置空的批处理信号，所以不会发送该信号。  
  
## <a name="see-also"></a>另请参阅  
 [对传出的 EDI 消息进行批处理](../core/batching-outgoing-edi-messages.md)