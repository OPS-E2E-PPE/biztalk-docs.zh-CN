---
title: 事务集详细信息状态报告 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d81367c7-c74e-42cb-b856-748962b727ec
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf94c5d39bcf304bfb2942d957f1c30d2e365571
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279735"
---
# <a name="transaction-set-details-status-report"></a><span data-ttu-id="9417c-102">事务集详细信息状态报告</span><span class="sxs-lookup"><span data-stu-id="9417c-102">Transaction Set Details Status Report</span></span>
<span data-ttu-id="9417c-103">此报表显示在交换 /ACK 状态报告中从选择的特定 EDI 交换中事务集的详细信息。</span><span class="sxs-lookup"><span data-stu-id="9417c-103">This report shows the details for transaction sets in a specific EDI interchange selected from within the Interchange/ACK Status report.</span></span> <span data-ttu-id="9417c-104">若要显示此状态报告中，右键单击交换 /ACK 状态报表中，在查询结果窗格中列出的交换，然后依次**事务集详细信息**。</span><span class="sxs-lookup"><span data-stu-id="9417c-104">To display this status report, right-click an interchange listed in the Query results pane of the Interchange/ACK Status report, and then click **Transaction Set Details**.</span></span>  
  
 <span data-ttu-id="9417c-105">此报表才可用，仅当你选择**存储事务集/负载以用于报告**相关参与方 EDI 属性对话框的常规页中的属性。</span><span class="sxs-lookup"><span data-stu-id="9417c-105">This report is available only if you have selected the **Store transaction set/payload for reporting** property in the General Page of the EDI Properties dialog box for the related party.</span></span>  
  
## <a name="fields-in-the-status-report"></a><span data-ttu-id="9417c-106">在状态报告中的字段</span><span class="sxs-lookup"><span data-stu-id="9417c-106">Fields in the Status Report</span></span>  
 <span data-ttu-id="9417c-107">事务的以下信息中设置该事务集详细信息状态报告显示已接收或发送的交换：</span><span class="sxs-lookup"><span data-stu-id="9417c-107">The Transaction Set Details Status Report displays the following information for transaction sets in received or sent interchanges:</span></span>  
  
- <span data-ttu-id="9417c-108">事务集 ID</span><span class="sxs-lookup"><span data-stu-id="9417c-108">Transaction Set ID</span></span>  
  
- <span data-ttu-id="9417c-109">文档类型</span><span class="sxs-lookup"><span data-stu-id="9417c-109">Document type</span></span>  
  
- <span data-ttu-id="9417c-110">发送方别名</span><span class="sxs-lookup"><span data-stu-id="9417c-110">Sender party alias</span></span>  
  
- <span data-ttu-id="9417c-111">应用程序发送方</span><span class="sxs-lookup"><span data-stu-id="9417c-111">Application Sender</span></span>  
  
- <span data-ttu-id="9417c-112">接收方别名</span><span class="sxs-lookup"><span data-stu-id="9417c-112">Receiver party alias</span></span>  
  
- <span data-ttu-id="9417c-113">应用程序接收方</span><span class="sxs-lookup"><span data-stu-id="9417c-113">Application Receiver</span></span>  
  
- <span data-ttu-id="9417c-114">Direction</span><span class="sxs-lookup"><span data-stu-id="9417c-114">Direction</span></span>  
  
- <span data-ttu-id="9417c-115">交换控制编号</span><span class="sxs-lookup"><span data-stu-id="9417c-115">Interchange Control Number</span></span>  
  
- <span data-ttu-id="9417c-116">组控制编号</span><span class="sxs-lookup"><span data-stu-id="9417c-116">Group Control Number</span></span>  
  
- <span data-ttu-id="9417c-117">事务集控制编号</span><span class="sxs-lookup"><span data-stu-id="9417c-117">Transaction Set Control Number</span></span>  
  
- <span data-ttu-id="9417c-118">事务集状态</span><span class="sxs-lookup"><span data-stu-id="9417c-118">Transaction Set Status</span></span>  
  
