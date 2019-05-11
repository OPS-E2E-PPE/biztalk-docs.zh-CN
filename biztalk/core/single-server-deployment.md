---
title: 单服务器部署 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9bfd875796613087ba0eda23b539a744f9367050
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392967"
---
# <a name="single-server-deployment"></a><span data-ttu-id="80a64-102">单服务器部署</span><span class="sxs-lookup"><span data-stu-id="80a64-102">Single-Server Deployment</span></span>
<span data-ttu-id="80a64-103">本主题讨论的单服务器安装程序和部署注意事项[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]针对 Windows SharePoint Services 适配器。</span><span class="sxs-lookup"><span data-stu-id="80a64-103">This topic discusses single-server setup and deployment considerations for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adapter for Windows SharePoint Services.</span></span>  
  
## <a name="installing-the-windows-sharepoint-services-adapter-in-a-single-server-deployment"></a><span data-ttu-id="80a64-104">在单服务器部署中安装 Windows SharePoint Services 适配器</span><span class="sxs-lookup"><span data-stu-id="80a64-104">Installing the Windows SharePoint Services adapter in a single-server deployment</span></span>  
 <span data-ttu-id="80a64-105">选择 Windows SharePoint Service 适配器 Web 服务组件将安装必需的软件的 Windows SharePoint Services 适配器处理通过 Windows SharePoint Services 传入和传出的文档。</span><span class="sxs-lookup"><span data-stu-id="80a64-105">Selecting the Windows SharePoint Service adapter Web service component installs the necessary software for the Windows SharePoint Services adapter to process incoming and outgoing documents through Windows SharePoint Services.</span></span> <span data-ttu-id="80a64-106">必须安装 Windows SharePoint Services 的服务器上安装此 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="80a64-106">This Web service must be installed on the server where Windows SharePoint Services is installed.</span></span> <span data-ttu-id="80a64-107">适配器 Web 服务可以处理多个 SharePoint 站点，包括承载业务活动服务 (BAS)，而不考虑它们是否相同的 IIS 站点上或在不同的 IIS 站点上的网站。</span><span class="sxs-lookup"><span data-stu-id="80a64-107">The adapter Web service can handle multiple SharePoint sites including the Web site that hosts Business Activity Services (BAS), regardless of whether they are on the same IIS site or on different IIS sites.</span></span>  
  
 <span data-ttu-id="80a64-108">Windows SharePoint Services 适配器具有三个组件：</span><span class="sxs-lookup"><span data-stu-id="80a64-108">The Windows SharePoint Services adapter has three components:</span></span>  
  
- <span data-ttu-id="80a64-109">运行时组件</span><span class="sxs-lookup"><span data-stu-id="80a64-109">Runtime components</span></span>  
  
- <span data-ttu-id="80a64-110">设计时组件</span><span class="sxs-lookup"><span data-stu-id="80a64-110">Design time components</span></span>  
  
