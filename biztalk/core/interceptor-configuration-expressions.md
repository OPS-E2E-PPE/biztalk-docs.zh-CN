---
title: "侦听器配置表达式 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2695f509-fece-40b8-aa00-fa3c0c0f19c5
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a28af058ac4750426f66dc6e290bc6a02bf2efd6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="interceptor-configuration-expressions"></a><span data-ttu-id="c4f9d-102">侦听器配置表达式</span><span class="sxs-lookup"><span data-stu-id="c4f9d-102">Interceptor Configuration Expressions</span></span>
<span data-ttu-id="c4f9d-103">BAM 侦听器配置文件使用筛选器表达式来标识活动，并使用数据表达式构造用于存储的数据元素，作为相关 ID、继续标记或类似用途使用。</span><span class="sxs-lookup"><span data-stu-id="c4f9d-103">The BAM interceptor configuraton file uses filter expressions to identify an activity and uses data expressions to construct a data element for storage, use as a correlation ID or continuation token, or similar purpose.</span></span> <span data-ttu-id="c4f9d-104">拦截器配置文件中不考虑目的，标识单个表达式`expression`元素和包含一个或多个操作使用反向波兰语表示法，也称为后缀表示法。</span><span class="sxs-lookup"><span data-stu-id="c4f9d-104">Regardless of the purpose, individual expressions are identified in the interceptor configuration file by the `expression` element and contain one or more operations using Reverse Polish Notation, also known as postfix notation.</span></span>  
  
## <a name="about-reverse-polish-notation"></a><span data-ttu-id="c4f9d-105">关于逆波兰表示法</span><span class="sxs-lookup"><span data-stu-id="c4f9d-105">About Reverse Polish Notation</span></span>  
 <span data-ttu-id="c4f9d-106">在逆波兰表示法 (RPN) 中，操作数的优先级高于运算符，因而不必使用括号作为优先运算符。</span><span class="sxs-lookup"><span data-stu-id="c4f9d-106">In Reverse Polish Notation (RPN), operands precede the operator, thereby removing the need to use parentheses as precedence operators.</span></span> <span data-ttu-id="c4f9d-107">堆栈用于保存值，而所有运算或者将值推送到堆栈上，或者从堆栈中弹出（删除）值，或者执行推送和弹出的组合以完成某个运算。</span><span class="sxs-lookup"><span data-stu-id="c4f9d-107">A stack is used to hold values and all operations either push values onto the stack, pop (remove) values from the stack, or perform a combination of pushes and pops to complete an operation.</span></span>  
  
 <span data-ttu-id="c4f9d-108">例如，如果要计算表达式</span><span class="sxs-lookup"><span data-stu-id="c4f9d-108">For example, if you wanted to evaluate the expression</span></span>  
  
 `5 + (10 - 2)`  
  
 <span data-ttu-id="c4f9d-109">将该表达式转换为等效的 RPN 结果，形式如下</span><span class="sxs-lookup"><span data-stu-id="c4f9d-109">Converting this to the equivalent RPN results in</span></span>  
  
 `5 10 2 - +`  
  
 <span data-ttu-id="c4f9d-110">该表达式计算过程如下：</span><span class="sxs-lookup"><span data-stu-id="c4f9d-110">This would be evaluated as follows:</span></span>  
  
