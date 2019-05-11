---
title: AS2 消息和相关的 MDN 状态报告 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 48ed0ee3-c844-4cb9-a84d-32b719ab8fab
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49bdfbc54ffa393733e8622226eab0b2652634b9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358907"
---
# <a name="as2-message-and-correlated-mdn-status-report"></a><span data-ttu-id="643e0-102">AS2 消息和相关的 MDN 状态报告</span><span class="sxs-lookup"><span data-stu-id="643e0-102">AS2 Message and Correlated MDN Status Report</span></span>
<span data-ttu-id="643e0-103">此报表显示所有由 AS2 处理的 AS2 消息发送和接收管道，以及与这些交换相关的 Mdn。</span><span class="sxs-lookup"><span data-stu-id="643e0-103">This report shows all AS2 messages that are processed by the AS2 send and receive pipelines, and the MDNs correlated to those interchanges.</span></span>  
  
## <a name="fields-in-the-status-report"></a><span data-ttu-id="643e0-104">在状态报告中的字段</span><span class="sxs-lookup"><span data-stu-id="643e0-104">Fields in the Status Report</span></span>  
 <span data-ttu-id="643e0-105">AS2 消息和相关 ACK 状态报告显示这些接收或发送交换和相关确认的以下信息：</span><span class="sxs-lookup"><span data-stu-id="643e0-105">The AS2 Message and Correlated ACK Status Report displays the following information for the received or sent interchanges and the acknowledgments that are correlated to them:</span></span>  
  
-   <span data-ttu-id="643e0-106">发送方的参与方名称</span><span class="sxs-lookup"><span data-stu-id="643e0-106">Sender Party Name</span></span>  
  
-   <span data-ttu-id="643e0-107">接收方的参与方名称</span><span class="sxs-lookup"><span data-stu-id="643e0-107">Receiver Party Name</span></span>  
  
-   <span data-ttu-id="643e0-108">As2 发件人</span><span class="sxs-lookup"><span data-stu-id="643e0-108">AS2 From</span></span>  
  
-   <span data-ttu-id="643e0-109">AS2 收件人</span><span class="sxs-lookup"><span data-stu-id="643e0-109">AS2 To</span></span>  
  
-   <span data-ttu-id="643e0-110">AS2 消息 ID</span><span class="sxs-lookup"><span data-stu-id="643e0-110">AS2 Message ID</span></span>  
  
-   <span data-ttu-id="643e0-111">AS2 消息日期时间</span><span class="sxs-lookup"><span data-stu-id="643e0-111">AS2 Message Date Time</span></span>  
  
-   <span data-ttu-id="643e0-112">接收的日期时间</span><span class="sxs-lookup"><span data-stu-id="643e0-112">Received Date Time</span></span>  
  
-   <span data-ttu-id="643e0-113">参与方角色</span><span class="sxs-lookup"><span data-stu-id="643e0-113">Party Role</span></span>  
  
-   <span data-ttu-id="643e0-114">MDN 状态</span><span class="sxs-lookup"><span data-stu-id="643e0-114">MDN Status</span></span>  
  
-   <span data-ttu-id="643e0-115">加密状态</span><span class="sxs-lookup"><span data-stu-id="643e0-115">Encryption Status</span></span>  
  
-   <span data-ttu-id="643e0-116">签名状态</span><span class="sxs-lookup"><span data-stu-id="643e0-116">Signature Status</span></span>  
  
-   <span data-ttu-id="643e0-117">Edi 交换状态</span><span class="sxs-lookup"><span data-stu-id="643e0-117">Edi Interchange Status</span></span>  
  
-   <span data-ttu-id="643e0-118">AS2 消息重复</span><span class="sxs-lookup"><span data-stu-id="643e0-118">Is AS2 Message duplicate</span></span>  
  
-   <span data-ttu-id="643e0-119">检查重复的天数</span><span class="sxs-lookup"><span data-stu-id="643e0-119">Days to check for duplicate</span></span>  
  
