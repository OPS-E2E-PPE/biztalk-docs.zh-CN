---
title: 示例路线方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6d438580-2b24-493c-a7d9-27632a75459c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 721a01015fe58b60642894b54423d7fa1309330a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399681"
---
# <a name="the-sample-itinerary-scenarios"></a>示例路线方案
下表列出了路线接入点示例中包含的所有预定义的路线文件。 这些位于 \Source\Samples\Itinerary\Itineraries 文件夹中。  
  
|File name|Description|  
|---------------|-----------------|  
|Disassembler_OneWay-MessageTransform-MessageRouting-MessgeSendPort.xml|此路线演示预定义的消息流，提交到路线接入点，指示 Microsoft BizTalk 执行针对提交的消息映射，然后将转换后的消息路由到 n，通过自定义动态的位置的数目发送端口。 冲突解决程序与服务关联数确定路由的数。 所有转换和路由发生在 BizTalk 消息传送层上，使用 ESB 调度程序管道组件支持的可选路由消息服务。 与在路线服务相关联的解析程序确定的路由的位置。 运行此路线将生成以下消息：|  
||在文件夹 \Source\Samples\DynamicResolution\Test\Filedrop\Out 2 条消息|  
||FTP 文件夹中的 1 条消息：FTP://localhost/out/%MessageID%.xml|  
||MQSeries 队列中的 1 条消息：MQS://localhost/ESB.DEP.Sample.QueueManager/TEST.OUT/%MessageID.xml|  
|Disassembler_OneWay-MessageTransform-MessgeSendPort.xml|此路线演示，当提交到路线接入点，指示 BizTalk 执行针对已提交的消息映射并路由到 n 的位置通过自定义动态数目转换后的消息发送端口的预定义的消息流。 冲突解决程序与服务关联数确定路由的数。 所有转换和路由发生在 BizTalk 消息传送层。 与在路线服务相关联的解析程序确定的路由的位置。 运行此路线将生成以下消息：|  
||在文件夹 \Source\Samples\DynamicResolution\Test\Filedrop\Out 2 条消息|  
||FTP 文件夹中的 1 条消息：FTP://localhost/out/%MessageID%.xml|  
||MQSeries 队列中的 1 条消息：MQS://localhost/ESB.DEP.Sample.QueueManager/TEST.OUT/%MessageID.xml|  
|OneWay-MessageTransform-MessageRouting-MessgeSendPort.xml|此路线演示，当提交到路线接入点，指示 BizTalk 执行针对已提交的消息映射并路由到一个位置通过自定义动态转换后的消息发送端口的预定义的消息流。 所有转换和路由发生在 BizTalk 消息传送层上，使用 ESB 调度程序管道组件支持的可选路由消息服务。 运行此路线 \Source\Samples\DynamicResolution\Test\Filedrop\Out 文件夹中生成一条消息。|  
|OneWay-MessageTransform-MessgeSendPort.xml|此路线演示，当提交到路线接入点，指示 BizTalk 执行针对已提交的消息映射并路由到一个位置通过自定义动态转换后的消息发送端口的预定义的消息流。 所有转换和路由发生在 BizTalk 消息传送层。 运行此路线 \Source\Samples\DynamicResolution\Test\Filedrop\Out 文件夹中生成一条消息。|  
|OneWay-MessgeSendPort.xml|此路线演示，当提交到路线接入点，指示 BizTalk 将路由到一个位置通过自定义动态消息发送端口的预定义的消息流。 所有路由发生在 BizTalk 消息传送层。 运行此路线 \Source\Samples\DynamicResolution\Test\Filedrop\Out 文件夹中生成一条消息。|  
|OneWay-OrchTransform-OrchRoutingGroup-MessgeSendPort.xml|此路线演示示例中的预定义的消息流，提交到路线接入点，指示要执行对已提交的消息使用自定义业务流程服务映射的 BizTalk。 然后，第二个自定义业务流程服务处理输出，并将四个消息路由到三个位置。 与此服务关联的解析程序确定以下路由位置：|  
||在文件夹 \Source\Samples\DynamicResolution\Test\Filedrop\Out 2 条消息|  
||FTP 文件夹中的 1 条消息：FTP://localhost/out/%MessageID%.xml|  
||MQSeries 队列中的 1 条消息：MQS://localhost/ESB.DEP.Sample.QueueManager/TEST.OUT/%MessageID.xml|  
||最后，路线通过自定义的动态发送端口将路由到一个单独位置 （\Source\Samples\DynamicResolution\Test\Filedrop\Out 文件夹） 的原始消息。 所有转换和路由发生通过 BizTalk 消息传送和业务流程服务的组合。 运行此路线的示例将生成五个消息。|  
|TwoWay-MessageTransform-MessageRouting-MessageTwoWaySendPort.xml|此路线演示预定义双向 （请求/响应） 消息流，提交到路线接入点，指示 BizTalk 执行针对已提交的消息映射并转换后的消息路由到通过 Web 服务自定义动态双向发送端口。 此示例使用 ESB 调度程序管道组件支持的可选路由消息服务。 所有转换和路由发生在 BizTalk 消息传送层。 运行此路线示例生成单个响应消息，路线将路由到原始调用方，在此情况下路线测试客户端。|  
|TwoWay-MessageTransform-MessageRouting-MessageTwoWaySendPort-MessageTransform.xml|此路线演示预定义双向 （请求/响应） 消息流，提交到路线接入点，指示 BizTalk 执行针对已提交的消息映射并转换后的消息路由到通过 Web 服务自定义动态双向发送端口。 当响应返回从 Web 服务时，路线指示 BizTalk 执行对响应消息的映射。 此示例使用 ESB 调度程序管道组件支持的可选路由消息服务。 所有转换和路由发生在 BizTalk 消息传送层。 运行此路线示例生成单个响应消息，路线将路由到原始调用方，在此情况下路线测试客户端。|  
|TwoWay-MessageTransform-MessageTwoWaySendPort.xml|此路线演示预定义双向 （请求/响应） 消息流，提交到路线接入点，指示 BizTalk 执行针对已提交的消息映射并转换后的消息路由到通过 Web 服务自定义动态双向发送端口。 所有转换和路由发生在 BizTalk 消息传送层。 运行此路线示例生成单个响应消息，路线将路由到原始调用方，在此情况下路线测试客户端。|  
|TwoWay-MessageTransform-MessageTwoWaySendPort-MessageTransform.xml|此路线演示预定义双向 （请求/响应） 消息流，提交到路线接入点，指示 BizTalk 执行针对已提交的消息映射并转换后的消息路由到通过 Web 服务自定义动态双向发送端口。 当响应返回从 Web 服务时，路线指示 BizTalk 执行对响应消息的映射。 所有转换和路由发生在 BizTalk 消息传送层。 运行此路线示例生成单个响应消息，路线将路由到原始调用方 （在此情况下，路线测试客户端）。|  
|TwoWay-MessageTransform-OrchRoutingGroup-OrchTwoWayCustom.xml|此路线演示预定义双向 （请求/响应） 消息流，提交到路线接入点，指示要执行对已提交的消息使用消息传送服务映射的 BizTalk。 路线然后将输出传递给对其进行处理的自定义业务流程服务。 与服务关联的解析程序确定以下四个路由位置：|  
||在文件夹 \Source\Samples\DynamicResolution\Test\Filedrop\Out 2 条消息|  
||FTP 文件夹中的 1 条消息：FTP://localhost/out/%MessageID%.xml|  
||MQSeries 队列中的 1 条消息：MQS://localhost/ESB.DEP.Sample.QueueManager/TEST.OUT/%MessageID.xml|  
||最后，路线将原始消息传递到另一个将响应消息路由回原始调用方 （在此情况下，路线测试客户端） 的自定义双向直接绑定业务流程服务。 所有转换和路由是通过 BizTalk 消息传送和业务流程服务的组合。|  
|TwoWay-OrchTransform-OrchRoutingGroup-OrchTwoWayCustom.xml|此路线演示预定义双向 （请求/响应） 消息流，提交到路线接入点，指示要执行对已提交的消息使用自定义业务流程服务映射的 BizTalk。 路线然后将输出传递给对其进行处理的自定义业务流程服务。 与服务关联的解析程序确定以下四个路由位置：|  
||在文件夹 \Source\Samples\DynamicResolution\Test\Filedrop\Out 2 条消息|  
||FTP 文件夹中的 1 条消息：FTP://localhost/out/%MessageID%.xml|  
||MQSeries 队列中的 1 条消息：MQS://localhost/ESB.DEP.Sample.QueueManager/TEST.OUT/%MessageID.xml|  
||最后，路线将原始消息路由到另一个将响应消息路由回原始调用方 （在此情况下，路线测试客户端） 的自定义双向直接绑定业务流程服务。 所有转换和路由是通过 BizTalk 消息传送和业务流程服务的组合。|  
|TwoWay TwoWayCustom （直接绑定）.xml|此路线演示预定义双向 （请求/响应） 消息流，提交到路线接入点，指示要执行的自定义双向直接绑定业务流程服务的 BizTalk。 此服务将响应消息路由回原始调用方，在此情况下路线测试客户端。|