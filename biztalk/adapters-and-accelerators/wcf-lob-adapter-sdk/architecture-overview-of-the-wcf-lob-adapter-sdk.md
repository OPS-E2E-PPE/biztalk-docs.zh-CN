---
title: "WCF LOB 适配器 SDK 的体系结构概述 |Microsoft 文档"
description: "处理程序、 通道实现，连接管理、 元数据，以及使用 WCF LOB 适配器 SDK 中的 WSDL 的简介"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dbd9b63c-54a4-4f63-b3a8-8600f6009a74
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd86d2104fff0e227d9cdda4c9fb3faf1ea7cb84
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="architecture-overview-of-the-wcf-lob-adapter-sdk"></a>WCF LOB 适配器 SDK 的体系结构概述
[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]构建于 WCF 通道模型之上，并提供适配器开发人员创建到包含大型的动态元数据的业务线系统的适配器的设计时和运行时扩展。 使用创建的适配器[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]提供给使用者为自定义 WCF 绑定。 下图显示了内部体系结构和 WCF LOB 适配器 SDK 的主要组件。  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/7183bded-465e-45b9-af78-fbb87cf2df92.gif "7183bded-465e-45b9-af78-fbb87cf2df92")  
  
## <a name="handlers"></a>处理程序  
 *处理程序*定义适配器支持的消息交换模式。  
  
 下表总结了可用的处理程序类型，其函数，与[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]它们映射到的通道。  
  
|**处理程序类型**|**函数**|**映射到 WCF 通道**|  
|---|---|---|  
|`Microsoft.ServiceModel.Channels.Common.IOutboundHandler`|支持单向发送或请求/响应模式。|IOutputChannel，<br /><br /> IRequestChannel|  
|`Microsoft.ServiceModel.Channels.Common.IAsyncOutboundHandler`|支持异步单向发送或请求/响应模式。|IOutputChannel，<br /><br /> IRequestChannel|  
|`Microsoft.ServiceModel.Channels.Common.IInboundHandler`|支持单向接收或答复模式。|IInputChannel，<br /><br /> IReplyChannel|  
|`Microsoft.ServiceModel.Channels.Common.IAsyncInboundHandler`|支持的单向方法的异步变体接收或答复模式。|IInputChannel<br /><br /> IReplyChannel|  
|`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler`|支持的目标系统上的元数据浏览。|IRequestChannel|  
|`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler`|支持搜索的目标系统上的元数据。|IRequestChannel|  
|`Microsoft.ServiceModel.Channels.Common.IMetadataResolverHandler`|支持从目标系统的元数据检索。|IRequestChannel|  
  
## <a name="channel-implementation"></a>通道实现  
 使用生成的适配器[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]基本上是传输通道 (System.ServiceModel.Channels.IServiceListner)。 使用生成的适配器[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]提供给使用者为 WCF 绑定，其中使用绑定创建通道堆栈。 此绑定可被视为的其他预定义的 WCF 绑定，如 BasicHttpBinding、 WsHttpBinding 和 NetTcpBinding，对等方，并可以通过 app.config 或在代码中通过设置客户端应用程序在调用服务时。 此绑定包含绑定元素，与适配器正在从 T:System.ServiceModel.Channels.TransportBindingElement 类派生的键绑定元素的有序的集。 在出站方案中，[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]运行时使用的通道工厂以创建适配器 （即，传输通道）。 在入站方案中，[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]运行时使用的通道侦听器为传入通道在服务应用程序。  运行时间以及设计时消息都会通过此组件。  
  
