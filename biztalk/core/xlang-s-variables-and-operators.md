---
title: Xlang-s 变量和运算符 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 02512789-2cb9-4ba9-aa78-e59b248e6b24
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4eace5d4a30f8cac80403143a5dc3cfb887c0bc5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65246438"
---
# <a name="xlang-s-variables-and-operators"></a><span data-ttu-id="3a634-102">Xlang-s 变量和运算符</span><span class="sxs-lookup"><span data-stu-id="3a634-102">XLANG-s Variables and Operators</span></span>
<span data-ttu-id="3a634-103">本部分讨论的变量和运算符在 XLANG/s 语言中使用。</span><span class="sxs-lookup"><span data-stu-id="3a634-103">This section discusses the variables and operators used in the XLANG/s language.</span></span>  
  
## <a name="xlangs-variables"></a><span data-ttu-id="3a634-104">XLANG/s 变量</span><span class="sxs-lookup"><span data-stu-id="3a634-104">XLANG/s Variables</span></span>  
 <span data-ttu-id="3a634-105">变量表示存储位置。</span><span class="sxs-lookup"><span data-stu-id="3a634-105">Variables represent storage locations.</span></span> <span data-ttu-id="3a634-106">每个变量具有类型，用于确定值可以是存储在该变量中。</span><span class="sxs-lookup"><span data-stu-id="3a634-106">Every variable has a type that determines what values can be stored in that variable.</span></span> <span data-ttu-id="3a634-107">XLANG/s 是类型安全和相应的编译器可确保存储在变量中的值始终是适当的类型。</span><span class="sxs-lookup"><span data-stu-id="3a634-107">XLANG/s is type-safe, and its compiler guarantees that values stored in variables are always of the appropriate type.</span></span> <span data-ttu-id="3a634-108">XLANG/s 支持以下变量类型：</span><span class="sxs-lookup"><span data-stu-id="3a634-108">XLANG/s supports the following variable types:</span></span>  
  
- <span data-ttu-id="3a634-109">消息</span><span class="sxs-lookup"><span data-stu-id="3a634-109">Messages</span></span>  
  
- <span data-ttu-id="3a634-110">相关集</span><span class="sxs-lookup"><span data-stu-id="3a634-110">Correlation sets</span></span>  
  
- <span data-ttu-id="3a634-111">服务链接</span><span class="sxs-lookup"><span data-stu-id="3a634-111">Service links</span></span>  
  
- <span data-ttu-id="3a634-112">端口</span><span class="sxs-lookup"><span data-stu-id="3a634-112">Ports</span></span>  
  
- <span data-ttu-id="3a634-113">可分辨内置值类型：**布尔**，**字节**， **Char**，**十进制**， **Double**， **Int16**， **Int32**， **Int64**， **SByte**，**单个**，**字符串**， **UInt16**， **UInt32**，并**UInt64**</span><span class="sxs-lookup"><span data-stu-id="3a634-113">Distinguished built-in value types: **Boolean**, **Byte**, **Char**, **Decimal**, **Double**, **Int16**, **Int32**, **Int64**, **SByte**, **Single**, **String**, **UInt16**, **UInt32**, and **UInt64**</span></span>  
  
- <span data-ttu-id="3a634-114">对象</span><span class="sxs-lookup"><span data-stu-id="3a634-114">Objects</span></span>  
  
- <span data-ttu-id="3a634-115">枚举类型</span><span class="sxs-lookup"><span data-stu-id="3a634-115">Enumeration types</span></span>  
  
  <span data-ttu-id="3a634-116">XLANG/s 为上述类型的每个提供初始化语义。</span><span class="sxs-lookup"><span data-stu-id="3a634-116">XLANG/s provides initialization semantics for each of the preceding types.</span></span> <span data-ttu-id="3a634-117">此类初始化可以查看为该类型的向变量赋值。</span><span class="sxs-lookup"><span data-stu-id="3a634-117">Such initialization can be viewed as an assignment to a variable of that type.</span></span> <span data-ttu-id="3a634-118">在 XLANG/s，必须明确赋值变量之前可以获取或使用它的值。</span><span class="sxs-lookup"><span data-stu-id="3a634-118">In XLANG/s, a variable must be definitely assigned before its value can be obtained or used.</span></span>  
  
