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
ms.openlocfilehash: 312b39c3313ce787a501f5473d9d311076fed252
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65313254"
---
# <a name="transaction-set-aggregation-report"></a><span data-ttu-id="07740-102">事务集聚合报告</span><span class="sxs-lookup"><span data-stu-id="07740-102">Transaction Set Aggregation Report</span></span>
<span data-ttu-id="07740-103">此报表提供了显示的共享同一事务集 ID、 EDI 编码类型、 发送方、 接收方和方向的 EDI 事务集数目的单个记录。</span><span class="sxs-lookup"><span data-stu-id="07740-103">This report provides a single record that shows the number of EDI transaction sets that share the same Transaction Set ID, EDI encoding type, sender party, receiver party, and direction.</span></span> <span data-ttu-id="07740-104">此报表不提供有关各个事务集的详细信息。</span><span class="sxs-lookup"><span data-stu-id="07740-104">This report does not provide details about the individual transaction sets.</span></span>  
  
 <span data-ttu-id="07740-105">通过单击 BizTalk Server 管理控制台中的组中心页底部的事务集聚合报告链接可显示此状态报告。</span><span class="sxs-lookup"><span data-stu-id="07740-105">This status report is displayed by clicking the Transaction Set Aggregation Report link at the bottom of the Group Hub page in the BizTalk Server Administration Console.</span></span>  
  
## <a name="fields-in-the-status-report"></a><span data-ttu-id="07740-106">在状态报告中的字段</span><span class="sxs-lookup"><span data-stu-id="07740-106">Fields in the Status Report</span></span>  
 <span data-ttu-id="07740-107">事务集聚合报告显示有关接收或发送交换的以下信息：</span><span class="sxs-lookup"><span data-stu-id="07740-107">The Transaction Set Aggregation Report displays the following information for the received or sent interchanges:</span></span>  
  
- <span data-ttu-id="07740-108">事务集计数共享同一事务集 ID、 EDI 编码类型、 发送方、 接收方和方向</span><span class="sxs-lookup"><span data-stu-id="07740-108">A count of how many transaction sets share the same Transaction Set ID, EDI encoding type, sender party, receiver party, and direction</span></span>  
  
- <span data-ttu-id="07740-109">每个事务集记录中的发件人参与方</span><span class="sxs-lookup"><span data-stu-id="07740-109">The Sender Party for each transaction set in the record</span></span>  
  
- <span data-ttu-id="07740-110">每个事务集记录中接收方</span><span class="sxs-lookup"><span data-stu-id="07740-110">The Receiver Party for each transaction set in the record</span></span>  
  
- <span data-ttu-id="07740-111">方向 （接收或发送） 的每个事务集记录中</span><span class="sxs-lookup"><span data-stu-id="07740-111">The Direction (receive or send) of each transaction set in the record</span></span>  
  
- <span data-ttu-id="07740-112">已发送或接收 （最早开始日期/时间） 的日期和时间最早事务的时间范围内设置</span><span class="sxs-lookup"><span data-stu-id="07740-112">The date and time at which the earliest transaction set in the time range was sent or received (Earliest Started Date/Time)</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="07740-113">对于收到的文档，如果交换中指定的日期格式为 YYMMDD 且 YY 大于或等于 75，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]会将年份显示为 19YY。</span><span class="sxs-lookup"><span data-stu-id="07740-113">For received documents, if the date specified in the interchange is YYMMDD format and YY is greater than or equal to 75, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will display the year as 19YY.</span></span> <span data-ttu-id="07740-114">如果日期是小于 75，将显示为 20YY。</span><span class="sxs-lookup"><span data-stu-id="07740-114">If the date is less than 75, it will be displayed as 20YY.</span></span>  
  > 
  >  <span data-ttu-id="07740-115">例如，如果收到包含在 ISA09 中的值 991113 的交换，最早开始日期/时间将会报告中列出为 1999 年 11/13。</span><span class="sxs-lookup"><span data-stu-id="07740-115">For example, if you receive an interchange that contains the value 991113 in ISA09, the Earliest Started Date/Time will be listed in the report as 11/13/1999.</span></span>  
  
- <span data-ttu-id="07740-116">日期和时间的最新的事务设置的时间范围内发送或接收 （最新结束日期/时间）</span><span class="sxs-lookup"><span data-stu-id="07740-116">The date and time at which the latest transaction set in the time range was sent or received (Latest Ended Date/Time)</span></span>  
  
