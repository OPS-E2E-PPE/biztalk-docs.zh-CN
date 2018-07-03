---
title: 如何在活动搜索中创建查询 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Query Builder [BAM portal], creating queries
- queries [BAM], saving
- queries [BAM], creating
- queries [BAM], executing
- Query Builder [BAM portal], executing queries
- Query Builder [BAM portal], opening queries
- Query Builder [BAM portal], saving queries
- queries [BAM], opening
ms.assetid: 7940e47d-10e4-4eb1-b4e6-a8b98461e3a8
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3fd89ec71319a70c0330ebef80c7c8165cacf6c2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989742"
---
# <a name="how-to-create-a-query-in-activity-search"></a><span data-ttu-id="d310d-102">如何在活动搜索中创建查询</span><span class="sxs-lookup"><span data-stu-id="d310d-102">How to Create a Query in Activity Search</span></span>
<span data-ttu-id="d310d-103">业务最终用户以及其他需要接收有关其业务的事件和状态通知的用户可以使用查询来创建活动搜索，警报将基于这些活动搜索。</span><span class="sxs-lookup"><span data-stu-id="d310d-103">Business end users and other users who need to receive notification of events and status pertaining to their business use queries to create activity searches on which to base alerts.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d310d-104">必要條件</span><span class="sxs-lookup"><span data-stu-id="d310d-104">Prerequisites</span></span>  
 <span data-ttu-id="d310d-105">必须具有已部署的视图。</span><span class="sxs-lookup"><span data-stu-id="d310d-105">You must have a deployed view.</span></span>  
  
### <a name="to-open-a-query"></a><span data-ttu-id="d310d-106">打开查询</span><span class="sxs-lookup"><span data-stu-id="d310d-106">To open a query</span></span>  
  
1. <span data-ttu-id="d310d-107">单击**启动**，依次指向**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BAM 门户网站**。</span><span class="sxs-lookup"><span data-stu-id="d310d-107">Click **Start**, point to **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BAM Portal Web Site**.</span></span>  
  
2. <span data-ttu-id="d310d-108">在中**我的视图**帧的门户中，单击现有视图，以扩展到该视图的可用菜单。</span><span class="sxs-lookup"><span data-stu-id="d310d-108">In the **My Views** frame of the portal, click an existing view to expand the menus available to that view.</span></span>  
  
3. <span data-ttu-id="d310d-109">单击**活动搜索**以展开的活动可用于该视图的列表。</span><span class="sxs-lookup"><span data-stu-id="d310d-109">Click **Activity Search** to expand the list of activities available for the view.</span></span>  
  
4. <span data-ttu-id="d310d-110">在列表中单击某个活动。</span><span class="sxs-lookup"><span data-stu-id="d310d-110">Click an activity from the list.</span></span> <span data-ttu-id="d310d-111">这将加载所选活动的“活动搜索”页。</span><span class="sxs-lookup"><span data-stu-id="d310d-111">This will load the Activity Search page for the selected activity.</span></span>  
  
5. <span data-ttu-id="d310d-112">在内容框架中，顶部的页上，单击**浏览**按钮以打开**选择文件**对话框。</span><span class="sxs-lookup"><span data-stu-id="d310d-112">In the content frame, at the top of the page, click the **Browse** button to open the **Choose file** dialog box.</span></span>  
  
6. <span data-ttu-id="d310d-113">浏览至先前保存查询的文件夹。</span><span class="sxs-lookup"><span data-stu-id="d310d-113">Browse to the folder where you have previously saved queries.</span></span>  
  
7. <span data-ttu-id="d310d-114">单击保存查询。</span><span class="sxs-lookup"><span data-stu-id="d310d-114">Click a save query.</span></span>  
  
