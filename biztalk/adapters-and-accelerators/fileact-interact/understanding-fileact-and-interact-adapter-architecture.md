---
title: 了解 FileAct 和 InterAct 适配器体系结构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8f97a7fe-20df-4509-bb6e-53743c3a57df
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b1a6b5cf310dfd7e65cba21364cbccc385300df
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364078"
---
# <a name="understanding-fileact-and-interact-adapter-architecture"></a>了解 FileAct 和 InterAct 适配器体系结构
SWIFT 适配器基于 BizTalk 适配器框架。 使用 BizTalk Server 中的适配器的分类，SWIFT 适配器，FileAct 和 InterAct，表示以下：  
  
- 自定义适配器。 这是专门为与使用专有标准调用 FileAct 和 Interact 的 SWIFT 网络交互构建的自定义适配器。  
  
- 传输适配器。 此适配器允许业务软件应用程序发送和接收消息的 SWIFT 网络。  
  
- 非事务处理。 适配器不会进行使用的任何事务对象与 SWIFT 网络进行交互。  
  
- 隔离。 接收适配器的单独进程中运行，并在进程中运行常规发送适配器。  
  
  BizTalk 适配器框架有关的信息，请参阅"什么是适配器框架？" BizTalk Server 帮助中的主题。  
  
  下图显示了 FileAct 和 InterAct 体系结构的高级视图。  
  
  ![](../../adapters-and-accelerators/fileact-interact/media/035ebb05-ce11-447c-b56b-ba8b41e07e50.gif "035ebb05-ce11-447c-b56b-ba8b41e07e50")  
  
> [!NOTE]
>  Microsoft[!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)]支持仅严格模式下 SWIFTNet 链接 (SNL) API。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [SWIFTNet 客户端和服务器](../../adapters-and-accelerators/fileact-interact/swiftnet-client-and-server.md)  
  
-   [SWIFT 发送配器体系结构](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-architecture.md)  
  
-   [SWIFT 接收适配器体系结构](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md)  
  
-   [FileAct 适配器体系结构](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md)  
  
-   [InterAct 适配器体系结构](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)