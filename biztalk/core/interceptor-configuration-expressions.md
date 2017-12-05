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
ms.openlocfilehash: 927afa60dc65fb014f0d44305db5e7f6e78b803b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="interceptor-configuration-expressions"></a><span data-ttu-id="698c4-102">侦听器配置表达式</span><span class="sxs-lookup"><span data-stu-id="698c4-102">Interceptor Configuration Expressions</span></span>
<span data-ttu-id="698c4-103">BAM 侦听器配置文件使用筛选器表达式来标识活动，并使用数据表达式构造用于存储的数据元素，作为相关 ID、继续标记或类似用途使用。</span><span class="sxs-lookup"><span data-stu-id="698c4-103">The BAM interceptor configuraton file uses filter expressions to identify an activity and uses data expressions to construct a data element for storage, use as a correlation ID or continuation token, or similar purpose.</span></span> <span data-ttu-id="698c4-104">拦截器配置文件中不考虑目的，标识单个表达式`expression`元素和包含一个或多个操作使用反向波兰语表示法，也称为后缀表示法。</span><span class="sxs-lookup"><span data-stu-id="698c4-104">Regardless of the purpose, individual expressions are identified in the interceptor configuration file by the `expression` element and contain one or more operations using Reverse Polish Notation, also known as postfix notation.</span></span>  
  
## <a name="about-reverse-polish-notation"></a><span data-ttu-id="698c4-105">关于逆波兰表示法</span><span class="sxs-lookup"><span data-stu-id="698c4-105">About Reverse Polish Notation</span></span>  
 <span data-ttu-id="698c4-106">在逆波兰表示法 (RPN) 中，操作数的优先级高于运算符，因而不必使用括号作为优先运算符。</span><span class="sxs-lookup"><span data-stu-id="698c4-106">In Reverse Polish Notation (RPN), operands precede the operator, thereby removing the need to use parentheses as precedence operators.</span></span> <span data-ttu-id="698c4-107">堆栈用于保存值，而所有运算或者将值推送到堆栈上，或者从堆栈中弹出（删除）值，或者执行推送和弹出的组合以完成某个运算。</span><span class="sxs-lookup"><span data-stu-id="698c4-107">A stack is used to hold values and all operations either push values onto the stack, pop (remove) values from the stack, or perform a combination of pushes and pops to complete an operation.</span></span>  
  
 <span data-ttu-id="698c4-108">例如，如果要计算表达式</span><span class="sxs-lookup"><span data-stu-id="698c4-108">For example, if you wanted to evaluate the expression</span></span>  
  
 `5 + (10 - 2)`  
  
 <span data-ttu-id="698c4-109">将该表达式转换为等效的 RPN 结果，形式如下</span><span class="sxs-lookup"><span data-stu-id="698c4-109">Converting this to the equivalent RPN results in</span></span>  
  
 `5 10 2 - +`  
  
 <span data-ttu-id="698c4-110">该表达式计算过程如下：</span><span class="sxs-lookup"><span data-stu-id="698c4-110">This would be evaluated as follows:</span></span>  
  
