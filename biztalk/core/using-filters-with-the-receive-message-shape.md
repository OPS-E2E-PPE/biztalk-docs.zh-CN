---
title: "使用筛选器与接收消息形状 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- filters, receive messages
- messages, filters
ms.assetid: 5310039b-6719-4971-933a-2da0573fb5e7
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1434e9704e073cfef1503ef550409e6d6414bb7c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-filters-with-the-receive-message-shape"></a><span data-ttu-id="de66f-102">使用接收消息形状使用筛选器</span><span class="sxs-lookup"><span data-stu-id="de66f-102">Using Filters With the Receive Message Shape</span></span>
<span data-ttu-id="de66f-103">筛选器表达式是可应用于业务流程接收形状的可选参数，它将“激活”属性的值指定为 True。</span><span class="sxs-lookup"><span data-stu-id="de66f-103">A filter expression is an optional parameter that can be applied to an orchestration receive shape that specifies a value of True for the Activate property.</span></span> <span data-ttu-id="de66f-104">如果指定了某一筛选器表达式，则只有当传入消息与该筛选器表达式中指定的条件匹配时，才会激活业务流程。</span><span class="sxs-lookup"><span data-stu-id="de66f-104">If a filter expression is specified then the orchestration will only be activated if an incoming message matches the condition(s) specified in the filter expression.</span></span> <span data-ttu-id="de66f-105">如果没有指定任何筛选器表达式，则业务流程订阅的任何传入消息都将激活该业务流程。</span><span class="sxs-lookup"><span data-stu-id="de66f-105">If no filter expression is specified then any incoming message that the orchestration subscribes to will activate the orchestration.</span></span>  
  
 <span data-ttu-id="de66f-106">若要创建某一筛选器表达式，可以将表达式左侧的传入消息的属性与该表达式右侧的常量进行比较。</span><span class="sxs-lookup"><span data-stu-id="de66f-106">To create a filter expression, you compare a property of an incoming message on the left side of the expression with a constant on the right side of the expression.</span></span> <span data-ttu-id="de66f-107">您还可以通过将 AND 和 OR 运算符应用于两个或多个表达式，创建复合表达式。</span><span class="sxs-lookup"><span data-stu-id="de66f-107">You can also create compound expressions by applying the AND and OR operators to two or more expressions.</span></span> <span data-ttu-id="de66f-108">还可以将筛选器表达式保留为空，在此情况下，将会接受所有消息。</span><span class="sxs-lookup"><span data-stu-id="de66f-108">You can also leave blank the filter expression, in which case all messages will be accepted.</span></span>  
  
 <span data-ttu-id="de66f-109">筛选器表达式可能如下：</span><span class="sxs-lookup"><span data-stu-id="de66f-109">A filter expression might look like the following:</span></span>  
  
```  
InvoiceSchema.Quantity >= 1000  
```  
  
 <span data-ttu-id="de66f-110">在此示例中，将一个传入消息提供给业务流程。</span><span class="sxs-lookup"><span data-stu-id="de66f-110">In this example, an incoming message is presented to the orchestration.</span></span> <span data-ttu-id="de66f-111">该业务流程没有激活**接收**形状 (**激活**属性设置为**True** ，以便收到某些消息会导致业务流程能够运行) 与前面的筛选器表达式应用于它。</span><span class="sxs-lookup"><span data-stu-id="de66f-111">The orchestration has an activation **Receive** shape (the **Activation** property is set to **True** so that receipt of a certain message will cause the orchestration to be run) with the preceding filter expression applied to it.</span></span> <span data-ttu-id="de66f-112">传入的消息应该具有属性的命名空间中调用数量**InvoiceSchema**。</span><span class="sxs-lookup"><span data-stu-id="de66f-112">The incoming message is expected to have property called Quantity in the namespace **InvoiceSchema**.</span></span> <span data-ttu-id="de66f-113">该业务流程只接受 1000 或更多项的发票，因此，运行时引擎将在该业务流程运行前检查传入的消息。</span><span class="sxs-lookup"><span data-stu-id="de66f-113">The orchestration accepts only invoices for 1000 or more items, so the runtime engine checks the incoming message before it runs.</span></span>  
  
 <span data-ttu-id="de66f-114">下表显示您可以在筛选器表达式中使用的运算符。</span><span class="sxs-lookup"><span data-stu-id="de66f-114">The following table shows operators that you can use in filter expressions.</span></span>  
  
