---
title: 关键组件的 WCF LOB 适配器 SDK |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 59b8029b-4799-471b-8825-15d79a30bf1f
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c034c1006ed898a28aab04cde201524e4c3b13b9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22226989"
---
# <a name="key-components-of-the-wcf-lob-adapter-sdk"></a>WCF LOB 适配器 SDK 的关键组成部分
适配器使用开发[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]需要多个以下的基本组件中的使用：  
  
-   **连接组件**以帮助建立和维护与业务线系统的连接。  
  
-   **处理程序组件**定义和实现用于处理入站和出站消息和元数据操作的过程。  
  
-   **元数据组件**定义和操作用于与业务线系统进行通信的元数据。  
  
-   **自定义组件**为事务、 可靠消息传递和安全提供支持。  
  
-   **核心组件**将所有组件绑定在一起，并确保无缝集成到[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]。  
  
 这些组件是本主题的重点。  
  
## <a name="connection-components"></a>连接组件  
 连接组件包括接口和类，可帮助定义和控制连接的生存期，以及管理统一资源标识符 (URI) 查询属性和用户属性。 连接组件包括的接口和下表中所述的类。  
  
|连接组件|必需？|Description|  
|---|---|---|  
|`Microsoft.ServiceModel.Channels.Common.ConnectionUri`|必需|用于提供生成的将使用你的适配器的用户体验的自定义的 URI 的基类。|  
|`Microsoft.ServiceModel.Channels.Common.IConnection`|必需|定义连接行为的接口。 开发人员必须实现此接口可定义了一个连接到目标系统。|  
|`Microsoft.ServiceModel.Channels.Common.IConnectionFactory`|必需|连接工厂的基类。 定义目标系统的连接工厂时，开发人员将子类。|  
|`Microsoft.ServiceModel.Channels.Common.ConnectionPoolSettings`|可选|包含控制连接池行为的设置。 开发人员可能想要调整这些值基于目标系统的行为。|  
|`Microsoft.ServiceModel.Channels.Common.ConnectionManagerSettings`|可选|包含静态控件的连接池行为的设置。 开发人员可能想要优化其目标系统的以下值。|  
  
 [!INCLUDE[afdevwizardnamelong](../../includes/afdevwizardnamelong-md.md)]将创建的实现`Microsoft.ServiceModel.Channels.Common.IConnection``Microsoft.ServiceModel.Channels.Common.ConnectionUri`和`Microsoft.ServiceModel.Channels.Common.IConnectionFactory`而不考虑所选的向导选项。 这些实现将包含支持 （包括连接 URI 中的连接属性） 向导中的所选选项的代码，但适配器开发人员必须提供打开、 关闭和其他的方法的实现`Microsoft.ServiceModel.Channels.Common.IConnection`和`Microsoft.ServiceModel.Channels.Common.ConnectionUri`.  
  
## <a name="handler-components"></a>处理程序组件  
 处理程序组件提供支持不同的消息交换模式包括入站、 出站、 异步的入站、 异步出站和元数据搜索、 浏览和解决操作。 处理程序组件包括的接口和下表中所述的类。  
  
