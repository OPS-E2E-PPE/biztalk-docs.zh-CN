---
title: 事务集详细信息状态报告 |Microsoft 文档
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
ms.openlocfilehash: b6da167ea995fa05d8e35807d8cf26f23b5444a2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279509"
---
# <a name="transaction-set-details-status-report"></a><span data-ttu-id="78d4e-102">事务集详细信息状态报告</span><span class="sxs-lookup"><span data-stu-id="78d4e-102">Transaction Set Details Status Report</span></span>
<span data-ttu-id="78d4e-103">该报告显示从“交换/ACK 状态”报告内部选择的特定 EDI 交换中的事务集的详细信息。</span><span class="sxs-lookup"><span data-stu-id="78d4e-103">This report shows the details for transaction sets in a specific EDI interchange selected from within the Interchange/ACK Status report.</span></span> <span data-ttu-id="78d4e-104">要显示此状态报表，请右键单击交换/ACK 状态报表中，查询结果窗格中列出的交换，然后单击**设置事务的详细信息**。</span><span class="sxs-lookup"><span data-stu-id="78d4e-104">To display this status report, right-click an interchange listed in the Query results pane of the Interchange/ACK Status report, and then click **Transaction Set Details**.</span></span>  
  
 <span data-ttu-id="78d4e-105">此报表才可用，仅当你选择**存储事务的一组负载，可用于报告**相关方的 EDI 属性对话框的常规页中的属性。</span><span class="sxs-lookup"><span data-stu-id="78d4e-105">This report is available only if you have selected the **Store transaction set/payload for reporting** property in the General Page of the EDI Properties dialog box for the related party.</span></span>  
  
## <a name="fields-in-the-status-report"></a><span data-ttu-id="78d4e-106">状态报告中的字段</span><span class="sxs-lookup"><span data-stu-id="78d4e-106">Fields in the Status Report</span></span>  
 <span data-ttu-id="78d4e-107">事务集详细信息状态报告显示已接收或已发送交换中的事务集的以下信息：</span><span class="sxs-lookup"><span data-stu-id="78d4e-107">The Transaction Set Details Status Report displays the following information for transaction sets in received or sent interchanges:</span></span>  
  
-   <span data-ttu-id="78d4e-108">事务集 ID</span><span class="sxs-lookup"><span data-stu-id="78d4e-108">Transaction Set ID</span></span>  
  
-   <span data-ttu-id="78d4e-109">文档类型</span><span class="sxs-lookup"><span data-stu-id="78d4e-109">Document type</span></span>  
  
-   <span data-ttu-id="78d4e-110">发件人方别名</span><span class="sxs-lookup"><span data-stu-id="78d4e-110">Sender party alias</span></span>  
  
-   <span data-ttu-id="78d4e-111">应用程序发送方</span><span class="sxs-lookup"><span data-stu-id="78d4e-111">Application Sender</span></span>  
  
-   <span data-ttu-id="78d4e-112">接收方方别名</span><span class="sxs-lookup"><span data-stu-id="78d4e-112">Receiver party alias</span></span>  
  
-   <span data-ttu-id="78d4e-113">应用程序接收方</span><span class="sxs-lookup"><span data-stu-id="78d4e-113">Application Receiver</span></span>  
  
-   <span data-ttu-id="78d4e-114">方向</span><span class="sxs-lookup"><span data-stu-id="78d4e-114">Direction</span></span>  
  
-   <span data-ttu-id="78d4e-115">交换控制编号</span><span class="sxs-lookup"><span data-stu-id="78d4e-115">Interchange Control Number</span></span>  
  
-   <span data-ttu-id="78d4e-116">组控制编号</span><span class="sxs-lookup"><span data-stu-id="78d4e-116">Group Control Number</span></span>  
  
-   <span data-ttu-id="78d4e-117">事务集控制编号</span><span class="sxs-lookup"><span data-stu-id="78d4e-117">Transaction Set Control Number</span></span>  
  
-   <span data-ttu-id="78d4e-118">事务集状态</span><span class="sxs-lookup"><span data-stu-id="78d4e-118">Transaction Set Status</span></span>  
  
