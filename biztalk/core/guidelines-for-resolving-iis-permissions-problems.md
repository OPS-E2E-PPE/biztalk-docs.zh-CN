---
title: "以解决 IIS 权限问题的指导原则 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: troubleshooting
ms.assetid: d9793a90-3aa3-46ab-a317-6d1e0fbfc1ef
caps.latest.revision: "30"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fdae0c97d0441ccb57320ec24908cca522ae2088
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="guidelines-for-resolving-iis-permissions-problems"></a><span data-ttu-id="c087f-102">以解决 IIS 权限问题的指导原则</span><span class="sxs-lookup"><span data-stu-id="c087f-102">Guidelines for Resolving IIS Permissions Problems</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="c087f-103"> 将 Microsoft Internet 信息服务 (IIS) 广泛应用于 Web Services 支持，并与 HTTP、SOAP 和 Windows SharePoint Services 适配器一起使用。</span><span class="sxs-lookup"><span data-stu-id="c087f-103"> makes extensive use of Microsoft Internet Information Services (IIS) for Web services support and for use with the HTTP, SOAP, and Windows SharePoint Services adapters.</span></span>  
  
 <span data-ttu-id="c087f-104">在解决 IIS 权限疑难问题之前，了解 IIS 如何实现应用程序隔离是很有帮助的。</span><span class="sxs-lookup"><span data-stu-id="c087f-104">It is helpful to understand how IIS implements application isolation before troubleshooting IIS permissions problems.</span></span>  
  
 <span data-ttu-id="c087f-105">使用 IIS 可创建作为不同宿主进程的 IIS 应用程序，它们在自己的内存空间中运行。</span><span class="sxs-lookup"><span data-stu-id="c087f-105">IIS provides functionality for creating IIS applications as distinct host processes that are run in their own memory space.</span></span> <span data-ttu-id="c087f-106">一旦你创建的 IIS 应用程序主机，然后必须定义两个集的权限，在 IIS 应用程序主机**进程标识**和 IIS 应用程序主机**用户访问权限**。</span><span class="sxs-lookup"><span data-stu-id="c087f-106">Once you create an IIS application host, then you must define two sets of permissions, the IIS application host **process identity** and the IIS application host **user access rights**.</span></span> <span data-ttu-id="c087f-107">在解决 IIS 权限疑难问题时，您应对每组权限都进行检查。</span><span class="sxs-lookup"><span data-stu-id="c087f-107">You should examine each of these permissions sets when troubleshooting IIS permissions problems.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c087f-108">**进程标识**和**用户访问权限**也称为**安全上下文**的 IIS 应用程序主机进程。</span><span class="sxs-lookup"><span data-stu-id="c087f-108">The **process identity** and **user access rights** are also referred to as the **security context** of the IIS application host process.</span></span>  
  
 <span data-ttu-id="c087f-109">本主题介绍如何设置**进程标识**和**用户访问权限**为 IIS 应用程序主机进程，并为解决 IIS 权限问题提供一些通用准则。</span><span class="sxs-lookup"><span data-stu-id="c087f-109">This topic describes how to set **process identity** and **user access rights** for an IIS application host process and gives some general guidelines for resolving IIS permissions problems.</span></span>  
  
