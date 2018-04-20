---
title: HTTPSSO （BizTalk Server 示例） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP adapters, examples
- SSO, examples
- SSO, HTTP adapters
- examples, HTTP adapters
- HTTP adapters, SSO
- examples, SSO
ms.assetid: 322360df-81d2-4a73-9512-bda9382351a2
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41956d9e10cba87e0e1a1f44d49dd8ec8b6039bc
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2018
---
# <a name="httpsso-biztalk-server-sample"></a><span data-ttu-id="665e8-102">HTTPSSO （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="665e8-102">HTTPSSO (BizTalk Server Sample)</span></span>
<span data-ttu-id="665e8-103">HTTPSSO 示例演示如何使用 Microsoft 的企业单一登录 (SSO) 功能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HTTP 适配器。</span><span class="sxs-lookup"><span data-stu-id="665e8-103">The HTTPSSO sample demonstrates how to use the Enterprise Single Sign-On (SSO) feature with the Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="665e8-104">本示例不支持 64 位操作系统。</span><span class="sxs-lookup"><span data-stu-id="665e8-104">This sample is not supported on 64-bit operating systems.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="665e8-105">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="665e8-105">What This Sample Does</span></span>  
 <span data-ttu-id="665e8-106">本示例演示一个端到端的应用方案，该方案使用 SSO 及 BizTalk HTTP 发送和接收适配器来模拟 SSO 如何允许用户在通过 Windows 的身份验证之后无需提供其他凭据即可登录到非 Microsoft Windows 系统。</span><span class="sxs-lookup"><span data-stu-id="665e8-106">This sample demonstrates an end-to-end scenario that uses SSO and the BizTalk HTTP Send and Receive adapters to simulate how SSO allows a user to avoid supplying additional credentials to log on to non-Microsoft Windows systems after Windows authenticates them.</span></span>  
  
 <span data-ttu-id="665e8-107">此外，本示例还使用 SSO 的管理和映射模块来创建使用 SSO 的互操作客户端 DLL 的关联应用程序和 SSO 映射。</span><span class="sxs-lookup"><span data-stu-id="665e8-107">The sample also uses the administration and mapping modules of SSO to create affiliate application and SSO mappings using the interop client DLL of SSO.</span></span>  
  
 <span data-ttu-id="665e8-108">示例通过实现端到端方案的以下几个方面演示了 SSO 的使用方法：</span><span class="sxs-lookup"><span data-stu-id="665e8-108">The sample demonstrates the use of SSO by implementing the following aspects of an end-to-end scenario:</span></span>  
  
-   <span data-ttu-id="665e8-109">用户界面，由配置为使用 Windows 集成身份验证的一个 Microsoft Internet 信息服务 (IIS) 虚拟目录表示。</span><span class="sxs-lookup"><span data-stu-id="665e8-109">User interface, represented by a Microsoft Internet Information Services (IIS) virtual directory configured to use Windows integrated authentication.</span></span>  
  
-   <span data-ttu-id="665e8-110">后端系统，由配置为使用基本身份验证的一个 IIS 虚拟目录表示。</span><span class="sxs-lookup"><span data-stu-id="665e8-110">Back-end system, represented by an IIS virtual directory configured to use basic authentication.</span></span>  
  
