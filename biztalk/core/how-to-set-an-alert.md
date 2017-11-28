---
title: "如何设置警报 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- alerts, creating
- Query Builder [BAM portal], creating alerts
- queries [BAM], aggregations
- Query Builder [BAM portal], activity searches
- Query Builder [BAM portal], aggregation alerts
- queries [BAM], alerts
- aggregations, alerts
ms.assetid: 8745d2c6-5bc0-4d7a-8c17-361535f5c6e6
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 774fbab86c1da1389b813f621c89f38cf0aa7656
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-an-alert"></a><span data-ttu-id="8e3d9-102">如何设置警报</span><span class="sxs-lookup"><span data-stu-id="8e3d9-102">How to Set an Alert</span></span>
<span data-ttu-id="8e3d9-103">通过将警报附加到活动搜索或钻取聚合，可设置警报。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-103">You can set an alert by attaching it to an activity search or drilling down through an aggregation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8e3d9-104">在设置查询警报之前，应先运行该查询，评估警报周期持续时间是否适合您要监视的流程。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-104">Before setting an alert on a query, you should run the query and evaluate whether the alert cycle durations are appropriate for the process you are monitoring.</span></span> <span data-ttu-id="8e3d9-105">如果周期持续时间太短，则警报条件可能只是瞬时存在，因此可能被警报系统遗漏。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-105">If the cycle duration is too short, it is possible for an alert condition to occur in a transient manner and thus be missed by the alerting system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8e3d9-106">如果在这些过程中单击后退按钮，你可能会收到以下消息:"警告： 页面已过期。"</span><span class="sxs-lookup"><span data-stu-id="8e3d9-106">If you click the back button during these procedures, you may receive the following message: "Warning: page has expired."</span></span> <span data-ttu-id="8e3d9-107">若要返回至以前的内容，请按 F5。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-107">To return to the previous content, press F5.</span></span> <span data-ttu-id="8e3d9-108">（可能需要多次按 F5。）</span><span class="sxs-lookup"><span data-stu-id="8e3d9-108">(You may have to press F5 several times.)</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8e3d9-109">在视图上创建第一个警报时，将不会显示用于该警报的数据。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-109">When you create the first alert on a view, there will be no data displayed for the alert.</span></span> <span data-ttu-id="8e3d9-110">在定义警报阶段而并未实际创建警报之前，并不会收集该时间帧的警报数据。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-110">Defining an alert does not collect alert data from the time frame before the alert was created.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8e3d9-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="8e3d9-111">Prerequisites</span></span>  
 <span data-ttu-id="8e3d9-112">以下为执行本主题中步骤的前提条件：</span><span class="sxs-lookup"><span data-stu-id="8e3d9-112">The following are prerequisites for performing the procedures in this topic:</span></span>  
  
-   <span data-ttu-id="8e3d9-113">必须具有已部署的视图。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-113">You must have a deployed view.</span></span>  
  
-   <span data-ttu-id="8e3d9-114">必须具有用于实例警报的活动搜索。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-114">You must have an activity search for an instance alert.</span></span>  
  
-   <span data-ttu-id="8e3d9-115">必须具有用于聚合警报的已填充的聚合。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-115">You must have a populated aggregation for an aggregation alert.</span></span>  
  
### <a name="to-set-an-alert-on-an-activity-search"></a><span data-ttu-id="8e3d9-116">设置有关活动搜索的警报</span><span class="sxs-lookup"><span data-stu-id="8e3d9-116">To set an alert on an activity search</span></span>  
  
1.  <span data-ttu-id="8e3d9-117">在**我视图**框架中，单击要展开的视图的任务列表中的视图。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-117">In the **My Views** frame, click a view to expand the list of tasks for the view.</span></span>  
  
2.  <span data-ttu-id="8e3d9-118">单击**活动搜索**你展开视图下的任务。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-118">Click the **Activity Search** task under the view you expanded.</span></span>  
  
3.  <span data-ttu-id="8e3d9-119">创建或打开活动搜索。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-119">Create or open an activity search.</span></span> <span data-ttu-id="8e3d9-120">有关如何执行此操作的信息，请参阅[How to Create in 活动搜索查询](../core/how-to-create-a-query-in-activity-search.md)。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-120">For information about how to do this, see [How to Create a Query in Activity Search](../core/how-to-create-a-query-in-activity-search.md).</span></span>  
  
