---
title: Internet 信息服务疑难解答 |Microsoft 文档
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
ms.openlocfilehash: 222d034c2dee38f041bb53b3164869712201bc76
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22280101"
---
# <a name="troubleshooting-internet-information-services"></a>Internet 信息服务疑难解答
Microsoft Internet 信息服务 (IIS) 被 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 广泛用于各种功能，其中包括 HTTP、SOAP 和 Windows SharePoint Services 适配器。 本主题介绍使用 IIS 时可能遇到的某些已知问题以及这些问题的可能解决方法。  
  
## <a name="known-issues"></a>已知问题  
 要显示本主题中所列的错误，必须将 Internet Explorer 配置为禁用友好 HTTP 错误消息。  
  
#### <a name="to-configure-internet-explorer-to-disable-friendly-http-error-messages"></a>配置 Internet Explorer 以禁用友好 HTTP 错误消息  
  
1.  上**工具**菜单上，单击**Internet 选项**。  
  
2.  上**高级**选项卡上，在**浏览**部分中，清除**显示友好 HTTP 错误信息**复选框，并依次**确定**。  
  
3.  关闭 Internet Explorer。  
  
#### <a name="http-404---file-not-found-error-occurs-when-accessing-a-web-page-on-an-iis-server"></a>访问 IIS 服务器上的网页时出现“ HTTP 404 – 未找到文件” 错误  
  
##### <a name="problem"></a>问题  
 尝试访问 IIS 服务器上的网页时显示类似如下错误：  
  
 找不到该页  
  
 \- 或 -  
  
 HTTP 404 – 未找到文件  
  
##### <a name="cause"></a>原因  
 此错误可能是由于以下原因引发：  
  
-   所请求的文件已重命名。  
  
-   所请求的文件已移到其他位置或被删除。  
  
-   因维护、更新或其他未知原因，所请求的文件暂时不可用。  
  
-   所请求的文件不存在。  
  
-   IIS 6.0：未启用适当 Web Services 扩展或 MIME 类型。  
  
-   虚拟目录映射到其另一个服务器上驱动器的根目录中。  
  
