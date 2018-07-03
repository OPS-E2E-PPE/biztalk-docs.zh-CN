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
ms.openlocfilehash: b44f89133cbfb7f5925f975a723b84c715180c7a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013798"
---
# <a name="correlating-an-incoming-transaction-set-with-an-outgoing-batch"></a><span data-ttu-id="cd817-102">将传入事务集与传出批相关联</span><span class="sxs-lookup"><span data-stu-id="cd817-102">Correlating an Incoming Transaction Set with an Outgoing Batch</span></span>
<span data-ttu-id="cd817-103">借助 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，您可将提交到批处理业务流程的 EDI 事务集与传出批相关联。</span><span class="sxs-lookup"><span data-stu-id="cd817-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] enables you to correlate an EDI transaction set submitted to the Batching Orchestration with an outgoing batch.</span></span> <span data-ttu-id="cd817-104">通过将提交到批处理业务流程的事务集的状态报告条目 (BTSInterchangeID) 关联到业务流程的状态报告条目 (ActivityID)，您可以实现这一点。</span><span class="sxs-lookup"><span data-stu-id="cd817-104">You do so by correlating a status reporting entry for the transaction set submitted to the Batching Orchestration (the BTSInterchangeID) to a status reporting entry for the orchestration (ActivityID).</span></span> <span data-ttu-id="cd817-105">此关联是通过使用 BusinessMessageJournal BAM 活动中的条目执行的。</span><span class="sxs-lookup"><span data-stu-id="cd817-105">This correlation is performed using entries in the BusinessMessageJournal BAM activity.</span></span> <span data-ttu-id="cd817-106">这些条目是在接收批元素时由批处理业务流程创建的。</span><span class="sxs-lookup"><span data-stu-id="cd817-106">These entries are created by the Batching Orchestration when a batch element is received.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cd817-107">只有在对协议启用 EDI 状态报告和事务集跟踪的情况下，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 才会在 BusinessMessageJournal 活动中生成条目。</span><span class="sxs-lookup"><span data-stu-id="cd817-107">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will make entries in the BusinessMessageJournal activity only if EDI status reporting and Transaction Set tracking is enabled for the agreement.</span></span>  
  
 <span data-ttu-id="cd817-108">以下各节介绍的内容如下：</span><span class="sxs-lookup"><span data-stu-id="cd817-108">The sections below describe the following:</span></span>  
  
- <span data-ttu-id="cd817-109">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 如何保存跟踪数据</span><span class="sxs-lookup"><span data-stu-id="cd817-109">How [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] saves tracking data</span></span>  
  
- <span data-ttu-id="cd817-110">如何创建用于启用关联的自定义管道组件。</span><span class="sxs-lookup"><span data-stu-id="cd817-110">How you can create a custom pipeline component to enable correlation</span></span>  
  
- <span data-ttu-id="cd817-111">如何将传入事务集与传出批相关联。</span><span class="sxs-lookup"><span data-stu-id="cd817-111">How you can correlate an incoming transaction set with an outgoing batch.</span></span>  
  
- <span data-ttu-id="cd817-112">在知道批中所包含事务集的 BTSInterchangeID 的情况下，如何查询 BusinessMessageJournal 活动以确定批的 BTSInterchangeID。</span><span class="sxs-lookup"><span data-stu-id="cd817-112">How you can query the BusinessMessageJournal activity to determine the BTSInterchangeID of the batch if you know the BTSInterchangeID of the transaction set contained in the batch.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cd817-113">必要條件</span><span class="sxs-lookup"><span data-stu-id="cd817-113">Prerequisites</span></span>  
 <span data-ttu-id="cd817-114">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="cd817-114">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
