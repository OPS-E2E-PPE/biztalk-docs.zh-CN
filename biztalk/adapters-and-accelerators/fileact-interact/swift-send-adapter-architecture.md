---
title: "SWIFT 发送适配器体系结构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e52a5a21-0aa1-4cd9-a2a4-f9df425913a0
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d772203c980495c5aa62266beb060693c1a8ad8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="swift-send-adapter-architecture"></a>SWIFT 发送适配器体系结构
一般情况下，在 BizTalk 服务过程中，Btsntsvc.exe 托管 BizTalk Server 发送适配器。 这意味着 BizTalk Server 管理适配器的生存期。  
  
 有两种方法将消息发送到 SWIFT 网络： 同步 (ExchangeRequest) 和异步 （对于此版本未实现）。 在 BizTalk Server 中，发送适配器应支持以下的通信模式，与 BizTalk 消息传送引擎进行交互：  
  
-   请求作出响应-采用对，调用的基元，与 SWIFT 网络交换消息。 发送到 SWIFT 任何消息将包含业务、 确认或错误的响应。 响应消息返回到 messagebox 提交。 这种模式的操作用于实时通信。  
  
-   一种方法发送 — 适配器中的一种方法配置时可在存储和转发模式运行。 消息发送到预配置队列而不是收件人。 发件人可以通过使用队列在推送或拉取模式下打开会话检索响应。  
  
> [!NOTE]
>  创建适配器的方式影响它的操作的方式。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [SWIFT 发送适配器 URI](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-uri.md)  
  
-   [SWIFT 发送适配器动态发送](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-dynamic-send.md)  
  
-   [SWIFT 发送适配器初始化](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-initialization.md)  
  
-   [SWIFT 发送适配器同步模式](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-synchronous-mode.md)  
  
-   [SWIFT 发送适配器终止](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-termination.md)