|<span data-ttu-id="c4f9d-111">输入</span><span class="sxs-lookup"><span data-stu-id="c4f9d-111">Input</span></span>|<span data-ttu-id="c4f9d-112">运算</span><span class="sxs-lookup"><span data-stu-id="c4f9d-112">Operation</span></span>|<span data-ttu-id="c4f9d-113">堆栈</span><span class="sxs-lookup"><span data-stu-id="c4f9d-113">Stack</span></span>|  
|-----------|---------------|-----------|  
|<span data-ttu-id="c4f9d-114">5</span><span class="sxs-lookup"><span data-stu-id="c4f9d-114">5</span></span>|<span data-ttu-id="c4f9d-115">推送</span><span class="sxs-lookup"><span data-stu-id="c4f9d-115">Push</span></span>|<span data-ttu-id="c4f9d-116">5</span><span class="sxs-lookup"><span data-stu-id="c4f9d-116">5</span></span>|  
|<span data-ttu-id="c4f9d-117">10</span><span class="sxs-lookup"><span data-stu-id="c4f9d-117">10</span></span>|<span data-ttu-id="c4f9d-118">推送</span><span class="sxs-lookup"><span data-stu-id="c4f9d-118">Push</span></span>|<span data-ttu-id="c4f9d-119">5, 10</span><span class="sxs-lookup"><span data-stu-id="c4f9d-119">5, 10</span></span>|  
|<span data-ttu-id="c4f9d-120">2</span><span class="sxs-lookup"><span data-stu-id="c4f9d-120">2</span></span>|<span data-ttu-id="c4f9d-121">推送</span><span class="sxs-lookup"><span data-stu-id="c4f9d-121">Push</span></span>|<span data-ttu-id="c4f9d-122">5, 10, 2</span><span class="sxs-lookup"><span data-stu-id="c4f9d-122">5, 10, 2</span></span>|  
|-|<span data-ttu-id="c4f9d-123">减</span><span class="sxs-lookup"><span data-stu-id="c4f9d-123">Subtract</span></span>|<span data-ttu-id="c4f9d-124">5, 8</span><span class="sxs-lookup"><span data-stu-id="c4f9d-124">5, 8</span></span>|  
|+|<span data-ttu-id="c4f9d-125">添加</span><span class="sxs-lookup"><span data-stu-id="c4f9d-125">Add</span></span>|<span data-ttu-id="c4f9d-126">13</span><span class="sxs-lookup"><span data-stu-id="c4f9d-126">13</span></span>|  
  
 <span data-ttu-id="c4f9d-127">假设 RPN 系统支持字符串连接运算，也可以计算下列表达式</span><span class="sxs-lookup"><span data-stu-id="c4f9d-127">Assuming the RPN system supported the string concatenate operation, you could also evaluate the expression</span></span>  
  
 `"The quick brown " + "fox " + "jumped over the lazy " + "dog."`  
  
 <span data-ttu-id="c4f9d-128">将该表达式转换为等效的 RPN 符号可生成：</span><span class="sxs-lookup"><span data-stu-id="c4f9d-128">Converting this to the equivalent RPN notation yields:</span></span>  
  
 `"The quick brown " "fox " "jumped over the lazy " "dog" + + +`  
  
 <span data-ttu-id="c4f9d-129">该表达式计算过程如下：</span><span class="sxs-lookup"><span data-stu-id="c4f9d-129">This would be evaluated as follows:</span></span>  
  