-   <span data-ttu-id="643e0-120">Filename</span><span class="sxs-lookup"><span data-stu-id="643e0-120">Filename</span></span>  
  
-   <span data-ttu-id="643e0-121">启用可靠消息传送</span><span class="sxs-lookup"><span data-stu-id="643e0-121">Reliable messaging enabled</span></span>  
  
## <a name="fields-in-the-query-expression-for-the-status-report"></a><span data-ttu-id="643e0-122">在状态报告的查询表达式中的字段</span><span class="sxs-lookup"><span data-stu-id="643e0-122">Fields in the Query Expression for the Status Report</span></span>  
 <span data-ttu-id="643e0-123">可以通过更改用于确定所显示数据的查询表达式中的字段来自定义 AS2 消息和相关 ACK 状态报告。</span><span class="sxs-lookup"><span data-stu-id="643e0-123">You can customize the AS2 Message and Correlated ACK Status Report by changing the fields in the query expression that determines the data displayed.</span></span> <span data-ttu-id="643e0-124">可以使用下列域：</span><span class="sxs-lookup"><span data-stu-id="643e0-124">The following fields are available:</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="643e0-125">查询表达式字段</span><span class="sxs-lookup"><span data-stu-id="643e0-125">Query Expression Field</span></span>|<span data-ttu-id="643e0-126">可能的运算符</span><span class="sxs-lookup"><span data-stu-id="643e0-126">Potential Operators</span></span>|<span data-ttu-id="643e0-127">可能的值</span><span class="sxs-lookup"><span data-stu-id="643e0-127">Potential Values</span></span>|<span data-ttu-id="643e0-128">默认情况下包含？</span><span class="sxs-lookup"><span data-stu-id="643e0-128">Included By Default?</span></span>|  