4.  <span data-ttu-id="8e3d9-121">在 BAM 门户的内容框架中，单击**设置警报**按钮。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-121">In the content frame of the BAM portal, click the **Set Alert** button.</span></span> <span data-ttu-id="8e3d9-122">该内容框架中将加载警报创建模板。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-122">The content frame will load with the alert creation template.</span></span>  
  
5.  <span data-ttu-id="8e3d9-123">在**名称**文本框中，键入警报的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-123">In the **Name** text box, type a descriptive name for the alert.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8e3d9-124">名称限制为 100 个字符并且不能包含以下字符: ~ ！ @# $%^&amp;* （); 如果在名称中输入以下任意字符，虚线的红色边框的边框，该值指示错误。 请纠正以完成操作的文本字段。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-124">Names are limited to 100 characters and cannot contain the following characters: ~!@#$%^&amp;*();  If you enter any of these characters in a name, a dashed red border appears around the text field indicating an error that you must correct to complete the action.</span></span>  
  
6.  <span data-ttu-id="8e3d9-125">如果您不希望在此时间启用的警报，清除**警报启用**复选框。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-125">If you do not want the alert enabled at this time, clear the **Alert Enabled** check box.</span></span>  
  
7.  <span data-ttu-id="8e3d9-126">在**消息**文本框中，键入时，将触发警报传递的消息。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-126">In the **Message** text box, type the message that is delivered when the alert is triggered.</span></span>  
  
8.  <span data-ttu-id="8e3d9-127">从**优先级**下拉列表中，选择此警报的优先级。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-127">From the **Priority** drop-down list, choose the priority level for this alert.</span></span> <span data-ttu-id="8e3d9-128">优先级设置表示设置警报的问题的严重性。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-128">The priority setting indicates the severity of the issue on which the alert was set.</span></span>  
  
9. <span data-ttu-id="8e3d9-129">在**所有者**文本框中，键入此警报的所有者的别名。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-129">In the **Owners** text box, type the aliases of the owners of this alert.</span></span> <span data-ttu-id="8e3d9-130">在多个用户名之间使用分号将其隔开。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-130">Use semicolons between the names of multiple users.</span></span>  
  
10. <span data-ttu-id="8e3d9-131">在**警报安全**区域中，选择此复选框以允许其他用户看到此警报并订阅它。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-131">In the **Alert Security** area, select the check box to allow other users to see this alert and subscribe to it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8e3d9-132">可以随时在私有和公共之间切换警报安全性，即使该警报有订户，也可以进行切换。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-132">You can switch the alert security between private and public at any time; the presence of subscribers to the alert does not affect this action.</span></span> <span data-ttu-id="8e3d9-133">但是，在将警报安全性从公共切换为私有时，应该考虑该警报是否有订户。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-133">When you switch the alert security from public to private, however, you should consider whether there are any subscribers to the alert.</span></span> <span data-ttu-id="8e3d9-134">如果该警报有订户，在警报切换为私有后，他们将无法编辑订阅的警报。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-134">If there are subscribers to the alert, they will have no way to edit their subscription when the alert is made private.</span></span>  
  
11. <span data-ttu-id="8e3d9-135">在右上角的**警报详细信息**区域中，单击**保存警报**按钮。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-135">In the upper-right corner of the **Alert Details** area, click the **Save Alert** button.</span></span>  
  
### <a name="to-set-an-alert-on-an-aggregation"></a><span data-ttu-id="8e3d9-136">设置有关聚合的警报</span><span class="sxs-lookup"><span data-stu-id="8e3d9-136">To set an alert on an aggregation</span></span>  
  
1.  <span data-ttu-id="8e3d9-137">在**我视图**框架中，单击要展开的视图的任务列表中的视图。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-137">In the **My Views** frame, click a view to expand the list of tasks for the view.</span></span>  
  
2.  <span data-ttu-id="8e3d9-138">单击**聚合**任务中**我视图**下展开的视图。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-138">Click the **Aggregations** task in **My Views** under the view you expanded.</span></span>  
  
3.  <span data-ttu-id="8e3d9-139">在 BAM 门户的内容框架中，右键单击数据透视表总计列中的单元格。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-139">In the content frame of the BAM portal, right-click a cell in the totals column of the PivotTable report.</span></span> <span data-ttu-id="8e3d9-140">这时将打开上下文菜单，其中包含可用于执行聚合总计的函数。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-140">This opens a context menu with functions that are available to perform on the aggregation total.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8e3d9-141">通过展开行项目，可以对聚合总计的特定组件设置警报。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-141">You can set an alert on a specific component of the aggregation total by expanding that line item.</span></span> <span data-ttu-id="8e3d9-142">您可以以此方式展开随后的级别，直到到达要设置警报的级别。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-142">You can expand succeeding levels in this manner until you reach the level at which you want to set your alert.</span></span>  
  
