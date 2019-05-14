---
title: WCF LOB 适配器 SDK 的体系结构概述 |Microsoft Docs
description: 介绍了处理程序，信道实现、 连接管理、 元数据，和使用 WCF LOB 适配器 SDK 中的 WSDL
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dbd9b63c-54a4-4f63-b3a8-8600f6009a74
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de1214859a94a05271d2cabc931dcf9531cdcf0c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364003"
---
# <a name="architecture-overview-of-the-wcf-lob-adapter-sdk"></a>WCF LOB 适配器 SDK 的体系结构概述
[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] WCF 通道模型的基础上构建并提供适配器开发人员能够创建于具有大型的动态元数据的业务线系统的适配器设计时和运行时扩展。 创建使用的适配器[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]提供给使用者为自定义 WCF 绑定。 下图显示了内部体系结构和 WCF LOB 适配器 SDK 的主要组件。  
  
 ![](../../adapters-and-accelerators/wcf-lob-adapter-sdk/media/7183bded-465e-45b9-af78-fbb87cf2df92.gif "7183bded-465e-45b9-af78-fbb87cf2df92")  
  
## <a name="handlers"></a>处理程序  
 *处理程序*定义适配器支持的消息交换模式。  
  
 下表总结了可用的处理程序类型，其功能和[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]它们映射到的频道。  
  
|**处理程序类型**|**函数**|**映射到 WCF 通道**|  
|---|---|---|  
|`Microsoft.ServiceModel.Channels.Common.IOutboundHandler`|支持单向发送或请求/响应模式。|IOutputChannel,<br /><br /> IRequestChannel|  
|`Microsoft.ServiceModel.Channels.Common.IAsyncOutboundHandler`|支持异步单向发送或请求/响应模式。|IOutputChannel,<br /><br /> IRequestChannel|  
|`Microsoft.ServiceModel.Channels.Common.IInboundHandler`|支持单向接收或答复模式。|IInputChannel,<br /><br /> IReplyChannel|  
|`Microsoft.ServiceModel.Channels.Common.IAsyncInboundHandler`|支持的单向方法的异步变体接收或答复模式。|IInputChannel<br /><br /> IReplyChannel|  
|`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler`|支持的目标系统上的元数据浏览。|IRequestChannel|  
|`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler`|支持搜索的目标系统上的元数据。|IRequestChannel|  
|`Microsoft.ServiceModel.Channels.Common.IMetadataResolverHandler`|支持从目标系统的元数据检索。|IRequestChannel|  
  
## <a name="channel-implementation"></a>信道实现  
 使用生成的适配器[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]基本上是传输通道 (System.ServiceModel.Channels.IServiceListner)。 使用生成的适配器[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]提供给使用者为 WCF 绑定，该绑定用于创建通道堆栈。 此绑定可被视为与其他预定义的 WCF 绑定 BasicHttpBinding、 WsHttpBinding 和 NetTcpBinding，如对等，可以通过 app.config 或在代码中的客户端应用程序时设置调用的服务。 此绑定包含绑定元素，与适配器正在从 T:System.ServiceModel.Channels.TransportBindingElement 类派生的键绑定元素的有序的集。 在出站方案中，[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]运行时使用的通道工厂创建的适配器 （即，传输通道）。 在入站方案中，[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]运行时使用的通道侦听器为传入通道在服务应用程序中。  运行时以及设计时的消息通过此组件。  
  
## <a name="connection-factory-connection-and-connection-uri-builder"></a>连接工厂、 连接和连接 URI 生成器  
 *ConnectionFactory*提供用于创建基于 URI 和用户凭据的连接的工厂模式。 有关详细信息，请参阅 `Microsoft.ServiceModel.Channels.Common.IConnectionFactory` 。  
  
 *连接*定义与目标系统中，低级别通信协定和封装的本机通信 Api 和连接句柄。 有关详细信息，请参阅 `Microsoft.ServiceModel.Channels.Common.IConnection` 。  
  
 *连接 Uri 生成器*允许适配器使用者以编程方式生成连接 Uri 特定不知情的情况下的语法。 有关详细信息，请参阅 `Microsoft.ServiceModel.Channels.Common.ConnectionUri` 。  
  
## <a name="connection-management"></a>连接管理  
 *连接管理*负责的生存期管理的适配器的连接。 它在内部保留连接的池供使用。 此连接池是凭据和基于 URI 的。 该凭据包含用户名和密码用于定义连接的安全上下文下运行。  
  
 当使用相同的凭据和 URI 时，在同一个连接工厂下的打开的任何通道如果已存在一个可用获取连接池中的线程。  
  
 连接池管理器保留多少个到该 URI，而不考虑凭据并跨通道工厂的边界的打开连接的记录。 例如，在一个系统中，您可以有两个用户有不同的凭据，这意味着连接到系统的两个通道工厂。  
  
> [!NOTE]
>  该适配器可能会受到限制，它可以支持的连接数方面通常受系统资源限制。  
  
 若要帮助配置连接池设置，适配器开发人员[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]提供了两个类`Microsoft.ServiceModel.Channels.Common.ConnectionPoolSettings`和`Microsoft.ServiceModel.Channels.Common.ConnectionManagerSettings`。  
  
## <a name="metadata-management"></a>元数据管理  
 *元数据管理*负责的面向对象的表示形式的目标系统的元数据缓存。 元数据可以保存在常见的缓存可访问跨所有凭据，也可以是缓存的每个凭据基础。  
  
 元数据生命周期开始其设计时定义和在运行时通过使用情况将继续。 在设计时，适配器开发人员必须标识组的操作，并必须生成必要的 WSDL 和客户端代理。 在运行时，基于适配器框架的适配器使用的预定义的元数据来解释从目标系统调用返回的消息。  
  
 为了配置元数据设置适配器编写人员，适配器框架提供了三个类： `Microsoft.ServiceModel.Channels.Common.CacheSettings`，`Microsoft.ServiceModel.Channels.Common.MetadataSettings`和`Microsoft.ServiceModel.Channels.Common.CommonCacheSettings`。  
  
## <a name="wsdl-builder"></a>WSDL 生成器  
 *WSDL 生成器*提供自动生成的 WSDL，从 WCF LOB 适配器 SDK 的内部元数据对象模型 （需要自定义 WSDL 生成的情况下可以覆盖）。  
  
 请参阅`Microsoft.ServiceModel.Channels.Common.IWsdlRetrieval`有关详细信息。  
  
## <a name="metadata-browsesearch"></a>元数据浏览/搜索  
 *元数据浏览/搜索*允许浏览和搜索所有 LOB 元数据。  
  
 有关详细信息，请参阅 `Microsoft.ServiceModel.Channels.IMetadataRetrievalContract` 。  
  
## <a name="metadata-generation"></a>元数据生成  
 *元数据生成*允许为客户端 （用于出站方案） 生成代码并根据选择的适配器使用者的操作 （用于入站方案） 的服务。 即使我们建议适配器使用者使用的工具[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] ([!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]发生 BizTalk 应用程序时)，则[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]提供一个公共接口`Microsoft.ServiceModel.Channels.MetadataRetrievalClient.GetMetadata%2A`检索System.Web.Services.Description.ServiceDescription，它表示 Web 服务描述语言 (WSDL) 包含有关所选的操作和类型的信息。 适配器编写人员请使用为该元数据对象模型[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]包括类派生自`Microsoft.ServiceModel.Channels.Common.OperationMetadata`和`Microsoft.ServiceModel.Channels.Common.TypeMetadata`来描述每个操作和类型的详细信息。  
  