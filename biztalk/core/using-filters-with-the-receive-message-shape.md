---
title: 接收消息形状中使用筛选器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- filters, receive messages
- messages, filters
ms.assetid: 5310039b-6719-4971-933a-2da0573fb5e7
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58c0ed34645fc7b576a76092c676d4eb4c390020
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65246424"
---
# <a name="using-filters-with-the-receive-message-shape"></a><span data-ttu-id="7cf2c-102">接收消息形状中使用筛选器</span><span class="sxs-lookup"><span data-stu-id="7cf2c-102">Using Filters With the Receive Message Shape</span></span>
<span data-ttu-id="7cf2c-103">筛选器表达式是一个可选参数，可以应用于业务流程接收形状指定值的激活属性，则返回 True。</span><span class="sxs-lookup"><span data-stu-id="7cf2c-103">A filter expression is an optional parameter that can be applied to an orchestration receive shape that specifies a value of True for the Activate property.</span></span> <span data-ttu-id="7cf2c-104">如果指定了筛选器表达式然后业务流程将仅激活如果传入消息与筛选器表达式中指定的条件相匹配。</span><span class="sxs-lookup"><span data-stu-id="7cf2c-104">If a filter expression is specified then the orchestration will only be activated if an incoming message matches the condition(s) specified in the filter expression.</span></span> <span data-ttu-id="7cf2c-105">如果不指定任何筛选器表达式，则业务流程订阅任何传入消息将激活业务流程。</span><span class="sxs-lookup"><span data-stu-id="7cf2c-105">If no filter expression is specified then any incoming message that the orchestration subscribes to will activate the orchestration.</span></span>  
  
 <span data-ttu-id="7cf2c-106">若要创建筛选器表达式，进行比较的表达式右侧的常量表达式左侧的传入消息的属性。</span><span class="sxs-lookup"><span data-stu-id="7cf2c-106">To create a filter expression, you compare a property of an incoming message on the left side of the expression with a constant on the right side of the expression.</span></span> <span data-ttu-id="7cf2c-107">此外可以创建复合表达式，通过应用 AND 和 OR 运算符对两个或多个表达式。</span><span class="sxs-lookup"><span data-stu-id="7cf2c-107">You can also create compound expressions by applying the AND and OR operators to two or more expressions.</span></span> <span data-ttu-id="7cf2c-108">您也可以将空白筛选器表达式中，在这种情况下将接受所有消息。</span><span class="sxs-lookup"><span data-stu-id="7cf2c-108">You can also leave blank the filter expression, in which case all messages will be accepted.</span></span>  
  
 <span data-ttu-id="7cf2c-109">筛选器表达式可能如下所示：</span><span class="sxs-lookup"><span data-stu-id="7cf2c-109">A filter expression might look like the following:</span></span>  
  
```  
InvoiceSchema.Quantity >= 1000  
```  
  
 <span data-ttu-id="7cf2c-110">在此示例中，传入消息，提供给业务流程。</span><span class="sxs-lookup"><span data-stu-id="7cf2c-110">In this example, an incoming message is presented to the orchestration.</span></span> <span data-ttu-id="7cf2c-111">业务流程具有激活**接收**形状 (**激活**属性设置为**True** ，以便收到某些消息将导致业务流程，以运行) 与前面的筛选器表达式应用于它。</span><span class="sxs-lookup"><span data-stu-id="7cf2c-111">The orchestration has an activation **Receive** shape (the **Activation** property is set to **True** so that receipt of a certain message will cause the orchestration to be run) with the preceding filter expression applied to it.</span></span> <span data-ttu-id="7cf2c-112">传入消息都必须具有属性的命名空间中名为 Quantity **InvoiceSchema**。</span><span class="sxs-lookup"><span data-stu-id="7cf2c-112">The incoming message is expected to have property called Quantity in the namespace **InvoiceSchema**.</span></span> <span data-ttu-id="7cf2c-113">业务流程接受仅为 1000年或多个项的发票，因此其运行前，运行时引擎将检查传入的消息。</span><span class="sxs-lookup"><span data-stu-id="7cf2c-113">The orchestration accepts only invoices for 1000 or more items, so the runtime engine checks the incoming message before it runs.</span></span>  
  
 <span data-ttu-id="7cf2c-114">下表显示了可以使用筛选器表达式中的多个运算符。</span><span class="sxs-lookup"><span data-stu-id="7cf2c-114">The following table shows operators that you can use in filter expressions.</span></span>  
  