|<span data-ttu-id="643e0-129">搜索</span><span class="sxs-lookup"><span data-stu-id="643e0-129">Search for</span></span>|<span data-ttu-id="643e0-130">等于</span><span class="sxs-lookup"><span data-stu-id="643e0-130">Equals</span></span>|<span data-ttu-id="643e0-131">AS2/MDN 状态</span><span class="sxs-lookup"><span data-stu-id="643e0-131">AS2/MDN Status</span></span>|<span data-ttu-id="643e0-132">是（必需）</span><span class="sxs-lookup"><span data-stu-id="643e0-132">Yes (required)</span></span>|  
|<span data-ttu-id="643e0-133">消息状态</span><span class="sxs-lookup"><span data-stu-id="643e0-133">Message Status</span></span>|<span data-ttu-id="643e0-134">等于</span><span class="sxs-lookup"><span data-stu-id="643e0-134">Equals</span></span><br /><br /> <span data-ttu-id="643e0-135">不等于</span><span class="sxs-lookup"><span data-stu-id="643e0-135">Not Equals</span></span>|<span data-ttu-id="643e0-136">All</span><span class="sxs-lookup"><span data-stu-id="643e0-136">All</span></span><br /><br /> <span data-ttu-id="643e0-137">已确认-已处理</span><span class="sxs-lookup"><span data-stu-id="643e0-137">Acknowledged - Processed</span></span><br /><br /> <span data-ttu-id="643e0-138">已确认-失败</span><span class="sxs-lookup"><span data-stu-id="643e0-138">Acknowledged - Failed</span></span><br /><br /> <span data-ttu-id="643e0-139">已处理-MDN 挂起</span><span class="sxs-lookup"><span data-stu-id="643e0-139">Processed - MDN pending</span></span><br /><br /> <span data-ttu-id="643e0-140">已处理-非预期的 MDN</span><span class="sxs-lookup"><span data-stu-id="643e0-140">Processed - MDN not expected</span></span><br /><br /> <span data-ttu-id="643e0-141">未确认 – 超过重新发送尝试次数</span><span class="sxs-lookup"><span data-stu-id="643e0-141">Not acknowledged – Resend attempts exceeded</span></span><br /><br /> <span data-ttu-id="643e0-142">未确认 – 重新发送持续时间超过</span><span class="sxs-lookup"><span data-stu-id="643e0-142">Not acknowledged – Resend duration exceeded</span></span>|<span data-ttu-id="643e0-143">是</span><span class="sxs-lookup"><span data-stu-id="643e0-143">Yes</span></span>|  
|<span data-ttu-id="643e0-144">AS2 消息日期时间</span><span class="sxs-lookup"><span data-stu-id="643e0-144">AS2 Message Date Time</span></span>|<span data-ttu-id="643e0-145">小于或等于</span><span class="sxs-lookup"><span data-stu-id="643e0-145">Less Than or Equals</span></span><br /><br /> <span data-ttu-id="643e0-146">大于或等于</span><span class="sxs-lookup"><span data-stu-id="643e0-146">Greater Than or Equals</span></span>|<span data-ttu-id="643e0-147">特定日期时间</span><span class="sxs-lookup"><span data-stu-id="643e0-147">Specific Date Time</span></span><br /><br /> <span data-ttu-id="643e0-148">今天</span><span class="sxs-lookup"><span data-stu-id="643e0-148">Today</span></span><br /><br /> <span data-ttu-id="643e0-149">Today-1</span><span class="sxs-lookup"><span data-stu-id="643e0-149">Today - 1</span></span>|<span data-ttu-id="643e0-150">是</span><span class="sxs-lookup"><span data-stu-id="643e0-150">Yes</span></span><br /><br /> <span data-ttu-id="643e0-151">注意：可以包含多个查询表达式中。</span><span class="sxs-lookup"><span data-stu-id="643e0-151">Note: Can be included more than once in the query expression.</span></span>|  
|<span data-ttu-id="643e0-152">最大匹配数</span><span class="sxs-lookup"><span data-stu-id="643e0-152">Maximum Matches</span></span>|<span data-ttu-id="643e0-153">等于</span><span class="sxs-lookup"><span data-stu-id="643e0-153">Equals</span></span>|<span data-ttu-id="643e0-154">整数 （默认值为 50）</span><span class="sxs-lookup"><span data-stu-id="643e0-154">Integer (default of 50)</span></span>|<span data-ttu-id="643e0-155">是</span><span class="sxs-lookup"><span data-stu-id="643e0-155">Yes</span></span>|  
|<span data-ttu-id="643e0-156">AS2 消息 ID</span><span class="sxs-lookup"><span data-stu-id="643e0-156">AS2 Message ID</span></span>|<span data-ttu-id="643e0-157">等于</span><span class="sxs-lookup"><span data-stu-id="643e0-157">Equals</span></span>|<span data-ttu-id="643e0-158">All</span><span class="sxs-lookup"><span data-stu-id="643e0-158">All</span></span><br /><br /> <span data-ttu-id="643e0-159">特定的 AS2 消息 ID</span><span class="sxs-lookup"><span data-stu-id="643e0-159">Specific AS2 Message ID</span></span>|<span data-ttu-id="643e0-160">否</span><span class="sxs-lookup"><span data-stu-id="643e0-160">No</span></span>|  
|<span data-ttu-id="643e0-161">Direction</span><span class="sxs-lookup"><span data-stu-id="643e0-161">Direction</span></span>|<span data-ttu-id="643e0-162">等于</span><span class="sxs-lookup"><span data-stu-id="643e0-162">Equals</span></span>|<span data-ttu-id="643e0-163">所有 （默认值）</span><span class="sxs-lookup"><span data-stu-id="643e0-163">All (default)</span></span><br /><br /> <span data-ttu-id="643e0-164">Receive</span><span class="sxs-lookup"><span data-stu-id="643e0-164">Receive</span></span><br /><br /> <span data-ttu-id="643e0-165">Send</span><span class="sxs-lookup"><span data-stu-id="643e0-165">Send</span></span>|<span data-ttu-id="643e0-166">否</span><span class="sxs-lookup"><span data-stu-id="643e0-166">No</span></span>|  
|<span data-ttu-id="643e0-167">接收方的参与方名称</span><span class="sxs-lookup"><span data-stu-id="643e0-167">Receiver Party Name</span></span>|<span data-ttu-id="643e0-168">等于</span><span class="sxs-lookup"><span data-stu-id="643e0-168">Equals</span></span>|<span data-ttu-id="643e0-169">所有 （默认值）</span><span class="sxs-lookup"><span data-stu-id="643e0-169">All (default)</span></span><br /><br /> <span data-ttu-id="643e0-170">特定参与方名称</span><span class="sxs-lookup"><span data-stu-id="643e0-170">Specific party name</span></span>|<span data-ttu-id="643e0-171">否</span><span class="sxs-lookup"><span data-stu-id="643e0-171">No</span></span>|  
|<span data-ttu-id="643e0-172">发送方的参与方名称</span><span class="sxs-lookup"><span data-stu-id="643e0-172">Sender Party Name</span></span>|<span data-ttu-id="643e0-173">等于</span><span class="sxs-lookup"><span data-stu-id="643e0-173">Equals</span></span>|<span data-ttu-id="643e0-174">所有 （默认值）</span><span class="sxs-lookup"><span data-stu-id="643e0-174">All (default)</span></span><br /><br /> <span data-ttu-id="643e0-175">特定参与方名称</span><span class="sxs-lookup"><span data-stu-id="643e0-175">Specific party name</span></span>|<span data-ttu-id="643e0-176">否</span><span class="sxs-lookup"><span data-stu-id="643e0-176">No</span></span>|  
  
