---
title: 交互适配器存储和转发 |Microsoft 文档
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
ms.openlocfilehash: 6c7aff0b2421a19f5fe84ee914c4f9d2bd7ef04e
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963203"
---
# <a name="interact-adapter-store-and-forward"></a>交互适配器存储和转发
存储区中和进 (SnF) 模式下，消息在发送时，传递到队列并从由目标队列检索。 当使用 SnF，响应来自 SWIFTNet SnF 本身，并且不包含从响应方的任何反馈。  
  
 消息和文件可以使用作为消息路由到的服务器进程，不使用 SnF 时一样灵活地处理路由排入队列。 此定义都在 MRR （内 SWIFTNet) 内。 它是接收方负责决定哪个队列在消息或文件都将发送方发送后而言。 将消息或文件放入队列可通过标记 （在 RequestControl) SnF 传递模式的消息。  
  
 从队列检索消息所做的工作会两种不同模式，具体取决于应用程序设计器所做的选择。 这些模式被调用推送和拉取。  
  
 使用推送模式时，与 SWIFTNet SnF 驻留驻留计划传递的消息。 消息然后"推送"从 SWIFTNet SnF，并且接收 SWIFTNet 链接上的应用程序服务器。 服务器应用程序以确保使用确认响应之前，消息，是 safestored。 此确认指示 SWIFTNet SnF 接收消息的方式。 确认不包含任何其他附加"业务"逻辑。  
  
## <a name="queues-in-swiftnet"></a>SWIFTNet 中的队列  
 队列包含消息和发件人发送到指定的接收方发送的文件。 队列也包含由 SWIFTNet SnF 生成的发送通知。  
  
 队列是定义和配置由接收方的组织。 实际创建队列是通过 SWIFT 上的用户的请求。 发件人不知道任何有关在其中最终会将消息队列。 这是完全受控制的接收方。  
  
 Queue 窗口大小属性控制的最大 SWIFTNet SnF 从而无需确认队列中检索的消息数。 接收方仍必须确认消息之前，释放窗口中的槽。  
  
### <a name="delivery-into-a-queue"></a>传递到队列  
 使用存储转发的服务接收方判定哪个队列将用于存储在存储转发模式下发送的消息。  
  
 送达通知被放入发件人机构，以通知发件人发送的消息的传递状态有关的队列。 这是与发送适配器属性可配置。  
  
## <a name="sessions"></a>会话  
 获取队列时, 启动会话。 Sw:SnFSessionId 返回每个消息，则由 SWIFTNet SnF 传送中。 Sw:SnFSessionId 包含队列名称、 会话模式： 推送和会话数。 所会话数将增加为每个会话中。 是一个示例：  
  
 **\<Sw:SnFSessionId\>bankwxyz_applicq1:p:000458\</Sw:SnFSessionId\>**  
  
 "P"指示推送会话。 会话可以也被视为队列的保留由授权者。 后续的消息具有相同授权者的确认。  
  
 将消息发送到存储转发时，会话不适用。  
  
### <a name="push-session-snf"></a>推送会话 SnF  
 SnF 序列假设如下：  
  
-   客户端进程完成其工作时，并可以立即终止。 若要执行此操作，打开安全上下文必须通过发出 SwSec:DestroyContextRequest 的身份清理。 后 Sw:TermRequest，进程可能 exit()。  
  
-   启动另一个客户端。 初始化步骤都与第一个客户端的相同。 通过执行与作为输入基元 Sw:ReleaseSnFQueueRequest SwCall 是队列的版本。  
  
     SWIFTNet 停止从队列的消息传递，一旦它已成功处理的队列的版本。  
  
 服务器在时间处理一个请求。 SWIFTNet SnF 提供从队列中移除的多个请求。 服务器响应，或发生超时之前网络和 SWIFTNet 链接中缓冲。  
  
 有可能，一些请求了已传递，但尚未确认之前释放队列。 SWIFTNet SnF 不处理这些消息的任何详细确认，直到队列被释放。 这些消息将重新发送后续会话中。  
  
 它是从左到的本地实现是否服务器应用程序仍将使用进行响应的请求在客户端已发出版本的该队列，但是通常这不是这种情况后从队列传递一个正确认。  
  
## <a name="see-also"></a>另请参阅  
 [交互适配器体系结构](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)   
 [交互适配器组件](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md)   
 [适用于业务 Exchange 交互适配器消息](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md)   
 [交互适配器客户端应用程序](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md)   
 [交互适配器服务器应用程序](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md)   
 [交互适配器安全体系结构](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md)   
 [交互适配器端到端可靠传递](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md)   
 [交互适配器状态监视](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md)   
 [InterAct 适配器不可否认性](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)