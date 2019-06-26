---
title: 解决 IIS 权限疑难问题的准则 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting
ms.assetid: d9793a90-3aa3-46ab-a317-6d1e0fbfc1ef
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5473ef63655b7b135de1ea830cff0d41efe625e3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344859"
---
# <a name="guidelines-for-resolving-iis-permissions-problems"></a><span data-ttu-id="e129e-102">解决 IIS 权限疑难问题的准则</span><span class="sxs-lookup"><span data-stu-id="e129e-102">Guidelines for Resolving IIS Permissions Problems</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="e129e-103">可以广泛使用的 Microsoft Internet 信息服务 (IIS) Web services 支持并与 HTTP、 SOAP 和 Windows SharePoint Services 适配器一起使用。</span><span class="sxs-lookup"><span data-stu-id="e129e-103">makes extensive use of Microsoft Internet Information Services (IIS) for Web services support and for use with the HTTP, SOAP, and Windows SharePoint Services adapters.</span></span>  
  
 <span data-ttu-id="e129e-104">最好先了解 IIS 如何实现之前解决 IIS 权限疑难问题的应用程序隔离。</span><span class="sxs-lookup"><span data-stu-id="e129e-104">It is helpful to understand how IIS implements application isolation before troubleshooting IIS permissions problems.</span></span>  
  
 <span data-ttu-id="e129e-105">IIS 提供了用于创建作为不同宿主进程在其自己的内存空间中运行的 IIS 应用程序的功能。</span><span class="sxs-lookup"><span data-stu-id="e129e-105">IIS provides functionality for creating IIS applications as distinct host processes that are run in their own memory space.</span></span> <span data-ttu-id="e129e-106">一旦创建 IIS 应用程序主机，然后必须定义两个集的权限，IIS 应用程序主机**进程标识**和 IIS 应用程序主机**用户访问权限**。</span><span class="sxs-lookup"><span data-stu-id="e129e-106">Once you create an IIS application host, then you must define two sets of permissions, the IIS application host **process identity** and the IIS application host **user access rights**.</span></span> <span data-ttu-id="e129e-107">解决 IIS 权限疑难问题时，应检查的每个这些权限集。</span><span class="sxs-lookup"><span data-stu-id="e129e-107">You should examine each of these permissions sets when troubleshooting IIS permissions problems.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e129e-108">**进程标识**并**用户访问权限**也称为**安全上下文**的 IIS 应用程序宿主进程。</span><span class="sxs-lookup"><span data-stu-id="e129e-108">The **process identity** and **user access rights** are also referred to as the **security context** of the IIS application host process.</span></span>  
  
 <span data-ttu-id="e129e-109">本主题介绍如何设置**进程标识**并**用户访问权限**IIS 应用程序主机进程，并提供用于解决 IIS 权限疑难问题的一些通用准则。</span><span class="sxs-lookup"><span data-stu-id="e129e-109">This topic describes how to set **process identity** and **user access rights** for an IIS application host process and gives some general guidelines for resolving IIS permissions problems.</span></span>  
  
## <a name="setting-iis-application-host-process-identity"></a><span data-ttu-id="e129e-110">设置 IIS 应用程序主机进程标识</span><span class="sxs-lookup"><span data-stu-id="e129e-110">Setting IIS Application Host Process Identity</span></span>  
 <span data-ttu-id="e129e-111">IIS 应用程序主机进程的配置的主机进程所提供的功能级别而异。</span><span class="sxs-lookup"><span data-stu-id="e129e-111">Configuration of an IIS application host process can vary depending on the level of functionality being served by the host process.</span></span> <span data-ttu-id="e129e-112">例如，通常与作为 ASP 页或 ASP.NET 应用程序 IIS 应用程序宿主进程不同配置 IIS 应用程序宿主进程，仅作为静态 HTML 页。</span><span class="sxs-lookup"><span data-stu-id="e129e-112">For example, an IIS application host process that only serves static HTML pages is typically configured differently than an IIS application host process that serves ASP pages or ASP.NET applications.</span></span>  
  
 <span data-ttu-id="e129e-113">IIS 应用程序主机进程的配置根据托管应用程序的 IIS 版本各不相同。</span><span class="sxs-lookup"><span data-stu-id="e129e-113">Configuration of an IIS application host process also varies depending on the version of IIS that is hosting the application.</span></span> <span data-ttu-id="e129e-114">Windows Server 2008 (IIS 7.0) 上运行的应用程序的主机进程标识所依据的应用程序与关联的应用程序池标识。</span><span class="sxs-lookup"><span data-stu-id="e129e-114">The host process identity of applications running on Windows Server 2008 (IIS 7.0) is governed by the identity of the application pool associated with the application.</span></span>  
  
