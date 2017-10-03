---
title: "BizTalk Server 中的适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapters
- adapters, about adapters
- adapters, list of BizTalk adapters
- adapters, features
ms.assetid: 8fd279fb-2c68-4de4-a586-5a8e42a685ff
caps.latest.revision: "48"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d65d7304547df50ac14128717526fa7d55880775
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="adapters-in-biztalk-server"></a>BizTalk Server 中的适配器
主要设计目标之一[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]是便于实现的业务文档贸易合作伙伴之间交换。 为了帮助满足这一目标，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]包括几个适配器，提供 BizTalk Server 和使用通常在贸易合作伙伴之间的连接识别数据协议文档格式。 本主题探讨适配器的含义以及使用适配器的原因。  
  
## <a name="what-is-an-adapter"></a>什么是适配器？  
 适配器是一种软件组件，让你可以使用符合常用标准（例如 SMTP、POP3、FTP 或 Microsoft 消息队列 (MSMQ)）的传送机制轻松地从 BizTalk Server 发出消息或将消息接收到 BizTalk Server 中。 作为 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]的发展，需使用快速通常启用与连接的适配器的应用程序和技术的增加。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]包括以下适配器，统称为"本机"或"集成"适配器： 文件、 FTP、 HTTP、 MQSeries、 MSMQ、 POP3、 SMTP、 SOAP、 Windows Sharepoint Services 和七个 WCF 适配器 （WCF WSHttp、 WCF BasicHttp、 WCF NetTcp、 WCF NetMsmq，WCF-NetNamedPipe、 WCF 自定义和 WCF CustomIsolated)。 安装本机适配器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 你还可以通过使用 BizTalk 适配器框架为特定解决方案创建自定义适配器。  
  
 每个本地适配器均关联有一个接收位置，用于在特定地址侦听来自特定传输的消息。 在接收位置收到消息后，消息将传递给适配器。 适配器将向消息（通常在消息的正文部分）附加数据流，添加有关接收数据的源终结点的所有元数据，然后将消息提交到 BizTalk 消息引擎。  
  
 默认情况下，在运行 BizTalk 配置向导时，该向导将安装本地适配器，并为每个适配器创建具有默认配置的适配器处理程序。  
  
 使用 BizTalk Server 管理控制台，可以修改适配器处理程序的默认配置，还可为适配器添加、删除和修改发送端口和接收位置。 有关这些过程的详细信息，请参阅“另请参见”部分中的相应主题。  
  
## <a name="why-use-an-adapter"></a>使用适配器的原因  
 使用适配器可极大地简化通过 BizTalk Server 传输消息的过程。 如果你的现有基础结构使用任意具有对应 BizTalk 适配器的传输，则通过 BizTalk Server 发送或接收消息的过程将非常简单，只需将相应的适配器配置为使用所对应的传输机制发送或接收消息即可。  
  
## <a name="summary-of-functionality-supported-by-biztalk-native-adapters"></a>BizTalk 本地适配器支持的功能摘要  
 下表列出了每种本地适配器的主要优点以及对下列功能的支持情况：  
  
-   **事务支持。** 能够在分布式事务处理协调器 (DTC) 事务的上下文中发送和接收文档。 若要确保按序送达消息并且不会复制或丢失文档，则必须使用此功能。  
  
-   **双向通信支持 （请求/响应或请求/响应）。** 能够发送文档并处理来自目标的响应消息，或能够接收文档并向源发送响应消息。  
  
-   **按顺序获得支持。** 能够以接收文档的同样顺序将收到的文档发布到 BizTalk MessageBox 数据库。  
  
-   **启用 SSO。** 能够在通过适配器发送或接收文档时使用 SSO 验证。  
  
-   **承载进程**适配器在其中执行的过程。 *BizTalk IP*在 BTSNTSvc.exe 进程内执行时*IIS OOP*外部 Internet 信息服务器 (IIS) 进程中的 BizTalk Server 过程运行。  
  
