---
title: HTTPSSO （BizTalk Server 示例） |Microsoft Docs
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
ms.openlocfilehash: 061753526738bfc134fc89b459b7bef87a68f216
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382835"
---
# <a name="httpsso-biztalk-server-sample"></a><span data-ttu-id="93650-102">HTTPSSO （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="93650-102">HTTPSSO (BizTalk Server Sample)</span></span>
<span data-ttu-id="93650-103">HTTPSSO 示例演示如何使用 Microsoft 企业单一登录 (SSO) 功能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HTTP 适配器。</span><span class="sxs-lookup"><span data-stu-id="93650-103">The HTTPSSO sample demonstrates how to use the Enterprise Single Sign-On (SSO) feature with the Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP adapter.</span></span>  

> [!NOTE]
>  <span data-ttu-id="93650-104">此示例不支持在 64 位操作系统上。</span><span class="sxs-lookup"><span data-stu-id="93650-104">This sample is not supported on 64-bit operating systems.</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="93650-105">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="93650-105">What This Sample Does</span></span>  
 <span data-ttu-id="93650-106">此示例演示如何使用 SSO 及 BizTalk HTTP 发送和接收适配器来模拟 SSO 如何允许用户在无需提供其他凭据即可登录到非 Microsoft Windows 系统 Windows 的身份验证之后的端到端方案。</span><span class="sxs-lookup"><span data-stu-id="93650-106">This sample demonstrates an end-to-end scenario that uses SSO and the BizTalk HTTP Send and Receive adapters to simulate how SSO allows a user to avoid supplying additional credentials to log on to non-Microsoft Windows systems after Windows authenticates them.</span></span>  

 <span data-ttu-id="93650-107">该示例还使用 SSO 的管理和映射模块来创建关联应用程序和使用互操作客户端 DLL 的 SSO 的 SSO 映射。</span><span class="sxs-lookup"><span data-stu-id="93650-107">The sample also uses the administration and mapping modules of SSO to create affiliate application and SSO mappings using the interop client DLL of SSO.</span></span>  

 <span data-ttu-id="93650-108">此示例演示使用 SSO 通过实现端到端方案的以下方面：</span><span class="sxs-lookup"><span data-stu-id="93650-108">The sample demonstrates the use of SSO by implementing the following aspects of an end-to-end scenario:</span></span>  

- <span data-ttu-id="93650-109">用户界面，由 Microsoft Internet 信息服务 (IIS) 虚拟目录配置为使用 Windows 集成身份验证。</span><span class="sxs-lookup"><span data-stu-id="93650-109">User interface, represented by a Microsoft Internet Information Services (IIS) virtual directory configured to use Windows integrated authentication.</span></span>  

- <span data-ttu-id="93650-110">后端系统，由配置为使用基本身份验证的 IIS 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="93650-110">Back-end system, represented by an IIS virtual directory configured to use basic authentication.</span></span>  

