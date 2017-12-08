---
title: "准备计算机以安装 |Microsoft 文档"
ms.custom: 
ms.date: 2016-03-15
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 53df7a2f-638b-4921-a97f-736760248526
caps.latest.revision: "32"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a493c1a0ef38e9be5e229ff82f8773211adfe765
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="prepare-your-computer-for-installation"></a><span data-ttu-id="d793b-102">准备计算机以进行安装</span><span class="sxs-lookup"><span data-stu-id="d793b-102">Prepare Your Computer for Installation</span></span>
<span data-ttu-id="d793b-103">本主题将介绍如何通过安装和配置所有必备软件，然后再创建帐户并设置权限来准备你的计算机。</span><span class="sxs-lookup"><span data-stu-id="d793b-103">This topic lists the steps to prepare your computer by installing and configuring all software prerequisites, and then creating accounts and setting permissions.</span></span>  

> [!TIP] 
> <span data-ttu-id="d793b-104">集成 MVP 准备了非常详细的分步指南，用于安装必备组件和 BizTalk Server：[BizTalk 2013 Installation and Configuration part 1](http://sandroaspbiztalkblog.wordpress.com/2013/05/05/biztalk-2013-installation-and-configuration-important-considerations-before-set-up-the-server-part-1/)（BizTalk 2013 安装和配置第 1 部分）。</span><span class="sxs-lookup"><span data-stu-id="d793b-104">An integration MVP prepared a very detailed step-by-step guide to install the prerequisites, and BizTalk Server:  [BizTalk 2013 Installation and Configuration part 1](http://sandroaspbiztalkblog.wordpress.com/2013/05/05/biztalk-2013-installation-and-configuration-important-considerations-before-set-up-the-server-part-1/).</span></span>  
> 
> <span data-ttu-id="d793b-105">Microsoft 不推荐某些步骤，例如，禁用用户访问控制 (UAC) 或 Windows 防火墙。</span><span class="sxs-lookup"><span data-stu-id="d793b-105">Some steps are not recommended by Microsoft, such as disabling User Access Control (UAC) or Windows Firewall.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="d793b-106">按列出的顺序完成这些任务。</span><span class="sxs-lookup"><span data-stu-id="d793b-106">Complete these tasks in the order listed.</span></span>  
  
##  <a name="BKMK_InstUpdates"></a> <span data-ttu-id="d793b-107">安装 Windows 更新</span><span class="sxs-lookup"><span data-stu-id="d793b-107">Install Windows Updates</span></span>  
  
-   <span data-ttu-id="d793b-108">**Windows 7**：单击“开始”。</span><span class="sxs-lookup"><span data-stu-id="d793b-108">**Windows 7**: Click Start.</span></span> <span data-ttu-id="d793b-109">在“搜索”文本框中，键入 **Windows Update**。</span><span class="sxs-lookup"><span data-stu-id="d793b-109">In the **Search** text box, type **Windows Update**.</span></span>  
  
-   <span data-ttu-id="d793b-110">**Windows 8.1、[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] 和 [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] R2**：单击键盘上的 Windows 按钮，并键入“Windows 更新”。</span><span class="sxs-lookup"><span data-stu-id="d793b-110">**Windows 8.1, [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)], and [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] R2**: Click the Windows button on the keyboard and type **Windows Update**.</span></span> <span data-ttu-id="d793b-111">在搜索结果中，单击“Windows 更新”。</span><span class="sxs-lookup"><span data-stu-id="d793b-111">From the search results, click **Windows Update**.</span></span>  
  
 <span data-ttu-id="d793b-112">安装更新之后，你可能需要重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="d793b-112">After installing updates, you may need to restart the computer.</span></span>  
  
##  <a name="BKMK_IIS"></a> <span data-ttu-id="d793b-113">启用 Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="d793b-113">Enable Internet Information Services</span></span>  
 <span data-ttu-id="d793b-114">Microsoft Internet 信息服务 (IIS) 为许多 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 功能提供了 Web 应用程序基础结构，包括：</span><span class="sxs-lookup"><span data-stu-id="d793b-114">Microsoft Internet Information Services (IIS) provides a Web application infrastructure for many [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] features, including:</span></span>  
  
-   <span data-ttu-id="d793b-115">HTTP 适配器</span><span class="sxs-lookup"><span data-stu-id="d793b-115">HTTP adapter</span></span>  
  
-   <span data-ttu-id="d793b-116">SOAP 适配器</span><span class="sxs-lookup"><span data-stu-id="d793b-116">SOAP adapter</span></span>  
  
-   <span data-ttu-id="d793b-117">Windows SharePoint Services 适配器</span><span class="sxs-lookup"><span data-stu-id="d793b-117">Windows SharePoint Services adapter</span></span>  
  
-   <span data-ttu-id="d793b-118">安全套接字层 (SSL) 加密</span><span class="sxs-lookup"><span data-stu-id="d793b-118">Secure Sockets Layer (SSL) encryption</span></span>  
  
-   <span data-ttu-id="d793b-119">BAM 门户</span><span class="sxs-lookup"><span data-stu-id="d793b-119">BAM Portal</span></span>  
  
#### <a name="install-iis-75-on-windows-7-sp1"></a><span data-ttu-id="d793b-120">在 Windows 7 SP1 上安装 IIS 7.5</span><span class="sxs-lookup"><span data-stu-id="d793b-120">Install IIS 7.5 on Windows 7 SP1</span></span>  
  
1.  <span data-ttu-id="d793b-121">选择“开始”。</span><span class="sxs-lookup"><span data-stu-id="d793b-121">Select **Start**.</span></span> <span data-ttu-id="d793b-122">在“搜索”文本框中，键入“程序和功能”，并将其打开。</span><span class="sxs-lookup"><span data-stu-id="d793b-122">In the **Search** text box, type **Programs and Features**, and open it.</span></span>  
  
2.  <span data-ttu-id="d793b-123">选择“打开或关闭 Windows 功能”。</span><span class="sxs-lookup"><span data-stu-id="d793b-123">Select**Turn Windows features on or off**.</span></span>  
  
3.  <span data-ttu-id="d793b-124">选择“Internet Information Services”并展开“Internet Information Services”。</span><span class="sxs-lookup"><span data-stu-id="d793b-124">Select**Internet Information Services** and expand **Internet Information Services**.</span></span> <span data-ttu-id="d793b-125">除了已默认选中的选项之外，还应选中以下选项：</span><span class="sxs-lookup"><span data-stu-id="d793b-125">In addition to the default checked options, also check the following:</span></span>  
  
    -   <span data-ttu-id="d793b-126">“Web 管理工具”：还需检查：</span><span class="sxs-lookup"><span data-stu-id="d793b-126">**Web Management Tools**: Also check:</span></span>  
  
        -   <span data-ttu-id="d793b-127">IIS 6 管理兼容性：</span><span class="sxs-lookup"><span data-stu-id="d793b-127">IIS 6 Management Compatibility:</span></span>  
  
            -   <span data-ttu-id="d793b-128">IIS 6 管理控制台</span><span class="sxs-lookup"><span data-stu-id="d793b-128">IIS 6 Management Console</span></span>  
  
            -   <span data-ttu-id="d793b-129">IIS 元数据库和 IIS 6 配置兼容性</span><span class="sxs-lookup"><span data-stu-id="d793b-129">IIS Metabase and IIS 6 configuration compatibility</span></span>  
  
        -   <span data-ttu-id="d793b-130">IIS 管理控制台</span><span class="sxs-lookup"><span data-stu-id="d793b-130">IIS Management Console</span></span>  
  
    -   <span data-ttu-id="d793b-131">**万维网服务**：展开“安全性”，还需选择：</span><span class="sxs-lookup"><span data-stu-id="d793b-131">**World Wide Web Services**: Expand **Security** and also select:</span></span>  
  
        -   <span data-ttu-id="d793b-132">基本身份验证</span><span class="sxs-lookup"><span data-stu-id="d793b-132">Basic Authentication</span></span>  
  
        -   <span data-ttu-id="d793b-133">Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="d793b-133">Windows Authentication</span></span>  
  