## <a name="setting-iis-application-host-process-identity"></a><span data-ttu-id="c087f-110">设置 IIS 应用程序宿主进程标识</span><span class="sxs-lookup"><span data-stu-id="c087f-110">Setting IIS Application Host Process Identity</span></span>  
 <span data-ttu-id="c087f-111">IIS 应用程序宿主进程的配置随宿主进程提供的不同功能级别而异。</span><span class="sxs-lookup"><span data-stu-id="c087f-111">Configuration of an IIS application host process can vary depending on the level of functionality being served by the host process.</span></span> <span data-ttu-id="c087f-112">例如，通常不同于 IIS 应用程序主机进程提供服务 ASP 页或 ASP.NET 应用程序配置 IIS 应用程序主机进程，仅提供静态 HTML 页。</span><span class="sxs-lookup"><span data-stu-id="c087f-112">For example, an IIS application host process that only serves static HTML pages is typically configured differently than an IIS application host process that serves ASP pages or ASP.NET applications.</span></span>  
  
 <span data-ttu-id="c087f-113">IIS 应用程序宿主进程的配置也随该应用程序的宿主 IIS 的不同版本而异。</span><span class="sxs-lookup"><span data-stu-id="c087f-113">Configuration of an IIS application host process also varies depending on the version of IIS that is hosting the application.</span></span> <span data-ttu-id="c087f-114">运行在 Windows Server 2008 (IIS 7.0) 上的应用程序的宿主进程标识由与该应用程序关联的应用程序池标识管理。</span><span class="sxs-lookup"><span data-stu-id="c087f-114">The host process identity of applications running on Windows Server 2008 (IIS 7.0) is governed by the identity of the application pool associated with the application.</span></span>  
  
### <a name="setting-iis-process-identity-for-iis-70-on-windows-server-2008-or-windows-vista"></a><span data-ttu-id="c087f-115">在 Windows Server 2008 或 Windows Vista 中设置 IIS 7.0 的 IIS 进程标识</span><span class="sxs-lookup"><span data-stu-id="c087f-115">Setting IIS Process Identity for IIS 7.0 on Windows Server 2008 or Windows Vista</span></span>  
  
1.  <span data-ttu-id="c087f-116">单击**启动**，然后**所有程序**，然后单击**Internet Information Services (IIS) 7 Manager**。</span><span class="sxs-lookup"><span data-stu-id="c087f-116">Click **Start**, then **All Programs**, and click **Internet Information Services (IIS) 7 Manager**.</span></span>  
  
2.  <span data-ttu-id="c087f-117">在 Internet 信息服务 (IIS) 管理器中，展开*\<计算机名称 >***（用户帐户）**单击**应用程序池**。</span><span class="sxs-lookup"><span data-stu-id="c087f-117">In Internet Information Services (IIS) Manager, expand *\<computer name>***(User account)** and click **Application Pools**.</span></span>  
  
3.  <span data-ttu-id="c087f-118">右键单击应用程序池，单击**查看应用程序**若要查看与应用程序池关联的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c087f-118">Right-click an application pool and click **View Applications** to see the applications associated with the application pool.</span></span>  
  
4.  <span data-ttu-id="c087f-119">右键单击应用程序池，单击**高级设置**以显示应用程序池高级设置对话框。</span><span class="sxs-lookup"><span data-stu-id="c087f-119">Right-click an application pool and click **Advanced Settings** to display the Advanced Settings dialog for the application pool.</span></span>  
  
5.  <span data-ttu-id="c087f-120">通过旁边单击省略号 （…） 按钮来修改应用程序池的标识**标识**下**进程模型**部分**高级设置**对话框框。</span><span class="sxs-lookup"><span data-stu-id="c087f-120">Modify the identity for the application pool by clicking the ellipsis (…) button next to **Identity** under the **Process Model** section of the **Advanced Settings** dialog box.</span></span>  
  
## <a name="setting-user-access-rights-for-the-iis-server"></a><span data-ttu-id="c087f-121">为 IIS 服务器设置用户访问权限</span><span class="sxs-lookup"><span data-stu-id="c087f-121">Setting User Access Rights for the IIS Server</span></span>  
 <span data-ttu-id="c087f-122">进程标识控制运行的 IIS 应用程序宿主进程可用的安全上下文，而用户访问权限控制实际访问所承载网页的帐户的安全上下文。</span><span class="sxs-lookup"><span data-stu-id="c087f-122">While process identity governs the security context available to the running IIS application host process, user access permissions govern the security context for the account that is actually accessing the Web page(s) being served.</span></span> <span data-ttu-id="c087f-123">必须为两个安全上下文设置适当的权限，以避免权限错误。</span><span class="sxs-lookup"><span data-stu-id="c087f-123">Permissions must be set appropriately for both security contexts to avoid permissions errors.</span></span>  
  
 <span data-ttu-id="c087f-124">IIS 7.0 支持以下用户验证方法：</span><span class="sxs-lookup"><span data-stu-id="c087f-124">IIS 7.0 supports the following user authentication methods:</span></span>  
  
