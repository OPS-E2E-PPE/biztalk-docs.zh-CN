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
# <a name="constructing-messages"></a><span data-ttu-id="fa19e-102">构造消息</span><span class="sxs-lookup"><span data-stu-id="fa19e-102">Constructing Messages</span></span>
<span data-ttu-id="fa19e-103">只要您通过接收消息或为消息变量赋值将消息引入业务流程，就需要构造消息。</span><span class="sxs-lookup"><span data-stu-id="fa19e-103">You construct a message any time that you introduce a message into your orchestration, either by receiving it or by assigning values to a message variable.</span></span> <span data-ttu-id="fa19e-104">您构造的任何消息必须具有消息类型，这样运行时引擎才有所使用的对象的完整说明。</span><span class="sxs-lookup"><span data-stu-id="fa19e-104">Any message that you construct must have a message type, so that the runtime engine has a complete description of the object that it is working with.</span></span> <span data-ttu-id="fa19e-105">多部分消息类型可以是用户定义的，可以是 .NET 类，也可以是架构。</span><span class="sxs-lookup"><span data-stu-id="fa19e-105">The multi-part message type can be user-defined, it can be a .NET class, or it can be a schema.</span></span> <span data-ttu-id="fa19e-106">您可以构造消息以各种方式： 你可以调用一个.NET 类来创建一条消息，将一条消息分配给另一个字符串，或使用转换来将消息中的某些值映射到另一条消息中的值。</span><span class="sxs-lookup"><span data-stu-id="fa19e-106">You can construct messages in various ways: you can invoke a .NET class to create a message, assign one message to another, or use a transform to map certain values within a message to values within another message.</span></span> <span data-ttu-id="fa19e-107">消息还可以由接收操作构造，或者在业务流程将消息作为参数来接受的时候构造。</span><span class="sxs-lookup"><span data-stu-id="fa19e-107">Messages are also constructed by a receive action or when your orchestration accepts a message as a parameter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fa19e-108">多部分消息类型不一定包含多个部分，也可能只包含一个部分。</span><span class="sxs-lookup"><span data-stu-id="fa19e-108">A multi-part message type does not necessarily contain multiple parts; it might contain just one.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fa19e-109">消息在 BizTalk 中是不可改变的，也就是说，在您构造它之后，就不能修改该原始消息了。</span><span class="sxs-lookup"><span data-stu-id="fa19e-109">Messages are immutable in BizTalk; that is, once you have constructed it, you cannot modify the original.</span></span> <span data-ttu-id="fa19e-110">如果需要进行更改，必须构造消息的新副本，并适当地为其赋值。</span><span class="sxs-lookup"><span data-stu-id="fa19e-110">If you need to make a change, you must construct a new copy of the message and assign values to it appropriately.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fa19e-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="fa19e-111">In This Section</span></span>  
 [<span data-ttu-id="fa19e-112">如何配置构造消息形状</span><span class="sxs-lookup"><span data-stu-id="fa19e-112">How to Configure the Construct Message Shape</span></span>](../core/how-to-configure-the-construct-message-shape.md)  
  
 [<span data-ttu-id="fa19e-113">如何配置消息赋值形状</span><span class="sxs-lookup"><span data-stu-id="fa19e-113">How to Configure the Message Assignment Shape</span></span>](../core/how-to-configure-the-message-assignment-shape.md) 
  
 [<span data-ttu-id="fa19e-114">如何配置转换形状</span><span class="sxs-lookup"><span data-stu-id="fa19e-114">How to Configure the Transform Shape</span></span>](../core/how-to-configure-the-transform-shape.md) 
  
 [<span data-ttu-id="fa19e-115">消息赋值形状中的消息引用</span><span class="sxs-lookup"><span data-stu-id="fa19e-115">Message References in Message Assignment Shape</span></span>](../core/message-references-in-message-assignment-shape.md)  
  
 [<span data-ttu-id="fa19e-116">在用户代码中的消息引用</span><span class="sxs-lookup"><span data-stu-id="fa19e-116">Message References in User Code</span></span>](../core/message-references-in-user-code.md)  
  
 [<span data-ttu-id="fa19e-117">在消息分配中使用 Xpath</span><span class="sxs-lookup"><span data-stu-id="fa19e-117">Using XPaths in Message Assignments</span></span>](../core/using-xpaths-in-message-assignments.md)  
  
 [<span data-ttu-id="fa19e-118">在消息分配中使用非规范 Xpath</span><span class="sxs-lookup"><span data-stu-id="fa19e-118">Using Non-Canonical XPaths in Message Assignments</span></span>](../core/using-non-canonical-xpaths-in-message-assignments.md)  
  
 [<span data-ttu-id="fa19e-119">构造在用户代码中的消息</span><span class="sxs-lookup"><span data-stu-id="fa19e-119">Constructing Messages in User Code</span></span>](../core/constructing-messages-in-user-code.md)  
  
 [<span data-ttu-id="fa19e-120">将节点追加到用户代码中的消息</span><span class="sxs-lookup"><span data-stu-id="fa19e-120">Appending Nodes to Messages in User Code</span></span>](../core/appending-nodes-to-messages-in-user-code.md)  
  
## <a name="see-also"></a><span data-ttu-id="fa19e-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fa19e-121">See Also</span></span>  
 [<span data-ttu-id="fa19e-122">在业务流程中使用消息</span><span class="sxs-lookup"><span data-stu-id="fa19e-122">Using Messages in Orchestrations</span></span>](../core/using-messages-in-orchestrations.md)