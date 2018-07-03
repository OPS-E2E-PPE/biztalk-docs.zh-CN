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
ms.openlocfilehash: e857aece2911aa9f1b3551f339524d2262cc0bf4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979758"
---
# <a name="multiserver-deployment"></a><span data-ttu-id="b26d3-102">多服务器部署</span><span class="sxs-lookup"><span data-stu-id="b26d3-102">Multiserver Deployment</span></span>
<span data-ttu-id="b26d3-103">本主题讨论在多服务器安装和部署注意事项[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]针对 Windows SharePoint Services 适配器。</span><span class="sxs-lookup"><span data-stu-id="b26d3-103">This topic discusses multiserver setup and deployment considerations for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adapter for Windows SharePoint Services.</span></span>  
  
## <a name="installing-the-windows-sharepoint-services-adapter-in-a-multiserver-deployment"></a><span data-ttu-id="b26d3-104">在多服务器部署中安装 Windows SharePoint Services 适配器</span><span class="sxs-lookup"><span data-stu-id="b26d3-104">Installing the Windows SharePoint Services adapter in a multiserver deployment</span></span>  
 <span data-ttu-id="b26d3-105">如果选择 Windows SharePoint Services 适配器 Web Services 组件，则会安装 Windows SharePoint Services 适配器处理通过 Windows SharePoint Services 传入和传出的文档所必需的软件。</span><span class="sxs-lookup"><span data-stu-id="b26d3-105">Selecting the Windows SharePoint Service Adapter Web Service component installs the necessary software for the Windows SharePoint Services adapter to process incoming and outgoing documents through Windows SharePoint Services.</span></span> <span data-ttu-id="b26d3-106">此 Web Services 必须安装在安装有 Windows SharePoint Services 的服务器上。</span><span class="sxs-lookup"><span data-stu-id="b26d3-106">This Web service must be installed on the server where Windows SharePoint Services is installed.</span></span>  
  
 <span data-ttu-id="b26d3-107">适配器 Web 服务可以处理多个 SharePoint 站点，无论这些站点位于同一 IIS 站点还是位于不同的 IIS 站点。</span><span class="sxs-lookup"><span data-stu-id="b26d3-107">The adapter Web service can handle multiple SharePoint sites regardless of whether they are on the same IIS site or on different IIS sites.</span></span>  
  
 <span data-ttu-id="b26d3-108">Windows SharePoint Services 适配器具有三个组件：</span><span class="sxs-lookup"><span data-stu-id="b26d3-108">The Windows SharePoint Services Adapter has three components:</span></span>  
  
- <span data-ttu-id="b26d3-109">运行时组件</span><span class="sxs-lookup"><span data-stu-id="b26d3-109">Runtime components</span></span>  
  
- <span data-ttu-id="b26d3-110">设计时组件</span><span class="sxs-lookup"><span data-stu-id="b26d3-110">Design time components</span></span>  
  
