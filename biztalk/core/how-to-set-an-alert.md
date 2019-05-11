---
title: 如何设置警报 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 116f8ac2a2fd79efec82449339732cde90a547db
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334645"
---
# <a name="how-to-set-an-alert"></a><span data-ttu-id="46f46-102">如何设置警报</span><span class="sxs-lookup"><span data-stu-id="46f46-102">How to Set an Alert</span></span>
<span data-ttu-id="46f46-103">通过将其附加到活动搜索或向下钻取聚合，可以设置警报。</span><span class="sxs-lookup"><span data-stu-id="46f46-103">You can set an alert by attaching it to an activity search or drilling down through an aggregation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="46f46-104">在查询上设置警报之前, 应运行查询并评估警报周期持续时间是否适合你监视的进程。</span><span class="sxs-lookup"><span data-stu-id="46f46-104">Before setting an alert on a query, you should run the query and evaluate whether the alert cycle durations are appropriate for the process you are monitoring.</span></span> <span data-ttu-id="46f46-105">如果周期持续时间太短，很可能出现暂时性的方式并因此被警报系统遗漏的警报条件。</span><span class="sxs-lookup"><span data-stu-id="46f46-105">If the cycle duration is too short, it is possible for an alert condition to occur in a transient manner and thus be missed by the alerting system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="46f46-106">如果在这些步骤中单击后退按钮，可能会收到以下消息："警告： 网页已过期。"</span><span class="sxs-lookup"><span data-stu-id="46f46-106">If you click the back button during these procedures, you may receive the following message: "Warning: page has expired."</span></span> <span data-ttu-id="46f46-107">若要返回到以前的内容，请按 F5。</span><span class="sxs-lookup"><span data-stu-id="46f46-107">To return to the previous content, press F5.</span></span> <span data-ttu-id="46f46-108">（您可能需要多次按 F5。）</span><span class="sxs-lookup"><span data-stu-id="46f46-108">(You may have to press F5 several times.)</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="46f46-109">在视图上创建第一个警报，将显示警报的任何数据。</span><span class="sxs-lookup"><span data-stu-id="46f46-109">When you create the first alert on a view, there will be no data displayed for the alert.</span></span> <span data-ttu-id="46f46-110">定义警报不会收集警报数据时间范围内创建警报之前。</span><span class="sxs-lookup"><span data-stu-id="46f46-110">Defining an alert does not collect alert data from the time frame before the alert was created.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="46f46-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="46f46-111">Prerequisites</span></span>  
 <span data-ttu-id="46f46-112">以下是执行本主题中的过程的先决条件：</span><span class="sxs-lookup"><span data-stu-id="46f46-112">The following are prerequisites for performing the procedures in this topic:</span></span>  
  
-   <span data-ttu-id="46f46-113">您必须具有已部署的视图。</span><span class="sxs-lookup"><span data-stu-id="46f46-113">You must have a deployed view.</span></span>  
  
-   <span data-ttu-id="46f46-114">您必须具有用于实例警报活动搜索。</span><span class="sxs-lookup"><span data-stu-id="46f46-114">You must have an activity search for an instance alert.</span></span>  
  
-   <span data-ttu-id="46f46-115">您必须具有用于聚合警报填充的聚合。</span><span class="sxs-lookup"><span data-stu-id="46f46-115">You must have a populated aggregation for an aggregation alert.</span></span>  
  
### <a name="to-set-an-alert-on-an-activity-search"></a><span data-ttu-id="46f46-116">若要设置有关活动搜索的警报</span><span class="sxs-lookup"><span data-stu-id="46f46-116">To set an alert on an activity search</span></span>  
  
1.  <span data-ttu-id="46f46-117">在中**我的视图**框架中，单击要展开的视图的任务列表的视图。</span><span class="sxs-lookup"><span data-stu-id="46f46-117">In the **My Views** frame, click a view to expand the list of tasks for the view.</span></span>  
  
