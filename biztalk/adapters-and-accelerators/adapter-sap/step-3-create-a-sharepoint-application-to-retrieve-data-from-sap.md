---
title: 步骤 3： 创建 SharePoint 应用程序将数据从 SAP 检索 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO application, creating an
- Business Data Catalog Definition Editor
- application definition file, importing
- Web Part
- SSP
- Web Part page, creating a
- Shared Services Provider, creating a
ms.assetid: 7158caec-9dc0-477c-9db3-179e634e5196
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 346dcf24e1440717e111a1ae146521d887054cd0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983478"
---
# <a name="step-3-create-a-sharepoint-application-to-retrieve-data-from-sap"></a><span data-ttu-id="72bb2-102">步骤 3： 创建 SharePoint 应用程序以从 SAP 检索数据</span><span class="sxs-lookup"><span data-stu-id="72bb2-102">Step 3: Create a SharePoint Application to Retrieve Data from SAP</span></span>
<span data-ttu-id="72bb2-103">![步骤 3，共 4 步](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span><span class="sxs-lookup"><span data-stu-id="72bb2-103">![Step 3 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span></span>  
  
 <span data-ttu-id="72bb2-104">**完成时间：** 15 分钟</span><span class="sxs-lookup"><span data-stu-id="72bb2-104">**Time to complete:** 15 minutes</span></span>  
  
 <span data-ttu-id="72bb2-105">**目标：** 必须现在需要通过使用 Business Data Catalog Definition Editor 工具创建的应用程序定义文件并将其导入 Microsoft Office SharePoint Server。</span><span class="sxs-lookup"><span data-stu-id="72bb2-105">**Objective:** You must now take the application definition file that you created by using the Business Data Catalog Definition Editor tool, and import it into Microsoft Office SharePoint Server.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="72bb2-106">必要條件</span><span class="sxs-lookup"><span data-stu-id="72bb2-106">Prerequisites</span></span>  
  
-   <span data-ttu-id="72bb2-107">您将会创建应用程序定义文件中所述[步骤 2： 为 SAP 项目创建应用程序定义文件](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="72bb2-107">You should have created an application definition file as described in [Step 2: Create an Application Definition File for the SAP Artifacts](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md).</span></span>  
  
-   <span data-ttu-id="72bb2-108">必须运行 Microsoft 单一登录服务。</span><span class="sxs-lookup"><span data-stu-id="72bb2-108">The Microsoft Single Sign-on service must be running.</span></span>  
  
## <a name="how-to-create-a-sharepoint-application"></a><span data-ttu-id="72bb2-109">如何创建 SharePoint 应用程序</span><span class="sxs-lookup"><span data-stu-id="72bb2-109">How to Create a SharePoint Application</span></span>  
 <span data-ttu-id="72bb2-110">创建 SharePoint 应用程序涉及以下步骤：</span><span class="sxs-lookup"><span data-stu-id="72bb2-110">Creating a SharePoint application involves the following steps:</span></span>  
  
- <span data-ttu-id="72bb2-111">在 SharePoint 中创建的单一登录 (SSO) 应用程序</span><span class="sxs-lookup"><span data-stu-id="72bb2-111">Create a single sign-on (SSO) application in SharePoint</span></span>  
  
- <span data-ttu-id="72bb2-112">创建共享服务提供程序</span><span class="sxs-lookup"><span data-stu-id="72bb2-112">Create a Shared Services provider</span></span>  
  
- <span data-ttu-id="72bb2-113">导入应用程序定义文件</span><span class="sxs-lookup"><span data-stu-id="72bb2-113">Import the application definition file</span></span>  
  
- <span data-ttu-id="72bb2-114">创建 Web 部件页，并添加 Web 部件</span><span class="sxs-lookup"><span data-stu-id="72bb2-114">Create a Web Part page, and add Web Parts</span></span>  
  
  <span data-ttu-id="72bb2-115">本主题演示如何执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="72bb2-115">This topic demonstrates how to perform these steps.</span></span>  
  
## <a name="creating-an-sso-application-in-sharepoint"></a><span data-ttu-id="72bb2-116">在 SharePoint 中创建的 SSO 应用程序</span><span class="sxs-lookup"><span data-stu-id="72bb2-116">Creating an SSO Application in SharePoint</span></span>  
 <span data-ttu-id="72bb2-117">若要在 SAP 系统从 SharePoint 应用程序中访问数据，必须设置映射到 SAP 用户的 SharePoint 用户的 SSO 应用程序。</span><span class="sxs-lookup"><span data-stu-id="72bb2-117">To access the data in an SAP system from a SharePoint application, you must set up an SSO application that maps a SharePoint user to an SAP user.</span></span> <span data-ttu-id="72bb2-118">在 SharePoint 中创建的 SSO 应用程序涉及以下步骤：</span><span class="sxs-lookup"><span data-stu-id="72bb2-118">Creating an SSO application in SharePoint involves the following steps:</span></span>  
  
1.  <span data-ttu-id="72bb2-119">**管理服务器上单一登录设置**。</span><span class="sxs-lookup"><span data-stu-id="72bb2-119">**Manage server settings for single sign-on**.</span></span> <span data-ttu-id="72bb2-120">在此步骤中，你指定的用户帐户，可以管理和设置单一登录服务。</span><span class="sxs-lookup"><span data-stu-id="72bb2-120">In this step, you specify a user account that can manage and set up the single sign-on service.</span></span> <span data-ttu-id="72bb2-121">可以在管理服务器设置页上执行操作。</span><span class="sxs-lookup"><span data-stu-id="72bb2-121">You can do so on the Manage Server Settings page.</span></span> <span data-ttu-id="72bb2-122">此选项可从 SharePoint 中心管理控制台。</span><span class="sxs-lookup"><span data-stu-id="72bb2-122">This option is available from the SharePoint Central Administration console.</span></span> <span data-ttu-id="72bb2-123">有关此步骤的详细信息，请参阅"配置单一登录适用于 Office SharePoint Server 2007"部分在[ http://go.microsoft.com/fwlink/?LinkId=105291 ](http://go.microsoft.com/fwlink/?LinkId=105291)。</span><span class="sxs-lookup"><span data-stu-id="72bb2-123">For more information about this step, refer to the “Configure Single Sign-On for Office SharePoint Server 2007” section at [http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291).</span></span>  
  
2.  <span data-ttu-id="72bb2-124">**管理企业应用程序定义的设置**。</span><span class="sxs-lookup"><span data-stu-id="72bb2-124">**Manage settings for enterprise application definitions**.</span></span> <span data-ttu-id="72bb2-125">在此步骤中，您配置企业应用程序定义的设置。</span><span class="sxs-lookup"><span data-stu-id="72bb2-125">In this step, you configure the settings for the enterprise application definition.</span></span> <span data-ttu-id="72bb2-126">您可以从企业应用程序定义页的管理设置执行操作。</span><span class="sxs-lookup"><span data-stu-id="72bb2-126">You can do so from the Manage Settings for Enterprise Application Definitions page.</span></span> <span data-ttu-id="72bb2-127">此选项可从 SharePoint 中心管理控制台。</span><span class="sxs-lookup"><span data-stu-id="72bb2-127">This option is available from the SharePoint Central Administration console.</span></span>  
  
    1.  <span data-ttu-id="72bb2-128">在管理中心内，在顶部导航栏上，单击**操作**。</span><span class="sxs-lookup"><span data-stu-id="72bb2-128">On Central Administration, on the top navigation bar, click **Operations**.</span></span>  
  
    2.  <span data-ttu-id="72bb2-129">在操作页中**的安全配置**部分中，单击**管理的单一登录设置**。</span><span class="sxs-lookup"><span data-stu-id="72bb2-129">On the Operations page, in the **Security Configuration** section, click  **Manage settings for single sign-on**.</span></span>  
  
    3.  <span data-ttu-id="72bb2-130">在单一登录页上，管理设置中**企业应用程序定义设置**部分中，单击**管理企业应用程序定义的设置**。</span><span class="sxs-lookup"><span data-stu-id="72bb2-130">On the Manage Settings for Single Sign-On page, in the **Enterprise Application Definition Settings** section, click **Manage settings for enterprise application definitions**.</span></span>  
  
    4.  <span data-ttu-id="72bb2-131">在管理企业应用程序定义页上，提供的值**显示名称**，**应用程序名称**，并**联系人电子邮件地址**字段。</span><span class="sxs-lookup"><span data-stu-id="72bb2-131">On the Manage Enterprise Application Definitions page, provide values for the **Display name**, **Application name**, and the **Contact e-mail address** fields.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="72bb2-132">有关**应用程序名称**字段中，请确保指定相同的 SSO 应用程序名称为指定**SecondarySsoApplicationId**时创建应用程序定义文件中，为变量中所述[步骤 2： 为 SAP 项目创建应用程序定义文件](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="72bb2-132">For the **Application name** field, make sure you specify the same SSO application name that you specified for the **SecondarySsoApplicationId** variable while creating the application definition file, as described in [Step 2: Create an Application Definition File for the SAP Artifacts](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md).</span></span>  
  
    5.  <span data-ttu-id="72bb2-133">将其他字段保留为默认值，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="72bb2-133">Leave the other fields as default, and click **OK**.</span></span>  
  
3.  <span data-ttu-id="72bb2-134">**管理企业应用程序定义的帐户信息**。</span><span class="sxs-lookup"><span data-stu-id="72bb2-134">**Manage account information for enterprise application definitions**.</span></span> <span data-ttu-id="72bb2-135">在此步骤中，启用单个用户或组从 SharePoint 连接到企业应用程序。</span><span class="sxs-lookup"><span data-stu-id="72bb2-135">In this step, you enable individual users or groups to connect to an enterprise application from SharePoint.</span></span> <span data-ttu-id="72bb2-136">从根本上来说，在此步骤中您映射单个用户或组到用户在 LOB 系统。</span><span class="sxs-lookup"><span data-stu-id="72bb2-136">Essentially, in this step you map an individual user or group to a user in the LOB system.</span></span> <span data-ttu-id="72bb2-137">您还指定用于连接到 LOB 系统的凭据。</span><span class="sxs-lookup"><span data-stu-id="72bb2-137">You also specify the credentials to connect to the LOB system.</span></span> <span data-ttu-id="72bb2-138">您可以从企业应用程序定义页的管理帐户信息执行操作。</span><span class="sxs-lookup"><span data-stu-id="72bb2-138">You can do so from the Manage Account Information for Enterprise Application Definitions page.</span></span> <span data-ttu-id="72bb2-139">此选项可从 SharePoint 中心管理控制台。</span><span class="sxs-lookup"><span data-stu-id="72bb2-139">This option is available from the SharePoint Central Administration console.</span></span> <span data-ttu-id="72bb2-140">有关此步骤的详细信息，请参阅"管理企业应用程序定义的帐户信息"部分在[ http://go.microsoft.com/fwlink/?LinkId=105291 ](http://go.microsoft.com/fwlink/?LinkId=105291)。</span><span class="sxs-lookup"><span data-stu-id="72bb2-140">For more information about this step, refer to the “Manage account information for an enterprise application definition” section at [http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291).</span></span>  
  
## <a name="creating-a-shared-services-provider"></a><span data-ttu-id="72bb2-141">创建共享的服务提供程序</span><span class="sxs-lookup"><span data-stu-id="72bb2-141">Creating a Shared Services Provider</span></span>  
 <span data-ttu-id="72bb2-142">共享服务提供程序是共享的服务和及其支持资源的逻辑分组。</span><span class="sxs-lookup"><span data-stu-id="72bb2-142">A Shared Service Provider is a logical grouping of shared services and their supporting resources.</span></span> <span data-ttu-id="72bb2-143">可以使用 SharePoint 中心管理控制台来创建 SSP。</span><span class="sxs-lookup"><span data-stu-id="72bb2-143">You can create an SSP by using the SharePoint Central Administration console.</span></span>  
  
 <span data-ttu-id="72bb2-144">必须定义网站时创建 ssp。</span><span class="sxs-lookup"><span data-stu-id="72bb2-144">You must define a Web site when creating an SSP.</span></span> <span data-ttu-id="72bb2-145">请记住的端口号和你创建的站点地址。</span><span class="sxs-lookup"><span data-stu-id="72bb2-145">Remember the port number and the site address that you create.</span></span> <span data-ttu-id="72bb2-146">你将导出到此站点的业务数据目录应用程序定义。</span><span class="sxs-lookup"><span data-stu-id="72bb2-146">You will import the Business Data Catalog application definition to this site.</span></span>  
  
 <span data-ttu-id="72bb2-147">有关创建 SSP 的详细信息，请参阅"一章概述： 创建和配置共享服务提供程序"处[ http://go.microsoft.com/fwlink/?LinkId=105119 ](http://go.microsoft.com/fwlink/?LinkId=105119)。</span><span class="sxs-lookup"><span data-stu-id="72bb2-147">For more information about creating an SSP, see "Chapter overview: Create and configure Shared Services Providers" at [http://go.microsoft.com/fwlink/?LinkId=105119](http://go.microsoft.com/fwlink/?LinkId=105119).</span></span>  
  
## <a name="importing-the-application-definition-file"></a><span data-ttu-id="72bb2-148">导入应用程序定义文件</span><span class="sxs-lookup"><span data-stu-id="72bb2-148">Importing the Application Definition File</span></span>  
 <span data-ttu-id="72bb2-149">现在必须将应用程序定义文件导入 ssp。</span><span class="sxs-lookup"><span data-stu-id="72bb2-149">You must now import the application definition file into the SSP.</span></span>  
  
#### <a name="to-import-the-application-definition-file"></a><span data-ttu-id="72bb2-150">若要导入应用程序定义文件</span><span class="sxs-lookup"><span data-stu-id="72bb2-150">To import the application definition file</span></span>  
  
1.  <span data-ttu-id="72bb2-151">启动 SharePoint 3.0 管理中心。</span><span class="sxs-lookup"><span data-stu-id="72bb2-151">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="72bb2-152">单击**启动**，依次指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**.</span><span class="sxs-lookup"><span data-stu-id="72bb2-152">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="72bb2-153">在左侧的导航窗格中，单击你想要导入应用程序定义的 SSP 的名称。</span><span class="sxs-lookup"><span data-stu-id="72bb2-153">In the left navigation pane, click the name of the SSP to which you want to import the application definition.</span></span>  
  
3.  <span data-ttu-id="72bb2-154">在中**业务数据目录**部分中，单击**导入应用程序定义**。</span><span class="sxs-lookup"><span data-stu-id="72bb2-154">In the **Business Data Catalog** section, click **Import application definition**.</span></span>  
  
4.  <span data-ttu-id="72bb2-155">在导入应用程序定义页，此时会打开，浏览到 Customer_Orders.xml，选择该文件，并单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="72bb2-155">On the Import Application Definition page that opens, browse to Customer_Orders.xml, select the file, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="72bb2-156">单击“导入” 。</span><span class="sxs-lookup"><span data-stu-id="72bb2-156">Click **Import**.</span></span>  
  
6.  <span data-ttu-id="72bb2-157">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="72bb2-157">Click **OK**.</span></span>  
  
     <span data-ttu-id="72bb2-158">导入后应用程序，可以查看你的应用程序通过转到**查看应用程序**链接。</span><span class="sxs-lookup"><span data-stu-id="72bb2-158">After importing the application, you can view your application by going to the **View Applications** link.</span></span> <span data-ttu-id="72bb2-159">单击以查看应用程序中的实体的应用程序名称。</span><span class="sxs-lookup"><span data-stu-id="72bb2-159">Click the application name to see the entities in the application.</span></span>  
  
## <a name="creating-web-parts"></a><span data-ttu-id="72bb2-160">创建 Web 部件</span><span class="sxs-lookup"><span data-stu-id="72bb2-160">Creating Web Parts</span></span>  
 <span data-ttu-id="72bb2-161">现在必须在您的 SharePoint 站点查看和管理将从 SAP 系统中提取的业务数据中创建 Web 部件。</span><span class="sxs-lookup"><span data-stu-id="72bb2-161">You must now create Web Parts in your SharePoint site to view and manage the business data that will be extracted from the SAP system.</span></span> <span data-ttu-id="72bb2-162">Web 部件是信息的可重用的组件，可包含任何类型的基于 Web，包括分析、 协作式和和数据库信息。</span><span class="sxs-lookup"><span data-stu-id="72bb2-162">Web Parts are reusable components that can contain any kind of Web-based information, including analytical, collaborative, and database information.</span></span>  
  
 <span data-ttu-id="72bb2-163">在本教程中，在 Business Data Catalog Definition Editor 创建方法实例创建 Web 部件。</span><span class="sxs-lookup"><span data-stu-id="72bb2-163">In this tutorial, Web Parts are created for the method instances that were created in the Business Data Catalog Definition Editor.</span></span> <span data-ttu-id="72bb2-164">Office SharePoint Server 提供了特定使用 Web 部件的不同种类。</span><span class="sxs-lookup"><span data-stu-id="72bb2-164">Office SharePoint Server provides different kinds of Web Parts for specific use.</span></span> <span data-ttu-id="72bb2-165">此处使用了以下 Web 部件：</span><span class="sxs-lookup"><span data-stu-id="72bb2-165">The following Web Parts are used here:</span></span>  
  
- <span data-ttu-id="72bb2-166">**业务数据列表**适用于 Web 部件**Finder**方法实例。</span><span class="sxs-lookup"><span data-stu-id="72bb2-166">**Business Data List** Web Part for the **Finder** method instance.</span></span> <span data-ttu-id="72bb2-167">此 Web 部件，可指定要从 SAP 系统中检索客户列表的搜索表达式。</span><span class="sxs-lookup"><span data-stu-id="72bb2-167">This Web Part enables you to specify a search expression to retrieve a list of customers from the SAP system.</span></span> <span data-ttu-id="72bb2-168">对于本教程中，这被称为搜索客户 Web 部件。</span><span class="sxs-lookup"><span data-stu-id="72bb2-168">For this tutorial, this is called the Search Customers Web Part.</span></span>  
  
- <span data-ttu-id="72bb2-169">**业务数据项**适用于 Web 部件**特定的 Finder**方法实例。</span><span class="sxs-lookup"><span data-stu-id="72bb2-169">**Business Data Item** Web Part for the **Specific Finder** method instance.</span></span> <span data-ttu-id="72bb2-170">此 Web 部件显示您从搜索客户 Web 部件中选择特定客户的详细信息。</span><span class="sxs-lookup"><span data-stu-id="72bb2-170">This Web Part presents the details for a specific customer that you select from the Search Customers Web Part.</span></span> <span data-ttu-id="72bb2-171">此 Web 部件映射到搜索客户 Web 部件。</span><span class="sxs-lookup"><span data-stu-id="72bb2-171">This Web Part is mapped to the Search Customer Web Part.</span></span>  <span data-ttu-id="72bb2-172">对于本教程中，这被称为客户详细信息 Web 部件。</span><span class="sxs-lookup"><span data-stu-id="72bb2-172">For this tutorial, this is called the Customer Details Web Part.</span></span>  
  
- <span data-ttu-id="72bb2-173">**业务数据相关列表**适用于 Web 部件**关联**方法实例。</span><span class="sxs-lookup"><span data-stu-id="72bb2-173">**Business Data Related List** Web Part for the **Association** method instance.</span></span> <span data-ttu-id="72bb2-174">此 Web 部件列出了从搜索客户 Web 部件中选择的特定客户的销售订单。</span><span class="sxs-lookup"><span data-stu-id="72bb2-174">This Web Part lists the sales orders for a specific customer that you select from the Search Customers Web Part.</span></span> <span data-ttu-id="72bb2-175">此 Web 部件是与搜索客户 Web 部件相关联。</span><span class="sxs-lookup"><span data-stu-id="72bb2-175">This Web Part is associated with the Search Customer Web Part.</span></span>  <span data-ttu-id="72bb2-176">对于本教程中，这被称为销售订单详细信息 Web 部件。</span><span class="sxs-lookup"><span data-stu-id="72bb2-176">For this tutorial, this is called the Sales Order Details Web Part.</span></span>  
  
  <span data-ttu-id="72bb2-177">本部分提供的说明来创建这些 Web 部件，并创建它们之间的关联。</span><span class="sxs-lookup"><span data-stu-id="72bb2-177">This section provides instructions to create these Web Parts and to create associations between them.</span></span> <span data-ttu-id="72bb2-178">有关创建 Web 部件的详细信息，请参阅"自定义业务数据列表、 Web 部件和站点"网址[ http://go.microsoft.com/fwlink/?LinkId=104131 ](http://go.microsoft.com/fwlink/?LinkId=104131)。</span><span class="sxs-lookup"><span data-stu-id="72bb2-178">For more information about creating Web Parts, see "Customize business data lists, Web Parts, and sites" at [http://go.microsoft.com/fwlink/?LinkId=104131](http://go.microsoft.com/fwlink/?LinkId=104131).</span></span>  
  
  <span data-ttu-id="72bb2-179">Web 部件将添加到单个 Web 部件页。</span><span class="sxs-lookup"><span data-stu-id="72bb2-179">The Web Parts will be added to a single Web Part page.</span></span> <span data-ttu-id="72bb2-180">必须添加 Web 部件之前创建的 Web 部件页。</span><span class="sxs-lookup"><span data-stu-id="72bb2-180">You must create a Web Part page before adding the Web Parts.</span></span> <span data-ttu-id="72bb2-181">对于本教程中，此 Web 部件页称为 Customer_SalesOrders。</span><span class="sxs-lookup"><span data-stu-id="72bb2-181">For this tutorial, this Web Part page is called Customer_SalesOrders.</span></span>  
  
### <a name="creating-a-web-part-page"></a><span data-ttu-id="72bb2-182">创建 Web 部件页</span><span class="sxs-lookup"><span data-stu-id="72bb2-182">Creating a Web Part Page</span></span>  
 <span data-ttu-id="72bb2-183">本部分介绍如何创建 Web 部件页。</span><span class="sxs-lookup"><span data-stu-id="72bb2-183">This section provides instructions to create a Web Part page.</span></span>  
  
##### <a name="to-create-a-web-part-page"></a><span data-ttu-id="72bb2-184">若要创建的 Web 部件页</span><span class="sxs-lookup"><span data-stu-id="72bb2-184">To create a Web Part page</span></span>  
  
1.  <span data-ttu-id="72bb2-185">启动 SharePoint 3.0 管理中心。</span><span class="sxs-lookup"><span data-stu-id="72bb2-185">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="72bb2-186">单击**启动**，依次指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**。</span><span class="sxs-lookup"><span data-stu-id="72bb2-186">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="72bb2-187">在左侧的导航窗格中，单击你想要导入应用程序定义的 SSP 的名称。</span><span class="sxs-lookup"><span data-stu-id="72bb2-187">In the left navigation pane, click the name of the SSP to which you want to import the application definition.</span></span>  
  
3.  <span data-ttu-id="72bb2-188">在共享服务管理页上，在右上角，单击**站点操作**，然后单击**创建**。</span><span class="sxs-lookup"><span data-stu-id="72bb2-188">On the Shared Services Administration page, in the upper-right corner, click **Site Actions**, and then click **Create**.</span></span>  
  
     <span data-ttu-id="72bb2-189">![若要创建 web 部件的菜单](../../adapters-and-accelerators/adapter-oracle-ebs/media/a9872c3e-f823-4c47-a538-19242565d2e9.gif "a9872c3e-f823-4c47-a538-19242565d2e9")</span><span class="sxs-lookup"><span data-stu-id="72bb2-189">![Menu to create a web part](../../adapters-and-accelerators/adapter-oracle-ebs/media/a9872c3e-f823-4c47-a538-19242565d2e9.gif "a9872c3e-f823-4c47-a538-19242565d2e9")</span></span>  
  
4.  <span data-ttu-id="72bb2-190">在创建页上，在**网页**部分中，单击**Web 部件页**。</span><span class="sxs-lookup"><span data-stu-id="72bb2-190">On the Create page, in the **Web Pages** section, click **Web Part Page**.</span></span>  
  
5.  <span data-ttu-id="72bb2-191">在新的 Web 部件页上，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="72bb2-191">On the New Web Part page, do the following:</span></span>  
  
    1.  <span data-ttu-id="72bb2-192">在中**名称**字段中，键入页面的名称。</span><span class="sxs-lookup"><span data-stu-id="72bb2-192">In the **Name** field, type a name for the page.</span></span> <span data-ttu-id="72bb2-193">对于本教程中，键入作为名称**Customer_SalesOrders**。</span><span class="sxs-lookup"><span data-stu-id="72bb2-193">For this tutorial, type the name as **Customer_SalesOrders**.</span></span>  
  
    2.  <span data-ttu-id="72bb2-194">选择**如果文件已存在，则覆盖**复选框，如果你想要使用相同的名称创建新的页覆盖旧页面。</span><span class="sxs-lookup"><span data-stu-id="72bb2-194">Select the **Overwrite if file already exists** check box, if you want to overwrite old pages with the same name as the new page you create.</span></span>  
  
    3.  <span data-ttu-id="72bb2-195">在中**布局**部分中，从**选择一个布局模板**框中，选择适用于 Web 部件页的布局。</span><span class="sxs-lookup"><span data-stu-id="72bb2-195">In the **Layout** section, from the **Choose a Layout Template** box, select a layout for the Web Part page.</span></span> <span data-ttu-id="72bb2-196">对于本教程中，选择**标头，左侧列中，正文**。</span><span class="sxs-lookup"><span data-stu-id="72bb2-196">For this tutorial, select **Header, Left Column, Body**.</span></span>  
  
    4.  <span data-ttu-id="72bb2-197">在中**保存位置**部分中，在**文档库**列表中，单击**窗体模板**。</span><span class="sxs-lookup"><span data-stu-id="72bb2-197">In the **Save Location** section, in the **Document Library** list, click **Form Templates**.</span></span>  
  
    5.  <span data-ttu-id="72bb2-198">单击 **“创建”**。</span><span class="sxs-lookup"><span data-stu-id="72bb2-198">Click **Create**.</span></span> <span data-ttu-id="72bb2-199">只需创建后下, 图显示的 Web 部件页。</span><span class="sxs-lookup"><span data-stu-id="72bb2-199">The following figure shows a Web Part page after it is just created.</span></span>  
  
         <span data-ttu-id="72bb2-200">![空 Web 部件页](../../adapters-and-accelerators/adapter-sap/media/6aa68c43-59df-47c4-95a6-453f7c668025.gif "6aa68c43-59df-47c4-95a6-453f7c668025")</span><span class="sxs-lookup"><span data-stu-id="72bb2-200">![Empty Web Part page](../../adapters-and-accelerators/adapter-sap/media/6aa68c43-59df-47c4-95a6-453f7c668025.gif "6aa68c43-59df-47c4-95a6-453f7c668025")</span></span>  
  
    6.  <span data-ttu-id="72bb2-201">您现在必须将不同的 Web 部件添加到此页。</span><span class="sxs-lookup"><span data-stu-id="72bb2-201">You must now add the different Web Parts to this page.</span></span>  
  
### <a name="adding-a-business-data-list-web-part"></a><span data-ttu-id="72bb2-202">添加业务数据列表 Web 部件</span><span class="sxs-lookup"><span data-stu-id="72bb2-202">Adding a Business Data List Web Part</span></span>  
 <span data-ttu-id="72bb2-203">现在，你必须将业务数据列表 Web 部件添加到 Web 部件页。</span><span class="sxs-lookup"><span data-stu-id="72bb2-203">You must now add a Business Data List Web Part to the Web Part page.</span></span> <span data-ttu-id="72bb2-204">使用此 Web 部件将从 SAP 系统相匹配的搜索表达式检索客户列表。</span><span class="sxs-lookup"><span data-stu-id="72bb2-204">Using this Web Part you will retrieve a list of customers from the SAP system that matches a search expression.</span></span> <span data-ttu-id="72bb2-205">此 Web 部件对应于**Finder**方法实例 (*GetCustomerByName_Instance*) 创建在 Business Data Catalog Definition Editor。</span><span class="sxs-lookup"><span data-stu-id="72bb2-205">This Web Part corresponds to the **Finder** method instance (*GetCustomerByName_Instance*) that you created in the Business Data Catalog Definition Editor.</span></span>  
  
##### <a name="to-add-a-business-data-list-web-part"></a><span data-ttu-id="72bb2-206">若要添加业务数据列表 Web 部件</span><span class="sxs-lookup"><span data-stu-id="72bb2-206">To add a Business Data List Web Part</span></span>  
  
1.  <span data-ttu-id="72bb2-207">在 Customer_SalesOrders 页上，在**标头**部分中，单击**添加 Web 部件**。</span><span class="sxs-lookup"><span data-stu-id="72bb2-207">On the Customer_SalesOrders page, in the **Header** section, click **Add a Web Part**.</span></span>  
  
2.  <span data-ttu-id="72bb2-208">在中**添加 Web 部件**对话框中**业务数据**部分中，选择**业务数据列表**复选框，然后依次**添加**。</span><span class="sxs-lookup"><span data-stu-id="72bb2-208">In the **Add Web Parts** dialog box, in the **Business Data** section, select the **Business Data List** check box, and then click **Add**.</span></span>  
  
     <span data-ttu-id="72bb2-209">![创建业务数据 Web 部件的选项](../../adapters-and-accelerators/adapter-oracle-ebs/media/ae7c952c-1592-495f-9452-c1bffd44421c.gif "ae7c952c-1592-495f-9452-c1bffd44421c")</span><span class="sxs-lookup"><span data-stu-id="72bb2-209">![Options to create a business data Web Part](../../adapters-and-accelerators/adapter-oracle-ebs/media/ae7c952c-1592-495f-9452-c1bffd44421c.gif "ae7c952c-1592-495f-9452-c1bffd44421c")</span></span>  
  
3.  <span data-ttu-id="72bb2-210">在新添加的业务数据列表 Web 部件，单击**打开工具窗格**链接。</span><span class="sxs-lookup"><span data-stu-id="72bb2-210">In the newly added Business Data List Web Part, click the **Open the tool pane** link.</span></span>  
  
     <span data-ttu-id="72bb2-211">![Web 部件中打开工具窗格](../../adapters-and-accelerators/adapter-oracle-ebs/media/4e7a1cb1-69dc-4e0d-a211-6a217dc4a549.gif "4e7a1cb1-69dc-4e0d-a211-6a217dc4a549")</span><span class="sxs-lookup"><span data-stu-id="72bb2-211">![Open the tool pane for Web Part](../../adapters-and-accelerators/adapter-oracle-ebs/media/4e7a1cb1-69dc-4e0d-a211-6a217dc4a549.gif "4e7a1cb1-69dc-4e0d-a211-6a217dc4a549")</span></span>  
  
4.  <span data-ttu-id="72bb2-212">业务数据列表工具窗格将在右窗格中打开。</span><span class="sxs-lookup"><span data-stu-id="72bb2-212">The Business Data List tool pane opens in the right pane.</span></span> <span data-ttu-id="72bb2-213">在中**业务数据列表**部分中，对于**类型**字段中，单击**浏览**按钮。</span><span class="sxs-lookup"><span data-stu-id="72bb2-213">In the **Business Data List** section, for the **Type** field, click the **Browse** button.</span></span>  
  
     <span data-ttu-id="72bb2-214">![业务数据列表工具窗格](../../adapters-and-accelerators/adapter-sap/media/580c58bf-bfc7-4d48-8c62-8ca4eee4ab48.gif "580c58bf-bfc7-4d48-8c62-8ca4eee4ab48")</span><span class="sxs-lookup"><span data-stu-id="72bb2-214">![Business Data List tool pane](../../adapters-and-accelerators/adapter-sap/media/580c58bf-bfc7-4d48-8c62-8ca4eee4ab48.gif "580c58bf-bfc7-4d48-8c62-8ca4eee4ab48")</span></span>  
  
5.  <span data-ttu-id="72bb2-215">在中**业务数据类型选取器**对话框中，选择**Customer_Order_Instance**应用程序，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="72bb2-215">In the **Business Data Type Picker** dialog box, select the **Customer_Order_Instance** application, and then click **OK**.</span></span>  
  
     <span data-ttu-id="72bb2-216">![选择应用程序实例](../../adapters-and-accelerators/adapter-sap/media/79967c27-9c76-4394-89bc-38c63649bdda.gif "79967c27-9c76-4394-89bc-38c63649bdda")</span><span class="sxs-lookup"><span data-stu-id="72bb2-216">![Select the application instance](../../adapters-and-accelerators/adapter-sap/media/79967c27-9c76-4394-89bc-38c63649bdda.gif "79967c27-9c76-4394-89bc-38c63649bdda")</span></span>  
  
6.  <span data-ttu-id="72bb2-217">展开**外观**节点，然后在**标题**框中，键入 Web 部件的标题。</span><span class="sxs-lookup"><span data-stu-id="72bb2-217">Expand the **Appearance** node, and in the **Title** box, type a title for the Web Part.</span></span> <span data-ttu-id="72bb2-218">为此 Web 部件中，键入**客户列表**。</span><span class="sxs-lookup"><span data-stu-id="72bb2-218">For this Web Part, type **Customer List**.</span></span>  
  
7.  <span data-ttu-id="72bb2-219">在业务数据列表工具窗格中，单击**Apply**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="72bb2-219">In the Business Data List tool pane, click **Apply**, and then click **OK**.</span></span> <span data-ttu-id="72bb2-220">业务数据列表 Web 部件现在看起来如下所示：</span><span class="sxs-lookup"><span data-stu-id="72bb2-220">The Business Data List Web Part now looks like the following:</span></span>  
  
     <span data-ttu-id="72bb2-221">![业务数据列表 Web 部件](../../adapters-and-accelerators/adapter-sap/media/185fb3f3-98b0-4efe-960d-91312912ad7d.gif "185fb3f3-98b0-4efe-960d-91312912ad7d")</span><span class="sxs-lookup"><span data-stu-id="72bb2-221">![Business Data List Web Part](../../adapters-and-accelerators/adapter-sap/media/185fb3f3-98b0-4efe-960d-91312912ad7d.gif "185fb3f3-98b0-4efe-960d-91312912ad7d")</span></span>  
  
8.  <span data-ttu-id="72bb2-222">Web 部件列出了通过执行 SD_RFC_CUSTOMER_GET RFC 返回的字段。</span><span class="sxs-lookup"><span data-stu-id="72bb2-222">The Web Part lists the fields that are returned by executing the SD_RFC_CUSTOMER_GET RFC.</span></span> <span data-ttu-id="72bb2-223">可以删除不想要在 SharePoint 门户上显示的字段。</span><span class="sxs-lookup"><span data-stu-id="72bb2-223">You can remove the fields that you do not want to display on the SharePoint portal.</span></span> <span data-ttu-id="72bb2-224">若要删除字段，请单击**编辑视图**Web 部件右上角中的链接。</span><span class="sxs-lookup"><span data-stu-id="72bb2-224">To remove the fields, click the **Edit View** link in the upper-right corner of the Web Part.</span></span>  
  
9. <span data-ttu-id="72bb2-225">在编辑视图页上的列部分中，清除针对不想要显示的列的复选框。</span><span class="sxs-lookup"><span data-stu-id="72bb2-225">On the Edit View page, in the Columns section, clear the check boxes against the columns that you do not want to display.</span></span>  
  
     <span data-ttu-id="72bb2-226">![在 SharePoint 中查看特定的列](../../adapters-and-accelerators/adapter-sap/media/24213b67-aafe-4534-91a7-06bde7bcbf7c.gif "24213b67-aafe-4534-91a7-06bde7bcbf7c")</span><span class="sxs-lookup"><span data-stu-id="72bb2-226">![View specific columns in SharePoint](../../adapters-and-accelerators/adapter-sap/media/24213b67-aafe-4534-91a7-06bde7bcbf7c.gif "24213b67-aafe-4534-91a7-06bde7bcbf7c")</span></span>  
  
10. <span data-ttu-id="72bb2-227">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="72bb2-227">Click **OK**.</span></span>  
  
### <a name="adding-a-business-data-item-web-part"></a><span data-ttu-id="72bb2-228">添加业务数据项 Web 部件</span><span class="sxs-lookup"><span data-stu-id="72bb2-228">Adding a Business Data Item Web Part</span></span>  
 <span data-ttu-id="72bb2-229">您现在必须将业务数据项 Web 部件添加到 Web 部件页。</span><span class="sxs-lookup"><span data-stu-id="72bb2-229">You must now add a Business Data Item Web Part to the Web Part page.</span></span> <span data-ttu-id="72bb2-230">您还将此 Web 部件连接到刚创建的业务数据列表 Web 部件中。</span><span class="sxs-lookup"><span data-stu-id="72bb2-230">You will also connect this Web Part to the Business Data List Web Part that you just created.</span></span> <span data-ttu-id="72bb2-231">这样，您将能够查看业务数据列表 Web 部件中选择的客户的详细信息。</span><span class="sxs-lookup"><span data-stu-id="72bb2-231">By doing so, you will be able to see the details for a customer that you select in the Business Data List Web Part.</span></span> <span data-ttu-id="72bb2-232">此 Web 部件对应于**特定的 Finder**方法实例 (*GetCustomerByNumber_Instance*) 创建在 Business Data Catalog Definition Editor。</span><span class="sxs-lookup"><span data-stu-id="72bb2-232">This Web Part corresponds to the **Specific Finder** method instance (*GetCustomerByNumber_Instance*) that you created in the Business Data Catalog Definition Editor.</span></span>  
  
##### <a name="to-add-a-business-data-item-web-part"></a><span data-ttu-id="72bb2-233">若要添加业务数据项 Web 部件</span><span class="sxs-lookup"><span data-stu-id="72bb2-233">To add a Business Data Item Web Part</span></span>  
  
1.  <span data-ttu-id="72bb2-234">在 Customer_SalesOrders 页上，在右上角，单击**站点操作**，然后单击**编辑页面**。</span><span class="sxs-lookup"><span data-stu-id="72bb2-234">On the Customer_SalesOrders page, in the upper-right corner, click **Site Actions**, and then click **Edit Page**.</span></span>  
  
2.  <span data-ttu-id="72bb2-235">在 Customer_SalesOrders 页上，在**左侧列**部分中，单击**添加 Web 部件**。</span><span class="sxs-lookup"><span data-stu-id="72bb2-235">On the Customer_SalesOrders page, in the **Left Column** section, click **Add a Web Part**.</span></span>  
  
3.  <span data-ttu-id="72bb2-236">在中**添加 Web 部件**对话框中**业务数据**部分中，选择**业务数据项**复选框，然后依次**添加**。</span><span class="sxs-lookup"><span data-stu-id="72bb2-236">In the **Add Web Parts** dialog box, in the **Business Data** section, select the **Business Data Item** check box, and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="72bb2-237">在新添加的业务数据项 Web 部件，单击**打开工具窗格**链接。</span><span class="sxs-lookup"><span data-stu-id="72bb2-237">In the newly added Business Data Item Web Part, click the **Open the tool pane** link.</span></span>  
  
5.  <span data-ttu-id="72bb2-238">在右窗格中打开业务数据项工具窗格。</span><span class="sxs-lookup"><span data-stu-id="72bb2-238">The Business Data Item tool pane opens in the right pane.</span></span> <span data-ttu-id="72bb2-239">在中**业务数据项**部分中，对于**类型**字段中，单击**浏览**按钮。</span><span class="sxs-lookup"><span data-stu-id="72bb2-239">In the **Business Data Item** section, for the **Type** field, click the **Browse** button.</span></span>  
  
     <span data-ttu-id="72bb2-240">![业务数据项工具窗格](../../adapters-and-accelerators/adapter-sap/media/29322df5-4ce3-4c1f-a658-39a355dfe2aa.gif "29322df5-4ce3-4c1f-a658-39a355dfe2aa")</span><span class="sxs-lookup"><span data-stu-id="72bb2-240">![Business Data Item tool pane](../../adapters-and-accelerators/adapter-sap/media/29322df5-4ce3-4c1f-a658-39a355dfe2aa.gif "29322df5-4ce3-4c1f-a658-39a355dfe2aa")</span></span>  
  
6.  <span data-ttu-id="72bb2-241">在中**业务数据类型选取器**对话框中，选择**Customer_Order_Instance**应用程序，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="72bb2-241">In the **Business Data Type Picker** dialog box, select the **Customer_Order_Instance** application, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="72bb2-242">在中**视图**列表中，选择**默认**。</span><span class="sxs-lookup"><span data-stu-id="72bb2-242">In the **View** list, select **Default**.</span></span>  
  
8.  <span data-ttu-id="72bb2-243">将保留**项**列表为空。</span><span class="sxs-lookup"><span data-stu-id="72bb2-243">Leave the **Item** list empty.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="72bb2-244">有关**项**字段中，必须指定一个客户名称或你想要查看的详细信息的客户编号。</span><span class="sxs-lookup"><span data-stu-id="72bb2-244">For the **Item** field, you must specify a customer name or customer number for which you want to see the details.</span></span> <span data-ttu-id="72bb2-245">为此 Web 部件可用作输入参数。</span><span class="sxs-lookup"><span data-stu-id="72bb2-245">That serves as an input parameter for this Web Part.</span></span> <span data-ttu-id="72bb2-246">您将通过连接到业务数据列表 Web 部件来获得的输入的参数，因为您无需显式指定项。</span><span class="sxs-lookup"><span data-stu-id="72bb2-246">Because you will be getting the input parameter by connecting to the Business Data List Web Part, you need not specify an item explicitly.</span></span>  
  
9. <span data-ttu-id="72bb2-247">在中**字段**部分中，单击**选择**以选择想要在页面上显示的字段。</span><span class="sxs-lookup"><span data-stu-id="72bb2-247">In the **Fields** section, click **Choose** to select the fields you want to display on the page.</span></span>  
  
10. <span data-ttu-id="72bb2-248">展开**外观**节点，然后在**标题**字段中，指定 Web 部件的标题。</span><span class="sxs-lookup"><span data-stu-id="72bb2-248">Expand the **Appearance** node, and in the **Title** field, specify a title for the Web Part.</span></span> <span data-ttu-id="72bb2-249">对于此 Web 部件，指定**特定客户的详细信息**。</span><span class="sxs-lookup"><span data-stu-id="72bb2-249">For this Web Part, specify **Details for a Specific Customer**.</span></span>  
  
11. <span data-ttu-id="72bb2-250">单击**Apply**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="72bb2-250">Click **Apply**, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="72bb2-251">连接到 Web 部件**客户列表**Web 部件。</span><span class="sxs-lookup"><span data-stu-id="72bb2-251">Connect the Web Part to the **Customer List** Web Part.</span></span> <span data-ttu-id="72bb2-252">为此：</span><span class="sxs-lookup"><span data-stu-id="72bb2-252">To do so:</span></span>  
  
    1.  <span data-ttu-id="72bb2-253">单击**编辑**向 Web 部件右上角。</span><span class="sxs-lookup"><span data-stu-id="72bb2-253">Click **edit** towards the upper-right corner of the Web Part.</span></span>  
  
    2.  <span data-ttu-id="72bb2-254">从上下文菜单上指向**连接**，依次指向**获取项从**，然后单击**客户列表**。</span><span class="sxs-lookup"><span data-stu-id="72bb2-254">From the context menu point to **Connections**, point to **Get Item From**, and click **Customer List**.</span></span>  
  
         <span data-ttu-id="72bb2-255">![连接两个 Web 部件](../../adapters-and-accelerators/adapter-sap/media/505aead7-f498-448f-a7cb-55d0a121f91f.gif "505aead7-f498-448f-a7cb-55d0a121f91f")</span><span class="sxs-lookup"><span data-stu-id="72bb2-255">![Connect two Web Parts](../../adapters-and-accelerators/adapter-sap/media/505aead7-f498-448f-a7cb-55d0a121f91f.gif "505aead7-f498-448f-a7cb-55d0a121f91f")</span></span>  
  
### <a name="adding-a-business-data-related-list-web-part"></a><span data-ttu-id="72bb2-256">添加业务数据相关列表 Web 部件</span><span class="sxs-lookup"><span data-stu-id="72bb2-256">Adding a Business Data Related List Web Part</span></span>  
 <span data-ttu-id="72bb2-257">现在，您必须将业务数据相关列表 Web 部件添加到 Web 部件页。</span><span class="sxs-lookup"><span data-stu-id="72bb2-257">You must now add a Business Data Related List Web Part to the Web Part page.</span></span> <span data-ttu-id="72bb2-258">此外会将此 Web 部件连接到前面创建的业务数据列表 Web 部件。</span><span class="sxs-lookup"><span data-stu-id="72bb2-258">You will also connect this Web Part to the Business Data List Web Part you created earlier.</span></span> <span data-ttu-id="72bb2-259">这样，您将能够查看业务数据列表 Web 部件中选择的客户的销售订单。</span><span class="sxs-lookup"><span data-stu-id="72bb2-259">By doing so, you will be able to see the sales orders for a customer that you select in the Business Data List Web Part.</span></span> <span data-ttu-id="72bb2-260">此 Web 部件对应于**关联**方法实例 (*SalesOrderForCustomer_Instance*) 创建在 Business Data Catalog Definition Editor。</span><span class="sxs-lookup"><span data-stu-id="72bb2-260">This Web Part corresponds to the **Association** method instance (*SalesOrderForCustomer_Instance*) you created in the Business Data Catalog Definition Editor.</span></span>  
  
##### <a name="to-add-a-business-data-related-list-web-part"></a><span data-ttu-id="72bb2-261">添加业务数据相关列表 Web 部件</span><span class="sxs-lookup"><span data-stu-id="72bb2-261">To add a Business Data Related List Web Part</span></span>  
  
1.  <span data-ttu-id="72bb2-262">在 Customer_SalesOrders 页上，在**正文**部分中，单击**添加 Web 部件**。</span><span class="sxs-lookup"><span data-stu-id="72bb2-262">On the Customer_SalesOrders page, in the **Body** section, click **Add a Web Part**.</span></span>  
  
2.  <span data-ttu-id="72bb2-263">在中**添加 Web 部件**对话框中**业务数据**部分中，选择**业务数据相关列表**复选框，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="72bb2-263">In the **Add Web Parts** dialog box, in the **Business Data** section, select the **Business Data Related List** check box, and click **Add**.</span></span>  
  
3.  <span data-ttu-id="72bb2-264">在新添加的业务数据相关列表 Web 部件中，单击**打开工具窗格**链接。</span><span class="sxs-lookup"><span data-stu-id="72bb2-264">In the newly added Business Data Related List Web Part, click the **Open the tool pane** link.</span></span>  
  
4.  <span data-ttu-id="72bb2-265">业务数据相关列表工具窗格将在右窗格中打开。</span><span class="sxs-lookup"><span data-stu-id="72bb2-265">The Business Data Related List tool pane opens in the right pane.</span></span> <span data-ttu-id="72bb2-266">在中**业务数据相关列表**部分中，对于**类型**字段中，单击**浏览**按钮。</span><span class="sxs-lookup"><span data-stu-id="72bb2-266">In the **Business Data Related List** section, for the **Type** field, click the **Browse** button.</span></span>  
  
     <span data-ttu-id="72bb2-267">![业务数据相关列表](../../adapters-and-accelerators/adapter-sap/media/1914e12d-27f0-4ecb-9605-3177183a2d44.gif "1914e12d-27f0-4ecb-9605-3177183a2d44")</span><span class="sxs-lookup"><span data-stu-id="72bb2-267">![Business Data Related List](../../adapters-and-accelerators/adapter-sap/media/1914e12d-27f0-4ecb-9605-3177183a2d44.gif "1914e12d-27f0-4ecb-9605-3177183a2d44")</span></span>  
  
5.  <span data-ttu-id="72bb2-268">在中**业务数据类型选取器**对话框中，选择**Customer_Order_Instance**应用程序，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="72bb2-268">In the **Business Data Type Picker** dialog box, select the **Customer_Order_Instance** application, and then click **OK**.</span></span> <span data-ttu-id="72bb2-269">**关系**列表的名称填充**关联**方法实例 (*SalesOrderForCustomer_Instance*)。</span><span class="sxs-lookup"><span data-stu-id="72bb2-269">The **Relationship** list populates with the name of the **Association** method instance (*SalesOrderForCustomer_Instance*).</span></span>  
  
6.  <span data-ttu-id="72bb2-270">展开**外观**节点，然后在**标题**框中，键入 Web 部件的标题。</span><span class="sxs-lookup"><span data-stu-id="72bb2-270">Expand the **Appearance** node, and in the **Title** box, type a title for the Web Part.</span></span> <span data-ttu-id="72bb2-271">为此 Web 部件中，键入**特定客户的销售订单**。</span><span class="sxs-lookup"><span data-stu-id="72bb2-271">For this Web Part, type **Sales Order for a Specific Customer**.</span></span>  
  
7.  <span data-ttu-id="72bb2-272">单击**Apply**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="72bb2-272">Click **Apply**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="72bb2-273">Web 部件列出了通过执行 BAPI_SALESORDER_GETLIST RFC 返回的字段。</span><span class="sxs-lookup"><span data-stu-id="72bb2-273">The Web Part lists the fields that are returned by executing the BAPI_SALESORDER_GETLIST RFC.</span></span> <span data-ttu-id="72bb2-274">可以删除不想要在 SharePoint 门户上显示的字段。</span><span class="sxs-lookup"><span data-stu-id="72bb2-274">You can remove the fields that you do not want to display on the SharePoint portal.</span></span> <span data-ttu-id="72bb2-275">若要删除字段，请单击**编辑视图**Web 部件右上角中的链接。</span><span class="sxs-lookup"><span data-stu-id="72bb2-275">To remove the fields, click the **Edit View** link in the upper-right corner of the Web Part.</span></span>  
  
9. <span data-ttu-id="72bb2-276">在编辑视图页上，在**列**部分中，清除针对不想要显示的列文本框。</span><span class="sxs-lookup"><span data-stu-id="72bb2-276">On the Edit View page, in the **Columns** section, clear the text boxes against the columns that you do not want to display.</span></span>  
  
10. <span data-ttu-id="72bb2-277">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="72bb2-277">Click **OK**.</span></span>  
  
11. <span data-ttu-id="72bb2-278">连接到 Web 部件**客户列表**Web 部件。</span><span class="sxs-lookup"><span data-stu-id="72bb2-278">Connect the Web Part to the **Customer List** Web Part.</span></span> <span data-ttu-id="72bb2-279">为此：</span><span class="sxs-lookup"><span data-stu-id="72bb2-279">To do so:</span></span>  
  
    1.  <span data-ttu-id="72bb2-280">单击**编辑**针对的右上角**特定客户的销售订单**Web 部件。</span><span class="sxs-lookup"><span data-stu-id="72bb2-280">Click **edit** towards the upper-right corner of the **Sales Order for a Specific Customer** Web Part.</span></span>  
  
    2.  <span data-ttu-id="72bb2-281">从上下文菜单中，指向**连接**，依次指向**获取相关项从**，然后单击**客户列表**。</span><span class="sxs-lookup"><span data-stu-id="72bb2-281">From the context menu, point to **Connections**, point to **Get Related Item From**, and then click **Customer List**.</span></span>  
  
12. <span data-ttu-id="72bb2-282">单击**退出编辑模式**从页面的右上角。</span><span class="sxs-lookup"><span data-stu-id="72bb2-282">Click **Exit Edit Mode** from the upper-right corner of the page.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="72bb2-283">后续步骤</span><span class="sxs-lookup"><span data-stu-id="72bb2-283">Next Steps</span></span>  
 <span data-ttu-id="72bb2-284">通过从 SAP 系统中检索数据来测试 SharePoint 应用程序。</span><span class="sxs-lookup"><span data-stu-id="72bb2-284">Test the SharePoint application by retrieving data from an SAP system.</span></span> <span data-ttu-id="72bb2-285">请参阅[步骤 4： 测试 SharePoint 应用程序](../../adapters-and-accelerators/adapter-sap/step-4-test-your-sharepoint-application1.md)。</span><span class="sxs-lookup"><span data-stu-id="72bb2-285">See [Step 4: Test Your SharePoint Application](../../adapters-and-accelerators/adapter-sap/step-4-test-your-sharepoint-application1.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72bb2-286">请参阅</span><span class="sxs-lookup"><span data-stu-id="72bb2-286">See Also</span></span>  
 [<span data-ttu-id="72bb2-287">教程 1：在 SharePoint 上提供来自 SAP 系统的数据</span><span class="sxs-lookup"><span data-stu-id="72bb2-287">Tutorial 1: Presenting Data from an SAP System on a SharePoint Site</span></span>](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md)