4.  <span data-ttu-id="8e3d9-143">在上下文菜单的顶部，单击**创建警报**。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-143">At the top of the context menu, click **Create Alert**.</span></span> <span data-ttu-id="8e3d9-144">该内容框架中将加载警报创建模板。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-144">The content frame will load with the alert creation template.</span></span>  
  
5.  <span data-ttu-id="8e3d9-145">在**名称**文本框中，键入警报的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-145">In the **Name** text box, type a descriptive name for the alert.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8e3d9-146">名称限制为 100 个字符并且不能包含以下字符: ~ ！ @# $%^&amp;* （); 如果在名称中输入以下任意字符，虚线的红色边框的边框，该值指示错误。 请纠正以完成操作的文本字段。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-146">Names are limited to 100 characters and cannot contain the following characters: ~!@#$%^&amp;*();  If you enter any of these characters in a name, a dashed red border appears around the text field indicating an error that you must correct to complete the action.</span></span>  
  
6.  <span data-ttu-id="8e3d9-147">如果您不希望在此时间启用的警报，清除**警报启用**复选框。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-147">If you do not want the alert enabled at this time, clear the **Alert Enabled** check box.</span></span>  
  
7.  <span data-ttu-id="8e3d9-148">在**消息**文本框中，键入时，将触发警报传递的消息。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-148">In the **Message** text box, type the message that is delivered when the alert is triggered.</span></span>  
  
8.  <span data-ttu-id="8e3d9-149">从**优先级**下拉列表中，选择此警报的优先级。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-149">From the **Priority** drop-down list, choose the priority level for this alert.</span></span> <span data-ttu-id="8e3d9-150">优先级设置表示设置警报的问题的严重性。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-150">The priority setting indicates the severity of the issue on which the alert was set.</span></span>  
  
9. <span data-ttu-id="8e3d9-151">在**所有者**文本框中，键入此警报的所有者的别名。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-151">In the **Owners** text box, type the aliases of the owners of this alert.</span></span> <span data-ttu-id="8e3d9-152">在多个用户名之间使用分号将其隔开。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-152">Use semicolons between the names of multiple users.</span></span>  
  
10. <span data-ttu-id="8e3d9-153">在**阈值**区域中，选择比较条件从**计数**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-153">In the **Threshold** area, select a comparison condition from the **Count** drop-down list.</span></span>  
  
11. <span data-ttu-id="8e3d9-154">在**持续时间**文本框中，输入在其阈值的测量的时间单位数。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-154">In the **Duration** text box, enter the number of time units across which the threshold is measured.</span></span>  
  
12. <span data-ttu-id="8e3d9-155">从**持续时间**下拉列表中，选择的时间单位。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-155">From the **Duration** drop-down list, select the unit of time.</span></span>  
  
13. <span data-ttu-id="8e3d9-156">在**警报安全**区域中，选择此复选框以允许其他用户看到此警报并订阅它。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-156">In the **Alert Security** area, select the check box to allow other users to see this alert and subscribe to it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8e3d9-157">可以随时在私有和公共之间切换警报安全性，即使该警报有订户，也可以进行切换。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-157">You can switch the alert security between private and public at any time; the presence of subscribers to the alert does not affect this action.</span></span> <span data-ttu-id="8e3d9-158">但是，在将警报安全性从公共切换为私有时，应该考虑该警报是否有订户。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-158">When you switch the alert security from public to private, however, you should consider whether there are any subscribers to the alert.</span></span> <span data-ttu-id="8e3d9-159">如果该警报有订户，在警报切换为私有后，他们将无法编辑订阅的警报。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-159">If there are subscribers to the alert, they will have no way to edit their subscription when the alert is made private.</span></span>  
  
14. <span data-ttu-id="8e3d9-160">在右上角的**警报详细信息**区域中，单击**保存警报**按钮。</span><span class="sxs-lookup"><span data-stu-id="8e3d9-160">In the upper-right corner of the **Alert Details** area, click the **Save Alert** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e3d9-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8e3d9-161">See Also</span></span>  
 [<span data-ttu-id="8e3d9-162">如何创建活动搜索查询</span><span class="sxs-lookup"><span data-stu-id="8e3d9-162">How to Create a Query in Activity Search</span></span>](../core/how-to-create-a-query-in-activity-search.md)