-   <span data-ttu-id="78d4e-119">交换日期时间（默认情况下不显示）</span><span class="sxs-lookup"><span data-stu-id="78d4e-119">Interchange Date Time (not displayed by default)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="78d4e-120">对于收到的文档，如果在交换中指定的日期格式为 YYMMDD 且 YY 大于等于 75，则 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 会将年份显示为 19YY。</span><span class="sxs-lookup"><span data-stu-id="78d4e-120">For received documents, if the date specified in the interchange is YYMMDD format and YY is greater than or equal to 75, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will display the year as 19YY.</span></span> <span data-ttu-id="78d4e-121">如果日期中的 YY 小于 75，将显示为 20YY。</span><span class="sxs-lookup"><span data-stu-id="78d4e-121">If the date is less than 75, it will be displayed as 20YY.</span></span>  
    >   
    >  <span data-ttu-id="78d4e-122">例如，如果你在 ISA09 中收到包含值 991113 的交换，则报告中将列出交换日期时间为 11/13/1999。</span><span class="sxs-lookup"><span data-stu-id="78d4e-122">For example, if you receive an interchange that contains the value 991113 in ISA09, the Interchange Date Time will be listed in the report as 11/13/1999.</span></span>  
  
-   <span data-ttu-id="78d4e-123">处理日期/时间（默认情况下不显示）</span><span class="sxs-lookup"><span data-stu-id="78d4e-123">Processing Date/Time (not displayed by default)</span></span>  
  
-   <span data-ttu-id="78d4e-124">组日期/时间（默认情况下不显示）</span><span class="sxs-lookup"><span data-stu-id="78d4e-124">Group Date/Time (not displayed by default)</span></span>  
  
## <a name="fields-in-the-query-expression-for-the-status-report"></a><span data-ttu-id="78d4e-125">状态报告的查询表达式中的字段</span><span class="sxs-lookup"><span data-stu-id="78d4e-125">Fields in the Query Expression for the Status Report</span></span>  
 <span data-ttu-id="78d4e-126">您可更改用于确定所显示数据的查询表达式中的字段来自定义 EDI 交换及相关 ACK 状态报告。</span><span class="sxs-lookup"><span data-stu-id="78d4e-126">You can customize the EDI Interchange and Correlated ACK Status Report by changing the fields in the query expression that determines the data displayed.</span></span> <span data-ttu-id="78d4e-127">下列字段可用：</span><span class="sxs-lookup"><span data-stu-id="78d4e-127">The following fields are available:</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="78d4e-128">查询表达式字段</span><span class="sxs-lookup"><span data-stu-id="78d4e-128">Query Expression Field</span></span>|<span data-ttu-id="78d4e-129">可能的运算符</span><span class="sxs-lookup"><span data-stu-id="78d4e-129">Potential Operators</span></span>|<span data-ttu-id="78d4e-130">可能的值</span><span class="sxs-lookup"><span data-stu-id="78d4e-130">Potential Values</span></span>|<span data-ttu-id="78d4e-131">默认情况下是否包括？</span><span class="sxs-lookup"><span data-stu-id="78d4e-131">Included By Default?</span></span>|  
