---
title: 多服务器部署 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [Windows SharePoint Services adapters], multi-server deployment
- planning, Windows SharePoint Services adapters
- Windows SharePoint Services adapters, deploying
- Windows SharePoint Services adapters, multi-server deployment
- deploying, Windows SharePoint Services adapters
- Windows SharePoint Services adapters, installing
ms.assetid: 0c6e2aa0-e873-461b-8101-9b0988019597
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a767c0edd8c174919979ece2d42cf21b1b6bb7bd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323752"
---
# <a name="multiserver-deployment"></a><span data-ttu-id="0a25f-102">多服务器部署</span><span class="sxs-lookup"><span data-stu-id="0a25f-102">Multiserver Deployment</span></span>
<span data-ttu-id="0a25f-103">本主题讨论在多服务器安装和部署注意事项[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]针对 Windows SharePoint Services 适配器。</span><span class="sxs-lookup"><span data-stu-id="0a25f-103">This topic discusses multiserver setup and deployment considerations for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adapter for Windows SharePoint Services.</span></span>  
  
## <a name="installing-the-windows-sharepoint-services-adapter-in-a-multiserver-deployment"></a><span data-ttu-id="0a25f-104">在多服务器部署中安装 Windows SharePoint Services 适配器</span><span class="sxs-lookup"><span data-stu-id="0a25f-104">Installing the Windows SharePoint Services adapter in a multiserver deployment</span></span>  
 <span data-ttu-id="0a25f-105">选择 Windows SharePoint Services 适配器 Web Services 组件将安装必需的软件的 Windows SharePoint Services 适配器处理通过 Windows SharePoint Services 传入和传出的文档。</span><span class="sxs-lookup"><span data-stu-id="0a25f-105">Selecting the Windows SharePoint Service Adapter Web Service component installs the necessary software for the Windows SharePoint Services adapter to process incoming and outgoing documents through Windows SharePoint Services.</span></span> <span data-ttu-id="0a25f-106">必须安装 Windows SharePoint Services 的服务器上安装此 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="0a25f-106">This Web service must be installed on the server where Windows SharePoint Services is installed.</span></span>  
  
 <span data-ttu-id="0a25f-107">适配器 Web 服务可以处理多个 SharePoint 站点，无论它们是相同的 IIS 站点上或位于不同的 IIS 站点。</span><span class="sxs-lookup"><span data-stu-id="0a25f-107">The adapter Web service can handle multiple SharePoint sites regardless of whether they are on the same IIS site or on different IIS sites.</span></span>  
  
 <span data-ttu-id="0a25f-108">Windows SharePoint Services 适配器具有三个组件：</span><span class="sxs-lookup"><span data-stu-id="0a25f-108">The Windows SharePoint Services Adapter has three components:</span></span>  
  
- <span data-ttu-id="0a25f-109">运行时组件</span><span class="sxs-lookup"><span data-stu-id="0a25f-109">Runtime components</span></span>  
  
- <span data-ttu-id="0a25f-110">设计时组件</span><span class="sxs-lookup"><span data-stu-id="0a25f-110">Design time components</span></span>  
  
