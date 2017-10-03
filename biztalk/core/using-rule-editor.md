---
title: "使用规则编辑器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Rule Editor [Business Rule Composer], about Rule Editor
- Rule Editor [Business Rule Composer], Conditions Editor
- Business Rule Composer, Rule Editor
- Rule Editor [Business Rule Composer], Actions Editor
- Rule Editor [Business Rule Composer]
ms.assetid: 6559a8d1-6caf-4c6e-ac80-acaa4eb57938
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57041914d688b8d0dbe2bd0558e8572878218164
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-rule-editor"></a><span data-ttu-id="4e9fc-102">使用规则编辑器</span><span class="sxs-lookup"><span data-stu-id="4e9fc-102">Using Rule Editor</span></span>
<span data-ttu-id="4e9fc-103">使用 规则编辑器 ，可以在条件编辑器中查看和编辑所选规则的条件，也可以在操作编辑器中查看和编辑所选规则的操作。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-103">Use the Rule Editor to view and edit conditions in the Conditions Editor and actions in the Actions Editor for the selected rule.</span></span>  
  
## <a name="conditions-editor"></a><span data-ttu-id="4e9fc-104">条件编辑器</span><span class="sxs-lookup"><span data-stu-id="4e9fc-104">Conditions Editor</span></span>  
 <span data-ttu-id="4e9fc-105">使用 条件编辑器 （规则编辑器的一部分）可查看和编辑触发规则的条件。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-105">Use the Conditions Editor (part of the Rule Editor) to view and edit conditions for firing rules.</span></span> <span data-ttu-id="4e9fc-106">您可以通过使用快捷菜单添加内置谓词，从事实数据资源管理器来定义自变量和谓词，拖动项并通过单击参数链接输入自变量值内联。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-106">You can add built-in predicates by using the shortcut menu, drag items from the Facts Explorer to define arguments and predicates, and enter argument values inline by clicking an argument link.</span></span>  
  
 <span data-ttu-id="4e9fc-107">使用快捷菜单可访问以下选项：</span><span class="sxs-lookup"><span data-stu-id="4e9fc-107">Use the shortcut menu to access the following options.</span></span>  
  
