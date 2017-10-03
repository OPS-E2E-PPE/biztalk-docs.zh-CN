---
title: "EDI 交换和关联的 ACK 状态报表 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a112cc3d-d34c-4652-a8ee-3355a31d4a03
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd5f4268badf9907eb90b090abe34a8355b3ab8f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="edi-interchange-and-correlated-ack-status-report"></a><span data-ttu-id="293b6-102">EDI 交换和相关 ACK 状态报告</span><span class="sxs-lookup"><span data-stu-id="293b6-102">EDI Interchange and Correlated ACK Status Report</span></span>
<span data-ttu-id="293b6-103">此报告显示由 EDI 发送管道和接收管道处理的所有 EDI 交换，以及与这些交换相关的确认。</span><span class="sxs-lookup"><span data-stu-id="293b6-103">This report shows all EDI interchanges that are processed by the EDI send and receive pipelines, and the acknowledgment correlated to those interchanges.</span></span>  
  
## <a name="fields-in-the-status-report"></a><span data-ttu-id="293b6-104">状态报告中的字段</span><span class="sxs-lookup"><span data-stu-id="293b6-104">Fields in the Status Report</span></span>  
 <span data-ttu-id="293b6-105">EDI 交换和相关 ACK 状态报告将显示有关接收或发送交换及其相关确认的以下信息：</span><span class="sxs-lookup"><span data-stu-id="293b6-105">The EDI Interchange and Correlated ACK Status Report displays the following information for the received or sent interchanges and the acknowledgments that are correlated to them:</span></span>  
  
-   <span data-ttu-id="293b6-106">发件人方</span><span class="sxs-lookup"><span data-stu-id="293b6-106">Sender Party</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="293b6-107">发送方的确定原则如下：</span><span class="sxs-lookup"><span data-stu-id="293b6-107">The sender party will be determined as follows:</span></span>  
    >   
    >  -   <span data-ttu-id="293b6-108">如果交换中的参与方名称与在 EDI 属性中为某个参与方配置的名称相匹配，则将显示配置的名称。</span><span class="sxs-lookup"><span data-stu-id="293b6-108">If the party name in the interchange matches the name configured in the EDI Properties for a party, then the configured name is displayed.</span></span>  
    > -   <span data-ttu-id="293b6-109">如果交换中的参与方名称不与任何配置的现有参与方的 EDI 属性匹配，则将显示交换中所指定的参与方名称。</span><span class="sxs-lookup"><span data-stu-id="293b6-109">If the party name in the interchange does not match any of the configured EDI Properties for existing parties, the party name specified in the interchange is displayed.</span></span>  
  
-   <span data-ttu-id="293b6-110">接收方</span><span class="sxs-lookup"><span data-stu-id="293b6-110">Receiver Party</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="293b6-111">接收方名称的确定原则如下：</span><span class="sxs-lookup"><span data-stu-id="293b6-111">The receiver party name will be determined as follows:</span></span>  
    >   
    >  -   <span data-ttu-id="293b6-112">如果交换中的参与方名称与在 EDI 属性中为某个参与方配置的名称相匹配，则将显示配置的名称。</span><span class="sxs-lookup"><span data-stu-id="293b6-112">If the party name in the interchange matches the name configured in the EDI Properties for a party, then the configured name is displayed.</span></span>  
    > -   <span data-ttu-id="293b6-113">如果交换中的参与方名称不与任何配置的现有参与方的 EDI 属性匹配，则将显示交换中所指定的参与方名称。</span><span class="sxs-lookup"><span data-stu-id="293b6-113">If the party name in the interchange does not match any of the configured EDI Properties for existing parties, the party name specified in the interchange is displayed.</span></span>  
  
-   <span data-ttu-id="293b6-114">控件 ID</span><span class="sxs-lookup"><span data-stu-id="293b6-114">Control ID</span></span>  
  
-   <span data-ttu-id="293b6-115">方向</span><span class="sxs-lookup"><span data-stu-id="293b6-115">Direction</span></span>  
  
