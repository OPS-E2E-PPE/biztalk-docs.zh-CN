---
title: EDI 交换和相关的 ACK 状态报告 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a112cc3d-d34c-4652-a8ee-3355a31d4a03
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c7a1246da341cc984995b2222681cb8164919e5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350625"
---
# <a name="edi-interchange-and-correlated-ack-status-report"></a><span data-ttu-id="3fef2-102">EDI 交换和相关 ACK 状态报告</span><span class="sxs-lookup"><span data-stu-id="3fef2-102">EDI Interchange and Correlated ACK Status Report</span></span>
<span data-ttu-id="3fef2-103">此报表显示所有 EDI 交换的 edi 处理发送和接收管道，以及与这些交换相关的确认。</span><span class="sxs-lookup"><span data-stu-id="3fef2-103">This report shows all EDI interchanges that are processed by the EDI send and receive pipelines, and the acknowledgment correlated to those interchanges.</span></span>  
  
## <a name="fields-in-the-status-report"></a><span data-ttu-id="3fef2-104">在状态报告中的字段</span><span class="sxs-lookup"><span data-stu-id="3fef2-104">Fields in the Status Report</span></span>  
 <span data-ttu-id="3fef2-105">EDI 交换和相关 ACK 状态报告显示这些接收或发送交换和相关确认的以下信息：</span><span class="sxs-lookup"><span data-stu-id="3fef2-105">The EDI Interchange and Correlated ACK Status Report displays the following information for the received or sent interchanges and the acknowledgments that are correlated to them:</span></span>  
  
- <span data-ttu-id="3fef2-106">发送方</span><span class="sxs-lookup"><span data-stu-id="3fef2-106">Sender Party</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="3fef2-107">发送方将按如下所示确定：</span><span class="sxs-lookup"><span data-stu-id="3fef2-107">The sender party will be determined as follows:</span></span>  
  > 
  > - <span data-ttu-id="3fef2-108">如果交换中的参与方名称与参与方 EDI 属性中配置的名称相匹配，则会显示配置的名称。</span><span class="sxs-lookup"><span data-stu-id="3fef2-108">If the party name in the interchange matches the name configured in the EDI Properties for a party, then the configured name is displayed.</span></span>  
  >   -   <span data-ttu-id="3fef2-109">如果交换中的参与方名称不匹配任何已配置的 EDI 属性的现有参与方，则会显示在交换中指定的参与方名称。</span><span class="sxs-lookup"><span data-stu-id="3fef2-109">If the party name in the interchange does not match any of the configured EDI Properties for existing parties, the party name specified in the interchange is displayed.</span></span>  
  
- <span data-ttu-id="3fef2-110">接收方</span><span class="sxs-lookup"><span data-stu-id="3fef2-110">Receiver Party</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="3fef2-111">接收方的参与方名称将按如下所示确定：</span><span class="sxs-lookup"><span data-stu-id="3fef2-111">The receiver party name will be determined as follows:</span></span>  
  > 
  > - <span data-ttu-id="3fef2-112">如果交换中的参与方名称与参与方 EDI 属性中配置的名称相匹配，则会显示配置的名称。</span><span class="sxs-lookup"><span data-stu-id="3fef2-112">If the party name in the interchange matches the name configured in the EDI Properties for a party, then the configured name is displayed.</span></span>  
  >   -   <span data-ttu-id="3fef2-113">如果交换中的参与方名称不匹配任何已配置的 EDI 属性的现有参与方，则会显示在交换中指定的参与方名称。</span><span class="sxs-lookup"><span data-stu-id="3fef2-113">If the party name in the interchange does not match any of the configured EDI Properties for existing parties, the party name specified in the interchange is displayed.</span></span>  
  
- <span data-ttu-id="3fef2-114">控件 ID</span><span class="sxs-lookup"><span data-stu-id="3fef2-114">Control ID</span></span>  
  
- <span data-ttu-id="3fef2-115">Direction</span><span class="sxs-lookup"><span data-stu-id="3fef2-115">Direction</span></span>  
  
