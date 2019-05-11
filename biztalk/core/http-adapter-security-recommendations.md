---
title: HTTP 适配器的安全建议 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, HTTP adapters
- configuring [HTTP adapters], security
- HTTP adapters, security
ms.assetid: ef6043c2-c62a-40e5-b2e1-53e60f87a761
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89b0a18ae91a9fd8c37baf2aa04f7a16c09c4409
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332613"
---
# <a name="http-adapter-security-recommendations"></a>HTTP 适配器的安全建议
使用 HTTP 适配器之间交换信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和应用程序通过超文本传输协议 (HTTP)。 应用程序可以通过将 HTTP POST 或 HTTP GET 请求发送到指定的 HTTP URL 向服务器发送消息。 有关 HTTP 适配器的详细信息，请参阅[HTTP 适配器](../core/http-adapter.md)。 建议用于保护和部署你的环境中的 HTTP 适配器的以下准则：  
  
- 请确保配置 HTTP 适配器的 Internet 信息服务 (IIS) 设置。 有关详细信息，请参阅[如何配置 IIS 以实现 HTTP 接收位置](../core/how-to-configure-iis-for-an-http-receive-location.md)。  
  
- 如果使用 7.0，请确保您遵循 IIS 7.0 建议以配置应用程序隔离。  
  
- 当您使用基本身份验证，或在消息级别未使用加密时，建议使用安全套接字层 (SSL) 来接收和发送消息，以确保未经授权的人员无法探查用户凭据。  
  
- 建议使用 Windows 集成身份验证来发送和接收消息。  
  
- 建议，则执行不重命名、 复制或移动 ISAPI 扩展文件。 这可确保安全更新安装程序能够正确地应用任何潜在的安全更新与此文件有关。  
  
- 您应使用加强的任意访问控制列表 (Dacl) 包含 ISAPI 扩展文件的目录和虚拟目录创建用于接收消息。 运行 HTTP 适配器的主机的 BizTalk Isolated Host 组的成员需要读取和执行权限，而 HTTP 适配器进行身份验证的用户需要拥有读取这些目录的权限。  
  
- 当你使用 SSL 客户端证书与 HTTP 发送适配器，则必须手动配置这些证书。  
  
- 就像其他[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组件，则建议您不要将 HTTP 适配器放在外围网络中。 如果这样做，您必须打开从外围网络到 SQL Server 流量发送到 MessageBox 数据库，这容易引起风险数据域的端口。 建议在处理域 （即，不是外围网络） 中配置 HTTP 适配器。 然后可以配置最外层防火墙 (FW4) 转发 HTTP 请求通过处理域 (FW3) 中的防火墙。 在这种情况下，不需要 IIS 的外围网络中。 此机制称为反向代理。 （Forefront Threat Management Gateway (TMG) 2010年服务器实施被称为 Web 发布。）  
  
- 当 HTTP 接收位置创建应用程序池时，您必须将其配置为是独立主机运行 HTTP 接收适配器和 Internet 信息服务工作进程组 (IIS_ Windows 组的成员的帐户下运行WPG 组）。 然后，您必须使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中的主机实例配置 http 接收适配器以使用此帐户。 如果你更改了 IIS_WPG 组帐户，则必须确保也更新为新帐户下运行的主机实例。 有关详细信息，请参阅[如何配置 IIS 以实现 HTTP 接收位置](../core/how-to-configure-iis-for-an-http-receive-location.md)。  
  
## <a name="see-also"></a>请参阅  
 [用于接收和发送服务器端口](../core/ports-for-the-receive-and-send-servers.md)   
 [最低安全用户权限](../core/minimum-security-user-rights.md)