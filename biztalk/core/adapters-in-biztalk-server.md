---
title: BizTalk Server 中的适配器 |Microsoft Docs
description: 在 BizTalk Server，包括内置适配器、 enterprise 适配器和 BizTalk 适配器包中的所有可用适配器的完整列表
ms.custom: ''
ms.date: 06/22/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8fd279fb-2c68-4de4-a586-5a8e42a685ff
caps.latest.revision: 48
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c21203f0bcadee50142b7f3021fdfb5f1b6949f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361060"
---
# <a name="adapters-in-biztalk-server"></a>BizTalk Server 中的适配器
主要设计目标之一[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]是方便贸易合作伙伴之间业务文档交换。 为帮助实现此目标，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]包括几个适配器提供 BizTalk Server 与通常使用贸易合作伙伴之间的连接识别数据协议和文档格式。 本主题讨论了适配器和使用适配器的原因。  
  
## <a name="what-is-an-adapter"></a>什么是适配器？  
 适配器是使您能够轻松地发出消息或符合可识别的常用标准，如 SMTP、 POP3、 FTP 或 Microsoft 消息队列 (MSMQ) 的传送机制与消息接收到 BizTalk Server 的软件组件。 作为 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]的不断发展，需要为适配器能够快速地与的连接通常使用应用程序和技术已增加。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 包括以下适配器，简称为"本机"或"集成"适配器：文件、 FTP、 HTTP、 MQSeries、 MSMQ、 POP3、 SMTP、 SOAP、 Windows Sharepoint Services 和七个 WCF 适配器 （Wcf-wshttp、 Wcf-basichttp、 Wcf-nettcp、 Wcf-netmsmq、 Wcf-netnamedpipe、 WCF 自定义和 Wcf-customisolated）。 本地适配器随一起安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 此外可以使用 BizTalk 适配器框架为特定解决方案创建自定义适配器。  
  
 每个本地适配器都具有用于侦听来自特定传输在某个地址的消息的接收位置相关联。 接收位置接收此消息后，它被传递给适配器。 适配器将数据流附加到消息 （通常在消息的正文部分），请添加任何终结点的数据来自，然后将该消息提交到 BizTalk 消息引擎相关的元数据。  
  
 默认情况下时运行 BizTalk 配置向导，该向导会安装本地适配器并为每个默认配置创建适配器处理程序。  
  
 使用 BizTalk Server 管理控制台，可以修改适配器处理程序的默认配置，以及添加、 删除和修改发送端口和接收适配器的位置。 有关这些过程的详细信息，请参阅另请参阅中的相应主题。  
  
## <a name="why-use-an-adapter"></a>使用适配器的原因  
 使用适配器可以大大简化了消息的传输传入或传出 BizTalk Server。 如果现有的基础结构使用任何没有相应的 BizTalk 适配器的传输，然后将消息发送到或从 BizTalk Server 接收消息的过程只需配置相应的适配器以发送或接收具有相应的消息传输机制。  
  
## <a name="functionality-support-in-built-in-adapters"></a>内置适配器中的功能支持  
 下表列出了每种本地适配器和适配器是否提供了以下功能的主要优点：  
  
-   **事务支持**:能够发送和接收文档的分布式的事务处理协调器 (DTC) 事务上下文。 此功能是必需的按序送达消息，并保证，文档不会重复或丢失的。  
  
-   **双向通信支持 （请求/响应或要求/响应）** :能够将文档发送和处理来自目标的响应消息或接收文档并将响应消息发送到源。  
  
-   **按序接收支持**:能够将接收到的文档发布到 BizTalk MessageBox 数据库接收到文档的确切顺序。  
  
-   **启用了 SSO** :使用 SSO 身份验证时发送或接收适配器的文档功能。  
  
-   **承载进程**:适配器在其中执行过程。 *BizTalk IP* BTSNTSvc.exe 进程内执行时*IIS OOP* Internet 信息服务器 (IIS) 进程中的 BizTalk Server 进程外部运行。  
  
