---
title: 交换聚合报告 |Microsoft Docs
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
ms.openlocfilehash: df8163506f3b71379038e8beb82bc8f9f2297249
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381950"
---
# <a name="interchange-aggregation-report"></a><span data-ttu-id="1867e-102">交换聚合报告</span><span class="sxs-lookup"><span data-stu-id="1867e-102">Interchange Aggregation Report</span></span>
<span data-ttu-id="1867e-103">此报表提供了一条记录，用于指示共享同一 EDI 编码类型、 发送方、 接收方和方向的 EDI 交换。</span><span class="sxs-lookup"><span data-stu-id="1867e-103">This report provides one record that indicates the number of EDI interchanges that share the same EDI encoding type, sender party, receiver party, and direction.</span></span> <span data-ttu-id="1867e-104">此报表不提供有关单个交换的详细信息。</span><span class="sxs-lookup"><span data-stu-id="1867e-104">This report does not provide details about the individual interchanges.</span></span>  
  
 <span data-ttu-id="1867e-105">通过单击中的组中心页底部的交换聚合报告链接可显示此状态报告[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="1867e-105">This status report is displayed by clicking the Interchange Aggregation Report link at the bottom of the Group Hub page in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span>  
  
## <a name="fields-in-the-status-report"></a><span data-ttu-id="1867e-106">在状态报告中的字段</span><span class="sxs-lookup"><span data-stu-id="1867e-106">Fields in the Status Report</span></span>  
 <span data-ttu-id="1867e-107">交换聚合报告显示每个记录的以下信息：</span><span class="sxs-lookup"><span data-stu-id="1867e-107">The Interchange Aggregation Report displays the following information for each record:</span></span>  
  
- <span data-ttu-id="1867e-108">交换计数共享同一 EDI 编码类型、 发送方、 接收方和方向</span><span class="sxs-lookup"><span data-stu-id="1867e-108">A count of how many interchanges share the same EDI encoding type, sender party, receiver party, and direction</span></span>  
  
- <span data-ttu-id="1867e-109">记录中每个交换的发送方参与方</span><span class="sxs-lookup"><span data-stu-id="1867e-109">The Sender Party for each interchange in the record</span></span>  
  
- <span data-ttu-id="1867e-110">记录中每个交换的接收方参与方</span><span class="sxs-lookup"><span data-stu-id="1867e-110">The Receiver Party for each interchange in the record</span></span>  
  
- <span data-ttu-id="1867e-111">方向 （接收或发送） 的记录中每个交换</span><span class="sxs-lookup"><span data-stu-id="1867e-111">The Direction (receive or send) of each interchange in the record</span></span>  
  
- <span data-ttu-id="1867e-112">日期和时间的最早时间范围内发送或接收交换 （最早开始日期/时间）</span><span class="sxs-lookup"><span data-stu-id="1867e-112">The date and time at which the earliest interchange in the time range was sent or received (Earliest Started Date/Time)</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="1867e-113">对于收到的文档，如果交换中指定的日期格式为 YYMMDD 且 YY 大于或等于 75，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]会将年份显示为 19YY。</span><span class="sxs-lookup"><span data-stu-id="1867e-113">For received documents, if the date specified in the interchange is YYMMDD format and YY is greater than or equal to 75, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will display the year as 19YY.</span></span> <span data-ttu-id="1867e-114">如果日期是小于 75，将显示为 20YY。</span><span class="sxs-lookup"><span data-stu-id="1867e-114">If the date is less than 75, it will be displayed as 20YY.</span></span>  
  > 
  >  <span data-ttu-id="1867e-115">例如，如果您收到的交换包含值 991113 在 ISA09，最早开始日期/时间将为 1999 年 11/13/报告中列出。</span><span class="sxs-lookup"><span data-stu-id="1867e-115">For example, if you receive an interchange that contains the value 991113 in ISA09, the Earliest Started Date/time will be listed in the report as 11/13/1999.</span></span>  
  
- <span data-ttu-id="1867e-116">日期和时间的最新时间范围内发送或接收交换 （最新结束日期/时间）</span><span class="sxs-lookup"><span data-stu-id="1867e-116">The date and time at which the latest interchange in the time range was sent or received (Latest Ended Date/Time)</span></span>  
  
