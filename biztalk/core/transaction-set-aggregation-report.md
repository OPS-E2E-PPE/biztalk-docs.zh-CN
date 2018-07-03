---
title: 事务集聚合报告 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a6e1417e-e0c6-4d30-aab5-d9bfe14cd4b8
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c95dcb1bc0ff0038b431505cbcccf004d772921
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015070"
---
# <a name="transaction-set-aggregation-report"></a><span data-ttu-id="81504-102">事务集聚合报告</span><span class="sxs-lookup"><span data-stu-id="81504-102">Transaction Set Aggregation Report</span></span>
<span data-ttu-id="81504-103">此报告提供了单个记录，用于说明共享同一事务集 ID、EDI 编码类型、发送方、接收方和方向的 EDI 事务集的数量。</span><span class="sxs-lookup"><span data-stu-id="81504-103">This report provides a single record that shows the number of EDI transaction sets that share the same Transaction Set ID, EDI encoding type, sender party, receiver party, and direction.</span></span> <span data-ttu-id="81504-104">此报告不提供有关单个事务集的详细信息。</span><span class="sxs-lookup"><span data-stu-id="81504-104">This report does not provide details about the individual transaction sets.</span></span>  
  
 <span data-ttu-id="81504-105">通过单击 BizTalk Server 管理控制台中“组中心”页底部的“事务集聚合报告”链接，可显示此状态报告。</span><span class="sxs-lookup"><span data-stu-id="81504-105">This status report is displayed by clicking the Transaction Set Aggregation Report link at the bottom of the Group Hub page in the BizTalk Server Administration Console.</span></span>  
  
## <a name="fields-in-the-status-report"></a><span data-ttu-id="81504-106">状态报告中的字段</span><span class="sxs-lookup"><span data-stu-id="81504-106">Fields in the Status Report</span></span>  
 <span data-ttu-id="81504-107">事务集聚合报告显示了下列与已接收或已发送交换有关的信息：</span><span class="sxs-lookup"><span data-stu-id="81504-107">The Transaction Set Aggregation Report displays the following information for the received or sent interchanges:</span></span>  
  
- <span data-ttu-id="81504-108">共享同一事务集 ID、EDI 编码类型、发送方、接收方和方向的事务集的计数</span><span class="sxs-lookup"><span data-stu-id="81504-108">A count of how many transaction sets share the same Transaction Set ID, EDI encoding type, sender party, receiver party, and direction</span></span>  
  
- <span data-ttu-id="81504-109">每个事务集记录中的发件人参与方</span><span class="sxs-lookup"><span data-stu-id="81504-109">The Sender Party for each transaction set in the record</span></span>  
  
- <span data-ttu-id="81504-110">每个事务集记录中接收方</span><span class="sxs-lookup"><span data-stu-id="81504-110">The Receiver Party for each transaction set in the record</span></span>  
  
- <span data-ttu-id="81504-111">记录中每个事务集的方向（接收或发送）</span><span class="sxs-lookup"><span data-stu-id="81504-111">The Direction (receive or send) of each transaction set in the record</span></span>  
  
- <span data-ttu-id="81504-112">在时间范围内发送或接收最早事务集的日期和时间（最早开始日期/时间）</span><span class="sxs-lookup"><span data-stu-id="81504-112">The date and time at which the earliest transaction set in the time range was sent or received (Earliest Started Date/Time)</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="81504-113">对于收到的文档，如果在交换中指定的日期格式为 YYMMDD 且 YY 大于等于 75，则 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 会将年份显示为 19YY。</span><span class="sxs-lookup"><span data-stu-id="81504-113">For received documents, if the date specified in the interchange is YYMMDD format and YY is greater than or equal to 75, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will display the year as 19YY.</span></span> <span data-ttu-id="81504-114">如果日期中的 YY 小于 75，将显示为 20YY。</span><span class="sxs-lookup"><span data-stu-id="81504-114">If the date is less than 75, it will be displayed as 20YY.</span></span>  
  > 
  >  <span data-ttu-id="81504-115">例如，如果你在 ISA09 中收到包含值 991113 的交换，则报告中将列出最早开始日期/时间为 11/13/1999。</span><span class="sxs-lookup"><span data-stu-id="81504-115">For example, if you receive an interchange that contains the value 991113 in ISA09, the Earliest Started Date/Time will be listed in the report as 11/13/1999.</span></span>  
  
