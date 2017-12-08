---
title: "方案 2： 搜索使用搜索框 web 部件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a233772f-7577-4ac5-b55a-cb1ba2f464c7
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03e536df00499e8965632a3952eb3ae50e3f83df
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="scenario-2--search-using-the-search-box-web-part"></a><span data-ttu-id="48ec9-102">方案 2： 搜索使用搜索框 web 部件</span><span class="sxs-lookup"><span data-stu-id="48ec9-102">Scenario 2:  Search using the search box web part</span></span>
<span data-ttu-id="48ec9-103">我们将在 Microsoft Office SharePoint Server，若要配置使用可以对执行全文搜索的搜索应用程序配置的搜索设置中 Oracle E-business Suite 的 MS_SAMPLE_EMPLOYEE 接口表。</span><span class="sxs-lookup"><span data-stu-id="48ec9-103">We will configure the search settings in Microsoft Office SharePoint Server to configure a search application using which you can perform a full text search on the MS_SAMPLE_EMPLOYEE interface table in Oracle E-Business Suite.</span></span> <span data-ttu-id="48ec9-104">更高版本，我们将添加一个搜索框 Web 部件到从可在其中进行搜索。</span><span class="sxs-lookup"><span data-stu-id="48ec9-104">Later, we will add a Search Box Web Part to from where you can perform the search.</span></span>  
  
 
  
