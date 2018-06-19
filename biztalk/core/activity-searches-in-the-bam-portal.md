---
title: BAM 门户中的活动搜索 |Microsoft 文档
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
ms.openlocfilehash: 723848f61294cc710bd2292758383cf674093265
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966595"
---
# <a name="activity-searches-in-the-bam-portal"></a><span data-ttu-id="7184a-102">BAM 门户中的活动搜索</span><span class="sxs-lookup"><span data-stu-id="7184a-102">Activity Searches in the BAM Portal</span></span>
<span data-ttu-id="7184a-103">您可以使用活动搜索对 BAM 数据进行搜索。搜索将基于 BAM 视图中可用的跟踪值和项，查找与指定的标准匹配的活动并显示活动，以便您可以编辑这些活动或基于它们创建警报。</span><span class="sxs-lookup"><span data-stu-id="7184a-103">An activity search allows you to perform searches against BAM data to find activities that match the criteria you specify based on tracked values and items available in a BAM view, and to display these activities so that you can edit them or create alerts based on them.</span></span>  
  
## <a name="parts-of-the-query-builder"></a><span data-ttu-id="7184a-104">查询生成器的部分</span><span class="sxs-lookup"><span data-stu-id="7184a-104">Parts of the Query Builder</span></span>  
 <span data-ttu-id="7184a-105">您可以通过选择业务数据项来为活动搜索生成查询，选择的业务数据项就是所创建的用于提取目标数据的布尔比较所基于的业务数据项。</span><span class="sxs-lookup"><span data-stu-id="7184a-105">You build queries for your activity search by selecting items of business data against which you will create Boolean comparisons to extract data of interest.</span></span> <span data-ttu-id="7184a-106">通过选择 BAM 视图从启动**我视图**门户的框架。</span><span class="sxs-lookup"><span data-stu-id="7184a-106">You start by selecting a BAM view from the **My Views** frame of the portal.</span></span> <span data-ttu-id="7184a-107">从所选视图中选择要针对其生成查询的活动。</span><span class="sxs-lookup"><span data-stu-id="7184a-107">From the selected view you select an activity on which to build the query.</span></span>  
  
 <span data-ttu-id="7184a-108">![](../core/media/bamportalviewschooser.gif "BAMPortalViewsChooser")</span><span class="sxs-lookup"><span data-stu-id="7184a-108">![](../core/media/bamportalviewschooser.gif "BAMPortalViewsChooser")</span></span>  
  
 <span data-ttu-id="7184a-109">在选择活动后，门户的内容框架会显示查询生成器、列选择器和结果框。</span><span class="sxs-lookup"><span data-stu-id="7184a-109">When you have selected the activity, the content frame of the portal displays the Query builder, Column Chooser, and Results boxes.</span></span> <span data-ttu-id="7184a-110">您可以打开现有查询，也可以生成新的查询。</span><span class="sxs-lookup"><span data-stu-id="7184a-110">You can open an existing query or you can build a new one.</span></span>  
  
 <span data-ttu-id="7184a-111">![](../core/media/activitysearchquerybuilder.gif "ActivitySearchQueryBuilder")</span><span class="sxs-lookup"><span data-stu-id="7184a-111">![](../core/media/activitysearchquerybuilder.gif "ActivitySearchQueryBuilder")</span></span>  
  
 <span data-ttu-id="7184a-112">若要生成一个新的查询，通过选择从业务的数据项目启动**业务数据**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="7184a-112">To build a new query you start by selecting a business data item from the **Business Data** drop-down list.</span></span>  
  
 <span data-ttu-id="7184a-113">![](../core/media/activitysearchquerybuilderbusinessdatadropdown.gif "ActivitySearchQueryBuilderBusinessDataDropdown")</span><span class="sxs-lookup"><span data-stu-id="7184a-113">![](../core/media/activitysearchquerybuilderbusinessdatadropdown.gif "ActivitySearchQueryBuilderBusinessDataDropdown")</span></span>  
  
 <span data-ttu-id="7184a-114">接下来，在“运算符”下拉列表中选择比较运算符。</span><span class="sxs-lookup"><span data-stu-id="7184a-114">Next, you select your comparison operator in the Operator drop-down list.</span></span> <span data-ttu-id="7184a-115">利用比较运算符可以精确定义查询的结果。</span><span class="sxs-lookup"><span data-stu-id="7184a-115">The comparison operator allows you to refine the results of the query.</span></span>  
  
 <span data-ttu-id="7184a-116">![](../core/media/activitysearchcomparisonoperatordropdown.gif "ActivitySearchComparisonOperatorDropDown")</span><span class="sxs-lookup"><span data-stu-id="7184a-116">![](../core/media/activitysearchcomparisonoperatordropdown.gif "ActivitySearchComparisonOperatorDropDown")</span></span>  
  
 <span data-ttu-id="7184a-117">“值”下拉列表是基于业务数据项表示的数据类型的上下文相关的列表。</span><span class="sxs-lookup"><span data-stu-id="7184a-117">The Value drop-down list is context-sensitive based on the type of data represented by the business data item.</span></span> <span data-ttu-id="7184a-118">其用户界面 (UI) 会根据所允许的数据类型而更改。</span><span class="sxs-lookup"><span data-stu-id="7184a-118">The user interface (UI) changes as the type of permitted data changes.</span></span>  
  
 <span data-ttu-id="7184a-119">可以将联接子句的查询中使用和或 OR 运算符以形成更复杂的查询，通过单击**添加**按钮。</span><span class="sxs-lookup"><span data-stu-id="7184a-119">You can join clauses of the query with AND or OR operators to form more complex queries by clicking the **Add** button.</span></span>  
  
 <span data-ttu-id="7184a-120">![](../core/media/activitysearchjoiningclauses.gif "ActivitySearchJoiningClauses")</span><span class="sxs-lookup"><span data-stu-id="7184a-120">![](../core/media/activitysearchjoiningclauses.gif "ActivitySearchJoiningClauses")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7184a-121">不能分组子句。</span><span class="sxs-lookup"><span data-stu-id="7184a-121">You cannot group clauses.</span></span> <span data-ttu-id="7184a-122">查询是由 AND/OR 运算符联接的多个子句的简单字符串。</span><span class="sxs-lookup"><span data-stu-id="7184a-122">A query is a simple string of individual clauses joined by AND/OR operators.</span></span>  
  
 <span data-ttu-id="7184a-123">下表说明了日期和时间字段。</span><span class="sxs-lookup"><span data-stu-id="7184a-123">The following table describes the date and time fields.</span></span>  
  
