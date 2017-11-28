---
title: "BAM 门户中的活动搜索 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 617461b104f3188c14bb7c5b6eb5eb0bd329693f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="activity-searches-in-the-bam-portal"></a><span data-ttu-id="8c525-102">BAM 门户中的活动搜索</span><span class="sxs-lookup"><span data-stu-id="8c525-102">Activity Searches in the BAM Portal</span></span>
<span data-ttu-id="8c525-103">您可以使用活动搜索对 BAM 数据进行搜索。搜索将基于 BAM 视图中可用的跟踪值和项，查找与指定的标准匹配的活动并显示活动，以便您可以编辑这些活动或基于它们创建警报。</span><span class="sxs-lookup"><span data-stu-id="8c525-103">An activity search allows you to perform searches against BAM data to find activities that match the criteria you specify based on tracked values and items available in a BAM view, and to display these activities so that you can edit them or create alerts based on them.</span></span>  
  
## <a name="parts-of-the-query-builder"></a><span data-ttu-id="8c525-104">查询生成器的部分</span><span class="sxs-lookup"><span data-stu-id="8c525-104">Parts of the Query Builder</span></span>  
 <span data-ttu-id="8c525-105">您可以通过选择业务数据项来为活动搜索生成查询，选择的业务数据项就是所创建的用于提取目标数据的布尔比较所基于的业务数据项。</span><span class="sxs-lookup"><span data-stu-id="8c525-105">You build queries for your activity search by selecting items of business data against which you will create Boolean comparisons to extract data of interest.</span></span> <span data-ttu-id="8c525-106">通过选择 BAM 视图从启动**我视图**门户的框架。</span><span class="sxs-lookup"><span data-stu-id="8c525-106">You start by selecting a BAM view from the **My Views** frame of the portal.</span></span> <span data-ttu-id="8c525-107">从所选视图中选择要针对其生成查询的活动。</span><span class="sxs-lookup"><span data-stu-id="8c525-107">From the selected view you select an activity on which to build the query.</span></span>  
  
 ![](../core/media/bamportalviewschooser.gif "BAMPortalViewsChooser")  
  
 <span data-ttu-id="8c525-108">在选择活动后，门户的内容框架会显示查询生成器、列选择器和结果框。</span><span class="sxs-lookup"><span data-stu-id="8c525-108">When you have selected the activity, the content frame of the portal displays the Query builder, Column Chooser, and Results boxes.</span></span> <span data-ttu-id="8c525-109">您可以打开现有查询，也可以生成新的查询。</span><span class="sxs-lookup"><span data-stu-id="8c525-109">You can open an existing query or you can build a new one.</span></span>  
  
 ![](../core/media/activitysearchquerybuilder.gif "ActivitySearchQueryBuilder")  
  
 <span data-ttu-id="8c525-110">若要生成一个新的查询，通过选择从业务的数据项目启动**业务数据**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="8c525-110">To build a new query you start by selecting a business data item from the **Business Data** drop-down list.</span></span>  
  
 ![](../core/media/activitysearchquerybuilderbusinessdatadropdown.gif "ActivitySearchQueryBuilderBusinessDataDropdown")  
  
 <span data-ttu-id="8c525-111">接下来，在“运算符”下拉列表中选择比较运算符。</span><span class="sxs-lookup"><span data-stu-id="8c525-111">Next, you select your comparison operator in the Operator drop-down list.</span></span> <span data-ttu-id="8c525-112">利用比较运算符可以精确定义查询的结果。</span><span class="sxs-lookup"><span data-stu-id="8c525-112">The comparison operator allows you to refine the results of the query.</span></span>  
  
 ![](../core/media/activitysearchcomparisonoperatordropdown.gif "ActivitySearchComparisonOperatorDropDown")  
  
 <span data-ttu-id="8c525-113">“值”下拉列表是基于业务数据项表示的数据类型的上下文相关的列表。</span><span class="sxs-lookup"><span data-stu-id="8c525-113">The Value drop-down list is context-sensitive based on the type of data represented by the business data item.</span></span> <span data-ttu-id="8c525-114">其用户界面 (UI) 会根据所允许的数据类型而更改。</span><span class="sxs-lookup"><span data-stu-id="8c525-114">The user interface (UI) changes as the type of permitted data changes.</span></span>  
  
 <span data-ttu-id="8c525-115">可以将联接子句的查询中使用和或 OR 运算符以形成更复杂的查询，通过单击**添加**按钮。</span><span class="sxs-lookup"><span data-stu-id="8c525-115">You can join clauses of the query with AND or OR operators to form more complex queries by clicking the **Add** button.</span></span>  
  
 ![](../core/media/activitysearchjoiningclauses.gif "ActivitySearchJoiningClauses")  
  