-   <span data-ttu-id="293b6-116">交换日期时间</span><span class="sxs-lookup"><span data-stu-id="293b6-116">Interchange Date Time</span></span>  
  
-   <span data-ttu-id="293b6-117">EDI 编码类型</span><span class="sxs-lookup"><span data-stu-id="293b6-117">EDI encoding type</span></span>  
  
-   <span data-ttu-id="293b6-118">交换状态</span><span class="sxs-lookup"><span data-stu-id="293b6-118">Interchange Status</span></span>  
  
-   <span data-ttu-id="293b6-119">组计数</span><span class="sxs-lookup"><span data-stu-id="293b6-119">Group Count</span></span>  
  
-   <span data-ttu-id="293b6-120">端口 ID</span><span class="sxs-lookup"><span data-stu-id="293b6-120">Port ID</span></span>  
  
-   <span data-ttu-id="293b6-121">发件人方别名</span><span class="sxs-lookup"><span data-stu-id="293b6-121">Sender Party Alias</span></span>  
  
-   <span data-ttu-id="293b6-122">接收方方别名</span><span class="sxs-lookup"><span data-stu-id="293b6-122">Receiver Party Alias</span></span>  
  
-   <span data-ttu-id="293b6-123">事务集相关 ID</span><span class="sxs-lookup"><span data-stu-id="293b6-123">Transaction Set Correlation ID</span></span>  
  
## <a name="fields-in-the-query-expression-for-the-status-report"></a><span data-ttu-id="293b6-124">状态报告的查询表达式中的字段</span><span class="sxs-lookup"><span data-stu-id="293b6-124">Fields in the Query Expression for the Status Report</span></span>  
 <span data-ttu-id="293b6-125">您可更改用于确定所显示数据的查询表达式中的字段来自定义 EDI 交换及相关 ACK 状态报告。</span><span class="sxs-lookup"><span data-stu-id="293b6-125">You can customize the EDI Interchange and Correlated ACK Status Report by changing the fields in the query expression that determines the data displayed.</span></span> <span data-ttu-id="293b6-126">下列字段可用：</span><span class="sxs-lookup"><span data-stu-id="293b6-126">The following fields are available:</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="293b6-127">查询表达式字段</span><span class="sxs-lookup"><span data-stu-id="293b6-127">Query Expression Field</span></span>|<span data-ttu-id="293b6-128">可能的运算符</span><span class="sxs-lookup"><span data-stu-id="293b6-128">Potential Operators</span></span>|<span data-ttu-id="293b6-129">可能的值</span><span class="sxs-lookup"><span data-stu-id="293b6-129">Potential Values</span></span>|<span data-ttu-id="293b6-130">默认情况下是否包括？</span><span class="sxs-lookup"><span data-stu-id="293b6-130">Included By Default?</span></span>|  