- <span data-ttu-id="1867e-117">EDI 编码类型的记录中每个交换</span><span class="sxs-lookup"><span data-stu-id="1867e-117">The EDI encoding type for each interchange in the record</span></span>  
  
## <a name="fields-in-the-query-expression-for-the-status-report"></a><span data-ttu-id="1867e-118">在状态报告的查询表达式中的字段</span><span class="sxs-lookup"><span data-stu-id="1867e-118">Fields in the Query Expression for the Status Report</span></span>  
 <span data-ttu-id="1867e-119">您可以更改用于确定所显示数据的查询表达式中的字段来自定义交换聚合报告。</span><span class="sxs-lookup"><span data-stu-id="1867e-119">You can customize the Interchange Aggregation Report by changing the fields in the query expression that determines the data displayed.</span></span> <span data-ttu-id="1867e-120">可以使用下列域：</span><span class="sxs-lookup"><span data-stu-id="1867e-120">The following fields are available:</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="1867e-121">查询表达式字段</span><span class="sxs-lookup"><span data-stu-id="1867e-121">Query Expression Field</span></span>|<span data-ttu-id="1867e-122">可能的运算符</span><span class="sxs-lookup"><span data-stu-id="1867e-122">Potential Operators</span></span>|<span data-ttu-id="1867e-123">可能的值</span><span class="sxs-lookup"><span data-stu-id="1867e-123">Potential Values</span></span>|<span data-ttu-id="1867e-124">默认情况下包含？</span><span class="sxs-lookup"><span data-stu-id="1867e-124">Included By Default?</span></span>|  