> [!NOTE]
>  <span data-ttu-id="8c525-116">不能分组子句。</span><span class="sxs-lookup"><span data-stu-id="8c525-116">You cannot group clauses.</span></span> <span data-ttu-id="8c525-117">查询是由 AND/OR 运算符联接的多个子句的简单字符串。</span><span class="sxs-lookup"><span data-stu-id="8c525-117">A query is a simple string of individual clauses joined by AND/OR operators.</span></span>  
  
 <span data-ttu-id="8c525-118">下表说明了日期和时间字段。</span><span class="sxs-lookup"><span data-stu-id="8c525-118">The following table describes the date and time fields.</span></span>  
  
|<span data-ttu-id="8c525-119">运算符</span><span class="sxs-lookup"><span data-stu-id="8c525-119">Operator</span></span>|<span data-ttu-id="8c525-120">Description</span><span class="sxs-lookup"><span data-stu-id="8c525-120">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="8c525-121">**在**</span><span class="sxs-lookup"><span data-stu-id="8c525-121">**At**</span></span>|<span data-ttu-id="8c525-122">指定完全匹配项。</span><span class="sxs-lookup"><span data-stu-id="8c525-122">Specifies an exact match.</span></span> <span data-ttu-id="8c525-123">等效于布尔运算中的等于 (=) 运算。</span><span class="sxs-lookup"><span data-stu-id="8c525-123">Equivalent to a Boolean Equals (=) operation.</span></span> <span data-ttu-id="8c525-124">**注意：**如果你选择**在**运算符和使用此门户使用的默认值为午夜没有时间部分指定一个日期。</span><span class="sxs-lookup"><span data-stu-id="8c525-124">**Note:**  If you select the **At** operator and specify a date with no time part the portal uses midnight as the default value.</span></span> <span data-ttu-id="8c525-125">如果这不是你的意图，使用**或之前**或**时或之后**运算符来获取所需的结果。</span><span class="sxs-lookup"><span data-stu-id="8c525-125">If this is not your intent, use the **At or before** or the **At or after** operators to obtain the desired results.</span></span>|  
|<span data-ttu-id="8c525-126">**指定日期或之前**</span><span class="sxs-lookup"><span data-stu-id="8c525-126">**On or before**</span></span>|<span data-ttu-id="8c525-127">指定只匹配等于或早于指定日期的事务。</span><span class="sxs-lookup"><span data-stu-id="8c525-127">Specifies that only transactions on or before the specified date are matched.</span></span> <span data-ttu-id="8c525-128">等效于一个布尔值小于或等于 （≤） 操作。</span><span class="sxs-lookup"><span data-stu-id="8c525-128">Equivalent to a Boolean less than or equals (≤) operation.</span></span>|  
|<span data-ttu-id="8c525-129">**或之后**</span><span class="sxs-lookup"><span data-stu-id="8c525-129">**On or after**</span></span>|<span data-ttu-id="8c525-130">指定只匹配等于或晚于指定日期的事务。</span><span class="sxs-lookup"><span data-stu-id="8c525-130">Specifies that only transactions on or after the specified date are matched.</span></span> <span data-ttu-id="8c525-131">等效于布尔值大于或等于 （≥） 操作。</span><span class="sxs-lookup"><span data-stu-id="8c525-131">Equivalent to a Boolean greater than or equals (≥) operation.</span></span>|  
|<span data-ttu-id="8c525-132">**早于**</span><span class="sxs-lookup"><span data-stu-id="8c525-132">**Before**</span></span>|<span data-ttu-id="8c525-133">指定只匹配早于指定日期的事务。</span><span class="sxs-lookup"><span data-stu-id="8c525-133">Specifies that only transactions before the specified date are matched.</span></span> <span data-ttu-id="8c525-134">等效于一个布尔值小于 (\<) 操作。</span><span class="sxs-lookup"><span data-stu-id="8c525-134">Equivalent to a Boolean less than (\<) operation.</span></span>|  
|<span data-ttu-id="8c525-135">**After**</span><span class="sxs-lookup"><span data-stu-id="8c525-135">**After**</span></span>|<span data-ttu-id="8c525-136">指定只匹配晚于指定日期的事务。</span><span class="sxs-lookup"><span data-stu-id="8c525-136">Specifies that only transactions after the specified date are matched.</span></span> <span data-ttu-id="8c525-137">等效于大于 (>) 的布尔操作。</span><span class="sxs-lookup"><span data-stu-id="8c525-137">Equivalent to a Boolean greater than (>) operation.</span></span>|  
|<span data-ttu-id="8c525-138">**在过去**</span><span class="sxs-lookup"><span data-stu-id="8c525-138">**In the last**</span></span>|<span data-ttu-id="8c525-139">指定只匹配在上一个指定时间段内发生的事务。</span><span class="sxs-lookup"><span data-stu-id="8c525-139">Specifies that only transactions that occurred in the previous specified time period are matched.</span></span> <span data-ttu-id="8c525-140">时间段可以按秒、分钟、小时或天指定。</span><span class="sxs-lookup"><span data-stu-id="8c525-140">The time period can be specified in seconds, minutes, hours, or days.</span></span>|  
|<span data-ttu-id="8c525-141">**最后一个之前**</span><span class="sxs-lookup"><span data-stu-id="8c525-141">**Before the last**</span></span>|<span data-ttu-id="8c525-142">指定只匹配在指定时间段以前发生的事务。</span><span class="sxs-lookup"><span data-stu-id="8c525-142">Specifies that only transactions that occurred prior to the specified time period are matched.</span></span> <span data-ttu-id="8c525-143">时间段可以按秒、分钟、小时或天指定。</span><span class="sxs-lookup"><span data-stu-id="8c525-143">The time period can be specified in seconds, minutes, hours, or days.</span></span>|  
|<span data-ttu-id="8c525-144">**为空**</span><span class="sxs-lookup"><span data-stu-id="8c525-144">**Is empty**</span></span>|<span data-ttu-id="8c525-145">指定只返回业务数据项不包含任何数据（数据字段的值为 NULL）的事务。</span><span class="sxs-lookup"><span data-stu-id="8c525-145">Specifies that only transactions for which the business data item contains no data (the value of data field is NULL) are returned.</span></span>|  
|<span data-ttu-id="8c525-146">**不为空**</span><span class="sxs-lookup"><span data-stu-id="8c525-146">**Is not empty**</span></span>|<span data-ttu-id="8c525-147">指定只返回业务数据项包含数据（数据字段的值不为 NULL）的事务。</span><span class="sxs-lookup"><span data-stu-id="8c525-147">Specifies that only transactions for which the business data item contains data (the value of data field is not NULL) are returned.</span></span>|  
  
 <span data-ttu-id="8c525-148">下表介绍数值字段和持续时间字段。</span><span class="sxs-lookup"><span data-stu-id="8c525-148">The following table describes the numeric fields and the duration fields.</span></span> <span data-ttu-id="8c525-149">数值字段包含如数量或货币金额这样的数据。</span><span class="sxs-lookup"><span data-stu-id="8c525-149">Numeric fields contain data such as quantities or currency amounts.</span></span> <span data-ttu-id="8c525-150">持续时间字段指定一个时间段。</span><span class="sxs-lookup"><span data-stu-id="8c525-150">Duration fields specify a time period.</span></span>  
  
