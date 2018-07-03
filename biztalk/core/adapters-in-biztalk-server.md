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
ms.openlocfilehash: 0f19ecce5c7068f7218d9189a6dffd19e76d6211
ms.sourcegitcommit: e7609c319b64ec20bf215d17aa5ac4f9dcae52ec
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/26/2018
ms.locfileid: "36945536"
---
# <a name="adapters-in-biztalk-server"></a>BizTalk Server 中的适配器
主要设计目标之一[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]是方便贸易合作伙伴之间业务文档交换。 为帮助实现此目标，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]包括几个适配器提供 BizTalk Server 与通常使用贸易合作伙伴之间的连接识别数据协议和文档格式。 本主题探讨适配器的含义以及使用适配器的原因。  
  
## <a name="what-is-an-adapter"></a>什么是适配器？  
 适配器是一种软件组件，让你可以使用符合常用标准（例如 SMTP、POP3、FTP 或 Microsoft 消息队列 (MSMQ)）的传送机制轻松地从 BizTalk Server 发出消息或将消息接收到 BizTalk Server 中。 作为 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]的不断发展，需要为适配器能够快速地与的连接通常使用应用程序和技术已增加。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 包括以下适配器，简称为"本机"或"集成"适配器： 文件、 FTP、 HTTP、 MQSeries、 MSMQ、 POP3、 SMTP、 SOAP、 Windows Sharepoint Services 和七个 WCF 适配器 （Wcf-wshttp、 Wcf-basichttp、 Wcf-nettcp、 Wcf-netmsmq，WCF-NetNamedPipe、 Wcf-custom 和 Wcf-customisolated)。 本地适配器随一起安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 你还可以通过使用 BizTalk 适配器框架为特定解决方案创建自定义适配器。  
  
 每个本地适配器均关联有一个接收位置，用于在特定地址侦听来自特定传输的消息。 在接收位置收到消息后，消息将传递给适配器。 适配器将向消息（通常在消息的正文部分）附加数据流，添加有关接收数据的源终结点的所有元数据，然后将消息提交到 BizTalk 消息引擎。  
  
 默认情况下，在运行 BizTalk 配置向导时，该向导将安装本地适配器，并为每个适配器创建具有默认配置的适配器处理程序。  
  
 使用 BizTalk Server 管理控制台，可以修改适配器处理程序的默认配置，还可为适配器添加、删除和修改发送端口和接收位置。 有关这些过程的详细信息，请参阅“另请参见”部分中的相应主题。  
  
## <a name="why-use-an-adapter"></a>使用适配器的原因  
 使用适配器可极大地简化通过 BizTalk Server 传输消息的过程。 如果你的现有基础结构使用任意具有对应 BizTalk 适配器的传输，则通过 BizTalk Server 发送或接收消息的过程将非常简单，只需将相应的适配器配置为使用所对应的传输机制发送或接收消息即可。  
  
## <a name="functionality-support-in-built-in-adapters"></a>内置适配器中的功能支持  
 下表列出了每种本地适配器的主要优点以及对下列功能的支持情况：  
  
-   **事务支持**： 发送和接收文档的分布式的事务处理协调器 (DTC) 事务上下文的能力。 若要确保按序送达消息并且不会复制或丢失文档，则必须使用此功能。  
  
-   **双向通信支持 （请求/响应或要求/响应）** ： 能够将文档发送和处理来自目标的响应消息或接收文档并将响应消息发送到源。  
  
-   **按序接收支持**： 将接收到的文档发布到 BizTalk MessageBox 数据库接收到文档的确切顺序的功能。  
  
-   **启用了 SSO** ： 使用 SSO 身份验证时发送或接收适配器的文档的能力。  
  
-   **承载进程**： 适配器将在其中执行的过程。 *BizTalk IP* BTSNTSvc.exe 进程内执行时*IIS OOP* Internet 信息服务器 (IIS) 进程中的 BizTalk Server 进程外部运行。  
  
