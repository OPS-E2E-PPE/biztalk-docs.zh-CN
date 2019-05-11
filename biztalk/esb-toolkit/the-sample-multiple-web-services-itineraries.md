---
title: 该示例多个 Web 服务路线 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3f67a4c6-b547-4261-ab3f-db78603ac588
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f08f85b3fb82c105f21a921fb73c35470179a8f6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399671"
---
# <a name="the-sample-multiple-web-services-itineraries"></a>该示例多个 Web 服务路线
下表列出了所有预定义路线附带的文件的多个 Web 服务示例。 这些位于 \Source\Samples\MultipleWebServices\Itineraries 文件夹中。  
  
|File name|Description|  
|---------------|-----------------|  
|OneWayMessagingMultipleServices.xml|此单向路线 NAOrderDoc 消息转换为 CNOrderDoc 消息，然后将它路由到使用关闭负载增加 DynamicResolutionSolicitResp Candian 订单服务。 响应然后转换为使用基于消息的转换服务 CNOrderDoc 消息，然后将它路由再次到加拿大订单服务使用关闭负载增加 DynamicResolutionSolicitResp。 返回的响应路由到使用路由服务在 Source\Samples\DynamicResolution\Test\Filedrop\Out 文件夹中。|  
|TwoWayMessagingMultipleServices.xml|此双向路线 NAOrderDoc 消息转换为 CNOrderDoc 消息，然后将它路由到加拿大订单服务。 它然后，将来自加拿大的订单服务的响应将其转换为 CNOrderDoc 消息，，然后再次将它路由到加拿大订单服务。 然后向调用方返回的结果。 所有转换和路由所需都发生通过消息传递服务。 这两个接出点使用 DynamicResolutionSolicitRespForwarder 发送端口。|  
|TwoWayMessagingOrchestrationMultipleServices.xml|此双向路线使用消息传送服务以转换为 CNOrderDoc 消息，NAOrderDoc 消息，然后将该消息路由到加拿大订单服务使用 DynamicResolutionSolicitRespForwarder 发送端口。 使用基于业务流程的服务实现的转换，转换响应，则传递到自定义 Microsoft.Practices.ESB.Routing.TwoWay 基于业务流程的路线服务作为示例的一部分提供。 此服务将消息发送到关联的冲突解决程序 （在本例中为加拿大订单服务），指定的 Web 服务，然后它接收并从服务返回的响应。 此响应然后发送回调用方。|  
|TwoWayOrchestrationsMultipleServices.xml|此双向路线使用消息传送服务以转换为 CNOrderDoc 消息，NAOrderDoc 消息，然后它使用 Microsoft.Practices.ESB.Routing.TwoWay 业务流程将该消息路由到加拿大订单服务并返回结果。 随后将该消息转换回 CNOrderDoc 消息使用基于业务流程的转换服务;然后，它是发送回加拿大订单服务使用 Microsoft.Practices.ESB.Routing.TwoWay 基于业务流程的路线服务。 然后向调用方返回的结果。|  
|TwoWay-Partial-Selector-Required.xml|通过关闭 ramp DynamicResolutionSolicitResp 加拿大订单服务向客户传达消息的消息服务路由 NAOrderDoc 此两种方式路线用法。 NAOrderDoc 转换为 CNOrderDoc 使用基于消息的转换服务和加拿大的服务调用。 然后返回到调用方返回的响应。|