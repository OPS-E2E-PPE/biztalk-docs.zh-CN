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
ms.openlocfilehash: 62b99fd47ec04ecfd0286a694f21da733339885c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996142"
---
# <a name="single-server-deployment"></a><span data-ttu-id="8a0de-102">单服务器部署</span><span class="sxs-lookup"><span data-stu-id="8a0de-102">Single-Server Deployment</span></span>
<span data-ttu-id="8a0de-103">本主题将介绍对用于 Windows SharePoint Services 的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 适配器进行单服务器安装和部署时的注意事项。</span><span class="sxs-lookup"><span data-stu-id="8a0de-103">This topic discusses single-server setup and deployment considerations for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adapter for Windows SharePoint Services.</span></span>  
  
## <a name="installing-the-windows-sharepoint-services-adapter-in-a-single-server-deployment"></a><span data-ttu-id="8a0de-104">在单服务器部署中安装 Windows SharePoint Services 适配器</span><span class="sxs-lookup"><span data-stu-id="8a0de-104">Installing the Windows SharePoint Services adapter in a single-server deployment</span></span>  
 <span data-ttu-id="8a0de-105">选择 Windows SharePoint Service 适配器 Web 服务组件将安装必需的软件的 Windows SharePoint Services 适配器处理通过 Windows SharePoint Services 传入和传出的文档。</span><span class="sxs-lookup"><span data-stu-id="8a0de-105">Selecting the Windows SharePoint Service adapter Web service component installs the necessary software for the Windows SharePoint Services adapter to process incoming and outgoing documents through Windows SharePoint Services.</span></span> <span data-ttu-id="8a0de-106">此 Web Services 必须安装在安装有 Windows SharePoint Services 的服务器上。</span><span class="sxs-lookup"><span data-stu-id="8a0de-106">This Web service must be installed on the server where Windows SharePoint Services is installed.</span></span> <span data-ttu-id="8a0de-107">适配器 Web 服务可以处理多个 SharePoint 站点，包括承载业务活动服务 (BAS)，而不考虑它们是否相同的 IIS 站点上或在不同的 IIS 站点上的网站。</span><span class="sxs-lookup"><span data-stu-id="8a0de-107">The adapter Web service can handle multiple SharePoint sites including the Web site that hosts Business Activity Services (BAS), regardless of whether they are on the same IIS site or on different IIS sites.</span></span>  
  
 <span data-ttu-id="8a0de-108">Windows SharePoint Services 适配器具有三个组件：</span><span class="sxs-lookup"><span data-stu-id="8a0de-108">The Windows SharePoint Services adapter has three components:</span></span>  
  
- <span data-ttu-id="8a0de-109">运行时组件</span><span class="sxs-lookup"><span data-stu-id="8a0de-109">Runtime components</span></span>  
  
- <span data-ttu-id="8a0de-110">设计时组件</span><span class="sxs-lookup"><span data-stu-id="8a0de-110">Design time components</span></span>  
  