|<span data-ttu-id="4e9fc-108">使用此选项</span><span class="sxs-lookup"><span data-stu-id="4e9fc-108">Use this</span></span>|<span data-ttu-id="4e9fc-109">执行的操作</span><span class="sxs-lookup"><span data-stu-id="4e9fc-109">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="4e9fc-110">**添加逻辑与**</span><span class="sxs-lookup"><span data-stu-id="4e9fc-110">**Add logical AND**</span></span>|<span data-ttu-id="4e9fc-111">添加一个运算符以组合两个或多个谓词，以形成逻辑**AND**表达式。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-111">Add an operator to combine two or more predicates to form a logical **AND** expression.</span></span>|  
|<span data-ttu-id="4e9fc-112">**添加逻辑或**</span><span class="sxs-lookup"><span data-stu-id="4e9fc-112">**Add logical OR**</span></span>|<span data-ttu-id="4e9fc-113">添加一个运算符以组合两个或多个谓词，以形成逻辑**OR**表达式。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-113">Add an operator to combine two or more predicates to form a logical **OR** expression.</span></span>|  
|<span data-ttu-id="4e9fc-114">**添加逻辑非**</span><span class="sxs-lookup"><span data-stu-id="4e9fc-114">**Add logical NOT**</span></span>|<span data-ttu-id="4e9fc-115">加法运算符**不**要求反的逻辑表达式或谓词。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-115">Add the operator **NOT** to negate a logical expression or predicate.</span></span>|  
|<span data-ttu-id="4e9fc-116">**谓词**</span><span class="sxs-lookup"><span data-stu-id="4e9fc-116">**Predicates**</span></span>|<span data-ttu-id="4e9fc-117">添加谓词表达式基于提供的规则对象模型，如内置谓词之一**等于**运算符。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-117">Add a predicate expression based on one of the built-in predicates provided by the Rule object model, such as the **Is Equal To** operator.</span></span>|  
|<span data-ttu-id="4e9fc-118">**谓词 \ 后**</span><span class="sxs-lookup"><span data-stu-id="4e9fc-118">**Predicates \ After**</span></span>|<span data-ttu-id="4e9fc-119">表示用于解答问题"后 time1 按时间顺序 time2"的临时谓词？</span><span class="sxs-lookup"><span data-stu-id="4e9fc-119">Represent the temporal predicate that answers the question "Is time1 chronologically after time2"?</span></span>|  
|<span data-ttu-id="4e9fc-120">**谓词 \ 之前**</span><span class="sxs-lookup"><span data-stu-id="4e9fc-120">**Predicates \ Before**</span></span>|<span data-ttu-id="4e9fc-121">表示临时谓词，回答"是按时间顺序之前 time2 time1"。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-121">Represent the temporal predicate that answers the question "Is time1 chronologically before time2."</span></span>|  
|<span data-ttu-id="4e9fc-122">**谓词 \ 之间**</span><span class="sxs-lookup"><span data-stu-id="4e9fc-122">**Predicates \ Between**</span></span>|<span data-ttu-id="4e9fc-123">表示临时谓词，回答"是按时间顺序之间 time2 和 time3 time1"。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-123">Represent the temporal predicate that answers the question "Is time1 chronologically between time2 and time3."</span></span>|  
|<span data-ttu-id="4e9fc-124">**谓词 \ 相等**</span><span class="sxs-lookup"><span data-stu-id="4e9fc-124">**Predicates \ Equal**</span></span>|<span data-ttu-id="4e9fc-125">表示关系的相等运算符。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-125">Represent the relational equality operator.</span></span>|  
|<span data-ttu-id="4e9fc-126">**谓词 \ 存在**</span><span class="sxs-lookup"><span data-stu-id="4e9fc-126">**Predicates \ Exists**</span></span>|<span data-ttu-id="4e9fc-127">表示在规则条件中使用的 XML 元素或属性存在谓词。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-127">Represent the XML element or attribute existence predicate used in rule conditions.</span></span>|  
|<span data-ttu-id="4e9fc-128">**谓词 \ GreaterThan**</span><span class="sxs-lookup"><span data-stu-id="4e9fc-128">**Predicates \ GreaterThan**</span></span>|<span data-ttu-id="4e9fc-129">表示关系的大于运算符。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-129">Represent the relational greater than operator.</span></span>|  
|<span data-ttu-id="4e9fc-130">**谓词 \ GreaterThanEqual**</span><span class="sxs-lookup"><span data-stu-id="4e9fc-130">**Predicates \ GreaterThanEqual**</span></span>|<span data-ttu-id="4e9fc-131">表示关系大于或等于运算符。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-131">Represent the relational greater than or equal to operator.</span></span>|  
|<span data-ttu-id="4e9fc-132">**谓词 \ LessThan**</span><span class="sxs-lookup"><span data-stu-id="4e9fc-132">**Predicates \ LessThan**</span></span>|<span data-ttu-id="4e9fc-133">表示关系小于运算符。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-133">Represent the relational less than operator.</span></span>|  
|<span data-ttu-id="4e9fc-134">**谓词 \ LessThanEqual**</span><span class="sxs-lookup"><span data-stu-id="4e9fc-134">**Predicates \ LessThanEqual**</span></span>|<span data-ttu-id="4e9fc-135">表示比关系小于或等于运算符。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-135">Represents the relational less than or equal to operator.</span></span>|  
|<span data-ttu-id="4e9fc-136">**谓词 \ 匹配**</span><span class="sxs-lookup"><span data-stu-id="4e9fc-136">**Predicates \ Match**</span></span>|<span data-ttu-id="4e9fc-137">确定是否存在指定的输入字符串中的正则表达式。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-137">Determines if a regular expression is present in a specified input string.</span></span>|  
|<span data-ttu-id="4e9fc-138">**谓词 \ NotEqual**</span><span class="sxs-lookup"><span data-stu-id="4e9fc-138">**Predicates \ NotEqual**</span></span>|<span data-ttu-id="4e9fc-139">表示关系不等运算符。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-139">Represent the relational inequality operator.</span></span>|  
|<span data-ttu-id="4e9fc-140">**谓词 \ 范围**</span><span class="sxs-lookup"><span data-stu-id="4e9fc-140">**Predicates \ Range**</span></span>|<span data-ttu-id="4e9fc-141">测试值是否可以为范围内。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-141">Test whether a value is between a range.</span></span>|  
|<span data-ttu-id="4e9fc-142">**删除逻辑运算符**</span><span class="sxs-lookup"><span data-stu-id="4e9fc-142">**Delete logical operator**</span></span>|<span data-ttu-id="4e9fc-143">删除所选的逻辑运算符 (**AND**， **OR**，或**不**)。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-143">Delete the selected logical operator (**AND**, **OR**, or **NOT**).</span></span>|  
|<span data-ttu-id="4e9fc-144">**删除谓词**</span><span class="sxs-lookup"><span data-stu-id="4e9fc-144">**Delete predicate**</span></span>|<span data-ttu-id="4e9fc-145">删除选定谓词。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-145">Delete the selected predicate.</span></span>|  
|<span data-ttu-id="4e9fc-146">**上移**</span><span class="sxs-lookup"><span data-stu-id="4e9fc-146">**Move Up**</span></span>|<span data-ttu-id="4e9fc-147">将谓词向上移动一个位置或上移一层。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-147">Move the predicate up one position or a level.</span></span>|  
|<span data-ttu-id="4e9fc-148">**下移**</span><span class="sxs-lookup"><span data-stu-id="4e9fc-148">**Move Down**</span></span>|<span data-ttu-id="4e9fc-149">将谓词向下移动一个位置或下移一层。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-149">Move the predicate down one position or a level.</span></span>|  
|<span data-ttu-id="4e9fc-150">**请转到词汇**</span><span class="sxs-lookup"><span data-stu-id="4e9fc-150">**Go to vocabulary**</span></span>|<span data-ttu-id="4e9fc-151">在事实浏览器中找到与所选谓词或参数相对应的词汇定义。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-151">Locate the vocabulary definition in the Facts Explorer that corresponds to the selected predicate or argument.</span></span>|  
|<span data-ttu-id="4e9fc-152">**转至源事实**</span><span class="sxs-lookup"><span data-stu-id="4e9fc-152">**Go to source fact**</span></span>|<span data-ttu-id="4e9fc-153">在事实浏览器中找到与所选谓词或参数相对应的 XML 元素、数据库列或 .NET 方法。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-153">Locate the XML element, database column, or .NET method in the Facts Explorer that corresponds to the selected predicate or argument.</span></span>|  
|<span data-ttu-id="4e9fc-154">**重置自变量**</span><span class="sxs-lookup"><span data-stu-id="4e9fc-154">**Reset argument**</span></span>|<span data-ttu-id="4e9fc-155">删除所选参数（以及所有嵌套参数）并恢复初始定义。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-155">Delete the selected argument (and any nested arguments), and restore the initial definition.</span></span>|  
|<span data-ttu-id="4e9fc-156">**设置为 null**</span><span class="sxs-lookup"><span data-stu-id="4e9fc-156">**Set to null**</span></span>|<span data-ttu-id="4e9fc-157">使用空常数定义替换所选参数。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-157">Replace the selected argument with a null constant definition.</span></span>|  
|<span data-ttu-id="4e9fc-158">**设置为空字符串**</span><span class="sxs-lookup"><span data-stu-id="4e9fc-158">**Set to empty string**</span></span>|<span data-ttu-id="4e9fc-159">使用空字符串值替换所选参数。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-159">Replace the selected argument with an empty string value.</span></span>|  
  