- <span data-ttu-id="b26d3-111">适配器 Web Services</span><span class="sxs-lookup"><span data-stu-id="b26d3-111">Adapter Web service</span></span>  
  
  <span data-ttu-id="b26d3-112">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 运行时功能将自动安装并配置适配器运行时。</span><span class="sxs-lookup"><span data-stu-id="b26d3-112">The adapter runtime is installed and configured automatically by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Runtime feature.</span></span> <span data-ttu-id="b26d3-113">该适配器的设计时组件将与其他 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 功能一起安装和配置。</span><span class="sxs-lookup"><span data-stu-id="b26d3-113">The adapter design time components are installed and configured with other [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] features.</span></span> <span data-ttu-id="b26d3-114">通过使用管理工具、开发人员工具、SDK 或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 运行时功能附带的工具来创建 Windows SharePoint Services 端口，可以与设计时组件进行交互。</span><span class="sxs-lookup"><span data-stu-id="b26d3-114">You interact with the design time components by creating Windows SharePoint Services ports through tools that are included in the Administration Tools, Developer Tools, and SDK or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Runtime features.</span></span> <span data-ttu-id="b26d3-115">你无法自定义运行时和设计时组件的任何配置选项。</span><span class="sxs-lookup"><span data-stu-id="b26d3-115">You cannot customize any configuration options for runtime and design time components.</span></span> <span data-ttu-id="b26d3-116">可以自定义仅 Windows SharePoint Services 适配器 Web 服务选项。</span><span class="sxs-lookup"><span data-stu-id="b26d3-116">You can customize only the Windows SharePoint Services adapter Web Service options.</span></span>  
  
  <span data-ttu-id="b26d3-117">只有 SharePoint Enabled Hosts 组的成员将有权调用该适配器 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="b26d3-117">Only members of the SharePoint Enabled Hosts group will have permissions to invoke the adapter Web service.</span></span> <span data-ttu-id="b26d3-118">有关 Windows SharePoint Services 适配器运行时所需的 Windows SharePoint Services 权限的详细信息，请参阅中的安全性部分[什么是 Windows SharePoint Services 适配器？](../core/what-is-the-windows-sharepoint-services-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="b26d3-118">For more information about the Windows SharePoint Services permissions needed by the Windows SharePoint Services adapter runtime, see the security section in [What Is the Windows SharePoint Services Adapter?](../core/what-is-the-windows-sharepoint-services-adapter.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b26d3-119">如果选择安装 BAS，系统将自动选择安装 Windows SharePoint Services 适配器 Web Services 组件。</span><span class="sxs-lookup"><span data-stu-id="b26d3-119">The Windows SharePoint Services adapter Web service component will be automatically selected if you choose to install BAS.</span></span>  
  
#### <a name="to-install-the-windows-sharepoint-services-adapter"></a><span data-ttu-id="b26d3-120">安装 Windows SharePoint Services 适配器</span><span class="sxs-lookup"><span data-stu-id="b26d3-120">To install the Windows SharePoint Services adapter</span></span>  
  
1. <span data-ttu-id="b26d3-121">安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b26d3-121">Install [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="b26d3-122">有关详细信息，请参阅[BizTalk Server 2013 和 2013 R2 安装概述](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)。</span><span class="sxs-lookup"><span data-stu-id="b26d3-122">For more information, see [Installation Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5).</span></span>  
  
2. <span data-ttu-id="b26d3-123">上**组件安装**屏幕上，在**可用组件**下**其他软件**，选择**Windows SharePoint Services 适配器Web 服务**。</span><span class="sxs-lookup"><span data-stu-id="b26d3-123">On the **Component Installation** screen, under **Available Components**, under **Additional Software**, select **Windows SharePoint Services Adapter Web service**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b26d3-124">必须在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 运行时的宿主计算机以及运行 Windows SharePoint Services 的计算机上运行安装和配置。</span><span class="sxs-lookup"><span data-stu-id="b26d3-124">You must run setup and configuration on the computer that hosts the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime and the computer running Windows SharePoint Services.</span></span>  
  
## <a name="configuring-the-windows-sharepoint-services-adapter-web-service-in-a-multiserver-deployment"></a><span data-ttu-id="b26d3-125">在多服务器部署中配置 Windows SharePoint Services 适配器 Web Services</span><span class="sxs-lookup"><span data-stu-id="b26d3-125">Configuring the Windows SharePoint Services adapter Web service in a multiserver deployment</span></span>  
 <span data-ttu-id="b26d3-126">可以使用 BizTalk Server 配置来配置 Windows SharePoint Services 适配器。</span><span class="sxs-lookup"><span data-stu-id="b26d3-126">You configure the Windows SharePoint Services adapter using the BizTalk Server Configuration.</span></span> <span data-ttu-id="b26d3-127">有关这些工具的详细信息，请参阅[BizTalk Server 2013 和 2013 R2 配置概述](http://msdn.microsoft.com/library/aa58c43f-8f0e-4a5c-89b9-db7b8a852a72)。</span><span class="sxs-lookup"><span data-stu-id="b26d3-127">For more information about these tools, see [Configuration Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/aa58c43f-8f0e-4a5c-89b9-db7b8a852a72).</span></span>  
  
### <a name="using-a-custom-configuration"></a><span data-ttu-id="b26d3-128">使用自定义配置</span><span class="sxs-lookup"><span data-stu-id="b26d3-128">Using a custom configuration</span></span>  
 <span data-ttu-id="b26d3-129">BizTalk Server 配置可以对本地计算机上已安装的功能的配置状态进行高级分析。</span><span class="sxs-lookup"><span data-stu-id="b26d3-129">The BizTalk Server Configuration provides a high-level analysis of the configuration state of the features you have installed on the local computer.</span></span> <span data-ttu-id="b26d3-130">使用该工具，可以配置功能、取消对功能的配置、配置安全设置，以及将配置导入和导出计算机。</span><span class="sxs-lookup"><span data-stu-id="b26d3-130">The tool allows you to configure and unconfigure features, configure security settings, and import and export configurations from other computers.</span></span>  
  
 <span data-ttu-id="b26d3-131">使用**Windows SharePoint Services**页后，可以在此计算机上配置 Windows SharePoint Services 适配器。</span><span class="sxs-lookup"><span data-stu-id="b26d3-131">Use the **Windows SharePoint Services** page to configure the Windows SharePoint Services adapter on this computer.</span></span> <span data-ttu-id="b26d3-132">下表列出了这些配置选项：</span><span class="sxs-lookup"><span data-stu-id="b26d3-132">The following table lists the configuration options.</span></span>  
  
|<span data-ttu-id="b26d3-133">使用此选项</span><span class="sxs-lookup"><span data-stu-id="b26d3-133">Use this</span></span>|<span data-ttu-id="b26d3-134">执行的操作</span><span class="sxs-lookup"><span data-stu-id="b26d3-134">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="b26d3-135">**此计算机上启用 Windows SharePoint Services 适配器**</span><span class="sxs-lookup"><span data-stu-id="b26d3-135">**Enable Windows SharePoint Services Adapter on this computer**</span></span>|<span data-ttu-id="b26d3-136">选择**启用此计算机上 Windows SharePoint Services 适配器**若要启用此计算机上的适配器。</span><span class="sxs-lookup"><span data-stu-id="b26d3-136">Select **Enable Windows SharePoint Services Adapter on this computer** to enable the adapter on this computer.</span></span>|  
|<span data-ttu-id="b26d3-137">**Windows 组**</span><span class="sxs-lookup"><span data-stu-id="b26d3-137">**Windows group**</span></span>|<span data-ttu-id="b26d3-138">**Windows 组**列表提供了 BizTalk SharePoint 适配器启用主机 Windows 组的可编辑视图。</span><span class="sxs-lookup"><span data-stu-id="b26d3-138">The **Windows group** list provides a view that you can edit of the BizTalk SharePoint Adapter Enabled Hosts Windows group.</span></span>|  
|<span data-ttu-id="b26d3-139">**Windows SharePoint Services 适配器网站**</span><span class="sxs-lookup"><span data-stu-id="b26d3-139">**Windows SharePoint Services Adapter Web site**</span></span>|<span data-ttu-id="b26d3-140">选择将用作 Windows SharePoint Services 适配器 Web Services 宿主的网站。</span><span class="sxs-lookup"><span data-stu-id="b26d3-140">Select the Web site that will host the Windows SharePoint Services adapter Web service.</span></span>|  
  
 <span data-ttu-id="b26d3-141">当使用自定义配置对 Windows SharePoint Services 适配器进行配置时，将出现以下结果：</span><span class="sxs-lookup"><span data-stu-id="b26d3-141">When you configure the Windows SharePoint Services adapter using custom configuration, the following happens:</span></span>  
  
-   <span data-ttu-id="b26d3-142">默认情况下，除非指定了其他 Windows 组，否则将创建 SharePoint Enabled Hosts 这一 Windows 组。</span><span class="sxs-lookup"><span data-stu-id="b26d3-142">The SharePoint Enabled Hosts Windows group is created by default unless you specify another Windows group</span></span>  
  
-   <span data-ttu-id="b26d3-143">除非指定其他网站，否则将使用默认网站作为 Windows SharePoint Services 适配器的宿主。</span><span class="sxs-lookup"><span data-stu-id="b26d3-143">The Default Web Site is used to host the Windows SharePoint Services adapter unless you specify another Web site</span></span>  
  
-   <span data-ttu-id="b26d3-144">创建 BTSSharePointAdapterWSAppPool 应用程序池，并将其配置为使用运行 Windows SharePoint Services 应用程序池所用的同一帐户来运行。</span><span class="sxs-lookup"><span data-stu-id="b26d3-144">The BTSSharePointAdapterWSAppPool application pool is created and configured to run under the account that is also used to run the Windows SharePoint Services application pool</span></span>  
  
-   <span data-ttu-id="b26d3-145">创建 BTSharePointAdapterWS 虚拟应用程序，并将其配置为在 BTSSharePointAdapterWSAppPool 应用程序池中运行</span><span class="sxs-lookup"><span data-stu-id="b26d3-145">The BTSharePointAdapterWS virtual application is created and configured to run in the BTSSharePointAdapterWSAppPool application pool</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b26d3-146">如果此虚拟目录已存在，则配置过程将不会更新元数据库中的属性。</span><span class="sxs-lookup"><span data-stu-id="b26d3-146">If this virtual directory already exists, configuration will not update the properties in the metabase.</span></span> <span data-ttu-id="b26d3-147">必须删除该虚拟目录，然后重新进行配置。</span><span class="sxs-lookup"><span data-stu-id="b26d3-147">You must delete the virtual directory and run configuration again.</span></span>  
  
- <span data-ttu-id="b26d3-148">BTSharePointAdapterWS 虚拟应用程序包含 Web Services</span><span class="sxs-lookup"><span data-stu-id="b26d3-148">The BTSharePointAdapterWS virtual application contains the Web service</span></span>  
  
  <span data-ttu-id="b26d3-149">有关 BizTalk Server 配置的详细信息，请参阅[导入和导出 BizTalk Server 配置](../install-and-config-guides/import-and-export-biztalk-server-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="b26d3-149">For more information about the BizTalk Server Configuration, see [Import and Export BizTalk Server Configuration](../install-and-config-guides/import-and-export-biztalk-server-configuration.md).</span></span>  
  
##### <a name="to-configure-the-windows-sharepoint-services-adapter-by-using-custom-configuration"></a><span data-ttu-id="b26d3-150">使用自定义配置对 Windows SharePoint Services 适配器进行配置</span><span class="sxs-lookup"><span data-stu-id="b26d3-150">To configure the Windows SharePoint Services adapter by using custom configuration</span></span>  
  
1. <span data-ttu-id="b26d3-151">在中**BizTalk Server 配置**，选择**SharePoint 适配器**节点。</span><span class="sxs-lookup"><span data-stu-id="b26d3-151">In the **BizTalk Server Configuration**, select the **SharePoint adapter** node.</span></span>  
  
2. <span data-ttu-id="b26d3-152">选择**启用此计算机上 Windows SharePoint Services 适配器**。</span><span class="sxs-lookup"><span data-stu-id="b26d3-152">Select **Enable Windows SharePoint Services Adapter on this computer**.</span></span>  
  
3. <span data-ttu-id="b26d3-153">下**Windows 组**，选择你将使用适用于 Windows SharePoint Services 适配器的 Windows 组。</span><span class="sxs-lookup"><span data-stu-id="b26d3-153">Under **Windows Group**, select the Windows group you will be using for the Windows SharePoint Services adapter.</span></span> <span data-ttu-id="b26d3-154">默认情况下，将选择 SharePoint Enabled Hosts。</span><span class="sxs-lookup"><span data-stu-id="b26d3-154">By default, this is SharePoint Enabled Hosts.</span></span>  
  
4. <span data-ttu-id="b26d3-155">在中**Windows SharePoint Services 适配器网站**下拉列表框中，选择网站将在其中安装适配器组件。</span><span class="sxs-lookup"><span data-stu-id="b26d3-155">In the **Windows SharePoint Services Adapter Web Site** drop-down box, select the Web site where the adapter components will be installed.</span></span> <span data-ttu-id="b26d3-156">默认情况下，将选择默认网站。</span><span class="sxs-lookup"><span data-stu-id="b26d3-156">By default, this is the Default Web Site.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="b26d3-157">在未安装任何其他 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 组件的远程 SharePoint Server 计算机上安装 Windows SharePoint Services 适配器网站为完全支持配置。</span><span class="sxs-lookup"><span data-stu-id="b26d3-157">The installation of the Windows SharePoint Services Adapter Web site on a remote SharePoint Server computer that does not have any other [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] components installed is a fully supported configuration.</span></span>  
  
5. <span data-ttu-id="b26d3-158">单击“应用配置”。</span><span class="sxs-lookup"><span data-stu-id="b26d3-158">Click **Apply Configuration**.</span></span>  
  
## <a name="considerations-for-a-multiserver-deployment"></a><span data-ttu-id="b26d3-159">多服务器部署的注意事项</span><span class="sxs-lookup"><span data-stu-id="b26d3-159">Considerations for a multiserver deployment</span></span>  
 <span data-ttu-id="b26d3-160">![](../core/media/adapters-wss-multiserver-screenshot01.gif "Adapters_WSS_Multiserver_Screenshot01")</span><span class="sxs-lookup"><span data-stu-id="b26d3-160">![](../core/media/adapters-wss-multiserver-screenshot01.gif "Adapters_WSS_Multiserver_Screenshot01")</span></span>  
  
### <a name="general-considerations"></a><span data-ttu-id="b26d3-161">常规注意事项</span><span class="sxs-lookup"><span data-stu-id="b26d3-161">General considerations</span></span>  
 <span data-ttu-id="b26d3-162">在多服务器环境中安装和部署 Windows SharePoint Services 适配器时，应注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="b26d3-162">When you set up and deploy the Windows SharePoint Services adapter in a multiserver environment, consider the following:</span></span>  
  
- <span data-ttu-id="b26d3-163">将 BizTalk 服务帐户添加到每个服务器上的 SharePoint Enabled Hosts 这一 Windows 组中。</span><span class="sxs-lookup"><span data-stu-id="b26d3-163">Add the BizTalk Service account to the SharePoint Enabled Hosts Windows group on each server.</span></span>  
  
- <span data-ttu-id="b26d3-164">使用 SharePoint 管理中心工具，将 SharePoint Enabled Hosts 组添加到 SharePoint 参与者角色中。</span><span class="sxs-lookup"><span data-stu-id="b26d3-164">Add the SharePoint Enabled Hosts group to the SharePoint Contributors role using the SharePoint Central Administration tool.</span></span>  
  
- <span data-ttu-id="b26d3-165">在 [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] 上，运行 SharePoint 适配器 Web Service 的标识需要具有以下权限：</span><span class="sxs-lookup"><span data-stu-id="b26d3-165">On [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)], the identity under which the SharePoint Adapter Web Service runs needs the following permissions:</span></span>  
  
   <span data-ttu-id="b26d3-166">**读取**上的权限**Program Files\Microsoft BizTalk Server\<版本\>\Business Activity Services\BTSharePointV3AdapterWS**文件夹。</span><span class="sxs-lookup"><span data-stu-id="b26d3-166">**Read** permissions on the **Program Files\Microsoft BizTalk Server \<version\>\Business Activity Services\BTSharePointV3AdapterWS** folder.</span></span> <span data-ttu-id="b26d3-167">如果使用 Windows 的 64 位版本和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，需要在上设置权限**Program Files (x86) \Microsoft BizTalk Server\<版本\>\Business Activity Services\BTSharePointV3AdapterWS**</span><span class="sxs-lookup"><span data-stu-id="b26d3-167">If using a 64-bit version of Windows and [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], permissions need to be set on the **Program Files (x86)\Microsoft BizTalk Server \<version\>\Business Activity Services\BTSharePointV3AdapterWS**</span></span>  
  
   <span data-ttu-id="b26d3-168">**读取**以下注册表项权限： **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Shared Tools\Web Server\Extensions\12.0\Secure\ConfigDB**。</span><span class="sxs-lookup"><span data-stu-id="b26d3-168">**Read** permission on the following registry key: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Shared Tools\Web Server\Extensions\12.0\Secure\ConfigDB**.</span></span>  
  
   <span data-ttu-id="b26d3-169">包含 Sharepoint 数据库的 SQL Server 的登录权限。</span><span class="sxs-lookup"><span data-stu-id="b26d3-169">Logon permissions on the SQL Server that contains the Sharepoint databases.</span></span>  
  
   <span data-ttu-id="b26d3-170">成员**公共**并**WSS_Content_Application_Pools** SharePoint 配置数据库中的角色。</span><span class="sxs-lookup"><span data-stu-id="b26d3-170">A member of the **Public** and **WSS_Content_Application_Pools** roles within the SharePoint configuration database.</span></span>  
  
   <span data-ttu-id="b26d3-171">成员**公共**并**db 所有者**SharePoint 内容数据库中的角色。</span><span class="sxs-lookup"><span data-stu-id="b26d3-171">A member of the **Public** and **db owner** roles within the SharePoint content database.</span></span>  
  
- <span data-ttu-id="b26d3-172">必须将 Web Services 安装所在的网站扩展为 SharePoint Services 网站。</span><span class="sxs-lookup"><span data-stu-id="b26d3-172">The Web site that you install the Web service on must be extended as a SharePoint Services Web site.</span></span>  
  
- <span data-ttu-id="b26d3-173">你可以使用无提示安装方式来安装和配置 Windows SharePoint Services 适配器。</span><span class="sxs-lookup"><span data-stu-id="b26d3-173">You can install and configure the Windows SharePoint Services adapter using a silent installation.</span></span> <span data-ttu-id="b26d3-174">有关详细信息，请参阅[附录 a： 无提示安装](../install-and-config-guides/appendix-a-silent-installation.md)。</span><span class="sxs-lookup"><span data-stu-id="b26d3-174">For more information, see [Appendix A: Silent Installation](../install-and-config-guides/appendix-a-silent-installation.md).</span></span>  
  
### <a name="considerations-for-network-load-balancing-nlb"></a><span data-ttu-id="b26d3-175">网络负载平衡 (NLB) 的注意事项</span><span class="sxs-lookup"><span data-stu-id="b26d3-175">Considerations for network load balancing (NLB)</span></span>  
 <span data-ttu-id="b26d3-176">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]针对 Windows SharePoint Services 适配器支持的 Windows SharePoint Services 服务器以及多个 BizTalk server 在同一个组中配置 NLB 群集。</span><span class="sxs-lookup"><span data-stu-id="b26d3-176">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adapter for Windows SharePoint Services supports NLB clustering of the Windows SharePoint Services servers along with multiple BizTalk servers that are configured in the same group.</span></span> <span data-ttu-id="b26d3-177">因此，必须按照 SharePoint 文档的建议将 Windows SharePoint Services 安装在 NLB 群集上。</span><span class="sxs-lookup"><span data-stu-id="b26d3-177">For this, Windows SharePoint Services must be installed on the NLB cluster as recommended by SharePoint documentation.</span></span>  
  
 <span data-ttu-id="b26d3-178">在具有 NLB 的多服务器环境中安装和部署 Windows SharePoint Services 适配器时，应注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="b26d3-178">When you set up and deploy the Windows SharePoint Services adapter in a multiserver environment with NLB, consider the following:</span></span>  
  
-   <span data-ttu-id="b26d3-179">通过选择相应的选项，将 Windows SharePoint Services 配置为指向现有 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="b26d3-179">Configure Windows SharePoint Services by selecting the option to point to an existing BizTalk Management database.</span></span> <span data-ttu-id="b26d3-180">指向在第一台计算机上创建的 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="b26d3-180">Point to the BizTalk Management database created on the first computer.</span></span> <span data-ttu-id="b26d3-181">这将向 Windows SharePoint Services 表明你要设置一个 Web 服务器环境。</span><span class="sxs-lookup"><span data-stu-id="b26d3-181">This indicates to Windows SharePoint Services that you intend to have a Web server environment.</span></span> <span data-ttu-id="b26d3-182">通过指向现有内容数据库来扩展网站。</span><span class="sxs-lookup"><span data-stu-id="b26d3-182">Extend the Web site by pointing to the existing content database.</span></span>  
  
-   <span data-ttu-id="b26d3-183">你必须在 Web 服务器环境中的每台 Windows SharePoint Services 计算机上扩展同一网站（例如，端口 80 上的默认网站）。</span><span class="sxs-lookup"><span data-stu-id="b26d3-183">You must extend the same Web site (for example, the default Web site on port 80) on each Windows SharePoint Services computer in the Web server environment.</span></span>  
  
-   <span data-ttu-id="b26d3-184">必须在每台 NLB 主机上以相同方式安装和配置 BTSharePointAdapterWS。</span><span class="sxs-lookup"><span data-stu-id="b26d3-184">The BTSharePointAdapterWS must be installed and configured the same way on each of the NLB hosts.</span></span> <span data-ttu-id="b26d3-185">必须配置以下 NLB 设置：</span><span class="sxs-lookup"><span data-stu-id="b26d3-185">You must configure the following NLB settings:</span></span>  
  
    -   <span data-ttu-id="b26d3-186">协议：TCP</span><span class="sxs-lookup"><span data-stu-id="b26d3-186">Protocol: TCP</span></span>  
  
    -   <span data-ttu-id="b26d3-187">端口： 80 （HTTP 端口已在其中安装并配置 Windows SharePoint Services 适配器 Web services 的 IIS Web 站点）</span><span class="sxs-lookup"><span data-stu-id="b26d3-187">Ports: 80 (The HTTP Port of the IIS Web site where the Windows SharePoint Services adapter Web service has been installed and configured)</span></span>  
  
    -   <span data-ttu-id="b26d3-188">筛选模式： 多个主机</span><span class="sxs-lookup"><span data-stu-id="b26d3-188">Filtering mode: Multiple host</span></span>  
  
    -   <span data-ttu-id="b26d3-189">关联：无</span><span class="sxs-lookup"><span data-stu-id="b26d3-189">Affinity: None</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b26d3-190">只有在该站点未配置 HTTPS 时，才能使用此设置。</span><span class="sxs-lookup"><span data-stu-id="b26d3-190">This setting can be used only if the site is not configured for HTTPS.</span></span> <span data-ttu-id="b26d3-191">如果在使用 HTTPS 的站点上安装 BTSharePointAdapterWS Web Services，则必须使用单客户端相似性。</span><span class="sxs-lookup"><span data-stu-id="b26d3-191">If the BTSharePointAdapterWS Web service is installed on a site with HTTPS, then you must use Single-client affinity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b26d3-192">请参阅</span><span class="sxs-lookup"><span data-stu-id="b26d3-192">See Also</span></span>  
 <span data-ttu-id="b26d3-193">[Windows SharePoint Services 适配器](../core/windows-sharepoint-services-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="b26d3-193">[Windows SharePoint Services Adapter](../core/windows-sharepoint-services-adapter.md) </span></span>  
 [<span data-ttu-id="b26d3-194">单服务器部署</span><span class="sxs-lookup"><span data-stu-id="b26d3-194">Single-Server Deployment</span></span>](../core/single-server-deployment.md)