|<span data-ttu-id="698c4-111">输入</span><span class="sxs-lookup"><span data-stu-id="698c4-111">Input</span></span>|<span data-ttu-id="698c4-112">运算</span><span class="sxs-lookup"><span data-stu-id="698c4-112">Operation</span></span>|<span data-ttu-id="698c4-113">堆栈</span><span class="sxs-lookup"><span data-stu-id="698c4-113">Stack</span></span>|  
|-----------|---------------|-----------|  
|<span data-ttu-id="698c4-114">5</span><span class="sxs-lookup"><span data-stu-id="698c4-114">5</span></span>|<span data-ttu-id="698c4-115">推送</span><span class="sxs-lookup"><span data-stu-id="698c4-115">Push</span></span>|<span data-ttu-id="698c4-116">5</span><span class="sxs-lookup"><span data-stu-id="698c4-116">5</span></span>|  
|<span data-ttu-id="698c4-117">10</span><span class="sxs-lookup"><span data-stu-id="698c4-117">10</span></span>|<span data-ttu-id="698c4-118">推送</span><span class="sxs-lookup"><span data-stu-id="698c4-118">Push</span></span>|<span data-ttu-id="698c4-119">5, 10</span><span class="sxs-lookup"><span data-stu-id="698c4-119">5, 10</span></span>|  
|<span data-ttu-id="698c4-120">2</span><span class="sxs-lookup"><span data-stu-id="698c4-120">2</span></span>|<span data-ttu-id="698c4-121">推送</span><span class="sxs-lookup"><span data-stu-id="698c4-121">Push</span></span>|<span data-ttu-id="698c4-122">5, 10, 2</span><span class="sxs-lookup"><span data-stu-id="698c4-122">5, 10, 2</span></span>|  
|-|<span data-ttu-id="698c4-123">减</span><span class="sxs-lookup"><span data-stu-id="698c4-123">Subtract</span></span>|<span data-ttu-id="698c4-124">5, 8</span><span class="sxs-lookup"><span data-stu-id="698c4-124">5, 8</span></span>|  
|+|<span data-ttu-id="698c4-125">添加</span><span class="sxs-lookup"><span data-stu-id="698c4-125">Add</span></span>|<span data-ttu-id="698c4-126">13</span><span class="sxs-lookup"><span data-stu-id="698c4-126">13</span></span>|  
  
 <span data-ttu-id="698c4-127">假设 RPN 系统支持字符串连接运算，也可以计算下列表达式</span><span class="sxs-lookup"><span data-stu-id="698c4-127">Assuming the RPN system supported the string concatenate operation, you could also evaluate the expression</span></span>  
  
 `"The quick brown " + "fox " + "jumped over the lazy " + "dog."`  
  
 <span data-ttu-id="698c4-128">将该表达式转换为等效的 RPN 符号可生成：</span><span class="sxs-lookup"><span data-stu-id="698c4-128">Converting this to the equivalent RPN notation yields:</span></span>  
  
 `"The quick brown " "fox " "jumped over the lazy " "dog" + + +`  
  
 <span data-ttu-id="698c4-129">该表达式计算过程如下：</span><span class="sxs-lookup"><span data-stu-id="698c4-129">This would be evaluated as follows:</span></span>  
  