### <a name="setting-iis-process-identity-for-iis-70-on-windows-server-2008-or-windows-vista"></a><span data-ttu-id="e129e-115">设置 Windows Server 2008 上的 IIS 7.0 的 IIS 进程标识或 Windows Vista</span><span class="sxs-lookup"><span data-stu-id="e129e-115">Setting IIS Process Identity for IIS 7.0 on Windows Server 2008 or Windows Vista</span></span>  
  
1.  <span data-ttu-id="e129e-116">单击**启动**，然后**所有程序**，然后单击**Internet Information Services (IIS) 7 Manager**。</span><span class="sxs-lookup"><span data-stu-id="e129e-116">Click **Start**, then **All Programs**, and click **Internet Information Services (IIS) 7 Manager**.</span></span>  
  
2.  <span data-ttu-id="e129e-117">在 Internet 信息服务 (IIS) 管理器中，展开*\<计算机名\>\*\*\*(User account)*\* 单击**应用程序池**。</span><span class="sxs-lookup"><span data-stu-id="e129e-117">In Internet Information Services (IIS) Manager, expand *\<computer name\>\*\*\*(User account)*\* and click **Application Pools**.</span></span>  
  
3.  <span data-ttu-id="e129e-118">右键单击应用程序池，然后单击**查看应用程序**若要查看与应用程序池相关联的应用程序。</span><span class="sxs-lookup"><span data-stu-id="e129e-118">Right-click an application pool and click **View Applications** to see the applications associated with the application pool.</span></span>  
  
4.  <span data-ttu-id="e129e-119">右键单击应用程序池，然后单击**高级设置**显示应用程序池高级设置对话框。</span><span class="sxs-lookup"><span data-stu-id="e129e-119">Right-click an application pool and click **Advanced Settings** to display the Advanced Settings dialog for the application pool.</span></span>  
  
5.  <span data-ttu-id="e129e-120">通过单击旁边的省略号 （...） 按钮来修改应用程序池标识**标识**下**进程模型**一部分**高级设置**对话框框。</span><span class="sxs-lookup"><span data-stu-id="e129e-120">Modify the identity for the application pool by clicking the ellipsis (…) button next to **Identity** under the **Process Model** section of the **Advanced Settings** dialog box.</span></span>  
  
## <a name="setting-user-access-rights-for-the-iis-server"></a><span data-ttu-id="e129e-121">设置用户访问权限是针对 IIS 服务器</span><span class="sxs-lookup"><span data-stu-id="e129e-121">Setting User Access Rights for the IIS Server</span></span>  
 <span data-ttu-id="e129e-122">进程标识控制到正在运行的 IIS 应用程序宿主进程可用的安全上下文，而用户访问权限控制实际访问所承载网页的帐户的安全上下文。</span><span class="sxs-lookup"><span data-stu-id="e129e-122">While process identity governs the security context available to the running IIS application host process, user access permissions govern the security context for the account that is actually accessing the Web page(s) being served.</span></span> <span data-ttu-id="e129e-123">对于这两个安全上下文，以避免权限错误，必须正确设置权限。</span><span class="sxs-lookup"><span data-stu-id="e129e-123">Permissions must be set appropriately for both security contexts to avoid permissions errors.</span></span>  
  
 <span data-ttu-id="e129e-124">IIS 7.0 支持以下用户身份验证方法：</span><span class="sxs-lookup"><span data-stu-id="e129e-124">IIS 7.0 supports the following user authentication methods:</span></span>  
  