|<span data-ttu-id="293b6-131">搜索</span><span class="sxs-lookup"><span data-stu-id="293b6-131">Search for</span></span>|<span data-ttu-id="293b6-132">等于</span><span class="sxs-lookup"><span data-stu-id="293b6-132">Equals</span></span>|<span data-ttu-id="293b6-133">交换/ACK 状态</span><span class="sxs-lookup"><span data-stu-id="293b6-133">Interchange/ACK Status</span></span>|<span data-ttu-id="293b6-134">是（必需）</span><span class="sxs-lookup"><span data-stu-id="293b6-134">Yes (required)</span></span>|  
|<span data-ttu-id="293b6-135">状态</span><span class="sxs-lookup"><span data-stu-id="293b6-135">Status</span></span>|<span data-ttu-id="293b6-136">等于</span><span class="sxs-lookup"><span data-stu-id="293b6-136">Equals</span></span><br /><br /> <span data-ttu-id="293b6-137">不等于</span><span class="sxs-lookup"><span data-stu-id="293b6-137">Not Equals</span></span>|<span data-ttu-id="293b6-138">已接受</span><span class="sxs-lookup"><span data-stu-id="293b6-138">Accepted</span></span><br /><br /> <span data-ttu-id="293b6-139">已接受但存在错误</span><span class="sxs-lookup"><span data-stu-id="293b6-139">Accepted with Errors</span></span><br /><br /> <span data-ttu-id="293b6-140">已发送</span><span class="sxs-lookup"><span data-stu-id="293b6-140">Sent</span></span><br /><br /> <span data-ttu-id="293b6-141">全部</span><span class="sxs-lookup"><span data-stu-id="293b6-141">All</span></span><br /><br /> <span data-ttu-id="293b6-142">预期的确认</span><span class="sxs-lookup"><span data-stu-id="293b6-142">Ack Expected</span></span><br /><br /> <span data-ttu-id="293b6-143">非预期的确认</span><span class="sxs-lookup"><span data-stu-id="293b6-143">Ack Not Expected</span></span><br /><br /> <span data-ttu-id="293b6-144">已拒绝</span><span class="sxs-lookup"><span data-stu-id="293b6-144">Rejected</span></span><br /><br /> <span data-ttu-id="293b6-145">（这些值定义如下。）</span><span class="sxs-lookup"><span data-stu-id="293b6-145">(These values are defined below.)</span></span>|<span data-ttu-id="293b6-146">是</span><span class="sxs-lookup"><span data-stu-id="293b6-146">Yes</span></span>|  
|<span data-ttu-id="293b6-147">交换日期时间</span><span class="sxs-lookup"><span data-stu-id="293b6-147">Interchange Date Time</span></span>|<span data-ttu-id="293b6-148">小于或等于</span><span class="sxs-lookup"><span data-stu-id="293b6-148">Less Than or Equals</span></span><br /><br /> <span data-ttu-id="293b6-149">大于或等于</span><span class="sxs-lookup"><span data-stu-id="293b6-149">Greater Than or Equals</span></span>|<span data-ttu-id="293b6-150">特定日期时间</span><span class="sxs-lookup"><span data-stu-id="293b6-150">Specific Date Time</span></span><br /><br /> <span data-ttu-id="293b6-151">今天</span><span class="sxs-lookup"><span data-stu-id="293b6-151">Today</span></span><br /><br /> <span data-ttu-id="293b6-152">Today-1</span><span class="sxs-lookup"><span data-stu-id="293b6-152">Today - 1</span></span>|<span data-ttu-id="293b6-153">是</span><span class="sxs-lookup"><span data-stu-id="293b6-153">Yes</span></span><br /><br /> <span data-ttu-id="293b6-154">注意：可在查询表达式中多次使用。</span><span class="sxs-lookup"><span data-stu-id="293b6-154">Note: Can be included more than once in the query expression.</span></span>|  
|<span data-ttu-id="293b6-155">最大匹配数</span><span class="sxs-lookup"><span data-stu-id="293b6-155">Maximum Matches</span></span>|<span data-ttu-id="293b6-156">等于</span><span class="sxs-lookup"><span data-stu-id="293b6-156">Equals</span></span>|<span data-ttu-id="293b6-157">整数（默认值为 50）</span><span class="sxs-lookup"><span data-stu-id="293b6-157">Integer (default of 50)</span></span>|<span data-ttu-id="293b6-158">是</span><span class="sxs-lookup"><span data-stu-id="293b6-158">Yes</span></span>|  
|<span data-ttu-id="293b6-159">控件 ID</span><span class="sxs-lookup"><span data-stu-id="293b6-159">Control ID</span></span>|<span data-ttu-id="293b6-160">等于</span><span class="sxs-lookup"><span data-stu-id="293b6-160">Equals</span></span>|<span data-ttu-id="293b6-161">交换控制 ID</span><span class="sxs-lookup"><span data-stu-id="293b6-161">Interchange Control ID</span></span>|<span data-ttu-id="293b6-162">是</span><span class="sxs-lookup"><span data-stu-id="293b6-162">No</span></span>|  
|<span data-ttu-id="293b6-163">方向</span><span class="sxs-lookup"><span data-stu-id="293b6-163">Direction</span></span>|<span data-ttu-id="293b6-164">等于</span><span class="sxs-lookup"><span data-stu-id="293b6-164">Equals</span></span>|<span data-ttu-id="293b6-165">所有 （默认值）</span><span class="sxs-lookup"><span data-stu-id="293b6-165">All (default)</span></span><br /><br /> <span data-ttu-id="293b6-166">Receive</span><span class="sxs-lookup"><span data-stu-id="293b6-166">Receive</span></span><br /><br /> <span data-ttu-id="293b6-167">Send</span><span class="sxs-lookup"><span data-stu-id="293b6-167">Send</span></span>|<span data-ttu-id="293b6-168">是</span><span class="sxs-lookup"><span data-stu-id="293b6-168">No</span></span>|  
|<span data-ttu-id="293b6-169">接收方</span><span class="sxs-lookup"><span data-stu-id="293b6-169">Receiver Party</span></span>|<span data-ttu-id="293b6-170">等于</span><span class="sxs-lookup"><span data-stu-id="293b6-170">Equals</span></span>|<span data-ttu-id="293b6-171">所有 （默认值）</span><span class="sxs-lookup"><span data-stu-id="293b6-171">All (default)</span></span><br /><br /> <span data-ttu-id="293b6-172">特定参与方名称</span><span class="sxs-lookup"><span data-stu-id="293b6-172">Specific party name</span></span>|<span data-ttu-id="293b6-173">是</span><span class="sxs-lookup"><span data-stu-id="293b6-173">No</span></span>|  
|<span data-ttu-id="293b6-174">发件人方</span><span class="sxs-lookup"><span data-stu-id="293b6-174">Sender Party</span></span>|<span data-ttu-id="293b6-175">等于</span><span class="sxs-lookup"><span data-stu-id="293b6-175">Equals</span></span>|<span data-ttu-id="293b6-176">所有 （默认值）</span><span class="sxs-lookup"><span data-stu-id="293b6-176">All (default)</span></span><br /><br /> <span data-ttu-id="293b6-177">特定参与方名称</span><span class="sxs-lookup"><span data-stu-id="293b6-177">Specific party name</span></span>|<span data-ttu-id="293b6-178">是</span><span class="sxs-lookup"><span data-stu-id="293b6-178">No</span></span>|  
  
