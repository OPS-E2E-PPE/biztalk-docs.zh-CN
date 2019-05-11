---
title: 应用场景 1：使用业务数据列表 web 部件显示数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b3831814-8b70-4352-b22f-cebd08750ef5
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2a88c99c6b0386a621a9ecdf44d901312736254
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65374649"
---
# <a name="scenario-1-display-data-using-business-data-list-web-part"></a><span data-ttu-id="ea181-102">应用场景 1：使用业务数据列表 web 部件显示数据</span><span class="sxs-lookup"><span data-stu-id="ea181-102">Scenario 1: Display data using Business Data List web part</span></span>
<span data-ttu-id="ea181-103">我们将使用**业务数据列表**适用于 Web 部件**Finder**方法实例。</span><span class="sxs-lookup"><span data-stu-id="ea181-103">We will use the **Business Data List** Web Part for the **Finder** method instance.</span></span> <span data-ttu-id="ea181-104">此 Web 部件，可指定要从 Oracle E-business Suite 中检索员工的列表的搜索表达式。</span><span class="sxs-lookup"><span data-stu-id="ea181-104">This Web Part enables you to specify a search expression to retrieve a list of employees from Oracle E-Business Suite.</span></span> <span data-ttu-id="ea181-105">对于本教程中，这被称为显示员工 Web 部件。</span><span class="sxs-lookup"><span data-stu-id="ea181-105">For this tutorial, this is called the Display Employees Web Part.</span></span> <span data-ttu-id="ea181-106">本部分介绍如何创建此 Web 部件。</span><span class="sxs-lookup"><span data-stu-id="ea181-106">This section provides instructions to create this Web Part.</span></span> <span data-ttu-id="ea181-107">有关创建 Web 部件的详细信息，请参阅"自定义业务数据列表、 Web 部件和站点"网址[ http://go.microsoft.com/fwlink/?LinkId=104131 ](http://go.microsoft.com/fwlink/?LinkId=104131)。</span><span class="sxs-lookup"><span data-stu-id="ea181-107">For more information about creating Web Parts, see "Customize business data lists, Web Parts, and sites" at [http://go.microsoft.com/fwlink/?LinkId=104131](http://go.microsoft.com/fwlink/?LinkId=104131).</span></span>  
  
 <span data-ttu-id="ea181-108">必须添加 Web 部件之前创建的 Web 部件页。</span><span class="sxs-lookup"><span data-stu-id="ea181-108">You must create a Web Part page before adding the Web Parts.</span></span>  
  
## <a name="creating-a-web-part-page"></a><span data-ttu-id="ea181-109">创建 Web 部件页</span><span class="sxs-lookup"><span data-stu-id="ea181-109">Creating a Web Part Page</span></span>  
 <span data-ttu-id="ea181-110">本部分介绍如何创建 Web 部件页。</span><span class="sxs-lookup"><span data-stu-id="ea181-110">This section provides instructions to create a Web Part page.</span></span>  
  
###  <a name="WebPart"></a> <span data-ttu-id="ea181-111">若要创建的 Web 部件页</span><span class="sxs-lookup"><span data-stu-id="ea181-111">To create a Web Part page</span></span>  
  
1.  <span data-ttu-id="ea181-112">启动 SharePoint 3.0 管理中心。</span><span class="sxs-lookup"><span data-stu-id="ea181-112">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="ea181-113">单击**启动**，依次指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**。</span><span class="sxs-lookup"><span data-stu-id="ea181-113">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="ea181-114">在左侧的导航窗格中，单击你想要导入应用程序定义的 SSP 的名称。</span><span class="sxs-lookup"><span data-stu-id="ea181-114">In the left navigation pane, click the name of the SSP to which you want to import the application definition.</span></span>  
  
3.  <span data-ttu-id="ea181-115">在共享服务管理页上，在右上角，单击**站点操作**，然后单击**创建**。</span><span class="sxs-lookup"><span data-stu-id="ea181-115">On the Shared Services Administration page, in the upper-right corner, click **Site Actions**, and then click **Create**.</span></span>  
  
     <span data-ttu-id="ea181-116">![若要创建 web 部件的菜单](../../adapters-and-accelerators/adapter-oracle-ebs/media/a9872c3e-f823-4c47-a538-19242565d2e9.gif "a9872c3e-f823-4c47-a538-19242565d2e9")</span><span class="sxs-lookup"><span data-stu-id="ea181-116">![Menu to create a web part](../../adapters-and-accelerators/adapter-oracle-ebs/media/a9872c3e-f823-4c47-a538-19242565d2e9.gif "a9872c3e-f823-4c47-a538-19242565d2e9")</span></span>  
  
4.  <span data-ttu-id="ea181-117">在创建页上，在**网页**部分中，单击**Web 部件页**。</span><span class="sxs-lookup"><span data-stu-id="ea181-117">On the Create page, in the **Web Pages** section, click **Web Part Page**.</span></span>  
  
5.  <span data-ttu-id="ea181-118">在新的 Web 部件页上，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="ea181-118">On the New Web Part page, do the following:</span></span>  
  
    1.  <span data-ttu-id="ea181-119">在中**名称**字段中，键入页面的名称。</span><span class="sxs-lookup"><span data-stu-id="ea181-119">In the **Name** field, type a name for the page.</span></span> <span data-ttu-id="ea181-120">对于本教程中，键入作为名称**MS_SAMPLE_EMPLOYEE**。</span><span class="sxs-lookup"><span data-stu-id="ea181-120">For this tutorial, type the name as **MS_SAMPLE_EMPLOYEE**.</span></span>  
  
    2.  <span data-ttu-id="ea181-121">选择**如果文件已存在，则覆盖**复选框，如果你想要使用相同的名称创建新的页覆盖旧页面。</span><span class="sxs-lookup"><span data-stu-id="ea181-121">Select the **Overwrite if file already exists** check box, if you want to overwrite old pages with the same name as the new page you create.</span></span>  
  
    3.  <span data-ttu-id="ea181-122">在中**布局**部分中，从**选择一个布局模板**框中，选择适用于 Web 部件页的布局。</span><span class="sxs-lookup"><span data-stu-id="ea181-122">In the **Layout** section, from the **Choose a Layout Template** box, select a layout for the Web Part page.</span></span> <span data-ttu-id="ea181-123">对于本教程中，选择**整页、 垂直**。</span><span class="sxs-lookup"><span data-stu-id="ea181-123">For this tutorial, select **Full Page, Vertical**.</span></span>  
  
    4.  <span data-ttu-id="ea181-124">在中**保存位置**部分中，在**文档库**列表中，单击**窗体模板**。</span><span class="sxs-lookup"><span data-stu-id="ea181-124">In the **Save Location** section, in the **Document Library** list, click **Form Templates**.</span></span>  
  
    5.  <span data-ttu-id="ea181-125">单击 **“创建”**。</span><span class="sxs-lookup"><span data-stu-id="ea181-125">Click **Create**.</span></span> <span data-ttu-id="ea181-126">在创建后下, 图显示 Web 部件页。</span><span class="sxs-lookup"><span data-stu-id="ea181-126">The following figure shows the Web Part page after it is created.</span></span>  
  
         <span data-ttu-id="ea181-127">![新的 web 部件页](../../adapters-and-accelerators/adapter-oracle-ebs/media/23-web-part.gif "23_Web_Part")</span><span class="sxs-lookup"><span data-stu-id="ea181-127">![The new WebPart page](../../adapters-and-accelerators/adapter-oracle-ebs/media/23-web-part.gif "23_Web_Part")</span></span>  
  
    6.  <span data-ttu-id="ea181-128">您现在必须将 Web 部件添加到此页。</span><span class="sxs-lookup"><span data-stu-id="ea181-128">You must now add the Web Parts to this page.</span></span>  
  
## <a name="adding-a-business-data-list-web-part"></a><span data-ttu-id="ea181-129">添加业务数据列表 Web 部件</span><span class="sxs-lookup"><span data-stu-id="ea181-129">Adding a Business Data List Web Part</span></span>  
 <span data-ttu-id="ea181-130">现在，你必须将业务数据列表 Web 部件添加到 Web 部件页。</span><span class="sxs-lookup"><span data-stu-id="ea181-130">You must now add a Business Data List Web Part to the Web Part page.</span></span> <span data-ttu-id="ea181-131">使用此 Web 部件将来自 MS_SAMPLE_EMPLOYEE 接口表相匹配的搜索表达式 Oracle E-business Suite 中检索员工记录的列表。</span><span class="sxs-lookup"><span data-stu-id="ea181-131">Using this Web Part you will retrieve a list of employee records from the MS_SAMPLE_EMPLOYEE interface table in Oracle E-Business Suite that matches a search expression.</span></span> <span data-ttu-id="ea181-132">此 Web 部件对应于**Finder**方法实例 (*Finder_Instance*) 创建在 Business Data Catalog Definition Editor。</span><span class="sxs-lookup"><span data-stu-id="ea181-132">This Web Part corresponds to the **Finder** method instance (*Finder_Instance*) that you created in the Business Data Catalog Definition Editor.</span></span>  
  
#### <a name="to-add-a-business-data-list-web-part"></a><span data-ttu-id="ea181-133">若要添加业务数据列表 Web 部件</span><span class="sxs-lookup"><span data-stu-id="ea181-133">To add a Business Data List Web Part</span></span>  
  
1.  <span data-ttu-id="ea181-134">在 MS_SAMPLE_EMPLOYEE 页上，单击**添加 Web 部件**。</span><span class="sxs-lookup"><span data-stu-id="ea181-134">On the MS_SAMPLE_EMPLOYEE page, click **Add a Web Part**.</span></span>  
  
2.  <span data-ttu-id="ea181-135">在中**添加 Web 部件**对话框中**业务数据**部分中，选择**业务数据列表**复选框，然后依次**添加**。</span><span class="sxs-lookup"><span data-stu-id="ea181-135">In the **Add Web Parts** dialog box, in the **Business Data** section, select the **Business Data List** check box, and then click **Add**.</span></span>  
  
     <span data-ttu-id="ea181-136">![创建业务数据 Web 部件的选项](../../adapters-and-accelerators/adapter-oracle-ebs/media/ae7c952c-1592-495f-9452-c1bffd44421c.gif "ae7c952c-1592-495f-9452-c1bffd44421c")</span><span class="sxs-lookup"><span data-stu-id="ea181-136">![Options to create a business data Web Part](../../adapters-and-accelerators/adapter-oracle-ebs/media/ae7c952c-1592-495f-9452-c1bffd44421c.gif "ae7c952c-1592-495f-9452-c1bffd44421c")</span></span>  
  
3.  <span data-ttu-id="ea181-137">在新添加的业务数据列表 Web 部件，单击**打开工具窗格**链接。</span><span class="sxs-lookup"><span data-stu-id="ea181-137">In the newly added Business Data List Web Part, click the **Open the tool pane** link.</span></span>  
  
     <span data-ttu-id="ea181-138">![Web 部件中打开工具窗格](../../adapters-and-accelerators/adapter-oracle-ebs/media/4e7a1cb1-69dc-4e0d-a211-6a217dc4a549.gif "4e7a1cb1-69dc-4e0d-a211-6a217dc4a549")</span><span class="sxs-lookup"><span data-stu-id="ea181-138">![Open the tool pane for Web Part](../../adapters-and-accelerators/adapter-oracle-ebs/media/4e7a1cb1-69dc-4e0d-a211-6a217dc4a549.gif "4e7a1cb1-69dc-4e0d-a211-6a217dc4a549")</span></span>  
  
4.  <span data-ttu-id="ea181-139">业务数据列表工具窗格将在右窗格中打开。</span><span class="sxs-lookup"><span data-stu-id="ea181-139">The Business Data List tool pane opens in the right pane.</span></span> <span data-ttu-id="ea181-140">在中**业务数据列表**部分中，对于**类型**字段中，单击**浏览**按钮。</span><span class="sxs-lookup"><span data-stu-id="ea181-140">In the **Business Data List** section, for the **Type** field, click the **Browse** button.</span></span>  
  
     <span data-ttu-id="ea181-141">![业务数据列表工具窗格](../../adapters-and-accelerators/adapter-oracle-ebs/media/24-bdc-browse.gif "24_BDC_Browse")</span><span class="sxs-lookup"><span data-stu-id="ea181-141">![Business Data List tool pane](../../adapters-and-accelerators/adapter-oracle-ebs/media/24-bdc-browse.gif "24_BDC_Browse")</span></span>  
  
5.  <span data-ttu-id="ea181-142">在中**业务数据类型选取器**对话框中，选择**MS_SAMPLE_EMPLOYEE_Instance**应用程序，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ea181-142">In the **Business Data Type Picker** dialog box, select the **MS_SAMPLE_EMPLOYEE_Instance** application, and then click **OK**.</span></span>  
  
     <span data-ttu-id="ea181-143">![选择应用程序实例](../../adapters-and-accelerators/adapter-oracle-ebs/media/25-bdc-picker.gif "25_BDC_Picker")</span><span class="sxs-lookup"><span data-stu-id="ea181-143">![Select the application instance](../../adapters-and-accelerators/adapter-oracle-ebs/media/25-bdc-picker.gif "25_BDC_Picker")</span></span>  
  
6.  <span data-ttu-id="ea181-144">展开**外观**节点，然后在**标题**框中，键入 Web 部件的标题。</span><span class="sxs-lookup"><span data-stu-id="ea181-144">Expand the **Appearance** node, and in the **Title** box, type a title for the Web Part.</span></span> <span data-ttu-id="ea181-145">为此 Web 部件中，键入**员工列表**。</span><span class="sxs-lookup"><span data-stu-id="ea181-145">For this Web Part, type **Employee List**.</span></span>  
  
7.  <span data-ttu-id="ea181-146">在业务数据列表工具窗格中，单击**Apply**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ea181-146">In the Business Data List tool pane, click **Apply**, and then click **OK**.</span></span> <span data-ttu-id="ea181-147">业务数据列表 Web 部件现在看起来如下所示：</span><span class="sxs-lookup"><span data-stu-id="ea181-147">The Business Data List Web Part now looks like the following:</span></span>  
  
     <span data-ttu-id="ea181-148">![业务数据列表 Web 部件](../../adapters-and-accelerators/adapter-oracle-ebs/media/26-bdc-webpart.gif "26_BDC_WebPart")</span><span class="sxs-lookup"><span data-stu-id="ea181-148">![Business Data List Web Part](../../adapters-and-accelerators/adapter-oracle-ebs/media/26-bdc-webpart.gif "26_BDC_WebPart")</span></span>  
  
8.  <span data-ttu-id="ea181-149">Web 部件列出了通过执行 MS_SAMPLE_EMPLOYEE 接口表上的选择操作返回的字段。</span><span class="sxs-lookup"><span data-stu-id="ea181-149">The Web Part lists the fields that are returned by executing the Select operation on the MS_SAMPLE_EMPLOYEE interface table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea181-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="ea181-150">See Also</span></span>  
 <span data-ttu-id="ea181-151">[步骤 3：创建 SharePoint 应用程序以从 Oracle E-business Suite 中检索数据](../../adapters-and-accelerators/adapter-oracle-ebs/step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-ebs.md) </span><span class="sxs-lookup"><span data-stu-id="ea181-151">[Step 3: Create a SharePoint Application to Retrieve Data from Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-ebs.md) </span></span>  
 [<span data-ttu-id="ea181-152">方案 2：使用搜索框 Web 部件进行搜索</span><span class="sxs-lookup"><span data-stu-id="ea181-152">Scenario 2: Search Using the Search Box Web Part</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-2-search-using-the-search-box-web-part.md)