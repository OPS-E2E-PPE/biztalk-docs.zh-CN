---
title: 交换聚合报表 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4619e8d0-9e9e-4d19-a67a-ac1058a0579b
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ac86a43bc74d862aa856a18f1564b03bc7f4e89
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257877"
---
# <a name="interchange-aggregation-report"></a><span data-ttu-id="1d6e8-102">交换聚合报表</span><span class="sxs-lookup"><span data-stu-id="1d6e8-102">Interchange Aggregation Report</span></span>
<span data-ttu-id="1d6e8-103">此报告中提供的一项记录指明了共享同一 EDI 编码类型、发送方、接收方和方向的 EDI 交换的数量。</span><span class="sxs-lookup"><span data-stu-id="1d6e8-103">This report provides one record that indicates the number of EDI interchanges that share the same EDI encoding type, sender party, receiver party, and direction.</span></span> <span data-ttu-id="1d6e8-104">此报告不提供有关单个交换的详细信息。</span><span class="sxs-lookup"><span data-stu-id="1d6e8-104">This report does not provide details about the individual interchanges.</span></span>  
  
 <span data-ttu-id="1d6e8-105">通过单击 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中“组中心”页底部的“交换聚合报告”链接可显示此状态报告。</span><span class="sxs-lookup"><span data-stu-id="1d6e8-105">This status report is displayed by clicking the Interchange Aggregation Report link at the bottom of the Group Hub page in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span>  
  
## <a name="fields-in-the-status-report"></a><span data-ttu-id="1d6e8-106">状态报告中的字段</span><span class="sxs-lookup"><span data-stu-id="1d6e8-106">Fields in the Status Report</span></span>  
 <span data-ttu-id="1d6e8-107">在交换聚合报告的每项记录中将显示如下信息：</span><span class="sxs-lookup"><span data-stu-id="1d6e8-107">The Interchange Aggregation Report displays the following information for each record:</span></span>  
  
-   <span data-ttu-id="1d6e8-108">共享同一 EDI 编码类型、发送方、接收方和方向的交换的数量。</span><span class="sxs-lookup"><span data-stu-id="1d6e8-108">A count of how many interchanges share the same EDI encoding type, sender party, receiver party, and direction</span></span>  
  
-   <span data-ttu-id="1d6e8-109">记录中每个交换的发送方</span><span class="sxs-lookup"><span data-stu-id="1d6e8-109">The Sender Party for each interchange in the record</span></span>  
  
-   <span data-ttu-id="1d6e8-110">记录中每个交换的接收方</span><span class="sxs-lookup"><span data-stu-id="1d6e8-110">The Receiver Party for each interchange in the record</span></span>  
  
-   <span data-ttu-id="1d6e8-111">记录中每个交换的方向（接收或发送）</span><span class="sxs-lookup"><span data-stu-id="1d6e8-111">The Direction (receive or send) of each interchange in the record</span></span>  
  
-   <span data-ttu-id="1d6e8-112">在时间范围内发送或接收最早交换的日期和时间（最早开始日期/时间）</span><span class="sxs-lookup"><span data-stu-id="1d6e8-112">The date and time at which the earliest interchange in the time range was sent or received (Earliest Started Date/Time)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1d6e8-113">对于收到的文档，如果在交换中指定的日期格式为 YYMMDD 且 YY 大于等于 75，则 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 会将年份显示为 19YY。</span><span class="sxs-lookup"><span data-stu-id="1d6e8-113">For received documents, if the date specified in the interchange is YYMMDD format and YY is greater than or equal to 75, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will display the year as 19YY.</span></span> <span data-ttu-id="1d6e8-114">如果日期中的 YY 小于 75，将显示为 20YY。</span><span class="sxs-lookup"><span data-stu-id="1d6e8-114">If the date is less than 75, it will be displayed as 20YY.</span></span>  
    >   
    >  <span data-ttu-id="1d6e8-115">例如，如果您收到的交换在 ISA09 中包含值 991113，则在报告中将“最早开始日期/时间”显示为 11/13/1999。</span><span class="sxs-lookup"><span data-stu-id="1d6e8-115">For example, if you receive an interchange that contains the value 991113 in ISA09, the Earliest Started Date/time will be listed in the report as 11/13/1999.</span></span>  
  
-   <span data-ttu-id="1d6e8-116">在时间范围内发送或接收最晚交换的日期和时间（最晚结束日期/时间）</span><span class="sxs-lookup"><span data-stu-id="1d6e8-116">The date and time at which the latest interchange in the time range was sent or received (Latest Ended Date/Time)</span></span>  
  