|<span data-ttu-id="698c4-130">输入</span><span class="sxs-lookup"><span data-stu-id="698c4-130">Input</span></span>|<span data-ttu-id="698c4-131">运算</span><span class="sxs-lookup"><span data-stu-id="698c4-131">Operation</span></span>|<span data-ttu-id="698c4-132">堆栈</span><span class="sxs-lookup"><span data-stu-id="698c4-132">Stack</span></span>|  
|-----------|---------------|-----------|  
|<span data-ttu-id="698c4-133">"快速 brown"</span><span class="sxs-lookup"><span data-stu-id="698c4-133">"The quick brown"</span></span>|<span data-ttu-id="698c4-134">推送</span><span class="sxs-lookup"><span data-stu-id="698c4-134">Push</span></span>|<span data-ttu-id="698c4-135">"The quick brown "</span><span class="sxs-lookup"><span data-stu-id="698c4-135">"The quick brown "</span></span>|  
|<span data-ttu-id="698c4-136">"fox"</span><span class="sxs-lookup"><span data-stu-id="698c4-136">"fox"</span></span>|<span data-ttu-id="698c4-137">推送</span><span class="sxs-lookup"><span data-stu-id="698c4-137">Push</span></span>|<span data-ttu-id="698c4-138">"The quick brown ", "fox "</span><span class="sxs-lookup"><span data-stu-id="698c4-138">"The quick brown ", "fox "</span></span>|  
|<span data-ttu-id="698c4-139">"jumped over the lazy"</span><span class="sxs-lookup"><span data-stu-id="698c4-139">"jumped over the lazy"</span></span>|<span data-ttu-id="698c4-140">推送</span><span class="sxs-lookup"><span data-stu-id="698c4-140">Push</span></span>|<span data-ttu-id="698c4-141">"The quick brown ", "fox ", "jumped over the lazy "</span><span class="sxs-lookup"><span data-stu-id="698c4-141">"The quick brown ", "fox ", "jumped over the lazy "</span></span>|  
|<span data-ttu-id="698c4-142">"dog."</span><span class="sxs-lookup"><span data-stu-id="698c4-142">"dog."</span></span>|<span data-ttu-id="698c4-143">推送</span><span class="sxs-lookup"><span data-stu-id="698c4-143">Push</span></span>|<span data-ttu-id="698c4-144">"The quick brown ", "fox ", "jumped over the lazy ", "dog."</span><span class="sxs-lookup"><span data-stu-id="698c4-144">"The quick brown ", "fox ", "jumped over the lazy ", "dog."</span></span>|  
|+|<span data-ttu-id="698c4-145">连接</span><span class="sxs-lookup"><span data-stu-id="698c4-145">Concatenate</span></span>|<span data-ttu-id="698c4-146">"The quick brown ", "fox ", "jumped over the lazy dog."</span><span class="sxs-lookup"><span data-stu-id="698c4-146">"The quick brown ", "fox ", "jumped over the lazy dog."</span></span>|  
|+|<span data-ttu-id="698c4-147">连接</span><span class="sxs-lookup"><span data-stu-id="698c4-147">Concatenate</span></span>|<span data-ttu-id="698c4-148">"The quick brown ", "fox jumped over the lazy dog."</span><span class="sxs-lookup"><span data-stu-id="698c4-148">"The quick brown ", "fox jumped over the lazy dog."</span></span>|  
|+|<span data-ttu-id="698c4-149">连接</span><span class="sxs-lookup"><span data-stu-id="698c4-149">Concatenate</span></span>|<span data-ttu-id="698c4-150">"The quick brown fox jumped over the lazy dog."</span><span class="sxs-lookup"><span data-stu-id="698c4-150">"The quick brown fox jumped over the lazy dog."</span></span>|  
  
 <span data-ttu-id="698c4-151">正如您所见，可以支持任意数量的运算，包括比较、布尔运算和用于检索适合于所参与运算的值的自定义运算。</span><span class="sxs-lookup"><span data-stu-id="698c4-151">As you can see, an arbitrary number of operations can be supported, including comparison, Boolean operations, and custom operations that retrieve values appropriate for the operations in which they participate.</span></span> <span data-ttu-id="698c4-152">各值将在此堆栈中进行累计并根据各个运算被推送到堆栈和弹出堆栈。</span><span class="sxs-lookup"><span data-stu-id="698c4-152">Values accumulate on the stack and are pushed and popped according to individual operations.</span></span>  
  
## <a name="reverse-polish-notation-in-the-interceptor-configuration-file"></a><span data-ttu-id="698c4-153">侦听器配置文件中的逆波兰表示法</span><span class="sxs-lookup"><span data-stu-id="698c4-153">Reverse Polish Notation in the Interceptor Configuration File</span></span>  
 <span data-ttu-id="698c4-154">你将配置文件中侦听器中编写两个类型的表达式： 筛选表达式和数据表达式。</span><span class="sxs-lookup"><span data-stu-id="698c4-154">You will write two kinds of expressions in the interceptor configuration file: filter expressions and data expressions.</span></span> <span data-ttu-id="698c4-155">筛选器表达式预计可以为一个布尔值 RPN 表达式的结果`true`或`false`时数据表达式预期在堆栈上的单个值。</span><span class="sxs-lookup"><span data-stu-id="698c4-155">Filter expressions expect the result of the RPN expression to be a Boolean `true` or `false` while data expressions expect a single value on the stack.</span></span>  
  
