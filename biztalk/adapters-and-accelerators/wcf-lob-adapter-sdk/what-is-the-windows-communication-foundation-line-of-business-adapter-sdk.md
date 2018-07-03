---
title: 什么是 Windows Communication Foundation 行业适配器 SDK |Microsoft Docs
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
ms.openlocfilehash: 4ada608dbac8071af182c26af02c8f47b43e6cca
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011982"
---
# <a name="what-is-the-windows-communication-foundation-line-of-business-adapter-sdk"></a>Windows Communication Foundation 行业适配器 SDK 是什么
中的组件的功能的概述[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。 本主题还描述关键概念，包括元数据、 连接管理和需要了解，如绑定和通道的术语。

## <a name="features-overview"></a>功能概述
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]旨在满足开发人员构建适配器公开的数据和操作的业务线系统的需求。 提供的功能的一些[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]包括：  
  
- 用于公开传输和数据的协议一致的机制
  
- 公开为 WCF 绑定的适配器的行为
  
- 通过 WCF 通道体系结构的可扩展性
  
- [!INCLUDE[afdevwizardnamelong](../../includes/afdevwizardnamelong-md.md)]
  
- 常见元数据搜索和浏览用户界面使用 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]
  
- [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 使用设计时集成 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]
  
  因为[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]是扩展到 WCF，它还提供以下功能：  
  
- 统一的现有.NET Framework 通信技术
  
- 对跨供应商互操作性，包括可靠性、 安全性和事务的支持
  
- 显式的服务定位
  
## <a name="components-overview"></a>组件概述
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]为适配器开发人员和通过的运行时和设计时组件、.NET 对象模型和支持组件包括一组适配器使用者提供了一致且可重复的体验：  
  

|                                        组件                                        |                                                                                                       Description                                                                                                        |
|-----------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|        [!INCLUDE[afdevwizardnamelong](../../includes/afdevwizardnamelong-md.md)]        |         提供在创建过程中的分步指导[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]项目内[!INCLUDE[btsVStudioNet](../../includes/btsvstudionet-md.md)]。         |
|            [!INCLUDE[afsvcdevwizlong](../../includes/afsvcdevwizlong-md.md)]            |                                                   提供在创建用于承载适配器在 Internet 信息服务 (IIS) 的 Web 项目的分步指南。                                                    |
| [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] 运行时系统 |                          支持[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]通过扩展 WCF 通道体系结构并提供其他运行时服务。                           |
|  [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] 对象模型   |                  类、 类型和支持适配器和等常见任务的元数据规范化、 缓存、 连接管理和池，消息检查接口的集合。                  |
|     [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]     |                               使自定义.NET 应用程序能够使用开发使用的适配器[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。                                |
|    [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]    | 为提供[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]使用开发使用的适配器的功能[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]。 |

## <a name="sdk-fundamentals"></a>SDK 基础知识  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]由运行时，Api 和用于创建公开数据和操作的业务线系统的适配器的设计时工具的集合组成。 适配器管理适配器使用者和业务线系统之间的消息，并且可以包含的元数据、 数据或其他信息。  

### <a name="metadata"></a>元数据  
 与编写的适配器的区分特征之一[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，且其中一个使用 Windows Communication Foundation (WCF) 服务模型对象模型实现的元数据。 元数据描述数据、 操作、 属性和系统的其他动态特征，并由适配器使用者发现、 使用，并与目标系统进行交互。  

 典型 WCF 服务编程生命周期包括 WCF 服务开发人员创建和承载服务。 WCF 服务终结点组成一个地址、 绑定和协定，也称为"A、 B 和 C 的"WCF。  地址是服务的位置，而绑定中指定协议和使用与服务进行通信的传输。  WCF 服务开发人员定义协定使用的 WCF System.ServiceModel 对象模型、 提供形式的 WCF 服务，其实现和承载它使用 ServiceHost。 SvcUtil.exe 和/或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]可用于生成客户端与已发布的服务元数据相对应。 服务启动并运行后，可以针对服务终结点地址的首选的语言和对应的 WCF 服务的详细信息的客户端实现的 app.config 文件中生成 WCF 代理运行设计时工具。  

 WCF LOB 适配器开发人员，但是，实现中提供的元数据对象模型[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]来定义操作和支持的适配器类型。 由于出站适配器是 WCF 自定义绑定，则托管的进程内使用者应用程序中。  该适配器的计算机上，安装后[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]可以浏览和搜索元数据，并因此在 app.config 文件包含适配器的配置详细信息和首选语言生成 WCF 代理使用。 协定创建并由查询提供业务线系统中的实时元数据生成按需由 WCF LOB 适配器。  

 例如，业务线系统可能 adjudicate 不同类型的卫生保健的声明，并且可能包含不断增长的唯一操作、 数据类型、 业务规则和报告系统的用户创建的集合。 如果此信息公开为静态协定时，它具有要修改与新的业务对象添加到系统或只需不提供对新的业务对象的访问。 但是，如果声明宣告系统中的动态业务对象有关的信息可浏览 （和可搜索），新对象的新的验证规则的机构声明或新的报表如公开，并且可以使用。  

### <a name="connection-management"></a>连接管理  
 可以使用业务线系统交换信息之前，适配器必须建立连接。 连接到业务线系统 （提供程序） 链接的适配器 （使用者），并控制连接生命周期，包括打开、 关闭、 中止，并验证连接有效性。 根据业务线系统的要求，连接可能需要一个或多个凭据和连接参数，如服务器名称、 默认目录或端口号。  

 连接生存期管理连接池。 当新的连接请求的适配器，[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]提供了一个现有的连接，如果一个可用; 否则为创建和放置到池中，然后提供的到适配器的新连接。 完成适配器操作后的连接，则将它放置到池中。 关闭和从池中删除空闲时间超出特定阈值的连接。  

### <a name="windows-communication-foundation"></a>Windows Communication Foundation  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]的扩展[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]，用于构建面向服务的应用程序的统一编程模型托管代码。 适配器使用编写[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]呈现为[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]可供任何支持 WCF 的应用程序的绑定。  

## <a name="important-terms"></a>重要术语  

|           |                                                                                                                                                                                                                                                         |
|-----------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  绑定 (binding)  | 定义适配器的进行通信。 通过创建绑定[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]并定义传输、 编码和其他详细信息。 在绑定中可能有一个或多个绑定元素。 |
|  channel  |                                                          绑定元素的实现。 通道一起以创建通道堆栈的绑定堆栈的集合。                                                           |
|  message  |                                                                              独立的几个部分包括消息正文和标头可能包含的数据单元。                                                                              |
| 元数据  |                                                                   描述业务线系统包括操作和可用的数据的特征。                                                                    |
| 操作 |                             函数和方法公开的业务线系统中。 它们对数据进行操作和执行有用的活动，例如 adjudicating 声明、 创建订单，或查询销售数据。                              |
   
## <a name="see-also"></a>请参阅  
 [BizTalk Server 和 WCF LOB 适配器 SDK](../../adapters-and-accelerators/wcf-lob-adapter-sdk/using-biztalk-server-and-the-wcf-lob-adapter-sdk.md)   
   [WCF LOB 适配器 SDK 教程](../../adapters-and-accelerators/wcf-lob-adapter-sdk/tutorials-to-learn-the-wcf-lob-adapter-sdk.md)