|<span data-ttu-id="c4f9d-130">输入</span><span class="sxs-lookup"><span data-stu-id="c4f9d-130">Input</span></span>|<span data-ttu-id="c4f9d-131">运算</span><span class="sxs-lookup"><span data-stu-id="c4f9d-131">Operation</span></span>|<span data-ttu-id="c4f9d-132">堆栈</span><span class="sxs-lookup"><span data-stu-id="c4f9d-132">Stack</span></span>|  
|-----------|---------------|-----------|  
|<span data-ttu-id="c4f9d-133">"快速 brown"</span><span class="sxs-lookup"><span data-stu-id="c4f9d-133">"The quick brown"</span></span>|<span data-ttu-id="c4f9d-134">推送</span><span class="sxs-lookup"><span data-stu-id="c4f9d-134">Push</span></span>|<span data-ttu-id="c4f9d-135">"The quick brown "</span><span class="sxs-lookup"><span data-stu-id="c4f9d-135">"The quick brown "</span></span>|  
|<span data-ttu-id="c4f9d-136">"fox"</span><span class="sxs-lookup"><span data-stu-id="c4f9d-136">"fox"</span></span>|<span data-ttu-id="c4f9d-137">推送</span><span class="sxs-lookup"><span data-stu-id="c4f9d-137">Push</span></span>|<span data-ttu-id="c4f9d-138">"The quick brown ", "fox "</span><span class="sxs-lookup"><span data-stu-id="c4f9d-138">"The quick brown ", "fox "</span></span>|  
|<span data-ttu-id="c4f9d-139">"jumped over the lazy"</span><span class="sxs-lookup"><span data-stu-id="c4f9d-139">"jumped over the lazy"</span></span>|<span data-ttu-id="c4f9d-140">推送</span><span class="sxs-lookup"><span data-stu-id="c4f9d-140">Push</span></span>|<span data-ttu-id="c4f9d-141">"The quick brown ", "fox ", "jumped over the lazy "</span><span class="sxs-lookup"><span data-stu-id="c4f9d-141">"The quick brown ", "fox ", "jumped over the lazy "</span></span>|  
|<span data-ttu-id="c4f9d-142">"dog."</span><span class="sxs-lookup"><span data-stu-id="c4f9d-142">"dog."</span></span>|<span data-ttu-id="c4f9d-143">推送</span><span class="sxs-lookup"><span data-stu-id="c4f9d-143">Push</span></span>|<span data-ttu-id="c4f9d-144">"The quick brown ", "fox ", "jumped over the lazy ", "dog."</span><span class="sxs-lookup"><span data-stu-id="c4f9d-144">"The quick brown ", "fox ", "jumped over the lazy ", "dog."</span></span>|  
|+|<span data-ttu-id="c4f9d-145">连接</span><span class="sxs-lookup"><span data-stu-id="c4f9d-145">Concatenate</span></span>|<span data-ttu-id="c4f9d-146">"The quick brown ", "fox ", "jumped over the lazy dog."</span><span class="sxs-lookup"><span data-stu-id="c4f9d-146">"The quick brown ", "fox ", "jumped over the lazy dog."</span></span>|  
|+|<span data-ttu-id="c4f9d-147">连接</span><span class="sxs-lookup"><span data-stu-id="c4f9d-147">Concatenate</span></span>|<span data-ttu-id="c4f9d-148">"The quick brown ", "fox jumped over the lazy dog."</span><span class="sxs-lookup"><span data-stu-id="c4f9d-148">"The quick brown ", "fox jumped over the lazy dog."</span></span>|  
|+|<span data-ttu-id="c4f9d-149">连接</span><span class="sxs-lookup"><span data-stu-id="c4f9d-149">Concatenate</span></span>|<span data-ttu-id="c4f9d-150">"The quick brown fox jumped over the lazy dog."</span><span class="sxs-lookup"><span data-stu-id="c4f9d-150">"The quick brown fox jumped over the lazy dog."</span></span>|  
  
 <span data-ttu-id="c4f9d-151">正如您所见，可以支持任意数量的运算，包括比较、布尔运算和用于检索适合于所参与运算的值的自定义运算。</span><span class="sxs-lookup"><span data-stu-id="c4f9d-151">As you can see, an arbitrary number of operations can be supported, including comparison, Boolean operations, and custom operations that retrieve values appropriate for the operations in which they participate.</span></span> <span data-ttu-id="c4f9d-152">各值将在此堆栈中进行累计并根据各个运算被推送到堆栈和弹出堆栈。</span><span class="sxs-lookup"><span data-stu-id="c4f9d-152">Values accumulate on the stack and are pushed and popped according to individual operations.</span></span>  
  
