---
title: "关联一个传入事务使用传出的批处理设置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2fbe40f8-7379-42be-b8a7-070ce8a7ce26
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ddd5a1ec83db1177050711d82bfb465c2bcb7637
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="correlating-an-incoming-transaction-set-with-an-outgoing-batch"></a>将使用的传出的批次的传入事务集相关联
借助 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，您可将提交到批处理业务流程的 EDI 事务集与传出批相关联。 通过将提交到批处理业务流程的事务集的状态报告条目 (BTSInterchangeID) 关联到业务流程的状态报告条目 (ActivityID)，您可以实现这一点。 此关联是通过使用 BusinessMessageJournal BAM 活动中的条目执行的。 这些条目是在接收批元素时由批处理业务流程创建的。  
  
> [!IMPORTANT]
>  只有在对协议启用 EDI 状态报告和事务集跟踪的情况下，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 才会在 BusinessMessageJournal 活动中生成条目。  
  
 以下各节介绍的内容如下：  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 如何保存跟踪数据  
  
-   如何创建用于启用关联的自定义管道组件。  
  
-   如何将传入事务集与传出批相关联。  
  
-   在知道批中所包含事务集的 BTSInterchangeID 的情况下，如何查询 BusinessMessageJournal 活动以确定批的 BTSInterchangeID。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
## <a name="changes-to-the-activities"></a>对活动所做的更改  
 批处理业务流程会在 BatchingActivity、TransactionSetActivity 和 BusinessMessageJournal BAM 活动中生成条目。 当事务集通过 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 时，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将在这些活动表中为该事务集以及包含该事务集的批生成以下条目：  
  
1.  当 EDI 拆装器处理传入 EDI 交换时，它会在 InterchangeStatusActivity 和 TransactionSetActivity 表中创建条目。  
  
    > [!NOTE]
    >  BAM 活动有关的详细信息，请参阅[BAM 活动跟踪 EDI AS2 消息的创建](../core/bam-activities-created-to-track-edi-as2-messages.md)。  
  
2.  当对批处理业务流程进行实例化时，业务流程会在 BatchingActivity 中创建条目。 BAM 子系统会创建 ActivityID 的值。  
  
3.  在批处理业务流程提取事务集之后，它会在 TransactionSetActivity 表中为事务集创建条目。  
  
4.  业务流程在 BusinessMessageJournal 活动中创建条目。 业务流程将此活动的 MessageTrackingID 字段设置为它在 TransactionSetActivity 表中所创建条目的 ActivityID 字段的值。 业务流程还将 BTSInterchangeID 字段和 BTSMessageID 字段分别设置为事务集的 BTS.InterchangeID 上下文属性和 BTS.MessageID 上下文属性。  
  
5.  业务流程在 BusinessMessageJournal 活动中创建第二个条目。 业务流程将 MessageTrackingID 字段设置为它在 TransactionSetActivity 表中所创建条目的 ActivityID 字段。 它将 BTSInterchangeID 字段设置为批的 BTS.InterchangeID 上下文属性。 业务流程不对 BTSMessageID 进行设置。 它将 ContainerActivityID 设置为 BatchingActivity 中的 ActivityID 的值。  
  
## <a name="creating-a-custom-pipeline-component-for-enabling-correlation"></a>创建用于启用关联的自定义管道组件  
 若要设置传入事务集与包含事该务集的传出批之间的关联，您需要创建自定义管道组件。 此管道组件应在 EDI 拆装器之后以及 EDIReceive 管道的 BatchMarker 组件之前使用。 此管道组件需要在 BusinessMessageJournal 活动中创建一个条目。 在此条目中，BTSInterchangeID 字段应设置为 BTS.InterchangeID 上下文属性，且 BTSMessageID 字段应设置为 BTS.MessageID 上下文属性。  
  
## <a name="looking-up-the-interchangeid-for-a-transaction-set-in-a-batch"></a>查找批中事务集的 InterchangeID  
 如下所述，通过使用 BatchingActivity 表中的条目以及 BusinessMessageJournal 活动中的条目，可将接收到的交换与包含来自交换的事务集的批相关联。  
  
### <a name="to-correlate-an-incoming-transaction-set-with-an-outgoing-batch-that-contains-that-transaction-set"></a>将传入事务集与包含该事务集的传出批相关联  
  
1.  在 BatchingActivity 表中确定批的 ActivityID 的值。  
  
2.  搜索 BusinessMessageJournal 活动表中 ContainerActivityID 字段的 ActivityID 值。  
  
3.  在由 ContainerActivityID 所标识的记录中，查找与批关联的 MessageTrackingID 字段的值。  
  
4.  使用 BusinessMessageJournal 活动表中与批关联的 MessageTrackingID 字段的值，在 BusinessMessageJournal 活动表中搜索其他记录中相同的 MessageTrackingID 字段值。 找到的任何记录均与批中的事务集相关，正如批处理业务流程所记录的那样。  
  
5.  在 BusinessMessageJournal 活动表中与事务集相关的记录中，查找 BTSInterchangeID 字段的值。  
  
6.  通过使用 BTSInterchangeID 的值，您可以查找在 BusinessMessageJournal 活动表中创建的该事务集记录，如自定义管道组件所记录的那样。 您也可以在 TransactionSetActivity 表中查找该事务集的记录。  
  
## <a name="querying-businessmessagejournal"></a>查询 BusinessMessageJournal  
 如果启用了事务集报告功能，且您知道所接收交换的 BTSInterchangeID，则可使用以下 SQL 查询查找包含提交给批处理业务流程的事务集的批的 BTSInterchangeID。 使用此代码，您可创建用于查看批中消息的自定义应用程序。  
  
> [!IMPORTANT]
>  只有在对协议启用 EDI 状态报告和事务集跟踪的情况下，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 才会在 BusinessMessageJournal 活动中生成条目。  
  
```  
Select MessageTrackingID  
From BusinessMessageJournal  
Where BTSInterchangeID = <given InterchangeID of the receive interchange>  
  
Select BTSInterchangeID  
From BusinessMessageJournal  
Where MessageTrackingID = <MessageTrackingID from the previous query> and BTSInterchangeID = <given InterchangeID>  
```  
  
## <a name="see-also"></a>另请参阅  
 [BAM 活动跟踪 EDI AS2 消息的创建](../core/bam-activities-created-to-track-edi-as2-messages.md)   
 [启用 EDI 和 AS2 状态报表](../core/enabling-edi-and-as2-status-reports.md)