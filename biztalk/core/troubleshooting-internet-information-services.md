---
title: Internet 信息服务的故障排除 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f77084f1-5797-42ab-bbf6-fe815144232e
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f7ca928aa2e47b5c62548aba02834b96d6a3baf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006654"
---
# <a name="troubleshooting-internet-information-services"></a><span data-ttu-id="50844-102">Internet 信息服务的故障排除</span><span class="sxs-lookup"><span data-stu-id="50844-102">Troubleshooting Internet Information Services</span></span>
<span data-ttu-id="50844-103">Microsoft Internet 信息服务 (IIS) 被 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 广泛用于各种功能，其中包括 HTTP、SOAP 和 Windows SharePoint Services 适配器。</span><span class="sxs-lookup"><span data-stu-id="50844-103">Microsoft Internet Information Services (IIS) is used extensively by Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for various functionality including the HTTP, SOAP, and Windows SharePoint Services adapters.</span></span> <span data-ttu-id="50844-104">本主题介绍使用 IIS 时可能遇到的某些已知问题以及这些问题的可能解决方法。</span><span class="sxs-lookup"><span data-stu-id="50844-104">This topic describes some known issues that you may encounter with IIS and possible resolutions to these issues.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="50844-105">已知问题</span><span class="sxs-lookup"><span data-stu-id="50844-105">Known Issues</span></span>  
 <span data-ttu-id="50844-106">要显示本主题中所列的错误，必须将 Internet Explorer 配置为禁用友好 HTTP 错误消息。</span><span class="sxs-lookup"><span data-stu-id="50844-106">The errors documented in this topic may not be displayed unless you configure Internet Explorer to disable friendly HTTP error messages.</span></span>  
  
#### <a name="to-configure-internet-explorer-to-disable-friendly-http-error-messages"></a><span data-ttu-id="50844-107">配置 Internet Explorer 以禁用友好 HTTP 错误消息</span><span class="sxs-lookup"><span data-stu-id="50844-107">To configure Internet Explorer to disable friendly HTTP error messages</span></span>  
  
1.  <span data-ttu-id="50844-108">上**工具**菜单上，单击**Internet 选项**。</span><span class="sxs-lookup"><span data-stu-id="50844-108">On the **Tools** menu, click **Internet Options**.</span></span>  
  
2.  <span data-ttu-id="50844-109">上**高级**选项卡上，在**浏览**部分中，清除**显示友好 HTTP 错误消息**复选框，然后依次**确定**。</span><span class="sxs-lookup"><span data-stu-id="50844-109">On the **Advanced** tab, in the **Browsing** section, clear the **Show friendly HTTP error messages** check box, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="50844-110">关闭 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="50844-110">Close Internet Explorer.</span></span>  
  
#### <a name="http-404---file-not-found-error-occurs-when-accessing-a-web-page-on-an-iis-server"></a><span data-ttu-id="50844-111">访问 IIS 服务器上的网页时出现“ HTTP 404 – 未找到文件” 错误</span><span class="sxs-lookup"><span data-stu-id="50844-111">"HTTP 404 - File not found" error occurs when accessing a Web page on an IIS server</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="50844-112">问题</span><span class="sxs-lookup"><span data-stu-id="50844-112">Problem</span></span>  
 <span data-ttu-id="50844-113">尝试访问 IIS 服务器上的网页时显示类似如下错误：</span><span class="sxs-lookup"><span data-stu-id="50844-113">When you attempt to access a Web page on an IIS server an error similar to the following is displayed:</span></span>  
  
 <span data-ttu-id="50844-114">找不到该页</span><span class="sxs-lookup"><span data-stu-id="50844-114">Page Cannot Be Found</span></span>  
  
 <span data-ttu-id="50844-115">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="50844-115">\- or -</span></span>  
  
 <span data-ttu-id="50844-116">HTTP 404 – 未找到文件</span><span class="sxs-lookup"><span data-stu-id="50844-116">HTTP 404 - File not found</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="50844-117">原因</span><span class="sxs-lookup"><span data-stu-id="50844-117">Cause</span></span>  
 <span data-ttu-id="50844-118">此错误可能是由于以下原因引发：</span><span class="sxs-lookup"><span data-stu-id="50844-118">This error may occur for the following reasons:</span></span>  
  