2.  <span data-ttu-id="46f46-118">单击**活动搜索**已展开的视图下的任务。</span><span class="sxs-lookup"><span data-stu-id="46f46-118">Click the **Activity Search** task under the view you expanded.</span></span>  
  
3.  <span data-ttu-id="46f46-119">创建或打开活动搜索。</span><span class="sxs-lookup"><span data-stu-id="46f46-119">Create or open an activity search.</span></span> <span data-ttu-id="46f46-120">有关如何执行此操作的信息，请参阅[如何在活动搜索中创建一个查询](../core/how-to-create-a-query-in-activity-search.md)。</span><span class="sxs-lookup"><span data-stu-id="46f46-120">For information about how to do this, see [How to Create a Query in Activity Search](../core/how-to-create-a-query-in-activity-search.md).</span></span>  
  
4.  <span data-ttu-id="46f46-121">在 BAM 门户内容框架中，单击**设置警报**按钮。</span><span class="sxs-lookup"><span data-stu-id="46f46-121">In the content frame of the BAM portal, click the **Set Alert** button.</span></span> <span data-ttu-id="46f46-122">内容框架中将加载警报创建模板。</span><span class="sxs-lookup"><span data-stu-id="46f46-122">The content frame will load with the alert creation template.</span></span>  
  
5.  <span data-ttu-id="46f46-123">在中**名称**文字框中，键入警报的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="46f46-123">In the **Name** text box, type a descriptive name for the alert.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="46f46-124">名称限制为 100 个字符并且不能包含以下字符: ~ ！ @# $%^&amp;\* （); 如果在名称中输入以下任何字符，必须更正以完成操作的错误，该值指示该文本字段周围出现红色虚线的边框。</span><span class="sxs-lookup"><span data-stu-id="46f46-124">Names are limited to 100 characters and cannot contain the following characters: ~!@#$%^&amp;\*();  If you enter any of these characters in a name, a dashed red border appears around the text field indicating an error that you must correct to complete the action.</span></span>  
  
6.  <span data-ttu-id="46f46-125">如果不希望在此时间启用警报，请清除**警报启用**复选框。</span><span class="sxs-lookup"><span data-stu-id="46f46-125">If you do not want the alert enabled at this time, clear the **Alert Enabled** check box.</span></span>  
  
7.  <span data-ttu-id="46f46-126">在中**消息**文字框中，键入触发警报时发送的消息。</span><span class="sxs-lookup"><span data-stu-id="46f46-126">In the **Message** text box, type the message that is delivered when the alert is triggered.</span></span>  
  
8.  <span data-ttu-id="46f46-127">从**优先级**下拉列表中，选择此警报的优先级。</span><span class="sxs-lookup"><span data-stu-id="46f46-127">From the **Priority** drop-down list, choose the priority level for this alert.</span></span> <span data-ttu-id="46f46-128">优先级设置表示在其设置警报问题的严重性。</span><span class="sxs-lookup"><span data-stu-id="46f46-128">The priority setting indicates the severity of the issue on which the alert was set.</span></span>  
  
9. <span data-ttu-id="46f46-129">在中**所有者**文本框中，键入此警报的所有者的别名。</span><span class="sxs-lookup"><span data-stu-id="46f46-129">In the **Owners** text box, type the aliases of the owners of this alert.</span></span> <span data-ttu-id="46f46-130">使用多个用户的名称之间的分号。</span><span class="sxs-lookup"><span data-stu-id="46f46-130">Use semicolons between the names of multiple users.</span></span>  
  