-   <span data-ttu-id="665e8-111">后端数据库，由 SQL 示例数据库 Northwind 表示。</span><span class="sxs-lookup"><span data-stu-id="665e8-111">Back-end database, represented by the SQL sample database Northwind.</span></span>  
  
 <span data-ttu-id="665e8-112">此示例假定你已安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 SSO。</span><span class="sxs-lookup"><span data-stu-id="665e8-112">This sample assumes that you have installed [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and SSO.</span></span> <span data-ttu-id="665e8-113">你必须具有管理员特权[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，IIS、 SSO，和在 Windows XP 专业版上的 COM +。</span><span class="sxs-lookup"><span data-stu-id="665e8-113">You must have administrator privileges for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], IIS, SSO, and COM+ on Windows XP Professional.</span></span> <span data-ttu-id="665e8-114">此外，您还必须是 SSO Administrators、BizTalk Server Administrators 和 BizTalk Isolated Host Users Windows 组的成员。</span><span class="sxs-lookup"><span data-stu-id="665e8-114">You must also be a member of SSO Administrators, BizTalk Server Administrators, and BizTalk Isolated Host Users Windows groups.</span></span>  
  
 <span data-ttu-id="665e8-115">若要有效利用本示例，您应当充分了解 SSO 和 BizTalk HTTP 适配器。</span><span class="sxs-lookup"><span data-stu-id="665e8-115">Effective use of this sample assumes that you have sufficient knowledge of SSO and the BizTalk HTTP adapter.</span></span> <span data-ttu-id="665e8-116">例如，您应当知道关联应用程序在 SSO 的上下文环境下的含义。</span><span class="sxs-lookup"><span data-stu-id="665e8-116">For example, you should know what an affiliate application is in the context of SSO.</span></span> <span data-ttu-id="665e8-117">有关这些主题的信息，请参阅[使用 SSO](../core/using-sso.md)。</span><span class="sxs-lookup"><span data-stu-id="665e8-117">For information about these topics, see [Using SSO](../core/using-sso.md).</span></span> <span data-ttu-id="665e8-118">另请参阅[HTTP 适配器](../core/http-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="665e8-118">Also see [HTTP Adapter](../core/http-adapter.md).</span></span>  
  
 <span data-ttu-id="665e8-119">在完成配置之后，本示例的工作方式将如下所示：</span><span class="sxs-lookup"><span data-stu-id="665e8-119">After you complete the configuration, this sample works as follows:</span></span>  
  
1.  <span data-ttu-id="665e8-120">当你单击 **完成** 向导应用程序，它包含此示例的用户界面，在 Internet Explorer 的实例启动，并将传递 BizTalk HTTP 接收 DLL 的 URL。</span><span class="sxs-lookup"><span data-stu-id="665e8-120">When you click **Finish** in the wizard application that comprises the user interface for this sample, an instance of Internet Explorer starts and passes the URL of the BizTalk HTTP Receive DLL.</span></span>  
  
2.  <span data-ttu-id="665e8-121">在 SSO 的帮助下，BizTalk Server 可有效地将 HTTP 请求转发到 IIS 虚拟目录中的 EmployeeData.aspx 文件，该目录已配置为使用基本身份验证。</span><span class="sxs-lookup"><span data-stu-id="665e8-121">BizTalk Server, with the help of SSO, effectively forwards the HTTP request to the file EmployeeData.aspx in an IIS virtual directory that has been configured with basic authentication.</span></span> <span data-ttu-id="665e8-122">此 ASPX 文件模拟一个进入非 Windows 后端系统的入口点。</span><span class="sxs-lookup"><span data-stu-id="665e8-122">This ASPX file simulates the entry point into a non-Windows back-end system.</span></span> <span data-ttu-id="665e8-123">由于您所使用的是 SSO，所以 HTTP 请求中已包含配置的凭据，这些凭据模拟了所模拟后端系统的登录帐户。</span><span class="sxs-lookup"><span data-stu-id="665e8-123">Because you are using SSO, the HTTP request includes the configured credentials that simulate a logon account to the simulated back-end system.</span></span>  
  
3.  <span data-ttu-id="665e8-124">该 ASPX 文件访问 SQL 示例数据库 Northwind 的一个修改过的版本，检索与所模拟后端系统凭据相对应的雇员数据。</span><span class="sxs-lookup"><span data-stu-id="665e8-124">The ASPX file accesses a modified version of the SQL sample database Northwind to retrieve employee data corresponding to the simulated back-end system credentials.</span></span>  
  
4.  <span data-ttu-id="665e8-125">ASPX 文件在 HTTP 响应中返回检索到的雇员数据。</span><span class="sxs-lookup"><span data-stu-id="665e8-125">The ASPX file returns the retrieved employee data in an HTTP response.</span></span>  
  
5.  <span data-ttu-id="665e8-126">BizTalk Server 将该 HTTP 响应发送到 Internet Explorer，后者向用户显示返回的雇员数据。</span><span class="sxs-lookup"><span data-stu-id="665e8-126">BizTalk Server routes the HTTP response to Internet Explorer, which displays the returned employee data to the user.</span></span>  
  
 <span data-ttu-id="665e8-127">如果绕过 BizTalk Server 和 SSO，并且直接浏览 EmployeeData.aspx 文件，会显示一个 Windows 对话框，提示您输入凭据。</span><span class="sxs-lookup"><span data-stu-id="665e8-127">If you bypass BizTalk Server and SSO, and browse directly to the file EmployeeData.aspx, a Windows dialog box will prompt you for your credentials.</span></span>  
  
 <span data-ttu-id="665e8-128">有关演示如何使用命令行实用工具 ssomanage.exe 配置 SSO，如创建关联应用程序和用户映射的示例，请参阅[管理 （BizTalk Server 示例）](../core/manage-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="665e8-128">For a sample that shows how to use the command-line utility ssomanage.exe to configure SSO, such as creating affiliate applications and user mappings, see [Manage (BizTalk Server Sample)](../core/manage-biztalk-server-sample.md).</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="665e8-129">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="665e8-129">Where to Find This Sample</span></span>  
 <span data-ttu-id="665e8-130">\<*示例路径*\>\SSO\HTTPSSO\\</span><span class="sxs-lookup"><span data-stu-id="665e8-130">\<*Samples Path*\>\SSO\HTTPSSO\\</span></span>  
  
 <span data-ttu-id="665e8-131">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="665e8-131">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="665e8-132">檔案</span><span class="sxs-lookup"><span data-stu-id="665e8-132">File(s)</span></span>|<span data-ttu-id="665e8-133">Description</span><span class="sxs-lookup"><span data-stu-id="665e8-133">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="665e8-134">AssemblyInfo.cs，SsoSample.csproj</span><span class="sxs-lookup"><span data-stu-id="665e8-134">AssemblyInfo.cs, SsoSample.csproj</span></span>|<span data-ttu-id="665e8-135">本 HTTP SSO 示例的项目文件和相关文件。</span><span class="sxs-lookup"><span data-stu-id="665e8-135">Project and related files for this HTTP SSO sample.</span></span>|  
|<span data-ttu-id="665e8-136">SsoSample.cs</span><span class="sxs-lookup"><span data-stu-id="665e8-136">SsoSample.cs</span></span>|<span data-ttu-id="665e8-137">作为本示例重要组成部分的 HTTP SSO 图形应用程序的顶层 Microsoft Visual C# 源文件。</span><span class="sxs-lookup"><span data-stu-id="665e8-137">Top-level Microsoft Visual C# source file for the HTTP SSO graphical application that constitutes much of this sample.</span></span> <span data-ttu-id="665e8-138">此文件包含一个名为类中的 SSO 配置代码 **SsoConfigurator** 最终是此示例的点。</span><span class="sxs-lookup"><span data-stu-id="665e8-138">This file contains the SSO configuration code, in a class named **SsoConfigurator** that is ultimately the point of this sample.</span></span>|  
|<span data-ttu-id="665e8-139">\Scripts 文件夹的内容：</span><span class="sxs-lookup"><span data-stu-id="665e8-139">In the \Scripts folder:</span></span><br /><br /> <span data-ttu-id="665e8-140">EmployeeData.aspx</span><span class="sxs-lookup"><span data-stu-id="665e8-140">EmployeeData.aspx</span></span>|<span data-ttu-id="665e8-141">用于在雇员发出请求以查看个人数据（无论是直接浏览还是使用 SSO）时访问和查询后端数据库（在本例中，为 SQL Northwind 数据库）。</span><span class="sxs-lookup"><span data-stu-id="665e8-141">Used to access and query the back-end database (in this case, the SQL Northwind database) when an employee initiates a request to view personal data, either directly or by using SSO.</span></span>|  
|<span data-ttu-id="665e8-142">\Scripts 文件夹的内容：</span><span class="sxs-lookup"><span data-stu-id="665e8-142">In the \Scripts folder:</span></span><br /><br /> <span data-ttu-id="665e8-143">ValidateUser.aspx</span><span class="sxs-lookup"><span data-stu-id="665e8-143">ValidateUser.aspx</span></span>|<span data-ttu-id="665e8-144">用于验证用户并报告用户是否为有效用户的简单测试（无论是直接浏览还是使用 SSO）。</span><span class="sxs-lookup"><span data-stu-id="665e8-144">Simple test to validate a user and report if that user was validated, either directly or by using SSO.</span></span>|  
|<span data-ttu-id="665e8-145">\UI 文件夹的内容：</span><span class="sxs-lookup"><span data-stu-id="665e8-145">In the \UI folder:</span></span><br /><br /> <span data-ttu-id="665e8-146">AddApplication.cs、AddApplication.resx、AddMapping.cs、AddMapping.resx、App.ico、BtsPage.cs、BtsPage.resx、ExecutePage.cs、ExecutePage.resx、FinishPage.cs、FinishPage.resx、IisPage.cs、IisPage.resx、InfoPage.cs、InfoPage.resx、PageBase.cs、PageBase.resx、SsoPage.cs、SsoPage.resx、SsoSampleWizard.cs、SsoSampleWizard.resx、WelcomePage.cs、WelcomePage.resx、WorkPage.cs、WorkPage.resx</span><span class="sxs-lookup"><span data-stu-id="665e8-146">AddApplication.cs, AddApplication.resx, AddMapping.cs, AddMapping.resx, App.ico, BtsPage.cs, BtsPage.resx, ExecutePage.cs, ExecutePage.resx, FinishPage.cs, FinishPage.resx, IisPage.cs, IisPage.resx, InfoPage.cs, InfoPage.resx, PageBase.cs, PageBase.resx, SsoPage.cs, SsoPage.resx, SsoSampleWizard.cs, SsoSampleWizard.resx, WelcomePage.cs, WelcomePage.resx, WorkPage.cs, WorkPage.resx</span></span>|<span data-ttu-id="665e8-147">辅助性的 Visual C# 源文件及其关联的 XML 格式的资源文件，这些文件用于构成了示例重要组成部分的 HTTP SSO 图形应用程序。</span><span class="sxs-lookup"><span data-stu-id="665e8-147">Auxiliary Visual C# source files, and their associated XML-formatted resource files, for the HTTP SSO graphical application that constitutes much of this sample.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="665e8-148">生成并初始化此示例</span><span class="sxs-lookup"><span data-stu-id="665e8-148">Building and Initializing This Sample</span></span>  
  
#### <a name="to-build-and-initialize-the-httpsso-sample"></a><span data-ttu-id="665e8-149">生成和初始化 HTTPSSO 示例</span><span class="sxs-lookup"><span data-stu-id="665e8-149">To build and initialize the HTTPSSO sample</span></span>  
  
1.  <span data-ttu-id="665e8-150">创建 Microsoft Internet 信息服务 (IIS) 可用于进行基本身份验证的一个本地 Windows 帐户。</span><span class="sxs-lookup"><span data-stu-id="665e8-150">Create a local Windows account that Microsoft Internet Information Services (IIS) can use for basic authentication.</span></span> <span data-ttu-id="665e8-151">SSO 将 Windows 域帐户映射到该本地 Windows 帐户。</span><span class="sxs-lookup"><span data-stu-id="665e8-151">SSO maps the Windows domain account to this local Windows account.</span></span> <span data-ttu-id="665e8-152">例如，可使用您的名字创建一个本地 Windows 帐户。</span><span class="sxs-lookup"><span data-stu-id="665e8-152">For example, use your last name to create a local Windows account.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="665e8-153">如果您使用的计算机是一台域控制器，可以创建域帐户并将您所登录的域帐户映射到此帐户。</span><span class="sxs-lookup"><span data-stu-id="665e8-153">If you are running on a domain controller, you can create domain accounts and map your logged on domain account to this account.</span></span>  
  
2.  <span data-ttu-id="665e8-154">使用 Microsoft SQL Server 企业管理器，打开 **员工** 表在 Northwind 示例数据库中，并将与你刚刚创建，包括各列的示例数据的本地 Windows 帐户相对应的行。</span><span class="sxs-lookup"><span data-stu-id="665e8-154">Using Microsoft SQL Server Enterprise Manager, open the **Employees** table in the Northwind sample database, and then add a row corresponding to the local Windows account that you just created, including sample data for the various columns.</span></span> <span data-ttu-id="665e8-155">您在 Employees 表的 LastName 列中添加的值必须与您在步骤 1 中添加的本地 Windows 帐户的用户名相同。</span><span class="sxs-lookup"><span data-stu-id="665e8-155">The value you add to the LastName column in the Employees table must be the same as the user name of the local Windows account you added in step 1.</span></span>  
  
3.  <span data-ttu-id="665e8-156">确保 ASP.NET 帐户 (ASPNET) 对 Northwind 数据库拥有读取权限。</span><span class="sxs-lookup"><span data-stu-id="665e8-156">Ensure the ASP.NET account (ASPNET) has read privileges to the Northwind database.</span></span>  
  
4.  <span data-ttu-id="665e8-157">打开项目文件 SsoSample.csproj 使用 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="665e8-157">Open the project file SsoSample.csproj using Visual Studio.</span></span>  
  
5.  <span data-ttu-id="665e8-158">在“生成”  菜单上，单击“生成解决方案” 。</span><span class="sxs-lookup"><span data-stu-id="665e8-158">On the **Build** menu, click **Build Solution**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="665e8-159">可能要求你保存解决方案文件，然后生成才能继续。</span><span class="sxs-lookup"><span data-stu-id="665e8-159">You may be asked to save a solution file before the build can proceed.</span></span>  
  
     <span data-ttu-id="665e8-160">如果项目，找不到以下 BizTalk 程序集引用，将其删除，重新将其添加从指定的位置，并再次生成︰</span><span class="sxs-lookup"><span data-stu-id="665e8-160">If you cannot find the following BizTalk assembly references for the project, delete them, re-add them from the indicated locations, and build again:</span></span>  
  
    -   <span data-ttu-id="665e8-161">**Microsoft.BizTalk.ExplorerOM**。</span><span class="sxs-lookup"><span data-stu-id="665e8-161">**Microsoft.BizTalk.ExplorerOM**.</span></span> <span data-ttu-id="665e8-162">默认情况下，Microsoft.BizTalk.ExplorerOM.dll 文件位于文件夹中[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]开发人员工具\\。</span><span class="sxs-lookup"><span data-stu-id="665e8-162">By default, the Microsoft.BizTalk.ExplorerOM.dll file is located in the folder [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Developer Tools\\.</span></span>  
  
    -   <span data-ttu-id="665e8-163">**Microsoft.BizTalk.SSOClient.Interop**。</span><span class="sxs-lookup"><span data-stu-id="665e8-163">**Microsoft.BizTalk.SSOClient.Interop**.</span></span> <span data-ttu-id="665e8-164">默认情况下，Microsoft.BizTalk.Interop.SSOClient.dll 文件位于文件夹中\< *ProgramFiles*\>上单一登录的 \Common Files\Enterprise\\。</span><span class="sxs-lookup"><span data-stu-id="665e8-164">By default, the Microsoft.BizTalk.Interop.SSOClient.dll file is located in the folder \<*ProgramFiles*\>\Common Files\Enterprise Single Sign-On\\.</span></span>  
  
     <span data-ttu-id="665e8-165">这将产生可执行文件的以下文件夹中的 SsoSample.exe:</span><span class="sxs-lookup"><span data-stu-id="665e8-165">This produces the executable file SsoSample.exe in the following folder:</span></span>  
  
     <span data-ttu-id="665e8-166">\<*示例路径*\>\SSO\HTTPSSO\bin\Debug\\</span><span class="sxs-lookup"><span data-stu-id="665e8-166">\<*Samples Path*\>\SSO\HTTPSSO\bin\Debug\\</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="665e8-167">运行本示例</span><span class="sxs-lookup"><span data-stu-id="665e8-167">Running This Sample</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="665e8-168">如果在 IIS 6.0 上以辅助进程隔离模式运行本示例，将为两个虚拟目录都创建应用程序池。</span><span class="sxs-lookup"><span data-stu-id="665e8-168">If you run this sample on IIS 6.0 in Worker Process Isolation Mode, application pools are created for both virtual directories.</span></span> <span data-ttu-id="665e8-169">Windows 帐户 （你可以配置在 Internet 信息服务管理器标识） 中，你必须手动配置这些两个应用程序池标识。</span><span class="sxs-lookup"><span data-stu-id="665e8-169">You must manually configure identity for these two application pools in your Windows account (you can configure identity in Internet Information Services Manager).</span></span>  
  
#### <a name="to-run-the-httpsso-sample"></a><span data-ttu-id="665e8-170">若要运行 HTTPSSO 示例</span><span class="sxs-lookup"><span data-stu-id="665e8-170">To run the HTTPSSO sample</span></span>  
  
1.  <span data-ttu-id="665e8-171">运行在以下文件夹中找到的可执行文件 SsoSample.exe:</span><span class="sxs-lookup"><span data-stu-id="665e8-171">Run the executable file SsoSample.exe, found in the following folder:</span></span>  
  
     <span data-ttu-id="665e8-172">\<*示例路径*\>\SSO\HTTPSSO\bin\Debug\\</span><span class="sxs-lookup"><span data-stu-id="665e8-172">\<*Samples Path*\>\SSO\HTTPSSO\bin\Debug\\</span></span>  
  
     <span data-ttu-id="665e8-173">此示例向导应用程序打开。</span><span class="sxs-lookup"><span data-stu-id="665e8-173">The wizard application for this sample opens.</span></span>  
  
2.  <span data-ttu-id="665e8-174">在欢迎页上，配置 IIS、 SSO 和 BizTalk，接受默认设置，然后单击 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="665e8-174">On the Welcome page, accept the default setting for configuring IIS, SSO, and BizTalk, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="665e8-175">在 IIS 配置页上，接受两个你想要创建，，然后单击的 IIS 虚拟目录的默认设置 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="665e8-175">On the IIS Configuration page, accept the default settings for the two IIS virtual directories you want to create, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="665e8-176">在 SSO 配置页上，接受默认设置为关联应用程序，这是可访问使用 **添加应用程序** 按钮。</span><span class="sxs-lookup"><span data-stu-id="665e8-176">On the SSO Configuration page, accept the default settings for the affiliate application, which is accessible using the **Add application** button.</span></span>  
  
5.  <span data-ttu-id="665e8-177">在 SSO 配置页上，接受大多数用户映射中，默认设置可访问使用 **添加映射** 按钮。</span><span class="sxs-lookup"><span data-stu-id="665e8-177">On the SSO Configuration page, accept most of the default settings for the user mappings, accessible using the **Add mapping** button.</span></span> <span data-ttu-id="665e8-178">提供基于时生成并初始化此示例添加的本地 Windows 帐户的以下两个设置的值。</span><span class="sxs-lookup"><span data-stu-id="665e8-178">Provide values for the following two settings based on the local Windows account you added when building and initializing this sample.</span></span>  
  
    |<span data-ttu-id="665e8-179">设置</span><span class="sxs-lookup"><span data-stu-id="665e8-179">Setting</span></span>|<span data-ttu-id="665e8-180">“值”</span><span class="sxs-lookup"><span data-stu-id="665e8-180">Value</span></span>|  
    |-------------|-----------|  
    |<span data-ttu-id="665e8-181">外部用户名称</span><span class="sxs-lookup"><span data-stu-id="665e8-181">External user name</span></span>|<span data-ttu-id="665e8-182">设置为添加的本地 Windows 用户帐户名称。</span><span class="sxs-lookup"><span data-stu-id="665e8-182">Set to the added local Windows user account name.</span></span>|  
    |<span data-ttu-id="665e8-183">外部用户密码</span><span class="sxs-lookup"><span data-stu-id="665e8-183">External user password</span></span>|<span data-ttu-id="665e8-184">将设置为添加的本地 Windows 用户帐户密码。</span><span class="sxs-lookup"><span data-stu-id="665e8-184">Set to the added local Windows user account password.</span></span>|  
  
6.  <span data-ttu-id="665e8-185">在 SSO 配置页面上单击 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="665e8-185">On the SSO Configuration page, click **Next**.</span></span>  
  
7.  <span data-ttu-id="665e8-186">在 BizTalk 配置页上，接受默认设置为发送和接收端口，以此类推，，然后单击 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="665e8-186">On the BizTalk Configuration page, accept the default settings for the send and receive ports, and so on, and then click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="665e8-187">你可以更改默认发送端口设置从 **EmployeeData.aspx** 到 **ValidateUser.aspx** 如果你想要查看简单的用户验证，而不是示例数据源自罗斯文 SQL 数据库的员工表。</span><span class="sxs-lookup"><span data-stu-id="665e8-187">You can change the default send port setting from **EmployeeData.aspx** to **ValidateUser.aspx** if you want to see simple user validation rather than sample data pulled from the Employee table of the Northwinds SQL database.</span></span> <span data-ttu-id="665e8-188">进行此更改更改后单击浏览器中显示的输出的性质 **完成** 在步骤 9。</span><span class="sxs-lookup"><span data-stu-id="665e8-188">Making this change changes the nature of the output displayed in the browser after clicking **Finish** in step 9.</span></span>  
  
8.  <span data-ttu-id="665e8-189">查看对应于正在执行的 IIS、 SSO 和 BizTalk 配置的状态消息。</span><span class="sxs-lookup"><span data-stu-id="665e8-189">Review the status messages corresponding to the IIS, SSO, and BizTalk configuration being performed.</span></span> <span data-ttu-id="665e8-190">你可以找到在此阶段运行的代码 **IisConfigurator**, ，**SsoConfigurator**, ，和 **BtsConfigurator** SsoSample.cs 文件中定义的类。</span><span class="sxs-lookup"><span data-stu-id="665e8-190">You can find the code that is run during this phase in the **IisConfigurator**, **SsoConfigurator**, and **BtsConfigurator** classes defined in the file SsoSample.cs.</span></span> <span data-ttu-id="665e8-191">已完成配置后，单击 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="665e8-191">After configuration has completed, click **Next**.</span></span>  
  
9. <span data-ttu-id="665e8-192">在向导应用程序的最后一页，接受默认设置**启动浏览器显示在**(选中的复选框和文本框中的 url http://localhost/SsoSampleBizTalkHttpReceive/BTSHttpReceive.dll? <message/>)，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="665e8-192">On the final page of the wizard application, accept the default settings for **Start browser at** (a selected check box and a text box with the URL http://localhost/SsoSampleBizTalkHttpReceive/BTSHttpReceive.dll?<message/>), and then click **Finish**.</span></span>  
  
     <span data-ttu-id="665e8-193">Internet Explorer 的实例将打开，并且很快显示添加到罗斯文 SQL 数据库的员工表的示例员工数据。</span><span class="sxs-lookup"><span data-stu-id="665e8-193">An instance of Internet Explorer will open, and soon display the sample employee data that you added to the Employee table of the Northwinds SQL database.</span></span>  
  
 <span data-ttu-id="665e8-194">为了进行比较，可以跳过 BizTalk 和 SSO，并浏览直接到 ASPX 文件之一︰</span><span class="sxs-lookup"><span data-stu-id="665e8-194">For comparison purposes, you can bypass BizTalk and SSO and browse directly to either of the ASPX files:</span></span>  
  
-   http://localhost/SsoSampleServerApplication/ValidateUser.aspx  
  
-   http://localhost/SsoSampleServerApplication/EmployeeData.aspx  
  
 <span data-ttu-id="665e8-195">在这两种情况下，由于你绕过 BizTalk 和 SSO，会提示你对身份验证信息 （使用你之前创建的本地 Windows 帐户信息） 的 iis。</span><span class="sxs-lookup"><span data-stu-id="665e8-195">In both cases, because you bypass BizTalk and SSO, you are prompted for your authentication information by IIS (use the local Windows account information you created previously).</span></span>  
  
## <a name="comments"></a><span data-ttu-id="665e8-196">注释</span><span class="sxs-lookup"><span data-stu-id="665e8-196">Comments</span></span>  
 <span data-ttu-id="665e8-197">SsoSample.exe 向导应用程序配置两个 IIS 虚拟目录︰</span><span class="sxs-lookup"><span data-stu-id="665e8-197">The SsoSample.exe wizard application configures two IIS virtual directories:</span></span>  
  
-   <span data-ttu-id="665e8-198">第一个虚拟目录使用 Windows 集成身份验证配置，并且对应于 BizTalk HTTP 接收 ISAPI 扩展插件。</span><span class="sxs-lookup"><span data-stu-id="665e8-198">The first virtual directory is configured with Windows integrated authentication and corresponds to the BizTalk HTTP Receive ISAPI extension.</span></span> <span data-ttu-id="665e8-199">它必须与 BTSHTTPReceive.dll 位于以下文件夹中的.dll 文件相关联︰</span><span class="sxs-lookup"><span data-stu-id="665e8-199">It must be associated with the .dll file BTSHTTPReceive.dll located in the following folder:</span></span>  
  
     <span data-ttu-id="665e8-200">\<*安装路径*\>\HttpReceive</span><span class="sxs-lookup"><span data-stu-id="665e8-200">\<*Install Path*\>\HttpReceive</span></span>  
  
-   <span data-ttu-id="665e8-201">第二个虚拟目录配置使用基本身份验证和模拟接受要对用户进行身份验证的用户 ID 和密码的后端系统。</span><span class="sxs-lookup"><span data-stu-id="665e8-201">The second virtual directory is configured with basic authentication and simulates a back-end system that accepts a user ID and password to authenticate the user.</span></span> <span data-ttu-id="665e8-202">必须将其与一个关联或 ValidateUser.aspx 或 EmployeeData.aspx，ASPX 文件的其他位于以下文件夹中︰</span><span class="sxs-lookup"><span data-stu-id="665e8-202">It must be associated with one or the other of the ASPX files, ValidateUser.aspx or EmployeeData.aspx, located in the following folder:</span></span>  
  
     <span data-ttu-id="665e8-203">\<*示例路径*\>\SSO\HTTPSSO\Scripts</span><span class="sxs-lookup"><span data-stu-id="665e8-203">\<*Samples Path*\>\SSO\HTTPSSO\Scripts</span></span>  
  
 <span data-ttu-id="665e8-204">你可以使用 SsoSample.exe 向导应用程序配置一个或多个关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="665e8-204">You can use the SsoSample.exe wizard application to configure one or more affiliate applications.</span></span> <span data-ttu-id="665e8-205">其中每项的关联应用程序，你可以创建一个或多个用户映射。</span><span class="sxs-lookup"><span data-stu-id="665e8-205">For each of these affiliate applications, you can create one or more user mappings.</span></span> <span data-ttu-id="665e8-206">这些用户映射的每个映射到用来访问特定的后端系统帐户的 Windows 用户帐户。</span><span class="sxs-lookup"><span data-stu-id="665e8-206">Each of these user mappings maps a Windows user account to an account that you use to access a specific back-end system.</span></span> <span data-ttu-id="665e8-207">在此示例中，该帐户是本地的 Windows 帐户的使用进行身份验证模拟真实的后端系统的第二个 IIS 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="665e8-207">In this sample, that account is a local Windows account that you use to authenticate with the second IIS virtual directory that is simulating a genuine back-end system.</span></span>  
  
 <span data-ttu-id="665e8-208">若要重新运行此示例，你有若干种选择︰</span><span class="sxs-lookup"><span data-stu-id="665e8-208">To rerun this sample, you have several choices:</span></span>  
  
-   <span data-ttu-id="665e8-209">浏览直接到 Internet 资源管理器中的以下 URL:</span><span class="sxs-lookup"><span data-stu-id="665e8-209">Browse directly to the following URL in Internet Explorer:</span></span>  
  
     http://localhost/SsoSampleBizTalkHttpReceive/BTSHttpReceive.dll?<message/>  
  
-   <span data-ttu-id="665e8-210">向导再次运行应用程序，但清除所有的第一页上的配置复选框。</span><span class="sxs-lookup"><span data-stu-id="665e8-210">Run the wizard application again, but clear all of the configuration check boxes on the first page.</span></span>  
  
-   <span data-ttu-id="665e8-211">运行一次向导应用程序、 配置复选框选择在第一页，但仔细适当地配置其他 BizTalk 项、 affiliate 应用程序和等等，以便不发生配置错误。</span><span class="sxs-lookup"><span data-stu-id="665e8-211">Run the wizard application again, leave the configuration check boxes selected in the first page, but carefully and appropriately configure additional BizTalk items, affiliate applications, and so on, so that configuration errors do not occur.</span></span>  
  
 <span data-ttu-id="665e8-212">若要清理与此示例，请使用以下过程。</span><span class="sxs-lookup"><span data-stu-id="665e8-212">To clean up from this sample, use the following procedure.</span></span>  
  
#### <a name="to-clean-up-from-this-sample"></a><span data-ttu-id="665e8-213">若要清理与此示例</span><span class="sxs-lookup"><span data-stu-id="665e8-213">To clean up from this sample</span></span>  
  
1.  <span data-ttu-id="665e8-214">根据具体情况，反向执行，删除本地 Windows 帐户等的手动配置。</span><span class="sxs-lookup"><span data-stu-id="665e8-214">As appropriate, reverse the manual configuration that you performed, such as removing the local Windows account.</span></span>  
  
2.  <span data-ttu-id="665e8-215">删除与虚拟目录对应的 IIS 应用程序，然后删除本示例创建的 IIS 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="665e8-215">Remove IIS applications that correspond to the virtual directories, and then delete the IIS virtual directories created by this sample.</span></span>  
  
3.  <span data-ttu-id="665e8-216">使用 BizTalk 管理控制台，取消登记与本示例关联的发送端口，然后删除该发送端口。</span><span class="sxs-lookup"><span data-stu-id="665e8-216">Using BizTalk Administration console, unenlist and then delete the send port associated with this sample.</span></span> <span data-ttu-id="665e8-217">然后，删除与此示例关联的接收端口（及其接收位置）。</span><span class="sxs-lookup"><span data-stu-id="665e8-217">Then delete the receive port (and its receive location) associated with this sample.</span></span>  
  
4.  <span data-ttu-id="665e8-218">使用 Ssomanage 应用程序 (位于 \program Files\Enterprise 单一登录\\) 若要删除此示例的 SSO 应用程序︰</span><span class="sxs-lookup"><span data-stu-id="665e8-218">Use the Ssomanage application (located in \Program Files\Common Files\Enterprise Single Sign-On\\) to delete the SSO application for this sample:</span></span>  
  
    ```  
    Ssomanage –deleteapp SsoSampleApplication  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="665e8-219">另请参阅</span><span class="sxs-lookup"><span data-stu-id="665e8-219">See Also</span></span>  
 [<span data-ttu-id="665e8-220">SSO（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="665e8-220">SSO (BizTalk Server Samples Folder)</span></span>](../core/sso-biztalk-server-samples-folder.md)