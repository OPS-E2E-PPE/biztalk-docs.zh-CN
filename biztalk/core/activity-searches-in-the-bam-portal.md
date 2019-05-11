---
title: BAM 门户中的活动搜索 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- activities [BAM], searching
- queries [BAM], field descriptions
- Query Builder [BAM portal], creating queries
- queries [BAM], activity searches
- Query Builder [BAM portal], about Query Builder
- Query Builder [BAM portal], activity searches
- Query Builder [BAM portal]
- Query Builder [BAM portal], field descriptions
- BAM portal, Query Builder
- BAM portal, activity searches
ms.assetid: 60ab8deb-ebe2-4959-97fd-261ff64d500c
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b97f9577d43552ad51766ccc4178bb2d73fb7107
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361589"
---
# <a name="activity-searches-in-the-bam-portal"></a><span data-ttu-id="a358d-102">BAM 门户中的活动搜索</span><span class="sxs-lookup"><span data-stu-id="a358d-102">Activity Searches in the BAM Portal</span></span>
<span data-ttu-id="a358d-103">活动搜索，可对 BAM 数据，以查找对其基于您指定基于跟踪的值和项可在 BAM 视图中，并显示这些活动，以便可以对其进行编辑或创建警报的条件匹配的活动执行搜索。</span><span class="sxs-lookup"><span data-stu-id="a358d-103">An activity search allows you to perform searches against BAM data to find activities that match the criteria you specify based on tracked values and items available in a BAM view, and to display these activities so that you can edit them or create alerts based on them.</span></span>  
  
## <a name="parts-of-the-query-builder"></a><span data-ttu-id="a358d-104">查询生成器的各个部分</span><span class="sxs-lookup"><span data-stu-id="a358d-104">Parts of the Query Builder</span></span>  
 <span data-ttu-id="a358d-105">通过选择将对其创建布尔比较中提取感兴趣的数据的业务数据的项，可以为活动搜索生成查询。</span><span class="sxs-lookup"><span data-stu-id="a358d-105">You build queries for your activity search by selecting items of business data against which you will create Boolean comparisons to extract data of interest.</span></span> <span data-ttu-id="a358d-106">首先选择中的 BAM 视图**我的视图**门户的框架。</span><span class="sxs-lookup"><span data-stu-id="a358d-106">You start by selecting a BAM view from the **My Views** frame of the portal.</span></span> <span data-ttu-id="a358d-107">从所选视图中选择要生成查询的活动。</span><span class="sxs-lookup"><span data-stu-id="a358d-107">From the selected view you select an activity on which to build the query.</span></span>  
  
 <span data-ttu-id="a358d-108">![](../core/media/bamportalviewschooser.gif "BAMPortalViewsChooser")</span><span class="sxs-lookup"><span data-stu-id="a358d-108">![](../core/media/bamportalviewschooser.gif "BAMPortalViewsChooser")</span></span>  
  
 <span data-ttu-id="a358d-109">当已选择活动时，在门户内容框架将显示查询生成器、 列选择器和结果框。</span><span class="sxs-lookup"><span data-stu-id="a358d-109">When you have selected the activity, the content frame of the portal displays the Query builder, Column Chooser, and Results boxes.</span></span> <span data-ttu-id="a358d-110">您可以打开现有查询，也可以生成一个新。</span><span class="sxs-lookup"><span data-stu-id="a358d-110">You can open an existing query or you can build a new one.</span></span>  
  
 <span data-ttu-id="a358d-111">![](../core/media/activitysearchquerybuilder.gif "ActivitySearchQueryBuilder")</span><span class="sxs-lookup"><span data-stu-id="a358d-111">![](../core/media/activitysearchquerybuilder.gif "ActivitySearchQueryBuilder")</span></span>  
  
 <span data-ttu-id="a358d-112">若要生成一个新的查询首先选择一个业务数据项**业务数据**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="a358d-112">To build a new query you start by selecting a business data item from the **Business Data** drop-down list.</span></span>  
  
 <span data-ttu-id="a358d-113">![](../core/media/activitysearchquerybuilderbusinessdatadropdown.gif "ActivitySearchQueryBuilderBusinessDataDropdown")</span><span class="sxs-lookup"><span data-stu-id="a358d-113">![](../core/media/activitysearchquerybuilderbusinessdatadropdown.gif "ActivitySearchQueryBuilderBusinessDataDropdown")</span></span>  
  
 <span data-ttu-id="a358d-114">接下来，在运算符下拉列表中选择比较运算符。</span><span class="sxs-lookup"><span data-stu-id="a358d-114">Next, you select your comparison operator in the Operator drop-down list.</span></span> <span data-ttu-id="a358d-115">比较运算符可以优化查询的结果。</span><span class="sxs-lookup"><span data-stu-id="a358d-115">The comparison operator allows you to refine the results of the query.</span></span>  
  
 <span data-ttu-id="a358d-116">![](../core/media/activitysearchcomparisonoperatordropdown.gif "ActivitySearchComparisonOperatorDropDown")</span><span class="sxs-lookup"><span data-stu-id="a358d-116">![](../core/media/activitysearchcomparisonoperatordropdown.gif "ActivitySearchComparisonOperatorDropDown")</span></span>  
  
 <span data-ttu-id="a358d-117">值下拉列表是上下文相关基于业务数据项表示的数据类型。</span><span class="sxs-lookup"><span data-stu-id="a358d-117">The Value drop-down list is context-sensitive based on the type of data represented by the business data item.</span></span> <span data-ttu-id="a358d-118">用户界面 (UI) 更改为允许的数据更改的类型。</span><span class="sxs-lookup"><span data-stu-id="a358d-118">The user interface (UI) changes as the type of permitted data changes.</span></span>  
  
 <span data-ttu-id="a358d-119">可以将联接的查询的子句和 OR 运算符，以形成更复杂的查询，通过单击**添加**按钮。</span><span class="sxs-lookup"><span data-stu-id="a358d-119">You can join clauses of the query with AND or OR operators to form more complex queries by clicking the **Add** button.</span></span>  
  
 <span data-ttu-id="a358d-120">![](../core/media/activitysearchjoiningclauses.gif "ActivitySearchJoiningClauses")</span><span class="sxs-lookup"><span data-stu-id="a358d-120">![](../core/media/activitysearchjoiningclauses.gif "ActivitySearchJoiningClauses")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a358d-121">不能对子句进行分组。</span><span class="sxs-lookup"><span data-stu-id="a358d-121">You cannot group clauses.</span></span> <span data-ttu-id="a358d-122">查询是通过联接多个子句的简单字符串和/或运算符。</span><span class="sxs-lookup"><span data-stu-id="a358d-122">A query is a simple string of individual clauses joined by AND/OR operators.</span></span>  
  
 <span data-ttu-id="a358d-123">下表描述的日期和时间字段。</span><span class="sxs-lookup"><span data-stu-id="a358d-123">The following table describes the date and time fields.</span></span>  
  