- <span data-ttu-id="3fef2-116">交换日期时间</span><span class="sxs-lookup"><span data-stu-id="3fef2-116">Interchange Date Time</span></span>  
  
- <span data-ttu-id="3fef2-117">EDI 编码类型</span><span class="sxs-lookup"><span data-stu-id="3fef2-117">EDI encoding type</span></span>  
  
- <span data-ttu-id="3fef2-118">交换状态</span><span class="sxs-lookup"><span data-stu-id="3fef2-118">Interchange Status</span></span>  
  
- <span data-ttu-id="3fef2-119">组计数</span><span class="sxs-lookup"><span data-stu-id="3fef2-119">Group Count</span></span>  
  
- <span data-ttu-id="3fef2-120">端口 ID</span><span class="sxs-lookup"><span data-stu-id="3fef2-120">Port ID</span></span>  
  
- <span data-ttu-id="3fef2-121">发送方的参与方别名</span><span class="sxs-lookup"><span data-stu-id="3fef2-121">Sender Party Alias</span></span>  
  
- <span data-ttu-id="3fef2-122">接收方的参与方别名</span><span class="sxs-lookup"><span data-stu-id="3fef2-122">Receiver Party Alias</span></span>  
  
- <span data-ttu-id="3fef2-123">事务集相关 ID</span><span class="sxs-lookup"><span data-stu-id="3fef2-123">Transaction Set Correlation ID</span></span>  
  
## <a name="fields-in-the-query-expression-for-the-status-report"></a><span data-ttu-id="3fef2-124">在状态报告的查询表达式中的字段</span><span class="sxs-lookup"><span data-stu-id="3fef2-124">Fields in the Query Expression for the Status Report</span></span>  
 <span data-ttu-id="3fef2-125">可以通过更改用于确定所显示数据的查询表达式中的字段来自定义 EDI 交换和相关 ACK 状态报告。</span><span class="sxs-lookup"><span data-stu-id="3fef2-125">You can customize the EDI Interchange and Correlated ACK Status Report by changing the fields in the query expression that determines the data displayed.</span></span> <span data-ttu-id="3fef2-126">可以使用下列域：</span><span class="sxs-lookup"><span data-stu-id="3fef2-126">The following fields are available:</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="3fef2-127">查询表达式字段</span><span class="sxs-lookup"><span data-stu-id="3fef2-127">Query Expression Field</span></span>|<span data-ttu-id="3fef2-128">可能的运算符</span><span class="sxs-lookup"><span data-stu-id="3fef2-128">Potential Operators</span></span>|<span data-ttu-id="3fef2-129">可能的值</span><span class="sxs-lookup"><span data-stu-id="3fef2-129">Potential Values</span></span>|<span data-ttu-id="3fef2-130">默认情况下包含？</span><span class="sxs-lookup"><span data-stu-id="3fef2-130">Included By Default?</span></span>|  