-   <span data-ttu-id="e129e-125">**匿名访问：** 允许用户建立匿名连接。</span><span class="sxs-lookup"><span data-stu-id="e129e-125">**Anonymous access:** Allows users to establish an anonymous connection.</span></span> <span data-ttu-id="e129e-126">使用指定的来宾帐户对用户的 IIS 服务器日志。</span><span class="sxs-lookup"><span data-stu-id="e129e-126">The IIS server logs on the user with the specified guest account.</span></span>  
  
-   <span data-ttu-id="e129e-127">**ASP.NET 模拟**允许在两个不同的上下文之一中运行应用程序： 作为通过 IIS 身份验证的用户或作为你设置的任意帐户。</span><span class="sxs-lookup"><span data-stu-id="e129e-127">**ASP.NET Impersonation** Allows an application to run in one of two different contexts: either as the user authenticated by IIS or as an arbitrary account that you set up.</span></span>  
  
-   <span data-ttu-id="e129e-128">**基本身份验证：** 以纯文本形式，以未加密形式在网络上传输密码。</span><span class="sxs-lookup"><span data-stu-id="e129e-128">**Basic authentication:** Transmits passwords across the network in plaintext, an unencrypted form.</span></span>  
  
-   <span data-ttu-id="e129e-129">**摘要式身份验证：** 仅适用于 Active Directory 帐户，通过在网络中，而不是纯文本密码发送的哈希值。</span><span class="sxs-lookup"><span data-stu-id="e129e-129">**Digest authentication:** Works only with Active Directory accounts, sending a hash value over the network, rather than a plaintext password.</span></span> <span data-ttu-id="e129e-130">摘要式身份验证可在代理服务器和其他防火墙，可在 Web 分布式创作和版本管理 (WebDAV) 目录。</span><span class="sxs-lookup"><span data-stu-id="e129e-130">Digest authentication works across proxy servers and other firewalls and is available on Web Distributed Authoring and Versioning (WebDAV) directories.</span></span> <span data-ttu-id="e129e-131">使用摘要式身份验证需要先禁用匿名身份验证。</span><span class="sxs-lookup"><span data-stu-id="e129e-131">Use of Digest authentication requires that Anonymous authentication is disabled first.</span></span>  
  
-   <span data-ttu-id="e129e-132">**窗体身份验证**适用的高流量站点或公用服务器上的应用程序的身份验证。</span><span class="sxs-lookup"><span data-stu-id="e129e-132">**Forms Authentication** Accommodates authentication for high-traffic sites or applications on public servers.</span></span> <span data-ttu-id="e129e-133">窗体身份验证允许你管理客户端注册和身份验证在应用程序级别，而不是依赖于由操作系统提供的身份验证机制。</span><span class="sxs-lookup"><span data-stu-id="e129e-133">Forms authentication lets you manage client registration and authentication at the application level, instead of relying on the authentication mechanisms provided by the operating system.</span></span>  
  
-   <span data-ttu-id="e129e-134">**Windows 身份验证：** 使用 Windows 域身份验证客户端连接进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="e129e-134">**Windows authentication:** Uses authentication on your Windows domain to authenticate client connections.</span></span>  
  
#### <a name="to-set-user-access-rights-for-a-virtual-directory-in-iis-70"></a><span data-ttu-id="e129e-135">若要在 IIS 7.0 中设置虚拟目录的用户访问权限</span><span class="sxs-lookup"><span data-stu-id="e129e-135">To set user access rights for a virtual directory in IIS 7.0</span></span>  
  
1.  <span data-ttu-id="e129e-136">在 Internet 信息服务 (IIS) 管理器中，展开*\<计算机名\>*，**站点**，以及**Default Web Site**中**连接**窗格。</span><span class="sxs-lookup"><span data-stu-id="e129e-136">In the Internet Information Services (IIS) Manager, expand *\<computer name\>*, **Sites**, and **Default Web Site** in the **Connections** pane.</span></span>  
  
