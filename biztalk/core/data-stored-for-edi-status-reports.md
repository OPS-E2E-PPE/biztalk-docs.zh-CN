---
title: 为 EDI 状态报告存储的数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec66e4d7-2694-499f-a60c-2f80fe643e12
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90d130d3151f16892e66e02eed834d124b1a2c1e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023227"
---
# <a name="data-stored-for-edi-status-reports"></a><span data-ttu-id="22e8f-102">为 EDI 状态报告存储的数据</span><span class="sxs-lookup"><span data-stu-id="22e8f-102">Data Stored for EDI Status Reports</span></span>
<span data-ttu-id="22e8f-103">EDI 状态报告中提供了两个级别的报告： 第一个 if**打开报告**属性选择一个协议，和第二个 if**存储事务集/负载以用于报告**为协议选择属性。</span><span class="sxs-lookup"><span data-stu-id="22e8f-103">Two levels of reporting are available in EDI status reporting: the first if the **Turn ON Reporting** property is selected for an agreement, and the second if the **Store transaction set/payload reporting** property is selected for an agreement.</span></span> <span data-ttu-id="22e8f-104">这些属性位于**常规属性**页**常规**选项卡中**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="22e8f-104">These properties are available in the **General Properties** page of the **General** tab in the **Agreement Properties** dialog box.</span></span>  
  
## <a name="data-stored-if-edi-reporting-is-activated"></a><span data-ttu-id="22e8f-105">激活 EDI 报告时存储的数据</span><span class="sxs-lookup"><span data-stu-id="22e8f-105">Data Stored If EDI Reporting Is Activated</span></span>  
 <span data-ttu-id="22e8f-106">如果**打开报告**协议，选择属性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将保留所有已发送或接收的交换、 技术确认和功能确认的记录。</span><span class="sxs-lookup"><span data-stu-id="22e8f-106">If the **Turn ON Reporting** property is selected for an agreement, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will keep a record of all sent or received interchanges, technical acknowledgments, and functional acknowledgments.</span></span>  
  
 <span data-ttu-id="22e8f-107">对于接收的交换，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 存储以下信息：</span><span class="sxs-lookup"><span data-stu-id="22e8f-107">For a received interchange, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] stores the following information:</span></span>  
  
- <span data-ttu-id="22e8f-108">所有已接收消息的记录。</span><span class="sxs-lookup"><span data-stu-id="22e8f-108">A record of all received interchanges.</span></span> <span data-ttu-id="22e8f-109">这是在 EDI 的状态报告 UI 中显示的第一个信息。</span><span class="sxs-lookup"><span data-stu-id="22e8f-109">This is the first information displayed in the status reporting UI for EDI.</span></span>  
  
- <span data-ttu-id="22e8f-110">交换中包含的所有事务集的记录。</span><span class="sxs-lookup"><span data-stu-id="22e8f-110">A record of all transaction sets contained in the interchange.</span></span> <span data-ttu-id="22e8f-111">这并不包括在启用了事务集存储时存储的所有详细信息。</span><span class="sxs-lookup"><span data-stu-id="22e8f-111">This does not include all the details that are stored when transaction-set storage is enabled.</span></span>  
  
- <span data-ttu-id="22e8f-112">所接收交换中存在的所有技术确认的记录</span><span class="sxs-lookup"><span data-stu-id="22e8f-112">A record of all Technical acknowledgments present in the received interchange</span></span>  
  
