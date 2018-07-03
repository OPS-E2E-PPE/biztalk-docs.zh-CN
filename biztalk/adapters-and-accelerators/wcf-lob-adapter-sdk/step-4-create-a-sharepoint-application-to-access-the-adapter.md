---
title: 步骤 4： 创建 Sharepoint 应用程序以访问适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e2d8c398-370a-4c62-961d-0eab6066ad5a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15da47a4171d6bdf4f3b53e2208851bd15ecb0d6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986638"
---
# <a name="step-4-create-a-sharepoint-application-to-access-the-adapter"></a><span data-ttu-id="c7e5a-102">步骤 4： 创建 Sharepoint 应用程序以访问适配器</span><span class="sxs-lookup"><span data-stu-id="c7e5a-102">Step 4: Create a Sharepoint Application to Access the Adapter</span></span>
<span data-ttu-id="c7e5a-103">![步骤 4 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span><span class="sxs-lookup"><span data-stu-id="c7e5a-103">![Step 4 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")</span></span>  
  
 <span data-ttu-id="c7e5a-104">**完成时间：** 15 分钟</span><span class="sxs-lookup"><span data-stu-id="c7e5a-104">**Time to complete:** 15 minutes</span></span>  
  
 <span data-ttu-id="c7e5a-105">在此步骤需要使用 Business Data Catalog Definition Editor 工具中，创建应用程序定义文件并将其导入 Microsoft Office SharePoint Server。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-105">In this step you take the application definition file that you created using the Business Data Catalog Definition Editor tool, and import it into Microsoft Office SharePoint Server.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c7e5a-106">必要條件</span><span class="sxs-lookup"><span data-stu-id="c7e5a-106">Prerequisites</span></span>  
  
-   <span data-ttu-id="c7e5a-107">您应创建了一个应用程序文件中所述[第 3 步： 创建应用程序定义文件](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md)。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-107">You should have created an application file as described in [Step 3: Create an Application Definition File](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md).</span></span>  
  
-   <span data-ttu-id="c7e5a-108">必须运行 Microsoft 单一登录服务。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-108">The Microsoft Single Sign-On service must be running.</span></span>  
  
## <a name="how-to-create-a-sharepoint-application"></a><span data-ttu-id="c7e5a-109">如何创建 SharePoint 应用程序</span><span class="sxs-lookup"><span data-stu-id="c7e5a-109">How to Create a SharePoint Application</span></span>  
 <span data-ttu-id="c7e5a-110">创建 SharePoint 应用程序涉及以下步骤：</span><span class="sxs-lookup"><span data-stu-id="c7e5a-110">Creating a SharePoint application involves the following steps:</span></span>  
  
- <span data-ttu-id="c7e5a-111">在 SharePoint 中创建的单一登录 (SSO) 应用程序。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-111">Create a Single Sign-On (SSO) application in SharePoint.</span></span>  
  
- <span data-ttu-id="c7e5a-112">创建共享服务提供程序，并导入应用程序定义文件。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-112">Create a Shared Services Provider, and import the application definition file.</span></span>  
  
- <span data-ttu-id="c7e5a-113">创建 Web 部件页，并添加 Web 部件。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-113">Create a Web Part page, and add Web Parts.</span></span>  
  
  <span data-ttu-id="c7e5a-114">本主题演示如何执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-114">This topic demonstrates how to perform these steps.</span></span>  
  
## <a name="creating-an-sso-application-in-sharepoint"></a><span data-ttu-id="c7e5a-115">在 SharePoint 中创建的 SSO 应用程序</span><span class="sxs-lookup"><span data-stu-id="c7e5a-115">Creating an SSO Application in SharePoint</span></span>  
 <span data-ttu-id="c7e5a-116">若要将用户凭据传递给 Echo 适配器中，从 SharePoint 应用程序，必须设置 SSO 应用程序映射到用户帐户或组。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-116">To pass user credentials to the Echo adapter from a SharePoint application, you must set up an SSO application that maps to a user account or group.</span></span>  
  
#### <a name="manage-server-settings-for-single-sign-on"></a><span data-ttu-id="c7e5a-117">管理服务器设置单一登录</span><span class="sxs-lookup"><span data-stu-id="c7e5a-117">Manage server settings for Single Sign-On</span></span>  
  
1.  <span data-ttu-id="c7e5a-118">启动 SharePoint 3.0 管理中心。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-118">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="c7e5a-119">上**启动**菜单，依次指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**.</span><span class="sxs-lookup"><span data-stu-id="c7e5a-119">On the **Start** menu, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="c7e5a-120">在顶部导航栏上，单击**操作**。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-120">On the top navigation bar, click **Operations**.</span></span>  
  
3.  <span data-ttu-id="c7e5a-121">在操作页中**的安全配置**部分中，单击**管理的单一登录设置**。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-121">On the Operations page, in the **Security Configuration** section, click **Manage settings for single sign-on**.</span></span>  
  
4.  <span data-ttu-id="c7e5a-122">在单一登录页上，管理设置中**服务器设置**部分中，单击**管理服务器设置**。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-122">On the Manage Settings for Single Sign-On page, in the **Server Settings** section, click **Manage Server Settings**.</span></span>  
  
5.  <span data-ttu-id="c7e5a-123">请确保此页上的信息是为实现单一登录安装正确。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-123">Ensure that the information on this page is correct for your Single Sign-On installation.</span></span> <span data-ttu-id="c7e5a-124">有关这些操作的详细信息，请参阅"配置单一登录 (Office SharePoint Server)"网址[ http://go.microsoft.com/fwlink/?LinkId=105291 ](http://go.microsoft.com/fwlink/?LinkId=105291)。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-124">For more information about these operations, see “Configure single sign-on (Office SharePoint Server)” at [http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291).</span></span>  
  
#### <a name="manage-settings-for-enterprise-application-definitions"></a><span data-ttu-id="c7e5a-125">管理企业应用程序定义的设置</span><span class="sxs-lookup"><span data-stu-id="c7e5a-125">Manage settings for enterprise application definitions</span></span>  
  
1.  <span data-ttu-id="c7e5a-126">在 SharePoint 管理中心内，在顶部导航栏上，单击**操作**。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-126">In SharePoint Central Administration, on the top navigation bar, click **Operations**.</span></span>  
  
2.  <span data-ttu-id="c7e5a-127">在操作页中**的安全配置**部分中，单击**管理的单一登录设置**。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-127">On the Operations page, in the **Security Configuration** section, click **Manage Settings for single sign-on**.</span></span>  
  
3.  <span data-ttu-id="c7e5a-128">在单一登录页上，管理设置中**企业应用程序定义设置**部分中，单击**管理企业应用程序定义的设置**。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-128">On the Manage Settings for Single Sign-On page, in the **Enterprise Application Definition Settings** section, click **Manage Settings for enterprise application definitions**.</span></span>  
  
4.  <span data-ttu-id="c7e5a-129">在管理企业应用程序定义页上，单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-129">On the Manage Enterprise Application Definitions page, click **New Item**.</span></span>  
  
5.  <span data-ttu-id="c7e5a-130">在创建企业应用程序定义页，将**显示名称**字段**EchoSSO**，然后设置**应用程序名称**字段**EchoSSO**。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-130">On the Create Enterprise Application Definitions Page, set the **Display name** field to **EchoSSO**, and then set the **Application name** field to **EchoSSO**.</span></span> <span data-ttu-id="c7e5a-131">此值应匹配中指定的 SecondarySsoApplicationId[第 3 步： 创建应用程序定义文件](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md)。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-131">This value should match the SecondarySsoApplicationId you specified in [Step 3: Create an Application Definition File](../../adapters-and-accelerators/wcf-lob-adapter-sdk/step-3-create-an-application-definition-file.md).</span></span>  
  
6.  <span data-ttu-id="c7e5a-132">在中**联系人电子邮件地址**字段中输入你的电子邮件地址，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-132">In the **Contact e-mail address** field, enter your e-mail address, and then click **OK**.</span></span>  
  
#### <a name="manage-account-information-for-enterprise-application-definitions"></a><span data-ttu-id="c7e5a-133">管理企业应用程序定义的帐户信息</span><span class="sxs-lookup"><span data-stu-id="c7e5a-133">Manage account information for enterprise application definitions</span></span>  
  
1.  <span data-ttu-id="c7e5a-134">在 SharePoint 管理中心内，在顶部导航栏上，单击**操作**。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-134">In SharePoint Central Administration, on the top navigation bar, click **Operations**.</span></span>  
  
2.  <span data-ttu-id="c7e5a-135">在操作页面上中**安全配置部分**，单击**管理的单一登录设置**。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-135">On the Operations page, in the **Security Configuration Section**, click **Manage settings for single sign-on**.</span></span>  
  
3.  <span data-ttu-id="c7e5a-136">在单一登录页上，管理设置中**企业应用程序定义设置**部分中，单击**管理帐户信息的企业应用程序定义**。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-136">On the Manage Settings for Single Sign-On page, in the **Enterprise Application Definition Settings** section, click **Manage account information for enterprise application definitions**.</span></span>  
  
4.  <span data-ttu-id="c7e5a-137">企业应用程序定义的管理帐户信息，选择**EchoSSO**从**企业应用程序定义**列表。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-137">On the Manage Account Information for an Enterprise Application Definition, select **EchoSSO** from the **Enterprise application definition** list.</span></span>  
  
5.  <span data-ttu-id="c7e5a-138">在中**组帐户名称**字段中，键入将用于保护此应用程序定义的 Windows 组。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-138">In the **Group account name** field, type the Windows group that will be used to secure this application definition.</span></span> <span data-ttu-id="c7e5a-139">例如， **\ 用户**。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-139">For example, **DOMAIN\Domain Users**.</span></span>  
  
6.  <span data-ttu-id="c7e5a-140">单击 **“设置”**。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-140">Click **Set**.</span></span>  
  
7.  <span data-ttu-id="c7e5a-141">在提供 EchoSSO 帐户信息页上，在**用户名**字段中，键入**testuser**，然后在**密码**字段中，键入**testpassword**.</span><span class="sxs-lookup"><span data-stu-id="c7e5a-141">On the Provide EchoSSO Account Information page, in the **Username** field type **testuser**, and then in the **Password** field type **testpassword**.</span></span>  
  
8.  <span data-ttu-id="c7e5a-142">单击**确定**，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-142">Click **OK**, and then click **Done**.</span></span>  
  
## <a name="creating-a-shared-services-provider-and-importing-the-application-definition-file"></a><span data-ttu-id="c7e5a-143">创建共享服务提供程序和导入应用程序定义文件</span><span class="sxs-lookup"><span data-stu-id="c7e5a-143">Creating a Shared Services Provider and importing the application definition file</span></span>  
 <span data-ttu-id="c7e5a-144">共享服务提供程序 (SSP) 是共享的服务和及其支持资源的逻辑分组。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-144">A Shared Services Provider (SSP) is a logical grouping of shared services and their supporting resources.</span></span> <span data-ttu-id="c7e5a-145">可以使用 SharePoint 中心管理控制台来创建 SSP。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-145">You can create an SSP by using the SharePoint Central Administration Console.</span></span> <span data-ttu-id="c7e5a-146">此示例适用于任何 ssp。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-146">This example will work in any SSP.</span></span> <span data-ttu-id="c7e5a-147">有关创建 SSP 的详细信息，请参阅"一章概述： 创建和配置共享服务提供程序"处[ http://go.microsoft.com/fwlink/?LinkId=105119 ](http://go.microsoft.com/fwlink/?LinkId=105119)。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-147">For more information about creating an SSP, see “Chapter overview: Create and Configure Shared Services Providers” at [http://go.microsoft.com/fwlink/?LinkId=105119](http://go.microsoft.com/fwlink/?LinkId=105119).</span></span>  
  
### <a name="to-import-the-application-definition-file"></a><span data-ttu-id="c7e5a-148">若要导入应用程序定义文件</span><span class="sxs-lookup"><span data-stu-id="c7e5a-148">To import the application definition file</span></span>  
  
1.  <span data-ttu-id="c7e5a-149">启动 SharePoint 3.0 管理中心。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-149">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="c7e5a-150">上**启动**菜单，依次指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**.</span><span class="sxs-lookup"><span data-stu-id="c7e5a-150">On the **Start** menu, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="c7e5a-151">在左侧的导航窗格中，单击你想要导入应用程序定义的 SSP 的名称。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-151">In the left navigation pane, click the name of the SSP to which you want to import the application definition.</span></span>  
  
3.  <span data-ttu-id="c7e5a-152">在中**业务数据目录**部分中，单击**导入应用程序定义**。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-152">In the **Business Data Catalog** section, click **Import application definition**.</span></span>  
  
4.  <span data-ttu-id="c7e5a-153">在导入应用程序定义页上单击**浏览**，然后选择 EchoWS.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-153">On the Import Application Definition page, click **Browse**, and then select the EchoWS.xml file.</span></span>  
  
5.  <span data-ttu-id="c7e5a-154">单击**导入**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-154">Click **Import**, and then click **OK**.</span></span>  
  
## <a name="creating-web-parts"></a><span data-ttu-id="c7e5a-155">创建 Web 部件</span><span class="sxs-lookup"><span data-stu-id="c7e5a-155">Creating Web Parts</span></span>  
 <span data-ttu-id="c7e5a-156">现在必须在 SharePoint 网站中使用方法实例创建在 Business Data Catalog Definition Editor 创建 Web 部件。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-156">You must now create Web Parts in your SharePoint site to use the method instance created in the Business Data Catalog Definition Editor.</span></span> <span data-ttu-id="c7e5a-157">Web 部件是信息的可重用的组件，可包含任何类型的基于 Web，包括分析、 协作式和和数据库信息。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-157">Web Parts are reusable components that can contain any kind of Web-based information, including analytical, collaborative, and database information.</span></span>  
  
#### <a name="to-create-a-web-part-page"></a><span data-ttu-id="c7e5a-158">若要创建的 Web 部件页</span><span class="sxs-lookup"><span data-stu-id="c7e5a-158">To create a Web Part page</span></span>  
  
1.  <span data-ttu-id="c7e5a-159">启动 SharePoint 3.0 管理中心。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-159">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="c7e5a-160">上**启动**菜单，依次指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**.</span><span class="sxs-lookup"><span data-stu-id="c7e5a-160">On the **Start** menu, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="c7e5a-161">在左侧的导航窗格中，单击导入应用程序定义文件的 SSP 的名称。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-161">In the left navigation pane, click the name of the SSP in which you imported the application definition file.</span></span>  
  
3.  <span data-ttu-id="c7e5a-162">在共享服务管理页上，在右上角，单击**站点操作**，然后单击**创建**。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-162">On the Shared Services Administration page, in the upper-right corner, click **Site Actions**, and then click **Create**.</span></span>  
  
     <span data-ttu-id="c7e5a-163">![创建站点操作](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/13f43659-ef61-48db-ac19-2d553367ec7e.gif "13f43659-ef61-48db-ac19-2d553367ec7e")</span><span class="sxs-lookup"><span data-stu-id="c7e5a-163">![Create Site Actions](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/13f43659-ef61-48db-ac19-2d553367ec7e.gif "13f43659-ef61-48db-ac19-2d553367ec7e")</span></span>  
  
4.  <span data-ttu-id="c7e5a-164">上**创建**页上，在**网页**部分中，单击**Web 部件页**。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-164">On the **Create** page, in the **Web Pages** section, click **Web Part Page**.</span></span>  
  
5.  <span data-ttu-id="c7e5a-165">在新的 Web 部件页上，在**名称**字段中，键入**EchoPart**，然后选择**整页、 垂直**从**选择布局模板**列表。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-165">On the New Web Part page, in the **Name** field, type **EchoPart**, and then select **Full Page, Vertical** from the **Chose a Layout Template** list.</span></span>  
  
6.  <span data-ttu-id="c7e5a-166">单击 **“创建”**。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-166">Click **Create**.</span></span>  
  
#### <a name="to-add-a-business-data-web-part"></a><span data-ttu-id="c7e5a-167">若要添加业务数据 Web 部件</span><span class="sxs-lookup"><span data-stu-id="c7e5a-167">To add a Business Data Web Part</span></span>  
  
1.  <span data-ttu-id="c7e5a-168">单击 **“添加 Web 部件”**。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-168">Click **Add a Web Part**.</span></span>  
  
2.  <span data-ttu-id="c7e5a-169">在中**添加 Web 部件**对话框中，选择**业务数据列表**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-169">In the **Add Web Parts** dialog box, select **Business Data List**, and then click **Add**.</span></span>  
  
     <span data-ttu-id="c7e5a-170">![业务数据列表](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/cd9e6bc8-c37e-49d2-9eaa-77246bb593df.gif "cd9e6bc8-c37e-49d2-9eaa-77246bb593df")</span><span class="sxs-lookup"><span data-stu-id="c7e5a-170">![Business Data List](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/cd9e6bc8-c37e-49d2-9eaa-77246bb593df.gif "cd9e6bc8-c37e-49d2-9eaa-77246bb593df")</span></span>  
  
3.  <span data-ttu-id="c7e5a-171">单击**打开工具窗格**。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-171">Click **Open the tool pane**.</span></span>  
  
4.  <span data-ttu-id="c7e5a-172">业务数据列表工具窗格将在右窗格中打开。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-172">The Business Data List tool pane opens in the right pane.</span></span> <span data-ttu-id="c7e5a-173">在中**业务数据列表**部分中，对于**类型**字段中，单击**浏览**按钮。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-173">In the **Business Data List** section, for the **Type** field, click the **Browse** button.</span></span>  
  
     <span data-ttu-id="c7e5a-174">![选择的类型](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/a054ed0e-0880-4154-9050-a00da356a4f6.gif "a054ed0e-0880-4154-9050-a00da356a4f6")</span><span class="sxs-lookup"><span data-stu-id="c7e5a-174">![Select the Type](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/a054ed0e-0880-4154-9050-a00da356a4f6.gif "a054ed0e-0880-4154-9050-a00da356a4f6")</span></span>  
  
5.  <span data-ttu-id="c7e5a-175">在中**业务数据类型选取器**对话框中，选择**EchoWSLob_Instance**应用程序，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-175">In the **Business Data Type Picker** dialog box, select the **EchoWSLob_Instance** application, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="c7e5a-176">在业务数据列表工具窗格中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-176">On the Business Data List tool pane, click **OK**.</span></span>  
  
7.  <span data-ttu-id="c7e5a-177">您会看到允许您输入要传递给 EchoGreetings 方法的问候语值的字段。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-177">You are presented with a field that allows you to enter a greeting value to pass to the EchoGreetings method.</span></span> <span data-ttu-id="c7e5a-178">问候语字段中输入数据，然后单击**检索数据**。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-178">Enter data in the greeting field and click **Retrieve Data**.</span></span> <span data-ttu-id="c7e5a-179">这将调用 Echo 适配器在 IIS 中承载的 EchoGreetings 方法并返回响应。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-179">This invokes the EchoGreetings method of the Echo adapter hosted in IIS and returns a response.</span></span>  
  
     <span data-ttu-id="c7e5a-180">![EchoGreetings 列表](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/f5a22fcd-2ae6-4384-9879-f0abd0255325.gif "f5a22fcd-2ae6-4384-9879-f0abd0255325")</span><span class="sxs-lookup"><span data-stu-id="c7e5a-180">![EchoGreetings List](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/f5a22fcd-2ae6-4384-9879-f0abd0255325.gif "f5a22fcd-2ae6-4384-9879-f0abd0255325")</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c7e5a-181">名称列不包含用户信息，但只显示 BDC。名称。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-181">The name column does not contain the user information, but only displays BDC.Name.</span></span> <span data-ttu-id="c7e5a-182">这是因为 BDC 需要仅简单记录结构，并且不会显示名称字段所表示的复杂结构。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-182">This occurs because the BDC expects only a simple record structure, and does not display the complex structure represented by the name field.</span></span>  
  
8.  <span data-ttu-id="c7e5a-183">单击**退出编辑模式**从页面右上角。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-183">Click **Exit Edit Mode** from the upper corner of the page.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="c7e5a-184">内容回顾</span><span class="sxs-lookup"><span data-stu-id="c7e5a-184">What did I just do?</span></span>  
 <span data-ttu-id="c7e5a-185">您使用 SharePoint 3.0 中心管理导入应用程序定义，并创建使用此定义调用 Echo 适配器的 EchoGreetings 操作的 Web 部件。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-185">You have used the SharePoint 3.0 Central Administration to import an application definition, and create Web Parts that use this definition to invoke the EchoGreetings operation of the Echo adapter.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="c7e5a-186">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c7e5a-186">Next Steps</span></span>  
 <span data-ttu-id="c7e5a-187">本教程中已完成。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-187">This tutorial is complete.</span></span> <span data-ttu-id="c7e5a-188">有关详细信息使用业务数据目录，请参阅"业务数据目录"网址[ http://go.microsoft.com/fwlink/?LinkId=119921 ](http://go.microsoft.com/fwlink/?LinkId=119921)。</span><span class="sxs-lookup"><span data-stu-id="c7e5a-188">For more information using the Business Data Catalog, see “Business Data Catalog” at [http://go.microsoft.com/fwlink/?LinkId=119921](http://go.microsoft.com/fwlink/?LinkId=119921).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7e5a-189">请参阅</span><span class="sxs-lookup"><span data-stu-id="c7e5a-189">See Also</span></span>  
 [<span data-ttu-id="c7e5a-190">教程 3：在 IIS 中托管 Echo 适配器</span><span class="sxs-lookup"><span data-stu-id="c7e5a-190">Tutorial 3: Hosting the Echo Adapter in IIS</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorial-3-hosting-the-echo-adapter-in-iis.md)