|<span data-ttu-id="3fef2-131">搜索</span><span class="sxs-lookup"><span data-stu-id="3fef2-131">Search for</span></span>|<span data-ttu-id="3fef2-132">等于</span><span class="sxs-lookup"><span data-stu-id="3fef2-132">Equals</span></span>|<span data-ttu-id="3fef2-133">交换 /ACK 状态</span><span class="sxs-lookup"><span data-stu-id="3fef2-133">Interchange/ACK Status</span></span>|<span data-ttu-id="3fef2-134">是（必需）</span><span class="sxs-lookup"><span data-stu-id="3fef2-134">Yes (required)</span></span>|  
|<span data-ttu-id="3fef2-135">“登录属性”</span><span class="sxs-lookup"><span data-stu-id="3fef2-135">Status</span></span>|<span data-ttu-id="3fef2-136">等于</span><span class="sxs-lookup"><span data-stu-id="3fef2-136">Equals</span></span><br /><br /> <span data-ttu-id="3fef2-137">不等于</span><span class="sxs-lookup"><span data-stu-id="3fef2-137">Not Equals</span></span>|<span data-ttu-id="3fef2-138">接受</span><span class="sxs-lookup"><span data-stu-id="3fef2-138">Accepted</span></span><br /><br /> <span data-ttu-id="3fef2-139">已接受但有错误</span><span class="sxs-lookup"><span data-stu-id="3fef2-139">Accepted with Errors</span></span><br /><br /> <span data-ttu-id="3fef2-140">发送</span><span class="sxs-lookup"><span data-stu-id="3fef2-140">Sent</span></span><br /><br /> <span data-ttu-id="3fef2-141">All</span><span class="sxs-lookup"><span data-stu-id="3fef2-141">All</span></span><br /><br /> <span data-ttu-id="3fef2-142">预期的确认</span><span class="sxs-lookup"><span data-stu-id="3fef2-142">Ack Expected</span></span><br /><br /> <span data-ttu-id="3fef2-143">非预期的确认</span><span class="sxs-lookup"><span data-stu-id="3fef2-143">Ack Not Expected</span></span><br /><br /> <span data-ttu-id="3fef2-144">已拒绝</span><span class="sxs-lookup"><span data-stu-id="3fef2-144">Rejected</span></span><br /><br /> <span data-ttu-id="3fef2-145">（这些值定义如下。）</span><span class="sxs-lookup"><span data-stu-id="3fef2-145">(These values are defined below.)</span></span>|<span data-ttu-id="3fef2-146">是</span><span class="sxs-lookup"><span data-stu-id="3fef2-146">Yes</span></span>|  
|<span data-ttu-id="3fef2-147">交换日期时间</span><span class="sxs-lookup"><span data-stu-id="3fef2-147">Interchange Date Time</span></span>|<span data-ttu-id="3fef2-148">小于或等于</span><span class="sxs-lookup"><span data-stu-id="3fef2-148">Less Than or Equals</span></span><br /><br /> <span data-ttu-id="3fef2-149">大于或等于</span><span class="sxs-lookup"><span data-stu-id="3fef2-149">Greater Than or Equals</span></span>|<span data-ttu-id="3fef2-150">特定日期时间</span><span class="sxs-lookup"><span data-stu-id="3fef2-150">Specific Date Time</span></span><br /><br /> <span data-ttu-id="3fef2-151">今天</span><span class="sxs-lookup"><span data-stu-id="3fef2-151">Today</span></span><br /><br /> <span data-ttu-id="3fef2-152">Today-1</span><span class="sxs-lookup"><span data-stu-id="3fef2-152">Today - 1</span></span>|<span data-ttu-id="3fef2-153">是</span><span class="sxs-lookup"><span data-stu-id="3fef2-153">Yes</span></span><br /><br /> <span data-ttu-id="3fef2-154">注意：可以包含多个查询表达式中。</span><span class="sxs-lookup"><span data-stu-id="3fef2-154">Note: Can be included more than once in the query expression.</span></span>|  
|<span data-ttu-id="3fef2-155">最大匹配数</span><span class="sxs-lookup"><span data-stu-id="3fef2-155">Maximum Matches</span></span>|<span data-ttu-id="3fef2-156">等于</span><span class="sxs-lookup"><span data-stu-id="3fef2-156">Equals</span></span>|<span data-ttu-id="3fef2-157">整数 （默认值为 50）</span><span class="sxs-lookup"><span data-stu-id="3fef2-157">Integer (default of 50)</span></span>|<span data-ttu-id="3fef2-158">是</span><span class="sxs-lookup"><span data-stu-id="3fef2-158">Yes</span></span>|  
|<span data-ttu-id="3fef2-159">控件 ID</span><span class="sxs-lookup"><span data-stu-id="3fef2-159">Control ID</span></span>|<span data-ttu-id="3fef2-160">等于</span><span class="sxs-lookup"><span data-stu-id="3fef2-160">Equals</span></span>|<span data-ttu-id="3fef2-161">交换控制 ID</span><span class="sxs-lookup"><span data-stu-id="3fef2-161">Interchange Control ID</span></span>|<span data-ttu-id="3fef2-162">否</span><span class="sxs-lookup"><span data-stu-id="3fef2-162">No</span></span>|  
|<span data-ttu-id="3fef2-163">Direction</span><span class="sxs-lookup"><span data-stu-id="3fef2-163">Direction</span></span>|<span data-ttu-id="3fef2-164">等于</span><span class="sxs-lookup"><span data-stu-id="3fef2-164">Equals</span></span>|<span data-ttu-id="3fef2-165">所有 （默认值）</span><span class="sxs-lookup"><span data-stu-id="3fef2-165">All (default)</span></span><br /><br /> <span data-ttu-id="3fef2-166">Receive</span><span class="sxs-lookup"><span data-stu-id="3fef2-166">Receive</span></span><br /><br /> <span data-ttu-id="3fef2-167">Send</span><span class="sxs-lookup"><span data-stu-id="3fef2-167">Send</span></span>|<span data-ttu-id="3fef2-168">否</span><span class="sxs-lookup"><span data-stu-id="3fef2-168">No</span></span>|  
|<span data-ttu-id="3fef2-169">接收方</span><span class="sxs-lookup"><span data-stu-id="3fef2-169">Receiver Party</span></span>|<span data-ttu-id="3fef2-170">等于</span><span class="sxs-lookup"><span data-stu-id="3fef2-170">Equals</span></span>|<span data-ttu-id="3fef2-171">所有 （默认值）</span><span class="sxs-lookup"><span data-stu-id="3fef2-171">All (default)</span></span><br /><br /> <span data-ttu-id="3fef2-172">特定参与方名称</span><span class="sxs-lookup"><span data-stu-id="3fef2-172">Specific party name</span></span>|<span data-ttu-id="3fef2-173">否</span><span class="sxs-lookup"><span data-stu-id="3fef2-173">No</span></span>|  
|<span data-ttu-id="3fef2-174">发送方</span><span class="sxs-lookup"><span data-stu-id="3fef2-174">Sender Party</span></span>|<span data-ttu-id="3fef2-175">等于</span><span class="sxs-lookup"><span data-stu-id="3fef2-175">Equals</span></span>|<span data-ttu-id="3fef2-176">所有 （默认值）</span><span class="sxs-lookup"><span data-stu-id="3fef2-176">All (default)</span></span><br /><br /> <span data-ttu-id="3fef2-177">特定参与方名称</span><span class="sxs-lookup"><span data-stu-id="3fef2-177">Specific party name</span></span>|<span data-ttu-id="3fef2-178">否</span><span class="sxs-lookup"><span data-stu-id="3fef2-178">No</span></span>|  
  