## <a name="additional-as2-message-and-correlated-mdn-status-reports"></a><span data-ttu-id="643e0-177">其他 AS2 消息和相关的 MDN 状态报告</span><span class="sxs-lookup"><span data-stu-id="643e0-177">Additional AS2 Message and Correlated MDN Status Reports</span></span>  
 <span data-ttu-id="643e0-178">如果右键单击 AS2 消息和相关 MDN 状态报告中列出的 AS2 消息，则可以显示一个详细的以下状态报告：</span><span class="sxs-lookup"><span data-stu-id="643e0-178">If you right-click an AS2 message listed in the AS2 Message and Correlated MDN status report, you can display one of the following more detailed status reports:</span></span>  
  
|<span data-ttu-id="643e0-179">状态报告</span><span class="sxs-lookup"><span data-stu-id="643e0-179">Status Report</span></span>|<span data-ttu-id="643e0-180">显示状态</span><span class="sxs-lookup"><span data-stu-id="643e0-180">Status Displayed</span></span>|  
|-------------------|----------------------|  
|<span data-ttu-id="643e0-181">交换 /ACK 状态</span><span class="sxs-lookup"><span data-stu-id="643e0-181">Interchange/ACK Status</span></span>|<span data-ttu-id="643e0-182">AS2 消息的 EDI 负载的状态</span><span class="sxs-lookup"><span data-stu-id="643e0-182">The status of the EDI payload of the AS2 message</span></span>|  
|<span data-ttu-id="643e0-183">重新发送状态详细信息</span><span class="sxs-lookup"><span data-stu-id="643e0-183">Resend Status Details</span></span>|<span data-ttu-id="643e0-184">该消息重新发送状态</span><span class="sxs-lookup"><span data-stu-id="643e0-184">The resend status of the message</span></span>|  
|<span data-ttu-id="643e0-185">消息传输格式</span><span class="sxs-lookup"><span data-stu-id="643e0-185">Message Wire Format</span></span>|<span data-ttu-id="643e0-186">AS2 消息传输格式</span><span class="sxs-lookup"><span data-stu-id="643e0-186">The wire format of the AS2 message</span></span>|  
|<span data-ttu-id="643e0-187">解码的消息</span><span class="sxs-lookup"><span data-stu-id="643e0-187">Message Decoded</span></span>|<span data-ttu-id="643e0-188">AS2 消息解码的格式</span><span class="sxs-lookup"><span data-stu-id="643e0-188">The decoded format of the AS2 message</span></span>|  
|<span data-ttu-id="643e0-189">MDN 消息</span><span class="sxs-lookup"><span data-stu-id="643e0-189">MDN Message</span></span>|<span data-ttu-id="643e0-190">与 AS2 消息相关的 MDN 消息</span><span class="sxs-lookup"><span data-stu-id="643e0-190">The MDN message correlated to the AS2 message</span></span>|  
  
 <span data-ttu-id="643e0-191">每个最终的三个消息的格式是相同的。</span><span class="sxs-lookup"><span data-stu-id="643e0-191">The format of each of the final three messages is the same.</span></span> <span data-ttu-id="643e0-192">有关详细信息，请参阅[AS2 消息内容状态报告](../core/as2-message-content-status-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="643e0-192">For more information, see [AS2 Message Content Status Reports](../core/as2-message-content-status-reports.md).</span></span>  
  
## <a name="correlate-an-as2-message-with-its-edi-payload"></a><span data-ttu-id="643e0-193">将 AS2 消息与其 EDI 负载相关联</span><span class="sxs-lookup"><span data-stu-id="643e0-193">Correlate an AS2 Message with its EDI Payload</span></span>  
 <span data-ttu-id="643e0-194">AS2 和 EDI 状态报告，可将 AS2 消息与其 EDI 负载的状态条目相关联。</span><span class="sxs-lookup"><span data-stu-id="643e0-194">AS2 and EDI status reporting enables you to correlate status entries for an AS2 message and its EDI payload.</span></span> <span data-ttu-id="643e0-195">如果已启用 AS2 和 EDI 状态报告，AS2 消息在 AS2 状态报告中建立了一个状态条目，并且该 AS2 消息的 EDI 负载在 EDI 状态报告中建立了一个状态条目。</span><span class="sxs-lookup"><span data-stu-id="643e0-195">If you have enabled both AS2 and EDI status reporting, a status entry is made in the AS2 status report for the AS2 message and a status entry is made in the EDI status report for the EDI payload of that AS2 message.</span></span> <span data-ttu-id="643e0-196">如果必须显示在 AS2 状态报告，则可以通过右键单击 AS2 消息状态条目，然后单击显示的 EDI 负载的 AS2 消息的状态**交换 /ACK 状态**。</span><span class="sxs-lookup"><span data-stu-id="643e0-196">If you have the AS2 status report displayed, you can display the status of the EDI payload for an AS2 message by right-clicking the AS2 message status entry, and then clicking **Interchange/ACK Status**.</span></span> <span data-ttu-id="643e0-197">如果 AS2 消息中只有一个 EDI 交换，此操作将显示为该交换的状态条目。</span><span class="sxs-lookup"><span data-stu-id="643e0-197">If there is only one EDI interchange in the AS2 message, this action will bring up the status entry for that one interchange.</span></span>  
  
 <span data-ttu-id="643e0-198">如果 AS2 消息包含多个 EDI 交换，并且您尝试显示 AS2 消息中的多个 EDI 交换的状态，则将在交换 /ACK 状态报告中显示仅最后一个 EDI 交换。</span><span class="sxs-lookup"><span data-stu-id="643e0-198">If the AS2 message contains multiple EDI interchanges, and you attempt to display the status of the multiple EDI interchanges in the AS2 message, only the last EDI interchange will be displayed in the Interchange/ACK status report.</span></span> <span data-ttu-id="643e0-199">此外， **EDI 交换控制编号**AS2/MDN 状态报告中的字段将只显示最后一个交换控制编号。</span><span class="sxs-lookup"><span data-stu-id="643e0-199">In addition, the **EDI Interchange Control No** field in the AS2/MDN Status report will only show the last interchange control number.</span></span> <span data-ttu-id="643e0-200">（交换控制编号关联 AS2 消息与其 EDI 交换负载。）</span><span class="sxs-lookup"><span data-stu-id="643e0-200">(The interchange control number correlates the AS2 message and its EDI interchange payload.)</span></span>  
  
 <span data-ttu-id="643e0-201">AS2 消息中的所有 EDI 交换的数据保存在状态报告数据库。</span><span class="sxs-lookup"><span data-stu-id="643e0-201">The data for all EDI interchanges in an AS2 message is saved in the status report database.</span></span> <span data-ttu-id="643e0-202">如果在交换 /ACK 状态报告中的 AS2 消息中显示的所有交换**控制 ID 等于全部**子句位于状态报告查询。</span><span class="sxs-lookup"><span data-stu-id="643e0-202">You can display all interchanges in an AS2 message in the Interchange/ACK Status report if the **Control ID Equals All** clause is in the status report query.</span></span> <span data-ttu-id="643e0-203">这还可能显示不在 AS2 消息中; 中的其他交换但是，可以确定哪些 EDI 交换中一条 AS2 消息是通过查看其他字段，例如发送方、 接收方和交换日期时间。</span><span class="sxs-lookup"><span data-stu-id="643e0-203">This will also potentially display other interchanges that are not in the AS2 message; however, you can determine which EDI interchanges are in a single AS2 message by looking at other fields, such as the Sender party, Receiver party, and Interchange Date Time.</span></span>  
  
 <span data-ttu-id="643e0-204">**参与方角色**AS2 状态报告中的字段和**方向**EDI 状态报告中字段的意义是相反。</span><span class="sxs-lookup"><span data-stu-id="643e0-204">The **Party role** field in the AS2 status report and the **Direction** field in the EDI status report are opposite in their meaning.</span></span> <span data-ttu-id="643e0-205">带有 EDI 负载的传入 AS2 消息**参与方角色**字段为 AS2 消息**发件人**，而**方向**字段为 EDI 交换**接收**。</span><span class="sxs-lookup"><span data-stu-id="643e0-205">For an incoming AS2 message with an EDI payload, the **Party role** field for the AS2 message would be **Sender**, while the **Direction** field for the EDI interchange would be **Receive**.</span></span> <span data-ttu-id="643e0-206">这样做的原因是从参与方接收的传入消息，该参与方的角色是发送方。</span><span class="sxs-lookup"><span data-stu-id="643e0-206">The reason for this is that for an incoming message received from a party, the role of that party is a sender.</span></span> <span data-ttu-id="643e0-207">该参与方的属性与它发送是作为 AS2 消息发送方的参与方定义在合作伙伴协议管理中的 AS2 属性对话框中的 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="643e0-207">The properties of that party related to an AS2 message that it sends are that of party as AS2 message sender, as defined in the AS2 Properties dialog box in the Partner Agreement Management.</span></span> <span data-ttu-id="643e0-208">因此，AS2 参与方角色是与 EDI 方向相反。</span><span class="sxs-lookup"><span data-stu-id="643e0-208">As a result, the AS2 party role is opposite to the EDI direction.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="643e0-209">后续步骤</span><span class="sxs-lookup"><span data-stu-id="643e0-209">Next steps</span></span>
  
-   [<span data-ttu-id="643e0-210">AS2 消息内容状态报告</span><span class="sxs-lookup"><span data-stu-id="643e0-210">AS2 Message Content Status Reports</span></span>](../core/as2-message-content-status-reports.md)  
  
-   [<span data-ttu-id="643e0-211">重新发送状态详细信息报告</span><span class="sxs-lookup"><span data-stu-id="643e0-211">Resend Status Details Report</span></span>](../core/resend-status-details-report.md)  
  
## <a name="see-also"></a><span data-ttu-id="643e0-212">请参阅</span><span class="sxs-lookup"><span data-stu-id="643e0-212">See Also</span></span>  
 [<span data-ttu-id="643e0-213">AS2 消息和相关 MDN 状态报告</span><span class="sxs-lookup"><span data-stu-id="643e0-213">AS2 Message and Correlated MDN Status Report</span></span>](../core/as2-message-and-correlated-mdn-status-report.md)   