8. <span data-ttu-id="d310d-115">单击**打开**按钮。</span><span class="sxs-lookup"><span data-stu-id="d310d-115">Click the **Open** button.</span></span> <span data-ttu-id="d310d-116">这将加载到左侧的文本框中的查询路径**浏览**按钮。</span><span class="sxs-lookup"><span data-stu-id="d310d-116">This will load the path to the query in the text box to the left of the **Browse** button.</span></span> <span data-ttu-id="d310d-117">您还可以在文本框中直接键入查询的路径。</span><span class="sxs-lookup"><span data-stu-id="d310d-117">You can also type the path to the query directly into the text box.</span></span>  
  
9. <span data-ttu-id="d310d-118">单击**打开查询**右侧的按钮**浏览**按钮。</span><span class="sxs-lookup"><span data-stu-id="d310d-118">Click the **Open Query** button to the right of the **Browse** button.</span></span>  
  
### <a name="to-construct-a-query"></a><span data-ttu-id="d310d-119">构造查询</span><span class="sxs-lookup"><span data-stu-id="d310d-119">To construct a query</span></span>  
  
1. <span data-ttu-id="d310d-120">单击**启动**，依次指向**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BAM 门户网站**。</span><span class="sxs-lookup"><span data-stu-id="d310d-120">Click **Start**, point to **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BAM Portal Web Site**.</span></span>  
  
2. <span data-ttu-id="d310d-121">在中**我的视图**目前有一系列门户的框架配置视图。</span><span class="sxs-lookup"><span data-stu-id="d310d-121">In the **My Views** frame of the portal there is a list of currently configured views.</span></span> <span data-ttu-id="d310d-122">在每个视图下，有三个可从该视图执行的任务。</span><span class="sxs-lookup"><span data-stu-id="d310d-122">Under each view there are three tasks that can be performed on the view.</span></span> <span data-ttu-id="d310d-123">如果视图当前是折叠的，请单击现有的视图，展开任务列表。</span><span class="sxs-lookup"><span data-stu-id="d310d-123">If the view is currently collapsed, click the existing view to expand the list of tasks.</span></span>  
  
3. <span data-ttu-id="d310d-124">单击**活动搜索**以展开的活动可用于该视图的列表。</span><span class="sxs-lookup"><span data-stu-id="d310d-124">Click **Activity Search** to expand the list of activities available for the view.</span></span>  
  
4. <span data-ttu-id="d310d-125">在列表中单击某个活动。</span><span class="sxs-lookup"><span data-stu-id="d310d-125">Click an activity from the list.</span></span> <span data-ttu-id="d310d-126">这将加载所选活动的“活动搜索”页。</span><span class="sxs-lookup"><span data-stu-id="d310d-126">This will load the Activity Search page for the selected activity.</span></span>  
  
5. <span data-ttu-id="d310d-127">在内容框架中**查询**框中，选择从一个字段**业务数据**下拉列表，用于在查询中的比较。</span><span class="sxs-lookup"><span data-stu-id="d310d-127">In the content frame, in the **Query** box, choose a field from the **Business Data** drop-down list to use for a comparison in the query.</span></span>  
  
6. <span data-ttu-id="d310d-128">从**运算符**下拉列表中，选择要使用的比较运算符。</span><span class="sxs-lookup"><span data-stu-id="d310d-128">From the **Operator** drop-down list, select the comparison operator to use.</span></span>  
  
7. <span data-ttu-id="d310d-129">在中**值**框中，输入要比较的值。</span><span class="sxs-lookup"><span data-stu-id="d310d-129">In the **Value** box, enter the value to compare against.</span></span> <span data-ttu-id="d310d-130">您只能输入适合于要进行比较的字段的值。</span><span class="sxs-lookup"><span data-stu-id="d310d-130">You will only be able to enter a value appropriate to the field to which you are comparing.</span></span> <span data-ttu-id="d310d-131">（如果业务数据项是日期字段，则比较数据为格式适合您的区域性设置的日期或日期时间。）</span><span class="sxs-lookup"><span data-stu-id="d310d-131">(If the business data item is a date field, then the comparison data is a date or date time formatted as appropriate for your culture settings.)</span></span>  
  
