---
title: "示例路线方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6d438580-2b24-493c-a7d9-27632a75459c
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9359a6fb3d0ce4d4f0d8fbd787c0d6a30f0f499
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-sample-itinerary-scenarios"></a>示例路线方案
下表列出路线入口示例中包含的所有预定义的路线文件。 这些位于 \Source\Samples\Itinerary\Itineraries 文件夹中。  
  
|文件名|Description|  
|---------------|-----------------|  
|Disassembler_OneWay MessageTransform MessageRouting MessgeSendPort.xml|此路线演示预定义的消息流，在提交到路线上的负载增加时, 指示 Microsoft BizTalk 执行对提交消息映射，然后将已转换的消息路由到通过自定义动态的位置的 n 数发送端口。 与服务关联的解析程序的数目确定路由的数。 所有转换和路由发生在 BizTalk 消息传送层上，使用受 ESB 调度程序管道组件的可选路由消息服务。 与服务在服务内路线冲突解决程序确定的路由的位置。 运行此路线将生成以下消息：|  
||在文件夹 \Source\Samples\DynamicResolution\Test\Filedrop\Out 的 2 条消息|  
||FTP 文件夹中的 1 条消息： FTP://localhost/out/%MessageID%.xml|  
||MQSeries 队列中的 1 条消息： MQS://localhost/ESB。DEP。Sample.QueueManager/TEST。OUT/%MessageID.xml|  
|Disassembler_OneWay MessageTransform MessgeSendPort.xml|此路线演示，当提交到路线上的负载增加，指示 BizTalk 执行针对已提交的邮件的映射，然后路由到通过自定义动态的位置的 n 数已转换的消息发送端口的预定义的消息流。 与服务关联的解析程序的数目确定路由的数。 所有转换和路由发生在 BizTalk 消息传送层。 与服务在服务内路线冲突解决程序确定的路由的位置。 运行此路线将生成以下消息：|  
||在文件夹 \Source\Samples\DynamicResolution\Test\Filedrop\Out 的 2 条消息|  
||FTP 文件夹中的 1 条消息： FTP://localhost/out/%MessageID%.xml|  
||MQSeries 队列中的 1 条消息： MQS://localhost/ESB。DEP。Sample.QueueManager/TEST。OUT/%MessageID.xml|  
|OneWay MessageTransform MessageRouting MessgeSendPort.xml|此路线演示，当提交到路线上的负载增加，指示 BizTalk 执行针对已提交的邮件的映射，然后路由到一个位置通过自定义动态已转换的消息发送端口的预定义的消息流。 所有转换和路由发生在 BizTalk 消息传送层上，使用受 ESB 调度程序管道组件的可选路由消息服务。 运行此路线 \Source\Samples\DynamicResolution\Test\Filedrop\Out 文件夹中生成一条消息。|  
|OneWay MessageTransform MessgeSendPort.xml|此路线演示，当提交到路线上的负载增加，指示 BizTalk 执行针对已提交的邮件的映射，然后路由到一个位置通过自定义动态已转换的消息发送端口的预定义的消息流。 所有转换和路由发生在 BizTalk 消息传送层。 运行此路线 \Source\Samples\DynamicResolution\Test\Filedrop\Out 文件夹中生成一条消息。|  
|OneWay MessgeSendPort.xml|此路线演示，当提交到路线上的负载增加，指示 BizTalk 将路由到一个位置通过自定义动态消息发送端口的预定义的消息流。 在 BizTalk 消息传送层所有路由时发生。 运行此路线 \Source\Samples\DynamicResolution\Test\Filedrop\Out 文件夹中生成一条消息。|  
|OneWay OrchTransform OrchRoutingGroup MessgeSendPort.xml|此路线演示一种预定义的消息流，在提交到路线上的负载增加时, 指示 BizTalk 执行针对已提交的邮件使用自定义业务流程服务的映射。 然后，第二个自定义业务流程服务处理输出，并将四个消息路由到三个位置。 与此服务关联的冲突解决程序确定以下路由位置：|  
||在文件夹 \Source\Samples\DynamicResolution\Test\Filedrop\Out 的 2 条消息|  
||FTP 文件夹中的 1 条消息： FTP://localhost/out/%MessageID%.xml|  
||MQSeries 队列中的 1 条消息： MQS://localhost/ESB。DEP。Sample.QueueManager/TEST。OUT/%MessageID.xml|  
||最后，路线通过自定义的动态发送端口将路由到一个位置 （\Source\Samples\DynamicResolution\Test\Filedrop\Out 文件夹） 的原始消息。 所有转换和路由发生通过 BizTalk 消息传送和业务流程服务的组合。 运行此路线的示例将生成五条消息。|  
|双向 MessageTransform MessageRouting MessageTwoWaySendPort.xml|此路线演示预定义双向 （请求/响应） 消息流，在提交到路线上的负载增加时, 指示 BizTalk 执行针对已提交的邮件的映射，然后将已转换的消息路由到 Web 服务通过自定义的动态双向发送端口。 此示例使用 ESB 调度程序管道组件支持的可选路由消息服务。 所有转换和路由发生在 BizTalk 消息传送层。 运行此路线示例生成单个响应消息，路线将路由到原始调用方，在此情况下的路线测试客户端。|  
|双向-MessageTransform-MessageRouting-MessageTwoWaySendPort-MessageTransform.xml|此路线演示预定义双向 （请求/响应） 消息流，在提交到路线上的负载增加时, 指示 BizTalk 执行针对已提交的邮件的映射，然后将已转换的消息路由到 Web 服务通过自定义的动态双向发送端口。 当响应返回从 Web 服务时，路线指示 BizTalk 执行对响应消息映射。 此示例使用 ESB 调度程序管道组件支持的可选路由消息服务。 所有转换和路由发生在 BizTalk 消息传送层。 运行此路线示例生成单个响应消息，路线将路由到原始调用方，在此情况下的路线测试客户端。|  
|双向 MessageTransform MessageTwoWaySendPort.xml|此路线演示预定义双向 （请求/响应） 消息流，在提交到路线上的负载增加时, 指示 BizTalk 执行针对已提交的邮件的映射，然后将已转换的消息路由到 Web 服务通过自定义的动态双向发送端口。 所有转换和路由发生在 BizTalk 消息传送层。 运行此路线示例生成单个响应消息，路线将路由到原始调用方，在此情况下的路线测试客户端。|  
|双向 MessageTransform MessageTwoWaySendPort MessageTransform.xml|此路线演示预定义双向 （请求/响应） 消息流，在提交到路线上的负载增加时, 指示 BizTalk 执行针对已提交的邮件的映射，然后将已转换的消息路由到 Web 服务通过自定义的动态双向发送端口。 当响应返回从 Web 服务时，路线指示 BizTalk 执行对响应消息映射。 所有转换和路由发生在 BizTalk 消息传送层。 运行此路线示例生成路线将路由到原始调用方 （在此情况下，路线测试客户端） 的单个响应消息。|  
|双向 MessageTransform OrchRoutingGroup OrchTwoWayCustom.xml|此路线演示预定义双向 （请求/响应） 消息流，在提交到路线上的负载增加时, 指示 BizTalk 执行针对已提交的邮件使用消息传递服务的映射。 路线然后将输出传递给处理它的自定义业务流程服务。 与服务关联的冲突解决程序确定以下四个路由位置：|  
||在文件夹 \Source\Samples\DynamicResolution\Test\Filedrop\Out 的 2 条消息|  
||FTP 文件夹中的 1 条消息： FTP://localhost/out/%MessageID%.xml|  
||MQSeries 队列中的 1 条消息： MQS://localhost/ESB。DEP。Sample.QueueManager/TEST。OUT/%MessageID.xml|  
||最后，路线将原始消息传递到另一个路由回原始调用方 （在此情况下，路线测试客户端） 的响应消息的自定义双向直接绑定业务流程服务。 所有转换和路由发生在通过 BizTalk 消息传送和业务流程服务的组合。|  
|双向 OrchTransform OrchRoutingGroup OrchTwoWayCustom.xml|此路线演示预定义双向 （请求/响应） 消息流，在提交到路线上的负载增加时, 指示 BizTalk 执行针对已提交的邮件使用自定义业务流程服务的映射。 路线然后将输出传递给处理它的自定义业务流程服务。 与服务关联的冲突解决程序确定以下四个路由位置：|  
||在文件夹 \Source\Samples\DynamicResolution\Test\Filedrop\Out 的 2 条消息|  
||FTP 文件夹中的 1 条消息： FTP://localhost/out/%MessageID%.xml|  
||MQSeries 队列中的 1 条消息： MQS://localhost/ESB。DEP。Sample.QueueManager/TEST。OUT/%MessageID.xml|  
||最后，路线将原始消息路由到另一个路由回原始调用方 （在此情况下，路线测试客户端） 的响应消息的自定义双向直接绑定业务流程服务。 所有转换和路由发生在通过 BizTalk 消息传送和业务流程服务的组合。|  
|双向 TwoWayCustom （直接绑定）.xml|此路线演示预定义双向 （请求/响应） 消息流，在提交到路线上的负载增加时, 指示 BizTalk 来执行自定义双向直接绑定业务流程服务。 此服务将响应消息路由回原始调用方，在此情况下的路线测试客户端。|