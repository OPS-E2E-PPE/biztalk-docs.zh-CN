---
title: 构造消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, messages
- multi-part message types
- messages, modifying
- multi-part message types, about multi-part message types
- modifying, messages
- messages, creating
ms.assetid: c9fc1e97-ff53-42e2-848c-6c8fae7c9122
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c2267863facd50af0f2c2c018d158fa6ee678cd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354643"
---
# <a name="constructing-messages"></a>构造消息
在构造消息任何时候您引入到您的业务流程，一条消息由接收它或者将值分配给消息变量。 构造的任何消息必须具有消息类型，以便运行时引擎具有自己正在使用的对象的完整说明。 多部分消息类型可以是用户定义，它可以是.NET 类，也可以是一个架构。 您可以构造消息以各种方式： 您可以调用.NET 类来创建一条消息、 将一条消息分配给另一个，或使用转换来将一条消息中的某些值映射到另一个消息中的值。 接收操作或当您的业务流程接受消息作为参数时也被构造的消息。  
  
> [!NOTE]
>  多部分消息类型不一定包含多个部分;它可能只包含一个。  
  
> [!IMPORTANT]
>  消息是不可改变在 BizTalk 中;也就是说，一旦您构造它，不能修改原始。 如果需要进行更改，必须构造新消息的副本，并相应地向其分配值。  
  
## <a name="in-this-section"></a>本节内容  
 [如何配置构造消息形状](../core/how-to-configure-the-construct-message-shape.md)  
  
 [如何配置消息赋值形状](../core/how-to-configure-the-message-assignment-shape.md) 
  
 [如何配置转换形状](../core/how-to-configure-the-transform-shape.md) 
  
 [“消息赋值”形状中的消息引用](../core/message-references-in-message-assignment-shape.md)  
  
 [用户代码中的消息引用](../core/message-references-in-user-code.md)  
  
 [在消息赋值中使用 XPath](../core/using-xpaths-in-message-assignments.md)  
  
 [在消息赋值中使用非规范化 XPath](../core/using-non-canonical-xpaths-in-message-assignments.md)  
  
 [在用户代码中构造消息](../core/constructing-messages-in-user-code.md)  
  
 [向用户代码中的消息追加节点](../core/appending-nodes-to-messages-in-user-code.md)  
  
## <a name="see-also"></a>请参阅  
 [在业务流程中使用消息](../core/using-messages-in-orchestrations.md)