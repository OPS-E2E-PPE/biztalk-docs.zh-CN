---
title: "AS2 消息和相关的 MDN 状态报告 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 48ed0ee3-c844-4cb9-a84d-32b719ab8fab
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1ce4aed138f4e32e87cb1d428050999cc2b764a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="as2-message-and-correlated-mdn-status-report"></a><span data-ttu-id="eebb4-102">AS2 消息和相关的 MDN 状态报表</span><span class="sxs-lookup"><span data-stu-id="eebb4-102">AS2 Message and Correlated MDN Status Report</span></span>
<span data-ttu-id="eebb4-103">此报告显示了 AS2 发送管道和接收管道处理的所有 AS2 消息以及与相应交换有关的 MDN。</span><span class="sxs-lookup"><span data-stu-id="eebb4-103">This report shows all AS2 messages that are processed by the AS2 send and receive pipelines, and the MDNs correlated to those interchanges.</span></span>  
  
## <a name="fields-in-the-status-report"></a><span data-ttu-id="eebb4-104">状态报告中的字段</span><span class="sxs-lookup"><span data-stu-id="eebb4-104">Fields in the Status Report</span></span>  
 <span data-ttu-id="eebb4-105">AS2 消息和相关的 ACK 状态报告显示了下列与已接收或已发送交换以及与这些交换相关的确认有关的信息：</span><span class="sxs-lookup"><span data-stu-id="eebb4-105">The AS2 Message and Correlated ACK Status Report displays the following information for the received or sent interchanges and the acknowledgments that are correlated to them:</span></span>  
  
-   <span data-ttu-id="eebb4-106">发送方名称</span><span class="sxs-lookup"><span data-stu-id="eebb4-106">Sender Party Name</span></span>  
  
-   <span data-ttu-id="eebb4-107">接收方参与方名称</span><span class="sxs-lookup"><span data-stu-id="eebb4-107">Receiver Party Name</span></span>  
  
-   <span data-ttu-id="eebb4-108">AS2 发件人</span><span class="sxs-lookup"><span data-stu-id="eebb4-108">AS2 From</span></span>  
  
-   <span data-ttu-id="eebb4-109">AS2 收件人</span><span class="sxs-lookup"><span data-stu-id="eebb4-109">AS2 To</span></span>  
  
-   <span data-ttu-id="eebb4-110">AS2 消息 ID</span><span class="sxs-lookup"><span data-stu-id="eebb4-110">AS2 Message ID</span></span>  
  
-   <span data-ttu-id="eebb4-111">AS2 消息日期时间</span><span class="sxs-lookup"><span data-stu-id="eebb4-111">AS2 Message Date Time</span></span>  
  
-   <span data-ttu-id="eebb4-112">接收日期时间</span><span class="sxs-lookup"><span data-stu-id="eebb4-112">Received Date Time</span></span>  
  
-   <span data-ttu-id="eebb4-113">参与方角色</span><span class="sxs-lookup"><span data-stu-id="eebb4-113">Party Role</span></span>  
  
-   <span data-ttu-id="eebb4-114">MDN 状态</span><span class="sxs-lookup"><span data-stu-id="eebb4-114">MDN Status</span></span>  
  
-   <span data-ttu-id="eebb4-115">加密状态</span><span class="sxs-lookup"><span data-stu-id="eebb4-115">Encryption Status</span></span>  
  
-   <span data-ttu-id="eebb4-116">签名状态</span><span class="sxs-lookup"><span data-stu-id="eebb4-116">Signature Status</span></span>  
  
-   <span data-ttu-id="eebb4-117">Edi 交换状态</span><span class="sxs-lookup"><span data-stu-id="eebb4-117">Edi Interchange Status</span></span>  
  
-   <span data-ttu-id="eebb4-118">是重复的 AS2 消息</span><span class="sxs-lookup"><span data-stu-id="eebb4-118">Is AS2 Message duplicate</span></span>  
  
-   <span data-ttu-id="eebb4-119">检查重复的天数</span><span class="sxs-lookup"><span data-stu-id="eebb4-119">Days to check for duplicate</span></span>  
  