### <a name="filter-expressions"></a><span data-ttu-id="698c4-156">筛选器表达式</span><span class="sxs-lookup"><span data-stu-id="698c4-156">Filter Expressions</span></span>  
 <span data-ttu-id="698c4-157">筛选器表达式的计算结果为布尔值`true`或`false`，用于标识特定的事件以跟踪 WF 或 WFC 应用程序中。</span><span class="sxs-lookup"><span data-stu-id="698c4-157">Filter expressions evaluate to Boolean `true` or `false` and are used to identify a specific event to track in the WF or WFC application.</span></span> <span data-ttu-id="698c4-158">在 WF 应用程序中，通常根据活动名称和事件进行筛选。</span><span class="sxs-lookup"><span data-stu-id="698c4-158">In WF applications, it is common to filter based on activity name and event.</span></span> <span data-ttu-id="698c4-159">例如，你可能想要选择**FoodAndDrinksPolicy**活动时**已关闭**。</span><span class="sxs-lookup"><span data-stu-id="698c4-159">For example, you may want to select the **FoodAndDrinksPolicy** activity when it is **Closed**.</span></span> <span data-ttu-id="698c4-160">使用 WF 运算，则可将此筛选器表示为：</span><span class="sxs-lookup"><span data-stu-id="698c4-160">Using WF operations, you could express the filter as:</span></span>  
  
 `(GetActivityName = "FoodAndDrinksPolicy") && (GetActivityEvent = "Closed")`  
  
 <span data-ttu-id="698c4-161">将此表达式转换为 RPN 可生成：</span><span class="sxs-lookup"><span data-stu-id="698c4-161">Converting this to RPN yields:</span></span>  
  
 `GetActivityName "FoodAndDrinksPolicy" == GetActivityEvent "Closed" == &&`  
  
 <span data-ttu-id="698c4-162">将此表达式转换为侦听器配置文件的等效表达式将生成以下 XML：</span><span class="sxs-lookup"><span data-stu-id="698c4-162">Converting this expression to the equivalent expression for the interceptor configuration file results in the following XML:</span></span>  
  
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
  
 <span data-ttu-id="698c4-163">最后，此表达式的计算结果将如下假设**GetActivityName**返回"DessertPolicy"和**GetActivityEvent**返回"已关闭":</span><span class="sxs-lookup"><span data-stu-id="698c4-163">Finally, this expression would be evaluated as follows assuming **GetActivityName** returned "DessertPolicy" and **GetActivityEvent** returned "Closed":</span></span>  
  
|<span data-ttu-id="698c4-164">输入</span><span class="sxs-lookup"><span data-stu-id="698c4-164">Input</span></span>|<span data-ttu-id="698c4-165">运算</span><span class="sxs-lookup"><span data-stu-id="698c4-165">Operation</span></span>|<span data-ttu-id="698c4-166">堆栈</span><span class="sxs-lookup"><span data-stu-id="698c4-166">Stack</span></span>|  
|-----------|---------------|-----------|  
||<span data-ttu-id="698c4-167">GetActivityName</span><span class="sxs-lookup"><span data-stu-id="698c4-167">GetActivityName</span></span>|<span data-ttu-id="698c4-168">"DessertPolicy"</span><span class="sxs-lookup"><span data-stu-id="698c4-168">"DessertPolicy"</span></span>|  
|<span data-ttu-id="698c4-169">"FoodAndDrinksPolicy"</span><span class="sxs-lookup"><span data-stu-id="698c4-169">"FoodAndDrinksPolicy"</span></span>|<span data-ttu-id="698c4-170">常量</span><span class="sxs-lookup"><span data-stu-id="698c4-170">Constant</span></span>|<span data-ttu-id="698c4-171">"DessertPolicy", "FoodAndDrinksPolicy"</span><span class="sxs-lookup"><span data-stu-id="698c4-171">"DessertPolicy", "FoodAndDrinksPolicy"</span></span>|  
|<span data-ttu-id="698c4-172">等于</span><span class="sxs-lookup"><span data-stu-id="698c4-172">Equals</span></span>|<span data-ttu-id="698c4-173">比较</span><span class="sxs-lookup"><span data-stu-id="698c4-173">Comparison</span></span>|<span data-ttu-id="698c4-174">False</span><span class="sxs-lookup"><span data-stu-id="698c4-174">False</span></span>|  
||<span data-ttu-id="698c4-175">GetActivityEvent</span><span class="sxs-lookup"><span data-stu-id="698c4-175">GetActivityEvent</span></span>|<span data-ttu-id="698c4-176">False, Closed</span><span class="sxs-lookup"><span data-stu-id="698c4-176">False, Closed</span></span>|  
|<span data-ttu-id="698c4-177">"Closed"</span><span class="sxs-lookup"><span data-stu-id="698c4-177">"Closed"</span></span>|<span data-ttu-id="698c4-178">常量</span><span class="sxs-lookup"><span data-stu-id="698c4-178">Constant</span></span>|<span data-ttu-id="698c4-179">False, "Closed", "Closed"</span><span class="sxs-lookup"><span data-stu-id="698c4-179">False, "Closed", "Closed"</span></span>|  
|<span data-ttu-id="698c4-180">等于</span><span class="sxs-lookup"><span data-stu-id="698c4-180">Equals</span></span>|<span data-ttu-id="698c4-181">比较</span><span class="sxs-lookup"><span data-stu-id="698c4-181">Comparison</span></span>|<span data-ttu-id="698c4-182">False, True</span><span class="sxs-lookup"><span data-stu-id="698c4-182">False, True</span></span>|  
|<span data-ttu-id="698c4-183">And</span><span class="sxs-lookup"><span data-stu-id="698c4-183">And</span></span>|<span data-ttu-id="698c4-184">逻辑和</span><span class="sxs-lookup"><span data-stu-id="698c4-184">Logical And</span></span>|<span data-ttu-id="698c4-185">False</span><span class="sxs-lookup"><span data-stu-id="698c4-185">False</span></span>|  
  
 <span data-ttu-id="698c4-186">在堆栈上保留的值是布尔值`False`。</span><span class="sxs-lookup"><span data-stu-id="698c4-186">The value left on the stack is Boolean `False`.</span></span> <span data-ttu-id="698c4-187">这将导致不会激发相应事件。</span><span class="sxs-lookup"><span data-stu-id="698c4-187">This will cause the corresponding event to not fire.</span></span> <span data-ttu-id="698c4-188">如果活动名为 "FoodAndDrinksPolicy"，则计算结果将为布尔值 `True`。</span><span class="sxs-lookup"><span data-stu-id="698c4-188">If the activity name were "FoodAndDrinksPolicy" then it would have evaluated to Boolean `True`.</span></span>  
  
 <span data-ttu-id="698c4-189">您可以通过使用 WCF 操作构造 （具有类似的评估） 的类似表达式`GetEndpointName`和`GetOperationName`。</span><span class="sxs-lookup"><span data-stu-id="698c4-189">You can construct a similar expression (with a similar evaluation) by using the WCF operations `GetEndpointName` and `GetOperationName`.</span></span>  
  
