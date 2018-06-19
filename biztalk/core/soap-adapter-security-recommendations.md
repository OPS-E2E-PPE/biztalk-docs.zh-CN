---
title: SOAP 适配器安全建议 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP adapters, security
- security, SOAP adapters
ms.assetid: f869bd82-df93-45e1-b747-b538820253fb
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3053bccde7830d2e8275c8e2f6f668c428709860
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279589"
---
# <a name="soap-adapter-security-recommendations"></a>SOAP 适配器安全建议
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用 SOAP 适配器来发布（接收）和使用（发送）Web Services。 有关 SOAP 适配器的详细信息，请参阅[SOAP 适配器](../core/soap-adapter.md)。 有关 Web 服务的详细信息，请参阅[使用 Web 服务](../core/using-web-services.md)。 建议你遵循这些准则以确保你的环境中的 SOAP 适配器的安全并对其进行部署。  
  
-   有关用于发布 Web 服务的安全建议，请参阅[启用 Web 服务](../core/enabling-web-services.md)。  
  
-   SOAP 适配器利用超文本传输协议 (HTTP) 来向 BizTalk Server 发送消息或从其接收消息。 因此，你必须遵循安全建议以确保 Internet 信息服务 (IIS) 的安全。 如果使用 IIS 7.0，请确保你遵循 IIS 7.0 建议以配置应用程序隔离。 有关详细信息，请参阅[创建应用程序池 (IIS 7)](http://go.microsoft.com/fwlink/?LinkId=196674)。  
  
-   在为 SOAP 接收位置创建应用程序池时，你必须将其配置为使用满足以下条件的帐户运行：该帐户是运行 SOAP 接收适配器的独立主机的 Windows 组以及 Internet 信息服务工作进程组（IIS_WPG 组）的成员。 随后，必须将 SOAP 接收适配器的主机实例配置为使用此帐户。 如果你更改 IIS_WPG 组的帐户，则必须确保也更新要在新的帐户下运行的主机实例。  
  
-   如果将安全套接字层 (SSL) 客户端证书与 SOAP 发送适配器一起使用，则必须手动配置这些证书。  
  
-   在使用 Web Services 时，可以通过匿名、基本、摘要、Windows 集成或客户端证书方式来进行验证。 如果通过基本验证来使用 Web Services，建议你使用 SSL 来确保未经授权的人员无法从消息中读取用户凭据。  
  
-   如果需要将前端用户的内容映射到后端系统中的凭据，则可以使用企业单一登录 (SSO)。 有关详细信息，请参阅[如何映射单一登录凭据](../core/how-to-map-single-sign-on-credentials.md)。  
  
-   如果使用基本验证或在消息级别未使用加密，则建议你使用 SSL 来接收和发送消息，以确保未经授权的人员无法读取用户凭据。  
  
-   建议使用 Windows 集成身份验证来发送消息和接收消息。  
  
-   运行 SOAP 适配器的计算机还具有 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 运行时。 建议不要将 SOAP 适配器放置在外围网络中。 如果将其置于外围网络中，则必须打开从外围网络到数据域的端口才能使 SQL Server 与 MessageBox 数据库进行通信，这样 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 运行时可能会受到攻击。 建议你在处理域（而不是外围网络）中配置 SOAP 适配器。 然后，可以将最外层防火墙配置为通过处理域中的防火墙转发 SOAP 请求。 此机制称为反向代理。 （Forefront Threat Management Gateway (TMG) 2010 服务器实施被称为 Web 发布。）  
  
## <a name="see-also"></a>另请参阅  
 [用于接收和发送服务器端口](../core/ports-for-the-receive-and-send-servers.md)   
 [最低安全用户权限](../core/minimum-security-user-rights.md)