|<span data-ttu-id="8c525-151">运算符</span><span class="sxs-lookup"><span data-stu-id="8c525-151">Operator</span></span>|<span data-ttu-id="8c525-152">Description</span><span class="sxs-lookup"><span data-stu-id="8c525-152">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="8c525-153">**等于**</span><span class="sxs-lookup"><span data-stu-id="8c525-153">**Equals**</span></span>|<span data-ttu-id="8c525-154">指定完全匹配项。</span><span class="sxs-lookup"><span data-stu-id="8c525-154">Specifies an exact match.</span></span> <span data-ttu-id="8c525-155">等效于布尔运算中的等于 (=) 运算。</span><span class="sxs-lookup"><span data-stu-id="8c525-155">Equivalent to a Boolean Equals (=) operation.</span></span>|  
|<span data-ttu-id="8c525-156">**大于**</span><span class="sxs-lookup"><span data-stu-id="8c525-156">**Greater than**</span></span>|<span data-ttu-id="8c525-157">指定完全匹配项。</span><span class="sxs-lookup"><span data-stu-id="8c525-157">Specifies an exact match.</span></span> <span data-ttu-id="8c525-158">等效于布尔大于 (>) 操作。</span><span class="sxs-lookup"><span data-stu-id="8c525-158">Equivalent to a Boolean Greater Than (>) operation.</span></span>|  
|<span data-ttu-id="8c525-159">**大于或等于**</span><span class="sxs-lookup"><span data-stu-id="8c525-159">**Greater than or equal**</span></span>|<span data-ttu-id="8c525-160">指定完全匹配项。</span><span class="sxs-lookup"><span data-stu-id="8c525-160">Specifies an exact match.</span></span> <span data-ttu-id="8c525-161">等效于 boolean 类型的值大于或等于 （≥） 操作。</span><span class="sxs-lookup"><span data-stu-id="8c525-161">Equivalent to a Boolean Greater Than or Equals (≥) operation.</span></span>|  
|<span data-ttu-id="8c525-162">**小于**</span><span class="sxs-lookup"><span data-stu-id="8c525-162">**Less than**</span></span>|<span data-ttu-id="8c525-163">指定完全匹配项。</span><span class="sxs-lookup"><span data-stu-id="8c525-163">Specifies an exact match.</span></span> <span data-ttu-id="8c525-164">等效于布尔小于 (<) 操作。</span><span class="sxs-lookup"><span data-stu-id="8c525-164">Equivalent to a Boolean Less Than (<) operation.</span></span>|  
|<span data-ttu-id="8c525-165">**小于或等于**</span><span class="sxs-lookup"><span data-stu-id="8c525-165">**Less than or equal**</span></span>|<span data-ttu-id="8c525-166">指定完全匹配项。</span><span class="sxs-lookup"><span data-stu-id="8c525-166">Specifies an exact match.</span></span> <span data-ttu-id="8c525-167">等效于早于或等于 （≤） 操作。</span><span class="sxs-lookup"><span data-stu-id="8c525-167">Equivalent to a Less Than or Equals (≤) operation.</span></span>|  
|<span data-ttu-id="8c525-168">**不等于**</span><span class="sxs-lookup"><span data-stu-id="8c525-168">**Not Equal**</span></span>|<span data-ttu-id="8c525-169">指定完全匹配项。</span><span class="sxs-lookup"><span data-stu-id="8c525-169">Specifies an exact match.</span></span> <span data-ttu-id="8c525-170">等效于不等于 （≠） 操作。</span><span class="sxs-lookup"><span data-stu-id="8c525-170">Equivalent to a Not Equals (≠) operation.</span></span>|  
|<span data-ttu-id="8c525-171">**为空**</span><span class="sxs-lookup"><span data-stu-id="8c525-171">**Is empty**</span></span>|<span data-ttu-id="8c525-172">指定只返回业务数据项不包含任何数据（数据字段的值为 NULL）的事务。</span><span class="sxs-lookup"><span data-stu-id="8c525-172">Specifies that only transactions for which the business data item contains no data (the value of data field is NULL) are returned.</span></span>|  
|<span data-ttu-id="8c525-173">**不为空**</span><span class="sxs-lookup"><span data-stu-id="8c525-173">**Is not empty**</span></span>|<span data-ttu-id="8c525-174">指定只返回业务数据项包含数据（数据字段的值不为 NULL）的事务。</span><span class="sxs-lookup"><span data-stu-id="8c525-174">Specifies that only transactions for which the business data item contains data (the value of data field is not NULL) are returned.</span></span>|  
  
 <span data-ttu-id="8c525-175">下表说明文本字段。</span><span class="sxs-lookup"><span data-stu-id="8c525-175">The following table describes the text fields.</span></span>  
  