|<span data-ttu-id="7184a-124">运算符</span><span class="sxs-lookup"><span data-stu-id="7184a-124">Operator</span></span>|<span data-ttu-id="7184a-125">Description</span><span class="sxs-lookup"><span data-stu-id="7184a-125">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="7184a-126">**在**</span><span class="sxs-lookup"><span data-stu-id="7184a-126">**At**</span></span>|<span data-ttu-id="7184a-127">指定完全匹配项。</span><span class="sxs-lookup"><span data-stu-id="7184a-127">Specifies an exact match.</span></span> <span data-ttu-id="7184a-128">等效于布尔运算中的等于 (=) 运算。</span><span class="sxs-lookup"><span data-stu-id="7184a-128">Equivalent to a Boolean Equals (=) operation.</span></span> <span data-ttu-id="7184a-129">**注意：** 如果你选择**在**运算符和使用此门户使用的默认值为午夜没有时间部分指定一个日期。</span><span class="sxs-lookup"><span data-stu-id="7184a-129">**Note:**  If you select the **At** operator and specify a date with no time part the portal uses midnight as the default value.</span></span> <span data-ttu-id="7184a-130">如果这不是你的意图，使用**或之前**或**时或之后**运算符来获取所需的结果。</span><span class="sxs-lookup"><span data-stu-id="7184a-130">If this is not your intent, use the **At or before** or the **At or after** operators to obtain the desired results.</span></span>|  
|<span data-ttu-id="7184a-131">**指定日期或之前**</span><span class="sxs-lookup"><span data-stu-id="7184a-131">**On or before**</span></span>|<span data-ttu-id="7184a-132">指定只匹配等于或早于指定日期的事务。</span><span class="sxs-lookup"><span data-stu-id="7184a-132">Specifies that only transactions on or before the specified date are matched.</span></span> <span data-ttu-id="7184a-133">等效于一个布尔值小于或等于 （≤） 操作。</span><span class="sxs-lookup"><span data-stu-id="7184a-133">Equivalent to a Boolean less than or equals (≤) operation.</span></span>|  
|<span data-ttu-id="7184a-134">**或之后**</span><span class="sxs-lookup"><span data-stu-id="7184a-134">**On or after**</span></span>|<span data-ttu-id="7184a-135">指定只匹配等于或晚于指定日期的事务。</span><span class="sxs-lookup"><span data-stu-id="7184a-135">Specifies that only transactions on or after the specified date are matched.</span></span> <span data-ttu-id="7184a-136">等效于布尔值大于或等于 （≥） 操作。</span><span class="sxs-lookup"><span data-stu-id="7184a-136">Equivalent to a Boolean greater than or equals (≥) operation.</span></span>|  
|<span data-ttu-id="7184a-137">**早于**</span><span class="sxs-lookup"><span data-stu-id="7184a-137">**Before**</span></span>|<span data-ttu-id="7184a-138">指定只匹配早于指定日期的事务。</span><span class="sxs-lookup"><span data-stu-id="7184a-138">Specifies that only transactions before the specified date are matched.</span></span> <span data-ttu-id="7184a-139">等效于一个布尔值小于 (<) 操作。</span><span class="sxs-lookup"><span data-stu-id="7184a-139">Equivalent to a Boolean less than (<) operation.</span></span>|  
|<span data-ttu-id="7184a-140">**After**</span><span class="sxs-lookup"><span data-stu-id="7184a-140">**After**</span></span>|<span data-ttu-id="7184a-141">指定只匹配晚于指定日期的事务。</span><span class="sxs-lookup"><span data-stu-id="7184a-141">Specifies that only transactions after the specified date are matched.</span></span> <span data-ttu-id="7184a-142">等效于大于 (>) 的布尔操作。</span><span class="sxs-lookup"><span data-stu-id="7184a-142">Equivalent to a Boolean greater than (>) operation.</span></span>|  
|<span data-ttu-id="7184a-143">**在过去**</span><span class="sxs-lookup"><span data-stu-id="7184a-143">**In the last**</span></span>|<span data-ttu-id="7184a-144">指定只匹配在上一个指定时间段内发生的事务。</span><span class="sxs-lookup"><span data-stu-id="7184a-144">Specifies that only transactions that occurred in the previous specified time period are matched.</span></span> <span data-ttu-id="7184a-145">时间段可以按秒、分钟、小时或天指定。</span><span class="sxs-lookup"><span data-stu-id="7184a-145">The time period can be specified in seconds, minutes, hours, or days.</span></span>|  
|<span data-ttu-id="7184a-146">**最后一个之前**</span><span class="sxs-lookup"><span data-stu-id="7184a-146">**Before the last**</span></span>|<span data-ttu-id="7184a-147">指定只匹配在指定时间段以前发生的事务。</span><span class="sxs-lookup"><span data-stu-id="7184a-147">Specifies that only transactions that occurred prior to the specified time period are matched.</span></span> <span data-ttu-id="7184a-148">时间段可以按秒、分钟、小时或天指定。</span><span class="sxs-lookup"><span data-stu-id="7184a-148">The time period can be specified in seconds, minutes, hours, or days.</span></span>|  
|<span data-ttu-id="7184a-149">**为空**</span><span class="sxs-lookup"><span data-stu-id="7184a-149">**Is empty**</span></span>|<span data-ttu-id="7184a-150">指定只返回业务数据项不包含任何数据（数据字段的值为 NULL）的事务。</span><span class="sxs-lookup"><span data-stu-id="7184a-150">Specifies that only transactions for which the business data item contains no data (the value of data field is NULL) are returned.</span></span>|  
|<span data-ttu-id="7184a-151">**不为空**</span><span class="sxs-lookup"><span data-stu-id="7184a-151">**Is not empty**</span></span>|<span data-ttu-id="7184a-152">指定只返回业务数据项包含数据（数据字段的值不为 NULL）的事务。</span><span class="sxs-lookup"><span data-stu-id="7184a-152">Specifies that only transactions for which the business data item contains data (the value of data field is not NULL) are returned.</span></span>|  
  
 <span data-ttu-id="7184a-153">下表介绍数值字段和持续时间字段。</span><span class="sxs-lookup"><span data-stu-id="7184a-153">The following table describes the numeric fields and the duration fields.</span></span> <span data-ttu-id="7184a-154">数值字段包含如数量或货币金额这样的数据。</span><span class="sxs-lookup"><span data-stu-id="7184a-154">Numeric fields contain data such as quantities or currency amounts.</span></span> <span data-ttu-id="7184a-155">持续时间字段指定一个时间段。</span><span class="sxs-lookup"><span data-stu-id="7184a-155">Duration fields specify a time period.</span></span>  
  
