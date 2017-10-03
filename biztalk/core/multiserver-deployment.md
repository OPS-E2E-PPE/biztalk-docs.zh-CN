---
title: "多服务器部署 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring [Windows SharePoint Services adapters], multi-server deployment
- planning, Windows SharePoint Services adapters
- Windows SharePoint Services adapters, deploying
- Windows SharePoint Services adapters, multi-server deployment
- deploying, Windows SharePoint Services adapters
- Windows SharePoint Services adapters, installing
ms.assetid: 0c6e2aa0-e873-461b-8101-9b0988019597
caps.latest.revision: "28"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d9770a2d9e4977ec23c8ff4013d5415c75087d3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="multiserver-deployment"></a><span data-ttu-id="dc27a-102">多服务器部署</span><span class="sxs-lookup"><span data-stu-id="dc27a-102">Multiserver Deployment</span></span>
<span data-ttu-id="dc27a-103">本主题讨论多服务器安装和部署注意事项[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]适用于 Windows SharePoint Services 的适配器。</span><span class="sxs-lookup"><span data-stu-id="dc27a-103">This topic discusses multiserver setup and deployment considerations for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adapter for Windows SharePoint Services.</span></span>  
  
## <a name="installing-the-windows-sharepoint-services-adapter-in-a-multiserver-deployment"></a><span data-ttu-id="dc27a-104">在多服务器部署中安装 Windows SharePoint Services 适配器</span><span class="sxs-lookup"><span data-stu-id="dc27a-104">Installing the Windows SharePoint Services adapter in a multiserver deployment</span></span>  
 <span data-ttu-id="dc27a-105">如果选择 Windows SharePoint Services 适配器 Web Services 组件，则会安装 Windows SharePoint Services 适配器处理通过 Windows SharePoint Services 传入和传出的文档所必需的软件。</span><span class="sxs-lookup"><span data-stu-id="dc27a-105">Selecting the Windows SharePoint Service Adapter Web Service component installs the necessary software for the Windows SharePoint Services adapter to process incoming and outgoing documents through Windows SharePoint Services.</span></span> <span data-ttu-id="dc27a-106">此 Web Services 必须安装在安装有 Windows SharePoint Services 的服务器上。</span><span class="sxs-lookup"><span data-stu-id="dc27a-106">This Web service must be installed on the server where Windows SharePoint Services is installed.</span></span>  
  
 <span data-ttu-id="dc27a-107">适配器 Web 服务可以处理多个 SharePoint 站点，无论这些站点位于同一 IIS 站点还是位于不同的 IIS 站点。</span><span class="sxs-lookup"><span data-stu-id="dc27a-107">The adapter Web service can handle multiple SharePoint sites regardless of whether they are on the same IIS site or on different IIS sites.</span></span>  
  
 <span data-ttu-id="dc27a-108">Windows SharePoint Services 适配器具有三个组件：</span><span class="sxs-lookup"><span data-stu-id="dc27a-108">The Windows SharePoint Services Adapter has three components:</span></span>  
  
-   <span data-ttu-id="dc27a-109">运行时组件</span><span class="sxs-lookup"><span data-stu-id="dc27a-109">Runtime components</span></span>  
  
-   <span data-ttu-id="dc27a-110">设计时组件</span><span class="sxs-lookup"><span data-stu-id="dc27a-110">Design time components</span></span>  
  