|<span data-ttu-id="78d4e-132">搜索</span><span class="sxs-lookup"><span data-stu-id="78d4e-132">Search for</span></span>|<span data-ttu-id="78d4e-133">等于</span><span class="sxs-lookup"><span data-stu-id="78d4e-133">Equals</span></span>|<span data-ttu-id="78d4e-134">事务集详细信息</span><span class="sxs-lookup"><span data-stu-id="78d4e-134">Transaction Set Details</span></span>|<span data-ttu-id="78d4e-135">是（必需）</span><span class="sxs-lookup"><span data-stu-id="78d4e-135">Yes (required)</span></span>|  
|<span data-ttu-id="78d4e-136">交换日期时间</span><span class="sxs-lookup"><span data-stu-id="78d4e-136">Interchange Date Time</span></span>|<span data-ttu-id="78d4e-137">小于或等于</span><span class="sxs-lookup"><span data-stu-id="78d4e-137">Less Than or Equals</span></span><br /><br /> <span data-ttu-id="78d4e-138">大于或等于</span><span class="sxs-lookup"><span data-stu-id="78d4e-138">Greater Than or Equals</span></span>|<span data-ttu-id="78d4e-139">特定日期时间</span><span class="sxs-lookup"><span data-stu-id="78d4e-139">Specific Date Time</span></span><br /><br /> <span data-ttu-id="78d4e-140">今天</span><span class="sxs-lookup"><span data-stu-id="78d4e-140">Today</span></span><br /><br /> <span data-ttu-id="78d4e-141">Today-1</span><span class="sxs-lookup"><span data-stu-id="78d4e-141">Today - 1</span></span>|<span data-ttu-id="78d4e-142">是</span><span class="sxs-lookup"><span data-stu-id="78d4e-142">Yes</span></span><br /><br /> <span data-ttu-id="78d4e-143">注意：可在查询表达式中多次使用。</span><span class="sxs-lookup"><span data-stu-id="78d4e-143">Note: Can be included more than once in the query expression.</span></span>|  
|<span data-ttu-id="78d4e-144">接收方参与方名称</span><span class="sxs-lookup"><span data-stu-id="78d4e-144">Receiver Party Name</span></span>|<span data-ttu-id="78d4e-145">等于</span><span class="sxs-lookup"><span data-stu-id="78d4e-145">Equals</span></span>|<span data-ttu-id="78d4e-146">所有 （默认值）</span><span class="sxs-lookup"><span data-stu-id="78d4e-146">All (default)</span></span><br /><br /> <span data-ttu-id="78d4e-147">特定参与方名称</span><span class="sxs-lookup"><span data-stu-id="78d4e-147">Specific party name</span></span>|<span data-ttu-id="78d4e-148">是</span><span class="sxs-lookup"><span data-stu-id="78d4e-148">Yes</span></span>|  
|<span data-ttu-id="78d4e-149">发送方名称</span><span class="sxs-lookup"><span data-stu-id="78d4e-149">Sender Party Name</span></span>|<span data-ttu-id="78d4e-150">等于</span><span class="sxs-lookup"><span data-stu-id="78d4e-150">Equals</span></span>|<span data-ttu-id="78d4e-151">所有 （默认值）</span><span class="sxs-lookup"><span data-stu-id="78d4e-151">All (default)</span></span><br /><br /> <span data-ttu-id="78d4e-152">特定参与方名称</span><span class="sxs-lookup"><span data-stu-id="78d4e-152">Specific party name</span></span>|<span data-ttu-id="78d4e-153">是</span><span class="sxs-lookup"><span data-stu-id="78d4e-153">Yes</span></span>|  
|<span data-ttu-id="78d4e-154">方向</span><span class="sxs-lookup"><span data-stu-id="78d4e-154">Direction</span></span>|<span data-ttu-id="78d4e-155">等于</span><span class="sxs-lookup"><span data-stu-id="78d4e-155">Equals</span></span>|<span data-ttu-id="78d4e-156">所有 （默认值）</span><span class="sxs-lookup"><span data-stu-id="78d4e-156">All (default)</span></span><br /><br /> <span data-ttu-id="78d4e-157">Receive</span><span class="sxs-lookup"><span data-stu-id="78d4e-157">Receive</span></span><br /><br /> <span data-ttu-id="78d4e-158">Send</span><span class="sxs-lookup"><span data-stu-id="78d4e-158">Send</span></span>|<span data-ttu-id="78d4e-159">是</span><span class="sxs-lookup"><span data-stu-id="78d4e-159">Yes</span></span>|  
|<span data-ttu-id="78d4e-160">控件 ID</span><span class="sxs-lookup"><span data-stu-id="78d4e-160">Control ID</span></span>|<span data-ttu-id="78d4e-161">等于</span><span class="sxs-lookup"><span data-stu-id="78d4e-161">Equals</span></span>|<span data-ttu-id="78d4e-162">交换控制 ID</span><span class="sxs-lookup"><span data-stu-id="78d4e-162">Interchange Control ID</span></span>|<span data-ttu-id="78d4e-163">是</span><span class="sxs-lookup"><span data-stu-id="78d4e-163">Yes</span></span>|  
|<span data-ttu-id="78d4e-164">事务集相关 ID</span><span class="sxs-lookup"><span data-stu-id="78d4e-164">Transaction Set Correlation Id</span></span>|<span data-ttu-id="78d4e-165">等于</span><span class="sxs-lookup"><span data-stu-id="78d4e-165">Equals</span></span>|<span data-ttu-id="78d4e-166">相关性 ID</span><span class="sxs-lookup"><span data-stu-id="78d4e-166">Correlation Id</span></span>|<span data-ttu-id="78d4e-167">是</span><span class="sxs-lookup"><span data-stu-id="78d4e-167">Yes</span></span>|  
|<span data-ttu-id="78d4e-168">最大匹配数</span><span class="sxs-lookup"><span data-stu-id="78d4e-168">Maximum Matches</span></span>|<span data-ttu-id="78d4e-169">等于</span><span class="sxs-lookup"><span data-stu-id="78d4e-169">Equals</span></span>|<span data-ttu-id="78d4e-170">整数（默认值为 50）</span><span class="sxs-lookup"><span data-stu-id="78d4e-170">Integer (default of 50)</span></span>|<span data-ttu-id="78d4e-171">是</span><span class="sxs-lookup"><span data-stu-id="78d4e-171">Yes</span></span>|  
|<span data-ttu-id="78d4e-172">状态</span><span class="sxs-lookup"><span data-stu-id="78d4e-172">Status</span></span>|<span data-ttu-id="78d4e-173">等于</span><span class="sxs-lookup"><span data-stu-id="78d4e-173">Equals</span></span><br /><br /> <span data-ttu-id="78d4e-174">不等于</span><span class="sxs-lookup"><span data-stu-id="78d4e-174">Not Equals</span></span>|<span data-ttu-id="78d4e-175">已接受</span><span class="sxs-lookup"><span data-stu-id="78d4e-175">Accepted</span></span><br /><br /> <span data-ttu-id="78d4e-176">已接受但存在错误</span><span class="sxs-lookup"><span data-stu-id="78d4e-176">Accepted with Errors</span></span><br /><br /> <span data-ttu-id="78d4e-177">已发送</span><span class="sxs-lookup"><span data-stu-id="78d4e-177">Sent</span></span><br /><br /> <span data-ttu-id="78d4e-178">全部</span><span class="sxs-lookup"><span data-stu-id="78d4e-178">All</span></span><br /><br /> <span data-ttu-id="78d4e-179">预期的确认</span><span class="sxs-lookup"><span data-stu-id="78d4e-179">Ack Expected</span></span><br /><br /> <span data-ttu-id="78d4e-180">非预期的确认</span><span class="sxs-lookup"><span data-stu-id="78d4e-180">Ack Not Expected</span></span><br /><br /> <span data-ttu-id="78d4e-181">已拒绝</span><span class="sxs-lookup"><span data-stu-id="78d4e-181">Rejected</span></span>|<span data-ttu-id="78d4e-182">是</span><span class="sxs-lookup"><span data-stu-id="78d4e-182">No</span></span>|  
|<span data-ttu-id="78d4e-183">事务集 ID</span><span class="sxs-lookup"><span data-stu-id="78d4e-183">Transaction Set Id</span></span>|<span data-ttu-id="78d4e-184">等于</span><span class="sxs-lookup"><span data-stu-id="78d4e-184">Equals</span></span>|<span data-ttu-id="78d4e-185">事务集 ID</span><span class="sxs-lookup"><span data-stu-id="78d4e-185">Transaction Set Id</span></span>|<span data-ttu-id="78d4e-186">是</span><span class="sxs-lookup"><span data-stu-id="78d4e-186">No</span></span>|  
  
