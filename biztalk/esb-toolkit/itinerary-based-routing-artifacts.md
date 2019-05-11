---
title: 基于路线的路由项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cff38ab7-5a16-42cc-9065-075e9db7acd3
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77c690d4157166db18fb29466d9d64283d892ba0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65261572"
---
# <a name="itinerary-based-routing-artifacts"></a>基于路线的路由项目
基于路线的路由功能的[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包括一组键在多个程序集中定义的项目。 下表列出了按类别以帮助开发人员使用时和扩展与其他 ESB 路线服务实现的基于路线的路由实现这些项目。  
  
## <a name="esb-itinerary-classes"></a>ESB 路线类  
 下表列出了程序集和 ESB 中包含的项目。路线的项目。 包含程序集的名称是**Microsoft.Practices.ESB.Itinerary.dll**。  
  
|关键项目|Description|  
|------------------|-----------------|  
|**MessageHelper**|包含调用的其他项目的所有私有函数。|  
|**IItineraryStep**|从返回的公共类**GetItineraryStep**方法。|  
|**ResolverCollection**|实现与服务关联的所有冲突解决程序的集合。 此类公开由**IItineraryStep**接口，并由填充**GetItineraryStep**方法。|  
|**IMessagingService**|定义由基于消息传送的路线服务实现的接口。|  
|**IMessagingService**|用于创建工厂**IMessagingService**对象基于 Esb.config 中配置的名称。|  
  
## <a name="esb-itinerary-messaging-services"></a>ESB 路线消息传递服务  
 下表列出了中定义的类**Microsoft.Practices.ESB.Itinerary.Services.dll**中的程序集**Microsoft.Practices.ESB.Itinerary.Services**命名空间。  
  
|关键项目|Description|  
|------------------|-----------------|  
|**路由**|ESB 路线消息传递路由的实现： 调用 ESB 调度程序或调度程序反汇编组件会使用 Esb.config 文件。|  
|**转换**|ESB 路线消息转换服务的实现： 调用 ESB 调度程序或调度程序反汇编组件会使用 Esb.config 文件。|  
  
 下表列出了中包含的项目**Microsoft.Practices.ESB.Itinerary.Services.Broker.dll**程序集。  
  
|关键项目|Description|  
|------------------|-----------------|  
|**MessagingBroker**|ESB 路线消息传递的消息上下文中的路由服务的实现： 调用 ESB 调度程序或调度程序反汇编组件会使用 Esb.config 文件。|  
  
 在 BizTalk ESB 工具包配置文件中，Esb.config 还定义这些服务。  
  
## <a name="esb-itinerary-orchestration-services"></a>ESB 路线的业务流程服务  
 下表列出了中包含的项目**Microsoft.Practices.ESB.Agents.dll**程序集。  
  
|关键项目|Description|  
|------------------|-----------------|  
|Delivery.odx|路由业务流程路线服务由服务名称标识的示例**Microsoft.Practices.ESB.Services.Routing**。|  
|Transform.odx|示例转换业务流程路线服务标识的服务名称**Microsoft.Practices.ESB.Services.Transform**。|  
  
## <a name="esb-itinerary-pipeline-components"></a>ESB 路线管道组件  
 下表列出的程序集和项目中包含**Microsoft.Practices.ESB.Itinerary.PipelineComponents.dll**程序集。  
  
|关键项目|Description|  
|------------------|-----------------|  
|**路线**|主路线处理管道组件用于处理和验证传入消息的路线。|  
|**ItineraryCache**|在要求-响应中使用缓存的路线管道组件的发送端口。|  
|**ItinerarySelector**|解析泛型接入中的服务器端路线路线选择器管道组件。|  
  
## <a name="esb-itinerary-pipelines"></a>ESB 路线管道  
 下表列出的程序集和项目中包含**Microsoft.Practices.ESB.Itinerary.Pipelines.dll**程序集。  
  
|关键项目|Description|  
|------------------|-----------------|  
|ItineraryReceive|使用在路线 Web 服务接入点的路线管道。 用作接收管道接收位置，并包含以下管道组件：<br /><br /> ESB 路线，XML 拆装器，ESB 调度程序|  
|ItineraryReceivePassthrough||  
|ItineraryReceiveXml|使用在路线 Web 服务接入点的路线管道。 用作接收管道的接收位置将传入消息路由到多个终结点，并包含以下管道组件：<br /><br /> ESB 路线，ESB 调度程序反汇编程序|  
|ItinerarySend|在关闭 ramp 路线中使用的路线管道。 用作发送管道的发送端口，并包含以下管道组件：<br /><br /> ESB 调度程序，XML 组装器，ESB 路线缓存|  
|ItinerarySendPassthrough|在关闭 ramp 路线中使用的路线管道。 用作发送管道的发送端口，并包含以下管道组件：<br /><br /> ESB 调度程序，ESB 路线缓存|  
|ItinerarySendReceive|在关闭 ramp 路线中使用的路线管道。 用作接收管道的要求响应发送端口，并包含以下管道组件：<br /><br /> ESB 路线缓存中，XML 拆装器，ESB 调度程序|  
|ItineraryForwarderSendReceive|在关闭 ramp 路线中使用的路线管道。 接收管道的发送端口和包含以下管道组件的使用：<br /><br /> ESB 路线缓存中，XML 拆装器，ESB 调度程序，转发器|  
|ItineraryForwarderSendReceiveXml|使用在路线 Web 服务接入点的路线管道。 接收管道的发送端口和包含以下管道组件的使用：<br /><br /> ESB 路线缓存、 ESB 调度程序反汇编、 转发器|  
|ItinerarySelectReceive|使用在路线 Web 服务接入点的路线管道。 用作接收管道接收位置，并包含以下管道组件：<br /><br /> ESB 路线选择器中，XML 拆装器，ESB 调度程序|  
|ItinerarySelectReceivePassthrough|使用在路线 Web 服务接入点的路线管道。 用作接收管道接收位置，并包含以下管道组件：<br /><br /> ESB 路线选择器，ESB 调度程序|  
|ItinerarySelectReceiveXml|使用在路线 Web 服务接入点的路线管道。 用作接收管道接收位置，并包含以下管道组件：<br /><br /> XML 拆装器，ESB 路线选择器，ESB 调度程序|  
|ItinerarySelectSendReceive|在关闭 ramp 路线中使用的路线管道。 接收管道的发送端口和包含以下管道组件的使用：<br /><br /> ESB 路线缓存，ESB 路线选择器中，XML 拆装器，ESB 调度程序|  
  
## <a name="esb-itinerary-schemas"></a>ESB 路线架构  
 下表列出的程序集和项目中包含**Microsoft.Practices.ESB.Itinerary.Schemas.dll**程序集。  
  
|关键项目|Description|  
|------------------|-----------------|  
|Itinerary.xsd|定义的 ESB 路线 SOAP 标头在基于 Windows Communication Foundation WCF 和基于 SOAP Web 服务接入中使用。|  
|ItineraryDescription.xsd|此列名表示路线的引用数据，应该用于将消息提交给基于 WCF 接入。|  
|System-Properties.xsd|定义与 ESB 路线相关 BizTalk 上下文属性。|