-   <span data-ttu-id="dc27a-111">适配器 Web Services</span><span class="sxs-lookup"><span data-stu-id="dc27a-111">Adapter Web service</span></span>  
  
 <span data-ttu-id="dc27a-112">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 运行时功能将自动安装并配置适配器运行时。</span><span class="sxs-lookup"><span data-stu-id="dc27a-112">The adapter runtime is installed and configured automatically by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Runtime feature.</span></span> <span data-ttu-id="dc27a-113">该适配器的设计时组件将与其他 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 功能一起安装和配置。</span><span class="sxs-lookup"><span data-stu-id="dc27a-113">The adapter design time components are installed and configured with other [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] features.</span></span> <span data-ttu-id="dc27a-114">通过使用管理工具、开发人员工具、SDK 或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 运行时功能附带的工具来创建 Windows SharePoint Services 端口，可以与设计时组件进行交互。</span><span class="sxs-lookup"><span data-stu-id="dc27a-114">You interact with the design time components by creating Windows SharePoint Services ports through tools that are included in the Administration Tools, Developer Tools, and SDK or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Runtime features.</span></span> <span data-ttu-id="dc27a-115">你无法自定义运行时和设计时组件的任何配置选项。</span><span class="sxs-lookup"><span data-stu-id="dc27a-115">You cannot customize any configuration options for runtime and design time components.</span></span> <span data-ttu-id="dc27a-116">你可以自定义仅 Windows SharePoint Services 适配器 Web 服务选项。</span><span class="sxs-lookup"><span data-stu-id="dc27a-116">You can customize only the Windows SharePoint Services adapter Web Service options.</span></span>  
  
 <span data-ttu-id="dc27a-117">只有 SharePoint 启用主机组的成员将具有权限来调用 Web 服务的适配器。</span><span class="sxs-lookup"><span data-stu-id="dc27a-117">Only members of the SharePoint Enabled Hosts group will have permissions to invoke the adapter Web service.</span></span> <span data-ttu-id="dc27a-118">有关由 Windows SharePoint Services 适配器运行所需的 Windows SharePoint Services 权限的详细信息，请参阅中的安全部分[什么是 Windows SharePoint Services Adapter？](../core/what-is-the-windows-sharepoint-services-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="dc27a-118">For more information about the Windows SharePoint Services permissions needed by the Windows SharePoint Services adapter runtime, see the security section in [What Is the Windows SharePoint Services Adapter?](../core/what-is-the-windows-sharepoint-services-adapter.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dc27a-119">如果选择安装 BAS，系统将自动选择安装 Windows SharePoint Services 适配器 Web Services 组件。</span><span class="sxs-lookup"><span data-stu-id="dc27a-119">The Windows SharePoint Services adapter Web service component will be automatically selected if you choose to install BAS.</span></span>  
  
#### <a name="to-install-the-windows-sharepoint-services-adapter"></a><span data-ttu-id="dc27a-120">安装 Windows SharePoint Services 适配器</span><span class="sxs-lookup"><span data-stu-id="dc27a-120">To install the Windows SharePoint Services adapter</span></span>  
  
1.  <span data-ttu-id="dc27a-121">安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="dc27a-121">Install [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="dc27a-122">有关详细信息，请参阅[BizTalk Server 2013 和 2013 R2 的安装概述](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)。</span><span class="sxs-lookup"><span data-stu-id="dc27a-122">For more information, see [Installation Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5).</span></span>  
  
2.  <span data-ttu-id="dc27a-123">上**组件安装**屏幕上，在**可用组件**下**其他软件**，选择**Windows SharePoint Services AdapterWeb 服务**。</span><span class="sxs-lookup"><span data-stu-id="dc27a-123">On the **Component Installation** screen, under **Available Components**, under **Additional Software**, select **Windows SharePoint Services Adapter Web service**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dc27a-124">必须在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 运行时的宿主计算机以及运行 Windows SharePoint Services 的计算机上运行安装和配置。</span><span class="sxs-lookup"><span data-stu-id="dc27a-124">You must run setup and configuration on the computer that hosts the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime and the computer running Windows SharePoint Services.</span></span>  
  
## <a name="configuring-the-windows-sharepoint-services-adapter-web-service-in-a-multiserver-deployment"></a><span data-ttu-id="dc27a-125">在多服务器部署中配置 Windows SharePoint Services 适配器 Web Services</span><span class="sxs-lookup"><span data-stu-id="dc27a-125">Configuring the Windows SharePoint Services adapter Web service in a multiserver deployment</span></span>  
 <span data-ttu-id="dc27a-126">可以使用 BizTalk Server 配置来配置 Windows SharePoint Services 适配器。</span><span class="sxs-lookup"><span data-stu-id="dc27a-126">You configure the Windows SharePoint Services adapter using the BizTalk Server Configuration.</span></span> <span data-ttu-id="dc27a-127">有关这些工具的详细信息，请参阅[BizTalk Server 2013 和 2013 R2 配置概述](http://msdn.microsoft.com/library/aa58c43f-8f0e-4a5c-89b9-db7b8a852a72)。</span><span class="sxs-lookup"><span data-stu-id="dc27a-127">For more information about these tools, see [Configuration Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/aa58c43f-8f0e-4a5c-89b9-db7b8a852a72).</span></span>  
  
### <a name="using-a-custom-configuration"></a><span data-ttu-id="dc27a-128">使用自定义配置</span><span class="sxs-lookup"><span data-stu-id="dc27a-128">Using a custom configuration</span></span>  
 <span data-ttu-id="dc27a-129">BizTalk Server 配置可以对本地计算机上已安装的功能的配置状态进行高级分析。</span><span class="sxs-lookup"><span data-stu-id="dc27a-129">The BizTalk Server Configuration provides a high-level analysis of the configuration state of the features you have installed on the local computer.</span></span> <span data-ttu-id="dc27a-130">使用该工具，可以配置功能、取消对功能的配置、配置安全设置，以及将配置导入和导出计算机。</span><span class="sxs-lookup"><span data-stu-id="dc27a-130">The tool allows you to configure and unconfigure features, configure security settings, and import and export configurations from other computers.</span></span>  
  
 <span data-ttu-id="dc27a-131">使用**Windows SharePoint Services**页后，可以在此计算机上配置 Windows SharePoint Services 适配器。</span><span class="sxs-lookup"><span data-stu-id="dc27a-131">Use the **Windows SharePoint Services** page to configure the Windows SharePoint Services adapter on this computer.</span></span> <span data-ttu-id="dc27a-132">下表列出了这些配置选项：</span><span class="sxs-lookup"><span data-stu-id="dc27a-132">The following table lists the configuration options.</span></span>  
  
|<span data-ttu-id="dc27a-133">使用此选项</span><span class="sxs-lookup"><span data-stu-id="dc27a-133">Use this</span></span>|<span data-ttu-id="dc27a-134">执行的操作</span><span class="sxs-lookup"><span data-stu-id="dc27a-134">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="dc27a-135">**在此计算机上启用 Windows SharePoint Services Adapter**</span><span class="sxs-lookup"><span data-stu-id="dc27a-135">**Enable Windows SharePoint Services Adapter on this computer**</span></span>|<span data-ttu-id="dc27a-136">选择**启用这台计算机上 Windows SharePoint Services Adapter**若要启用此计算机上的适配器。</span><span class="sxs-lookup"><span data-stu-id="dc27a-136">Select **Enable Windows SharePoint Services Adapter on this computer** to enable the adapter on this computer.</span></span>|  
|<span data-ttu-id="dc27a-137">**Windows 组**</span><span class="sxs-lookup"><span data-stu-id="dc27a-137">**Windows group**</span></span>|<span data-ttu-id="dc27a-138">**Windows 组**列表提供了你可以编辑 BizTalk SharePoint 适配器启用主机 Windows 组的视图。</span><span class="sxs-lookup"><span data-stu-id="dc27a-138">The **Windows group** list provides a view that you can edit of the BizTalk SharePoint Adapter Enabled Hosts Windows group.</span></span>|  
|<span data-ttu-id="dc27a-139">**Windows SharePoint Services 适配器网站**</span><span class="sxs-lookup"><span data-stu-id="dc27a-139">**Windows SharePoint Services Adapter Web site**</span></span>|<span data-ttu-id="dc27a-140">选择将用作 Windows SharePoint Services 适配器 Web Services 宿主的网站。</span><span class="sxs-lookup"><span data-stu-id="dc27a-140">Select the Web site that will host the Windows SharePoint Services adapter Web service.</span></span>|  
  
 <span data-ttu-id="dc27a-141">当使用自定义配置对 Windows SharePoint Services 适配器进行配置时，将出现以下结果：</span><span class="sxs-lookup"><span data-stu-id="dc27a-141">When you configure the Windows SharePoint Services adapter using custom configuration, the following happens:</span></span>  
  
-   <span data-ttu-id="dc27a-142">默认情况下，除非指定了其他 Windows 组，否则将创建 SharePoint Enabled Hosts 这一 Windows 组。</span><span class="sxs-lookup"><span data-stu-id="dc27a-142">The SharePoint Enabled Hosts Windows group is created by default unless you specify another Windows group</span></span>  
  
-   <span data-ttu-id="dc27a-143">除非指定其他网站，否则将使用默认网站作为 Windows SharePoint Services 适配器的宿主。</span><span class="sxs-lookup"><span data-stu-id="dc27a-143">The Default Web Site is used to host the Windows SharePoint Services adapter unless you specify another Web site</span></span>  
  
-   <span data-ttu-id="dc27a-144">创建 BTSSharePointAdapterWSAppPool 应用程序池，并将其配置为使用运行 Windows SharePoint Services 应用程序池所用的同一帐户来运行。</span><span class="sxs-lookup"><span data-stu-id="dc27a-144">The BTSSharePointAdapterWSAppPool application pool is created and configured to run under the account that is also used to run the Windows SharePoint Services application pool</span></span>  
  
-   <span data-ttu-id="dc27a-145">创建 BTSharePointAdapterWS 虚拟应用程序，并将其配置为在 BTSSharePointAdapterWSAppPool 应用程序池中运行</span><span class="sxs-lookup"><span data-stu-id="dc27a-145">The BTSharePointAdapterWS virtual application is created and configured to run in the BTSSharePointAdapterWSAppPool application pool</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dc27a-146">如果此虚拟目录已存在，则配置过程将不会更新元数据库中的属性。</span><span class="sxs-lookup"><span data-stu-id="dc27a-146">If this virtual directory already exists, configuration will not update the properties in the metabase.</span></span> <span data-ttu-id="dc27a-147">必须删除该虚拟目录，然后重新进行配置。</span><span class="sxs-lookup"><span data-stu-id="dc27a-147">You must delete the virtual directory and run configuration again.</span></span>  
  
-   <span data-ttu-id="dc27a-148">BTSharePointAdapterWS 虚拟应用程序包含 Web Services</span><span class="sxs-lookup"><span data-stu-id="dc27a-148">The BTSharePointAdapterWS virtual application contains the Web service</span></span>  
  
 <span data-ttu-id="dc27a-149">有关 BizTalk 服务器配置的详细信息，请参阅[导入和导出 BizTalk Server 配置](../install-and-config-guides/import-and-export-biztalk-server-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="dc27a-149">For more information about the BizTalk Server Configuration, see [Import and Export BizTalk Server Configuration](../install-and-config-guides/import-and-export-biztalk-server-configuration.md).</span></span>  
  
##### <a name="to-configure-the-windows-sharepoint-services-adapter-by-using-custom-configuration"></a><span data-ttu-id="dc27a-150">使用自定义配置对 Windows SharePoint Services 适配器进行配置</span><span class="sxs-lookup"><span data-stu-id="dc27a-150">To configure the Windows SharePoint Services adapter by using custom configuration</span></span>  
  
1.  <span data-ttu-id="dc27a-151">在**BizTalk Server 配置**，选择**SharePoint 适配器**节点。</span><span class="sxs-lookup"><span data-stu-id="dc27a-151">In the **BizTalk Server Configuration**, select the **SharePoint adapter** node.</span></span>  
  
2.  <span data-ttu-id="dc27a-152">选择**启用这台计算机上 Windows SharePoint Services Adapter**。</span><span class="sxs-lookup"><span data-stu-id="dc27a-152">Select **Enable Windows SharePoint Services Adapter on this computer**.</span></span>  
  
3.  <span data-ttu-id="dc27a-153">下**Windows 组**，选择将用于 Windows SharePoint Services 适配器的 Windows 组。</span><span class="sxs-lookup"><span data-stu-id="dc27a-153">Under **Windows Group**, select the Windows group you will be using for the Windows SharePoint Services adapter.</span></span> <span data-ttu-id="dc27a-154">默认情况下，将选择 SharePoint Enabled Hosts。</span><span class="sxs-lookup"><span data-stu-id="dc27a-154">By default, this is SharePoint Enabled Hosts.</span></span>  
  
4.  <span data-ttu-id="dc27a-155">在**Windows SharePoint Services 适配器网站**下拉列表中，选择网站将在其中安装适配器组件。</span><span class="sxs-lookup"><span data-stu-id="dc27a-155">In the **Windows SharePoint Services Adapter Web Site** drop-down box, select the Web site where the adapter components will be installed.</span></span> <span data-ttu-id="dc27a-156">默认情况下，将选择默认网站。</span><span class="sxs-lookup"><span data-stu-id="dc27a-156">By default, this is the Default Web Site.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="dc27a-157">在未安装任何其他 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 组件的远程 SharePoint Server 计算机上安装 Windows SharePoint Services 适配器网站为完全支持配置。</span><span class="sxs-lookup"><span data-stu-id="dc27a-157">The installation of the Windows SharePoint Services Adapter Web site on a remote SharePoint Server computer that does not have any other [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] components installed is a fully supported configuration.</span></span>  
  
5.  <span data-ttu-id="dc27a-158">单击“应用配置”。</span><span class="sxs-lookup"><span data-stu-id="dc27a-158">Click **Apply Configuration**.</span></span>  
  
## <a name="considerations-for-a-multiserver-deployment"></a><span data-ttu-id="dc27a-159">多服务器部署的注意事项</span><span class="sxs-lookup"><span data-stu-id="dc27a-159">Considerations for a multiserver deployment</span></span>  
 ![](../core/media/adapters-wss-multiserver-screenshot01.gif "Adapters_WSS_Multiserver_Screenshot01")  
  
### <a name="general-considerations"></a><span data-ttu-id="dc27a-160">常规注意事项</span><span class="sxs-lookup"><span data-stu-id="dc27a-160">General considerations</span></span>  
 <span data-ttu-id="dc27a-161">在多服务器环境中安装和部署 Windows SharePoint Services 适配器时，应注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="dc27a-161">When you set up and deploy the Windows SharePoint Services adapter in a multiserver environment, consider the following:</span></span>  
  
-   <span data-ttu-id="dc27a-162">将 BizTalk 服务帐户添加到每个服务器上的 SharePoint Enabled Hosts 这一 Windows 组中。</span><span class="sxs-lookup"><span data-stu-id="dc27a-162">Add the BizTalk Service account to the SharePoint Enabled Hosts Windows group on each server.</span></span>  
  
-   <span data-ttu-id="dc27a-163">使用 SharePoint 管理中心工具，将 SharePoint Enabled Hosts 组添加到 SharePoint 参与者角色中。</span><span class="sxs-lookup"><span data-stu-id="dc27a-163">Add the SharePoint Enabled Hosts group to the SharePoint Contributors role using the SharePoint Central Administration tool.</span></span>  
  
-   <span data-ttu-id="dc27a-164">在 [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] 上，运行 SharePoint 适配器 Web Service 的标识需要具有以下权限：</span><span class="sxs-lookup"><span data-stu-id="dc27a-164">On [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)], the identity under which the SharePoint Adapter Web Service runs needs the following permissions:</span></span>  
  
     <span data-ttu-id="dc27a-165">**读取**权限**Program Files\Microsoft BizTalk Server\<版本 > \Business Activity Services\BTSharePointV3AdapterWS**文件夹。</span><span class="sxs-lookup"><span data-stu-id="dc27a-165">**Read** permissions on the **Program Files\Microsoft BizTalk Server \<version>\Business Activity Services\BTSharePointV3AdapterWS** folder.</span></span> <span data-ttu-id="dc27a-166">如果使用 Windows 的 64 位版本和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，需要在上设置权限**Program Files (x86) \Microsoft BizTalk Server\<版本 > \Business Activity Services\BTSharePointV3AdapterWS**</span><span class="sxs-lookup"><span data-stu-id="dc27a-166">If using a 64-bit version of Windows and [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], permissions need to be set on the **Program Files (x86)\Microsoft BizTalk Server \<version>\Business Activity Services\BTSharePointV3AdapterWS**</span></span>  
  
     <span data-ttu-id="dc27a-167">**读取**对以下注册表项的权限： **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Shared Tools\Web Server\Extensions\12.0\Secure\ConfigDB**。</span><span class="sxs-lookup"><span data-stu-id="dc27a-167">**Read** permission on the following registry key: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Shared Tools\Web Server\Extensions\12.0\Secure\ConfigDB**.</span></span>  
  
     <span data-ttu-id="dc27a-168">包含 Sharepoint 数据库的 SQL Server 的登录权限。</span><span class="sxs-lookup"><span data-stu-id="dc27a-168">Logon permissions on the SQL Server that contains the Sharepoint databases.</span></span>  
  
     <span data-ttu-id="dc27a-169">成员**公共**和**WSS_Content_Application_Pools** SharePoint 配置数据库中的角色。</span><span class="sxs-lookup"><span data-stu-id="dc27a-169">A member of the **Public** and **WSS_Content_Application_Pools** roles within the SharePoint configuration database.</span></span>  
  
     <span data-ttu-id="dc27a-170">成员**公共**和**db 所有者**SharePoint 内容数据库中的角色。</span><span class="sxs-lookup"><span data-stu-id="dc27a-170">A member of the **Public** and **db owner** roles within the SharePoint content database.</span></span>  
  
-   <span data-ttu-id="dc27a-171">必须将 Web Services 安装所在的网站扩展为 SharePoint Services 网站。</span><span class="sxs-lookup"><span data-stu-id="dc27a-171">The Web site that you install the Web service on must be extended as a SharePoint Services Web site.</span></span>  
  
-   <span data-ttu-id="dc27a-172">你可以使用无提示安装方式来安装和配置 Windows SharePoint Services 适配器。</span><span class="sxs-lookup"><span data-stu-id="dc27a-172">You can install and configure the Windows SharePoint Services adapter using a silent installation.</span></span> <span data-ttu-id="dc27a-173">有关详细信息，请参阅[附录 a： 无提示安装](../install-and-config-guides/appendix-a-silent-installation.md)。</span><span class="sxs-lookup"><span data-stu-id="dc27a-173">For more information, see [Appendix A: Silent Installation](../install-and-config-guides/appendix-a-silent-installation.md).</span></span>  
  
### <a name="considerations-for-network-load-balancing-nlb"></a><span data-ttu-id="dc27a-174">网络负载平衡 (NLB) 的注意事项</span><span class="sxs-lookup"><span data-stu-id="dc27a-174">Considerations for network load balancing (NLB)</span></span>  
 <span data-ttu-id="dc27a-175">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]对于 Windows SharePoint Services 的适配器支持 NLB 群集的 Windows SharePoint Services 服务器和在同一个组中配置的多个 BizTalk 服务器。</span><span class="sxs-lookup"><span data-stu-id="dc27a-175">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adapter for Windows SharePoint Services supports NLB clustering of the Windows SharePoint Services servers along with multiple BizTalk servers that are configured in the same group.</span></span> <span data-ttu-id="dc27a-176">因此，必须按照 SharePoint 文档的建议将 Windows SharePoint Services 安装在 NLB 群集上。</span><span class="sxs-lookup"><span data-stu-id="dc27a-176">For this, Windows SharePoint Services must be installed on the NLB cluster as recommended by SharePoint documentation.</span></span>  
  
 <span data-ttu-id="dc27a-177">在具有 NLB 的多服务器环境中安装和部署 Windows SharePoint Services 适配器时，应注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="dc27a-177">When you set up and deploy the Windows SharePoint Services adapter in a multiserver environment with NLB, consider the following:</span></span>  
  
-   <span data-ttu-id="dc27a-178">通过选择相应的选项，将 Windows SharePoint Services 配置为指向现有 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="dc27a-178">Configure Windows SharePoint Services by selecting the option to point to an existing BizTalk Management database.</span></span> <span data-ttu-id="dc27a-179">指向在第一台计算机上创建的 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="dc27a-179">Point to the BizTalk Management database created on the first computer.</span></span> <span data-ttu-id="dc27a-180">这将向 Windows SharePoint Services 表明你要设置一个 Web 服务器环境。</span><span class="sxs-lookup"><span data-stu-id="dc27a-180">This indicates to Windows SharePoint Services that you intend to have a Web server environment.</span></span> <span data-ttu-id="dc27a-181">通过指向现有内容数据库来扩展网站。</span><span class="sxs-lookup"><span data-stu-id="dc27a-181">Extend the Web site by pointing to the existing content database.</span></span>  
  
-   <span data-ttu-id="dc27a-182">你必须在 Web 服务器环境中的每台 Windows SharePoint Services 计算机上扩展同一网站（例如，端口 80 上的默认网站）。</span><span class="sxs-lookup"><span data-stu-id="dc27a-182">You must extend the same Web site (for example, the default Web site on port 80) on each Windows SharePoint Services computer in the Web server environment.</span></span>  
  
-   <span data-ttu-id="dc27a-183">必须在每台 NLB 主机上以相同方式安装和配置 BTSharePointAdapterWS。</span><span class="sxs-lookup"><span data-stu-id="dc27a-183">The BTSharePointAdapterWS must be installed and configured the same way on each of the NLB hosts.</span></span> <span data-ttu-id="dc27a-184">必须配置以下 NLB 设置：</span><span class="sxs-lookup"><span data-stu-id="dc27a-184">You must configure the following NLB settings:</span></span>  
  
    -   <span data-ttu-id="dc27a-185">协议：TCP</span><span class="sxs-lookup"><span data-stu-id="dc27a-185">Protocol: TCP</span></span>  
  
    -   <span data-ttu-id="dc27a-186">端口： 80 （HTTP 端口的 IIS 网站已其中安装并配置 Windows SharePoint Services 适配器 Web 服务）</span><span class="sxs-lookup"><span data-stu-id="dc27a-186">Ports: 80 (The HTTP Port of the IIS Web site where the Windows SharePoint Services adapter Web service has been installed and configured)</span></span>  
  
    -   <span data-ttu-id="dc27a-187">筛选模式： 多个主机</span><span class="sxs-lookup"><span data-stu-id="dc27a-187">Filtering mode: Multiple host</span></span>  
  
    -   <span data-ttu-id="dc27a-188">相关性： 无</span><span class="sxs-lookup"><span data-stu-id="dc27a-188">Affinity: None</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dc27a-189">只有在该站点未配置 HTTPS 时，才能使用此设置。</span><span class="sxs-lookup"><span data-stu-id="dc27a-189">This setting can be used only if the site is not configured for HTTPS.</span></span> <span data-ttu-id="dc27a-190">如果在使用 HTTPS 的站点上安装 BTSharePointAdapterWS Web Services，则必须使用单客户端相似性。</span><span class="sxs-lookup"><span data-stu-id="dc27a-190">If the BTSharePointAdapterWS Web service is installed on a site with HTTPS, then you must use Single-client affinity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc27a-191">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dc27a-191">See Also</span></span>  
 <span data-ttu-id="dc27a-192">[Windows SharePoint Services Adapter](../core/windows-sharepoint-services-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="dc27a-192">[Windows SharePoint Services Adapter](../core/windows-sharepoint-services-adapter.md) </span></span>  
 [<span data-ttu-id="dc27a-193">单服务器部署</span><span class="sxs-lookup"><span data-stu-id="dc27a-193">Single-Server Deployment</span></span>](../core/single-server-deployment.md)