- <span data-ttu-id="22e8f-113">所接收交换中存在的所有功能确认的记录</span><span class="sxs-lookup"><span data-stu-id="22e8f-113">A record of all Functional acknowledgments present in the received interchange</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="22e8f-114">如果交换具有多个功能组，则会在状态报告 UI 中存储多个功能确认。</span><span class="sxs-lookup"><span data-stu-id="22e8f-114">If an interchange has multiple functional groups, multiple functional acknowledgments will be stored in the status reporting UI.</span></span> <span data-ttu-id="22e8f-115">但是，如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收的一组重复功能确认[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将存储在状态报告 UI 中的最后一个功能确认。</span><span class="sxs-lookup"><span data-stu-id="22e8f-115">However, if [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receives duplicate functional acknowledgments for a group, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will store only the last functional acknowledgment in the status reporting UI.</span></span>  
  
- <span data-ttu-id="22e8f-116">是否需要为收到的交换生成技术确认</span><span class="sxs-lookup"><span data-stu-id="22e8f-116">Whether a technical acknowledgment needs to be generated for the received interchange</span></span>  
  
- <span data-ttu-id="22e8f-117">是否需要为收到的事务集生成功能确认</span><span class="sxs-lookup"><span data-stu-id="22e8f-117">Whether functional acknowledgments need to be generated for the received transaction sets</span></span>  
  
  <span data-ttu-id="22e8f-118">对于发送的交换，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]存储以下信息：</span><span class="sxs-lookup"><span data-stu-id="22e8f-118">For a sent interchange, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] stores the following information:</span></span>  
  
- <span data-ttu-id="22e8f-119">所发送交换的记录</span><span class="sxs-lookup"><span data-stu-id="22e8f-119">A record of the sent interchange</span></span>  
  
- <span data-ttu-id="22e8f-120">交换中包含的所有事务集的记录</span><span class="sxs-lookup"><span data-stu-id="22e8f-120">A record of all transaction sets contained in the interchange</span></span>  
  
- <span data-ttu-id="22e8f-121">所发送交换中存在的所有技术确认的记录</span><span class="sxs-lookup"><span data-stu-id="22e8f-121">A record of all Technical acknowledgments present in the sent interchange</span></span>  
  
- <span data-ttu-id="22e8f-122">所发送交换中存在的所有功能确认的记录</span><span class="sxs-lookup"><span data-stu-id="22e8f-122">A record of all Functional acknowledgments present in the sent interchange</span></span>  
  
  <span data-ttu-id="22e8f-123">EDI 状态报告 UI 将这些记录可显示的完整信息相关联。</span><span class="sxs-lookup"><span data-stu-id="22e8f-123">EDI status reporting UI correlates these records to display complete information.</span></span> <span data-ttu-id="22e8f-124">例如，如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收一个交换，并且技术确认和功能确认需要发送给原始消息的发件人在状态报告 UI 中可以轻松地找到此信息。</span><span class="sxs-lookup"><span data-stu-id="22e8f-124">For example, if [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receives an interchange, and a technical acknowledgment and a functional acknowledgment need to be sent to the sender of the original message, you can easily find this information in the status reporting UI.</span></span>  
  
## <a name="data-stored-if-transaction-set-storage-is-enabled"></a><span data-ttu-id="22e8f-125">启用了事务集存储时保存的数据</span><span class="sxs-lookup"><span data-stu-id="22e8f-125">Data Stored If Transaction Set Storage Is Enabled</span></span>  
 <span data-ttu-id="22e8f-126">如果**存储消息负载以用于报告**协议，选择属性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将存储在发送或接收交换中找到的所有事务集的详细信息。</span><span class="sxs-lookup"><span data-stu-id="22e8f-126">If the **Store message payload for reporting** property is selected for an agreement, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will store details of all transaction sets found in a sent or received interchange.</span></span> <span data-ttu-id="22e8f-127">此级别的状态报告实现的所有执行激活 EDI 报告时，第一个级别报告以及事务集的特定信息。</span><span class="sxs-lookup"><span data-stu-id="22e8f-127">This level of status reporting implements all of the first-level reporting performed if EDI reporting is activated, plus transaction-set specific information.</span></span> <span data-ttu-id="22e8f-128">EDI 接收管道和发送管道生成条目 BAM 数据库中为每个传入和传出组/事务集 (尽管"**存储消息负载报告**选择属性)。</span><span class="sxs-lookup"><span data-stu-id="22e8f-128">The EDI receive pipeline and send pipeline make entries in the BAM database for each incoming and outgoing Group/Transaction Set (while the "**Store message payload reporting** property is selected).</span></span> <span data-ttu-id="22e8f-129">如果交换被拒绝，则不会生成任何记录。</span><span class="sxs-lookup"><span data-stu-id="22e8f-129">If the interchange is rejected, no entry is made.</span></span>  
  
 <span data-ttu-id="22e8f-130">对于发送或接收的交换，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 存储以下信息：</span><span class="sxs-lookup"><span data-stu-id="22e8f-130">For a sent or received interchange, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] stores the following information:</span></span>  
  