## <a name="status-definitions"></a><span data-ttu-id="293b6-179">状态定义</span><span class="sxs-lookup"><span data-stu-id="293b6-179">Status Definitions</span></span>  
 <span data-ttu-id="293b6-180">EDI 状态报告中使用的状态值具有以下定义：</span><span class="sxs-lookup"><span data-stu-id="293b6-180">The status values used in EDI status reports have the following definitions:</span></span>  
  
-   <span data-ttu-id="293b6-181">已接受：交换有效</span><span class="sxs-lookup"><span data-stu-id="293b6-181">Accepted: Valid interchange</span></span>  
  
-   <span data-ttu-id="293b6-182">已接受但存在错误：错误记录在段中</span><span class="sxs-lookup"><span data-stu-id="293b6-182">Accepted with Errors: Errors were noted in segments</span></span>  
  
-   <span data-ttu-id="293b6-183">已发送：交换已成功发送</span><span class="sxs-lookup"><span data-stu-id="293b6-183">Sent: The interchange was sent successfully</span></span>  
  
-   <span data-ttu-id="293b6-184">全部：显示针对任何其他值的消息</span><span class="sxs-lookup"><span data-stu-id="293b6-184">All: Display a message with any of the other values</span></span>  
  
-   <span data-ttu-id="293b6-185">预期的确认</span><span class="sxs-lookup"><span data-stu-id="293b6-185">Ack Expected</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="293b6-186">对于一个出站消息，当发送该消息时，如果 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 期望收到技术确认，则“交换状态和确认详细信息”状态报告中的“交换状态”字段将设置为“预期的确认”。</span><span class="sxs-lookup"><span data-stu-id="293b6-186">The Interchange Status field in the Interchange Status and ACK Details status report will be set to "Ack Expected" for an outbound message when the message is sent if [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] expects a technical acknowledgment.</span></span> <span data-ttu-id="293b6-187">如果发生这种情况**预期的 TA1**属性在中设置**确认**单向协议选项卡页。已收到并验证技术确认后，状态将更改为“已接受”。</span><span class="sxs-lookup"><span data-stu-id="293b6-187">This occurs if the **TA1 Expected** property is set in **Acknowledgements** page for the one-way agreement tab. The status will be changed to “Accepted” when the technical acknowledgment has been received and validated.</span></span> <span data-ttu-id="293b6-188">请注意，只有技术确定才会出现此情况，而功能确认则不会。</span><span class="sxs-lookup"><span data-stu-id="293b6-188">Note that this only occurs for a technical acknowledgment, not a functional acknowledgment.</span></span>  
  