-   <span data-ttu-id="c087f-125">**匿名访问：**允许用户建立匿名连接。</span><span class="sxs-lookup"><span data-stu-id="c087f-125">**Anonymous access:** Allows users to establish an anonymous connection.</span></span> <span data-ttu-id="c087f-126">IIS 服务器以指定的 Guest 帐户登录用户。</span><span class="sxs-lookup"><span data-stu-id="c087f-126">The IIS server logs on the user with the specified guest account.</span></span>  
  
-   <span data-ttu-id="c087f-127">**ASP.NET 模拟**允许应用程序在两个不同的上下文之一中运行： 作为通过 IIS 身份验证的用户或作为你设置的任意帐户。</span><span class="sxs-lookup"><span data-stu-id="c087f-127">**ASP.NET Impersonation** Allows an application to run in one of two different contexts: either as the user authenticated by IIS or as an arbitrary account that you set up.</span></span>  
  
-   <span data-ttu-id="c087f-128">**基本身份验证：**纯文本，以未加密形式在网络上传输密码。</span><span class="sxs-lookup"><span data-stu-id="c087f-128">**Basic authentication:** Transmits passwords across the network in plaintext, an unencrypted form.</span></span>  
  
-   <span data-ttu-id="c087f-129">**摘要式身份验证：**仅适用于 Active Directory 帐户，通过网络，而不是纯文本密码发送一个哈希值。</span><span class="sxs-lookup"><span data-stu-id="c087f-129">**Digest authentication:** Works only with Active Directory accounts, sending a hash value over the network, rather than a plaintext password.</span></span> <span data-ttu-id="c087f-130">摘要验证可通过代理服务器和其他防火墙工作，可以在 Web 分布式创作和版本管理 (WebDAV) 目录中使用。</span><span class="sxs-lookup"><span data-stu-id="c087f-130">Digest authentication works across proxy servers and other firewalls and is available on Web Distributed Authoring and Versioning (WebDAV) directories.</span></span> <span data-ttu-id="c087f-131">要使用摘要式身份验证，首先必须禁用匿名身份验证。</span><span class="sxs-lookup"><span data-stu-id="c087f-131">Use of Digest authentication requires that Anonymous authentication is disabled first.</span></span>  
  
-   <span data-ttu-id="c087f-132">**窗体身份验证**Accommodates 的高流量站点或公共服务器上的应用程序的身份验证。</span><span class="sxs-lookup"><span data-stu-id="c087f-132">**Forms Authentication** Accommodates authentication for high-traffic sites or applications on public servers.</span></span> <span data-ttu-id="c087f-133">表单身份验证可管理客户端注册和应用程序级别的身份验证，而非依赖操作系统提供的身份验证机制。</span><span class="sxs-lookup"><span data-stu-id="c087f-133">Forms authentication lets you manage client registration and authentication at the application level, instead of relying on the authentication mechanisms provided by the operating system.</span></span>  
  
-   <span data-ttu-id="c087f-134">**Windows 身份验证：**在您的 Windows 域进行身份验证的客户端连接的使用身份验证。</span><span class="sxs-lookup"><span data-stu-id="c087f-134">**Windows authentication:** Uses authentication on your Windows domain to authenticate client connections.</span></span>  
  
#### <a name="to-set-user-access-rights-for-a-virtual-directory-in-iis-70"></a><span data-ttu-id="c087f-135">设置 IIS 7.0 中虚拟目录的用户访问权限</span><span class="sxs-lookup"><span data-stu-id="c087f-135">To set user access rights for a virtual directory in IIS 7.0</span></span>  
  
1.  <span data-ttu-id="c087f-136">在 Internet 信息服务 (IIS) 管理器中，展开*\<计算机名称 >*，**站点**，和**Default Web Site**中**连接**窗格。</span><span class="sxs-lookup"><span data-stu-id="c087f-136">In the Internet Information Services (IIS) Manager, expand *\<computer name>*, **Sites**, and **Default Web Site** in the **Connections** pane.</span></span>  
  
