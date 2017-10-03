---
title: "单服务器部署 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows SharePoint Services adapters, deploying
- configuring [Windows SharePoint Services adapters], customizing
- deploying, Windows SharePoint Services adapters
- Windows SharePoint Services adapters, installing
- Windows SharePoint Services adapters, configuring
- configuring [Windows SharePoint Services adapters], single-server deployment
- Windows SharePoint Services adapters, single-server deployment
ms.assetid: 94ba8241-9a30-46ca-b962-721e2d00f420
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 38bb6aa65a77c5473ac2934bd2bd0c59268eb2af
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-server-deployment"></a><span data-ttu-id="74419-102">单服务器部署</span><span class="sxs-lookup"><span data-stu-id="74419-102">Single-Server Deployment</span></span>
<span data-ttu-id="74419-103">本主题将介绍对用于 Windows SharePoint Services 的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 适配器进行单服务器安装和部署时的注意事项。</span><span class="sxs-lookup"><span data-stu-id="74419-103">This topic discusses single-server setup and deployment considerations for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adapter for Windows SharePoint Services.</span></span>  
  
## <a name="installing-the-windows-sharepoint-services-adapter-in-a-single-server-deployment"></a><span data-ttu-id="74419-104">在单服务器部署中安装 Windows SharePoint Services 适配器</span><span class="sxs-lookup"><span data-stu-id="74419-104">Installing the Windows SharePoint Services adapter in a single-server deployment</span></span>  
 <span data-ttu-id="74419-105">选择 Windows SharePoint Service 适配器 Web 服务组件将安装为 Windows SharePoint Services 适配器来处理传入和传出文档通过 Windows SharePoint Services 所必需的软件。</span><span class="sxs-lookup"><span data-stu-id="74419-105">Selecting the Windows SharePoint Service adapter Web service component installs the necessary software for the Windows SharePoint Services adapter to process incoming and outgoing documents through Windows SharePoint Services.</span></span> <span data-ttu-id="74419-106">此 Web Services 必须安装在安装有 Windows SharePoint Services 的服务器上。</span><span class="sxs-lookup"><span data-stu-id="74419-106">This Web service must be installed on the server where Windows SharePoint Services is installed.</span></span> <span data-ttu-id="74419-107">适配器 Web 服务可以处理包括托管业务活动服务 (BAS)，而不考虑它们是否在相同的 IIS 站点或不同的 IIS 站点上的 Web 站点的多个 SharePoint 站点。</span><span class="sxs-lookup"><span data-stu-id="74419-107">The adapter Web service can handle multiple SharePoint sites including the Web site that hosts Business Activity Services (BAS), regardless of whether they are on the same IIS site or on different IIS sites.</span></span>  
  
 <span data-ttu-id="74419-108">Windows SharePoint Services 适配器有三个组件：</span><span class="sxs-lookup"><span data-stu-id="74419-108">The Windows SharePoint Services adapter has three components:</span></span>  
  
-   <span data-ttu-id="74419-109">运行时组件</span><span class="sxs-lookup"><span data-stu-id="74419-109">Runtime components</span></span>  
  
-   <span data-ttu-id="74419-110">设计时组件</span><span class="sxs-lookup"><span data-stu-id="74419-110">Design time components</span></span>  
  