## <a name="xlangs-operators"></a><span data-ttu-id="3a634-119">XLANG/s 运算符</span><span class="sxs-lookup"><span data-stu-id="3a634-119">XLANG/s Operators</span></span>  
 <span data-ttu-id="3a634-120">XLANG/s 支持以下运算符。</span><span class="sxs-lookup"><span data-stu-id="3a634-120">XLANG/s supports the following operators.</span></span> <span data-ttu-id="3a634-121">它们紧密遵循 C# 中的相应运算符的功能。</span><span class="sxs-lookup"><span data-stu-id="3a634-121">They adhere closely to the functionality of the corresponding operators in C#.</span></span>  
  
|<span data-ttu-id="3a634-122">运算符</span><span class="sxs-lookup"><span data-stu-id="3a634-122">Operator</span></span>|<span data-ttu-id="3a634-123">Description</span><span class="sxs-lookup"><span data-stu-id="3a634-123">Description</span></span>|<span data-ttu-id="3a634-124">示例</span><span class="sxs-lookup"><span data-stu-id="3a634-124">Example</span></span>|  
|--------------|-----------------|-------------|  
|<span data-ttu-id="3a634-125">已选中</span><span class="sxs-lookup"><span data-stu-id="3a634-125">checked</span></span>|<span data-ttu-id="3a634-126">在算术溢出将引发错误</span><span class="sxs-lookup"><span data-stu-id="3a634-126">Raises error on arithmetic overflow</span></span>|<span data-ttu-id="3a634-127">checked(x = y \* 1000)</span><span class="sxs-lookup"><span data-stu-id="3a634-127">checked(x = y \* 1000)</span></span>|  
|<span data-ttu-id="3a634-128">unchecked</span><span class="sxs-lookup"><span data-stu-id="3a634-128">unchecked</span></span>|<span data-ttu-id="3a634-129">忽略算术溢出</span><span class="sxs-lookup"><span data-stu-id="3a634-129">Ignores arithmetic overflow</span></span>|<span data-ttu-id="3a634-130">unchecked(x = y \* 1000)</span><span class="sxs-lookup"><span data-stu-id="3a634-130">unchecked(x = y \* 1000)</span></span>|  
|<span data-ttu-id="3a634-131">新</span><span class="sxs-lookup"><span data-stu-id="3a634-131">new</span></span>|<span data-ttu-id="3a634-132">创建一个类的实例</span><span class="sxs-lookup"><span data-stu-id="3a634-132">Creates an instance of a class</span></span>|<span data-ttu-id="3a634-133">匹配大小写 = 新 MyClass;</span><span class="sxs-lookup"><span data-stu-id="3a634-133">myObject = new MyClass;</span></span>|  
|<span data-ttu-id="3a634-134">typeof</span><span class="sxs-lookup"><span data-stu-id="3a634-134">typeof</span></span>|<span data-ttu-id="3a634-135">检索的类型</span><span class="sxs-lookup"><span data-stu-id="3a634-135">Retrieves a type</span></span>|<span data-ttu-id="3a634-136">myMapType = typeof(myMap)</span><span class="sxs-lookup"><span data-stu-id="3a634-136">myMapType = typeof(myMap)</span></span>|  
|<span data-ttu-id="3a634-137">succeeded</span><span class="sxs-lookup"><span data-stu-id="3a634-137">succeeded</span></span>|<span data-ttu-id="3a634-138">测试成功完成的事务作用域或业务流程</span><span class="sxs-lookup"><span data-stu-id="3a634-138">Tests for successful completion of transactional scope or orchestration</span></span>|<span data-ttu-id="3a634-139">已成功 (\<的子事务的当前作用域或服务的事务 ID\>)</span><span class="sxs-lookup"><span data-stu-id="3a634-139">succeeded(\<transaction ID for child transaction of current scope or service\>)</span></span>|  
|<span data-ttu-id="3a634-140">存在</span><span class="sxs-lookup"><span data-stu-id="3a634-140">exists</span></span>|<span data-ttu-id="3a634-141">测试存在的消息上下文属性</span><span class="sxs-lookup"><span data-stu-id="3a634-141">Tests for the existence of a message context property</span></span>|<span data-ttu-id="3a634-142">BTS。RetryCount 存在 Message_In</span><span class="sxs-lookup"><span data-stu-id="3a634-142">BTS.RetryCount exists Message_In</span></span>|  
|+|<span data-ttu-id="3a634-143">一元加</span><span class="sxs-lookup"><span data-stu-id="3a634-143">Unary plus</span></span>|<span data-ttu-id="3a634-144">+(int x)</span><span class="sxs-lookup"><span data-stu-id="3a634-144">+(int x)</span></span>|  
|-|<span data-ttu-id="3a634-145">一元负</span><span class="sxs-lookup"><span data-stu-id="3a634-145">Unary minus</span></span>|<span data-ttu-id="3a634-146">-(int x)</span><span class="sxs-lookup"><span data-stu-id="3a634-146">-(int x)</span></span>|  
|<span data-ttu-id="3a634-147">!</span><span class="sxs-lookup"><span data-stu-id="3a634-147">!</span></span>|<span data-ttu-id="3a634-148">逻辑求反</span><span class="sxs-lookup"><span data-stu-id="3a634-148">Logical negation</span></span>|<span data-ttu-id="3a634-149">!myBool</span><span class="sxs-lookup"><span data-stu-id="3a634-149">!myBool</span></span>|  
|~|<span data-ttu-id="3a634-150">按位求补</span><span class="sxs-lookup"><span data-stu-id="3a634-150">Bitwise complement</span></span>|<span data-ttu-id="3a634-151">x = ~y</span><span class="sxs-lookup"><span data-stu-id="3a634-151">x = ~y</span></span>|  
|<span data-ttu-id="3a634-152">()</span><span class="sxs-lookup"><span data-stu-id="3a634-152">()</span></span>|<span data-ttu-id="3a634-153">强制转换</span><span class="sxs-lookup"><span data-stu-id="3a634-153">Cast</span></span>|<span data-ttu-id="3a634-154">(bool) myInt</span><span class="sxs-lookup"><span data-stu-id="3a634-154">(bool) myInt</span></span>|  
|*|<span data-ttu-id="3a634-155">时间</span><span class="sxs-lookup"><span data-stu-id="3a634-155">Times</span></span>|<span data-ttu-id="3a634-156">Weight = MyMsg.numOrders \* 20</span><span class="sxs-lookup"><span data-stu-id="3a634-156">Weight = MyMsg.numOrders \* 20</span></span>|  
|/|<span data-ttu-id="3a634-157">除以</span><span class="sxs-lookup"><span data-stu-id="3a634-157">Divided by</span></span>|<span data-ttu-id="3a634-158">x / y</span><span class="sxs-lookup"><span data-stu-id="3a634-158">x / y</span></span>|  
|+|<span data-ttu-id="3a634-159">Plus</span><span class="sxs-lookup"><span data-stu-id="3a634-159">Plus</span></span>|<span data-ttu-id="3a634-160">x + y</span><span class="sxs-lookup"><span data-stu-id="3a634-160">x + y</span></span>|  
|-|<span data-ttu-id="3a634-161">减号</span><span class="sxs-lookup"><span data-stu-id="3a634-161">Minus</span></span>|<span data-ttu-id="3a634-162">x - y</span><span class="sxs-lookup"><span data-stu-id="3a634-162">x - y</span></span>|  
|<<|<span data-ttu-id="3a634-163">左移</span><span class="sxs-lookup"><span data-stu-id="3a634-163">Shift left</span></span>|<span data-ttu-id="3a634-164">x << 2</span><span class="sxs-lookup"><span data-stu-id="3a634-164">x << 2</span></span>|  
|>>|<span data-ttu-id="3a634-165">右移</span><span class="sxs-lookup"><span data-stu-id="3a634-165">Shift right</span></span>|<span data-ttu-id="3a634-166">x >> 2</span><span class="sxs-lookup"><span data-stu-id="3a634-166">x >> 2</span></span>|  
|<|<span data-ttu-id="3a634-167">小于</span><span class="sxs-lookup"><span data-stu-id="3a634-167">Less than</span></span>|<span data-ttu-id="3a634-168">如果 (MyMsg.numOrders < 10)...</span><span class="sxs-lookup"><span data-stu-id="3a634-168">If (MyMsg.numOrders < 10)...</span></span>|  
|>|<span data-ttu-id="3a634-169">大于</span><span class="sxs-lookup"><span data-stu-id="3a634-169">Greater than</span></span>|<span data-ttu-id="3a634-170">如果 (MyMsg.numOrders > 10)...</span><span class="sxs-lookup"><span data-stu-id="3a634-170">If (MyMsg.numOrders > 10)...</span></span>|  
|<=|<span data-ttu-id="3a634-171">小于或等于</span><span class="sxs-lookup"><span data-stu-id="3a634-171">Less than or equal to</span></span>|<span data-ttu-id="3a634-172">如果 (MyMsg.numOrders < = 10)...</span><span class="sxs-lookup"><span data-stu-id="3a634-172">If (MyMsg.numOrders <= 10)...</span></span>|  
|>=|<span data-ttu-id="3a634-173">大于或等于</span><span class="sxs-lookup"><span data-stu-id="3a634-173">Greater than or equal to</span></span>|<span data-ttu-id="3a634-174">If (MyMsg.numOrders >= 10)...</span><span class="sxs-lookup"><span data-stu-id="3a634-174">If (MyMsg.numOrders >= 10)...</span></span>|  
|==|<span data-ttu-id="3a634-175">等于</span><span class="sxs-lookup"><span data-stu-id="3a634-175">Equal to</span></span>|<span data-ttu-id="3a634-176">If (MyMsg.numOrders == 10)...</span><span class="sxs-lookup"><span data-stu-id="3a634-176">If (MyMsg.numOrders == 10)...</span></span>|  
|<span data-ttu-id="3a634-177">!=</span><span class="sxs-lookup"><span data-stu-id="3a634-177">!=</span></span>|<span data-ttu-id="3a634-178">不等于</span><span class="sxs-lookup"><span data-stu-id="3a634-178">Not equal to</span></span>|<span data-ttu-id="3a634-179">If (MyMsg.numOrders != 10)...</span><span class="sxs-lookup"><span data-stu-id="3a634-179">If (MyMsg.numOrders != 10)...</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3a634-180">请参阅</span><span class="sxs-lookup"><span data-stu-id="3a634-180">See Also</span></span>  
 <span data-ttu-id="3a634-181">[Xlang-s 数据类型](../core/xlang-s-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="3a634-181">[XLANG-s Data Types](../core/xlang-s-data-types.md) </span></span>  
 <span data-ttu-id="3a634-182">[Xlang-s 语句](../core/xlang-s-statements.md) </span><span class="sxs-lookup"><span data-stu-id="3a634-182">[XLANG-s Statements](../core/xlang-s-statements.md) </span></span>  
 <span data-ttu-id="3a634-183">[Xlang-s 表达式](../core/xlang-s-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="3a634-183">[XLANG-s Expressions](../core/xlang-s-expressions.md) </span></span>  
 <span data-ttu-id="3a634-184">[Xlang-s 保留字](../core/xlang-s-reserved-words.md) </span><span class="sxs-lookup"><span data-stu-id="3a634-184">[XLANG-s Reserved Words](../core/xlang-s-reserved-words.md) </span></span>  
 [<span data-ttu-id="3a634-185">XLANG-s 到 BPEL4WS 的类型转换</span><span class="sxs-lookup"><span data-stu-id="3a634-185">XLANG-s to BPEL4WS Type Conversions</span></span>](../core/xlang-s-to-bpel4ws-type-conversions.md)