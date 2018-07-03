---
title: 步骤 3： 创建 SharePoint 应用程序以从 Siebel 检索数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 86bde531-2daf-452b-b3e6-5481d66f72e7
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df6c92b371291f4359c4bbce5e16529700bcc0c8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971862"
---
# <a name="step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel"></a><span data-ttu-id="88d27-102">步骤 3： 创建 SharePoint 应用程序以从 Siebel 检索数据</span><span class="sxs-lookup"><span data-stu-id="88d27-102">Step 3: Create a SharePoint Application to Retrieve Data from Siebel</span></span>
<span data-ttu-id="88d27-103">![步骤 3，共 4 步](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span><span class="sxs-lookup"><span data-stu-id="88d27-103">![Step 3 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span></span>  
  
 <span data-ttu-id="88d27-104">**完成时间：** 15 分钟。</span><span class="sxs-lookup"><span data-stu-id="88d27-104">**Time to complete:** 15 minutes.</span></span>  
  
 <span data-ttu-id="88d27-105">**目标：** 现在必须通过使用 Business Data Catalog Definition Editor，创建将应用程序定义文件，并将其导入 Office SharePoint Server。</span><span class="sxs-lookup"><span data-stu-id="88d27-105">**Objective:** You must now take the application definition file you created by using the Business Data Catalog Definition Editor, and import it into Office SharePoint Server.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="88d27-106">必要條件</span><span class="sxs-lookup"><span data-stu-id="88d27-106">Prerequisites</span></span>  
  
-   <span data-ttu-id="88d27-107">您应创建了一个应用程序定义文件，如中所述[步骤 2： 为 Siebel 业务组件操作创建应用程序定义文件](../../adapters-and-accelerators/adapter-siebel/step-2-create-an-application-definition-file-for-siebel-business-component.md)。</span><span class="sxs-lookup"><span data-stu-id="88d27-107">You should have created an application definition file, as described in [Step 2: Create an Application Definition File for Siebel Business Component Operations](../../adapters-and-accelerators/adapter-siebel/step-2-create-an-application-definition-file-for-siebel-business-component.md).</span></span>  
  
-   <span data-ttu-id="88d27-108">必须运行 Microsoft 单一登录服务。</span><span class="sxs-lookup"><span data-stu-id="88d27-108">The Microsoft Single Sign-on service must be running.</span></span>  
  
## <a name="how-to-create-a-sharepoint-application"></a><span data-ttu-id="88d27-109">如何创建 SharePoint 应用程序</span><span class="sxs-lookup"><span data-stu-id="88d27-109">How to Create a SharePoint Application</span></span>  
 <span data-ttu-id="88d27-110">创建 SharePoint 应用程序涉及以下步骤：</span><span class="sxs-lookup"><span data-stu-id="88d27-110">Creating a SharePoint application involves the following steps:</span></span>  
  
-   <span data-ttu-id="88d27-111">在 SharePoint 中创建的单一登录 (SSO) 应用程序</span><span class="sxs-lookup"><span data-stu-id="88d27-111">Create a single sign-on (SSO) application in SharePoint</span></span>  
  
-   <span data-ttu-id="88d27-112">创建共享的服务提供程序 (SSP)</span><span class="sxs-lookup"><span data-stu-id="88d27-112">Create a Shared Services Provider (SSP)</span></span>  
  
-   <span data-ttu-id="88d27-113">导入应用程序定义文件</span><span class="sxs-lookup"><span data-stu-id="88d27-113">Import the application definition file</span></span>  
  
-   <span data-ttu-id="88d27-114">创建 Web 部件页，并添加 Web 部件</span><span class="sxs-lookup"><span data-stu-id="88d27-114">Create a Web Part page, and add Web Parts</span></span>  
  
## <a name="creating-an-sso-application-in-sharepoint"></a><span data-ttu-id="88d27-115">在 SharePoint 中创建的 SSO 应用程序</span><span class="sxs-lookup"><span data-stu-id="88d27-115">Creating an SSO Application in SharePoint</span></span>  
 <span data-ttu-id="88d27-116">若要在 Siebel 系统中的 SharePoint 应用程序中访问数据，必须设置映射到 Siebel 用户的 SharePoint 用户的 SSO 应用程序。</span><span class="sxs-lookup"><span data-stu-id="88d27-116">To access the data in a Siebel system from a SharePoint application, you must set up an SSO application that maps a SharePoint user to a Siebel user.</span></span> <span data-ttu-id="88d27-117">在 SharePoint 中创建的 SSO 应用程序涉及以下步骤：</span><span class="sxs-lookup"><span data-stu-id="88d27-117">Creating an SSO application in SharePoint involves the following steps:</span></span>  
  
1.  <span data-ttu-id="88d27-118">**管理服务器上单一登录设置**。</span><span class="sxs-lookup"><span data-stu-id="88d27-118">**Manage server settings for single sign-on**.</span></span> <span data-ttu-id="88d27-119">在此步骤中，你指定的用户帐户，可以管理和设置单一登录服务。</span><span class="sxs-lookup"><span data-stu-id="88d27-119">In this step, you specify a user account that can manage and set up the single sign-on service.</span></span> <span data-ttu-id="88d27-120">您可以从管理服务器设置页来执行操作。</span><span class="sxs-lookup"><span data-stu-id="88d27-120">You can do so from the Manage Server Settings page.</span></span> <span data-ttu-id="88d27-121">此选项可从 SharePoint 中心管理控制台。</span><span class="sxs-lookup"><span data-stu-id="88d27-121">This option is available from the SharePoint Central Administration console.</span></span> <span data-ttu-id="88d27-122">有关此步骤的详细信息，请参阅"配置单一登录适用于 Office SharePoint Server 2007"部分在[ http://go.microsoft.com/fwlink/?LinkId=105291 ](http://go.microsoft.com/fwlink/?LinkId=105291)。</span><span class="sxs-lookup"><span data-stu-id="88d27-122">For more information about this step, refer to the “Configure Single Sign-On for Office SharePoint Server 2007” section at [http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291).</span></span>  
  
2.  <span data-ttu-id="88d27-123">**管理企业应用程序定义的设置**。</span><span class="sxs-lookup"><span data-stu-id="88d27-123">**Manage settings for enterprise application definitions**.</span></span> <span data-ttu-id="88d27-124">在此步骤中，您配置企业应用程序定义的设置。</span><span class="sxs-lookup"><span data-stu-id="88d27-124">In this step, you configure the settings for the enterprise application definition.</span></span> <span data-ttu-id="88d27-125">您可以从企业应用程序定义页的管理设置执行操作。</span><span class="sxs-lookup"><span data-stu-id="88d27-125">You can do so from the Manage Settings for Enterprise Application Definitions page.</span></span> <span data-ttu-id="88d27-126">此选项可从 SharePoint 中心管理控制台。</span><span class="sxs-lookup"><span data-stu-id="88d27-126">This option is available from the SharePoint Central Administration console.</span></span>  
  
    1.  <span data-ttu-id="88d27-127">在管理中心内，在顶部导航栏上，单击**操作**。</span><span class="sxs-lookup"><span data-stu-id="88d27-127">On Central Administration, on the top navigation bar, click **Operations**.</span></span>  
  
    2.  <span data-ttu-id="88d27-128">在操作页中**的安全配置**部分中，单击**管理的单一登录设置**。</span><span class="sxs-lookup"><span data-stu-id="88d27-128">On the Operations page, in the **Security Configuration** section, click  **Manage settings for single sign-on**.</span></span>  
  
    3.  <span data-ttu-id="88d27-129">在单一登录页上，管理设置中**企业应用程序定义设置**部分中，单击**管理企业应用程序定义的设置**。</span><span class="sxs-lookup"><span data-stu-id="88d27-129">On the Manage Settings for Single Sign-On page, in the **Enterprise Application Definition Settings** section, click **Manage settings for enterprise application definitions**.</span></span>  
  
    4.  <span data-ttu-id="88d27-130">在管理企业应用程序定义页上，提供的值**显示名称**，**应用程序名称**，并**联系人电子邮件地址**字段。</span><span class="sxs-lookup"><span data-stu-id="88d27-130">On the Manage Enterprise Application Definitions page, provide values for the **Display name**, **Application name**, and the **Contact e-mail address** fields.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="88d27-131">有关**应用程序名称**字段中，请确保指定相同的 SSO 应用程序名称为指定**SecondarySsoApplicationId**时创建应用程序定义文件中，为变量中所述[步骤 2： 为 Siebel 业务组件操作创建应用程序定义文件](../../adapters-and-accelerators/adapter-siebel/step-2-create-an-application-definition-file-for-siebel-business-component.md)。</span><span class="sxs-lookup"><span data-stu-id="88d27-131">For the **Application name** field, make sure you specify the same SSO application name that you specified for the **SecondarySsoApplicationId** variable while creating the application definition file, as described in [Step 2: Create an Application Definition File for Siebel Business Component Operations](../../adapters-and-accelerators/adapter-siebel/step-2-create-an-application-definition-file-for-siebel-business-component.md).</span></span>  
  
    5.  <span data-ttu-id="88d27-132">将其他字段保留为默认值，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="88d27-132">Leave the other fields as default, and click **OK**.</span></span>  
  
3.  <span data-ttu-id="88d27-133">**管理企业应用程序定义的帐户信息**。</span><span class="sxs-lookup"><span data-stu-id="88d27-133">**Manage account information for enterprise application definitions**.</span></span> <span data-ttu-id="88d27-134">在此步骤中，启用单个用户或组从 SharePoint 连接到企业应用程序。</span><span class="sxs-lookup"><span data-stu-id="88d27-134">In this step, you enable individual users or groups to connect to an enterprise application from SharePoint.</span></span> <span data-ttu-id="88d27-135">从根本上来说，在此步骤中您映射单个用户或组到用户在 LOB 系统。</span><span class="sxs-lookup"><span data-stu-id="88d27-135">Essentially, in this step you map an individual user or group to a user in the LOB system.</span></span> <span data-ttu-id="88d27-136">您还指定用于连接到 LOB 系统的凭据。</span><span class="sxs-lookup"><span data-stu-id="88d27-136">You also specify the credentials to connect to the LOB system.</span></span> <span data-ttu-id="88d27-137">您可以从管理帐户信息执行操作的企业应用程序定义页。</span><span class="sxs-lookup"><span data-stu-id="88d27-137">You can do so from Manage Account Information for Enterprise Application Definitions page.</span></span> <span data-ttu-id="88d27-138">此选项可从 SharePoint 中心管理控制台。</span><span class="sxs-lookup"><span data-stu-id="88d27-138">This option is available from the SharePoint Central Administration console.</span></span> <span data-ttu-id="88d27-139">有关此步骤的详细信息，请参阅"管理企业应用程序定义的帐户信息"部分在[ http://go.microsoft.com/fwlink/?LinkId=105291 ](http://go.microsoft.com/fwlink/?LinkId=105291)。</span><span class="sxs-lookup"><span data-stu-id="88d27-139">For more information about this step, refer to the “Manage account information for an enterprise application definition” section at [http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291).</span></span>  
  
## <a name="creating-a-shared-services-provider"></a><span data-ttu-id="88d27-140">创建共享的服务提供程序</span><span class="sxs-lookup"><span data-stu-id="88d27-140">Creating a Shared Services Provider</span></span>  
 <span data-ttu-id="88d27-141">SSP 是共享的服务和及其支持资源的逻辑分组。</span><span class="sxs-lookup"><span data-stu-id="88d27-141">An SSP is a logical grouping of shared services and their supporting resources.</span></span> <span data-ttu-id="88d27-142">您可以创建使用 SharePoint 管理中心控制台 SSP。</span><span class="sxs-lookup"><span data-stu-id="88d27-142">You can create an SSP using the SharePoint Central Administration console.</span></span>  
  
 <span data-ttu-id="88d27-143">必须创建 SSP 时定义 Web 站点</span><span class="sxs-lookup"><span data-stu-id="88d27-143">You must define a Web site while creating an SSP.</span></span> <span data-ttu-id="88d27-144">请记住的端口号和你创建的站点地址。</span><span class="sxs-lookup"><span data-stu-id="88d27-144">Remember the port number and the site address you create.</span></span> <span data-ttu-id="88d27-145">你将导出到此站点的业务数据目录应用程序定义。</span><span class="sxs-lookup"><span data-stu-id="88d27-145">You will import the Business Data Catalog application definition to this site.</span></span>  
  
 <span data-ttu-id="88d27-146">有关创建 SSP 的详细信息，请参阅"一章概述： 创建和配置共享服务提供程序"处[ http://go.microsoft.com/fwlink/?LinkId=105119 ](http://go.microsoft.com/fwlink/?LinkId=105119)。</span><span class="sxs-lookup"><span data-stu-id="88d27-146">For more information about creating an SSP, see "Chapter overview: Create and configure Shared Services Providers" at [http://go.microsoft.com/fwlink/?LinkId=105119](http://go.microsoft.com/fwlink/?LinkId=105119).</span></span>  
  
## <a name="importing-the-application-definition-file"></a><span data-ttu-id="88d27-147">导入应用程序定义文件</span><span class="sxs-lookup"><span data-stu-id="88d27-147">Importing the Application Definition File</span></span>  
 <span data-ttu-id="88d27-148">现在必须将应用程序定义文件导入 ssp。</span><span class="sxs-lookup"><span data-stu-id="88d27-148">You must now import the application definition file into the SSP.</span></span>  
  
#### <a name="to-import-the-application-definition-file"></a><span data-ttu-id="88d27-149">若要导入应用程序定义文件</span><span class="sxs-lookup"><span data-stu-id="88d27-149">To import the application definition file</span></span>  
  
1. <span data-ttu-id="88d27-150">启动 SharePoint 3.0 管理中心。</span><span class="sxs-lookup"><span data-stu-id="88d27-150">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="88d27-151">单击**启动**，依次指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**.</span><span class="sxs-lookup"><span data-stu-id="88d27-151">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2. <span data-ttu-id="88d27-152">在左侧的导航窗格中，单击你想要导入应用程序定义的 SSP 的名称。</span><span class="sxs-lookup"><span data-stu-id="88d27-152">In the left navigation pane, click the name of the SSP to which you want to import the application definition.</span></span>  
  
3. <span data-ttu-id="88d27-153">在中**业务数据目录**部分中，单击**导入应用程序定义**。</span><span class="sxs-lookup"><span data-stu-id="88d27-153">In the **Business Data Catalog** section, click **Import application definition**.</span></span>  
  
4. <span data-ttu-id="88d27-154">在导入应用程序定义页，此时会打开，浏览到 Siebel_Account.xml，选择该文件，并单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="88d27-154">On the Import Application Definition page that opens, browse to Siebel_Account.xml, select the file, and then click **Open**.</span></span>  
  
5. <span data-ttu-id="88d27-155">单击“导入” 。</span><span class="sxs-lookup"><span data-stu-id="88d27-155">Click **Import**.</span></span>  
  
6. <span data-ttu-id="88d27-156">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="88d27-156">Click **OK**.</span></span>  
  
   <span data-ttu-id="88d27-157">导入应用程序之后, 中，你可以查看你的应用程序通过转到**查看应用程序**链接。</span><span class="sxs-lookup"><span data-stu-id="88d27-157">After importing the application, you can see your application by going to the **View Applications** link.</span></span> <span data-ttu-id="88d27-158">单击以查看应用程序中的实体的应用程序名称。</span><span class="sxs-lookup"><span data-stu-id="88d27-158">Click the application name to see the entities in the application.</span></span>  
  
## <a name="creating-web-parts"></a><span data-ttu-id="88d27-159">创建 Web 部件</span><span class="sxs-lookup"><span data-stu-id="88d27-159">Creating Web Parts</span></span>  
 <span data-ttu-id="88d27-160">现在必须在您的 SharePoint 站点查看和管理将从 Siebel 系统中提取的业务数据中创建 Web 部件。</span><span class="sxs-lookup"><span data-stu-id="88d27-160">You must now create Web Parts in your SharePoint site to view and manage the business data that will be extracted from the Siebel system.</span></span> <span data-ttu-id="88d27-161">Web 部件是信息的可重用的组件，可包含任何类型的基于 Web，包括分析、 协作式和和数据库信息。</span><span class="sxs-lookup"><span data-stu-id="88d27-161">Web Parts are reusable components that can contain any kind of Web-based information, including analytical, collaborative, and database information.</span></span>  
  
 <span data-ttu-id="88d27-162">在本教程中，在 Business Data Catalog Definition Editor 创建方法实例创建 Web 部件。</span><span class="sxs-lookup"><span data-stu-id="88d27-162">In this tutorial, Web Parts are created for the method instances that were created in Business Data Catalog Definition Editor.</span></span> <span data-ttu-id="88d27-163">Office SharePoint Server 提供了特定使用 Web 部件的不同种类。</span><span class="sxs-lookup"><span data-stu-id="88d27-163">Office SharePoint Server provides different kinds of Web Parts for specific use.</span></span> <span data-ttu-id="88d27-164">Finder 方法实例，我们将使用**业务数据列表**Web 部件。</span><span class="sxs-lookup"><span data-stu-id="88d27-164">For the Finder method instance, we will use the **Business Data List** Web Part.</span></span> <span data-ttu-id="88d27-165">此 Web 部件，可指定要对帐户业务组件执行查询的搜索表达式。</span><span class="sxs-lookup"><span data-stu-id="88d27-165">This Web Part enables you to specify a search expression to perform a query on the Account business component.</span></span> <span data-ttu-id="88d27-166">对于本教程，我们称之为**查询帐户**Web 部件。</span><span class="sxs-lookup"><span data-stu-id="88d27-166">For this tutorial, we call this the **Query Accounts** Web Part.</span></span>  
  
 <span data-ttu-id="88d27-167">本部分介绍如何创建这些 Web 部件。</span><span class="sxs-lookup"><span data-stu-id="88d27-167">This section provides instructions to create these Web Parts.</span></span> <span data-ttu-id="88d27-168">有关创建 Web 部件的详细信息，请参阅 Microsoft Office SharePoint Server 2007 文档 （"自定义业务数据列表、 Web 部件和网站"） 处[ http://go.microsoft.com/fwlink/?LinkId=104131 ](http://go.microsoft.com/fwlink/?LinkId=104131)。</span><span class="sxs-lookup"><span data-stu-id="88d27-168">For more information about creating Web Parts, see the Microsoft Office SharePoint Server 2007 document ("Customize business data lists, Web Parts, and sites") at [http://go.microsoft.com/fwlink/?LinkId=104131](http://go.microsoft.com/fwlink/?LinkId=104131).</span></span>  
  
 <span data-ttu-id="88d27-169">Web 部件将添加到单个 Web 部件页。</span><span class="sxs-lookup"><span data-stu-id="88d27-169">The Web Parts will be added to a single Web Part page.</span></span> <span data-ttu-id="88d27-170">必须添加 Web 部件之前创建的 Web 部件页。</span><span class="sxs-lookup"><span data-stu-id="88d27-170">You must create a Web Part page before adding the Web Parts.</span></span> <span data-ttu-id="88d27-171">对于本教程中，调用该 Web 部件页**Siebel 帐户**。</span><span class="sxs-lookup"><span data-stu-id="88d27-171">For this tutorial, the Web Part page is called **Siebel Account**.</span></span>  
  
### <a name="creating-a-web-part-page"></a><span data-ttu-id="88d27-172">创建 Web 部件页</span><span class="sxs-lookup"><span data-stu-id="88d27-172">Creating a Web Part Page</span></span>  
 <span data-ttu-id="88d27-173">本部分介绍如何创建 Web 部件页。</span><span class="sxs-lookup"><span data-stu-id="88d27-173">This section provides instructions to create a Web Part page.</span></span>  
  
##### <a name="to-create-a-web-part-page"></a><span data-ttu-id="88d27-174">若要创建的 web 部件页</span><span class="sxs-lookup"><span data-stu-id="88d27-174">To create a web part page</span></span>  
  
1. <span data-ttu-id="88d27-175">启动 SharePoint 3.0 管理中心。</span><span class="sxs-lookup"><span data-stu-id="88d27-175">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="88d27-176">单击**启动**，依次指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**。</span><span class="sxs-lookup"><span data-stu-id="88d27-176">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and click **SharePoint 3.0 Central Administration**.</span></span>  
  
2. <span data-ttu-id="88d27-177">在左侧的导航窗格中，单击你想要导入应用程序定义的 SSP 的名称。</span><span class="sxs-lookup"><span data-stu-id="88d27-177">In the left navigation pane, click the name of the SSP to which you want to import the application definition.</span></span>  
  
3. <span data-ttu-id="88d27-178">在共享服务管理页上，从右上角，单击**站点操作**，然后单击**创建**。</span><span class="sxs-lookup"><span data-stu-id="88d27-178">On the Shared Services Administration page, from the top right-hand corner, click **Site Actions**, and then click **Create**.</span></span>  
  
    <span data-ttu-id="88d27-179">![若要创建 web 部件的菜单](../../adapters-and-accelerators/adapter-oracle-ebs/media/a9872c3e-f823-4c47-a538-19242565d2e9.gif "a9872c3e-f823-4c47-a538-19242565d2e9")</span><span class="sxs-lookup"><span data-stu-id="88d27-179">![Menu to create a web part](../../adapters-and-accelerators/adapter-oracle-ebs/media/a9872c3e-f823-4c47-a538-19242565d2e9.gif "a9872c3e-f823-4c47-a538-19242565d2e9")</span></span>  
  
4. <span data-ttu-id="88d27-180">在创建页下**网页**部分中，单击**Web 部件页**。</span><span class="sxs-lookup"><span data-stu-id="88d27-180">On the Create page, under the **Web Pages** section, click **Web Part Page**.</span></span>  
  
5. <span data-ttu-id="88d27-181">在新的 Web 部件页中，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="88d27-181">In the New Web Part page, do the following:</span></span>  
  
   1. <span data-ttu-id="88d27-182">在中**名称**字段中，指定页面的名称。</span><span class="sxs-lookup"><span data-stu-id="88d27-182">In the **Name** field, specify a name for the page.</span></span> <span data-ttu-id="88d27-183">对于本教程，将名称指定为`Siebel Account`。</span><span class="sxs-lookup"><span data-stu-id="88d27-183">For this tutorial, specify the name as `Siebel Account`.</span></span>  
  
   2. <span data-ttu-id="88d27-184">选择**如果文件已存在，则覆盖**复选框，如果你想要使用相同的名称创建的页覆盖旧页面。</span><span class="sxs-lookup"><span data-stu-id="88d27-184">Select the **Overwrite if file already exists** check box, if you want to overwrite old pages with the same name as the page you create.</span></span>  
  
   3. <span data-ttu-id="88d27-185">在中**布局**部分中，从**选择一个布局模板**框中，选择适用于 Web 部件页的布局。</span><span class="sxs-lookup"><span data-stu-id="88d27-185">In the **Layout** section, from the **Choose a Layout Template** box, select a layout for the Web Part page.</span></span> <span data-ttu-id="88d27-186">对于本教程中，选择**整页、 垂直**。</span><span class="sxs-lookup"><span data-stu-id="88d27-186">For this tutorial, select **Full Page, Vertical**.</span></span>  
  
   4. <span data-ttu-id="88d27-187">在中**保存位置**部分中，在**文档库**列表中，选择**窗体模板**。</span><span class="sxs-lookup"><span data-stu-id="88d27-187">In **the Save Location** section, in the **Document Library** list, select **Form Templates**.</span></span>  
  
   5. <span data-ttu-id="88d27-188">单击 **“创建”**。</span><span class="sxs-lookup"><span data-stu-id="88d27-188">Click **Create**.</span></span> <span data-ttu-id="88d27-189">只需创建后下, 图显示的 Web 部件页。</span><span class="sxs-lookup"><span data-stu-id="88d27-189">The following figure shows a Web Part page after it is just created.</span></span>  
  
       <span data-ttu-id="88d27-190">![空 Web 部件页](../../adapters-and-accelerators/adapter-siebel/media/1fa218f5-de81-43be-b1b1-c46de422f112.gif "1fa218f5-de81-43be-b1b1-c46de422f112")</span><span class="sxs-lookup"><span data-stu-id="88d27-190">![Empty Web Part page](../../adapters-and-accelerators/adapter-siebel/media/1fa218f5-de81-43be-b1b1-c46de422f112.gif "1fa218f5-de81-43be-b1b1-c46de422f112")</span></span>  
  
      <span data-ttu-id="88d27-191">您现在必须将不同的 Web 部件添加到此页。</span><span class="sxs-lookup"><span data-stu-id="88d27-191">You must now add the different Web Parts to this page.</span></span>  
  
### <a name="adding-a-business-data-list-web-part"></a><span data-ttu-id="88d27-192">添加业务数据列表 Web 部件</span><span class="sxs-lookup"><span data-stu-id="88d27-192">Adding a Business Data List Web Part</span></span>  
 <span data-ttu-id="88d27-193">现在，你必须将业务数据列表 Web 部件添加到 Web 部件页。</span><span class="sxs-lookup"><span data-stu-id="88d27-193">You must now add a Business Data List Web Part to the Web Part page.</span></span> <span data-ttu-id="88d27-194">使用此 Web 部件，您将查询帐户业务组件使用的搜索表达式。</span><span class="sxs-lookup"><span data-stu-id="88d27-194">Using this Web Part, you will query the Account business component using a search expression.</span></span> <span data-ttu-id="88d27-195">此 Web 部件对应于创建在 Business Data Catalog Definition Editor 的 Finder 方法实例 (QueryAccount)。</span><span class="sxs-lookup"><span data-stu-id="88d27-195">This Web Part corresponds to the Finder method instance (QueryAccount) you created in the Business Data Catalog Definition Editor.</span></span>  
  
##### <a name="to-add-a-business-data-list-web-part"></a><span data-ttu-id="88d27-196">若要添加业务数据列表 Web 部件</span><span class="sxs-lookup"><span data-stu-id="88d27-196">To add a Business Data List Web Part</span></span>  
  
1.  <span data-ttu-id="88d27-197">在中**Siebel 帐户**页上，在**标头**部分中，单击**添加 Web 部件**。</span><span class="sxs-lookup"><span data-stu-id="88d27-197">In the **Siebel Account** page, in the **Header** section, click **Add a Web Part**.</span></span>  
  
2.  <span data-ttu-id="88d27-198">在中**添加 Web 部件**对话框中**业务数据**部分中，选择**业务数据列表**复选框，然后依次**添加**。</span><span class="sxs-lookup"><span data-stu-id="88d27-198">In the **Add Web Parts** dialog box, in the **Business Data** section, select the **Business Data List** check box, and then click **Add**.</span></span>  
  
     <span data-ttu-id="88d27-199">![创建业务数据 Web 部件的选项](../../adapters-and-accelerators/adapter-oracle-ebs/media/ae7c952c-1592-495f-9452-c1bffd44421c.gif "ae7c952c-1592-495f-9452-c1bffd44421c")</span><span class="sxs-lookup"><span data-stu-id="88d27-199">![Options to create a business data Web Part](../../adapters-and-accelerators/adapter-oracle-ebs/media/ae7c952c-1592-495f-9452-c1bffd44421c.gif "ae7c952c-1592-495f-9452-c1bffd44421c")</span></span>  
  
3.  <span data-ttu-id="88d27-200">在新添加的业务数据列表 Web 部件，单击**打开工具窗格**链接。</span><span class="sxs-lookup"><span data-stu-id="88d27-200">In the newly added Business Data List Web Part, click the **Open the tool pane** link.</span></span>  
  
     <span data-ttu-id="88d27-201">![Web 部件中打开工具窗格](../../adapters-and-accelerators/adapter-oracle-ebs/media/4e7a1cb1-69dc-4e0d-a211-6a217dc4a549.gif "4e7a1cb1-69dc-4e0d-a211-6a217dc4a549")</span><span class="sxs-lookup"><span data-stu-id="88d27-201">![Open the tool pane for Web Part](../../adapters-and-accelerators/adapter-oracle-ebs/media/4e7a1cb1-69dc-4e0d-a211-6a217dc4a549.gif "4e7a1cb1-69dc-4e0d-a211-6a217dc4a549")</span></span>  
  
4.  <span data-ttu-id="88d27-202">业务数据列表工具窗格将在右窗格中打开。</span><span class="sxs-lookup"><span data-stu-id="88d27-202">The Business Data List tool pane opens in the right pane.</span></span> <span data-ttu-id="88d27-203">在中**业务数据列表**部分中，对于**类型**字段中，单击**浏览**按钮。</span><span class="sxs-lookup"><span data-stu-id="88d27-203">In the **Business Data List** section, for the **Type** field, click the **Browse** button.</span></span>  
  
     <span data-ttu-id="88d27-204">![业务数据列表工具窗格](../../adapters-and-accelerators/adapter-siebel/media/3b6e1576-03ce-4fc8-bf5a-7b414ef4408c.gif "3b6e1576-03ce-4fc8-bf5a-7b414ef4408c")</span><span class="sxs-lookup"><span data-stu-id="88d27-204">![Business Data List tool pane](../../adapters-and-accelerators/adapter-siebel/media/3b6e1576-03ce-4fc8-bf5a-7b414ef4408c.gif "3b6e1576-03ce-4fc8-bf5a-7b414ef4408c")</span></span>  
  
5.  <span data-ttu-id="88d27-205">在中**业务数据类型选取器**对话框中，选择**Siebel_Account_Instance**应用程序，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="88d27-205">In the **Business Data Type Picker** dialog box, select the **Siebel_Account_Instance** application, and then click **OK**.</span></span>  
  
     <span data-ttu-id="88d27-206">![选择应用程序实例](../../adapters-and-accelerators/adapter-siebel/media/a658d06a-83a8-4e4b-9451-ce58e7ac3632.gif "a658d06a-83a8-4e4b-9451-ce58e7ac3632")</span><span class="sxs-lookup"><span data-stu-id="88d27-206">![Select the application instance](../../adapters-and-accelerators/adapter-siebel/media/a658d06a-83a8-4e4b-9451-ce58e7ac3632.gif "a658d06a-83a8-4e4b-9451-ce58e7ac3632")</span></span>  
  
6.  <span data-ttu-id="88d27-207">展开**外观**节点，然后在**标题**字段中，指定 Web 部件的标题。</span><span class="sxs-lookup"><span data-stu-id="88d27-207">Expand the **Appearance** node, and in the **Title** field, specify a title for the Web Part.</span></span> <span data-ttu-id="88d27-208">对于此 Web 部件，指定**Account List**。</span><span class="sxs-lookup"><span data-stu-id="88d27-208">For this Web Part, specify **Account List**.</span></span>  
  
7.  <span data-ttu-id="88d27-209">在业务数据列表工具窗格中，单击**Apply**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="88d27-209">In the Business Data List tool pane, click **Apply**, and then click **OK**.</span></span> <span data-ttu-id="88d27-210">业务数据列表 Web 部件现在看起来如下所示：</span><span class="sxs-lookup"><span data-stu-id="88d27-210">The Business Data List Web Part now looks like the following:</span></span>  
  
     <span data-ttu-id="88d27-211">![业务数据列表 Web 部件](../../adapters-and-accelerators/adapter-siebel/media/06dbb84a-38c3-4ece-b981-5aa7471909ed.gif "06dbb84a-38c3-4ece-b981-5aa7471909ed")</span><span class="sxs-lookup"><span data-stu-id="88d27-211">![Business Data List Web Part](../../adapters-and-accelerators/adapter-siebel/media/06dbb84a-38c3-4ece-b981-5aa7471909ed.gif "06dbb84a-38c3-4ece-b981-5aa7471909ed")</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="88d27-212">此外可以更改参数列的显示的顺序。</span><span class="sxs-lookup"><span data-stu-id="88d27-212">You can also change the order in which the parameter columns appear.</span></span> <span data-ttu-id="88d27-213">就可以通过单击**编辑视图**向 Web 部件右上角的链接。</span><span class="sxs-lookup"><span data-stu-id="88d27-213">You can do so by clicking the **Edit View** link towards the right corner of the Web Part.</span></span>  
  
8.  <span data-ttu-id="88d27-214">单击**退出编辑模式**从页面的右上角。</span><span class="sxs-lookup"><span data-stu-id="88d27-214">Click **Exit Edit Mode** from the top right corner of the page.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="88d27-215">后续步骤</span><span class="sxs-lookup"><span data-stu-id="88d27-215">Next Steps</span></span>  
 <span data-ttu-id="88d27-216">通过从 Siebel 系统检索数据来测试 SharePoint 应用程序。</span><span class="sxs-lookup"><span data-stu-id="88d27-216">Test the SharePoint application by retrieving data from a Siebel system.</span></span> <span data-ttu-id="88d27-217">请参阅[步骤 4： 测试 SharePoint 应用程序](../../adapters-and-accelerators/adapter-oracle-ebs/step-4-test-your-sharepoint-application.md)。</span><span class="sxs-lookup"><span data-stu-id="88d27-217">See [Step 4: Test Your SharePoint Application](../../adapters-and-accelerators/adapter-oracle-ebs/step-4-test-your-sharepoint-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88d27-218">请参阅</span><span class="sxs-lookup"><span data-stu-id="88d27-218">See Also</span></span>  
 [<span data-ttu-id="88d27-219">教程 1：在 SharePoint 站点上从 Siebel 系统提供数据</span><span class="sxs-lookup"><span data-stu-id="88d27-219">Tutorial 1: Presenting Data From a Siebel System on a SharePoint Site</span></span>](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md)