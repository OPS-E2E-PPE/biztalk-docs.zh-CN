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
# <a name="guidelines-for-resolving-iis-permissions-problems"></a>解决 IIS 权限疑难问题的准则
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可以广泛使用的 Microsoft Internet 信息服务 (IIS) Web services 支持并与 HTTP、 SOAP 和 Windows SharePoint Services 适配器一起使用。  
  
 最好先了解 IIS 如何实现之前解决 IIS 权限疑难问题的应用程序隔离。  
  
 IIS 提供了用于创建作为不同宿主进程在其自己的内存空间中运行的 IIS 应用程序的功能。 一旦创建 IIS 应用程序主机，然后必须定义两个集的权限，IIS 应用程序主机**进程标识**和 IIS 应用程序主机**用户访问权限**。 解决 IIS 权限疑难问题时，应检查的每个这些权限集。  
  
> [!NOTE]
>  **进程标识**并**用户访问权限**也称为**安全上下文**的 IIS 应用程序宿主进程。  
  
 本主题介绍如何设置**进程标识**并**用户访问权限**IIS 应用程序主机进程，并提供用于解决 IIS 权限疑难问题的一些通用准则。  
  
## <a name="setting-iis-application-host-process-identity"></a>设置 IIS 应用程序主机进程标识  
 IIS 应用程序主机进程的配置的主机进程所提供的功能级别而异。 例如，通常与作为 ASP 页或 ASP.NET 应用程序 IIS 应用程序宿主进程不同配置 IIS 应用程序宿主进程，仅作为静态 HTML 页。  
  
 IIS 应用程序主机进程的配置根据托管应用程序的 IIS 版本各不相同。 Windows Server 2008 (IIS 7.0) 上运行的应用程序的主机进程标识所依据的应用程序与关联的应用程序池标识。  
  
### <a name="setting-iis-process-identity-for-iis-70-on-windows-server-2008-or-windows-vista"></a>设置 Windows Server 2008 上的 IIS 7.0 的 IIS 进程标识或 Windows Vista  
  
1.  单击**启动**，然后**所有程序**，然后单击**Internet Information Services (IIS) 7 Manager**。  
  
2.  在 Internet 信息服务 (IIS) 管理器中，展开*\<计算机名\>***(User account)** 单击**应用程序池**。  
  
3.  右键单击应用程序池，然后单击**查看应用程序**若要查看与应用程序池相关联的应用程序。  
  
4.  右键单击应用程序池，然后单击**高级设置**显示应用程序池高级设置对话框。  
  
5.  通过单击旁边的省略号 （...） 按钮来修改应用程序池标识**标识**下**进程模型**一部分**高级设置**对话框框。  
  
## <a name="setting-user-access-rights-for-the-iis-server"></a>设置用户访问权限是针对 IIS 服务器  
 进程标识控制到正在运行的 IIS 应用程序宿主进程可用的安全上下文，而用户访问权限控制实际访问所承载网页的帐户的安全上下文。 对于这两个安全上下文，以避免权限错误，必须正确设置权限。  
  
 IIS 7.0 支持以下用户身份验证方法：  
  
-   **匿名访问：** 允许用户建立匿名连接。 使用指定的来宾帐户对用户的 IIS 服务器日志。  
  
-   **ASP.NET 模拟**允许在两个不同的上下文之一中运行应用程序： 作为通过 IIS 身份验证的用户或作为你设置的任意帐户。  
  
-   **基本身份验证：** 以纯文本形式，以未加密形式在网络上传输密码。  
  
-   **摘要式身份验证：** 仅适用于 Active Directory 帐户，通过在网络中，而不是纯文本密码发送的哈希值。 摘要式身份验证可在代理服务器和其他防火墙，可在 Web 分布式创作和版本管理 (WebDAV) 目录。 使用摘要式身份验证需要先禁用匿名身份验证。  
  
-   **窗体身份验证**适用的高流量站点或公用服务器上的应用程序的身份验证。 窗体身份验证允许你管理客户端注册和身份验证在应用程序级别，而不是依赖于由操作系统提供的身份验证机制。  
  
-   **Windows 身份验证：** 使用 Windows 域身份验证客户端连接进行身份验证。  
  
#### <a name="to-set-user-access-rights-for-a-virtual-directory-in-iis-70"></a>若要在 IIS 7.0 中设置虚拟目录的用户访问权限  
  
1.  在 Internet 信息服务 (IIS) 管理器中，展开*\<计算机名\>*，**站点**，以及**Default Web Site**中**连接**窗格。  
  
2.  单击此项可选择的虚拟目录，然后单击**功能视图**底部的工作区窗格中列出的虚拟目录的可配置功能。  
  
3.  双击**身份验证**工作区窗格中列出的虚拟目录启用的身份验证方法中的新功能。  
  
4.  单击以选择你想要启用或禁用并单击的身份验证方法**禁用**或**启用**中**操作**IIS 管理器窗格。  
  
    > [!NOTE]
    >  如果**启用匿名访问**是启用，IIS 将设置用户访问权限为配置的匿名用户标识之前设置与任何其他用户访问权限启用身份验证方法。  
    >   
    >  若要配置匿名用户标识，右键单击**匿名身份验证**方法，并单击**编辑**以显示**编辑匿名身份验证凭据**对话框。  
  
## <a name="general-guidelines-for-resolving-iis-permissions-problems"></a>解决 IIS 权限问题的一般指导原则  
 请执行以下步骤解决 IIS 权限：  
  
1.  检查错误的 IIS 服务器计算机的应用程序日志。  
  
2.  按照中的步骤[IIS 7.0:配置为在 IIS 7.0 失败请求跟踪](http://go.microsoft.com/fwlink/?LinkId=130600)来解决 IIS 7.0 计算机上的权限问题。  
  
3.  检查 HTTP 401 错误 IIS 服务器的 IIS 日志文件。  
  
     默认情况下，IIS 上运行 Windows Server 2008 或 Windows Vista 的计算机的日志文件位于以下目录中：  
  
     C:\inetpub\logs\LogFiles\W3SVC1\  
  
    -   如果 IIS 7.0 计算机包含 HTTP 401 错误，请按照 Microsoft 知识库文章 943891 中的步骤，IIS 日志文件，"HTTP 状态代码在 IIS 7.0 中"网址[ http://support.microsoft.com/kb/943891 ](http://support.microsoft.com/kb/943891)来确定子状态代码和对基于状态代码的权限问题进行故障排除。  
  
    -   检查的值**cs 用户名**与 HTTP 401 错误关联的字段。 此字段包含访问 IIS 服务器的经过身份验证用户的名称。 在此字段中一个连字符 （-） 表示匿名用户帐户。 请确保此帐户具有相应的资源的权限。  
  
4.  验证正确设置 IIS 应用程序主机进程使用的进程标识凭据的帐户具有适当的权限。 如果用于进程标识的帐户没有足够的权限然后更改帐户或授予适当的权限的帐户。  
  
5.  使用 RegMon 和 FileMon 实用程序中所述[工具和实用程序用于故障排除](../core/tools-and-utilities-to-use-for-troubleshooting.md)诊断文件或注册表访问权限问题。  
  
## <a name="see-also"></a>请参阅  
 [故障排除的 BizTalk Server 权限](../core/troubleshooting-biztalk-server-permissions.md)   
 [IIS 7.0:在 IIS 7.0 中配置身份验证](http://go.microsoft.com/fwlink/?LinkId=129909)