-   <span data-ttu-id="eebb4-120">Filename</span><span class="sxs-lookup"><span data-stu-id="eebb4-120">Filename</span></span>  
  
-   <span data-ttu-id="eebb4-121">启用可靠消息传送</span><span class="sxs-lookup"><span data-stu-id="eebb4-121">Reliable messaging enabled</span></span>  
  
## <a name="fields-in-the-query-expression-for-the-status-report"></a><span data-ttu-id="eebb4-122">状态报告的查询表达式中的字段</span><span class="sxs-lookup"><span data-stu-id="eebb4-122">Fields in the Query Expression for the Status Report</span></span>  
 <span data-ttu-id="eebb4-123">您可以通过更改查询表达式中用于确定所显示数据的字段来自定义 AS2 消息和相关的 ACK 状态报告。</span><span class="sxs-lookup"><span data-stu-id="eebb4-123">You can customize the AS2 Message and Correlated ACK Status Report by changing the fields in the query expression that determines the data displayed.</span></span> <span data-ttu-id="eebb4-124">下列字段可用：</span><span class="sxs-lookup"><span data-stu-id="eebb4-124">The following fields are available:</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="eebb4-125">查询表达式字段</span><span class="sxs-lookup"><span data-stu-id="eebb4-125">Query Expression Field</span></span>|<span data-ttu-id="eebb4-126">可能的运算符</span><span class="sxs-lookup"><span data-stu-id="eebb4-126">Potential Operators</span></span>|<span data-ttu-id="eebb4-127">可能的值</span><span class="sxs-lookup"><span data-stu-id="eebb4-127">Potential Values</span></span>|<span data-ttu-id="eebb4-128">默认情况下是否包括？</span><span class="sxs-lookup"><span data-stu-id="eebb4-128">Included By Default?</span></span>|  
