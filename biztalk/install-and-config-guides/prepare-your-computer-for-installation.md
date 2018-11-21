---
title: 准备计算机以安装 |Microsoft Docs
ms.custom: ''
ms.date: 03/15/2016
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53df7a2f-638b-4921-a97f-736760248526
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bba64728220eb2fc5be99153892d68e93eb8e22c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37017202"
---
# <a name="prepare-your-computer-for-installation"></a><span data-ttu-id="fe862-102">准备计算机以进行安装</span><span class="sxs-lookup"><span data-stu-id="fe862-102">Prepare Your Computer for Installation</span></span>
<span data-ttu-id="fe862-103">本主题将介绍如何通过安装和配置所有必备软件，然后再创建帐户并设置权限来准备你的计算机。</span><span class="sxs-lookup"><span data-stu-id="fe862-103">This topic lists the steps to prepare your computer by installing and configuring all software prerequisites, and then creating accounts and setting permissions.</span></span>  

> [!TIP] 
> <span data-ttu-id="fe862-104">集成 MVP 准备了非常详细的分步指南，用于安装必备组件和 BizTalk Server：[BizTalk 2013 Installation and Configuration part 1](http://sandroaspbiztalkblog.wordpress.com/2013/05/05/biztalk-2013-installation-and-configuration-important-considerations-before-set-up-the-server-part-1/)（BizTalk 2013 安装和配置第 1 部分）。</span><span class="sxs-lookup"><span data-stu-id="fe862-104">An integration MVP prepared a very detailed step-by-step guide to install the prerequisites, and BizTalk Server:  [BizTalk 2013 Installation and Configuration part 1](http://sandroaspbiztalkblog.wordpress.com/2013/05/05/biztalk-2013-installation-and-configuration-important-considerations-before-set-up-the-server-part-1/).</span></span>  
> 
> <span data-ttu-id="fe862-105">Microsoft 不推荐某些步骤，例如，禁用用户访问控制 (UAC) 或 Windows 防火墙。</span><span class="sxs-lookup"><span data-stu-id="fe862-105">Some steps are not recommended by Microsoft, such as disabling User Access Control (UAC) or Windows Firewall.</span></span> 
  
> [!IMPORTANT]
>  <span data-ttu-id="fe862-106">按列出的顺序完成这些任务。</span><span class="sxs-lookup"><span data-stu-id="fe862-106">Complete these tasks in the order listed.</span></span>  
  
##  <a name="BKMK_InstUpdates"></a> <span data-ttu-id="fe862-107">安装 Windows 更新</span><span class="sxs-lookup"><span data-stu-id="fe862-107">Install Windows Updates</span></span>  
  
- <span data-ttu-id="fe862-108">**Windows 7**：单击“开始”。</span><span class="sxs-lookup"><span data-stu-id="fe862-108">**Windows 7**: Click Start.</span></span> <span data-ttu-id="fe862-109">在“搜索”文本框中，键入 **Windows Update**。</span><span class="sxs-lookup"><span data-stu-id="fe862-109">In the **Search** text box, type **Windows Update**.</span></span>  
  
- <span data-ttu-id="fe862-110">**Windows 8.1、 Windows Server 2012 和 Windows Server 2012 R2**： 单击键盘和类型上的 Windows 按钮**Windows Update**。</span><span class="sxs-lookup"><span data-stu-id="fe862-110">**Windows 8.1, Windows Server 2012, and Windows Server 2012 R2**: Click the Windows button on the keyboard and type **Windows Update**.</span></span> <span data-ttu-id="fe862-111">在搜索结果中，单击“Windows 更新”。</span><span class="sxs-lookup"><span data-stu-id="fe862-111">From the search results, click **Windows Update**.</span></span>  
  
  <span data-ttu-id="fe862-112">安装更新之后，你可能需要重新启动计算机。</span><span class="sxs-lookup"><span data-stu-id="fe862-112">After installing updates, you may need to restart the computer.</span></span>  
  
##  <a name="BKMK_IIS"></a> <span data-ttu-id="fe862-113">启用 Internet Information Services</span><span class="sxs-lookup"><span data-stu-id="fe862-113">Enable Internet Information Services</span></span>  
 <span data-ttu-id="fe862-114">Microsoft Internet 信息服务 (IIS) 提供的很多 BizTalk Server 功能，包括 Web 应用程序基础结构：</span><span class="sxs-lookup"><span data-stu-id="fe862-114">Microsoft Internet Information Services (IIS) provides a Web application infrastructure for many BizTalk Server features, including:</span></span>  
  
-   <span data-ttu-id="fe862-115">HTTP 适配器</span><span class="sxs-lookup"><span data-stu-id="fe862-115">HTTP adapter</span></span>  
  
-   <span data-ttu-id="fe862-116">SOAP 适配器</span><span class="sxs-lookup"><span data-stu-id="fe862-116">SOAP adapter</span></span>  
  
-   <span data-ttu-id="fe862-117">Windows SharePoint Services 适配器</span><span class="sxs-lookup"><span data-stu-id="fe862-117">Windows SharePoint Services adapter</span></span>  
  
-   <span data-ttu-id="fe862-118">安全套接字层 (SSL) 加密</span><span class="sxs-lookup"><span data-stu-id="fe862-118">Secure Sockets Layer (SSL) encryption</span></span>  
  
-   <span data-ttu-id="fe862-119">BAM 门户</span><span class="sxs-lookup"><span data-stu-id="fe862-119">BAM Portal</span></span>  
  
#### <a name="install-iis"></a><span data-ttu-id="fe862-120">安装 IIS</span><span class="sxs-lookup"><span data-stu-id="fe862-120">Install IIS</span></span>

<span data-ttu-id="fe862-121">针对特定的安装步骤，请参阅：</span><span class="sxs-lookup"><span data-stu-id="fe862-121">For the specific install steps, see:</span></span> 

[<span data-ttu-id="fe862-122">安装 IIS （Windows 8 和 Windows Server 2012）</span><span class="sxs-lookup"><span data-stu-id="fe862-122">Install IIS (Windows 8 and Windows Server 2012)</span></span>](https://docs.microsoft.com/iis/get-started/whats-new-in-iis-8/installing-iis-8-on-windows-server-2012)

[<span data-ttu-id="fe862-123">安装 IIS （Windows 7 和 Windows Vista）</span><span class="sxs-lookup"><span data-stu-id="fe862-123">Install IIS (Windows 7 and Windows Vista)</span></span>](https://docs.microsoft.com/iis/install/installing-iis-7/installing-iis-on-windows-vista-and-windows-7)


<span data-ttu-id="fe862-124">在安装 IIS，除了默认选中选项时，还检查以下项：</span><span class="sxs-lookup"><span data-stu-id="fe862-124">When you install IIS, in addition to the default checked options, also check the following:</span></span>  
  
- <span data-ttu-id="fe862-125">“Web 管理工具”：还需检查：</span><span class="sxs-lookup"><span data-stu-id="fe862-125">**Web Management Tools**: Also check:</span></span>  
  
    - <span data-ttu-id="fe862-126">IIS 6 管理兼容性：</span><span class="sxs-lookup"><span data-stu-id="fe862-126">IIS 6 Management Compatibility:</span></span>  
  
        - <span data-ttu-id="fe862-127">IIS 6 管理控制台</span><span class="sxs-lookup"><span data-stu-id="fe862-127">IIS 6 Management Console</span></span>  
  
        - <span data-ttu-id="fe862-128">IIS 元数据库和 IIS 6 配置兼容性</span><span class="sxs-lookup"><span data-stu-id="fe862-128">IIS Metabase and IIS 6 configuration compatibility</span></span>  
  
    - <span data-ttu-id="fe862-129">IIS 管理控制台</span><span class="sxs-lookup"><span data-stu-id="fe862-129">IIS Management Console</span></span>  
  
- <span data-ttu-id="fe862-130">**万维网服务**：展开“安全性”，还需选择：</span><span class="sxs-lookup"><span data-stu-id="fe862-130">**World Wide Web Services**: Expand **Security** and also select:</span></span>  
  
    - <span data-ttu-id="fe862-131">基本身份验证</span><span class="sxs-lookup"><span data-stu-id="fe862-131">Basic Authentication</span></span>  
  
    - <span data-ttu-id="fe862-132">Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="fe862-132">Windows Authentication</span></span>  

<span data-ttu-id="fe862-133">同时还应考虑下列事项：</span><span class="sxs-lookup"><span data-stu-id="fe862-133">Also consider the following:</span></span>  
  
- <span data-ttu-id="fe862-134">**.Net framework 3.5 功能**:.NET Framework 4.5 和.NET Framework 3.5 可用于开发.Net 应用程序涉及 BizTalk Adapter Pack。</span><span class="sxs-lookup"><span data-stu-id="fe862-134">**.Net Framework 3.5 Features**: .NET Framework 4.5 and .NET Framework 3.5 can be used to develop .Net applications involving the BizTalk Adapter Pack.</span></span> <span data-ttu-id="fe862-135">通常情况下， **.NET Framework 4.5 功能**已安装。</span><span class="sxs-lookup"><span data-stu-id="fe862-135">Typically, **.NET Framework 4.5 Features** is already installed.</span></span> <span data-ttu-id="fe862-136">如果将使用.NET Framework 3.5，然后在此计算机上创建应用程序 **.Net Framework 3.5 功能**也可以安装。</span><span class="sxs-lookup"><span data-stu-id="fe862-136">If you will use .NET Framework 3.5 to create applications on this computer, then **.Net Framework 3.5 Features** can also be installed.</span></span>  
  
- <span data-ttu-id="fe862-137">**消息队列**：如果使用 MSMQ 适配器，可以通过选中“消息队列”创建本地 MSMQ 存储。</span><span class="sxs-lookup"><span data-stu-id="fe862-137">**Message Queuing**: If you are using the MSMQ adapter, you can create a local MSMQ store by checking **Message Queuing**.</span></span>  
  
- <span data-ttu-id="fe862-138">**SMTP 服务器**：如果使用 SMTP 适配器，可以通过选中“SMTP 服务器”创建本地 SMTP 服务器。</span><span class="sxs-lookup"><span data-stu-id="fe862-138">**SMTP Server**: If you are using the SMTP adapter, you can create a local SMTP Server by checking **SMTP Server**.</span></span>  
  
- <span data-ttu-id="fe862-139">**Windows Identity Foundation 3.5**： 使用 CSOM 安装选项时，SharePoint 适配器需要 Windows Identity Foundation (WIF)。</span><span class="sxs-lookup"><span data-stu-id="fe862-139">**Windows Identity Foundation 3.5**: Windows Identity Foundation (WIF) is required by the SharePoint adapter when using the CSOM installation option.</span></span> <span data-ttu-id="fe862-140">[附录 b： 安装 Microsoft SharePoint 适配器](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)介绍 SharePoint 适配器的 CSOM 安装选项。</span><span class="sxs-lookup"><span data-stu-id="fe862-140">[Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) describes the CSOM installation option for the SharePoint adapter.</span></span>    
  
 
##  <a name="BKMK_XLS"></a> <span data-ttu-id="fe862-141">安装 Microsoft Office Excel</span><span class="sxs-lookup"><span data-stu-id="fe862-141">Install Microsoft Office Excel</span></span>  
  
1. <span data-ttu-id="fe862-142">运行 Microsoft Office 安装程序。</span><span class="sxs-lookup"><span data-stu-id="fe862-142">Run the Microsoft Office setup.</span></span>  
  
2. <span data-ttu-id="fe862-143">显示“安装类型”屏幕时，选择“自定义安装”，然后选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="fe862-143">When you reach the **Type of Installation** screen, select **Custom Install**, and then select **Next**.</span></span>  
  
3. <span data-ttu-id="fe862-144">在“自定义安装”屏幕上，选择“Excel”，然后选择“下一步”。</span><span class="sxs-lookup"><span data-stu-id="fe862-144">On the **Custom Setup** screen, select **Excel**, and then select **Next**.</span></span>  
  
4. <span data-ttu-id="fe862-145">选择“安装”。</span><span class="sxs-lookup"><span data-stu-id="fe862-145">Select **Install**.</span></span>  
  
5. <span data-ttu-id="fe862-146">在“已完成安装”中，选择“完成”。</span><span class="sxs-lookup"><span data-stu-id="fe862-146">In **Setup Completed**, select **Finish**.</span></span>  
  
   <span data-ttu-id="fe862-147">**补充说明**</span><span class="sxs-lookup"><span data-stu-id="fe862-147">**Additional**</span></span>  
  
-   <span data-ttu-id="fe862-148">BizTalk Server 仅支持 32 位版本的 Microsoft Office。</span><span class="sxs-lookup"><span data-stu-id="fe862-148">BizTalk Server supports only 32-bit version of Microsoft Office.</span></span>  
  
-   <span data-ttu-id="fe862-149">Microsoft Office Excel 需要由业务活动监视 (BAM) 在 BizTalk Server 中。</span><span class="sxs-lookup"><span data-stu-id="fe862-149">Microsoft Office Excel is required by Business Activity Monitoring (BAM) in BizTalk Server.</span></span> <span data-ttu-id="fe862-150">可以使用 BAM Office Excel 工作簿来定义要监视的业务流程。</span><span class="sxs-lookup"><span data-stu-id="fe862-150">The BAM Office Excel Workbook defines the business processes you want to monitor.</span></span> <span data-ttu-id="fe862-151">还可以使用 BAM Excel 工作簿定义业务用户查看 BAM 所收集的数据的方式。</span><span class="sxs-lookup"><span data-stu-id="fe862-151">You also use the BAM Excel Workbook to define the way business users see the data collected by BAM.</span></span>  
  
-   <span data-ttu-id="fe862-152">若要成功将 BAM.xla 加载到 Excel 中，请在“Office 共享功能”下安装“Visual Basic for Applications”。</span><span class="sxs-lookup"><span data-stu-id="fe862-152">To successfully load BAM.xla into Excel, install **Visual Basic for Applications** under **Office Shared Features**.</span></span> <span data-ttu-id="fe862-153">否则，可能会收到“此工作簿已丢失了其 VBA 项目、ActiveX 控件以及其他任何与可编程性相关的功能”错误。</span><span class="sxs-lookup"><span data-stu-id="fe862-153">Otherwise, you may get error “This workbook has lost its VBA project, ActiveX controls and any other programmability-related features.”</span></span>  
  
##  <a name="BKMK_VS"></a> <span data-ttu-id="fe862-154">安装 Visual Studio</span><span class="sxs-lookup"><span data-stu-id="fe862-154">Install Visual Studio</span></span>  
  
1. <span data-ttu-id="fe862-155">以管理员身份运行 Visual Studio 安装程序。</span><span class="sxs-lookup"><span data-stu-id="fe862-155">Run the Visual Studio setup as Administrator.</span></span>  
  
2. <span data-ttu-id="fe862-156">接受许可协议，然后单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="fe862-156">Accept the license agreement and click **Next**.</span></span>  
  
3. <span data-ttu-id="fe862-157">在“要安装的可选功能”中，选择所需的选项，然后选择“安装”。</span><span class="sxs-lookup"><span data-stu-id="fe862-157">In **Optional features to install**, select the options you need and then select **Install**.</span></span> <span data-ttu-id="fe862-158">BizTalk Server 不需要任何可选功能。</span><span class="sxs-lookup"><span data-stu-id="fe862-158">BizTalk Server does not require any of the optional features.</span></span>  
  
4. <span data-ttu-id="fe862-159">在“完成”页面上，关闭窗口或单击“启动”打开 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="fe862-159">On the **Finish** page, close the window or click **Launch** to open Visual Studio.</span></span>  
  
   <span data-ttu-id="fe862-160">**补充说明**</span><span class="sxs-lookup"><span data-stu-id="fe862-160">**Additional**</span></span>  
  
-   <span data-ttu-id="fe862-161">如果安装 BizTalk Server 之前安装 Visual Studio，然后升级到 Visual Studio 团队资源管理器，您可能需要修复从 BizTalk Server 安装**Control Panel** / **程序**选项。</span><span class="sxs-lookup"><span data-stu-id="fe862-161">If you install Visual Studio before installing BizTalk Server, and then upgrade to Visual Studio Team Explorer, you may need to repair your BizTalk Server installation from the **Control Panel** / **Programs** option.</span></span>  
  
-   <span data-ttu-id="fe862-162">Visual Studio 会自动安装 Microsoft SQL Server Express；而 BizTalk Server 并不使用它。</span><span class="sxs-lookup"><span data-stu-id="fe862-162">Visual Studio automatically installs Microsoft SQL Server Express; which is not used by BizTalk Server.</span></span> <span data-ttu-id="fe862-163">最好卸载 Microsoft SQL Server Express。</span><span class="sxs-lookup"><span data-stu-id="fe862-163">As a best practice, uninstall Microsoft SQL Server Express.</span></span>  
  
-   <span data-ttu-id="fe862-164">BizTalk Server 开发工具基于 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="fe862-164">The BizTalk Server development tools are based on Visual Studio.</span></span> <span data-ttu-id="fe862-165">至少，您必须安装 Visual Studio 的 Microsoft Visual C#®.NET 组件，在安装 BizTalk Server 之前**开发人员工具和 SDK**。</span><span class="sxs-lookup"><span data-stu-id="fe862-165">At a minimum, you must install the Microsoft Visual C#® .NET component of Visual Studio before you install the BizTalk Server**Developer Tools and SDK**.</span></span>  
  
-   <span data-ttu-id="fe862-166">Visual studio*不*所需安装任何应用程序开发或调试是必需的 BizTalk Server （仅限运行时），在生产计算机上。</span><span class="sxs-lookup"><span data-stu-id="fe862-166">Visual Studio is *not* required if you are installing BizTalk Server on a production computer (runtime only), on which no application development or debugging is required.</span></span>  
  
-   <span data-ttu-id="fe862-167">BizTalk Server 运行时需要.NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="fe862-167">The BizTalk Server runtime requires .NET Framework 4.5.</span></span> <span data-ttu-id="fe862-168">如果已安装 Windows Communication Foundation (WCF) 适配器或 WCF 侦听器，则需要安装 .NET Framework 3.0。</span><span class="sxs-lookup"><span data-stu-id="fe862-168">The .NET Framework 3.0 is required if the Windows Communication Foundation (WCF) adapter or WCF Interceptor is installed.</span></span>  
  
##  <a name="BKMK_SQL"></a> <span data-ttu-id="fe862-169">安装 SQL Server</span><span class="sxs-lookup"><span data-stu-id="fe862-169">Install SQL Server</span></span>  
 <span data-ttu-id="fe862-170">安装 [SQL Server 2008 R2](http://msdn.microsoft.com/library/bb500395\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="fe862-170">Install [SQL Server 2008 R2](http://msdn.microsoft.com/library/bb500395\(v=sql.105\).aspx)</span></span>  
  
 <span data-ttu-id="fe862-171">安装 [SQL Server 2012](http://msdn.microsoft.com/library/bb500469\(v=sql.110\).aspx)</span><span class="sxs-lookup"><span data-stu-id="fe862-171">Install [SQL Server 2012](http://msdn.microsoft.com/library/bb500469\(v=sql.110\).aspx)</span></span>  
  
 <span data-ttu-id="fe862-172">安装 [SQL Server 2014](http://msdn.microsoft.com/library/bb500469\(v=sql.120\).aspx)</span><span class="sxs-lookup"><span data-stu-id="fe862-172">Install [SQL Server 2014](http://msdn.microsoft.com/library/bb500469\(v=sql.120\).aspx)</span></span>  
  
 <span data-ttu-id="fe862-173">在安装 SQL Server 时，选择以下功能：</span><span class="sxs-lookup"><span data-stu-id="fe862-173">When you install SQL Server, select the following features:</span></span>  
  
- <span data-ttu-id="fe862-174">数据库引擎服务</span><span class="sxs-lookup"><span data-stu-id="fe862-174">Database Engine Services</span></span>  
  
  -   <span data-ttu-id="fe862-175">SQL Server 复制</span><span class="sxs-lookup"><span data-stu-id="fe862-175">SQL Server Replication</span></span>  
  
  -   <span data-ttu-id="fe862-176">全文搜索</span><span class="sxs-lookup"><span data-stu-id="fe862-176">Full-Text Search</span></span>  
  
- <span data-ttu-id="fe862-177">Analysis Services</span><span class="sxs-lookup"><span data-stu-id="fe862-177">Analysis Services</span></span>  
  
- <span data-ttu-id="fe862-178">Reporting Services</span><span class="sxs-lookup"><span data-stu-id="fe862-178">Reporting Services</span></span>  
  
- <span data-ttu-id="fe862-179">共享功能</span><span class="sxs-lookup"><span data-stu-id="fe862-179">Shared Features</span></span>  
  
  -   <span data-ttu-id="fe862-180">SQL Server Data Tools (SQL Server 2014/SQL Server 2012) 或 Business Intelligence Development Studio (SQL Server 2008 R2)</span><span class="sxs-lookup"><span data-stu-id="fe862-180">SQL Server Data Tools (SQL Server 2014 / SQL Server 2012) or Business Intelligence Development Studio (SQL Server 2008 R2)</span></span>  
  
       [<span data-ttu-id="fe862-181">下载 SQL Server 2014 Data Tools</span><span class="sxs-lookup"><span data-stu-id="fe862-181">Download SQL Server 2014 Data Tools</span></span>](http://www.microsoft.com/download/details.aspx?id=42313)  
  
  -   <span data-ttu-id="fe862-182">客户端工具连接</span><span class="sxs-lookup"><span data-stu-id="fe862-182">Client Tools Connectivity</span></span>  
  
  -   <span data-ttu-id="fe862-183">Integration Services</span><span class="sxs-lookup"><span data-stu-id="fe862-183">Integration Services</span></span>  
  
  -   <span data-ttu-id="fe862-184">管理工具 - 基本</span><span class="sxs-lookup"><span data-stu-id="fe862-184">Management Tools - Basic</span></span>  
  
      -   <span data-ttu-id="fe862-185">管理工具 - 完整</span><span class="sxs-lookup"><span data-stu-id="fe862-185">Management Tools - Complete</span></span>  
  
  <span data-ttu-id="fe862-186">**补充说明**</span><span class="sxs-lookup"><span data-stu-id="fe862-186">**Additional**</span></span>  
  
- <span data-ttu-id="fe862-187">BizTalk Server 支持所有区分大小写和不区分大小写的 SQL Server 排序规则，二进制排序规则例外。</span><span class="sxs-lookup"><span data-stu-id="fe862-187">BizTalk Server supports all case-sensitive and case-insensitive SQL Server collations except for binary collations.</span></span> <span data-ttu-id="fe862-188">不支持二进制排序规则。</span><span class="sxs-lookup"><span data-stu-id="fe862-188">Binary collations are not supported.</span></span>  
  
- <span data-ttu-id="fe862-189">为了获得最佳性能，Microsoft 建议使用 SQL Server Enterprise Edition。</span><span class="sxs-lookup"><span data-stu-id="fe862-189">For optimal performance, Microsoft recommends using the Enterprise Edition of SQL Server.</span></span> <span data-ttu-id="fe862-190">请参阅 [SQL Server 2008 R2 版本](http://msdn.microsoft.com/library/cc645993\(v=sql.105\).aspx)、[SQL Server 2012 版本](http://msdn.microsoft.com/library/cc645993\(v=sql.110\).aspx)或 [SQL Server 2014 版本](http://msdn.microsoft.com/library/cc645993\(v=sql.120\).aspx)。</span><span class="sxs-lookup"><span data-stu-id="fe862-190">See [SQL Server 2008 R2 Editions](http://msdn.microsoft.com/library/cc645993\(v=sql.105\).aspx), [SQL Server 2012 Editions](http://msdn.microsoft.com/library/cc645993\(v=sql.110\).aspx), or [SQL Server 2014 Editions](http://msdn.microsoft.com/library/cc645993\(v=sql.120\).aspx).</span></span>  
  
- <span data-ttu-id="fe862-191">支持 Service Pack 和 Windows Update，并且应进行安装。</span><span class="sxs-lookup"><span data-stu-id="fe862-191">Service packs and Windows Updates are supported and should be installed.</span></span>  
  
- <span data-ttu-id="fe862-192">当 BizTalk Server 和 SQL Server 在不同计算机上时，分布式事务处理协调器 (MS DTC) 处理计算机之间的事务。</span><span class="sxs-lookup"><span data-stu-id="fe862-192">When BizTalk Server and SQL Server are on separate computers, Distributed Transaction Coordinator (MS DTC) handles the transactions between the computers.</span></span> <span data-ttu-id="fe862-193">SQL Server AlwaysOn 功能不支持 MSDTC 事务。</span><span class="sxs-lookup"><span data-stu-id="fe862-193">The SQL Server AlwaysOn feature does not support MSDTC transactions.</span></span> <span data-ttu-id="fe862-194">不支持 SQL Server AlwaysOn 功能。</span><span class="sxs-lookup"><span data-stu-id="fe862-194">The SQL Server AlwaysOn feature is not supported.</span></span>  
  
##  <a name="BKMK_MQSeries"></a> <span data-ttu-id="fe862-195">安装 MQSeries 必备组件</span><span class="sxs-lookup"><span data-stu-id="fe862-195">Install MQSeries Prerequisites</span></span>  
 <span data-ttu-id="fe862-196">**MQSeries 适配器**：自动随 BizTalk Server 一起安装。</span><span class="sxs-lookup"><span data-stu-id="fe862-196">**MQSeries adapter**: Automatically installed with the BizTalk Server installation.</span></span>  
  
 <span data-ttu-id="fe862-197">**MQSeries 客户端 (MQSC) 适配器**：</span><span class="sxs-lookup"><span data-stu-id="fe862-197">**MQSeries Client (MQSC) adapter**:</span></span>  
  
1. <span data-ttu-id="fe862-198">运行 Host Integration Server (HIS) 安装</span><span class="sxs-lookup"><span data-stu-id="fe862-198">Run the Host Integration Server (HIS) installation</span></span>  
  
2. <span data-ttu-id="fe862-199">在组件安装中，展开“BizTalk 适配器”。</span><span class="sxs-lookup"><span data-stu-id="fe862-199">In component installation, expand **BizTalk Adapters**.</span></span>  
  
3. <span data-ttu-id="fe862-200">选择“适用于 WebSphere MQ 的 BizTalk 适配器(基于客户端)”。</span><span class="sxs-lookup"><span data-stu-id="fe862-200">Select **BizTalk Adapter for WebSphere MQ (Client-Based)**.</span></span>  
  
   <span data-ttu-id="fe862-201">**支持的 IBM WebSphere MQ 版本：**：</span><span class="sxs-lookup"><span data-stu-id="fe862-201">**Supported IBM WebSphere MQ versions**:</span></span>  
  
-   <span data-ttu-id="fe862-202">IBM WebSphere MQ 6.0.2.12 和更高版本</span><span class="sxs-lookup"><span data-stu-id="fe862-202">IBM WebSphere MQ 6.0.2.12 and later</span></span>  
  
-   <span data-ttu-id="fe862-203">IBM WebSphere MQ 7.0.1.9 和更高版本</span><span class="sxs-lookup"><span data-stu-id="fe862-203">IBM WebSphere MQ 7.0.1.9 and later</span></span>  
  
-   <span data-ttu-id="fe862-204">IBM WebSphere MQ 7.1.0.5 和更高版本</span><span class="sxs-lookup"><span data-stu-id="fe862-204">IBM WebSphere MQ 7.1.0.5 and later</span></span>  
  
-   <span data-ttu-id="fe862-205">IBM WebSphere MQ 7.5.0.3 和更高版本</span><span class="sxs-lookup"><span data-stu-id="fe862-205">IBM WebSphere MQ 7.5.0.3 and later</span></span>  
  
-   <span data-ttu-id="fe862-206">IBM WebSphere MQ 8（限制为运行时；无管理 API）</span><span class="sxs-lookup"><span data-stu-id="fe862-206">IBM WebSphere MQ 8 (limited to runtime; no administration APIs)</span></span>  
  
     <span data-ttu-id="fe862-207">MQ 版本 8 支持随附在[主机集成服务器累积更新 3](https://support.microsoft.com/kb/3019572)中。</span><span class="sxs-lookup"><span data-stu-id="fe862-207">MQ version 8 support is included with [Host Integration Server CU3](https://support.microsoft.com/kb/3019572).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fe862-208">如果未列出特定的 WebSphere MQ 版本，如 MQ 5.x，则它不支持与此 BizTalk Server 版本。</span><span class="sxs-lookup"><span data-stu-id="fe862-208">If a specific WebSphere MQ version is not listed, like MQ 5.x, then it is not supported with this BizTalk Server version.</span></span>  
  
 <span data-ttu-id="fe862-209">**补充说明**</span><span class="sxs-lookup"><span data-stu-id="fe862-209">**Additional**</span></span>  
  
- <span data-ttu-id="fe862-210">最佳做法是，始终安装最新的 WebSphere MQ 修补程序包。</span><span class="sxs-lookup"><span data-stu-id="fe862-210">As a best practice, always install the latest WebSphere MQ fix pack.</span></span> <span data-ttu-id="fe862-211">请参阅[ http://www.ibm.com/support/docview.wss?uid=swg27006037 ](http://www.ibm.com/support/docview.wss?uid=swg27006037)。</span><span class="sxs-lookup"><span data-stu-id="fe862-211">See [http://www.ibm.com/support/docview.wss?uid=swg27006037](http://www.ibm.com/support/docview.wss?uid=swg27006037).</span></span>  
  
- <span data-ttu-id="fe862-212">如果在非 Windows 计算机上安装 IBM WebSphere MQ，可将 **MQSAgent COM+ 应用程序** (MQSConfigWiz.exe) 和 **MQSeries Server for Windows** 安装在同一台计算机上。</span><span class="sxs-lookup"><span data-stu-id="fe862-212">If IBM WebSphere MQ is installed on a non-Windows computer, install the **MQSAgent COM+ application** (MQSConfigWiz.exe) and **MQSeries Server for Windows** on the same computer.</span></span> <span data-ttu-id="fe862-213">如果在 Windows 计算机上安装 IBM WebSphere MQ，则不使用也不需要 **MQSAgent COM+ 应用程序**和 **MQSeries Server for Windows** 程序。</span><span class="sxs-lookup"><span data-stu-id="fe862-213">If IBM WebSphere MQ is installed on a Windows computer, then the **MQSAgent COM+ application** and **MQSeries Server for Windows** program are not used or needed.</span></span>  
  
   <span data-ttu-id="fe862-214">**MQSConfigWiz.exe**包含在 BizTalk Server 安装文件。</span><span class="sxs-lookup"><span data-stu-id="fe862-214">**MQSConfigWiz.exe** is included in the BizTalk Server installation files.</span></span>  
  
   <span data-ttu-id="fe862-215">**MQSeries Server for Windows** 不是 Microsoft 程序，必须通过 IBM WebSphere MQ 程序获得。</span><span class="sxs-lookup"><span data-stu-id="fe862-215">**MQSeries Server for Windows** is not a Microsoft program and must be obtained with your IBM WebSphere MQ program.</span></span>  
  
- <span data-ttu-id="fe862-216">[MQSeries 适配器](http://technet.microsoft.com/library/aa547973\(v=BTS.80\).aspx)提供了有关 MQSeries 适配器及配置不同组件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="fe862-216">[MQSeries Adapter](http://technet.microsoft.com/library/aa547973\(v=BTS.80\).aspx) provides more information on the MQSeries adapter, including configuring the different components.</span></span> <span data-ttu-id="fe862-217">[BizTalk Server：MQSeries 和 MQSeries 客户端 (MQSC) 适配器](http://social.technet.microsoft.com/wiki/contents/articles/18316.biztalk-server-mqseries-and-mqseries-client-mqsc-adapters.aspx)提供了有关 MQSeries 和 MQSC 适配器的详细信息。</span><span class="sxs-lookup"><span data-stu-id="fe862-217">[BizTalk Server: MQSeries and MQSeries Client (MQSC) adapters](http://social.technet.microsoft.com/wiki/contents/articles/18316.biztalk-server-mqseries-and-mqseries-client-mqsc-adapters.aspx) provides additional details on the MQSeries and MQSC adapters.</span></span>  
  
- <span data-ttu-id="fe862-218">IBM WebSphere 不是 Microsoft 产品，也不受 Microsoft 支持。</span><span class="sxs-lookup"><span data-stu-id="fe862-218">IBM WebSphere is not a Microsoft product and is not supported by Microsoft.</span></span> <span data-ttu-id="fe862-219">Microsoft 不保证此程序的适用性。</span><span class="sxs-lookup"><span data-stu-id="fe862-219">Microsoft makes no guarantees about the suitability of this program.</span></span> <span data-ttu-id="fe862-220">有关 IBM WebSphere MQ 的详细信息，请参阅 www.ibm.com 。</span><span class="sxs-lookup"><span data-stu-id="fe862-220">For more information about IBM WebSphere MQ, including download instructions, see www.ibm.com.</span></span>  
  
##  <a name="BKMK_BAMAlerts"></a> <span data-ttu-id="fe862-221">BAM 警报</span><span class="sxs-lookup"><span data-stu-id="fe862-221">BAM Alerts</span></span>  
 <span data-ttu-id="fe862-222">使用 SQL Server 2012 和更高版本的 BAM 警报使用 SQL Server 中的数据库邮件。</span><span class="sxs-lookup"><span data-stu-id="fe862-222">BAM Alerts with SQL Server 2012 and newer versions use Database Mail in SQL Server.</span></span> <span data-ttu-id="fe862-223">使用 SQL Server 2008 R2 和较旧版本的 BAM 警报使用 SQL Notification Services。</span><span class="sxs-lookup"><span data-stu-id="fe862-223">BAM Alerts with SQL Server 2008 R2 and older versions use SQL Notification Services.</span></span> <span data-ttu-id="fe862-224">安装或配置 BAM 警报之前, 您必须对 SQL Server 中配置 Notification Services 或数据库邮件。</span><span class="sxs-lookup"><span data-stu-id="fe862-224">Before installing or configuring BAM Alerts, you must configure the Notification Services or Database Mail in SQL Server.</span></span>  
  
###  <a name="BKMK_DBMail"></a> <span data-ttu-id="fe862-225">使用 SQL Server 2012/2014 的 BAM 警报</span><span class="sxs-lookup"><span data-stu-id="fe862-225">BAM Alerts using SQL Server 2012/2014</span></span>  
 <span data-ttu-id="fe862-226">配置 [SQL Server 2012 数据库邮件](http://msdn.microsoft.com/library/hh245116\(v=sql.110\).aspx)。</span><span class="sxs-lookup"><span data-stu-id="fe862-226">Configure [SQL Server 2012 Database Mail](http://msdn.microsoft.com/library/hh245116\(v=sql.110\).aspx).</span></span>  
  
 <span data-ttu-id="fe862-227">配置 [SQL Server 2014 数据库邮件](http://msdn.microsoft.com/library/hh245116\(v=sql.120\).aspx)。</span><span class="sxs-lookup"><span data-stu-id="fe862-227">Configure [SQL Server 2014 Database Mail](http://msdn.microsoft.com/library/hh245116\(v=sql.120\).aspx).</span></span>  
  
 <span data-ttu-id="fe862-228">**补充说明**</span><span class="sxs-lookup"><span data-stu-id="fe862-228">**Additional**</span></span>  
  
-   <span data-ttu-id="fe862-229">数据库邮件使用 SMTP 服务器发送 BAM 警报。</span><span class="sxs-lookup"><span data-stu-id="fe862-229">Database Mail uses an SMTP server to send the BAM Alerts.</span></span> <span data-ttu-id="fe862-230">在 BizTalk Server 上或在另一台 IIS 服务器上，可以本地安装 SMTP 服务器。</span><span class="sxs-lookup"><span data-stu-id="fe862-230">SMTP Server can be installed locally on the BizTalk Server or on another IIS server.</span></span> <span data-ttu-id="fe862-231">[附录 D：创建 SMTP 服务器](../install-and-config-guides/appendix-d-create-the-smtp-server.md)中列出了安装和配置 SMTP 服务器的步骤。</span><span class="sxs-lookup"><span data-stu-id="fe862-231">[Appendix D: Create the SMTP Server](../install-and-config-guides/appendix-d-create-the-smtp-server.md) lists the steps to install and configure a SMTP Server.</span></span>  
  
###  <a name="BKMK_SSNS"></a> <span data-ttu-id="fe862-232">使用 SQL Server 2008 R2 的 BAM 警报 – 安装 SQL Server 2005 Notification Services</span><span class="sxs-lookup"><span data-stu-id="fe862-232">BAM Alerts using SQL Server 2008 R2 – Install SQL Server 2005 Notification Services</span></span>  
  
1. <span data-ttu-id="fe862-233">转到 [SQL Server 2005 SP4 功能包](http://go.microsoft.com/fwlink/p/?LinkId=286285)。</span><span class="sxs-lookup"><span data-stu-id="fe862-233">Go to [Feature Pack for Microsoft SQL Server 2005 SP4](http://go.microsoft.com/fwlink/p/?LinkId=286285).</span></span>  
  
2. <span data-ttu-id="fe862-234">下载并安装以下组件的相应平台包：</span><span class="sxs-lookup"><span data-stu-id="fe862-234">Download and install the appropriate platform package for the following components:</span></span>  
  
    <span data-ttu-id="fe862-235">**Microsoft SQL Server Native Client**</span><span class="sxs-lookup"><span data-stu-id="fe862-235">**Microsoft SQL Server Native Client**</span></span>  
  
   - <span data-ttu-id="fe862-236">超链接"<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/sqlncli.msi>"X86 程序包 (sqlncli.msi)</span><span class="sxs-lookup"><span data-stu-id="fe862-236">HYPERLINK "<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/sqlncli.msi>" X86 Package (sqlncli.msi)</span></span>  
  
   - <span data-ttu-id="fe862-237">超链接"<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/sqlncli_x64.msi>"X64 程序包 (sqlncli_x64.msi)</span><span class="sxs-lookup"><span data-stu-id="fe862-237">HYPERLINK "<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/sqlncli_x64.msi>" X64 Package (sqlncli_x64.msi)</span></span>  
  
     <span data-ttu-id="fe862-238">**Microsoft SQL Server 2005 管理对象集合**</span><span class="sxs-lookup"><span data-stu-id="fe862-238">**Microsoft SQL Server 2005 Management Objects Collection**</span></span>  
  
   - <span data-ttu-id="fe862-239">超链接"<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_XMO.msi>"X86 程序包 (SQLServer2005_XMO.msi)</span><span class="sxs-lookup"><span data-stu-id="fe862-239">HYPERLINK "<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_XMO.msi>" X86 Package (SQLServer2005_XMO.msi)</span></span>  
  
   - <span data-ttu-id="fe862-240">超链接"<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_XMO_x64.msi>"X64 程序包 (SQLServer2005_XMO_x64.msi)</span><span class="sxs-lookup"><span data-stu-id="fe862-240">HYPERLINK "<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_XMO_x64.msi>" X64 Package (SQLServer2005_XMO_x64.msi)</span></span>  
  
     <span data-ttu-id="fe862-241">**Microsoft SQL Server 2005 Notification Services 客户端组件**</span><span class="sxs-lookup"><span data-stu-id="fe862-241">**Microsoft SQL Server 2005 Notification Services Client Components**</span></span>  
  
   - <span data-ttu-id="fe862-242">超链接"<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_NS.msi>"X86 程序包 (SQLServer2005_NS.msi)</span><span class="sxs-lookup"><span data-stu-id="fe862-242">HYPERLINK "<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_NS.msi>" X86 Package (SQLServer2005_NS.msi)</span></span>  
  
   - <span data-ttu-id="fe862-243">超链接"<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_NS_x64.msi>"X64 程序包 (SQLServer2005_NS_x64.msi)</span><span class="sxs-lookup"><span data-stu-id="fe862-243">HYPERLINK "<http://download.microsoft.com/download/3/1/6/316FADB2-E703-4351-8E9C-E0B36D9D697E/SQLServer2005_NS_x64.msi>" X64 Package (SQLServer2005_NS_x64.msi)</span></span>  
  
   <span data-ttu-id="fe862-244">**补充说明**</span><span class="sxs-lookup"><span data-stu-id="fe862-244">**Additional**</span></span>  
  
-   <span data-ttu-id="fe862-245">SQL Notification Services 不需要配置;仅安装 BizTalk Server 上。</span><span class="sxs-lookup"><span data-stu-id="fe862-245">SQL Notification Services does not need to be configured; only installed on the BizTalk Server.</span></span>  
  
##  <a name="BKMK_WIF"></a> <span data-ttu-id="fe862-246">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="fe862-246">Windows Identity Foundation</span></span>  
  
|                                                              |                                                                                                                                                                                      |
|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="fe862-247">Windows 8.1、 Windows Server 2012 和 Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="fe862-247">Windows 8.1, Windows Server 2012, and Windows Server 2012 R2</span></span> |                                <span data-ttu-id="fe862-248">Windows Identity Foundation 作为“打开或关闭 Windows 功能”中的功能包括在操作系统中。</span><span class="sxs-lookup"><span data-stu-id="fe862-248">Windows Identity Foundation is included with the operating system as a Feature in **Turn Windows features on or off**.</span></span>                                |
|                      <span data-ttu-id="fe862-249">Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="fe862-249">Windows Vista SP1</span></span>                       | <span data-ttu-id="fe862-250">下载位置[Windows Identity Foundation](http://www.microsoft.com/download/details.aspx?id=17331)超链接"<http://www.microsoft.com/download/details.aspx?id=17331>"。</span><span class="sxs-lookup"><span data-stu-id="fe862-250">Download available at [Windows Identity Foundation](http://www.microsoft.com/download/details.aspx?id=17331) HYPERLINK "<http://www.microsoft.com/download/details.aspx?id=17331>" .</span></span> |
  
 <span data-ttu-id="fe862-251">**补充说明**</span><span class="sxs-lookup"><span data-stu-id="fe862-251">**Additional**</span></span>  
  
-   <span data-ttu-id="fe862-252">Windows Identity Foundation (WIF) 是 SharePoint 适配器或 SharePoint Online 使用与 SharePoint 客户端对象模型 (CSOM) 时所必需的。</span><span class="sxs-lookup"><span data-stu-id="fe862-252">Windows Identity Foundation (WIF) is required for the SharePoint adapter or SharePoint Online when used with SharePoint Client Side Object Model (CSOM).</span></span> <span data-ttu-id="fe862-253">具体来说：</span><span class="sxs-lookup"><span data-stu-id="fe862-253">Specifically:</span></span>  
  
    |<span data-ttu-id="fe862-254">安装选项</span><span class="sxs-lookup"><span data-stu-id="fe862-254">Installation Option</span></span>|<span data-ttu-id="fe862-255">需要 WIF</span><span class="sxs-lookup"><span data-stu-id="fe862-255">WIF Required</span></span>|  
    |-------------------------|------------------|  
    |<span data-ttu-id="fe862-256">使用 CSOM 的 SharePoint 适配器</span><span class="sxs-lookup"><span data-stu-id="fe862-256">SharePoint Adapter with CSOM</span></span>|<span data-ttu-id="fe862-257">是</span><span class="sxs-lookup"><span data-stu-id="fe862-257">Yes</span></span>|  
    |<span data-ttu-id="fe862-258">使用 CSOM 的 SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="fe862-258">SharePoint Online with CSOM</span></span>|<span data-ttu-id="fe862-259">是</span><span class="sxs-lookup"><span data-stu-id="fe862-259">Yes</span></span>|  
    |<span data-ttu-id="fe862-260">SharePoint 适配器 Web Service （不推荐使用）</span><span class="sxs-lookup"><span data-stu-id="fe862-260">SharePoint Adapter Web Service (deprecated)</span></span>|<span data-ttu-id="fe862-261">“否”</span><span class="sxs-lookup"><span data-stu-id="fe862-261">No</span></span>|  
    |<span data-ttu-id="fe862-262">无 SharePoint</span><span class="sxs-lookup"><span data-stu-id="fe862-262">No SharePoint</span></span>|<span data-ttu-id="fe862-263">“否”</span><span class="sxs-lookup"><span data-stu-id="fe862-263">No</span></span>|  
  
-   <span data-ttu-id="fe862-264">[附录 b： 安装 Microsoft SharePoint 适配器](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)上的 SharePoint 安装选项提供特定信息。</span><span class="sxs-lookup"><span data-stu-id="fe862-264">[Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) provides specific information on the SharePoint installation options.</span></span>  
  
##  <a name="BKMK_WSS"></a> <span data-ttu-id="fe862-265">安装和配置 Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="fe862-265">Install and Configure Microsoft SharePoint</span></span>  
 <span data-ttu-id="fe862-266">安装 [SharePoint 2013](http://technet.microsoft.com/library/cc303424.aspx)</span><span class="sxs-lookup"><span data-stu-id="fe862-266">Install [SharePoint 2013](http://technet.microsoft.com/library/cc303424.aspx)</span></span>  
  
 <span data-ttu-id="fe862-267">安装 [SharePoint Online 服务](http://technet.microsoft.com/library/jj819267.aspx)</span><span class="sxs-lookup"><span data-stu-id="fe862-267">Install [SharePoint Online Service](http://technet.microsoft.com/library/jj819267.aspx)</span></span>  
  
 <span data-ttu-id="fe862-268">安装 [SharePoint Server 2010](http://technet.microsoft.com/library/cc303424\(v=office.14\).aspx)</span><span class="sxs-lookup"><span data-stu-id="fe862-268">Install [SharePoint Server 2010](http://technet.microsoft.com/library/cc303424\(v=office.14\).aspx)</span></span>  
  
 <span data-ttu-id="fe862-269">安装 [SharePoint 2007](http://technet.microsoft.com/library/cc303424\(v=office.12\).aspx)</span><span class="sxs-lookup"><span data-stu-id="fe862-269">Install [SharePoint 2007](http://technet.microsoft.com/library/cc303424\(v=office.12\).aspx)</span></span>  
  
 <span data-ttu-id="fe862-270">**补充说明**</span><span class="sxs-lookup"><span data-stu-id="fe862-270">**Additional**</span></span>  
  
-   <span data-ttu-id="fe862-271">如果在安装 SharePoint，必须在继续执行剩余的 BizTalk Server 必备组件之前执行操作。</span><span class="sxs-lookup"><span data-stu-id="fe862-271">If you are installing SharePoint, you must do so before continuing with the remaining BizTalk Server prerequisites.</span></span>  
  
-   <span data-ttu-id="fe862-272">安装和配置 SharePoint 包括下列过程：</span><span class="sxs-lookup"><span data-stu-id="fe862-272">Installing and configuring SharePoint consists of the following procedures:</span></span>  
  
    -   <span data-ttu-id="fe862-273">安装 SharePoint</span><span class="sxs-lookup"><span data-stu-id="fe862-273">Install SharePoint</span></span>  
  
    -   <span data-ttu-id="fe862-274">配置 SharePoint</span><span class="sxs-lookup"><span data-stu-id="fe862-274">Configure SharePoint</span></span>  
  
    -   <span data-ttu-id="fe862-275">将默认网站扩展为虚拟服务器</span><span class="sxs-lookup"><span data-stu-id="fe862-275">Extend the default Web site as a virtual server</span></span>  
  
-   <span data-ttu-id="fe862-276">[附录 B：安装 Microsoft SharePoint 适配器](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)描述了 BizTalk Server 的 SharePoint 适配器安装选项。</span><span class="sxs-lookup"><span data-stu-id="fe862-276">[Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) describes the SharePoint adapter installation options for BizTalk Server.</span></span>  
  
-   <span data-ttu-id="fe862-277">使用 SharePoint 适配器时，建议安装新 CSOM 选项（而不是 SharePoint Service Web Service）；相关说明请参阅[附录 B：安装 Microsoft SharePoint 适配器](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="fe862-277">When using the SharePoint adapter, it is recommended to install the new CSOM option instead of the SharePoint Service Web Service; described at [Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md).</span></span>  
  
##  <a name="BKMK_SharedMem"></a> <span data-ttu-id="fe862-278">禁用 Shared Memory 协议</span><span class="sxs-lookup"><span data-stu-id="fe862-278">Disable the Shared Memory Protocol</span></span>  
  
1. <span data-ttu-id="fe862-279">打开 **SQL Server 配置管理器**。</span><span class="sxs-lookup"><span data-stu-id="fe862-279">Open **SQL Server Configuration Manager**.</span></span>  
  
2. <span data-ttu-id="fe862-280">在“SQL Server 配置管理器”中，展开“SQL Server 网络配置”，然后选择“MSSQLSERVER 的协议”。</span><span class="sxs-lookup"><span data-stu-id="fe862-280">In **SQL Server Configuration Manager**, expand **SQL Server Network Configuration**, and then select **Protocols for MSSQLSERVER**.</span></span>  
  
3. <span data-ttu-id="fe862-281">右键单击“共享内存”，然后选择“禁用”。</span><span class="sxs-lookup"><span data-stu-id="fe862-281">Right-click **Shared Memory**, and then select **Disable**.</span></span>  
  
4. <span data-ttu-id="fe862-282">选择“SQL Server 服务”，右键单击“SQL Server (MSSQLSERVER)”，然后再选择“停止”。</span><span class="sxs-lookup"><span data-stu-id="fe862-282">Select **SQL Server Services**, right-click **SQL Server (MSSQLSERVER)**, and then select **Stop**.</span></span> <span data-ttu-id="fe862-283">该服务停止后，再次右键单击“SQL Server (MSSQLSERVER)”，然后选择“启动”。</span><span class="sxs-lookup"><span data-stu-id="fe862-283">After the service has stopped, right-click **SQL Server (MSSQLSERVER)** again, and then select **Start**.</span></span>  
  
5. <span data-ttu-id="fe862-284">关闭“SQL Server 配置管理器”。</span><span class="sxs-lookup"><span data-stu-id="fe862-284">Close **SQL Server Configuration Manager**.</span></span>  
  
   <span data-ttu-id="fe862-285">**补充说明**</span><span class="sxs-lookup"><span data-stu-id="fe862-285">**Additional**</span></span>  
  
-   <span data-ttu-id="fe862-286">在任务繁忙时（例如，客户端从同一计算机访问 SQL Server 时），SQL Server Shared Memory 协议可能会降低 BizTalk Server 性能。</span><span class="sxs-lookup"><span data-stu-id="fe862-286">Under certain stress conditions (such as clients accessing SQL Server from the same computer), the SQL Server Shared Memory protocol may lower BizTalk Server performance.</span></span> <span data-ttu-id="fe862-287">可以通过在“SQL Server 网络配置”中禁用 Shared Memory 网络协议来解决此行为。</span><span class="sxs-lookup"><span data-stu-id="fe862-287">You can resolve this behavior by disabling the Shared Memory network protocol in SQL Server Network Configuration.</span></span>  
  
-   <span data-ttu-id="fe862-288">ReplaceThisText</span><span class="sxs-lookup"><span data-stu-id="fe862-288">ReplaceThisText</span></span>  
  
##  <a name="BKMK_LocalAdmin"></a> <span data-ttu-id="fe862-289">加入本地管理员组</span><span class="sxs-lookup"><span data-stu-id="fe862-289">Join the Local Administrators Group</span></span>  
 <span data-ttu-id="fe862-290">**Windows Server 2012** : [Windows Server 2012： 如何将帐户添加到本地管理员组](http://social.technet.microsoft.com/wiki/contents/articles/13436.windows-server-2012-how-to-add-an-account-to-a-local-administrator-group.aspx)</span><span class="sxs-lookup"><span data-stu-id="fe862-290">**Windows Server 2012** : [Windows Server 2012: How to Add an Account to a Local Administrator Group](http://social.technet.microsoft.com/wiki/contents/articles/13436.windows-server-2012-how-to-add-an-account-to-a-local-administrator-group.aspx)</span></span>  
  
 <span data-ttu-id="fe862-291">**Windows 8.1**：若要在 Windows 8 上打开“本地用户和组”，请单击键盘上的 Windows 按钮，然后键入“组”。</span><span class="sxs-lookup"><span data-stu-id="fe862-291">**Windows 8.1**: To open Local Users and Groups on Windows 8, click the Windows button on the keyboard and type **groups**.</span></span> <span data-ttu-id="fe862-292">在“搜索”窗口中，单击“设置”。</span><span class="sxs-lookup"><span data-stu-id="fe862-292">In the Search window, click **Settings**.</span></span> <span data-ttu-id="fe862-293">在“结果”窗口中，单击“编辑本地用户和组”。</span><span class="sxs-lookup"><span data-stu-id="fe862-293">In the Results window, click **Edit local users and groups**.</span></span> <span data-ttu-id="fe862-294">单击“组”，然后双击“管理员”以添加帐户。</span><span class="sxs-lookup"><span data-stu-id="fe862-294">Click **Groups** and then double-click Administrators to add an account.</span></span>  
  
 <span data-ttu-id="fe862-295">**Windows 7 SP1**：单击“启动”。</span><span class="sxs-lookup"><span data-stu-id="fe862-295">**Windows 7 SP1**: Click Start.</span></span> <span data-ttu-id="fe862-296">在“搜索”文本框中，键入“计算机管理”，然后单击将其打开。</span><span class="sxs-lookup"><span data-stu-id="fe862-296">In the **Search** text box, type **Computer Management**, and click it to open.</span></span> <span data-ttu-id="fe862-297">展开“本地用户和组”，单击“组”，然后双击以添加帐户。</span><span class="sxs-lookup"><span data-stu-id="fe862-297">Expand **Local Users and Groups**, click **Groups**, and then double-click Administrators to add an account.</span></span>  
  
 <span data-ttu-id="fe862-298">**补充说明**</span><span class="sxs-lookup"><span data-stu-id="fe862-298">**Additional**</span></span>  
  
-   <span data-ttu-id="fe862-299">必须是本地 Administrators 组的成员才能安装和配置 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="fe862-299">You must be a member of the local Administrators group to install and configure BizTalk Server.</span></span>  
  
##  <a name="BKMK_AppLog"></a> <span data-ttu-id="fe862-300">配置应用程序事件日志</span><span class="sxs-lookup"><span data-stu-id="fe862-300">Configure the Application Event Log</span></span>  
  
1. <span data-ttu-id="fe862-301">打开“事件查看器”：</span><span class="sxs-lookup"><span data-stu-id="fe862-301">Open **Event Viewer**:</span></span>  
  
    <span data-ttu-id="fe862-302">**Windows Server 2012** ： 单击键盘和类型上的 Windows 按钮**事件查看器**。</span><span class="sxs-lookup"><span data-stu-id="fe862-302">**Windows Server 2012** : Click the Windows button on the keyboard and type **Event Viewer**.</span></span> <span data-ttu-id="fe862-303">在“结果”窗口中，单击“事件查看器”。</span><span class="sxs-lookup"><span data-stu-id="fe862-303">In the Results window, click **Event Viewer**.</span></span>  
  
    <span data-ttu-id="fe862-304">**Windows 8.1**：单击键盘上的 Windows 按钮，并键入“事件查看器”。</span><span class="sxs-lookup"><span data-stu-id="fe862-304">**Windows 8.1**: Click the Windows button on the keyboard and type **Event Viewer**.</span></span> <span data-ttu-id="fe862-305">在“搜索”窗口中，单击“设置”。</span><span class="sxs-lookup"><span data-stu-id="fe862-305">In the Search window, click **Settings**.</span></span> <span data-ttu-id="fe862-306">在“结果”窗口中，单击“查看事件日志”。</span><span class="sxs-lookup"><span data-stu-id="fe862-306">In the Results window, click **View event logs**.</span></span>  
  
    <span data-ttu-id="fe862-307">**Windows 7 SP1**：单击“启动”。</span><span class="sxs-lookup"><span data-stu-id="fe862-307">**Windows 7 SP1**: Click Start.</span></span> <span data-ttu-id="fe862-308">在“搜索”文本框中，键入**事件查看器**，然后单击将其打开。</span><span class="sxs-lookup"><span data-stu-id="fe862-308">In the **Search** text box, type **Event Viewer**, and click it to open.</span></span>  
  
2. <span data-ttu-id="fe862-309">展开“Windows 日志”，右键单击“应用程序”，然后单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="fe862-309">Expand **Windows Logs**, right-click **Application**, and then click **Properties**.</span></span> <span data-ttu-id="fe862-310">在“日志属性”中：</span><span class="sxs-lookup"><span data-stu-id="fe862-310">In **Log Properties**:</span></span>  
  
   -   <span data-ttu-id="fe862-311">若要确定可用空间，请比较“日志大小”和“最大日志大小”属性。</span><span class="sxs-lookup"><span data-stu-id="fe862-311">To determine the available space, compare the **Log Size** and the **Maximum log size** properties.</span></span>  
  
   -   <span data-ttu-id="fe862-312">若要提供更多的空间，请在“最大日志大小”中输入一个更大的值。</span><span class="sxs-lookup"><span data-stu-id="fe862-312">To provide more space, enter a higher number in **Maximum log size**.</span></span>  
  
   -   <span data-ttu-id="fe862-313">若要在日志变满时启用对旧事件的覆盖功能，请选择“按需要覆盖事件”。</span><span class="sxs-lookup"><span data-stu-id="fe862-313">To enable overwriting of old events when the log becomes full, select **Overwrite events as needed**.</span></span>  
  
   -   <span data-ttu-id="fe862-314">若要清除日志事件，请选择“清除日志”。</span><span class="sxs-lookup"><span data-stu-id="fe862-314">To clear the log events, select **Clear log**.</span></span>  
  
3. <span data-ttu-id="fe862-315">单击“确定”关闭“事件查看器”。</span><span class="sxs-lookup"><span data-stu-id="fe862-315">Click **OK** to close the **Event Viewer**.</span></span>  
  
   <span data-ttu-id="fe862-316">**补充说明**</span><span class="sxs-lookup"><span data-stu-id="fe862-316">**Additional**</span></span>  
  
-   <span data-ttu-id="fe862-317">BizTalk Server 安装程序会将事件记录保留在应用程序事件日志中。</span><span class="sxs-lookup"><span data-stu-id="fe862-317">BizTalk Server setup keeps a record of events in the Application Event Log.</span></span> <span data-ttu-id="fe862-318">日志中所需的空间量可能会超出其限制，具体取决于已安装的 BizTalk Server 功能。</span><span class="sxs-lookup"><span data-stu-id="fe862-318">Depending on the BizTalk Server features installed, the amount of space required in the log may exceed its limit.</span></span> <span data-ttu-id="fe862-319">如果在 BizTalk Server 安装期间应用程序事件日志空间不足，安装将失败。</span><span class="sxs-lookup"><span data-stu-id="fe862-319">If the application event log runs out of space during BizTalk Server setup, the installation fails.</span></span> <span data-ttu-id="fe862-320">更改“应用程序事件日志”设置可防止此故障。</span><span class="sxs-lookup"><span data-stu-id="fe862-320">Changing the Application Event Log settings prevents this failure.</span></span>  
  
## <a name="next"></a><span data-ttu-id="fe862-321">Next</span><span class="sxs-lookup"><span data-stu-id="fe862-321">Next</span></span>  
 [<span data-ttu-id="fe862-322">选择 BizTalk Server 功能和组件</span><span class="sxs-lookup"><span data-stu-id="fe862-322">Choose BizTalk Server Features and Components</span></span>](http://msdn.microsoft.com/library/b8c43fcf-9e5c-48ba-830b-13a5177e30f0)  
  
## <a name="see-also"></a><span data-ttu-id="fe862-323">请参阅</span><span class="sxs-lookup"><span data-stu-id="fe862-323">See Also</span></span>  
 <span data-ttu-id="fe862-324">[BizTalk Server 2013 和 2013 R2 安装概述](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5) </span><span class="sxs-lookup"><span data-stu-id="fe862-324">[Installation Overview for BizTalk Server 2013 and 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5) </span></span>  
 <span data-ttu-id="fe862-325">[附录 A：无提示安装](../install-and-config-guides/appendix-a-silent-installation.md) </span><span class="sxs-lookup"><span data-stu-id="fe862-325">[Appendix A: Silent Installation](../install-and-config-guides/appendix-a-silent-installation.md) </span></span>  
 <span data-ttu-id="fe862-326">[附录 B：安装 Microsoft SharePoint 适配器](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="fe862-326">[Appendix B: Install the Microsoft SharePoint Adapter](../install-and-config-guides/appendix-b-install-the-microsoft-sharepoint-adapter.md) </span></span>  
 <span data-ttu-id="fe862-327">[附录 C：可再发行的 CAB 文件](../install-and-config-guides/appendix-c-redistributable-cab-files.md) </span><span class="sxs-lookup"><span data-stu-id="fe862-327">[Appendix C: Redistributable CAB Files](../install-and-config-guides/appendix-c-redistributable-cab-files.md) </span></span>  
 [<span data-ttu-id="fe862-328">附录 D：创建 SMTP 服务器</span><span class="sxs-lookup"><span data-stu-id="fe862-328">Appendix D: Create the SMTP Server</span></span>](../install-and-config-guides/appendix-d-create-the-smtp-server.md)