2.  <span data-ttu-id="e129e-137">单击此项可选择的虚拟目录，然后单击**功能视图**底部的工作区窗格中列出的虚拟目录的可配置功能。</span><span class="sxs-lookup"><span data-stu-id="e129e-137">Click to select the virtual directory and click the **Features View** at the bottom of the Workspace pane to list the configurable features for the virtual directory.</span></span>  
  
3.  <span data-ttu-id="e129e-138">双击**身份验证**工作区窗格中列出的虚拟目录启用的身份验证方法中的新功能。</span><span class="sxs-lookup"><span data-stu-id="e129e-138">Double-click the **Authentication** feature in the Workspace pane to list the authentication methods that are enabled for the virtual directory.</span></span>  
  
4.  <span data-ttu-id="e129e-139">单击以选择你想要启用或禁用并单击的身份验证方法**禁用**或**启用**中**操作**IIS 管理器窗格。</span><span class="sxs-lookup"><span data-stu-id="e129e-139">Click to select the authentication method that you would like to enable or disable and click either **Disable** or **Enable** in the **Actions** pane of the IIS Manager.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e129e-140">如果**启用匿名访问**是启用，IIS 将设置用户访问权限为配置的匿名用户标识之前设置与任何其他用户访问权限启用身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="e129e-140">If **Enable anonymous access** is enabled, IIS will set user access rights as the configured Anonymous user identity before setting user access rights with any other enabled authentication methods.</span></span>  
    >   
    >  <span data-ttu-id="e129e-141">若要配置匿名用户标识，右键单击**匿名身份验证**方法，并单击**编辑**以显示**编辑匿名身份验证凭据**对话框。</span><span class="sxs-lookup"><span data-stu-id="e129e-141">To configure the Anonymous user identity, right-click the **Anonymous Authentication** method and click **Edit** to display the **Edit Anonymous Authentication Credentials** dialog.</span></span>  
  
## <a name="general-guidelines-for-resolving-iis-permissions-problems"></a><span data-ttu-id="e129e-142">解决 IIS 权限问题的一般指导原则</span><span class="sxs-lookup"><span data-stu-id="e129e-142">General Guidelines for Resolving IIS Permissions Problems</span></span>  
 <span data-ttu-id="e129e-143">请执行以下步骤解决 IIS 权限：</span><span class="sxs-lookup"><span data-stu-id="e129e-143">Follow these steps to troubleshoot IIS permissions:</span></span>  
  
1.  <span data-ttu-id="e129e-144">检查错误的 IIS 服务器计算机的应用程序日志。</span><span class="sxs-lookup"><span data-stu-id="e129e-144">Check the application log of the IIS Server computer for errors.</span></span>  
  