## <a name="status-definitions"></a><span data-ttu-id="3fef2-179">状态定义</span><span class="sxs-lookup"><span data-stu-id="3fef2-179">Status Definitions</span></span>  
 <span data-ttu-id="3fef2-180">使用 EDI 状态报告中的状态值具有以下定义：</span><span class="sxs-lookup"><span data-stu-id="3fef2-180">The status values used in EDI status reports have the following definitions:</span></span>  
  
- <span data-ttu-id="3fef2-181">已接受：交换有效</span><span class="sxs-lookup"><span data-stu-id="3fef2-181">Accepted: Valid interchange</span></span>  
  
- <span data-ttu-id="3fef2-182">已接受但有错误：错误记录在段</span><span class="sxs-lookup"><span data-stu-id="3fef2-182">Accepted with Errors: Errors were noted in segments</span></span>  
  
- <span data-ttu-id="3fef2-183">发送：已成功发送该交换</span><span class="sxs-lookup"><span data-stu-id="3fef2-183">Sent: The interchange was sent successfully</span></span>  
  
- <span data-ttu-id="3fef2-184">所有：显示一条消息与任何其他值</span><span class="sxs-lookup"><span data-stu-id="3fef2-184">All: Display a message with any of the other values</span></span>  
  
- <span data-ttu-id="3fef2-185">预期的确认</span><span class="sxs-lookup"><span data-stu-id="3fef2-185">Ack Expected</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="3fef2-186">交换状态和确认详细信息状态报告中的交换状态字段将设置为"预期的确认"为出站消息时将消息发送如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]要求技术确认。</span><span class="sxs-lookup"><span data-stu-id="3fef2-186">The Interchange Status field in the Interchange Status and ACK Details status report will be set to "Ack Expected" for an outbound message when the message is sent if [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] expects a technical acknowledgment.</span></span> <span data-ttu-id="3fef2-187">如果发生这种情况**预期的 TA1**属性中设置**确认**页的单向协议选项卡。当收到并验证技术确认时，状态将更改为"已接受"。</span><span class="sxs-lookup"><span data-stu-id="3fef2-187">This occurs if the **TA1 Expected** property is set in **Acknowledgements** page for the one-way agreement tab. The status will be changed to “Accepted” when the technical acknowledgment has been received and validated.</span></span> <span data-ttu-id="3fef2-188">请注意这只是个技术确认，而不进行功能确认。</span><span class="sxs-lookup"><span data-stu-id="3fef2-188">Note that this only occurs for a technical acknowledgment, not a functional acknowledgment.</span></span>  
  