|适配器|主要优点|事务支持|双向通信支持|按序接收支持|SSO 已启用|承载进程|  
|---|---|---|---|---|---|---|  
|自定义|支持你的系统。|是的需要自定义代码。|是的需要自定义代码。|是的需要自定义代码。|是的需要自定义代码。|BizTalk IP|  
|文件|易于使用。|否|否|否|否|BizTalk IP|  
|FTP|广泛用于企业到企业通信。|否|否|否|是|BizTalk IP|  
|Http （s)|广泛用于企业到企业通信。|否|请求/响应和要求/响应|否|是|IIS OOP|  
|MSMQ|确保在 BizTalk Server 和 Microsoft 消息队列之间的消息的一次性送达。|是|否|是|否|BizTalk IP|  
|逻辑应用| 接收来自，并将发送到 Azure 逻辑应用。 适用于在本地和云环境中，使用此适配器访问许多 Azure 服务 | 是 | 取决于您的工作流设计 | 否 | 否 |收到：BizTalk IP<br/>发送：IIS OOP| 
|MQ 系列|确保在 BizTalk Server 和 IBM WebSphere MQ 之间为 Windows 平台的消息的一次性送达。|是|否|是|是|BizTalk IP|  
|Office 365 邮件 | 接收和发送到 Office 365 电子邮件 | | 否 | 不按顺序接收 | 否 | BizTalk IP| 
|Office 365 日历 | 接收和 Office 365 中创建事件 | | 否 | 不按顺序接收 | 否 | BizTalk IP| 
|Office 365 联系人 | 在 Office 365 中创建联系人 | | 否 | 不按顺序接收 | 否 | BizTalk IP| 
|POP3|支持接收通过电子邮件的文档。|否|否|否|否|BizTalk IP|  
|SMTP|支持发送电子邮件通过的文档。|否|否|否|否|BizTalk IP|  
|SOAP|支持 Web 服务的使用。|否|请求/响应和要求/响应|否|是|IIS OOP|  
|Windows SharePoint Services|支持 XML 和二进制消息，BizTalk Server 和 SharePoint 文档库之间交换。|否|否|否|否|BizTalk IP| 
|WCF-WSHttp|支持 WS-* 标准通过 HTTP 传输。|是的 (仅限 Ws-transactions) wshttp 支持事务|请求/响应和要求/响应|否|是|IIS OOP|  
|WCF-BasicHttp|与基于 ASMX 的 Web 服务和客户端以及符合 WS 其他服务进行通信的基本配置文件 1.1 使用 HTTP 或 HTTPS。|否|请求/响应和要求/响应|否|是|IIS OOP|  
|WCF-NetTcp|支持 WS-* 标准通过 TCP 传输。|是|请求/响应和要求/响应|否|是|BizTalk IP|  
|WCF-NetMsmq|通过利用 Microsoft 消息队列 (MSMQ) 作为传输协议队列的支持。|是|否|是|是|BizTalk IP|  
|WCF-NetNamedPipe|（仅适用于 WCF 应用程序） 在同一台计算机上的跨进程通信提供快速传输。|是|请求/响应和要求/响应|否|是|BizTalk IP|  
|WCF 自定义|启用 WCF 扩展功能的使用。|是|是|是的只要绑定支持它。|是|BizTalk IP|  
|WCF-CustomIsolated|允许通过 HTTP 传输使用 WCF 扩展功能。|是|是|否|是|IIS OOP|  
  
## <a name="enterprise-adapters"></a>Enterprise 适配器  
 下面是由 Microsoft 提供的业务线 (LOB) 适配器的列表。  
  
|适配器|Description|支持的版本|  
|---|---|---|  
|PeopleSoft Enterprise|用于 BizTalk Server 和 PeopleSoft 系统之间的组件接口 (CI) 消息交换。|[支持的业务线 (LOB) 和企业系统](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)|  
|JD Edwards OneWorld XE|用于 BizTalk Server 和 JD Edwards OneWorld 系统间的业务功能消息交换。|[支持的业务线 (LOB) 和企业系统](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)|  
|JD Edwards EnterpriseOne|用于 BizTalk Server 和 JD Edwards EnterpriseOne 系统间的业务功能消息交换。|[支持的业务线 (LOB) 和企业系统](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)|  
|TIBCO Rendezvous|用于交换 XML 和 BizTalk Server 和 TIBCO Rendezvous 之间的二进制数据格式消息。|[支持的业务线 (LOB) 和企业系统](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)|  
|TIBCO Enterprise Message Service|用于交换 XML 和 BizTalk Server 和 TIBCO EMS 服务器提供一个高度整合并且可靠的应用程序基础结构之间的二进制数据格式消息。|[支持的业务线 (LOB) 和企业系统](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)|  

## <a name="biztalk-adapter-pack"></a>BizTalk 适配器包  
 此外可以使用随提供的适配器[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]连接到各种业务线系统。 有关详细信息[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]，请参阅[BizTalk Adapter Pack](../adapters-and-accelerators/biztalk-adapter-pack.md)。
  
## <a name="see-also"></a>请参阅  
 [确保适配器安全的最佳实践](../core/best-practices-for-securing-adapters.md)   
 [创建和删除适配器处理程序](../core/creating-and-deleting-adapter-handlers.md)   
 [实现企业单一登录](../core/implementing-enterprise-single-sign-on.md)