|<span data-ttu-id="7184a-156">运算符</span><span class="sxs-lookup"><span data-stu-id="7184a-156">Operator</span></span>|<span data-ttu-id="7184a-157">Description</span><span class="sxs-lookup"><span data-stu-id="7184a-157">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="7184a-158">**等于**</span><span class="sxs-lookup"><span data-stu-id="7184a-158">**Equals**</span></span>|<span data-ttu-id="7184a-159">指定完全匹配项。</span><span class="sxs-lookup"><span data-stu-id="7184a-159">Specifies an exact match.</span></span> <span data-ttu-id="7184a-160">等效于布尔运算中的等于 (=) 运算。</span><span class="sxs-lookup"><span data-stu-id="7184a-160">Equivalent to a Boolean Equals (=) operation.</span></span>|  
|<span data-ttu-id="7184a-161">**大于**</span><span class="sxs-lookup"><span data-stu-id="7184a-161">**Greater than**</span></span>|<span data-ttu-id="7184a-162">指定完全匹配项。</span><span class="sxs-lookup"><span data-stu-id="7184a-162">Specifies an exact match.</span></span> <span data-ttu-id="7184a-163">等效于布尔大于 (>) 操作。</span><span class="sxs-lookup"><span data-stu-id="7184a-163">Equivalent to a Boolean Greater Than (>) operation.</span></span>|  
|<span data-ttu-id="7184a-164">**大于或等于**</span><span class="sxs-lookup"><span data-stu-id="7184a-164">**Greater than or equal**</span></span>|<span data-ttu-id="7184a-165">指定完全匹配项。</span><span class="sxs-lookup"><span data-stu-id="7184a-165">Specifies an exact match.</span></span> <span data-ttu-id="7184a-166">等效于 boolean 类型的值大于或等于 （≥） 操作。</span><span class="sxs-lookup"><span data-stu-id="7184a-166">Equivalent to a Boolean Greater Than or Equals (≥) operation.</span></span>|  
|<span data-ttu-id="7184a-167">**小于**</span><span class="sxs-lookup"><span data-stu-id="7184a-167">**Less than**</span></span>|<span data-ttu-id="7184a-168">指定完全匹配项。</span><span class="sxs-lookup"><span data-stu-id="7184a-168">Specifies an exact match.</span></span> <span data-ttu-id="7184a-169">等效于布尔小于 (<) 操作。</span><span class="sxs-lookup"><span data-stu-id="7184a-169">Equivalent to a Boolean Less Than (<) operation.</span></span>|  
|<span data-ttu-id="7184a-170">**小于或等于**</span><span class="sxs-lookup"><span data-stu-id="7184a-170">**Less than or equal**</span></span>|<span data-ttu-id="7184a-171">指定完全匹配项。</span><span class="sxs-lookup"><span data-stu-id="7184a-171">Specifies an exact match.</span></span> <span data-ttu-id="7184a-172">等效于早于或等于 （≤） 操作。</span><span class="sxs-lookup"><span data-stu-id="7184a-172">Equivalent to a Less Than or Equals (≤) operation.</span></span>|  
|<span data-ttu-id="7184a-173">**不等于**</span><span class="sxs-lookup"><span data-stu-id="7184a-173">**Not Equal**</span></span>|<span data-ttu-id="7184a-174">指定完全匹配项。</span><span class="sxs-lookup"><span data-stu-id="7184a-174">Specifies an exact match.</span></span> <span data-ttu-id="7184a-175">等效于不等于 （≠） 操作。</span><span class="sxs-lookup"><span data-stu-id="7184a-175">Equivalent to a Not Equals (≠) operation.</span></span>|  
|<span data-ttu-id="7184a-176">**为空**</span><span class="sxs-lookup"><span data-stu-id="7184a-176">**Is empty**</span></span>|<span data-ttu-id="7184a-177">指定只返回业务数据项不包含任何数据（数据字段的值为 NULL）的事务。</span><span class="sxs-lookup"><span data-stu-id="7184a-177">Specifies that only transactions for which the business data item contains no data (the value of data field is NULL) are returned.</span></span>|  
|<span data-ttu-id="7184a-178">**不为空**</span><span class="sxs-lookup"><span data-stu-id="7184a-178">**Is not empty**</span></span>|<span data-ttu-id="7184a-179">指定只返回业务数据项包含数据（数据字段的值不为 NULL）的事务。</span><span class="sxs-lookup"><span data-stu-id="7184a-179">Specifies that only transactions for which the business data item contains data (the value of data field is not NULL) are returned.</span></span>|  
  
 <span data-ttu-id="7184a-180">下表说明文本字段。</span><span class="sxs-lookup"><span data-stu-id="7184a-180">The following table describes the text fields.</span></span>  
  
