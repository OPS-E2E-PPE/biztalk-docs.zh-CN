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
# <a name="message-references-in-message-assignment-shape"></a><span data-ttu-id="c1159-102">消息赋值形状中的消息引用</span><span class="sxs-lookup"><span data-stu-id="c1159-102">Message References in Message Assignment Shape</span></span>
<span data-ttu-id="c1159-103">当你首次分配。基于 NET 的对象添加到一条消息或消息部分，该消息保存并维护对对象的引用。</span><span class="sxs-lookup"><span data-stu-id="c1159-103">When you first assign a .NET-based object to a message or message part, that message holds and maintains a reference to the object.</span></span>  
  
 <span data-ttu-id="c1159-104">对于效率和可伸缩性，业务流程引擎不会执行该对象的"深层复制": 即，它不到消息复制对象的全部内容。</span><span class="sxs-lookup"><span data-stu-id="c1159-104">For efficiency and scalability, the orchestration engine does not do a "deep copy" of the object: that is, it does not copy the entire contents of the object to the message.</span></span>  
  
 <span data-ttu-id="c1159-105">如果随后将对象分配到另一条消息或消息部分，对原始进行任何修改将导致对第二个消息或消息部分进行修改。</span><span class="sxs-lookup"><span data-stu-id="c1159-105">If you subsequently assign the object to another message or message part, any modifications to the original results in modifications to the second message or message part.</span></span> <span data-ttu-id="c1159-106">应避免这种做法，因为是不可预知的结果。</span><span class="sxs-lookup"><span data-stu-id="c1159-106">You should avoid this practice, because results are unpredictable.</span></span>  
  
 <span data-ttu-id="c1159-107">如果需要第二个中的消息具有不同的对象的副本，应将第一条消息或消息部分分配给第二个消息或消息部分。</span><span class="sxs-lookup"><span data-stu-id="c1159-107">If you need your second message to have a distinct copy of the object, you should assign the first message or message part to the second message or message part.</span></span>  
  
 <span data-ttu-id="c1159-108">请看下面的示例：</span><span class="sxs-lookup"><span data-stu-id="c1159-108">Consider the following example:</span></span>  
  
 <span data-ttu-id="c1159-109">错误的处理方式：</span><span class="sxs-lookup"><span data-stu-id="c1159-109">Wrong way:</span></span>  
  
```  
myMsg1 = myObj; // assign the first message  
myMsg2 = myObj; // assign the second message (wrong!)  
myMsg2.myInt = 100; // modify the second  
myMsg1.myInt = 5;  
```  
  
 <span data-ttu-id="c1159-110">在这种情况下，myMsg2.myInt 已被覆盖，并且现在具有值 5。</span><span class="sxs-lookup"><span data-stu-id="c1159-110">In this case, myMsg2.myInt has been overwritten, and now has the value 5.</span></span>  
  
 <span data-ttu-id="c1159-111">正确的方式：</span><span class="sxs-lookup"><span data-stu-id="c1159-111">Right way:</span></span>  
  
```  
myMsg1 = myObj; // assign the first message  
myMsg2 = myMsg1; // assign the second message (right!)  
myMsg2.myInt = 100; // modify the second  
myMsg1.myInt = 5;  
```  
  
 <span data-ttu-id="c1159-112">在这种情况下，myMsg2.myInt 仍具有值 100，按预期方式。</span><span class="sxs-lookup"><span data-stu-id="c1159-112">In this case, myMsg2.myInt still has the value 100, as expected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1159-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="c1159-113">See Also</span></span>  
 [<span data-ttu-id="c1159-114">构造消息</span><span class="sxs-lookup"><span data-stu-id="c1159-114">Constructing Messages</span></span>](../core/constructing-messages.md)