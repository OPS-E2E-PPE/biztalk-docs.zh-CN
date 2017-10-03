---
title: "示例多个 Web 服务路线 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f67a4c6-b547-4261-ab3f-db78603ac588
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df8beeda266ae29eb4bb3e7c2a373c9ac6fc2b2c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-sample-multiple-web-services-itineraries"></a>示例多个 Web 服务路线
下表列出所有预定义路线包含的文件使用多个 Web 服务的示例。 这些位于 \Source\Samples\MultipleWebServices\Itineraries 文件夹中。  
  
|文件名|Description|  
|---------------|-----------------|  
|OneWayMessagingMultipleServices.xml|此单向路线转换到 CNOrderDoc 消息 NAOrderDoc 消息，然后将它路由到使用关闭负载增加 DynamicResolutionSolicitResp Candian 顺序服务。 响应然后转换为使用基于消息的转换服务 CNOrderDoc 消息，然后将送交再次使用关闭负载增加 DynamicResolutionSolicitResp 加拿大顺序服务。 返回的响应路由到使用路由服务的 Source\Samples\DynamicResolution\Test\Filedrop\Out 文件夹中。|  
|TwoWayMessagingMultipleServices.xml|此双向路线转换到 CNOrderDoc 消息 NAOrderDoc 消息，然后将它路由到加拿大的订单服务。 它然后采用来自加拿大顺序服务的响应，将其转换到 CNOrderDoc 邮件中，并随后再次将它路由到加拿大的订单服务。 随后会将结果返回给调用方。 所有转换和路由采用都放置通过消息传递服务。 关闭渐变使用 DynamicResolutionSolicitRespForwarder 发送端口。|  
|TwoWayMessagingOrchestrationMultipleServices.xml|此双向路线使用消息传递服务来转换到 CNOrderDoc 邮件中，一 NAOrderDoc 消息，然后将该消息路由到使用 DynamicResolutionSolicitRespForwarder 发送端口的加拿大顺序服务。 使用基于业务流程的服务实现的转换，转换响应，然后它将传递到自定义 Microsoft.Practices.ESB.Routing.TwoWay 基于业务流程的路线服务作为示例的一部分提供。 此服务将消息发送到由关联的解析程序 （在这种情况下，加拿大的订单服务），指定的 Web 服务，然后它接收并从服务返回的响应。 此响应然后发送回调用方。|  
|TwoWayOrchestrationsMultipleServices.xml|此双向路线使用消息传递服务将为 CNOrderDoc 的消息，NAOrderDoc 消息转换，然后它使用 Microsoft.Practices.ESB.Routing.TwoWay 业务流程将该消息路由到加拿大的订单服务并返回结果。 随后将消息转换回 CNOrderDoc 消息使用基于业务流程的转换服务;之后，它是发送回加拿大使用 Microsoft.Practices.ESB.Routing.TwoWay 基于业务流程的路线服务的顺序服务。 随后会将结果返回给调用方。|  
|双向部分选择器 Required.xml|向通过关闭提升 DynamicResolutionSolicitResp 加拿大的订单服务发送消息消息服务路由 NAOrderDoc 此两种方式路线用法。 NAOrderDoc 将转换为 CNOrderDoc 使用基于消息的转换服务和加拿大的服务调用。 返回到调用方，然后返回响应。|