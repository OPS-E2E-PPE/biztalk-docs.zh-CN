---
title: 将节点追加到用户代码中的消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, nodes
- messages, cloning
ms.assetid: 636e0064-095e-49d1-850f-eaee0f0ffe77
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6dacbe06634748590be17ca8cd668e0825de1880
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359654"
---
# <a name="appending-nodes-to-messages-in-user-code"></a>将节点追加到用户代码中的消息
由于 BizTalk Server 处理消息的方式，只需不能直接向现有的消息中附加一个新的节点。 相反，必须按如下所示克隆现有的消息：  
  
```  
myXMLDoc = myExistingMsg; // just holding a reference  
// use CloneNode to make a fresh copy of myModifiedMsg  
myXMLDoc = (XMLDocument)myXMLDoc.CloneNode;  
myXMLDoc.append myNode; // here is the node we want to append  
//update temp message   
myModifiedMsg = myXMLDoc;  
```  
  
 现在可以使用 myModifiedMsg，其中包括新节点。 如果出于某种原因，你想要重复使用 myExistingMsg，可以构造新的 （空） 副本并为其分配 myModifiedMsg。  
  
```  
myExistingMsg = myModifiedMsg;  
```  
  
## <a name="see-also"></a>请参阅  
 [在用户代码中构造消息](../core/constructing-messages-in-user-code.md)   
 [构造消息](../core/constructing-messages.md)