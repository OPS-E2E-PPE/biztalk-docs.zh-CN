---
title: 了解 FileAct 和交互适配器体系结构 |Microsoft 文档
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
ms.openlocfilehash: c04d0ba8b1c2bbd99a71e3d76c8d7ad60c251147
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223405"
---
# <a name="understanding-fileact-and-interact-adapter-architecture"></a>了解 FileAct 和交互适配器体系结构
SWIFT 适配器取决于 BizTalk 适配器框架。 使用 BizTalk Server 中的适配器的分类，SWIFT 适配器，FileAct 和交互，表示的意义如下：  
  
-   自定义适配器。 这是生成专门用于与使用称为 FileAct 和交互的专有标准 SWIFT 网络交互的自定义适配器。  
  
-   传输适配器。 此适配器允许商业软件应用程序发送和接收与 SWIFT 网络的消息。  
  
-   非事务性。 适配器不会进行的任何事务对象用于与 SWIFT 网络交互。  
  
-   隔离。 接收适配器在单独的进程中运行并在进程中运行常规发送适配器。  
  
 BizTalk 适配器框架有关的信息，请参阅"什么是适配器 Framework？" BizTalk Server 帮助中的主题。  
  
 下图显示的 FileAct 和交互体系结构的高级视图。  
  
 ![](../../adapters-and-accelerators/fileact-interact/media/035ebb05-ce11-447c-b56b-ba8b41e07e50.gif "035ebb05-ce11-447c-b56b-ba8b41e07e50")  
  
> [!NOTE]
>  Microsoft[!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)]支持仅严格模式下 SWIFTNet 链接 (SNL) API。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [SWIFTNet 客户端和服务器](../../adapters-and-accelerators/fileact-interact/swiftnet-client-and-server.md)  
  
-   [SWIFT 发送适配器体系结构](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-architecture.md)  
  
-   [SWIFT 接收适配器体系结构](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md)  
  
-   [FileAct 适配器体系结构](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md)  
  
-   [交互适配器体系结构](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)