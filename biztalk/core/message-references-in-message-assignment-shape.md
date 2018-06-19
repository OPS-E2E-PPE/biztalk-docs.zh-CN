---
title: 消息中消息赋值形状引用 |Microsoft 文档
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
ms.openlocfilehash: b834eefa991b6cad89a04a836f63d1b9af73fc04
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262805"
---
# <a name="message-references-in-message-assignment-shape"></a>消息赋值形状中的消息引用
当你首次分配。基于网络的对象添加到一条消息或消息部分，该消息可保持并保留该对象的引用。  
  
 对于效率和可伸缩性，业务流程引擎不执行对象的"深层副本": 即，它不会复制该对象的全部内容到消息。  
  
 如果你随后将对象分配到另一条消息或消息部分，对原始进行任何修改会导致对第二个消息或消息部分进行修改。 你应当避免这种做法，因为结果是不可预知。  
  
 如果你需要你拥有的对象的不同副本的第二条消息，你应该分配到第二个消息或消息部分的第一条消息或消息部分。  
  
 请参考如下示例：  
  
 错误的方式：  
  
```  
myMsg1 = myObj; // assign the first message  
myMsg2 = myObj; // assign the second message (wrong!)  
myMsg2.myInt = 100; // modify the second  
myMsg1.myInt = 5;  
```  
  
 在这种情况下，myMsg2.myInt 已被覆盖，并且现在有值 5。  
  
 正确的方式：  
  
```  
myMsg1 = myObj; // assign the first message  
myMsg2 = myMsg1; // assign the second message (right!)  
myMsg2.myInt = 100; // modify the second  
myMsg1.myInt = 5;  
```  
  
 在这种情况下，myMsg2.myInt 仍然有值 100，按预期方式。  
  
## <a name="see-also"></a>另请参阅  
 [构造消息](../core/constructing-messages.md)