- <span data-ttu-id="0a25f-111">适配器 Web 服务</span><span class="sxs-lookup"><span data-stu-id="0a25f-111">Adapter Web service</span></span>  
  
  <span data-ttu-id="0a25f-112">适配器运行时已安装并配置自动[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时功能。</span><span class="sxs-lookup"><span data-stu-id="0a25f-112">The adapter runtime is installed and configured automatically by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Runtime feature.</span></span> <span data-ttu-id="0a25f-113">适配器设计时组件安装和配置与其他[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]功能。</span><span class="sxs-lookup"><span data-stu-id="0a25f-113">The adapter design time components are installed and configured with other [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] features.</span></span> <span data-ttu-id="0a25f-114">通过创建 Windows SharePoint Services 端口通过管理工具、 开发人员工具和 SDK 中包含的工具与设计时组件交互或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时功能。</span><span class="sxs-lookup"><span data-stu-id="0a25f-114">You interact with the design time components by creating Windows SharePoint Services ports through tools that are included in the Administration Tools, Developer Tools, and SDK or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Runtime features.</span></span> <span data-ttu-id="0a25f-115">您不能自定义运行时的任何配置选项和设计时组件。</span><span class="sxs-lookup"><span data-stu-id="0a25f-115">You cannot customize any configuration options for runtime and design time components.</span></span> <span data-ttu-id="0a25f-116">可以自定义仅 Windows SharePoint Services 适配器 Web 服务选项。</span><span class="sxs-lookup"><span data-stu-id="0a25f-116">You can customize only the Windows SharePoint Services adapter Web Service options.</span></span>  
  
  <span data-ttu-id="0a25f-117">只有 SharePoint Enabled Hosts 组的成员将有权调用该适配器 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="0a25f-117">Only members of the SharePoint Enabled Hosts group will have permissions to invoke the adapter Web service.</span></span> <span data-ttu-id="0a25f-118">有关 Windows SharePoint Services 适配器运行时所需的 Windows SharePoint Services 权限的详细信息，请参阅中的安全性部分[什么是 Windows SharePoint Services 适配器？](../core/what-is-the-windows-sharepoint-services-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="0a25f-118">For more information about the Windows SharePoint Services permissions needed by the Windows SharePoint Services adapter runtime, see the security section in [What Is the Windows SharePoint Services Adapter?](../core/what-is-the-windows-sharepoint-services-adapter.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0a25f-119">如果您选择安装 BAS，将自动选择 Windows SharePoint Services 适配器 Web 服务组件。</span><span class="sxs-lookup"><span data-stu-id="0a25f-119">The Windows SharePoint Services adapter Web service component will be automatically selected if you choose to install BAS.</span></span>  
  
#### <a name="to-install-the-windows-sharepoint-services-adapter"></a><span data-ttu-id="0a25f-120">若要安装的 Windows SharePoint Services 适配器</span><span class="sxs-lookup"><span data-stu-id="0a25f-120">To install the Windows SharePoint Services adapter</span></span>  
  
1. <span data-ttu-id="0a25f-121">安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0a25f-121">Install [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="0a25f-122">有关详细信息，请参阅[BizTalk Server 2013 和 2013 R2 安装概述](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)。</span><span class="sxs-lookup"><span data-stu-id="0a25f-122">For more information, see [Installation Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5).</span></span>  
  
2. <span data-ttu-id="0a25f-123">上**组件安装**屏幕上，在**可用组件**下**其他软件**，选择**Windows SharePoint Services 适配器Web 服务**。</span><span class="sxs-lookup"><span data-stu-id="0a25f-123">On the **Component Installation** screen, under **Available Components**, under **Additional Software**, select **Windows SharePoint Services Adapter Web service**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0a25f-124">您必须安装和配置在计算机上运行该主机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时和计算机正在运行 Windows SharePoint Services。</span><span class="sxs-lookup"><span data-stu-id="0a25f-124">You must run setup and configuration on the computer that hosts the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime and the computer running Windows SharePoint Services.</span></span>  
  
## <a name="configuring-the-windows-sharepoint-services-adapter-web-service-in-a-multiserver-deployment"></a><span data-ttu-id="0a25f-125">在多服务器部署中配置 Windows SharePoint Services 适配器 Web services</span><span class="sxs-lookup"><span data-stu-id="0a25f-125">Configuring the Windows SharePoint Services adapter Web service in a multiserver deployment</span></span>  
 <span data-ttu-id="0a25f-126">配置 Windows SharePoint Services 适配器使用 BizTalk Server 配置。</span><span class="sxs-lookup"><span data-stu-id="0a25f-126">You configure the Windows SharePoint Services adapter using the BizTalk Server Configuration.</span></span> <span data-ttu-id="0a25f-127">有关这些工具的详细信息，请参阅[BizTalk Server 2013 和 2013 R2 配置概述](http://msdn.microsoft.com/library/aa58c43f-8f0e-4a5c-89b9-db7b8a852a72)。</span><span class="sxs-lookup"><span data-stu-id="0a25f-127">For more information about these tools, see [Configuration Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/aa58c43f-8f0e-4a5c-89b9-db7b8a852a72).</span></span>  
  
### <a name="using-a-custom-configuration"></a><span data-ttu-id="0a25f-128">使用自定义配置</span><span class="sxs-lookup"><span data-stu-id="0a25f-128">Using a custom configuration</span></span>  
 <span data-ttu-id="0a25f-129">BizTalk Server 配置可提供已在本地计算机安装的功能的配置状态的高级分析。</span><span class="sxs-lookup"><span data-stu-id="0a25f-129">The BizTalk Server Configuration provides a high-level analysis of the configuration state of the features you have installed on the local computer.</span></span> <span data-ttu-id="0a25f-130">该工具，可配置和取消对功能、 配置安全设置，并导入和导出配置，从其他计算机。</span><span class="sxs-lookup"><span data-stu-id="0a25f-130">The tool allows you to configure and unconfigure features, configure security settings, and import and export configurations from other computers.</span></span>  
  
 <span data-ttu-id="0a25f-131">使用**Windows SharePoint Services**页后，可以在此计算机上配置 Windows SharePoint Services 适配器。</span><span class="sxs-lookup"><span data-stu-id="0a25f-131">Use the **Windows SharePoint Services** page to configure the Windows SharePoint Services adapter on this computer.</span></span> <span data-ttu-id="0a25f-132">下表列出了配置选项。</span><span class="sxs-lookup"><span data-stu-id="0a25f-132">The following table lists the configuration options.</span></span>  
  
|<span data-ttu-id="0a25f-133">使用此选项</span><span class="sxs-lookup"><span data-stu-id="0a25f-133">Use this</span></span>|<span data-ttu-id="0a25f-134">执行的操作</span><span class="sxs-lookup"><span data-stu-id="0a25f-134">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="0a25f-135">**此计算机上启用 Windows SharePoint Services 适配器**</span><span class="sxs-lookup"><span data-stu-id="0a25f-135">**Enable Windows SharePoint Services Adapter on this computer**</span></span>|<span data-ttu-id="0a25f-136">选择**启用此计算机上 Windows SharePoint Services 适配器**若要启用此计算机上的适配器。</span><span class="sxs-lookup"><span data-stu-id="0a25f-136">Select **Enable Windows SharePoint Services Adapter on this computer** to enable the adapter on this computer.</span></span>|  
|<span data-ttu-id="0a25f-137">**Windows 组**</span><span class="sxs-lookup"><span data-stu-id="0a25f-137">**Windows group**</span></span>|<span data-ttu-id="0a25f-138">**Windows 组**列表提供了 BizTalk SharePoint 适配器启用主机 Windows 组的可编辑视图。</span><span class="sxs-lookup"><span data-stu-id="0a25f-138">The **Windows group** list provides a view that you can edit of the BizTalk SharePoint Adapter Enabled Hosts Windows group.</span></span>|  
|<span data-ttu-id="0a25f-139">**Windows SharePoint Services 适配器网站**</span><span class="sxs-lookup"><span data-stu-id="0a25f-139">**Windows SharePoint Services Adapter Web site**</span></span>|<span data-ttu-id="0a25f-140">选择将承载 Windows SharePoint Services 适配器 Web services 的 Web 站点。</span><span class="sxs-lookup"><span data-stu-id="0a25f-140">Select the Web site that will host the Windows SharePoint Services adapter Web service.</span></span>|  
  
 <span data-ttu-id="0a25f-141">在配置使用自定义配置的 Windows SharePoint Services 适配器时，会发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="0a25f-141">When you configure the Windows SharePoint Services adapter using custom configuration, the following happens:</span></span>  
  
-   <span data-ttu-id="0a25f-142">默认情况下创建 SharePoint 启用主机 Windows 组，除非指定另一个 Windows 组</span><span class="sxs-lookup"><span data-stu-id="0a25f-142">The SharePoint Enabled Hosts Windows group is created by default unless you specify another Windows group</span></span>  
  
-   <span data-ttu-id="0a25f-143">默认网站用于承载 Windows SharePoint Services 适配器，除非指定其他网站</span><span class="sxs-lookup"><span data-stu-id="0a25f-143">The Default Web Site is used to host the Windows SharePoint Services adapter unless you specify another Web site</span></span>  
  
-   <span data-ttu-id="0a25f-144">创建 BTSSharePointAdapterWSAppPool 应用程序池并将其配置还用于运行 Windows SharePoint Services 应用程序池帐户下运行</span><span class="sxs-lookup"><span data-stu-id="0a25f-144">The BTSSharePointAdapterWSAppPool application pool is created and configured to run under the account that is also used to run the Windows SharePoint Services application pool</span></span>  
  
-   <span data-ttu-id="0a25f-145">创建 BTSharePointAdapterWS 虚拟应用程序并将其配置为在 BTSSharePointAdapterWSAppPool 应用程序池中运行</span><span class="sxs-lookup"><span data-stu-id="0a25f-145">The BTSharePointAdapterWS virtual application is created and configured to run in the BTSSharePointAdapterWSAppPool application pool</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0a25f-146">如果此虚拟目录已存在，配置不会更新元数据库中的属性。</span><span class="sxs-lookup"><span data-stu-id="0a25f-146">If this virtual directory already exists, configuration will not update the properties in the metabase.</span></span> <span data-ttu-id="0a25f-147">必须删除该虚拟目录，并重新进行配置。</span><span class="sxs-lookup"><span data-stu-id="0a25f-147">You must delete the virtual directory and run configuration again.</span></span>  
  
- <span data-ttu-id="0a25f-148">BTSharePointAdapterWS 虚拟应用程序包含 Web 服务</span><span class="sxs-lookup"><span data-stu-id="0a25f-148">The BTSharePointAdapterWS virtual application contains the Web service</span></span>  
  
  <span data-ttu-id="0a25f-149">有关 BizTalk Server 配置的详细信息，请参阅[导入和导出 BizTalk Server 配置](../install-and-config-guides/import-and-export-biztalk-server-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="0a25f-149">For more information about the BizTalk Server Configuration, see [Import and Export BizTalk Server Configuration](../install-and-config-guides/import-and-export-biztalk-server-configuration.md).</span></span>  
  
##### <a name="to-configure-the-windows-sharepoint-services-adapter-by-using-custom-configuration"></a><span data-ttu-id="0a25f-150">若要通过使用自定义配置来配置 Windows SharePoint Services 适配器</span><span class="sxs-lookup"><span data-stu-id="0a25f-150">To configure the Windows SharePoint Services adapter by using custom configuration</span></span>  
  
1. <span data-ttu-id="0a25f-151">在中**BizTalk Server 配置**，选择**SharePoint 适配器**节点。</span><span class="sxs-lookup"><span data-stu-id="0a25f-151">In the **BizTalk Server Configuration**, select the **SharePoint adapter** node.</span></span>  
  
2. <span data-ttu-id="0a25f-152">选择**启用此计算机上 Windows SharePoint Services 适配器**。</span><span class="sxs-lookup"><span data-stu-id="0a25f-152">Select **Enable Windows SharePoint Services Adapter on this computer**.</span></span>  
  
3. <span data-ttu-id="0a25f-153">下**Windows 组**，选择你将使用适用于 Windows SharePoint Services 适配器的 Windows 组。</span><span class="sxs-lookup"><span data-stu-id="0a25f-153">Under **Windows Group**, select the Windows group you will be using for the Windows SharePoint Services adapter.</span></span> <span data-ttu-id="0a25f-154">默认情况下，这是 SharePoint Enabled Hosts。</span><span class="sxs-lookup"><span data-stu-id="0a25f-154">By default, this is SharePoint Enabled Hosts.</span></span>  
  
4. <span data-ttu-id="0a25f-155">在中**Windows SharePoint Services 适配器网站**下拉列表框中，选择网站将在其中安装适配器组件。</span><span class="sxs-lookup"><span data-stu-id="0a25f-155">In the **Windows SharePoint Services Adapter Web Site** drop-down box, select the Web site where the adapter components will be installed.</span></span> <span data-ttu-id="0a25f-156">默认情况下，这是默认 Web 站点。</span><span class="sxs-lookup"><span data-stu-id="0a25f-156">By default, this is the Default Web Site.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="0a25f-157">不具有任何其他远程 SharePoint Server 计算机上的 Windows SharePoint Services 适配器 Web 站点安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装的组件是完全受支持的配置。</span><span class="sxs-lookup"><span data-stu-id="0a25f-157">The installation of the Windows SharePoint Services Adapter Web site on a remote SharePoint Server computer that does not have any other [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] components installed is a fully supported configuration.</span></span>  
  
5. <span data-ttu-id="0a25f-158">单击**应用配置**。</span><span class="sxs-lookup"><span data-stu-id="0a25f-158">Click **Apply Configuration**.</span></span>  
  
## <a name="considerations-for-a-multiserver-deployment"></a><span data-ttu-id="0a25f-159">多服务器部署的注意事项</span><span class="sxs-lookup"><span data-stu-id="0a25f-159">Considerations for a multiserver deployment</span></span>  
 <span data-ttu-id="0a25f-160">![](../core/media/adapters-wss-multiserver-screenshot01.gif "Adapters_WSS_Multiserver_Screenshot01")</span><span class="sxs-lookup"><span data-stu-id="0a25f-160">![](../core/media/adapters-wss-multiserver-screenshot01.gif "Adapters_WSS_Multiserver_Screenshot01")</span></span>  
  
### <a name="general-considerations"></a><span data-ttu-id="0a25f-161">一般注意事项</span><span class="sxs-lookup"><span data-stu-id="0a25f-161">General considerations</span></span>  
 <span data-ttu-id="0a25f-162">当您设置和部署多服务器环境中的 Windows SharePoint Services 适配器时，考虑以下方面：</span><span class="sxs-lookup"><span data-stu-id="0a25f-162">When you set up and deploy the Windows SharePoint Services adapter in a multiserver environment, consider the following:</span></span>  
  
- <span data-ttu-id="0a25f-163">BizTalk 服务帐户添加到每个服务器上的 SharePoint 启用主机 Windows 组。</span><span class="sxs-lookup"><span data-stu-id="0a25f-163">Add the BizTalk Service account to the SharePoint Enabled Hosts Windows group on each server.</span></span>  
  
- <span data-ttu-id="0a25f-164">将 SharePoint Enabled Hosts 组添加到 SharePoint 参与者角色使用 SharePoint 管理中心工具。</span><span class="sxs-lookup"><span data-stu-id="0a25f-164">Add the SharePoint Enabled Hosts group to the SharePoint Contributors role using the SharePoint Central Administration tool.</span></span>  
  
- <span data-ttu-id="0a25f-165">在[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]，SharePoint 适配器 Web 服务来运行的标识需要以下权限：</span><span class="sxs-lookup"><span data-stu-id="0a25f-165">On [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)], the identity under which the SharePoint Adapter Web Service runs needs the following permissions:</span></span>  
  
   <span data-ttu-id="0a25f-166">**读取**上的权限**Program Files\Microsoft BizTalk Server\<版本\>\Business Activity Services\BTSharePointV3AdapterWS**文件夹。</span><span class="sxs-lookup"><span data-stu-id="0a25f-166">**Read** permissions on the **Program Files\Microsoft BizTalk Server \<version\>\Business Activity Services\BTSharePointV3AdapterWS** folder.</span></span> <span data-ttu-id="0a25f-167">如果使用 Windows 的 64 位版本和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，需要在上设置权限**Program Files (x86) \Microsoft BizTalk Server\<版本\>\Business Activity Services\BTSharePointV3AdapterWS**</span><span class="sxs-lookup"><span data-stu-id="0a25f-167">If using a 64-bit version of Windows and [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], permissions need to be set on the **Program Files (x86)\Microsoft BizTalk Server \<version\>\Business Activity Services\BTSharePointV3AdapterWS**</span></span>  
  
   <span data-ttu-id="0a25f-168">**读取**以下注册表项权限：**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Shared Tools\Web Server\Extensions\12.0\Secure\ConfigDB**。</span><span class="sxs-lookup"><span data-stu-id="0a25f-168">**Read** permission on the following registry key: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Shared Tools\Web Server\Extensions\12.0\Secure\ConfigDB**.</span></span>  
  
   <span data-ttu-id="0a25f-169">包含 Sharepoint 数据库的 SQL 服务器上的登录权限。</span><span class="sxs-lookup"><span data-stu-id="0a25f-169">Logon permissions on the SQL Server that contains the Sharepoint databases.</span></span>  
  
   <span data-ttu-id="0a25f-170">成员**公共**并**WSS_Content_Application_Pools** SharePoint 配置数据库中的角色。</span><span class="sxs-lookup"><span data-stu-id="0a25f-170">A member of the **Public** and **WSS_Content_Application_Pools** roles within the SharePoint configuration database.</span></span>  
  
   <span data-ttu-id="0a25f-171">成员**公共**并**db 所有者**SharePoint 内容数据库中的角色。</span><span class="sxs-lookup"><span data-stu-id="0a25f-171">A member of the **Public** and **db owner** roles within the SharePoint content database.</span></span>  
  
- <span data-ttu-id="0a25f-172">在安装 Web 服务的网站必须扩展为 SharePoint Services 网站。</span><span class="sxs-lookup"><span data-stu-id="0a25f-172">The Web site that you install the Web service on must be extended as a SharePoint Services Web site.</span></span>  
  
- <span data-ttu-id="0a25f-173">你可以安装和配置 Windows SharePoint Services 适配器使用无提示安装。</span><span class="sxs-lookup"><span data-stu-id="0a25f-173">You can install and configure the Windows SharePoint Services adapter using a silent installation.</span></span> <span data-ttu-id="0a25f-174">有关详细信息，请参阅[附录 a:无提示安装](../install-and-config-guides/appendix-a-silent-installation.md)。</span><span class="sxs-lookup"><span data-stu-id="0a25f-174">For more information, see [Appendix A: Silent Installation](../install-and-config-guides/appendix-a-silent-installation.md).</span></span>  
  
### <a name="considerations-for-network-load-balancing-nlb"></a><span data-ttu-id="0a25f-175">考虑网络负载平衡 (NLB)</span><span class="sxs-lookup"><span data-stu-id="0a25f-175">Considerations for network load balancing (NLB)</span></span>  
 <span data-ttu-id="0a25f-176">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]针对 Windows SharePoint Services 适配器支持的 Windows SharePoint Services 服务器以及多个 BizTalk server 在同一个组中配置 NLB 群集。</span><span class="sxs-lookup"><span data-stu-id="0a25f-176">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adapter for Windows SharePoint Services supports NLB clustering of the Windows SharePoint Services servers along with multiple BizTalk servers that are configured in the same group.</span></span> <span data-ttu-id="0a25f-177">为此，Windows SharePoint Services 必须安装在 NLB 群集上按照 SharePoint 文档的建议。</span><span class="sxs-lookup"><span data-stu-id="0a25f-177">For this, Windows SharePoint Services must be installed on the NLB cluster as recommended by SharePoint documentation.</span></span>  
  
 <span data-ttu-id="0a25f-178">当你设置和部署 Windows SharePoint Services 适配器使用 NLB 的多服务器环境中时，考虑以下方面：</span><span class="sxs-lookup"><span data-stu-id="0a25f-178">When you set up and deploy the Windows SharePoint Services adapter in a multiserver environment with NLB, consider the following:</span></span>  
  
-   <span data-ttu-id="0a25f-179">通过选择指向现有 BizTalk 管理数据库的选项来配置 Windows SharePoint Services。</span><span class="sxs-lookup"><span data-stu-id="0a25f-179">Configure Windows SharePoint Services by selecting the option to point to an existing BizTalk Management database.</span></span> <span data-ttu-id="0a25f-180">指向第一台计算机上创建的 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="0a25f-180">Point to the BizTalk Management database created on the first computer.</span></span> <span data-ttu-id="0a25f-181">这向 Windows SharePoint Services 表明，你要将 Web 服务器环境。</span><span class="sxs-lookup"><span data-stu-id="0a25f-181">This indicates to Windows SharePoint Services that you intend to have a Web server environment.</span></span> <span data-ttu-id="0a25f-182">通过指向现有内容数据库中扩展 Web 站点。</span><span class="sxs-lookup"><span data-stu-id="0a25f-182">Extend the Web site by pointing to the existing content database.</span></span>  
  
-   <span data-ttu-id="0a25f-183">您必须扩展 Web 服务器环境中每个 Windows SharePoint Services 计算机上的相同 Web 站点 （例如，端口 80 上默认 Web 站点）。</span><span class="sxs-lookup"><span data-stu-id="0a25f-183">You must extend the same Web site (for example, the default Web site on port 80) on each Windows SharePoint Services computer in the Web server environment.</span></span>  
  
-   <span data-ttu-id="0a25f-184">必须安装并配置每台 NLB 主机上的相同方式 BTSharePointAdapterWS。</span><span class="sxs-lookup"><span data-stu-id="0a25f-184">The BTSharePointAdapterWS must be installed and configured the same way on each of the NLB hosts.</span></span> <span data-ttu-id="0a25f-185">必须配置下列 NLB 设置：</span><span class="sxs-lookup"><span data-stu-id="0a25f-185">You must configure the following NLB settings:</span></span>  
  
    -   <span data-ttu-id="0a25f-186">协议：TCP</span><span class="sxs-lookup"><span data-stu-id="0a25f-186">Protocol: TCP</span></span>  
  
    -   <span data-ttu-id="0a25f-187">端口：80 （HTTP 端口已在其中安装并配置 Windows SharePoint Services 适配器 Web services 的 IIS Web 站点）</span><span class="sxs-lookup"><span data-stu-id="0a25f-187">Ports: 80 (The HTTP Port of the IIS Web site where the Windows SharePoint Services adapter Web service has been installed and configured)</span></span>  
  
    -   <span data-ttu-id="0a25f-188">筛选模式：多个主机</span><span class="sxs-lookup"><span data-stu-id="0a25f-188">Filtering mode: Multiple host</span></span>  
  
    -   <span data-ttu-id="0a25f-189">关联：None</span><span class="sxs-lookup"><span data-stu-id="0a25f-189">Affinity: None</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0a25f-190">仅当该站点未配置为支持 HTTPS，可以使用此设置。</span><span class="sxs-lookup"><span data-stu-id="0a25f-190">This setting can be used only if the site is not configured for HTTPS.</span></span> <span data-ttu-id="0a25f-191">如果在使用 HTTPS 的站点上安装 BTSharePointAdapterWS Web 服务，则必须使用单客户端相关性。</span><span class="sxs-lookup"><span data-stu-id="0a25f-191">If the BTSharePointAdapterWS Web service is installed on a site with HTTPS, then you must use Single-client affinity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a25f-192">请参阅</span><span class="sxs-lookup"><span data-stu-id="0a25f-192">See Also</span></span>  
 <span data-ttu-id="0a25f-193">[Windows SharePoint Services 适配器](../core/windows-sharepoint-services-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="0a25f-193">[Windows SharePoint Services Adapter](../core/windows-sharepoint-services-adapter.md) </span></span>  
 [<span data-ttu-id="0a25f-194">单服务器部署</span><span class="sxs-lookup"><span data-stu-id="0a25f-194">Single-Server Deployment</span></span>](../core/single-server-deployment.md)