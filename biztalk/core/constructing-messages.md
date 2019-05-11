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
# <a name="constructing-messages"></a><span data-ttu-id="8d186-102">构造消息</span><span class="sxs-lookup"><span data-stu-id="8d186-102">Constructing Messages</span></span>
<span data-ttu-id="8d186-103">在构造消息任何时候您引入到您的业务流程，一条消息由接收它或者将值分配给消息变量。</span><span class="sxs-lookup"><span data-stu-id="8d186-103">You construct a message any time that you introduce a message into your orchestration, either by receiving it or by assigning values to a message variable.</span></span> <span data-ttu-id="8d186-104">构造的任何消息必须具有消息类型，以便运行时引擎具有自己正在使用的对象的完整说明。</span><span class="sxs-lookup"><span data-stu-id="8d186-104">Any message that you construct must have a message type, so that the runtime engine has a complete description of the object that it is working with.</span></span> <span data-ttu-id="8d186-105">多部分消息类型可以是用户定义，它可以是.NET 类，也可以是一个架构。</span><span class="sxs-lookup"><span data-stu-id="8d186-105">The multi-part message type can be user-defined, it can be a .NET class, or it can be a schema.</span></span> <span data-ttu-id="8d186-106">您可以构造消息以各种方式： 您可以调用.NET 类来创建一条消息、 将一条消息分配给另一个，或使用转换来将一条消息中的某些值映射到另一个消息中的值。</span><span class="sxs-lookup"><span data-stu-id="8d186-106">You can construct messages in various ways: you can invoke a .NET class to create a message, assign one message to another, or use a transform to map certain values within a message to values within another message.</span></span> <span data-ttu-id="8d186-107">接收操作或当您的业务流程接受消息作为参数时也被构造的消息。</span><span class="sxs-lookup"><span data-stu-id="8d186-107">Messages are also constructed by a receive action or when your orchestration accepts a message as a parameter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8d186-108">多部分消息类型不一定包含多个部分;它可能只包含一个。</span><span class="sxs-lookup"><span data-stu-id="8d186-108">A multi-part message type does not necessarily contain multiple parts; it might contain just one.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8d186-109">消息是不可改变在 BizTalk 中;也就是说，一旦您构造它，不能修改原始。</span><span class="sxs-lookup"><span data-stu-id="8d186-109">Messages are immutable in BizTalk; that is, once you have constructed it, you cannot modify the original.</span></span> <span data-ttu-id="8d186-110">如果需要进行更改，必须构造新消息的副本，并相应地向其分配值。</span><span class="sxs-lookup"><span data-stu-id="8d186-110">If you need to make a change, you must construct a new copy of the message and assign values to it appropriately.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8d186-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="8d186-111">In This Section</span></span>  
 [<span data-ttu-id="8d186-112">如何配置构造消息形状</span><span class="sxs-lookup"><span data-stu-id="8d186-112">How to Configure the Construct Message Shape</span></span>](../core/how-to-configure-the-construct-message-shape.md)  
  
 [<span data-ttu-id="8d186-113">如何配置消息赋值形状</span><span class="sxs-lookup"><span data-stu-id="8d186-113">How to Configure the Message Assignment Shape</span></span>](../core/how-to-configure-the-message-assignment-shape.md) 
  
 [<span data-ttu-id="8d186-114">如何配置转换形状</span><span class="sxs-lookup"><span data-stu-id="8d186-114">How to Configure the Transform Shape</span></span>](../core/how-to-configure-the-transform-shape.md) 
  
 [<span data-ttu-id="8d186-115">“消息赋值”形状中的消息引用</span><span class="sxs-lookup"><span data-stu-id="8d186-115">Message References in Message Assignment Shape</span></span>](../core/message-references-in-message-assignment-shape.md)  
  
 [<span data-ttu-id="8d186-116">用户代码中的消息引用</span><span class="sxs-lookup"><span data-stu-id="8d186-116">Message References in User Code</span></span>](../core/message-references-in-user-code.md)  
  
 [<span data-ttu-id="8d186-117">在消息赋值中使用 XPath</span><span class="sxs-lookup"><span data-stu-id="8d186-117">Using XPaths in Message Assignments</span></span>](../core/using-xpaths-in-message-assignments.md)  
  
 [<span data-ttu-id="8d186-118">在消息赋值中使用非规范化 XPath</span><span class="sxs-lookup"><span data-stu-id="8d186-118">Using Non-Canonical XPaths in Message Assignments</span></span>](../core/using-non-canonical-xpaths-in-message-assignments.md)  
  
 [<span data-ttu-id="8d186-119">在用户代码中构造消息</span><span class="sxs-lookup"><span data-stu-id="8d186-119">Constructing Messages in User Code</span></span>](../core/constructing-messages-in-user-code.md)  
  
 [<span data-ttu-id="8d186-120">向用户代码中的消息追加节点</span><span class="sxs-lookup"><span data-stu-id="8d186-120">Appending Nodes to Messages in User Code</span></span>](../core/appending-nodes-to-messages-in-user-code.md)  
  
## <a name="see-also"></a><span data-ttu-id="8d186-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="8d186-121">See Also</span></span>  
 [<span data-ttu-id="8d186-122">在业务流程中使用消息</span><span class="sxs-lookup"><span data-stu-id="8d186-122">Using Messages in Orchestrations</span></span>](../core/using-messages-in-orchestrations.md)