-   <span data-ttu-id="1d6e8-117">记录中每个交换的 EDI 编码类型</span><span class="sxs-lookup"><span data-stu-id="1d6e8-117">The EDI encoding type for each interchange in the record</span></span>  
  
## <a name="fields-in-the-query-expression-for-the-status-report"></a><span data-ttu-id="1d6e8-118">状态报告的查询表达式中的字段</span><span class="sxs-lookup"><span data-stu-id="1d6e8-118">Fields in the Query Expression for the Status Report</span></span>  
 <span data-ttu-id="1d6e8-119">您可以通过更改用于确定所显示数据的查询表达式中的字段来自定义交换聚合报告。</span><span class="sxs-lookup"><span data-stu-id="1d6e8-119">You can customize the Interchange Aggregation Report by changing the fields in the query expression that determines the data displayed.</span></span> <span data-ttu-id="1d6e8-120">下列字段可用：</span><span class="sxs-lookup"><span data-stu-id="1d6e8-120">The following fields are available:</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="1d6e8-121">查询表达式字段</span><span class="sxs-lookup"><span data-stu-id="1d6e8-121">Query Expression Field</span></span>|<span data-ttu-id="1d6e8-122">可能的运算符</span><span class="sxs-lookup"><span data-stu-id="1d6e8-122">Potential Operators</span></span>|<span data-ttu-id="1d6e8-123">可能的值</span><span class="sxs-lookup"><span data-stu-id="1d6e8-123">Potential Values</span></span>|<span data-ttu-id="1d6e8-124">默认情况下是否包括？</span><span class="sxs-lookup"><span data-stu-id="1d6e8-124">Included By Default?</span></span>|  