## <a name="actions-editor"></a><span data-ttu-id="4e9fc-160">操作编辑器</span><span class="sxs-lookup"><span data-stu-id="4e9fc-160">Actions Editor</span></span>  
 <span data-ttu-id="4e9fc-161">使用操作编辑器 （规则编辑器的一部分） 来查看和编辑引发规则时要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-161">Use the Actions Editor (part of the Rule Editor) to view and edit actions to execute when a rule is fired.</span></span> <span data-ttu-id="4e9fc-162">你可以添加使用快捷菜单中，内置操作从项拖动事实数据资源管理器来定义操作和参数，并通过单击参数链接一起输入多个自变量值。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-162">You can add built-in actions by using the shortcut menu, drag items from the Facts Explorer to define actions and arguments, and enter argument values inline by clicking an argument link.</span></span>  
  
|<span data-ttu-id="4e9fc-163">使用此选项</span><span class="sxs-lookup"><span data-stu-id="4e9fc-163">Use this</span></span>|<span data-ttu-id="4e9fc-164">执行的操作</span><span class="sxs-lookup"><span data-stu-id="4e9fc-164">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="4e9fc-165">**删除操作**</span><span class="sxs-lookup"><span data-stu-id="4e9fc-165">**Delete action**</span></span>|<span data-ttu-id="4e9fc-166">删除选定的操作。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-166">Delete the selected action.</span></span>|  
|<span data-ttu-id="4e9fc-167">**请转到词汇**</span><span class="sxs-lookup"><span data-stu-id="4e9fc-167">**Go to vocabulary**</span></span>|<span data-ttu-id="4e9fc-168">在事实浏览器中找到与所选操作或参数相对应的词汇定义。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-168">Locate the vocabulary definition in the Facts Explorer that corresponds to the selected action or argument.</span></span>|  
|<span data-ttu-id="4e9fc-169">**转至源事实**</span><span class="sxs-lookup"><span data-stu-id="4e9fc-169">**Go to source fact**</span></span>|<span data-ttu-id="4e9fc-170">在事实浏览器中找到与所选操作或参数相对应的 XML 元素、数据库列或 .NET 方法。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-170">Locate the XML element, database column, or .NET method in the Facts Explorer that corresponds to the selected action or argument.</span></span>|  
|<span data-ttu-id="4e9fc-171">**上移**</span><span class="sxs-lookup"><span data-stu-id="4e9fc-171">**Move Up**</span></span>|<span data-ttu-id="4e9fc-172">将操作向上移动一个位置或上移一层。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-172">Move the action up one position or a level.</span></span>|  
|<span data-ttu-id="4e9fc-173">**下移**</span><span class="sxs-lookup"><span data-stu-id="4e9fc-173">**Move Down**</span></span>|<span data-ttu-id="4e9fc-174">将操作向下移动一个位置或下移一层。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-174">Move the action down one position or a level.</span></span>|  
|<span data-ttu-id="4e9fc-175">**重置自变量**</span><span class="sxs-lookup"><span data-stu-id="4e9fc-175">**Reset argument**</span></span>|<span data-ttu-id="4e9fc-176">删除所选参数（以及所有嵌套参数）并恢复初始定义。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-176">Delete the selected argument (and any nested arguments), and restore the initial definition.</span></span>|  
|<span data-ttu-id="4e9fc-177">**设置为 null**</span><span class="sxs-lookup"><span data-stu-id="4e9fc-177">**Set to null**</span></span>|<span data-ttu-id="4e9fc-178">使用空常数定义替换所选参数。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-178">Replace the selected argument with a null constant definition.</span></span>|  
|<span data-ttu-id="4e9fc-179">**设置为空字符串**</span><span class="sxs-lookup"><span data-stu-id="4e9fc-179">**Set to empty string**</span></span>|<span data-ttu-id="4e9fc-180">使用空字符串值替换所选参数。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-180">Replace the selected argument with an empty string value.</span></span>|  
|<span data-ttu-id="4e9fc-181">**函数**</span><span class="sxs-lookup"><span data-stu-id="4e9fc-181">**Functions**</span></span>|<span data-ttu-id="4e9fc-182">添加自变量基于由规则对象模型，如提供的内置函数之一**添加**运算符。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-182">Add an argument based on one of the built-in functions provided by the Rule object model, such as the **Add** operator.</span></span>|  
|<span data-ttu-id="4e9fc-183">**ActualRebinds**</span><span class="sxs-lookup"><span data-stu-id="4e9fc-183">**Assert**</span></span>|<span data-ttu-id="4e9fc-184">将新的事实添加到规则引擎实例的工作内存。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-184">Add a new fact into the working memory of the rule engine instance.</span></span>|  
|<span data-ttu-id="4e9fc-185">**收回**</span><span class="sxs-lookup"><span data-stu-id="4e9fc-185">**Retract**</span></span>|<span data-ttu-id="4e9fc-186">规则引擎实例的工作内存中移除一个事实。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-186">Remove a fact from the working memory of the rule engine instance.</span></span>|  
|<span data-ttu-id="4e9fc-187">**RetractByType**</span><span class="sxs-lookup"><span data-stu-id="4e9fc-187">**RetractByType**</span></span>|<span data-ttu-id="4e9fc-188">规则引擎实例的工作内存中移除指定类型的事实。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-188">Remove a fact of specified type from the working memory of the rule engine instance.</span></span>|  
|<span data-ttu-id="4e9fc-189">**Clear**</span><span class="sxs-lookup"><span data-stu-id="4e9fc-189">**Clear**</span></span>|<span data-ttu-id="4e9fc-190">重置工作内存和计划是规则引擎实例。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-190">Reset the working memory and agenda of the rule engine instance.</span></span>|  
|<span data-ttu-id="4e9fc-191">**异常终止**</span><span class="sxs-lookup"><span data-stu-id="4e9fc-191">**Halt**</span></span>|<span data-ttu-id="4e9fc-192">终止规则处理。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-192">Terminate the rule processing.</span></span>|  
|<span data-ttu-id="4e9fc-193">**Update**</span><span class="sxs-lookup"><span data-stu-id="4e9fc-193">**Update**</span></span>|<span data-ttu-id="4e9fc-194">更新的规则引擎实例的工作内存中的事实。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-194">Update a fact in the working memory of the rule engine instance.</span></span>|  
  