|<span data-ttu-id="7184a-181">运算符</span><span class="sxs-lookup"><span data-stu-id="7184a-181">Operator</span></span>|<span data-ttu-id="7184a-182">Description</span><span class="sxs-lookup"><span data-stu-id="7184a-182">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="7184a-183">**正是**</span><span class="sxs-lookup"><span data-stu-id="7184a-183">**Is Exactly**</span></span>|<span data-ttu-id="7184a-184">指定完全匹配项。</span><span class="sxs-lookup"><span data-stu-id="7184a-184">Specifies an exact match.</span></span> <span data-ttu-id="7184a-185">等效于布尔运算中的等于 (=) 运算。</span><span class="sxs-lookup"><span data-stu-id="7184a-185">Equivalent to a Boolean Equals (=) operation.</span></span>|  
|<span data-ttu-id="7184a-186">**包含**</span><span class="sxs-lookup"><span data-stu-id="7184a-186">**Contains**</span></span>|<span data-ttu-id="7184a-187">指定业务数据项中的文本包含指定的值。</span><span class="sxs-lookup"><span data-stu-id="7184a-187">Specifies that the text in the business data item contains the specified value.</span></span> <span data-ttu-id="7184a-188">这允许对数据执行部分匹配。</span><span class="sxs-lookup"><span data-stu-id="7184a-188">This allows you to do partial matches on the data.</span></span>|  
|<span data-ttu-id="7184a-189">**不包含**</span><span class="sxs-lookup"><span data-stu-id="7184a-189">**Does not contain**</span></span>|<span data-ttu-id="7184a-190">指定业务数据项中的文本不包含指定的值。</span><span class="sxs-lookup"><span data-stu-id="7184a-190">Specifies that the text in the business data item does not contain the specified value.</span></span>|  
|<span data-ttu-id="7184a-191">**为空**</span><span class="sxs-lookup"><span data-stu-id="7184a-191">**Is empty**</span></span>|<span data-ttu-id="7184a-192">指定只返回业务数据项不包含任何数据（数据字段的值为 NULL）的事务。</span><span class="sxs-lookup"><span data-stu-id="7184a-192">Specifies that only transactions for which the business data item contains no data (the value of data field is NULL) are returned.</span></span>|  
|<span data-ttu-id="7184a-193">**不为空**</span><span class="sxs-lookup"><span data-stu-id="7184a-193">**Is not empty**</span></span>|<span data-ttu-id="7184a-194">指定只返回业务数据项包含数据（数据字段的值不为 NULL）的事务。</span><span class="sxs-lookup"><span data-stu-id="7184a-194">Specifies that only transactions for which the business data item contains data (the value of data field is not NULL) are returned.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="7184a-195">本节内容</span><span class="sxs-lookup"><span data-stu-id="7184a-195">In This Section</span></span>  
  
-   [<span data-ttu-id="7184a-196">如何创建活动搜索查询</span><span class="sxs-lookup"><span data-stu-id="7184a-196">How to Create a Query in Activity Search</span></span>](../core/how-to-create-a-query-in-activity-search.md)  
  
-   [<span data-ttu-id="7184a-197">如何设置警报</span><span class="sxs-lookup"><span data-stu-id="7184a-197">How to Set an Alert</span></span>](../core/how-to-set-an-alert.md)  
  
-   [<span data-ttu-id="7184a-198">如何查看活动搜索的结果</span><span class="sxs-lookup"><span data-stu-id="7184a-198">How to View the Results of an Activity Search</span></span>](../core/how-to-view-the-results-of-an-activity-search.md)  
  
## <a name="see-also"></a><span data-ttu-id="7184a-199">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7184a-199">See Also</span></span>  
 [<span data-ttu-id="7184a-200">BAM 门户</span><span class="sxs-lookup"><span data-stu-id="7184a-200">BAM Portal</span></span>](../core/bam-portal.md)