|<span data-ttu-id="a358d-124">运算符</span><span class="sxs-lookup"><span data-stu-id="a358d-124">Operator</span></span>|<span data-ttu-id="a358d-125">Description</span><span class="sxs-lookup"><span data-stu-id="a358d-125">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="a358d-126">**At**</span><span class="sxs-lookup"><span data-stu-id="a358d-126">**At**</span></span>|<span data-ttu-id="a358d-127">指定完全匹配。</span><span class="sxs-lookup"><span data-stu-id="a358d-127">Specifies an exact match.</span></span> <span data-ttu-id="a358d-128">等效于布尔等于 （=） 操作。</span><span class="sxs-lookup"><span data-stu-id="a358d-128">Equivalent to a Boolean Equals (=) operation.</span></span> <span data-ttu-id="a358d-129">**注意：** 如果选择**在**运算符指定该门户会使用午夜作为默认值没有时间部分的日期。</span><span class="sxs-lookup"><span data-stu-id="a358d-129">**Note:**  If you select the **At** operator and specify a date with no time part the portal uses midnight as the default value.</span></span> <span data-ttu-id="a358d-130">如果这不是你的意图，使用**该位置或之前**或**符号处或紧**运算符以获取所需的结果。</span><span class="sxs-lookup"><span data-stu-id="a358d-130">If this is not your intent, use the **At or before** or the **At or after** operators to obtain the desired results.</span></span>|  
|<span data-ttu-id="a358d-131">**晚于**</span><span class="sxs-lookup"><span data-stu-id="a358d-131">**On or before**</span></span>|<span data-ttu-id="a358d-132">指定匹配的事务或早于指定日期。</span><span class="sxs-lookup"><span data-stu-id="a358d-132">Specifies that only transactions on or before the specified date are matched.</span></span> <span data-ttu-id="a358d-133">等效于布尔值小于或等于 （≤） 运算。</span><span class="sxs-lookup"><span data-stu-id="a358d-133">Equivalent to a Boolean less than or equals (≤) operation.</span></span>|  
|<span data-ttu-id="a358d-134">**等于或晚于**</span><span class="sxs-lookup"><span data-stu-id="a358d-134">**On or after**</span></span>|<span data-ttu-id="a358d-135">指定匹配的唯一事务或晚于指定日期。</span><span class="sxs-lookup"><span data-stu-id="a358d-135">Specifies that only transactions on or after the specified date are matched.</span></span> <span data-ttu-id="a358d-136">等效于布尔值大于或等于 （≥） 运算。</span><span class="sxs-lookup"><span data-stu-id="a358d-136">Equivalent to a Boolean greater than or equals (≥) operation.</span></span>|  
|<span data-ttu-id="a358d-137">**早于**</span><span class="sxs-lookup"><span data-stu-id="a358d-137">**Before**</span></span>|<span data-ttu-id="a358d-138">指定匹配的只是早于指定日期的事务。</span><span class="sxs-lookup"><span data-stu-id="a358d-138">Specifies that only transactions before the specified date are matched.</span></span> <span data-ttu-id="a358d-139">等效于布尔值小于 (<) 操作。</span><span class="sxs-lookup"><span data-stu-id="a358d-139">Equivalent to a Boolean less than (<) operation.</span></span>|  
|<span data-ttu-id="a358d-140">**After**</span><span class="sxs-lookup"><span data-stu-id="a358d-140">**After**</span></span>|<span data-ttu-id="a358d-141">指定匹配晚于指定日期的唯一事务。</span><span class="sxs-lookup"><span data-stu-id="a358d-141">Specifies that only transactions after the specified date are matched.</span></span> <span data-ttu-id="a358d-142">等效于布尔大于 (>) 运算。</span><span class="sxs-lookup"><span data-stu-id="a358d-142">Equivalent to a Boolean greater than (>) operation.</span></span>|  
|<span data-ttu-id="a358d-143">**在过去**</span><span class="sxs-lookup"><span data-stu-id="a358d-143">**In the last**</span></span>|<span data-ttu-id="a358d-144">指定匹配的唯一发生的事务。 在以前指定的期限。</span><span class="sxs-lookup"><span data-stu-id="a358d-144">Specifies that only transactions that occurred in the previous specified time period are matched.</span></span> <span data-ttu-id="a358d-145">可以以秒、 分钟、 小时或天指定时间段。</span><span class="sxs-lookup"><span data-stu-id="a358d-145">The time period can be specified in seconds, minutes, hours, or days.</span></span>|  
|<span data-ttu-id="a358d-146">**早于最后**</span><span class="sxs-lookup"><span data-stu-id="a358d-146">**Before the last**</span></span>|<span data-ttu-id="a358d-147">指定匹配在指定的时间段之前发生的事务。</span><span class="sxs-lookup"><span data-stu-id="a358d-147">Specifies that only transactions that occurred prior to the specified time period are matched.</span></span> <span data-ttu-id="a358d-148">可以以秒、 分钟、 小时或天指定时间段。</span><span class="sxs-lookup"><span data-stu-id="a358d-148">The time period can be specified in seconds, minutes, hours, or days.</span></span>|  
|<span data-ttu-id="a358d-149">**为空**</span><span class="sxs-lookup"><span data-stu-id="a358d-149">**Is empty**</span></span>|<span data-ttu-id="a358d-150">指定返回的唯一事务为其业务数据项不包含数据 （数据字段的值为 NULL）。</span><span class="sxs-lookup"><span data-stu-id="a358d-150">Specifies that only transactions for which the business data item contains no data (the value of data field is NULL) are returned.</span></span>|  
|<span data-ttu-id="a358d-151">**不为空**</span><span class="sxs-lookup"><span data-stu-id="a358d-151">**Is not empty**</span></span>|<span data-ttu-id="a358d-152">指定返回业务数据项包含的数据 （数据字段的值不为 NULL） 的事务。</span><span class="sxs-lookup"><span data-stu-id="a358d-152">Specifies that only transactions for which the business data item contains data (the value of data field is not NULL) are returned.</span></span>|  
  
 <span data-ttu-id="a358d-153">下表描述了数值的字段和持续时间字段。</span><span class="sxs-lookup"><span data-stu-id="a358d-153">The following table describes the numeric fields and the duration fields.</span></span> <span data-ttu-id="a358d-154">数值字段包含如数量或货币金额的数据。</span><span class="sxs-lookup"><span data-stu-id="a358d-154">Numeric fields contain data such as quantities or currency amounts.</span></span> <span data-ttu-id="a358d-155">持续时间字段指定的时间段。</span><span class="sxs-lookup"><span data-stu-id="a358d-155">Duration fields specify a time period.</span></span>  
  
