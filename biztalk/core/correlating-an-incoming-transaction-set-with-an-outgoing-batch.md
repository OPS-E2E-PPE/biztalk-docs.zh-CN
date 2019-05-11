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
# <a name="correlating-an-incoming-transaction-set-with-an-outgoing-batch"></a><span data-ttu-id="8a918-102">将传入事务集与传出批相关联</span><span class="sxs-lookup"><span data-stu-id="8a918-102">Correlating an Incoming Transaction Set with an Outgoing Batch</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="8a918-103">使您能够将的 EDI 事务集提交到批处理业务流程与传出批相关联。</span><span class="sxs-lookup"><span data-stu-id="8a918-103">enables you to correlate an EDI transaction set submitted to the Batching Orchestration with an outgoing batch.</span></span> <span data-ttu-id="8a918-104">则执行操作来将状态报告条目为事务集提交到批处理业务流程 (BTSInterchangeID) 关联到状态报告条目 (ActivityID) 的业务流程。</span><span class="sxs-lookup"><span data-stu-id="8a918-104">You do so by correlating a status reporting entry for the transaction set submitted to the Batching Orchestration (the BTSInterchangeID) to a status reporting entry for the orchestration (ActivityID).</span></span> <span data-ttu-id="8a918-105">使用 BusinessMessageJournal BAM 活动中的条目来执行此相关。</span><span class="sxs-lookup"><span data-stu-id="8a918-105">This correlation is performed using entries in the BusinessMessageJournal BAM activity.</span></span> <span data-ttu-id="8a918-106">接收批元素时，批处理业务流程将创建这些项。</span><span class="sxs-lookup"><span data-stu-id="8a918-106">These entries are created by the Batching Orchestration when a batch element is received.</span></span>  
  
> [!IMPORTANT]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="8a918-107">仅当协议启用 EDI 状态报告和事务集跟踪时，会在 BusinessMessageJournal 活动中生成条目。</span><span class="sxs-lookup"><span data-stu-id="8a918-107">will make entries in the BusinessMessageJournal activity only if EDI status reporting and Transaction Set tracking is enabled for the agreement.</span></span>  
  
 <span data-ttu-id="8a918-108">以下各节介绍了以下：</span><span class="sxs-lookup"><span data-stu-id="8a918-108">The sections below describe the following:</span></span>  
  
- <span data-ttu-id="8a918-109">如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]保存跟踪数据</span><span class="sxs-lookup"><span data-stu-id="8a918-109">How [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] saves tracking data</span></span>  
  
- <span data-ttu-id="8a918-110">如何创建用于启用关联的自定义管道组件</span><span class="sxs-lookup"><span data-stu-id="8a918-110">How you can create a custom pipeline component to enable correlation</span></span>  
  
- <span data-ttu-id="8a918-111">您如何可以将传入事务集与传出批相关联。</span><span class="sxs-lookup"><span data-stu-id="8a918-111">How you can correlate an incoming transaction set with an outgoing batch.</span></span>  
  
- <span data-ttu-id="8a918-112">如何查询 BusinessMessageJournal 活动以确定批的 BTSInterchangeID，如果知道包含批处理中的事务集的 BTSInterchangeID。</span><span class="sxs-lookup"><span data-stu-id="8a918-112">How you can query the BusinessMessageJournal activity to determine the BTSInterchangeID of the batch if you know the BTSInterchangeID of the transaction set contained in the batch.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8a918-113">先决条件</span><span class="sxs-lookup"><span data-stu-id="8a918-113">Prerequisites</span></span>  
 <span data-ttu-id="8a918-114">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。</span><span class="sxs-lookup"><span data-stu-id="8a918-114">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
