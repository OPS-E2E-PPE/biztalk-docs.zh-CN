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
ms.openlocfilehash: b2a099338dc882da6f5271cd28535a63edeb7302
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65295698"
---
# <a name="troubleshooting-internet-information-services"></a>Internet 信息服务的故障排除
Microsoft Internet 信息服务 (IIS) 广泛使用 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]用于各种功能，包括 HTTP、 SOAP 和 Windows SharePoint Services 适配器。 本主题介绍使用 IIS 和这些问题的可能解决方法可能会遇到一些已知的问题。  
  
## <a name="known-issues"></a>已知问题  
 本主题中所列的错误可能不会显示，除非您配置了 Internet Explorer 以禁用友好 HTTP 错误消息。  
  
#### <a name="to-configure-internet-explorer-to-disable-friendly-http-error-messages"></a>若要配置 Internet Explorer 以禁用友好 HTTP 错误消息  
  
1.  上**工具**菜单上，单击**Internet 选项**。  
  
2.  上**高级**选项卡上，在**浏览**部分中，清除**显示友好 HTTP 错误消息**复选框，然后依次**确定**。  
  
3.  关闭 Internet Explorer。  
  
#### <a name="http-404---file-not-found-error-occurs-when-accessing-a-web-page-on-an-iis-server"></a>"HTTP 404-文件找不到"访问 IIS 服务器上的网页时出现错误  
  
##### <a name="problem"></a>问题  
 当您尝试访问 IIS 服务器上的 Web 页面时将显示如下错误：  
  
 找不到页面  
  
 \- 或 -  
  
 HTTP 404-文件未找到  
  
##### <a name="cause"></a>原因  
 此错误可能由于以下原因：  
  
-   已重命名所请求的文件。  
  
-   所请求的文件已被移动到另一个位置或删除。  
  
-   所请求的文件是因维护、 升级或其他未知的原因而暂时不可用。  
  
-   所请求的文件不存在。  
  
-   IIS 6.0:未启用适当 Web 服务扩展或 MIME 类型。  
  
-   虚拟目录映射到另一台服务器上的驱动器的根目录。  
  
