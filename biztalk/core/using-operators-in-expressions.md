---
title: 在表达式中使用运算符 |Microsoft Docs
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
ms.openlocfilehash: acb471fd12ad41776b116b1ed2f27fcfb6ea6f8f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395428"
---
# <a name="using-operators-in-expressions"></a><span data-ttu-id="94d1a-102">在表达式中使用运算符</span><span class="sxs-lookup"><span data-stu-id="94d1a-102">Using Operators in Expressions</span></span>
<span data-ttu-id="94d1a-103">以下 XLANG/s 运算符是可在业务流程表达式中使用。</span><span class="sxs-lookup"><span data-stu-id="94d1a-103">The following XLANG/s operators are available for use in orchestration expressions.</span></span> <span data-ttu-id="94d1a-104">它们紧密遵循 C# 中的相应运算符的功能。</span><span class="sxs-lookup"><span data-stu-id="94d1a-104">They adhere closely to the functionality of the corresponding operators in C#.</span></span>  
  
|<span data-ttu-id="94d1a-105">运算符</span><span class="sxs-lookup"><span data-stu-id="94d1a-105">Operator</span></span>|<span data-ttu-id="94d1a-106">Description</span><span class="sxs-lookup"><span data-stu-id="94d1a-106">Description</span></span>|<span data-ttu-id="94d1a-107">示例</span><span class="sxs-lookup"><span data-stu-id="94d1a-107">Example</span></span>|  
|--------------|-----------------|-------------|  
|<span data-ttu-id="94d1a-108">checked()</span><span class="sxs-lookup"><span data-stu-id="94d1a-108">checked()</span></span>|<span data-ttu-id="94d1a-109">引发在算术溢出错误</span><span class="sxs-lookup"><span data-stu-id="94d1a-109">raise error on arithmetic overflow</span></span>|<span data-ttu-id="94d1a-110">checked(x = y \* 1000)</span><span class="sxs-lookup"><span data-stu-id="94d1a-110">checked(x = y \* 1000)</span></span>|  
|<span data-ttu-id="94d1a-111">unchecked()</span><span class="sxs-lookup"><span data-stu-id="94d1a-111">unchecked()</span></span>|<span data-ttu-id="94d1a-112">忽略算术溢出</span><span class="sxs-lookup"><span data-stu-id="94d1a-112">ignore arithmetic overflow</span></span>|<span data-ttu-id="94d1a-113">unchecked(x = y \* 1000)</span><span class="sxs-lookup"><span data-stu-id="94d1a-113">unchecked(x = y \* 1000)</span></span>|  
|<span data-ttu-id="94d1a-114">新</span><span class="sxs-lookup"><span data-stu-id="94d1a-114">new</span></span>|<span data-ttu-id="94d1a-115">创建一个类的实例</span><span class="sxs-lookup"><span data-stu-id="94d1a-115">create an instance of a class</span></span>|<span data-ttu-id="94d1a-116">匹配大小写 = 新 MyClass;</span><span class="sxs-lookup"><span data-stu-id="94d1a-116">myObject = new MyClass;</span></span>|  
|<span data-ttu-id="94d1a-117">typeof</span><span class="sxs-lookup"><span data-stu-id="94d1a-117">typeof</span></span>|<span data-ttu-id="94d1a-118">类型检索</span><span class="sxs-lookup"><span data-stu-id="94d1a-118">Type retrieval</span></span>|<span data-ttu-id="94d1a-119">myMapType = typeof(myMap)</span><span class="sxs-lookup"><span data-stu-id="94d1a-119">myMapType = typeof(myMap)</span></span>|  
|<span data-ttu-id="94d1a-120">succeeded （)</span><span class="sxs-lookup"><span data-stu-id="94d1a-120">succeeded()</span></span>|<span data-ttu-id="94d1a-121">测试成功完成的事务作用域或业务流程</span><span class="sxs-lookup"><span data-stu-id="94d1a-121">test for successful completion of transactional scope or orchestration</span></span>|<span data-ttu-id="94d1a-122">已成功 (\<的子事务的当前作用域或服务的事务 ID\>)</span><span class="sxs-lookup"><span data-stu-id="94d1a-122">succeeded(\<transaction ID for child transaction of current scope or service\>)</span></span>|  
|<span data-ttu-id="94d1a-123">存在</span><span class="sxs-lookup"><span data-stu-id="94d1a-123">exists</span></span>|<span data-ttu-id="94d1a-124">测试存在的消息上下文属性</span><span class="sxs-lookup"><span data-stu-id="94d1a-124">test for the existence of a message context property</span></span>|<span data-ttu-id="94d1a-125">BTS。RetryCount 存在 Message_In</span><span class="sxs-lookup"><span data-stu-id="94d1a-125">BTS.RetryCount exists Message_In</span></span>|  
|+|<span data-ttu-id="94d1a-126">一元加</span><span class="sxs-lookup"><span data-stu-id="94d1a-126">unary plus</span></span>|<span data-ttu-id="94d1a-127">+(int x)</span><span class="sxs-lookup"><span data-stu-id="94d1a-127">+(int x)</span></span>|  
|-|<span data-ttu-id="94d1a-128">一元负</span><span class="sxs-lookup"><span data-stu-id="94d1a-128">unary minus</span></span>|<span data-ttu-id="94d1a-129">-(int x)</span><span class="sxs-lookup"><span data-stu-id="94d1a-129">-(int x)</span></span>|  
|<span data-ttu-id="94d1a-130">!</span><span class="sxs-lookup"><span data-stu-id="94d1a-130">!</span></span>|<span data-ttu-id="94d1a-131">逻辑求反</span><span class="sxs-lookup"><span data-stu-id="94d1a-131">logical negation</span></span>|<span data-ttu-id="94d1a-132">!myBool</span><span class="sxs-lookup"><span data-stu-id="94d1a-132">!myBool</span></span>|  
|~|<span data-ttu-id="94d1a-133">按位求补</span><span class="sxs-lookup"><span data-stu-id="94d1a-133">bitwise complement</span></span>|<span data-ttu-id="94d1a-134">x = ~y</span><span class="sxs-lookup"><span data-stu-id="94d1a-134">x = ~y</span></span>|  
|<span data-ttu-id="94d1a-135">()</span><span class="sxs-lookup"><span data-stu-id="94d1a-135">()</span></span>|<span data-ttu-id="94d1a-136">强制转换</span><span class="sxs-lookup"><span data-stu-id="94d1a-136">cast</span></span>|<span data-ttu-id="94d1a-137">(bool) myInt</span><span class="sxs-lookup"><span data-stu-id="94d1a-137">(bool) myInt</span></span>|  
|*|<span data-ttu-id="94d1a-138">times</span><span class="sxs-lookup"><span data-stu-id="94d1a-138">times</span></span>|<span data-ttu-id="94d1a-139">Weight = MyMsg.numOrders \* 20</span><span class="sxs-lookup"><span data-stu-id="94d1a-139">Weight = MyMsg.numOrders \* 20</span></span>|  
|/|<span data-ttu-id="94d1a-140">除以</span><span class="sxs-lookup"><span data-stu-id="94d1a-140">divided by</span></span>|<span data-ttu-id="94d1a-141">x / y</span><span class="sxs-lookup"><span data-stu-id="94d1a-141">x / y</span></span>|  
|+|<span data-ttu-id="94d1a-142">Plus</span><span class="sxs-lookup"><span data-stu-id="94d1a-142">plus</span></span>|<span data-ttu-id="94d1a-143">x + y</span><span class="sxs-lookup"><span data-stu-id="94d1a-143">x + y</span></span>|  
|-|<span data-ttu-id="94d1a-144">减号</span><span class="sxs-lookup"><span data-stu-id="94d1a-144">minus</span></span>|<span data-ttu-id="94d1a-145">x - y</span><span class="sxs-lookup"><span data-stu-id="94d1a-145">x - y</span></span>|  
|<<|<span data-ttu-id="94d1a-146">左移</span><span class="sxs-lookup"><span data-stu-id="94d1a-146">shift left</span></span>|<span data-ttu-id="94d1a-147">x << 2</span><span class="sxs-lookup"><span data-stu-id="94d1a-147">x << 2</span></span>|  
|>>|<span data-ttu-id="94d1a-148">右移</span><span class="sxs-lookup"><span data-stu-id="94d1a-148">shift right</span></span>|<span data-ttu-id="94d1a-149">x >> 2</span><span class="sxs-lookup"><span data-stu-id="94d1a-149">x >> 2</span></span>|  
|<|<span data-ttu-id="94d1a-150">小于</span><span class="sxs-lookup"><span data-stu-id="94d1a-150">less than</span></span>|<span data-ttu-id="94d1a-151">如果 (MyMsg.numOrders < 10)...</span><span class="sxs-lookup"><span data-stu-id="94d1a-151">If (MyMsg.numOrders < 10)...</span></span>|  
|>|<span data-ttu-id="94d1a-152">大于</span><span class="sxs-lookup"><span data-stu-id="94d1a-152">greater than</span></span>|<span data-ttu-id="94d1a-153">如果 (MyMsg.numOrders > 10)...</span><span class="sxs-lookup"><span data-stu-id="94d1a-153">If (MyMsg.numOrders > 10)...</span></span>|  
|<=|<span data-ttu-id="94d1a-154">小于或等于</span><span class="sxs-lookup"><span data-stu-id="94d1a-154">less than or equal to</span></span>|<span data-ttu-id="94d1a-155">如果 (MyMsg.numOrders < = 10)...</span><span class="sxs-lookup"><span data-stu-id="94d1a-155">If (MyMsg.numOrders <= 10)...</span></span>|  
|>=|<span data-ttu-id="94d1a-156">大于或等于</span><span class="sxs-lookup"><span data-stu-id="94d1a-156">greater than or equal to</span></span>|<span data-ttu-id="94d1a-157">If (MyMsg.numOrders >= 10)...</span><span class="sxs-lookup"><span data-stu-id="94d1a-157">If (MyMsg.numOrders >= 10)...</span></span>|  
|==|<span data-ttu-id="94d1a-158">等于</span><span class="sxs-lookup"><span data-stu-id="94d1a-158">equal to</span></span>|<span data-ttu-id="94d1a-159">If (MyMsg.numOrders == 10)...</span><span class="sxs-lookup"><span data-stu-id="94d1a-159">If (MyMsg.numOrders == 10)...</span></span>|  
|<span data-ttu-id="94d1a-160">!=</span><span class="sxs-lookup"><span data-stu-id="94d1a-160">!=</span></span>|<span data-ttu-id="94d1a-161">不等于</span><span class="sxs-lookup"><span data-stu-id="94d1a-161">not equal to</span></span>|<span data-ttu-id="94d1a-162">If (MyMsg.numOrders != 10)...</span><span class="sxs-lookup"><span data-stu-id="94d1a-162">If (MyMsg.numOrders != 10)...</span></span>|  
|&|<span data-ttu-id="94d1a-163">和</span><span class="sxs-lookup"><span data-stu-id="94d1a-163">and</span></span>|<span data-ttu-id="94d1a-164">如果 (myByte 和 255)...</span><span class="sxs-lookup"><span data-stu-id="94d1a-164">If (myByte & 255)...</span></span>|  
|^|<span data-ttu-id="94d1a-165">异或</span><span class="sxs-lookup"><span data-stu-id="94d1a-165">exclusive or</span></span>|<span data-ttu-id="94d1a-166">如果 (myByte ^1)...</span><span class="sxs-lookup"><span data-stu-id="94d1a-166">If (myByte ^ 1)...</span></span>|  
|<span data-ttu-id="94d1a-167">&#124;</span><span class="sxs-lookup"><span data-stu-id="94d1a-167">&#124;</span></span>|<span data-ttu-id="94d1a-168">或</span><span class="sxs-lookup"><span data-stu-id="94d1a-168">or</span></span>|<span data-ttu-id="94d1a-169">If (myByte &#124; 1)...</span><span class="sxs-lookup"><span data-stu-id="94d1a-169">If (myByte &#124; 1)...</span></span>|  
|&&|<span data-ttu-id="94d1a-170">条件和</span><span class="sxs-lookup"><span data-stu-id="94d1a-170">conditional and</span></span>|<span data-ttu-id="94d1a-171">如果 (MyMsg.numOrders > 10) & & (MyMsg.numOrders < 100)</span><span class="sxs-lookup"><span data-stu-id="94d1a-171">If (MyMsg.numOrders > 10) && (MyMsg.numOrders < 100)</span></span>|  
|<span data-ttu-id="94d1a-172">&#124;&#124;</span><span class="sxs-lookup"><span data-stu-id="94d1a-172">&#124;&#124;</span></span>|<span data-ttu-id="94d1a-173">条件或</span><span class="sxs-lookup"><span data-stu-id="94d1a-173">conditional or</span></span>|<span data-ttu-id="94d1a-174">If (MyMsg.numOrders < 10) &#124;&#124; (MyMsg.numOrders > 100)</span><span class="sxs-lookup"><span data-stu-id="94d1a-174">If (MyMsg.numOrders < 10) &#124;&#124; (MyMsg.numOrders > 100)</span></span>|  
|//|<span data-ttu-id="94d1a-175">注释</span><span class="sxs-lookup"><span data-stu-id="94d1a-175">commenting</span></span>|<span data-ttu-id="94d1a-176">这是注释</span><span class="sxs-lookup"><span data-stu-id="94d1a-176">//This is the comment</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="94d1a-177">常规表达式和与一起使用的筛选器表达式的规则有所不同**接收**形状。</span><span class="sxs-lookup"><span data-stu-id="94d1a-177">The rules differ between general expressions and filter expressions that are used with the **Receive** shape.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94d1a-178">请参阅</span><span class="sxs-lookup"><span data-stu-id="94d1a-178">See Also</span></span>  
 [<span data-ttu-id="94d1a-179">使用带接收消息形状的筛选器</span><span class="sxs-lookup"><span data-stu-id="94d1a-179">Using Filters With the Receive Message Shape</span></span>](../core/using-filters-with-the-receive-message-shape.md)