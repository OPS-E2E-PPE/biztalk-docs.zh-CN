---
title: "步骤 3： 创建 SharePoint 应用程序从 SAP 检索数据 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 879a4b48da7645471e53db357f7c0a6260117f99
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-create-a-sharepoint-application-to-retrieve-data-from-sap"></a><span data-ttu-id="0ec71-102">步骤 3： 创建 SharePoint 应用程序从 SAP 检索数据</span><span class="sxs-lookup"><span data-stu-id="0ec71-102">Step 3: Create a SharePoint Application to Retrieve Data from SAP</span></span>
<span data-ttu-id="0ec71-103">![步骤 3 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span><span class="sxs-lookup"><span data-stu-id="0ec71-103">![Step 3 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span></span>  
  
 <span data-ttu-id="0ec71-104">**完成时间：** 15 分钟</span><span class="sxs-lookup"><span data-stu-id="0ec71-104">**Time to complete:** 15 minutes</span></span>  
  
 <span data-ttu-id="0ec71-105">**目标：**现在必须采用使用业务数据目录定义编辑器工具创建的应用程序定义文件，并将其导入 Microsoft Office SharePoint Server。</span><span class="sxs-lookup"><span data-stu-id="0ec71-105">**Objective:** You must now take the application definition file that you created by using the Business Data Catalog Definition Editor tool, and import it into Microsoft Office SharePoint Server.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0ec71-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="0ec71-106">Prerequisites</span></span>  
  
-   <span data-ttu-id="0ec71-107">您将会创建应用程序定义文件中所述[步骤 2： 为 SAP 项目创建应用程序定义文件](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="0ec71-107">You should have created an application definition file as described in [Step 2: Create an Application Definition File for the SAP Artifacts](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md).</span></span>  
  
-   <span data-ttu-id="0ec71-108">必须运行 Microsoft 单一登录服务。</span><span class="sxs-lookup"><span data-stu-id="0ec71-108">The Microsoft Single Sign-on service must be running.</span></span>  
  
## <a name="how-to-create-a-sharepoint-application"></a><span data-ttu-id="0ec71-109">如何创建一个 SharePoint 应用程序</span><span class="sxs-lookup"><span data-stu-id="0ec71-109">How to Create a SharePoint Application</span></span>  
 <span data-ttu-id="0ec71-110">创建 SharePoint 应用程序涉及以下步骤：</span><span class="sxs-lookup"><span data-stu-id="0ec71-110">Creating a SharePoint application involves the following steps:</span></span>  
  
-   <span data-ttu-id="0ec71-111">在 SharePoint 中创建的单一登录 (SSO) 应用程序</span><span class="sxs-lookup"><span data-stu-id="0ec71-111">Create a single sign-on (SSO) application in SharePoint</span></span>  
  
-   <span data-ttu-id="0ec71-112">创建共享服务提供程序</span><span class="sxs-lookup"><span data-stu-id="0ec71-112">Create a Shared Services provider</span></span>  
  
-   <span data-ttu-id="0ec71-113">导入应用程序定义文件</span><span class="sxs-lookup"><span data-stu-id="0ec71-113">Import the application definition file</span></span>  
  
-   <span data-ttu-id="0ec71-114">创建 Web 部件页，并添加 Web 部件</span><span class="sxs-lookup"><span data-stu-id="0ec71-114">Create a Web Part page, and add Web Parts</span></span>  
  
 <span data-ttu-id="0ec71-115">本主题演示如何执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="0ec71-115">This topic demonstrates how to perform these steps.</span></span>  
  
## <a name="creating-an-sso-application-in-sharepoint"></a><span data-ttu-id="0ec71-116">在 SharePoint 中创建 SSO 应用程序</span><span class="sxs-lookup"><span data-stu-id="0ec71-116">Creating an SSO Application in SharePoint</span></span>  
 <span data-ttu-id="0ec71-117">若要访问 SAP 系统从 SharePoint 应用程序中的数据，必须设置的 SSO 应用程序将 SharePoint 用户映射到 SAP 用户。</span><span class="sxs-lookup"><span data-stu-id="0ec71-117">To access the data in an SAP system from a SharePoint application, you must set up an SSO application that maps a SharePoint user to an SAP user.</span></span> <span data-ttu-id="0ec71-118">在 SharePoint 中创建 SSO 应用程序涉及以下步骤：</span><span class="sxs-lookup"><span data-stu-id="0ec71-118">Creating an SSO application in SharePoint involves the following steps:</span></span>  
  
1.  <span data-ttu-id="0ec71-119">**管理服务器上单一登录设置**。</span><span class="sxs-lookup"><span data-stu-id="0ec71-119">**Manage server settings for single sign-on**.</span></span> <span data-ttu-id="0ec71-120">在此步骤中，你可以指定可以管理和设置单一登录服务的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="0ec71-120">In this step, you specify a user account that can manage and set up the single sign-on service.</span></span> <span data-ttu-id="0ec71-121">你可以在管理服务器设置页上执行操作。</span><span class="sxs-lookup"><span data-stu-id="0ec71-121">You can do so on the Manage Server Settings page.</span></span> <span data-ttu-id="0ec71-122">此选项才可用从 SharePoint 管理中心控制台。</span><span class="sxs-lookup"><span data-stu-id="0ec71-122">This option is available from the SharePoint Central Administration console.</span></span> <span data-ttu-id="0ec71-123">有关此步骤的详细信息，请参阅"配置单一登录的 Office SharePoint Server 2007"部分在[http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291)。</span><span class="sxs-lookup"><span data-stu-id="0ec71-123">For more information about this step, refer to the “Configure Single Sign-On for Office SharePoint Server 2007” section at [http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291).</span></span>  
  
2.  <span data-ttu-id="0ec71-124">**管理企业应用程序定义的设置**。</span><span class="sxs-lookup"><span data-stu-id="0ec71-124">**Manage settings for enterprise application definitions**.</span></span> <span data-ttu-id="0ec71-125">在此步骤中，你配置的企业应用程序定义的设置。</span><span class="sxs-lookup"><span data-stu-id="0ec71-125">In this step, you configure the settings for the enterprise application definition.</span></span> <span data-ttu-id="0ec71-126">你可以从企业应用程序定义页面的管理设置来实现。</span><span class="sxs-lookup"><span data-stu-id="0ec71-126">You can do so from the Manage Settings for Enterprise Application Definitions page.</span></span> <span data-ttu-id="0ec71-127">此选项才可用从 SharePoint 管理中心控制台。</span><span class="sxs-lookup"><span data-stu-id="0ec71-127">This option is available from the SharePoint Central Administration console.</span></span>  
  
    1.  <span data-ttu-id="0ec71-128">在管理中心内，在顶部导航栏上，单击**操作**。</span><span class="sxs-lookup"><span data-stu-id="0ec71-128">On Central Administration, on the top navigation bar, click **Operations**.</span></span>  
  
    2.  <span data-ttu-id="0ec71-129">在操作页面中**安全配置**部分中，单击**管理单一登录设置**。</span><span class="sxs-lookup"><span data-stu-id="0ec71-129">On the Operations page, in the **Security Configuration** section, click  **Manage settings for single sign-on**.</span></span>  
  
    3.  <span data-ttu-id="0ec71-130">单一登录页的管理设置中**企业应用程序定义设置**部分中，单击**管理企业应用程序定义的设置**。</span><span class="sxs-lookup"><span data-stu-id="0ec71-130">On the Manage Settings for Single Sign-On page, in the **Enterprise Application Definition Settings** section, click **Manage settings for enterprise application definitions**.</span></span>  
  
    4.  <span data-ttu-id="0ec71-131">在管理企业应用程序定义页上，提供的值**显示名称**，**应用程序名称**，和**联系人电子邮件地址**字段。</span><span class="sxs-lookup"><span data-stu-id="0ec71-131">On the Manage Enterprise Application Definitions page, provide values for the **Display name**, **Application name**, and the **Contact e-mail address** fields.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="0ec71-132">有关**应用程序名称**字段中，请确保指定相同为指定的 SSO 应用程序名称**SecondarySsoApplicationId**时创建应用程序定义文件中，将其作为变量中所述[步骤 2： 为 SAP 项目创建应用程序定义文件](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="0ec71-132">For the **Application name** field, make sure you specify the same SSO application name that you specified for the **SecondarySsoApplicationId** variable while creating the application definition file, as described in [Step 2: Create an Application Definition File for the SAP Artifacts](../../adapters-and-accelerators/adapter-sap/step-2-create-an-application-definition-file-for-the-sap-artifacts.md).</span></span>  
  
    5.  <span data-ttu-id="0ec71-133">将其他字段保留为默认值，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0ec71-133">Leave the other fields as default, and click **OK**.</span></span>  
  
3.  <span data-ttu-id="0ec71-134">**管理企业应用程序定义的帐户信息**。</span><span class="sxs-lookup"><span data-stu-id="0ec71-134">**Manage account information for enterprise application definitions**.</span></span> <span data-ttu-id="0ec71-135">在此步骤中，你可以启用从 SharePoint 连接到企业应用程序的单个用户或组。</span><span class="sxs-lookup"><span data-stu-id="0ec71-135">In this step, you enable individual users or groups to connect to an enterprise application from SharePoint.</span></span> <span data-ttu-id="0ec71-136">实质上，在此步骤中你映射单个用户或组的用户在 LOB 系统。</span><span class="sxs-lookup"><span data-stu-id="0ec71-136">Essentially, in this step you map an individual user or group to a user in the LOB system.</span></span> <span data-ttu-id="0ec71-137">你还可以指定要连接到 LOB 系统的凭据。</span><span class="sxs-lookup"><span data-stu-id="0ec71-137">You also specify the credentials to connect to the LOB system.</span></span> <span data-ttu-id="0ec71-138">你可以从企业应用程序定义页的管理帐户信息来实现。</span><span class="sxs-lookup"><span data-stu-id="0ec71-138">You can do so from the Manage Account Information for Enterprise Application Definitions page.</span></span> <span data-ttu-id="0ec71-139">此选项才可用从 SharePoint 管理中心控制台。</span><span class="sxs-lookup"><span data-stu-id="0ec71-139">This option is available from the SharePoint Central Administration console.</span></span> <span data-ttu-id="0ec71-140">有关此步骤的详细信息，请参阅"管理企业应用程序定义的帐户信息"部分在[http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291)。</span><span class="sxs-lookup"><span data-stu-id="0ec71-140">For more information about this step, refer to the “Manage account information for an enterprise application definition” section at [http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291).</span></span>  
  
## <a name="creating-a-shared-services-provider"></a><span data-ttu-id="0ec71-141">创建共享的服务提供程序</span><span class="sxs-lookup"><span data-stu-id="0ec71-141">Creating a Shared Services Provider</span></span>  
 <span data-ttu-id="0ec71-142">共享的服务提供程序是共享的服务和其支持的资源的逻辑分组。</span><span class="sxs-lookup"><span data-stu-id="0ec71-142">A Shared Service Provider is a logical grouping of shared services and their supporting resources.</span></span> <span data-ttu-id="0ec71-143">可以通过使用 SharePoint 管理中心控制台来创建一个 SSP。</span><span class="sxs-lookup"><span data-stu-id="0ec71-143">You can create an SSP by using the SharePoint Central Administration console.</span></span>  
  
 <span data-ttu-id="0ec71-144">创建 SSP 时，必须定义网站</span><span class="sxs-lookup"><span data-stu-id="0ec71-144">You must define a Web site when creating an SSP.</span></span> <span data-ttu-id="0ec71-145">请记住端口号和你创建的站点地址。</span><span class="sxs-lookup"><span data-stu-id="0ec71-145">Remember the port number and the site address that you create.</span></span> <span data-ttu-id="0ec71-146">将将的业务数据目录应用程序定义导入到此站点。</span><span class="sxs-lookup"><span data-stu-id="0ec71-146">You will import the Business Data Catalog application definition to this site.</span></span>  
  
 <span data-ttu-id="0ec71-147">有关创建一个 SSP 的详细信息，请参阅"章概述： 创建和配置共享服务提供程序"在[http://go.microsoft.com/fwlink/?LinkId=105119](http://go.microsoft.com/fwlink/?LinkId=105119)。</span><span class="sxs-lookup"><span data-stu-id="0ec71-147">For more information about creating an SSP, see "Chapter overview: Create and configure Shared Services Providers" at [http://go.microsoft.com/fwlink/?LinkId=105119](http://go.microsoft.com/fwlink/?LinkId=105119).</span></span>  
  
## <a name="importing-the-application-definition-file"></a><span data-ttu-id="0ec71-148">导入的应用程序定义文件</span><span class="sxs-lookup"><span data-stu-id="0ec71-148">Importing the Application Definition File</span></span>  
 <span data-ttu-id="0ec71-149">现在，你必须将应用程序定义文件导入 SSP</span><span class="sxs-lookup"><span data-stu-id="0ec71-149">You must now import the application definition file into the SSP.</span></span>  
  
#### <a name="to-import-the-application-definition-file"></a><span data-ttu-id="0ec71-150">若要导入应用程序定义文件</span><span class="sxs-lookup"><span data-stu-id="0ec71-150">To import the application definition file</span></span>  
  
1.  <span data-ttu-id="0ec71-151">启动 SharePoint 3.0 管理中心。</span><span class="sxs-lookup"><span data-stu-id="0ec71-151">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="0ec71-152">单击**启动**，指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**.</span><span class="sxs-lookup"><span data-stu-id="0ec71-152">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="0ec71-153">在左侧的导航窗格中，单击你想要导入的应用程序定义的 SSP 的名称。</span><span class="sxs-lookup"><span data-stu-id="0ec71-153">In the left navigation pane, click the name of the SSP to which you want to import the application definition.</span></span>  
  
3.  <span data-ttu-id="0ec71-154">在**业务数据目录**部分中，单击**导入应用程序定义**。</span><span class="sxs-lookup"><span data-stu-id="0ec71-154">In the **Business Data Catalog** section, click **Import application definition**.</span></span>  
  
4.  <span data-ttu-id="0ec71-155">在导入应用程序定义用于打开的页面，浏览到 Customer_Orders.xml，选择的文件，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="0ec71-155">On the Import Application Definition page that opens, browse to Customer_Orders.xml, select the file, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="0ec71-156">单击“导入” 。</span><span class="sxs-lookup"><span data-stu-id="0ec71-156">Click **Import**.</span></span>  
  
6.  <span data-ttu-id="0ec71-157">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="0ec71-157">Click **OK**.</span></span>  
  
     <span data-ttu-id="0ec71-158">导入应用程序之后, 中，您可以查看你的应用程序通过转到**查看应用程序**链接。</span><span class="sxs-lookup"><span data-stu-id="0ec71-158">After importing the application, you can view your application by going to the **View Applications** link.</span></span> <span data-ttu-id="0ec71-159">单击以查看应用程序中的实体的应用程序名称。</span><span class="sxs-lookup"><span data-stu-id="0ec71-159">Click the application name to see the entities in the application.</span></span>  
  
## <a name="creating-web-parts"></a><span data-ttu-id="0ec71-160">创建 Web 部件</span><span class="sxs-lookup"><span data-stu-id="0ec71-160">Creating Web Parts</span></span>  
 <span data-ttu-id="0ec71-161">你现在必须在 SharePoint 站点，以查看和管理将从 SAP 系统中提取的业务数据创建 Web 部件。</span><span class="sxs-lookup"><span data-stu-id="0ec71-161">You must now create Web Parts in your SharePoint site to view and manage the business data that will be extracted from the SAP system.</span></span> <span data-ttu-id="0ec71-162">Web 部件是信息的可重用组件，可以包含任何类型的基于 Web，包括分析、 协作，和数据库信息。</span><span class="sxs-lookup"><span data-stu-id="0ec71-162">Web Parts are reusable components that can contain any kind of Web-based information, including analytical, collaborative, and database information.</span></span>  
  
 <span data-ttu-id="0ec71-163">在本教程中，创建在业务数据目录定义编辑器中的方法实例创建了 Web 部件。</span><span class="sxs-lookup"><span data-stu-id="0ec71-163">In this tutorial, Web Parts are created for the method instances that were created in the Business Data Catalog Definition Editor.</span></span> <span data-ttu-id="0ec71-164">Office SharePoint Server 提供了用于特定 Web 部件的不同类型。</span><span class="sxs-lookup"><span data-stu-id="0ec71-164">Office SharePoint Server provides different kinds of Web Parts for specific use.</span></span> <span data-ttu-id="0ec71-165">此处使用以下 Web 部件：</span><span class="sxs-lookup"><span data-stu-id="0ec71-165">The following Web Parts are used here:</span></span>  
  
-   <span data-ttu-id="0ec71-166">**业务数据列表**Web 部件**Finder**方法实例。</span><span class="sxs-lookup"><span data-stu-id="0ec71-166">**Business Data List** Web Part for the **Finder** method instance.</span></span> <span data-ttu-id="0ec71-167">此 Web 部件，可指定要从 SAP 系统中检索一个客户列表的搜索表达式。</span><span class="sxs-lookup"><span data-stu-id="0ec71-167">This Web Part enables you to specify a search expression to retrieve a list of customers from the SAP system.</span></span> <span data-ttu-id="0ec71-168">对于本教程中，这被称为搜索客户 Web 部件。</span><span class="sxs-lookup"><span data-stu-id="0ec71-168">For this tutorial, this is called the Search Customers Web Part.</span></span>  
  
-   <span data-ttu-id="0ec71-169">**业务数据项**Web 部件**特定的 Finder**方法实例。</span><span class="sxs-lookup"><span data-stu-id="0ec71-169">**Business Data Item** Web Part for the **Specific Finder** method instance.</span></span> <span data-ttu-id="0ec71-170">此 Web 部件显示特定客户从搜索客户 Web 部件中选择的详细信息。</span><span class="sxs-lookup"><span data-stu-id="0ec71-170">This Web Part presents the details for a specific customer that you select from the Search Customers Web Part.</span></span> <span data-ttu-id="0ec71-171">此 Web 部件映射到搜索客户 Web 部件。</span><span class="sxs-lookup"><span data-stu-id="0ec71-171">This Web Part is mapped to the Search Customer Web Part.</span></span>  <span data-ttu-id="0ec71-172">对于本教程中，这被称为客户详细信息 Web 部件。</span><span class="sxs-lookup"><span data-stu-id="0ec71-172">For this tutorial, this is called the Customer Details Web Part.</span></span>  
  
-   <span data-ttu-id="0ec71-173">**业务数据相关列表**Web 部件**关联**方法实例。</span><span class="sxs-lookup"><span data-stu-id="0ec71-173">**Business Data Related List** Web Part for the **Association** method instance.</span></span> <span data-ttu-id="0ec71-174">此 Web 部件列出特定客户从搜索客户 Web 部件中选择的销售订单。</span><span class="sxs-lookup"><span data-stu-id="0ec71-174">This Web Part lists the sales orders for a specific customer that you select from the Search Customers Web Part.</span></span> <span data-ttu-id="0ec71-175">此 Web 部件将搜索客户 Web 部件与关联。</span><span class="sxs-lookup"><span data-stu-id="0ec71-175">This Web Part is associated with the Search Customer Web Part.</span></span>  <span data-ttu-id="0ec71-176">对于本教程中，这被称为销售订单详细信息 Web 部件。</span><span class="sxs-lookup"><span data-stu-id="0ec71-176">For this tutorial, this is called the Sales Order Details Web Part.</span></span>  
  
 <span data-ttu-id="0ec71-177">本部分提供说明来创建这些 Web 部件并创建它们之间的关联。</span><span class="sxs-lookup"><span data-stu-id="0ec71-177">This section provides instructions to create these Web Parts and to create associations between them.</span></span> <span data-ttu-id="0ec71-178">有关创建 Web 部件的详细信息，请参阅"自定义业务数据列表、 Web 部件和站点"在[http://go.microsoft.com/fwlink/?LinkId=104131](http://go.microsoft.com/fwlink/?LinkId=104131)。</span><span class="sxs-lookup"><span data-stu-id="0ec71-178">For more information about creating Web Parts, see "Customize business data lists, Web Parts, and sites" at [http://go.microsoft.com/fwlink/?LinkId=104131](http://go.microsoft.com/fwlink/?LinkId=104131).</span></span>  
  
 <span data-ttu-id="0ec71-179">Web 部件将添加到单个 Web 部件页。</span><span class="sxs-lookup"><span data-stu-id="0ec71-179">The Web Parts will be added to a single Web Part page.</span></span> <span data-ttu-id="0ec71-180">添加 Web 部件之前，必须创建的 Web 部件页。</span><span class="sxs-lookup"><span data-stu-id="0ec71-180">You must create a Web Part page before adding the Web Parts.</span></span> <span data-ttu-id="0ec71-181">对于本教程中，此 Web 部件页被称为 Customer_SalesOrders。</span><span class="sxs-lookup"><span data-stu-id="0ec71-181">For this tutorial, this Web Part page is called Customer_SalesOrders.</span></span>  
  
### <a name="creating-a-web-part-page"></a><span data-ttu-id="0ec71-182">创建 Web 部件页</span><span class="sxs-lookup"><span data-stu-id="0ec71-182">Creating a Web Part Page</span></span>  
 <span data-ttu-id="0ec71-183">本部分提供说明创建的 Web 部件页。</span><span class="sxs-lookup"><span data-stu-id="0ec71-183">This section provides instructions to create a Web Part page.</span></span>  
  
##### <a name="to-create-a-web-part-page"></a><span data-ttu-id="0ec71-184">若要创建的 Web 部件页</span><span class="sxs-lookup"><span data-stu-id="0ec71-184">To create a Web Part page</span></span>  
  
1.  <span data-ttu-id="0ec71-185">启动 SharePoint 3.0 管理中心。</span><span class="sxs-lookup"><span data-stu-id="0ec71-185">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="0ec71-186">单击**启动**，指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**。</span><span class="sxs-lookup"><span data-stu-id="0ec71-186">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="0ec71-187">在左侧的导航窗格中，单击你想要导入的应用程序定义的 SSP 的名称。</span><span class="sxs-lookup"><span data-stu-id="0ec71-187">In the left navigation pane, click the name of the SSP to which you want to import the application definition.</span></span>  
  
3.  <span data-ttu-id="0ec71-188">在共享服务管理页上，在右上角，单击**站点操作**，然后单击**创建**。</span><span class="sxs-lookup"><span data-stu-id="0ec71-188">On the Shared Services Administration page, in the upper-right corner, click **Site Actions**, and then click **Create**.</span></span>  
  
     <span data-ttu-id="0ec71-189">![若要创建 web 部件的菜单](../../adapters-and-accelerators/adapter-oracle-ebs/media/a9872c3e-f823-4c47-a538-19242565d2e9.gif "a9872c3e-f823-4c47-a538-19242565d2e9")</span><span class="sxs-lookup"><span data-stu-id="0ec71-189">![Menu to create a web part](../../adapters-and-accelerators/adapter-oracle-ebs/media/a9872c3e-f823-4c47-a538-19242565d2e9.gif "a9872c3e-f823-4c47-a538-19242565d2e9")</span></span>  
  
4.  <span data-ttu-id="0ec71-190">在创建页面上，在**网页**部分中，单击**Web 部件页**。</span><span class="sxs-lookup"><span data-stu-id="0ec71-190">On the Create page, in the **Web Pages** section, click **Web Part Page**.</span></span>  
  
5.  <span data-ttu-id="0ec71-191">在新建 Web 部件页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0ec71-191">On the New Web Part page, do the following:</span></span>  
  
    1.  <span data-ttu-id="0ec71-192">在**名称**字段中，键入页面的名称。</span><span class="sxs-lookup"><span data-stu-id="0ec71-192">In the **Name** field, type a name for the page.</span></span> <span data-ttu-id="0ec71-193">对于本教程中，键入的名称作为**Customer_SalesOrders**。</span><span class="sxs-lookup"><span data-stu-id="0ec71-193">For this tutorial, type the name as **Customer_SalesOrders**.</span></span>  
  
    2.  <span data-ttu-id="0ec71-194">选择**文件已存在时覆盖**复选框，如果你想要使用与你创建的新页相同的名称覆盖旧的页。</span><span class="sxs-lookup"><span data-stu-id="0ec71-194">Select the **Overwrite if file already exists** check box, if you want to overwrite old pages with the same name as the new page you create.</span></span>  
  
    3.  <span data-ttu-id="0ec71-195">在**布局**部分中，从**选择布局模板**框中，选择 Web 部件页的布局。</span><span class="sxs-lookup"><span data-stu-id="0ec71-195">In the **Layout** section, from the **Choose a Layout Template** box, select a layout for the Web Part page.</span></span> <span data-ttu-id="0ec71-196">对于本教程中，选择**标头，左侧列中，正文**。</span><span class="sxs-lookup"><span data-stu-id="0ec71-196">For this tutorial, select **Header, Left Column, Body**.</span></span>  
  
    4.  <span data-ttu-id="0ec71-197">在**保存位置**部分中，在**文档库**列表中，单击**表单模板**。</span><span class="sxs-lookup"><span data-stu-id="0ec71-197">In the **Save Location** section, in the **Document Library** list, click **Form Templates**.</span></span>  
  
    5.  <span data-ttu-id="0ec71-198">单击 **“创建”**。</span><span class="sxs-lookup"><span data-stu-id="0ec71-198">Click **Create**.</span></span> <span data-ttu-id="0ec71-199">只需创建后下, 图显示的 Web 部件页。</span><span class="sxs-lookup"><span data-stu-id="0ec71-199">The following figure shows a Web Part page after it is just created.</span></span>  
  
         <span data-ttu-id="0ec71-200">![空 Web 部件页](../../adapters-and-accelerators/adapter-sap/media/6aa68c43-59df-47c4-95a6-453f7c668025.gif "6aa68c43-59df-47c4-95a6-453f7c668025")</span><span class="sxs-lookup"><span data-stu-id="0ec71-200">![Empty Web Part page](../../adapters-and-accelerators/adapter-sap/media/6aa68c43-59df-47c4-95a6-453f7c668025.gif "6aa68c43-59df-47c4-95a6-453f7c668025")</span></span>  
  
    6.  <span data-ttu-id="0ec71-201">现在，你必须将不同的 Web 部件添加到此页。</span><span class="sxs-lookup"><span data-stu-id="0ec71-201">You must now add the different Web Parts to this page.</span></span>  
  
### <a name="adding-a-business-data-list-web-part"></a><span data-ttu-id="0ec71-202">添加业务数据列表 Web 部件</span><span class="sxs-lookup"><span data-stu-id="0ec71-202">Adding a Business Data List Web Part</span></span>  
 <span data-ttu-id="0ec71-203">现在，你必须将业务数据列表 Web 部件添加到 Web 部件页。</span><span class="sxs-lookup"><span data-stu-id="0ec71-203">You must now add a Business Data List Web Part to the Web Part page.</span></span> <span data-ttu-id="0ec71-204">使用此 Web 部件将从匹配的搜索表达式的 SAP 系统检索一个客户列表。</span><span class="sxs-lookup"><span data-stu-id="0ec71-204">Using this Web Part you will retrieve a list of customers from the SAP system that matches a search expression.</span></span> <span data-ttu-id="0ec71-205">此 Web 部件对应于**Finder**方法实例 (*GetCustomerByName_Instance*) 创建在业务数据目录定义编辑器中。</span><span class="sxs-lookup"><span data-stu-id="0ec71-205">This Web Part corresponds to the **Finder** method instance (*GetCustomerByName_Instance*) that you created in the Business Data Catalog Definition Editor.</span></span>  
  
##### <a name="to-add-a-business-data-list-web-part"></a><span data-ttu-id="0ec71-206">若要添加业务数据列表 Web 部件</span><span class="sxs-lookup"><span data-stu-id="0ec71-206">To add a Business Data List Web Part</span></span>  
  
1.  <span data-ttu-id="0ec71-207">在 Customer_SalesOrders 页上，在**标头**部分中，单击**添加 Web 部件**。</span><span class="sxs-lookup"><span data-stu-id="0ec71-207">On the Customer_SalesOrders page, in the **Header** section, click **Add a Web Part**.</span></span>  
  
2.  <span data-ttu-id="0ec71-208">在**添加 Web 部件**对话框中，在**业务数据**部分中，选择**业务数据列表**复选框，并依次**添加**。</span><span class="sxs-lookup"><span data-stu-id="0ec71-208">In the **Add Web Parts** dialog box, in the **Business Data** section, select the **Business Data List** check box, and then click **Add**.</span></span>  
  
     <span data-ttu-id="0ec71-209">![创建业务数据 Web 部件的选项](../../adapters-and-accelerators/adapter-oracle-ebs/media/ae7c952c-1592-495f-9452-c1bffd44421c.gif "ae7c952c-1592-495f-9452-c1bffd44421c")</span><span class="sxs-lookup"><span data-stu-id="0ec71-209">![Options to create a business data Web Part](../../adapters-and-accelerators/adapter-oracle-ebs/media/ae7c952c-1592-495f-9452-c1bffd44421c.gif "ae7c952c-1592-495f-9452-c1bffd44421c")</span></span>  
  
3.  <span data-ttu-id="0ec71-210">在新添加的业务数据列表 Web 部件，单击**打开工具窗格**链接。</span><span class="sxs-lookup"><span data-stu-id="0ec71-210">In the newly added Business Data List Web Part, click the **Open the tool pane** link.</span></span>  
  
     <span data-ttu-id="0ec71-211">![为 Web 部件中打开工具窗格](../../adapters-and-accelerators/adapter-oracle-ebs/media/4e7a1cb1-69dc-4e0d-a211-6a217dc4a549.gif "4e7a1cb1-69dc-4e0d-a211-6a217dc4a549")</span><span class="sxs-lookup"><span data-stu-id="0ec71-211">![Open the tool pane for Web Part](../../adapters-and-accelerators/adapter-oracle-ebs/media/4e7a1cb1-69dc-4e0d-a211-6a217dc4a549.gif "4e7a1cb1-69dc-4e0d-a211-6a217dc4a549")</span></span>  
  
4.  <span data-ttu-id="0ec71-212">业务数据列表工具窗格中将在右窗格中打开。</span><span class="sxs-lookup"><span data-stu-id="0ec71-212">The Business Data List tool pane opens in the right pane.</span></span> <span data-ttu-id="0ec71-213">在**业务数据列表**部分中，为**类型**字段中，单击**浏览**按钮。</span><span class="sxs-lookup"><span data-stu-id="0ec71-213">In the **Business Data List** section, for the **Type** field, click the **Browse** button.</span></span>  
  
     <span data-ttu-id="0ec71-214">![业务数据列表工具窗格](../../adapters-and-accelerators/adapter-sap/media/580c58bf-bfc7-4d48-8c62-8ca4eee4ab48.gif "580c58bf-bfc7-4d48-8c62-8ca4eee4ab48")</span><span class="sxs-lookup"><span data-stu-id="0ec71-214">![Business Data List tool pane](../../adapters-and-accelerators/adapter-sap/media/580c58bf-bfc7-4d48-8c62-8ca4eee4ab48.gif "580c58bf-bfc7-4d48-8c62-8ca4eee4ab48")</span></span>  
  
5.  <span data-ttu-id="0ec71-215">在**业务数据类型选取器**对话框中，选择**Customer_Order_Instance**应用程序，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0ec71-215">In the **Business Data Type Picker** dialog box, select the **Customer_Order_Instance** application, and then click **OK**.</span></span>  
  
     <span data-ttu-id="0ec71-216">![选择应用程序实例](../../adapters-and-accelerators/adapter-sap/media/79967c27-9c76-4394-89bc-38c63649bdda.gif "79967c27-9c76-4394-89bc-38c63649bdda")</span><span class="sxs-lookup"><span data-stu-id="0ec71-216">![Select the application instance](../../adapters-and-accelerators/adapter-sap/media/79967c27-9c76-4394-89bc-38c63649bdda.gif "79967c27-9c76-4394-89bc-38c63649bdda")</span></span>  
  
6.  <span data-ttu-id="0ec71-217">展开**外观**节点，然后在**标题**框中，键入 Web 部件的标题。</span><span class="sxs-lookup"><span data-stu-id="0ec71-217">Expand the **Appearance** node, and in the **Title** box, type a title for the Web Part.</span></span> <span data-ttu-id="0ec71-218">有关此 Web 部件中，键入**客户列表**。</span><span class="sxs-lookup"><span data-stu-id="0ec71-218">For this Web Part, type **Customer List**.</span></span>  
  
7.  <span data-ttu-id="0ec71-219">在业务数据列表工具窗格中，单击**应用**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0ec71-219">In the Business Data List tool pane, click **Apply**, and then click **OK**.</span></span> <span data-ttu-id="0ec71-220">业务数据列表 Web 部件现在如下所示：</span><span class="sxs-lookup"><span data-stu-id="0ec71-220">The Business Data List Web Part now looks like the following:</span></span>  
  
     <span data-ttu-id="0ec71-221">![业务数据列表 Web 部件](../../adapters-and-accelerators/adapter-sap/media/185fb3f3-98b0-4efe-960d-91312912ad7d.gif "185fb3f3-98b0-4efe-960d-91312912ad7d")</span><span class="sxs-lookup"><span data-stu-id="0ec71-221">![Business Data List Web Part](../../adapters-and-accelerators/adapter-sap/media/185fb3f3-98b0-4efe-960d-91312912ad7d.gif "185fb3f3-98b0-4efe-960d-91312912ad7d")</span></span>  
  
8.  <span data-ttu-id="0ec71-222">Web 部件列出通过执行 SD_RFC_CUSTOMER_GET RFC 返回的字段。</span><span class="sxs-lookup"><span data-stu-id="0ec71-222">The Web Part lists the fields that are returned by executing the SD_RFC_CUSTOMER_GET RFC.</span></span> <span data-ttu-id="0ec71-223">你可以删除不希望在 SharePoint 门户上显示的字段。</span><span class="sxs-lookup"><span data-stu-id="0ec71-223">You can remove the fields that you do not want to display on the SharePoint portal.</span></span> <span data-ttu-id="0ec71-224">若要删除字段，请单击**编辑视图**Web 部件右上角中的链接。</span><span class="sxs-lookup"><span data-stu-id="0ec71-224">To remove the fields, click the **Edit View** link in the upper-right corner of the Web Part.</span></span>  
  
9. <span data-ttu-id="0ec71-225">在编辑视图页上的列部分中，清除针对你不想要显示的列的复选框。</span><span class="sxs-lookup"><span data-stu-id="0ec71-225">On the Edit View page, in the Columns section, clear the check boxes against the columns that you do not want to display.</span></span>  
  
     <span data-ttu-id="0ec71-226">![查看 SharePoint 中的特定列](../../adapters-and-accelerators/adapter-sap/media/24213b67-aafe-4534-91a7-06bde7bcbf7c.gif "24213b67-aafe-4534-91a7-06bde7bcbf7c")</span><span class="sxs-lookup"><span data-stu-id="0ec71-226">![View specific columns in SharePoint](../../adapters-and-accelerators/adapter-sap/media/24213b67-aafe-4534-91a7-06bde7bcbf7c.gif "24213b67-aafe-4534-91a7-06bde7bcbf7c")</span></span>  
  
10. <span data-ttu-id="0ec71-227">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="0ec71-227">Click **OK**.</span></span>  
  
### <a name="adding-a-business-data-item-web-part"></a><span data-ttu-id="0ec71-228">添加业务数据项 Web 部件</span><span class="sxs-lookup"><span data-stu-id="0ec71-228">Adding a Business Data Item Web Part</span></span>  
 <span data-ttu-id="0ec71-229">现在，你必须将业务数据项 Web 部件添加到 Web 部件页。</span><span class="sxs-lookup"><span data-stu-id="0ec71-229">You must now add a Business Data Item Web Part to the Web Part page.</span></span> <span data-ttu-id="0ec71-230">你还将连接到你刚刚创建业务数据列表 Web 部件的此 Web 部件。</span><span class="sxs-lookup"><span data-stu-id="0ec71-230">You will also connect this Web Part to the Business Data List Web Part that you just created.</span></span> <span data-ttu-id="0ec71-231">这样，你将能够看到在业务数据列表 Web 部件中选择的客户的详细信息。</span><span class="sxs-lookup"><span data-stu-id="0ec71-231">By doing so, you will be able to see the details for a customer that you select in the Business Data List Web Part.</span></span> <span data-ttu-id="0ec71-232">此 Web 部件对应于**特定的 Finder**方法实例 (*GetCustomerByNumber_Instance*) 创建在业务数据目录定义编辑器中。</span><span class="sxs-lookup"><span data-stu-id="0ec71-232">This Web Part corresponds to the **Specific Finder** method instance (*GetCustomerByNumber_Instance*) that you created in the Business Data Catalog Definition Editor.</span></span>  
  
##### <a name="to-add-a-business-data-item-web-part"></a><span data-ttu-id="0ec71-233">若要添加业务数据项 Web 部件</span><span class="sxs-lookup"><span data-stu-id="0ec71-233">To add a Business Data Item Web Part</span></span>  
  
1.  <span data-ttu-id="0ec71-234">在 Customer_SalesOrders 页上，在右上角，单击**站点操作**，然后单击**编辑页**。</span><span class="sxs-lookup"><span data-stu-id="0ec71-234">On the Customer_SalesOrders page, in the upper-right corner, click **Site Actions**, and then click **Edit Page**.</span></span>  
  
2.  <span data-ttu-id="0ec71-235">在 Customer_SalesOrders 页上，在**左列**部分中，单击**添加 Web 部件**。</span><span class="sxs-lookup"><span data-stu-id="0ec71-235">On the Customer_SalesOrders page, in the **Left Column** section, click **Add a Web Part**.</span></span>  
  
3.  <span data-ttu-id="0ec71-236">在**添加 Web 部件**对话框中，在**业务数据**部分中，选择**业务数据项**复选框，并依次**添加**。</span><span class="sxs-lookup"><span data-stu-id="0ec71-236">In the **Add Web Parts** dialog box, in the **Business Data** section, select the **Business Data Item** check box, and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="0ec71-237">在新添加的业务数据项 Web 部件，单击**打开工具窗格**链接。</span><span class="sxs-lookup"><span data-stu-id="0ec71-237">In the newly added Business Data Item Web Part, click the **Open the tool pane** link.</span></span>  
  
5.  <span data-ttu-id="0ec71-238">业务数据项工具窗格中打开在右窗格中。</span><span class="sxs-lookup"><span data-stu-id="0ec71-238">The Business Data Item tool pane opens in the right pane.</span></span> <span data-ttu-id="0ec71-239">在**业务数据项**部分中，为**类型**字段中，单击**浏览**按钮。</span><span class="sxs-lookup"><span data-stu-id="0ec71-239">In the **Business Data Item** section, for the **Type** field, click the **Browse** button.</span></span>  
  
     <span data-ttu-id="0ec71-240">![业务数据项工具窗格](../../adapters-and-accelerators/adapter-sap/media/29322df5-4ce3-4c1f-a658-39a355dfe2aa.gif "29322df5-4ce3-4c1f-a658-39a355dfe2aa")</span><span class="sxs-lookup"><span data-stu-id="0ec71-240">![Business Data Item tool pane](../../adapters-and-accelerators/adapter-sap/media/29322df5-4ce3-4c1f-a658-39a355dfe2aa.gif "29322df5-4ce3-4c1f-a658-39a355dfe2aa")</span></span>  
  
6.  <span data-ttu-id="0ec71-241">在**业务数据类型选取器**对话框中，选择**Customer_Order_Instance**应用程序，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0ec71-241">In the **Business Data Type Picker** dialog box, select the **Customer_Order_Instance** application, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="0ec71-242">在**视图**列表中，选择**默认**。</span><span class="sxs-lookup"><span data-stu-id="0ec71-242">In the **View** list, select **Default**.</span></span>  
  
8.  <span data-ttu-id="0ec71-243">保留**项**列表是空的。</span><span class="sxs-lookup"><span data-stu-id="0ec71-243">Leave the **Item** list empty.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0ec71-244">有关**项**字段中，你必须指定客户名称或你想要查看的详细信息的客户编号。</span><span class="sxs-lookup"><span data-stu-id="0ec71-244">For the **Item** field, you must specify a customer name or customer number for which you want to see the details.</span></span> <span data-ttu-id="0ec71-245">以便提供作为输入参数为此 Web 部件。</span><span class="sxs-lookup"><span data-stu-id="0ec71-245">That serves as an input parameter for this Web Part.</span></span> <span data-ttu-id="0ec71-246">因为你将通过连接到业务数据列表 Web 部件遇到输入的参数，你不需要显式指定一个项。</span><span class="sxs-lookup"><span data-stu-id="0ec71-246">Because you will be getting the input parameter by connecting to the Business Data List Web Part, you need not specify an item explicitly.</span></span>  
  
9. <span data-ttu-id="0ec71-247">在**字段**部分中，单击**选择**以选择你想要显示在页面上的字段。</span><span class="sxs-lookup"><span data-stu-id="0ec71-247">In the **Fields** section, click **Choose** to select the fields you want to display on the page.</span></span>  
  
10. <span data-ttu-id="0ec71-248">展开**外观**节点，然后在**标题**字段中，指定 Web 部件的标题。</span><span class="sxs-lookup"><span data-stu-id="0ec71-248">Expand the **Appearance** node, and in the **Title** field, specify a title for the Web Part.</span></span> <span data-ttu-id="0ec71-249">对于此 Web 部件，指定**特定客户的详细信息**。</span><span class="sxs-lookup"><span data-stu-id="0ec71-249">For this Web Part, specify **Details for a Specific Customer**.</span></span>  
  
11. <span data-ttu-id="0ec71-250">单击**应用**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0ec71-250">Click **Apply**, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="0ec71-251">连接到 Web 部件**客户列表**Web 部件。</span><span class="sxs-lookup"><span data-stu-id="0ec71-251">Connect the Web Part to the **Customer List** Web Part.</span></span> <span data-ttu-id="0ec71-252">为此：</span><span class="sxs-lookup"><span data-stu-id="0ec71-252">To do so:</span></span>  
  
    1.  <span data-ttu-id="0ec71-253">单击**编辑**Web 部件右上角。</span><span class="sxs-lookup"><span data-stu-id="0ec71-253">Click **edit** towards the upper-right corner of the Web Part.</span></span>  
  
    2.  <span data-ttu-id="0ec71-254">从上下文菜单中指向**连接**，指向**获取项从**，然后单击**客户列表**。</span><span class="sxs-lookup"><span data-stu-id="0ec71-254">From the context menu point to **Connections**, point to **Get Item From**, and click **Customer List**.</span></span>  
  
         <span data-ttu-id="0ec71-255">![连接两个 Web 部件](../../adapters-and-accelerators/adapter-sap/media/505aead7-f498-448f-a7cb-55d0a121f91f.gif "505aead7-f498-448f-a7cb-55d0a121f91f")</span><span class="sxs-lookup"><span data-stu-id="0ec71-255">![Connect two Web Parts](../../adapters-and-accelerators/adapter-sap/media/505aead7-f498-448f-a7cb-55d0a121f91f.gif "505aead7-f498-448f-a7cb-55d0a121f91f")</span></span>  
  
### <a name="adding-a-business-data-related-list-web-part"></a><span data-ttu-id="0ec71-256">添加业务数据相关列表 Web 部件</span><span class="sxs-lookup"><span data-stu-id="0ec71-256">Adding a Business Data Related List Web Part</span></span>  
 <span data-ttu-id="0ec71-257">现在，你必须将业务数据相关列表 Web 部件添加到 Web 部件页。</span><span class="sxs-lookup"><span data-stu-id="0ec71-257">You must now add a Business Data Related List Web Part to the Web Part page.</span></span> <span data-ttu-id="0ec71-258">你还将连接到之前创建业务数据列表 Web 部件的此 Web 部件。</span><span class="sxs-lookup"><span data-stu-id="0ec71-258">You will also connect this Web Part to the Business Data List Web Part you created earlier.</span></span> <span data-ttu-id="0ec71-259">这样，你将能够查看你在业务数据列表 Web 部件中选择的客户的销售订单。</span><span class="sxs-lookup"><span data-stu-id="0ec71-259">By doing so, you will be able to see the sales orders for a customer that you select in the Business Data List Web Part.</span></span> <span data-ttu-id="0ec71-260">此 Web 部件对应于**关联**方法实例 (*SalesOrderForCustomer_Instance*) 创建在业务数据目录定义编辑器中。</span><span class="sxs-lookup"><span data-stu-id="0ec71-260">This Web Part corresponds to the **Association** method instance (*SalesOrderForCustomer_Instance*) you created in the Business Data Catalog Definition Editor.</span></span>  
  
##### <a name="to-add-a-business-data-related-list-web-part"></a><span data-ttu-id="0ec71-261">添加业务数据相关的列表 Web 部件</span><span class="sxs-lookup"><span data-stu-id="0ec71-261">To add a Business Data Related List Web Part</span></span>  
  
1.  <span data-ttu-id="0ec71-262">在 Customer_SalesOrders 页上，在**正文**部分中，单击**添加 Web 部件**。</span><span class="sxs-lookup"><span data-stu-id="0ec71-262">On the Customer_SalesOrders page, in the **Body** section, click **Add a Web Part**.</span></span>  
  
2.  <span data-ttu-id="0ec71-263">在**添加 Web 部件**对话框中，在**业务数据**部分中，选择**业务数据相关列表**复选框，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="0ec71-263">In the **Add Web Parts** dialog box, in the **Business Data** section, select the **Business Data Related List** check box, and click **Add**.</span></span>  
  
3.  <span data-ttu-id="0ec71-264">在新添加业务数据相关列表 Web 部件中，单击**打开工具窗格**链接。</span><span class="sxs-lookup"><span data-stu-id="0ec71-264">In the newly added Business Data Related List Web Part, click the **Open the tool pane** link.</span></span>  
  
4.  <span data-ttu-id="0ec71-265">业务数据相关列表工具窗格中将在右窗格中打开。</span><span class="sxs-lookup"><span data-stu-id="0ec71-265">The Business Data Related List tool pane opens in the right pane.</span></span> <span data-ttu-id="0ec71-266">在**业务数据相关列表**部分中，为**类型**字段中，单击**浏览**按钮。</span><span class="sxs-lookup"><span data-stu-id="0ec71-266">In the **Business Data Related List** section, for the **Type** field, click the **Browse** button.</span></span>  
  
     <span data-ttu-id="0ec71-267">![业务数据相关列表](../../adapters-and-accelerators/adapter-sap/media/1914e12d-27f0-4ecb-9605-3177183a2d44.gif "1914e12d-27f0-4ecb-9605-3177183a2d44")</span><span class="sxs-lookup"><span data-stu-id="0ec71-267">![Business Data Related List](../../adapters-and-accelerators/adapter-sap/media/1914e12d-27f0-4ecb-9605-3177183a2d44.gif "1914e12d-27f0-4ecb-9605-3177183a2d44")</span></span>  
  
5.  <span data-ttu-id="0ec71-268">在**业务数据类型选取器**对话框中，选择**Customer_Order_Instance**应用程序，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0ec71-268">In the **Business Data Type Picker** dialog box, select the **Customer_Order_Instance** application, and then click **OK**.</span></span> <span data-ttu-id="0ec71-269">**关系**列表的名称，并用其填充**关联**方法实例 (*SalesOrderForCustomer_Instance*)。</span><span class="sxs-lookup"><span data-stu-id="0ec71-269">The **Relationship** list populates with the name of the **Association** method instance (*SalesOrderForCustomer_Instance*).</span></span>  
  
6.  <span data-ttu-id="0ec71-270">展开**外观**节点，然后在**标题**框中，键入 Web 部件的标题。</span><span class="sxs-lookup"><span data-stu-id="0ec71-270">Expand the **Appearance** node, and in the **Title** box, type a title for the Web Part.</span></span> <span data-ttu-id="0ec71-271">有关此 Web 部件中，键入**特定客户的销售订单**。</span><span class="sxs-lookup"><span data-stu-id="0ec71-271">For this Web Part, type **Sales Order for a Specific Customer**.</span></span>  
  
7.  <span data-ttu-id="0ec71-272">单击**应用**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="0ec71-272">Click **Apply**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="0ec71-273">Web 部件列出通过执行 BAPI_SALESORDER_GETLIST RFC 返回的字段。</span><span class="sxs-lookup"><span data-stu-id="0ec71-273">The Web Part lists the fields that are returned by executing the BAPI_SALESORDER_GETLIST RFC.</span></span> <span data-ttu-id="0ec71-274">你可以删除不希望在 SharePoint 门户上显示的字段。</span><span class="sxs-lookup"><span data-stu-id="0ec71-274">You can remove the fields that you do not want to display on the SharePoint portal.</span></span> <span data-ttu-id="0ec71-275">若要删除字段，请单击**编辑视图**Web 部件右上角中的链接。</span><span class="sxs-lookup"><span data-stu-id="0ec71-275">To remove the fields, click the **Edit View** link in the upper-right corner of the Web Part.</span></span>  
  
9. <span data-ttu-id="0ec71-276">在编辑视图页上，在**列**部分中，清除针对你不想要显示的列文本框。</span><span class="sxs-lookup"><span data-stu-id="0ec71-276">On the Edit View page, in the **Columns** section, clear the text boxes against the columns that you do not want to display.</span></span>  
  
10. <span data-ttu-id="0ec71-277">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="0ec71-277">Click **OK**.</span></span>  
  
11. <span data-ttu-id="0ec71-278">连接到 Web 部件**客户列表**Web 部件。</span><span class="sxs-lookup"><span data-stu-id="0ec71-278">Connect the Web Part to the **Customer List** Web Part.</span></span> <span data-ttu-id="0ec71-279">为此：</span><span class="sxs-lookup"><span data-stu-id="0ec71-279">To do so:</span></span>  
  
    1.  <span data-ttu-id="0ec71-280">单击**编辑**右上角**特定客户的销售订单**Web 部件。</span><span class="sxs-lookup"><span data-stu-id="0ec71-280">Click **edit** towards the upper-right corner of the **Sales Order for a Specific Customer** Web Part.</span></span>  
  
    2.  <span data-ttu-id="0ec71-281">从上下文菜单中，指向**连接**，指向**获取相关项从**，然后单击**客户列表**。</span><span class="sxs-lookup"><span data-stu-id="0ec71-281">From the context menu, point to **Connections**, point to **Get Related Item From**, and then click **Customer List**.</span></span>  
  
12. <span data-ttu-id="0ec71-282">单击**退出编辑模式**从页面的右上角。</span><span class="sxs-lookup"><span data-stu-id="0ec71-282">Click **Exit Edit Mode** from the upper-right corner of the page.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="0ec71-283">后续步骤</span><span class="sxs-lookup"><span data-stu-id="0ec71-283">Next Steps</span></span>  
 <span data-ttu-id="0ec71-284">通过从某个 SAP 系统检索数据来测试 SharePoint 应用程序。</span><span class="sxs-lookup"><span data-stu-id="0ec71-284">Test the SharePoint application by retrieving data from an SAP system.</span></span> <span data-ttu-id="0ec71-285">请参阅[步骤 4： 测试 SharePoint 应用程序](../../adapters-and-accelerators/adapter-sap/step-4-test-your-sharepoint-application1.md)。</span><span class="sxs-lookup"><span data-stu-id="0ec71-285">See [Step 4: Test Your SharePoint Application](../../adapters-and-accelerators/adapter-sap/step-4-test-your-sharepoint-application1.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ec71-286">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0ec71-286">See Also</span></span>  
 [<span data-ttu-id="0ec71-287">教程 1： 从 SharePoint 站点上的 SAP 系统提供数据</span><span class="sxs-lookup"><span data-stu-id="0ec71-287">Tutorial 1: Presenting Data from an SAP System on a SharePoint Site</span></span>](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md)