## <a name="additional-reports-displayed-from-this-report"></a><span data-ttu-id="78d4e-187">此报告中显示的其他报告</span><span class="sxs-lookup"><span data-stu-id="78d4e-187">Additional Reports Displayed from This Report</span></span>  
 <span data-ttu-id="78d4e-188">对于在“事务集详细信息”报告中显示的事务集，可以显示以下其他状态报告：</span><span class="sxs-lookup"><span data-stu-id="78d4e-188">You can display the following additional status reports for a transaction set shown in the Transaction Set Details report:</span></span>  
  
-   <span data-ttu-id="78d4e-189">消息内容状态报告。</span><span class="sxs-lookup"><span data-stu-id="78d4e-189">Message Content status report.</span></span> <span data-ttu-id="78d4e-190">右键单击详细信息报告中的事务集，再单击“查看事务集内容”可访问此报告。</span><span class="sxs-lookup"><span data-stu-id="78d4e-190">You access this report by right-clicking a transaction set in the details reports, and then clicking View Transaction Set Content.</span></span> <span data-ttu-id="78d4e-191">有关详细信息，请参阅[EDI 消息内容状态报告](../core/edi-message-content-status-report.md)。</span><span class="sxs-lookup"><span data-stu-id="78d4e-191">For more information, see [EDI Message Content Status Report](../core/edi-message-content-status-report.md).</span></span>  
  
-   <span data-ttu-id="78d4e-192">交换/ACK 状态报告</span><span class="sxs-lookup"><span data-stu-id="78d4e-192">Interchange/ACK Status report.</span></span> <span data-ttu-id="78d4e-193">此报表使用相同的用户界面[EDI 交换和关联 ACK 状态报表](../core/edi-interchange-and-correlated-ack-status-report.md)显示为多个的交换。</span><span class="sxs-lookup"><span data-stu-id="78d4e-193">This report uses the same user interface as the [EDI Interchange and Correlated ACK Status Report](../core/edi-interchange-and-correlated-ack-status-report.md) that is displayed for multiple interchanges.</span></span> <span data-ttu-id="78d4e-194">区别在于此报告数据仅适用于包含此事务集的交换。</span><span class="sxs-lookup"><span data-stu-id="78d4e-194">The difference is that this report data for only the interchange that contains this transaction set.</span></span>  
  
