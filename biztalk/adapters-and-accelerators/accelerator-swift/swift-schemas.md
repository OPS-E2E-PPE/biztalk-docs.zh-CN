---
title: SWIFT 架构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SWIFT, SWIFT messages
- schemas, SWIFT
- SWIFT messages, SWIFT schemas
- SWIFT, schemas
ms.assetid: 53017a56-a718-4577-a08c-9c92d9a54e7a
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b4bac26d99fb3282650c20381bbc18237f8908a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214917"
---
# <a name="swift-schemas"></a>SWIFT 架构
[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]通过发送和接收 SWIFT 财务 (FIN) 消息作为单个平面文件 SWIFT 网络。 每个单个消息包含一组标头块组成一组预定义的标记的字段和位置或有序子字段和尾部预告片块中的一组文本块。 文本块的内容因消息类型而异。  
  
 也有许多应用程序，交换 SWIFT 财务 (FIN) 消息批处理-一组的单个文件中包含的消息。 该文件可能本地传递，或可能通过 FileAct 传输 (通过 SWIFT IP 网络-SIPN)，或通过 FTP。  
  
 若要简化与这些消息，无论它们是批处理还是单独，提交关联的数据的操作[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]提供 XSD 架构定义每种消息类型。 此架构提升消息类型，以便可以自动与正确的架构，并自动转换之间外部的平面文件表示形式，由 SWIFT 网络，或从 XML 消息。  
  
 架构包含的所有块包括标头、 文本和拖车安排。 此架构是信息的交换架构，因为它是信息的完整，无法通过 SWIFT 网络使用 FIN 消息级协议，传输消息，并可包含所有与通过 SWIFT 网络收到的消息关联。  
  
 每种消息类型的架构定义的整体的格式和该消息类型的上下文。 A4SWIFT 定义每个块。 在每个块内的字段和子字段的布局。根据需要，从常见的基本或复杂类型，在单独的架构中定义生成的字段和子字段。 架构级别验证包括格式、 字符集、 设置值、 范围、 必需/可选，可重复性、 位置和长度，根据需要。 业务规则执行跨字段验证和其他逻辑检查。  
  
 本部分包含：  
  
-   [示例消息演示文稿](../../adapters-and-accelerators/accelerator-swift/sample-message-presentation.md)  
  
-   [示例架构演示文稿](../../adapters-and-accelerators/accelerator-swift/sample-schema-presentation.md)  
  
-   [SWIFT 标头](../../adapters-and-accelerators/accelerator-swift/swift-headers.md)  
  
-   [SWIFT 文本](../../adapters-and-accelerators/accelerator-swift/swift-text.md)  
  
-   [SWIFT 拖车安排](../../adapters-and-accelerators/accelerator-swift/swift-trailers.md)  
  
-   [更新 SWIFT 消息标准](../../adapters-and-accelerators/accelerator-swift/updating-swift-messaging-standards.md)