## <a name="connection-factory-connection-and-connection-uri-builder"></a>连接工厂、 连接和连接 URI 生成器  
 *ConnectionFactory*提供用于创建基于 URI 和用户凭据的连接的工厂模式。 有关详细信息，请参阅`Microsoft.ServiceModel.Channels.Common.IConnectionFactory`。  
  
 *连接*定义与目标系统中，低级别的通信协定和封装本机通信 Api 和连接句柄。 有关详细信息，请参阅`Microsoft.ServiceModel.Channels.Common.IConnection`。  
  
 *连接 Uri 生成器*允许适配器使用者能够以编程方式生成连接 Uri 特定不知情的情况下的语法。 有关详细信息，请参阅`Microsoft.ServiceModel.Channels.Common.ConnectionUri`。  
  
## <a name="connection-management"></a>连接管理  
 *连接管理*负责的生存期管理的适配器的连接。 它在内部将保留连接的池可供使用。 此连接池是凭据和基于 URI 的。 凭据包含的用户名称和定义的安全上下文连接的密码在其下运行。  
  
 当使用相同的凭据和 URI 时，在相同的连接工厂下打开任何通道如果已存在一个可用获取连接池中的线程。  
  
 连接池管理器将保留与该 URI，而不考虑凭据以及与通道工厂在边界之间有多少打开连接的记录。 例如，在一个系统中，你可以有两个用户具有不同的凭据，这意味着两个连接到系统的通道工厂。  
  
> [!NOTE]
>  适配器可能会受到某些限制，它可以支持的连接数方面通常受系统资源限制。  
  
 若要帮助适配器开发人员配置连接池设置，[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]提供两个类，`Microsoft.ServiceModel.Channels.Common.ConnectionPoolSettings`和`Microsoft.ServiceModel.Channels.Common.ConnectionManagerSettings`。  
  
## <a name="metadata-management"></a>元数据管理  
 *元数据管理*负责面向对象的表示形式的目标系统的元数据缓存。 元数据可容纳在常见的缓存中访问跨所有凭据，也可以是缓存的每个凭据基础。  
  
 元数据生命周期开头其设计时定义，并在运行时期间继续通过使用情况。 在设计时，适配器开发人员必须确定的一组操作，并必须生成必要的 WSDL 和客户端代理。 在运行时，基于适配器框架的适配器使用的预定义的元数据来解释从目标系统调用返回的消息。  
  
 为了帮助配置元数据设置的适配器编写器，适配器框架，提供了三个类， `Microsoft.ServiceModel.Channels.Common.CacheSettings`，`Microsoft.ServiceModel.Channels.Common.MetadataSettings`和`Microsoft.ServiceModel.Channels.Common.CommonCacheSettings`。  
  
## <a name="wsdl-builder"></a>WSDL 生成器  
 *WSDL 生成器*提供自动 WSDL 生成从 WCF LOB 适配器 SDK 中的内部元数据对象模型 （它可以为需要自定义 WSDL 生成的方案中覆盖）。  
  
 请参阅`Microsoft.ServiceModel.Channels.Common.IWsdlRetrieval`有关详细信息。  
  
## <a name="metadata-browsesearch"></a>元数据浏览/搜索  
 *元数据浏览/搜索*允许用于浏览和搜索所有 LOB 元数据。  
  
 有关详细信息，请参阅`Microsoft.ServiceModel.Channels.IMetadataRetrievalContract`。  
  
## <a name="metadata-generation"></a>元数据生成  
 *元数据生成*允许客户端 （用于出站方案） 的生成代码以及根据选择的适配器使用者的操作 （用于入站方案） 服务。 即使我们建议适配器使用者使用的工具[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] ([!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]发生 BizTalk 应用程序时)，则[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]提供一个公共接口`Microsoft.ServiceModel.Channels.MetadataRetrievalClient.GetMetadata%2A`检索System.Web.Services.Description.ServiceDescription，它表示 Web 服务描述语言 (WSDL) 包含有关所选的操作和类型的信息。 适配器编写器常犯的元数据对象模型的使用[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]包括派生自的类`Microsoft.ServiceModel.Channels.Common.OperationMetadata`和`Microsoft.ServiceModel.Channels.Common.TypeMetadata`来描述每个操作和类型的详细信息。  
  