---
title: "在用户代码中对消息追加节点 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, nodes
- messages, cloning
ms.assetid: 636e0064-095e-49d1-850f-eaee0f0ffe77
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b0376094f31478c74a408eacab6c363ce22c9d2a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="appending-nodes-to-messages-in-user-code"></a>将节点追加到用户代码中的消息
由于 BizTalk Server 处理消息的方法，不能只需直接向现有消息追加一个新的节点。 相反，必须克隆现有的消息，如下所示：  
  
```  
myXMLDoc = myExistingMsg; // just holding a reference  
// use CloneNode to make a fresh copy of myModifiedMsg  
myXMLDoc = (XMLDocument)myXMLDoc.CloneNode;  
myXMLDoc.append myNode; // here is the node we want to append  
//update temp message   
myModifiedMsg = myXMLDoc;  
```  
  
 现在你可以使用 myModifiedMsg，其中包括新的节点。 如果出于某种原因，你想要重用 myExistingMsg，你可以构造新的 （空） 副本，并为其分配 myModifiedMsg。  
  
```  
myExistingMsg = myModifiedMsg;  
```  
  
## <a name="see-also"></a>另请参阅  
 [构造在用户代码中的消息](../core/constructing-messages-in-user-code.md)   
 [构造消息](../core/constructing-messages.md)