---
title: SWIFT 接收适配器存储和转发 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 11eeb335-366b-4b29-9078-de9396b258ca
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1744f86cc10bfe37b1a4c7814c31e6e2e8812507
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364376"
---
# <a name="swift-receive-adapter-store-and-forward"></a>SWIFT 接收适配器存储和转发
接收适配器接收来自 SWIFT 的存储和转发 (SnF) 队列消息。 若要从队列接收消息，适配器必须使用 SnF 队列打开会话。 若要打开队列，必须建立与队列的会话的专用客户端进程。 在设计中，作为 COM plus 的进程外组件实现此过程。  
  
## <a name="push-session-store-and-forward-sequence"></a>将会话存储和转发序列推送  
 以下列表介绍的存储和转发的序列。  
  
1.  开始处理消息的服务器应用程序。  
  
2.  服务器进程将所需的安全上下文作为输入基元期间 Sw:HandleInitRequest 与第一个 SwCallback 上打开。  
  
3.  服务器响应与一个或两个 Sw:CryptoMode 和设置为高级 Sw:FACryptoMode Sw:HandleInitRequest。  
  
     服务器现已开始处理传入的请求。  
  
4.  若要启动队列的消息传递，客户端进程启动推送会话。 基于适配器配置 （push 模式），接收适配器生成名为 SnFQueueManager.exe 获取在推送模式下队列的客户端进程。  
  
5.  SwCall() 作为输入基元运行与 Sw:AcquireSnFRequest （在 Sw:ExchangeSnFRequest)。 此请求启动与所指示的队列的会话 （如果 SwSec:AuthorisationContext 具有必需的 RBAC 角色）。  
  
6.  Sw:AcquireStatus 中响应与"已接受"后立即, SWIFTNet SnF 开始将消息发送到中获取指定的服务器。 如果未尚未启动接收适配器，消息将收到异常。 （这是就是必须已启动的接收适配器的原因）。  
  
7.  SWIFTNet SnF 启动推送数 （最大窗口大小） 的消息。  
  
8.  为确认每条消息，推送新消息 （如果有）。  
  
9. 客户端进程 (SnFQueueManager.exe) 完成其工作后，可以立即终止。 该过程会发出 SwSec:DestroyContextRequest，清理打开安全上下文。 Sw:TermRequest 之后, 在进程退出。  
  
### <a name="message-correlation"></a>消息相关性  
 RequestRef 字段是将保留并替换为返回响应消息中接收适配器。 这可确保传入消息和响应消息之间的端到端相关性  
  
### <a name="duplicate-processing"></a>重复处理  
 如果 FileAct 请求和适配器实例接收，则接收的消息可能重复的指示符节点，然后，它必须检查以查看引用的传输已成功完成，或者如果它出现故障，并采取相应的措施。 如果文件传输适配器更新为"重复"传输状态已执行，否则它将更新其为"已接受"。  
  
### <a name="acknowledgments"></a>确认  
 如果发件人请求 FileAct 请求确认，适配器将检查文件传输完成事件，并生成验证文件摘要值后的确认。 适配器向 BizTalk 发送适配器以选择它并将其发送给发件人发送确认消息。  
  
## <a name="see-also"></a>请参阅  
 [SWIFT 接收适配器体系结构](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md)   
 [SWIFT 接收适配器 URI](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md)   
 [SWIFT 接收适配器初始化](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-initialization.md)   
 [SWIFT 接收适配器安全上下文](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-security-context.md)   
 [SWIFT 接收适配器同步和延迟模式](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-synchronous-and-deferred-modes.md)