## <a name="reverse-polish-notation-in-the-interceptor-configuration-file"></a><span data-ttu-id="c4f9d-153">侦听器配置文件中的逆波兰表示法</span><span class="sxs-lookup"><span data-stu-id="c4f9d-153">Reverse Polish Notation in the Interceptor Configuration File</span></span>  
 <span data-ttu-id="c4f9d-154">你将配置文件中侦听器中编写两个类型的表达式： 筛选表达式和数据表达式。</span><span class="sxs-lookup"><span data-stu-id="c4f9d-154">You will write two kinds of expressions in the interceptor configuration file: filter expressions and data expressions.</span></span> <span data-ttu-id="c4f9d-155">筛选器表达式预计可以为一个布尔值 RPN 表达式的结果`true`或`false`时数据表达式预期在堆栈上的单个值。</span><span class="sxs-lookup"><span data-stu-id="c4f9d-155">Filter expressions expect the result of the RPN expression to be a Boolean `true` or `false` while data expressions expect a single value on the stack.</span></span>  
  
### <a name="filter-expressions"></a><span data-ttu-id="c4f9d-156">筛选器表达式</span><span class="sxs-lookup"><span data-stu-id="c4f9d-156">Filter Expressions</span></span>  
 <span data-ttu-id="c4f9d-157">筛选器表达式的计算结果为布尔值`true`或`false`，用于标识特定的事件以跟踪 WF 或 WFC 应用程序中。</span><span class="sxs-lookup"><span data-stu-id="c4f9d-157">Filter expressions evaluate to Boolean `true` or `false` and are used to identify a specific event to track in the WF or WFC application.</span></span> <span data-ttu-id="c4f9d-158">在 WF 应用程序中，通常根据活动名称和事件进行筛选。</span><span class="sxs-lookup"><span data-stu-id="c4f9d-158">In WF applications, it is common to filter based on activity name and event.</span></span> <span data-ttu-id="c4f9d-159">例如，你可能想要选择**FoodAndDrinksPolicy**活动时**已关闭**。</span><span class="sxs-lookup"><span data-stu-id="c4f9d-159">For example, you may want to select the **FoodAndDrinksPolicy** activity when it is **Closed**.</span></span> <span data-ttu-id="c4f9d-160">使用 WF 运算，则可将此筛选器表示为：</span><span class="sxs-lookup"><span data-stu-id="c4f9d-160">Using WF operations, you could express the filter as:</span></span>  
  
 `(GetActivityName = "FoodAndDrinksPolicy") && (GetActivityEvent = "Closed")`  
  
 <span data-ttu-id="c4f9d-161">将此表达式转换为 RPN 可生成：</span><span class="sxs-lookup"><span data-stu-id="c4f9d-161">Converting this to RPN yields:</span></span>  
  
 `GetActivityName "FoodAndDrinksPolicy" == GetActivityEvent "Closed" == &&`  
  
 <span data-ttu-id="c4f9d-162">将此表达式转换为侦听器配置文件的等效表达式将生成以下 XML：</span><span class="sxs-lookup"><span data-stu-id="c4f9d-162">Converting this expression to the equivalent expression for the interceptor configuration file results in the following XML:</span></span>  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>FoodAndDrinksPolicy</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <wf:Operation Name="GetActivityEvent"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
    <ic:Operation Name="And"/>  
  </ic:Expression>  