|适配器|主要好处|事务支持|双向通信支持|按序接收支持|SSO 已启用|宿主进程|  
|-------------|---------------------|-------------------------|------------------------------------|-------------------------------|-----------------|---------------------|  
|文件|便于使用。|是|“否”|“否”|是|BizTalk IP|  
|FTP|广泛应用于企业对企业通信。|是|“否”|是|是|BizTalk IP|  
|HTTP(s)|广泛应用于企业对企业通信。|是|请求/响应和要求/响应|是|是|IIS OOP|  
|SOAP|支持使用 Web Services。|是|请求/响应和要求/响应|是|是|IIS OOP|  
|MSMQ|确保在 BizTalk Server 和 Microsoft 消息队列之间一次性送达消息。|是|“否”|是|是|BizTalk IP|  
|MQ Series|确保在 BizTalk Server 和用于 Windows 平台的 IBM WebSphere MQ 之间一次性送达消息。|是|“否”|是|是|BizTalk IP|  
|Windows SharePoint Services|用于在 BizTalk Server 和 SharePoint 文档库之间交换 XML 和二进制消息。|是|“否”|“否”|是|BizTalk IP|  
|POP3|支持通过电子邮件接收文档。|是|“否”|“否”|是|BizTalk IP|  
|SMTP|支持通过电子邮件发送文档。|是|“否”|“否”|是|BizTalk IP|  
|自定义|支持你的系统。|是，但需要自定义代码。|是，但需要自定义代码。|是，但需要自定义代码。|是，但需要自定义代码。|BizTalk IP|  
|WCF-WSHttp|通过 HTTP 传输支持 WS-* 标准。|是，WsHTTP 支持事务（仅限 WS-Transactions）|请求/响应和要求/响应|是|是|IIS OOP|  
|WCF-BasicHttp|使用 HTTP 或 HTTPS 与基于 ASMX 的 Web Services 以及符合 WS-I 基本配置文件 1.1 的客户端和其他服务进行通信。|是|请求/响应和要求/响应|是|是|IIS OOP|  
|WCF-NetTcp|通过 TCP 传输支持 WS-* 标准。|是|请求/响应和要求/响应|是|是|BizTalk IP|  
|WCF-NetMsmq|通过将 Microsoft 消息队列 (MSMQ) 作为传输利用来支持队列。|是|“否”|是|是|BizTalk IP|  
|WCF-NetNamedPipe|为在同一台计算机上进行进程间通信提供快速传输（仅适用于 WCF 应用程序）。|是|请求/响应和要求/响应|是|是|BizTalk IP|  
|WCF-Custom|允许使用 WCF 扩展功能。|是。|是。|是，只要绑定支持。|是。|BizTalk IP|  
|WCF-CustomIsolated|允许通过 HTTP 传输使用 WCF 扩展功能。|是。|是。|否。|是。|IIS OOP|  
  
## <a name="line-of-business-adapters"></a>业务线适配器  
 下面是 Microsoft 提供的业务线 (LOB) 适配器的列表。  
  
|适配器|Description|支持的版本|  
|-------------|-----------------|------------------------|  
|PeopleSoft Enterprise|用于在 BizTalk Server 和 PeopleSoft 系统间交换组件接口 (CI) 消息。|[支持的业务线 (LOB) 和企业系统](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)|  
|JD Edwards OneWorld XE|用于在 BizTalk Server 和 JD Edwards OneWorld 系统间交换业务功能消息。|[支持的业务线 (LOB) 和企业系统](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)|  
|JD Edwards EnterpriseOne|用于在 BizTalk Server 和 JD Edwards EnterpriseOne 系统间交换业务功能消息。|[支持的业务线 (LOB) 和企业系统](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)|  
|TIBCO Rendezvous|用于在 BizTalk Server 和 TIBCO Rendezvous 间交换 XML 和二进制数据格式消息。|[支持的业务线 (LOB) 和企业系统](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)|  
|TIBCO Enterprise Message Service|用于在 BizTalk Server 和 TIBCO EMS 服务器间交换 XML 和二进制数据格式消息，可提供一个高度整合的可靠的应用程序基础结构。|[支持的业务线 (LOB) 和企业系统](http://social.technet.microsoft.com/wiki/contents/articles/17631.biztalk-server-supported-line-of-business-lob-and-enterprise-systems.aspx)|  
  
 您也可以使用随 [!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)] 一起安装的适配器连接到多个业务线系统。 有关详细信息[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]，请参阅[http://go.microsoft.com/fwlink/p/?LinkID=188849](http://go.microsoft.com/fwlink/p/?LinkID=188849)  
  
## <a name="see-also"></a>另请参阅  
 [保护适配器的最佳方案](../core/best-practices-for-securing-adapters.md)   
 [创建和删除适配器处理程序](../core/creating-and-deleting-adapter-handlers.md)   
 [实现企业单一登录](../core/implementing-enterprise-single-sign-on.md)