- <span data-ttu-id="81504-116">在时间范围内发送或接收最晚事务集的日期和时间（最晚结束日期/时间）</span><span class="sxs-lookup"><span data-stu-id="81504-116">The date and time at which the latest transaction set in the time range was sent or received (Latest Ended Date/Time)</span></span>  
  
## <a name="fields-in-the-query-expression-for-the-status-report"></a><span data-ttu-id="81504-117">状态报告的查询表达式中的字段</span><span class="sxs-lookup"><span data-stu-id="81504-117">Fields in the Query Expression for the Status Report</span></span>  
 <span data-ttu-id="81504-118">您可以通过更改用于确定所显示数据的查询表达式中的字段来自定义交换聚合报告。</span><span class="sxs-lookup"><span data-stu-id="81504-118">You can customize the Interchange Aggregation Report by changing the fields in the query expression that determines the data displayed.</span></span> <span data-ttu-id="81504-119">下列字段可用：</span><span class="sxs-lookup"><span data-stu-id="81504-119">The following fields are available:</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="81504-120">查询表达式字段</span><span class="sxs-lookup"><span data-stu-id="81504-120">Query Expression Field</span></span>|<span data-ttu-id="81504-121">可能的运算符</span><span class="sxs-lookup"><span data-stu-id="81504-121">Potential Operators</span></span>|<span data-ttu-id="81504-122">可能的值</span><span class="sxs-lookup"><span data-stu-id="81504-122">Potential Values</span></span>|<span data-ttu-id="81504-123">默认情况下是否包括？</span><span class="sxs-lookup"><span data-stu-id="81504-123">Included By Default?</span></span>|  