2.  <span data-ttu-id="c087f-137">单击此项可选择的虚拟目录，然后单击**功能视图**底部的工作区窗格中列出的虚拟目录的可配置功能。</span><span class="sxs-lookup"><span data-stu-id="c087f-137">Click to select the virtual directory and click the **Features View** at the bottom of the Workspace pane to list the configurable features for the virtual directory.</span></span>  
  
3.  <span data-ttu-id="c087f-138">双击**身份验证**工作区窗格中，若要列出的虚拟目录启用的身份验证方法中的新功能。</span><span class="sxs-lookup"><span data-stu-id="c087f-138">Double-click the **Authentication** feature in the Workspace pane to list the authentication methods that are enabled for the virtual directory.</span></span>  
  
4.  <span data-ttu-id="c087f-139">单击以选择你想要启用或禁用并单击的身份验证方法**禁用**或**启用**中**操作**的 IIS 管理器窗格。</span><span class="sxs-lookup"><span data-stu-id="c087f-139">Click to select the authentication method that you would like to enable or disable and click either **Disable** or **Enable** in the **Actions** pane of the IIS Manager.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c087f-140">如果**启用匿名访问**是启用，IIS 将设置用户访问权限以配置的匿名用户身份之前设置与任何其他用户访问权限启用身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="c087f-140">If **Enable anonymous access** is enabled, IIS will set user access rights as the configured Anonymous user identity before setting user access rights with any other enabled authentication methods.</span></span>  
    >   
    >  <span data-ttu-id="c087f-141">若要配置的匿名用户标识，右键单击**匿名身份验证**方法，并单击**编辑**以显示**编辑匿名身份验证凭据**对话框。</span><span class="sxs-lookup"><span data-stu-id="c087f-141">To configure the Anonymous user identity, right-click the **Anonymous Authentication** method and click **Edit** to display the **Edit Anonymous Authentication Credentials** dialog.</span></span>  
  
## <a name="general-guidelines-for-resolving-iis-permissions-problems"></a><span data-ttu-id="c087f-142">解决 IIS 权限问题的一般准则</span><span class="sxs-lookup"><span data-stu-id="c087f-142">General Guidelines for Resolving IIS Permissions Problems</span></span>  
 <span data-ttu-id="c087f-143">按照以下步骤来解决 IIS 权限疑难问题：</span><span class="sxs-lookup"><span data-stu-id="c087f-143">Follow these steps to troubleshoot IIS permissions:</span></span>  
  
1.  <span data-ttu-id="c087f-144">在 IIS 服务器计算机的应用程序日志中查找错误。</span><span class="sxs-lookup"><span data-stu-id="c087f-144">Check the application log of the IIS Server computer for errors.</span></span>  
  