10. <span data-ttu-id="46f46-131">在中**警报安全性**区域中，选择该复选框以允许其他用户看到此警报，并且订阅它。</span><span class="sxs-lookup"><span data-stu-id="46f46-131">In the **Alert Security** area, select the check box to allow other users to see this alert and subscribe to it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="46f46-132">您可以在任何时间; 切换警报安全性私有和公共之间警报的订阅服务器存在不会影响此操作。</span><span class="sxs-lookup"><span data-stu-id="46f46-132">You can switch the alert security between private and public at any time; the presence of subscribers to the alert does not affect this action.</span></span> <span data-ttu-id="46f46-133">在切换警报安全性从公共为私有时，但是，应考虑是否有任何警报的订户。</span><span class="sxs-lookup"><span data-stu-id="46f46-133">When you switch the alert security from public to private, however, you should consider whether there are any subscribers to the alert.</span></span> <span data-ttu-id="46f46-134">如果对警报的订阅服务器，它们将没有任何办法警报设为私有时编辑其订阅。</span><span class="sxs-lookup"><span data-stu-id="46f46-134">If there are subscribers to the alert, they will have no way to edit their subscription when the alert is made private.</span></span>  
  
11. <span data-ttu-id="46f46-135">在右上角的**警报详细信息**区域中，单击**保存警报**按钮。</span><span class="sxs-lookup"><span data-stu-id="46f46-135">In the upper-right corner of the **Alert Details** area, click the **Save Alert** button.</span></span>  
  
### <a name="to-set-an-alert-on-an-aggregation"></a><span data-ttu-id="46f46-136">若要设置有关聚合的警报</span><span class="sxs-lookup"><span data-stu-id="46f46-136">To set an alert on an aggregation</span></span>  
  
1.  <span data-ttu-id="46f46-137">在中**我的视图**框架中，单击要展开的视图的任务列表的视图。</span><span class="sxs-lookup"><span data-stu-id="46f46-137">In the **My Views** frame, click a view to expand the list of tasks for the view.</span></span>  
  
2.  <span data-ttu-id="46f46-138">单击**聚合**中的任务**我的视图**已展开的视图下。</span><span class="sxs-lookup"><span data-stu-id="46f46-138">Click the **Aggregations** task in **My Views** under the view you expanded.</span></span>  
  
3.  <span data-ttu-id="46f46-139">在 BAM 门户内容框架中，右键单击数据透视表总计列中的单元格。</span><span class="sxs-lookup"><span data-stu-id="46f46-139">In the content frame of the BAM portal, right-click a cell in the totals column of the PivotTable report.</span></span> <span data-ttu-id="46f46-140">这可以用来执行聚合总计的函数将打开上下文菜单。</span><span class="sxs-lookup"><span data-stu-id="46f46-140">This opens a context menu with functions that are available to perform on the aggregation total.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="46f46-141">您可以通过设置警报特定组件的聚合总展开行项目。</span><span class="sxs-lookup"><span data-stu-id="46f46-141">You can set an alert on a specific component of the aggregation total by expanding that line item.</span></span> <span data-ttu-id="46f46-142">您可以展开随后的级别，以这种方式，直到达到想要设置你的警报的级别。</span><span class="sxs-lookup"><span data-stu-id="46f46-142">You can expand succeeding levels in this manner until you reach the level at which you want to set your alert.</span></span>  
  
4.  <span data-ttu-id="46f46-143">在上下文菜单的顶部，单击**创建警报**。</span><span class="sxs-lookup"><span data-stu-id="46f46-143">At the top of the context menu, click **Create Alert**.</span></span> <span data-ttu-id="46f46-144">内容框架中将加载警报创建模板。</span><span class="sxs-lookup"><span data-stu-id="46f46-144">The content frame will load with the alert creation template.</span></span>  
  
5.  <span data-ttu-id="46f46-145">在中**名称**文字框中，键入警报的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="46f46-145">In the **Name** text box, type a descriptive name for the alert.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="46f46-146">名称限制为 100 个字符并且不能包含以下字符: ~ ！ @# $%^&amp;\* （); 如果在名称中输入以下任何字符，必须更正以完成操作的错误，该值指示该文本字段周围出现红色虚线的边框。</span><span class="sxs-lookup"><span data-stu-id="46f46-146">Names are limited to 100 characters and cannot contain the following characters: ~!@#$%^&amp;\*();  If you enter any of these characters in a name, a dashed red border appears around the text field indicating an error that you must correct to complete the action.</span></span>  
  
