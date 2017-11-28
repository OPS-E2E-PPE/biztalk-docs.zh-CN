---
title: "消息中消息赋值形状引用 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, code samples
- code samples, messages
- messages, objects
ms.assetid: 428f7eb8-001e-4147-b1c8-f9bb6f3a80f9
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b834eefa991b6cad89a04a836f63d1b9af73fc04
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="message-references-in-message-assignment-shape"></a><span data-ttu-id="2c1aa-102">消息赋值形状中的消息引用</span><span class="sxs-lookup"><span data-stu-id="2c1aa-102">Message References in Message Assignment Shape</span></span>
<span data-ttu-id="2c1aa-103">当你首次分配。基于网络的对象添加到一条消息或消息部分，该消息可保持并保留该对象的引用。</span><span class="sxs-lookup"><span data-stu-id="2c1aa-103">When you first assign a .NET-based object to a message or message part, that message holds and maintains a reference to the object.</span></span>  
  
 <span data-ttu-id="2c1aa-104">对于效率和可伸缩性，业务流程引擎不执行对象的"深层副本": 即，它不会复制该对象的全部内容到消息。</span><span class="sxs-lookup"><span data-stu-id="2c1aa-104">For efficiency and scalability, the orchestration engine does not do a "deep copy" of the object: that is, it does not copy the entire contents of the object to the message.</span></span>  
  
 <span data-ttu-id="2c1aa-105">如果你随后将对象分配到另一条消息或消息部分，对原始进行任何修改会导致对第二个消息或消息部分进行修改。</span><span class="sxs-lookup"><span data-stu-id="2c1aa-105">If you subsequently assign the object to another message or message part, any modifications to the original results in modifications to the second message or message part.</span></span> <span data-ttu-id="2c1aa-106">你应当避免这种做法，因为结果是不可预知。</span><span class="sxs-lookup"><span data-stu-id="2c1aa-106">You should avoid this practice, because results are unpredictable.</span></span>  
  
 <span data-ttu-id="2c1aa-107">如果你需要你拥有的对象的不同副本的第二条消息，你应该分配到第二个消息或消息部分的第一条消息或消息部分。</span><span class="sxs-lookup"><span data-stu-id="2c1aa-107">If you need your second message to have a distinct copy of the object, you should assign the first message or message part to the second message or message part.</span></span>  
  
 <span data-ttu-id="2c1aa-108">请参考如下示例：</span><span class="sxs-lookup"><span data-stu-id="2c1aa-108">Consider the following example:</span></span>  
  
 <span data-ttu-id="2c1aa-109">错误的方式：</span><span class="sxs-lookup"><span data-stu-id="2c1aa-109">Wrong way:</span></span>  
  
```  
myMsg1 = myObj; // assign the first message  
myMsg2 = myObj; // assign the second message (wrong!)  
myMsg2.myInt = 100; // modify the second  
myMsg1.myInt = 5;  
```  
  
 <span data-ttu-id="2c1aa-110">在这种情况下，myMsg2.myInt 已被覆盖，并且现在有值 5。</span><span class="sxs-lookup"><span data-stu-id="2c1aa-110">In this case, myMsg2.myInt has been overwritten, and now has the value 5.</span></span>  
  
 <span data-ttu-id="2c1aa-111">正确的方式：</span><span class="sxs-lookup"><span data-stu-id="2c1aa-111">Right way:</span></span>  
  
```  
myMsg1 = myObj; // assign the first message  
myMsg2 = myMsg1; // assign the second message (right!)  
myMsg2.myInt = 100; // modify the second  
myMsg1.myInt = 5;  
```  
  
 <span data-ttu-id="2c1aa-112">在这种情况下，myMsg2.myInt 仍然有值 100，按预期方式。</span><span class="sxs-lookup"><span data-stu-id="2c1aa-112">In this case, myMsg2.myInt still has the value 100, as expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c1aa-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2c1aa-113">See Also</span></span>  
 [<span data-ttu-id="2c1aa-114">构造消息</span><span class="sxs-lookup"><span data-stu-id="2c1aa-114">Constructing Messages</span></span>](../core/constructing-messages.md)