8. <span data-ttu-id="d310d-132">如果你有更多子句将添加到查询，请单击**添加**按钮右侧的查询框。</span><span class="sxs-lookup"><span data-stu-id="d310d-132">If you have more clauses to add to the query, click the **Add** button to the right of the query box.</span></span> <span data-ttu-id="d310d-133">这将为下一个子句添加一个新行。</span><span class="sxs-lookup"><span data-stu-id="d310d-133">This will add a new line for the next clause.</span></span> <span data-ttu-id="d310d-134">您可以选择是使用 AND 还是使用 OR 来联接子句。</span><span class="sxs-lookup"><span data-stu-id="d310d-134">You can select whether the clauses are join by using an AND or an OR.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="d310d-135">您无法对子句进行分组以构成更复杂的查询。</span><span class="sxs-lookup"><span data-stu-id="d310d-135">You cannot group clauses to form more complex queries.</span></span> <span data-ttu-id="d310d-136">查询是一组由 AND 或 OR 运算符联接的简单子句。</span><span class="sxs-lookup"><span data-stu-id="d310d-136">A query is a simple set of clauses joined by an AND or an OR operator.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="d310d-137">如果您在这些步骤中单击后退按钮，并收到"警告： 网页已过期，"您可以按 F5 重新获得原始内容。</span><span class="sxs-lookup"><span data-stu-id="d310d-137">If you click the back button during these procedures and receive a "warning: page has expired," you can press F5 to get your original contents back.</span></span> <span data-ttu-id="d310d-138">可能需要多次按 F5。</span><span class="sxs-lookup"><span data-stu-id="d310d-138">You may have to press F5 several times.</span></span>  
  
9. <span data-ttu-id="d310d-139">在列选择器中选择的数据或从里程碑**可用的数据和里程碑**查询要作为数据返回的列表框。</span><span class="sxs-lookup"><span data-stu-id="d310d-139">In the Column Chooser select the data or milestones from the **Available Data and Milestones** list box for the query to return as data.</span></span> <span data-ttu-id="d310d-140">您可以选择多个项，方法是按下 SHIFT 键并单击要返回的组中的第一个和最后一个项。</span><span class="sxs-lookup"><span data-stu-id="d310d-140">You can select multiple items by holding down the SHIFT key and clicking the first and last items in the group you want to return.</span></span> <span data-ttu-id="d310d-141">还可以通过按下 CTRL 键并选择要返回的项，从列表中选择多个项。</span><span class="sxs-lookup"><span data-stu-id="d310d-141">You can also select multiple items from the list by holding down the CTRL key and selecting the items to return.</span></span>  
  
10. <span data-ttu-id="d310d-142">使用**>>** 按钮，将移动到所选的项目**要显示的项**列表框。</span><span class="sxs-lookup"><span data-stu-id="d310d-142">Use the **>>** button to move the selected items to the **Items to show** list box.</span></span> <span data-ttu-id="d310d-143">可以通过选择它们并使用从此列表中删除项**<<** 按钮以将它们移回数据和里程碑列表框。</span><span class="sxs-lookup"><span data-stu-id="d310d-143">You can remove items from this list by selecting them and using the **<<** button to move them back to the data and milestones list box.</span></span>  
  
11. <span data-ttu-id="d310d-144">选择了查询要返回的所有项后，可以重排结果，确定列显示的顺序。</span><span class="sxs-lookup"><span data-stu-id="d310d-144">Once you have selected all the items that the query will return, you can rearrange the results to determine in what order the columns are shown.</span></span> <span data-ttu-id="d310d-145">若要将列移到返回的数据集的第一个位置，选择通过单击它并单击**移**按钮，直至它位于项列表的顶部。</span><span class="sxs-lookup"><span data-stu-id="d310d-145">To move a column to the first position in the returned data set, select it by clicking it and clicking the **Move Up** button until it is at the top of the list of items.</span></span> <span data-ttu-id="d310d-146">同样，若要将项移至更高版本中返回的数据集的位置，选择项的单击它，然后单击**下移**按钮，直至它位于希望其显示的位置。</span><span class="sxs-lookup"><span data-stu-id="d310d-146">Similarly, to move an item to a later position in the returned data set, select the item by clicking it and then clicking the **Move Down** button until it is in the position in which you want it to display.</span></span>  
  