4.  <span data-ttu-id="d793b-134">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="d793b-134">Select **OK**.</span></span> <span data-ttu-id="d793b-135">完成时，单击“关闭”。</span><span class="sxs-lookup"><span data-stu-id="d793b-135">When complete, click **Close**.</span></span>  
  
 <span data-ttu-id="d793b-136">[http://go.microsoft.com/fwlink/p/?LinkId=257033](http://go.microsoft.com/fwlink/p/?LinkId=257033) 还列出了在 Windows 7 上启用 IIS 的步骤。</span><span class="sxs-lookup"><span data-stu-id="d793b-136">[http://go.microsoft.com/fwlink/p/?LinkId=257033](http://go.microsoft.com/fwlink/p/?LinkId=257033) also lists the steps to enable IIS on Windows 7.</span></span>  
  
#### <a name="install-iis-80-on-windows-8"></a><span data-ttu-id="d793b-137">在 Windows 8 上安装 IIS 8.0</span><span class="sxs-lookup"><span data-stu-id="d793b-137">Install IIS 8.0 on Windows 8</span></span>  
  
1.  <span data-ttu-id="d793b-138">选择键盘上的 Windows 按钮。</span><span class="sxs-lookup"><span data-stu-id="d793b-138">Select the Windows button on your keyboard.</span></span> <span data-ttu-id="d793b-139">键入“程序和功能”，然后选择“设置”。</span><span class="sxs-lookup"><span data-stu-id="d793b-139">Type **Programs and Features** and select**Settings**.</span></span> <span data-ttu-id="d793b-140">在“结果”窗口中，选择“程序和功能”。</span><span class="sxs-lookup"><span data-stu-id="d793b-140">In the Results window, select **Programs and Features**.</span></span>  
  
2.  <span data-ttu-id="d793b-141">选择“打开或关闭 Windows 功能”。</span><span class="sxs-lookup"><span data-stu-id="d793b-141">Select **Turn Windows features on or off**.</span></span>  
  
3.  <span data-ttu-id="d793b-142">选择“Internet Information Services”并展开“Internet Information Services”。</span><span class="sxs-lookup"><span data-stu-id="d793b-142">Select **Internet Information Services** and expand **Internet Information Services**.</span></span> <span data-ttu-id="d793b-143">除了已默认选中的选项之外，还应选择以下选项：</span><span class="sxs-lookup"><span data-stu-id="d793b-143">In addition to the default checked options, also select the following:</span></span>  
  
    -   <span data-ttu-id="d793b-144">“Web 管理工具”：还需检查：</span><span class="sxs-lookup"><span data-stu-id="d793b-144">**Web Management Tools**: Also check:</span></span>  
  
        -   <span data-ttu-id="d793b-145">IIS 6 管理兼容性：</span><span class="sxs-lookup"><span data-stu-id="d793b-145">IIS 6 Management Compatibility:</span></span>  
  
            -   <span data-ttu-id="d793b-146">IIS 6 管理控制台</span><span class="sxs-lookup"><span data-stu-id="d793b-146">IIS 6 Management Console</span></span>  
  
            -   <span data-ttu-id="d793b-147">IIS 元数据库和 IIS 6 配置兼容性</span><span class="sxs-lookup"><span data-stu-id="d793b-147">IIS Metabase and IIS 6 configuration compatibility</span></span>  
  
        -   <span data-ttu-id="d793b-148">IIS 管理控制台</span><span class="sxs-lookup"><span data-stu-id="d793b-148">IIS Management Console</span></span>  
  
    -   <span data-ttu-id="d793b-149">**万维网服务**：展开“安全性”，还需检查：</span><span class="sxs-lookup"><span data-stu-id="d793b-149">**World Wide Web Services**: Expand **Security** and also check:</span></span>  
  
        -   <span data-ttu-id="d793b-150">基本身份验证</span><span class="sxs-lookup"><span data-stu-id="d793b-150">Basic Authentication</span></span>  
  
        -   <span data-ttu-id="d793b-151">Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="d793b-151">Windows Authentication</span></span>  
  
4.  <span data-ttu-id="d793b-152">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="d793b-152">Click **OK**.</span></span> <span data-ttu-id="d793b-153">完成时，单击“关闭”。</span><span class="sxs-lookup"><span data-stu-id="d793b-153">When complete, click **Close**.</span></span>  
  
 <span data-ttu-id="d793b-154">[http://go.microsoft.com/fwlink/p/?LinkID=291297](http://go.microsoft.com/fwlink/p/?LinkID=291297) 还列出了在 Windows 8 上启用 IIS 的步骤。</span><span class="sxs-lookup"><span data-stu-id="d793b-154">[http://go.microsoft.com/fwlink/p/?LinkID=291297](http://go.microsoft.com/fwlink/p/?LinkID=291297) also lists the steps to enable IIS on Windows 8.</span></span>  
  
#### <a name="install-iis-80-on-windows-server-2012"></a><span data-ttu-id="d793b-155">在 Windows Server 2012 上安装 IIS 8.0</span><span class="sxs-lookup"><span data-stu-id="d793b-155">Install IIS 8.0 on Windows Server 2012</span></span>  
  
1.  <span data-ttu-id="d793b-156">打开“服务器管理器”，然后单击左侧窗格中的“仪表板”。</span><span class="sxs-lookup"><span data-stu-id="d793b-156">Open **Server Manager** and click **Dashboard** in the left pane.</span></span>  
  
2.  <span data-ttu-id="d793b-157">单击“添加角色和功能”。</span><span class="sxs-lookup"><span data-stu-id="d793b-157">Click **Add roles and features**.</span></span> <span data-ttu-id="d793b-158">也可从右上角的“管理”菜单打开“添加角色和功能”。</span><span class="sxs-lookup"><span data-stu-id="d793b-158">**Add Roles and Features** can also be opened from the **Manage** menu in the top right-hand corner.</span></span>  
  
3.  <span data-ttu-id="d793b-159">在“开始之前”窗口上，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="d793b-159">On the **Before You Begin** window, click **Next**.</span></span>  
  
4.  <span data-ttu-id="d793b-160">在“安装类型”窗口上，单击“基于角色或基于功能的安装”，再单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="d793b-160">On the **Installation Type** window, click **Role-based or feature-based installation**, and click **Next**.</span></span>  
  
5.  <span data-ttu-id="d793b-161">在“服务器选择” 窗口上，依次单击“从服务器池中选择服务器”、所需的服务器，然后单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="d793b-161">On the **Server Selection** window, click **Select a server from the server pool**, click the desired server, and click **Next**.</span></span>  
  
     <span data-ttu-id="d793b-162">“服务器选择”窗口中会列出“服务器管理器”中使用“添加服务器”添加的服务器。</span><span class="sxs-lookup"><span data-stu-id="d793b-162">The **Server Selection** window lists the servers that have been added using **Add Server** in **Server Manager**.</span></span> <span data-ttu-id="d793b-163">默认情况下，本地服务器处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="d793b-163">By default, it selects the local server.</span></span> <span data-ttu-id="d793b-164">[将服务器添加到服务器管理器](http://go.microsoft.com/fwlink/p/?LinkID=241353)中列出了在 [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] 上使用“添加服务器”的步骤。</span><span class="sxs-lookup"><span data-stu-id="d793b-164">[Add Servers to Server Manager](http://go.microsoft.com/fwlink/p/?LinkID=241353) lists the steps to use **Add Server** on [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)].</span></span>  
  
6.  <span data-ttu-id="d793b-165">在“服务器角色”窗口上，单击“Web 服务器(IIS)”。</span><span class="sxs-lookup"><span data-stu-id="d793b-165">On the **Server Roles** window, click **Web Server (IIS)**.</span></span> <span data-ttu-id="d793b-166">如果系统提示，单击“添加功能”，然后单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="d793b-166">If prompted, click **Add Features**, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="d793b-167">在“功能”窗口上，保留启用的默认选项，同时考虑以下选项：</span><span class="sxs-lookup"><span data-stu-id="d793b-167">On the **Features** window, keep the default options enabled and also consider the following:</span></span>  
  
     <span data-ttu-id="d793b-168">**.Net Framework 3.5 Features**：[!INCLUDE[dotnet45](../includes/dotnet45-md.md)] 和 [!INCLUDE[btsDotNetFramework3.5](../includes/btsdotnetframework3-5-md.md)] 可用于开发包含 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] 的 .Net 应用程序。</span><span class="sxs-lookup"><span data-stu-id="d793b-168">**.Net Framework 3.5 Features**: [!INCLUDE[dotnet45](../includes/dotnet45-md.md)] and [!INCLUDE[btsDotNetFramework3.5](../includes/btsdotnetframework3-5-md.md)] can be used to develop .Net applications involving the [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="d793b-169">通常，“[!INCLUDE[dotnet45](../includes/dotnet45-md.md)] 功能”已经安装。</span><span class="sxs-lookup"><span data-stu-id="d793b-169">Typically, **[!INCLUDE[dotnet45](../includes/dotnet45-md.md)] Features** is already installed.</span></span> <span data-ttu-id="d793b-170">如果将使用 [!INCLUDE[btsDotNetFramework3.5](../includes/btsdotnetframework3-5-md.md)] 在此计算机上创建应用程序，也可以安装 **.Net Framework 3.5 功能**。</span><span class="sxs-lookup"><span data-stu-id="d793b-170">If you will use [!INCLUDE[btsDotNetFramework3.5](../includes/btsdotnetframework3-5-md.md)] to create applications on this computer, then **.Net Framework 3.5 Features** can also be installed.</span></span>  
  
     <span data-ttu-id="d793b-171">**消息队列**：如果使用 MSMQ 适配器，可以通过选中“消息队列”创建本地 MSMQ 存储。</span><span class="sxs-lookup"><span data-stu-id="d793b-171">**Message Queuing**: If you are using the MSMQ adapter, you can create a local MSMQ store by checking **Message Queuing**.</span></span>  
  
     <span data-ttu-id="d793b-172">**SMTP 服务器**：如果使用 SMTP 适配器，可以通过选中“SMTP 服务器”创建本地 SMTP 服务器。</span><span class="sxs-lookup"><span data-stu-id="d793b-172">**SMTP Server**: If you are using the SMTP adapter, you can create a local SMTP Server by checking **SMTP Server**.</span></span>  
  
     <span data-ttu-id="d793b-173">**Windows Identity Foundation 3.5**：使用 CSOM 安装选项时，[!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] 适配器需要 Windows Identity Foundation (WIF)。</span><span class="sxs-lookup"><span data-stu-id="d793b-173">**Windows Identity Foundation 3.5**: Windows Identity Foundation (WIF) is required by the [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] adapter when using the CSOM installation option.</span></span> <span data-ttu-id="d793b-174">[附录 B：安装 Microsoft SharePoint 适配器](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) 描述了 [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] 适配器的 CSOM 安装选项。</span><span class="sxs-lookup"><span data-stu-id="d793b-174">[Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) describes the CSOM installation option for the [!INCLUDE[btsWinSharePointSvcsNoVersion](../includes/btswinsharepointsvcsnoversion-md.md)] adapter.</span></span>  
  
     <span data-ttu-id="d793b-175">单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="d793b-175">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="d793b-176">在“Web 服务器角色(IIS)”窗口上，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="d793b-176">On the **Web Server Role (IIS)** window, click **Next**.</span></span>  
  
9. <span data-ttu-id="d793b-177">在“角色服务”窗口上（位于“Web 服务器角色(IIS)”下），单击以下选项：</span><span class="sxs-lookup"><span data-stu-id="d793b-177">On the **Role Services** window (under **Web Server Role (IIS)**), click the following options:</span></span>  
  
     <span data-ttu-id="d793b-178">**安全**：除了默认选项之外，还应单击：</span><span class="sxs-lookup"><span data-stu-id="d793b-178">**Security**: In addition to the default options, also click:</span></span>  
  
    -   <span data-ttu-id="d793b-179">基本身份验证</span><span class="sxs-lookup"><span data-stu-id="d793b-179">Basic Authentication</span></span>  
  
    -   <span data-ttu-id="d793b-180">Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="d793b-180">Windows Authentication</span></span>  
  
     <span data-ttu-id="d793b-181">**应用程序开发**：默认选项足够满足 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的需求。</span><span class="sxs-lookup"><span data-stu-id="d793b-181">**Application Development**: The default options are sufficient for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="d793b-182">如果此计算机上还承载了其他基于 IIS 的应用程序，请选中所需的角色。</span><span class="sxs-lookup"><span data-stu-id="d793b-182">If you host other IIS-based applications on this computer, check the needed roles.</span></span>  
  
     <span data-ttu-id="d793b-183">**管理工具**：除了默认选项之外，还应单击：</span><span class="sxs-lookup"><span data-stu-id="d793b-183">**Management Tools**: In addition to the default options, also click:</span></span>  
  
    -   <span data-ttu-id="d793b-184">IIS 管理控制台</span><span class="sxs-lookup"><span data-stu-id="d793b-184">IIS Management Console</span></span>  
  
    -   <span data-ttu-id="d793b-185">IIS 6 管理兼容性：</span><span class="sxs-lookup"><span data-stu-id="d793b-185">IIS 6 Management Compatibility:</span></span>  
  
        -   <span data-ttu-id="d793b-186">IIS 6 元数据库兼容性</span><span class="sxs-lookup"><span data-stu-id="d793b-186">IIS 6 Metabase Compatibility</span></span>  
  
        -   <span data-ttu-id="d793b-187">IIS 6 管理控制台</span><span class="sxs-lookup"><span data-stu-id="d793b-187">IIS 6 Management Console</span></span>  
  
     <span data-ttu-id="d793b-188">单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="d793b-188">Click **Next**.</span></span>  
  
10. <span data-ttu-id="d793b-189">在“确认”窗口上，单击“安装”。</span><span class="sxs-lookup"><span data-stu-id="d793b-189">On the **Confirmation** window, click **Install**.</span></span> <span data-ttu-id="d793b-190">完成时，单击“关闭”。</span><span class="sxs-lookup"><span data-stu-id="d793b-190">When complete, click **Close**.</span></span>  
  
 <span data-ttu-id="d793b-191">[http://go.microsoft.com/fwlink/p/?LinkID=291297](http://go.microsoft.com/fwlink/p/?LinkID=291297) 还列出了在 [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] 上启用 IIS 的步骤。</span><span class="sxs-lookup"><span data-stu-id="d793b-191">[http://go.microsoft.com/fwlink/p/?LinkID=291297](http://go.microsoft.com/fwlink/p/?LinkID=291297) also lists the steps to enable IIS on [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)].</span></span>  
  
##  <a name="BKMK_XLS"></a> <span data-ttu-id="d793b-192">安装 Microsoft Office Excel</span><span class="sxs-lookup"><span data-stu-id="d793b-192">Install Microsoft Office Excel</span></span>  
  
1.  <span data-ttu-id="d793b-193">运行 Microsoft Office 安装程序。</span><span class="sxs-lookup"><span data-stu-id="d793b-193">Run the Microsoft Office setup.</span></span>  
  
2.  <span data-ttu-id="d793b-194">显示“安装类型”屏幕时，选择“自定义安装”，然后选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="d793b-194">When you reach the **Type of Installation** screen, select **Custom Install**, and then select **Next**.</span></span>  
  
3.  <span data-ttu-id="d793b-195">在“自定义安装”屏幕上，选择“Excel”，然后选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="d793b-195">On the **Custom Setup** screen, select **Excel**, and then select **Next**.</span></span>  
  
4.  <span data-ttu-id="d793b-196">选择“安装”。</span><span class="sxs-lookup"><span data-stu-id="d793b-196">Select **Install**.</span></span>  
  
5.  <span data-ttu-id="d793b-197">在“已完成安装”中，选择“完成”。</span><span class="sxs-lookup"><span data-stu-id="d793b-197">In **Setup Completed**, select **Finish**.</span></span>  
  
 <span data-ttu-id="d793b-198">**补充说明**</span><span class="sxs-lookup"><span data-stu-id="d793b-198">**Additional**</span></span>  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="d793b-199"> 仅支持 32 位版本的 Microsoft Office。</span><span class="sxs-lookup"><span data-stu-id="d793b-199"> supports only 32-bit version of Microsoft Office.</span></span>  
  
-   <span data-ttu-id="d793b-200">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中的业务活动监视 (BAM) 需要 Microsoft Office Excel。</span><span class="sxs-lookup"><span data-stu-id="d793b-200">Microsoft Office Excel is required by Business Activity Monitoring (BAM) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="d793b-201">可以使用 BAM Office Excel 工作簿来定义要监视的业务流程。</span><span class="sxs-lookup"><span data-stu-id="d793b-201">The BAM Office Excel Workbook defines the business processes you want to monitor.</span></span> <span data-ttu-id="d793b-202">还可以使用 BAM Excel 工作簿定义业务用户查看 BAM 所收集的数据的方式。</span><span class="sxs-lookup"><span data-stu-id="d793b-202">You also use the BAM Excel Workbook to define the way business users see the data collected by BAM.</span></span>  
  
-   <span data-ttu-id="d793b-203">若要成功将 BAM.xla 加载到 Excel 中，请在“Office 共享功能”下安装“Visual Basic for Applications”。</span><span class="sxs-lookup"><span data-stu-id="d793b-203">To successfully load BAM.xla into Excel, install **Visual Basic for Applications** under **Office Shared Features**.</span></span> <span data-ttu-id="d793b-204">否则，可能会收到“此工作簿已丢失了其 VBA 项目、ActiveX 控件以及其他任何与可编程性相关的功能”错误。</span><span class="sxs-lookup"><span data-stu-id="d793b-204">Otherwise, you may get error “This workbook has lost its VBA project, ActiveX controls and any other programmability-related features.”</span></span>  
  
##  <a name="BKMK_VS"></a> <span data-ttu-id="d793b-205">安装 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d793b-205">Install Visual Studio</span></span>  
  
1.  <span data-ttu-id="d793b-206">以管理员身份运行 Visual Studio 安装程序。</span><span class="sxs-lookup"><span data-stu-id="d793b-206">Run the Visual Studio setup as Administrator.</span></span>  
  
2.  <span data-ttu-id="d793b-207">接受许可协议，然后单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="d793b-207">Accept the license agreement and click **Next**.</span></span>  
  
3.  <span data-ttu-id="d793b-208">在“要安装的可选功能”中，选择所需的选项，然后选择“安装”。</span><span class="sxs-lookup"><span data-stu-id="d793b-208">In **Optional features to install**, select the options you need and then select **Install**.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="d793b-209"> 不需要任何可选功能。</span><span class="sxs-lookup"><span data-stu-id="d793b-209"> does not require any of the optional features.</span></span>  
  
4.  <span data-ttu-id="d793b-210">在“完成”页面上，关闭窗口或单击“启动”打开 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="d793b-210">On the **Finish** page, close the window or click **Launch** to open Visual Studio.</span></span>  
  
 <span data-ttu-id="d793b-211">**补充说明**</span><span class="sxs-lookup"><span data-stu-id="d793b-211">**Additional**</span></span>  
  
-   <span data-ttu-id="d793b-212">如果安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 之前安装 Visual Studio，然后升级到 Visual Studio Team Explorer，可能需要通过“控制面板” / “程序”选项对 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 安装进行修复。</span><span class="sxs-lookup"><span data-stu-id="d793b-212">If you install Visual Studio before installing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and then upgrade to Visual Studio Team Explorer, you may need to repair your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation from the **Control Panel** / **Programs** option.</span></span>  
  
-   <span data-ttu-id="d793b-213">Visual Studio 会自动安装 Microsoft SQL Server Express；[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 并不使用。</span><span class="sxs-lookup"><span data-stu-id="d793b-213">Visual Studio automatically installs Microsoft SQL Server Express; which is not used by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="d793b-214">最好卸载 Microsoft SQL Server Express。</span><span class="sxs-lookup"><span data-stu-id="d793b-214">As a best practice, uninstall Microsoft SQL Server Express.</span></span>  
  
-   <span data-ttu-id="d793b-215">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 开发工具基于 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="d793b-215">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] development tools are based on Visual Studio.</span></span> <span data-ttu-id="d793b-216">在安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**开发人员工具和 SDK** 之前，至少必须安装 Visual Studio 的 Microsoft Visual C#® .NET 组件。</span><span class="sxs-lookup"><span data-stu-id="d793b-216">At a minimum, you must install the Microsoft Visual C#® .NET component of Visual Studio before you install the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**Developer Tools and SDK**.</span></span>  
  
-   <span data-ttu-id="d793b-217">如果要在不需要进行任何应用程序开发或调试的生产计算机（仅限运行时）上安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，则不需要 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="d793b-217">Visual Studio is *not* required if you are installing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] on a production computer (runtime only), on which no application development or debugging is required.</span></span>  
  
-   <span data-ttu-id="d793b-218">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 运行时需要 [!INCLUDE[dotnet45](../includes/dotnet45-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d793b-218">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime requires [!INCLUDE[dotnet45](../includes/dotnet45-md.md)].</span></span> <span data-ttu-id="d793b-219">如果已安装 Windows Communication Foundation (WCF) 适配器或 WCF 侦听器，则需要安装 .NET Framework 3.0。</span><span class="sxs-lookup"><span data-stu-id="d793b-219">The .NET Framework 3.0 is required if the Windows Communication Foundation (WCF) adapter or WCF Interceptor is installed.</span></span>  
  
##  <a name="BKMK_SQL"></a> <span data-ttu-id="d793b-220">安装 SQL Server</span><span class="sxs-lookup"><span data-stu-id="d793b-220">Install SQL Server</span></span>  
 <span data-ttu-id="d793b-221">安装 [SQL Server 2008 R2](http://msdn.microsoft.com/library/bb500395\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="d793b-221">Install [SQL Server 2008 R2](http://msdn.microsoft.com/library/bb500395\(v=sql.105\).aspx)</span></span>  
  
 <span data-ttu-id="d793b-222">安装 [SQL Server 2012](http://msdn.microsoft.com/library/bb500469\(v=sql.110\).aspx)</span><span class="sxs-lookup"><span data-stu-id="d793b-222">Install [SQL Server 2012](http://msdn.microsoft.com/library/bb500469\(v=sql.110\).aspx)</span></span>  
  
 <span data-ttu-id="d793b-223">安装 [SQL Server 2014](http://msdn.microsoft.com/library/bb500469\(v=sql.120\).aspx)</span><span class="sxs-lookup"><span data-stu-id="d793b-223">Install [SQL Server 2014](http://msdn.microsoft.com/library/bb500469\(v=sql.120\).aspx)</span></span>  
  
 <span data-ttu-id="d793b-224">当你安装 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 时，请选择以下功能：</span><span class="sxs-lookup"><span data-stu-id="d793b-224">When you install [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)], select the following features:</span></span>  
  
-   <span data-ttu-id="d793b-225">数据库引擎服务</span><span class="sxs-lookup"><span data-stu-id="d793b-225">Database Engine Services</span></span>  
  
    -   <span data-ttu-id="d793b-226">SQL Server 复制</span><span class="sxs-lookup"><span data-stu-id="d793b-226">SQL Server Replication</span></span>  
  
    -   <span data-ttu-id="d793b-227">全文搜索</span><span class="sxs-lookup"><span data-stu-id="d793b-227">Full-Text Search</span></span>  
  
-   <span data-ttu-id="d793b-228">Analysis Services</span><span class="sxs-lookup"><span data-stu-id="d793b-228">Analysis Services</span></span>  
  
-   <span data-ttu-id="d793b-229">Reporting Services</span><span class="sxs-lookup"><span data-stu-id="d793b-229">Reporting Services</span></span>  
  
-   <span data-ttu-id="d793b-230">共享功能</span><span class="sxs-lookup"><span data-stu-id="d793b-230">Shared Features</span></span>  
  
    -   <span data-ttu-id="d793b-231">SQL Server Data Tools (SQL Server 2014/SQL Server 2012) 或 Business Intelligence Development Studio (SQL Server 2008 R2)</span><span class="sxs-lookup"><span data-stu-id="d793b-231">SQL Server Data Tools (SQL Server 2014 / SQL Server 2012) or Business Intelligence Development Studio (SQL Server 2008 R2)</span></span>  
  
         [<span data-ttu-id="d793b-232">下载 SQL Server 2014 Data Tools</span><span class="sxs-lookup"><span data-stu-id="d793b-232">Download SQL Server 2014 Data Tools</span></span>](http://www.microsoft.com/download/details.aspx?id=42313)  
  
    -   <span data-ttu-id="d793b-233">客户端工具连接</span><span class="sxs-lookup"><span data-stu-id="d793b-233">Client Tools Connectivity</span></span>  
  
    -   <span data-ttu-id="d793b-234">Integration Services</span><span class="sxs-lookup"><span data-stu-id="d793b-234">Integration Services</span></span>  
  
    -   <span data-ttu-id="d793b-235">管理工具 - 基本</span><span class="sxs-lookup"><span data-stu-id="d793b-235">Management Tools - Basic</span></span>  
  
        -   <span data-ttu-id="d793b-236">管理工具 - 完整</span><span class="sxs-lookup"><span data-stu-id="d793b-236">Management Tools - Complete</span></span>  
  
 <span data-ttu-id="d793b-237">**补充说明**</span><span class="sxs-lookup"><span data-stu-id="d793b-237">**Additional**</span></span>  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="d793b-238"> 支持所有区分大小写和不区分大小写的 SQL Server 排序规则，二进制排序规则例外。</span><span class="sxs-lookup"><span data-stu-id="d793b-238"> supports all case-sensitive and case-insensitive SQL Server collations except for binary collations.</span></span> <span data-ttu-id="d793b-239">不支持二进制排序规则。</span><span class="sxs-lookup"><span data-stu-id="d793b-239">Binary collations are not supported.</span></span>  
  
-   <span data-ttu-id="d793b-240">为了获得最佳性能，Microsoft 建议使用 SQL Server Enterprise Edition。</span><span class="sxs-lookup"><span data-stu-id="d793b-240">For optimal performance, Microsoft recommends using the Enterprise Edition of SQL Server.</span></span> <span data-ttu-id="d793b-241">请参阅 [SQL Server 2008 R2 版本](http://msdn.microsoft.com/library/cc645993\(v=sql.105\).aspx)、[SQL Server 2012 版本](http://msdn.microsoft.com/library/cc645993\(v=sql.110\).aspx)或 [SQL Server 2014 版本](http://msdn.microsoft.com/library/cc645993\(v=sql.120\).aspx)。</span><span class="sxs-lookup"><span data-stu-id="d793b-241">See [SQL Server 2008 R2 Editions](http://msdn.microsoft.com/library/cc645993\(v=sql.105\).aspx), [SQL Server 2012 Editions](http://msdn.microsoft.com/library/cc645993\(v=sql.110\).aspx), or [SQL Server 2014 Editions](http://msdn.microsoft.com/library/cc645993\(v=sql.120\).aspx).</span></span>  
  
-   <span data-ttu-id="d793b-242">支持 Service Pack 和 Windows Update，并且应进行安装。</span><span class="sxs-lookup"><span data-stu-id="d793b-242">Service packs and Windows Updates are supported and should be installed.</span></span>  
  
-   <span data-ttu-id="d793b-243">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 和 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 位于单独的计算机上时，分布式事务协调器 (MS DTC) 处理计算机之间的事务。</span><span class="sxs-lookup"><span data-stu-id="d793b-243">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] are on separate computers, Distributed Transaction Coordinator (MS DTC) handles the transactions between the computers.</span></span> <span data-ttu-id="d793b-244">[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] AlwaysOn 功能不支持 MSDTC 事务。</span><span class="sxs-lookup"><span data-stu-id="d793b-244">The [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] AlwaysOn feature does not support MSDTC transactions.</span></span> <span data-ttu-id="d793b-245">不支持 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] AlwaysOn 功能。</span><span class="sxs-lookup"><span data-stu-id="d793b-245">The [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] AlwaysOn feature is not supported.</span></span>  
  
##  <a name="BKMK_MQSeries"></a> <span data-ttu-id="d793b-246">安装 MQSeries 必备组件</span><span class="sxs-lookup"><span data-stu-id="d793b-246">Install MQSeries Prerequisites</span></span>  
 <span data-ttu-id="d793b-247">**MQSeries 适配器**：自动随 BizTalk Server 一起安装。</span><span class="sxs-lookup"><span data-stu-id="d793b-247">**MQSeries adapter**: Automatically installed with the BizTalk Server installation.</span></span>  
  
 <span data-ttu-id="d793b-248">**MQSeries 客户端 (MQSC) 适配器**：</span><span class="sxs-lookup"><span data-stu-id="d793b-248">**MQSeries Client (MQSC) adapter**:</span></span>  
  
1.  <span data-ttu-id="d793b-249">运行 Host Integration Server (HIS) 安装</span><span class="sxs-lookup"><span data-stu-id="d793b-249">Run the Host Integration Server (HIS) installation</span></span>  
  
2.  <span data-ttu-id="d793b-250">在组件安装中，展开“BizTalk 适配器”。</span><span class="sxs-lookup"><span data-stu-id="d793b-250">In component installation, expand **BizTalk Adapters**.</span></span>  
  
3.  <span data-ttu-id="d793b-251">选择“适用于 WebSphere MQ 的 BizTalk 适配器(基于客户端)”。</span><span class="sxs-lookup"><span data-stu-id="d793b-251">Select **BizTalk Adapter for WebSphere MQ (Client-Based)**.</span></span>  
  
 <span data-ttu-id="d793b-252">**支持的 IBM WebSphere MQ 版本：**：</span><span class="sxs-lookup"><span data-stu-id="d793b-252">**Supported IBM WebSphere MQ versions**:</span></span>  
  
-   <span data-ttu-id="d793b-253">IBM WebSphere MQ 6.0.2.12 和更高版本</span><span class="sxs-lookup"><span data-stu-id="d793b-253">IBM WebSphere MQ 6.0.2.12 and later</span></span>  
  
-   <span data-ttu-id="d793b-254">IBM WebSphere MQ 7.0.1.9 和更高版本</span><span class="sxs-lookup"><span data-stu-id="d793b-254">IBM WebSphere MQ 7.0.1.9 and later</span></span>  
  
-   <span data-ttu-id="d793b-255">IBM WebSphere MQ 7.1.0.5 和更高版本</span><span class="sxs-lookup"><span data-stu-id="d793b-255">IBM WebSphere MQ 7.1.0.5 and later</span></span>  
  
-   <span data-ttu-id="d793b-256">IBM WebSphere MQ 7.5.0.3 和更高版本</span><span class="sxs-lookup"><span data-stu-id="d793b-256">IBM WebSphere MQ 7.5.0.3 and later</span></span>  
  
-   <span data-ttu-id="d793b-257">IBM WebSphere MQ 8（限制为运行时；无管理 API）</span><span class="sxs-lookup"><span data-stu-id="d793b-257">IBM WebSphere MQ 8 (limited to runtime; no administration APIs)</span></span>  
  
     <span data-ttu-id="d793b-258">MQ 版本 8 支持随附在[主机集成服务器累积更新 3](https://support.microsoft.com/kb/3019572)中。</span><span class="sxs-lookup"><span data-stu-id="d793b-258">MQ version 8 support is included with [Host Integration Server CU3](https://support.microsoft.com/kb/3019572).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d793b-259">如果未列出特定的 WebSphere MQ 版本，如 MQ 5.x，则不支持其与此 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 版本一起使用。</span><span class="sxs-lookup"><span data-stu-id="d793b-259">If a specific WebSphere MQ version is not listed, like MQ 5.x, then it is not supported with this [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] version.</span></span>  
  
 <span data-ttu-id="d793b-260">**补充说明**</span><span class="sxs-lookup"><span data-stu-id="d793b-260">**Additional**</span></span>  
  
-   <span data-ttu-id="d793b-261">最佳做法是，始终安装最新的 WebSphere MQ 修补程序包。</span><span class="sxs-lookup"><span data-stu-id="d793b-261">As a best practice, always install the latest WebSphere MQ fix pack.</span></span> <span data-ttu-id="d793b-262">请参阅 [http://www.ibm.com/support/docview.wss?uid=swg27006037](http://www.ibm.com/support/docview.wss?uid=swg27006037)。</span><span class="sxs-lookup"><span data-stu-id="d793b-262">See [http://www.ibm.com/support/docview.wss?uid=swg27006037](http://www.ibm.com/support/docview.wss?uid=swg27006037).</span></span>  
  
-   <span data-ttu-id="d793b-263">如果在非 Windows 计算机上安装 IBM WebSphere MQ，可将 **MQSAgent COM+ 应用程序** (MQSConfigWiz.exe) 和 **MQSeries Server for Windows** 安装在同一台计算机上。</span><span class="sxs-lookup"><span data-stu-id="d793b-263">If IBM WebSphere MQ is installed on a non-Windows computer, install the **MQSAgent COM+ application** (MQSConfigWiz.exe) and **MQSeries Server for Windows** on the same computer.</span></span> <span data-ttu-id="d793b-264">如果在 Windows 计算机上安装 IBM WebSphere MQ，则不使用也不需要 **MQSAgent COM+ 应用程序**和 **MQSeries Server for Windows** 程序。</span><span class="sxs-lookup"><span data-stu-id="d793b-264">If IBM WebSphere MQ is installed on a Windows computer, then the **MQSAgent COM+ application** and **MQSeries Server for Windows** program are not used or needed.</span></span>  
  
     <span data-ttu-id="d793b-265">**MQSConfigWiz.exe** 包含在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 安装文件中。</span><span class="sxs-lookup"><span data-stu-id="d793b-265">**MQSConfigWiz.exe** is included in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation files.</span></span>  
  
     <span data-ttu-id="d793b-266">**MQSeries Server for Windows** 不是 Microsoft 程序，必须通过 IBM WebSphere MQ 程序获得。</span><span class="sxs-lookup"><span data-stu-id="d793b-266">**MQSeries Server for Windows** is not a Microsoft program and must be obtained with your IBM WebSphere MQ program.</span></span>  
  
-   <span data-ttu-id="d793b-267">[MQSeries 适配器](http://technet.microsoft.com/library/aa547973\(v=BTS.80\).aspx)提供了有关 MQSeries 适配器及配置不同组件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d793b-267">[MQSeries Adapter](http://technet.microsoft.com/library/aa547973\(v=BTS.80\).aspx) provides more information on the MQSeries adapter, including configuring the different components.</span></span> <span data-ttu-id="d793b-268">[BizTalk Server：MQSeries 和 MQSeries 客户端 (MQSC) 适配器](http://social.technet.microsoft.com/wiki/contents/articles/18316.biztalk-server-mqseries-and-mqseries-client-mqsc-adapters.aspx)提供了有关 MQSeries 和 MQSC 适配器的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d793b-268">[BizTalk Server: MQSeries and MQSeries Client (MQSC) adapters](http://social.technet.microsoft.com/wiki/contents/articles/18316.biztalk-server-mqseries-and-mqseries-client-mqsc-adapters.aspx) provides additional details on the MQSeries and MQSC adapters.</span></span>  
  
-   <span data-ttu-id="d793b-269">IBM WebSphere 不是 Microsoft 产品，也不受 Microsoft 支持。</span><span class="sxs-lookup"><span data-stu-id="d793b-269">IBM WebSphere is not a Microsoft product and is not supported by Microsoft.</span></span> <span data-ttu-id="d793b-270">Microsoft 不保证此程序的适用性。</span><span class="sxs-lookup"><span data-stu-id="d793b-270">Microsoft makes no guarantees about the suitability of this program.</span></span> <span data-ttu-id="d793b-271">有关 IBM WebSphere MQ 的详细信息，请参阅 www.ibm.com。</span><span class="sxs-lookup"><span data-stu-id="d793b-271">For more information about IBM WebSphere MQ, including download instructions, see www.ibm.com.</span></span>  
  
##  <a name="BKMK_BAMAlerts"></a> <span data-ttu-id="d793b-272">BAM 警报</span><span class="sxs-lookup"><span data-stu-id="d793b-272">BAM Alerts</span></span>  
 <span data-ttu-id="d793b-273">[!INCLUDE[sqlserver2014](../includes/sqlserver2014-md.md)] 或 [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)] 的 BAM 警报使用 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 的数据库邮件功能。</span><span class="sxs-lookup"><span data-stu-id="d793b-273">BAM Alerts with [!INCLUDE[sqlserver2014](../includes/sqlserver2014-md.md)] or [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)] uses Database Mail in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span> <span data-ttu-id="d793b-274">[!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] 的 BAM 警报使用 SQL Notification Services。</span><span class="sxs-lookup"><span data-stu-id="d793b-274">BAM Alerts with [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] uses SQL Notification Services.</span></span> <span data-ttu-id="d793b-275">在安装或配置 BAM 警报之前，你必须先在 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 中配置 Notification Services 或数据库邮件功能。</span><span class="sxs-lookup"><span data-stu-id="d793b-275">Before installing or configuring BAM Alerts, you must configure the Notification Services or Database Mail in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)].</span></span>  
  
###  <a name="BKMK_DBMail"></a> <span data-ttu-id="d793b-276">使用 SQL Server 2012/2014 的 BAM 警报</span><span class="sxs-lookup"><span data-stu-id="d793b-276">BAM Alerts using SQL Server 2012/2014</span></span>  
 <span data-ttu-id="d793b-277">配置 [SQL Server 2012 数据库邮件](http://msdn.microsoft.com/library/hh245116\(v=sql.110\).aspx)。</span><span class="sxs-lookup"><span data-stu-id="d793b-277">Configure [SQL Server 2012 Database Mail](http://msdn.microsoft.com/library/hh245116\(v=sql.110\).aspx).</span></span>  
  
 <span data-ttu-id="d793b-278">配置 [SQL Server 2014 数据库邮件](http://msdn.microsoft.com/library/hh245116\(v=sql.120\).aspx)。</span><span class="sxs-lookup"><span data-stu-id="d793b-278">Configure [SQL Server 2014 Database Mail](http://msdn.microsoft.com/library/hh245116\(v=sql.120\).aspx).</span></span>  
  
 <span data-ttu-id="d793b-279">**补充说明**</span><span class="sxs-lookup"><span data-stu-id="d793b-279">**Additional**</span></span>  
  
-   <span data-ttu-id="d793b-280">数据库邮件使用 SMTP 服务器发送 BAM 警报。</span><span class="sxs-lookup"><span data-stu-id="d793b-280">Database Mail uses an SMTP server to send the BAM Alerts.</span></span> <span data-ttu-id="d793b-281">SMTP 服务器可以本地安装在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 上，也可以安装在其他 IIS 服务器上。</span><span class="sxs-lookup"><span data-stu-id="d793b-281">SMTP Server can be installed locally on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or on another IIS server.</span></span> <span data-ttu-id="d793b-282">[附录 D：创建 SMTP 服务器](../install-and-config-guides/appendix-d-create-the-smtp-server.md)中列出了安装和配置 SMTP 服务器的步骤。</span><span class="sxs-lookup"><span data-stu-id="d793b-282">[Appendix D: Create the SMTP Server](../install-and-config-guides/appendix-d-create-the-smtp-server.md) lists the steps to install and configure a SMTP Server.</span></span>  
  
###  <a name="BKMK_SSNS"></a> <span data-ttu-id="d793b-283">使用 SQL Server 2008 R2 的 BAM 警报 – 安装 SQL Server 2005 Notification Services</span><span class="sxs-lookup"><span data-stu-id="d793b-283">BAM Alerts using SQL Server 2008 R2 – Install SQL Server 2005 Notification Services</span></span>  
  
1.  <span data-ttu-id="d793b-284">转到 [SQL Server 2005 SP4 功能包](http://go.microsoft.com/fwlink/p/?LinkId=286285)。</span><span class="sxs-lookup"><span data-stu-id="d793b-284">Go to [Feature Pack for Microsoft SQL Server 2005 SP4](http://go.microsoft.com/fwlink/p/?LinkId=286285).</span></span>  
  
2.  <span data-ttu-id="d793b-285">下载并安装以下组件的相应平台包：</span><span class="sxs-lookup"><span data-stu-id="d793b-285">Download and install the appropriate platform package for the following components:</span></span>  
  
     <span data-ttu-id="d793b-286">**Microsoft SQL Server Native Client**</span><span class="sxs-lookup"><span data-stu-id="d793b-286">**Microsoft SQL Server Native Client**</span></span>  
  
    -   <span data-ttu-id="d793b-287">HYPERLINK "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/sqlncli.msi" X86 Package (sqlncli.msi)</span><span class="sxs-lookup"><span data-stu-id="d793b-287">HYPERLINK "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/sqlncli.msi" X86 Package (sqlncli.msi)</span></span>  
  
    -   <span data-ttu-id="d793b-288">HYPERLINK "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/sqlncli_x64.msi" X64 Package (sqlncli_x64.msi)</span><span class="sxs-lookup"><span data-stu-id="d793b-288">HYPERLINK "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/sqlncli_x64.msi" X64 Package (sqlncli_x64.msi)</span></span>  
  
     <span data-ttu-id="d793b-289">**Microsoft SQL Server 2005 管理对象集合**</span><span class="sxs-lookup"><span data-stu-id="d793b-289">**Microsoft SQL Server 2005 Management Objects Collection**</span></span>  
  
    -   <span data-ttu-id="d793b-290">HYPERLINK "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_XMO.msi" X86 Package (SQLServer2005_XMO.msi)</span><span class="sxs-lookup"><span data-stu-id="d793b-290">HYPERLINK "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_XMO.msi" X86 Package (SQLServer2005_XMO.msi)</span></span>  
  
    -   <span data-ttu-id="d793b-291">HYPERLINK "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_XMO_x64.msi" X64 Package (SQLServer2005_XMO_x64.msi)</span><span class="sxs-lookup"><span data-stu-id="d793b-291">HYPERLINK "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_XMO_x64.msi" X64 Package (SQLServer2005_XMO_x64.msi)</span></span>  
  
     <span data-ttu-id="d793b-292">**Microsoft SQL Server 2005 Notification Services 客户端组件**</span><span class="sxs-lookup"><span data-stu-id="d793b-292">**Microsoft SQL Server 2005 Notification Services Client Components**</span></span>  
  
    -   <span data-ttu-id="d793b-293">HYPERLINK "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_NS.msi" X86 Package (SQLServer2005_NS.msi)</span><span class="sxs-lookup"><span data-stu-id="d793b-293">HYPERLINK "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_NS.msi" X86 Package (SQLServer2005_NS.msi)</span></span>  
  
    -   <span data-ttu-id="d793b-294">HYPERLINK "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_NS_x64.msi" X64 Package (SQLServer2005_NS_x64.msi)</span><span class="sxs-lookup"><span data-stu-id="d793b-294">HYPERLINK "http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_NS_x64.msi" X64 Package (SQLServer2005_NS_x64.msi)</span></span>  
  
 <span data-ttu-id="d793b-295">**补充说明**</span><span class="sxs-lookup"><span data-stu-id="d793b-295">**Additional**</span></span>  
  
-   <span data-ttu-id="d793b-296">不需要配置 SQL Notification Services；只需将其安装在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 上。</span><span class="sxs-lookup"><span data-stu-id="d793b-296">SQL Notification Services does not need to be configured; only installed on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
##  <a name="BKMK_WIF"></a> <span data-ttu-id="d793b-297">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="d793b-297">Windows Identity Foundation</span></span>  
  
|||  
|-|-|  
|[!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)]<span data-ttu-id="d793b-298"> 8.1、[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] 和 [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] R2</span><span class="sxs-lookup"><span data-stu-id="d793b-298"> 8.1, [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)], and [!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)] R2</span></span>|<span data-ttu-id="d793b-299">Windows Identity Foundation 作为“打开或关闭 Windows 功能”中的功能包括在操作系统中。</span><span class="sxs-lookup"><span data-stu-id="d793b-299">Windows Identity Foundation is included with the operating system as a Feature in **Turn Windows features on or off**.</span></span>|  
|[!INCLUDE[btsWinVista](../includes/btswinvista-md.md)]<span data-ttu-id="d793b-300"> SP1</span><span class="sxs-lookup"><span data-stu-id="d793b-300"> SP1</span></span>|<span data-ttu-id="d793b-301">可在下面的地址下载[Windows Identity Foundation](http://www.microsoft.com/download/details.aspx?id=17331) HYPERLINK "http://www.microsoft.com/download/details.aspx?id=17331"。</span><span class="sxs-lookup"><span data-stu-id="d793b-301">Download available at [Windows Identity Foundation](http://www.microsoft.com/download/details.aspx?id=17331) HYPERLINK "http://www.microsoft.com/download/details.aspx?id=17331" .</span></span>|  
  
 <span data-ttu-id="d793b-302">**补充说明**</span><span class="sxs-lookup"><span data-stu-id="d793b-302">**Additional**</span></span>  
  
-   <span data-ttu-id="d793b-303">在与 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 客户端对象模型 (CSOM) 结合使用时，[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 适配器或 SharePoint Online 需要 Windows Identity Foundation (WIF)。</span><span class="sxs-lookup"><span data-stu-id="d793b-303">Windows Identity Foundation (WIF) is required for the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] adapter or SharePoint Online when used with [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Client Side Object Model (CSOM).</span></span> <span data-ttu-id="d793b-304">具体来说：</span><span class="sxs-lookup"><span data-stu-id="d793b-304">Specifically:</span></span>  
  
    |<span data-ttu-id="d793b-305">安装选项</span><span class="sxs-lookup"><span data-stu-id="d793b-305">Installation Option</span></span>|<span data-ttu-id="d793b-306">需要 WIF</span><span class="sxs-lookup"><span data-stu-id="d793b-306">WIF Required</span></span>|  
    |-------------------------|------------------|  
    |<span data-ttu-id="d793b-307">使用 CSOM 的 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 适配器</span><span class="sxs-lookup"><span data-stu-id="d793b-307">[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] Adapter with CSOM</span></span>|<span data-ttu-id="d793b-308">是</span><span class="sxs-lookup"><span data-stu-id="d793b-308">Yes</span></span>|  
    |<span data-ttu-id="d793b-309">使用 CSOM 的 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="d793b-309">SharePoint Online with CSOM</span></span>|<span data-ttu-id="d793b-310">是</span><span class="sxs-lookup"><span data-stu-id="d793b-310">Yes</span></span>|  
    |[!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)]<span data-ttu-id="d793b-311"> 适配器 Web Service（不赞成使用）</span><span class="sxs-lookup"><span data-stu-id="d793b-311"> Adapter Web Service (deprecated)</span></span>|<span data-ttu-id="d793b-312">是</span><span class="sxs-lookup"><span data-stu-id="d793b-312">No</span></span>|  
    |<span data-ttu-id="d793b-313">无 SharePoint</span><span class="sxs-lookup"><span data-stu-id="d793b-313">No SharePoint</span></span>|<span data-ttu-id="d793b-314">是</span><span class="sxs-lookup"><span data-stu-id="d793b-314">No</span></span>|  
  
-   <span data-ttu-id="d793b-315">[附录 B：安装 Microsoft SharePoint 适配器](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)提供了有关 [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] 安装选项的特殊信息。</span><span class="sxs-lookup"><span data-stu-id="d793b-315">[Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) provides specific information on the [!INCLUDE[btsSharePointSvcsNoVersion](../includes/btssharepointsvcsnoversion-md.md)] installation options.</span></span>  
  
##  <a name="BKMK_WSS"></a> <span data-ttu-id="d793b-316">安装和配置 Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="d793b-316">Install and Configure Microsoft SharePoint</span></span>  
 <span data-ttu-id="d793b-317">安装 [SharePoint 2013](http://technet.microsoft.com/library/cc303424.aspx)</span><span class="sxs-lookup"><span data-stu-id="d793b-317">Install [SharePoint 2013](http://technet.microsoft.com/library/cc303424.aspx)</span></span>  
  
 <span data-ttu-id="d793b-318">安装 [SharePoint Online 服务](http://technet.microsoft.com/library/jj819267.aspx)</span><span class="sxs-lookup"><span data-stu-id="d793b-318">Install [SharePoint Online Service](http://technet.microsoft.com/library/jj819267.aspx)</span></span>  
  
 <span data-ttu-id="d793b-319">安装 [SharePoint Server 2010](http://technet.microsoft.com/library/cc303424\(v=office.14\).aspx)</span><span class="sxs-lookup"><span data-stu-id="d793b-319">Install [SharePoint Server 2010](http://technet.microsoft.com/library/cc303424\(v=office.14\).aspx)</span></span>  
  
 <span data-ttu-id="d793b-320">安装 [SharePoint 2007](http://technet.microsoft.com/library/cc303424\(v=office.12\).aspx)</span><span class="sxs-lookup"><span data-stu-id="d793b-320">Install [SharePoint 2007](http://technet.microsoft.com/library/cc303424\(v=office.12\).aspx)</span></span>  
  
 <span data-ttu-id="d793b-321">**补充说明**</span><span class="sxs-lookup"><span data-stu-id="d793b-321">**Additional**</span></span>  
  
-   <span data-ttu-id="d793b-322">如果你要安装 SharePoint，你必须先完成该安装，然后才能继续安装剩余的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 必备软件。</span><span class="sxs-lookup"><span data-stu-id="d793b-322">If you are installing SharePoint, you must do so before continuing with the remaining [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] prerequisites.</span></span>  
  
-   <span data-ttu-id="d793b-323">安装和配置 SharePoint 包括下列过程：</span><span class="sxs-lookup"><span data-stu-id="d793b-323">Installing and configuring SharePoint consists of the following procedures:</span></span>  
  
    -   <span data-ttu-id="d793b-324">安装 SharePoint</span><span class="sxs-lookup"><span data-stu-id="d793b-324">Install SharePoint</span></span>  
  
    -   <span data-ttu-id="d793b-325">配置 SharePoint</span><span class="sxs-lookup"><span data-stu-id="d793b-325">Configure SharePoint</span></span>  
  
    -   <span data-ttu-id="d793b-326">将默认网站扩展为虚拟服务器</span><span class="sxs-lookup"><span data-stu-id="d793b-326">Extend the default Web site as a virtual server</span></span>  
  
-   <span data-ttu-id="d793b-327">[附录 B：安装 Microsoft SharePoint 适配器](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)描述了 BizTalk Server 的 SharePoint 适配器安装选项。</span><span class="sxs-lookup"><span data-stu-id="d793b-327">[Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) describes the SharePoint adapter installation options for BizTalk Server.</span></span>  
  
-   <span data-ttu-id="d793b-328">使用 SharePoint 适配器时，建议安装新 CSOM 选项（而不是 SharePoint Service Web Service）；相关说明请参阅[附录 B：安装 Microsoft SharePoint 适配器](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="d793b-328">When using the SharePoint adapter, it is recommended to install the new CSOM option instead of the SharePoint Service Web Service; described at [Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md).</span></span>  
  
##  <a name="BKMK_SharedMem"></a> <span data-ttu-id="d793b-329">禁用 Shared Memory 协议</span><span class="sxs-lookup"><span data-stu-id="d793b-329">Disable the Shared Memory Protocol</span></span>  
  
1.  <span data-ttu-id="d793b-330">打开“SQL Server 配置管理器”。</span><span class="sxs-lookup"><span data-stu-id="d793b-330">Open **SQL Server Configuration Manager**.</span></span>  
  
2.  <span data-ttu-id="d793b-331">在“SQL Server 配置管理器”中，展开“SQL Server 网络配置”，然后选择“MSSQLSERVER 的协议”。</span><span class="sxs-lookup"><span data-stu-id="d793b-331">In **SQL Server Configuration Manager**, expand **SQL Server Network Configuration**, and then select **Protocols for MSSQLSERVER**.</span></span>  
  
3.  <span data-ttu-id="d793b-332">右键单击“共享内存”，然后选择“禁用”。</span><span class="sxs-lookup"><span data-stu-id="d793b-332">Right-click **Shared Memory**, and then select **Disable**.</span></span>  
  
4.  <span data-ttu-id="d793b-333">选择“SQL Server 服务”，右键单击“SQL Server (MSSQLSERVER)”，然后再选择“停止”。</span><span class="sxs-lookup"><span data-stu-id="d793b-333">Select **SQL Server Services**, right-click **SQL Server (MSSQLSERVER)**, and then select **Stop**.</span></span> <span data-ttu-id="d793b-334">该服务停止后，再次右键单击“SQL Server (MSSQLSERVER)”，然后选择“启动”。</span><span class="sxs-lookup"><span data-stu-id="d793b-334">After the service has stopped, right-click **SQL Server (MSSQLSERVER)** again, and then select **Start**.</span></span>  
  
5.  <span data-ttu-id="d793b-335">关闭“SQL Server 配置管理器”。</span><span class="sxs-lookup"><span data-stu-id="d793b-335">Close **SQL Server Configuration Manager**.</span></span>  
  
 <span data-ttu-id="d793b-336">**补充说明**</span><span class="sxs-lookup"><span data-stu-id="d793b-336">**Additional**</span></span>  
  
-   <span data-ttu-id="d793b-337">在任务繁忙时（例如，客户端从同一计算机访问 SQL Server 时），SQL Server Shared Memory 协议可能会降低 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 性能。</span><span class="sxs-lookup"><span data-stu-id="d793b-337">Under certain stress conditions (such as clients accessing SQL Server from the same computer), the SQL Server Shared Memory protocol may lower [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] performance.</span></span> <span data-ttu-id="d793b-338">可以通过在“SQL Server 网络配置”中禁用 Shared Memory 网络协议来解决此行为。</span><span class="sxs-lookup"><span data-stu-id="d793b-338">You can resolve this behavior by disabling the Shared Memory network protocol in SQL Server Network Configuration.</span></span>  
  
-   <span data-ttu-id="d793b-339">ReplaceThisText</span><span class="sxs-lookup"><span data-stu-id="d793b-339">ReplaceThisText</span></span>  
  
##  <a name="BKMK_LocalAdmin"></a> <span data-ttu-id="d793b-340">加入本地管理员组</span><span class="sxs-lookup"><span data-stu-id="d793b-340">Join the Local Administrators Group</span></span>  
 <span data-ttu-id="d793b-341">**[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]**[Windows Server 2012: How to Add an Account to a Local Administrator Group](http://social.technet.microsoft.com/wiki/contents/articles/13436.windows-server-2012-how-to-add-an-account-to-a-local-administrator-group.aspx)（Windows Server 2012：如何将帐户添加到本地管理员组）</span><span class="sxs-lookup"><span data-stu-id="d793b-341">**[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]** : [Windows Server 2012: How to Add an Account to a Local Administrator Group](http://social.technet.microsoft.com/wiki/contents/articles/13436.windows-server-2012-how-to-add-an-account-to-a-local-administrator-group.aspx)</span></span>  
  
 <span data-ttu-id="d793b-342">**Windows 8.1**：若要在 Windows 8 上打开“本地用户和组”，请单击键盘上的 Windows 按钮，然后键入“组”。</span><span class="sxs-lookup"><span data-stu-id="d793b-342">**Windows 8.1**: To open Local Users and Groups on Windows 8, click the Windows button on the keyboard and type **groups**.</span></span> <span data-ttu-id="d793b-343">在“搜索”窗口中，单击“设置”。</span><span class="sxs-lookup"><span data-stu-id="d793b-343">In the Search window, click **Settings**.</span></span> <span data-ttu-id="d793b-344">在“结果”窗口中，单击“编辑本地用户和组”。</span><span class="sxs-lookup"><span data-stu-id="d793b-344">In the Results window, click **Edit local users and groups**.</span></span> <span data-ttu-id="d793b-345">单击“组”，然后双击“管理员”以添加帐户。</span><span class="sxs-lookup"><span data-stu-id="d793b-345">Click **Groups** and then double-click Administrators to add an account.</span></span>  
  
 <span data-ttu-id="d793b-346">**Windows 7 SP1**：单击“启动”。</span><span class="sxs-lookup"><span data-stu-id="d793b-346">**Windows 7 SP1**: Click Start.</span></span> <span data-ttu-id="d793b-347">在“搜索”文本框中，键入“计算机管理”，然后单击将其打开。</span><span class="sxs-lookup"><span data-stu-id="d793b-347">In the **Search** text box, type **Computer Management**, and click it to open.</span></span> <span data-ttu-id="d793b-348">展开“本地用户和组”，单击“组”，然后双击以添加帐户。</span><span class="sxs-lookup"><span data-stu-id="d793b-348">Expand **Local Users and Groups**, click **Groups**, and then double-click Administrators to add an account.</span></span>  
  
 <span data-ttu-id="d793b-349">**补充说明**</span><span class="sxs-lookup"><span data-stu-id="d793b-349">**Additional**</span></span>  
  
-   <span data-ttu-id="d793b-350">你必须是本地 Administrators 组的成员才能安装和配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d793b-350">You must be a member of the local Administrators group to install and configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
##  <a name="BKMK_AppLog"></a> <span data-ttu-id="d793b-351">配置应用程序事件日志</span><span class="sxs-lookup"><span data-stu-id="d793b-351">Configure the Application Event Log</span></span>  
  
1.  <span data-ttu-id="d793b-352">打开“事件查看器”：</span><span class="sxs-lookup"><span data-stu-id="d793b-352">Open **Event Viewer**:</span></span>  
  
     <span data-ttu-id="d793b-353">**[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]**：单击键盘上的 Windows 按钮，并键入“事件查看器”。</span><span class="sxs-lookup"><span data-stu-id="d793b-353">**[!INCLUDE[btsWinSrv2k12](../includes/btswinsrv2k12-md.md)]** : Click the Windows button on the keyboard and type **Event Viewer**.</span></span> <span data-ttu-id="d793b-354">在“结果”窗口中，单击“事件查看器”。</span><span class="sxs-lookup"><span data-stu-id="d793b-354">In the Results window, click **Event Viewer**.</span></span>  
  
     <span data-ttu-id="d793b-355">**Windows 8.1**：单击键盘上的 Windows 按钮，并键入“事件查看器”。</span><span class="sxs-lookup"><span data-stu-id="d793b-355">**Windows 8.1**: Click the Windows button on the keyboard and type **Event Viewer**.</span></span> <span data-ttu-id="d793b-356">在“搜索”窗口中，单击“设置”。</span><span class="sxs-lookup"><span data-stu-id="d793b-356">In the Search window, click **Settings**.</span></span> <span data-ttu-id="d793b-357">在“结果”窗口中，单击“查看事件日志”。</span><span class="sxs-lookup"><span data-stu-id="d793b-357">In the Results window, click **View event logs**.</span></span>  
  
     <span data-ttu-id="d793b-358">**Windows 7 SP1**：单击“启动”。</span><span class="sxs-lookup"><span data-stu-id="d793b-358">**Windows 7 SP1**: Click Start.</span></span> <span data-ttu-id="d793b-359">在“搜索”文本框中，键入**事件查看器**，然后单击将其打开。</span><span class="sxs-lookup"><span data-stu-id="d793b-359">In the **Search** text box, type **Event Viewer**, and click it to open.</span></span>  
  
2.  <span data-ttu-id="d793b-360">展开“Windows 日志”，右键单击“应用程序”，然后单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="d793b-360">Expand **Windows Logs**, right-click **Application**, and then click **Properties**.</span></span> <span data-ttu-id="d793b-361">在“日志属性”中：</span><span class="sxs-lookup"><span data-stu-id="d793b-361">In **Log Properties**:</span></span>  
  
    -   <span data-ttu-id="d793b-362">若要确定可用空间，请比较“日志大小”和“最大日志大小”属性。</span><span class="sxs-lookup"><span data-stu-id="d793b-362">To determine the available space, compare the **Log Size** and the **Maximum log size** properties.</span></span>  
  
    -   <span data-ttu-id="d793b-363">若要提供更多的空间，请在“最大日志大小”中输入一个更大的值。</span><span class="sxs-lookup"><span data-stu-id="d793b-363">To provide more space, enter a higher number in **Maximum log size**.</span></span>  
  
    -   <span data-ttu-id="d793b-364">若要在日志变满时启用对旧事件的覆盖功能，请选择“按需要覆盖事件”。</span><span class="sxs-lookup"><span data-stu-id="d793b-364">To enable overwriting of old events when the log becomes full, select **Overwrite events as needed**.</span></span>  
  
    -   <span data-ttu-id="d793b-365">若要清除日志事件，请选择“清除日志”。</span><span class="sxs-lookup"><span data-stu-id="d793b-365">To clear the log events, select **Clear log**.</span></span>  
  
3.  <span data-ttu-id="d793b-366">单击“确定”关闭“事件查看器”。</span><span class="sxs-lookup"><span data-stu-id="d793b-366">Click **OK** to close the **Event Viewer**.</span></span>  
  
 <span data-ttu-id="d793b-367">**补充说明**</span><span class="sxs-lookup"><span data-stu-id="d793b-367">**Additional**</span></span>  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="d793b-368"> 安装程序会将事件记录保留在应用程序事件日志中。</span><span class="sxs-lookup"><span data-stu-id="d793b-368"> setup keeps a record of events in the Application Event Log.</span></span> <span data-ttu-id="d793b-369">日志中所需的空间量可能会超出其限制，具体取决于所安装的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 功能。</span><span class="sxs-lookup"><span data-stu-id="d793b-369">Depending on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] features installed, the amount of space required in the log may exceed its limit.</span></span> <span data-ttu-id="d793b-370">如果在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 安装期间应用程序事件日志出现空间不足，安装将失败。</span><span class="sxs-lookup"><span data-stu-id="d793b-370">If the application event log runs out of space during [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] setup, the installation fails.</span></span> <span data-ttu-id="d793b-371">更改“应用程序事件日志”设置可防止此故障。</span><span class="sxs-lookup"><span data-stu-id="d793b-371">Changing the Application Event Log settings prevents this failure.</span></span>  
  
## <a name="next"></a><span data-ttu-id="d793b-372">Next</span><span class="sxs-lookup"><span data-stu-id="d793b-372">Next</span></span>  
 [<span data-ttu-id="d793b-373">选择 BizTalk Server 功能和组件</span><span class="sxs-lookup"><span data-stu-id="d793b-373">Choose BizTalk Server Features and Components</span></span>](http://msdn.microsoft.com/library/b8c43fcf-9e5c-48ba-830b-13a5177e30f0)  
  
## <a name="see-also"></a><span data-ttu-id="d793b-374">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d793b-374">See Also</span></span>  
 <span data-ttu-id="d793b-375">[BizTalk Server 2013 和 2013 R2 安装概述](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5) </span><span class="sxs-lookup"><span data-stu-id="d793b-375">[Installation Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5) </span></span>  
 <span data-ttu-id="d793b-376">[附录 A：无提示安装](../install-and-config-guides/appendix-a-silent-installation.md) </span><span class="sxs-lookup"><span data-stu-id="d793b-376">[Appendix A: Silent Installation](../install-and-config-guides/appendix-a-silent-installation.md) </span></span>  
 <span data-ttu-id="d793b-377">[附录 B：安装 Microsoft SharePoint 适配器](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="d793b-377">[Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) </span></span>  
 <span data-ttu-id="d793b-378">[附录 C：可再发行的 CAB 文件](../install-and-config-guides/appendix-c-redistributable-cab-files.md) </span><span class="sxs-lookup"><span data-stu-id="d793b-378">[Appendix C: Redistributable CAB Files](../install-and-config-guides/appendix-c-redistributable-cab-files.md) </span></span>  
 [<span data-ttu-id="d793b-379">附录 D：创建 SMTP 服务器</span><span class="sxs-lookup"><span data-stu-id="d793b-379">Appendix D: Create the SMTP Server</span></span>](../install-and-config-guides/appendix-d-create-the-smtp-server.md)