-   <span data-ttu-id="50844-119">所请求的文件已重命名。</span><span class="sxs-lookup"><span data-stu-id="50844-119">The requested file has been renamed.</span></span>  
  
-   <span data-ttu-id="50844-120">所请求的文件已移到其他位置或被删除。</span><span class="sxs-lookup"><span data-stu-id="50844-120">The requested file has been moved to another location or deleted.</span></span>  
  
-   <span data-ttu-id="50844-121">因维护、更新或其他未知原因，所请求的文件暂时不可用。</span><span class="sxs-lookup"><span data-stu-id="50844-121">The requested file is temporarily unavailable due to maintenance, upgrades, or other unknown causes.</span></span>  
  
-   <span data-ttu-id="50844-122">所请求的文件不存在。</span><span class="sxs-lookup"><span data-stu-id="50844-122">The requested file does not exist.</span></span>  
  
-   <span data-ttu-id="50844-123">IIS 6.0：未启用适当 Web Services 扩展或 MIME 类型。</span><span class="sxs-lookup"><span data-stu-id="50844-123">IIS 6.0: The appropriate Web service extension or MIME type is not enabled.</span></span>  
  
-   <span data-ttu-id="50844-124">虚拟目录映射到其另一个服务器上驱动器的根目录中。</span><span class="sxs-lookup"><span data-stu-id="50844-124">A virtual directory is mapped to the root of a drive on another server.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="50844-125">解决方法</span><span class="sxs-lookup"><span data-stu-id="50844-125">Resolution</span></span>  
 <span data-ttu-id="50844-126">按照 Microsoft 知识库文章 248033，"常见原因 IIS 服务器将返回"HTTP 404-文件未找到"错误"的解决方法部分中的步骤可在[ http://support.microsoft.com/kb/248033 ](http://support.microsoft.com/kb/248033)。</span><span class="sxs-lookup"><span data-stu-id="50844-126">Follow the steps in the RESOLUTION section of Microsoft Knowledge Base article 248033, "Common reasons IIS Server returns "HTTP 404 - File not found" error" available at [http://support.microsoft.com/kb/248033](http://support.microsoft.com/kb/248033).</span></span>  
  
#### <a name="cannot-find-server-or-dns-error-error-occurs-when-accessing-a-web-page-on-an-iis-server"></a><span data-ttu-id="50844-127">访问 IIS 服务器上的网页时出现“找不到服务器或发生 DNS 错误”错误</span><span class="sxs-lookup"><span data-stu-id="50844-127">"Cannot find server or DNS Error error" occurs when accessing a Web page on an IIS server</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="50844-128">问题</span><span class="sxs-lookup"><span data-stu-id="50844-128">Problem</span></span>  
 <span data-ttu-id="50844-129">尝试访问 IIS 服务器上的网页时显示类似如下错误：</span><span class="sxs-lookup"><span data-stu-id="50844-129">When you attempt to access a Web page on an IIS server an error similar to the following is displayed:</span></span>  
  
 <span data-ttu-id="50844-130">该页无法显示</span><span class="sxs-lookup"><span data-stu-id="50844-130">The Page Cannot Be Displayed</span></span>  
  
 <span data-ttu-id="50844-131">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="50844-131">\- or -</span></span>  
  
 <span data-ttu-id="50844-132">找不到服务器或发生 DNS 错误</span><span class="sxs-lookup"><span data-stu-id="50844-132">Cannot find server or DNS Error</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="50844-133">原因</span><span class="sxs-lookup"><span data-stu-id="50844-133">Cause</span></span>  
 <span data-ttu-id="50844-134">此错误可能是由于以下原因引发：</span><span class="sxs-lookup"><span data-stu-id="50844-134">This error may occur for the following reasons:</span></span>  
  
-   <span data-ttu-id="50844-135">Internet Explorer 的连接设置不正确。</span><span class="sxs-lookup"><span data-stu-id="50844-135">Your Internet Explorer connection settings are incorrect.</span></span>  
  
-   <span data-ttu-id="50844-136">安装了配置不正确、不能正常工作或不兼容的防火墙或代理软件。</span><span class="sxs-lookup"><span data-stu-id="50844-136">Incorrectly configured, non-functioning, or incompatible firewall or proxy software has been installed.</span></span>  
  
-   <span data-ttu-id="50844-137">某个 Hosts 文件中有不正确的条目。</span><span class="sxs-lookup"><span data-stu-id="50844-137">There is an incorrect entry in a Hosts file.</span></span>  
  
-   <span data-ttu-id="50844-138">网络适配器未正常工作，或者安装了不兼容的网络适配器驱动程序。</span><span class="sxs-lookup"><span data-stu-id="50844-138">Your network adapter is not functioning correctly or you have incompatible network adapter drivers installed.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="50844-139">解决方法</span><span class="sxs-lookup"><span data-stu-id="50844-139">Resolution</span></span>  
 <span data-ttu-id="50844-140">按照 Microsoft 知识库文章 326155 的解决方法部分中的步骤"尝试访问 Internet 资源管理器中的 Web 站点时的错误消息:"页无法显示""网址[ http://support.microsoft.com/kb/326155 ](http://support.microsoft.com/kb/326155)。</span><span class="sxs-lookup"><span data-stu-id="50844-140">Follow the steps in the RESOLUTION section of Microsoft Knowledge Base article 326155, "Error message when you try to access a Web site in Internet Explorer: "Page Cannot Be Displayed"" available at [http://support.microsoft.com/kb/326155](http://support.microsoft.com/kb/326155).</span></span>  
  
#### <a name="401---access-denied-error-occurs-when-accessing-a-web-page-on-an-iis-server"></a><span data-ttu-id="50844-141">访问 IIS 服务器上的网页时出现“ 401 – 访问被拒绝” 错误</span><span class="sxs-lookup"><span data-stu-id="50844-141">"401 - Access denied" error occurs when accessing a Web page on an IIS server</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="50844-142">问题</span><span class="sxs-lookup"><span data-stu-id="50844-142">Problem</span></span>  
 <span data-ttu-id="50844-143">尝试访问 IIS 服务器上的网页时显示类似如下错误：</span><span class="sxs-lookup"><span data-stu-id="50844-143">When you attempt to access a Web page on an IIS server an error similar to the following is displayed:</span></span>  
  
 <span data-ttu-id="50844-144">401 – 访问被拒绝</span><span class="sxs-lookup"><span data-stu-id="50844-144">401 - Access denied</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="50844-145">原因</span><span class="sxs-lookup"><span data-stu-id="50844-145">Cause</span></span>  
 <span data-ttu-id="50844-146">IIS 定义了若干不同的 401 错误以表明更具体的错误原因。</span><span class="sxs-lookup"><span data-stu-id="50844-146">IIS defines several different 401 errors that indicate a more specific cause of the error.</span></span> <span data-ttu-id="50844-147">这些具体错误代码显示在浏览器中：</span><span class="sxs-lookup"><span data-stu-id="50844-147">These specific error codes are displayed in the browser:</span></span>  
  
- <span data-ttu-id="50844-148">401.1 – 登录失败 。</span><span class="sxs-lookup"><span data-stu-id="50844-148">401.1 - Logon failed.</span></span>  
  
- <span data-ttu-id="50844-149">401.2 – 服务器配置导致登录失败 。</span><span class="sxs-lookup"><span data-stu-id="50844-149">401.2 - Logon failed due to server configuration.</span></span>  
  
- <span data-ttu-id="50844-150">401.3 – 因资源上的 ACL 而未能获得授权 。</span><span class="sxs-lookup"><span data-stu-id="50844-150">401.3 - Unauthorized due to ACL on resource.</span></span>  
  
- <span data-ttu-id="50844-151">401.4 – 筛选器授权失败 。</span><span class="sxs-lookup"><span data-stu-id="50844-151">401.4 - Authorization failed by filter.</span></span>  
  
- <span data-ttu-id="50844-152">401.5 - ISAPI/CGI 应用程序授权失败。</span><span class="sxs-lookup"><span data-stu-id="50844-152">401.5 - Authorization failed by ISAPI/CGI application.</span></span>  
  
- <span data-ttu-id="50844-153">401.7 – 访问被 Web 服务器上的 URL 授权策略拒绝 。</span><span class="sxs-lookup"><span data-stu-id="50844-153">401.7 – Access denied by URL authorization policy on the Web server.</span></span> <span data-ttu-id="50844-154">此错误代码是特定于 IIS 6.0 的。</span><span class="sxs-lookup"><span data-stu-id="50844-154">This error code is specific to IIS 6.0.</span></span>  
  
  <span data-ttu-id="50844-155">IIS 7.0 状态代码的完整列表，请参阅 Microsoft 知识库文章 943891，"IIS 7.0 中的 HTTP 状态代码"网址[ http://support.microsoft.com/kb/943891 ](http://support.microsoft.com/kb/943891)。</span><span class="sxs-lookup"><span data-stu-id="50844-155">For a complete list of the IIS 7.0 status codes, see Microsoft Knowledge Base article 943891, "The HTTP status codes in IIS 7.0" available at [http://support.microsoft.com/kb/943891](http://support.microsoft.com/kb/943891).</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="50844-156">解决方法</span><span class="sxs-lookup"><span data-stu-id="50844-156">Resolution</span></span>  
 <span data-ttu-id="50844-157">按照中的步骤[解决 IIS 权限疑难问题的准则](../core/guidelines-for-resolving-iis-permissions-problems.md)解决 IIS 权限问题。</span><span class="sxs-lookup"><span data-stu-id="50844-157">Follow the steps in [Guidelines for Resolving IIS Permissions Problems](../core/guidelines-for-resolving-iis-permissions-problems.md) to resolve IIS permissions problems.</span></span>  
  
#### <a name="500---internal-server-error-occurs-when-accessing-a-web-page-on-an-iis-server"></a><span data-ttu-id="50844-158">访问 IIS 服务器上的网页时出现“ 500 – 内部服务器错误”</span><span class="sxs-lookup"><span data-stu-id="50844-158">"500 - Internal server error" occurs when accessing a Web page on an IIS server</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="50844-159">问题</span><span class="sxs-lookup"><span data-stu-id="50844-159">Problem</span></span>  
 <span data-ttu-id="50844-160">尝试访问 IIS 服务器上的网页时显示类似如下错误：</span><span class="sxs-lookup"><span data-stu-id="50844-160">When you attempt to access a Web page on an IIS server an error similar to the following is displayed:</span></span>  
  
 <span data-ttu-id="50844-161">500 – 内部服务器错误</span><span class="sxs-lookup"><span data-stu-id="50844-161">500 - Internal server error</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="50844-162">原因</span><span class="sxs-lookup"><span data-stu-id="50844-162">Cause</span></span>  
 <span data-ttu-id="50844-163">服务器方面的许多问题都可能导致出现此错误消息。</span><span class="sxs-lookup"><span data-stu-id="50844-163">This error message can be caused by a wide variety of server-side problems.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="50844-164">解决方法</span><span class="sxs-lookup"><span data-stu-id="50844-164">Resolution</span></span>  
 <span data-ttu-id="50844-165">若要解决此问题，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="50844-165">To resolve the issue, do the following:</span></span>  
  
- <span data-ttu-id="50844-166">检查 IIS 服务器的应用程序日志以获取有关出现此错误的原因的信息。</span><span class="sxs-lookup"><span data-stu-id="50844-166">Review the Application log of the IIS server for information about why this error occurs.</span></span>  
  
- <span data-ttu-id="50844-167">检查 IIS 日志文件或 HTTPERR 日志文件以获取可能有助于确定错误原因的信息。</span><span class="sxs-lookup"><span data-stu-id="50844-167">Review the IIS log files or HTTPERR log files for information that may be helpful for determining the cause of the error.</span></span> <span data-ttu-id="50844-168">默认情况下，在运行 [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] 操作系统的计算机上的 IIS 日志文件位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="50844-168">By default the IIS log files on a computer running [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] operating systems are located in the following directory:</span></span>  
  
   <span data-ttu-id="50844-169"><em>%Windir%\\</em>system32\LogFiles\W3SVC1\\</span><span class="sxs-lookup"><span data-stu-id="50844-169"><em>%WinDir%\\</em>system32\LogFiles\W3SVC1\\</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="50844-170">*%Windir%* 是 IIS 服务器上的 Windows 目录的位置的占位符。</span><span class="sxs-lookup"><span data-stu-id="50844-170">*%WinDir%* is a placeholder for the location of the Windows directory on the IIS server.</span></span>  
  
   <span data-ttu-id="50844-171">默认情况下，在运行 Windows Server 2008 或 Windows Vista 的计算机中，IIS 日志文件位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="50844-171">By default the IIS log files on a computer running Windows Server 2008 or Windows Vista are located in the following directory:</span></span>  
  
   <span data-ttu-id="50844-172">C:\inetpub\logs\LogFiles\W3SVC1\\</span><span class="sxs-lookup"><span data-stu-id="50844-172">C:\inetpub\logs\LogFiles\W3SVC1\\</span></span>  
  
   <span data-ttu-id="50844-173">默认情况下，[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] 上的 HTTPERR 日志文件位于以下目录中：</span><span class="sxs-lookup"><span data-stu-id="50844-173">By default the HTTPERR log files on [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] are located in the following directory:</span></span>  
  
   <span data-ttu-id="50844-174"><em>%Windir%</em>system32LogFilesHTTPERR</span><span class="sxs-lookup"><span data-stu-id="50844-174"><em>%WinDir%</em>system32LogFilesHTTPERR</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="50844-175">只有 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 或 Windows Vista 计算机上才有 HTTPERR 日志文件。</span><span class="sxs-lookup"><span data-stu-id="50844-175">The HTTPERR log file is only available on a [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], or Windows Vista computer.</span></span>  
  
#### <a name="service-unavailable-error-occurs-when-accessing-a-web-page-on-an-iis-server"></a><span data-ttu-id="50844-176">访问 IIS 服务器上的网页时出现“服务不可用”错误</span><span class="sxs-lookup"><span data-stu-id="50844-176">"Service Unavailable" error occurs when accessing a Web page on an IIS server</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="50844-177">问题</span><span class="sxs-lookup"><span data-stu-id="50844-177">Problem</span></span>  
 <span data-ttu-id="50844-178">尝试访问 IIS 服务器上的网页时显示类似如下错误：</span><span class="sxs-lookup"><span data-stu-id="50844-178">When you attempt to access a Web page on an IIS server an error similar to the following is displayed:</span></span>  
  
 <span data-ttu-id="50844-179">服务不可用</span><span class="sxs-lookup"><span data-stu-id="50844-179">Service Unavailable</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="50844-180">原因</span><span class="sxs-lookup"><span data-stu-id="50844-180">Cause</span></span>  
 <span data-ttu-id="50844-181">此错误的最常见原因是：该网页的应用程序池（IIS 6.0 和 IIS 7.0）已停止。</span><span class="sxs-lookup"><span data-stu-id="50844-181">The most common cause for this error is that the application pool (IIS 6.0 and IIS 7.0) for the Web page is stopped.</span></span> <span data-ttu-id="50844-182">如果该应用程序池或 COM+ 应用程序配置了标识，但指定的用户名或密码无效，则通常会出现此错误。</span><span class="sxs-lookup"><span data-stu-id="50844-182">This commonly occurs if the application pool or COM+ application is configured with an Identity for which the specified user name and or password is invalid.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="50844-183">解决方法</span><span class="sxs-lookup"><span data-stu-id="50844-183">Resolution</span></span>  
 <span data-ttu-id="50844-184">按照本主题的"设置 IIS 应用程序主机进程标识"部分中的步骤[解决 IIS 权限疑难问题的准则](../core/guidelines-for-resolving-iis-permissions-problems.md)设置相应的主机进程标识。</span><span class="sxs-lookup"><span data-stu-id="50844-184">Follow the steps in the "Setting IIS Application Host Process Identity" section of the topic [Guidelines for Resolving IIS Permissions Problems](../core/guidelines-for-resolving-iis-permissions-problems.md) to set the appropriate host process identity.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50844-185">请参阅</span><span class="sxs-lookup"><span data-stu-id="50844-185">See Also</span></span>  
 [<span data-ttu-id="50844-186">解决 IIS 权限疑难问题的准则</span><span class="sxs-lookup"><span data-stu-id="50844-186">Guidelines for Resolving IIS Permissions Problems</span></span>](../core/guidelines-for-resolving-iis-permissions-problems.md)