### <a name="data-expressions"></a><span data-ttu-id="698c4-190">数据表达式</span><span class="sxs-lookup"><span data-stu-id="698c4-190">Data Expressions</span></span>  
 <span data-ttu-id="698c4-191">数据表达式用于定义单个字符串数据值。</span><span class="sxs-lookup"><span data-stu-id="698c4-191">Data expressions are used to define a single string data value.</span></span> <span data-ttu-id="698c4-192">数据表达式是不包括任何表达式`Filter`元素。</span><span class="sxs-lookup"><span data-stu-id="698c4-192">A data expression is any expression that is not enclosed by a `Filter` element.</span></span> <span data-ttu-id="698c4-193">通过使用数据表达式`OnEvent`元素`CorrelationID`， `ContinuationToken`， `Reference`，和`Update`。</span><span class="sxs-lookup"><span data-stu-id="698c4-193">Data expressions are used by the `OnEvent` elements `CorrelationID`, `ContinuationToken`, `Reference`, and `Update`.</span></span>  
  
 <span data-ttu-id="698c4-194">通常要求使用已标记的时间戳来更新 BAM 活动数据库。</span><span class="sxs-lookup"><span data-stu-id="698c4-194">It is a common requirement to update the BAM activity database with a labeled time stamp.</span></span> <span data-ttu-id="698c4-195">例如，你可能想要捕获事件格式化为字符串开头的时间"启动： \<EventTime\>"。</span><span class="sxs-lookup"><span data-stu-id="698c4-195">For example, you might want to capture the time an event starts with a string formatted as "Start: \<EventTime\>".</span></span> <span data-ttu-id="698c4-196">为此，需要使用类似以下格式的表达式（其中 + 表示连接）：</span><span class="sxs-lookup"><span data-stu-id="698c4-196">To do this, you need to use an expression similar to the following (where + represents concatenation):</span></span>  
  
 `"Start: " + GetContextProperty(EventTime)`  
  
 <span data-ttu-id="698c4-197">将此表达式转换为 RPN 可生成：</span><span class="sxs-lookup"><span data-stu-id="698c4-197">Converting this to RPN yields:</span></span>  
  
 `"Start: " GetContextProperty(EventTime) +`  
  
 <span data-ttu-id="698c4-198">将此表达式转换为的等效表达式`Update`下面的 XML 中的侦听器的配置文件结果中的元素：</span><span class="sxs-lookup"><span data-stu-id="698c4-198">Converting this expression to the equivalent expression for an `Update` element in the interceptor configuration file results in the following XML:</span></span>  
  
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
  
 <span data-ttu-id="698c4-199">下表显示了在事件时间为“12:00 PM”的情况下如何解释该表达式。</span><span class="sxs-lookup"><span data-stu-id="698c4-199">The following table shows how this expression would be interpreted if the event time was "12:00 PM".</span></span>  
  
