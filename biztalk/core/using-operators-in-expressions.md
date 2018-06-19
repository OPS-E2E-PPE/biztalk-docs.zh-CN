---
title: 在表达式中使用运算符 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, operators
- XLANG/s, operators
- orchestrations, XLANG/s
ms.assetid: f0948ce2-c508-48aa-af79-d207f577b22f
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5aec9ed6ebecb0b151dbfe9d5c09707b954fdf45
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25974299"
---
# <a name="using-operators-in-expressions"></a><span data-ttu-id="cc596-102">在表达式中使用运算符</span><span class="sxs-lookup"><span data-stu-id="cc596-102">Using Operators in Expressions</span></span>
<span data-ttu-id="cc596-103">以下 XLANG/s 运算符可用于业务流程表达式。</span><span class="sxs-lookup"><span data-stu-id="cc596-103">The following XLANG/s operators are available for use in orchestration expressions.</span></span> <span data-ttu-id="cc596-104">这些运算符与 C# 中相应运算符的功能基本一致。</span><span class="sxs-lookup"><span data-stu-id="cc596-104">They adhere closely to the functionality of the corresponding operators in C#.</span></span>  
  
|<span data-ttu-id="cc596-105">运算符</span><span class="sxs-lookup"><span data-stu-id="cc596-105">Operator</span></span>|<span data-ttu-id="cc596-106">Description</span><span class="sxs-lookup"><span data-stu-id="cc596-106">Description</span></span>|<span data-ttu-id="cc596-107">示例</span><span class="sxs-lookup"><span data-stu-id="cc596-107">Example</span></span>|  
|--------------|-----------------|-------------|  
|<span data-ttu-id="cc596-108">checked()</span><span class="sxs-lookup"><span data-stu-id="cc596-108">checked()</span></span>|<span data-ttu-id="cc596-109">在算术溢出时引发错误</span><span class="sxs-lookup"><span data-stu-id="cc596-109">raise error on arithmetic overflow</span></span>|<span data-ttu-id="cc596-110">检查 (x = y \* 1000年)</span><span class="sxs-lookup"><span data-stu-id="cc596-110">checked(x = y \* 1000)</span></span>|  
|<span data-ttu-id="cc596-111">unchecked()</span><span class="sxs-lookup"><span data-stu-id="cc596-111">unchecked()</span></span>|<span data-ttu-id="cc596-112">忽略算术溢出</span><span class="sxs-lookup"><span data-stu-id="cc596-112">ignore arithmetic overflow</span></span>|<span data-ttu-id="cc596-113">未选中状态 (x = y \* 1000年)</span><span class="sxs-lookup"><span data-stu-id="cc596-113">unchecked(x = y \* 1000)</span></span>|  
|<span data-ttu-id="cc596-114">新</span><span class="sxs-lookup"><span data-stu-id="cc596-114">new</span></span>|<span data-ttu-id="cc596-115">创建类的实例</span><span class="sxs-lookup"><span data-stu-id="cc596-115">create an instance of a class</span></span>|<span data-ttu-id="cc596-116">myObject = 新 MyClass;</span><span class="sxs-lookup"><span data-stu-id="cc596-116">myObject = new MyClass;</span></span>|  
|<span data-ttu-id="cc596-117">typeof</span><span class="sxs-lookup"><span data-stu-id="cc596-117">typeof</span></span>|<span data-ttu-id="cc596-118">类型检索</span><span class="sxs-lookup"><span data-stu-id="cc596-118">Type retrieval</span></span>|<span data-ttu-id="cc596-119">myMapType = typeof(myMap)</span><span class="sxs-lookup"><span data-stu-id="cc596-119">myMapType = typeof(myMap)</span></span>|  
|<span data-ttu-id="cc596-120">succeeded()</span><span class="sxs-lookup"><span data-stu-id="cc596-120">succeeded()</span></span>|<span data-ttu-id="cc596-121">测试事务作用域或业务流程是否已经成功完成</span><span class="sxs-lookup"><span data-stu-id="cc596-121">test for successful completion of transactional scope or orchestration</span></span>|<span data-ttu-id="cc596-122">成功 (\<子事务的当前作用域或服务的事务 ID\>)</span><span class="sxs-lookup"><span data-stu-id="cc596-122">succeeded(\<transaction ID for child transaction of current scope or service\>)</span></span>|  
|<span data-ttu-id="cc596-123">存在</span><span class="sxs-lookup"><span data-stu-id="cc596-123">exists</span></span>|<span data-ttu-id="cc596-124">测试是否存在某个消息上下文属性</span><span class="sxs-lookup"><span data-stu-id="cc596-124">test for the existence of a message context property</span></span>|<span data-ttu-id="cc596-125">BTS。RetryCount 存在 Message_In</span><span class="sxs-lookup"><span data-stu-id="cc596-125">BTS.RetryCount exists Message_In</span></span>|  
|+|<span data-ttu-id="cc596-126">一元加</span><span class="sxs-lookup"><span data-stu-id="cc596-126">unary plus</span></span>|<span data-ttu-id="cc596-127">+(int x)</span><span class="sxs-lookup"><span data-stu-id="cc596-127">+(int x)</span></span>|  
|-|<span data-ttu-id="cc596-128">一元减</span><span class="sxs-lookup"><span data-stu-id="cc596-128">unary minus</span></span>|<span data-ttu-id="cc596-129">-(int x)</span><span class="sxs-lookup"><span data-stu-id="cc596-129">-(int x)</span></span>|  
|<span data-ttu-id="cc596-130">!</span><span class="sxs-lookup"><span data-stu-id="cc596-130">!</span></span>|<span data-ttu-id="cc596-131">逻辑求反</span><span class="sxs-lookup"><span data-stu-id="cc596-131">logical negation</span></span>|<span data-ttu-id="cc596-132">！ myBool</span><span class="sxs-lookup"><span data-stu-id="cc596-132">!myBool</span></span>|  
|~|<span data-ttu-id="cc596-133">按位求补</span><span class="sxs-lookup"><span data-stu-id="cc596-133">bitwise complement</span></span>|<span data-ttu-id="cc596-134">x = ~ y</span><span class="sxs-lookup"><span data-stu-id="cc596-134">x = ~y</span></span>|  
|<span data-ttu-id="cc596-135">()</span><span class="sxs-lookup"><span data-stu-id="cc596-135">()</span></span>|<span data-ttu-id="cc596-136">强制转换</span><span class="sxs-lookup"><span data-stu-id="cc596-136">cast</span></span>|<span data-ttu-id="cc596-137">(bool) myInt</span><span class="sxs-lookup"><span data-stu-id="cc596-137">(bool) myInt</span></span>|  
|*|<span data-ttu-id="cc596-138">times</span><span class="sxs-lookup"><span data-stu-id="cc596-138">times</span></span>|<span data-ttu-id="cc596-139">权重 = MyMsg.numOrders \* 20</span><span class="sxs-lookup"><span data-stu-id="cc596-139">Weight = MyMsg.numOrders \* 20</span></span>|  
|/|<span data-ttu-id="cc596-140">除以</span><span class="sxs-lookup"><span data-stu-id="cc596-140">divided by</span></span>|<span data-ttu-id="cc596-141">x / y</span><span class="sxs-lookup"><span data-stu-id="cc596-141">x / y</span></span>|  
|+|<span data-ttu-id="cc596-142">加</span><span class="sxs-lookup"><span data-stu-id="cc596-142">plus</span></span>|<span data-ttu-id="cc596-143">x + y</span><span class="sxs-lookup"><span data-stu-id="cc596-143">x + y</span></span>|  
|-|<span data-ttu-id="cc596-144">减号</span><span class="sxs-lookup"><span data-stu-id="cc596-144">minus</span></span>|<span data-ttu-id="cc596-145">x-y</span><span class="sxs-lookup"><span data-stu-id="cc596-145">x - y</span></span>|  
|<<|<span data-ttu-id="cc596-146">左移</span><span class="sxs-lookup"><span data-stu-id="cc596-146">shift left</span></span>|<span data-ttu-id="cc596-147">x << 2</span><span class="sxs-lookup"><span data-stu-id="cc596-147">x << 2</span></span>|  
|>>|<span data-ttu-id="cc596-148">右移</span><span class="sxs-lookup"><span data-stu-id="cc596-148">shift right</span></span>|<span data-ttu-id="cc596-149">x >> 2</span><span class="sxs-lookup"><span data-stu-id="cc596-149">x >> 2</span></span>|  
|<|<span data-ttu-id="cc596-150">小于</span><span class="sxs-lookup"><span data-stu-id="cc596-150">less than</span></span>|<span data-ttu-id="cc596-151">如果 (MyMsg.numOrders < 10)...</span><span class="sxs-lookup"><span data-stu-id="cc596-151">If (MyMsg.numOrders < 10)...</span></span>|  
|>|<span data-ttu-id="cc596-152">大于</span><span class="sxs-lookup"><span data-stu-id="cc596-152">greater than</span></span>|<span data-ttu-id="cc596-153">如果 (MyMsg.numOrders > 10)...</span><span class="sxs-lookup"><span data-stu-id="cc596-153">If (MyMsg.numOrders > 10)...</span></span>|  
|<=|<span data-ttu-id="cc596-154">小于或等于</span><span class="sxs-lookup"><span data-stu-id="cc596-154">less than or equal to</span></span>|<span data-ttu-id="cc596-155">如果 (MyMsg.numOrders < = 10)...</span><span class="sxs-lookup"><span data-stu-id="cc596-155">If (MyMsg.numOrders <= 10)...</span></span>|  
|>=|<span data-ttu-id="cc596-156">大于或等于</span><span class="sxs-lookup"><span data-stu-id="cc596-156">greater than or equal to</span></span>|<span data-ttu-id="cc596-157">如果 (MyMsg.numOrders > = 10)...</span><span class="sxs-lookup"><span data-stu-id="cc596-157">If (MyMsg.numOrders >= 10)...</span></span>|  
|==|<span data-ttu-id="cc596-158">等于</span><span class="sxs-lookup"><span data-stu-id="cc596-158">equal to</span></span>|<span data-ttu-id="cc596-159">如果 (MyMsg.numOrders = = 10)...</span><span class="sxs-lookup"><span data-stu-id="cc596-159">If (MyMsg.numOrders == 10)...</span></span>|  
|<span data-ttu-id="cc596-160">!=</span><span class="sxs-lookup"><span data-stu-id="cc596-160">!=</span></span>|<span data-ttu-id="cc596-161">不等于</span><span class="sxs-lookup"><span data-stu-id="cc596-161">not equal to</span></span>|<span data-ttu-id="cc596-162">如果 (MyMsg.numOrders ！ = 10)...</span><span class="sxs-lookup"><span data-stu-id="cc596-162">If (MyMsg.numOrders != 10)...</span></span>|  
|&|<span data-ttu-id="cc596-163">和</span><span class="sxs-lookup"><span data-stu-id="cc596-163">and</span></span>|<span data-ttu-id="cc596-164">如果 (myByte 和 255)...</span><span class="sxs-lookup"><span data-stu-id="cc596-164">If (myByte & 255)...</span></span>|  
|^|<span data-ttu-id="cc596-165">异或</span><span class="sxs-lookup"><span data-stu-id="cc596-165">exclusive or</span></span>|<span data-ttu-id="cc596-166">If (myByte ^ 1)...</span><span class="sxs-lookup"><span data-stu-id="cc596-166">If (myByte ^ 1)...</span></span>|  
|<span data-ttu-id="cc596-167">&#124;</span><span class="sxs-lookup"><span data-stu-id="cc596-167">&#124;</span></span>|<span data-ttu-id="cc596-168">或</span><span class="sxs-lookup"><span data-stu-id="cc596-168">or</span></span>|<span data-ttu-id="cc596-169">如果 (myByte &#124; 1)...</span><span class="sxs-lookup"><span data-stu-id="cc596-169">If (myByte &#124; 1)...</span></span>|  
|&&|<span data-ttu-id="cc596-170">条件与</span><span class="sxs-lookup"><span data-stu-id="cc596-170">conditional and</span></span>|<span data-ttu-id="cc596-171">如果 (MyMsg.numOrders > 10) （& a) （& a) (MyMsg.numOrders < 100)</span><span class="sxs-lookup"><span data-stu-id="cc596-171">If (MyMsg.numOrders > 10) && (MyMsg.numOrders < 100)</span></span>|  
|<span data-ttu-id="cc596-172">&#124;&#124;</span><span class="sxs-lookup"><span data-stu-id="cc596-172">&#124;&#124;</span></span>|<span data-ttu-id="cc596-173">条件或</span><span class="sxs-lookup"><span data-stu-id="cc596-173">conditional or</span></span>|<span data-ttu-id="cc596-174">如果 (MyMsg.numOrders < 10) &#124; &#124;(MyMsg.numOrders > 100)</span><span class="sxs-lookup"><span data-stu-id="cc596-174">If (MyMsg.numOrders < 10) &#124;&#124; (MyMsg.numOrders > 100)</span></span>|  
|//|<span data-ttu-id="cc596-175">注释</span><span class="sxs-lookup"><span data-stu-id="cc596-175">commenting</span></span>|<span data-ttu-id="cc596-176">//This is the comment</span><span class="sxs-lookup"><span data-stu-id="cc596-176">//This is the comment</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="cc596-177">常规表达式和一起使用的筛选器表达式之间有所不同，规则**接收**形状。</span><span class="sxs-lookup"><span data-stu-id="cc596-177">The rules differ between general expressions and filter expressions that are used with the **Receive** shape.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc596-178">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cc596-178">See Also</span></span>  
 [<span data-ttu-id="cc596-179">使用带接收消息形状的筛选器</span><span class="sxs-lookup"><span data-stu-id="cc596-179">Using Filters With the Receive Message Shape</span></span>](../core/using-filters-with-the-receive-message-shape.md)