|<span data-ttu-id="1d6e8-125">搜索</span><span class="sxs-lookup"><span data-stu-id="1d6e8-125">Search for</span></span>|<span data-ttu-id="1d6e8-126">等于</span><span class="sxs-lookup"><span data-stu-id="1d6e8-126">Equals</span></span>|<span data-ttu-id="1d6e8-127">交换聚合报表</span><span class="sxs-lookup"><span data-stu-id="1d6e8-127">Interchange Aggregation Report</span></span>|<span data-ttu-id="1d6e8-128">是（必需）</span><span class="sxs-lookup"><span data-stu-id="1d6e8-128">Yes (required)</span></span>|  
|<span data-ttu-id="1d6e8-129">交换日期时间</span><span class="sxs-lookup"><span data-stu-id="1d6e8-129">Interchange Date Time</span></span>|<span data-ttu-id="1d6e8-130">小于或等于</span><span class="sxs-lookup"><span data-stu-id="1d6e8-130">Less Than or Equals</span></span><br /><br /> <span data-ttu-id="1d6e8-131">大于或等于</span><span class="sxs-lookup"><span data-stu-id="1d6e8-131">Greater Than or Equals</span></span>|<span data-ttu-id="1d6e8-132">特定日期时间</span><span class="sxs-lookup"><span data-stu-id="1d6e8-132">Specific Date Time</span></span><br /><br /> <span data-ttu-id="1d6e8-133">今天</span><span class="sxs-lookup"><span data-stu-id="1d6e8-133">Today</span></span><br /><br /> <span data-ttu-id="1d6e8-134">Today-1</span><span class="sxs-lookup"><span data-stu-id="1d6e8-134">Today - 1</span></span>|<span data-ttu-id="1d6e8-135">是</span><span class="sxs-lookup"><span data-stu-id="1d6e8-135">Yes</span></span><br /><br /> <span data-ttu-id="1d6e8-136">注意： 可以包含在查询表达式中，一次使用小于两次-比运算符和一次使用大于-高于运算符，提供一系列。</span><span class="sxs-lookup"><span data-stu-id="1d6e8-136">Note: Can be included twice in the query expression, once with a less-than operator and once with a greater-than operator, to provide a range.</span></span>|  
|<span data-ttu-id="1d6e8-137">最大匹配数</span><span class="sxs-lookup"><span data-stu-id="1d6e8-137">Maximum Matches</span></span>|<span data-ttu-id="1d6e8-138">等于</span><span class="sxs-lookup"><span data-stu-id="1d6e8-138">Equals</span></span>|<span data-ttu-id="1d6e8-139">整数（默认值为 50）</span><span class="sxs-lookup"><span data-stu-id="1d6e8-139">Integer (default of 50)</span></span>|<span data-ttu-id="1d6e8-140">是</span><span class="sxs-lookup"><span data-stu-id="1d6e8-140">Yes</span></span>|  
|<span data-ttu-id="1d6e8-141">方向</span><span class="sxs-lookup"><span data-stu-id="1d6e8-141">Direction</span></span>|<span data-ttu-id="1d6e8-142">等于</span><span class="sxs-lookup"><span data-stu-id="1d6e8-142">Equals</span></span>|<span data-ttu-id="1d6e8-143">所有 （默认值）</span><span class="sxs-lookup"><span data-stu-id="1d6e8-143">All (default)</span></span><br /><br /> <span data-ttu-id="1d6e8-144">Receive</span><span class="sxs-lookup"><span data-stu-id="1d6e8-144">Receive</span></span><br /><br /> <span data-ttu-id="1d6e8-145">Send</span><span class="sxs-lookup"><span data-stu-id="1d6e8-145">Send</span></span>|<span data-ttu-id="1d6e8-146">是</span><span class="sxs-lookup"><span data-stu-id="1d6e8-146">No</span></span>|  
|<span data-ttu-id="1d6e8-147">接收方参与方名称</span><span class="sxs-lookup"><span data-stu-id="1d6e8-147">Receiver Party Name</span></span>|<span data-ttu-id="1d6e8-148">等于</span><span class="sxs-lookup"><span data-stu-id="1d6e8-148">Equals</span></span>|<span data-ttu-id="1d6e8-149">所有 （默认值）</span><span class="sxs-lookup"><span data-stu-id="1d6e8-149">All (default)</span></span><br /><br /> <span data-ttu-id="1d6e8-150">特定参与方名称（AN 字符串）</span><span class="sxs-lookup"><span data-stu-id="1d6e8-150">Specific party name (AN string)</span></span>|<span data-ttu-id="1d6e8-151">是</span><span class="sxs-lookup"><span data-stu-id="1d6e8-151">No</span></span>|  
|<span data-ttu-id="1d6e8-152">发送方名称</span><span class="sxs-lookup"><span data-stu-id="1d6e8-152">Sender Party Name</span></span>|<span data-ttu-id="1d6e8-153">等于</span><span class="sxs-lookup"><span data-stu-id="1d6e8-153">Equals</span></span>|<span data-ttu-id="1d6e8-154">所有 （默认值）</span><span class="sxs-lookup"><span data-stu-id="1d6e8-154">All (default)</span></span><br /><br /> <span data-ttu-id="1d6e8-155">特定参与方名称（AN 字符串）</span><span class="sxs-lookup"><span data-stu-id="1d6e8-155">Specific party name (AN string)</span></span>|<span data-ttu-id="1d6e8-156">是</span><span class="sxs-lookup"><span data-stu-id="1d6e8-156">No</span></span>|  
|<span data-ttu-id="1d6e8-157">状态</span><span class="sxs-lookup"><span data-stu-id="1d6e8-157">Status</span></span>|<span data-ttu-id="1d6e8-158">等于</span><span class="sxs-lookup"><span data-stu-id="1d6e8-158">Equals</span></span><br /><br /> <span data-ttu-id="1d6e8-159">不等于</span><span class="sxs-lookup"><span data-stu-id="1d6e8-159">Not Equals</span></span>|<span data-ttu-id="1d6e8-160">已接受</span><span class="sxs-lookup"><span data-stu-id="1d6e8-160">Accepted</span></span><br /><br /> <span data-ttu-id="1d6e8-161">已接受但存在错误</span><span class="sxs-lookup"><span data-stu-id="1d6e8-161">Accepted with Errors</span></span><br /><br /> <span data-ttu-id="1d6e8-162">已发送</span><span class="sxs-lookup"><span data-stu-id="1d6e8-162">Sent</span></span><br /><br /> <span data-ttu-id="1d6e8-163">全部</span><span class="sxs-lookup"><span data-stu-id="1d6e8-163">All</span></span><br /><br /> <span data-ttu-id="1d6e8-164">预期的确认</span><span class="sxs-lookup"><span data-stu-id="1d6e8-164">Ack Expected</span></span><br /><br /> <span data-ttu-id="1d6e8-165">非预期的确认</span><span class="sxs-lookup"><span data-stu-id="1d6e8-165">Ack Not Expected</span></span><br /><br /> <span data-ttu-id="1d6e8-166">已拒绝</span><span class="sxs-lookup"><span data-stu-id="1d6e8-166">Rejected</span></span>|<span data-ttu-id="1d6e8-167">是</span><span class="sxs-lookup"><span data-stu-id="1d6e8-167">No</span></span>|