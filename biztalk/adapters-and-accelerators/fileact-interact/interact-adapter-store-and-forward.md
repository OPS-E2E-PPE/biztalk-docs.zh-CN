---
title: InterAct 适配器存储和转发 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d596780a-085d-48db-be44-a3ae58f591d0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f3ce047de1c926e6e144b1351954774c1d3edb5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022587"
---
# <a name="interact-adapter-store-and-forward"></a>InterAct 适配器存储和转发
在存储和转发 (SnF) 模式下，消息在发送时，传递到的队列和目标队列中的检索。 当使用 SnF，响应来自 SWIFTNet SnF 本身并不包含从响应方的任何反馈。  
  
 消息和文件可使用一条消息路由到的服务器进程时不使用 SnF 灵活路由到队列。 此定义位于 MRR （内部 SWIFTNet)。 它是决定哪个队列在消息或文件将处于由发件人发送后接收方。 将消息或文件放在队列中，可以标记 （在 RequestControl) SnF 传递模式的消息。  
  
 从队列检索消息可能在两个不同的模式下，具体取决于应用程序设计器所做的选择。 这些模式被调用推送和拉取。  
  
 使用推送模式时，计划时传递语音消息位于 SWIFTNet SnF。 该消息然后"推送"从 SWIFTNet SnF 且会收到 SWIFTNet 链接上的应用程序服务器。 服务器应用程序必须确保该消息是 safestored 确认响应之前。 此确认指示 SWIFTNet SnF 如何接收消息。 确认不包含任何其他更多"业务"逻辑。  
  
## <a name="queues-in-swiftnet"></a>SWIFTNet 中的队列  
 队列包含消息和发送的发送方要传递到指定的接收方的文件。 队列还包含生成的 SWIFTNet SnF 的发送通知。  
  
 队列定义和配置的接收方的组织。 实际创建队列，可以在用户请求 SWIFT。 发件人不知道在其中最终会将消息队列有关的任何信息。 这是完全受控制的接收方。  
  
 队列窗口大小属性控制 SWIFTNet SnF 确认对队列中检索的消息的最大数目。 接收方仍必须确认该消息之前，释放在窗口中的槽。  
  
### <a name="delivery-into-a-queue"></a>传递到队列  
 使用存储和转发的服务接收方判定哪个队列用于存储中存储和转发模式发送的消息。  
  
 送达通知被放入队列的发件人机构，若要发送的消息的传递状态通知发件人。 这是可配置为发送适配器属性。  
  
## <a name="sessions"></a>会话  
 获取队列时, 启动一个会话。 Sw:SnFSessionId 返回每个消息，则由 SWIFTNet SnF 传送。 Sw:SnFSessionId 包含队列名称的会话模式： 推送和会话编号。 会话号会递增为每个会话。 是一个示例：  
  
 **\<Sw:SnFSessionId\>bankwxyz_applicq1:p:000458\</Sw:SnFSessionId\>**  
  
 "P"指示推送会话。 会话可以也被视为的队列保留授权者。 必须确认相同授权者的后续消息。  
  
 将消息发送到存储转发时，会话不适用。  
  
### <a name="push-session-snf"></a>推送会话 SnF  
 SnF 序列的假设条件如下：  
  
- 客户端进程已完成其工作，并可以立即终止。 若要执行此操作，打开安全上下文必须通过发出 SwSec:DestroyContextRequest 的身份清理。 后 Sw:TermRequest，进程可能 exit()。  
  
- 启动另一个客户端。 与第一个客户端相同的初始化步骤。 通过执行与作为输入基元 Sw:ReleaseSnFQueueRequest SwCall 是队列的版本。  
  
   SWIFTNet 停止从队列的消息传递，只要它已成功处理的队列的版本。  
  
  服务器时将处理一个请求。 SWIFTNet SnF 提供了多个请求从队列中移除。 这些被缓存中的网络和 SWIFTNet 链接，直到服务器做出响应，或发生超时。  
  
  有可能，某些请求已被传递，但尚未确认之前释放队列。 SWIFTNet SnF 不处理任何多个确认中的为这些消息，直到释放队列。 这些消息将被重新传送后续会话中。  
  
  服务器应用程序仍会响应与请求后的客户端发出的新版该队列，但这不是这种情况通常从队列传递的肯定确认是否将由的本地实现。  
  
## <a name="see-also"></a>请参阅  
 [InterAct 适配器体系结构](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)   
 [InterAct 适配器组件](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md)   
 [Business Exchange 的 interAct 适配器消息](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md)   
 [InterAct 适配器客户端应用程序](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md)   
 [InterAct 适配器服务器应用程序](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md)   
 [InterAct 适配器安全体系结构](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md)   
 [交互适配器端到端可靠传递](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md)   
 [InterAct 适配器状态监视](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md)   
 [InterAct 适配器不可否认性](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)