2.  <span data-ttu-id="e129e-145">按照中的步骤[IIS 7.0:配置为在 IIS 7.0 失败请求跟踪](http://go.microsoft.com/fwlink/?LinkId=130600)来解决 IIS 7.0 计算机上的权限问题。</span><span class="sxs-lookup"><span data-stu-id="e129e-145">Follow the steps in [IIS 7.0: Configuring Tracing for Failed Requests in IIS 7.0](http://go.microsoft.com/fwlink/?LinkId=130600) to troubleshoot permissions problems on IIS 7.0 computers.</span></span>  
  
3.  <span data-ttu-id="e129e-146">检查 HTTP 401 错误 IIS 服务器的 IIS 日志文件。</span><span class="sxs-lookup"><span data-stu-id="e129e-146">Check the IIS log files of the IIS server for HTTP 401 errors.</span></span>  
  
     <span data-ttu-id="e129e-147">默认情况下，IIS 上运行 Windows Server 2008 或 Windows Vista 的计算机的日志文件位于以下目录中：</span><span class="sxs-lookup"><span data-stu-id="e129e-147">By default the IIS log files on a computer running Windows Server 2008 or Windows Vista are located in the following directory:</span></span>  
  
     <span data-ttu-id="e129e-148">C:\inetpub\logs\LogFiles\W3SVC1</span><span class="sxs-lookup"><span data-stu-id="e129e-148">C:\inetpub\logs\LogFiles\W3SVC1</span></span>\  
  
    -   <span data-ttu-id="e129e-149">如果 IIS 7.0 计算机包含 HTTP 401 错误，请按照 Microsoft 知识库文章 943891 中的步骤，IIS 日志文件，"HTTP 状态代码在 IIS 7.0 中"网址[ http://support.microsoft.com/kb/943891 ](http://support.microsoft.com/kb/943891)来确定子状态代码和对基于状态代码的权限问题进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="e129e-149">If the IIS log file for an IIS 7.0 computer contains HTTP 401 errors, follow the steps in Microsoft Knowledge Base article 943891, "The HTTP status codes in IIS 7.0" available at [http://support.microsoft.com/kb/943891](http://support.microsoft.com/kb/943891) to determine the substatus code and to troubleshoot the permissions problem based on the status code.</span></span>  
  
    -   <span data-ttu-id="e129e-150">检查的值**cs 用户名**与 HTTP 401 错误关联的字段。</span><span class="sxs-lookup"><span data-stu-id="e129e-150">Check the value of the **cs-username** field associated with the HTTP 401 error.</span></span> <span data-ttu-id="e129e-151">此字段包含访问 IIS 服务器的经过身份验证用户的名称。</span><span class="sxs-lookup"><span data-stu-id="e129e-151">This field contains the name of the authenticated user who accessed the IIS server.</span></span> <span data-ttu-id="e129e-152">在此字段中一个连字符 （-） 表示匿名用户帐户。</span><span class="sxs-lookup"><span data-stu-id="e129e-152">The anonymous user account is represented by a hyphen (-) in this field.</span></span> <span data-ttu-id="e129e-153">请确保此帐户具有相应的资源的权限。</span><span class="sxs-lookup"><span data-stu-id="e129e-153">Ensure that this account has permissions on the appropriate resources.</span></span>  
  
4.  <span data-ttu-id="e129e-154">验证正确设置 IIS 应用程序主机进程使用的进程标识凭据的帐户具有适当的权限。</span><span class="sxs-lookup"><span data-stu-id="e129e-154">Verify that the process identity credentials used by the IIS application host process are set correctly and that the account has the appropriate permissions.</span></span> <span data-ttu-id="e129e-155">如果用于进程标识的帐户没有足够的权限然后更改帐户或授予适当的权限的帐户。</span><span class="sxs-lookup"><span data-stu-id="e129e-155">If the account used for the process identity has insufficient permissions then either change the account or grant the account the appropriate permissions.</span></span>  
  
5.  <span data-ttu-id="e129e-156">使用 RegMon 和 FileMon 实用程序中所述[工具和实用程序用于故障排除](../core/tools-and-utilities-to-use-for-troubleshooting.md)诊断文件或注册表访问权限问题。</span><span class="sxs-lookup"><span data-stu-id="e129e-156">Use the RegMon and FileMon utilities described in [Tools and Utilities to Use for Troubleshooting](../core/tools-and-utilities-to-use-for-troubleshooting.md) to diagnose file or registry access permissions problems.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e129e-157">请参阅</span><span class="sxs-lookup"><span data-stu-id="e129e-157">See Also</span></span>  
 <span data-ttu-id="e129e-158">[故障排除的 BizTalk Server 权限](../core/troubleshooting-biztalk-server-permissions.md) </span><span class="sxs-lookup"><span data-stu-id="e129e-158">[Troubleshooting BizTalk Server Permissions](../core/troubleshooting-biztalk-server-permissions.md) </span></span>  
 [<span data-ttu-id="e129e-159">IIS 7.0:在 IIS 7.0 中配置身份验证</span><span class="sxs-lookup"><span data-stu-id="e129e-159">IIS 7.0: Configuring Authentication in IIS 7.0</span></span>](http://go.microsoft.com/fwlink/?LinkId=129909)