</ic:Filter>  
```  
  
 <span data-ttu-id="c4f9d-163">最后，此表达式的计算结果将如下假设**GetActivityName**返回"DessertPolicy"和**GetActivityEvent**返回"已关闭":</span><span class="sxs-lookup"><span data-stu-id="c4f9d-163">Finally, this expression would be evaluated as follows assuming **GetActivityName** returned "DessertPolicy" and **GetActivityEvent** returned "Closed":</span></span>  
  
|<span data-ttu-id="c4f9d-164">输入</span><span class="sxs-lookup"><span data-stu-id="c4f9d-164">Input</span></span>|<span data-ttu-id="c4f9d-165">运算</span><span class="sxs-lookup"><span data-stu-id="c4f9d-165">Operation</span></span>|<span data-ttu-id="c4f9d-166">堆栈</span><span class="sxs-lookup"><span data-stu-id="c4f9d-166">Stack</span></span>|  
|-----------|---------------|-----------|  
||<span data-ttu-id="c4f9d-167">GetActivityName</span><span class="sxs-lookup"><span data-stu-id="c4f9d-167">GetActivityName</span></span>|<span data-ttu-id="c4f9d-168">"DessertPolicy"</span><span class="sxs-lookup"><span data-stu-id="c4f9d-168">"DessertPolicy"</span></span>|  
|<span data-ttu-id="c4f9d-169">"FoodAndDrinksPolicy"</span><span class="sxs-lookup"><span data-stu-id="c4f9d-169">"FoodAndDrinksPolicy"</span></span>|<span data-ttu-id="c4f9d-170">常量</span><span class="sxs-lookup"><span data-stu-id="c4f9d-170">Constant</span></span>|<span data-ttu-id="c4f9d-171">"DessertPolicy", "FoodAndDrinksPolicy"</span><span class="sxs-lookup"><span data-stu-id="c4f9d-171">"DessertPolicy", "FoodAndDrinksPolicy"</span></span>|  
|<span data-ttu-id="c4f9d-172">等于</span><span class="sxs-lookup"><span data-stu-id="c4f9d-172">Equals</span></span>|<span data-ttu-id="c4f9d-173">比较</span><span class="sxs-lookup"><span data-stu-id="c4f9d-173">Comparison</span></span>|<span data-ttu-id="c4f9d-174">False</span><span class="sxs-lookup"><span data-stu-id="c4f9d-174">False</span></span>|  
||<span data-ttu-id="c4f9d-175">GetActivityEvent</span><span class="sxs-lookup"><span data-stu-id="c4f9d-175">GetActivityEvent</span></span>|<span data-ttu-id="c4f9d-176">False, Closed</span><span class="sxs-lookup"><span data-stu-id="c4f9d-176">False, Closed</span></span>|  
|<span data-ttu-id="c4f9d-177">"Closed"</span><span class="sxs-lookup"><span data-stu-id="c4f9d-177">"Closed"</span></span>|<span data-ttu-id="c4f9d-178">常量</span><span class="sxs-lookup"><span data-stu-id="c4f9d-178">Constant</span></span>|<span data-ttu-id="c4f9d-179">False, "Closed", "Closed"</span><span class="sxs-lookup"><span data-stu-id="c4f9d-179">False, "Closed", "Closed"</span></span>|  
|<span data-ttu-id="c4f9d-180">等于</span><span class="sxs-lookup"><span data-stu-id="c4f9d-180">Equals</span></span>|<span data-ttu-id="c4f9d-181">比较</span><span class="sxs-lookup"><span data-stu-id="c4f9d-181">Comparison</span></span>|<span data-ttu-id="c4f9d-182">False, True</span><span class="sxs-lookup"><span data-stu-id="c4f9d-182">False, True</span></span>|  
|<span data-ttu-id="c4f9d-183">And</span><span class="sxs-lookup"><span data-stu-id="c4f9d-183">And</span></span>|<span data-ttu-id="c4f9d-184">逻辑和</span><span class="sxs-lookup"><span data-stu-id="c4f9d-184">Logical And</span></span>|<span data-ttu-id="c4f9d-185">False</span><span class="sxs-lookup"><span data-stu-id="c4f9d-185">False</span></span>|  
  
 <span data-ttu-id="c4f9d-186">在堆栈上保留的值是布尔值`False`。</span><span class="sxs-lookup"><span data-stu-id="c4f9d-186">The value left on the stack is Boolean `False`.</span></span> <span data-ttu-id="c4f9d-187">这将导致不会激发相应事件。</span><span class="sxs-lookup"><span data-stu-id="c4f9d-187">This will cause the corresponding event to not fire.</span></span> <span data-ttu-id="c4f9d-188">如果活动名为 "FoodAndDrinksPolicy"，则计算结果将为布尔值 `True`。</span><span class="sxs-lookup"><span data-stu-id="c4f9d-188">If the activity name were "FoodAndDrinksPolicy" then it would have evaluated to Boolean `True`.</span></span>  
  
 <span data-ttu-id="c4f9d-189">您可以通过使用 WCF 操作构造 （具有类似的评估） 的类似表达式`GetEndpointName`和`GetOperationName`。</span><span class="sxs-lookup"><span data-stu-id="c4f9d-189">You can construct a similar expression (with a similar evaluation) by using the WCF operations `GetEndpointName` and `GetOperationName`.</span></span>  
  
### <a name="data-expressions"></a><span data-ttu-id="c4f9d-190">数据表达式</span><span class="sxs-lookup"><span data-stu-id="c4f9d-190">Data Expressions</span></span>  
 <span data-ttu-id="c4f9d-191">数据表达式用于定义单个字符串数据值。</span><span class="sxs-lookup"><span data-stu-id="c4f9d-191">Data expressions are used to define a single string data value.</span></span> <span data-ttu-id="c4f9d-192">数据表达式是不包括任何表达式`Filter`元素。</span><span class="sxs-lookup"><span data-stu-id="c4f9d-192">A data expression is any expression that is not enclosed by a `Filter` element.</span></span> <span data-ttu-id="c4f9d-193">通过使用数据表达式`OnEvent`元素`CorrelationID`， `ContinuationToken`， `Reference`，和`Update`。</span><span class="sxs-lookup"><span data-stu-id="c4f9d-193">Data expressions are used by the `OnEvent` elements `CorrelationID`, `ContinuationToken`, `Reference`, and `Update`.</span></span>  
  
 <span data-ttu-id="c4f9d-194">通常要求使用已标记的时间戳来更新 BAM 活动数据库。</span><span class="sxs-lookup"><span data-stu-id="c4f9d-194">It is a common requirement to update the BAM activity database with a labeled time stamp.</span></span> <span data-ttu-id="c4f9d-195">例如，你可能想要捕获事件格式化为字符串开头的时间"启动： \<EventTime >"。</span><span class="sxs-lookup"><span data-stu-id="c4f9d-195">For example, you might want to capture the time an event starts with a string formatted as "Start: \<EventTime>".</span></span> <span data-ttu-id="c4f9d-196">为此，需要使用类似以下格式的表达式（其中 + 表示连接）：</span><span class="sxs-lookup"><span data-stu-id="c4f9d-196">To do this, you need to use an expression similar to the following (where + represents concatenation):</span></span>  
  
 `"Start: " + GetContextProperty(EventTime)`  
  
 <span data-ttu-id="c4f9d-197">将此表达式转换为 RPN 可生成：</span><span class="sxs-lookup"><span data-stu-id="c4f9d-197">Converting this to RPN yields:</span></span>  
  
 `"Start: " GetContextProperty(EventTime) +`  
  
 <span data-ttu-id="c4f9d-198">将此表达式转换为的等效表达式`Update`下面的 XML 中的侦听器的配置文件结果中的元素：</span><span class="sxs-lookup"><span data-stu-id="c4f9d-198">Converting this expression to the equivalent expression for an `Update` element in the interceptor configuration file results in the following XML:</span></span>  
  
```  
<ic:Update DataItemName="NewOrderCreateTime" Type="NVARCHAR">  
  <ic:Expression>  
    <ic:Operation Name="Constant">  
      <ic:Argument>Start:</ic:Argument>  
    </ic:Operation>  
    <wf:Operation Name="GetContextProperty">  
      <wf:Argument>EventTime</wf:Argument>  
    </wf:Operation>  
    <ic:Operation Name="Concatenate" />  
  </ic:Expression>  
