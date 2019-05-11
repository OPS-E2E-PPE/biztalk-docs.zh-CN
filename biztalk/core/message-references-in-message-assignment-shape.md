---
title: 消息在消息赋值形状中的引用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, code samples
- code samples, messages
- messages, objects
ms.assetid: 428f7eb8-001e-4147-b1c8-f9bb6f3a80f9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d74aea98cb780ba8ef81e0329f12fbd7685878f8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65325000"
---
# <a name="message-references-in-message-assignment-shape"></a>消息赋值形状中的消息引用
当你首次分配。基于 NET 的对象添加到一条消息或消息部分，该消息保存并维护对对象的引用。  
  
 对于效率和可伸缩性，业务流程引擎不会执行该对象的"深层复制": 即，它不到消息复制对象的全部内容。  
  
 如果随后将对象分配到另一条消息或消息部分，对原始进行任何修改将导致对第二个消息或消息部分进行修改。 应避免这种做法，因为是不可预知的结果。  
  
 如果需要第二个中的消息具有不同的对象的副本，应将第一条消息或消息部分分配给第二个消息或消息部分。  
  
 请看下面的示例：  
  
 错误的处理方式：  
  
```  
myMsg1 = myObj; // assign the first message  
myMsg2 = myObj; // assign the second message (wrong!)  
myMsg2.myInt = 100; // modify the second  
myMsg1.myInt = 5;  
```  
  
 在这种情况下，myMsg2.myInt 已被覆盖，并且现在具有值 5。  
  
 正确的方式：  
  
```  
myMsg1 = myObj; // assign the first message  
myMsg2 = myMsg1; // assign the second message (right!)  
myMsg2.myInt = 100; // modify the second  
myMsg1.myInt = 5;  
```  
  
 在这种情况下，myMsg2.myInt 仍具有值 100，按预期方式。  
  
## <a name="see-also"></a>请参阅  
 [构造消息](../core/constructing-messages.md)