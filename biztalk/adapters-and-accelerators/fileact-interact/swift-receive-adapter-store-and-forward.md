---
title: SWIFT 接收适配器存储和转发 |Microsoft 文档
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
ms.openlocfilehash: 315b9bbe6985bbce5ccb44d8d4846b18730f292b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224469"
---
# <a name="swift-receive-adapter-store-and-forward"></a>SWIFT 接收适配器存储和转发
接收适配器从 SWIFT 存储和转发 (SnF) 队列接收消息。 若要从队列接收消息，适配器必须使用 SnF 队列打开会话。 若要打开队列，则必须建立与队列的会话的专用客户端进程。 在设计中，作为 COM plus 进程外的组件来实现此过程。  
  
## <a name="push-session-store-and-forward-sequence"></a>将会话存储和转发序列推送  
 以下列表介绍的存储和转发的序列。  
  
1.  启动服务器应用程序处理消息。  
  
2.  服务器进程将所需的安全上下文作为输入基元期间 Sw:HandleInitRequest 与第一个 SwCallback 上打开。  
  
3.  服务器响应的其中一种或两个 Sw:CryptoMode 和设置为高级 Sw:FACryptoMode Sw:HandleInitRequest。  
  
     服务器现已开始处理传入请求。  
  
4.  若要启动队列消息的传递，客户端进程启动推送会话。 接收适配器根据适配器配置 （推送模式下），生成一个称为 SnFQueueManager.exe 获取在推送模式下队列的客户端进程。  
  
5.  SwCall() 运行 Sw:AcquireSnFRequest （在 Sw:ExchangeSnFRequest) 作为输入基元。 此请求启动与指示队列的会话 （如果 SwSec:AuthorisationContext 具有所需的 RBAC 角色）。  
  
6.  在响应中 Sw:AcquireStatus"已接受"之后立即, SWIFTNet SnF 启动将消息发送到中获取指定的服务器。 如果接收适配器未尚未启动，消息将获得异常。 （这是非常重要具有已开始接收适配器的原因）。  
  
7.  SWIFTNet SnF 开始推送数消息 （最多的窗口大小）。  
  
8.  确认每个消息，推送一条新消息 （如果有）。  
  
9. 客户端进程 (SnFQueueManager.exe) 完成其工作时，并可以立即终止。 进程发出 SwSec:DestroyContextRequest，清理打开的安全上下文。 后 Sw:TermRequest，在进程退出。  
  
### <a name="message-correlation"></a>消息相关性  
 RequestRef 字段是将保留并在响应消息中返回替换由接收适配器。 这可确保传入的消息和响应消息之间的端到端相关性  
  
### <a name="duplicate-processing"></a>重复处理  
 如果接收 FileAct 请求和适配器实例接收可能重复的指示器节点下，消息，则它必须检查以查看是否引用的传输已成功完成或已失败，并采取相应的措施。 如果文件传输已经完成，然后适配器更新工作项作为"副本"传输状态否则它将更新其为"已接受。"  
  
### <a name="acknowledgments"></a>鸣谢  
 如果发件人请求 FileAct 请求确认，该适配器将检查文件传输完成事件，并生成验证文件摘要值后的确认。 适配器将确认消息发送到 BizTalk 发送适配器选取它，并将其发送到发送方。  
  
## <a name="see-also"></a>另请参阅  
 [SWIFT 接收适配器体系结构](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md)   
 [SWIFT 接收适配器 URI](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md)   
 [SWIFT 接收适配器初始化](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-initialization.md)   
 [SWIFT 接收适配器安全上下文](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-security-context.md)   
 [SWIFT 接收适配器同步和延迟模式](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-synchronous-and-deferred-modes.md)