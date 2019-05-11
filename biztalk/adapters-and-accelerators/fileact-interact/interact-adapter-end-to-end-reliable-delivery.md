---
title: 交互适配器端到端可靠传递 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ac7c22f2-ee4a-4e9b-af40-da7eb58daf51
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b2d7ccacde04243c2635bbe5adcafad3f2b9987
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366702"
---
# <a name="interact-adapter-end-to-end-reliable-delivery"></a>交互适配器端到端可靠传递
在向收件人发送的消息或文件，我们建议确保传递的消息或文件，和的业务事务包含在这些执行没有更多的时间比预期。  
  
 当这两个实体相互通信可以使用持久存储 （例如，持久面向消息的中间件和使用它的接口应用程序提供的） 时，很容易地实现可靠的传递，如果进行通信的方式标准化感知到的消息的状态。  
  
 下图显示了 E2EControl 结构的示例。  
  
 ![结束&#45;到&#45;结束控制](../../adapters-and-accelerators/fileact-interact/media/63e39b43-118e-4572-9d75-21770253a1ee.gif "63e39b43-118e-4572-9d75-21770253a1ee")  
  
 在图中所示的示例中的元素是 SwInt:Request 内发送和传递到接收应用程序 SwInt:RequestHandle 内保持不变。 行 02 允许向请求分配的唯一标识符。 在同一请求的每个后续重新传输中重复此唯一标识符。  
  
 构造此标识符的方式由实施者，但通常基于系统调用，如 uuidgen()，也可能是计算 sha-1 上要发送的请求的结果 （使用带前缀的 Sw:MsgId，然后替换它的 base64 编码的 SHA 1 s字符串）。 主要要求是全局唯一 （具有非常高的概率）。  
  
 Sw:CreationTime 是创建的原始请求的时间。 它是一个可选参数，但它可用于限制为此消息的上一个通信尝试最终搜索。  
  
 元素 Sw:PDIndication 是存在以指明这是第二个或更多尝试传输消息。 接收应用程序可以识别的 E2EControl 然后可以使用 Sw:MsgId 是否收到的消息或不返回查找。 可选 Sw:EmissionList 包含以前的尝试的时间。 这一次是本地时间 （以世界时） 发件人的如使用 Sw:GetDateTime 函数时由发件人获得。 再次，这可能会是用于限制搜索。  
  
## <a name="see-also"></a>请参阅  
 [InterAct 适配器体系结构](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)   
 [InterAct 适配器组件](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md)   
 [Business Exchange 的 interAct 适配器消息](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md)   
 [InterAct 适配器客户端应用程序](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md)   
 [InterAct 适配器服务器应用程序](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md)   
 [InterAct 适配器存储和转发](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md)   
 [InterAct 适配器安全体系结构](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md)   
 [InterAct 适配器状态监视](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md)   
 [InterAct 适配器不可否认性](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)