##### <a name="resolution"></a>解决方法  
 按照 Microsoft 知识库文章 248033，"常见原因 IIS 服务器将返回"HTTP 404-文件找不到"错误"的解决方法部分中的步骤在[http://support.microsoft.com/kb/248033](http://support.microsoft.com/kb/248033)。  
  
#### <a name="cannot-find-server-or-dns-error-error-occurs-when-accessing-a-web-page-on-an-iis-server"></a>访问 IIS 服务器上的网页时出现“找不到服务器或发生 DNS 错误”错误  
  
##### <a name="problem"></a>问题  
 尝试访问 IIS 服务器上的网页时显示类似如下错误：  
  
 该页无法显示  
  
 \- 或 -  
  
 找不到服务器或发生 DNS 错误  
  
##### <a name="cause"></a>原因  
 此错误可能是由于以下原因引发：  
  
-   Internet Explorer 的连接设置不正确。  
  
-   安装了配置不正确、不能正常工作或不兼容的防火墙或代理软件。  
  
-   某个 Hosts 文件中有不正确的条目。  
  
-   网络适配器未正常工作，或者安装了不兼容的网络适配器驱动程序。  
  
##### <a name="resolution"></a>解决方法  
 按照 Microsoft 知识库文章 326155 的解决方法部分中的步骤"当你尝试访问 Internet 资源管理器中的 Web 站点时的错误消息:"页无法显示""在可用[http://support.microsoft.com/kb/326155](http://support.microsoft.com/kb/326155).  
  
#### <a name="401---access-denied-error-occurs-when-accessing-a-web-page-on-an-iis-server"></a>访问 IIS 服务器上的网页时出现“ 401 – 访问被拒绝” 错误  
  
##### <a name="problem"></a>问题  
 尝试访问 IIS 服务器上的网页时显示类似如下错误：  
  
 401 – 访问被拒绝  
  
##### <a name="cause"></a>原因  
 IIS 定义了若干不同的 401 错误以表明更具体的错误原因。 这些具体错误代码显示在浏览器中：  
  
-   401.1 – 登录失败 。  
  
-   401.2 – 服务器配置导致登录失败 。  
  
-   401.3 – 因资源上的 ACL 而未能获得授权 。  
  
-   401.4 – 筛选器授权失败 。  
  
-   401.5 - ISAPI/CGI 应用程序授权失败。  
  
-   401.7 – 访问被 Web 服务器上的 URL 授权策略拒绝 。 此错误代码是特定于 IIS 6.0 的。  
  
 IIS 7.0 状态代码的完整列表，请参阅 Microsoft 知识库文章 943891，"在 IIS 7.0 中的 HTTP 状态代码"在可用[http://support.microsoft.com/kb/943891](http://support.microsoft.com/kb/943891)。  
  
##### <a name="resolution"></a>解决方法  
 按照中的步骤[解决 IIS 权限问题的指导原则](../core/guidelines-for-resolving-iis-permissions-problems.md)来解决 IIS 权限问题。  
  
#### <a name="500---internal-server-error-occurs-when-accessing-a-web-page-on-an-iis-server"></a>访问 IIS 服务器上的网页时出现“ 500 – 内部服务器错误”  
  
##### <a name="problem"></a>问题  
 尝试访问 IIS 服务器上的网页时显示类似如下错误：  
  
 500 – 内部服务器错误  
  
##### <a name="cause"></a>原因  
 服务器方面的许多问题都可能导致出现此错误消息。  
  
##### <a name="resolution"></a>解决方法  
 若要解决此问题，请执行以下操作：  
  
-   检查 IIS 服务器的应用程序日志以获取有关出现此错误的原因的信息。  
  
-   检查 IIS 日志文件或 HTTPERR 日志文件以获取可能有助于确定错误原因的信息。 默认情况下，在运行 [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] 操作系统的计算机上的 IIS 日志文件位于以下目录：  
  
     *%Windir%\\*system32\LogFiles\W3SVC1\  
  
    > [!NOTE]
    >  *%Windir%* 是 IIS 服务器上的 Windows 目录的位置的占位符。  
  
     默认情况下，在运行 Windows Server 2008 或 Windows Vista 的计算机中，IIS 日志文件位于以下目录：  
  
     C:\inetpub\logs\LogFiles\W3SVC1\  
  
     默认情况下，[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] 上的 HTTPERR 日志文件位于以下目录中：  
  
     *%Windir%* system32LogFilesHTTPERR  
  
    > [!NOTE]
    >  只有 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 或 Windows Vista 计算机上才有 HTTPERR 日志文件。  
  
#### <a name="service-unavailable-error-occurs-when-accessing-a-web-page-on-an-iis-server"></a>访问 IIS 服务器上的网页时出现“服务不可用”错误  
  
##### <a name="problem"></a>问题  
 尝试访问 IIS 服务器上的网页时显示类似如下错误：  
  
 服务不可用  
  
##### <a name="cause"></a>原因  
 此错误的最常见原因是：该网页的应用程序池（IIS 6.0 和 IIS 7.0）已停止。 如果该应用程序池或 COM+ 应用程序配置了标识，但指定的用户名或密码无效，则通常会出现此错误。  
  
##### <a name="resolution"></a>解决方法  
 按照主题的"设置 IIS 应用程序主机进程标识"部分中的步骤[解决 IIS 权限问题的指导原则](../core/guidelines-for-resolving-iis-permissions-problems.md)设置适当的主机进程标识。  
  
## <a name="see-also"></a>另请参阅  
 [以解决 IIS 权限问题的指导原则](../core/guidelines-for-resolving-iis-permissions-problems.md)