|适配器|主要优点|事务支持|双向通信支持|按序接收支持|SSO 已启用|宿主进程|  
|---|---|---|---|---|---|---|  
|自定义|支持你的系统。|是，但需要自定义代码。|是，但需要自定义代码。|是，但需要自定义代码。|是，但需要自定义代码。|BizTalk IP|  
|文件|便于使用。|“否”|否|否|“否”|BizTalk IP|  
|FTP|广泛应用于企业对企业通信。|“否”|否|否|是|BizTalk IP|  
|HTTP(s)|广泛应用于企业对企业通信。|“否”|请求/响应和要求/响应|“否”|是|IIS OOP|  
|MSMQ|确保在 BizTalk Server 和 Microsoft 消息队列之间一次性送达消息。|是|否|是|“否”|BizTalk IP|  
|逻辑应用| 接收来自，并将发送到 Azure 逻辑应用。 适用于在本地和云环境中，使用此适配器访问许多 Azure 服务 | 是 | 取决于您的工作流设计 | “否” | “否” |收到： BizTalk IP<br/>发送： IIS OOP| 
|MQ Series|确保在 BizTalk Server 和用于 Windows 平台的 IBM WebSphere MQ 之间一次性送达消息。|是|否|是|是|BizTalk IP|  
|Office 365 邮件 | 接收和发送到 Office 365 电子邮件 | | “否” | 不按顺序接收 | “否” | BizTalk IP| 
|Office 365 日历 | 接收和 Office 365 中创建事件 | | “否” | 不按顺序接收 | “否” | BizTalk IP| 
|Office 365 联系人 | 在 Office 365 中创建联系人 | | “否” | 不按顺序接收 | “否” | BizTalk IP| 
|POP3|支持通过电子邮件接收文档。|“否”|否|否|“否”|BizTalk IP|  
|SMTP|支持通过电子邮件发送文档。|“否”|否|否|“否”|BizTalk IP|  
|SOAP|支持使用 Web Services。|“否”|请求/响应和要求/响应|“否”|是|IIS OOP|  
|Windows SharePoint Services|用于在 BizTalk Server 和 SharePoint 文档库之间交换 XML 和二进制消息。|“否”|否|否|“否”|BizTalk IP| 
|WCF-WSHttp|通过 HTTP 传输支持 WS-* 标准。|是，WsHTTP 支持事务（仅限 WS-Transactions）|请求/响应和要求/响应|“否”|是|IIS OOP|  
|WCF-BasicHttp|使用 HTTP 或 HTTPS 与基于 ASMX 的 Web Services 以及符合 WS-I 基本配置文件 1.1 的客户端和其他服务进行通信。|“否”|请求/响应和要求/响应|“否”|是|IIS OOP|  
|WCF-NetTcp|通过 TCP 传输支持 WS-* 标准。|是|请求/响应和要求/响应|“否”|是|BizTalk IP|  
|WCF-NetMsmq|通过将 Microsoft 消息队列 (MSMQ) 作为传输利用来支持队列。|是|否|是|是|BizTalk IP|  
|WCF-NetNamedPipe|为在同一台计算机上进行进程间通信提供快速传输（仅适用于 WCF 应用程序）。|是|请求/响应和要求/响应|“否”|是|BizTalk IP|  
|WCF-Custom|允许使用 WCF 扩展功能。|是|是|是，只要绑定支持。|是|BizTalk IP|  
|WCF-CustomIsolated|允许通过 HTTP 传输使用 WCF 扩展功能。|是|是|否|是|IIS OOP|  
  
## <a name="enterprise-adapters"></a>Enterprise 适配器  
 下面是 Microsoft 提供的业务线 (LOB) 适配器的列表。  
  
|适配器|Description|支持的版本|  
|---|---|---|  
|PeopleSoft Enterprise|用于在 BizTalk Server 和 PeopleSoft 系统间交换组件接口 (CI) 消息。|[支持的业务线 (LOB) 和企业系统](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)|  
|JD Edwards OneWorld XE|用于在 BizTalk Server 和 JD Edwards OneWorld 系统间交换业务功能消息。|[支持的业务线 (LOB) 和企业系统](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)|  
|JD Edwards EnterpriseOne|用于在 BizTalk Server 和 JD Edwards EnterpriseOne 系统间交换业务功能消息。|[支持的业务线 (LOB) 和企业系统](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)|  
|TIBCO Rendezvous|用于在 BizTalk Server 和 TIBCO Rendezvous 间交换 XML 和二进制数据格式消息。|[支持的业务线 (LOB) 和企业系统](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)|  
|TIBCO Enterprise Message Service|用于在 BizTalk Server 和 TIBCO EMS 服务器间交换 XML 和二进制数据格式消息，可提供一个高度整合的可靠的应用程序基础结构。|[支持的业务线 (LOB) 和企业系统](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)|  

## <a name="biztalk-adapter-pack"></a>BizTalk 适配器包  
 您也可以使用随 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] 一起安装的适配器连接到多个业务线系统。 有关详细信息[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]，请参阅[BizTalk Adapter Pack](../adapters-and-accelerators/biztalk-adapter-pack.md)。
  
## <a name="see-also"></a>请参阅  
 [确保适配器安全的最佳实践](../core/best-practices-for-securing-adapters.md)   
 [创建和删除适配器处理程序](../core/creating-and-deleting-adapter-handlers.md)   
 [实现企业单一登录](../core/implementing-enterprise-single-sign-on.md)