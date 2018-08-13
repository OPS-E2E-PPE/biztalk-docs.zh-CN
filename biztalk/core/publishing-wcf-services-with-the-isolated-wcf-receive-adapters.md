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
ms.openlocfilehash: 701b5ca0b1a056b28d6e5d3565d38c1fa7938996
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006406"
---
# <a name="publishing-wcf-services-with-the-isolated-wcf-receive-adapters"></a>通过独立 WCF 接收适配器发布 WCF 服务
BizTalk Windows Communication Foundation (WCF) 适配器允许[!INCLUDE[btsCoName](../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与基于 WCF 的应用程序进行通信。 BizTalk WCF 适配器包含七个物理适配器。 除 WCF CustomIsolated 适配器之外，每个适配器包含发送和接收适配器。  
  
 WCF 接收适配器提供以下两种类型的适配器：独立 WCF 适配器和进程内 WCF 适配器。 尽管进程内适配器由[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，独立的适配器不通过实例化[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 而是在另一个进程中实例化并以此进程为宿主。 独立 WCF 适配器承载在运行于 Internet 信息服务 (IIS) 中的 Web 应用程序中。  
  
> [!NOTE]
>  在使用独立 WCF 适配器发布 WCF 服务之前，您应当了解如何在 Internet 信息服务 (IIS) 中承载 WCF 服务。 有关在 IIS 中承载的 WCF 服务的详细信息，请参阅"在 IIS 中承载"网址[ http://go.microsoft.com/fwlink/?LinkID=75700 ](http://go.microsoft.com/fwlink/?LinkID=75700)。  
  
 **版本的 IIS**  
  
 三个独立 WCF 适配器（WCF-CustomIsolated、WCF-BasicHttp 和 WCF-WSHttp）可以承载在下列操作系统中如下版本的 IIS 上：  
  
-   **Windows Vista 和 Windows Server 2008 上的 IIS 7.0/7.5。** IIS 7.0/7.5 提供与 IIS 6.0 相同的高级的进程模型。 发布的 BizTalk WCF 服务必须在 IIS 7.0/7.5 的 ASP.NET 兼容模式下运行。  
  
> [!NOTE]
>  即使 IIS 7.0/7.5 中的 Windows 进程激活服务 (WAS) 允许通过 HTTP 以外的协议进行激活和网络通信，独立 WCF 适配器也仅支持 HTTP 传输。  
  
 **独立的 WCF 适配器**  
  
 下面是独立 WCF 适配器的列表：  
  
- **Wcf-wshttp 适配器**。 通过 HTTP 传输提供对于 WS-* 标准的支持。 WCF-WSHttp 适配器实现了下列规范：WS-Transaction（用来在外部应用程序和 MessageBox 数据库之间进行事务性交互）和 WS-Security（用来实现消息安全和身份验证）。 传输协议是 HTTP 或 HTTPS，消息编码是文本或消息传输优化机制 (MTOM) 编码。  
  
- **Wcf-basichttp 适配器**。 与基于 ASMX 的 Web Services 和客户端以及符合 WS-I 基本配置文件 1.1 的其他服务进行通信。 传输采用 HTTP 或 HTTPS，并且消息编码采用文本或 MTOM 编码。  
  
- **Wcf-customisolated 适配器**。 允许通过 HTTP 传输使用 WCF 扩展功能。 使用该适配器，可以为运行于独立主机上的接收位置选择和配置 WCF 绑定和行为信息。  
  
  **通过独立 WCF 适配器发布 WCF 服务**  
  
  若要通过独立 WCF 接收适配器发布 WCF 服务，必须使用 BizTalk WCF 服务发布向导来创建用来承载独立 WCF 适配器的 Web 应用程序。 另外，BizTalk WCF 服务发布向导还在所创建的 Web 应用程序的根文件夹中生成下列文件：  
  
|             文件             |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             文件夹                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |                                                                                                                                                         Description                                                                                                                                                         |
|------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  WCF 服务（.svc 文件）   |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     \|WCF 服务，用于 WCF 接收位置发布的独立 WCF 适配器。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |                                                                                                                                                                                                                                                                                                                             |
|          Web.config          | \|包含 ASP.NET Web 应用程序行为、 已发布的 WCF 服务行为、 元数据终结点和特定于 BizTalk 的设置信息的 ASP.NET 配置文件。 由 BizTalk WCF 发布向导生成的默认元数据绑定是不安全的，因为它允许对元数据进行匿名访问。 服务元数据中包含有关服务的详细说明，可能会有意或无意地包含敏感信息。 为了防止服务元数据受到未经授权的访问，可以修改 Web.config，使其针对元数据终结点使用安全绑定。 **注意：** 并非所有的元数据终结点绑定和服务终结点绑定的组合都有效。 在某些情况下，元数据终结点的绑定配置必须与其服务终结点的绑定配置一致。 例如，当服务终结点依赖于 HTTPS 时，其相应的元数据终结点不能在要求使用 HTTP 传输的安全模式下进行配置。 |                                                                                                                                                                                                                                                                                                                             |
|    ServiceDescription.xml    |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   \|XML 文件中描述的已发布的 WCF 服务协定包含消息类型。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   |                                                                                                                                                                                                                                                                                                                             |
| BizTalk 架构（.xsd 文件） |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           \App_Data                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                      XML 架构，用于定义通过独立 WCF 适配器发布的 XML 实例消息的结构。                                                                                                       |
|       SchemaIndex.xml        |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           \App_Data                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                      指示在已发布 WCF 服务中使用的 XML 架构文件的 XML 文件。                                                                                                                       |
|      Serialization.xsd       |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           \App_Data                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |                                                       通过导出的 XML 架构[DataContractSerializer](http://go.microsoft.com/fwlink/?LinkId=81722)的类型、 元素和命名空间的属性 http://schemas.microsoft.com/2003/10/Serialization/ 。                                                        |
|       BindingInfo.xml        |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         \App_Data\Temp                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         | 用来创建与已发布的 WCF 服务对应的 WCF 接收位置的 BizTalk 绑定文件。 BindingInfo.xml 文件可以通过开发命令行工具或向导导入，以创建所需接收位置。 已发布的 WCF 服务在运行时不使用此文件和 Temp 文件夹。 |
|  WcfServiceDescription.xml   |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         \App_Data\Temp                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |                                                     XML 文件，概述与 BizTalk WCF 服务发布向导一起用来创建此 Web 应用程序的设置。 已发布的 WCF 服务在运行时不使用此文件和 Temp 文件夹。                                                     |
  
 您还可以使用 BizTalk WCF 服务发布向导为运行于独立 WCF 适配器中的接收位置创建 WCF 接收位置和服务元数据。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何使用 BizTalk WCF 服务发布向导将业务流程发布为 WCF 服务](../core/publish-orchestrations-as-wcf-services--biztalk-wcf-service-publishing-wizard.md)  
  
-   [如何使用 BizTalk WCF 服务发布向导将架构发布为 WCF 服务](../core/publish-schemas-as-wcf-services--use-the-biztalk-wcf-service-publishing-wizard.md)  
  
-   [为独立的 WCF 接收适配器配置 IIS](../core/configuring-iis-for-the-isolated-wcf-receive-adapters.md)  
  
-   [如何配置使用 BizTalk WCF 服务发布向导发布 WCF 服务](../core/configure-wcf-services-published-with-the-biztalk-wcf-service-publishing-wizard.md)  
  
-   [如何创建.NET 应用程序以测试通过 BizTalk WCF 服务发布向导发布的 WCF 服务](../core/use-net-application-to-test-wcf-service-published-with-wcf-service-publishing.md)  
  
## <a name="see-also"></a>请参阅  
 [演练：通过 WCF-BasicHttp 适配器发布 WCF 服务](../core/walkthrough-publishing-wcf-services-with-the-wcf-basichttp-adapter.md)