|<span data-ttu-id="eebb4-129">搜索</span><span class="sxs-lookup"><span data-stu-id="eebb4-129">Search for</span></span>|<span data-ttu-id="eebb4-130">等于</span><span class="sxs-lookup"><span data-stu-id="eebb4-130">Equals</span></span>|<span data-ttu-id="eebb4-131">AS2/MDN 状态</span><span class="sxs-lookup"><span data-stu-id="eebb4-131">AS2/MDN Status</span></span>|<span data-ttu-id="eebb4-132">是（必需）</span><span class="sxs-lookup"><span data-stu-id="eebb4-132">Yes (required)</span></span>|  
|<span data-ttu-id="eebb4-133">消息状态</span><span class="sxs-lookup"><span data-stu-id="eebb4-133">Message Status</span></span>|<span data-ttu-id="eebb4-134">等于</span><span class="sxs-lookup"><span data-stu-id="eebb4-134">Equals</span></span><br /><br /> <span data-ttu-id="eebb4-135">不等于</span><span class="sxs-lookup"><span data-stu-id="eebb4-135">Not Equals</span></span>|<span data-ttu-id="eebb4-136">全部</span><span class="sxs-lookup"><span data-stu-id="eebb4-136">All</span></span><br /><br /> <span data-ttu-id="eebb4-137">已确认 - 已处理</span><span class="sxs-lookup"><span data-stu-id="eebb4-137">Acknowledged - Processed</span></span><br /><br /> <span data-ttu-id="eebb4-138">已确认 - 失败</span><span class="sxs-lookup"><span data-stu-id="eebb4-138">Acknowledged - Failed</span></span><br /><br /> <span data-ttu-id="eebb4-139">已处理 - MDN 挂起</span><span class="sxs-lookup"><span data-stu-id="eebb4-139">Processed - MDN pending</span></span><br /><br /> <span data-ttu-id="eebb4-140">已处理 - 非预期的 MDN</span><span class="sxs-lookup"><span data-stu-id="eebb4-140">Processed - MDN not expected</span></span><br /><br /> <span data-ttu-id="eebb4-141">未确认 – 超过重新发送尝试次数</span><span class="sxs-lookup"><span data-stu-id="eebb4-141">Not acknowledged – Resend attempts exceeded</span></span><br /><br /> <span data-ttu-id="eebb4-142">未确认 – 超过重新发送持续时间</span><span class="sxs-lookup"><span data-stu-id="eebb4-142">Not acknowledged – Resend duration exceeded</span></span>|<span data-ttu-id="eebb4-143">是</span><span class="sxs-lookup"><span data-stu-id="eebb4-143">Yes</span></span>|  
|<span data-ttu-id="eebb4-144">AS2 消息日期时间</span><span class="sxs-lookup"><span data-stu-id="eebb4-144">AS2 Message Date Time</span></span>|<span data-ttu-id="eebb4-145">小于或等于</span><span class="sxs-lookup"><span data-stu-id="eebb4-145">Less Than or Equals</span></span><br /><br /> <span data-ttu-id="eebb4-146">大于或等于</span><span class="sxs-lookup"><span data-stu-id="eebb4-146">Greater Than or Equals</span></span>|<span data-ttu-id="eebb4-147">特定日期时间</span><span class="sxs-lookup"><span data-stu-id="eebb4-147">Specific Date Time</span></span><br /><br /> <span data-ttu-id="eebb4-148">今天</span><span class="sxs-lookup"><span data-stu-id="eebb4-148">Today</span></span><br /><br /> <span data-ttu-id="eebb4-149">Today-1</span><span class="sxs-lookup"><span data-stu-id="eebb4-149">Today - 1</span></span>|<span data-ttu-id="eebb4-150">是</span><span class="sxs-lookup"><span data-stu-id="eebb4-150">Yes</span></span><br /><br /> <span data-ttu-id="eebb4-151">注意：可在查询表达式中多次使用。</span><span class="sxs-lookup"><span data-stu-id="eebb4-151">Note: Can be included more than once in the query expression.</span></span>|  
|<span data-ttu-id="eebb4-152">最大匹配数</span><span class="sxs-lookup"><span data-stu-id="eebb4-152">Maximum Matches</span></span>|<span data-ttu-id="eebb4-153">等于</span><span class="sxs-lookup"><span data-stu-id="eebb4-153">Equals</span></span>|<span data-ttu-id="eebb4-154">整数（默认值为 50）</span><span class="sxs-lookup"><span data-stu-id="eebb4-154">Integer (default of 50)</span></span>|<span data-ttu-id="eebb4-155">是</span><span class="sxs-lookup"><span data-stu-id="eebb4-155">Yes</span></span>|  
|<span data-ttu-id="eebb4-156">AS2 消息 ID</span><span class="sxs-lookup"><span data-stu-id="eebb4-156">AS2 Message ID</span></span>|<span data-ttu-id="eebb4-157">等于</span><span class="sxs-lookup"><span data-stu-id="eebb4-157">Equals</span></span>|<span data-ttu-id="eebb4-158">全部</span><span class="sxs-lookup"><span data-stu-id="eebb4-158">All</span></span><br /><br /> <span data-ttu-id="eebb4-159">特定的 AS2 消息 ID</span><span class="sxs-lookup"><span data-stu-id="eebb4-159">Specific AS2 Message ID</span></span>|<span data-ttu-id="eebb4-160">是</span><span class="sxs-lookup"><span data-stu-id="eebb4-160">No</span></span>|  
|<span data-ttu-id="eebb4-161">方向</span><span class="sxs-lookup"><span data-stu-id="eebb4-161">Direction</span></span>|<span data-ttu-id="eebb4-162">等于</span><span class="sxs-lookup"><span data-stu-id="eebb4-162">Equals</span></span>|<span data-ttu-id="eebb4-163">所有 （默认值）</span><span class="sxs-lookup"><span data-stu-id="eebb4-163">All (default)</span></span><br /><br /> <span data-ttu-id="eebb4-164">Receive</span><span class="sxs-lookup"><span data-stu-id="eebb4-164">Receive</span></span><br /><br /> <span data-ttu-id="eebb4-165">Send</span><span class="sxs-lookup"><span data-stu-id="eebb4-165">Send</span></span>|<span data-ttu-id="eebb4-166">是</span><span class="sxs-lookup"><span data-stu-id="eebb4-166">No</span></span>|  
|<span data-ttu-id="eebb4-167">接收方参与方名称</span><span class="sxs-lookup"><span data-stu-id="eebb4-167">Receiver Party Name</span></span>|<span data-ttu-id="eebb4-168">等于</span><span class="sxs-lookup"><span data-stu-id="eebb4-168">Equals</span></span>|<span data-ttu-id="eebb4-169">所有 （默认值）</span><span class="sxs-lookup"><span data-stu-id="eebb4-169">All (default)</span></span><br /><br /> <span data-ttu-id="eebb4-170">特定参与方名称</span><span class="sxs-lookup"><span data-stu-id="eebb4-170">Specific party name</span></span>|<span data-ttu-id="eebb4-171">是</span><span class="sxs-lookup"><span data-stu-id="eebb4-171">No</span></span>|  
|<span data-ttu-id="eebb4-172">发送方名称</span><span class="sxs-lookup"><span data-stu-id="eebb4-172">Sender Party Name</span></span>|<span data-ttu-id="eebb4-173">等于</span><span class="sxs-lookup"><span data-stu-id="eebb4-173">Equals</span></span>|<span data-ttu-id="eebb4-174">所有 （默认值）</span><span class="sxs-lookup"><span data-stu-id="eebb4-174">All (default)</span></span><br /><br /> <span data-ttu-id="eebb4-175">特定参与方名称</span><span class="sxs-lookup"><span data-stu-id="eebb4-175">Specific party name</span></span>|<span data-ttu-id="eebb4-176">是</span><span class="sxs-lookup"><span data-stu-id="eebb4-176">No</span></span>|  
  