## <a name="output-window"></a><span data-ttu-id="4e9fc-195">输出窗口</span><span class="sxs-lookup"><span data-stu-id="4e9fc-195">Output window</span></span>  
 <span data-ttu-id="4e9fc-196">使用输出窗口来查看所选的策略版本的测试执行的结果。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-196">Use the Output window to view results of test execution for a selected policy version.</span></span>  
  
 <span data-ttu-id="4e9fc-197">使用快捷菜单可访问以下选项：</span><span class="sxs-lookup"><span data-stu-id="4e9fc-197">Use the shortcut menu to access the following options.</span></span>  
  
|<span data-ttu-id="4e9fc-198">使用此选项</span><span class="sxs-lookup"><span data-stu-id="4e9fc-198">Use this</span></span>|<span data-ttu-id="4e9fc-199">执行的操作</span><span class="sxs-lookup"><span data-stu-id="4e9fc-199">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="4e9fc-200">**全部清除**</span><span class="sxs-lookup"><span data-stu-id="4e9fc-200">**Clear All**</span></span>|<span data-ttu-id="4e9fc-201">清除输出窗口中的所有文本。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-201">Clear all text from the Output window.</span></span>|  
|<span data-ttu-id="4e9fc-202">**复制**</span><span class="sxs-lookup"><span data-stu-id="4e9fc-202">**Copy**</span></span>|<span data-ttu-id="4e9fc-203">在输出窗口中选定的文本复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-203">Copy the selected text in the Output window to the Clipboard.</span></span>|  
|<span data-ttu-id="4e9fc-204">**全选**</span><span class="sxs-lookup"><span data-stu-id="4e9fc-204">**Select All**</span></span>|<span data-ttu-id="4e9fc-205">选择包含在输出窗口中的所有文本。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-205">Select all the text contained in the Output window.</span></span>|  
|<span data-ttu-id="4e9fc-206">**将保存到文件**</span><span class="sxs-lookup"><span data-stu-id="4e9fc-206">**Save to File**</span></span>|<span data-ttu-id="4e9fc-207">保存到指定文件的输出窗口中包含的文本。</span><span class="sxs-lookup"><span data-stu-id="4e9fc-207">Save the text contained in the Output window to a specified file.</span></span>|