|<span data-ttu-id="698c4-200">输入</span><span class="sxs-lookup"><span data-stu-id="698c4-200">Input</span></span>|<span data-ttu-id="698c4-201">运算</span><span class="sxs-lookup"><span data-stu-id="698c4-201">Operation</span></span>|<span data-ttu-id="698c4-202">堆栈</span><span class="sxs-lookup"><span data-stu-id="698c4-202">Stack</span></span>|  
|-----------|---------------|-----------|  
|<span data-ttu-id="698c4-203">"启动:"</span><span class="sxs-lookup"><span data-stu-id="698c4-203">"Start: "</span></span>|<span data-ttu-id="698c4-204">常量</span><span class="sxs-lookup"><span data-stu-id="698c4-204">Constant</span></span>|<span data-ttu-id="698c4-205">"启动:"</span><span class="sxs-lookup"><span data-stu-id="698c4-205">"Start: "</span></span>|  
|<span data-ttu-id="698c4-206">GetContextProperty(EventTime)</span><span class="sxs-lookup"><span data-stu-id="698c4-206">GetContextProperty(EventTime)</span></span>|<span data-ttu-id="698c4-207">推送</span><span class="sxs-lookup"><span data-stu-id="698c4-207">Push</span></span>|<span data-ttu-id="698c4-208">"启动:"，"2006年-09-27T12:00:34.000Z"</span><span class="sxs-lookup"><span data-stu-id="698c4-208">"Start: ", "2006-09-27T12:00:34.000Z"</span></span>|  
|<span data-ttu-id="698c4-209">连接</span><span class="sxs-lookup"><span data-stu-id="698c4-209">Concatenate</span></span>|<span data-ttu-id="698c4-210">连接</span><span class="sxs-lookup"><span data-stu-id="698c4-210">Concatenate</span></span>|<span data-ttu-id="698c4-211">"启动： 2006年-09-27T12:00:34.000Z"</span><span class="sxs-lookup"><span data-stu-id="698c4-211">"Start: 2006-09-27T12:00:34.000Z"</span></span>|  
  
 <span data-ttu-id="698c4-212">使用更新命令的值将"启动： 2006年-09-27T12:00:34.000Z"。</span><span class="sxs-lookup"><span data-stu-id="698c4-212">The value used by the update command would be "Start: 2006-09-27T12:00:34.000Z".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="698c4-213">不要在数据表达式中使用比较运算符“And”或“Equals”。</span><span class="sxs-lookup"><span data-stu-id="698c4-213">Do not use the comparison operations "And" or "Equals" in data expressions.</span></span> <span data-ttu-id="698c4-214">如果使用这两种运算符，则部署侦听器配置文件时将收到一个错误。</span><span class="sxs-lookup"><span data-stu-id="698c4-214">If you do, you will receive an error when deploying your interceptor configuration file.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="698c4-215">本节内容</span><span class="sxs-lookup"><span data-stu-id="698c4-215">In This Section</span></span>  
 [<span data-ttu-id="698c4-216">侦听器运算</span><span class="sxs-lookup"><span data-stu-id="698c4-216">Interceptor Operations</span></span>](../core/interceptor-operations.md)  
  
## <a name="see-also"></a><span data-ttu-id="698c4-217">另请参阅</span><span class="sxs-lookup"><span data-stu-id="698c4-217">See Also</span></span>  
 [<span data-ttu-id="698c4-218">侦听器配置文件的结构</span><span class="sxs-lookup"><span data-stu-id="698c4-218">Structure of an Interceptor Configuration File</span></span>](../core/structure-of-an-interceptor-configuration-file.md)