- <span data-ttu-id="9417c-119">交换日期时间 （默认情况下不显示）</span><span class="sxs-lookup"><span data-stu-id="9417c-119">Interchange Date Time (not displayed by default)</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="9417c-120">对于收到的文档，如果交换中指定的日期格式为 YYMMDD 且 YY 大于或等于 75，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]会将年份显示为 19YY。</span><span class="sxs-lookup"><span data-stu-id="9417c-120">For received documents, if the date specified in the interchange is YYMMDD format and YY is greater than or equal to 75, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will display the year as 19YY.</span></span> <span data-ttu-id="9417c-121">如果日期是小于 75，将显示为 20YY。</span><span class="sxs-lookup"><span data-stu-id="9417c-121">If the date is less than 75, it will be displayed as 20YY.</span></span>  
  > 
  >  <span data-ttu-id="9417c-122">例如，如果收到包含在 ISA09 中的值 991113 的交换，交换日期时间将会报告中列出为 1999 年 11/13。</span><span class="sxs-lookup"><span data-stu-id="9417c-122">For example, if you receive an interchange that contains the value 991113 in ISA09, the Interchange Date Time will be listed in the report as 11/13/1999.</span></span>  
  
- <span data-ttu-id="9417c-123">处理日期/时间 （默认情况下不显示）</span><span class="sxs-lookup"><span data-stu-id="9417c-123">Processing Date/Time (not displayed by default)</span></span>  
  
- <span data-ttu-id="9417c-124">组日期/时间 （默认情况下不显示）</span><span class="sxs-lookup"><span data-stu-id="9417c-124">Group Date/Time (not displayed by default)</span></span>  
  
## <a name="fields-in-the-query-expression-for-the-status-report"></a><span data-ttu-id="9417c-125">在状态报告的查询表达式中的字段</span><span class="sxs-lookup"><span data-stu-id="9417c-125">Fields in the Query Expression for the Status Report</span></span>  
 <span data-ttu-id="9417c-126">可以通过更改用于确定所显示数据的查询表达式中的字段来自定义 EDI 交换和相关 ACK 状态报告。</span><span class="sxs-lookup"><span data-stu-id="9417c-126">You can customize the EDI Interchange and Correlated ACK Status Report by changing the fields in the query expression that determines the data displayed.</span></span> <span data-ttu-id="9417c-127">可以使用下列域：</span><span class="sxs-lookup"><span data-stu-id="9417c-127">The following fields are available:</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="9417c-128">查询表达式字段</span><span class="sxs-lookup"><span data-stu-id="9417c-128">Query Expression Field</span></span>|<span data-ttu-id="9417c-129">可能的运算符</span><span class="sxs-lookup"><span data-stu-id="9417c-129">Potential Operators</span></span>|<span data-ttu-id="9417c-130">可能的值</span><span class="sxs-lookup"><span data-stu-id="9417c-130">Potential Values</span></span>|<span data-ttu-id="9417c-131">默认情况下包含？</span><span class="sxs-lookup"><span data-stu-id="9417c-131">Included By Default?</span></span>|  