|处理程序组件|必需？|Description|  
|---|---|---|  
|`Microsoft.ServiceModel.Channels.Common.IAsyncInboundHandler`|可选|用于以异步方式从目标系统接收消息。 异步支持是可选的。|  
|`Microsoft.ServiceModel.Channels.Common.IAsyncOutboundHandler`|可选|用于将消息异步发送从目标系统。 异步支持是可选的。|  
|`Microsoft.ServiceModel.Channels.Common.IInboundHandler`|可选|用于从目标系统接收消息。 如果适配器需要侦听来自目标系统的消息，开发人员应实现此处理程序。|  
|`Microsoft.ServiceModel.Channels.Common.IOutboundHandler`|可选|为将消息发送到目标系统提供支持。 尽管都是可选的它是必需的请求-响应消息模式。 最基本的通信技术基于包括 HTTP、 RPC 和许多其他此模式。|  
|`Microsoft.ServiceModel.Channels.Common.IMetadataBrowseHandler`|可选|适配器支持元数据浏览时，将执行此处理程序。 可选的但开发人员通常将实现此处理程序提供在目标系统中可用的操作列表。|  
|`Microsoft.ServiceModel.Channels.Common.IMetadataResolverHandler`|可选|当适配器检索并返回从目标系统，它表示特定于系统的逻辑和数据类型的元数据，则必须实现此处理程序。 可以从实际的目标系统中，检索元数据，或者可以创建用于表示目标系统的功能。 例如，FTP 适配器可以创建 GET 和 PUT 操作。<br /><br /> 尽管不要求这样做，开发人员通常将实现此处理程序，以提供有关特定操作的信息。|  
|`Microsoft.ServiceModel.Channels.Common.IMetadataSearchHandler`|可选|适配器支持元数据搜索时，将执行此处理程序。|  
  
 [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]将创建的实现`Microsoft.ServiceModel.Channels.Common.IAsyncOutboundHandler`， `Microsoft.ServiceModel.Channels.Common.IOutboundHandler`，`Microsoft.ServiceModel.Channels.Common.IInboundHandler`和元数据的处理程序基于由开发人员所做的选择。 提供了支持的代码;但是，适配器开发人员将需要提供代码以启动和停止入站侦听程序和其他 TODO 注释标记的代码。  
  
## <a name="metadata-components"></a>元数据组件  
元数据组件提供支持，用于处理元数据请求，以及描述类型和目标应用程序中的操作。 处理程序组件来控制如何将元数据请求得到处理。 元数据组件描述了数据类型和公开的目标系统操作。  

 元数据组件设计用于保存两种类型的元数据信息： 键入元数据和操作元数据。  
  
-   *类型元数据*描述目标系统中可用的数据类型并包含类型，其数组属性的名称，如果它是一个数组，以及是否它是简单的 XSD 架构类型或复杂类型。  
  