|<span data-ttu-id="81504-124">搜索</span><span class="sxs-lookup"><span data-stu-id="81504-124">Search for</span></span>|<span data-ttu-id="81504-125">等于</span><span class="sxs-lookup"><span data-stu-id="81504-125">Equals</span></span>|<span data-ttu-id="81504-126">事务集聚合报告</span><span class="sxs-lookup"><span data-stu-id="81504-126">Transaction Set Aggregation Report</span></span>|<span data-ttu-id="81504-127">是（必需）</span><span class="sxs-lookup"><span data-stu-id="81504-127">Yes (required)</span></span>|  
|<span data-ttu-id="81504-128">交换日期时间</span><span class="sxs-lookup"><span data-stu-id="81504-128">Interchange Date Time</span></span>|<span data-ttu-id="81504-129">小于或等于</span><span class="sxs-lookup"><span data-stu-id="81504-129">Less Than or Equals</span></span><br /><br /> <span data-ttu-id="81504-130">大于或等于</span><span class="sxs-lookup"><span data-stu-id="81504-130">Greater Than or Equals</span></span>|<span data-ttu-id="81504-131">特定日期时间</span><span class="sxs-lookup"><span data-stu-id="81504-131">Specific Date Time</span></span><br /><br /> <span data-ttu-id="81504-132">今天</span><span class="sxs-lookup"><span data-stu-id="81504-132">Today</span></span><br /><br /> <span data-ttu-id="81504-133">Today-1</span><span class="sxs-lookup"><span data-stu-id="81504-133">Today - 1</span></span>|<span data-ttu-id="81504-134">是</span><span class="sxs-lookup"><span data-stu-id="81504-134">Yes</span></span><br /><br /> <span data-ttu-id="81504-135">注意： 可以包含两次在查询表达式中，一次用于小于-运算符，一次用于大于-运算符，以提供了一系列</span><span class="sxs-lookup"><span data-stu-id="81504-135">Note: Can be included twice in the query expression, once with a less-than operator and once with  a greater-than operator, to provide a range</span></span>|  
|<span data-ttu-id="81504-136">最大匹配数</span><span class="sxs-lookup"><span data-stu-id="81504-136">Maximum Matches</span></span>|<span data-ttu-id="81504-137">等于</span><span class="sxs-lookup"><span data-stu-id="81504-137">Equals</span></span>|<span data-ttu-id="81504-138">整数（默认值为 50）</span><span class="sxs-lookup"><span data-stu-id="81504-138">Integer (default of 50)</span></span>|<span data-ttu-id="81504-139">是</span><span class="sxs-lookup"><span data-stu-id="81504-139">Yes</span></span>|  
|<span data-ttu-id="81504-140">方向</span><span class="sxs-lookup"><span data-stu-id="81504-140">Direction</span></span>|<span data-ttu-id="81504-141">等于</span><span class="sxs-lookup"><span data-stu-id="81504-141">Equals</span></span>|<span data-ttu-id="81504-142">所有 （默认值）</span><span class="sxs-lookup"><span data-stu-id="81504-142">All (default)</span></span><br /><br /> <span data-ttu-id="81504-143">Receive</span><span class="sxs-lookup"><span data-stu-id="81504-143">Receive</span></span><br /><br /> <span data-ttu-id="81504-144">Send</span><span class="sxs-lookup"><span data-stu-id="81504-144">Send</span></span>|<span data-ttu-id="81504-145">“否”</span><span class="sxs-lookup"><span data-stu-id="81504-145">No</span></span>|  
|<span data-ttu-id="81504-146">接收方的参与方名称</span><span class="sxs-lookup"><span data-stu-id="81504-146">Receiver Party Name</span></span>|<span data-ttu-id="81504-147">等于</span><span class="sxs-lookup"><span data-stu-id="81504-147">Equals</span></span>|<span data-ttu-id="81504-148">所有 （默认值）</span><span class="sxs-lookup"><span data-stu-id="81504-148">All (default)</span></span><br /><br /> <span data-ttu-id="81504-149">特定参与方名称（AN 字符串）</span><span class="sxs-lookup"><span data-stu-id="81504-149">Specific party name (AN string)</span></span>|<span data-ttu-id="81504-150">“否”</span><span class="sxs-lookup"><span data-stu-id="81504-150">No</span></span>|  
|<span data-ttu-id="81504-151">发送方名称</span><span class="sxs-lookup"><span data-stu-id="81504-151">Sender Party Name</span></span>|<span data-ttu-id="81504-152">等于</span><span class="sxs-lookup"><span data-stu-id="81504-152">Equals</span></span>|<span data-ttu-id="81504-153">所有 （默认值）</span><span class="sxs-lookup"><span data-stu-id="81504-153">All (default)</span></span><br /><br /> <span data-ttu-id="81504-154">特定参与方名称（AN 字符串）</span><span class="sxs-lookup"><span data-stu-id="81504-154">Specific party name (AN string)</span></span>|<span data-ttu-id="81504-155">“否”</span><span class="sxs-lookup"><span data-stu-id="81504-155">No</span></span>|  
|<span data-ttu-id="81504-156">“登录属性”</span><span class="sxs-lookup"><span data-stu-id="81504-156">Status</span></span>|<span data-ttu-id="81504-157">等于</span><span class="sxs-lookup"><span data-stu-id="81504-157">Equals</span></span><br /><br /> <span data-ttu-id="81504-158">不等于</span><span class="sxs-lookup"><span data-stu-id="81504-158">Not Equals</span></span>|<span data-ttu-id="81504-159">已接受</span><span class="sxs-lookup"><span data-stu-id="81504-159">Accepted</span></span><br /><br /> <span data-ttu-id="81504-160">已接受但存在错误</span><span class="sxs-lookup"><span data-stu-id="81504-160">Accepted with Errors</span></span><br /><br /> <span data-ttu-id="81504-161">已发送</span><span class="sxs-lookup"><span data-stu-id="81504-161">Sent</span></span><br /><br /> <span data-ttu-id="81504-162">All</span><span class="sxs-lookup"><span data-stu-id="81504-162">All</span></span><br /><br /> <span data-ttu-id="81504-163">预期的确认</span><span class="sxs-lookup"><span data-stu-id="81504-163">Ack Expected</span></span><br /><br /> <span data-ttu-id="81504-164">非预期的确认</span><span class="sxs-lookup"><span data-stu-id="81504-164">Ack Not Expected</span></span><br /><br /> <span data-ttu-id="81504-165">已拒绝</span><span class="sxs-lookup"><span data-stu-id="81504-165">Rejected</span></span>|<span data-ttu-id="81504-166">“否”</span><span class="sxs-lookup"><span data-stu-id="81504-166">No</span></span>|  
|<span data-ttu-id="81504-167">事务集 ID</span><span class="sxs-lookup"><span data-stu-id="81504-167">Transaction Set ID</span></span>|<span data-ttu-id="81504-168">等于</span><span class="sxs-lookup"><span data-stu-id="81504-168">Equals</span></span>|<span data-ttu-id="81504-169">所有 （默认值）</span><span class="sxs-lookup"><span data-stu-id="81504-169">All (default)</span></span><br /><br /> <span data-ttu-id="81504-170">特定事务集 ID</span><span class="sxs-lookup"><span data-stu-id="81504-170">Specific transaction set ID</span></span>|<span data-ttu-id="81504-171">“否”</span><span class="sxs-lookup"><span data-stu-id="81504-171">No</span></span>|  
  