|<span data-ttu-id="8c525-176">运算符</span><span class="sxs-lookup"><span data-stu-id="8c525-176">Operator</span></span>|<span data-ttu-id="8c525-177">Description</span><span class="sxs-lookup"><span data-stu-id="8c525-177">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="8c525-178">**正是**</span><span class="sxs-lookup"><span data-stu-id="8c525-178">**Is Exactly**</span></span>|<span data-ttu-id="8c525-179">指定完全匹配项。</span><span class="sxs-lookup"><span data-stu-id="8c525-179">Specifies an exact match.</span></span> <span data-ttu-id="8c525-180">等效于布尔运算中的等于 (=) 运算。</span><span class="sxs-lookup"><span data-stu-id="8c525-180">Equivalent to a Boolean Equals (=) operation.</span></span>|  
|<span data-ttu-id="8c525-181">**包含**</span><span class="sxs-lookup"><span data-stu-id="8c525-181">**Contains**</span></span>|<span data-ttu-id="8c525-182">指定业务数据项中的文本包含指定的值。</span><span class="sxs-lookup"><span data-stu-id="8c525-182">Specifies that the text in the business data item contains the specified value.</span></span> <span data-ttu-id="8c525-183">这允许对数据执行部分匹配。</span><span class="sxs-lookup"><span data-stu-id="8c525-183">This allows you to do partial matches on the data.</span></span>|  
|<span data-ttu-id="8c525-184">**不包含**</span><span class="sxs-lookup"><span data-stu-id="8c525-184">**Does not contain**</span></span>|<span data-ttu-id="8c525-185">指定业务数据项中的文本不包含指定的值。</span><span class="sxs-lookup"><span data-stu-id="8c525-185">Specifies that the text in the business data item does not contain the specified value.</span></span>|  
|<span data-ttu-id="8c525-186">**为空**</span><span class="sxs-lookup"><span data-stu-id="8c525-186">**Is empty**</span></span>|<span data-ttu-id="8c525-187">指定只返回业务数据项不包含任何数据（数据字段的值为 NULL）的事务。</span><span class="sxs-lookup"><span data-stu-id="8c525-187">Specifies that only transactions for which the business data item contains no data (the value of data field is NULL) are returned.</span></span>|  
|<span data-ttu-id="8c525-188">**不为空**</span><span class="sxs-lookup"><span data-stu-id="8c525-188">**Is not empty**</span></span>|<span data-ttu-id="8c525-189">指定只返回业务数据项包含数据（数据字段的值不为 NULL）的事务。</span><span class="sxs-lookup"><span data-stu-id="8c525-189">Specifies that only transactions for which the business data item contains data (the value of data field is not NULL) are returned.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="8c525-190">本节内容</span><span class="sxs-lookup"><span data-stu-id="8c525-190">In This Section</span></span>  
  
-   [<span data-ttu-id="8c525-191">如何创建活动搜索查询</span><span class="sxs-lookup"><span data-stu-id="8c525-191">How to Create a Query in Activity Search</span></span>](../core/how-to-create-a-query-in-activity-search.md)  
  
-   [<span data-ttu-id="8c525-192">如何设置警报</span><span class="sxs-lookup"><span data-stu-id="8c525-192">How to Set an Alert</span></span>](../core/how-to-set-an-alert.md)  
  
-   [<span data-ttu-id="8c525-193">如何查看活动搜索的结果</span><span class="sxs-lookup"><span data-stu-id="8c525-193">How to View the Results of an Activity Search</span></span>](../core/how-to-view-the-results-of-an-activity-search.md)  
  
## <a name="see-also"></a><span data-ttu-id="8c525-194">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8c525-194">See Also</span></span>  
 [<span data-ttu-id="8c525-195">BAM 门户</span><span class="sxs-lookup"><span data-stu-id="8c525-195">BAM Portal</span></span>](../core/bam-portal.md)