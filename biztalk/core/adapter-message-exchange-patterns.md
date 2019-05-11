---
title: 适配器消息交换模式 |Microsoft Docs
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
ms.openlocfilehash: e15afa09234b046b0cd4388a03e5d4fc92480eaf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361379"
---
# <a name="adapter-message-exchange-patterns"></a>适配器消息交换模式
BizTalk 适配器框架支持许多功能强大的消息传递方案中的一组丰富的适配器可以使用的消息交换模式。  
  
## <a name="one-way-asynchronous"></a>单向 （异步）  
 此处的关键概念是消息按一个方向流动。  
  
 此消息交换模式，在消息流到的一种方法[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过适配器。 消息引擎将消息发布到 MessageBox 数据库。 如果业务流程具有一条消息的该类型的有效订阅，则会将消息路由到该业务流程。  
  
 处理消息之后, 该业务流程将消息发布回 MessageBox 数据库之前将它路由到适配器以传输到特定终结点。  
  
 将消息提交到引擎，预期无响应。 在出站端，当传输消息时，都应无响应。 这通常称为异步消息传送和在许多方面基本的构建基块引擎使用的所有消息传送方案。  
  
## <a name="request-response-style-protocols-sync-on-async"></a>请求-响应样式协议 （同步上异步）  
 请求-响应方案包括接收请求消息、 处理它和发送响应消息。 它也称为同步上异步 （同步-上的异步） 因为基础[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]体系结构是异步的可伸缩性原因。 但是，BizTalk 消息引擎的体系结构可公开基于这些异步交换的同步消息交换模式。 若要执行此操作，引擎处理将请求和响应消息向外扩展体系结构相关联的链接在一起的异步消息交换以将同步接口公开大量的复杂任务。  
  
 例如，一个网页，检查清单可能会使 SOAP 调用对 BizTalk SOAP 接收适配器。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 协调一系列的聚合信息并将其返回一个 SOAP 响应中的 Web 服务。 到客户端，这似乎是同步的 SOAP 调用，但实际上，引擎 knits 一起异步消息交换的数量。  
  
## <a name="solicit-response-style-protocols"></a>要求响应样式协议  
 这种情况下是通过发送要求消息来启动并完成接收的响应消息。 它被称为要求-响应因为发送初始消息请求的响应消息的终结点。 使用此消息交换模式的方案可能涉及到业务流程进行出站 HTTP 调用 （对于响应要求），并等待响应。  
  
## <a name="request-multiresponse"></a>请求 Multiresponse  
 此方案中是类似于请求-响应方案。 但是，在此方案中多个响应可能会返回针对给定的请求。 使用 Api，必须指定一个超时值和超时期间内收到的所有响应都返回到接收适配器。  
  
## <a name="loop-back"></a>环回  
 此方案中是类似于请求-响应方案。 请求消息已发布，像往常一样，但该引擎可确保响应消息将路由回同一适配器实例已发布的请求消息。 由于请求消息发布到 MessageBox 数据库，可确保跟踪基础结构会跟踪请求和响应消息。 这也是一种很好的方法来调用发送管道处理消息立即得到的输出消息发送到适配器进行后续处理。  
  
 此方案的一个示例是需要回执的消息的客户端。 入站的消息发布到 MessageBox 数据库。 此消息并接收返回到在同一批中适配器。 在这种情况下，入站的消息返回到客户端和其他正在处理以正常方式的一个实例复制。 此特定方案还需要编写自定义 XML 拆装器。  
  
## <a name="see-also"></a>请参阅  
 [适配器框架概述](../core/what-is-the-adapter-framework.md)