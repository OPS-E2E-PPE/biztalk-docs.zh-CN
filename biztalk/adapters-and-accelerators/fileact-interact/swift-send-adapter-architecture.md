---
title: SWIFT 发送适配器体系结构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e52a5a21-0aa1-4cd9-a2a4-f9df425913a0
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4347680cf4fa1434e72e80c74debe0ca2de8d47
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364175"
---
# <a name="swift-send-adapter-architecture"></a>SWIFT 发送适配器体系结构
一般情况下，BizTalk Server 发送适配器的宿主 BizTalk 服务进程 Btsntsvc.exe。 这意味着 BizTalk Server 管理适配器的生存期。  
  
 有两种方法将消息发送到 SWIFT 网络的： 同步 (ExchangeRequest) 和异步 （对于此版本未实现）。 在 BizTalk Server 中，发送适配器应支持以下通信模式与 BizTalk 消息引擎进行交互：  
  
-   要求响应 — 成对，名为的基元，与 SWIFT 网络交换消息。 向 SWIFT 发送任何消息将具有是其业务、 确认或错误的响应。 响应消息提交回 messagebox。 此操作模式用于实时通信。  
  
-   一种方式发送，适配器中的一种方法配置时可在存储和转发模式运行。 将消息发送到预配置队列而不是收件人。 发件人可以通过使用队列在推送或拉取模式下打开会话检索响应。  
  
> [!NOTE]
>  创建适配器的方式会影响运行的方式。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [SWIFT 发送适配器 URI](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-uri.md)  
  
-   [SWIFT 发送适配器动态发送](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-dynamic-send.md)  
  
-   [SWIFT 发送适配器初始化](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-initialization.md)  
  
-   [SWIFT 发送适配器同步模式](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-synchronous-mode.md)  
  
-   [SWIFT 发送适配器终止](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-termination.md)