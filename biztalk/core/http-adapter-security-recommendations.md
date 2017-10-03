---
title: "HTTP 适配器安全建议 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, HTTP adapters
- configuring [HTTP adapters], security
- HTTP adapters, security
ms.assetid: ef6043c2-c62a-40e5-b2e1-53e60f87a761
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1bb4e5909a61040a2bcd2dd84a81f81077d25a3b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="http-adapter-security-recommendations"></a>HTTP 适配器安全建议
使用 HTTP 适配器可以通过超文本传输协议 (HTTP) 在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 与应用程序之间交换信息。 通过向指定的 HTTP URL 发送 HTTP POST 或 HTTP GET 请求，应用程序可以向服务器发送消息。 有关 HTTP 适配器的详细信息，请参阅[HTTP 适配器](../core/http-adapter.md)。 建议你使用以下准则以确保你的环境中的 HTTP 适配器的安全并对其进行部署：  
  
-   确保为 HTTP 适配器配置了 Internet 信息服务 (IIS) 设置。 有关详细信息，请参阅[如何将 IIS 配置的 HTTP 接收位置](../core/how-to-configure-iis-for-an-http-receive-location.md)。  
  
-   如果使用 7.0，请确保你遵循 IIS 7.0 建议以配置应用程序隔离。  
  
-   如果使用基本验证或在消息级别未使用加密，则建议你使用安全套接字层 (SSL) 来接收和发送消息，以确保未经授权的人员无法探查用户凭据。  
  
-   建议使用 Windows 集成身份验证来发送消息和接收消息。  
  
-   建议不要对 ISAPI 扩展文件进行重命名、复制或移动。 这样可确保安全更新安装程序能够正确地应用任何与此文件有关的可能的安全更新。  
  
-   应对包含 ISAPI 扩展文件的目录以及为接收消息创建的虚拟目录使用加强的任意访问控制列表 (DACL)。 运行 HTTP 适配器的主机的 BizTalk Isolated Host Users 组成员需要对这些目录具有读取和执行权限，而 HTTP 适配器对其进行验证的用户需要对这些目录具有读取权限。  
  
-   如果将 SSL 客户端证书与 HTTP 发送适配器一起使用，则必须手动配置这些证书。  
  
-   与其他 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 组件一样，建议你不要将 HTTP 适配器置于外围网络中。 如果将其置于外围网络中，则必须打开从外围网络到数据域的端口才能使 SQL Server 与 MessageBox 数据库进行通信，这样容易引起风险。 建议在处理域（而不是外围网络）中配置 HTTP 适配器。 然后，可以将最外层防火墙 (FW4) 配置为通过处理域中的防火墙 (FW3) 转发 HTTP 请求。 在这种情况下，外围网络中不需要 IIS。 此机制称为反向代理。 （Forefront Threat Management Gateway (TMG) 2010 服务器实施被称为 Web 发布。）  
  
-   在为 HTTP 接收位置创建应用程序池时，你必须将其配置为使用满足以下条件的帐户运行：该帐户是运行 HTTP 接收适配器的独立主机的 Windows 组以及 Internet 信息服务工作进程组（IIS_WPG 组）的成员。 随后，必须使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台将 HTTP 接收适配器的主机实例配置为使用此帐户。 如果你更改 IIS_WPG 组的帐户，则必须确保也更新要在新的帐户下运行的主机实例。 有关详细信息，请参阅[如何将 IIS 配置的 HTTP 接收位置](../core/how-to-configure-iis-for-an-http-receive-location.md)。  
  
## <a name="see-also"></a>另请参阅  
 [用于接收和发送服务器端口](../core/ports-for-the-receive-and-send-servers.md)   
 [最低安全用户权限](../core/minimum-security-user-rights.md)