## <a name="changes-to-the-activities"></a><span data-ttu-id="8a918-115">对活动的更改</span><span class="sxs-lookup"><span data-stu-id="8a918-115">Changes to the Activities</span></span>  
 <span data-ttu-id="8a918-116">批处理业务流程中创建条目 BatchingActivity、 TransactionSetActivity 和 BusinessMessageJournal BAM 活动。</span><span class="sxs-lookup"><span data-stu-id="8a918-116">The Batching Orchestration makes entries in the BatchingActivity, TransactionSetActivity, and BusinessMessageJournal BAM activities.</span></span> <span data-ttu-id="8a918-117">为事务集将通过移动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将在这些活动表中为事务集以及包含它的批生成以下条目：</span><span class="sxs-lookup"><span data-stu-id="8a918-117">As a transaction set moves through [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will make the following entries in these activity tables for the transaction set and the batch that includes it:</span></span>  
  
1.  <span data-ttu-id="8a918-118">当 EDI 拆装器处理传入 EDI 交换时，它在 InterchangeStatusActivity 和 TransactionSetActivity 表中创建条目。</span><span class="sxs-lookup"><span data-stu-id="8a918-118">When the EDI disassembler processes an incoming EDI interchange, it creates entries in the InterchangeStatusActivity and the TransactionSetActivity tables.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8a918-119">有关 BAM 活动的详细信息，请参阅[BAM 跟踪 EDI-AS2 消息的活动创建](../core/bam-activities-created-to-track-edi-as2-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="8a918-119">For more information about the BAM activities, see [BAM Activities Created to Track EDI-AS2 Messages](../core/bam-activities-created-to-track-edi-as2-messages.md).</span></span>  
  
2.  <span data-ttu-id="8a918-120">实例化批处理业务流程时，业务流程在 BatchingActivity 中创建一个条目。</span><span class="sxs-lookup"><span data-stu-id="8a918-120">When the Batching Orchestration is instantiated, the orchestration creates an entry in the BatchingActivity.</span></span> <span data-ttu-id="8a918-121">BAM 子系统创建 activityid 的值。</span><span class="sxs-lookup"><span data-stu-id="8a918-121">The BAM subsystem creates a value for the ActivityID.</span></span>  
  
3.  <span data-ttu-id="8a918-122">批处理业务流程提取事务集后，将创建的事务集在 TransactionSetActivity 表中的条目。</span><span class="sxs-lookup"><span data-stu-id="8a918-122">After the batching orchestration has picked up the transaction set, it creates an entry for the transaction set in the TransactionSetActivity table.</span></span>  
  
4.  <span data-ttu-id="8a918-123">业务流程在 BusinessMessageJournal 活动中创建一个条目。</span><span class="sxs-lookup"><span data-stu-id="8a918-123">The orchestration creates an entry in the BusinessMessageJournal activity.</span></span> <span data-ttu-id="8a918-124">它将此活动的 MessageTrackingID 字段设置为在 TransactionSetActivity 表中创建了业务流程的条目的 ActivityID 字段的值。</span><span class="sxs-lookup"><span data-stu-id="8a918-124">It sets the MessageTrackingID field of this activity to the value of the ActivityID field of the entry that the orchestration created in TransactionSetActivity table.</span></span> <span data-ttu-id="8a918-125">它还将 BTSInterchangeID 字段设置为 BTS。事务集和 BTS BTSMessageID 字段的 InterchangeID 上下文属性。事务集的 MessageID 上下文属性。</span><span class="sxs-lookup"><span data-stu-id="8a918-125">It also sets the BTSInterchangeID field to the BTS.InterchangeID context property for the transaction set and the BTSMessageID field to the BTS.MessageID context property for the transaction set.</span></span>  
  
5.  <span data-ttu-id="8a918-126">业务流程在 BusinessMessageJournal 活动中创建第二个条目。</span><span class="sxs-lookup"><span data-stu-id="8a918-126">The orchestration creates a second entry in the BusinessMessageJournal activity.</span></span> <span data-ttu-id="8a918-127">它将 MessageTrackingID 字段设置为在 TransactionSetActivity 表中创建了业务流程的条目的 ActivityID 字段。</span><span class="sxs-lookup"><span data-stu-id="8a918-127">It sets the MessageTrackingID field to the ActivityID field of the entry that the orchestration created in TransactionSetActivity table.</span></span> <span data-ttu-id="8a918-128">它将 BTSInterchangeID 字段设置为 BTS。批处理的 InterchangeID 上下文属性。</span><span class="sxs-lookup"><span data-stu-id="8a918-128">It sets the BTSInterchangeID field to the BTS.InterchangeID context property for the batch.</span></span> <span data-ttu-id="8a918-129">它不会不对 BTSMessageID 进行设置。</span><span class="sxs-lookup"><span data-stu-id="8a918-129">It does not set the BTSMessageID.</span></span> <span data-ttu-id="8a918-130">它将 ContainerActivityID 设置为 BatchingActivity 中的 ActivityID 的值。</span><span class="sxs-lookup"><span data-stu-id="8a918-130">It sets the ContainerActivityID to the value of the ActivityID in the BatchingActivity.</span></span>  
  
## <a name="creating-a-custom-pipeline-component-for-enabling-correlation"></a><span data-ttu-id="8a918-131">创建用于启用关联的自定义管道组件</span><span class="sxs-lookup"><span data-stu-id="8a918-131">Creating a Custom Pipeline Component for Enabling Correlation</span></span>  
 <span data-ttu-id="8a918-132">若要设置的传入事务集与传出批包含该事务的相关集，您需要创建自定义管道组件。</span><span class="sxs-lookup"><span data-stu-id="8a918-132">To set up correlation of an incoming transaction set with an outgoing batch that contains that transaction set, you need to create a custom pipeline component.</span></span> <span data-ttu-id="8a918-133">EDI 拆装器之后以及 EDIReceive 管道的 BatchMarker 组件之前，应来自此管道组件。</span><span class="sxs-lookup"><span data-stu-id="8a918-133">This pipeline component should come after the EDI Disassembler and before the BatchMarker component of the EDIReceive pipeline.</span></span> <span data-ttu-id="8a918-134">此管道组件需要在 BusinessMessageJournal 活动中创建一个条目。</span><span class="sxs-lookup"><span data-stu-id="8a918-134">This pipeline component needs to create an entry in the BusinessMessageJournal activity.</span></span> <span data-ttu-id="8a918-135">在此条目中，BTSInterchangeID 字段应设置为 BTS。InterchangeID 上下文属性和 BTSMessageID 字段应设置为 BTS。MessageID 上下文属性。</span><span class="sxs-lookup"><span data-stu-id="8a918-135">In this entry, the BTSInterchangeID field should be set to the BTS.InterchangeID context property and the BTSMessageID field should be set to the BTS.MessageID context property.</span></span>  
  
## <a name="looking-up-the-interchangeid-for-a-transaction-set-in-a-batch"></a><span data-ttu-id="8a918-136">在一个批处理中事务的 Interchangeid 查找设置</span><span class="sxs-lookup"><span data-stu-id="8a918-136">Looking Up the InterchangeID for a Transaction Set in a Batch</span></span>  
 <span data-ttu-id="8a918-137">关联接收的交换，并包含在事务的批处理设置从交换中，通过使用 BatchingActivity 表和 BusinessMessageJournal 活动中的条目，如下所述。</span><span class="sxs-lookup"><span data-stu-id="8a918-137">You correlate a received interchange, and the batch that contains the transaction set from the interchange, by using the entries in the BatchingActivity table and the BusinessMessageJournal activity, as described below.</span></span>  
  
### <a name="to-correlate-an-incoming-transaction-set-with-an-outgoing-batch-that-contains-that-transaction-set"></a><span data-ttu-id="8a918-138">若要将传入事务集与传出批包含该事务关联设置</span><span class="sxs-lookup"><span data-stu-id="8a918-138">To correlate an incoming transaction set with an outgoing batch that contains that transaction set</span></span>  
  
1.  <span data-ttu-id="8a918-139">确定在 BatchingActivity 表中批处理的 ActivityID 的值。</span><span class="sxs-lookup"><span data-stu-id="8a918-139">Determine the value of ActivityID for the batch in the BatchingActivity table.</span></span>  
  
2.  <span data-ttu-id="8a918-140">搜索 BusinessMessageJournal 活动表 ContainerActivityID 字段中的 ActivityID 值。</span><span class="sxs-lookup"><span data-stu-id="8a918-140">Search for the ActivityID value in the ContainerActivityID field of the BusinessMessageJournal activity table.</span></span>  
  
3.  <span data-ttu-id="8a918-141">在由 ContainerActivityID 标识的记录，查找与批处理关联的 MessageTrackingID 字段的值。</span><span class="sxs-lookup"><span data-stu-id="8a918-141">In the record identified by the ContainerActivityID, look up the value of the MessageTrackingID field, which is associated with the batch.</span></span>  
  
4.  <span data-ttu-id="8a918-142">使用 BusinessMessageJournal 活动表中与批关联的 MessageTrackingID 字段的值，搜索 BusinessMessageJournal 活动表中的其他记录的 MessageTrackingID 字段中的值相同。</span><span class="sxs-lookup"><span data-stu-id="8a918-142">Using the value of the MessageTrackingID field associated with the batch in the BusinessMessageJournal activity table, search for the same value in the MessageTrackingID field of other records in the BusinessMessageJournal activity table.</span></span> <span data-ttu-id="8a918-143">未找到任何记录是与批处理中的事务集相关联，因为由批处理业务流程记录。</span><span class="sxs-lookup"><span data-stu-id="8a918-143">Any records found are associated with transaction sets in the batch, as recorded by the Batching Orchestration.</span></span>  
  
5.  <span data-ttu-id="8a918-144">在 BusinessMessageJournal 活动表中的事务集与关联的记录，查找 BTSInterchangeID 字段的值。</span><span class="sxs-lookup"><span data-stu-id="8a918-144">In a record associated with a transaction set in the BusinessMessageJournal activity table, look up the value of the BTSInterchangeID field.</span></span>  
  
6.  <span data-ttu-id="8a918-145">使用 BTSInterchangeID 的值，您可以查找在 BusinessMessageJournal 活动表中，已创建的事务集的记录所记录的自定义管道组件。</span><span class="sxs-lookup"><span data-stu-id="8a918-145">Using the value of the BTSInterchangeID, you can look up a record for the transaction set that was created in the BusinessMessageJournal activity table, as recorded by the custom pipeline component.</span></span> <span data-ttu-id="8a918-146">您还可以查看事务集在 TransactionSetActivity 表中的记录。</span><span class="sxs-lookup"><span data-stu-id="8a918-146">You can also look up a record for the transaction set in the TransactionSetActivity table.</span></span>  
  
## <a name="querying-businessmessagejournal"></a><span data-ttu-id="8a918-147">查询 BusinessMessageJournal</span><span class="sxs-lookup"><span data-stu-id="8a918-147">Querying BusinessMessageJournal</span></span>  
 <span data-ttu-id="8a918-148">如果事务集报告已启用，且您知道所接收交换的 BTSInterchangeID，可以使用以下 SQL 查询以查找包含提交到批处理业务流程的事务集批的 btsinterchangeid。</span><span class="sxs-lookup"><span data-stu-id="8a918-148">If transaction set reporting is enabled, and you know the BTSInterchangeID of the received interchange, you can use the following SQL Query to find out the BTSInterchangeID of the batch that contains the transaction set submitted to the Batching Orchestration.</span></span> <span data-ttu-id="8a918-149">使用此代码，可以创建自定义应用程序中，若要深入了解批处理中的消息。</span><span class="sxs-lookup"><span data-stu-id="8a918-149">With this code, you can create a custom application to gain visibility into the messages in a batch.</span></span>  
  
> [!IMPORTANT]
>  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="8a918-150">仅当协议启用 EDI 状态报告和事务集跟踪时，会在 BusinessMessageJournal 活动中生成条目。</span><span class="sxs-lookup"><span data-stu-id="8a918-150">will make entries in the BusinessMessageJournal activity only if EDI status reporting and Transaction Set tracking is enabled for the agreement.</span></span>  
  
```  
Select MessageTrackingID  
From BusinessMessageJournal  
Where BTSInterchangeID = <given InterchangeID of the receive interchange>  
  
Select BTSInterchangeID  
From BusinessMessageJournal  
Where MessageTrackingID = <MessageTrackingID from the previous query> and BTSInterchangeID = <given InterchangeID>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8a918-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="8a918-151">See Also</span></span>  
 <span data-ttu-id="8a918-152">[为跟踪 edi/as2 消息创建的 BAM 活动](../core/bam-activities-created-to-track-edi-as2-messages.md) </span><span class="sxs-lookup"><span data-stu-id="8a918-152">[BAM Activities Created to Track EDI-AS2 Messages](../core/bam-activities-created-to-track-edi-as2-messages.md) </span></span>  
 [<span data-ttu-id="8a918-153">启用 EDI 和 AS2 状态报告</span><span class="sxs-lookup"><span data-stu-id="8a918-153">Enabling EDI and AS2 Status Reports</span></span>](../core/enabling-edi-and-as2-status-reports.md)