|<span data-ttu-id="9417c-132">搜索</span><span class="sxs-lookup"><span data-stu-id="9417c-132">Search for</span></span>|<span data-ttu-id="9417c-133">等于</span><span class="sxs-lookup"><span data-stu-id="9417c-133">Equals</span></span>|<span data-ttu-id="9417c-134">事务集详细信息</span><span class="sxs-lookup"><span data-stu-id="9417c-134">Transaction Set Details</span></span>|<span data-ttu-id="9417c-135">是（必需）</span><span class="sxs-lookup"><span data-stu-id="9417c-135">Yes (required)</span></span>|  
|<span data-ttu-id="9417c-136">交换日期时间</span><span class="sxs-lookup"><span data-stu-id="9417c-136">Interchange Date Time</span></span>|<span data-ttu-id="9417c-137">小于或等于</span><span class="sxs-lookup"><span data-stu-id="9417c-137">Less Than or Equals</span></span><br /><br /> <span data-ttu-id="9417c-138">大于或等于</span><span class="sxs-lookup"><span data-stu-id="9417c-138">Greater Than or Equals</span></span>|<span data-ttu-id="9417c-139">特定日期时间</span><span class="sxs-lookup"><span data-stu-id="9417c-139">Specific Date Time</span></span><br /><br /> <span data-ttu-id="9417c-140">今天</span><span class="sxs-lookup"><span data-stu-id="9417c-140">Today</span></span><br /><br /> <span data-ttu-id="9417c-141">Today-1</span><span class="sxs-lookup"><span data-stu-id="9417c-141">Today - 1</span></span>|<span data-ttu-id="9417c-142">是</span><span class="sxs-lookup"><span data-stu-id="9417c-142">Yes</span></span><br /><br /> <span data-ttu-id="9417c-143">注意：可以包含多个查询表达式中。</span><span class="sxs-lookup"><span data-stu-id="9417c-143">Note: Can be included more than once in the query expression.</span></span>|  
|<span data-ttu-id="9417c-144">接收方的参与方名称</span><span class="sxs-lookup"><span data-stu-id="9417c-144">Receiver Party Name</span></span>|<span data-ttu-id="9417c-145">等于</span><span class="sxs-lookup"><span data-stu-id="9417c-145">Equals</span></span>|<span data-ttu-id="9417c-146">所有 （默认值）</span><span class="sxs-lookup"><span data-stu-id="9417c-146">All (default)</span></span><br /><br /> <span data-ttu-id="9417c-147">特定参与方名称</span><span class="sxs-lookup"><span data-stu-id="9417c-147">Specific party name</span></span>|<span data-ttu-id="9417c-148">是</span><span class="sxs-lookup"><span data-stu-id="9417c-148">Yes</span></span>|  
|<span data-ttu-id="9417c-149">发送方的参与方名称</span><span class="sxs-lookup"><span data-stu-id="9417c-149">Sender Party Name</span></span>|<span data-ttu-id="9417c-150">等于</span><span class="sxs-lookup"><span data-stu-id="9417c-150">Equals</span></span>|<span data-ttu-id="9417c-151">所有 （默认值）</span><span class="sxs-lookup"><span data-stu-id="9417c-151">All (default)</span></span><br /><br /> <span data-ttu-id="9417c-152">特定参与方名称</span><span class="sxs-lookup"><span data-stu-id="9417c-152">Specific party name</span></span>|<span data-ttu-id="9417c-153">是</span><span class="sxs-lookup"><span data-stu-id="9417c-153">Yes</span></span>|  
|<span data-ttu-id="9417c-154">Direction</span><span class="sxs-lookup"><span data-stu-id="9417c-154">Direction</span></span>|<span data-ttu-id="9417c-155">等于</span><span class="sxs-lookup"><span data-stu-id="9417c-155">Equals</span></span>|<span data-ttu-id="9417c-156">所有 （默认值）</span><span class="sxs-lookup"><span data-stu-id="9417c-156">All (default)</span></span><br /><br /> <span data-ttu-id="9417c-157">Receive</span><span class="sxs-lookup"><span data-stu-id="9417c-157">Receive</span></span><br /><br /> <span data-ttu-id="9417c-158">Send</span><span class="sxs-lookup"><span data-stu-id="9417c-158">Send</span></span>|<span data-ttu-id="9417c-159">是</span><span class="sxs-lookup"><span data-stu-id="9417c-159">Yes</span></span>|  
|<span data-ttu-id="9417c-160">控件 ID</span><span class="sxs-lookup"><span data-stu-id="9417c-160">Control ID</span></span>|<span data-ttu-id="9417c-161">等于</span><span class="sxs-lookup"><span data-stu-id="9417c-161">Equals</span></span>|<span data-ttu-id="9417c-162">交换控制 ID</span><span class="sxs-lookup"><span data-stu-id="9417c-162">Interchange Control ID</span></span>|<span data-ttu-id="9417c-163">是</span><span class="sxs-lookup"><span data-stu-id="9417c-163">Yes</span></span>|  
|<span data-ttu-id="9417c-164">事务集相关 Id</span><span class="sxs-lookup"><span data-stu-id="9417c-164">Transaction Set Correlation Id</span></span>|<span data-ttu-id="9417c-165">等于</span><span class="sxs-lookup"><span data-stu-id="9417c-165">Equals</span></span>|<span data-ttu-id="9417c-166">相关 Id</span><span class="sxs-lookup"><span data-stu-id="9417c-166">Correlation Id</span></span>|<span data-ttu-id="9417c-167">是</span><span class="sxs-lookup"><span data-stu-id="9417c-167">Yes</span></span>|  
|<span data-ttu-id="9417c-168">最大匹配数</span><span class="sxs-lookup"><span data-stu-id="9417c-168">Maximum Matches</span></span>|<span data-ttu-id="9417c-169">等于</span><span class="sxs-lookup"><span data-stu-id="9417c-169">Equals</span></span>|<span data-ttu-id="9417c-170">整数 （默认值为 50）</span><span class="sxs-lookup"><span data-stu-id="9417c-170">Integer (default of 50)</span></span>|<span data-ttu-id="9417c-171">是</span><span class="sxs-lookup"><span data-stu-id="9417c-171">Yes</span></span>|  
|<span data-ttu-id="9417c-172">“登录属性”</span><span class="sxs-lookup"><span data-stu-id="9417c-172">Status</span></span>|<span data-ttu-id="9417c-173">等于</span><span class="sxs-lookup"><span data-stu-id="9417c-173">Equals</span></span><br /><br /> <span data-ttu-id="9417c-174">不等于</span><span class="sxs-lookup"><span data-stu-id="9417c-174">Not Equals</span></span>|<span data-ttu-id="9417c-175">接受</span><span class="sxs-lookup"><span data-stu-id="9417c-175">Accepted</span></span><br /><br /> <span data-ttu-id="9417c-176">已接受但有错误</span><span class="sxs-lookup"><span data-stu-id="9417c-176">Accepted with Errors</span></span><br /><br /> <span data-ttu-id="9417c-177">发送</span><span class="sxs-lookup"><span data-stu-id="9417c-177">Sent</span></span><br /><br /> <span data-ttu-id="9417c-178">All</span><span class="sxs-lookup"><span data-stu-id="9417c-178">All</span></span><br /><br /> <span data-ttu-id="9417c-179">预期的确认</span><span class="sxs-lookup"><span data-stu-id="9417c-179">Ack Expected</span></span><br /><br /> <span data-ttu-id="9417c-180">非预期的确认</span><span class="sxs-lookup"><span data-stu-id="9417c-180">Ack Not Expected</span></span><br /><br /> <span data-ttu-id="9417c-181">已拒绝</span><span class="sxs-lookup"><span data-stu-id="9417c-181">Rejected</span></span>|<span data-ttu-id="9417c-182">否</span><span class="sxs-lookup"><span data-stu-id="9417c-182">No</span></span>|  
|<span data-ttu-id="9417c-183">事务集 Id</span><span class="sxs-lookup"><span data-stu-id="9417c-183">Transaction Set Id</span></span>|<span data-ttu-id="9417c-184">等于</span><span class="sxs-lookup"><span data-stu-id="9417c-184">Equals</span></span>|<span data-ttu-id="9417c-185">事务集 Id</span><span class="sxs-lookup"><span data-stu-id="9417c-185">Transaction Set Id</span></span>|<span data-ttu-id="9417c-186">否</span><span class="sxs-lookup"><span data-stu-id="9417c-186">No</span></span>|  
  