6.  <span data-ttu-id="46f46-147">如果不希望在此时间启用警报，请清除**警报启用**复选框。</span><span class="sxs-lookup"><span data-stu-id="46f46-147">If you do not want the alert enabled at this time, clear the **Alert Enabled** check box.</span></span>  
  
7.  <span data-ttu-id="46f46-148">在中**消息**文字框中，键入触发警报时发送的消息。</span><span class="sxs-lookup"><span data-stu-id="46f46-148">In the **Message** text box, type the message that is delivered when the alert is triggered.</span></span>  
  
8.  <span data-ttu-id="46f46-149">从**优先级**下拉列表中，选择此警报的优先级。</span><span class="sxs-lookup"><span data-stu-id="46f46-149">From the **Priority** drop-down list, choose the priority level for this alert.</span></span> <span data-ttu-id="46f46-150">优先级设置表示在其设置警报问题的严重性。</span><span class="sxs-lookup"><span data-stu-id="46f46-150">The priority setting indicates the severity of the issue on which the alert was set.</span></span>  
  
9. <span data-ttu-id="46f46-151">在中**所有者**文本框中，键入此警报的所有者的别名。</span><span class="sxs-lookup"><span data-stu-id="46f46-151">In the **Owners** text box, type the aliases of the owners of this alert.</span></span> <span data-ttu-id="46f46-152">使用多个用户的名称之间的分号。</span><span class="sxs-lookup"><span data-stu-id="46f46-152">Use semicolons between the names of multiple users.</span></span>  
  
10. <span data-ttu-id="46f46-153">在中**阈值**区域中，选择比较条件从**计数**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="46f46-153">In the **Threshold** area, select a comparison condition from the **Count** drop-down list.</span></span>  
  
11. <span data-ttu-id="46f46-154">在中**持续时间**文字框中，输入在其中度量阈值的时间单位数。</span><span class="sxs-lookup"><span data-stu-id="46f46-154">In the **Duration** text box, enter the number of time units across which the threshold is measured.</span></span>  
  
12. <span data-ttu-id="46f46-155">从**持续时间**下拉列表中，选择时间单位。</span><span class="sxs-lookup"><span data-stu-id="46f46-155">From the **Duration** drop-down list, select the unit of time.</span></span>  
  
13. <span data-ttu-id="46f46-156">在中**警报安全性**区域中，选择该复选框以允许其他用户看到此警报，并且订阅它。</span><span class="sxs-lookup"><span data-stu-id="46f46-156">In the **Alert Security** area, select the check box to allow other users to see this alert and subscribe to it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="46f46-157">您可以在任何时间; 切换警报安全性私有和公共之间警报的订阅服务器存在不会影响此操作。</span><span class="sxs-lookup"><span data-stu-id="46f46-157">You can switch the alert security between private and public at any time; the presence of subscribers to the alert does not affect this action.</span></span> <span data-ttu-id="46f46-158">在切换警报安全性从公共为私有时，但是，应考虑是否有任何警报的订户。</span><span class="sxs-lookup"><span data-stu-id="46f46-158">When you switch the alert security from public to private, however, you should consider whether there are any subscribers to the alert.</span></span> <span data-ttu-id="46f46-159">如果对警报的订阅服务器，它们将没有任何办法警报设为私有时编辑其订阅。</span><span class="sxs-lookup"><span data-stu-id="46f46-159">If there are subscribers to the alert, they will have no way to edit their subscription when the alert is made private.</span></span>  
  
14. <span data-ttu-id="46f46-160">在右上角的**警报详细信息**区域中，单击**保存警报**按钮。</span><span class="sxs-lookup"><span data-stu-id="46f46-160">In the upper-right corner of the **Alert Details** area, click the **Save Alert** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46f46-161">请参阅</span><span class="sxs-lookup"><span data-stu-id="46f46-161">See Also</span></span>  
 [<span data-ttu-id="46f46-162">如何在活动搜索中创建查询</span><span class="sxs-lookup"><span data-stu-id="46f46-162">How to Create a Query in Activity Search</span></span>](../core/how-to-create-a-query-in-activity-search.md)