-   <span data-ttu-id="293b6-189">非预期的确认</span><span class="sxs-lookup"><span data-stu-id="293b6-189">Ack Not Expected</span></span>  
  
-   <span data-ttu-id="293b6-190">已拒绝：由于出现错误，交换无效。</span><span class="sxs-lookup"><span data-stu-id="293b6-190">Rejected: The interchange was invalid due to errors.</span></span>  
  
## <a name="additional-reports-displayed-from-this-report"></a><span data-ttu-id="293b6-191">此报告中显示的其他报告</span><span class="sxs-lookup"><span data-stu-id="293b6-191">Additional Reports Displayed from This Report</span></span>  
 <span data-ttu-id="293b6-192">对于在“事务集详细信息”报告中显示的事务集，可以显示以下其他状态报告。</span><span class="sxs-lookup"><span data-stu-id="293b6-192">You can display the following additional status reports for a transaction set shown in the Transaction Set Details report.</span></span> <span data-ttu-id="293b6-193">通过右键单击“EDI 交换和相关 ACK 状态”报告中所列出的交换或确认，然后单击相应的命令，可以查看以下报告：</span><span class="sxs-lookup"><span data-stu-id="293b6-193">You access the reports by right-clicking an interchange or acknowledgment listed in the EDI Interchange and Correlated ACK Status report, and then clicking the appropriate command:</span></span>  
  
-   [<span data-ttu-id="293b6-194">交换状态和 ACK 的详细信息状态报表</span><span class="sxs-lookup"><span data-stu-id="293b6-194">Interchange Status and ACK Details Status Report</span></span>](../core/interchange-status-and-ack-details-status-report.md)  
  
-   [<span data-ttu-id="293b6-195">事务集详细信息状态报告</span><span class="sxs-lookup"><span data-stu-id="293b6-195">Transaction Set Details Status Report</span></span>](../core/transaction-set-details-status-report.md)  
  
## <a name="next-steps"></a><span data-ttu-id="293b6-196">后续步骤</span><span class="sxs-lookup"><span data-stu-id="293b6-196">Next steps</span></span>
  
-   [<span data-ttu-id="293b6-197">交换状态和 ACK 的详细信息状态报表</span><span class="sxs-lookup"><span data-stu-id="293b6-197">Interchange Status and ACK Details Status Report</span></span>](../core/interchange-status-and-ack-details-status-report.md)  
  
-   [<span data-ttu-id="293b6-198">事务集详细信息状态报告</span><span class="sxs-lookup"><span data-stu-id="293b6-198">Transaction Set Details Status Report</span></span>](../core/transaction-set-details-status-report.md)  
  
-   [<span data-ttu-id="293b6-199">EDI 消息内容状态报表</span><span class="sxs-lookup"><span data-stu-id="293b6-199">EDI Message Content Status Report</span></span>](../core/edi-message-content-status-report.md)  
  