|<span data-ttu-id="a358d-156">运算符</span><span class="sxs-lookup"><span data-stu-id="a358d-156">Operator</span></span>|<span data-ttu-id="a358d-157">Description</span><span class="sxs-lookup"><span data-stu-id="a358d-157">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="a358d-158">**等于**</span><span class="sxs-lookup"><span data-stu-id="a358d-158">**Equals**</span></span>|<span data-ttu-id="a358d-159">指定完全匹配。</span><span class="sxs-lookup"><span data-stu-id="a358d-159">Specifies an exact match.</span></span> <span data-ttu-id="a358d-160">等效于布尔等于 （=） 操作。</span><span class="sxs-lookup"><span data-stu-id="a358d-160">Equivalent to a Boolean Equals (=) operation.</span></span>|  
|<span data-ttu-id="a358d-161">**大于**</span><span class="sxs-lookup"><span data-stu-id="a358d-161">**Greater than**</span></span>|<span data-ttu-id="a358d-162">指定完全匹配。</span><span class="sxs-lookup"><span data-stu-id="a358d-162">Specifies an exact match.</span></span> <span data-ttu-id="a358d-163">等效于布尔大于 (>) 操作。</span><span class="sxs-lookup"><span data-stu-id="a358d-163">Equivalent to a Boolean Greater Than (>) operation.</span></span>|  
|<span data-ttu-id="a358d-164">**大于或等于**</span><span class="sxs-lookup"><span data-stu-id="a358d-164">**Greater than or equal**</span></span>|<span data-ttu-id="a358d-165">指定完全匹配。</span><span class="sxs-lookup"><span data-stu-id="a358d-165">Specifies an exact match.</span></span> <span data-ttu-id="a358d-166">等效于布尔值大于或等于 （≥） 操作。</span><span class="sxs-lookup"><span data-stu-id="a358d-166">Equivalent to a Boolean Greater Than or Equals (≥) operation.</span></span>|  
|<span data-ttu-id="a358d-167">**小于**</span><span class="sxs-lookup"><span data-stu-id="a358d-167">**Less than**</span></span>|<span data-ttu-id="a358d-168">指定完全匹配。</span><span class="sxs-lookup"><span data-stu-id="a358d-168">Specifies an exact match.</span></span> <span data-ttu-id="a358d-169">等效于布尔小于 (<) 操作。</span><span class="sxs-lookup"><span data-stu-id="a358d-169">Equivalent to a Boolean Less Than (<) operation.</span></span>|  
|<span data-ttu-id="a358d-170">**小于或等于**</span><span class="sxs-lookup"><span data-stu-id="a358d-170">**Less than or equal**</span></span>|<span data-ttu-id="a358d-171">指定完全匹配。</span><span class="sxs-lookup"><span data-stu-id="a358d-171">Specifies an exact match.</span></span> <span data-ttu-id="a358d-172">等效于小于于或等于 （≤） 运算。</span><span class="sxs-lookup"><span data-stu-id="a358d-172">Equivalent to a Less Than or Equals (≤) operation.</span></span>|  
|<span data-ttu-id="a358d-173">**不等于**</span><span class="sxs-lookup"><span data-stu-id="a358d-173">**Not Equal**</span></span>|<span data-ttu-id="a358d-174">指定完全匹配。</span><span class="sxs-lookup"><span data-stu-id="a358d-174">Specifies an exact match.</span></span> <span data-ttu-id="a358d-175">等效于不等于 （≠） 操作。</span><span class="sxs-lookup"><span data-stu-id="a358d-175">Equivalent to a Not Equals (≠) operation.</span></span>|  
|<span data-ttu-id="a358d-176">**为空**</span><span class="sxs-lookup"><span data-stu-id="a358d-176">**Is empty**</span></span>|<span data-ttu-id="a358d-177">指定返回的唯一事务为其业务数据项不包含数据 （数据字段的值为 NULL）。</span><span class="sxs-lookup"><span data-stu-id="a358d-177">Specifies that only transactions for which the business data item contains no data (the value of data field is NULL) are returned.</span></span>|  
|<span data-ttu-id="a358d-178">**不为空**</span><span class="sxs-lookup"><span data-stu-id="a358d-178">**Is not empty**</span></span>|<span data-ttu-id="a358d-179">指定返回业务数据项包含的数据 （数据字段的值不为 NULL） 的事务。</span><span class="sxs-lookup"><span data-stu-id="a358d-179">Specifies that only transactions for which the business data item contains data (the value of data field is not NULL) are returned.</span></span>|  
  
 <span data-ttu-id="a358d-180">下表描述的文本字段。</span><span class="sxs-lookup"><span data-stu-id="a358d-180">The following table describes the text fields.</span></span>  
  