## <a name="additional-as2-message-and-correlated-mdn-status-reports"></a><span data-ttu-id="eebb4-177">其他 AS2 消息和相关 MDN 状态报告</span><span class="sxs-lookup"><span data-stu-id="eebb4-177">Additional AS2 Message and Correlated MDN Status Reports</span></span>  
 <span data-ttu-id="eebb4-178">如果右键单击 AS2 消息和相关 MDN 状态报告中列出的 AS2 消息，则可以显示下列其中一种更详细的状态报告：</span><span class="sxs-lookup"><span data-stu-id="eebb4-178">If you right-click an AS2 message listed in the AS2 Message and Correlated MDN status report, you can display one of the following more detailed status reports:</span></span>  
  
|<span data-ttu-id="eebb4-179">状态报表</span><span class="sxs-lookup"><span data-stu-id="eebb4-179">Status Report</span></span>|<span data-ttu-id="eebb4-180">显示的状态</span><span class="sxs-lookup"><span data-stu-id="eebb4-180">Status Displayed</span></span>|  
|-------------------|----------------------|  
|<span data-ttu-id="eebb4-181">交换/ACK 状态</span><span class="sxs-lookup"><span data-stu-id="eebb4-181">Interchange/ACK Status</span></span>|<span data-ttu-id="eebb4-182">AS2 消息的 EDI 负载的状态</span><span class="sxs-lookup"><span data-stu-id="eebb4-182">The status of the EDI payload of the AS2 message</span></span>|  
|<span data-ttu-id="eebb4-183">重新发送状态详细信息</span><span class="sxs-lookup"><span data-stu-id="eebb4-183">Resend Status Details</span></span>|<span data-ttu-id="eebb4-184">消息的重新发送状态</span><span class="sxs-lookup"><span data-stu-id="eebb4-184">The resend status of the message</span></span>|  
|<span data-ttu-id="eebb4-185">消息传输格式</span><span class="sxs-lookup"><span data-stu-id="eebb4-185">Message Wire Format</span></span>|<span data-ttu-id="eebb4-186">AS2 消息的传输格式</span><span class="sxs-lookup"><span data-stu-id="eebb4-186">The wire format of the AS2 message</span></span>|  
|<span data-ttu-id="eebb4-187">解码的消息</span><span class="sxs-lookup"><span data-stu-id="eebb4-187">Message Decoded</span></span>|<span data-ttu-id="eebb4-188">AS2 消息的解码格式</span><span class="sxs-lookup"><span data-stu-id="eebb4-188">The decoded format of the AS2 message</span></span>|  
|<span data-ttu-id="eebb4-189">MDN 消息</span><span class="sxs-lookup"><span data-stu-id="eebb4-189">MDN Message</span></span>|<span data-ttu-id="eebb4-190">与 AS2 消息相关的 MDN 消息</span><span class="sxs-lookup"><span data-stu-id="eebb4-190">The MDN message correlated to the AS2 message</span></span>|  
  
 <span data-ttu-id="eebb4-191">最后三个消息中的每个消息格式都相同。</span><span class="sxs-lookup"><span data-stu-id="eebb4-191">The format of each of the final three messages is the same.</span></span> <span data-ttu-id="eebb4-192">有关详细信息，请参阅[AS2 消息内容状态报表](../core/as2-message-content-status-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="eebb4-192">For more information, see [AS2 Message Content Status Reports](../core/as2-message-content-status-reports.md).</span></span>  
  
## <a name="correlate-an-as2-message-with-its-edi-payload"></a><span data-ttu-id="eebb4-193">关联 AS2 消息具有其 EDI 负载</span><span class="sxs-lookup"><span data-stu-id="eebb4-193">Correlate an AS2 Message with its EDI Payload</span></span>  
 <span data-ttu-id="eebb4-194">利用 AS2 和 EDI 状态报告，您可以将 AS2 消息的状态条目与其 EDI 负载的状态条目相关联。</span><span class="sxs-lookup"><span data-stu-id="eebb4-194">AS2 and EDI status reporting enables you to correlate status entries for an AS2 message and its EDI payload.</span></span> <span data-ttu-id="eebb4-195">如果已启用 AS2 和 EDI 状态报告，则在 AS2 状态报告中为 AS2 消息生成一个状态条目并在 EDI 状态报告中为该 AS2 消息的 EDI 负载生成一个状态条目。</span><span class="sxs-lookup"><span data-stu-id="eebb4-195">If you have enabled both AS2 and EDI status reporting, a status entry is made in the AS2 status report for the AS2 message and a status entry is made in the EDI status report for the EDI payload of that AS2 message.</span></span> <span data-ttu-id="eebb4-196">如果你有显示 AS2 状态报表，你可以通过右键单击 AS2 消息状态条目，然后单击显示的 AS2 消息的 EDI 负载状态**交换/ACK 状态**。</span><span class="sxs-lookup"><span data-stu-id="eebb4-196">If you have the AS2 status report displayed, you can display the status of the EDI payload for an AS2 message by right-clicking the AS2 message status entry, and then clicking **Interchange/ACK Status**.</span></span> <span data-ttu-id="eebb4-197">如果 AS2 消息中只有一个 EDI 交换，此操作将为该交换调出状态条目。</span><span class="sxs-lookup"><span data-stu-id="eebb4-197">If there is only one EDI interchange in the AS2 message, this action will bring up the status entry for that one interchange.</span></span>  
  
 <span data-ttu-id="eebb4-198">如果此 AS2 消息包含多个 EDI 交换，并且您试图显示该 AS2 消息中多个 EDI 交换的状态，则在交换/ACK 状态报告中将只显示最后一个 EDI 交换。</span><span class="sxs-lookup"><span data-stu-id="eebb4-198">If the AS2 message contains multiple EDI interchanges, and you attempt to display the status of the multiple EDI interchanges in the AS2 message, only the last EDI interchange will be displayed in the Interchange/ACK status report.</span></span> <span data-ttu-id="eebb4-199">此外， **EDI 交换控制否**AS2/MDN 状态报告中的字段将仅显示最后一个的交换控制编号。</span><span class="sxs-lookup"><span data-stu-id="eebb4-199">In addition, the **EDI Interchange Control No** field in the AS2/MDN Status report will only show the last interchange control number.</span></span> <span data-ttu-id="eebb4-200">（该交换控制编号将 AS2 消息与其 EDI 交换负载关联起来。）</span><span class="sxs-lookup"><span data-stu-id="eebb4-200">(The interchange control number correlates the AS2 message and its EDI interchange payload.)</span></span>  
  
 <span data-ttu-id="eebb4-201">AS2 消息中所有 EDI 交换的数据都保存在状态报告数据库中。</span><span class="sxs-lookup"><span data-stu-id="eebb4-201">The data for all EDI interchanges in an AS2 message is saved in the status report database.</span></span> <span data-ttu-id="eebb4-202">你可以在交换/ACK 状态报表采用的 AS2 消息中显示所有的交换，如果**控件 ID 等于所有**子句是状态报表查询中。</span><span class="sxs-lookup"><span data-stu-id="eebb4-202">You can display all interchanges in an AS2 message in the Interchange/ACK Status report if the **Control ID Equals All** clause is in the status report query.</span></span> <span data-ttu-id="eebb4-203">这还可能显示不属于 AS2 消息的其他交换；但是，通过查看其他字段（如“发送方”、“接收方”和“交换日期时间”），您可以确定 AS2 消息中有哪些 EDI 交换。</span><span class="sxs-lookup"><span data-stu-id="eebb4-203">This will also potentially display other interchanges that are not in the AS2 message; however, you can determine which EDI interchanges are in a single AS2 message by looking at other fields, such as the Sender party, Receiver party, and Interchange Date Time.</span></span>  
  
 <span data-ttu-id="eebb4-204">**方角色**AS2 状态报表中的字段和**方向**EDI 状态报表字段是相反的意义。</span><span class="sxs-lookup"><span data-stu-id="eebb4-204">The **Party role** field in the AS2 status report and the **Direction** field in the EDI status report are opposite in their meaning.</span></span> <span data-ttu-id="eebb4-205">使用 EDI 负载，传入 AS2 消息的**方角色**字段将 AS2 消息**发件人**，虽然**方向**字段 EDI 交换将**接收**。</span><span class="sxs-lookup"><span data-stu-id="eebb4-205">For an incoming AS2 message with an EDI payload, the **Party role** field for the AS2 message would be **Sender**, while the **Direction** field for the EDI interchange would be **Receive**.</span></span> <span data-ttu-id="eebb4-206">其原因在于对于从参与方接收的传入消息来说，参与方的角色是发送方。</span><span class="sxs-lookup"><span data-stu-id="eebb4-206">The reason for this is that for an incoming message received from a party, the role of that party is a sender.</span></span> <span data-ttu-id="eebb4-207">与其所发送的 AS2 消息相关的参与方的属性是作为 AS2 消息发送方的参与方的属性，它是在“合作伙伴协议管理器”的“AS2 属性”对话框中定义的。</span><span class="sxs-lookup"><span data-stu-id="eebb4-207">The properties of that party related to an AS2 message that it sends are that of party as AS2 message sender, as defined in the AS2 Properties dialog box in the Partner Agreement Management.</span></span> <span data-ttu-id="eebb4-208">因此，AS2 参与方角色与 EDI 方向的含义相反。</span><span class="sxs-lookup"><span data-stu-id="eebb4-208">As a result, the AS2 party role is opposite to the EDI direction.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="eebb4-209">后续步骤</span><span class="sxs-lookup"><span data-stu-id="eebb4-209">Next steps</span></span>
  
-   [<span data-ttu-id="eebb4-210">AS2 消息内容状态报表</span><span class="sxs-lookup"><span data-stu-id="eebb4-210">AS2 Message Content Status Reports</span></span>](../core/as2-message-content-status-reports.md)  
  
-   [<span data-ttu-id="eebb4-211">重新发送状态详细信息报表</span><span class="sxs-lookup"><span data-stu-id="eebb4-211">Resend Status Details Report</span></span>](../core/resend-status-details-report.md)  
  
## <a name="see-also"></a><span data-ttu-id="eebb4-212">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eebb4-212">See Also</span></span>  
 [<span data-ttu-id="eebb4-213">AS2 消息和相关的 MDN 状态报表</span><span class="sxs-lookup"><span data-stu-id="eebb4-213">AS2 Message and Correlated MDN Status Report</span></span>](../core/as2-message-and-correlated-mdn-status-report.md)   
