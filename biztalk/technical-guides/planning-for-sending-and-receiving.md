---
title: 规划发送和接收 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d67e5f7-5127-4c1d-be20-8d8dbb538286
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a96c75ceadfeaf06dde2c3661dd00f435529dcc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009518"
---
# <a name="planning-for-sending-and-receiving"></a>规划发送和接收
处理的几乎每个文档[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]收到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收适配器，并从发送[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]发送适配器。 因为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]适配器因此突出图中任何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境中，务必要提前计划来确定哪些适配器或加速器你将使用以及如何正确配置这些适配器和/或加速器。  
  
## <a name="determining-which-adapters-and-accelerators-you-will-use"></a>确定哪些适配器和加速器将使用  
 请咨询您的贸易合作伙伴提前用于确定哪些适配器和加速器需要以便发送和接收文档之间以及 BizTalk 应用程序和内部之间组织和贸易合作伙伴，业务应用程序。 设计你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将来体系结构足够灵活，以便添加其他适配器或加速器的事件中建立关系与其他贸易合作伙伴。  
  
## <a name="functionality-supported-by-biztalk-adapters"></a>BizTalk 适配器支持的功能  
 在本部分中的表列出了每种本地适配器和适配器是否提供了以下功能的主要优点：  
  
-   **事务支持**能够发送和接收文档的分布式的事务处理协调器 (DTC) 事务上下文。 若要确保按序送达消息并且不会复制或丢失文档，则必须使用此功能。  
  
    > [!NOTE]  
    >  如果遇到对 MSDTC 问题，请查看本主题[MSDTC 疑难解答](http://go.microsoft.com/fwlink/?LinkID=154693)(http://go.microsoft.com/fwlink/?LinkID=154693)。  
  
-   **双向通信支持 （请求/响应或要求/响应）** 能够将文档发送和处理来自目标的响应消息或接收文档并将响应消息发送到源。  
  
-   **按序接收支持。** 能够将接收到的文档发布到 MessageBox 数据库接收到文档的确切顺序。  
  
    > [!NOTE]  
    >  某些适配器可以强制执行在接收位置级别的有序的文档传递，而其他适配器不能。 仍在发送端口级别的顺序在接收位置级别的文档传递这些适配器不支持强制执行按序的送达，但这样做可能会对性能产生负面影响。 有关按序送达消息的详细信息，请参阅主题[的消息按序送达](http://go.microsoft.com/fwlink/?LinkId=155751)(http://go.microsoft.com/fwlink/?LinkId=155751)。  
  
-   **SSO 已启用。** 能够在通过适配器发送或接收文档时使用 SSO 验证。  
  
|适配器|主要优点|事务支持|双向通信支持|按序接收支持|SSO 已启用|  
|-------------|---------------------|-------------------------|------------------------------------|-------------------------------|-----------------|  
|文件|易于使用|“否”|否|否|“否”|  
|FTP|广泛用于企业到企业通信|“否”|否|否|是|  
|HTTP(s)|广泛用于企业到企业通信|“否”|请求/响应和要求/响应|“否”|是|  
|SOAP|支持使用 Web 服务|“否”|请求/响应和要求/响应|“否”|是|  
|MSMQ|确保在 BizTalk Server 和 Microsoft 消息队列之间的消息的一次性送达|是|否|是|“否”|  
|MQ Series|确保在仅限一次的 BizTalk Server 和 IBM WebSphere MQ 之间为 Windows 平台的消息送达|是|否|是|是|  
|SQL|支持直接 BizTalk Server 和 SQL Server 数据库之间的通信|是|仅要求/响应|“否”|“否”|  
|Windows SharePoint Services|支持 XML 和二进制消息，BizTalk Server 和 SharePoint 文档库之间交换|“否”|否|否|“否”|  
|POP3|支持接收通过电子邮件的文档|“否”|否|否|“否”|  
|SMTP|支持发送电子邮件通过文档|“否”|否|否|“否”|  
|EDI|支持处理符合 EDI 标准的业务文档|“否”|否|否|“否”|  
|自定义|支持您的旧系统|是，但需要自定义代码。|是，但需要自定义代码。|是，但需要自定义代码。|是，但需要自定义代码。|  
|WCF-WSHttp|支持 WS-* 标准通过 HTTP 传输|是，WsHTTP 支持事务（仅限 WS-Transactions）|请求/响应和要求/响应|“否”|是|  
|WCF-BasicHttp|与基于 ASMX 的 Web 服务和客户端以及符合 WS 其他服务进行通信的基本配置文件 1.1 使用 HTTP 或 HTTPS|“否”|请求/响应和要求/响应|“否”|是|  
|WCF-NetTcp|支持 WS-* 标准通过 TCP 传输|是|请求/响应和要求/响应|“否”|是|  
|WCF-NetMsmq|通过利用 Microsoft 消息队列 (MSMQ) 作为传输协议队列的支持|是|否|是|是|  
|WCF-NetNamedPipe|（仅适用于 WCF 应用程序） 在同一计算机上的跨进程通信提供快速传输|是|请求/响应和要求/响应|“否”|是|  
|WCF-Custom|可以使用 WCF 扩展功能|是。|是。|是，只要绑定支持。|是。|  
|WCF-CustomIsolated|允许通过 HTTP 传输使用 WCF 扩展功能|是。|是。|否。|是。|  
  
## <a name="line-of-business-adapters"></a>业务线适配器  
 下面是 Microsoft 提供的业务线 (LOB) 适配器的列表。  
  
> [!NOTE]  
>  除了 Microsoft BizTalk Adapter v2.0 for mySAP™ Business Suite （适配器），任何业务线适配器支持在 Windows Vista 上。  
  
|适配器|Description|支持的版本|  
|-------------|-----------------|------------------------|  
|SAP （也称为"适配器"）|用于交换中间文档 (IDOC)、 BAPI 和 BizTalk Server 和 SAP R/3® 系统之间的远程函数调用 (RFC) 消息。|SAP R/3 4.x 和 R/3 6.20 (Enterprise)|  
|PeopleSoft Enterprise|用于在 BizTalk Server 和 PeopleSoft 系统间交换组件接口 (CI) 消息。|PeopleTools 版本 8.17.02、8.43、8.45、8.46 和 8.48|  
|JD Edwards OneWorld XE|用于在 BizTalk Server 和 JD Edwards OneWorld 系统间交换业务功能消息。|B7.3.3.3 SP23 和 JDE 8.0 (B7.3.3.4)|  
|JD Edwards EnterpriseOne|用于在 BizTalk Server 和 JD Edwards EnterpriseOne 系统间交换业务功能消息。|8.10 & 8.11 工具发布 8.93、 8.94、 8.95 和 8.96|  
|ODBC Adapter for Oracle Database|用于从 Oracle Server 数据库读取信息和将信息写入该数据库。|Oracle 8i (8.1.6.0) 9i (9.2.0.1) 或 10 g|  
|Siebel eBusiness Applications|用于在 BizTalk Server 和 Siebel eBusiness Application 间交换业务组件和业务服务消息。|7.0、 7.5。 *、 7.7。\*，和 7.8。\*|  
|TIBCO Rendezvous|用于在 BizTalk Server 和 TIBCO Rendezvous 间交换 XML 和二进制数据格式消息。|7.3|  
|TIBCO Enterprise Message Service|用于在 BizTalk Server 和 TIBCO EMS 服务器间交换 XML 和二进制数据格式消息，可提供一个高度整合的可靠的应用程序基础结构。|4.2|  
|WebSphere MQ|用于在 BizTalk Server 和 IBM WebSphere MQ 间交换消息。|5.3 带有 Fix Pack 10 或更高版本和 6.0 修复包 1.1 或更高版本|  
  
 有关与 BizTalk Server 提供的 LOB 适配器的详细信息，请参阅[适配器使用 BizTalk Server 2010 中包含](http://go.microsoft.com/fwlink/?LinkId=152664)(http://go.microsoft.com/fwlink/?LinkId=152664)。  
  
## <a name="biztalk-adapter-pack"></a>BizTalk 适配器包  
 Microsoft[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]包含基于 WCF 的适配器，以提供与 LOB 应用程序，如 Oracle Database、 Oracle E-business Suite、 SAP、 Siebel 和 SQL Server 的连接。 有关使用可用的适配器列表[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]，请参阅[BizTalk Adapter Pack](http://go.microsoft.com/fwlink/?LinkId=152665) (<http://go.microsoft.com/fwlink/?LinkId=152665>)。  
  
> [!IMPORTANT]
>  可以使用[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]迁移工具迁移到 BizTalk 项目类型提供的基于 WCF LOB 适配器附带的 LOB 适配器的 BizTalk 项目[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。 您可以下载[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]中的迁移工具[BizTalk 适配器包迁移工具](http://go.microsoft.com/fwlink/?LinkID=153328)(<http://go.microsoft.com/fwlink/?LinkID=153328>)。 若要了解有关迁移到基于 WCF LOB 适配器附带的 LOB 适配器的详细信息[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]，请参阅[Microsoft BizTalk 适配器 2.0 迁移白皮书](http://go.microsoft.com/fwlink/?LinkId=158848)(<http://go.microsoft.com/fwlink/?LinkId=158848>)。  
  
## <a name="biztalk-accelerators"></a>BizTalk 加速器  
 尽管 BizTalk 适配器适合使用特定协议的发送和接收文档，BizTalk 加速器设计为可以容纳根据特定行业标准的文档的交换。 有关可用的 BizTalk 快捷键的列表，请参阅[Microsoft BizTalk Server 加速器](http://go.microsoft.com/fwlink/?LinkId=103609)(http://go.microsoft.com/fwlink/?LinkId=103609)。  
  
##  <a name="BKMK_InternetTrans"></a> 公开到 Internet 的传输时配置你的域  
 为了简化的发送和接收您的组织和外部贸易合作伙伴之间的文档，可能需要公开可从 Internet 访问的公共面向站点上的传输。 在这些情况下，建议使用以下域配置：  
  
- **使用外围网络域，（也称为外围安全区域 (DMZ) 或屏蔽子网），对房屋服务器来提供 Internet 相关服务为你的组织**  
  
   外围网络域应包含容纳其中面向 Internet 的传输路由文档运行的计算机之间的物理位置的服务器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与贸易合作伙伴。 外围网络防火墙只应该打开以允许从 Internet 传输之间的通信所需的端口。 不应运行的任何计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]外围网络域中接收位置或企业单一登录服务器的计算机。 应将文档发送/接收向/从外围网络域中的传输从面向 Internet 的防火墙路由到保护使用 Internet Security and Acceleration Server (ISA) Server Web 发布在处理域的防火墙和服务器发布。 有关使用 ISA Server Web 角色和发布服务器的详细信息，请参阅[ISA Server 2006 中发布概念](http://go.microsoft.com/fwlink/?LinkID=86359)(<http://go.microsoft.com/fwlink/?LinkID=86359>)。  
  
  > [!NOTE]  
  >  当附加的安全，措施考虑进行文档加密和解密使用公钥基础结构 (PKI) 数字证书，文档签名和验证 （不可否认性） 的文档发送或接收来自贸易通过此域中的传输面向 Internet 的合作伙伴。  
  
   可从 Internet 访问的外围网络域通常用于下列传输：  
  
  -   FTP-若要接收使用 FTP 协议文档  
  
  -   SMTP-发送使用 SMTP 协议文档  
  
  -   HTTP-若要接收使用 HTTP 协议的文档  
  
  -   SOAP-若要接收使用 SOAP 的文档  
  
  -   POP3 的接收使用 POP3 协议文档  
  
- **使用处理域来存放包含 BizTalk Server 的服务器接收和发送处理程序和 BAM 门户服务器**  
  
   应通过这些域之间的防火墙路由之间外围域中的外部面向传输和处理域中的 BizTalk 适配器的文档流。 处理域应存放[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]端口、 接收位置、 管道、 映射、 架构和程序集用来接收、 路由并发送消息。 处理域还应包含 BAM 门户的服务器。 运行的计算机数量[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]处理域中将取决于主机的数目，托管实例需要以满足你的组织的所需的性能。  
  
  > [!IMPORTANT]  
  >  请确保在要容纳外围域中的 HTTP 和 SOAP 传输和处理域中的 HTTP 和 SOAP 适配器之间的通信的处理域中创建足够的独立的主机实例。 如果你的组织和贸易合作伙伴之间的文档通信有很大一部分通过 HTTP 和 SOAP 传输流，必须有足够的处理带宽，来处理文档流在处理域中。  
  
- **使用其他域来为您的环境提供进一步的隔离和安全层**  
  
   这些域中应包括：  
  
  - 服务域，且受处理域和需要用到已成功处理消息。 服务域中的服务器通常运行 BizTalk 业务流程、 管道、 企业单一登录 (SSO) 服务，业务规则引擎，并且可能包括其他业务流程。  
  
  - 运行所使用的 SQL Server 的计算机的数据域[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
  - 公司域为服务器和台式计算机，以向你的组织中的信息工作者提供服务。  
  
    有关域拓扑，建议为各种详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]体系结构，请参阅[Sample BizTalk Server Architectures](http://go.microsoft.com/fwlink/?LinkId=155750) (<http://go.microsoft.com/fwlink/?LinkId=155750>)。  
  
## <a name="high-availability-considerations"></a>高可用性注意事项  
 可以由 BizTalk 组中的多个 BizTalk 服务器上运行适配器处理程序主机实例为大多数适配器提供高可用性。 这样一来，一个适配器处理程序主机实例失败，另一个适配器处理程序主机实例可用于继续进行处理。 但是，存在一些例外情况执行此操作。 在某些情况下运行多个适配器处理程序主机实例可能会导致争用问题。 例如运行 POP3 和 FTP 适配器的多个实例时，可能会发生争用问题。 在这些情况下，高可用性可以通过在群集 BizTalk 主机中运行适配器处理程序主机实例提供的适配器。  
  
 有关通过聚类分析的主机适配器处理程序主机实例提供高可用性的详细信息，请参阅[群集主机内运行适配器处理程序的注意事项](http://go.microsoft.com/fwlink/?LinkID=151284)(http://go.microsoft.com/fwlink/?LinkID=151284)。 有关为 BizTalk 主机提供高可用性的详细信息，请参阅[BizTalk 主机的高可用性](../technical-guides/high-availability-for-biztalk-hosts.md)。  
  
## <a name="performance-considerations"></a>性能注意事项  
 **SOAP 适配器的性能注意事项**  
  
 有关 SOAP 适配器的性能优化的信息，请参阅[配置参数的影响适配器性能](http://go.microsoft.com/fwlink/?LinkID=154200)(http://go.microsoft.com/fwlink/?LinkID=154200)。  
  
 **MQSeries 适配器的性能注意事项**  
  
 **禁用事务支持和按序送达，如果不是所需的 MQSeries 适配器接收位置**时 MQSeries 适配器接收位置配置有**事务支持**选项设置为**是**，或**Ordered**选项设置为**顺序停止**，然后将 Microsoft 分布式上下文中处理通过接收位置提取每条消息事务处理协调器 (MSDTC) 事务。 由于没有其他销量时处理的 MSDTC 事务上下文中的消息，这些选项不应启用如果按序送达或事务支持不是必需的 MQSeries 适配器可以接收位置。  
  
## <a name="planning-for-ordered-message-delivery"></a>规划按序送达的消息  
 按序送达的消息可确保发布到 MessageBox 数据库中给定订单的消息将传送到相同的顺序在每个匹配的订户。 实现按序的送达消息时，应考虑以下事项：  
  
 **配置按序送达的消息**  
  
 可以在以下位置配置按序消息送达：  
  
- 业务流程中的 接收 形状  
  
- 某些适配器的接收位置  
  
- 发送端口  
  
  **按序送达使用现有传输实现**  
  
  某些传输的基础协议（例如，FILE 和 HTTP）与按序送达的概念不一致。 但是，即使对于此类传输，如果将绑定到传输的端口标记为按序送达，BizTalk Server 也会通过确保在当前消息成功发送之后再获取下一个出站消息来强制实现按序送达。 若要实现此目的，BizTalk Server 每个将消息传递到传输的适配器在单个批次并等待直到适配器已成功删除该消息从 MessageBox 数据库在另一个批处理中的下一条消息，交付到适配器之前。  
  
  **自定义适配器按序送达**  
  
  自定义接收适配器提交给 BizTalk Server 时保留消息的顺序，适配器必须开发具有以下功能：  
  
- 在提交一批消息之后, 您的自定义接收适配器应提交下一批之前等待来自 BizTalk Server 的 BatchComplete 回调。 有关更多详细信息，请参阅[Batch-Supported 接收适配器的接口](http://go.microsoft.com/fwlink/?LinkId=155752)(http://go.microsoft.com/fwlink/?LinkId=155752)。  
  
- 如果消息在管道中失败，则应挂起，最好作为不可恢复。 使用 BTS。SuspendAsNonResumable 消息上下文属性在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]来适当地标记消息。  
  
  > [!NOTE]  
  >  如果随后恢复了挂起的消息，则可能会打乱消息顺序。 如果不希望此行为，挂起且不可恢复的失败的消息。  
  
  **条件的端到端按序消息处理**  
  
  为提供端对端的按序送达功能，必须满足以下条件：  
  
- 接收消息的适配器必须保持消息提交给 BizTalk Server 时的顺序。 在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，这样的适配器的示例包括 MSMQ 和 MQSeries。 此外，HTTP 或 SOAP 适配器也可以用来按序提交消息，但在该情况下，HTTP 或 SOAP 客户端需要通过每次提交一条消息来强制实现顺序提交。  
  
- 您必须订阅这些消息与发送端口都**按序送达**选项设置为**True**。  
  
- 如果业务流程来的处理消息，只能运行一个业务流程实例应使用，该业务流程应配置为使用顺序保护，并**按序送达**属性业务流程的接收端口应设置为 **，则返回 True**。  
  
## <a name="see-also"></a>请参阅  
 [为 BizTalk Server 规划环境](../technical-guides/planning-the-environment-for-biztalk-server.md)