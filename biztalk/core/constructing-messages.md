---
title: "构造消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, messages
- multi-part message types
- messages, modifying
- multi-part message types, about multi-part message types
- modifying, messages
- messages, creating
ms.assetid: c9fc1e97-ff53-42e2-848c-6c8fae7c9122
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 923fa87c4f3400a80ce83df132747d0004232323
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="constructing-messages"></a>构造消息
只要您通过接收消息或为消息变量赋值将消息引入业务流程，就需要构造消息。 您构造的任何消息必须具有消息类型，这样运行时引擎才有所使用的对象的完整说明。 多部分消息类型可以是用户定义的，可以是 .NET 类，也可以是架构。 您可以构造消息以各种方式： 你可以调用一个.NET 类来创建一条消息，将一条消息分配给另一个字符串，或使用转换来将消息中的某些值映射到另一条消息中的值。 消息还可以由接收操作构造，或者在业务流程将消息作为参数来接受的时候构造。  
  
> [!NOTE]
>  多部分消息类型不一定包含多个部分，也可能只包含一个部分。  
  
> [!IMPORTANT]
>  消息在 BizTalk 中是不可改变的，也就是说，在您构造它之后，就不能修改该原始消息了。 如果需要进行更改，必须构造消息的新副本，并适当地为其赋值。  
  
## <a name="in-this-section"></a>本节内容  
 [如何配置构造消息形状](../core/how-to-configure-the-construct-message-shape.md)  
  
 [如何配置消息赋值形状](../core/how-to-configure-the-message-assignment-shape.md) 
  
 [如何配置转换形状](../core/how-to-configure-the-transform-shape.md) 
  
 [消息赋值形状中的消息引用](../core/message-references-in-message-assignment-shape.md)  
  
 [在用户代码中的消息引用](../core/message-references-in-user-code.md)  
  
 [在消息分配中使用 Xpath](../core/using-xpaths-in-message-assignments.md)  
  
 [在消息分配中使用非规范 Xpath](../core/using-non-canonical-xpaths-in-message-assignments.md)  
  
 [构造在用户代码中的消息](../core/constructing-messages-in-user-code.md)  
  
 [将节点追加到用户代码中的消息](../core/appending-nodes-to-messages-in-user-code.md)  
  
## <a name="see-also"></a>另请参阅  
 [在业务流程中使用消息](../core/using-messages-in-orchestrations.md)