##### <a name="resolution"></a>解决方法  
 按照 Microsoft 知识库文章 248033，"常见原因 IIS 服务器将返回"HTTP 404-文件未找到"错误"的解决方法部分中的步骤可在[ http://support.microsoft.com/kb/248033 ](http://support.microsoft.com/kb/248033)。  
  
#### <a name="cannot-find-server-or-dns-error-error-occurs-when-accessing-a-web-page-on-an-iis-server"></a>"找不到服务器或发生 DNS 错误错误"时发生访问 IIS 服务器上的网页  
  
##### <a name="problem"></a>问题  
 当您尝试访问 IIS 服务器上的 Web 页面时将显示如下错误：  
  
 不显示此页  
  
 \- 或 -  
  
 找不到服务器或 DNS 错误  
  
##### <a name="cause"></a>原因  
 此错误可能由于以下原因：  
  
-   Internet Explorer 连接设置不正确。  
  
-   未正确配置的、 非正常运行或不兼容的防火墙或代理软件已安装。  
  
-   某个 Hosts 文件中存在不正确的条目。  
  
-   您的网络适配器不正常或具有不兼容的网络适配器驱动程序安装。  
  
##### <a name="resolution"></a>解决方法  
 按照 Microsoft 知识库文章 326155 的解决方法部分中的步骤"尝试访问 Internet 资源管理器中的 Web 站点时的错误消息："页无法显示""网址[ http://support.microsoft.com/kb/326155 ](http://support.microsoft.com/kb/326155)。  
  
#### <a name="401---access-denied-error-occurs-when-accessing-a-web-page-on-an-iis-server"></a>访问 IIS 服务器上的网页时出现"401 – 访问被拒绝"错误  
  
##### <a name="problem"></a>问题  
 当您尝试访问 IIS 服务器上的 Web 页面时将显示如下错误：  
  
 401 – 访问被拒绝  
  
##### <a name="cause"></a>原因  
 IIS 定义几个不同的 401 错误以指示错误的更具体原因。 在浏览器中显示这些特定错误代码：  
  
- 401.1 – 登录失败。  
  
- 401.2 – 服务器配置导致登录失败。  
  
- 401.3-未授权操作 acl 资源上。  
  
- 401.4 – 筛选器授权失败。  
  
- 401.5-ISAPI/CGI 应用程序失败的授权。  
  
- 401.7 – 访问被拒绝的 Web 服务器上的 URL 授权策略。 此错误代码是特定于 IIS 6.0。  
  
  IIS 7.0 状态代码的完整列表，请参阅 Microsoft 知识库文章 943891，"IIS 7.0 中的 HTTP 状态代码"网址[ http://support.microsoft.com/kb/943891 ](http://support.microsoft.com/kb/943891)。  
  
##### <a name="resolution"></a>解决方法  
 按照中的步骤[解决 IIS 权限疑难问题的准则](../core/guidelines-for-resolving-iis-permissions-problems.md)解决 IIS 权限问题。  
  
#### <a name="500---internal-server-error-occurs-when-accessing-a-web-page-on-an-iis-server"></a>访问 IIS 服务器上的网页时出现"500-内部服务器错误"  
  
##### <a name="problem"></a>问题  
 当您尝试访问 IIS 服务器上的 Web 页面时将显示如下错误：  
  
 500-内部服务器错误  
  
##### <a name="cause"></a>原因  
 可以通过各种服务器端问题导致此错误消息。  
  
##### <a name="resolution"></a>解决方法  
 若要解决此问题，请执行以下操作：  
  
- 查看有关为何会出现此错误的信息的 IIS 服务器的应用程序日志。  
  
- 查看 IIS 日志文件或 HTTPERR 日志文件中的信息可能会有所帮助确定错误的原因。 默认情况下 IIS 日志文件运行的计算机上[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]操作系统都位于以下目录：  
  
   <em>%WinDir%\\</em>system32\LogFiles\W3SVC1\  
  
  > [!NOTE]
  >  *%Windir%* 是 IIS 服务器上的 Windows 目录的位置的占位符。  
  
   默认情况下，IIS 上运行 Windows Server 2008 或 Windows Vista 的计算机的日志文件位于以下目录中：  
  
   C:\inetpub\logs\LogFiles\W3SVC1\  
  
   默认情况下上，HTTPERR 日志文件[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]位于以下目录中：  
  
   <em>%WinDir%</em>system32LogFilesHTTPERR  
  
  > [!NOTE]
  >  上才有 HTTPERR 日志文件[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，或 Windows Vista 计算机。  
  
#### <a name="service-unavailable-error-occurs-when-accessing-a-web-page-on-an-iis-server"></a>访问 IIS 服务器上的网页时出现"服务不可用"错误  
  
##### <a name="problem"></a>问题  
 当您尝试访问 IIS 服务器上的 Web 页面时将显示如下错误：  
  
 服务不可用  
  
##### <a name="cause"></a>原因  
 此错误的最常见原因是网页上的应用程序池 （IIS 6.0 和 IIS 7.0） 已停止。 这通常会发生的应用程序池或 COM + 应用程序使用标识配置，但如果指定的用户名和或密码无效。  
  
##### <a name="resolution"></a>解决方法  
 按照本主题的"设置 IIS 应用程序主机进程标识"部分中的步骤[解决 IIS 权限疑难问题的准则](../core/guidelines-for-resolving-iis-permissions-problems.md)设置相应的主机进程标识。  
  
## <a name="see-also"></a>请参阅  
 [解决 IIS 权限疑难问题的准则](../core/guidelines-for-resolving-iis-permissions-problems.md)