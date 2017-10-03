---
title: "步骤 3： 创建 SharePoint 应用程序从 Siebel 检索数据 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 86bde531-2daf-452b-b3e6-5481d66f72e7
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94537b57a731e5d71459518fcbb0a528b6240d19
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel"></a><span data-ttu-id="6dd14-102">步骤 3： 创建 SharePoint 应用程序从 Siebel 检索数据</span><span class="sxs-lookup"><span data-stu-id="6dd14-102">Step 3: Create a SharePoint Application to Retrieve Data from Siebel</span></span>
<span data-ttu-id="6dd14-103">![步骤 3 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span><span class="sxs-lookup"><span data-stu-id="6dd14-103">![Step 3 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span></span>  
  
 <span data-ttu-id="6dd14-104">**完成时间：** 15 分钟。</span><span class="sxs-lookup"><span data-stu-id="6dd14-104">**Time to complete:** 15 minutes.</span></span>  
  
 <span data-ttu-id="6dd14-105">**目标：**现在必须采用通过业务数据目录的定义编辑器中，创建的应用程序定义文件，并将其导入 Office SharePoint Server。</span><span class="sxs-lookup"><span data-stu-id="6dd14-105">**Objective:** You must now take the application definition file you created by using the Business Data Catalog Definition Editor, and import it into Office SharePoint Server.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6dd14-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="6dd14-106">Prerequisites</span></span>  
  
-   <span data-ttu-id="6dd14-107">您将会创建应用程序定义文件，如中所述[步骤 2： 为 Siebel 业务组件操作创建应用程序定义文件](../../adapters-and-accelerators/adapter-siebel/step-2-create-an-application-definition-file-for-siebel-business-component.md)。</span><span class="sxs-lookup"><span data-stu-id="6dd14-107">You should have created an application definition file, as described in [Step 2: Create an Application Definition File for Siebel Business Component Operations](../../adapters-and-accelerators/adapter-siebel/step-2-create-an-application-definition-file-for-siebel-business-component.md).</span></span>  
  
-   <span data-ttu-id="6dd14-108">必须运行 Microsoft 单一登录服务。</span><span class="sxs-lookup"><span data-stu-id="6dd14-108">The Microsoft Single Sign-on service must be running.</span></span>  
  
## <a name="how-to-create-a-sharepoint-application"></a><span data-ttu-id="6dd14-109">如何创建一个 SharePoint 应用程序</span><span class="sxs-lookup"><span data-stu-id="6dd14-109">How to Create a SharePoint Application</span></span>  
 <span data-ttu-id="6dd14-110">创建 SharePoint 应用程序涉及以下步骤：</span><span class="sxs-lookup"><span data-stu-id="6dd14-110">Creating a SharePoint application involves the following steps:</span></span>  
  
-   <span data-ttu-id="6dd14-111">在 SharePoint 中创建的单一登录 (SSO) 应用程序</span><span class="sxs-lookup"><span data-stu-id="6dd14-111">Create a single sign-on (SSO) application in SharePoint</span></span>  
  
-   <span data-ttu-id="6dd14-112">创建共享的服务提供程序 (SSP)</span><span class="sxs-lookup"><span data-stu-id="6dd14-112">Create a Shared Services Provider (SSP)</span></span>  
  
-   <span data-ttu-id="6dd14-113">导入应用程序定义文件</span><span class="sxs-lookup"><span data-stu-id="6dd14-113">Import the application definition file</span></span>  
  
-   <span data-ttu-id="6dd14-114">创建 Web 部件页，并添加 Web 部件</span><span class="sxs-lookup"><span data-stu-id="6dd14-114">Create a Web Part page, and add Web Parts</span></span>  
  
## <a name="creating-an-sso-application-in-sharepoint"></a><span data-ttu-id="6dd14-115">在 SharePoint 中创建 SSO 应用程序</span><span class="sxs-lookup"><span data-stu-id="6dd14-115">Creating an SSO Application in SharePoint</span></span>  
 <span data-ttu-id="6dd14-116">若要在 Siebel 系统从 SharePoint 应用程序中访问数据，你必须设置的 SSO 应用程序将 SharePoint 用户映射到 Siebel 用户。</span><span class="sxs-lookup"><span data-stu-id="6dd14-116">To access the data in a Siebel system from a SharePoint application, you must set up an SSO application that maps a SharePoint user to a Siebel user.</span></span> <span data-ttu-id="6dd14-117">在 SharePoint 中创建 SSO 应用程序涉及以下步骤：</span><span class="sxs-lookup"><span data-stu-id="6dd14-117">Creating an SSO application in SharePoint involves the following steps:</span></span>  
  
1.  <span data-ttu-id="6dd14-118">**管理服务器上单一登录设置**。</span><span class="sxs-lookup"><span data-stu-id="6dd14-118">**Manage server settings for single sign-on**.</span></span> <span data-ttu-id="6dd14-119">在此步骤中，你可以指定可以管理和设置单一登录服务的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="6dd14-119">In this step, you specify a user account that can manage and set up the single sign-on service.</span></span> <span data-ttu-id="6dd14-120">可以从管理服务器设置页来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="6dd14-120">You can do so from the Manage Server Settings page.</span></span> <span data-ttu-id="6dd14-121">此选项才可用从 SharePoint 管理中心控制台。</span><span class="sxs-lookup"><span data-stu-id="6dd14-121">This option is available from the SharePoint Central Administration console.</span></span> <span data-ttu-id="6dd14-122">有关此步骤的详细信息，请参阅"配置单一登录的 Office SharePoint Server 2007"部分在[http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291)。</span><span class="sxs-lookup"><span data-stu-id="6dd14-122">For more information about this step, refer to the “Configure Single Sign-On for Office SharePoint Server 2007” section at [http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291).</span></span>  
  
2.  <span data-ttu-id="6dd14-123">**管理企业应用程序定义的设置**。</span><span class="sxs-lookup"><span data-stu-id="6dd14-123">**Manage settings for enterprise application definitions**.</span></span> <span data-ttu-id="6dd14-124">在此步骤中，你配置的企业应用程序定义的设置。</span><span class="sxs-lookup"><span data-stu-id="6dd14-124">In this step, you configure the settings for the enterprise application definition.</span></span> <span data-ttu-id="6dd14-125">你可以从企业应用程序定义页面的管理设置来实现。</span><span class="sxs-lookup"><span data-stu-id="6dd14-125">You can do so from the Manage Settings for Enterprise Application Definitions page.</span></span> <span data-ttu-id="6dd14-126">此选项才可用从 SharePoint 管理中心控制台。</span><span class="sxs-lookup"><span data-stu-id="6dd14-126">This option is available from the SharePoint Central Administration console.</span></span>  
  
    1.  <span data-ttu-id="6dd14-127">在管理中心内，在顶部导航栏上，单击**操作**。</span><span class="sxs-lookup"><span data-stu-id="6dd14-127">On Central Administration, on the top navigation bar, click **Operations**.</span></span>  
  
    2.  <span data-ttu-id="6dd14-128">在操作页面中**安全配置**部分中，单击**管理单一登录设置**。</span><span class="sxs-lookup"><span data-stu-id="6dd14-128">On the Operations page, in the **Security Configuration** section, click  **Manage settings for single sign-on**.</span></span>  
  
    3.  <span data-ttu-id="6dd14-129">单一登录页的管理设置中**企业应用程序定义设置**部分中，单击**管理企业应用程序定义的设置**。</span><span class="sxs-lookup"><span data-stu-id="6dd14-129">On the Manage Settings for Single Sign-On page, in the **Enterprise Application Definition Settings** section, click **Manage settings for enterprise application definitions**.</span></span>  
  
    4.  <span data-ttu-id="6dd14-130">在管理企业应用程序定义页上，提供的值**显示名称**，**应用程序名称**，和**联系人电子邮件地址**字段。</span><span class="sxs-lookup"><span data-stu-id="6dd14-130">On the Manage Enterprise Application Definitions page, provide values for the **Display name**, **Application name**, and the **Contact e-mail address** fields.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="6dd14-131">有关**应用程序名称**字段中，请确保指定相同为指定的 SSO 应用程序名称**SecondarySsoApplicationId**时创建应用程序定义文件中，将其作为变量中所述[步骤 2： 为 Siebel 业务组件操作创建应用程序定义文件](../../adapters-and-accelerators/adapter-siebel/step-2-create-an-application-definition-file-for-siebel-business-component.md)。</span><span class="sxs-lookup"><span data-stu-id="6dd14-131">For the **Application name** field, make sure you specify the same SSO application name that you specified for the **SecondarySsoApplicationId** variable while creating the application definition file, as described in [Step 2: Create an Application Definition File for Siebel Business Component Operations](../../adapters-and-accelerators/adapter-siebel/step-2-create-an-application-definition-file-for-siebel-business-component.md).</span></span>  
  
    5.  <span data-ttu-id="6dd14-132">将其他字段保留为默认值，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="6dd14-132">Leave the other fields as default, and click **OK**.</span></span>  
  
3.  <span data-ttu-id="6dd14-133">**管理企业应用程序定义的帐户信息**。</span><span class="sxs-lookup"><span data-stu-id="6dd14-133">**Manage account information for enterprise application definitions**.</span></span> <span data-ttu-id="6dd14-134">在此步骤中，你可以启用从 SharePoint 连接到企业应用程序的单个用户或组。</span><span class="sxs-lookup"><span data-stu-id="6dd14-134">In this step, you enable individual users or groups to connect to an enterprise application from SharePoint.</span></span> <span data-ttu-id="6dd14-135">实质上，在此步骤中你映射单个用户或组的用户在 LOB 系统。</span><span class="sxs-lookup"><span data-stu-id="6dd14-135">Essentially, in this step you map an individual user or group to a user in the LOB system.</span></span> <span data-ttu-id="6dd14-136">你还可以指定要连接到 LOB 系统的凭据。</span><span class="sxs-lookup"><span data-stu-id="6dd14-136">You also specify the credentials to connect to the LOB system.</span></span> <span data-ttu-id="6dd14-137">你可以从管理帐户信息执行操作企业应用程序定义页。</span><span class="sxs-lookup"><span data-stu-id="6dd14-137">You can do so from Manage Account Information for Enterprise Application Definitions page.</span></span> <span data-ttu-id="6dd14-138">此选项才可用从 SharePoint 管理中心控制台。</span><span class="sxs-lookup"><span data-stu-id="6dd14-138">This option is available from the SharePoint Central Administration console.</span></span> <span data-ttu-id="6dd14-139">有关此步骤的详细信息，请参阅"管理企业应用程序定义的帐户信息"部分在[http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291)。</span><span class="sxs-lookup"><span data-stu-id="6dd14-139">For more information about this step, refer to the “Manage account information for an enterprise application definition” section at [http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291).</span></span>  
  
## <a name="creating-a-shared-services-provider"></a><span data-ttu-id="6dd14-140">创建共享的服务提供程序</span><span class="sxs-lookup"><span data-stu-id="6dd14-140">Creating a Shared Services Provider</span></span>  
 <span data-ttu-id="6dd14-141">SSP 是共享的服务和其支持的资源的逻辑分组。</span><span class="sxs-lookup"><span data-stu-id="6dd14-141">An SSP is a logical grouping of shared services and their supporting resources.</span></span> <span data-ttu-id="6dd14-142">你可以创建使用 SharePoint 管理中心控制台 SSP。</span><span class="sxs-lookup"><span data-stu-id="6dd14-142">You can create an SSP using the SharePoint Central Administration console.</span></span>  
  
 <span data-ttu-id="6dd14-143">你必须创建 SSP 时定义网站</span><span class="sxs-lookup"><span data-stu-id="6dd14-143">You must define a Web site while creating an SSP.</span></span> <span data-ttu-id="6dd14-144">请记住端口号和你创建的站点地址。</span><span class="sxs-lookup"><span data-stu-id="6dd14-144">Remember the port number and the site address you create.</span></span> <span data-ttu-id="6dd14-145">将将的业务数据目录应用程序定义导入到此站点。</span><span class="sxs-lookup"><span data-stu-id="6dd14-145">You will import the Business Data Catalog application definition to this site.</span></span>  
  
 <span data-ttu-id="6dd14-146">有关创建一个 SSP 的详细信息，请参阅"章概述： 创建和配置共享服务提供程序"在[http://go.microsoft.com/fwlink/?LinkId=105119](http://go.microsoft.com/fwlink/?LinkId=105119)。</span><span class="sxs-lookup"><span data-stu-id="6dd14-146">For more information about creating an SSP, see "Chapter overview: Create and configure Shared Services Providers" at [http://go.microsoft.com/fwlink/?LinkId=105119](http://go.microsoft.com/fwlink/?LinkId=105119).</span></span>  
  
## <a name="importing-the-application-definition-file"></a><span data-ttu-id="6dd14-147">导入的应用程序定义文件</span><span class="sxs-lookup"><span data-stu-id="6dd14-147">Importing the Application Definition File</span></span>  
 <span data-ttu-id="6dd14-148">现在，你必须将应用程序定义文件导入 SSP</span><span class="sxs-lookup"><span data-stu-id="6dd14-148">You must now import the application definition file into the SSP.</span></span>  
  
#### <a name="to-import-the-application-definition-file"></a><span data-ttu-id="6dd14-149">若要导入应用程序定义文件</span><span class="sxs-lookup"><span data-stu-id="6dd14-149">To import the application definition file</span></span>  
  
1.  <span data-ttu-id="6dd14-150">启动 SharePoint 3.0 管理中心。</span><span class="sxs-lookup"><span data-stu-id="6dd14-150">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="6dd14-151">单击**启动**，指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**.</span><span class="sxs-lookup"><span data-stu-id="6dd14-151">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="6dd14-152">在左侧的导航窗格中，单击你想要导入的应用程序定义的 SSP 的名称。</span><span class="sxs-lookup"><span data-stu-id="6dd14-152">In the left navigation pane, click the name of the SSP to which you want to import the application definition.</span></span>  
  
3.  <span data-ttu-id="6dd14-153">在**业务数据目录**部分中，单击**导入应用程序定义**。</span><span class="sxs-lookup"><span data-stu-id="6dd14-153">In the **Business Data Catalog** section, click **Import application definition**.</span></span>  
  
4.  <span data-ttu-id="6dd14-154">在导入应用程序定义用于打开的页面，浏览到 Siebel_Account.xml，选择的文件，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="6dd14-154">On the Import Application Definition page that opens, browse to Siebel_Account.xml, select the file, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="6dd14-155">单击“导入” 。</span><span class="sxs-lookup"><span data-stu-id="6dd14-155">Click **Import**.</span></span>  
  
6.  <span data-ttu-id="6dd14-156">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="6dd14-156">Click **OK**.</span></span>  
  
 <span data-ttu-id="6dd14-157">导入应用程序之后, 中，你可以看到你的应用程序通过转到**查看应用程序**链接。</span><span class="sxs-lookup"><span data-stu-id="6dd14-157">After importing the application, you can see your application by going to the **View Applications** link.</span></span> <span data-ttu-id="6dd14-158">单击以查看应用程序中的实体的应用程序名称。</span><span class="sxs-lookup"><span data-stu-id="6dd14-158">Click the application name to see the entities in the application.</span></span>  
  
## <a name="creating-web-parts"></a><span data-ttu-id="6dd14-159">创建 Web 部件</span><span class="sxs-lookup"><span data-stu-id="6dd14-159">Creating Web Parts</span></span>  
 <span data-ttu-id="6dd14-160">你现在必须在 SharePoint 站点，以查看和管理将从 Siebel 系统中提取的业务数据创建 Web 部件。</span><span class="sxs-lookup"><span data-stu-id="6dd14-160">You must now create Web Parts in your SharePoint site to view and manage the business data that will be extracted from the Siebel system.</span></span> <span data-ttu-id="6dd14-161">Web 部件是信息的可重用组件，可以包含任何类型的基于 Web，包括分析、 协作，和数据库信息。</span><span class="sxs-lookup"><span data-stu-id="6dd14-161">Web Parts are reusable components that can contain any kind of Web-based information, including analytical, collaborative, and database information.</span></span>  
  
 <span data-ttu-id="6dd14-162">在本教程中，已在业务数据目录定义编辑器中创建的方法实例创建了 Web 部件。</span><span class="sxs-lookup"><span data-stu-id="6dd14-162">In this tutorial, Web Parts are created for the method instances that were created in Business Data Catalog Definition Editor.</span></span> <span data-ttu-id="6dd14-163">Office SharePoint Server 提供了用于特定 Web 部件的不同类型。</span><span class="sxs-lookup"><span data-stu-id="6dd14-163">Office SharePoint Server provides different kinds of Web Parts for specific use.</span></span> <span data-ttu-id="6dd14-164">对于 Finder 方法实例，我们将使用**业务数据列表**Web 部件。</span><span class="sxs-lookup"><span data-stu-id="6dd14-164">For the Finder method instance, we will use the **Business Data List** Web Part.</span></span> <span data-ttu-id="6dd14-165">此 Web 部件，可指定要对帐户在业务组件执行查询的搜索表达式。</span><span class="sxs-lookup"><span data-stu-id="6dd14-165">This Web Part enables you to specify a search expression to perform a query on the Account business component.</span></span> <span data-ttu-id="6dd14-166">对于本教程，我们将此**查询帐户**Web 部件。</span><span class="sxs-lookup"><span data-stu-id="6dd14-166">For this tutorial, we call this the **Query Accounts** Web Part.</span></span>  
  
 <span data-ttu-id="6dd14-167">本部分提供创建这些 Web 部件的说明。</span><span class="sxs-lookup"><span data-stu-id="6dd14-167">This section provides instructions to create these Web Parts.</span></span> <span data-ttu-id="6dd14-168">有关创建 Web 部件的详细信息，请参阅 Microsoft Office SharePoint Server 2007 文档 （"自定义业务数据列表、 Web 部件和网站"） 在[http://go.microsoft.com/fwlink/?LinkId=104131](http://go.microsoft.com/fwlink/?LinkId=104131)。</span><span class="sxs-lookup"><span data-stu-id="6dd14-168">For more information about creating Web Parts, see the Microsoft Office SharePoint Server 2007 document ("Customize business data lists, Web Parts, and sites") at [http://go.microsoft.com/fwlink/?LinkId=104131](http://go.microsoft.com/fwlink/?LinkId=104131).</span></span>  
  
 <span data-ttu-id="6dd14-169">Web 部件将添加到单个 Web 部件页。</span><span class="sxs-lookup"><span data-stu-id="6dd14-169">The Web Parts will be added to a single Web Part page.</span></span> <span data-ttu-id="6dd14-170">添加 Web 部件之前，必须创建的 Web 部件页。</span><span class="sxs-lookup"><span data-stu-id="6dd14-170">You must create a Web Part page before adding the Web Parts.</span></span> <span data-ttu-id="6dd14-171">对于本教程中，Web 部件页称为**Siebel 帐户**。</span><span class="sxs-lookup"><span data-stu-id="6dd14-171">For this tutorial, the Web Part page is called **Siebel Account**.</span></span>  
  
### <a name="creating-a-web-part-page"></a><span data-ttu-id="6dd14-172">创建 Web 部件页</span><span class="sxs-lookup"><span data-stu-id="6dd14-172">Creating a Web Part Page</span></span>  
 <span data-ttu-id="6dd14-173">本部分提供说明创建的 Web 部件页。</span><span class="sxs-lookup"><span data-stu-id="6dd14-173">This section provides instructions to create a Web Part page.</span></span>  
  
##### <a name="to-create-a-web-part-page"></a><span data-ttu-id="6dd14-174">若要创建的 web 部件页</span><span class="sxs-lookup"><span data-stu-id="6dd14-174">To create a web part page</span></span>  
  
1.  <span data-ttu-id="6dd14-175">启动 SharePoint 3.0 管理中心。</span><span class="sxs-lookup"><span data-stu-id="6dd14-175">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="6dd14-176">单击**启动**，指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**。</span><span class="sxs-lookup"><span data-stu-id="6dd14-176">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="6dd14-177">在左侧的导航窗格中，单击你想要导入的应用程序定义的 SSP 的名称。</span><span class="sxs-lookup"><span data-stu-id="6dd14-177">In the left navigation pane, click the name of the SSP to which you want to import the application definition.</span></span>  
  
3.  <span data-ttu-id="6dd14-178">在共享服务管理页上，从右上角，单击**站点操作**，然后单击**创建**。</span><span class="sxs-lookup"><span data-stu-id="6dd14-178">On the Shared Services Administration page, from the top right-hand corner, click **Site Actions**, and then click **Create**.</span></span>  
  
     <span data-ttu-id="6dd14-179">![若要创建 web 部件的菜单](../../adapters-and-accelerators/adapter-oracle-ebs/media/a9872c3e-f823-4c47-a538-19242565d2e9.gif "a9872c3e-f823-4c47-a538-19242565d2e9")</span><span class="sxs-lookup"><span data-stu-id="6dd14-179">![Menu to create a web part](../../adapters-and-accelerators/adapter-oracle-ebs/media/a9872c3e-f823-4c47-a538-19242565d2e9.gif "a9872c3e-f823-4c47-a538-19242565d2e9")</span></span>  
  
4.  <span data-ttu-id="6dd14-180">在创建页面上，在**网页**部分中，单击**Web 部件页**。</span><span class="sxs-lookup"><span data-stu-id="6dd14-180">On the Create page, under the **Web Pages** section, click **Web Part Page**.</span></span>  
  
5.  <span data-ttu-id="6dd14-181">在新建 Web 部件页中，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6dd14-181">In the New Web Part page, do the following:</span></span>  
  
    1.  <span data-ttu-id="6dd14-182">在**名称**字段中，指定页面的名称。</span><span class="sxs-lookup"><span data-stu-id="6dd14-182">In the **Name** field, specify a name for the page.</span></span> <span data-ttu-id="6dd14-183">对于本教程，将名称指定为`Siebel Account`。</span><span class="sxs-lookup"><span data-stu-id="6dd14-183">For this tutorial, specify the name as `Siebel Account`.</span></span>  
  
    2.  <span data-ttu-id="6dd14-184">选择**文件已存在时覆盖**复选框，如果你想要为你创建的网页的相同名称覆盖旧的页。</span><span class="sxs-lookup"><span data-stu-id="6dd14-184">Select the **Overwrite if file already exists** check box, if you want to overwrite old pages with the same name as the page you create.</span></span>  
  
    3.  <span data-ttu-id="6dd14-185">在**布局**部分中，从**选择布局模板**框中，选择 Web 部件页的布局。</span><span class="sxs-lookup"><span data-stu-id="6dd14-185">In the **Layout** section, from the **Choose a Layout Template** box, select a layout for the Web Part page.</span></span> <span data-ttu-id="6dd14-186">对于本教程中，选择**完整的页面、 垂直**。</span><span class="sxs-lookup"><span data-stu-id="6dd14-186">For this tutorial, select **Full Page, Vertical**.</span></span>  
  
    4.  <span data-ttu-id="6dd14-187">在**保存位置**部分中，在**文档库**列表中，选择**表单模板**。</span><span class="sxs-lookup"><span data-stu-id="6dd14-187">In **the Save Location** section, in the **Document Library** list, select **Form Templates**.</span></span>  
  
    5.  <span data-ttu-id="6dd14-188">单击 **“创建”**。</span><span class="sxs-lookup"><span data-stu-id="6dd14-188">Click **Create**.</span></span> <span data-ttu-id="6dd14-189">只需创建后下, 图显示的 Web 部件页。</span><span class="sxs-lookup"><span data-stu-id="6dd14-189">The following figure shows a Web Part page after it is just created.</span></span>  
  
         <span data-ttu-id="6dd14-190">![空 Web 部件页](../../adapters-and-accelerators/adapter-siebel/media/1fa218f5-de81-43be-b1b1-c46de422f112.gif "1fa218f5-de81-43be-b1b1-c46de422f112")</span><span class="sxs-lookup"><span data-stu-id="6dd14-190">![Empty Web Part page](../../adapters-and-accelerators/adapter-siebel/media/1fa218f5-de81-43be-b1b1-c46de422f112.gif "1fa218f5-de81-43be-b1b1-c46de422f112")</span></span>  
  
     <span data-ttu-id="6dd14-191">现在，你必须将不同的 Web 部件添加到此页。</span><span class="sxs-lookup"><span data-stu-id="6dd14-191">You must now add the different Web Parts to this page.</span></span>  
  
### <a name="adding-a-business-data-list-web-part"></a><span data-ttu-id="6dd14-192">添加业务数据列表 Web 部件</span><span class="sxs-lookup"><span data-stu-id="6dd14-192">Adding a Business Data List Web Part</span></span>  
 <span data-ttu-id="6dd14-193">现在，你必须将业务数据列表 Web 部件添加到 Web 部件页。</span><span class="sxs-lookup"><span data-stu-id="6dd14-193">You must now add a Business Data List Web Part to the Web Part page.</span></span> <span data-ttu-id="6dd14-194">使用此 Web 部件，你将查询帐户业务组件使用搜索表达式。</span><span class="sxs-lookup"><span data-stu-id="6dd14-194">Using this Web Part, you will query the Account business component using a search expression.</span></span> <span data-ttu-id="6dd14-195">此 Web 部件对应于你创建在业务数据目录定义编辑器中的 Finder 方法实例 (QueryAccount)。</span><span class="sxs-lookup"><span data-stu-id="6dd14-195">This Web Part corresponds to the Finder method instance (QueryAccount) you created in the Business Data Catalog Definition Editor.</span></span>  
  
##### <a name="to-add-a-business-data-list-web-part"></a><span data-ttu-id="6dd14-196">若要添加业务数据列表 Web 部件</span><span class="sxs-lookup"><span data-stu-id="6dd14-196">To add a Business Data List Web Part</span></span>  
  
1.  <span data-ttu-id="6dd14-197">在**Siebel 帐户**页上，在**标头**部分中，单击**添加 Web 部件**。</span><span class="sxs-lookup"><span data-stu-id="6dd14-197">In the **Siebel Account** page, in the **Header** section, click **Add a Web Part**.</span></span>  
  
2.  <span data-ttu-id="6dd14-198">在**添加 Web 部件**对话框中，在**业务数据**部分中，选择**业务数据列表**复选框，并依次**添加**。</span><span class="sxs-lookup"><span data-stu-id="6dd14-198">In the **Add Web Parts** dialog box, in the **Business Data** section, select the **Business Data List** check box, and then click **Add**.</span></span>  
  
     <span data-ttu-id="6dd14-199">![创建业务数据 Web 部件的选项](../../adapters-and-accelerators/adapter-oracle-ebs/media/ae7c952c-1592-495f-9452-c1bffd44421c.gif "ae7c952c-1592-495f-9452-c1bffd44421c")</span><span class="sxs-lookup"><span data-stu-id="6dd14-199">![Options to create a business data Web Part](../../adapters-and-accelerators/adapter-oracle-ebs/media/ae7c952c-1592-495f-9452-c1bffd44421c.gif "ae7c952c-1592-495f-9452-c1bffd44421c")</span></span>  
  
3.  <span data-ttu-id="6dd14-200">在新添加的业务数据列表 Web 部件，单击**打开工具窗格**链接。</span><span class="sxs-lookup"><span data-stu-id="6dd14-200">In the newly added Business Data List Web Part, click the **Open the tool pane** link.</span></span>  
  
     <span data-ttu-id="6dd14-201">![为 Web 部件中打开工具窗格](../../adapters-and-accelerators/adapter-oracle-ebs/media/4e7a1cb1-69dc-4e0d-a211-6a217dc4a549.gif "4e7a1cb1-69dc-4e0d-a211-6a217dc4a549")</span><span class="sxs-lookup"><span data-stu-id="6dd14-201">![Open the tool pane for Web Part](../../adapters-and-accelerators/adapter-oracle-ebs/media/4e7a1cb1-69dc-4e0d-a211-6a217dc4a549.gif "4e7a1cb1-69dc-4e0d-a211-6a217dc4a549")</span></span>  
  
4.  <span data-ttu-id="6dd14-202">业务数据列表工具窗格中将在右窗格中打开。</span><span class="sxs-lookup"><span data-stu-id="6dd14-202">The Business Data List tool pane opens in the right pane.</span></span> <span data-ttu-id="6dd14-203">在**业务数据列表**部分中，为**类型**字段中，单击**浏览**按钮。</span><span class="sxs-lookup"><span data-stu-id="6dd14-203">In the **Business Data List** section, for the **Type** field, click the **Browse** button.</span></span>  
  
     <span data-ttu-id="6dd14-204">![业务数据列表工具窗格](../../adapters-and-accelerators/adapter-siebel/media/3b6e1576-03ce-4fc8-bf5a-7b414ef4408c.gif "3b6e1576-03ce-4fc8-bf5a-7b414ef4408c")</span><span class="sxs-lookup"><span data-stu-id="6dd14-204">![Business Data List tool pane](../../adapters-and-accelerators/adapter-siebel/media/3b6e1576-03ce-4fc8-bf5a-7b414ef4408c.gif "3b6e1576-03ce-4fc8-bf5a-7b414ef4408c")</span></span>  
  
5.  <span data-ttu-id="6dd14-205">在**业务数据类型选取器**对话框中，选择**Siebel_Account_Instance**应用程序，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="6dd14-205">In the **Business Data Type Picker** dialog box, select the **Siebel_Account_Instance** application, and then click **OK**.</span></span>  
  
     <span data-ttu-id="6dd14-206">![选择应用程序实例](../../adapters-and-accelerators/adapter-siebel/media/a658d06a-83a8-4e4b-9451-ce58e7ac3632.gif "a658d06a-83a8-4e4b-9451-ce58e7ac3632")</span><span class="sxs-lookup"><span data-stu-id="6dd14-206">![Select the application instance](../../adapters-and-accelerators/adapter-siebel/media/a658d06a-83a8-4e4b-9451-ce58e7ac3632.gif "a658d06a-83a8-4e4b-9451-ce58e7ac3632")</span></span>  
  
6.  <span data-ttu-id="6dd14-207">展开**外观**节点，然后在**标题**字段中，指定 Web 部件的标题。</span><span class="sxs-lookup"><span data-stu-id="6dd14-207">Expand the **Appearance** node, and in the **Title** field, specify a title for the Web Part.</span></span> <span data-ttu-id="6dd14-208">对于此 Web 部件，指定**帐户列表**。</span><span class="sxs-lookup"><span data-stu-id="6dd14-208">For this Web Part, specify **Account List**.</span></span>  
  
7.  <span data-ttu-id="6dd14-209">在业务数据列表工具窗格中，单击**应用**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="6dd14-209">In the Business Data List tool pane, click **Apply**, and then click **OK**.</span></span> <span data-ttu-id="6dd14-210">业务数据列表 Web 部件现在如下所示：</span><span class="sxs-lookup"><span data-stu-id="6dd14-210">The Business Data List Web Part now looks like the following:</span></span>  
  
     <span data-ttu-id="6dd14-211">![业务数据列表 Web 部件](../../adapters-and-accelerators/adapter-siebel/media/06dbb84a-38c3-4ece-b981-5aa7471909ed.gif "06dbb84a-38c3-4ece-b981-5aa7471909ed")</span><span class="sxs-lookup"><span data-stu-id="6dd14-211">![Business Data List Web Part](../../adapters-and-accelerators/adapter-siebel/media/06dbb84a-38c3-4ece-b981-5aa7471909ed.gif "06dbb84a-38c3-4ece-b981-5aa7471909ed")</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6dd14-212">你还可以更改参数列的出现顺序。</span><span class="sxs-lookup"><span data-stu-id="6dd14-212">You can also change the order in which the parameter columns appear.</span></span> <span data-ttu-id="6dd14-213">你可以通过单击来实现**编辑视图**Web 部件的右角的链接。</span><span class="sxs-lookup"><span data-stu-id="6dd14-213">You can do so by clicking the **Edit View** link towards the right corner of the Web Part.</span></span>  
  
8.  <span data-ttu-id="6dd14-214">单击**退出编辑模式**从页面的右上角。</span><span class="sxs-lookup"><span data-stu-id="6dd14-214">Click **Exit Edit Mode** from the top right corner of the page.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="6dd14-215">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6dd14-215">Next Steps</span></span>  
 <span data-ttu-id="6dd14-216">通过从 Siebel 系统检索数据来测试 SharePoint 应用程序。</span><span class="sxs-lookup"><span data-stu-id="6dd14-216">Test the SharePoint application by retrieving data from a Siebel system.</span></span> <span data-ttu-id="6dd14-217">请参阅[步骤 4： 测试 SharePoint 应用程序](../../adapters-and-accelerators/adapter-oracle-ebs/step-4-test-your-sharepoint-application.md)。</span><span class="sxs-lookup"><span data-stu-id="6dd14-217">See [Step 4: Test Your SharePoint Application](../../adapters-and-accelerators/adapter-oracle-ebs/step-4-test-your-sharepoint-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6dd14-218">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6dd14-218">See Also</span></span>  
 [<span data-ttu-id="6dd14-219">教程 1： 从 SharePoint 站点上的 Siebel 系统提供数据</span><span class="sxs-lookup"><span data-stu-id="6dd14-219">Tutorial 1: Presenting Data From a Siebel System on a SharePoint Site</span></span>](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md)