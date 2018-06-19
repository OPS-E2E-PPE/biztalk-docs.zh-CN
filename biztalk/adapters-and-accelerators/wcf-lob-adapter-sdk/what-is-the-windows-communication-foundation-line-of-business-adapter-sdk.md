---
title: 什么是 Windows Communication Foundation 行的业务适配器 SDK |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: dc690e8f-fd37-44b5-a277-89952e631ae6
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 084201d9680cb8d17c37c2218ebe7622c4cc4495
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22226485"
---
# <a name="what-is-the-windows-communication-foundation-line-of-business-adapter-sdk"></a>什么是 Windows Communication Foundation 行的业务适配器 SDK
概述的功能和组件中的[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。 本主题还描述关键概念，包括元数据、 连接管理和需要了解，如绑定和通道的术语。

## <a name="features-overview"></a>功能概述
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]旨在满足需求的开发人员构建公开的数据和操作的业务线系统的适配器。 提供的功能的一些[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]包括：  
  
-   用于公开传输和数据的协议的一致机制
  
-   为 WCF 绑定的适配器的公开
  
-   通过 WCF 通道体系结构可扩展性
  
-   [!INCLUDE[afdevwizardnamelong](../../includes/afdevwizardnamelong-md.md)]
  
-   常见的元数据搜索和浏览用户接口使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]使用设计时集成[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]
  
 因为[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是扩展到 WCF，它还提供以下功能：  
  
-   统一的现有的.NET Framework 通信技术
  
-   供应商的跨互操作性，包括可靠性、 安全性和事务支持
  
-   显式服务方向
  
## <a name="components-overview"></a>组件概述
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]适配器开发人员和通过的运行时和设计时组件、.NET 对象模型中，和支持组件包括一组的适配器使用者提供一致且可重复的体验：  
  
|组件|Description|  
|---------------|-----------------|  
|[!INCLUDE[afdevwizardnamelong](../../includes/afdevwizardnamelong-md.md)]|提供了分步指导创建[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]项目内[!INCLUDE[btsVStudioNet](../../includes/btsvstudionet-md.md)]。|  
|[!INCLUDE[afsvcdevwizlong](../../includes/afsvcdevwizlong-md.md)]|提供了在创建用于承载在 Internet 信息服务 (IIS) 的适配器的 Web 项目的分步指导。|  
|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]运行时系统|支持[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]通过扩展 WCF 通道体系结构并提供其他运行时服务。|  
|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]对象模型|类、 类型和支持适配器和等常见任务元数据规范化、 缓存、 连接管理和池时，消息传送检查接口的集合。|  
|[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]|使自定义.NET 应用程序能够使用适配器使用开发[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。|  
|[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]|提供[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]能够使用适配器使用开发[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。|  

## <a name="sdk-fundamentals"></a>SDK 基础知识  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]由运行时，Api 和用于创建公开数据和操作从业务线系统的适配器的设计时工具的集合组成。 适配器管理适配器使用者和业务线系统之间的消息，并且可以包含的元数据、 数据或其他信息。  
  
### <a name="metadata"></a>元数据  
 使用编写一个适配器的可分辨特征之一[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]并且有一个使用 Windows Communication Foundation (WCF) 服务模型对象模型实现元数据。 元数据描述数据、 操作、 属性和系统的其他动态特征和适配器使用者使用发现、 使用，并使用目标系统进行交互。  
  
 一个典型 WCF 服务编程生命周期包括 WCF 服务开发人员创建和承载服务。 WCF 服务终结点由地址、 绑定和一个协定，也称为"A、 B 和 C 的"WCF。  地址是服务的位置，而绑定指定协议和使用与服务进行通信的传输。  WCF 服务开发人员定义了一个使用 WCF System.ServiceModel 对象模型的协定、 提供形式的 WCF 服务，其实现和承载它使用 ServiceHost。 SvcUtil.exe 和/或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]可用来生成客户端与已发布的服务的元数据相对应。 在服务启动并运行之后，可以针对要首选的语言和对应的 WCF 服务的详细信息的客户端实现的 app.config 文件中生成 WCF 代理的服务终结点地址运行设计时工具。  
  
 WCF LOB 适配器开发人员，另一方面，实现中提供的元数据对象模型[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]定义的操作和适配器支持的类型。 由于出站适配器是 WCF 自定义绑定，它是托管的进程在使用者应用程序。  适配器的计算机上，安装后[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]可用来浏览和搜索元数据，并因此在以及一个包含适配器配置详细信息的 app.config 文件的首选语言生成 WCF 代理。 协定创建和生成的查询的实时的元数据中的业务系统提供的按需 WCF LOB 适配器。  
  
 例如，业务线系统可能 adjudicate 不同类型的卫生保健的声明，并且可能包含唯一的操作、 数据类型、 业务规则，以及由系统的用户创建的报告的不断增长集合。 如果此信息公开为静态协定时，它具有要修改为新的业务对象添加到系统，或只需不提供新的业务对象的访问权限。 但是，如果声明裁定系统中的动态业务对象有关的信息可浏览 （和搜索），如制度声明或新的报表的新验证规则的新对象公开，并且可以使用。  
  
### <a name="connection-management"></a>连接管理  
 可以与业务线系统交换信息之前，适配器必须建立连接。 连接链接到业务线系统 （提供程序） 的适配器 （使用者），并控制连接生命周期包括打开、 关闭、 中止，和验证连接有效性。 根据业务线系统的要求，连接可能需要一个或多个凭据和连接参数，如服务器名称、 默认目录或端口号。  
  
 连接生存期由连接池管理。 当新的连接请求的适配器，[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]提供一个现有的连接，如果一个则可用; 否则为新连接创建和放置到池中，并且然后提供给适配器。 适配器与连接完成操作后，它被放置到池中。 关闭和从池中删除空闲超出特定的阈值的连接。  
  
### <a name="windows-communication-foundation"></a>Windows Communication Foundation  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是的扩展[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]，用于构建面向服务的应用程序的统一编程模型托管代码。 适配器使用编写[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]作为[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]可由任何支持 WCF 的应用程序使用的绑定。  
  
## <a name="important-terms"></a>重要术语  

| | |
|---|---|
| 绑定 (binding) | 定义适配器的通信方式。 绑定由[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]并定义传输、 编码和其他详细信息。 绑定中可能有一个或多个绑定元素。 |
|channel | 绑定元素的实现。 渠道，在一起以创建通道堆栈的绑定堆栈的集合。 |
| message  |  独立的几个部分，包括消息正文和标头可能包含的数据单元。|
| 元数据 | 描述的业务线系统包括的操作和可用的数据的特征。|
| 操作 | 函数和由业务线系统公开方法。 它们对数据进行操作，并执行有用的活动，如 adjudicating 声明、 创建订单时，或查询中的销售数据。  |
 
   
## <a name="see-also"></a>另请参阅  
 [BizTalk Server 和 WCF LOB 适配器 SDK](../../adapters-and-accelerators/wcf-lob-adapter-sdk/using-biztalk-server-and-the-wcf-lob-adapter-sdk.md)   
   [WCF LOB 适配器 SDK 教程](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorials-to-learn-the-wcf-lob-adapter-sdk.md)