-   *操作元数据*描述目标系统中可用的操作。 属性包括返回类型、 参数和操作名称的列表。  
  
 适配器中的元数据支持是可选的但建议这样做。 使用的好处之一[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]生成与实现作为功能的适配器[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务是能够公开和绑定到一组动态的操作。  

> [!NOTE]
>  如果你需要公开一组有限的静态方法，则应考虑使用[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]。  
 
  可供处理的组件，用于描述，并将处理元数据是下表中所述。  
  
|元数据组件|Description|  
|---|---|  
|`Microsoft.ServiceModel.Channels.Common.ComplexQualifiedType`|表示适配器的复杂限定的类型的类。 例如，如果目标系统是关系数据库、 表、 行，或用户定义的过程返回的类型所有可能是自定义的限定的类型。|  
|`Microsoft.ServiceModel.Channels.Common.OperationMetadata`|用于表示目标系统的操作元数据的基类。 例如，你可以子类 OperationMetadata 以包含有关针对关系数据库适配器中的存储过程的信息。|  
|`Microsoft.ServiceModel.Channels.Common.OperationMetadataTraceRecord`|使您能够捕获到一个跟踪文件的操作元数据。 将跟踪收集的信息，如唯一 ID，最后一次访问，时间戳，显示名称、 原始名称、 参数和其他详细信息。|  
|`Microsoft.ServiceModel.Channels.Common.ParameterizedOperationMetadata`|提供一种方法定义的操作如参数和返回类型的属性。|  
|`Microsoft.ServiceModel.Channels.Common.OperationParameter`|描述用于调用目标系统上的操作的参数。 属性包括名称、 原始名称、 参数方向和一个标志，指示参数是否为空。|  
|`Microsoft.ServiceModel.Channels.Common.OperationParameterDirection`|描述的操作的参数方向的枚举的类型。 参数可以是入站仅 （中），出站唯一 （扩展） 或双向 (InOut)。|  
|`Microsoft.ServiceModel.Channels.Common.OperationResult`|表示操作结果。 可以 OperationResult.Empty 用于返回 void 或 null 的操作和一个字符串、 整数或其他值具体取决于该操作。|  
|`Microsoft.ServiceModel.Channels.Common.QualifiedType`|设计为类的基类限定类型属性，用于描述属性的目标系统的类型元数据。|  
|`Microsoft.ServiceModel.Channels.Common.QualifiedTypeContainer`|提供一组相关的限定类型的容器。|  
|`Microsoft.ServiceModel.Channels.Common.SimpleQualifiedType`|当该类型直接映射到 W3C XSD 架构类型，则介绍的目标系统的类型元数据的属性。 允许的类型的列表，请参阅[XmlTypeCode 枚举](https://msdn.microsoft.com/library/system.xml.schema.xmltypecode(v=vs.110).aspx)。|  
|`Microsoft.ServiceModel.Channels.Common.TypeMember`|提供一种结构化的类型元数据中定义的简单或复杂的数据成员。|  
|`Microsoft.ServiceModel.Channels.Common.TypeMetadata`|用于表示目标系统的类型元数据的基类。|  
|`Microsoft.ServiceModel.Channels.Common.StructuredTypeMetadata`|提供一种定义包含复杂和/或简单类型成员的数据结构。|  
|`Microsoft.ServiceModel.Channels.Common.TypeMetadataCollection`|提供一组相关的类型元数据容器。|  
|`Microsoft.ServiceModel.Channels.Common.TypeMetadataTraceRecord`|使您能够捕获到一个跟踪文件的类型元数据。 将跟踪收集信息，如唯一 ID、 上次访问时间戳和其他详细信息。|  
  
## <a name="custom-components"></a>自定义组件  
 自定义组件提供事务、 安全、 可靠消息传递和其他功能的高度依赖于目标系统的支持。 作为适配器开发人员使用[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，你将需要了解目标系统的功能，并确定你想要支持它们的范围。  
  
## <a name="core-components"></a>核心组件  
 核心组件提供一组的基类，这些类和接口，使该适配器中插入[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]。 以下表所述的核心组件。  
  
|核心组件|必需？|Description|  
|---|---|---|  
|`Microsoft.ServiceModel.Channels.Common.Adapter`|必需|使用编写一个适配器的基本类[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。 它负责与交互[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道体系结构|  
|`Microsoft.ServiceModel.Channels.Common.AdapterBinding`|必需|类包含用于控制各种设置包括连接池的适配器的设置 (`Microsoft.ServiceModel.Channels.Common.ConnectionPoolSettings`)，缓存 (`Microsoft.ServiceModel.Channels.Common.CacheSettings`)，元数据 (`Microsoft.ServiceModel.Channels.Common.MetadataSettings`)，和消息传送 (`Microsoft.ServiceModel.Channels.Common.MessagingSettings`)。|  
  
 自定义适配器 WCF 绑定通过公开。 有关详细信息，请参阅 WCF 文档： [http://go.microsoft.com/fwlink/?LinkId=100308](http://go.microsoft.com/fwlink/?LinkId=100308)。  
  
 [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]创建的实现`Microsoft.ServiceModel.Channels.Common.Adapter`， `Microsoft.ServiceModel.Channels.Common.AdapterBinding`， `System.ServiceModel.Configuration.StandardBindingElement`，和`System.ServiceModel.Configuration.StandardBindingCollectionElement`公开适配器绑定到 WCF 配置系统。 [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]还将生成的实现`System.ServiceModel.Configuration.BindingElementExtensionElement`启用`Microsoft.ServiceModel.Channels.Common.Adapter`要在从计算机或应用程序配置文件中的 WCF 自定义绑定中使用。  
  
 有关 StandardBindingElement、 StandardBindingCollectionElement 和 BindingElementExtensionElement 的详细信息，请参阅 WCF 文档。  
  
 有关配置使用编写一个适配器的详细信息[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，请参阅[部署使用 WCF LOB 适配器 SDK 适配器](../../adapters-and-accelerators/wcf-lob-adapter-sdk/deploy-an-adapter-using-the-wcf-lob-adapter-sdk.md)。  
  
## <a name="see-also"></a>另请参阅  
 [了解 LOB 系统与 WCF LOB 适配器 SDK](../../adapters-and-accelerators/wcf-lob-adapter-sdk/understand-the-lob-system-with-the-wcf-lob-adapter-sdk.md)