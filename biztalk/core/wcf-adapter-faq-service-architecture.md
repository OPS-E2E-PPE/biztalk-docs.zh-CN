---
title: WCF 适配器常见问题解答：服务体系结构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8bad0063-ccff-41f4-b4e0-a02b49403c2d
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8cf46334fe3c40b222552c97115bc7758134c7a4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393594"
---
# <a name="wcf-adapter-faq-service-architecture"></a>WCF 适配器常见问题解答：服务体系结构
## <a name="what-is-the-difference-between-a-wcf-custom-behavior-and-a-biztalk-pipeline-component"></a>WCF 自定义行为和 BizTalk 管道组件之间的区别是什么？  
 在初始检查，WCF 自定义行为是非常类似于传统的 BizTalk 管道。 两者都利用消息侦听中断到其目标的消息流、 执行某些自定义消息，处理的基本概念，并将其转发到其目标。 此侦听可以发生之前 （绑定到接收位置） 或之后 （绑定到发送端口） 处理消息通过 BizTalk Server。 如何在两个方法中进行此侦听不同在都实现中的拦截的点。 下面是一些差异：  
  
-   管道可以使用由业务流程。 WCF 行为仅限于由 WCF 适配器从 BizTalk Server 中被调用。  
  
-   管道是特定于 BizTalk Server 比较老的技术。 由 BizTalk Server 以及其他纯 WCF 方案中，可以使用 WCF 行为。  
  
-   管道存在于设置管道阶段，如解码、 验证等。WCF 行为可以插入到在任何其四个侦听入口点 （稍后介绍） 的消息流。  
  
-   管道是纯粹它们的功能的运行时。 虽然 WCF 行为也是这样，它们还可以强制实施关系，或在从 BizTalk Server 管理控制台中的配置过程中设置数据约束值。  
  
-   管道可以对 BizTalk 消息，而 WCF 行为在 WCF 消息上运行。 这意味着管道可以某些操作，如升级 BizTalk 上下文属性，而 WCF 行为则可以访问 WCF 消息属性。  
  
-   没有在 WCF 或 WCF 适配器的多部分消息的模型。 但是，因为管道组件可以处理需要的任何方式在 BizTalk 消息，它可以处理多部分消息，如有必要。  
  
## <a name="for-the-receive-locations-or-send-ports-using-the-wcf-basichttp-and-wcf-wshttp-adapters-what-type-of-encoding-should-i-select"></a>对于接收位置或使用 Wcf-basichttp 和 Wcf-wshttp 适配器的发送端口，哪种类型的编码应该我选择？  
 对于每个这些适配器没有基于 HTTP 的消息和文本编码。 消息编码指定用于消息，即 MTOM （消息传输组织机制） 或文本的 SOAP 编码器。 如果选择文本，则文本编码必须选择。 此选项是 unicodeFFF (大 endian)、 （16 位编码），utf-16 和 utf-8 （8 位编码）。  
  
 MTOM 是二进制数据的建议且最有效的传输机制。 但是，需要该服务能够处理 MTOM 数据，这使得此选项比纯文本的可移植性更低。 如果使用标准的非二进制数据传输，MTOM 实际效率可能比使用文本选项。 文本普遍接受，并允许更多跨平台互操作性，但它是两个效率较低的选择，如果要传输的数据包含非文本内容。 使用 WCF 服务约定时选择绑定编码选项时，这是一个重要因素。 了解 WCF 操作将传输的数据和进程影响的消息编码正确的选择。