-   <span data-ttu-id="74419-111">适配器 Web Services</span><span class="sxs-lookup"><span data-stu-id="74419-111">Adapter Web service</span></span>  
  
 <span data-ttu-id="74419-112">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 运行时功能将自动安装并配置适配器运行时。</span><span class="sxs-lookup"><span data-stu-id="74419-112">The adapter runtime is installed and configured automatically by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Runtime feature.</span></span> <span data-ttu-id="74419-113">安装和配置与其他适配器的设计时组件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]功能。</span><span class="sxs-lookup"><span data-stu-id="74419-113">The adapter design time components are installed and configured with the other [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] features.</span></span> <span data-ttu-id="74419-114">通过使用管理工具、开发人员工具、SDK 或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 运行时功能附带的工具来创建 Windows SharePoint Services 端口，可以与设计时组件进行交互。</span><span class="sxs-lookup"><span data-stu-id="74419-114">You interact with the design time components by creating Windows SharePoint Services ports through tools that are included in the Administration Tools, Developer Tools, and SDK or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Runtime features.</span></span> <span data-ttu-id="74419-115">你无法自定义运行时和设计时组件的任何配置选项。</span><span class="sxs-lookup"><span data-stu-id="74419-115">You cannot customize any configuration options for runtime and design time components.</span></span> <span data-ttu-id="74419-116">只能自定义 Windows SharePoint Services 适配器 Web Services 选项。</span><span class="sxs-lookup"><span data-stu-id="74419-116">You can customize only the Windows SharePoint Service adapter Web service options.</span></span>  
  
 <span data-ttu-id="74419-117">只有 SharePoint Enabled Hosts 组的成员才具有调用该适配器 Web Services 的权限。</span><span class="sxs-lookup"><span data-stu-id="74419-117">Only members of the SharePoint Enabled Hosts group have permissions to invoke the adapter Web service.</span></span> <span data-ttu-id="74419-118">有关由 Windows SharePoint Services 适配器运行所需的 Windows SharePoint Services 权限的详细信息，请参阅中的安全部分[什么是 Windows SharePoint Services Adapter？](../core/what-is-the-windows-sharepoint-services-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="74419-118">For more information about the Windows SharePoint Services permissions needed by the Windows SharePoint Services adapter runtime, see the security section in [What Is the Windows SharePoint Services Adapter?](../core/what-is-the-windows-sharepoint-services-adapter.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="74419-119">如果选择安装 BAS，系统将自动选择安装 Windows SharePoint Services 适配器 Web Services 组件。</span><span class="sxs-lookup"><span data-stu-id="74419-119">The Windows SharePoint Services adapter Web service component will be automatically selected if you choose to install BAS.</span></span>  
  
#### <a name="to-install-the-windows-sharepoint-services-adapter"></a><span data-ttu-id="74419-120">安装 Windows SharePoint Services 适配器</span><span class="sxs-lookup"><span data-stu-id="74419-120">To install the Windows SharePoint Services adapter</span></span>  
  
1.  <span data-ttu-id="74419-121">安装 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="74419-121">Install BizTalk Server.</span></span> <span data-ttu-id="74419-122">有关详细信息，请参阅[BizTalk Server 2013 和 2013 R2 的安装概述](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)。</span><span class="sxs-lookup"><span data-stu-id="74419-122">For more information, see [Installation Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5).</span></span>  
  
2.  <span data-ttu-id="74419-123">上**组件安装**屏幕上，在**可用组件**下**其他软件**，选择**Windows SharePoint Services AdapterWeb 服务**。</span><span class="sxs-lookup"><span data-stu-id="74419-123">On the **Component Installation** screen, under **Available Components**, under **Additional Software**, select **Windows SharePoint Services Adapter Web service**.</span></span>  
  
## <a name="configuring-the-windows-sharepoint-services-adapter-web-service-in-a-single-server-deployment"></a><span data-ttu-id="74419-124">在单服务器部署中配置 Windows SharePoint Services 适配器 Web Services</span><span class="sxs-lookup"><span data-stu-id="74419-124">Configuring the Windows SharePoint Services adapter Web service in a single-server deployment</span></span>  
 <span data-ttu-id="74419-125">你可以使用基本配置或自定义配置来配置 Windows SharePoint Services 适配器。</span><span class="sxs-lookup"><span data-stu-id="74419-125">You can configure the Windows SharePoint Services adapter using either a basic configuration or a custom configuration.</span></span> <span data-ttu-id="74419-126">有关这些工具的详细信息，请参阅[BizTalk Server 2013 和 2013 R2 配置概述](http://msdn.microsoft.com/library/aa58c43f-8f0e-4a5c-89b9-db7b8a852a72)。</span><span class="sxs-lookup"><span data-stu-id="74419-126">For more information about these tools, see [Configuration Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/aa58c43f-8f0e-4a5c-89b9-db7b8a852a72).</span></span>  
  
### <a name="using-a-basic-configuration"></a><span data-ttu-id="74419-127">使用基本配置</span><span class="sxs-lookup"><span data-stu-id="74419-127">Using a basic configuration</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="74419-128"> 允许用户使用默认设置来配置服务器。</span><span class="sxs-lookup"><span data-stu-id="74419-128"> allows you to configure the server by using default settings.</span></span> <span data-ttu-id="74419-129">服务器的默认配置设置使用的是你在配置向导中输入的数据库服务器名称、用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="74419-129">The default settings for the server are configured using the database server name, user name, and password that you enter into the configuration wizard.</span></span> <span data-ttu-id="74419-130">当使用基本配置对 Windows SharePoint Services 适配器 Web Services 进行配置时，将出现以下结果：</span><span class="sxs-lookup"><span data-stu-id="74419-130">When you configure the Windows SharePoint Services adapter Web service using a basic configuration, the following happens:</span></span>  
  
-   <span data-ttu-id="74419-131">创建 SharePoint Enabled Hosts Windows 组。</span><span class="sxs-lookup"><span data-stu-id="74419-131">The SharePoint Enabled Hosts Windows group is created.</span></span>  
  
-   <span data-ttu-id="74419-132">使用默认网站作为 Windows SharePoint Services 适配器的宿主</span><span class="sxs-lookup"><span data-stu-id="74419-132">The Default Web Site is used to host the Windows SharePoint Services Adapter</span></span>  
  
-   <span data-ttu-id="74419-133">创建并配置为在还用于运行 Windows SharePoint Services 应用程序池的帐户下运行 BTSSharePointAdapterWSAppPool 应用程序池。</span><span class="sxs-lookup"><span data-stu-id="74419-133">The BTSSharePointAdapterWSAppPool application pool is created and configured to run under the account that is also used to run the Windows SharePoint Services application pool.</span></span>  
  
-   <span data-ttu-id="74419-134">创建 BTSharePointAdapterWS 虚拟应用程序，并将其配置为在 BTSSharePointAdapterWSAppPool 应用程序池中运行</span><span class="sxs-lookup"><span data-stu-id="74419-134">The BTSharePointAdapterWS virtual application is created and configured to run in the BTSSharePointAdapterWSAppPool application pool</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="74419-135">如果此虚拟目录已存在，则配置过程将不会更新元数据库中的属性。</span><span class="sxs-lookup"><span data-stu-id="74419-135">If this virtual directory already exists, configuration will not update the properties in the metabase.</span></span> <span data-ttu-id="74419-136">你必须删除该虚拟目录，并重新运行配置。</span><span class="sxs-lookup"><span data-stu-id="74419-136">You must delete the virtual directory, and run configuration again.</span></span>  
  
-   <span data-ttu-id="74419-137">BTSharePointAdapterWS 虚拟应用程序包含 Web Services</span><span class="sxs-lookup"><span data-stu-id="74419-137">The BTSharePointAdapterWS virtual application contains the Web service</span></span>  
  
 <span data-ttu-id="74419-138">有关基本配置的详细信息，请参阅[基本配置](http://msdn.microsoft.com/library/abdf3eb5-9779-47ff-bc97-2209eb4b12f5)。</span><span class="sxs-lookup"><span data-stu-id="74419-138">For more information about basic configuration, see [Basic Configuration](http://msdn.microsoft.com/library/abdf3eb5-9779-47ff-bc97-2209eb4b12f5).</span></span>  
  
### <a name="using-a-custom-configuration"></a><span data-ttu-id="74419-139">使用自定义配置</span><span class="sxs-lookup"><span data-stu-id="74419-139">Using a custom configuration</span></span>  
 <span data-ttu-id="74419-140">BizTalk Server 配置可以对本地计算机上已安装的功能的配置状态进行高级分析。</span><span class="sxs-lookup"><span data-stu-id="74419-140">The BizTalk Server Configuration provides a high-level analysis of the configuration state of the features you have installed on the local computer.</span></span> <span data-ttu-id="74419-141">使用该工具，可以配置功能、取消对功能的配置、配置安全设置，以及将配置导入和导出计算机。</span><span class="sxs-lookup"><span data-stu-id="74419-141">The tool allows you to configure and unconfigure features, configure security settings, and import and export configurations from other computers.</span></span>  
  
 <span data-ttu-id="74419-142">使用**Windows SharePoint Services 适配器 Web 服务**页后，可以在此计算机上配置 Windows SharePoint Services 适配器。</span><span class="sxs-lookup"><span data-stu-id="74419-142">Use the **Windows SharePoint Services Adapter Web Service** page to configure the Windows SharePoint Services adapter on this computer.</span></span> <span data-ttu-id="74419-143">下表列出了这些配置选项：</span><span class="sxs-lookup"><span data-stu-id="74419-143">The following table lists the configuration options.</span></span>  
  
|<span data-ttu-id="74419-144">使用此选项</span><span class="sxs-lookup"><span data-stu-id="74419-144">Use this</span></span>|<span data-ttu-id="74419-145">执行的操作</span><span class="sxs-lookup"><span data-stu-id="74419-145">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="74419-146">**在此计算机上启用 Windows SharePoint Services Adapter**</span><span class="sxs-lookup"><span data-stu-id="74419-146">**Enable Windows SharePoint Services Adapter on this computer**</span></span>|<span data-ttu-id="74419-147">选择**启用这台计算机上 Windows SharePoint Services Adapter**若要启用此计算机上的适配器。</span><span class="sxs-lookup"><span data-stu-id="74419-147">Select **Enable Windows SharePoint Services Adapter on this computer** to enable the adapter on this computer.</span></span>|  
|<span data-ttu-id="74419-148">**Windows 组**</span><span class="sxs-lookup"><span data-stu-id="74419-148">**Windows group**</span></span>|<span data-ttu-id="74419-149">**Windows 组**列表提供了你可以编辑 BizTalk SharePoint 适配器启用主机 Windows 组的视图。</span><span class="sxs-lookup"><span data-stu-id="74419-149">The **Windows group** list provides a view that you can edit of the BizTalk SharePoint Adapter Enabled Hosts Windows group.</span></span>|  
|<span data-ttu-id="74419-150">**Windows SharePoint Services 适配器网站**</span><span class="sxs-lookup"><span data-stu-id="74419-150">**Windows SharePoint Services Adapter Web site**</span></span>|<span data-ttu-id="74419-151">选择将用作 Windows SharePoint Services 适配器 Web Services 的宿主的网站。</span><span class="sxs-lookup"><span data-stu-id="74419-151">Select the Web site that will host the Windows SharePoint Service adapter Web service.</span></span>|  
  
 <span data-ttu-id="74419-152">当配置使用自定义配置的 Windows SharePoint Services 适配器时，将发生下列情况：</span><span class="sxs-lookup"><span data-stu-id="74419-152">When you configure the Windows SharePoint Services adapter using a custom configuration, the following happens:</span></span>  
  
-   <span data-ttu-id="74419-153">默认情况下，除非指定了其他 Windows 组，否则将创建 SharePoint Enabled Hosts 这一 Windows 组。</span><span class="sxs-lookup"><span data-stu-id="74419-153">The SharePoint Enabled Hosts Windows group is created by default unless you specify another Windows group</span></span>  
  
-   <span data-ttu-id="74419-154">除非指定其他网站，否则将使用默认网站作为 Windows SharePoint Services 适配器的宿主。</span><span class="sxs-lookup"><span data-stu-id="74419-154">The Default Web Site is used to host the Windows SharePoint Services adapter unless you specify another Web site</span></span>  
  
-   <span data-ttu-id="74419-155">创建 BTSSharePointAdapterWSAppPool 应用程序池，并将其配置为使用运行 Windows SharePoint Services 应用程序池所用的同一帐户来运行。</span><span class="sxs-lookup"><span data-stu-id="74419-155">The BTSSharePointAdapterWSAppPool application pool is created and configured to run under the account that is also used to run the Windows SharePoint Services application pool</span></span>  
  
-   <span data-ttu-id="74419-156">创建 BTSharePointAdapterWS 虚拟应用程序，并将其配置为在 BTSSharePointAdapterWSAppPool 应用程序池中运行</span><span class="sxs-lookup"><span data-stu-id="74419-156">The BTSharePointAdapterWS virtual application is created and configured to run in the BTSSharePointAdapterWSAppPool application pool</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="74419-157">如果此虚拟目录已存在，则配置过程将不会更新元数据库中的属性。</span><span class="sxs-lookup"><span data-stu-id="74419-157">If this virtual directory already exists, configuration will not update the properties in the metabase.</span></span> <span data-ttu-id="74419-158">你必须删除该虚拟目录，并重新运行配置。</span><span class="sxs-lookup"><span data-stu-id="74419-158">You must delete the virtual directory, and run configuration again.</span></span>  
  
-   <span data-ttu-id="74419-159">BTSharePointAdapterWS 虚拟应用程序包含 Web Services</span><span class="sxs-lookup"><span data-stu-id="74419-159">The BTSharePointAdapterWS virtual application contains the Web service</span></span>  
  
 <span data-ttu-id="74419-160">有关自定义配置管理器的详细信息，请参阅[导入和导出 BizTalk Server 配置](../install-and-config-guides/import-and-export-biztalk-server-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="74419-160">For more information about the custom configuration manager, see [Import and Export BizTalk Server Configuration](../install-and-config-guides/import-and-export-biztalk-server-configuration.md).</span></span>  
  
##### <a name="to-configure-the-windows-sharepoint-services-adapter-by-using-a-custom-configuration"></a><span data-ttu-id="74419-161">若要使用自定义配置配置的 Windows SharePoint Services 适配器</span><span class="sxs-lookup"><span data-stu-id="74419-161">To configure the Windows SharePoint Services adapter by using a custom configuration</span></span>  
  
1.  <span data-ttu-id="74419-162">在**BizTalk Server 配置**，选择**SharePoint 适配器**节点。</span><span class="sxs-lookup"><span data-stu-id="74419-162">In the **BizTalk Server Configuration**, select the **SharePoint adapter** node.</span></span>  
  
2.  <span data-ttu-id="74419-163">选择**启用这台计算机上 Windows SharePoint Services Adapter**。</span><span class="sxs-lookup"><span data-stu-id="74419-163">Select **Enable Windows SharePoint Services Adapter on this computer**.</span></span>  
  
3.  <span data-ttu-id="74419-164">下**Windows 组**，选择将用于 Windows SharePoint Services 适配器的 Windows 组。</span><span class="sxs-lookup"><span data-stu-id="74419-164">Under **Windows Group**, select the Windows group you will be using for the Windows SharePoint Services adapter.</span></span> <span data-ttu-id="74419-165">默认情况下，将选择 SharePoint Enabled Hosts。</span><span class="sxs-lookup"><span data-stu-id="74419-165">By default, this is SharePoint Enabled Hosts.</span></span>  
  
4.  <span data-ttu-id="74419-166">在**Windows SharePoint Services 适配器网站**下拉列表中，选择网站将在其中安装适配器组件。</span><span class="sxs-lookup"><span data-stu-id="74419-166">In the **Windows SharePoint Services Adapter Web Site** drop-down box, select the Web site where the adapter components will be installed.</span></span> <span data-ttu-id="74419-167">默认情况下，将选择默认网站。</span><span class="sxs-lookup"><span data-stu-id="74419-167">By default, this is the Default Web Site.</span></span>  
  
5.  <span data-ttu-id="74419-168">单击“应用配置”。</span><span class="sxs-lookup"><span data-stu-id="74419-168">Click **Apply Configuration**.</span></span>  
  
## <a name="considerations-for-a-single-server-deployment"></a><span data-ttu-id="74419-169">单服务器部署的注意事项</span><span class="sxs-lookup"><span data-stu-id="74419-169">Considerations for a single-server deployment</span></span>  
 <span data-ttu-id="74419-170">在单服务器环境中安装和部署 Windows SharePoint Services 适配器时，应注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="74419-170">When you set up and deploy the Windows SharePoint Services adapter in a single-server environment, consider the following:</span></span>  
  
-   <span data-ttu-id="74419-171">将 BizTalk 服务帐户添加到该服务器上的 SharePoint Enabled Hosts 这一 Windows 组中。</span><span class="sxs-lookup"><span data-stu-id="74419-171">Add the BizTalk Service account to the SharePoint Enabled Hosts Windows group on that server.</span></span>  
  
-   <span data-ttu-id="74419-172">使用 SharePoint 管理中心工具，将 SharePoint Enabled Hosts 组添加到 SharePoint 参与者角色中。</span><span class="sxs-lookup"><span data-stu-id="74419-172">Add the SharePoint Enabled Hosts group to the SharePoint Contributors role using the SharePoint Central Administration tool.</span></span>  
  
-   <span data-ttu-id="74419-173">在 [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] 上，运行 SharePoint 适配器 Web Service 的标识需要具有以下权限：</span><span class="sxs-lookup"><span data-stu-id="74419-173">On [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)], the identity under which the SharePoint Adapter Web Service runs needs the following permissions:</span></span>  
  
     <span data-ttu-id="74419-174">**读取**权限**Program Files\Microsoft BizTalk Server\<版本 > \Business Activity Services\BTSharePointV3AdapterWS**文件夹。</span><span class="sxs-lookup"><span data-stu-id="74419-174">**Read** permissions on the **Program Files\Microsoft BizTalk Server \<version>\Business Activity Services\BTSharePointV3AdapterWS** folder.</span></span> <span data-ttu-id="74419-175">如果使用的 Windows 和 BizTalk Server 的 64 位版本，需要在上设置权限**Program Files (x86) \Microsoft BizTalk Server\<版本 > \Business Activity Services\BTSharePointV3AdapterWS**</span><span class="sxs-lookup"><span data-stu-id="74419-175">If using a 64-bit version of Windows and BizTalk Server, permissions need to be set on the **Program Files (x86)\Microsoft BizTalk Server \<version>\Business Activity Services\BTSharePointV3AdapterWS**</span></span>  
  
     <span data-ttu-id="74419-176">**读取**对以下注册表项的权限： **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Shared Tools\Web Server\Extensions\12.0\Secure\ConfigDB**。</span><span class="sxs-lookup"><span data-stu-id="74419-176">**Read** permission on the following registry key: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Shared Tools\Web Server\Extensions\12.0\Secure\ConfigDB**.</span></span>  
  
     <span data-ttu-id="74419-177">包含 Sharepoint 数据库的 SQL Server 的登录权限。</span><span class="sxs-lookup"><span data-stu-id="74419-177">Logon permissions on the SQL Server that contains the Sharepoint databases.</span></span>  
  
     <span data-ttu-id="74419-178">成员**公共**和**WSS_Content_Application_Pools** SharePoint 配置数据库中的角色。</span><span class="sxs-lookup"><span data-stu-id="74419-178">A member of the **Public** and **WSS_Content_Application_Pools** roles within the SharePoint configuration database.</span></span>  
  
     <span data-ttu-id="74419-179">成员**公共**和**db 所有者**SharePoint 内容数据库中的角色。</span><span class="sxs-lookup"><span data-stu-id="74419-179">A member of the **Public** and **db owner** roles within the SharePoint content database.</span></span>  
  
-   <span data-ttu-id="74419-180">必须将 Web Services 安装所在的网站扩展为 SharePoint Services 网站。</span><span class="sxs-lookup"><span data-stu-id="74419-180">The Web site that you install the Web service on must be extended as a SharePoint Services Web site.</span></span>  
  
-   <span data-ttu-id="74419-181">你可以安装和配置使用无提示安装的 Windows SharePoint Services 适配器。</span><span class="sxs-lookup"><span data-stu-id="74419-181">You can install and configure the Windows SharePoint Services adapter using silent installation.</span></span> <span data-ttu-id="74419-182">有关详细信息，请参阅[附录 a： 无提示安装](../install-and-config-guides/appendix-a-silent-installation.md)。</span><span class="sxs-lookup"><span data-stu-id="74419-182">For more information, see [Appendix A: Silent Installation](../install-and-config-guides/appendix-a-silent-installation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74419-183">另请参阅</span><span class="sxs-lookup"><span data-stu-id="74419-183">See Also</span></span>  
 <span data-ttu-id="74419-184">[Windows SharePoint Services Adapter](../core/windows-sharepoint-services-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="74419-184">[Windows SharePoint Services Adapter](../core/windows-sharepoint-services-adapter.md) </span></span>  
 [<span data-ttu-id="74419-185">多服务器部署</span><span class="sxs-lookup"><span data-stu-id="74419-185">Multiserver Deployment</span></span>](../core/multiserver-deployment.md)