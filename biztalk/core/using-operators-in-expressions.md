---
title: "在表达式中使用运算符 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, operators
- XLANG/s, operators
- orchestrations, XLANG/s
ms.assetid: f0948ce2-c508-48aa-af79-d207f577b22f
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 155aad11ecddd021b8e16892b5a5294087fedd4d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-operators-in-expressions"></a><span data-ttu-id="4836b-102">在表达式中使用运算符</span><span class="sxs-lookup"><span data-stu-id="4836b-102">Using Operators in Expressions</span></span>
<span data-ttu-id="4836b-103">以下 XLANG/s 运算符可用于业务流程表达式。</span><span class="sxs-lookup"><span data-stu-id="4836b-103">The following XLANG/s operators are available for use in orchestration expressions.</span></span> <span data-ttu-id="4836b-104">这些运算符与 C# 中相应运算符的功能基本一致。</span><span class="sxs-lookup"><span data-stu-id="4836b-104">They adhere closely to the functionality of the corresponding operators in C#.</span></span>  
  
|<span data-ttu-id="4836b-105">运算符</span><span class="sxs-lookup"><span data-stu-id="4836b-105">Operator</span></span>|<span data-ttu-id="4836b-106">Description</span><span class="sxs-lookup"><span data-stu-id="4836b-106">Description</span></span>|<span data-ttu-id="4836b-107">示例</span><span class="sxs-lookup"><span data-stu-id="4836b-107">Example</span></span>|  
|--------------|-----------------|-------------|  
|<span data-ttu-id="4836b-108">checked()</span><span class="sxs-lookup"><span data-stu-id="4836b-108">checked()</span></span>|<span data-ttu-id="4836b-109">在算术溢出时引发错误</span><span class="sxs-lookup"><span data-stu-id="4836b-109">raise error on arithmetic overflow</span></span>|<span data-ttu-id="4836b-110">检查 (x = y * 1000年)</span><span class="sxs-lookup"><span data-stu-id="4836b-110">checked(x = y * 1000)</span></span>|  
|<span data-ttu-id="4836b-111">unchecked()</span><span class="sxs-lookup"><span data-stu-id="4836b-111">unchecked()</span></span>|<span data-ttu-id="4836b-112">忽略算术溢出</span><span class="sxs-lookup"><span data-stu-id="4836b-112">ignore arithmetic overflow</span></span>|<span data-ttu-id="4836b-113">未选中状态 (x = y * 1000年)</span><span class="sxs-lookup"><span data-stu-id="4836b-113">unchecked(x = y * 1000)</span></span>|  
|<span data-ttu-id="4836b-114">新</span><span class="sxs-lookup"><span data-stu-id="4836b-114">new</span></span>|<span data-ttu-id="4836b-115">创建类的实例</span><span class="sxs-lookup"><span data-stu-id="4836b-115">create an instance of a class</span></span>|<span data-ttu-id="4836b-116">myObject = 新 MyClass;</span><span class="sxs-lookup"><span data-stu-id="4836b-116">myObject = new MyClass;</span></span>|  
|<span data-ttu-id="4836b-117">typeof</span><span class="sxs-lookup"><span data-stu-id="4836b-117">typeof</span></span>|<span data-ttu-id="4836b-118">类型检索</span><span class="sxs-lookup"><span data-stu-id="4836b-118">Type retrieval</span></span>|<span data-ttu-id="4836b-119">myMapType = typeof(myMap)</span><span class="sxs-lookup"><span data-stu-id="4836b-119">myMapType = typeof(myMap)</span></span>|  
|<span data-ttu-id="4836b-120">succeeded()</span><span class="sxs-lookup"><span data-stu-id="4836b-120">succeeded()</span></span>|<span data-ttu-id="4836b-121">测试事务作用域或业务流程是否已经成功完成</span><span class="sxs-lookup"><span data-stu-id="4836b-121">test for successful completion of transactional scope or orchestration</span></span>|<span data-ttu-id="4836b-122">成功 (\<子事务的当前作用域或服务的事务 ID >)</span><span class="sxs-lookup"><span data-stu-id="4836b-122">succeeded(\<transaction ID for child transaction of current scope or service>)</span></span>|  
|<span data-ttu-id="4836b-123">存在</span><span class="sxs-lookup"><span data-stu-id="4836b-123">exists</span></span>|<span data-ttu-id="4836b-124">测试是否存在某个消息上下文属性</span><span class="sxs-lookup"><span data-stu-id="4836b-124">test for the existence of a message context property</span></span>|<span data-ttu-id="4836b-125">BTS。RetryCount 存在 Message_In</span><span class="sxs-lookup"><span data-stu-id="4836b-125">BTS.RetryCount exists Message_In</span></span>|  
|+|<span data-ttu-id="4836b-126">一元加</span><span class="sxs-lookup"><span data-stu-id="4836b-126">unary plus</span></span>|<span data-ttu-id="4836b-127">+(int x)</span><span class="sxs-lookup"><span data-stu-id="4836b-127">+(int x)</span></span>|  
|-|<span data-ttu-id="4836b-128">一元减</span><span class="sxs-lookup"><span data-stu-id="4836b-128">unary minus</span></span>|<span data-ttu-id="4836b-129">-(int x)</span><span class="sxs-lookup"><span data-stu-id="4836b-129">-(int x)</span></span>|  
|<span data-ttu-id="4836b-130">!</span><span class="sxs-lookup"><span data-stu-id="4836b-130">!</span></span>|<span data-ttu-id="4836b-131">逻辑求反</span><span class="sxs-lookup"><span data-stu-id="4836b-131">logical negation</span></span>|<span data-ttu-id="4836b-132">！ myBool</span><span class="sxs-lookup"><span data-stu-id="4836b-132">!myBool</span></span>|  
|~|<span data-ttu-id="4836b-133">按位求补</span><span class="sxs-lookup"><span data-stu-id="4836b-133">bitwise complement</span></span>|<span data-ttu-id="4836b-134">x = ~ y</span><span class="sxs-lookup"><span data-stu-id="4836b-134">x = ~y</span></span>|  
|<span data-ttu-id="4836b-135">()</span><span class="sxs-lookup"><span data-stu-id="4836b-135">()</span></span>|<span data-ttu-id="4836b-136">强制转换</span><span class="sxs-lookup"><span data-stu-id="4836b-136">cast</span></span>|<span data-ttu-id="4836b-137">(bool) myInt</span><span class="sxs-lookup"><span data-stu-id="4836b-137">(bool) myInt</span></span>|  
|*|<span data-ttu-id="4836b-138">times</span><span class="sxs-lookup"><span data-stu-id="4836b-138">times</span></span>|<span data-ttu-id="4836b-139">权重 = MyMsg.numOrders * 20</span><span class="sxs-lookup"><span data-stu-id="4836b-139">Weight = MyMsg.numOrders * 20</span></span>|  
|/|<span data-ttu-id="4836b-140">除以</span><span class="sxs-lookup"><span data-stu-id="4836b-140">divided by</span></span>|<span data-ttu-id="4836b-141">x / y</span><span class="sxs-lookup"><span data-stu-id="4836b-141">x / y</span></span>|  
|+|<span data-ttu-id="4836b-142">加</span><span class="sxs-lookup"><span data-stu-id="4836b-142">plus</span></span>|<span data-ttu-id="4836b-143">x + y</span><span class="sxs-lookup"><span data-stu-id="4836b-143">x + y</span></span>|  
|-|<span data-ttu-id="4836b-144">减号</span><span class="sxs-lookup"><span data-stu-id="4836b-144">minus</span></span>|<span data-ttu-id="4836b-145">x-y</span><span class="sxs-lookup"><span data-stu-id="4836b-145">x - y</span></span>|  
|<<|<span data-ttu-id="4836b-146">左移</span><span class="sxs-lookup"><span data-stu-id="4836b-146">shift left</span></span>|<span data-ttu-id="4836b-147">x <\< 2</span><span class="sxs-lookup"><span data-stu-id="4836b-147">x <\< 2</span></span>|  
|>>|<span data-ttu-id="4836b-148">右移</span><span class="sxs-lookup"><span data-stu-id="4836b-148">shift right</span></span>|<span data-ttu-id="4836b-149">x >> 2</span><span class="sxs-lookup"><span data-stu-id="4836b-149">x >> 2</span></span>|  
|<|<span data-ttu-id="4836b-150">小于</span><span class="sxs-lookup"><span data-stu-id="4836b-150">less than</span></span>|<span data-ttu-id="4836b-151">如果 (MyMsg.numOrders \< 10)...</span><span class="sxs-lookup"><span data-stu-id="4836b-151">If (MyMsg.numOrders \< 10)...</span></span>|  
|>|<span data-ttu-id="4836b-152">大于</span><span class="sxs-lookup"><span data-stu-id="4836b-152">greater than</span></span>|<span data-ttu-id="4836b-153">如果 (MyMsg.numOrders > 10)...</span><span class="sxs-lookup"><span data-stu-id="4836b-153">If (MyMsg.numOrders > 10)...</span></span>|  
|<=|<span data-ttu-id="4836b-154">小于或等于</span><span class="sxs-lookup"><span data-stu-id="4836b-154">less than or equal to</span></span>|<span data-ttu-id="4836b-155">如果 (MyMsg.numOrders \<= 10)...</span><span class="sxs-lookup"><span data-stu-id="4836b-155">If (MyMsg.numOrders \<= 10)...</span></span>|  
|>=|<span data-ttu-id="4836b-156">大于或等于</span><span class="sxs-lookup"><span data-stu-id="4836b-156">greater than or equal to</span></span>|<span data-ttu-id="4836b-157">如果 (MyMsg.numOrders > = 10)...</span><span class="sxs-lookup"><span data-stu-id="4836b-157">If (MyMsg.numOrders >= 10)...</span></span>|  
|==|<span data-ttu-id="4836b-158">等于</span><span class="sxs-lookup"><span data-stu-id="4836b-158">equal to</span></span>|<span data-ttu-id="4836b-159">如果 (MyMsg.numOrders = = 10)...</span><span class="sxs-lookup"><span data-stu-id="4836b-159">If (MyMsg.numOrders == 10)...</span></span>|  
|<span data-ttu-id="4836b-160">!=</span><span class="sxs-lookup"><span data-stu-id="4836b-160">!=</span></span>|<span data-ttu-id="4836b-161">不等于</span><span class="sxs-lookup"><span data-stu-id="4836b-161">not equal to</span></span>|<span data-ttu-id="4836b-162">如果 (MyMsg.numOrders ！ = 10)...</span><span class="sxs-lookup"><span data-stu-id="4836b-162">If (MyMsg.numOrders != 10)...</span></span>|  
|&|<span data-ttu-id="4836b-163">和</span><span class="sxs-lookup"><span data-stu-id="4836b-163">and</span></span>|<span data-ttu-id="4836b-164">如果 (myByte 和 255)...</span><span class="sxs-lookup"><span data-stu-id="4836b-164">If (myByte & 255)...</span></span>|  
|^|<span data-ttu-id="4836b-165">异或</span><span class="sxs-lookup"><span data-stu-id="4836b-165">exclusive or</span></span>|<span data-ttu-id="4836b-166">If (myByte ^ 1)...</span><span class="sxs-lookup"><span data-stu-id="4836b-166">If (myByte ^ 1)...</span></span>|  
|<span data-ttu-id="4836b-167">&#124;</span><span class="sxs-lookup"><span data-stu-id="4836b-167">&#124;</span></span>|<span data-ttu-id="4836b-168">或</span><span class="sxs-lookup"><span data-stu-id="4836b-168">or</span></span>|<span data-ttu-id="4836b-169">如果 (myByte &#124; 1)...</span><span class="sxs-lookup"><span data-stu-id="4836b-169">If (myByte &#124; 1)...</span></span>|  
|&&|<span data-ttu-id="4836b-170">条件与</span><span class="sxs-lookup"><span data-stu-id="4836b-170">conditional and</span></span>|<span data-ttu-id="4836b-171">如果 (MyMsg.numOrders > 10) （& a) （& a) (MyMsg.numOrders < 100)</span><span class="sxs-lookup"><span data-stu-id="4836b-171">If (MyMsg.numOrders > 10) && (MyMsg.numOrders < 100)</span></span>|  
|<span data-ttu-id="4836b-172">&#124;&#124;</span><span class="sxs-lookup"><span data-stu-id="4836b-172">&#124;&#124;</span></span>|<span data-ttu-id="4836b-173">条件或</span><span class="sxs-lookup"><span data-stu-id="4836b-173">conditional or</span></span>|<span data-ttu-id="4836b-174">如果 (MyMsg.numOrders \< 10) &#124; &#124;(MyMsg.numOrders > 100)</span><span class="sxs-lookup"><span data-stu-id="4836b-174">If (MyMsg.numOrders \< 10) &#124;&#124; (MyMsg.numOrders > 100)</span></span>|  
|//|<span data-ttu-id="4836b-175">注释</span><span class="sxs-lookup"><span data-stu-id="4836b-175">commenting</span></span>|<span data-ttu-id="4836b-176">//This is the comment</span><span class="sxs-lookup"><span data-stu-id="4836b-176">//This is the comment</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="4836b-177">常规表达式和一起使用的筛选器表达式之间有所不同，规则**接收**形状。</span><span class="sxs-lookup"><span data-stu-id="4836b-177">The rules differ between general expressions and filter expressions that are used with the **Receive** shape.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4836b-178">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4836b-178">See Also</span></span>  
 [<span data-ttu-id="4836b-179">使用接收消息形状使用筛选器</span><span class="sxs-lookup"><span data-stu-id="4836b-179">Using Filters With the Receive Message Shape</span></span>](../core/using-filters-with-the-receive-message-shape.md)