-   <span data-ttu-id="22e8f-131">事务集的内容。</span><span class="sxs-lookup"><span data-stu-id="22e8f-131">The transaction set content.</span></span> <span data-ttu-id="22e8f-132">在状态报告 UI 中，可以查看交换中包含的事务集，然后查看事务集的实际内容。</span><span class="sxs-lookup"><span data-stu-id="22e8f-132">In the status reporting UI, you can look at the transaction sets contained in an interchange, and then view the actual transaction set content.</span></span>  
  
-   <span data-ttu-id="22e8f-133">有关事务集的更详细信息包括：</span><span class="sxs-lookup"><span data-stu-id="22e8f-133">More detailed information about a transaction set, including the following:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="22e8f-134">信息</span><span class="sxs-lookup"><span data-stu-id="22e8f-134">Information</span></span>|<span data-ttu-id="22e8f-135">字段或值</span><span class="sxs-lookup"><span data-stu-id="22e8f-135">Field or Value</span></span>|  
|<span data-ttu-id="22e8f-136">ApplicationSender</span><span class="sxs-lookup"><span data-stu-id="22e8f-136">ApplicationSender</span></span>|<span data-ttu-id="22e8f-137">(GS02 或\<UNG2.1(UNG2.2)\></span><span class="sxs-lookup"><span data-stu-id="22e8f-137">(GS02 or \<UNG2.1(UNG2.2)\></span></span>|  
|<span data-ttu-id="22e8f-138">ApplicationReceiver</span><span class="sxs-lookup"><span data-stu-id="22e8f-138">ApplicationReceiver</span></span>|<span data-ttu-id="22e8f-139">GS03 或\<UNG3.1(UNG3.2)\></span><span class="sxs-lookup"><span data-stu-id="22e8f-139">GS03 or \<UNG3.1(UNG3.2)\></span></span>|  
|<span data-ttu-id="22e8f-140">GroupDate</span><span class="sxs-lookup"><span data-stu-id="22e8f-140">GroupDate</span></span>|<span data-ttu-id="22e8f-141">GS04 或 UNG2.4</span><span class="sxs-lookup"><span data-stu-id="22e8f-141">GS04 or UNG2.4</span></span>|  
|<span data-ttu-id="22e8f-142">GroupTime</span><span class="sxs-lookup"><span data-stu-id="22e8f-142">GroupTime</span></span>|<span data-ttu-id="22e8f-143">GS05 或 UNG2.5</span><span class="sxs-lookup"><span data-stu-id="22e8f-143">GS05 or UNG2.5</span></span>|  
|<span data-ttu-id="22e8f-144">TransactionSetId</span><span class="sxs-lookup"><span data-stu-id="22e8f-144">TransactionSetId</span></span>|<span data-ttu-id="22e8f-145">ST01 或 UNH2.1(AN 字符串）</span><span class="sxs-lookup"><span data-stu-id="22e8f-145">ST01 or  UNH2.1 (AN string)</span></span>|  
|<span data-ttu-id="22e8f-146">InterchangeControlNo</span><span class="sxs-lookup"><span data-stu-id="22e8f-146">InterchangeControlNo</span></span>|<span data-ttu-id="22e8f-147">ISA13</span><span class="sxs-lookup"><span data-stu-id="22e8f-147">ISA13</span></span>|  
|<span data-ttu-id="22e8f-148">GroupControlNo</span><span class="sxs-lookup"><span data-stu-id="22e8f-148">GroupControlNo</span></span>|<span data-ttu-id="22e8f-149">GS06</span><span class="sxs-lookup"><span data-stu-id="22e8f-149">GS06</span></span>|  
|<span data-ttu-id="22e8f-150">BtsDocType</span><span class="sxs-lookup"><span data-stu-id="22e8f-150">BtsDocType</span></span>|<span data-ttu-id="22e8f-151">命名空间 + 根节点名称</span><span class="sxs-lookup"><span data-stu-id="22e8f-151">NameSpace + Root node name</span></span>|  
|<span data-ttu-id="22e8f-152">TransactionSetControlID</span><span class="sxs-lookup"><span data-stu-id="22e8f-152">TransactionSetControlID</span></span>|<span data-ttu-id="22e8f-153">ST02 或 UNH1</span><span class="sxs-lookup"><span data-stu-id="22e8f-153">ST02 or UNH1</span></span>|  
|<span data-ttu-id="22e8f-154">TransactionSetStatus</span><span class="sxs-lookup"><span data-stu-id="22e8f-154">TransactionSetStatus</span></span>|<span data-ttu-id="22e8f-155">“已接受”、“已接受但存在错误”或者“已拒绝”</span><span class="sxs-lookup"><span data-stu-id="22e8f-155">Accepted, AcceptedWithError, or Rejected</span></span>|  
|<span data-ttu-id="22e8f-156">方向</span><span class="sxs-lookup"><span data-stu-id="22e8f-156">Direction</span></span>|<span data-ttu-id="22e8f-157">发送或接收</span><span class="sxs-lookup"><span data-stu-id="22e8f-157">Send or Receive</span></span>|  
|<span data-ttu-id="22e8f-158">BtsProcessingTime</span><span class="sxs-lookup"><span data-stu-id="22e8f-158">BtsProcessingTime</span></span>|<span data-ttu-id="22e8f-159">在接收端：管道中添加的时间戳 BTSReceiveTime（本地时间）</span><span class="sxs-lookup"><span data-stu-id="22e8f-159">On receive side: BTSReceiveTime (local time) as stamped in the Pipeline</span></span><br /><br /> <span data-ttu-id="22e8f-160">在发送端：ASM 组件在信封上添加的时间戳 BTSSendTime（本地时间）</span><span class="sxs-lookup"><span data-stu-id="22e8f-160">On send side: BTSSendTime as (local time) stamped on the envelope by the ASM component</span></span>|  
|<span data-ttu-id="22e8f-161">BTS.MessageId</span><span class="sxs-lookup"><span data-stu-id="22e8f-161">BTS.MessageId</span></span>|<span data-ttu-id="22e8f-162">在接收端：来自消息属性的 BTSMessageId</span><span class="sxs-lookup"><span data-stu-id="22e8f-162">On receive side: BTSMessageId from message properties</span></span><br /><br /> <span data-ttu-id="22e8f-163">在发送端：</span><span class="sxs-lookup"><span data-stu-id="22e8f-163">On send side:</span></span><br /><br /> <span data-ttu-id="22e8f-164">对于单个事务集：BTSMessageId</span><span class="sxs-lookup"><span data-stu-id="22e8f-164">For single Transaction Set: BTSMessageId</span></span><br /><br /> <span data-ttu-id="22e8f-165">对于出站批： 批次 (不是批消息的 BTSMessageId) 中每个消息的事务集 BTSMessageId**注意：** 存储仅 – 将不会显示在 UI 中。</span><span class="sxs-lookup"><span data-stu-id="22e8f-165">For outbound batch: TransactionSet BTSMessageId for each individual message in batch (not the BTSMessageId for the batch message) **Note:**  Storage only – will not be displayed in UI.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="22e8f-166">请参阅</span><span class="sxs-lookup"><span data-stu-id="22e8f-166">See Also</span></span>  
 <span data-ttu-id="22e8f-167">[为 EDI 和 AS2 状态报告存储的数据](../core/data-stored-for-edi-and-as2-status-reports.md) </span><span class="sxs-lookup"><span data-stu-id="22e8f-167">[Data Stored for EDI and AS2 Status Reports](../core/data-stored-for-edi-and-as2-status-reports.md) </span></span>  
 <span data-ttu-id="22e8f-168">[为批处理状态报告存储的数据](../core/data-stored-for-batching-status-reports.md) </span><span class="sxs-lookup"><span data-stu-id="22e8f-168">[Data Stored for Batching Status Reports](../core/data-stored-for-batching-status-reports.md) </span></span>  
 [<span data-ttu-id="22e8f-169">为 AS2 状态报告存储的数据</span><span class="sxs-lookup"><span data-stu-id="22e8f-169">Data Stored for AS2 Status Reports</span></span>](../core/data-stored-for-as2-status-reports.md)