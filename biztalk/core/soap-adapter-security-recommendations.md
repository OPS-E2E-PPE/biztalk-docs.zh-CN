---
title: SOAP 适配器的安全建议 |Microsoft Docs
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
ms.openlocfilehash: 77b8636793d1001aad671b9bc1b8493daee71687
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244398"
---
# <a name="soap-adapter-security-recommendations"></a>SOAP 适配器的安全建议
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用 SOAP 适配器来发布 （接收） 和使用 （发送） Web 服务。 有关 SOAP 适配器的详细信息，请参阅[SOAP 适配器](../core/soap-adapter.md)。 有关 Web 服务的详细信息，请参阅[使用 Web 服务的](../core/using-web-services.md)。 建议您遵循这些准则以保护和部署你的环境中的 SOAP 适配器。  
  
- 有关针对发布 Web 服务的安全建议，请参阅[启用 Web 服务](../core/enabling-web-services.md)。  
  
- SOAP 适配器利用超文本传输协议 (HTTP) 来发送和接收消息与 BizTalk Server。 因此，必须遵循安全建议以确保 Internet 信息服务 (IIS)。 如果使用 IIS 7.0，请确保您遵循 IIS 7.0 建议以配置应用程序隔离。 有关详细信息，请参阅[创建应用程序池 (IIS 7)](http://go.microsoft.com/fwlink/?LinkId=196674)。  
  
- 当为 SOAP 接收位置创建应用程序池时，必须将其独立的主机运行 SOAP 接收适配器和 Internet 信息服务工作进程组 (IIS_ 是 Windows 组的成员的帐户下运行配置WPG 组）。 SOAP 接收适配器以使用此帐户，然后必须配置的主机实例。 如果你更改了 IIS_WPG 组帐户，则必须确保也更新为新帐户下运行的主机实例。  
  
- 当你使用安全套接字层 (SSL) 客户端证书与 SOAP 发送适配器，则必须手动配置这些证书。  
  
- 时使用的 Web 服务，你可以使用匿名、 基本、 摘要、 Windows 集成在一起或客户端证书进行身份验证。 当通过使用基本身份验证来使用 Web 服务，建议使用 SSL 来确保未经授权的人员无法从消息中读取用户凭据。  
  
- 在方案中可以使用企业单一登录 (SSO) 需要在后端系统中将前端用户的内容映射到凭据。 有关详细信息，请参阅[如何映射单个登录凭据](../core/how-to-map-single-sign-on-credentials.md)。  
  
- 当使用基本身份验证，或在消息级别未使用加密时，建议使用 SSL 来接收和发送消息，以确保未经授权的人员无法读取用户凭据。  
  
- 建议使用 Windows 集成身份验证来发送和接收消息。  
  
- 此外运行 SOAP 适配器的计算机具有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行时。 建议您不要将 SOAP 适配器放在外围网络中。 如果您执行操作，您必须从外围网络到数据域到 MessageBox 数据库的 SQL Server 流量打开端口并将公开[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]潜在攻击的运行时。 建议在处理域 （即，不是外围网络） 中配置 SOAP 适配器。 然后可以配置的最外层防火墙转发 SOAP 请求通过处理域中的防火墙。 此机制称为反向代理。 （Forefront Threat Management Gateway (TMG) 2010年服务器实施被称为 Web 发布。）  
  
## <a name="see-also"></a>请参阅  
 [用于接收和发送服务器端口](../core/ports-for-the-receive-and-send-servers.md)   
 [最低安全用户权限](../core/minimum-security-user-rights.md)