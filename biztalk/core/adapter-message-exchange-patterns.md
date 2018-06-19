---
title: 适配器消息交换模式 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 54a3fc8f-33d0-4b7e-ad4c-b00912dc3328
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f42368d8687bbed4cbce60243a3b8528364b5fda
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230173"
---
# <a name="adapter-message-exchange-patterns"></a>适配器消息交换模式
在许多功能强大的消息传递方案中，BizTalk 适配器框架支持一组丰富的适配器可以使用的消息交换模式。  
  
## <a name="one-way-asynchronous"></a>单向 （异步）  
 此处的关键概念在于消息按一个方向流动。  
  
 此消息交换模式，在消息流到一种方法[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过适配器。 The Messaging Engine 将消息发布到 MessageBox 数据库。 如果业务流程具有该类型的一条消息的有效订阅，则会将消息路由到该业务流程。  
  
 处理消息之后, 业务流程将发布该消息回 MessageBox 数据库之前将它路由到适配器，将传输到特定终结点。  
  
 当消息提交至引擎时，预期无响应。 在出站端，当传输消息时，都应无响应。 这通常称为异步消息传送和在许多方面基本构建基块由引擎应用于所有消息传递方案。  
  
## <a name="request-response-style-protocols-sync-on-async"></a>请求-响应样式协议 （同步上异步）  
 请求-响应方案由收到的请求消息，处理它，并将发送响应消息。 它也称为同步上异步 （同步上-异步） 因为基础[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]体系结构是异步的可伸缩性原因。 但是，BizTalk 消息引擎的体系结构使公开这些异步交换之上的同步消息交换模式。 若要执行此操作，引擎处理关联跨向外扩展体系结构的请求和响应消息，通过将大量的异步消息交换来公开同步接口链接在一起的复杂任务。  
  
 例如，一个网页，检查清单可能会使 SOAP 调用 BizTalk SOAP 接收适配器。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安排一系列的聚合信息并将其返回一个 SOAP 响应中的 Web 服务。 到客户端，这似乎是同步的 SOAP 调用，但事实上引擎 knits 一起大量的异步消息交换。  
  
## <a name="solicit-response-style-protocols"></a>请求作出响应样式协议  
 这种情况下是由发送的请求消息启动和完成通过接收响应消息。 它被称为请求作出响应因为发送初始消息请求的响应消息的终结点。 使用此消息交换模式的方案可能涉及业务流程进行出站 HTTP 调用 （响应要求），并等待响应。  
  
## <a name="request-multiresponse"></a>请求 Multiresponse  
 这种情况下是请求-响应方案类似。 但是，在此方案中的多个响应可能返回针对给定请求。 使用 Api，一个超时值以指定数据类型，并在超时期限内收到的所有响应都返回到接收适配器。  
  
## <a name="loop-back"></a>循环后  
 这种情况下是请求-响应方案类似。 请求消息将像往常一样，发布但引擎可以确保响应消息返回到同一个适配器实例已发布的请求消息。 因为请求消息发布到 MessageBox 数据库，则可以确保跟踪基础结构请求和响应消息进行跟踪。 这也是一种好方法，以调用发送管道处理消息，然后立即返回输出消息发送到以进行后续处理的适配器。  
  
 此方案的一个示例是需要回执的消息的客户端。 入站的消息发布到 MessageBox 数据库。 此消息和接收返回到同一个批处理中的适配器。 在这种情况下，与返回到客户端和其他正在处理以正常方式的一个实例复制入站的消息。 此特定方案还需要自定义的 XML 反汇编程序要写入。  
  
## <a name="see-also"></a>另请参阅  
 [什么是适配器 Framework？](../core/what-is-the-adapter-framework.md)