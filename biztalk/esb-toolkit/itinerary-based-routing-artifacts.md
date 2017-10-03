---
title: "基于路线的路由项目 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cff38ab7-5a16-42cc-9065-075e9db7acd3
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ca01cc5313c8ca64418f65cec3fdf18fdbc85df
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="itinerary-based-routing-artifacts"></a>路线基于路由的项目
基于路线的路由功能[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包括一套密钥在多个程序集中定义的项目。 下表列出了按类别以帮助开发人员在使用和扩展与其他 ESB 路线服务实现的基于路线的路由实现的这些项目。  
  
## <a name="esb-itinerary-classes"></a>ESB 路线类  
 下表列出的程序集和 ESB 中包含的项目。路线项目。 包含程序集的名称是**Microsoft.Practices.ESB.Itinerary.dll**。  
  
|关键项目|Description|  
|------------------|-----------------|  
|**MessageHelper**|包含调用的其他项目的所有专用函数。|  
|**IItineraryStep**|返回从在公共类**GetItineraryStep**方法。|  
|**ResolverCollection**|实现与服务关联的所有冲突解决程序的集合。 此类公开由**IItineraryStep**接口，并由填充**GetItineraryStep**方法。|  
|**IMessagingService**|定义由基于消息的路线服务实现的接口。|  
|**IMessagingService**|用于创建工厂**IMessagingService**对象基于 Esb.config 中配置的名称。|  
  
## <a name="esb-itinerary-messaging-services"></a>ESB 路线的消息传递服务  
 下表列出了中定义的类**Microsoft.Practices.ESB.Itinerary.Services.dll**中的程序集**Microsoft.Practices.ESB.Itinerary.Services**命名空间。  
  
|关键项目|Description|  
|------------------|-----------------|  
|**路由**|ESB 路线消息传送的实现： 调用 ESB 调度程序或调度程序反汇编组件使用 Esb.config 文件。|  
|**转换**|消息转换服务 ESB 路线的实现： 调用 ESB 调度程序或调度程序反汇编组件使用 Esb.config 文件。|  
  
 下表列出了中包含的项目**Microsoft.Practices.ESB.Itinerary.Services.Broker.dll**程序集。  
  
|关键项目|Description|  
|------------------|-----------------|  
|**MessagingBroker**|ESB 路线消息用于路由消息上下文中的服务的实现： 调用 ESB 调度程序或调度程序反汇编组件使用 Esb.config 文件。|  
  
 在 BizTalk ESB 工具包配置文件中，Esb.config 还定义这些服务。  
  
## <a name="esb-itinerary-orchestration-services"></a>ESB 路线业务流程服务  
 下表列出了中包含的项目**Microsoft.Practices.ESB.Agents.dll**程序集。  
  
|关键项目|Description|  
|------------------|-----------------|  
|Delivery.odx|路由服务由名称标识的业务流程路线服务的示例**Microsoft.Practices.ESB.Services.Routing**。|  
|Transform.odx|示例转换业务流程路线服务的服务名称标识**Microsoft.Practices.ESB.Services.Transform**。|  
  
## <a name="esb-itinerary-pipeline-components"></a>ESB 路线管道组件  
 下表列出的程序集和项目中包含**Microsoft.Practices.ESB.Itinerary.PipelineComponents.dll**程序集。  
  
|关键项目|Description|  
|------------------|-----------------|  
|**路线**|主路线处理管道组件的处理和验证传入消息的路线。|  
|**ItineraryCache**|在请求-响应中使用缓存的路线管道组件发送端口。|  
|**ItinerarySelector**|解析泛型上渐变中的服务器端路线路线的选择器管道组件。|  
  
## <a name="esb-itinerary-pipelines"></a>ESB 路线管道  
 下表列出的程序集和项目中包含**Microsoft.Practices.ESB.Itinerary.Pipelines.dll**程序集。  
  
|关键项目|Description|  
|------------------|-----------------|  
|ItineraryReceive|使用在路线 Web 服务上的负载增加的路线管道。 接收管道接收位置，并包含以下管道组件用作：<br /><br /> ESB 路线，XML 反汇编程序 ESB 调度程序|  
|ItineraryReceivePassthrough||  
|ItineraryReceiveXml|使用在路线 Web 服务上的负载增加的路线管道。 接收管道接收位置以将传入消息路由到多个终结点，并包含以下管道组件用作：<br /><br /> ESB 路线，ESB 调度程序反汇编程序|  
|ItinerarySend|在关闭提升路线中使用的管道路线。 用作发送管道发送端口并且包含以下管道组件：<br /><br /> ESB 调度程序，XML 汇编程序 ESB 路线缓存|  
|ItinerarySendPassthrough|在关闭提升路线中使用的管道路线。 用作发送管道发送端口并且包含以下管道组件：<br /><br /> ESB 调度程序，ESB 路线缓存|  
|ItinerarySendReceive|在关闭提升路线中使用的管道路线。 用作请求-响应接收管道发送端口并且包含以下管道组件：<br /><br /> ESB 路线缓存，XML 反汇编程序 ESB 调度程序|  
|ItineraryForwarderSendReceive|在关闭提升路线中使用的管道路线。 接收管道发送端口，并包含以下管道组件用作：<br /><br /> ESB 路线缓存，XML 反汇编程序 ESB 调度程序，转发器|  
|ItineraryForwarderSendReceiveXml|使用在路线 Web 服务上的负载增加的路线管道。 接收管道发送端口，并包含以下管道组件用作：<br /><br /> ESB 路线缓存、 ESB 调度程序反汇编、 转发器|  
|ItinerarySelectReceive|使用在路线 Web 服务上的负载增加的路线管道。 接收管道接收位置，并包含以下管道组件用作：<br /><br /> ESB 路线选择器，XML 反汇编程序 ESB 调度程序|  
|ItinerarySelectReceivePassthrough|使用在路线 Web 服务上的负载增加的路线管道。 接收管道接收位置，并包含以下管道组件用作：<br /><br /> ESB 路线选择器，ESB 调度程序|  
|ItinerarySelectReceiveXml|使用在路线 Web 服务上的负载增加的路线管道。 接收管道接收位置，并包含以下管道组件用作：<br /><br /> XML 反汇编程序 ESB 路线选择器，ESB 调度程序|  
|ItinerarySelectSendReceive|在关闭提升路线中使用的管道路线。 接收管道发送端口，并包含以下管道组件用作：<br /><br /> ESB 路线缓存，ESB 路线选择器，XML 反汇编程序，ESB 调度程序|  
  
## <a name="esb-itinerary-schemas"></a>ESB 路线架构  
 下表列出的程序集和项目中包含**Microsoft.Practices.ESB.Itinerary.Schemas.dll**程序集。  
  
|关键项目|Description|  
|------------------|-----------------|  
|Itinerary.xsd|定义 ESB 路线 SOAP 使用的标头中基于 Windows Communication Foundation WCF 和基于 SOAP 的 Web 服务上的渐变。|  
|ItineraryDescription.xsd|此 scehma 表示路线引用数据，并应该用于提交到基于 WCF 的渐变上的消息。|  
|系统 Properties.xsd|定义 ESB 路线相关 BizTalk 上下文属性。|