## <a name="fields-in-the-query-expression-for-the-status-report"></a><span data-ttu-id="07740-117">在状态报告的查询表达式中的字段</span><span class="sxs-lookup"><span data-stu-id="07740-117">Fields in the Query Expression for the Status Report</span></span>  
 <span data-ttu-id="07740-118">您可以更改用于确定所显示数据的查询表达式中的字段来自定义交换聚合报告。</span><span class="sxs-lookup"><span data-stu-id="07740-118">You can customize the Interchange Aggregation Report by changing the fields in the query expression that determines the data displayed.</span></span> <span data-ttu-id="07740-119">可以使用下列域：</span><span class="sxs-lookup"><span data-stu-id="07740-119">The following fields are available:</span></span>  
  
|||||  
|-|-|-|-|  
|<span data-ttu-id="07740-120">查询表达式字段</span><span class="sxs-lookup"><span data-stu-id="07740-120">Query Expression Field</span></span>|<span data-ttu-id="07740-121">可能的运算符</span><span class="sxs-lookup"><span data-stu-id="07740-121">Potential Operators</span></span>|<span data-ttu-id="07740-122">可能的值</span><span class="sxs-lookup"><span data-stu-id="07740-122">Potential Values</span></span>|<span data-ttu-id="07740-123">默认情况下包含？</span><span class="sxs-lookup"><span data-stu-id="07740-123">Included By Default?</span></span>|  
|<span data-ttu-id="07740-124">搜索</span><span class="sxs-lookup"><span data-stu-id="07740-124">Search for</span></span>|<span data-ttu-id="07740-125">等于</span><span class="sxs-lookup"><span data-stu-id="07740-125">Equals</span></span>|<span data-ttu-id="07740-126">事务集聚合报告</span><span class="sxs-lookup"><span data-stu-id="07740-126">Transaction Set Aggregation Report</span></span>|<span data-ttu-id="07740-127">是（必需）</span><span class="sxs-lookup"><span data-stu-id="07740-127">Yes (required)</span></span>|  
|<span data-ttu-id="07740-128">交换日期时间</span><span class="sxs-lookup"><span data-stu-id="07740-128">Interchange Date Time</span></span>|<span data-ttu-id="07740-129">小于或等于</span><span class="sxs-lookup"><span data-stu-id="07740-129">Less Than or Equals</span></span><br /><br /> <span data-ttu-id="07740-130">大于或等于</span><span class="sxs-lookup"><span data-stu-id="07740-130">Greater Than or Equals</span></span>|<span data-ttu-id="07740-131">特定日期时间</span><span class="sxs-lookup"><span data-stu-id="07740-131">Specific Date Time</span></span><br /><br /> <span data-ttu-id="07740-132">今天</span><span class="sxs-lookup"><span data-stu-id="07740-132">Today</span></span><br /><br /> <span data-ttu-id="07740-133">Today-1</span><span class="sxs-lookup"><span data-stu-id="07740-133">Today - 1</span></span>|<span data-ttu-id="07740-134">是</span><span class="sxs-lookup"><span data-stu-id="07740-134">Yes</span></span><br /><br /> <span data-ttu-id="07740-135">注意：可以包含在查询表达式中，一次用于小于两次-运算符，一次用于大于-运算符，以提供了一系列</span><span class="sxs-lookup"><span data-stu-id="07740-135">Note: Can be included twice in the query expression, once with a less-than operator and once with  a greater-than operator, to provide a range</span></span>|  
|<span data-ttu-id="07740-136">最大匹配数</span><span class="sxs-lookup"><span data-stu-id="07740-136">Maximum Matches</span></span>|<span data-ttu-id="07740-137">等于</span><span class="sxs-lookup"><span data-stu-id="07740-137">Equals</span></span>|<span data-ttu-id="07740-138">整数 （默认值为 50）</span><span class="sxs-lookup"><span data-stu-id="07740-138">Integer (default of 50)</span></span>|<span data-ttu-id="07740-139">是</span><span class="sxs-lookup"><span data-stu-id="07740-139">Yes</span></span>|  
|<span data-ttu-id="07740-140">Direction</span><span class="sxs-lookup"><span data-stu-id="07740-140">Direction</span></span>|<span data-ttu-id="07740-141">等于</span><span class="sxs-lookup"><span data-stu-id="07740-141">Equals</span></span>|<span data-ttu-id="07740-142">所有 （默认值）</span><span class="sxs-lookup"><span data-stu-id="07740-142">All (default)</span></span><br /><br /> <span data-ttu-id="07740-143">Receive</span><span class="sxs-lookup"><span data-stu-id="07740-143">Receive</span></span><br /><br /> <span data-ttu-id="07740-144">Send</span><span class="sxs-lookup"><span data-stu-id="07740-144">Send</span></span>|<span data-ttu-id="07740-145">否</span><span class="sxs-lookup"><span data-stu-id="07740-145">No</span></span>|  
|<span data-ttu-id="07740-146">接收方的参与方名称</span><span class="sxs-lookup"><span data-stu-id="07740-146">Receiver Party Name</span></span>|<span data-ttu-id="07740-147">等于</span><span class="sxs-lookup"><span data-stu-id="07740-147">Equals</span></span>|<span data-ttu-id="07740-148">所有 （默认值）</span><span class="sxs-lookup"><span data-stu-id="07740-148">All (default)</span></span><br /><br /> <span data-ttu-id="07740-149">特定参与方名称 （字符串）</span><span class="sxs-lookup"><span data-stu-id="07740-149">Specific party name (AN string)</span></span>|<span data-ttu-id="07740-150">否</span><span class="sxs-lookup"><span data-stu-id="07740-150">No</span></span>|  
|<span data-ttu-id="07740-151">发送方的参与方名称</span><span class="sxs-lookup"><span data-stu-id="07740-151">Sender Party Name</span></span>|<span data-ttu-id="07740-152">等于</span><span class="sxs-lookup"><span data-stu-id="07740-152">Equals</span></span>|<span data-ttu-id="07740-153">所有 （默认值）</span><span class="sxs-lookup"><span data-stu-id="07740-153">All (default)</span></span><br /><br /> <span data-ttu-id="07740-154">特定参与方名称 （字符串）</span><span class="sxs-lookup"><span data-stu-id="07740-154">Specific party name (AN string)</span></span>|<span data-ttu-id="07740-155">否</span><span class="sxs-lookup"><span data-stu-id="07740-155">No</span></span>|  
|<span data-ttu-id="07740-156">“登录属性”</span><span class="sxs-lookup"><span data-stu-id="07740-156">Status</span></span>|<span data-ttu-id="07740-157">等于</span><span class="sxs-lookup"><span data-stu-id="07740-157">Equals</span></span><br /><br /> <span data-ttu-id="07740-158">不等于</span><span class="sxs-lookup"><span data-stu-id="07740-158">Not Equals</span></span>|<span data-ttu-id="07740-159">接受</span><span class="sxs-lookup"><span data-stu-id="07740-159">Accepted</span></span><br /><br /> <span data-ttu-id="07740-160">已接受但有错误</span><span class="sxs-lookup"><span data-stu-id="07740-160">Accepted with Errors</span></span><br /><br /> <span data-ttu-id="07740-161">发送</span><span class="sxs-lookup"><span data-stu-id="07740-161">Sent</span></span><br /><br /> <span data-ttu-id="07740-162">All</span><span class="sxs-lookup"><span data-stu-id="07740-162">All</span></span><br /><br /> <span data-ttu-id="07740-163">预期的确认</span><span class="sxs-lookup"><span data-stu-id="07740-163">Ack Expected</span></span><br /><br /> <span data-ttu-id="07740-164">非预期的确认</span><span class="sxs-lookup"><span data-stu-id="07740-164">Ack Not Expected</span></span><br /><br /> <span data-ttu-id="07740-165">已拒绝</span><span class="sxs-lookup"><span data-stu-id="07740-165">Rejected</span></span>|<span data-ttu-id="07740-166">否</span><span class="sxs-lookup"><span data-stu-id="07740-166">No</span></span>|  
|<span data-ttu-id="07740-167">事务集 ID</span><span class="sxs-lookup"><span data-stu-id="07740-167">Transaction Set ID</span></span>|<span data-ttu-id="07740-168">等于</span><span class="sxs-lookup"><span data-stu-id="07740-168">Equals</span></span>|<span data-ttu-id="07740-169">所有 （默认值）</span><span class="sxs-lookup"><span data-stu-id="07740-169">All (default)</span></span><br /><br /> <span data-ttu-id="07740-170">特定事务集 ID</span><span class="sxs-lookup"><span data-stu-id="07740-170">Specific transaction set ID</span></span>|<span data-ttu-id="07740-171">否</span><span class="sxs-lookup"><span data-stu-id="07740-171">No</span></span>|  
  