- <span data-ttu-id="93650-111">后端数据库，由 SQL 示例数据库 Northwind 表示。</span><span class="sxs-lookup"><span data-stu-id="93650-111">Back-end database, represented by the SQL sample database Northwind.</span></span>  

  <span data-ttu-id="93650-112">此示例假定你已安装了[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 SSO。</span><span class="sxs-lookup"><span data-stu-id="93650-112">This sample assumes that you have installed [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and SSO.</span></span> <span data-ttu-id="93650-113">必须具有管理员特权的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，IIS、 SSO 和 COM + on Windows XP Professional。</span><span class="sxs-lookup"><span data-stu-id="93650-113">You must have administrator privileges for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], IIS, SSO, and COM+ on Windows XP Professional.</span></span> <span data-ttu-id="93650-114">您必须是 SSO Administrators、 BizTalk Server Administrators 和 BizTalk Isolated 主机用户 Windows 组的成员。</span><span class="sxs-lookup"><span data-stu-id="93650-114">You must also be a member of SSO Administrators, BizTalk Server Administrators, and BizTalk Isolated Host Users Windows groups.</span></span>  

  <span data-ttu-id="93650-115">有效地使用此示例假定您已充分了解 SSO 和 BizTalk HTTP 适配器。</span><span class="sxs-lookup"><span data-stu-id="93650-115">Effective use of this sample assumes that you have sufficient knowledge of SSO and the BizTalk HTTP adapter.</span></span> <span data-ttu-id="93650-116">例如，您应该知道哪些关联应用程序是 SSO 的上下文中。</span><span class="sxs-lookup"><span data-stu-id="93650-116">For example, you should know what an affiliate application is in the context of SSO.</span></span> <span data-ttu-id="93650-117">有关这些主题的信息，请参阅[使用 SSO](../core/using-sso.md)。</span><span class="sxs-lookup"><span data-stu-id="93650-117">For information about these topics, see [Using SSO](../core/using-sso.md).</span></span> <span data-ttu-id="93650-118">另请参阅[HTTP 适配器](../core/http-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="93650-118">Also see [HTTP Adapter](../core/http-adapter.md).</span></span>  

  <span data-ttu-id="93650-119">完成配置后，此示例的工作方式如下：</span><span class="sxs-lookup"><span data-stu-id="93650-119">After you complete the configuration, this sample works as follows:</span></span>  

1. <span data-ttu-id="93650-120">当您单击**完成**在此示例的用户界面的向导应用程序，Internet Explorer 的实例启动并传递 BizTalk HTTP Receive DLL 的 URL。</span><span class="sxs-lookup"><span data-stu-id="93650-120">When you click **Finish** in the wizard application that comprises the user interface for this sample, an instance of Internet Explorer starts and passes the URL of the BizTalk HTTP Receive DLL.</span></span>  

2. <span data-ttu-id="93650-121">BizTalk Server 的 SSO，帮助有效 HTTP 将请求转发到已配置了基本身份验证的 IIS 虚拟目录中的 EmployeeData.aspx 文件。</span><span class="sxs-lookup"><span data-stu-id="93650-121">BizTalk Server, with the help of SSO, effectively forwards the HTTP request to the file EmployeeData.aspx in an IIS virtual directory that has been configured with basic authentication.</span></span> <span data-ttu-id="93650-122">此 ASPX 文件模拟非 Windows 后端系统的入口点。</span><span class="sxs-lookup"><span data-stu-id="93650-122">This ASPX file simulates the entry point into a non-Windows back-end system.</span></span> <span data-ttu-id="93650-123">使用 SSO，因为 HTTP 请求包括模拟模拟后端系统的登录帐户的凭据配置。</span><span class="sxs-lookup"><span data-stu-id="93650-123">Because you are using SSO, the HTTP request includes the configured credentials that simulate a logon account to the simulated back-end system.</span></span>  

3. <span data-ttu-id="93650-124">ASPX 文件访问 SQL 示例数据库 Northwind 来检索与模拟的后端系统凭据相对应的员工数据的修改的版本。</span><span class="sxs-lookup"><span data-stu-id="93650-124">The ASPX file accesses a modified version of the SQL sample database Northwind to retrieve employee data corresponding to the simulated back-end system credentials.</span></span>  

4. <span data-ttu-id="93650-125">ASPX 文件返回 HTTP 响应中检索到的雇员数据。</span><span class="sxs-lookup"><span data-stu-id="93650-125">The ASPX file returns the retrieved employee data in an HTTP response.</span></span>  

5. <span data-ttu-id="93650-126">BizTalk Server 将路由到 Internet 资源管理器，它为用户显示返回的雇员数据的 HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="93650-126">BizTalk Server routes the HTTP response to Internet Explorer, which displays the returned employee data to the user.</span></span>  

   <span data-ttu-id="93650-127">如果绕过 BizTalk Server 和 SSO，并直接浏览 EmployeeData.aspx 文件，Windows 对话框将提示您输入凭据。</span><span class="sxs-lookup"><span data-stu-id="93650-127">If you bypass BizTalk Server and SSO, and browse directly to the file EmployeeData.aspx, a Windows dialog box will prompt you for your credentials.</span></span>  

   <span data-ttu-id="93650-128">有关演示如何使用命令行实用工具 ssomanage.exe 配置 SSO，例如创建关联应用程序和用户映射的示例，请参阅[管理 （BizTalk Server 示例）](../core/manage-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="93650-128">For a sample that shows how to use the command-line utility ssomanage.exe to configure SSO, such as creating affiliate applications and user mappings, see [Manage (BizTalk Server Sample)](../core/manage-biztalk-server-sample.md).</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="93650-129">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="93650-129">Where to Find This Sample</span></span>  
 <span data-ttu-id="93650-130">\<*示例路径*\>\SSO\HTTPSSO\\</span><span class="sxs-lookup"><span data-stu-id="93650-130">\<*Samples Path*\>\SSO\HTTPSSO\\</span></span>  

 <span data-ttu-id="93650-131">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="93650-131">The following table shows the files in this sample and describes their purpose.</span></span>  

|<span data-ttu-id="93650-132">文件</span><span class="sxs-lookup"><span data-stu-id="93650-132">File(s)</span></span>|<span data-ttu-id="93650-133">Description</span><span class="sxs-lookup"><span data-stu-id="93650-133">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="93650-134">AssemblyInfo.cs SsoSample.csproj</span><span class="sxs-lookup"><span data-stu-id="93650-134">AssemblyInfo.cs, SsoSample.csproj</span></span>|<span data-ttu-id="93650-135">项目和相关的文件，本 HTTP SSO 示例。</span><span class="sxs-lookup"><span data-stu-id="93650-135">Project and related files for this HTTP SSO sample.</span></span>|  
|<span data-ttu-id="93650-136">SsoSample.cs</span><span class="sxs-lookup"><span data-stu-id="93650-136">SsoSample.cs</span></span>|<span data-ttu-id="93650-137">顶层 Microsoft VisualC#的 HTTP SSO 图形应用程序的重要组成部分本示例的源文件。</span><span class="sxs-lookup"><span data-stu-id="93650-137">Top-level Microsoft Visual C# source file for the HTTP SSO graphical application that constitutes much of this sample.</span></span> <span data-ttu-id="93650-138">此文件包含一个名为类中的 SSO 配置代码**SsoConfigurator**最终是此示例的点。</span><span class="sxs-lookup"><span data-stu-id="93650-138">This file contains the SSO configuration code, in a class named **SsoConfigurator** that is ultimately the point of this sample.</span></span>|  
|<span data-ttu-id="93650-139">在 \Scripts 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="93650-139">In the \Scripts folder:</span></span><br /><br /> <span data-ttu-id="93650-140">EmployeeData.aspx</span><span class="sxs-lookup"><span data-stu-id="93650-140">EmployeeData.aspx</span></span>|<span data-ttu-id="93650-141">用于访问和查询后端数据库 （在本例中为 SQL Northwind 数据库） 时雇员发出请求以直接或通过使用 SSO 查看个人数据。</span><span class="sxs-lookup"><span data-stu-id="93650-141">Used to access and query the back-end database (in this case, the SQL Northwind database) when an employee initiates a request to view personal data, either directly or by using SSO.</span></span>|  
|<span data-ttu-id="93650-142">在 \Scripts 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="93650-142">In the \Scripts folder:</span></span><br /><br /> <span data-ttu-id="93650-143">ValidateUser.aspx</span><span class="sxs-lookup"><span data-stu-id="93650-143">ValidateUser.aspx</span></span>|<span data-ttu-id="93650-144">简单的测试来验证用户和报表，如果该用户为有效，直接或通过使用 SSO。</span><span class="sxs-lookup"><span data-stu-id="93650-144">Simple test to validate a user and report if that user was validated, either directly or by using SSO.</span></span>|  
|<span data-ttu-id="93650-145">\UI 文件夹的位置：</span><span class="sxs-lookup"><span data-stu-id="93650-145">In the \UI folder:</span></span><br /><br /> <span data-ttu-id="93650-146">AddApplication.cs、 AddApplication.resx、 AddMapping.cs、 AddMapping.resx、 App.ico、 BtsPage.cs、 BtsPage.resx、 ExecutePage.cs、 ExecutePage.resx、 FinishPage.cs、 FinishPage.resx、 IisPage.cs、 IisPage.resx、 InfoPage.cs、 InfoPage.resx、 PageBase.cs，PageBase.resx、 SsoPage.cs、 SsoPage.resx、 SsoSampleWizard.cs、 SsoSampleWizard.resx、 WelcomePage.cs、 WelcomePage.resx、 WorkPage.cs、 WorkPage.resx</span><span class="sxs-lookup"><span data-stu-id="93650-146">AddApplication.cs, AddApplication.resx, AddMapping.cs, AddMapping.resx, App.ico, BtsPage.cs, BtsPage.resx, ExecutePage.cs, ExecutePage.resx, FinishPage.cs, FinishPage.resx, IisPage.cs, IisPage.resx, InfoPage.cs, InfoPage.resx, PageBase.cs, PageBase.resx, SsoPage.cs, SsoPage.resx, SsoSampleWizard.cs, SsoSampleWizard.resx, WelcomePage.cs, WelcomePage.resx, WorkPage.cs, WorkPage.resx</span></span>|<span data-ttu-id="93650-147">辅助 VisualC#源代码文件和其关联的 XML 格式的资源文件，构成了很多此示例的 HTTP SSO 图形应用程序。</span><span class="sxs-lookup"><span data-stu-id="93650-147">Auxiliary Visual C# source files, and their associated XML-formatted resource files, for the HTTP SSO graphical application that constitutes much of this sample.</span></span>|  

## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="93650-148">生成并初始化此示例</span><span class="sxs-lookup"><span data-stu-id="93650-148">Building and Initializing This Sample</span></span>  

#### <a name="to-build-and-initialize-the-httpsso-sample"></a><span data-ttu-id="93650-149">若要生成和初始化 HTTPSSO 示例</span><span class="sxs-lookup"><span data-stu-id="93650-149">To build and initialize the HTTPSSO sample</span></span>  

1. <span data-ttu-id="93650-150">创建 Microsoft Internet 信息服务 (IIS) 可用于基本身份验证的本地 Windows 帐户。</span><span class="sxs-lookup"><span data-stu-id="93650-150">Create a local Windows account that Microsoft Internet Information Services (IIS) can use for basic authentication.</span></span> <span data-ttu-id="93650-151">SSO 将 Windows 域帐户映射到此本地 Windows 帐户。</span><span class="sxs-lookup"><span data-stu-id="93650-151">SSO maps the Windows domain account to this local Windows account.</span></span> <span data-ttu-id="93650-152">例如，使用你的姓氏创建一个本地 Windows 帐户。</span><span class="sxs-lookup"><span data-stu-id="93650-152">For example, use your last name to create a local Windows account.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="93650-153">如果在域控制器上运行，可以创建域帐户，并将映射到此帐户的域帐户上的已登录。</span><span class="sxs-lookup"><span data-stu-id="93650-153">If you are running on a domain controller, you can create domain accounts and map your logged on domain account to this account.</span></span>  

2. <span data-ttu-id="93650-154">使用 Microsoft SQL Server 企业管理器，打开**员工**表中 Northwind 示例数据库，以及如何将你刚刚创建，添加的各种示例数据的本地 Windows 帐户对应的行列。</span><span class="sxs-lookup"><span data-stu-id="93650-154">Using Microsoft SQL Server Enterprise Manager, open the **Employees** table in the Northwind sample database, and then add a row corresponding to the local Windows account that you just created, including sample data for the various columns.</span></span> <span data-ttu-id="93650-155">您将添加到雇员表中的姓氏列的值必须是在步骤 1 中添加的本地 Windows 帐户的用户名相同。</span><span class="sxs-lookup"><span data-stu-id="93650-155">The value you add to the LastName column in the Employees table must be the same as the user name of the local Windows account you added in step 1.</span></span>  

3. <span data-ttu-id="93650-156">确保 ASP.NET 帐户 (ASPNET) 具有读取到 Northwind 数据库的权限。</span><span class="sxs-lookup"><span data-stu-id="93650-156">Ensure the ASP.NET account (ASPNET) has read privileges to the Northwind database.</span></span>  

4. <span data-ttu-id="93650-157">打开项目文件 SsoSample.csproj 使用 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="93650-157">Open the project file SsoSample.csproj using Visual Studio.</span></span>  

5. <span data-ttu-id="93650-158">在“生成”  菜单上，单击“生成解决方案” 。</span><span class="sxs-lookup"><span data-stu-id="93650-158">On the **Build** menu, click **Build Solution**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="93650-159">您可能需要生成可以继续操作之前保存解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="93650-159">You may be asked to save a solution file before the build can proceed.</span></span>  

    <span data-ttu-id="93650-160">如果您找不到以下 BizTalk 程序集引用该项目，将其删除、 重新将其添加从指示的位置，并重新生成：</span><span class="sxs-lookup"><span data-stu-id="93650-160">If you cannot find the following BizTalk assembly references for the project, delete them, re-add them from the indicated locations, and build again:</span></span>  

   - <span data-ttu-id="93650-161">**Microsoft.BizTalk.ExplorerOM**.</span><span class="sxs-lookup"><span data-stu-id="93650-161">**Microsoft.BizTalk.ExplorerOM**.</span></span> <span data-ttu-id="93650-162">默认情况下，Microsoft.BizTalk.ExplorerOM.dll 文件位于文件夹[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]开发人员工具\\。</span><span class="sxs-lookup"><span data-stu-id="93650-162">By default, the Microsoft.BizTalk.ExplorerOM.dll file is located in the folder [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Developer Tools\\.</span></span>  

   - <span data-ttu-id="93650-163">**Microsoft.BizTalk.SSOClient.Interop**.</span><span class="sxs-lookup"><span data-stu-id="93650-163">**Microsoft.BizTalk.SSOClient.Interop**.</span></span> <span data-ttu-id="93650-164">默认情况下，Microsoft.BizTalk.Interop.SSOClient.dll 文件位于文件夹\< *ProgramFiles*\>上单一登录的 \Common Files\Enterprise\\。</span><span class="sxs-lookup"><span data-stu-id="93650-164">By default, the Microsoft.BizTalk.Interop.SSOClient.dll file is located in the folder \<*ProgramFiles*\>\Common Files\Enterprise Single Sign-On\\.</span></span>  

     <span data-ttu-id="93650-165">这会生成可执行文件 SsoSample.exe 以下文件夹中：</span><span class="sxs-lookup"><span data-stu-id="93650-165">This produces the executable file SsoSample.exe in the following folder:</span></span>  

     <span data-ttu-id="93650-166">\<*示例路径*\>\SSO\HTTPSSO\bin\Debug\\</span><span class="sxs-lookup"><span data-stu-id="93650-166">\<*Samples Path*\>\SSO\HTTPSSO\bin\Debug\\</span></span>  

## <a name="running-this-sample"></a><span data-ttu-id="93650-167">运行本示例</span><span class="sxs-lookup"><span data-stu-id="93650-167">Running This Sample</span></span>  

> [!NOTE]
>  <span data-ttu-id="93650-168">如果工作进程隔离模式在 IIS 6.0 上运行此示例，为这两个虚拟目录都创建应用程序池。</span><span class="sxs-lookup"><span data-stu-id="93650-168">If you run this sample on IIS 6.0 in Worker Process Isolation Mode, application pools are created for both virtual directories.</span></span> <span data-ttu-id="93650-169">Windows 帐户 （你可以配置在 Internet 信息服务管理器标识） 中，必须手动配置这些两个应用程序池标识。</span><span class="sxs-lookup"><span data-stu-id="93650-169">You must manually configure identity for these two application pools in your Windows account (you can configure identity in Internet Information Services Manager).</span></span>  

#### <a name="to-run-the-httpsso-sample"></a><span data-ttu-id="93650-170">若要运行 HTTPSSO 示例</span><span class="sxs-lookup"><span data-stu-id="93650-170">To run the HTTPSSO sample</span></span>  

1. <span data-ttu-id="93650-171">运行以下文件夹中找到的可执行文件 SsoSample.exe:</span><span class="sxs-lookup"><span data-stu-id="93650-171">Run the executable file SsoSample.exe, found in the following folder:</span></span>  

    <span data-ttu-id="93650-172">\<*示例路径*\>\SSO\HTTPSSO\bin\Debug\\</span><span class="sxs-lookup"><span data-stu-id="93650-172">\<*Samples Path*\>\SSO\HTTPSSO\bin\Debug\\</span></span>  

    <span data-ttu-id="93650-173">此示例的向导应用程序将打开。</span><span class="sxs-lookup"><span data-stu-id="93650-173">The wizard application for this sample opens.</span></span>  

2. <span data-ttu-id="93650-174">在欢迎页上，配置 IIS、 SSO 和 BizTalk 中，接受默认设置，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="93650-174">On the Welcome page, accept the default setting for configuring IIS, SSO, and BizTalk, and then click **Next**.</span></span>  

3. <span data-ttu-id="93650-175">在 IIS 配置页上，接受以创建，然后单击所需的两个 IIS 虚拟目录的默认设置**下一步**。</span><span class="sxs-lookup"><span data-stu-id="93650-175">On the IIS Configuration page, accept the default settings for the two IIS virtual directories you want to create, and then click **Next**.</span></span>  

4. <span data-ttu-id="93650-176">在 SSO 配置页上，接受关联应用程序，这是可访问使用的默认设置**添加应用程序**按钮。</span><span class="sxs-lookup"><span data-stu-id="93650-176">On the SSO Configuration page, accept the default settings for the affiliate application, which is accessible using the **Add application** button.</span></span>  

5. <span data-ttu-id="93650-177">在 SSO 配置页上，接受用户映射的默认设置的大多数可使用**添加映射**按钮。</span><span class="sxs-lookup"><span data-stu-id="93650-177">On the SSO Configuration page, accept most of the default settings for the user mappings, accessible using the **Add mapping** button.</span></span> <span data-ttu-id="93650-178">为基于时生成并初始化本示例添加的本地 Windows 帐户的以下两个设置提供值。</span><span class="sxs-lookup"><span data-stu-id="93650-178">Provide values for the following two settings based on the local Windows account you added when building and initializing this sample.</span></span>  


   |        <span data-ttu-id="93650-179">设置</span><span class="sxs-lookup"><span data-stu-id="93650-179">Setting</span></span>         |                         <span data-ttu-id="93650-180">ReplTest1</span><span class="sxs-lookup"><span data-stu-id="93650-180">Value</span></span>                         |
   |------------------------|-------------------------------------------------------|
   |   <span data-ttu-id="93650-181">外部用户名称</span><span class="sxs-lookup"><span data-stu-id="93650-181">External user name</span></span>   |   <span data-ttu-id="93650-182">将设置为添加的本地 Windows 用户帐户名称。</span><span class="sxs-lookup"><span data-stu-id="93650-182">Set to the added local Windows user account name.</span></span>   |
   | <span data-ttu-id="93650-183">外部用户密码</span><span class="sxs-lookup"><span data-stu-id="93650-183">External user password</span></span> | <span data-ttu-id="93650-184">将设置为添加的本地 Windows 用户帐户密码。</span><span class="sxs-lookup"><span data-stu-id="93650-184">Set to the added local Windows user account password.</span></span> |


6. <span data-ttu-id="93650-185">在 SSO 配置页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="93650-185">On the SSO Configuration page, click **Next**.</span></span>  

7. <span data-ttu-id="93650-186">在 BizTalk 配置页上，接受默认设置为发送和接收端口和等等，然后依次**下一步**。</span><span class="sxs-lookup"><span data-stu-id="93650-186">On the BizTalk Configuration page, accept the default settings for the send and receive ports, and so on, and then click **Next**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="93650-187">你可以将默认发送端口设置从**EmployeeData.aspx**到**ValidateUser.aspx**如果你想要查看简单的用户验证，而不是从 Employee 表的示例数据提取Northwinds SQL 数据库。</span><span class="sxs-lookup"><span data-stu-id="93650-187">You can change the default send port setting from **EmployeeData.aspx** to **ValidateUser.aspx** if you want to see simple user validation rather than sample data pulled from the Employee table of the Northwinds SQL database.</span></span> <span data-ttu-id="93650-188">进行此更改将更改在单击后显示在浏览器中的输出的性质**完成**步骤 9 中。</span><span class="sxs-lookup"><span data-stu-id="93650-188">Making this change changes the nature of the output displayed in the browser after clicking **Finish** in step 9.</span></span>  

8. <span data-ttu-id="93650-189">查看与正在执行的 IIS、 SSO 和 BizTalk 配置相对应的状态消息。</span><span class="sxs-lookup"><span data-stu-id="93650-189">Review the status messages corresponding to the IIS, SSO, and BizTalk configuration being performed.</span></span> <span data-ttu-id="93650-190">您可以找到在此阶段中运行的代码**IisConfigurator**， **SsoConfigurator**，并**BtsConfigurator**文件 SsoSample.cs 中定义的类。</span><span class="sxs-lookup"><span data-stu-id="93650-190">You can find the code that is run during this phase in the **IisConfigurator**, **SsoConfigurator**, and **BtsConfigurator** classes defined in the file SsoSample.cs.</span></span> <span data-ttu-id="93650-191">配置完成后，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="93650-191">After configuration has completed, click **Next**.</span></span>  

9. <span data-ttu-id="93650-192">在向导应用程序的最后一页上，接受默认设置**启动浏览器显示在**(选中的复选框和文本框中的 url http://localhost/SsoSampleBizTalkHttpReceive/BTSHttpReceive.dll? <message/>)，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="93650-192">On the final page of the wizard application, accept the default settings for **Start browser at** (a selected check box and a text box with the URL http://localhost/SsoSampleBizTalkHttpReceive/BTSHttpReceive.dll?<message/>), and then click **Finish**.</span></span>  

     <span data-ttu-id="93650-193">Internet Explorer 的实例将打开，并很快显示示例员工数据添加到 Northwinds SQL 数据库的 Employee 表。</span><span class="sxs-lookup"><span data-stu-id="93650-193">An instance of Internet Explorer will open, and soon display the sample employee data that you added to the Employee table of the Northwinds SQL database.</span></span>  

   <span data-ttu-id="93650-194">为方便比较，可以绕过 BizTalk 和 SSO 和直接浏览到 ASPX 文件之一：</span><span class="sxs-lookup"><span data-stu-id="93650-194">For comparison purposes, you can bypass BizTalk and SSO and browse directly to either of the ASPX files:</span></span>  

- http://localhost/SsoSampleServerApplication/ValidateUser.aspx  

- http://localhost/SsoSampleServerApplication/EmployeeData.aspx  

  <span data-ttu-id="93650-195">在这两种情况下，因为您绕过 BizTalk 和 SSO，系统会提示对身份验证信息由 IIS （使用以前创建的本地 Windows 帐户信息）。</span><span class="sxs-lookup"><span data-stu-id="93650-195">In both cases, because you bypass BizTalk and SSO, you are prompted for your authentication information by IIS (use the local Windows account information you created previously).</span></span>  

## <a name="comments"></a><span data-ttu-id="93650-196">注释</span><span class="sxs-lookup"><span data-stu-id="93650-196">Comments</span></span>  
 <span data-ttu-id="93650-197">SsoSample.exe 向导应用程序配置两个 IIS 虚拟目录：</span><span class="sxs-lookup"><span data-stu-id="93650-197">The SsoSample.exe wizard application configures two IIS virtual directories:</span></span>  

- <span data-ttu-id="93650-198">第一个虚拟目录使用 Windows 集成身份验证配置，对应于 BizTalk HTTP 接收 ISAPI 扩展。</span><span class="sxs-lookup"><span data-stu-id="93650-198">The first virtual directory is configured with Windows integrated authentication and corresponds to the BizTalk HTTP Receive ISAPI extension.</span></span> <span data-ttu-id="93650-199">它必须与 BTSHTTPReceive.dll 位于以下文件夹中的.dll 文件相关联：</span><span class="sxs-lookup"><span data-stu-id="93650-199">It must be associated with the .dll file BTSHTTPReceive.dll located in the following folder:</span></span>  

   <span data-ttu-id="93650-200">\<*Install Path*\>\HttpReceive</span><span class="sxs-lookup"><span data-stu-id="93650-200">\<*Install Path*\>\HttpReceive</span></span>  

- <span data-ttu-id="93650-201">第二个虚拟目录配置基本身份验证和模拟后端系统接受用户进行身份验证的用户 ID 和密码。</span><span class="sxs-lookup"><span data-stu-id="93650-201">The second virtual directory is configured with basic authentication and simulates a back-end system that accepts a user ID and password to authenticate the user.</span></span> <span data-ttu-id="93650-202">必须将其与一个关联或其他的 ASPX 文件、 ValidateUser.aspx 或 EmployeeData.aspx，位于以下文件夹中：</span><span class="sxs-lookup"><span data-stu-id="93650-202">It must be associated with one or the other of the ASPX files, ValidateUser.aspx or EmployeeData.aspx, located in the following folder:</span></span>  

   <span data-ttu-id="93650-203">\<*示例路径*\>\SSO\HTTPSSO\Scripts</span><span class="sxs-lookup"><span data-stu-id="93650-203">\<*Samples Path*\>\SSO\HTTPSSO\Scripts</span></span>  

  <span data-ttu-id="93650-204">您可以使用 SsoSample.exe 向导应用程序配置一个或多个关联应用程序。</span><span class="sxs-lookup"><span data-stu-id="93650-204">You can use the SsoSample.exe wizard application to configure one or more affiliate applications.</span></span> <span data-ttu-id="93650-205">每个关联应用程序，可以创建一个或多个用户映射。</span><span class="sxs-lookup"><span data-stu-id="93650-205">For each of these affiliate applications, you can create one or more user mappings.</span></span> <span data-ttu-id="93650-206">每个用户映射将 Windows 用户帐户映射到用于访问特定的后端系统的帐户。</span><span class="sxs-lookup"><span data-stu-id="93650-206">Each of these user mappings maps a Windows user account to an account that you use to access a specific back-end system.</span></span> <span data-ttu-id="93650-207">在此示例中，该帐户是本地的 Windows 帐户，用于使用模拟正版的后端系统的第二个 IIS 虚拟目录进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="93650-207">In this sample, that account is a local Windows account that you use to authenticate with the second IIS virtual directory that is simulating a genuine back-end system.</span></span>  

  <span data-ttu-id="93650-208">若要重新运行此示例，可以选择多种方法：</span><span class="sxs-lookup"><span data-stu-id="93650-208">To rerun this sample, you have several choices:</span></span>  

- <span data-ttu-id="93650-209">直接浏览到在 Internet Explorer 中的以下 URL:</span><span class="sxs-lookup"><span data-stu-id="93650-209">Browse directly to the following URL in Internet Explorer:</span></span>  

   http://localhost/SsoSampleBizTalkHttpReceive/BTSHttpReceive.dll?<message/>  

- <span data-ttu-id="93650-210">向导再次运行应用程序，但清除所有的第一页上的配置复选框。</span><span class="sxs-lookup"><span data-stu-id="93650-210">Run the wizard application again, but clear all of the configuration check boxes on the first page.</span></span>  

- <span data-ttu-id="93650-211">向导再次运行应用程序、 配置复选框选择在第一页上，但仔细适当地配置其他 BizTalk 项目、 关联应用程序中，依次类推，以便不会发生配置错误。</span><span class="sxs-lookup"><span data-stu-id="93650-211">Run the wizard application again, leave the configuration check boxes selected in the first page, but carefully and appropriately configure additional BizTalk items, affiliate applications, and so on, so that configuration errors do not occur.</span></span>  

  <span data-ttu-id="93650-212">若要清理本示例中，使用以下过程。</span><span class="sxs-lookup"><span data-stu-id="93650-212">To clean up from this sample, use the following procedure.</span></span>  

#### <a name="to-clean-up-from-this-sample"></a><span data-ttu-id="93650-213">若要清理本示例</span><span class="sxs-lookup"><span data-stu-id="93650-213">To clean up from this sample</span></span>  

1.  <span data-ttu-id="93650-214">根据需要，反向执行，如删除本地 Windows 帐户的手动配置。</span><span class="sxs-lookup"><span data-stu-id="93650-214">As appropriate, reverse the manual configuration that you performed, such as removing the local Windows account.</span></span>  

2.  <span data-ttu-id="93650-215">删除 IIS 应用程序对应的虚拟目录，然后再删除此示例创建的 IIS 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="93650-215">Remove IIS applications that correspond to the virtual directories, and then delete the IIS virtual directories created by this sample.</span></span>  

3.  <span data-ttu-id="93650-216">使用 BizTalk 管理控制台中，取消登记，然后再删除此示例与关联的发送端口。</span><span class="sxs-lookup"><span data-stu-id="93650-216">Using BizTalk Administration console, unenlist and then delete the send port associated with this sample.</span></span> <span data-ttu-id="93650-217">然后，删除与此示例相关联的接收端口 （和其接收位置）。</span><span class="sxs-lookup"><span data-stu-id="93650-217">Then delete the receive port (and its receive location) associated with this sample.</span></span>  

4.  <span data-ttu-id="93650-218">使用 Ssomanage 应用程序 (位于 Files\Enterprise Single Sign-on \Program Files\Common\\) 若要删除此示例的 SSO 应用程序：</span><span class="sxs-lookup"><span data-stu-id="93650-218">Use the Ssomanage application (located in \Program Files\Common Files\Enterprise Single Sign-On\\) to delete the SSO application for this sample:</span></span>  

    ```  
    Ssomanage –deleteapp SsoSampleApplication  
    ```  

## <a name="see-also"></a><span data-ttu-id="93650-219">请参阅</span><span class="sxs-lookup"><span data-stu-id="93650-219">See Also</span></span>  
 [<span data-ttu-id="93650-220">SSO（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="93650-220">SSO (BizTalk Server Samples Folder)</span></span>](../core/sso-biztalk-server-samples-folder.md)