## <a name="changes-to-the-activities"></a><span data-ttu-id="cd817-115">对活动所做的更改</span><span class="sxs-lookup"><span data-stu-id="cd817-115">Changes to the Activities</span></span>  
 <span data-ttu-id="cd817-116">批处理业务流程会在 BatchingActivity、TransactionSetActivity 和 BusinessMessageJournal BAM 活动中生成条目。</span><span class="sxs-lookup"><span data-stu-id="cd817-116">The Batching Orchestration makes entries in the BatchingActivity, TransactionSetActivity, and BusinessMessageJournal BAM activities.</span></span> <span data-ttu-id="cd817-117">当事务集通过 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 时，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将在这些活动表中为该事务集以及包含该事务集的批生成以下条目：</span><span class="sxs-lookup"><span data-stu-id="cd817-117">As a transaction set moves through [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will make the following entries in these activity tables for the transaction set and the batch that includes it:</span></span>  
  
1.  <span data-ttu-id="cd817-118">当 EDI 拆装器处理传入 EDI 交换时，它会在 InterchangeStatusActivity 和 TransactionSetActivity 表中创建条目。</span><span class="sxs-lookup"><span data-stu-id="cd817-118">When the EDI disassembler processes an incoming EDI interchange, it creates entries in the InterchangeStatusActivity and the TransactionSetActivity tables.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cd817-119">有关 BAM 活动的详细信息，请参阅[BAM 跟踪 EDI-AS2 消息的活动创建](../core/bam-activities-created-to-track-edi-as2-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="cd817-119">For more information about the BAM activities, see [BAM Activities Created to Track EDI-AS2 Messages](../core/bam-activities-created-to-track-edi-as2-messages.md).</span></span>  
  
2.  <span data-ttu-id="cd817-120">当对批处理业务流程进行实例化时，业务流程会在 BatchingActivity 中创建条目。</span><span class="sxs-lookup"><span data-stu-id="cd817-120">When the Batching Orchestration is instantiated, the orchestration creates an entry in the BatchingActivity.</span></span> <span data-ttu-id="cd817-121">BAM 子系统会创建 ActivityID 的值。</span><span class="sxs-lookup"><span data-stu-id="cd817-121">The BAM subsystem creates a value for the ActivityID.</span></span>  
  
3.  <span data-ttu-id="cd817-122">在批处理业务流程提取事务集之后，它会在 TransactionSetActivity 表中为事务集创建条目。</span><span class="sxs-lookup"><span data-stu-id="cd817-122">After the batching orchestration has picked up the transaction set, it creates an entry for the transaction set in the TransactionSetActivity table.</span></span>  
  
4.  <span data-ttu-id="cd817-123">业务流程在 BusinessMessageJournal 活动中创建条目。</span><span class="sxs-lookup"><span data-stu-id="cd817-123">The orchestration creates an entry in the BusinessMessageJournal activity.</span></span> <span data-ttu-id="cd817-124">业务流程将此活动的 MessageTrackingID 字段设置为它在 TransactionSetActivity 表中所创建条目的 ActivityID 字段的值。</span><span class="sxs-lookup"><span data-stu-id="cd817-124">It sets the MessageTrackingID field of this activity to the value of the ActivityID field of the entry that the orchestration created in TransactionSetActivity table.</span></span> <span data-ttu-id="cd817-125">业务流程还将 BTSInterchangeID 字段和 BTSMessageID 字段分别设置为事务集的 BTS.InterchangeID 上下文属性和 BTS.MessageID 上下文属性。</span><span class="sxs-lookup"><span data-stu-id="cd817-125">It also sets the BTSInterchangeID field to the BTS.InterchangeID context property for the transaction set and the BTSMessageID field to the BTS.MessageID context property for the transaction set.</span></span>  
  
5.  <span data-ttu-id="cd817-126">业务流程在 BusinessMessageJournal 活动中创建第二个条目。</span><span class="sxs-lookup"><span data-stu-id="cd817-126">The orchestration creates a second entry in the BusinessMessageJournal activity.</span></span> <span data-ttu-id="cd817-127">业务流程将 MessageTrackingID 字段设置为它在 TransactionSetActivity 表中所创建条目的 ActivityID 字段。</span><span class="sxs-lookup"><span data-stu-id="cd817-127">It sets the MessageTrackingID field to the ActivityID field of the entry that the orchestration created in TransactionSetActivity table.</span></span> <span data-ttu-id="cd817-128">它将 BTSInterchangeID 字段设置为批的 BTS.InterchangeID 上下文属性。</span><span class="sxs-lookup"><span data-stu-id="cd817-128">It sets the BTSInterchangeID field to the BTS.InterchangeID context property for the batch.</span></span> <span data-ttu-id="cd817-129">业务流程不对 BTSMessageID 进行设置。</span><span class="sxs-lookup"><span data-stu-id="cd817-129">It does not set the BTSMessageID.</span></span> <span data-ttu-id="cd817-130">它将 ContainerActivityID 设置为 BatchingActivity 中的 ActivityID 的值。</span><span class="sxs-lookup"><span data-stu-id="cd817-130">It sets the ContainerActivityID to the value of the ActivityID in the BatchingActivity.</span></span>  
  
## <a name="creating-a-custom-pipeline-component-for-enabling-correlation"></a><span data-ttu-id="cd817-131">创建用于启用关联的自定义管道组件</span><span class="sxs-lookup"><span data-stu-id="cd817-131">Creating a Custom Pipeline Component for Enabling Correlation</span></span>  
 <span data-ttu-id="cd817-132">若要设置传入事务集与包含事该务集的传出批之间的关联，您需要创建自定义管道组件。</span><span class="sxs-lookup"><span data-stu-id="cd817-132">To set up correlation of an incoming transaction set with an outgoing batch that contains that transaction set, you need to create a custom pipeline component.</span></span> <span data-ttu-id="cd817-133">此管道组件应在 EDI 拆装器之后以及 EDIReceive 管道的 BatchMarker 组件之前使用。</span><span class="sxs-lookup"><span data-stu-id="cd817-133">This pipeline component should come after the EDI Disassembler and before the BatchMarker component of the EDIReceive pipeline.</span></span> <span data-ttu-id="cd817-134">此管道组件需要在 BusinessMessageJournal 活动中创建一个条目。</span><span class="sxs-lookup"><span data-stu-id="cd817-134">This pipeline component needs to create an entry in the BusinessMessageJournal activity.</span></span> <span data-ttu-id="cd817-135">在此条目中，BTSInterchangeID 字段应设置为 BTS.InterchangeID 上下文属性，且 BTSMessageID 字段应设置为 BTS.MessageID 上下文属性。</span><span class="sxs-lookup"><span data-stu-id="cd817-135">In this entry, the BTSInterchangeID field should be set to the BTS.InterchangeID context property and the BTSMessageID field should be set to the BTS.MessageID context property.</span></span>  
  
## <a name="looking-up-the-interchangeid-for-a-transaction-set-in-a-batch"></a><span data-ttu-id="cd817-136">查找批中事务集的 InterchangeID</span><span class="sxs-lookup"><span data-stu-id="cd817-136">Looking Up the InterchangeID for a Transaction Set in a Batch</span></span>  
 <span data-ttu-id="cd817-137">如下所述，通过使用 BatchingActivity 表中的条目以及 BusinessMessageJournal 活动中的条目，可将接收到的交换与包含来自交换的事务集的批相关联。</span><span class="sxs-lookup"><span data-stu-id="cd817-137">You correlate a received interchange, and the batch that contains the transaction set from the interchange, by using the entries in the BatchingActivity table and the BusinessMessageJournal activity, as described below.</span></span>  
  
### <a name="to-correlate-an-incoming-transaction-set-with-an-outgoing-batch-that-contains-that-transaction-set"></a><span data-ttu-id="cd817-138">将传入事务集与包含该事务集的传出批相关联</span><span class="sxs-lookup"><span data-stu-id="cd817-138">To correlate an incoming transaction set with an outgoing batch that contains that transaction set</span></span>  
  
1.  <span data-ttu-id="cd817-139">在 BatchingActivity 表中确定批的 ActivityID 的值。</span><span class="sxs-lookup"><span data-stu-id="cd817-139">Determine the value of ActivityID for the batch in the BatchingActivity table.</span></span>  
  
2.  <span data-ttu-id="cd817-140">搜索 BusinessMessageJournal 活动表中 ContainerActivityID 字段的 ActivityID 值。</span><span class="sxs-lookup"><span data-stu-id="cd817-140">Search for the ActivityID value in the ContainerActivityID field of the BusinessMessageJournal activity table.</span></span>  
  
3.  <span data-ttu-id="cd817-141">在由 ContainerActivityID 所标识的记录中，查找与批关联的 MessageTrackingID 字段的值。</span><span class="sxs-lookup"><span data-stu-id="cd817-141">In the record identified by the ContainerActivityID, look up the value of the MessageTrackingID field, which is associated with the batch.</span></span>  
  
4.  <span data-ttu-id="cd817-142">使用 BusinessMessageJournal 活动表中与批关联的 MessageTrackingID 字段的值，在 BusinessMessageJournal 活动表中搜索其他记录中相同的 MessageTrackingID 字段值。</span><span class="sxs-lookup"><span data-stu-id="cd817-142">Using the value of the MessageTrackingID field associated with the batch in the BusinessMessageJournal activity table, search for the same value in the MessageTrackingID field of other records in the BusinessMessageJournal activity table.</span></span> <span data-ttu-id="cd817-143">找到的任何记录均与批中的事务集相关，正如批处理业务流程所记录的那样。</span><span class="sxs-lookup"><span data-stu-id="cd817-143">Any records found are associated with transaction sets in the batch, as recorded by the Batching Orchestration.</span></span>  
  
5.  <span data-ttu-id="cd817-144">在 BusinessMessageJournal 活动表中与事务集相关的记录中，查找 BTSInterchangeID 字段的值。</span><span class="sxs-lookup"><span data-stu-id="cd817-144">In a record associated with a transaction set in the BusinessMessageJournal activity table, look up the value of the BTSInterchangeID field.</span></span>  
  
6.  <span data-ttu-id="cd817-145">通过使用 BTSInterchangeID 的值，您可以查找在 BusinessMessageJournal 活动表中创建的该事务集记录，如自定义管道组件所记录的那样。</span><span class="sxs-lookup"><span data-stu-id="cd817-145">Using the value of the BTSInterchangeID, you can look up a record for the transaction set that was created in the BusinessMessageJournal activity table, as recorded by the custom pipeline component.</span></span> <span data-ttu-id="cd817-146">您也可以在 TransactionSetActivity 表中查找该事务集的记录。</span><span class="sxs-lookup"><span data-stu-id="cd817-146">You can also look up a record for the transaction set in the TransactionSetActivity table.</span></span>  
  
## <a name="querying-businessmessagejournal"></a><span data-ttu-id="cd817-147">查询 BusinessMessageJournal</span><span class="sxs-lookup"><span data-stu-id="cd817-147">Querying BusinessMessageJournal</span></span>  
 <span data-ttu-id="cd817-148">如果启用了事务集报告功能，且您知道所接收交换的 BTSInterchangeID，则可使用以下 SQL 查询查找包含提交给批处理业务流程的事务集的批的 BTSInterchangeID。</span><span class="sxs-lookup"><span data-stu-id="cd817-148">If transaction set reporting is enabled, and you know the BTSInterchangeID of the received interchange, you can use the following SQL Query to find out the BTSInterchangeID of the batch that contains the transaction set submitted to the Batching Orchestration.</span></span> <span data-ttu-id="cd817-149">使用此代码，您可创建用于查看批中消息的自定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="cd817-149">With this code, you can create a custom application to gain visibility into the messages in a batch.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cd817-150">只有在对协议启用 EDI 状态报告和事务集跟踪的情况下，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 才会在 BusinessMessageJournal 活动中生成条目。</span><span class="sxs-lookup"><span data-stu-id="cd817-150">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will make entries in the BusinessMessageJournal activity only if EDI status reporting and Transaction Set tracking is enabled for the agreement.</span></span>  
  
```  
Select MessageTrackingID  
From BusinessMessageJournal  
Where BTSInterchangeID = <given InterchangeID of the receive interchange>  
  
Select BTSInterchangeID  
From BusinessMessageJournal  
Where MessageTrackingID = <MessageTrackingID from the previous query> and BTSInterchangeID = <given InterchangeID>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cd817-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="cd817-151">See Also</span></span>  
 <span data-ttu-id="cd817-152">[为跟踪 edi/as2 消息创建的 BAM 活动](../core/bam-activities-created-to-track-edi-as2-messages.md) </span><span class="sxs-lookup"><span data-stu-id="cd817-152">[BAM Activities Created to Track EDI-AS2 Messages](../core/bam-activities-created-to-track-edi-as2-messages.md) </span></span>  
 [<span data-ttu-id="cd817-153">启用 EDI 和 AS2 状态报告</span><span class="sxs-lookup"><span data-stu-id="cd817-153">Enabling EDI and AS2 Status Reports</span></span>](../core/enabling-edi-and-as2-status-reports.md)