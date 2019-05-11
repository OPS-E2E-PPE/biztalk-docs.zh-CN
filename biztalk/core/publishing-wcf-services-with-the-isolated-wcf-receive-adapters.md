---
title: 接收适配器发布 WCF 服务通过独立 WCF |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive adapters, WCF services
- publishing, WCF services
- WCF services, receive adapters
- WCF services, publishing
ms.assetid: 62ebf373-075c-4c98-8130-ac2cf06e4a70
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5cf917a0d796d3fb17d4b3ae69eb5146bcc91f0b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398370"
---
# <a name="publishing-wcf-services-with-the-isolated-wcf-receive-adapters"></a>发布 WCF 服务通过独立 WCF 接收适配器
BizTalk Windows Communication Foundation (WCF) 适配器允许[!INCLUDE[btsCoName](../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与基于 WCF 的应用程序进行通信。 BizTalk WCF 适配器包括七个物理适配器。 除 WCF CustomIsolated 适配器之外的每个适配器包含发送和接收适配器。  
  
 WCF 接收适配器提供两种类型的适配器： 独立 WCF 适配器和进程内 WCF 适配器。 尽管进程内适配器由[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，独立的适配器不通过实例化[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 相反，它们是实例化，在另一个进程中托管。 运行 Internet 信息服务 (IIS) 中的 Web 应用程序中托管的独立的 WCF 适配器。  
  
> [!NOTE]
>  通过独立 WCF 适配器发布 WCF 服务之前，应具有托管 WCF 服务如何了解在 Internet 信息服务 (IIS)。 有关在 IIS 中承载的 WCF 服务的详细信息，请参阅"在 IIS 中承载"网址[ http://go.microsoft.com/fwlink/?LinkID=75700 ](http://go.microsoft.com/fwlink/?LinkID=75700)。  
  
 **版本的 IIS**  
  
 可以在以下操作系统上的以下版本的 IIS 上承载三个独立的 WCF 适配器 （Wcf-customisolated、 Wcf-basichttp 和 Wcf-wshttp）：  
  
-   **Windows Vista 和 Windows Server 2008 上的 IIS 7.0/7.5。** IIS 7.0/7.5 提供与 IIS 6.0 相同的高级的进程模型。 已发布的 BizTalk WCF 服务必须运行在 ASP.NET 兼容性模式下的 IIS 7.0/7.5。  
  
> [!NOTE]
>  即使 Windows 进程激活服务 (WAS) 在 IIS 7.0/7.5 中允许通过 HTTP 之外的协议激活和网络通信，独立的 WCF 适配器也仅支持 HTTP 传输。  
  
 **独立的 WCF 适配器**  
  
 以下是独立 WCF 适配器的列表：  
  
- **Wcf-wshttp 适配器**。 提供对于 WS-* 标准的支持通过 HTTP 传输。 Wcf-wshttp 适配器实现了下列规范：WS 事务之间外部应用程序和 MessageBox 数据库和 Ws-security 的消息安全性和身份验证的事务交互。 传输协议是 HTTP 或 HTTPS，并且消息编码是文本或消息传输优化机制 (MTOM) 编码。  
  
- **Wcf-basichttp 适配器**。 与基于 ASMX 的 Web 服务和客户端，并与其他服务相符合 WS-Basic Profile 1.1。 传输协议是 HTTP 或 HTTPS，并且消息编码是文本或 MTOM 编码。  
  
- **Wcf-customisolated 适配器**。 允许通过 HTTP 传输使用 WCF 扩展功能。 该适配器，可以选择和配置 WCF 绑定和行为信息在独立主机中运行的接收位置。  
  
  **通过独立 WCF 适配器发布 WCF 服务**  
  
  若要发布 WCF 服务通过独立 WCF 接收适配器，则必须使用 BizTalk WCF 服务发布向导创建 Web 应用程序来承载独立的 WCF 适配器。 此外，BizTalk WCF 服务发布向导创建的 Web 应用程序的根文件夹中生成以下文件：  
  
|             文件             |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             文件夹                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |                                                                                                                                                         Description                                                                                                                                                         |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  WCF 服务 （.svc 文件）   |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     \|WCF 服务，用于 WCF 接收位置发布的独立 WCF 适配器。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |                                                                                                                                                                                                                                                                                                                             |
|          Web.config          | \|包含 ASP.NET Web 应用程序行为、 已发布的 WCF 服务行为、 元数据终结点和特定于 BizTalk 的设置信息的 ASP.NET 配置文件。 通过 BizTalk WCF 发布向导生成的默认元数据绑定不安全，它允许匿名访问的元数据。 服务元数据包含有关服务的详细的说明，可能会有意或无意地包含敏感信息。 若要防止未经授权的访问服务元数据，您可以修改 Web.config 以元数据终结点使用安全绑定。 **注意：** 并非所有组合的元数据终结点绑定和服务终结点绑定都都有效。 在某些情况下，元数据终结点的绑定配置必须与其服务终结点的绑定配置一致。 例如，不能在其服务终结点的安全模式依赖于 HTTPS 时需要 HTTP 传输的安全模式下配置元数据终结点。 |                                                                                                                                                                                                                                                                                                                             |
|    ServiceDescription.xml    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   \|XML 文件中描述的已发布的 WCF 服务协定包含消息类型。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |                                                                                                                                                                                                                                                                                                                             |
| BizTalk 架构 （.xsd 文件） |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           \App_Data                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                      XML 架构，用于定义通过独立 WCF 适配器发布的 XML 实例消息的结构。                                                                                                       |
|       SchemaIndex.xml        |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           \App_Data                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                      指示在已发布的 WCF 服务中使用的 XML 架构文件的 XML 文件。                                                                                                                       |
|      Serialization.xsd       |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           \App_Data                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |                                                       通过导出的 XML 架构[DataContractSerializer](http://go.microsoft.com/fwlink/?LinkId=81722)的类型、 元素和命名空间的属性 http://schemas.microsoft.com/2003/10/Serialization/ 。                                                        |
|       BindingInfo.xml        |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         \App_Data\Temp                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         | BizTalk 绑定文件来创建 WCF 接收位置对应于已发布的 WCF 服务。 BindingInfo.xml 文件可以导入通过开发命令行工具或向导以创建所需接收位置。 已发布的 WCF 服务在运行时中使用此文件和 Temp 文件夹。 |
|  WcfServiceDescription.xml   |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         \App_Data\Temp                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |                                                     概述了用于通过 BizTalk WCF 服务发布向导创建此 Web 应用程序的设置的 XML 文件。 已发布的 WCF 服务在运行时中使用此文件和 Temp 文件夹。                                                     |
  
 此外可以使用 BizTalk WCF 服务发布向导创建 WCF 接收位置和运行的独立的 WCF 适配器的接收位置的服务元数据。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何使用 BizTalk WCF 服务发布向导将业务流程发布为 WCF 服务](../core/publish-orchestrations-as-wcf-services--biztalk-wcf-service-publishing-wizard.md)  
  
-   [如何使用 BizTalk WCF 服务发布向导将架构发布为 WCF 服务](../core/publish-schemas-as-wcf-services--use-the-biztalk-wcf-service-publishing-wizard.md)  
  
-   [为独立的 WCF 接收适配器配置 IIS](../core/configuring-iis-for-the-isolated-wcf-receive-adapters.md)  
  
-   [如何配置使用 BizTalk WCF 服务发布向导发布 WCF 服务](../core/configure-wcf-services-published-with-the-biztalk-wcf-service-publishing-wizard.md)  
  
-   [如何创建.NET 应用程序以测试通过 BizTalk WCF 服务发布向导发布的 WCF 服务](../core/use-net-application-to-test-wcf-service-published-with-wcf-service-publishing.md)  
  
## <a name="see-also"></a>请参阅  
 [演练：使用 Wcf-basichttp 适配器发布 WCF 服务](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)