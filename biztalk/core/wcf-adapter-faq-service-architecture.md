---
title: "WCF 适配器常见问题： 服务体系结构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8bad0063-ccff-41f4-b4e0-a02b49403c2d
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b73b70474fd30e3a571f59558d6dc439cb981f64
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="wcf-adapter-faq-service-architecture"></a>WCF 适配器常见问题： 服务体系结构
## <a name="what-is-the-difference-between-a-wcf-custom-behavior-and-a-biztalk-pipeline-component"></a>WCF 自定义行为和 BizTalk 管道组件之间的区别是什么？  
 在初始检查，WCF 自定义行为非常类似的传统 BizTalk 管道。 两者都利用消息侦听的基本概念来中断流向目标的消息流、在流中执行一些自定义消息处理，然后将流转发至其目标。 此侦听可以发生在 BizTalk Server 处理消息之前（绑定到接收位置）或之后（绑定到发送端口）。 两种方法中侦听的发生方式在实现上和在侦听点中都有所不同。 下面是一些差异：  
  
-   通过业务流程，可以使用管道。 WCF 行为则仅限于由 WCF 适配器从 BizTalk Server 中调用。  
  
-   管道是一种特定于 BizTalk Server 的旧技术。 BizTalk Server 中，按以及其他纯 WCF 方案中，可以使用 WCF 行为。  
  
-   管道实时内集管道阶段，例如解码、 验证等。WCF 行为可以插入到消息流在任何 （稍后介绍） 其四个截获入口点。  
  
-   管道是只是它们的功能的运行时。 虽然 WCF 行为也是这样，但 WCF 行为还可以对在配置过程中从 BizTalk Server 管理控制台设置的值强制实施关系约束或数据约束。  
  
-   BizTalk 消息的管道可运行，而 WCF 行为在 WCF 消息上运行。 这意味着管道可以执行如升级 BizTalk 上下文属性等操作，而 WCF 行为则可以访问 WCF 消息属性。  
  
-   没有在 WCF 或 WCF 适配器的多部分消息的模型。 但由于管道组件可以通过任何所需的方式来操作 BizTalk 消息，因此，这种组件可以在必要时处理多部分消息。  
  
## <a name="for-the-receive-locations-or-send-ports-using-the-wcf-basichttp-and-wcf-wshttp-adapters-what-type-of-encoding-should-i-select"></a>对于使用 WCF-BasicHttp 和 WCF-WSHttp 适配器的接收位置或发送端口，应该选择何种类型的编码？  
 对于其中每个适配器没有基于 HTTP 的消息与文本编码。 消息编码指定用于消息的 SOAP 编码器，可以是“MTOM”（消息传输组织机制）或“文本”。 如果选择文本，则文本编码必须选择。 此选项有 unicodeFFF (big-endian)、 utf-16 （16 位编码） 和 utf-8 （8 位编码）。  
  
 MTOM 是二进制数据的建议且最高效传输机制。 但该机制要求服务能够处理 MTOM 数据，这使得此选项的可移植性低远低于纯“文本”。 如果用于传输标准的非二进制数据，则 MTOM 的实际效率低于“文本”选项。 “文本”是普遍接受的选项，它允许更高的跨平台互操作性，但如果传输的数据包含非文本内容，则该选项是两个选项中效率较低的一个。 如果使用 WCF 服务约定，则在选择绑定编码选项时，这是一个重要的考虑因素。 了解 WCF 操作将传输和处理何种数据，有助于正确地选择何种消息编码。