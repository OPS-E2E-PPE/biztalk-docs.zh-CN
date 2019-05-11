---
title: 关联的传入事务集与传出批 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2fbe40f8-7379-42be-b8a7-070ce8a7ce26
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6d1e0d6b9a26809325d28fd954ae9197ac36ec9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354476"
---
# <a name="correlating-an-incoming-transaction-set-with-an-outgoing-batch"></a>将传入事务集与传出批相关联
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使您能够将的 EDI 事务集提交到批处理业务流程与传出批相关联。 则执行操作来将状态报告条目为事务集提交到批处理业务流程 (BTSInterchangeID) 关联到状态报告条目 (ActivityID) 的业务流程。 使用 BusinessMessageJournal BAM 活动中的条目来执行此相关。 接收批元素时，批处理业务流程将创建这些项。  
  
> [!IMPORTANT]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 仅当协议启用 EDI 状态报告和事务集跟踪时，会在 BusinessMessageJournal 活动中生成条目。  
  
 以下各节介绍了以下：  
  
- 如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]保存跟踪数据  
  
- 如何创建用于启用关联的自定义管道组件  
  
- 您如何可以将传入事务集与传出批相关联。  
  
- 如何查询 BusinessMessageJournal 活动以确定批的 BTSInterchangeID，如果知道包含批处理中的事务集的 BTSInterchangeID。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。  
  
## <a name="changes-to-the-activities"></a>对活动的更改  
 批处理业务流程中创建条目 BatchingActivity、 TransactionSetActivity 和 BusinessMessageJournal BAM 活动。 为事务集将通过移动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将在这些活动表中为事务集以及包含它的批生成以下条目：  
  
1.  当 EDI 拆装器处理传入 EDI 交换时，它在 InterchangeStatusActivity 和 TransactionSetActivity 表中创建条目。  
  
    > [!NOTE]
    >  有关 BAM 活动的详细信息，请参阅[BAM 跟踪 EDI-AS2 消息的活动创建](../core/bam-activities-created-to-track-edi-as2-messages.md)。  
  
2.  实例化批处理业务流程时，业务流程在 BatchingActivity 中创建一个条目。 BAM 子系统创建 activityid 的值。  
  
3.  批处理业务流程提取事务集后，将创建的事务集在 TransactionSetActivity 表中的条目。  
  
4.  业务流程在 BusinessMessageJournal 活动中创建一个条目。 它将此活动的 MessageTrackingID 字段设置为在 TransactionSetActivity 表中创建了业务流程的条目的 ActivityID 字段的值。 它还将 BTSInterchangeID 字段设置为 BTS。事务集和 BTS BTSMessageID 字段的 InterchangeID 上下文属性。事务集的 MessageID 上下文属性。  
  
5.  业务流程在 BusinessMessageJournal 活动中创建第二个条目。 它将 MessageTrackingID 字段设置为在 TransactionSetActivity 表中创建了业务流程的条目的 ActivityID 字段。 它将 BTSInterchangeID 字段设置为 BTS。批处理的 InterchangeID 上下文属性。 它不会不对 BTSMessageID 进行设置。 它将 ContainerActivityID 设置为 BatchingActivity 中的 ActivityID 的值。  
  
## <a name="creating-a-custom-pipeline-component-for-enabling-correlation"></a>创建用于启用关联的自定义管道组件  
 若要设置的传入事务集与传出批包含该事务的相关集，您需要创建自定义管道组件。 EDI 拆装器之后以及 EDIReceive 管道的 BatchMarker 组件之前，应来自此管道组件。 此管道组件需要在 BusinessMessageJournal 活动中创建一个条目。 在此条目中，BTSInterchangeID 字段应设置为 BTS。InterchangeID 上下文属性和 BTSMessageID 字段应设置为 BTS。MessageID 上下文属性。  
  
## <a name="looking-up-the-interchangeid-for-a-transaction-set-in-a-batch"></a>在一个批处理中事务的 Interchangeid 查找设置  
 关联接收的交换，并包含在事务的批处理设置从交换中，通过使用 BatchingActivity 表和 BusinessMessageJournal 活动中的条目，如下所述。  
  
### <a name="to-correlate-an-incoming-transaction-set-with-an-outgoing-batch-that-contains-that-transaction-set"></a>若要将传入事务集与传出批包含该事务关联设置  
  
1.  确定在 BatchingActivity 表中批处理的 ActivityID 的值。  
  
2.  搜索 BusinessMessageJournal 活动表 ContainerActivityID 字段中的 ActivityID 值。  
  
3.  在由 ContainerActivityID 标识的记录，查找与批处理关联的 MessageTrackingID 字段的值。  
  
4.  使用 BusinessMessageJournal 活动表中与批关联的 MessageTrackingID 字段的值，搜索 BusinessMessageJournal 活动表中的其他记录的 MessageTrackingID 字段中的值相同。 未找到任何记录是与批处理中的事务集相关联，因为由批处理业务流程记录。  
  
5.  在 BusinessMessageJournal 活动表中的事务集与关联的记录，查找 BTSInterchangeID 字段的值。  
  
6.  使用 BTSInterchangeID 的值，您可以查找在 BusinessMessageJournal 活动表中，已创建的事务集的记录所记录的自定义管道组件。 您还可以查看事务集在 TransactionSetActivity 表中的记录。  
  
## <a name="querying-businessmessagejournal"></a>查询 BusinessMessageJournal  
 如果事务集报告已启用，且您知道所接收交换的 BTSInterchangeID，可以使用以下 SQL 查询以查找包含提交到批处理业务流程的事务集批的 btsinterchangeid。 使用此代码，可以创建自定义应用程序中，若要深入了解批处理中的消息。  
  
> [!IMPORTANT]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 仅当协议启用 EDI 状态报告和事务集跟踪时，会在 BusinessMessageJournal 活动中生成条目。  
  
```  
Select MessageTrackingID  
From BusinessMessageJournal  
Where BTSInterchangeID = <given InterchangeID of the receive interchange>  
  
Select BTSInterchangeID  
From BusinessMessageJournal  
Where MessageTrackingID = <MessageTrackingID from the previous query> and BTSInterchangeID = <given InterchangeID>  
```  
  
## <a name="see-also"></a>请参阅  
 [为跟踪 edi/as2 消息创建的 BAM 活动](../core/bam-activities-created-to-track-edi-as2-messages.md)   
 [启用 EDI 和 AS2 状态报告](../core/enabling-edi-and-as2-status-reports.md)