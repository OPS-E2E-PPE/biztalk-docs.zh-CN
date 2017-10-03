---
title: "FileAct 适配器存储和转发 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 50110bf0-75c2-426c-9833-65c3117224b2
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1201a5ab5cb45ceba2622aa1c269404acec910df
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="fileact-adapter-store-and-forward"></a>FileAct 适配器存储和转发
存储区中和进 (SnF) 模式下，将文件发送至队列在发送时，并从由目标队列检索。 中间响应将返回由 SWIFTNet 到发件人，直到该文件安全地传递到目标。  
  
## <a name="sending-using-snf"></a>发送使用 SnF  
 如果你创建单向发送端口，适配器在 SnF 模式下工作，并将消息发送到队列。  
  
## <a name="receiving-using-snf"></a>接收使用 SnF  
 SnF FileAct 会在推送模式下运行。 这是运行时选项。  
  
 在能够从队列检索消息前, SWIFTNet SnF 应收到获取队列的请求。 这是通过调用进程外的 COM + 组件接收适配器实现的。 在成功获取之后, 创建一个会话。 然后将请求中指定的模式中打开队列。 所有消息将都返回到发出请求的物理节点。  
  
 消息传递指定的顺序 （请注意可以交织在一起，并按优先级排列交互和 FileAct 传输。）序列化消息，但是，是依赖于就好像它们存储的时间。 对于 FileAct，这是完成文件存储，不是在它启动时的时间。  
  
### <a name="push-a-file-from-the-queue"></a>将从队列推送文件  
 FileAct 适配器 （服务器） 接收 HandleFileRequest 来自 SWIFTNet，其中包含的队列名称、 会话和序列的信息。 服务器通过 HandleFileResponse 做出响应。  
  
 服务器之后发出 FetchFileRequest 并且文件被传送到服务器。  
  
## <a name="see-also"></a>另请参阅  
 [FileAct 适配器体系结构](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md)   
 [FileAct 适配器实时端到端基元](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-end-to-end-primitives.md)   
 [FileAct 适配器实时本地基元](../../adapters-and-accelerators/fileact-interact/fileact-adapter-real-time-local-primitives.md)   
 [FileAct 适配器安全体系结构](../../adapters-and-accelerators/fileact-interact/fileact-adapter-security-architecture.md)   
 [FileAct 适配器文件和传输标识](../../adapters-and-accelerators/fileact-interact/fileact-adapter-file-and-transfer-identification.md)   
 [FileAct 适配器支持信息传输](../../adapters-and-accelerators/fileact-interact/fileact-adapter-supporting-information-transfer.md)   
 [FileAct 适配器传递通知](../../adapters-and-accelerators/fileact-interact/fileact-adapter-delivery-notification.md)   
 [FileAct 适配器状态监视](../../adapters-and-accelerators/fileact-interact/fileact-adapter-status-monitoring.md)