|<span data-ttu-id="1867e-125">搜索</span><span class="sxs-lookup"><span data-stu-id="1867e-125">Search for</span></span>|<span data-ttu-id="1867e-126">等于</span><span class="sxs-lookup"><span data-stu-id="1867e-126">Equals</span></span>|<span data-ttu-id="1867e-127">交换聚合报告</span><span class="sxs-lookup"><span data-stu-id="1867e-127">Interchange Aggregation Report</span></span>|<span data-ttu-id="1867e-128">是（必需）</span><span class="sxs-lookup"><span data-stu-id="1867e-128">Yes (required)</span></span>|  
|<span data-ttu-id="1867e-129">交换日期时间</span><span class="sxs-lookup"><span data-stu-id="1867e-129">Interchange Date Time</span></span>|<span data-ttu-id="1867e-130">小于或等于</span><span class="sxs-lookup"><span data-stu-id="1867e-130">Less Than or Equals</span></span><br /><br /> <span data-ttu-id="1867e-131">大于或等于</span><span class="sxs-lookup"><span data-stu-id="1867e-131">Greater Than or Equals</span></span>|<span data-ttu-id="1867e-132">特定日期时间</span><span class="sxs-lookup"><span data-stu-id="1867e-132">Specific Date Time</span></span><br /><br /> <span data-ttu-id="1867e-133">今天</span><span class="sxs-lookup"><span data-stu-id="1867e-133">Today</span></span><br /><br /> <span data-ttu-id="1867e-134">Today-1</span><span class="sxs-lookup"><span data-stu-id="1867e-134">Today - 1</span></span>|<span data-ttu-id="1867e-135">是</span><span class="sxs-lookup"><span data-stu-id="1867e-135">Yes</span></span><br /><br /> <span data-ttu-id="1867e-136">注意：可以包含在查询表达式中，一次用于小于两次-运算符，一次用于大于-运算符，以提供一个范围。</span><span class="sxs-lookup"><span data-stu-id="1867e-136">Note: Can be included twice in the query expression, once with a less-than operator and once with a greater-than operator, to provide a range.</span></span>|  
|<span data-ttu-id="1867e-137">最大匹配数</span><span class="sxs-lookup"><span data-stu-id="1867e-137">Maximum Matches</span></span>|<span data-ttu-id="1867e-138">等于</span><span class="sxs-lookup"><span data-stu-id="1867e-138">Equals</span></span>|<span data-ttu-id="1867e-139">整数 （默认值为 50）</span><span class="sxs-lookup"><span data-stu-id="1867e-139">Integer (default of 50)</span></span>|<span data-ttu-id="1867e-140">是</span><span class="sxs-lookup"><span data-stu-id="1867e-140">Yes</span></span>|  
|<span data-ttu-id="1867e-141">Direction</span><span class="sxs-lookup"><span data-stu-id="1867e-141">Direction</span></span>|<span data-ttu-id="1867e-142">等于</span><span class="sxs-lookup"><span data-stu-id="1867e-142">Equals</span></span>|<span data-ttu-id="1867e-143">所有 （默认值）</span><span class="sxs-lookup"><span data-stu-id="1867e-143">All (default)</span></span><br /><br /> <span data-ttu-id="1867e-144">Receive</span><span class="sxs-lookup"><span data-stu-id="1867e-144">Receive</span></span><br /><br /> <span data-ttu-id="1867e-145">Send</span><span class="sxs-lookup"><span data-stu-id="1867e-145">Send</span></span>|<span data-ttu-id="1867e-146">否</span><span class="sxs-lookup"><span data-stu-id="1867e-146">No</span></span>|  
|<span data-ttu-id="1867e-147">接收方的参与方名称</span><span class="sxs-lookup"><span data-stu-id="1867e-147">Receiver Party Name</span></span>|<span data-ttu-id="1867e-148">等于</span><span class="sxs-lookup"><span data-stu-id="1867e-148">Equals</span></span>|<span data-ttu-id="1867e-149">所有 （默认值）</span><span class="sxs-lookup"><span data-stu-id="1867e-149">All (default)</span></span><br /><br /> <span data-ttu-id="1867e-150">特定参与方名称 （字符串）</span><span class="sxs-lookup"><span data-stu-id="1867e-150">Specific party name (AN string)</span></span>|<span data-ttu-id="1867e-151">否</span><span class="sxs-lookup"><span data-stu-id="1867e-151">No</span></span>|  
|<span data-ttu-id="1867e-152">发送方的参与方名称</span><span class="sxs-lookup"><span data-stu-id="1867e-152">Sender Party Name</span></span>|<span data-ttu-id="1867e-153">等于</span><span class="sxs-lookup"><span data-stu-id="1867e-153">Equals</span></span>|<span data-ttu-id="1867e-154">所有 （默认值）</span><span class="sxs-lookup"><span data-stu-id="1867e-154">All (default)</span></span><br /><br /> <span data-ttu-id="1867e-155">特定参与方名称 （字符串）</span><span class="sxs-lookup"><span data-stu-id="1867e-155">Specific party name (AN string)</span></span>|<span data-ttu-id="1867e-156">否</span><span class="sxs-lookup"><span data-stu-id="1867e-156">No</span></span>|  
|<span data-ttu-id="1867e-157">“登录属性”</span><span class="sxs-lookup"><span data-stu-id="1867e-157">Status</span></span>|<span data-ttu-id="1867e-158">等于</span><span class="sxs-lookup"><span data-stu-id="1867e-158">Equals</span></span><br /><br /> <span data-ttu-id="1867e-159">不等于</span><span class="sxs-lookup"><span data-stu-id="1867e-159">Not Equals</span></span>|<span data-ttu-id="1867e-160">接受</span><span class="sxs-lookup"><span data-stu-id="1867e-160">Accepted</span></span><br /><br /> <span data-ttu-id="1867e-161">已接受但有错误</span><span class="sxs-lookup"><span data-stu-id="1867e-161">Accepted with Errors</span></span><br /><br /> <span data-ttu-id="1867e-162">发送</span><span class="sxs-lookup"><span data-stu-id="1867e-162">Sent</span></span><br /><br /> <span data-ttu-id="1867e-163">All</span><span class="sxs-lookup"><span data-stu-id="1867e-163">All</span></span><br /><br /> <span data-ttu-id="1867e-164">预期的确认</span><span class="sxs-lookup"><span data-stu-id="1867e-164">Ack Expected</span></span><br /><br /> <span data-ttu-id="1867e-165">非预期的确认</span><span class="sxs-lookup"><span data-stu-id="1867e-165">Ack Not Expected</span></span><br /><br /> <span data-ttu-id="1867e-166">已拒绝</span><span class="sxs-lookup"><span data-stu-id="1867e-166">Rejected</span></span>|<span data-ttu-id="1867e-167">否</span><span class="sxs-lookup"><span data-stu-id="1867e-167">No</span></span>|