|<span data-ttu-id="7cf2c-115">运算符</span><span class="sxs-lookup"><span data-stu-id="7cf2c-115">Operator</span></span>|<span data-ttu-id="7cf2c-116">Description</span><span class="sxs-lookup"><span data-stu-id="7cf2c-116">Description</span></span>|<span data-ttu-id="7cf2c-117">示例</span><span class="sxs-lookup"><span data-stu-id="7cf2c-117">Example</span></span>|  
|--------------|-----------------|-------------|  
|==|<span data-ttu-id="7cf2c-118">等于</span><span class="sxs-lookup"><span data-stu-id="7cf2c-118">equal to</span></span>|<span data-ttu-id="7cf2c-119">ReqMsg(Total) == 100</span><span class="sxs-lookup"><span data-stu-id="7cf2c-119">ReqMsg(Total) == 100</span></span>|  
|<span data-ttu-id="7cf2c-120">!=</span><span class="sxs-lookup"><span data-stu-id="7cf2c-120">!=</span></span>|<span data-ttu-id="7cf2c-121">不等于</span><span class="sxs-lookup"><span data-stu-id="7cf2c-121">not equal to</span></span>|<span data-ttu-id="7cf2c-122">ReqMsg(Total) != 100</span><span class="sxs-lookup"><span data-stu-id="7cf2c-122">ReqMsg(Total) != 100</span></span>|  
|<|<span data-ttu-id="7cf2c-123">小于</span><span class="sxs-lookup"><span data-stu-id="7cf2c-123">less than</span></span>|<span data-ttu-id="7cf2c-124">ReqMsg(Total) \< 100</span><span class="sxs-lookup"><span data-stu-id="7cf2c-124">ReqMsg(Total) \< 100</span></span>|  
|>|<span data-ttu-id="7cf2c-125">大于</span><span class="sxs-lookup"><span data-stu-id="7cf2c-125">greater than</span></span>|<span data-ttu-id="7cf2c-126">ReqMsg(Total) > 100</span><span class="sxs-lookup"><span data-stu-id="7cf2c-126">ReqMsg(Total) > 100</span></span>|  
|<=|<span data-ttu-id="7cf2c-127">小于或等于</span><span class="sxs-lookup"><span data-stu-id="7cf2c-127">less than or equal to</span></span>|<span data-ttu-id="7cf2c-128">ReqMsg(Total) \<= 100</span><span class="sxs-lookup"><span data-stu-id="7cf2c-128">ReqMsg(Total) \<= 100</span></span>|  
|>=|<span data-ttu-id="7cf2c-129">大于或等于</span><span class="sxs-lookup"><span data-stu-id="7cf2c-129">greater than or equal to</span></span>|<span data-ttu-id="7cf2c-130">ReqMsg(Total) >= 100</span><span class="sxs-lookup"><span data-stu-id="7cf2c-130">ReqMsg(Total) >= 100</span></span>|  
|<span data-ttu-id="7cf2c-131">存在</span><span class="sxs-lookup"><span data-stu-id="7cf2c-131">exists</span></span>|<span data-ttu-id="7cf2c-132">存在</span><span class="sxs-lookup"><span data-stu-id="7cf2c-132">exists</span></span>|<span data-ttu-id="7cf2c-133">Reqmsg （description） 存在</span><span class="sxs-lookup"><span data-stu-id="7cf2c-133">ReqMsg(Description) exists</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="7cf2c-134">在筛选表达式中的字符串值括在引号中，例如：Reqmsg （description) ="Purchase Order Status"。</span><span class="sxs-lookup"><span data-stu-id="7cf2c-134">String values in filter expressions are enclosed in quotation marks, for example: ReqMsg(Description) = "Purchase Order Status".</span></span> <span data-ttu-id="7cf2c-135">不能在筛选器表达式中使用的字符值。</span><span class="sxs-lookup"><span data-stu-id="7cf2c-135">You cannot use a character value in a filter expression.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7cf2c-136">如果您的激活接收程序与直接绑定端口，并随后发送具有相同的值在筛选器中测试的属性的相同类型的消息，将创建一个无限循环。</span><span class="sxs-lookup"><span data-stu-id="7cf2c-136">If your activate receive is associated with a direct-bound port, and you subsequently send a message of the same type with the same value for the property tested in your filter, you will create an infinite loop.</span></span> <span data-ttu-id="7cf2c-137">该消息将转到 MessageBox，其中它将会再次挑选由于它匹配的筛选条件。</span><span class="sxs-lookup"><span data-stu-id="7cf2c-137">The message will go to the MessageBox, where it will be picked up again because it matches the filter criteria.</span></span> <span data-ttu-id="7cf2c-138">若要避免此问题，应该对不同属性进行筛选、 可以发送不同类型的消息，或确保将相同类型的消息发送之前更改属性的值。</span><span class="sxs-lookup"><span data-stu-id="7cf2c-138">To avoid this, you should either filter on a different property, send a message of a different type, or be sure to change the value of the property before sending out a message of the same type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cf2c-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="7cf2c-139">See Also</span></span>  
 <span data-ttu-id="7cf2c-140">[如何配置接收形状](../core/how-to-configure-the-receive-shape.md) </span><span class="sxs-lookup"><span data-stu-id="7cf2c-140">[How to Configure the Receive Shape](../core/how-to-configure-the-receive-shape.md) </span></span>  
 <span data-ttu-id="7cf2c-141">[业务流程中使用的相关性](../core/using-correlations-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="7cf2c-141">[Using Correlations in Orchestrations](../core/using-correlations-in-orchestrations.md) </span></span>  
 <span data-ttu-id="7cf2c-142">[使用可分辨的字段和属性字段](../core/using-distinguished-fields-and-property-fields.md) </span><span class="sxs-lookup"><span data-stu-id="7cf2c-142">[Using Distinguished Fields and Property Fields](../core/using-distinguished-fields-and-property-fields.md) </span></span>  
 [<span data-ttu-id="7cf2c-143">在业务流程中使用消息</span><span class="sxs-lookup"><span data-stu-id="7cf2c-143">Using Messages in Orchestrations</span></span>](../core/using-messages-in-orchestrations.md)