- <span data-ttu-id="80a64-111">适配器 Web 服务</span><span class="sxs-lookup"><span data-stu-id="80a64-111">Adapter Web service</span></span>  
  
  <span data-ttu-id="80a64-112">适配器运行时已安装并配置自动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时功能。</span><span class="sxs-lookup"><span data-stu-id="80a64-112">The adapter runtime is installed and configured automatically by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Runtime feature.</span></span> <span data-ttu-id="80a64-113">适配器设计时组件安装和配置与其他[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]功能。</span><span class="sxs-lookup"><span data-stu-id="80a64-113">The adapter design time components are installed and configured with the other [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] features.</span></span> <span data-ttu-id="80a64-114">通过创建 Windows SharePoint Services 端口通过管理工具、 开发人员工具和 SDK 中包含的工具与设计时组件交互或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时功能。</span><span class="sxs-lookup"><span data-stu-id="80a64-114">You interact with the design time components by creating Windows SharePoint Services ports through tools that are included in the Administration Tools, Developer Tools, and SDK or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Runtime features.</span></span> <span data-ttu-id="80a64-115">您不能自定义运行时的任何配置选项和设计时组件。</span><span class="sxs-lookup"><span data-stu-id="80a64-115">You cannot customize any configuration options for runtime and design time components.</span></span> <span data-ttu-id="80a64-116">可以自定义仅 Windows SharePoint Service 适配器 Web 服务选项。</span><span class="sxs-lookup"><span data-stu-id="80a64-116">You can customize only the Windows SharePoint Service adapter Web service options.</span></span>  
  
  <span data-ttu-id="80a64-117">只有 SharePoint Enabled Hosts 组的成员有权调用该适配器 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="80a64-117">Only members of the SharePoint Enabled Hosts group have permissions to invoke the adapter Web service.</span></span> <span data-ttu-id="80a64-118">有关 Windows SharePoint Services 适配器运行时所需的 Windows SharePoint Services 权限的详细信息，请参阅中的安全性部分[什么是 Windows SharePoint Services 适配器？](../core/what-is-the-windows-sharepoint-services-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="80a64-118">For more information about the Windows SharePoint Services permissions needed by the Windows SharePoint Services adapter runtime, see the security section in [What Is the Windows SharePoint Services Adapter?](../core/what-is-the-windows-sharepoint-services-adapter.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="80a64-119">如果您选择安装 BAS，将自动选择 Windows SharePoint Services 适配器 Web 服务组件。</span><span class="sxs-lookup"><span data-stu-id="80a64-119">The Windows SharePoint Services adapter Web service component will be automatically selected if you choose to install BAS.</span></span>  
  
#### <a name="to-install-the-windows-sharepoint-services-adapter"></a><span data-ttu-id="80a64-120">若要安装的 Windows SharePoint Services 适配器</span><span class="sxs-lookup"><span data-stu-id="80a64-120">To install the Windows SharePoint Services adapter</span></span>  
  
1.  <span data-ttu-id="80a64-121">安装 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="80a64-121">Install BizTalk Server.</span></span> <span data-ttu-id="80a64-122">有关详细信息，请参阅[BizTalk Server 2013 和 2013 R2 安装概述](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)。</span><span class="sxs-lookup"><span data-stu-id="80a64-122">For more information, see [Installation Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5).</span></span>  
  
2.  <span data-ttu-id="80a64-123">上**组件安装**屏幕上，在**可用组件**下**其他软件**，选择**Windows SharePoint Services 适配器Web 服务**。</span><span class="sxs-lookup"><span data-stu-id="80a64-123">On the **Component Installation** screen, under **Available Components**, under **Additional Software**, select **Windows SharePoint Services Adapter Web service**.</span></span>  
  
## <a name="configuring-the-windows-sharepoint-services-adapter-web-service-in-a-single-server-deployment"></a><span data-ttu-id="80a64-124">在单服务器部署中配置 Windows SharePoint Services 适配器 Web services</span><span class="sxs-lookup"><span data-stu-id="80a64-124">Configuring the Windows SharePoint Services adapter Web service in a single-server deployment</span></span>  
 <span data-ttu-id="80a64-125">可以配置 Windows SharePoint Services 适配器使用基本配置或自定义配置。</span><span class="sxs-lookup"><span data-stu-id="80a64-125">You can configure the Windows SharePoint Services adapter using either a basic configuration or a custom configuration.</span></span> <span data-ttu-id="80a64-126">有关这些工具的详细信息，请参阅[BizTalk Server 2013 和 2013 R2 配置概述](http://msdn.microsoft.com/library/aa58c43f-8f0e-4a5c-89b9-db7b8a852a72)。</span><span class="sxs-lookup"><span data-stu-id="80a64-126">For more information about these tools, see [Configuration Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/aa58c43f-8f0e-4a5c-89b9-db7b8a852a72).</span></span>  
  
### <a name="using-a-basic-configuration"></a><span data-ttu-id="80a64-127">使用基本配置</span><span class="sxs-lookup"><span data-stu-id="80a64-127">Using a basic configuration</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="80a64-128">可以使用默认设置来配置服务器。</span><span class="sxs-lookup"><span data-stu-id="80a64-128">allows you to configure the server by using default settings.</span></span> <span data-ttu-id="80a64-129">使用数据库服务器名称、 用户名称和密码输入到配置向导配置服务器的默认设置。</span><span class="sxs-lookup"><span data-stu-id="80a64-129">The default settings for the server are configured using the database server name, user name, and password that you enter into the configuration wizard.</span></span> <span data-ttu-id="80a64-130">在配置 Windows SharePoint Services 适配器 Web services 使用基本配置时，会发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="80a64-130">When you configure the Windows SharePoint Services adapter Web service using a basic configuration, the following happens:</span></span>  
  
-   <span data-ttu-id="80a64-131">创建 SharePoint 启用主机 Windows 组。</span><span class="sxs-lookup"><span data-stu-id="80a64-131">The SharePoint Enabled Hosts Windows group is created.</span></span>  
  
-   <span data-ttu-id="80a64-132">默认网站用于承载 Windows SharePoint Services 适配器</span><span class="sxs-lookup"><span data-stu-id="80a64-132">The Default Web Site is used to host the Windows SharePoint Services Adapter</span></span>  
  
-   <span data-ttu-id="80a64-133">创建 BTSSharePointAdapterWSAppPool 应用程序池并将其配置为还用于运行 Windows SharePoint Services 应用程序池的帐户下运行。</span><span class="sxs-lookup"><span data-stu-id="80a64-133">The BTSSharePointAdapterWSAppPool application pool is created and configured to run under the account that is also used to run the Windows SharePoint Services application pool.</span></span>  
  
-   <span data-ttu-id="80a64-134">创建 BTSharePointAdapterWS 虚拟应用程序并将其配置为在 BTSSharePointAdapterWSAppPool 应用程序池中运行</span><span class="sxs-lookup"><span data-stu-id="80a64-134">The BTSharePointAdapterWS virtual application is created and configured to run in the BTSSharePointAdapterWSAppPool application pool</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="80a64-135">如果此虚拟目录已存在，配置不会更新元数据库中的属性。</span><span class="sxs-lookup"><span data-stu-id="80a64-135">If this virtual directory already exists, configuration will not update the properties in the metabase.</span></span> <span data-ttu-id="80a64-136">必须删除该虚拟目录，并重新进行配置。</span><span class="sxs-lookup"><span data-stu-id="80a64-136">You must delete the virtual directory, and run configuration again.</span></span>  
  
- <span data-ttu-id="80a64-137">BTSharePointAdapterWS 虚拟应用程序包含 Web 服务</span><span class="sxs-lookup"><span data-stu-id="80a64-137">The BTSharePointAdapterWS virtual application contains the Web service</span></span>  
  
  <span data-ttu-id="80a64-138">有关基本配置的详细信息，请参阅[基本配置](http://msdn.microsoft.com/library/abdf3eb5-9779-47ff-bc97-2209eb4b12f5)。</span><span class="sxs-lookup"><span data-stu-id="80a64-138">For more information about basic configuration, see [Basic Configuration](http://msdn.microsoft.com/library/abdf3eb5-9779-47ff-bc97-2209eb4b12f5).</span></span>  
  
### <a name="using-a-custom-configuration"></a><span data-ttu-id="80a64-139">使用自定义配置</span><span class="sxs-lookup"><span data-stu-id="80a64-139">Using a custom configuration</span></span>  
 <span data-ttu-id="80a64-140">BizTalk Server 配置可提供已在本地计算机安装的功能的配置状态的高级分析。</span><span class="sxs-lookup"><span data-stu-id="80a64-140">The BizTalk Server Configuration provides a high-level analysis of the configuration state of the features you have installed on the local computer.</span></span> <span data-ttu-id="80a64-141">该工具，可配置和取消对功能、 配置安全设置，并导入和导出配置，从其他计算机。</span><span class="sxs-lookup"><span data-stu-id="80a64-141">The tool allows you to configure and unconfigure features, configure security settings, and import and export configurations from other computers.</span></span>  
  
 <span data-ttu-id="80a64-142">使用**Windows SharePoint Services 适配器 Web Services**页后，可以在此计算机上配置 Windows SharePoint Services 适配器。</span><span class="sxs-lookup"><span data-stu-id="80a64-142">Use the **Windows SharePoint Services Adapter Web Service** page to configure the Windows SharePoint Services adapter on this computer.</span></span> <span data-ttu-id="80a64-143">下表列出了配置选项。</span><span class="sxs-lookup"><span data-stu-id="80a64-143">The following table lists the configuration options.</span></span>  
  
|<span data-ttu-id="80a64-144">使用此选项</span><span class="sxs-lookup"><span data-stu-id="80a64-144">Use this</span></span>|<span data-ttu-id="80a64-145">执行的操作</span><span class="sxs-lookup"><span data-stu-id="80a64-145">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="80a64-146">**此计算机上启用 Windows SharePoint Services 适配器**</span><span class="sxs-lookup"><span data-stu-id="80a64-146">**Enable Windows SharePoint Services Adapter on this computer**</span></span>|<span data-ttu-id="80a64-147">选择**启用此计算机上 Windows SharePoint Services 适配器**若要启用此计算机上的适配器。</span><span class="sxs-lookup"><span data-stu-id="80a64-147">Select **Enable Windows SharePoint Services Adapter on this computer** to enable the adapter on this computer.</span></span>|  
|<span data-ttu-id="80a64-148">**Windows 组**</span><span class="sxs-lookup"><span data-stu-id="80a64-148">**Windows group**</span></span>|<span data-ttu-id="80a64-149">**Windows 组**列表提供了 BizTalk SharePoint 适配器启用主机 Windows 组的可编辑视图。</span><span class="sxs-lookup"><span data-stu-id="80a64-149">The **Windows group** list provides a view that you can edit of the BizTalk SharePoint Adapter Enabled Hosts Windows group.</span></span>|  
|<span data-ttu-id="80a64-150">**Windows SharePoint Services 适配器网站**</span><span class="sxs-lookup"><span data-stu-id="80a64-150">**Windows SharePoint Services Adapter Web site**</span></span>|<span data-ttu-id="80a64-151">选择将承载 Windows SharePoint Service 适配器 Web 服务的 Web 站点。</span><span class="sxs-lookup"><span data-stu-id="80a64-151">Select the Web site that will host the Windows SharePoint Service adapter Web service.</span></span>|  
  
 <span data-ttu-id="80a64-152">在配置使用自定义配置的 Windows SharePoint Services 适配器时，会发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="80a64-152">When you configure the Windows SharePoint Services adapter using a custom configuration, the following happens:</span></span>  
  
-   <span data-ttu-id="80a64-153">默认情况下创建 SharePoint 启用主机 Windows 组，除非指定另一个 Windows 组</span><span class="sxs-lookup"><span data-stu-id="80a64-153">The SharePoint Enabled Hosts Windows group is created by default unless you specify another Windows group</span></span>  
  
-   <span data-ttu-id="80a64-154">默认网站用于承载 Windows SharePoint Services 适配器，除非指定其他网站</span><span class="sxs-lookup"><span data-stu-id="80a64-154">The Default Web Site is used to host the Windows SharePoint Services adapter unless you specify another Web site</span></span>  
  
-   <span data-ttu-id="80a64-155">创建 BTSSharePointAdapterWSAppPool 应用程序池并将其配置还用于运行 Windows SharePoint Services 应用程序池帐户下运行</span><span class="sxs-lookup"><span data-stu-id="80a64-155">The BTSSharePointAdapterWSAppPool application pool is created and configured to run under the account that is also used to run the Windows SharePoint Services application pool</span></span>  
  
-   <span data-ttu-id="80a64-156">创建 BTSharePointAdapterWS 虚拟应用程序并将其配置为在 BTSSharePointAdapterWSAppPool 应用程序池中运行</span><span class="sxs-lookup"><span data-stu-id="80a64-156">The BTSharePointAdapterWS virtual application is created and configured to run in the BTSSharePointAdapterWSAppPool application pool</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="80a64-157">如果此虚拟目录已存在，配置不会更新元数据库中的属性。</span><span class="sxs-lookup"><span data-stu-id="80a64-157">If this virtual directory already exists, configuration will not update the properties in the metabase.</span></span> <span data-ttu-id="80a64-158">必须删除该虚拟目录，并重新进行配置。</span><span class="sxs-lookup"><span data-stu-id="80a64-158">You must delete the virtual directory, and run configuration again.</span></span>  
  
- <span data-ttu-id="80a64-159">BTSharePointAdapterWS 虚拟应用程序包含 Web 服务</span><span class="sxs-lookup"><span data-stu-id="80a64-159">The BTSharePointAdapterWS virtual application contains the Web service</span></span>  
  
  <span data-ttu-id="80a64-160">有关自定义配置管理器的详细信息，请参阅[导入和导出 BizTalk Server 配置](../install-and-config-guides/import-and-export-biztalk-server-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="80a64-160">For more information about the custom configuration manager, see [Import and Export BizTalk Server Configuration](../install-and-config-guides/import-and-export-biztalk-server-configuration.md).</span></span>  
  
##### <a name="to-configure-the-windows-sharepoint-services-adapter-by-using-a-custom-configuration"></a><span data-ttu-id="80a64-161">若要通过使用自定义配置来配置 Windows SharePoint Services 适配器</span><span class="sxs-lookup"><span data-stu-id="80a64-161">To configure the Windows SharePoint Services adapter by using a custom configuration</span></span>  
  
1.  <span data-ttu-id="80a64-162">在中**BizTalk Server 配置**，选择**SharePoint 适配器**节点。</span><span class="sxs-lookup"><span data-stu-id="80a64-162">In the **BizTalk Server Configuration**, select the **SharePoint adapter** node.</span></span>  
  
2.  <span data-ttu-id="80a64-163">选择**启用此计算机上 Windows SharePoint Services 适配器**。</span><span class="sxs-lookup"><span data-stu-id="80a64-163">Select **Enable Windows SharePoint Services Adapter on this computer**.</span></span>  
  
3.  <span data-ttu-id="80a64-164">下**Windows 组**，选择你将使用适用于 Windows SharePoint Services 适配器的 Windows 组。</span><span class="sxs-lookup"><span data-stu-id="80a64-164">Under **Windows Group**, select the Windows group you will be using for the Windows SharePoint Services adapter.</span></span> <span data-ttu-id="80a64-165">默认情况下，这是 SharePoint Enabled Hosts。</span><span class="sxs-lookup"><span data-stu-id="80a64-165">By default, this is SharePoint Enabled Hosts.</span></span>  
  
4.  <span data-ttu-id="80a64-166">在中**Windows SharePoint Services 适配器网站**下拉列表框中，选择网站将在其中安装适配器组件。</span><span class="sxs-lookup"><span data-stu-id="80a64-166">In the **Windows SharePoint Services Adapter Web Site** drop-down box, select the Web site where the adapter components will be installed.</span></span> <span data-ttu-id="80a64-167">默认情况下，这是默认 Web 站点。</span><span class="sxs-lookup"><span data-stu-id="80a64-167">By default, this is the Default Web Site.</span></span>  
  
5.  <span data-ttu-id="80a64-168">单击**应用配置**。</span><span class="sxs-lookup"><span data-stu-id="80a64-168">Click **Apply Configuration**.</span></span>  
  
## <a name="considerations-for-a-single-server-deployment"></a><span data-ttu-id="80a64-169">单服务器部署的注意事项</span><span class="sxs-lookup"><span data-stu-id="80a64-169">Considerations for a single-server deployment</span></span>  
 <span data-ttu-id="80a64-170">当您设置和部署在单服务器环境中的 Windows SharePoint Services 适配器时，考虑以下方面：</span><span class="sxs-lookup"><span data-stu-id="80a64-170">When you set up and deploy the Windows SharePoint Services adapter in a single-server environment, consider the following:</span></span>  
  
- <span data-ttu-id="80a64-171">BizTalk 服务帐户添加到该服务器上的 SharePoint 启用主机 Windows 组。</span><span class="sxs-lookup"><span data-stu-id="80a64-171">Add the BizTalk Service account to the SharePoint Enabled Hosts Windows group on that server.</span></span>  
  
- <span data-ttu-id="80a64-172">将 SharePoint Enabled Hosts 组添加到 SharePoint 参与者角色使用 SharePoint 管理中心工具。</span><span class="sxs-lookup"><span data-stu-id="80a64-172">Add the SharePoint Enabled Hosts group to the SharePoint Contributors role using the SharePoint Central Administration tool.</span></span>  
  
- <span data-ttu-id="80a64-173">在[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]，SharePoint 适配器 Web 服务来运行的标识需要以下权限：</span><span class="sxs-lookup"><span data-stu-id="80a64-173">On [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)], the identity under which the SharePoint Adapter Web Service runs needs the following permissions:</span></span>  
  
   <span data-ttu-id="80a64-174">**读取**上的权限**Program Files\Microsoft BizTalk Server\<版本\>\Business Activity Services\BTSharePointV3AdapterWS**文件夹。</span><span class="sxs-lookup"><span data-stu-id="80a64-174">**Read** permissions on the **Program Files\Microsoft BizTalk Server \<version\>\Business Activity Services\BTSharePointV3AdapterWS** folder.</span></span> <span data-ttu-id="80a64-175">如果使用的 Windows 和 BizTalk Server 的 64 位版，需要在上设置权限**Program Files (x86) \Microsoft BizTalk Server\<版本\>\Business Activity Services\BTSharePointV3AdapterWS**</span><span class="sxs-lookup"><span data-stu-id="80a64-175">If using a 64-bit version of Windows and BizTalk Server, permissions need to be set on the **Program Files (x86)\Microsoft BizTalk Server \<version\>\Business Activity Services\BTSharePointV3AdapterWS**</span></span>  
  
   <span data-ttu-id="80a64-176">**读取**以下注册表项权限：**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Shared Tools\Web Server\Extensions\12.0\Secure\ConfigDB**。</span><span class="sxs-lookup"><span data-stu-id="80a64-176">**Read** permission on the following registry key: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Shared Tools\Web Server\Extensions\12.0\Secure\ConfigDB**.</span></span>  
  
   <span data-ttu-id="80a64-177">包含 Sharepoint 数据库的 SQL 服务器上的登录权限。</span><span class="sxs-lookup"><span data-stu-id="80a64-177">Logon permissions on the SQL Server that contains the Sharepoint databases.</span></span>  
  
   <span data-ttu-id="80a64-178">成员**公共**并**WSS_Content_Application_Pools** SharePoint 配置数据库中的角色。</span><span class="sxs-lookup"><span data-stu-id="80a64-178">A member of the **Public** and **WSS_Content_Application_Pools** roles within the SharePoint configuration database.</span></span>  
  
   <span data-ttu-id="80a64-179">成员**公共**并**db 所有者**SharePoint 内容数据库中的角色。</span><span class="sxs-lookup"><span data-stu-id="80a64-179">A member of the **Public** and **db owner** roles within the SharePoint content database.</span></span>  
  
- <span data-ttu-id="80a64-180">在安装 Web 服务的网站必须扩展为 SharePoint Services 网站。</span><span class="sxs-lookup"><span data-stu-id="80a64-180">The Web site that you install the Web service on must be extended as a SharePoint Services Web site.</span></span>  
  
- <span data-ttu-id="80a64-181">你可以安装和配置 Windows SharePoint Services 适配器使用无提示安装。</span><span class="sxs-lookup"><span data-stu-id="80a64-181">You can install and configure the Windows SharePoint Services adapter using silent installation.</span></span> <span data-ttu-id="80a64-182">有关详细信息，请参阅[附录 a:无提示安装](../install-and-config-guides/appendix-a-silent-installation.md)。</span><span class="sxs-lookup"><span data-stu-id="80a64-182">For more information, see [Appendix A: Silent Installation](../install-and-config-guides/appendix-a-silent-installation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80a64-183">请参阅</span><span class="sxs-lookup"><span data-stu-id="80a64-183">See Also</span></span>  
 <span data-ttu-id="80a64-184">[Windows SharePoint Services 适配器](../core/windows-sharepoint-services-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="80a64-184">[Windows SharePoint Services Adapter](../core/windows-sharepoint-services-adapter.md) </span></span>  
 [<span data-ttu-id="80a64-185">多服务器部署</span><span class="sxs-lookup"><span data-stu-id="80a64-185">Multiserver Deployment</span></span>](../core/multiserver-deployment.md)