- <span data-ttu-id="8a0de-111">适配器 Web Services</span><span class="sxs-lookup"><span data-stu-id="8a0de-111">Adapter Web service</span></span>  
  
  <span data-ttu-id="8a0de-112">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 运行时功能将自动安装并配置适配器运行时。</span><span class="sxs-lookup"><span data-stu-id="8a0de-112">The adapter runtime is installed and configured automatically by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Runtime feature.</span></span> <span data-ttu-id="8a0de-113">适配器设计时组件安装和配置与其他[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]功能。</span><span class="sxs-lookup"><span data-stu-id="8a0de-113">The adapter design time components are installed and configured with the other [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] features.</span></span> <span data-ttu-id="8a0de-114">通过使用管理工具、开发人员工具、SDK 或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 运行时功能附带的工具来创建 Windows SharePoint Services 端口，可以与设计时组件进行交互。</span><span class="sxs-lookup"><span data-stu-id="8a0de-114">You interact with the design time components by creating Windows SharePoint Services ports through tools that are included in the Administration Tools, Developer Tools, and SDK or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Runtime features.</span></span> <span data-ttu-id="8a0de-115">你无法自定义运行时和设计时组件的任何配置选项。</span><span class="sxs-lookup"><span data-stu-id="8a0de-115">You cannot customize any configuration options for runtime and design time components.</span></span> <span data-ttu-id="8a0de-116">只能自定义 Windows SharePoint Services 适配器 Web Services 选项。</span><span class="sxs-lookup"><span data-stu-id="8a0de-116">You can customize only the Windows SharePoint Service adapter Web service options.</span></span>  
  
  <span data-ttu-id="8a0de-117">只有 SharePoint Enabled Hosts 组的成员才具有调用该适配器 Web Services 的权限。</span><span class="sxs-lookup"><span data-stu-id="8a0de-117">Only members of the SharePoint Enabled Hosts group have permissions to invoke the adapter Web service.</span></span> <span data-ttu-id="8a0de-118">有关 Windows SharePoint Services 适配器运行时所需的 Windows SharePoint Services 权限的详细信息，请参阅中的安全性部分[什么是 Windows SharePoint Services 适配器？](../core/what-is-the-windows-sharepoint-services-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="8a0de-118">For more information about the Windows SharePoint Services permissions needed by the Windows SharePoint Services adapter runtime, see the security section in [What Is the Windows SharePoint Services Adapter?](../core/what-is-the-windows-sharepoint-services-adapter.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8a0de-119">如果选择安装 BAS，系统将自动选择安装 Windows SharePoint Services 适配器 Web Services 组件。</span><span class="sxs-lookup"><span data-stu-id="8a0de-119">The Windows SharePoint Services adapter Web service component will be automatically selected if you choose to install BAS.</span></span>  
  
#### <a name="to-install-the-windows-sharepoint-services-adapter"></a><span data-ttu-id="8a0de-120">安装 Windows SharePoint Services 适配器</span><span class="sxs-lookup"><span data-stu-id="8a0de-120">To install the Windows SharePoint Services adapter</span></span>  
  
1.  <span data-ttu-id="8a0de-121">安装 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="8a0de-121">Install BizTalk Server.</span></span> <span data-ttu-id="8a0de-122">有关详细信息，请参阅[BizTalk Server 2013 和 2013 R2 安装概述](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)。</span><span class="sxs-lookup"><span data-stu-id="8a0de-122">For more information, see [Installation Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5).</span></span>  
  
2.  <span data-ttu-id="8a0de-123">上**组件安装**屏幕上，在**可用组件**下**其他软件**，选择**Windows SharePoint Services 适配器Web 服务**。</span><span class="sxs-lookup"><span data-stu-id="8a0de-123">On the **Component Installation** screen, under **Available Components**, under **Additional Software**, select **Windows SharePoint Services Adapter Web service**.</span></span>  
  
## <a name="configuring-the-windows-sharepoint-services-adapter-web-service-in-a-single-server-deployment"></a><span data-ttu-id="8a0de-124">在单服务器部署中配置 Windows SharePoint Services 适配器 Web Services</span><span class="sxs-lookup"><span data-stu-id="8a0de-124">Configuring the Windows SharePoint Services adapter Web service in a single-server deployment</span></span>  
 <span data-ttu-id="8a0de-125">你可以使用基本配置或自定义配置来配置 Windows SharePoint Services 适配器。</span><span class="sxs-lookup"><span data-stu-id="8a0de-125">You can configure the Windows SharePoint Services adapter using either a basic configuration or a custom configuration.</span></span> <span data-ttu-id="8a0de-126">有关这些工具的详细信息，请参阅[BizTalk Server 2013 和 2013 R2 配置概述](http://msdn.microsoft.com/library/aa58c43f-8f0e-4a5c-89b9-db7b8a852a72)。</span><span class="sxs-lookup"><span data-stu-id="8a0de-126">For more information about these tools, see [Configuration Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/aa58c43f-8f0e-4a5c-89b9-db7b8a852a72).</span></span>  
  
### <a name="using-a-basic-configuration"></a><span data-ttu-id="8a0de-127">使用基本配置</span><span class="sxs-lookup"><span data-stu-id="8a0de-127">Using a basic configuration</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="8a0de-128"> 允许用户使用默认设置来配置服务器。</span><span class="sxs-lookup"><span data-stu-id="8a0de-128"> allows you to configure the server by using default settings.</span></span> <span data-ttu-id="8a0de-129">服务器的默认配置设置使用的是你在配置向导中输入的数据库服务器名称、用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="8a0de-129">The default settings for the server are configured using the database server name, user name, and password that you enter into the configuration wizard.</span></span> <span data-ttu-id="8a0de-130">当使用基本配置对 Windows SharePoint Services 适配器 Web Services 进行配置时，将出现以下结果：</span><span class="sxs-lookup"><span data-stu-id="8a0de-130">When you configure the Windows SharePoint Services adapter Web service using a basic configuration, the following happens:</span></span>  
  
-   <span data-ttu-id="8a0de-131">创建 SharePoint Enabled Hosts Windows 组。</span><span class="sxs-lookup"><span data-stu-id="8a0de-131">The SharePoint Enabled Hosts Windows group is created.</span></span>  
  
-   <span data-ttu-id="8a0de-132">使用默认网站作为 Windows SharePoint Services 适配器的宿主</span><span class="sxs-lookup"><span data-stu-id="8a0de-132">The Default Web Site is used to host the Windows SharePoint Services Adapter</span></span>  
  
-   <span data-ttu-id="8a0de-133">创建 BTSSharePointAdapterWSAppPool 应用程序池并将其配置为还用于运行 Windows SharePoint Services 应用程序池的帐户下运行。</span><span class="sxs-lookup"><span data-stu-id="8a0de-133">The BTSSharePointAdapterWSAppPool application pool is created and configured to run under the account that is also used to run the Windows SharePoint Services application pool.</span></span>  
  
-   <span data-ttu-id="8a0de-134">创建 BTSharePointAdapterWS 虚拟应用程序，并将其配置为在 BTSSharePointAdapterWSAppPool 应用程序池中运行</span><span class="sxs-lookup"><span data-stu-id="8a0de-134">The BTSharePointAdapterWS virtual application is created and configured to run in the BTSSharePointAdapterWSAppPool application pool</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8a0de-135">如果此虚拟目录已存在，则配置过程将不会更新元数据库中的属性。</span><span class="sxs-lookup"><span data-stu-id="8a0de-135">If this virtual directory already exists, configuration will not update the properties in the metabase.</span></span> <span data-ttu-id="8a0de-136">必须删除该虚拟目录，并重新进行配置。</span><span class="sxs-lookup"><span data-stu-id="8a0de-136">You must delete the virtual directory, and run configuration again.</span></span>  
  
- <span data-ttu-id="8a0de-137">BTSharePointAdapterWS 虚拟应用程序包含 Web Services</span><span class="sxs-lookup"><span data-stu-id="8a0de-137">The BTSharePointAdapterWS virtual application contains the Web service</span></span>  
  
  <span data-ttu-id="8a0de-138">有关基本配置的详细信息，请参阅[基本配置](http://msdn.microsoft.com/library/abdf3eb5-9779-47ff-bc97-2209eb4b12f5)。</span><span class="sxs-lookup"><span data-stu-id="8a0de-138">For more information about basic configuration, see [Basic Configuration](http://msdn.microsoft.com/library/abdf3eb5-9779-47ff-bc97-2209eb4b12f5).</span></span>  
  
### <a name="using-a-custom-configuration"></a><span data-ttu-id="8a0de-139">使用自定义配置</span><span class="sxs-lookup"><span data-stu-id="8a0de-139">Using a custom configuration</span></span>  
 <span data-ttu-id="8a0de-140">BizTalk Server 配置可以对本地计算机上已安装的功能的配置状态进行高级分析。</span><span class="sxs-lookup"><span data-stu-id="8a0de-140">The BizTalk Server Configuration provides a high-level analysis of the configuration state of the features you have installed on the local computer.</span></span> <span data-ttu-id="8a0de-141">使用该工具，可以配置功能、取消对功能的配置、配置安全设置，以及将配置导入和导出计算机。</span><span class="sxs-lookup"><span data-stu-id="8a0de-141">The tool allows you to configure and unconfigure features, configure security settings, and import and export configurations from other computers.</span></span>  
  
 <span data-ttu-id="8a0de-142">使用**Windows SharePoint Services 适配器 Web Services**页后，可以在此计算机上配置 Windows SharePoint Services 适配器。</span><span class="sxs-lookup"><span data-stu-id="8a0de-142">Use the **Windows SharePoint Services Adapter Web Service** page to configure the Windows SharePoint Services adapter on this computer.</span></span> <span data-ttu-id="8a0de-143">下表列出了这些配置选项：</span><span class="sxs-lookup"><span data-stu-id="8a0de-143">The following table lists the configuration options.</span></span>  
  
|<span data-ttu-id="8a0de-144">使用此选项</span><span class="sxs-lookup"><span data-stu-id="8a0de-144">Use this</span></span>|<span data-ttu-id="8a0de-145">执行的操作</span><span class="sxs-lookup"><span data-stu-id="8a0de-145">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="8a0de-146">**此计算机上启用 Windows SharePoint Services 适配器**</span><span class="sxs-lookup"><span data-stu-id="8a0de-146">**Enable Windows SharePoint Services Adapter on this computer**</span></span>|<span data-ttu-id="8a0de-147">选择**启用此计算机上 Windows SharePoint Services 适配器**若要启用此计算机上的适配器。</span><span class="sxs-lookup"><span data-stu-id="8a0de-147">Select **Enable Windows SharePoint Services Adapter on this computer** to enable the adapter on this computer.</span></span>|  
|<span data-ttu-id="8a0de-148">**Windows 组**</span><span class="sxs-lookup"><span data-stu-id="8a0de-148">**Windows group**</span></span>|<span data-ttu-id="8a0de-149">**Windows 组**列表提供了 BizTalk SharePoint 适配器启用主机 Windows 组的可编辑视图。</span><span class="sxs-lookup"><span data-stu-id="8a0de-149">The **Windows group** list provides a view that you can edit of the BizTalk SharePoint Adapter Enabled Hosts Windows group.</span></span>|  
|<span data-ttu-id="8a0de-150">**Windows SharePoint Services 适配器网站**</span><span class="sxs-lookup"><span data-stu-id="8a0de-150">**Windows SharePoint Services Adapter Web site**</span></span>|<span data-ttu-id="8a0de-151">选择将用作 Windows SharePoint Services 适配器 Web Services 的宿主的网站。</span><span class="sxs-lookup"><span data-stu-id="8a0de-151">Select the Web site that will host the Windows SharePoint Service adapter Web service.</span></span>|  
  
 <span data-ttu-id="8a0de-152">在配置使用自定义配置的 Windows SharePoint Services 适配器时，会发生以下情况：</span><span class="sxs-lookup"><span data-stu-id="8a0de-152">When you configure the Windows SharePoint Services adapter using a custom configuration, the following happens:</span></span>  
  
-   <span data-ttu-id="8a0de-153">默认情况下，除非指定了其他 Windows 组，否则将创建 SharePoint Enabled Hosts 这一 Windows 组。</span><span class="sxs-lookup"><span data-stu-id="8a0de-153">The SharePoint Enabled Hosts Windows group is created by default unless you specify another Windows group</span></span>  
  
-   <span data-ttu-id="8a0de-154">除非指定其他网站，否则将使用默认网站作为 Windows SharePoint Services 适配器的宿主。</span><span class="sxs-lookup"><span data-stu-id="8a0de-154">The Default Web Site is used to host the Windows SharePoint Services adapter unless you specify another Web site</span></span>  
  
-   <span data-ttu-id="8a0de-155">创建 BTSSharePointAdapterWSAppPool 应用程序池，并将其配置为使用运行 Windows SharePoint Services 应用程序池所用的同一帐户来运行。</span><span class="sxs-lookup"><span data-stu-id="8a0de-155">The BTSSharePointAdapterWSAppPool application pool is created and configured to run under the account that is also used to run the Windows SharePoint Services application pool</span></span>  
  
-   <span data-ttu-id="8a0de-156">创建 BTSharePointAdapterWS 虚拟应用程序，并将其配置为在 BTSSharePointAdapterWSAppPool 应用程序池中运行</span><span class="sxs-lookup"><span data-stu-id="8a0de-156">The BTSharePointAdapterWS virtual application is created and configured to run in the BTSSharePointAdapterWSAppPool application pool</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8a0de-157">如果此虚拟目录已存在，则配置过程将不会更新元数据库中的属性。</span><span class="sxs-lookup"><span data-stu-id="8a0de-157">If this virtual directory already exists, configuration will not update the properties in the metabase.</span></span> <span data-ttu-id="8a0de-158">必须删除该虚拟目录，并重新进行配置。</span><span class="sxs-lookup"><span data-stu-id="8a0de-158">You must delete the virtual directory, and run configuration again.</span></span>  
  
- <span data-ttu-id="8a0de-159">BTSharePointAdapterWS 虚拟应用程序包含 Web Services</span><span class="sxs-lookup"><span data-stu-id="8a0de-159">The BTSharePointAdapterWS virtual application contains the Web service</span></span>  
  
  <span data-ttu-id="8a0de-160">有关自定义配置管理器的详细信息，请参阅[导入和导出 BizTalk Server 配置](../install-and-config-guides/import-and-export-biztalk-server-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="8a0de-160">For more information about the custom configuration manager, see [Import and Export BizTalk Server Configuration](../install-and-config-guides/import-and-export-biztalk-server-configuration.md).</span></span>  
  
##### <a name="to-configure-the-windows-sharepoint-services-adapter-by-using-a-custom-configuration"></a><span data-ttu-id="8a0de-161">若要通过使用自定义配置来配置 Windows SharePoint Services 适配器</span><span class="sxs-lookup"><span data-stu-id="8a0de-161">To configure the Windows SharePoint Services adapter by using a custom configuration</span></span>  
  
1.  <span data-ttu-id="8a0de-162">在中**BizTalk Server 配置**，选择**SharePoint 适配器**节点。</span><span class="sxs-lookup"><span data-stu-id="8a0de-162">In the **BizTalk Server Configuration**, select the **SharePoint adapter** node.</span></span>  
  
2.  <span data-ttu-id="8a0de-163">选择**启用此计算机上 Windows SharePoint Services 适配器**。</span><span class="sxs-lookup"><span data-stu-id="8a0de-163">Select **Enable Windows SharePoint Services Adapter on this computer**.</span></span>  
  
3.  <span data-ttu-id="8a0de-164">下**Windows 组**，选择你将使用适用于 Windows SharePoint Services 适配器的 Windows 组。</span><span class="sxs-lookup"><span data-stu-id="8a0de-164">Under **Windows Group**, select the Windows group you will be using for the Windows SharePoint Services adapter.</span></span> <span data-ttu-id="8a0de-165">默认情况下，将选择 SharePoint Enabled Hosts。</span><span class="sxs-lookup"><span data-stu-id="8a0de-165">By default, this is SharePoint Enabled Hosts.</span></span>  
  
4.  <span data-ttu-id="8a0de-166">在中**Windows SharePoint Services 适配器网站**下拉列表框中，选择网站将在其中安装适配器组件。</span><span class="sxs-lookup"><span data-stu-id="8a0de-166">In the **Windows SharePoint Services Adapter Web Site** drop-down box, select the Web site where the adapter components will be installed.</span></span> <span data-ttu-id="8a0de-167">默认情况下，将选择默认网站。</span><span class="sxs-lookup"><span data-stu-id="8a0de-167">By default, this is the Default Web Site.</span></span>  
  
5.  <span data-ttu-id="8a0de-168">单击“应用配置”。</span><span class="sxs-lookup"><span data-stu-id="8a0de-168">Click **Apply Configuration**.</span></span>  
  
## <a name="considerations-for-a-single-server-deployment"></a><span data-ttu-id="8a0de-169">单服务器部署的注意事项</span><span class="sxs-lookup"><span data-stu-id="8a0de-169">Considerations for a single-server deployment</span></span>  
 <span data-ttu-id="8a0de-170">在单服务器环境中安装和部署 Windows SharePoint Services 适配器时，应注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="8a0de-170">When you set up and deploy the Windows SharePoint Services adapter in a single-server environment, consider the following:</span></span>  
  
- <span data-ttu-id="8a0de-171">将 BizTalk 服务帐户添加到该服务器上的 SharePoint Enabled Hosts 这一 Windows 组中。</span><span class="sxs-lookup"><span data-stu-id="8a0de-171">Add the BizTalk Service account to the SharePoint Enabled Hosts Windows group on that server.</span></span>  
  
- <span data-ttu-id="8a0de-172">使用 SharePoint 管理中心工具，将 SharePoint Enabled Hosts 组添加到 SharePoint 参与者角色中。</span><span class="sxs-lookup"><span data-stu-id="8a0de-172">Add the SharePoint Enabled Hosts group to the SharePoint Contributors role using the SharePoint Central Administration tool.</span></span>  
  
- <span data-ttu-id="8a0de-173">在 [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] 上，运行 SharePoint 适配器 Web Service 的标识需要具有以下权限：</span><span class="sxs-lookup"><span data-stu-id="8a0de-173">On [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)], the identity under which the SharePoint Adapter Web Service runs needs the following permissions:</span></span>  
  
   <span data-ttu-id="8a0de-174">**读取**上的权限**Program Files\Microsoft BizTalk Server\<版本\>\Business Activity Services\BTSharePointV3AdapterWS**文件夹。</span><span class="sxs-lookup"><span data-stu-id="8a0de-174">**Read** permissions on the **Program Files\Microsoft BizTalk Server \<version\>\Business Activity Services\BTSharePointV3AdapterWS** folder.</span></span> <span data-ttu-id="8a0de-175">如果使用的 Windows 和 BizTalk Server 的 64 位版，需要在上设置权限**Program Files (x86) \Microsoft BizTalk Server\<版本\>\Business Activity Services\BTSharePointV3AdapterWS**</span><span class="sxs-lookup"><span data-stu-id="8a0de-175">If using a 64-bit version of Windows and BizTalk Server, permissions need to be set on the **Program Files (x86)\Microsoft BizTalk Server \<version\>\Business Activity Services\BTSharePointV3AdapterWS**</span></span>  
  
   <span data-ttu-id="8a0de-176">**读取**以下注册表项权限： **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Shared Tools\Web Server\Extensions\12.0\Secure\ConfigDB**。</span><span class="sxs-lookup"><span data-stu-id="8a0de-176">**Read** permission on the following registry key: **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Shared Tools\Web Server\Extensions\12.0\Secure\ConfigDB**.</span></span>  
  
   <span data-ttu-id="8a0de-177">包含 Sharepoint 数据库的 SQL Server 的登录权限。</span><span class="sxs-lookup"><span data-stu-id="8a0de-177">Logon permissions on the SQL Server that contains the Sharepoint databases.</span></span>  
  
   <span data-ttu-id="8a0de-178">成员**公共**并**WSS_Content_Application_Pools** SharePoint 配置数据库中的角色。</span><span class="sxs-lookup"><span data-stu-id="8a0de-178">A member of the **Public** and **WSS_Content_Application_Pools** roles within the SharePoint configuration database.</span></span>  
  
   <span data-ttu-id="8a0de-179">成员**公共**并**db 所有者**SharePoint 内容数据库中的角色。</span><span class="sxs-lookup"><span data-stu-id="8a0de-179">A member of the **Public** and **db owner** roles within the SharePoint content database.</span></span>  
  
- <span data-ttu-id="8a0de-180">必须将 Web Services 安装所在的网站扩展为 SharePoint Services 网站。</span><span class="sxs-lookup"><span data-stu-id="8a0de-180">The Web site that you install the Web service on must be extended as a SharePoint Services Web site.</span></span>  
  
- <span data-ttu-id="8a0de-181">你可以安装和配置 Windows SharePoint Services 适配器使用无提示安装。</span><span class="sxs-lookup"><span data-stu-id="8a0de-181">You can install and configure the Windows SharePoint Services adapter using silent installation.</span></span> <span data-ttu-id="8a0de-182">有关详细信息，请参阅[附录 a： 无提示安装](../install-and-config-guides/appendix-a-silent-installation.md)。</span><span class="sxs-lookup"><span data-stu-id="8a0de-182">For more information, see [Appendix A: Silent Installation](../install-and-config-guides/appendix-a-silent-installation.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a0de-183">请参阅</span><span class="sxs-lookup"><span data-stu-id="8a0de-183">See Also</span></span>  
 <span data-ttu-id="8a0de-184">[Windows SharePoint Services 适配器](../core/windows-sharepoint-services-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="8a0de-184">[Windows SharePoint Services Adapter](../core/windows-sharepoint-services-adapter.md) </span></span>  
 [<span data-ttu-id="8a0de-185">多服务器部署</span><span class="sxs-lookup"><span data-stu-id="8a0de-185">Multiserver Deployment</span></span>](../core/multiserver-deployment.md)