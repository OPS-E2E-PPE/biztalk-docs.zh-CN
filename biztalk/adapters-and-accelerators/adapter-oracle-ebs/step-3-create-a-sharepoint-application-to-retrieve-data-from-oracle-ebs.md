---
title: "步骤 3： 创建 SharePoint 应用程序从 Oracle E-business Suite 检索数据 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eaa16011-9284-4ccf-8132-9c1e14cc6aa7
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4fe9d6fc34fa039bb4b3861deb35fb51524180ab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-e-business-suite"></a><span data-ttu-id="31381-102">步骤 3： 创建 SharePoint 应用程序从 Oracle E-business Suite 检索数据</span><span class="sxs-lookup"><span data-stu-id="31381-102">Step 3: Create a SharePoint application to retrieve data from Oracle E-Business Suite</span></span>
<span data-ttu-id="31381-103">![步骤 3 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span><span class="sxs-lookup"><span data-stu-id="31381-103">![Step 3 of 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-3of4.gif "Step_3of4")</span></span>  
  
 <span data-ttu-id="31381-104">**完成时间：** 15 分钟</span><span class="sxs-lookup"><span data-stu-id="31381-104">**Time to complete:** 15 minutes</span></span>  
  
 <span data-ttu-id="31381-105">**目标：**现在必须导入 Microsoft Office SharePoint Server 中的应用程序定义文件，并设置应用程序从 Oracle E-business Suite 检索数据。</span><span class="sxs-lookup"><span data-stu-id="31381-105">**Objective:** You must now import the application definition file in Microsoft Office SharePoint Server, and set up an application to retrieve data from Oracle E-Business Suite.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="31381-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="31381-106">Prerequisites</span></span>  
  
-   <span data-ttu-id="31381-107">您将会创建应用程序定义文件中所述[步骤 2： 为 Oracle E-business Suite 项目创建应用程序定义文件](../../adapters-and-accelerators/adapter-oracle-ebs/step-2-create-an-application-definition-file-for-the-oracle-ebs-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="31381-107">You should have created an application definition file as described in [Step 2: Create an Application Definition File for the Oracle E-Business Suite Artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/step-2-create-an-application-definition-file-for-the-oracle-ebs-artifacts.md).</span></span>  
  
-   <span data-ttu-id="31381-108">必须运行 Microsoft 单一登录服务。</span><span class="sxs-lookup"><span data-stu-id="31381-108">The Microsoft Single Sign-on service must be running.</span></span>  
  
 
  
##  <span data-ttu-id="31381-109"><a name="SSO"></a>在 SharePoint 中创建 SSO 应用程序</span><span class="sxs-lookup"><span data-stu-id="31381-109"><a name="SSO"></a> Creating an SSO Application in SharePoint</span></span>  
 <span data-ttu-id="31381-110">若要从 SharePoint 应用程序访问 Oracle E-business Suite 中的数据，你必须设置的 SSO 应用程序将 SharePoint 用户映射到的 Oracle E-business Suite 用户。</span><span class="sxs-lookup"><span data-stu-id="31381-110">To access the data in Oracle E-Business Suite from a SharePoint application, you must set up an SSO application that maps a SharePoint user to an Oracle E-Business Suite user.</span></span> <span data-ttu-id="31381-111">在 SharePoint 中创建 SSO 应用程序涉及以下步骤：</span><span class="sxs-lookup"><span data-stu-id="31381-111">Creating an SSO application in SharePoint involves the following steps:</span></span>  
  
1.  <span data-ttu-id="31381-112">**管理服务器上单一登录设置**。</span><span class="sxs-lookup"><span data-stu-id="31381-112">**Manage server settings for single sign-on**.</span></span> <span data-ttu-id="31381-113">在此步骤中，你可以指定可以管理和设置单一登录服务的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="31381-113">In this step, you specify a user account that can manage and set up the single sign-on service.</span></span> <span data-ttu-id="31381-114">你可以在管理服务器设置页上执行操作。</span><span class="sxs-lookup"><span data-stu-id="31381-114">You can do so on the Manage Server Settings page.</span></span> <span data-ttu-id="31381-115">此选项才可用从 SharePoint 管理中心控制台。</span><span class="sxs-lookup"><span data-stu-id="31381-115">This option is available from the SharePoint Central Administration console.</span></span> <span data-ttu-id="31381-116">有关此步骤的详细信息，请参阅"配置单一登录的 Office SharePoint Server 2007"部分在[http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291)。</span><span class="sxs-lookup"><span data-stu-id="31381-116">For more information about this step, refer to the “Configure Single Sign-On for Office SharePoint Server 2007” section at [http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291).</span></span>  
  
2.  <span data-ttu-id="31381-117">**管理企业应用程序定义的设置**。</span><span class="sxs-lookup"><span data-stu-id="31381-117">**Manage settings for enterprise application definitions**.</span></span> <span data-ttu-id="31381-118">在此步骤中，你配置的企业应用程序定义的设置。</span><span class="sxs-lookup"><span data-stu-id="31381-118">In this step, you configure the settings for the enterprise application definition.</span></span> <span data-ttu-id="31381-119">你可以从企业应用程序定义页面的管理设置来实现。</span><span class="sxs-lookup"><span data-stu-id="31381-119">You can do so from the Manage Settings for Enterprise Application Definitions page.</span></span> <span data-ttu-id="31381-120">此选项才可用从 SharePoint 管理中心控制台。</span><span class="sxs-lookup"><span data-stu-id="31381-120">This option is available from the SharePoint Central Administration console.</span></span>  
  
    1.  <span data-ttu-id="31381-121">在管理中心内，在顶部导航栏上，单击**操作**。</span><span class="sxs-lookup"><span data-stu-id="31381-121">On Central Administration, on the top navigation bar, click **Operations**.</span></span>  
  
    2.  <span data-ttu-id="31381-122">在操作页面中**安全配置**部分中，单击**管理单一登录设置**。</span><span class="sxs-lookup"><span data-stu-id="31381-122">On the Operations page, in the **Security Configuration** section, click  **Manage settings for single sign-on**.</span></span>  
  
    3.  <span data-ttu-id="31381-123">单一登录页的管理设置中**企业应用程序定义设置**部分中，单击**管理企业应用程序定义的设置**。</span><span class="sxs-lookup"><span data-stu-id="31381-123">On the Manage Settings for Single Sign-On page, in the **Enterprise Application Definition Settings** section, click **Manage settings for enterprise application definitions**.</span></span>  
  
    4.  <span data-ttu-id="31381-124">在管理企业应用程序定义页上，提供的值**显示名称**，**应用程序名称**，和**联系人电子邮件地址**字段。</span><span class="sxs-lookup"><span data-stu-id="31381-124">On the Manage Enterprise Application Definitions page, provide values for the **Display name**, **Application name**, and the **Contact e-mail address** fields.</span></span>  
  
        > [!IMPORTANT]
        >  <span data-ttu-id="31381-125">有关**应用程序名称**字段中，请确保指定相同为指定的 SSO 应用程序名称**SecondarySsoApplicationId**时创建应用程序定义文件中，将其作为变量中所述[步骤 2： 为 Oracle E-business Suite 项目创建应用程序定义文件](../../adapters-and-accelerators/adapter-oracle-ebs/step-2-create-an-application-definition-file-for-the-oracle-ebs-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="31381-125">For the **Application name** field, make sure you specify the same SSO application name that you specified for the **SecondarySsoApplicationId** variable while creating the application definition file, as described in [Step 2: Create an Application Definition File for the Oracle E-Business Suite Artifacts](../../adapters-and-accelerators/adapter-oracle-ebs/step-2-create-an-application-definition-file-for-the-oracle-ebs-artifacts.md).</span></span>  
  
    5.  <span data-ttu-id="31381-126">将其他字段保留为默认值，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="31381-126">Leave the other fields as default, and click **OK**.</span></span>  
  
3.  <span data-ttu-id="31381-127">**管理企业应用程序定义的帐户信息**。</span><span class="sxs-lookup"><span data-stu-id="31381-127">**Manage account information for enterprise application definitions**.</span></span> <span data-ttu-id="31381-128">在此步骤中，你可以启用从 SharePoint 连接到企业应用程序的单个用户或组。</span><span class="sxs-lookup"><span data-stu-id="31381-128">In this step, you enable individual users or groups to connect to an enterprise application from SharePoint.</span></span> <span data-ttu-id="31381-129">实质上，在此步骤中你映射单个用户或组的用户在 LOB 系统。</span><span class="sxs-lookup"><span data-stu-id="31381-129">Essentially, in this step you map an individual user or group to a user in the LOB system.</span></span> <span data-ttu-id="31381-130">你还可以指定要连接到 LOB 系统的凭据。</span><span class="sxs-lookup"><span data-stu-id="31381-130">You also specify the credentials to connect to the LOB system.</span></span> <span data-ttu-id="31381-131">你可以从企业应用程序定义页的管理帐户信息来实现。</span><span class="sxs-lookup"><span data-stu-id="31381-131">You can do so from the Manage Account Information for Enterprise Application Definitions page.</span></span> <span data-ttu-id="31381-132">此选项才可用从 SharePoint 管理中心控制台。</span><span class="sxs-lookup"><span data-stu-id="31381-132">This option is available from the SharePoint Central Administration console.</span></span> <span data-ttu-id="31381-133">有关此步骤的详细信息，请参阅"管理企业应用程序定义的帐户信息"部分在[http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291)。</span><span class="sxs-lookup"><span data-stu-id="31381-133">For more information about this step, refer to the “Manage account information for an enterprise application definition” section at [http://go.microsoft.com/fwlink/?LinkId=105291](http://go.microsoft.com/fwlink/?LinkId=105291).</span></span>  
  
##  <span data-ttu-id="31381-134"><a name="SSP"></a>创建共享的服务提供程序</span><span class="sxs-lookup"><span data-stu-id="31381-134"><a name="SSP"></a> Creating a Shared Services Provider</span></span>  
 <span data-ttu-id="31381-135">共享的服务提供程序是共享的服务和其支持的资源的逻辑分组。</span><span class="sxs-lookup"><span data-stu-id="31381-135">A Shared Service Provider is a logical grouping of shared services and their supporting resources.</span></span> <span data-ttu-id="31381-136">可以通过使用 SharePoint 管理中心控制台来创建一个 SSP。</span><span class="sxs-lookup"><span data-stu-id="31381-136">You can create an SSP by using the SharePoint Central Administration console.</span></span>  
  
 <span data-ttu-id="31381-137">创建 SSP 时，必须定义网站</span><span class="sxs-lookup"><span data-stu-id="31381-137">You must define a Web site when creating an SSP.</span></span> <span data-ttu-id="31381-138">请记住端口号和你创建的站点地址。</span><span class="sxs-lookup"><span data-stu-id="31381-138">Remember the port number and the site address that you create.</span></span> <span data-ttu-id="31381-139">将将的业务数据目录应用程序定义导入到此站点。</span><span class="sxs-lookup"><span data-stu-id="31381-139">You will import the Business Data Catalog application definition to this site.</span></span>  
  
 <span data-ttu-id="31381-140">有关创建一个 SSP 的详细信息，请参阅"章概述： 创建和配置共享服务提供程序"在[http://go.microsoft.com/fwlink/?LinkId=105119](http://go.microsoft.com/fwlink/?LinkId=105119)。</span><span class="sxs-lookup"><span data-stu-id="31381-140">For more information about creating an SSP, see "Chapter overview: Create and configure Shared Services Providers" at [http://go.microsoft.com/fwlink/?LinkId=105119](http://go.microsoft.com/fwlink/?LinkId=105119).</span></span>  
  
##  <span data-ttu-id="31381-141"><a name="Import"></a>导入的应用程序定义文件</span><span class="sxs-lookup"><span data-stu-id="31381-141"><a name="Import"></a> Importing the Application Definition File</span></span>  
 <span data-ttu-id="31381-142">现在，你必须将应用程序定义文件导入 SSP</span><span class="sxs-lookup"><span data-stu-id="31381-142">You must now import the application definition file into the SSP.</span></span>  
  
#### <a name="to-import-the-application-definition-file"></a><span data-ttu-id="31381-143">若要导入应用程序定义文件</span><span class="sxs-lookup"><span data-stu-id="31381-143">To import the application definition file</span></span>  
  
1.  <span data-ttu-id="31381-144">启动 SharePoint 3.0 管理中心。</span><span class="sxs-lookup"><span data-stu-id="31381-144">Start SharePoint 3.0 Central Administration.</span></span> <span data-ttu-id="31381-145">单击**启动**，指向**所有程序**，指向**Microsoft Office Server**，然后单击**SharePoint 3.0 管理中心**.</span><span class="sxs-lookup"><span data-stu-id="31381-145">Click **Start**, point to **All Programs**, point to **Microsoft Office Server**, and then click **SharePoint 3.0 Central Administration**.</span></span>  
  
2.  <span data-ttu-id="31381-146">在左侧的导航窗格中，单击你想要导入的应用程序定义的 SSP 的名称。</span><span class="sxs-lookup"><span data-stu-id="31381-146">In the left navigation pane, click the name of the SSP to which you want to import the application definition.</span></span>  
  
3.  <span data-ttu-id="31381-147">在**业务数据目录**部分中，单击**导入应用程序定义**。</span><span class="sxs-lookup"><span data-stu-id="31381-147">In the **Business Data Catalog** section, click **Import application definition**.</span></span>  
  
4.  <span data-ttu-id="31381-148">在导入应用程序定义用于打开的页面，浏览到 Employee.xml，选择的文件，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="31381-148">On the Import Application Definition page that opens, browse to Employee.xml, select the file, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="31381-149">单击“导入” 。</span><span class="sxs-lookup"><span data-stu-id="31381-149">Click **Import**.</span></span>  
  
6.  <span data-ttu-id="31381-150">已成功导入的应用程序定义文件后，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="31381-150">After the application definition file is imported successfully, click **OK**.</span></span>  
  
     <span data-ttu-id="31381-151">由于导入应用程序定义文件中，MS_SAMPLE_EMPLOYEE，创建的应用程序将显示。</span><span class="sxs-lookup"><span data-stu-id="31381-151">The application created as a result of importing the application definition file, MS_SAMPLE_EMPLOYEE, appears.</span></span>  
  
     <span data-ttu-id="31381-152">![SharePoint 中的应用程序](../../adapters-and-accelerators/adapter-oracle-ebs/media/b0695720-0113-49dc-8eb6-c685aceada6c.gif "b0695720-0113-49dc-8eb6-c685aceada6c")</span><span class="sxs-lookup"><span data-stu-id="31381-152">![The application in SharePoint](../../adapters-and-accelerators/adapter-oracle-ebs/media/b0695720-0113-49dc-8eb6-c685aceada6c.gif "b0695720-0113-49dc-8eb6-c685aceada6c")</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="31381-153">后续步骤</span><span class="sxs-lookup"><span data-stu-id="31381-153">Next Steps</span></span>  
 <span data-ttu-id="31381-154">现在，你就可以创建 Web 部件，以创建 SharePoint 站点，以查看和搜索将从 Oracle E-business Suite 中提取的业务数据。</span><span class="sxs-lookup"><span data-stu-id="31381-154">Now, you are ready to create Web Parts to create a SharePoint site to view and search the business data that will be extracted from Oracle E-Business Suite.</span></span> <span data-ttu-id="31381-155">我们将创建一个：</span><span class="sxs-lookup"><span data-stu-id="31381-155">We will create a:</span></span>  
  
-   <span data-ttu-id="31381-156">业务数据列表 Web 部件显示 MS_SAMPLE_EMPLOYEE 接口表中的员工记录。</span><span class="sxs-lookup"><span data-stu-id="31381-156">Business Data List Web Part to display employee records from the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="31381-157">请参阅[方案 1： 使用业务数据列表 Web 部件显示数据](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md)。</span><span class="sxs-lookup"><span data-stu-id="31381-157">See [Scenario 1: Display Data Using Business Data List Web Part](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md).</span></span>  
  
-   <span data-ttu-id="31381-158">搜索框 Web 部件来执行 MS_SAMPLE_EMPLOYEE 接口表的全文搜索。</span><span class="sxs-lookup"><span data-stu-id="31381-158">Search Box Web Part to perform a full-text search on the MS_SAMPLE_EMPLOYEE interface table.</span></span> <span data-ttu-id="31381-159">请参阅[方案 2： 使用搜索框 Web 部件的搜索](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-2-search-using-the-search-box-web-part.md)。</span><span class="sxs-lookup"><span data-stu-id="31381-159">See [Scenario 2: Search Using the Search Box Web Part](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-2-search-using-the-search-box-web-part.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31381-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="31381-160">See Also</span></span>  
 [<span data-ttu-id="31381-161">教程： 从 SharePoint 站点上的 Oracle E-business Suite 显示数据</span><span class="sxs-lookup"><span data-stu-id="31381-161">Tutorial: Present Data from Oracle E-Business Suite on a SharePoint Site</span></span>](Tutorial:%20Present%20data%20from%20Oracle%20E-Business%20Suite%20on%20a%20SharePoint%20Site.md)