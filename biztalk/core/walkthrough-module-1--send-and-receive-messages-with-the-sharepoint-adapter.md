---
title: 演练：模块 1-发送和接收消息与 Windows SharePoint Services 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows SharePoint Services, creating sites
- tutorials, Windows SharePoint Services adapters
- Windows SharePoint Services adapter tutorials, receiving messages
- security, Windows SharePoint Services
- creating, Windows SharePoint Services site
- Windows SharePoint Services, security
- Windows SharePoint Services, document libraries
- Windows SharePoint Services adapters, security
- Windows SharePoint Services
- Windows SharePoint Services adapter tutorials, sending messages
ms.assetid: 6494aef5-bb1d-4a41-8186-1d49625a1013
caps.latest.revision: 41
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ade2e87fc22e822c825654e158458f1544ba6986
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395347"
---
# <a name="walkthrough-module-1---sending-and-receiving-messages-with-the-windows-sharepoint-services-adapter"></a><span data-ttu-id="fd86b-102">演练：模块 1-发送和接收消息与 Windows SharePoint Services 适配器</span><span class="sxs-lookup"><span data-stu-id="fd86b-102">Walkthrough: Module 1 - Sending and Receiving Messages with the Windows SharePoint Services Adapter</span></span>
<span data-ttu-id="fd86b-103">本演练演示如何配置 Windows SharePoint Services 和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]以便可以发送和接收消息使用的 Windows SharePoint Services 适配器和基于内容的路由 (CBR)。</span><span class="sxs-lookup"><span data-stu-id="fd86b-103">This walkthrough shows you how to configure Windows SharePoint Services and [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] so you can send and receive a message using the Windows SharePoint Services Adapter and content-based routing (CBR).</span></span> <span data-ttu-id="fd86b-104">基于内容的路由消除了订阅明确绑定到特定端口的消息的需要。</span><span class="sxs-lookup"><span data-stu-id="fd86b-104">Content-based routing eliminates the need for message subscription for messages that are deterministically bound to specific ports.</span></span> <span data-ttu-id="fd86b-105">为想要路由消息根据信封属性或仅根据用户接收端口配置属性，它还提供更大的灵活性。</span><span class="sxs-lookup"><span data-stu-id="fd86b-105">It also provides additional flexibility for users who want to route messages based on envelope properties or simply based on receive port configuration properties.</span></span> <span data-ttu-id="fd86b-106">Windows SharePoint Services 适配器的介绍，请参阅[什么是 Windows SharePoint Services 适配器？](../core/what-is-the-windows-sharepoint-services-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="fd86b-106">For an introduction to the Windows SharePoint Services adapter, see [What Is the Windows SharePoint Services Adapter?](../core/what-is-the-windows-sharepoint-services-adapter.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fd86b-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="fd86b-107">Prerequisites</span></span>  
 <span data-ttu-id="fd86b-108">以下是执行本主题中的过程的先决条件：</span><span class="sxs-lookup"><span data-stu-id="fd86b-108">The following are prerequisites for performing the procedures in this topic:</span></span>  
  
- <span data-ttu-id="fd86b-109">必须具有 BizTalk Server 上运行的完整安装的单服务器部署[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]或[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fd86b-109">You must have a single-server deployment with a complete installation of BizTalk Server running on [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)].</span></span>  
  
  <span data-ttu-id="fd86b-110">在多服务器部署中使用的 Windows SharePoint Services 适配器的信息，请参阅[设置和部署 Windows SharePoint Services 适配器](../core/setting-up-and-deploying-the-windows-sharepoint-services-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="fd86b-110">For information about using the Windows SharePoint Services adapter in a multiserver deployment, see [Setting Up and Deploying the Windows SharePoint Services Adapter](../core/setting-up-and-deploying-the-windows-sharepoint-services-adapter.md).</span></span>  
  
## <a name="configure-windows-sharepoint-services"></a><span data-ttu-id="fd86b-111">配置 Windows SharePoint Services</span><span class="sxs-lookup"><span data-stu-id="fd86b-111">Configure Windows SharePoint Services</span></span>  
 <span data-ttu-id="fd86b-112">在此过程中创建一个 SharePoint 顶级网站，其中包含三个文档库。</span><span class="sxs-lookup"><span data-stu-id="fd86b-112">In this procedure you create a SharePoint top-level Web site that contains three document libraries.</span></span> <span data-ttu-id="fd86b-113">Windows SharePoint Services 适配器使用这些库将消息从源库移动到目标库。</span><span class="sxs-lookup"><span data-stu-id="fd86b-113">The Windows SharePoint Services adapter uses these libraries to move a message from a source library to a destination library.</span></span> <span data-ttu-id="fd86b-114">此消息还存档文档库中。</span><span class="sxs-lookup"><span data-stu-id="fd86b-114">This message is also archived in a document library.</span></span> <span data-ttu-id="fd86b-115">提供可通过在本演练中的 Windows Sharepoint Services 适配器的 Windows Sharepoint Services 站点并设置用户权限以启用对此站点的访问，必须执行此过程。</span><span class="sxs-lookup"><span data-stu-id="fd86b-115">This procedure must be done to provide the Windows Sharepoint Services site that is accessed by the Windows Sharepoint Services adapter in this walkthrough and to set user rights to enable access to this site.</span></span>  
  
#### <a name="create-a-windows-sharepoint-services-site"></a><span data-ttu-id="fd86b-116">创建 Windows SharePoint Services 站点</span><span class="sxs-lookup"><span data-stu-id="fd86b-116">Create a Windows SharePoint Services site</span></span>  
  
1. <span data-ttu-id="fd86b-117">单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**SharePoint 管理中心。**</span><span class="sxs-lookup"><span data-stu-id="fd86b-117">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **SharePoint Central Administration.**</span></span>  
  
2. <span data-ttu-id="fd86b-118">下**虚拟服务器配置**，单击**创建一个顶级网站**。</span><span class="sxs-lookup"><span data-stu-id="fd86b-118">Under **Virtual Server Configuration**, click **Create a top-level Web site**.</span></span>  
  
3. <span data-ttu-id="fd86b-119">下**虚拟服务器列表**，选择在安装 Windows SharePoint Services 适配器的 Web 站点。</span><span class="sxs-lookup"><span data-stu-id="fd86b-119">Under **Virtual Server List**, select the Web site that you installed the Windows SharePoint Services Adapter on.</span></span> <span data-ttu-id="fd86b-120">例如，`Default Web Site`。</span><span class="sxs-lookup"><span data-stu-id="fd86b-120">For example, `Default Web Site`.</span></span>  
  
4. <span data-ttu-id="fd86b-121">在中**网站地址**部分中，在**URL 名称**字段中，键入`WSSAdapterWalkthrough`。</span><span class="sxs-lookup"><span data-stu-id="fd86b-121">In the **Web Site Address** section, in the **URL name** field, type `WSSAdapterWalkthrough`.</span></span>  
  
5. <span data-ttu-id="fd86b-122">在中**站点集合所有者**部分中，在**用户名字段中，** 键入用户名。</span><span class="sxs-lookup"><span data-stu-id="fd86b-122">In the **Site Collection Owner** section, in the **User name field,** type a user name.</span></span> <span data-ttu-id="fd86b-123">此用户将是网站的所有者，不需要特殊权限[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fd86b-123">This user will be the owner for the Web site and does not need special permissions in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
6. <span data-ttu-id="fd86b-124">在中**站点集合所有者**部分中，在**电子邮件**字段中，键入电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="fd86b-124">In the **Site Collection Owner** section, in the **E-mail** field, type in an e-mail address.</span></span>  
  
7. <span data-ttu-id="fd86b-125">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="fd86b-125">Click **OK**.</span></span>  
  
8. <span data-ttu-id="fd86b-126">上**顶层站点已成功创建**页上，单击刚创建的新的顶级网站。</span><span class="sxs-lookup"><span data-stu-id="fd86b-126">On the **Top-Level Site Successfully Created** page, click the new top-level Web site you just created.</span></span> <span data-ttu-id="fd86b-127">例如，`http://<server_name>/sites/WSSAdapterWalkthrough`。</span><span class="sxs-lookup"><span data-stu-id="fd86b-127">For example, `http://<server_name>/sites/WSSAdapterWalkthrough`.</span></span>  
  
9. <span data-ttu-id="fd86b-128">选择**团队网站**的模板，并单击列表中的模板**确定**。</span><span class="sxs-lookup"><span data-stu-id="fd86b-128">Select the **Team Site** template from the list of templates, and then click **OK**.</span></span> <span data-ttu-id="fd86b-129">这将打开工作组网站主页。</span><span class="sxs-lookup"><span data-stu-id="fd86b-129">This will open the Team Web Site Home page.</span></span>  
  
#### <a name="create-a-source-document-library"></a><span data-ttu-id="fd86b-130">创建"Source"文档库</span><span class="sxs-lookup"><span data-stu-id="fd86b-130">Create a "Source" document library</span></span>  
  
1.  <span data-ttu-id="fd86b-131">在团队网站主页上，在顶部导航栏上，单击**创建**。</span><span class="sxs-lookup"><span data-stu-id="fd86b-131">On the Team Web Site Home page, on the top navigation bar, click **Create**.</span></span>  
  
2.  <span data-ttu-id="fd86b-132">下**文档库**，单击**文档库**。</span><span class="sxs-lookup"><span data-stu-id="fd86b-132">Under **Document Libraries**, click **Document Library**.</span></span>  
  
3.  <span data-ttu-id="fd86b-133">在中**名称和描述**部分中，在**名称字段**类型`Source`。</span><span class="sxs-lookup"><span data-stu-id="fd86b-133">In the **Name and Description** section, in the **Name field,** type `Source`.</span></span>  
  
4.  <span data-ttu-id="fd86b-134">在中**导航**部分中，选择**是**快速启动栏上显示此窗体库。</span><span class="sxs-lookup"><span data-stu-id="fd86b-134">In the **Navigation** section, select **Yes** to display this form library on the Quick Launch bar.</span></span>  
  
5.  <span data-ttu-id="fd86b-135">在中**文档模板**部分中，在**文档模板**下拉列表中，选择`None`。</span><span class="sxs-lookup"><span data-stu-id="fd86b-135">In the **Document Template** section, in the **Document Template** drop-down list, select `None`.</span></span>  
  
6.  <span data-ttu-id="fd86b-136">单击 **“创建”**。</span><span class="sxs-lookup"><span data-stu-id="fd86b-136">Click **Create**.</span></span> <span data-ttu-id="fd86b-137">将创建文档库，并且你将重定向到该空库。</span><span class="sxs-lookup"><span data-stu-id="fd86b-137">The document library will be created and you will be redirected to the empty library.</span></span>  
  
#### <a name="create-a-destination-document-library"></a><span data-ttu-id="fd86b-138">创建"Destination"文档库</span><span class="sxs-lookup"><span data-stu-id="fd86b-138">Create a "Destination" document library</span></span>  
  
1.  <span data-ttu-id="fd86b-139">在团队网站主页上，在顶部导航栏上，单击**创建**。</span><span class="sxs-lookup"><span data-stu-id="fd86b-139">On the Team Web Site Home page, on the top navigation bar, click **Create**.</span></span>  
  
2.  <span data-ttu-id="fd86b-140">下**文档库**，单击**文档库**。</span><span class="sxs-lookup"><span data-stu-id="fd86b-140">Under **Document Libraries**, click **Document Library**.</span></span>  
  
3.  <span data-ttu-id="fd86b-141">在中**名称和描述**部分中，在**名称字段**，类型`Destination`。</span><span class="sxs-lookup"><span data-stu-id="fd86b-141">In the **Name and Description** section, in the **Name field**, type `Destination`.</span></span>  
  
4.  <span data-ttu-id="fd86b-142">在中**导航**部分中，选择**是**快速启动栏上显示此窗体库。</span><span class="sxs-lookup"><span data-stu-id="fd86b-142">In the **Navigation** section, select **Yes** to display this form library on the Quick Launch bar.</span></span>  
  
5.  <span data-ttu-id="fd86b-143">在中**文档模板**部分中，在**文档模板**下拉列表中，选择`None`。</span><span class="sxs-lookup"><span data-stu-id="fd86b-143">In the **Document Template** section, in the **Document Template** drop-down list, select `None`.</span></span>  
  
6.  <span data-ttu-id="fd86b-144">单击 **“创建”**。</span><span class="sxs-lookup"><span data-stu-id="fd86b-144">Click **Create**.</span></span> <span data-ttu-id="fd86b-145">将创建文档库，并且你将重定向到该空库。</span><span class="sxs-lookup"><span data-stu-id="fd86b-145">The document library will be created and you will be redirected to the empty library.</span></span>  
  
#### <a name="create-an-archive-document-library"></a><span data-ttu-id="fd86b-146">创建"Archive"文档库</span><span class="sxs-lookup"><span data-stu-id="fd86b-146">Create an "Archive" document library</span></span>  
  
1.  <span data-ttu-id="fd86b-147">在团队网站主页上，在顶部导航栏上，单击**创建**。</span><span class="sxs-lookup"><span data-stu-id="fd86b-147">On the Team Web Site Home page, on the top navigation bar, click **Create**.</span></span>  
  
2.  <span data-ttu-id="fd86b-148">下**文档库**，单击**文档库**。</span><span class="sxs-lookup"><span data-stu-id="fd86b-148">Under **Document Libraries**, click **Document Library**.</span></span>  
  
3.  <span data-ttu-id="fd86b-149">在中**名称**和描述部分，在**名称字段**，类型`Archive`。</span><span class="sxs-lookup"><span data-stu-id="fd86b-149">In the **Name** and Description section, in the **Name field**, type `Archive`.</span></span>  
  
4.  <span data-ttu-id="fd86b-150">在中**导航**部分中，选择**是**快速启动栏上显示此窗体库。</span><span class="sxs-lookup"><span data-stu-id="fd86b-150">In the **Navigation** section, select **Yes** to display this form library on the Quick Launch bar.</span></span>  
  
5.  <span data-ttu-id="fd86b-151">在中**文档模板**部分中，在**文档模板**下拉列表中，选择`None`。</span><span class="sxs-lookup"><span data-stu-id="fd86b-151">In the **Document Template** section, in the **Document Template** drop-down list, select `None`.</span></span>  
  
6.  <span data-ttu-id="fd86b-152">单击 **“创建”**。</span><span class="sxs-lookup"><span data-stu-id="fd86b-152">Click **Create**.</span></span> <span data-ttu-id="fd86b-153">将创建文档库，并且你将重定向到该空库。</span><span class="sxs-lookup"><span data-stu-id="fd86b-153">The document library will be created and you will be redirected to the empty library.</span></span>  
  
7.  <span data-ttu-id="fd86b-154">关闭`WSSAdapterWalkthrough`Web 站点。</span><span class="sxs-lookup"><span data-stu-id="fd86b-154">Close the `WSSAdapterWalkthrough` Web site.</span></span>  
  
8.  <span data-ttu-id="fd86b-155">关闭**SharePoint 管理中心**Web 站点。</span><span class="sxs-lookup"><span data-stu-id="fd86b-155">Close the **SharePoint Central Administration** Web site.</span></span>  
  
#### <a name="configure-windows-security"></a><span data-ttu-id="fd86b-156">配置 Windows 安全性</span><span class="sxs-lookup"><span data-stu-id="fd86b-156">Configure Windows security</span></span>  
  
1.  <span data-ttu-id="fd86b-157">单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**计算机管理**。</span><span class="sxs-lookup"><span data-stu-id="fd86b-157">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Computer Management**.</span></span>  
  
2.  <span data-ttu-id="fd86b-158">在控制台树中，展开**本地用户和组**，然后单击**组**。</span><span class="sxs-lookup"><span data-stu-id="fd86b-158">In the console tree, expand **Local Users and Groups**, and then click **Groups**.</span></span>  
  
3.  <span data-ttu-id="fd86b-159">右键单击**SharePoint Enabled Hosts**组中，单击**将添加到组**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="fd86b-159">Right-click the **SharePoint Enabled Hosts** group, click **Add to Group**, and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="fd86b-160">在中**选择用户、 计算机或组对话框**下**输入要选择的对象名称**，键入配置下，运行，然后单击 BizTalk Server 主机实例的帐户的名称**确定**。</span><span class="sxs-lookup"><span data-stu-id="fd86b-160">In the **Select Users, Computers, or Groups dialog box**, under **Enter the object names to select**, type the name of the account that you configured the BizTalk Server Host Instance to run under, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="fd86b-161">在控制台树中，展开**服务和应用程序**，然后单击**服务**。</span><span class="sxs-lookup"><span data-stu-id="fd86b-161">In the console tree, expand **Services and Applications**, and then click **Services**.</span></span>  
  
6.  <span data-ttu-id="fd86b-162">右键单击**BizTalk 服务 BizTalk 组： < BizTalk_Host_Name >**，然后单击**重新启动**。</span><span class="sxs-lookup"><span data-stu-id="fd86b-162">Right-click **BizTalk Service BizTalk Group: <BizTalk_Host_Name>**, and then click **Restart**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fd86b-163">< BizTalk_Host_Name > 是主机的你的名称。</span><span class="sxs-lookup"><span data-stu-id="fd86b-163"><BizTalk_Host_Name> is the name of your host.</span></span> <span data-ttu-id="fd86b-164">默认情况下，这是`BizTalkServerApplication`。</span><span class="sxs-lookup"><span data-stu-id="fd86b-164">By Default, this is `BizTalkServerApplication`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fd86b-165">重新启动该服务，成员资格才会生效。</span><span class="sxs-lookup"><span data-stu-id="fd86b-165">Membership does not take effect until the service is restarted.</span></span>  
  
7.  <span data-ttu-id="fd86b-166">关闭**计算机管理**。</span><span class="sxs-lookup"><span data-stu-id="fd86b-166">Close **Computer Management**.</span></span>  
  
#### <a name="configure-sharepoint-security"></a><span data-ttu-id="fd86b-167">配置 SharePoint 安全性</span><span class="sxs-lookup"><span data-stu-id="fd86b-167">Configure SharePoint security</span></span>  
  
1. <span data-ttu-id="fd86b-168">打开 Web 浏览器并导航到你创建的站点的 URL。</span><span class="sxs-lookup"><span data-stu-id="fd86b-168">Open a Web browser and navigate to the URL of the site you created.</span></span> <span data-ttu-id="fd86b-169">例如，`http://<server_name>/sites/WSSAdapterWalkthrough`。</span><span class="sxs-lookup"><span data-stu-id="fd86b-169">For example, `http://<server_name>/sites/WSSAdapterWalkthrough`.</span></span>  
  
2. <span data-ttu-id="fd86b-170">在团队网站主页上，在顶部导航栏上，单击**站点设置**。</span><span class="sxs-lookup"><span data-stu-id="fd86b-170">On the Team Web Site Home page, on the top navigation bar, click **Site Settings**.</span></span>  
  
3. <span data-ttu-id="fd86b-171">下**Administration**，单击**管理用户**。</span><span class="sxs-lookup"><span data-stu-id="fd86b-171">Under **Administration**, click **Manage users**.</span></span>  
  
4. <span data-ttu-id="fd86b-172">单击 **“添加用户”**。</span><span class="sxs-lookup"><span data-stu-id="fd86b-172">Click **Add Users**.</span></span>  
  
5. <span data-ttu-id="fd86b-173">在**步骤 1:选择用户**，键入帐户的名称，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]下运行主机实例。</span><span class="sxs-lookup"><span data-stu-id="fd86b-173">In **Step 1: Choose Users**, type the name of the account that the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Host Instance is running under.</span></span>  
  
6. <span data-ttu-id="fd86b-174">在“步骤 2：**选择网站用户组**，选择**读取器**并**参与者**复选框。</span><span class="sxs-lookup"><span data-stu-id="fd86b-174">In **Step 2: Choose Site Groups**, select the **Reader** and **Contributor** check boxes.</span></span>  
  
7. <span data-ttu-id="fd86b-175">单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="fd86b-175">Click **Next**.</span></span>  
  
8. <span data-ttu-id="fd86b-176">清除**发送以下电子邮件以通知这些用户现在他们已被添加**复选框，然后依次**完成**。</span><span class="sxs-lookup"><span data-stu-id="fd86b-176">Clear the **Send the following e-mail to let these users now they've been added** check box, and then click **Finish**.</span></span>  
  
9. <span data-ttu-id="fd86b-177">关闭`WSSAdapterWalkthrough`Web 站点。</span><span class="sxs-lookup"><span data-stu-id="fd86b-177">Close the `WSSAdapterWalkthrough` Web site.</span></span>  
  
## <a name="create-and-configure-the-biztalk-server-ports"></a><span data-ttu-id="fd86b-178">创建和配置 BizTalk Server 端口</span><span class="sxs-lookup"><span data-stu-id="fd86b-178">Create and configure the BizTalk Server ports</span></span>  
 <span data-ttu-id="fd86b-179">在此过程将创建并配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收端口、 接收位置和 Windows SharePoint Services 适配器发送端口。</span><span class="sxs-lookup"><span data-stu-id="fd86b-179">In this procedure you will create and configure the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive ports, receive locations, and send ports for the Windows SharePoint Services adapter.</span></span> <span data-ttu-id="fd86b-180">这些端口是输入和输出的入口点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]用于接收和 Windows Sharepoint Services 适配器发送的文档。</span><span class="sxs-lookup"><span data-stu-id="fd86b-180">These ports are points of entry into and out of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for documents received and sent by the Windows Sharepoint Services adapter.</span></span>  
  
#### <a name="create-the-receive-port"></a><span data-ttu-id="fd86b-181">创建接收端口</span><span class="sxs-lookup"><span data-stu-id="fd86b-181">Create the receive port</span></span>  
  
1. <span data-ttu-id="fd86b-182">单击**启动**，**所有程序**， [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理。**</span><span class="sxs-lookup"><span data-stu-id="fd86b-182">Click **Start**, **All Programs**, [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration.**</span></span>  
  
2. <span data-ttu-id="fd86b-183">展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，展开**应用程序**，展开**BizTalk Application 1**，右键单击**接收端口**，单击**新建**，然后单击**单向接收端口...**</span><span class="sxs-lookup"><span data-stu-id="fd86b-183">Expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, expand **Applications**, expand **BizTalk Application 1**, right-click **Receive Ports**, click **New**, and then click **One-way Receive Port…**</span></span>  
  
3. <span data-ttu-id="fd86b-184">在中**接收端口属性**对话框中的**常规**，类型`FromSource`中**名称**字段。</span><span class="sxs-lookup"><span data-stu-id="fd86b-184">In the **Receive Port Properties** dialog box, under **General**, type `FromSource` in the **Name** field.</span></span>  
  
4. <span data-ttu-id="fd86b-185">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="fd86b-185">Click **OK**.</span></span>  
  
#### <a name="create-the-receive-location"></a><span data-ttu-id="fd86b-186">创建接收位置</span><span class="sxs-lookup"><span data-stu-id="fd86b-186">Create the receive location</span></span>  
  
1.  <span data-ttu-id="fd86b-187">在中**BizTalk 管理控制台**，右键单击**接收位置**节点中，单击**新建**，然后单击**单向接收位置**.</span><span class="sxs-lookup"><span data-stu-id="fd86b-187">In the **BizTalk Administration Console**, right-click the **Receive Locations** node, click **New**, and then click **One-way Receive Location**.</span></span>  
  
2.  <span data-ttu-id="fd86b-188">在中**选择接收端口**对话框中，选择`FromSource`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="fd86b-188">In the **Select a Receive Port** dialog box, select `FromSource`, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="fd86b-189">在中**接收位置属性**对话框中的**常规**，类型`SourceLocation`中**名称**字段。</span><span class="sxs-lookup"><span data-stu-id="fd86b-189">In the **Receive Location Properties** dialog box, under **General**, type `SourceLocation` in the **Name** field.</span></span>  
  
4.  <span data-ttu-id="fd86b-190">在中**传输**部分中，在**类型**下拉列表中，选择`Windows``SharePoint``Services`。</span><span class="sxs-lookup"><span data-stu-id="fd86b-190">In the **Transport** section, in the **Type** drop-down list, select `Windows``SharePoint``Services`.</span></span>  
  
5.  <span data-ttu-id="fd86b-191">单击**配置**配置 Windows SharePoint Services 适配器属性。</span><span class="sxs-lookup"><span data-stu-id="fd86b-191">Click **Configure** to configure the Windows SharePoint Services adapter properties.</span></span>  
  
6.  <span data-ttu-id="fd86b-192">在中**适配器 Web 服务端口**属性中，键入已安装 Windows SharePoint Services 适配器 Web services 虚拟服务器的端口号。</span><span class="sxs-lookup"><span data-stu-id="fd86b-192">In the **Adapter Web Service Port** property, type the port number of the virtual server where the Windows SharePoint Services adapter Web service was installed.</span></span> <span data-ttu-id="fd86b-193">默认情况下，这是端口 80。</span><span class="sxs-lookup"><span data-stu-id="fd86b-193">By default, this is port 80.</span></span>  
  
7.  <span data-ttu-id="fd86b-194">类型`Archive`中**存档位置**属性。</span><span class="sxs-lookup"><span data-stu-id="fd86b-194">Type `Archive` in the **Archive Location** property.</span></span>  
  
8.  <span data-ttu-id="fd86b-195">类型`10`中**轮询间隔**属性。</span><span class="sxs-lookup"><span data-stu-id="fd86b-195">Type `10` in the **Polling Interval** property.</span></span>  
  
9. <span data-ttu-id="fd86b-196">键入指向 SharePoint 站点中的 URL **ShareP**oint 站点 Url 属性。</span><span class="sxs-lookup"><span data-stu-id="fd86b-196">Type the URL to your SharePoint site in the **ShareP**oint Site Url property.</span></span> <span data-ttu-id="fd86b-197">例如，`http://<server_name>/sites/WSSAdapterWalkthrough`。</span><span class="sxs-lookup"><span data-stu-id="fd86b-197">For example, `http://<server_name>/sites/WSSAdapterWalkthrough`.</span></span>  
  
10. <span data-ttu-id="fd86b-198">类型`Source`有关**源文档库**属性。</span><span class="sxs-lookup"><span data-stu-id="fd86b-198">Type `Source` for the **Source Document Library** property.</span></span>  
  
11. <span data-ttu-id="fd86b-199">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="fd86b-199">Click **OK**.</span></span>  
  
12. <span data-ttu-id="fd86b-200">在中**接收位置属性**对话框中，选择`BizTalkServerApplication`作为**接收处理程序**。</span><span class="sxs-lookup"><span data-stu-id="fd86b-200">In the **Receive Location Properties** dialog box, select `BizTalkServerApplication` as the **Receive handler**.</span></span>  
  
13. <span data-ttu-id="fd86b-201">在中**接收管道**下拉列表中，选择`PassThruReceive`。</span><span class="sxs-lookup"><span data-stu-id="fd86b-201">In the **Receive pipeline** drop-down list, select `PassThruReceive`.</span></span>  
  
14. <span data-ttu-id="fd86b-202">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="fd86b-202">Click **OK**.</span></span>  
  
#### <a name="create-the-send-port"></a><span data-ttu-id="fd86b-203">创建发送端口</span><span class="sxs-lookup"><span data-stu-id="fd86b-203">Create the send port</span></span>  
  
1.  <span data-ttu-id="fd86b-204">在中**BizTalk 管理控制台**，右键单击**发送端口**节点中，单击**新建**，然后单击**静态单向发送端口**.</span><span class="sxs-lookup"><span data-stu-id="fd86b-204">In the **BizTalk Administration Console**, right-click the **Send Ports** node, click **New**, and then click **Static One-way Send Port**.</span></span>  
  
2.  <span data-ttu-id="fd86b-205">在中**发送端口属性**对话框中的**常规**，类型`SendToDestination`中**名称**字段。</span><span class="sxs-lookup"><span data-stu-id="fd86b-205">In the **Send Port Properties** dialog box, under **General**, type `SendToDestination` in the **Name** field.</span></span>  
  
3.  <span data-ttu-id="fd86b-206">在中**传输**部分中，选择`Windows SharePoint Services`的类型。</span><span class="sxs-lookup"><span data-stu-id="fd86b-206">In the **Transport** section, select `Windows SharePoint Services` for the type.</span></span>  
  
4.  <span data-ttu-id="fd86b-207">单击**配置**配置 Windows SharePoint Services 适配器属性。</span><span class="sxs-lookup"><span data-stu-id="fd86b-207">Click **Configure** to configure the Windows SharePoint Services adapter properties.</span></span>  
  
5.  <span data-ttu-id="fd86b-208">在中**适配器 Web 服务端口**属性中，键入已安装 Windows SharePoint Services 适配器 Web services 虚拟服务器的端口号。</span><span class="sxs-lookup"><span data-stu-id="fd86b-208">In the **Adapter Web Service Port** property, type the port number of the virtual server where the Windows SharePoint Services adapter Web service was installed.</span></span> <span data-ttu-id="fd86b-209">默认情况下，这是端口 80。</span><span class="sxs-lookup"><span data-stu-id="fd86b-209">By default, this is port 80.</span></span>  
  
6.  <span data-ttu-id="fd86b-210">在键入`Destination`有关**目标文件夹**属性。</span><span class="sxs-lookup"><span data-stu-id="fd86b-210">Type in `Destination` for the **Destination Folder** property.</span></span>  
  
7.  <span data-ttu-id="fd86b-211">在键入`PurchaseOrder1-%MessageID%.xml`有关**文件名**属性。</span><span class="sxs-lookup"><span data-stu-id="fd86b-211">Type in `PurchaseOrder1-%MessageID%.xml` for the **Filename** property.</span></span>  
  
8.  <span data-ttu-id="fd86b-212">设置**覆盖**属性设置为`Yes`。</span><span class="sxs-lookup"><span data-stu-id="fd86b-212">Set the **Overwrite** property to `Yes`.</span></span>  
  
9. <span data-ttu-id="fd86b-213">中的 SharePoint 站点的 URL 中的类型**SharePoint 站点 Url**属性。</span><span class="sxs-lookup"><span data-stu-id="fd86b-213">Type in the URL to your SharePoint site in the **SharePoint Site Url** property.</span></span> <span data-ttu-id="fd86b-214">例如，`http://<server_name>/sites/WSSAdapterWalkthrough`。</span><span class="sxs-lookup"><span data-stu-id="fd86b-214">For example, `http://<server_name>/sites/WSSAdapterWalkthrough`.</span></span>  
  
10. <span data-ttu-id="fd86b-215">设置**Microsoft Office 集成**属性设置为`No`。</span><span class="sxs-lookup"><span data-stu-id="fd86b-215">Set the **Microsoft Office Integration** property to `No`.</span></span>  
  
11. <span data-ttu-id="fd86b-216">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="fd86b-216">Click **OK**.</span></span>  
  
12. <span data-ttu-id="fd86b-217">在中**发送端口属性对话框**，在**发送处理程序**下拉列表中，选择`BizTalkServerApplication`。</span><span class="sxs-lookup"><span data-stu-id="fd86b-217">In the **Send Port Properties dialog box**, in the **Send handler** drop-down list, select `BizTalkServerApplication`.</span></span>  
  
13. <span data-ttu-id="fd86b-218">在中**发送管道**下拉列表中，选择`PassThruTransmit`。</span><span class="sxs-lookup"><span data-stu-id="fd86b-218">In the **Send pipeline** drop-down list, select `PassThruTransmit`.</span></span>  
  
14. <span data-ttu-id="fd86b-219">单击**筛选器**选项卡。</span><span class="sxs-lookup"><span data-stu-id="fd86b-219">Click the **Filters** tab.</span></span>  
  
15. <span data-ttu-id="fd86b-220">选择`WSS.InListName`中**属性**字段。</span><span class="sxs-lookup"><span data-stu-id="fd86b-220">Select `WSS.InListName` in the **Property** field.</span></span>  
  
16. <span data-ttu-id="fd86b-221">选择`==`中**运算符**字段。</span><span class="sxs-lookup"><span data-stu-id="fd86b-221">Select `==` in the **Operator** field.</span></span>  
  
17. <span data-ttu-id="fd86b-222">类型`Source`中**值**字段。</span><span class="sxs-lookup"><span data-stu-id="fd86b-222">Type `Source` in the **Value** field.</span></span>  
  
18. <span data-ttu-id="fd86b-223">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="fd86b-223">Click **OK**.</span></span>  
  
## <a name="enable-and-start-the-receive-location-and-receive-port"></a><span data-ttu-id="fd86b-224">启用并启动接收位置和接收端口</span><span class="sxs-lookup"><span data-stu-id="fd86b-224">Enable and start the receive location and receive port</span></span>  
 <span data-ttu-id="fd86b-225">在这些过程中启用接收位置并启动接收端口。</span><span class="sxs-lookup"><span data-stu-id="fd86b-225">In these procedures you enable the receive location and start the receive port.</span></span> <span data-ttu-id="fd86b-226">必须完成此过程，以允许 Windows Sharepoint Services 适配器发送和接收消息通过指定的发送端口和接收位置。</span><span class="sxs-lookup"><span data-stu-id="fd86b-226">This procedure must be completed to allow the Windows Sharepoint Services adapter to send and receive messages through the specified send port and receive location.</span></span>  
  
#### <a name="enable-the-receive-location"></a><span data-ttu-id="fd86b-227">启用接收位置</span><span class="sxs-lookup"><span data-stu-id="fd86b-227">Enable the receive location</span></span>  
  
1.  <span data-ttu-id="fd86b-228">在中**BizTalk 管理控制台**，单击**接收位置**节点。</span><span class="sxs-lookup"><span data-stu-id="fd86b-228">In the **BizTalk Administration Console**, click the **Receive Locations** node.</span></span>  
  
2.  <span data-ttu-id="fd86b-229">右键单击`SourceLocation`，然后单击**启用**。</span><span class="sxs-lookup"><span data-stu-id="fd86b-229">Right-click `SourceLocation`, and then click **Enable**.</span></span>  
  
#### <a name="start-the-send-port"></a><span data-ttu-id="fd86b-230">启动发送端口</span><span class="sxs-lookup"><span data-stu-id="fd86b-230">Start the send port</span></span>  
  
1.  <span data-ttu-id="fd86b-231">在中**BizTalk 管理控制台**，单击**发送端口**节点。</span><span class="sxs-lookup"><span data-stu-id="fd86b-231">In the **BizTalk Administration Console**, click the **Send Ports** node.</span></span>  
  
2.  <span data-ttu-id="fd86b-232">右键单击`SendToDestination`，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="fd86b-232">Right-click `SendToDestination`, and then click **Start**.</span></span>  
  
3.  <span data-ttu-id="fd86b-233">关闭**BizTalk 管理控制台**。</span><span class="sxs-lookup"><span data-stu-id="fd86b-233">Close the **BizTalk Administration Console**.</span></span>  
  
## <a name="sending-a-message-through-the-system"></a><span data-ttu-id="fd86b-234">通过系统发送消息</span><span class="sxs-lookup"><span data-stu-id="fd86b-234">Sending a message through the system</span></span>  
 <span data-ttu-id="fd86b-235">在此过程中创建 XML 文档并将其上载到 Windows SharePoint Services 网站。</span><span class="sxs-lookup"><span data-stu-id="fd86b-235">In this procedure you create an XML document and upload it to the Windows SharePoint Services Web site.</span></span> <span data-ttu-id="fd86b-236">Windows SharePoint Services 适配器将接受该消息、 将其存档在存档文档库和将其发送给目标文档库中。</span><span class="sxs-lookup"><span data-stu-id="fd86b-236">The Windows SharePoint Services adapter will take that message, archive it in the Archive document library, and then send it to the Destination document library.</span></span> <span data-ttu-id="fd86b-237">此过程说明了文档的流动方式从 Sharepoint 网站， [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，到达 Sharepoint Services 网站使用 Windows Sharepoint Services 适配器。</span><span class="sxs-lookup"><span data-stu-id="fd86b-237">This procedure demonstrates how a document flows from a Sharepoint web site, through [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and to a Sharepoint Services Web site using the Windows Sharepoint Services adapter.</span></span>  
  
#### <a name="create-a-working-directory"></a><span data-ttu-id="fd86b-238">创建工作目录</span><span class="sxs-lookup"><span data-stu-id="fd86b-238">Create a working directory</span></span>  
  
-   <span data-ttu-id="fd86b-239">名为在计算机上创建一个目录**WSSAdapterWalkthrough**。</span><span class="sxs-lookup"><span data-stu-id="fd86b-239">Create a directory on your computer called **WSSAdapterWalkthrough**.</span></span> <span data-ttu-id="fd86b-240">例如，`C:\WSSAdapterWalkthrough`。</span><span class="sxs-lookup"><span data-stu-id="fd86b-240">For example, `C:\WSSAdapterWalkthrough`.</span></span>  
  
#### <a name="create-an-xml-file"></a><span data-ttu-id="fd86b-241">创建一个 XML 文件</span><span class="sxs-lookup"><span data-stu-id="fd86b-241">Create an XML file</span></span>  
  
1.  <span data-ttu-id="fd86b-242">单击**启动**，依次指向**所有程序**，指向**附件**，然后单击**记事本。**</span><span class="sxs-lookup"><span data-stu-id="fd86b-242">Click **Start**, point to **All Programs**, point to **Accessories**, and then click **Notepad.**</span></span>  
  
2.  <span data-ttu-id="fd86b-243">键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="fd86b-243">Type the following:</span></span>  
  
    ```  
    <?xml version="1.0"?>  
    <PurchaseOrder>  
        <ID>1001</ID>  
        <FirstName>John</FirstName>  
        <LastName>Doe</LastName>  
        <Amount>750</Amount>  
    </PurchaseOrder>  
    ```  
  
3.  <span data-ttu-id="fd86b-244">将文件保存在工作目录中为`PurchaseOrder1.xml`。</span><span class="sxs-lookup"><span data-stu-id="fd86b-244">Save the file in your working directory as `PurchaseOrder1.xml`.</span></span> <span data-ttu-id="fd86b-245">例如，`C:\WSSAdapterWalkthrough\PurchaseOrder1.xml`。</span><span class="sxs-lookup"><span data-stu-id="fd86b-245">For example, `C:\WSSAdapterWalkthrough\PurchaseOrder1.xml`.</span></span>  
  
#### <a name="upload-the-xml-file"></a><span data-ttu-id="fd86b-246">上传 XML 文件</span><span class="sxs-lookup"><span data-stu-id="fd86b-246">Upload the XML file</span></span>  
  
1. <span data-ttu-id="fd86b-247">打开 Web 浏览器并导航到上一个任务中创建的站点的 URL。</span><span class="sxs-lookup"><span data-stu-id="fd86b-247">Open a Web browser and navigate to the URL of the site you created in the last task.</span></span> <span data-ttu-id="fd86b-248">例如，`http://<server_name>/sites/WSSAdapterWalkthrough`。</span><span class="sxs-lookup"><span data-stu-id="fd86b-248">For example, `http://<server_name>/sites/WSSAdapterWalkthrough`.</span></span>  
  
2. <span data-ttu-id="fd86b-249">在左侧下,**文档**，单击**源**。</span><span class="sxs-lookup"><span data-stu-id="fd86b-249">On the left side, under **Documents**, click **Source**.</span></span>  
  
3. <span data-ttu-id="fd86b-250">单击**上传文档**。</span><span class="sxs-lookup"><span data-stu-id="fd86b-250">Click **Upload Document**.</span></span>  
  
4. <span data-ttu-id="fd86b-251">在中**名称**框中，键入或浏览到 XML 文件创建。</span><span class="sxs-lookup"><span data-stu-id="fd86b-251">In the **Name** box, type or browse to the XML file you created above.</span></span> <span data-ttu-id="fd86b-252">例如， `C:\WSSAdapterWalkthrough\PurchaseOrder1.xml`，然后单击**保存并关闭**。</span><span class="sxs-lookup"><span data-stu-id="fd86b-252">For example, `C:\WSSAdapterWalkthrough\PurchaseOrder1.xml`, and then click **Save and Close**.</span></span> <span data-ttu-id="fd86b-253">现在应能够看到列表中的文件。</span><span class="sxs-lookup"><span data-stu-id="fd86b-253">You should now be able to see the file in the list.</span></span>  
  
5. <span data-ttu-id="fd86b-254">刷新浏览器窗口。</span><span class="sxs-lookup"><span data-stu-id="fd86b-254">Refresh the browser window.</span></span> <span data-ttu-id="fd86b-255">`PurchaseOrder1.xml`文件将不再在此库中列出。</span><span class="sxs-lookup"><span data-stu-id="fd86b-255">The `PurchaseOrder1.xml` file will no longer be listed in this library.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="fd86b-256">您可能需要刷新浏览器几次，由于轮询间隔设置为 10 秒钟。</span><span class="sxs-lookup"><span data-stu-id="fd86b-256">You may have to refresh the browser a few times since the polling interval is set at 10 seconds.</span></span>  
  
6. <span data-ttu-id="fd86b-257">在顶部导航栏上，单击**文档和列表**。</span><span class="sxs-lookup"><span data-stu-id="fd86b-257">On the top navigation bar, click **Documents and Lists**.</span></span>  
  
7. <span data-ttu-id="fd86b-258">下**文档库**，单击**目标**。</span><span class="sxs-lookup"><span data-stu-id="fd86b-258">Under **Document Libraries**, click **Destination**.</span></span>  
  
8. <span data-ttu-id="fd86b-259">在目标文档库中，现在将看到你的消息已列出。</span><span class="sxs-lookup"><span data-stu-id="fd86b-259">In the Destination Document Library, you will now see your message listed.</span></span> <span data-ttu-id="fd86b-260">您还可以找到在存档文档库中存档的副本。</span><span class="sxs-lookup"><span data-stu-id="fd86b-260">You will also find a copy archived in the Archive Document Library.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="fd86b-261">如果在目标文档库中不显示消息，请参阅"故障排除 Windows SharePoint Services 适配器"中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="fd86b-261">If the message does not appear in the Destination Document Library, refer to "Troubleshooting the Windows SharePoint Services Adapter" in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="fd86b-262">总结</span><span class="sxs-lookup"><span data-stu-id="fd86b-262">Summary</span></span>  
 <span data-ttu-id="fd86b-263">在本演练中，你已了解如何配置 Windows SharePoint Services 和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]以便可以发送和接收消息使用的 Windows SharePoint Services 适配器和基于内容的路由 (CBR)。</span><span class="sxs-lookup"><span data-stu-id="fd86b-263">In this walkthrough you have seen how to configure Windows SharePoint Services and [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] so you can send and receive a message using the Windows SharePoint Services adapter and content-based routing (CBR).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="fd86b-264">后续步骤</span><span class="sxs-lookup"><span data-stu-id="fd86b-264">Next Steps</span></span>  
 <span data-ttu-id="fd86b-265">现在，已完成本演练中，执行[演练：模块 2-Office 与 Windows SharePoint Services 适配器相集成](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md)演练中，它扩展了本演练的工作并演示如何将 Office 与 Windows SharePoint Services 适配器相集成。</span><span class="sxs-lookup"><span data-stu-id="fd86b-265">Now that you have completed this walkthrough, perform the [Walkthrough: Module 2 - Integrating Office with the Windows SharePoint Services Adapter](../core/walkthrough-module-2--integrate-office-with-the-sharepoint-adapter-in-biztalk.md) walkthrough, which expands on the work you have done with this walkthrough and shows you how to integrate Office with the Windows SharePoint Services adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd86b-266">请参阅</span><span class="sxs-lookup"><span data-stu-id="fd86b-266">See Also</span></span>  
 <span data-ttu-id="fd86b-267">[什么是 Windows SharePoint Services 适配器？](../core/what-is-the-windows-sharepoint-services-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="fd86b-267">[What Is the Windows SharePoint Services Adapter?](../core/what-is-the-windows-sharepoint-services-adapter.md) </span></span>  
 [<span data-ttu-id="fd86b-268">Windows SharePoint Services 适配器演练</span><span class="sxs-lookup"><span data-stu-id="fd86b-268">Windows SharePoint Services Adapter Walkthroughs</span></span>](../core/windows-sharepoint-services-adapter-walkthroughs.md)