|<span data-ttu-id="a358d-181">运算符</span><span class="sxs-lookup"><span data-stu-id="a358d-181">Operator</span></span>|<span data-ttu-id="a358d-182">Description</span><span class="sxs-lookup"><span data-stu-id="a358d-182">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="a358d-183">**正是**</span><span class="sxs-lookup"><span data-stu-id="a358d-183">**Is Exactly**</span></span>|<span data-ttu-id="a358d-184">指定完全匹配。</span><span class="sxs-lookup"><span data-stu-id="a358d-184">Specifies an exact match.</span></span> <span data-ttu-id="a358d-185">等效于布尔等于 （=） 操作。</span><span class="sxs-lookup"><span data-stu-id="a358d-185">Equivalent to a Boolean Equals (=) operation.</span></span>|  
|<span data-ttu-id="a358d-186">**包含**</span><span class="sxs-lookup"><span data-stu-id="a358d-186">**Contains**</span></span>|<span data-ttu-id="a358d-187">指定业务数据项中的文本包含指定的值。</span><span class="sxs-lookup"><span data-stu-id="a358d-187">Specifies that the text in the business data item contains the specified value.</span></span> <span data-ttu-id="a358d-188">这允许您执行部分匹配的数据。</span><span class="sxs-lookup"><span data-stu-id="a358d-188">This allows you to do partial matches on the data.</span></span>|  
|<span data-ttu-id="a358d-189">**不包含**</span><span class="sxs-lookup"><span data-stu-id="a358d-189">**Does not contain**</span></span>|<span data-ttu-id="a358d-190">指定业务数据项中的文本不包含指定的值。</span><span class="sxs-lookup"><span data-stu-id="a358d-190">Specifies that the text in the business data item does not contain the specified value.</span></span>|  
|<span data-ttu-id="a358d-191">**为空**</span><span class="sxs-lookup"><span data-stu-id="a358d-191">**Is empty**</span></span>|<span data-ttu-id="a358d-192">指定返回的唯一事务为其业务数据项不包含数据 （数据字段的值为 NULL）。</span><span class="sxs-lookup"><span data-stu-id="a358d-192">Specifies that only transactions for which the business data item contains no data (the value of data field is NULL) are returned.</span></span>|  
|<span data-ttu-id="a358d-193">**不为空**</span><span class="sxs-lookup"><span data-stu-id="a358d-193">**Is not empty**</span></span>|<span data-ttu-id="a358d-194">指定返回业务数据项包含的数据 （数据字段的值不为 NULL） 的事务。</span><span class="sxs-lookup"><span data-stu-id="a358d-194">Specifies that only transactions for which the business data item contains data (the value of data field is not NULL) are returned.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="a358d-195">本节内容</span><span class="sxs-lookup"><span data-stu-id="a358d-195">In This Section</span></span>  
  
-   [<span data-ttu-id="a358d-196">如何在活动搜索中创建查询</span><span class="sxs-lookup"><span data-stu-id="a358d-196">How to Create a Query in Activity Search</span></span>](../core/how-to-create-a-query-in-activity-search.md)  
  
-   [<span data-ttu-id="a358d-197">如何设置警报</span><span class="sxs-lookup"><span data-stu-id="a358d-197">How to Set an Alert</span></span>](../core/how-to-set-an-alert.md)  
  
-   [<span data-ttu-id="a358d-198">如何查看活动搜索的结果</span><span class="sxs-lookup"><span data-stu-id="a358d-198">How to View the Results of an Activity Search</span></span>](../core/how-to-view-the-results-of-an-activity-search.md)  
  
## <a name="see-also"></a><span data-ttu-id="a358d-199">请参阅</span><span class="sxs-lookup"><span data-stu-id="a358d-199">See Also</span></span>  
 [<span data-ttu-id="a358d-200">BAM 门户</span><span class="sxs-lookup"><span data-stu-id="a358d-200">BAM Portal</span></span>](../core/bam-portal.md)