## <a name="additional-reports-displayed-from-this-report"></a><span data-ttu-id="9417c-187">此报告中显示的其他报表</span><span class="sxs-lookup"><span data-stu-id="9417c-187">Additional Reports Displayed from This Report</span></span>  
 <span data-ttu-id="9417c-188">可以显示以下其他状态报告事务集报告中显示的事务集详细信息：</span><span class="sxs-lookup"><span data-stu-id="9417c-188">You can display the following additional status reports for a transaction set shown in the Transaction Set Details report:</span></span>  
  
-   <span data-ttu-id="9417c-189">消息内容状态报告。</span><span class="sxs-lookup"><span data-stu-id="9417c-189">Message Content status report.</span></span> <span data-ttu-id="9417c-190">通过右键单击事务集详细信息报告中，然后单击查看事务集内容，可以访问此报表。</span><span class="sxs-lookup"><span data-stu-id="9417c-190">You access this report by right-clicking a transaction set in the details reports, and then clicking View Transaction Set Content.</span></span> <span data-ttu-id="9417c-191">有关详细信息，请参阅[EDI 消息内容状态报告](../core/edi-message-content-status-report.md)。</span><span class="sxs-lookup"><span data-stu-id="9417c-191">For more information, see [EDI Message Content Status Report](../core/edi-message-content-status-report.md).</span></span>  
  
-   <span data-ttu-id="9417c-192">交换 /ACK 状态报告。</span><span class="sxs-lookup"><span data-stu-id="9417c-192">Interchange/ACK Status report.</span></span> <span data-ttu-id="9417c-193">此报表使用相同的用户界面[EDI 交换和相关 ACK 状态报告](../core/edi-interchange-and-correlated-ack-status-report.md)显示多个交换。</span><span class="sxs-lookup"><span data-stu-id="9417c-193">This report uses the same user interface as the [EDI Interchange and Correlated ACK Status Report](../core/edi-interchange-and-correlated-ack-status-report.md) that is displayed for multiple interchanges.</span></span> <span data-ttu-id="9417c-194">不同之处在于此报表数据的交换，其中包含此事务设置。</span><span class="sxs-lookup"><span data-stu-id="9417c-194">The difference is that this report data for only the interchange that contains this transaction set.</span></span>  
  