##  <a name="Define"></a><span data-ttu-id="48ec9-105">定义内容的源</span><span class="sxs-lookup"><span data-stu-id="48ec9-105">Define the Content Source</span></span>  
 <span data-ttu-id="48ec9-106">本部分介绍的定义从 Microsoft Office SharePoint Server 可对数据爬网的内容源。</span><span class="sxs-lookup"><span data-stu-id="48ec9-106">This section talks about defining a content source from where Microsoft Office SharePoint Server can crawl the data.</span></span> <span data-ttu-id="48ec9-107">这涉及到将内容映射到 Id 的枚举器中创建方法实例[步骤 2： 创建应用程序定义文件的 Oracle E-business Suite 项目](../../adapters-and-accelerators/adapter-oracle-ebs/step-2-create-an-application-definition-file-for-the-oracle-ebs-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="48ec9-107">This involves mapping the content to the Id Enumerator method instance created in [Step 2: Create an application definition file for the Oracle E-Business Suite artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/step-2-create-an-application-definition-file-for-the-oracle-ebs-artifacts.md).</span></span>  
  
#### <a name="to-define-a-content-source"></a><span data-ttu-id="48ec9-108">若要定义内容的源</span><span class="sxs-lookup"><span data-stu-id="48ec9-108">To define a content source</span></span>  
  
1.  <span data-ttu-id="48ec9-109">启动 SharePoint 3.0 管理中心。</span><span class="sxs-lookup"><span data-stu-id="48ec9-109">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="48ec9-110">单击**启动**，指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**.</span><span class="sxs-lookup"><span data-stu-id="48ec9-110">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="48ec9-111">在左侧的导航窗格中，单击名称的共享服务提供程序 (SSP) 想要配置的搜索应用程序。</span><span class="sxs-lookup"><span data-stu-id="48ec9-111">In the left navigation pane, click the name of the Shared Service Provider (SSP) where you want to configure the search application.</span></span>  
  
3.  <span data-ttu-id="48ec9-112">在主页上，在**搜索**部分中，单击**搜索设置**。</span><span class="sxs-lookup"><span data-stu-id="48ec9-112">On the Home page, in the **Search** section, click **Search settings**.</span></span>  
  
4.  <span data-ttu-id="48ec9-113">在配置搜索设置页上的下的左窗格中，**爬网**，单击**默认内容访问帐户**以指定要用作默认帐户，爬网内容时的帐户。</span><span class="sxs-lookup"><span data-stu-id="48ec9-113">On the Configure Search Settings page, in the left pane under **Crawling**, click **Default content access account** to specify an account to use as the default account when crawling content.</span></span>  
  
5.  <span data-ttu-id="48ec9-114">在默认内容访问帐户页上，指定用户名和密码凭据，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="48ec9-114">On the Default Content Access Account page, specify the user name and password credentials, and click **OK**.</span></span> <span data-ttu-id="48ec9-115">您将返回到搜索管理页。</span><span class="sxs-lookup"><span data-stu-id="48ec9-115">You will return to the Search Administration page.</span></span>  
  
6.  <span data-ttu-id="48ec9-116">在左窗格中下**爬网**，单击**内容源**。</span><span class="sxs-lookup"><span data-stu-id="48ec9-116">In the left pane under **Crawling**, click **Content Sources**.</span></span>  
  
7.  <span data-ttu-id="48ec9-117">在管理内容源页中，单击**新内容源**。</span><span class="sxs-lookup"><span data-stu-id="48ec9-117">On the Manage Content Sources page, click **New Content Source**.</span></span>  
  
8.  <span data-ttu-id="48ec9-118">在管理内容源页中，单击**新内容源**。</span><span class="sxs-lookup"><span data-stu-id="48ec9-118">On the Manage Content Sources page, click **New Content Source**.</span></span>  
  
9. <span data-ttu-id="48ec9-119">在添加内容源页上：</span><span class="sxs-lookup"><span data-stu-id="48ec9-119">On the Add Content Source page:</span></span>  
  
    1.  <span data-ttu-id="48ec9-120">类型`MS_SAMPLE_EMPLOYEE`中**名称**框。</span><span class="sxs-lookup"><span data-stu-id="48ec9-120">Type `MS_SAMPLE_EMPLOYEE` in the **Name** box.</span></span>  
  
    2.  <span data-ttu-id="48ec9-121">在**内容的源类型**区域中，单击**业务数据**。</span><span class="sxs-lookup"><span data-stu-id="48ec9-121">In the **Content Source Type** area, click **Business Data**.</span></span>  
  
    3.  <span data-ttu-id="48ec9-122">在**应用程序**区域中，单击**爬网所选应用程序**，然后选择**MS_SAMPLE_EMPLOYEE_Instance**复选框。</span><span class="sxs-lookup"><span data-stu-id="48ec9-122">In the **Applications** area, click **Crawl selected applications**, and then select the **MS_SAMPLE_EMPLOYEE_Instance** check box.</span></span>  
  
    4.  <span data-ttu-id="48ec9-123">在**启动完全爬网**区域中，选择**启动完全爬网的此内容的源**复选框，并依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="48ec9-123">In the **Start Full Crawl** area, select the **Start full crawl of this content source** check box, and then click **OK**.</span></span>  
  
         <span data-ttu-id="48ec9-124">![添加内容的源](../../adapters-and-accelerators/adapter-oracle-ebs/media/27-add-content-source.gif "27_Add_Content_Source")</span><span class="sxs-lookup"><span data-stu-id="48ec9-124">![Add content source](../../adapters-and-accelerators/adapter-oracle-ebs/media/27-add-content-source.gif "27_Add_Content_Source")</span></span>  
  
10. <span data-ttu-id="48ec9-125">您将与新添加的内容源返回到管理内容源页。</span><span class="sxs-lookup"><span data-stu-id="48ec9-125">You will return to the Manage Content Sources page with the new content source added.</span></span> <span data-ttu-id="48ec9-126">内容的源将通过在 Oracle E-business Suite MS_SAMPLE_EMPLOYEE 接口表中的数据进行爬网。</span><span class="sxs-lookup"><span data-stu-id="48ec9-126">The content source will crawl through the data in the MS_SAMPLE_EMPLOYEE interface table in the Oracle E-Business Suite.</span></span> <span data-ttu-id="48ec9-127">等待，直到完成爬网。</span><span class="sxs-lookup"><span data-stu-id="48ec9-127">Wait until the crawling is completed.</span></span>  
  
11. <span data-ttu-id="48ec9-128">在左窗格中下**爬网**，单击**爬网日志**，然后验证日志文件，以确保爬网成功。</span><span class="sxs-lookup"><span data-stu-id="48ec9-128">In the left pane under **Crawling**, click **Crawl Log**, and then verify the log file to ensure that the crawling is successful.</span></span>  
  
##  <a name="Scope"></a><span data-ttu-id="48ec9-129">定义已爬网内容的作用域</span><span class="sxs-lookup"><span data-stu-id="48ec9-129">Define a Scope for the Crawled Content</span></span>  
  
1.  <span data-ttu-id="48ec9-130">启动 SharePoint 3.0 管理中心。</span><span class="sxs-lookup"><span data-stu-id="48ec9-130">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="48ec9-131">单击**启动**，指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**.</span><span class="sxs-lookup"><span data-stu-id="48ec9-131">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="48ec9-132">在左侧的导航窗格中，单击名称的共享服务提供程序 (SSP) 想要配置的搜索应用程序。</span><span class="sxs-lookup"><span data-stu-id="48ec9-132">In the left navigation pane, click the name of the Shared Service Provider (SSP) where you want to configure the search application.</span></span>  
  
3.  <span data-ttu-id="48ec9-133">在主页上，在**搜索**部分中，单击**搜索设置**。</span><span class="sxs-lookup"><span data-stu-id="48ec9-133">On the Home page, in the **Search** section, click **Search settings**.</span></span>  
  
4.  <span data-ttu-id="48ec9-134">在配置搜索设置页上的下的左窗格中，**查询和结果**，单击**作用域**若要定义对数据爬网的作用域。</span><span class="sxs-lookup"><span data-stu-id="48ec9-134">On the Configure Search Settings page, in the left pane under **Queries and Results**, click **Scopes** to define a scope for the crawling of data.</span></span>  
  
5.  <span data-ttu-id="48ec9-135">在视图作用域页上，单击**新作用域**。</span><span class="sxs-lookup"><span data-stu-id="48ec9-135">On the View Scopes page, click **New Scope**.</span></span>  
  
6.  <span data-ttu-id="48ec9-136">在创建作用域页上，键入`MS_SAMPLE_EMPLOYEE_Search`中**标题**框中，并依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="48ec9-136">On the Create Scope page, type `MS_SAMPLE_EMPLOYEE_Search` in the **Title** box, and then click **OK**.</span></span>  
  
     <span data-ttu-id="48ec9-137">![创建一个作用域](../../adapters-and-accelerators/adapter-oracle-ebs/media/28-create-scope.gif "28_Create_Scope")</span><span class="sxs-lookup"><span data-stu-id="48ec9-137">![Create a scope](../../adapters-and-accelerators/adapter-oracle-ebs/media/28-create-scope.gif "28_Create_Scope")</span></span>  
  
7.  <span data-ttu-id="48ec9-138">将返回与新的作用域添加到视图作用域页。</span><span class="sxs-lookup"><span data-stu-id="48ec9-138">You will return to the View Scopes page with the new scope added.</span></span> <span data-ttu-id="48ec9-139">在**更新状态**在新添加的作用域中的列中，单击**添加规则**链接。</span><span class="sxs-lookup"><span data-stu-id="48ec9-139">In the **Update Status** column for the newly added scope, click the **Add rules** link.</span></span>  
  
8.  <span data-ttu-id="48ec9-140">在添加作用域规则页上：</span><span class="sxs-lookup"><span data-stu-id="48ec9-140">On the Add Scope Rule page:</span></span>  
  
    1.  <span data-ttu-id="48ec9-141">在**作用域规则类型**区域中，单击**内容源**。</span><span class="sxs-lookup"><span data-stu-id="48ec9-141">In the **Scope Rule Type** area, click **Content Source**.</span></span>  
  
    2.  <span data-ttu-id="48ec9-142">在**内容源**列表中，单击**MS_SAMPLE_EMPLOYEE**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="48ec9-142">In the **Content Source** list, click **MS_SAMPLE_EMPLOYEE**, and then click **OK**.</span></span>  
  
         <span data-ttu-id="48ec9-143">![添加作用域规则](../../adapters-and-accelerators/adapter-oracle-ebs/media/29-add-scope-rule.gif "29_Add_Scope_Rule")</span><span class="sxs-lookup"><span data-stu-id="48ec9-143">![Add a scope rule](../../adapters-and-accelerators/adapter-oracle-ebs/media/29-add-scope-rule.gif "29_Add_Scope_Rule")</span></span>  
  
9. <span data-ttu-id="48ec9-144">您将返回到视图作用域页上添加为作用域的规则。</span><span class="sxs-lookup"><span data-stu-id="48ec9-144">You will return to the View Scopes page with the rule added for the scope.</span></span> <span data-ttu-id="48ec9-145">在左窗格中，单击**搜索管理**。</span><span class="sxs-lookup"><span data-stu-id="48ec9-145">In the left pane, click **Search Administration**.</span></span>  
  
10. <span data-ttu-id="48ec9-146">在搜索管理页上找到**需要更新的范围**行，然后单击**立即启动更新**链接。</span><span class="sxs-lookup"><span data-stu-id="48ec9-146">On the Search Administration page, locate the **Scopes needing update** row, and click the **Start update now** link.</span></span>  
  
 <span data-ttu-id="48ec9-147">**范围更新状态**行将显示范围更新的状态。</span><span class="sxs-lookup"><span data-stu-id="48ec9-147">The **Scope update status** row will display the status of the scope update.</span></span> <span data-ttu-id="48ec9-148">等待，直到已完成更新。</span><span class="sxs-lookup"><span data-stu-id="48ec9-148">Wait until the update is complete.</span></span> <span data-ttu-id="48ec9-149">更新完成后，范围是可供使用。</span><span class="sxs-lookup"><span data-stu-id="48ec9-149">After the updated is completed, the scope is ready to be used.</span></span>  
  
##  <a name="AddScope"></a><span data-ttu-id="48ec9-150">将范围添加到搜索下拉列表中</span><span class="sxs-lookup"><span data-stu-id="48ec9-150">Add the Scope to the Search Dropdown</span></span>  
 <span data-ttu-id="48ec9-151">创建搜索范围后，必须将作用域添加到 Microsoft Office SharePoint Server 中的搜索下拉列表，以便可以使用它。</span><span class="sxs-lookup"><span data-stu-id="48ec9-151">After you have created the search scope, you must add the scope to the search dropdown in Microsoft Office SharePoint Server so that it can be used.</span></span>  
  
#### <a name="to-add-the-scope-to-the-search-dropdown"></a><span data-ttu-id="48ec9-152">若要将作用域添加到搜索下拉列表中</span><span class="sxs-lookup"><span data-stu-id="48ec9-152">To add the scope to the search dropdown</span></span>  
  
1.  <span data-ttu-id="48ec9-153">启动 SharePoint 3.0 管理中心。</span><span class="sxs-lookup"><span data-stu-id="48ec9-153">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="48ec9-154">单击**启动**，指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**.</span><span class="sxs-lookup"><span data-stu-id="48ec9-154">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="48ec9-155">在左侧的导航窗格中，单击名称的共享服务提供程序 (SSP) 想要配置的搜索应用程序。</span><span class="sxs-lookup"><span data-stu-id="48ec9-155">In the left navigation pane, click the name of the Shared Service Provider (SSP) where you want to configure the search application.</span></span>  
  
3.  <span data-ttu-id="48ec9-156">在共享服务管理页上，在右上角，单击**站点操作**，然后单击**站点设置**。</span><span class="sxs-lookup"><span data-stu-id="48ec9-156">On the Shared Services Administration page, in the upper-right corner, click **Site Actions**, and then click **Site Settings**.</span></span>  
  
4.  <span data-ttu-id="48ec9-157">在站点设置页上，在**网站集管理**部分中，单击**搜索作用域**。</span><span class="sxs-lookup"><span data-stu-id="48ec9-157">On the Site Settings page, in the **Site Collection Administration** section, click **Search scopes**.</span></span>  
  
5.  <span data-ttu-id="48ec9-158">在视图作用域页上，单击**搜索下拉列表中**链接。</span><span class="sxs-lookup"><span data-stu-id="48ec9-158">On the View Scopes page, click the **Search Dropdown** link.</span></span>  
  
     <span data-ttu-id="48ec9-159">![查看作用域](../../adapters-and-accelerators/adapter-oracle-ebs/media/30-view-scope.gif "30_View_Scope")</span><span class="sxs-lookup"><span data-stu-id="48ec9-159">![View scopes](../../adapters-and-accelerators/adapter-oracle-ebs/media/30-view-scope.gif "30_View_Scope")</span></span>  
  
6.  <span data-ttu-id="48ec9-160">在编辑范围显示组页上：</span><span class="sxs-lookup"><span data-stu-id="48ec9-160">On the Edit Scope Display Group page:</span></span>  
  
    1.  <span data-ttu-id="48ec9-161">在**作用域**区域中，选择**MS_SAMPLE_EMPLOYEE_Search**复选框。</span><span class="sxs-lookup"><span data-stu-id="48ec9-161">In the **Scopes** area, select the **MS_SAMPLE_EMPLOYEE_Search** check box.</span></span>  
  
    2.  <span data-ttu-id="48ec9-162">在**默认作用域**区域中，单击**MS_SAMPLE_EMPLOYEE_Search**中**默认作用域**列表，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="48ec9-162">In the **Default Scope** area, click **MS_SAMPLE_EMPLOYEE_Search** in the **Default Scope** list, and then click **OK**.</span></span>  
  
         <span data-ttu-id="48ec9-163">![编辑范围显示组页](../../adapters-and-accelerators/adapter-oracle-ebs/media/31-edit-scope-display-group.gif "31_Edit_Scope_Display_Group")</span><span class="sxs-lookup"><span data-stu-id="48ec9-163">![Edit Scope Display Group page](../../adapters-and-accelerators/adapter-oracle-ebs/media/31-edit-scope-display-group.gif "31_Edit_Scope_Display_Group")</span></span>  
  
7.  <span data-ttu-id="48ec9-164">将返回与 MS_SAMPLE_EMPLOYEE_Search 范围中的搜索下拉列表中显示组添加到视图作用域页。</span><span class="sxs-lookup"><span data-stu-id="48ec9-164">You will return to the View Scopes page with the MS_SAMPLE_EMPLOYEE_Search scope added in the Search Dropdown display group.</span></span>  
  
##  <a name="SearchWebPart"></a><span data-ttu-id="48ec9-165">添加搜索框 Web 部件</span><span class="sxs-lookup"><span data-stu-id="48ec9-165">Add the Search Box Web Part</span></span>  
 <span data-ttu-id="48ec9-166">若要使用户能够执行全文搜索中 Oracle E-business Suite 的 MS_SAMPLE_EMPLOYEE 接口表，现在必须创建 Web 部件页，并将搜索框 Web 部件添加到它。</span><span class="sxs-lookup"><span data-stu-id="48ec9-166">To enable the users to perform a full-text search on the MS_SAMPLE_EMPLOYEE interface table in Oracle E-Business Suite, you must now create a Web part page, and add a Search Box Web Part to it.</span></span>  
  
#### <a name="to-add-the-search-box-web-part"></a><span data-ttu-id="48ec9-167">若要添加搜索框 Web 部件</span><span class="sxs-lookup"><span data-stu-id="48ec9-167">To add the Search Box Web Part</span></span>  
  
1.  <span data-ttu-id="48ec9-168">创建调用的 Web 部件页**MS_SAMPLE_EMPLOYEE_Search**。</span><span class="sxs-lookup"><span data-stu-id="48ec9-168">Create a Web Part page called **MS_SAMPLE_EMPLOYEE_Search**.</span></span> <span data-ttu-id="48ec9-169">若要了解有关创建的 Web 部件页的步骤，请参阅[方案 1： 使用业务数据列表 web 部件显示数据](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md)中[方案 1： 使用业务数据列表 web 部件显示数据](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md)。</span><span class="sxs-lookup"><span data-stu-id="48ec9-169">To know the steps for creating a Web Part page, see [Scenario 1: Display data using Business Data List web part](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md) in [Scenario 1: Display data using Business Data List web part](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md).</span></span>  
  
2.  <span data-ttu-id="48ec9-170">在 MS_SAMPLE_EMPLOYEE_Search 页上，单击**添加 Web 部件**。</span><span class="sxs-lookup"><span data-stu-id="48ec9-170">On the MS_SAMPLE_EMPLOYEE_Search page, click **Add a Web Part**.</span></span>  
  
3.  <span data-ttu-id="48ec9-171">在**添加 Web 部件**对话框中，在**搜索**部分中，选择**搜索框**复选框，并依次**添加**。</span><span class="sxs-lookup"><span data-stu-id="48ec9-171">In the **Add Web Parts** dialog box, in the **Search** section, select the **Search Box** check box, and then click **Add**.</span></span>  
  
     <span data-ttu-id="48ec9-172">![添加搜索框 Web 部件](../../adapters-and-accelerators/adapter-oracle-ebs/media/32-search-web-part.gif "32_Search_Web_Part")</span><span class="sxs-lookup"><span data-stu-id="48ec9-172">![Add the Search Box Web Part](../../adapters-and-accelerators/adapter-oracle-ebs/media/32-search-web-part.gif "32_Search_Web_Part")</span></span>  
  
4.  <span data-ttu-id="48ec9-173">搜索框 Web 部件添加到 MS_SAMPLE_EMPLOYEE_Search 页面。</span><span class="sxs-lookup"><span data-stu-id="48ec9-173">The Search Box Web part is added to the MS_SAMPLE_EMPLOYEE_Search page.</span></span>  
  
     <span data-ttu-id="48ec9-174">![搜索框 Web 部件](../../adapters-and-accelerators/adapter-oracle-ebs/media/33-search-web-part-final.gif "33_Search_Web_Part_Final")</span><span class="sxs-lookup"><span data-stu-id="48ec9-174">![Search Box Web Part](../../adapters-and-accelerators/adapter-oracle-ebs/media/33-search-web-part-final.gif "33_Search_Web_Part_Final")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48ec9-175">另请参阅</span><span class="sxs-lookup"><span data-stu-id="48ec9-175">See Also</span></span>  
 [<span data-ttu-id="48ec9-176">步骤 3： 创建 SharePoint 应用程序从 Oracle E-business Suite 检索数据</span><span class="sxs-lookup"><span data-stu-id="48ec9-176">Step 3: Create a SharePoint application to retrieve data from Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-ebs.md)  
 [<span data-ttu-id="48ec9-177">方案 1： 使用业务数据列表 web 部件的显示数据</span><span class="sxs-lookup"><span data-stu-id="48ec9-177">Scenario 1: Display data using Business Data List web part</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md)