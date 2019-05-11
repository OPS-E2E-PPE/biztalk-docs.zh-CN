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
# <a name="appending-nodes-to-messages-in-user-code"></a><span data-ttu-id="862b2-102">将节点追加到用户代码中的消息</span><span class="sxs-lookup"><span data-stu-id="862b2-102">Appending Nodes to Messages in User Code</span></span>
<span data-ttu-id="862b2-103">由于 BizTalk Server 处理消息的方式，只需不能直接向现有的消息中附加一个新的节点。</span><span class="sxs-lookup"><span data-stu-id="862b2-103">Because of the way BizTalk Server handles messages, you cannot simply append a new node directly to an existing message.</span></span> <span data-ttu-id="862b2-104">相反，必须按如下所示克隆现有的消息：</span><span class="sxs-lookup"><span data-stu-id="862b2-104">Instead, you must clone the existing message, as follows:</span></span>  
  
```  
myXMLDoc = myExistingMsg; // just holding a reference  
// use CloneNode to make a fresh copy of myModifiedMsg  
myXMLDoc = (XMLDocument)myXMLDoc.CloneNode;  
myXMLDoc.append myNode; // here is the node we want to append  
//update temp message   
myModifiedMsg = myXMLDoc;  
```  
  
 <span data-ttu-id="862b2-105">现在可以使用 myModifiedMsg，其中包括新节点。</span><span class="sxs-lookup"><span data-stu-id="862b2-105">Now you can use myModifiedMsg, which includes the new node.</span></span> <span data-ttu-id="862b2-106">如果出于某种原因，你想要重复使用 myExistingMsg，可以构造新的 （空） 副本并为其分配 myModifiedMsg。</span><span class="sxs-lookup"><span data-stu-id="862b2-106">If for some reason you want to reuse myExistingMsg, you can construct a new (empty) copy and assign myModifiedMsg to it.</span></span>  
  
```  
myExistingMsg = myModifiedMsg;  
```  
  
## <a name="see-also"></a><span data-ttu-id="862b2-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="862b2-107">See Also</span></span>  
 <span data-ttu-id="862b2-108">[在用户代码中构造消息](../core/constructing-messages-in-user-code.md) </span><span class="sxs-lookup"><span data-stu-id="862b2-108">[Constructing Messages in User Code](../core/constructing-messages-in-user-code.md) </span></span>  
 [<span data-ttu-id="862b2-109">构造消息</span><span class="sxs-lookup"><span data-stu-id="862b2-109">Constructing Messages</span></span>](../core/constructing-messages.md)