</ic:Update>  
```  
  
 <span data-ttu-id="c4f9d-199">下表显示了在事件时间为“12:00 PM”的情况下如何解释该表达式。</span><span class="sxs-lookup"><span data-stu-id="c4f9d-199">The following table shows how this expression would be interpreted if the event time was "12:00 PM".</span></span>  
  
|<span data-ttu-id="c4f9d-200">输入</span><span class="sxs-lookup"><span data-stu-id="c4f9d-200">Input</span></span>|<span data-ttu-id="c4f9d-201">运算</span><span class="sxs-lookup"><span data-stu-id="c4f9d-201">Operation</span></span>|<span data-ttu-id="c4f9d-202">堆栈</span><span class="sxs-lookup"><span data-stu-id="c4f9d-202">Stack</span></span>|  
|-----------|---------------|-----------|  
|<span data-ttu-id="c4f9d-203">"启动:"</span><span class="sxs-lookup"><span data-stu-id="c4f9d-203">"Start: "</span></span>|<span data-ttu-id="c4f9d-204">常量</span><span class="sxs-lookup"><span data-stu-id="c4f9d-204">Constant</span></span>|<span data-ttu-id="c4f9d-205">"启动:"</span><span class="sxs-lookup"><span data-stu-id="c4f9d-205">"Start: "</span></span>|  
|<span data-ttu-id="c4f9d-206">GetContextProperty(EventTime)</span><span class="sxs-lookup"><span data-stu-id="c4f9d-206">GetContextProperty(EventTime)</span></span>|<span data-ttu-id="c4f9d-207">推送</span><span class="sxs-lookup"><span data-stu-id="c4f9d-207">Push</span></span>|<span data-ttu-id="c4f9d-208">"启动:"，"2006年-09-27T12:00:34.000Z"</span><span class="sxs-lookup"><span data-stu-id="c4f9d-208">"Start: ", "2006-09-27T12:00:34.000Z"</span></span>|  
|<span data-ttu-id="c4f9d-209">连接</span><span class="sxs-lookup"><span data-stu-id="c4f9d-209">Concatenate</span></span>|<span data-ttu-id="c4f9d-210">连接</span><span class="sxs-lookup"><span data-stu-id="c4f9d-210">Concatenate</span></span>|<span data-ttu-id="c4f9d-211">"启动： 2006年-09-27T12:00:34.000Z"</span><span class="sxs-lookup"><span data-stu-id="c4f9d-211">"Start: 2006-09-27T12:00:34.000Z"</span></span>|  
  
 <span data-ttu-id="c4f9d-212">使用更新命令的值将"启动： 2006年-09-27T12:00:34.000Z"。</span><span class="sxs-lookup"><span data-stu-id="c4f9d-212">The value used by the update command would be "Start: 2006-09-27T12:00:34.000Z".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c4f9d-213">不要在数据表达式中使用比较运算符“And”或“Equals”。</span><span class="sxs-lookup"><span data-stu-id="c4f9d-213">Do not use the comparison operations "And" or "Equals" in data expressions.</span></span> <span data-ttu-id="c4f9d-214">如果使用这两种运算符，则部署侦听器配置文件时将收到一个错误。</span><span class="sxs-lookup"><span data-stu-id="c4f9d-214">If you do, you will receive an error when deploying your interceptor configuration file.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c4f9d-215">本节内容</span><span class="sxs-lookup"><span data-stu-id="c4f9d-215">In This Section</span></span>  
 [<span data-ttu-id="c4f9d-216">拦截器操作</span><span class="sxs-lookup"><span data-stu-id="c4f9d-216">Interceptor Operations</span></span>](../core/interceptor-operations.md)  
  
## <a name="see-also"></a><span data-ttu-id="c4f9d-217">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c4f9d-217">See Also</span></span>  
 [<span data-ttu-id="c4f9d-218">拦截器配置文件的结构</span><span class="sxs-lookup"><span data-stu-id="c4f9d-218">Structure of an Interceptor Configuration File</span></span>](../core/structure-of-an-interceptor-configuration-file.md)