2.  <span data-ttu-id="c087f-145">按照中的步骤[IIS 7.0： 配置为在 IIS 7.0 中的失败请求跟踪](http://go.microsoft.com/fwlink/?LinkId=130600)来解决 IIS 7.0 的计算机上的权限问题。</span><span class="sxs-lookup"><span data-stu-id="c087f-145">Follow the steps in [IIS 7.0: Configuring Tracing for Failed Requests in IIS 7.0](http://go.microsoft.com/fwlink/?LinkId=130600) to troubleshoot permissions problems on IIS 7.0 computers.</span></span>  
  
3.  <span data-ttu-id="c087f-146">在 IIS 服务器的 IIS 日志文件中查找 HTTP 401 错误。</span><span class="sxs-lookup"><span data-stu-id="c087f-146">Check the IIS log files of the IIS server for HTTP 401 errors.</span></span>  
  
     <span data-ttu-id="c087f-147">默认情况下，在运行 Windows Server 2008 或 Windows Vista 的计算机中，IIS 日志文件位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="c087f-147">By default the IIS log files on a computer running Windows Server 2008 or Windows Vista are located in the following directory:</span></span>  
  
     <span data-ttu-id="c087f-148">C:\inetpub\logs\LogFiles\W3SVC1\\</span><span class="sxs-lookup"><span data-stu-id="c087f-148">C:\inetpub\logs\LogFiles\W3SVC1\\</span></span>  
  
    -   <span data-ttu-id="c087f-149">如果 IIS 7.0 计算机包含 HTTP 401 错误，请按照 Microsoft 知识库文章 943891 中的步骤，IIS 日志文件，"HTTP 状态代码在 IIS 7.0 中"在可用[http://support.microsoft.com/kb/943891](http://support.microsoft.com/kb/943891)以确定子状态代码和故障排除，根据状态代码的权限问题。</span><span class="sxs-lookup"><span data-stu-id="c087f-149">If the IIS log file for an IIS 7.0 computer contains HTTP 401 errors, follow the steps in Microsoft Knowledge Base article 943891, "The HTTP status codes in IIS 7.0" available at [http://support.microsoft.com/kb/943891](http://support.microsoft.com/kb/943891) to determine the substatus code and to troubleshoot the permissions problem based on the status code.</span></span>  
  
    -   <span data-ttu-id="c087f-150">检查值**cs-username**与 HTTP 401 错误关联的字段。</span><span class="sxs-lookup"><span data-stu-id="c087f-150">Check the value of the **cs-username** field associated with the HTTP 401 error.</span></span> <span data-ttu-id="c087f-151">此字段包含访问 IIS 服务器的已通过验证的用户的名称。</span><span class="sxs-lookup"><span data-stu-id="c087f-151">This field contains the name of the authenticated user who accessed the IIS server.</span></span> <span data-ttu-id="c087f-152">在此字段中，匿名用户帐户由连字符 (-) 表示。</span><span class="sxs-lookup"><span data-stu-id="c087f-152">The anonymous user account is represented by a hyphen (-) in this field.</span></span> <span data-ttu-id="c087f-153">确保此帐户具有访问相应资源的权限。</span><span class="sxs-lookup"><span data-stu-id="c087f-153">Ensure that this account has permissions on the appropriate resources.</span></span>  
  
4.  <span data-ttu-id="c087f-154">验证 IIS 应用程序宿主进程使用的进程标识凭据已正确设置，并且该帐户具有适当的权限。</span><span class="sxs-lookup"><span data-stu-id="c087f-154">Verify that the process identity credentials used by the IIS application host process are set correctly and that the account has the appropriate permissions.</span></span> <span data-ttu-id="c087f-155">如果用于进程标识的帐户没有足够的权限，则更改帐户或授予该帐户适当的权限。</span><span class="sxs-lookup"><span data-stu-id="c087f-155">If the account used for the process identity has insufficient permissions then either change the account or grant the account the appropriate permissions.</span></span>  
  
5.  <span data-ttu-id="c087f-156">使用中所述的 RegMon 和 FileMon 实用工具[工具和实用程序用于故障排除](../core/tools-and-utilities-to-use-for-troubleshooting.md)来诊断文件或注册表中的访问权限问题。</span><span class="sxs-lookup"><span data-stu-id="c087f-156">Use the RegMon and FileMon utilities described in [Tools and Utilities to Use for Troubleshooting](../core/tools-and-utilities-to-use-for-troubleshooting.md) to diagnose file or registry access permissions problems.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c087f-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c087f-157">See Also</span></span>  
 <span data-ttu-id="c087f-158">[BizTalk Server 权限的疑难解答](../core/troubleshooting-biztalk-server-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="c087f-158">[Troubleshooting BizTalk Server Permissions](../core/troubleshooting-biztalk-server-permissions.md) </span></span>  
 [<span data-ttu-id="c087f-159">IIS 7.0： 在 IIS 7.0 中配置身份验证</span><span class="sxs-lookup"><span data-stu-id="c087f-159">IIS 7.0: Configuring Authentication in IIS 7.0</span></span>](http://go.microsoft.com/fwlink/?LinkId=129909)