- <span data-ttu-id="3fef2-189">非预期的确认</span><span class="sxs-lookup"><span data-stu-id="3fef2-189">Ack Not Expected</span></span>  
  
- <span data-ttu-id="3fef2-190">已拒绝：由于出现错误，交换无效。</span><span class="sxs-lookup"><span data-stu-id="3fef2-190">Rejected: The interchange was invalid due to errors.</span></span>  
  
## <a name="additional-reports-displayed-from-this-report"></a><span data-ttu-id="3fef2-191">此报告中显示的其他报表</span><span class="sxs-lookup"><span data-stu-id="3fef2-191">Additional Reports Displayed from This Report</span></span>  
 <span data-ttu-id="3fef2-192">可以显示以下其他状态报告事务集报告中显示的事务集详细信息。</span><span class="sxs-lookup"><span data-stu-id="3fef2-192">You can display the following additional status reports for a transaction set shown in the Transaction Set Details report.</span></span> <span data-ttu-id="3fef2-193">通过右键单击的交换或确认列出在 EDI 交换和相关 ACK 状态报告中，然后单击相应的命令访问报告：</span><span class="sxs-lookup"><span data-stu-id="3fef2-193">You access the reports by right-clicking an interchange or acknowledgment listed in the EDI Interchange and Correlated ACK Status report, and then clicking the appropriate command:</span></span>  
  
-   [<span data-ttu-id="3fef2-194">“交换状态和 ACK 详细信息”状态报告</span><span class="sxs-lookup"><span data-stu-id="3fef2-194">Interchange Status and ACK Details Status Report</span></span>](../core/interchange-status-and-ack-details-status-report.md)  
  
-   [<span data-ttu-id="3fef2-195">事务集详细信息状态报告</span><span class="sxs-lookup"><span data-stu-id="3fef2-195">Transaction Set Details Status Report</span></span>](../core/transaction-set-details-status-report.md)  
  
## <a name="next-steps"></a><span data-ttu-id="3fef2-196">后续步骤</span><span class="sxs-lookup"><span data-stu-id="3fef2-196">Next steps</span></span>
  
-   [<span data-ttu-id="3fef2-197">“交换状态和 ACK 详细信息”状态报告</span><span class="sxs-lookup"><span data-stu-id="3fef2-197">Interchange Status and ACK Details Status Report</span></span>](../core/interchange-status-and-ack-details-status-report.md)  
  
-   [<span data-ttu-id="3fef2-198">事务集详细信息状态报告</span><span class="sxs-lookup"><span data-stu-id="3fef2-198">Transaction Set Details Status Report</span></span>](../core/transaction-set-details-status-report.md)  
  
-   [<span data-ttu-id="3fef2-199">EDI 消息内容状态报告</span><span class="sxs-lookup"><span data-stu-id="3fef2-199">EDI Message Content Status Report</span></span>](../core/edi-message-content-status-report.md)  
  