|<span data-ttu-id="de66f-115">运算符</span><span class="sxs-lookup"><span data-stu-id="de66f-115">Operator</span></span>|<span data-ttu-id="de66f-116">Description</span><span class="sxs-lookup"><span data-stu-id="de66f-116">Description</span></span>|<span data-ttu-id="de66f-117">示例</span><span class="sxs-lookup"><span data-stu-id="de66f-117">Example</span></span>|  
|--------------|-----------------|-------------|  
|==|<span data-ttu-id="de66f-118">等于</span><span class="sxs-lookup"><span data-stu-id="de66f-118">equal to</span></span>|<span data-ttu-id="de66f-119">ReqMsg(Total) == 100</span><span class="sxs-lookup"><span data-stu-id="de66f-119">ReqMsg(Total) == 100</span></span>|  
|<span data-ttu-id="de66f-120">!=</span><span class="sxs-lookup"><span data-stu-id="de66f-120">!=</span></span>|<span data-ttu-id="de66f-121">不等于</span><span class="sxs-lookup"><span data-stu-id="de66f-121">not equal to</span></span>|<span data-ttu-id="de66f-122">ReqMsg(Total) != 100</span><span class="sxs-lookup"><span data-stu-id="de66f-122">ReqMsg(Total) != 100</span></span>|  
|<|<span data-ttu-id="de66f-123">小于</span><span class="sxs-lookup"><span data-stu-id="de66f-123">less than</span></span>|<span data-ttu-id="de66f-124">ReqMsg(Total) \< 100</span><span class="sxs-lookup"><span data-stu-id="de66f-124">ReqMsg(Total) \< 100</span></span>|  
|>|<span data-ttu-id="de66f-125">大于</span><span class="sxs-lookup"><span data-stu-id="de66f-125">greater than</span></span>|<span data-ttu-id="de66f-126">ReqMsg(Total) > 100</span><span class="sxs-lookup"><span data-stu-id="de66f-126">ReqMsg(Total) > 100</span></span>|  
|<=|<span data-ttu-id="de66f-127">小于或等于</span><span class="sxs-lookup"><span data-stu-id="de66f-127">less than or equal to</span></span>|<span data-ttu-id="de66f-128">ReqMsg(Total) \<= 100</span><span class="sxs-lookup"><span data-stu-id="de66f-128">ReqMsg(Total) \<= 100</span></span>|  
|>=|<span data-ttu-id="de66f-129">大于或等于</span><span class="sxs-lookup"><span data-stu-id="de66f-129">greater than or equal to</span></span>|<span data-ttu-id="de66f-130">ReqMsg(Total) > = 100</span><span class="sxs-lookup"><span data-stu-id="de66f-130">ReqMsg(Total) >= 100</span></span>|  
|<span data-ttu-id="de66f-131">存在</span><span class="sxs-lookup"><span data-stu-id="de66f-131">exists</span></span>|<span data-ttu-id="de66f-132">存在</span><span class="sxs-lookup"><span data-stu-id="de66f-132">exists</span></span>|<span data-ttu-id="de66f-133">ReqMsg(Description) exists</span><span class="sxs-lookup"><span data-stu-id="de66f-133">ReqMsg(Description) exists</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="de66f-134">在筛选表达式中的字符串值括在引号中，例如： reqmsg （description) ="采购订单状态"。</span><span class="sxs-lookup"><span data-stu-id="de66f-134">String values in filter expressions are enclosed in quotation marks, for example: ReqMsg(Description) = "Purchase Order Status".</span></span> <span data-ttu-id="de66f-135">不能在筛选器表达式中使用字符值。</span><span class="sxs-lookup"><span data-stu-id="de66f-135">You cannot use a character value in a filter expression.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="de66f-136">如果您的激活接收与某一直接绑定端口相关联，并且随后发送与在您的筛选器中测试的属性具有相同值的相同类型的消息，将会造成无限循环。</span><span class="sxs-lookup"><span data-stu-id="de66f-136">If your activate receive is associated with a direct-bound port, and you subsequently send a message of the same type with the same value for the property tested in your filter, you will create an infinite loop.</span></span> <span data-ttu-id="de66f-137">消息将发送到 MessageBox，在那里将会再次挑选它，因为该消息与筛选器条件匹配。</span><span class="sxs-lookup"><span data-stu-id="de66f-137">The message will go to the MessageBox, where it will be picked up again because it matches the filter criteria.</span></span> <span data-ttu-id="de66f-138">为了避免这一问题，您应该或者筛选不同属性，发送不同类型的消息，或者确保在发送出同一类型的消息前更改该属性的值。</span><span class="sxs-lookup"><span data-stu-id="de66f-138">To avoid this, you should either filter on a different property, send a message of a different type, or be sure to change the value of the property before sending out a message of the same type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de66f-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="de66f-139">See Also</span></span>  
 <span data-ttu-id="de66f-140">[如何配置接收形状](../core/how-to-configure-the-receive-shape.md) </span><span class="sxs-lookup"><span data-stu-id="de66f-140">[How to Configure the Receive Shape](../core/how-to-configure-the-receive-shape.md) </span></span>  
 <span data-ttu-id="de66f-141">[在业务流程中使用相关性](../core/using-correlations-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="de66f-141">[Using Correlations in Orchestrations](../core/using-correlations-in-orchestrations.md) </span></span>  
 <span data-ttu-id="de66f-142">[使用可分辨的字段和属性字段](../core/using-distinguished-fields-and-property-fields.md) </span><span class="sxs-lookup"><span data-stu-id="de66f-142">[Using Distinguished Fields and Property Fields](../core/using-distinguished-fields-and-property-fields.md) </span></span>  
 [<span data-ttu-id="de66f-143">在业务流程中使用消息</span><span class="sxs-lookup"><span data-stu-id="de66f-143">Using Messages in Orchestrations</span></span>](../core/using-messages-in-orchestrations.md)