### <a name="to-save-a-query"></a><span data-ttu-id="d310d-147">保存查询</span><span class="sxs-lookup"><span data-stu-id="d310d-147">To save a query</span></span>  
  
1.  <span data-ttu-id="d310d-148">在内容框架中，顶部的页上，单击**保存查询**按钮以打开**保存文件**对话框。</span><span class="sxs-lookup"><span data-stu-id="d310d-148">In the content frame, at the top of the page, click the **Save Query** button to open the **Save File** dialog box.</span></span>  
  
2.  <span data-ttu-id="d310d-149">上**文件下载**对话框中，单击**保存**按钮。</span><span class="sxs-lookup"><span data-stu-id="d310d-149">On the **File Download** dialog box, click the **Save** button.</span></span>  
  
3.  <span data-ttu-id="d310d-150">浏览至要保存查询的位置。</span><span class="sxs-lookup"><span data-stu-id="d310d-150">Browse to the location where you want to save the query.</span></span>  
  
4.  <span data-ttu-id="d310d-151">可以接受为查询提供的默认名称，也可以输入中的新名称**文件名**文本框。</span><span class="sxs-lookup"><span data-stu-id="d310d-151">You can accept the default name provided for the query or you can enter a new name in the **File Name** text box.</span></span>  
  
5.  <span data-ttu-id="d310d-152">单击**保存**按钮。</span><span class="sxs-lookup"><span data-stu-id="d310d-152">Click the **Save** button.</span></span>  
  
### <a name="to-execute-a-query"></a><span data-ttu-id="d310d-153">执行查询</span><span class="sxs-lookup"><span data-stu-id="d310d-153">To execute a query</span></span>  
  
1. <span data-ttu-id="d310d-154">单击**启动**，依次指向**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BAM 门户网站**。</span><span class="sxs-lookup"><span data-stu-id="d310d-154">Click **Start**, point to **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BAM Portal Web Site**.</span></span>  
  
2. <span data-ttu-id="d310d-155">在中**我的视图**帧的门户中，单击现有视图，以扩展到该视图的可用菜单。</span><span class="sxs-lookup"><span data-stu-id="d310d-155">In the **My Views** frame of the portal, click an existing view to expand the menus available to that view.</span></span>  
  
3. <span data-ttu-id="d310d-156">单击**活动搜索**以展开的活动可用于该视图的列表。</span><span class="sxs-lookup"><span data-stu-id="d310d-156">Click **Activity Search** to expand the list of activities available for the view.</span></span>  
  
4. <span data-ttu-id="d310d-157">在列表中单击某个活动。</span><span class="sxs-lookup"><span data-stu-id="d310d-157">Click an activity from the list.</span></span> <span data-ttu-id="d310d-158">这将加载所选活动的“活动搜索”页。</span><span class="sxs-lookup"><span data-stu-id="d310d-158">This will load the Activity Search page for the selected activity.</span></span>  
  
5. <span data-ttu-id="d310d-159">打开现有查询，或构建一个新的查询。</span><span class="sxs-lookup"><span data-stu-id="d310d-159">Either open an existing query or build a new query.</span></span>  
  
6. <span data-ttu-id="d310d-160">在门户的内容框架中，单击**执行查询**按钮。</span><span class="sxs-lookup"><span data-stu-id="d310d-160">In the content frame of the portal, click the **Execute Query** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d310d-161">请参阅</span><span class="sxs-lookup"><span data-stu-id="d310d-161">See Also</span></span>  
 [<span data-ttu-id="d310d-162">BAM 门户中的活动搜索</span><span class="sxs-lookup"><span data-stu-id="d310d-162">Activity Searches in the BAM Portal</span></span>](../core/activity-searches-in-the-bam-portal.md)