---
title: SWIFT 架构 |Microsoft Docs
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
ms.openlocfilehash: 84bc0cde2b41d5518c7bd15bdc35b148c658a63e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376948"
---
# <a name="swift-schemas"></a>SWIFT 架构
[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] 通过发送和接收 SWIFT 财务 (FIN) 消息作为单个平面文件的 SWIFT 网络。 每个消息包含一组标头块的一组预定义的标记的字段和位置或有序子字段和尾部尾部块内的一组组成的文本块。 文本块的内容因消息类型而异。  
  
 此外，还有许多应用程序，exchange SWIFT 财务 (FIN) 消息批，一系列单个文件中包含的消息。 该文件可能本地传递，或可能通过 FileAct 传输 (通过 SWIFT IP 网络 — SIPN)，或通过 FTP。  
  
 若要简化数据的操作与关联这些消息，不管它们是批处理中还是单独提交 Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]提供了一个 XSD 架构定义每种消息类型。 此架构将升级消息类型，以便可以自动与正确的架构，并自动外部的平面文件表示形式，由 SWIFT 网络，与 XML 之间转换消息。  
  
 架构包含的所有块包括标头、 文本和尾部。 此架构是信息的交换架构，因为它是信息的完整，无法使用 FIN 消息级协议，SWIFT 网络上传输消息，并将包含所有与通过 SWIFT 网络接收的消息关联。  
  
 每种消息类型的架构定义的总体格式和该消息类型的上下文。 A4SWIFT 定义每个块。 在每个块中，字段和子字段的布局方式。根据需要，从常见的基本或复杂类型，在单独的架构中定义生成的字段和子字段。 架构级的验证包括格式、 字符集、 设置值、 范围、 必需/可选，可重复性、 位置和长度，根据需要。 业务规则执行跨字段验证和其他逻辑检查。  
  
 本部分包含：  
  
-   [示例消息演示文稿](../../adapters-and-accelerators/accelerator-swift/sample-message-presentation.md)  
  
-   [示例架构演示文稿](../../adapters-and-accelerators/accelerator-swift/sample-schema-presentation.md)  
  
-   [SWIFT 标头](../../adapters-and-accelerators/accelerator-swift/swift-headers.md)  
  
-   [SWIFT 文本](../../adapters-and-accelerators/accelerator-swift/swift-text.md)  
  
-   [SWIFT 尾部](../../adapters-and-accelerators/accelerator-swift/swift-trailers.md)  
  
-   [更新 SWIFT 消息标准](../../adapters-and-accelerators/accelerator-swift/updating-swift-messaging-standards.md)