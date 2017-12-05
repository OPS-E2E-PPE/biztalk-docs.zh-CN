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
ms.openlocfilehash: eb91509ec3ad1c329190c848c25a60434f93499e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="guidelines-for-resolving-iis-permissions-problems"></a>以解决 IIS 权限问题的指导原则
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将 Microsoft Internet 信息服务 (IIS) 广泛应用于 Web Services 支持，并与 HTTP、SOAP 和 Windows SharePoint Services 适配器一起使用。  
  
 在解决 IIS 权限疑难问题之前，了解 IIS 如何实现应用程序隔离是很有帮助的。  
  
 使用 IIS 可创建作为不同宿主进程的 IIS 应用程序，它们在自己的内存空间中运行。 一旦你创建的 IIS 应用程序主机，然后必须定义两个集的权限，在 IIS 应用程序主机**进程标识**和 IIS 应用程序主机**用户访问权限**。 在解决 IIS 权限疑难问题时，您应对每组权限都进行检查。  
  
> [!NOTE]
>  **进程标识**和**用户访问权限**也称为**安全上下文**的 IIS 应用程序主机进程。  
  
 本主题介绍如何设置**进程标识**和**用户访问权限**为 IIS 应用程序主机进程，并为解决 IIS 权限问题提供一些通用准则。  
  
## <a name="setting-iis-application-host-process-identity"></a>设置 IIS 应用程序宿主进程标识  
 IIS 应用程序宿主进程的配置随宿主进程提供的不同功能级别而异。 例如，通常不同于 IIS 应用程序主机进程提供服务 ASP 页或 ASP.NET 应用程序配置 IIS 应用程序主机进程，仅提供静态 HTML 页。  
  
 IIS 应用程序宿主进程的配置也随该应用程序的宿主 IIS 的不同版本而异。 运行在 Windows Server 2008 (IIS 7.0) 上的应用程序的宿主进程标识由与该应用程序关联的应用程序池标识管理。  
  
### <a name="setting-iis-process-identity-for-iis-70-on-windows-server-2008-or-windows-vista"></a>在 Windows Server 2008 或 Windows Vista 中设置 IIS 7.0 的 IIS 进程标识  
  
1.  单击**启动**，然后**所有程序**，然后单击**Internet Information Services (IIS) 7 Manager**。  
  
2.  在 Internet 信息服务 (IIS) 管理器中，展开*\<计算机名称\>***（用户帐户）**单击**应用程序池**。  
  
3.  右键单击应用程序池，单击**查看应用程序**若要查看与应用程序池关联的应用程序。  
  
4.  右键单击应用程序池，单击**高级设置**以显示应用程序池高级设置对话框。  
  
5.  通过旁边单击省略号 （…） 按钮来修改应用程序池的标识**标识**下**进程模型**部分**高级设置**对话框框。  
  
## <a name="setting-user-access-rights-for-the-iis-server"></a>为 IIS 服务器设置用户访问权限  
 进程标识控制运行的 IIS 应用程序宿主进程可用的安全上下文，而用户访问权限控制实际访问所承载网页的帐户的安全上下文。 必须为两个安全上下文设置适当的权限，以避免权限错误。  
  
 IIS 7.0 支持以下用户验证方法：  
  
-   **匿名访问：**允许用户建立匿名连接。 IIS 服务器以指定的 Guest 帐户登录用户。  
  
-   **ASP.NET 模拟**允许应用程序在两个不同的上下文之一中运行： 作为通过 IIS 身份验证的用户或作为你设置的任意帐户。  
  
-   **基本身份验证：**纯文本，以未加密形式在网络上传输密码。  
  
-   **摘要式身份验证：**仅适用于 Active Directory 帐户，通过网络，而不是纯文本密码发送一个哈希值。 摘要验证可通过代理服务器和其他防火墙工作，可以在 Web 分布式创作和版本管理 (WebDAV) 目录中使用。 要使用摘要式身份验证，首先必须禁用匿名身份验证。  
  
-   **窗体身份验证**Accommodates 的高流量站点或公共服务器上的应用程序的身份验证。 表单身份验证可管理客户端注册和应用程序级别的身份验证，而非依赖操作系统提供的身份验证机制。  
  
-   **Windows 身份验证：**在您的 Windows 域进行身份验证的客户端连接的使用身份验证。  
  
#### <a name="to-set-user-access-rights-for-a-virtual-directory-in-iis-70"></a>设置 IIS 7.0 中虚拟目录的用户访问权限  
  
1.  在 Internet 信息服务 (IIS) 管理器中，展开*\<计算机名称\>*，**站点**，和**Default Web Site**中**连接**窗格。  
  
2.  单击此项可选择的虚拟目录，然后单击**功能视图**底部的工作区窗格中列出的虚拟目录的可配置功能。  
  
3.  双击**身份验证**工作区窗格中，若要列出的虚拟目录启用的身份验证方法中的新功能。  
  
4.  单击以选择你想要启用或禁用并单击的身份验证方法**禁用**或**启用**中**操作**的 IIS 管理器窗格。  
  
    > [!NOTE]
    >  如果**启用匿名访问**是启用，IIS 将设置用户访问权限以配置的匿名用户身份之前设置与任何其他用户访问权限启用身份验证方法。  
    >   
    >  若要配置的匿名用户标识，右键单击**匿名身份验证**方法，并单击**编辑**以显示**编辑匿名身份验证凭据**对话框。  
  
## <a name="general-guidelines-for-resolving-iis-permissions-problems"></a>解决 IIS 权限问题的一般准则  
 按照以下步骤来解决 IIS 权限疑难问题：  
  
1.  在 IIS 服务器计算机的应用程序日志中查找错误。  
  
2.  按照中的步骤[IIS 7.0： 配置为在 IIS 7.0 中的失败请求跟踪](http://go.microsoft.com/fwlink/?LinkId=130600)来解决 IIS 7.0 的计算机上的权限问题。  
  
3.  在 IIS 服务器的 IIS 日志文件中查找 HTTP 401 错误。  
  
     默认情况下，在运行 Windows Server 2008 或 Windows Vista 的计算机中，IIS 日志文件位于以下目录：  
  
     C:\inetpub\logs\LogFiles\W3SVC1\  
  
    -   如果 IIS 7.0 计算机包含 HTTP 401 错误，请按照 Microsoft 知识库文章 943891 中的步骤，IIS 日志文件，"HTTP 状态代码在 IIS 7.0 中"在可用[http://support.microsoft.com/kb/943891](http://support.microsoft.com/kb/943891)以确定子状态代码和故障排除，根据状态代码的权限问题。  
  
    -   检查值**cs-username**与 HTTP 401 错误关联的字段。 此字段包含访问 IIS 服务器的已通过验证的用户的名称。 在此字段中，匿名用户帐户由连字符 (-) 表示。 确保此帐户具有访问相应资源的权限。  
  
4.  验证 IIS 应用程序宿主进程使用的进程标识凭据已正确设置，并且该帐户具有适当的权限。 如果用于进程标识的帐户没有足够的权限，则更改帐户或授予该帐户适当的权限。  
  
5.  使用中所述的 RegMon 和 FileMon 实用工具[工具和实用程序用于故障排除](../core/tools-and-utilities-to-use-for-troubleshooting.md)来诊断文件或注册表中的访问权限问题。  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Server 权限的疑难解答](../core/troubleshooting-biztalk-server-permissions.md)   
 [IIS 7.0： 在 IIS 7.0 中配置身份验证](http://go.microsoft.com/fwlink/?LinkId=129909)