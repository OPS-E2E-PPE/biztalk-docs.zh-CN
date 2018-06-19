---
title: 在用户代码中对消息追加节点 |Microsoft 文档
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
ms.openlocfilehash: b0376094f31478c74a408eacab6c363ce22c9d2a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22229973"
---
# <a name="appending-nodes-to-messages-in-user-code"></a><span data-ttu-id="2cfdb-102">将节点追加到用户代码中的消息</span><span class="sxs-lookup"><span data-stu-id="2cfdb-102">Appending Nodes to Messages in User Code</span></span>
<span data-ttu-id="2cfdb-103">由于 BizTalk Server 处理消息的方法，不能只需直接向现有消息追加一个新的节点。</span><span class="sxs-lookup"><span data-stu-id="2cfdb-103">Because of the way BizTalk Server handles messages, you cannot simply append a new node directly to an existing message.</span></span> <span data-ttu-id="2cfdb-104">相反，必须克隆现有的消息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2cfdb-104">Instead, you must clone the existing message, as follows:</span></span>  
  
```  
myXMLDoc = myExistingMsg; // just holding a reference  
// use CloneNode to make a fresh copy of myModifiedMsg  
myXMLDoc = (XMLDocument)myXMLDoc.CloneNode;  
myXMLDoc.append myNode; // here is the node we want to append  
//update temp message   
myModifiedMsg = myXMLDoc;  
```  
  
 <span data-ttu-id="2cfdb-105">现在你可以使用 myModifiedMsg，其中包括新的节点。</span><span class="sxs-lookup"><span data-stu-id="2cfdb-105">Now you can use myModifiedMsg, which includes the new node.</span></span> <span data-ttu-id="2cfdb-106">如果出于某种原因，你想要重用 myExistingMsg，你可以构造新的 （空） 副本，并为其分配 myModifiedMsg。</span><span class="sxs-lookup"><span data-stu-id="2cfdb-106">If for some reason you want to reuse myExistingMsg, you can construct a new (empty) copy and assign myModifiedMsg to it.</span></span>  
  
```  
myExistingMsg = myModifiedMsg;  
```  
  
## <a name="see-also"></a><span data-ttu-id="2cfdb-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2cfdb-107">See Also</span></span>  
 <span data-ttu-id="2cfdb-108">[构造在用户代码中的消息](../core/constructing-messages-in-user-code.md) </span><span class="sxs-lookup"><span data-stu-id="2cfdb-108">[Constructing Messages in User Code](../core/constructing-messages-in-user-code.md) </span></span>  
 [<span data-ttu-id="2cfdb-109">构造消息</span><span class="sxs-lookup"><span data-stu-id="2cfdb-109">Constructing Messages</span></span>](../core/constructing-messages.md)