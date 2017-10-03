---
title: "规划用于发送和接收 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3d67e5f7-5127-4c1d-be20-8d8dbb538286
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf635712e7cafa534f7b6441407e4ec31e8bf047
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="planning-for-sending-and-receiving"></a>规划用于发送和接收
处理的几乎每个文档[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]由接收[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收适配器，并从发送[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]发送适配器。 因为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]适配器因此突出图中任何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境中，务必要提前计划来确定哪些适配器或快捷键，你将使用以及如何正确配置这些适配器和/或快捷键。  
  
## <a name="determining-which-adapters-and-accelerators-you-will-use"></a>确定哪些适配器和快捷键将使用  
 贸易合作伙伴提前来确定哪些适配器和快捷键将需要促进发送和接收文档之间以及 BizTalk 应用程序与内部之间组织和贸易合作伙伴，请咨询业务应用程序。 设计你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将来体系结构为灵活到足以容纳添加其他适配器或快捷键的事件中建立关系与其他贸易合作伙伴。  
  
## <a name="functionality-supported-by-biztalk-adapters"></a>BizTalk 适配器支持的功能  
 本部分中的表列出每个本机适配器并且适配器是否提供了以下功能的主要的优点：  
  
-   **事务支持**能够发送和接收的分布式的事务处理协调器 (DTC) 事务的上下文中的文档。 若要确保按序送达消息并且不会复制或丢失文档，则必须使用此功能。  
  
    > [!NOTE]  
    >  如果你遇到与 MSDTC 的问题，阅读主题[问题疑难解答与 MSDTC](http://go.microsoft.com/fwlink/?LinkID=154693) (http://go.microsoft.com/fwlink/?LinkID=154693)。  
  
-   **双向通信支持 （请求/响应或请求/响应）**能够处理目标的响应消息并将文档发送或接收文档并将响应消息发送到源。  
  
-   **按顺序获得支持。** 能够将接收到的文档发布到 MessageBox 数据库文档已接收的确切顺序。  
  
    > [!NOTE]  
    >  某些适配器可以强制执行级别接收位置的有序的文档传递，而其他适配器不能。 仍在发送端口级别有序接收位置级别的文档传送这些适配器不支持强制执行有序的传递，但这样做会降低对性能产生负面影响。 消息的有序传递的详细信息，请参阅主题[有序的消息的传递](http://go.microsoft.com/fwlink/?LinkId=155751)(http://go.microsoft.com/fwlink/?LinkId=155751)。  
  
-   **启用 SSO。** 能够在通过适配器发送或接收文档时使用 SSO 验证。  
  
|适配器|主要好处|事务支持|双向通信支持|按顺序接收支持|启用 SSO|  
|-------------|---------------------|-------------------------|------------------------------------|-------------------------------|-----------------|  
|文件|易于使用|是|“否”|“否”|是|  
|FTP|广泛用于企业到企业通信|是|“否”|是|是|  
|HTTP(s)|广泛用于企业到企业通信|是|请求/响应和要求/响应|是|是|  
|SOAP|支持 Web 服务的使用|是|请求/响应和要求/响应|是|是|  
|MSMQ|有保障的 BizTalk Server 和 Microsoft 消息队列之间的消息仅一次传递的支持|是|“否”|是|是|  
|MQ Series|保证仅一次传递消息 BizTalk Server 和 IBM WebSphere MQ 之间的 Windows 平台的支持|是|“否”|是|是|  
|SQL|支持直接 BizTalk Server 和 SQL Server 数据库之间的通信|是|仅要求/响应|是|是|  
|Windows SharePoint Services|支持 XML 和 BizTalk Server 和 SharePoint 文档库之间的二进制消息的交换|是|“否”|“否”|是|  
|POP3|接收文档通过电子邮件的支持|是|“否”|“否”|是|  
|SMTP|支持发送文档通过电子邮件|是|“否”|“否”|是|  
|EDI|支持处理符合 EDI 标准的业务文档|是|“否”|“否”|是|  
|自定义|支持您的旧系统|是，但需要自定义代码。|是，但需要自定义代码。|是，但需要自定义代码。|是，但需要自定义代码。|  
|WCF-WSHttp|支持 WS-* 标准 HTTP 传输|是，WsHTTP 支持事务（仅限 WS-Transactions）|请求/响应和要求/响应|是|是|  
|WCF-BasicHttp|与基于 ASMX 的 Web 服务和客户端以及符合 WS 其他服务进行通信的基本配置文件 1.1 使用 HTTP 或 HTTPS|是|请求/响应和要求/响应|是|是|  
|WCF-NetTcp|支持 WS-* 标准通过 TCP 传输|是|请求/响应和要求/响应|是|是|  
|WCF-NetMsmq|通过利用 Microsoft 消息队列 (MSMQ) 作为传输协议队列的支持|是|“否”|是|是|  
|WCF-NetNamedPipe|（仅适用于 WCF 应用程序） 在同一计算机上的跨进程通信提供快速传输|是|请求/响应和要求/响应|是|是|  
|WCF-Custom|启用 WCF 扩展性功能的使用|是。|是。|是，只要绑定支持。|是。|  
|WCF-CustomIsolated|启用通过 HTTP 传输的 WCF 扩展性功能|是。|是。|否。|是。|  
  
## <a name="line-of-business-adapters"></a>业务线适配器  
 下面是 Microsoft 提供的业务线 (LOB) 适配器的列表。  
  
> [!NOTE]  
>  除了 mySAP Microsoft BizTalk 适配器 v2.0™ Business Suite （适配器），无业务线适配器支持 Windows Vista 上。  
  
|适配器|Description|支持的版本|  
|-------------|-----------------|------------------------|  
|SAP （也称为"适配器"）|启用 exchange 中间文档 (IDOC)、 BAPI，和远程函数调用 BizTalk Server 和 SAP R/3® 系统之间的 (文档 RFC) 消息。|SAP R/3 4.x 和 R/3 6.20 (Enterprise)|  
|PeopleSoft Enterprise|用于在 BizTalk Server 和 PeopleSoft 系统间交换组件接口 (CI) 消息。|PeopleTools 版本 8.17.02、8.43、8.45、8.46 和 8.48|  
|JD Edwards OneWorld XE|用于在 BizTalk Server 和 JD Edwards OneWorld 系统间交换业务功能消息。|B7.3.3.3 SP23 和 JDE 8.0 (B7.3.3.4)|  
|JD Edwards EnterpriseOne|用于在 BizTalk Server 和 JD Edwards EnterpriseOne 系统间交换业务功能消息。|8.10 和工具与 8.11 释放 8.93、 8.94、 8.95 和 8.96|  
|ODBC Adapter for Oracle Database|用于从 Oracle Server 数据库读取信息和将信息写入该数据库。|Oracle 8i (8.1.6.0) 9i (9.2.0.1) 或 10g|  
|Siebel eBusiness Applications|用于在 BizTalk Server 和 Siebel eBusiness Application 间交换业务组件和业务服务消息。|7.0、 7.5。 *、 7.7。\*，和 7.8。\*|  
|TIBCO Rendezvous|用于在 BizTalk Server 和 TIBCO Rendezvous 间交换 XML 和二进制数据格式消息。|7.3|  
|TIBCO Enterprise Message Service|用于在 BizTalk Server 和 TIBCO EMS 服务器间交换 XML 和二进制数据格式消息，可提供一个高度整合的可靠的应用程序基础结构。|4.2|  
|WebSphere MQ|用于在 BizTalk Server 和 IBM WebSphere MQ 间交换消息。|5.3 修复包 10 或更高版本和 6.0 修复包 1.1 或更高版本|  
  
 有关适用于的 LOB 适配器详细信息[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]，请参阅[BizTalk Server 2010 中包含的适配器](http://go.microsoft.com/fwlink/?LinkId=152664)(http://go.microsoft.com/fwlink/?LinkId=152664)。  
  
## <a name="biztalk-adapter-pack"></a>BizTalk 适配器包  
 Microsoft[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]包含基于 WCF 的适配器，以提供到 LOB 应用程序，例如 Oracle 数据库、 Oracle E-business Suite、 SAP、 Siebel 和 SQL Server 的连接。 有关可使用的适配器列表[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]，请参阅[BizTalk 适配器包](http://go.microsoft.com/fwlink/?LinkId=152665)(http://go.microsoft.com/fwlink/?LinkId=152665)。  
  
> [!IMPORTANT]  
>  你可以使用[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]迁移工具迁移到 BizTalk 项目类型提供的基于 WCF LOB 适配器附带的 BizTalk 项目类型提供的 LOB 适配器[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。 你可以下载[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]迁移工具从[BizTalk 适配器包迁移工具](http://go.microsoft.com/fwlink/?LinkID=153328)(http://go.microsoft.com/fwlink/?LinkID=153328)。 若要了解有关迁移的 LOB 适配器附带的基于 WCF LOB 适配器到[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]，请参阅[Microsoft BizTalk 适配器 2.0 迁移白皮书](http://go.microsoft.com/fwlink/?LinkId=158848)(http://go.microsoft.com/fwlink/?LinkId=158848)。  
  
## <a name="biztalk-accelerators"></a>BizTalk 加速器  
 BizTalk 适配器适应与特定协议的发送和接收文档，而 BizTalk 加速器旨在满足根据特定的行业标准的文档的交换。 有关可用的 BizTalk 快捷键的列表，请参阅[Microsoft BizTalk Server 加速器](http://go.microsoft.com/fwlink/?LinkId=103609)(http://go.microsoft.com/fwlink/?LinkId=103609)。  
  
##  <a name="BKMK_InternetTrans"></a>公开传输到 Internet 时配置你的域  
 为了简化发送和接收的组织和外部贸易合作伙伴之间的文档，可能需要公开可从 Internet 访问的公共面向站点上的传输。 在这些情况下，建议使用以下域配置：  
  
-   **采用的外围网络域 （也称为外围安全区域 (DMZ) 或屏蔽子网），到内部服务器以提供 Internet 相关的服务为你的组织**  
  
     外围网络域应包含容纳其中面向 Internet 的传输将运行的计算机之间的文档的路由的物理位置的服务器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和贸易合作伙伴。 外围网络防火墙应只打开需要该项以允许与面向传输 Internet 通信的端口。 不应运行的任何计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收在外围网络域中的位置或企业单一登录服务器计算机。 应将文档发送/接收到/从外围网络域中的传输面向 Internet 的防火墙从路由到防火墙保护使用 Internet 安全和加速服务器 (ISA) Server Web 发布处理域和服务器发布。 有关使用 ISA Server 网页和发布服务器的详细信息，请参阅[在 ISA Server 2006 年发布概念](http://go.microsoft.com/fwlink/?LinkID=86359)(http://go.microsoft.com/fwlink/?LinkID=86359)。  
  
    > [!NOTE]  
    >  附加的安全，措施考虑出于文档加密和解密的目的使用公钥基础结构 (PKI) 数字证书，记录签名和验证 （不可否认性） 的文档发送到或接收从贸易通过此域中的传输面向 Internet 的合作伙伴。  
  
     可从 Internet 访问的外围网络域通常使用的以下传输：  
  
    -   FTP-接收使用 FTP 协议文档  
  
    -   SMTP-要将文档使用 SMTP 协议发送  
  
    -   HTTP-若要接收使用 HTTP 协议的文档  
  
    -   SOAP-若要接收使用 SOAP 的文档  
  
    -   POP3-要接收使用 POP3 协议的文档  
  
-   **采用将处理域指向内部包含 BizTalk Server 的服务器接收和发送处理程序和 BAM 门户服务器**  
  
     应通过这些域之间的防火墙路由外围域中的外部面向传输和处理域中的 BizTalk 适配器之间的文档流。 处理域应存放[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]端口，接收位置、 管道、 映射和架构，并用于接收的程序集将路由，和将消息发送。 处理域还应包含 BAM 门户的服务器。 运行的计算机数[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]处理域中将取决于主机的数目和托管满足你组织的性能需求所需的实例。  
  
    > [!IMPORTANT]  
    >  确保在处理域以适应流量流向外围域中的 HTTP 和 SOAP 传输和处理域中的 HTTP 和 SOAP 适配器之间创建足够的独立的主机实例。 如果你的组织和贸易合作伙伴之间的文档通信的很大一部分通过 HTTP 和 SOAP 传输流，必须有足够的处理带宽在要处理的文档流的处理域中。  
  
-   **使用其他域，以提供有关你的环境的进一步的隔离和安全层**  
  
     这些域中应包括：  
  
    -   服务域，哪些受信任的处理域和需成功处理消息。 服务域中的服务器通常运行 BizTalk 业务流程、 管道、 企业单一登录 (SSO) 服务，业务规则引擎，并且可能包括其他业务流程。  
  
    -   运行 SQL Server 使用的计算机的数据域[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
    -   服务器和台式计算机以向你的组织中的信息工作者提供服务的企业域。  
  
     有关为各种建议域拓扑的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]体系结构，请参阅[示例 BizTalk 服务器体系结构](http://go.microsoft.com/fwlink/?LinkId=155750)(http://go.microsoft.com/fwlink/?LinkId=155750)。  
  
## <a name="high-availability-considerations"></a>高可用性注意事项  
 BizTalk 组中的多个 BizTalk 服务器上运行适配器处理程序主机实例，可以为大多数适配器提供高可用性。 这样一来，如果一个适配器处理程序主机实例失败，则另一个适配器处理程序主机实例，可继续进行处理。 有，但是，例外执行此操作。 在某些情况下运行处理程序主机实例的多个适配器可能导致争用问题。 例如运行 POP3 和 FTP 适配器的多个实例时，可能会导致争用问题。 在这些情况下，高可用性可以通过在群集的 BizTalk 主机运行适配器处理程序主机实例提供的适配器。  
  
 有关为通过群集的主机适配器处理程序主机实例提供高可用性的详细信息，请参阅[在群集主机内运行适配器处理程序的注意事项](http://go.microsoft.com/fwlink/?LinkID=151284)(http://go.microsoft.com/fwlink/?LinkID=151284)。 有关为 BizTalk 主机提供高可用性的详细信息，请参阅[BizTalk 主机的高可用性](../technical-guides/high-availability-for-biztalk-hosts.md)。  
  
## <a name="performance-considerations"></a>性能注意事项  
 **SOAP 适配器性能注意事项**  
  
 有关优化性能的 SOAP 适配器的信息，请参阅[配置参数会影响适配器性能](http://go.microsoft.com/fwlink/?LinkID=154200)(http://go.microsoft.com/fwlink/?LinkID=154200)。  
  
 **MQSeries 适配器性能注意事项**  
  
 **禁用事务支持和有序传送，如果不是所需的 MQSeries 适配器接收位置**时 MQSeries 适配器接收配置位置**事务支持**选项设置为**是**，或**Ordered**选项设置为**停止使用的顺序**，然后由接收位置选取每条消息将处理 Microsoft 分布式的上下文中事务处理协调器 (MSDTC) 事务。 由于没有其他适配器的开销量处理 MSDTC 事务的上下文中的消息，这些选项不应启用如果有序传送或事务支持不需要 MQSeries 时接收位置。  
  
## <a name="planning-for-ordered-message-delivery"></a>规划有序的消息传递  
 有序的消息传递可确保发布到 MessageBox 数据库按给定顺序的消息都会传递到每个匹配的订阅服务器的相同顺序。 实现的消息有序的传递时，应考虑以下事项：  
  
 **配置有序的消息传递**  
  
 可以在以下位置配置按序消息送达：  
  
-   业务流程中的 接收 形状  
  
-   接收位置某些适配器  
  
-   发送端口  
  
 **具有现有的传输方式的传递顺序**  
  
 某些传输的基础协议（例如，FILE 和 HTTP）与按序送达的概念不一致。 但是，即使对于此类传输，如果将绑定到传输的端口标记为按序送达，BizTalk Server 也会通过确保在当前消息成功发送之后再获取下一个出站消息来强制实现按序送达。 若要实现此目的，BizTalk Server 每个将消息传递到传输的适配器，在单个批处理并等待直到适配器已成功将消息从数据库中删除 MessageBox 另一个批处理中的下一条消息，交付给适配器之前。  
  
 **传递顺序的自定义适配器**  
  
 自定义接收适配器时将它们提交到 BizTalk Server 保留消息的顺序，适配器必须开发具有以下功能：  
  
-   提交一批消息之后, 你自定义接收适配器应在提交下一批之前等待 BatchComplete 调用从 BizTalk Server。 有关更多详细信息，请参阅[Batch-Supported 接收适配器接口](http://go.microsoft.com/fwlink/?LinkId=155752)(http://go.microsoft.com/fwlink/?LinkId=155752)。  
  
-   如果消息在管道中失败，它应挂起，最好是作为非可恢复。 使用 BTS。中的 SuspendAsNonResumable 消息上下文属性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]相应地标记消息。  
  
    > [!NOTE]  
    >  如果随后恢复了挂起的消息，则可能会打乱消息顺序。 如果您不希望此行为，挂起作为非可恢复的失败的消息。  
  
 **端到端条件有序消息处理**  
  
 为提供端对端的按序送达功能，必须满足以下条件：  
  
-   接收消息的适配器必须保持消息提交给 BizTalk Server 时的顺序。 在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，这样的适配器的示例包括 MSMQ 和 MQSeries。 此外，HTTP 或 SOAP 适配器也可以用来按序提交消息，但在该情况下，HTTP 或 SOAP 客户端需要通过每次提交一条消息来强制实现顺序提交。  
  
-   您必须订阅拥有的发送端口与这些消息**按序送达**选项设置为**True**。  
  
-   如果业务流程用于的处理应使用的消息，仅业务流程的单个实例，应将业务流程配置为使用顺序保护和**按序送达**属性业务流程的接收端口应设置为**True**。  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Server 规划环境](../technical-guides/planning-the-environment-for-biztalk-server.md)