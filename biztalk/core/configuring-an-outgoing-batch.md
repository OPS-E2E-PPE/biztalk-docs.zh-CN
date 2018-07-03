---
title: 配置传出批 |Microsoft Docs
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
ms.openlocfilehash: 267616af46eeb08e46d35d3a6fd5fdde2a22e877
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003406"
---
# <a name="configuring-an-outgoing-batch"></a>配置传出批
若要定义 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将事务集批处理成 EDI 交换的方式，必须为协议创建一个或多个批配置。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 与该协议关联并且符合批筛选条件的所有交换，将遵循该批配置的发布条件进行批处理和发布。  
  
 批处理配置由批名称、 批 ID、 筛选器定义、 组定义、 批处理发布条件和批处理激活条件组成。 所有属性和与批处理相关的选项都位于**批配置**页中的单向协议选项卡**协议属性**对话框。 若要创建协议的批配置，请参阅[配置批处理 (X12)](../core/configuring-batching-x12.md)。  
  
> [!NOTE]
>  标准批处理文档是已确定协议属性本身。 例如，如果协议适用于 X12 消息的文档标准批将为 X12。  
  
## <a name="batch-categories"></a>批处理类别  
 使用上的右上角的下拉列表**批配置**页，确定显示哪个批配置。  
  
-   **所有**： 显示所有批处理配置。  
  
-   **Active**： 显示仅活动批配置。  
  
-   **非活动**： 显示仅不活动的批配置。  
  
## <a name="batch-identification"></a>批处理标识  
 批处理标识包含批名称、 说明、 批处理 ID 和批处理业务流程实例 id。  
  
### <a name="batch-name"></a>批处理名称  
 根据中指定的批处理名称创建批配置**批配置**页中的单向协议选项卡**协议属性**对话框。 多个批处理可以共享相同的配置设置，但必须具有唯一的批处理的名称。  
  
### <a name="batch-description"></a>批说明  
 批处理说明文本框中提供的批处理配置的说明。  
  
### <a name="batch-id"></a>批次 ID  
 自动生成的批处理 ID[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]中创建新的批配置时**批配置**页。 BatchMarker 管道组件使用此值来标记特定的批处理配置的批处理筛选器匹配的传入的交换。 此值还用作批处理业务流程与特定的批处理配置关联的订阅筛选器。  
  
### <a name="orchestration-instance-id"></a>业务流程实例 ID  
 为此批处理配置激活批处理业务流程实例的业务流程实例 ID。  
  
## <a name="batch-filter"></a>批处理筛选器  
 创建批处理时在应用中的批处理筛选器定义的基础**批配置**页中的单向协议选项卡**协议属性**对话框。 在此筛选器中，可确定批处理哪些事务集或消息。 激活批处理业务流程实例后，可以更改此筛选器的值。 更改筛选器不会影响批处理发布条件。  
  
> [!NOTE]
>  如果更改活动批的批筛选器，它将需要为新的筛选条件，因为此信息缓存由 Biztalk Server 变为活动状态 15 分钟。 此刷新时间间隔不能修改。  
> 
>  若要强制立即处于活动状态的新筛选器，请重新启动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]主机进程。  
  
 传出批处理可包含多个组，但每个事务类型只有一个组。 一个组可以包含多个事务集，但每个必须具有相同的事务类型。  
  
 多个批处理配置可以共享同一个批处理筛选器，如果文档与多个批处理筛选器会将其路由到所有匹配的批处理相匹配。  
  
## <a name="group-definition"></a>组定义  
 您确定如何组将按照在 batch 输出通过定义功能组标头 (对于 X12 为 GS) 和 UNG edifact 协议属性中。 对组的定义则依据其事务集标识符 (ST1)（针对 X12）或消息类型 (UNH2.1)（针对 EDIFACT）、版本及其目标命名空间进行。 例如，交换可包含两个组，一个由一种消息类型构成，另一个由另一种消息类型构成。 有关配置组的详细信息，请参阅[配置 EDI 属性](../core/configuring-edi-properties.md)。  
  
> [!NOTE]
>  对于组在交换中的顺序，则不定义。  
  
## <a name="batch-release-criteria"></a>批处理发布条件  
 将根据在中设置的条件发布批处理**批配置**页中的单向协议选项卡**协议属性**对话框。 可按以下任一方式发布批处理：  
  
- 根据计划，每小时、 每天或每周。  
  
- 特定数量的事务集时可用于一组。  
  
- 特定数量的事务集时可供交换。  
  
- 当特定数目的字符是可用于批处理。  
  
- 到外部应用程序执行外部触发器时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
  如果选择**发送空的批处理信号**上的属性**批处理计划**对话框中，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]批处理计划即使没有消息已发送时将发送一个空的批处理消息由批处理业务流程接收。  
  
## <a name="batch-activation-criteria"></a>批处理激活条件  
 仅当已满足批处理激活条件时，将根据批发布条件发布批处理。 若要激活业务流程的实例，必须按下**启动**按钮**批配置**中的单向协议选项卡页**协议属性**对话框。 这将创建批配置的业务流程的实例。 如果**启动**按钮可供单击，则当前尚未激活的批处理配置业务流程的实例。  
  
 按后**启动**按钮，将为批处理收集消息，仅当满足以下条件：  
  
- 消息符合批处理筛选器中规定的条件。  
  
- 日期和时间是在输入中的日期时间后**启动**字段。  
  
- 日期和时间之前中输入的值是**结束**字段中或处理的批数是小于或等于的中的出现次数**结束前的 （出现）** 字段或**无结束日期**选择选项。 所有三个选项都位于**终止**部分。  
  
  激活条件中设置**批配置**页中的单向协议选项卡**协议属性**对话框。  
  
  已按下后**启动**按钮以激活批处理业务流程的实例，消息之前提到的时间不会为批处理收集**启动**属性传递。  在**批配置**页上，如果**立即启动**未选择并**启动**日期时间设置为之前在其中按的时间值**启动**按钮时，批处理将启动业务流程处于活动状态时。 如果激活日期时间在将来，则将在该时间启动批处理。  
  
  可以设置**启动**是将来的日期时间的 datetime。 但是，如果单击**启动**按钮时**启动**日期时间是将来，将激活业务流程实例，但会收集任何消息，直到开始日期时间。 BatchMarker 管道组件不会升级将消息路由到路由业务流程或批处理业务流程的开始日期时间之前所需的相应属性。 因此不会对消息进行批处理。 但是，任何单独订阅这些消息的发送端口或业务流程仍会提取消息。 BatchMarker 管道组件执行的详细信息，请参阅[装配批处理的 EDI 交换](../core/assembling-a-batched-edi-interchange.md)。  
  
## <a name="batch-termination-criteria"></a>批处理终止条件  
 消息将停止收集后一批**结束**日期时间或之后的中的出现次数**结束前的 （出现）** 属性。 如果不希望将停用批处理业务流程，请选择**无结束日期**选项。  
  
> [!NOTE]
>  如果**结束前的 （出现）** 选择属性，空的批处理信号计入结束该批处理激活范围所需的次数。 如果出现在正常情况下可导致空的批处理信号的条件（在计划应发送批处理时批处理业务流程尚未收到任何消息），出现次数也将递增，但因为未配置空的批处理信号，所以不会发送该信号。  
  
## <a name="see-also"></a>请参阅  
 [对传出 EDI 消息进行批处理](../core/batching-outgoing-edi-messages.md)