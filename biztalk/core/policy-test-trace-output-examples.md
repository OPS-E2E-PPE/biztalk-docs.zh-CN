---
title: 策略测试跟踪输出示例 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing, policies
- policies, testing
- testing, examples
ms.assetid: 92e1dc7f-1a8d-41a5-84b6-46d5ad9f2ef2
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e3678769dffa03bb77c3e86fef02998a354b1fb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22266677"
---
# <a name="policy-test-trace-output-examples"></a><span data-ttu-id="1b4ac-102">策略测试跟踪输出示例</span><span class="sxs-lookup"><span data-stu-id="1b4ac-102">Policy Test Trace Output Examples</span></span>
<span data-ttu-id="1b4ac-103">本部分包含用于不同类型事实的策略测试输出的示例。</span><span class="sxs-lookup"><span data-stu-id="1b4ac-103">This section contains examples of the policy test output for different types of facts.</span></span>  
  
## <a name="net-class"></a><span data-ttu-id="1b4ac-104">.Net 类</span><span class="sxs-lookup"><span data-stu-id="1b4ac-104">.Net Class</span></span>  
 <span data-ttu-id="1b4ac-105">策略“ LoanProcessing” 中的示例规则“ TestRule1” ：</span><span class="sxs-lookup"><span data-stu-id="1b4ac-105">Example rule "TestRule1" in policy "LoanProcessing":</span></span>  
  
```  
IF test.get_ID > 0  
THEN <do something>  
```  
  
 <span data-ttu-id="1b4ac-106">**输出：**</span><span class="sxs-lookup"><span data-stu-id="1b4ac-106">**Output:**</span></span>  
  
 <span data-ttu-id="1b4ac-107">对于 RULESET 的规则引擎跟踪： LoanProcessing 2004 年 3 月 16 日上午 9:50:28</span><span class="sxs-lookup"><span data-stu-id="1b4ac-107">RULE ENGINE TRACE for RULESET: LoanProcessing 3/16/2004 9:50:28 AM</span></span>  
  
 <span data-ttu-id="1b4ac-108">事实活动 2004 年 3 月 16 日上午 9:50:28</span><span class="sxs-lookup"><span data-stu-id="1b4ac-108">FACT ACTIVITY 3/16/2004 9:50:28 AM</span></span>  
  
 <span data-ttu-id="1b4ac-109">规则引擎实例标识符: 9effe3f9-d3ad-4125-99fa-56bb379188f7</span><span class="sxs-lookup"><span data-stu-id="1b4ac-109">Rule Engine Instance Identifier: 9effe3f9-d3ad-4125-99fa-56bb379188f7</span></span>  
  
 <span data-ttu-id="1b4ac-110">规则集名称: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="1b4ac-110">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="1b4ac-111">操作: 添加</span><span class="sxs-lookup"><span data-stu-id="1b4ac-111">Operation: Assert</span></span>  
  
 <span data-ttu-id="1b4ac-112">对象类型: MyTest.test</span><span class="sxs-lookup"><span data-stu-id="1b4ac-112">Object Type: MyTest.test</span></span>  
  
 <span data-ttu-id="1b4ac-113">对象实例标识符： 872</span><span class="sxs-lookup"><span data-stu-id="1b4ac-113">Object Instance Identifier: 872</span></span>  
  
 <span data-ttu-id="1b4ac-114">条件评估测试 （匹配） 2004 年 3 月 16 日上午 9:50:28</span><span class="sxs-lookup"><span data-stu-id="1b4ac-114">CONDITION EVALUATION TEST (MATCH) 3/16/2004 9:50:28 AM</span></span>  
  
 <span data-ttu-id="1b4ac-115">规则引擎实例标识符: 9effe3f9-d3ad-4125-99fa-56bb379188f7</span><span class="sxs-lookup"><span data-stu-id="1b4ac-115">Rule Engine Instance Identifier: 9effe3f9-d3ad-4125-99fa-56bb379188f7</span></span>  
  
 <span data-ttu-id="1b4ac-116">规则集名称: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="1b4ac-116">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="1b4ac-117">测试表达式： MyTest.test.get_ID > 0</span><span class="sxs-lookup"><span data-stu-id="1b4ac-117">Test Expression: MyTest.test.get_ID > 0</span></span>  
  
 <span data-ttu-id="1b4ac-118">左操作数的值： 100</span><span class="sxs-lookup"><span data-stu-id="1b4ac-118">Left Operand Value: 100</span></span>  
  
 <span data-ttu-id="1b4ac-119">右操作数的值： 0</span><span class="sxs-lookup"><span data-stu-id="1b4ac-119">Right Operand Value: 0</span></span>  
  
 <span data-ttu-id="1b4ac-120">测试结果： True</span><span class="sxs-lookup"><span data-stu-id="1b4ac-120">Test Result: True</span></span>  
  
 <span data-ttu-id="1b4ac-121">安排更新 2004 年 3 月 16 日上午 9:50:28</span><span class="sxs-lookup"><span data-stu-id="1b4ac-121">AGENDA UPDATE 3/16/2004 9:50:28 AM</span></span>  
  
 <span data-ttu-id="1b4ac-122">规则引擎实例标识符: 9effe3f9-d3ad-4125-99fa-56bb379188f7</span><span class="sxs-lookup"><span data-stu-id="1b4ac-122">Rule Engine Instance Identifier: 9effe3f9-d3ad-4125-99fa-56bb379188f7</span></span>  
  
 <span data-ttu-id="1b4ac-123">规则集名称: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="1b4ac-123">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="1b4ac-124">操作： 添加</span><span class="sxs-lookup"><span data-stu-id="1b4ac-124">Operation: Add</span></span>  
  
 <span data-ttu-id="1b4ac-125">规则名称： TestRule1</span><span class="sxs-lookup"><span data-stu-id="1b4ac-125">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="1b4ac-126">冲突解决标准： 0</span><span class="sxs-lookup"><span data-stu-id="1b4ac-126">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="1b4ac-127">规则触发 2004 年 3 月 16 日上午 9:50:28</span><span class="sxs-lookup"><span data-stu-id="1b4ac-127">RULE FIRED 3/16/2004 9:50:28 AM</span></span>  
  
 <span data-ttu-id="1b4ac-128">规则引擎实例标识符: 9effe3f9-d3ad-4125-99fa-56bb379188f7</span><span class="sxs-lookup"><span data-stu-id="1b4ac-128">Rule Engine Instance Identifier: 9effe3f9-d3ad-4125-99fa-56bb379188f7</span></span>  
  
 <span data-ttu-id="1b4ac-129">规则集名称: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="1b4ac-129">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="1b4ac-130">规则名称： TestRule1</span><span class="sxs-lookup"><span data-stu-id="1b4ac-130">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="1b4ac-131">冲突解决标准： 0</span><span class="sxs-lookup"><span data-stu-id="1b4ac-131">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="1b4ac-132">事实活动 2004 年 3 月 16 日上午 9:50:28</span><span class="sxs-lookup"><span data-stu-id="1b4ac-132">FACT ACTIVITY 3/16/2004 9:50:28 AM</span></span>  
  
 <span data-ttu-id="1b4ac-133">规则引擎实例标识符: 9effe3f9-d3ad-4125-99fa-56bb379188f7</span><span class="sxs-lookup"><span data-stu-id="1b4ac-133">Rule Engine Instance Identifier: 9effe3f9-d3ad-4125-99fa-56bb379188f7</span></span>  
  
 <span data-ttu-id="1b4ac-134">规则集名称: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="1b4ac-134">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="1b4ac-135">操作： 收回</span><span class="sxs-lookup"><span data-stu-id="1b4ac-135">Operation: Retract</span></span>  
  
 <span data-ttu-id="1b4ac-136">对象类型: MyTest.test</span><span class="sxs-lookup"><span data-stu-id="1b4ac-136">Object Type: MyTest.test</span></span>  
  
 <span data-ttu-id="1b4ac-137">对象实例标识符： 872</span><span class="sxs-lookup"><span data-stu-id="1b4ac-137">Object Instance Identifier: 872</span></span>  
  
## <a name="dataconnectiontypeddatarow"></a><span data-ttu-id="1b4ac-138">DataConnection/TypedDataRow</span><span class="sxs-lookup"><span data-stu-id="1b4ac-138">DataConnection/TypedDataRow</span></span>  
 <span data-ttu-id="1b4ac-139">策略“ LoanProcessing” 中的示例规则“ TestRule1” ：</span><span class="sxs-lookup"><span data-stu-id="1b4ac-139">Example rule "TestRule1" in policy "LoanProcessing":</span></span>  
  
```  
IF NorthWind.CustInfo.CreditCardBalance > 0  
THEN <do something>  
```  
  
 <span data-ttu-id="1b4ac-140">**输出：**</span><span class="sxs-lookup"><span data-stu-id="1b4ac-140">**Output:**</span></span>  
  
 <span data-ttu-id="1b4ac-141">对于 RULESET 的规则引擎跟踪： LoanProcessing 2004 年 3 月 16 日上午 8:30:16</span><span class="sxs-lookup"><span data-stu-id="1b4ac-141">RULE ENGINE TRACE for RULESET: LoanProcessing 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="1b4ac-142">事实活动 3/16/2004 8:30:16 AM</span><span class="sxs-lookup"><span data-stu-id="1b4ac-142">FACT ACTIVITY 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="1b4ac-143">规则引擎实例标识符： 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="1b4ac-143">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="1b4ac-144">规则集名称: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="1b4ac-144">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="1b4ac-145">操作: 添加</span><span class="sxs-lookup"><span data-stu-id="1b4ac-145">Operation: Assert</span></span>  
  
 <span data-ttu-id="1b4ac-146">对象类型： DataConnection:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="1b4ac-146">Object Type: DataConnection:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="1b4ac-147">对象实例标识符： 874</span><span class="sxs-lookup"><span data-stu-id="1b4ac-147">Object Instance Identifier: 874</span></span>  
  
 <span data-ttu-id="1b4ac-148">条件评估测试(匹配) 3/16/2004 8:30:16 AM</span><span class="sxs-lookup"><span data-stu-id="1b4ac-148">CONDITION EVALUATION TEST (MATCH) 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="1b4ac-149">规则引擎实例标识符： 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="1b4ac-149">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="1b4ac-150">规则集名称: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="1b4ac-150">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="1b4ac-151">测试表达式： 选择 \* 从 [CustInfo] 其中 [CreditCardBalance] > 0</span><span class="sxs-lookup"><span data-stu-id="1b4ac-151">Test Expression: select \* from [CustInfo] where [CreditCardBalance] > 0</span></span>  
  
 <span data-ttu-id="1b4ac-152">左操作数的值：</span><span class="sxs-lookup"><span data-stu-id="1b4ac-152">Left Operand Value:</span></span>  
  
 <span data-ttu-id="1b4ac-153">右操作数的值:</span><span class="sxs-lookup"><span data-stu-id="1b4ac-153">Right Operand Value:</span></span>  
  
 <span data-ttu-id="1b4ac-154">测试结果： True</span><span class="sxs-lookup"><span data-stu-id="1b4ac-154">Test Result: True</span></span>  
  
 <span data-ttu-id="1b4ac-155">事实活动 3/16/2004 8:30:16 AM</span><span class="sxs-lookup"><span data-stu-id="1b4ac-155">FACT ACTIVITY 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="1b4ac-156">规则引擎实例标识符： 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="1b4ac-156">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="1b4ac-157">规则集名称: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="1b4ac-157">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="1b4ac-158">操作: 添加</span><span class="sxs-lookup"><span data-stu-id="1b4ac-158">Operation: Assert</span></span>  
  
 <span data-ttu-id="1b4ac-159">对象类型： TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="1b4ac-159">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="1b4ac-160">对象实例标识符： 177556</span><span class="sxs-lookup"><span data-stu-id="1b4ac-160">Object Instance Identifier: 177556</span></span>  
  
 <span data-ttu-id="1b4ac-161">日程更新 3/16/2004 8:30:16 AM</span><span class="sxs-lookup"><span data-stu-id="1b4ac-161">AGENDA UPDATE 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="1b4ac-162">规则引擎实例标识符： 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="1b4ac-162">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="1b4ac-163">规则集名称: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="1b4ac-163">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="1b4ac-164">操作： 添加</span><span class="sxs-lookup"><span data-stu-id="1b4ac-164">Operation: Add</span></span>  
  
 <span data-ttu-id="1b4ac-165">规则名称： TestRule1</span><span class="sxs-lookup"><span data-stu-id="1b4ac-165">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="1b4ac-166">冲突解决标准： 0</span><span class="sxs-lookup"><span data-stu-id="1b4ac-166">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="1b4ac-167">事实活动 3/16/2004 8:30:16 AM</span><span class="sxs-lookup"><span data-stu-id="1b4ac-167">FACT ACTIVITY 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="1b4ac-168">规则引擎实例标识符： 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="1b4ac-168">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="1b4ac-169">规则集名称: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="1b4ac-169">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="1b4ac-170">操作: 添加</span><span class="sxs-lookup"><span data-stu-id="1b4ac-170">Operation: Assert</span></span>  
  
 <span data-ttu-id="1b4ac-171">对象类型： TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="1b4ac-171">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="1b4ac-172">对象实例标识符： 177559</span><span class="sxs-lookup"><span data-stu-id="1b4ac-172">Object Instance Identifier: 177559</span></span>  
  
 <span data-ttu-id="1b4ac-173">日程更新 3/16/2004 8:30:16 AM</span><span class="sxs-lookup"><span data-stu-id="1b4ac-173">AGENDA UPDATE 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="1b4ac-174">规则引擎实例标识符： 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="1b4ac-174">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="1b4ac-175">规则集名称: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="1b4ac-175">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="1b4ac-176">操作： 添加</span><span class="sxs-lookup"><span data-stu-id="1b4ac-176">Operation: Add</span></span>  
  
 <span data-ttu-id="1b4ac-177">规则名称： TestRule1</span><span class="sxs-lookup"><span data-stu-id="1b4ac-177">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="1b4ac-178">冲突解决标准： 0</span><span class="sxs-lookup"><span data-stu-id="1b4ac-178">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="1b4ac-179">事实活动 3/16/2004 8:30:16 AM</span><span class="sxs-lookup"><span data-stu-id="1b4ac-179">FACT ACTIVITY 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="1b4ac-180">规则引擎实例标识符： 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="1b4ac-180">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="1b4ac-181">规则集名称: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="1b4ac-181">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="1b4ac-182">操作: 添加</span><span class="sxs-lookup"><span data-stu-id="1b4ac-182">Operation: Assert</span></span>  
  
 <span data-ttu-id="1b4ac-183">对象类型： TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="1b4ac-183">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="1b4ac-184">对象实例标识符： 177558</span><span class="sxs-lookup"><span data-stu-id="1b4ac-184">Object Instance Identifier: 177558</span></span>  
  
 <span data-ttu-id="1b4ac-185">日程更新 3/16/2004 8:30:16 AM</span><span class="sxs-lookup"><span data-stu-id="1b4ac-185">AGENDA UPDATE 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="1b4ac-186">规则引擎实例标识符： 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="1b4ac-186">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="1b4ac-187">规则集名称: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="1b4ac-187">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="1b4ac-188">操作： 添加</span><span class="sxs-lookup"><span data-stu-id="1b4ac-188">Operation: Add</span></span>  
  
 <span data-ttu-id="1b4ac-189">规则名称： TestRule1</span><span class="sxs-lookup"><span data-stu-id="1b4ac-189">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="1b4ac-190">冲突解决标准： 0</span><span class="sxs-lookup"><span data-stu-id="1b4ac-190">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="1b4ac-191">触发的规则 3/16/2004 8:30:16 AM</span><span class="sxs-lookup"><span data-stu-id="1b4ac-191">RULE FIRED 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="1b4ac-192">规则引擎实例标识符： 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="1b4ac-192">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="1b4ac-193">规则集名称: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="1b4ac-193">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="1b4ac-194">规则名称： TestRule1</span><span class="sxs-lookup"><span data-stu-id="1b4ac-194">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="1b4ac-195">冲突解决标准： 0</span><span class="sxs-lookup"><span data-stu-id="1b4ac-195">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="1b4ac-196">触发的规则 3/16/2004 8:30:16 AM</span><span class="sxs-lookup"><span data-stu-id="1b4ac-196">RULE FIRED 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="1b4ac-197">规则引擎实例标识符： 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="1b4ac-197">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="1b4ac-198">规则集名称: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="1b4ac-198">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="1b4ac-199">规则名称： TestRule1</span><span class="sxs-lookup"><span data-stu-id="1b4ac-199">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="1b4ac-200">冲突解决标准： 0</span><span class="sxs-lookup"><span data-stu-id="1b4ac-200">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="1b4ac-201">触发的规则 3/16/2004 8:30:16 AM</span><span class="sxs-lookup"><span data-stu-id="1b4ac-201">RULE FIRED 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="1b4ac-202">规则引擎实例标识符： 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="1b4ac-202">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="1b4ac-203">规则集名称: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="1b4ac-203">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="1b4ac-204">规则名称： TestRule1</span><span class="sxs-lookup"><span data-stu-id="1b4ac-204">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="1b4ac-205">冲突解决标准： 0</span><span class="sxs-lookup"><span data-stu-id="1b4ac-205">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="1b4ac-206">事实活动 3/16/2004 8:30:16 AM</span><span class="sxs-lookup"><span data-stu-id="1b4ac-206">FACT ACTIVITY 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="1b4ac-207">规则引擎实例标识符： 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="1b4ac-207">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="1b4ac-208">规则集名称: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="1b4ac-208">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="1b4ac-209">操作： 收回</span><span class="sxs-lookup"><span data-stu-id="1b4ac-209">Operation: Retract</span></span>  
  
 <span data-ttu-id="1b4ac-210">对象类型： DataConnection:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="1b4ac-210">Object Type: DataConnection:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="1b4ac-211">对象实例标识符： 874</span><span class="sxs-lookup"><span data-stu-id="1b4ac-211">Object Instance Identifier: 874</span></span>  
  
 <span data-ttu-id="1b4ac-212">事实活动 3/16/2004 8:30:16 AM</span><span class="sxs-lookup"><span data-stu-id="1b4ac-212">FACT ACTIVITY 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="1b4ac-213">规则引擎实例标识符： 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="1b4ac-213">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="1b4ac-214">规则集名称: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="1b4ac-214">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="1b4ac-215">操作： 收回</span><span class="sxs-lookup"><span data-stu-id="1b4ac-215">Operation: Retract</span></span>  
  
 <span data-ttu-id="1b4ac-216">对象类型： TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="1b4ac-216">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="1b4ac-217">对象实例标识符： 177559</span><span class="sxs-lookup"><span data-stu-id="1b4ac-217">Object Instance Identifier: 177559</span></span>  
  
 <span data-ttu-id="1b4ac-218">事实活动 3/16/2004 8:30:16 AM</span><span class="sxs-lookup"><span data-stu-id="1b4ac-218">FACT ACTIVITY 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="1b4ac-219">规则引擎实例标识符： 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="1b4ac-219">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="1b4ac-220">规则集名称: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="1b4ac-220">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="1b4ac-221">操作： 收回</span><span class="sxs-lookup"><span data-stu-id="1b4ac-221">Operation: Retract</span></span>  
  
 <span data-ttu-id="1b4ac-222">对象类型： TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="1b4ac-222">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="1b4ac-223">对象实例标识符： 177558</span><span class="sxs-lookup"><span data-stu-id="1b4ac-223">Object Instance Identifier: 177558</span></span>  
  
 <span data-ttu-id="1b4ac-224">事实活动 3/16/2004 8:30:16 AM</span><span class="sxs-lookup"><span data-stu-id="1b4ac-224">FACT ACTIVITY 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="1b4ac-225">规则引擎实例标识符： 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="1b4ac-225">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="1b4ac-226">规则集名称: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="1b4ac-226">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="1b4ac-227">操作： 收回</span><span class="sxs-lookup"><span data-stu-id="1b4ac-227">Operation: Retract</span></span>  
  
 <span data-ttu-id="1b4ac-228">对象类型： TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="1b4ac-228">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="1b4ac-229">对象实例标识符： 177556</span><span class="sxs-lookup"><span data-stu-id="1b4ac-229">Object Instance Identifier: 177556</span></span>  
  
 <span data-ttu-id="1b4ac-230">以上示例指示 CustInfo 表中有三行满足该规则中的条件。</span><span class="sxs-lookup"><span data-stu-id="1b4ac-230">The example above indicates that three rows in the CustInfo table met the condition in the rule.</span></span>  <span data-ttu-id="1b4ac-231">这导致三个唯一的 TypedDataRow 被添加到引擎中并对每个实例进行了议程更新和规则触发。</span><span class="sxs-lookup"><span data-stu-id="1b4ac-231">This caused three unique TypedDataRows to be asserted into the engine and an agenda update and rule firing to occur for each instance.</span></span>  
  
## <a name="typedatatabletypeddatarow"></a><span data-ttu-id="1b4ac-232">TypeDataTable/TypedDataRow</span><span class="sxs-lookup"><span data-stu-id="1b4ac-232">TypeDataTable/TypedDataRow</span></span>  
 <span data-ttu-id="1b4ac-233">策略“ LoanProcessing” 中的示例规则“ TestRule1” ：</span><span class="sxs-lookup"><span data-stu-id="1b4ac-233">Example rule "TestRule1" in policy "LoanProcessing":</span></span>  
  
```  
IF NorthWind.CustInfo.CreditCardBalance > 0  
THEN <do something>  
```  
  
 <span data-ttu-id="1b4ac-234">**输出：**</span><span class="sxs-lookup"><span data-stu-id="1b4ac-234">**Output:**</span></span>  
  
 <span data-ttu-id="1b4ac-235">对于 RULESET 的规则引擎跟踪： LoanProcessing 2004 年 3 月 17 日上午 11:27:35</span><span class="sxs-lookup"><span data-stu-id="1b4ac-235">RULE ENGINE TRACE for RULESET: LoanProcessing 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="1b4ac-236">事实活动 2004 年 3 月 17 日上午 11:27:35</span><span class="sxs-lookup"><span data-stu-id="1b4ac-236">FACT ACTIVITY 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="1b4ac-237">规则引擎实例标识符： 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="1b4ac-237">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="1b4ac-238">规则集名称: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="1b4ac-238">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="1b4ac-239">操作: 添加</span><span class="sxs-lookup"><span data-stu-id="1b4ac-239">Operation: Assert</span></span>  
  
 <span data-ttu-id="1b4ac-240">对象类型： TypedDataTable:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="1b4ac-240">Object Type: TypedDataTable:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="1b4ac-241">对象实例标识符： 377</span><span class="sxs-lookup"><span data-stu-id="1b4ac-241">Object Instance Identifier: 377</span></span>  
  
 <span data-ttu-id="1b4ac-242">事实活动 2004 年 3 月 17 日上午 11:27:35</span><span class="sxs-lookup"><span data-stu-id="1b4ac-242">FACT ACTIVITY 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="1b4ac-243">规则引擎实例标识符： 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="1b4ac-243">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="1b4ac-244">规则集名称: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="1b4ac-244">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="1b4ac-245">操作: 添加</span><span class="sxs-lookup"><span data-stu-id="1b4ac-245">Operation: Assert</span></span>  
  
 <span data-ttu-id="1b4ac-246">对象类型： TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="1b4ac-246">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="1b4ac-247">对象实例标识符： 376</span><span class="sxs-lookup"><span data-stu-id="1b4ac-247">Object Instance Identifier: 376</span></span>  
  
 <span data-ttu-id="1b4ac-248">条件评估测试 （匹配） 2004 年 3 月 17 日上午 11:27:35</span><span class="sxs-lookup"><span data-stu-id="1b4ac-248">CONDITION EVALUATION TEST (MATCH) 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="1b4ac-249">规则引擎实例标识符： 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="1b4ac-249">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="1b4ac-250">规则集名称: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="1b4ac-250">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="1b4ac-251">测试表达式： TypedDataRow:Northwind:CustInfo.CreditCardBalance > 0</span><span class="sxs-lookup"><span data-stu-id="1b4ac-251">Test Expression: TypedDataRow:Northwind:CustInfo.CreditCardBalance > 0</span></span>  
  
 <span data-ttu-id="1b4ac-252">左操作数的值： 500</span><span class="sxs-lookup"><span data-stu-id="1b4ac-252">Left Operand Value: 500</span></span>  
  
 <span data-ttu-id="1b4ac-253">右操作数的值： 0</span><span class="sxs-lookup"><span data-stu-id="1b4ac-253">Right Operand Value: 0</span></span>  
  
 <span data-ttu-id="1b4ac-254">测试结果： True</span><span class="sxs-lookup"><span data-stu-id="1b4ac-254">Test Result: True</span></span>  
  
 <span data-ttu-id="1b4ac-255">安排更新 2004 年 3 月 17 日上午 11:27:35</span><span class="sxs-lookup"><span data-stu-id="1b4ac-255">AGENDA UPDATE 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="1b4ac-256">规则引擎实例标识符： 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="1b4ac-256">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="1b4ac-257">规则集名称: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="1b4ac-257">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="1b4ac-258">操作： 添加</span><span class="sxs-lookup"><span data-stu-id="1b4ac-258">Operation: Add</span></span>  
  
 <span data-ttu-id="1b4ac-259">规则名称： TestRule1</span><span class="sxs-lookup"><span data-stu-id="1b4ac-259">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="1b4ac-260">冲突解决标准： 0</span><span class="sxs-lookup"><span data-stu-id="1b4ac-260">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="1b4ac-261">事实活动 2004 年 3 月 17 日上午 11:27:35</span><span class="sxs-lookup"><span data-stu-id="1b4ac-261">FACT ACTIVITY 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="1b4ac-262">规则引擎实例标识符： 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="1b4ac-262">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="1b4ac-263">规则集名称: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="1b4ac-263">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="1b4ac-264">操作: 添加</span><span class="sxs-lookup"><span data-stu-id="1b4ac-264">Operation: Assert</span></span>  
  
 <span data-ttu-id="1b4ac-265">对象类型： TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="1b4ac-265">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="1b4ac-266">对象实例标识符： 375</span><span class="sxs-lookup"><span data-stu-id="1b4ac-266">Object Instance Identifier: 375</span></span>  
  
 <span data-ttu-id="1b4ac-267">条件评估测试 （匹配） 2004 年 3 月 17 日上午 11:27:35</span><span class="sxs-lookup"><span data-stu-id="1b4ac-267">CONDITION EVALUATION TEST (MATCH) 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="1b4ac-268">规则引擎实例标识符： 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="1b4ac-268">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="1b4ac-269">规则集名称: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="1b4ac-269">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="1b4ac-270">测试表达式： TypedDataRow:Northwind:CustInfo.CreditCardBalance > 0</span><span class="sxs-lookup"><span data-stu-id="1b4ac-270">Test Expression: TypedDataRow:Northwind:CustInfo.CreditCardBalance > 0</span></span>  
  
 <span data-ttu-id="1b4ac-271">左操作数的值： 1000年</span><span class="sxs-lookup"><span data-stu-id="1b4ac-271">Left Operand Value: 1000</span></span>  
  
 <span data-ttu-id="1b4ac-272">右操作数的值： 0</span><span class="sxs-lookup"><span data-stu-id="1b4ac-272">Right Operand Value: 0</span></span>  
  
 <span data-ttu-id="1b4ac-273">测试结果： True</span><span class="sxs-lookup"><span data-stu-id="1b4ac-273">Test Result: True</span></span>  
  
 <span data-ttu-id="1b4ac-274">安排更新 2004 年 3 月 17 日上午 11:27:35</span><span class="sxs-lookup"><span data-stu-id="1b4ac-274">AGENDA UPDATE 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="1b4ac-275">规则引擎实例标识符： 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="1b4ac-275">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="1b4ac-276">规则集名称: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="1b4ac-276">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="1b4ac-277">操作： 添加</span><span class="sxs-lookup"><span data-stu-id="1b4ac-277">Operation: Add</span></span>  
  
 <span data-ttu-id="1b4ac-278">规则名称： TestRule1</span><span class="sxs-lookup"><span data-stu-id="1b4ac-278">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="1b4ac-279">冲突解决标准： 0</span><span class="sxs-lookup"><span data-stu-id="1b4ac-279">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="1b4ac-280">事实活动 2004 年 3 月 17 日上午 11:27:35</span><span class="sxs-lookup"><span data-stu-id="1b4ac-280">FACT ACTIVITY 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="1b4ac-281">规则引擎实例标识符： 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="1b4ac-281">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="1b4ac-282">规则集名称: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="1b4ac-282">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="1b4ac-283">操作: 添加</span><span class="sxs-lookup"><span data-stu-id="1b4ac-283">Operation: Assert</span></span>  
  
 <span data-ttu-id="1b4ac-284">对象类型： TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="1b4ac-284">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="1b4ac-285">对象实例标识符： 374</span><span class="sxs-lookup"><span data-stu-id="1b4ac-285">Object Instance Identifier: 374</span></span>  
  
 <span data-ttu-id="1b4ac-286">条件评估测试 （匹配） 2004 年 3 月 17 日上午 11:27:35</span><span class="sxs-lookup"><span data-stu-id="1b4ac-286">CONDITION EVALUATION TEST (MATCH) 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="1b4ac-287">规则引擎实例标识符： 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="1b4ac-287">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="1b4ac-288">规则集名称: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="1b4ac-288">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="1b4ac-289">测试表达式： TypedDataRow:Northwind:CustInfo.CreditCardBalance > 0</span><span class="sxs-lookup"><span data-stu-id="1b4ac-289">Test Expression: TypedDataRow:Northwind:CustInfo.CreditCardBalance > 0</span></span>  
  
 <span data-ttu-id="1b4ac-290">左操作数的值： 35000</span><span class="sxs-lookup"><span data-stu-id="1b4ac-290">Left Operand Value: 35000</span></span>  
  
 <span data-ttu-id="1b4ac-291">右操作数的值： 0</span><span class="sxs-lookup"><span data-stu-id="1b4ac-291">Right Operand Value: 0</span></span>  
  
 <span data-ttu-id="1b4ac-292">测试结果： True</span><span class="sxs-lookup"><span data-stu-id="1b4ac-292">Test Result: True</span></span>  
  
 <span data-ttu-id="1b4ac-293">安排更新 2004 年 3 月 17 日上午 11:27:35</span><span class="sxs-lookup"><span data-stu-id="1b4ac-293">AGENDA UPDATE 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="1b4ac-294">规则引擎实例标识符： 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="1b4ac-294">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="1b4ac-295">规则集名称: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="1b4ac-295">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="1b4ac-296">操作： 添加</span><span class="sxs-lookup"><span data-stu-id="1b4ac-296">Operation: Add</span></span>  
  
 <span data-ttu-id="1b4ac-297">规则名称： TestRule1</span><span class="sxs-lookup"><span data-stu-id="1b4ac-297">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="1b4ac-298">冲突解决标准： 0</span><span class="sxs-lookup"><span data-stu-id="1b4ac-298">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="1b4ac-299">规则触发 2004 年 3 月 17 日上午 11:27:35</span><span class="sxs-lookup"><span data-stu-id="1b4ac-299">RULE FIRED 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="1b4ac-300">规则引擎实例标识符： 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="1b4ac-300">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="1b4ac-301">规则集名称: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="1b4ac-301">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="1b4ac-302">规则名称： TestRule1</span><span class="sxs-lookup"><span data-stu-id="1b4ac-302">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="1b4ac-303">冲突解决标准： 0</span><span class="sxs-lookup"><span data-stu-id="1b4ac-303">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="1b4ac-304">规则触发 2004 年 3 月 17 日上午 11:27:35</span><span class="sxs-lookup"><span data-stu-id="1b4ac-304">RULE FIRED 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="1b4ac-305">规则引擎实例标识符： 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="1b4ac-305">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="1b4ac-306">规则集名称: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="1b4ac-306">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="1b4ac-307">规则名称： TestRule1</span><span class="sxs-lookup"><span data-stu-id="1b4ac-307">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="1b4ac-308">冲突解决标准： 0</span><span class="sxs-lookup"><span data-stu-id="1b4ac-308">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="1b4ac-309">规则触发 2004 年 3 月 17 日上午 11:27:35</span><span class="sxs-lookup"><span data-stu-id="1b4ac-309">RULE FIRED 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="1b4ac-310">规则引擎实例标识符： 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="1b4ac-310">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="1b4ac-311">规则集名称: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="1b4ac-311">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="1b4ac-312">规则名称： TestRule1</span><span class="sxs-lookup"><span data-stu-id="1b4ac-312">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="1b4ac-313">冲突解决标准： 0</span><span class="sxs-lookup"><span data-stu-id="1b4ac-313">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="1b4ac-314">事实活动 2004 年 3 月 17 日上午 11:27:35</span><span class="sxs-lookup"><span data-stu-id="1b4ac-314">FACT ACTIVITY 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="1b4ac-315">规则引擎实例标识符： 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="1b4ac-315">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="1b4ac-316">规则集名称: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="1b4ac-316">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="1b4ac-317">操作： 收回</span><span class="sxs-lookup"><span data-stu-id="1b4ac-317">Operation: Retract</span></span>  
  
 <span data-ttu-id="1b4ac-318">对象类型： TypedDataTable:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="1b4ac-318">Object Type: TypedDataTable:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="1b4ac-319">对象实例标识符： 377</span><span class="sxs-lookup"><span data-stu-id="1b4ac-319">Object Instance Identifier: 377</span></span>  
  
 <span data-ttu-id="1b4ac-320">事实活动 2004 年 3 月 17 日上午 11:27:35</span><span class="sxs-lookup"><span data-stu-id="1b4ac-320">FACT ACTIVITY 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="1b4ac-321">规则引擎实例标识符： 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="1b4ac-321">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="1b4ac-322">规则集名称: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="1b4ac-322">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="1b4ac-323">操作： 收回</span><span class="sxs-lookup"><span data-stu-id="1b4ac-323">Operation: Retract</span></span>  
  
 <span data-ttu-id="1b4ac-324">对象类型： TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="1b4ac-324">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="1b4ac-325">对象实例标识符： 375</span><span class="sxs-lookup"><span data-stu-id="1b4ac-325">Object Instance Identifier: 375</span></span>  
  
 <span data-ttu-id="1b4ac-326">事实活动 2004 年 3 月 17 日上午 11:27:35</span><span class="sxs-lookup"><span data-stu-id="1b4ac-326">FACT ACTIVITY 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="1b4ac-327">规则引擎实例标识符： 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="1b4ac-327">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="1b4ac-328">规则集名称: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="1b4ac-328">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="1b4ac-329">操作： 收回</span><span class="sxs-lookup"><span data-stu-id="1b4ac-329">Operation: Retract</span></span>  
  
 <span data-ttu-id="1b4ac-330">对象类型： TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="1b4ac-330">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="1b4ac-331">对象实例标识符： 374</span><span class="sxs-lookup"><span data-stu-id="1b4ac-331">Object Instance Identifier: 374</span></span>  
  
 <span data-ttu-id="1b4ac-332">事实活动 2004 年 3 月 17 日上午 11:27:35</span><span class="sxs-lookup"><span data-stu-id="1b4ac-332">FACT ACTIVITY 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="1b4ac-333">规则引擎实例标识符： 0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="1b4ac-333">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="1b4ac-334">规则集名称: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="1b4ac-334">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="1b4ac-335">操作： 收回</span><span class="sxs-lookup"><span data-stu-id="1b4ac-335">Operation: Retract</span></span>  
  
 <span data-ttu-id="1b4ac-336">对象类型： TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="1b4ac-336">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="1b4ac-337">对象实例标识符： 376</span><span class="sxs-lookup"><span data-stu-id="1b4ac-337">Object Instance Identifier: 376</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b4ac-338">以上示例显示 TypedDataTable 包含三行，每行均作为 TypedDataRow 添加。</span><span class="sxs-lookup"><span data-stu-id="1b4ac-338">The example above shows that the TypedDataTable contained three rows, and each was asserted as a TypedDataRow.</span></span>  <span data-ttu-id="1b4ac-339">每行在条件中的计算结果都为 True，因而导致该规则被添加到议程中并且已触发。</span><span class="sxs-lookup"><span data-stu-id="1b4ac-339">Each evaluated to True in the condition and caused the rule to be added to the agenda and fired.</span></span>  
  
## <a name="typedxmldocument"></a><span data-ttu-id="1b4ac-340">TypedXmlDocument</span><span class="sxs-lookup"><span data-stu-id="1b4ac-340">TypedXmlDocument</span></span>  
 <span data-ttu-id="1b4ac-341">策略“ LoanProcessing” 中的示例规则“ TestRule1” ：</span><span class="sxs-lookup"><span data-stu-id="1b4ac-341">Example rule "TestRule1" in policy "LoanProcessing":</span></span>  
  
```  
IF Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType.TimeInMonths >= 4  
THEN <do something>  
```  
  
 <span data-ttu-id="1b4ac-342">**输出：**</span><span class="sxs-lookup"><span data-stu-id="1b4ac-342">**Output:**</span></span>  
  
 <span data-ttu-id="1b4ac-343">对于 RULESET 的规则引擎跟踪： LoanProcessing 2004 年 3 月 17 日上午 9:23:05</span><span class="sxs-lookup"><span data-stu-id="1b4ac-343">RULE ENGINE TRACE for RULESET: LoanProcessing 3/17/2004 9:23:05 AM</span></span>  
  
 <span data-ttu-id="1b4ac-344">事实活动 2004 年 3 月 17 日上午 9:23:05</span><span class="sxs-lookup"><span data-stu-id="1b4ac-344">FACT ACTIVITY 3/17/2004 9:23:05 AM</span></span>  
  
 <span data-ttu-id="1b4ac-345">规则引擎实例标识符： 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span><span class="sxs-lookup"><span data-stu-id="1b4ac-345">Rule Engine Instance Identifier: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span></span>  
  
 <span data-ttu-id="1b4ac-346">规则集名称: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="1b4ac-346">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="1b4ac-347">操作: 添加</span><span class="sxs-lookup"><span data-stu-id="1b4ac-347">Operation: Assert</span></span>  
  
 <span data-ttu-id="1b4ac-348">对象类型： TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case</span><span class="sxs-lookup"><span data-stu-id="1b4ac-348">Object Type: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case</span></span>  
  
 <span data-ttu-id="1b4ac-349">对象实例标识符： 858</span><span class="sxs-lookup"><span data-stu-id="1b4ac-349">Object Instance Identifier: 858</span></span>  
  
 <span data-ttu-id="1b4ac-350">事实活动 2004 年 3 月 17 日上午 9:23:05</span><span class="sxs-lookup"><span data-stu-id="1b4ac-350">FACT ACTIVITY 3/17/2004 9:23:05 AM</span></span>  
  
 <span data-ttu-id="1b4ac-351">规则引擎实例标识符： 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span><span class="sxs-lookup"><span data-stu-id="1b4ac-351">Rule Engine Instance Identifier: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span></span>  
  
 <span data-ttu-id="1b4ac-352">规则集名称: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="1b4ac-352">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="1b4ac-353">操作: 添加</span><span class="sxs-lookup"><span data-stu-id="1b4ac-353">Operation: Assert</span></span>  
  
 <span data-ttu-id="1b4ac-354">对象类型： TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType</span><span class="sxs-lookup"><span data-stu-id="1b4ac-354">Object Type: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType</span></span>  
  
 <span data-ttu-id="1b4ac-355">对象实例标识符： 853</span><span class="sxs-lookup"><span data-stu-id="1b4ac-355">Object Instance Identifier: 853</span></span>  
  
 <span data-ttu-id="1b4ac-356">条件评估测试 （匹配） 2004 年 3 月 17 日上午 9:23:05</span><span class="sxs-lookup"><span data-stu-id="1b4ac-356">CONDITION EVALUATION TEST (MATCH) 3/17/2004 9:23:05 AM</span></span>  
  
 <span data-ttu-id="1b4ac-357">规则引擎实例标识符： 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span><span class="sxs-lookup"><span data-stu-id="1b4ac-357">Rule Engine Instance Identifier: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span></span>  
  
 <span data-ttu-id="1b4ac-358">规则集名称: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="1b4ac-358">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="1b4ac-359">测试表达式： TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType.TimeInMonths > = 4</span><span class="sxs-lookup"><span data-stu-id="1b4ac-359">Test Expression: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType.TimeInMonths >= 4</span></span>  
  
 <span data-ttu-id="1b4ac-360">左操作数的值： 6</span><span class="sxs-lookup"><span data-stu-id="1b4ac-360">Left Operand Value: 6</span></span>  
  
 <span data-ttu-id="1b4ac-361">右操作数的值： 4</span><span class="sxs-lookup"><span data-stu-id="1b4ac-361">Right Operand Value: 4</span></span>  
  
 <span data-ttu-id="1b4ac-362">测试结果： True</span><span class="sxs-lookup"><span data-stu-id="1b4ac-362">Test Result: True</span></span>  
  
 <span data-ttu-id="1b4ac-363">安排更新 2004 年 3 月 17 日上午 9:23:05</span><span class="sxs-lookup"><span data-stu-id="1b4ac-363">AGENDA UPDATE 3/17/2004 9:23:05 AM</span></span>  
  
 <span data-ttu-id="1b4ac-364">规则引擎实例标识符： 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span><span class="sxs-lookup"><span data-stu-id="1b4ac-364">Rule Engine Instance Identifier: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span></span>  
  
 <span data-ttu-id="1b4ac-365">规则集名称: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="1b4ac-365">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="1b4ac-366">操作： 添加</span><span class="sxs-lookup"><span data-stu-id="1b4ac-366">Operation: Add</span></span>  
  
 <span data-ttu-id="1b4ac-367">规则名称： TestRule1</span><span class="sxs-lookup"><span data-stu-id="1b4ac-367">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="1b4ac-368">冲突解决标准： 0</span><span class="sxs-lookup"><span data-stu-id="1b4ac-368">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="1b4ac-369">规则触发 2004 年 3 月 17 日上午 9:23:05</span><span class="sxs-lookup"><span data-stu-id="1b4ac-369">RULE FIRED 3/17/2004 9:23:05 AM</span></span>  
  
 <span data-ttu-id="1b4ac-370">规则引擎实例标识符： 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span><span class="sxs-lookup"><span data-stu-id="1b4ac-370">Rule Engine Instance Identifier: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span></span>  
  
 <span data-ttu-id="1b4ac-371">规则集名称: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="1b4ac-371">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="1b4ac-372">规则名称： TestRule1</span><span class="sxs-lookup"><span data-stu-id="1b4ac-372">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="1b4ac-373">冲突解决标准： 0</span><span class="sxs-lookup"><span data-stu-id="1b4ac-373">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="1b4ac-374">事实活动 2004 年 3 月 17 日上午 9:23:05</span><span class="sxs-lookup"><span data-stu-id="1b4ac-374">FACT ACTIVITY 3/17/2004 9:23:05 AM</span></span>  
  
 <span data-ttu-id="1b4ac-375">规则引擎实例标识符： 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span><span class="sxs-lookup"><span data-stu-id="1b4ac-375">Rule Engine Instance Identifier: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span></span>  
  
 <span data-ttu-id="1b4ac-376">规则集名称: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="1b4ac-376">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="1b4ac-377">操作： 收回</span><span class="sxs-lookup"><span data-stu-id="1b4ac-377">Operation: Retract</span></span>  
  
 <span data-ttu-id="1b4ac-378">对象类型： TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case</span><span class="sxs-lookup"><span data-stu-id="1b4ac-378">Object Type: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case</span></span>  
  
 <span data-ttu-id="1b4ac-379">对象实例标识符： 858</span><span class="sxs-lookup"><span data-stu-id="1b4ac-379">Object Instance Identifier: 858</span></span>  
  
 <span data-ttu-id="1b4ac-380">事实活动 2004 年 3 月 17 日上午 9:23:05</span><span class="sxs-lookup"><span data-stu-id="1b4ac-380">FACT ACTIVITY 3/17/2004 9:23:05 AM</span></span>  
  
 <span data-ttu-id="1b4ac-381">规则引擎实例标识符： 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span><span class="sxs-lookup"><span data-stu-id="1b4ac-381">Rule Engine Instance Identifier: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span></span>  
  
 <span data-ttu-id="1b4ac-382">规则集名称: LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="1b4ac-382">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="1b4ac-383">操作： 收回</span><span class="sxs-lookup"><span data-stu-id="1b4ac-383">Operation: Retract</span></span>  
  
 <span data-ttu-id="1b4ac-384">对象类型： TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType</span><span class="sxs-lookup"><span data-stu-id="1b4ac-384">Object Type: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType</span></span>  
  
 <span data-ttu-id="1b4ac-385">对象实例标识符： 853</span><span class="sxs-lookup"><span data-stu-id="1b4ac-385">Object Instance Identifier: 853</span></span>  
  
 <span data-ttu-id="1b4ac-386">此示例演示**TypedXmlDocument**文档类型为"Microsoft.Samples.BizTalk.LoansProcessor.Case"引擎所断言。</span><span class="sxs-lookup"><span data-stu-id="1b4ac-386">This example shows that a **TypedXmlDocument** was asserted into the engine with a document type of "Microsoft.Samples.BizTalk.LoansProcessor.Case".</span></span>  <span data-ttu-id="1b4ac-387">接下来，根据该规则中定义的 XPath 选择器，引擎基于文档类型和选择器字符串创建和添加了类型为“Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType”的子级 TypedXmlDocument。</span><span class="sxs-lookup"><span data-stu-id="1b4ac-387">Based on the XPath selector defined in the rule, the engine then created and asserted a child TypedXmlDocument with type  "Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType" based on the document type and selector string.</span></span>  
  
 <span data-ttu-id="1b4ac-388">此子级 TypedXmlDocument 在条件中的计算结果为 True，从而导致议程更新和规则触发。</span><span class="sxs-lookup"><span data-stu-id="1b4ac-388">This child TypedXmlDocument evaluated to True in the condition, causing an agenda update and rule firing.</span></span>  <span data-ttu-id="1b4ac-389">父级和子级**TypedXmlDocument**的然后收回。</span><span class="sxs-lookup"><span data-stu-id="1b4ac-389">The parent and child **TypedXmlDocument**'s were then retracted.</span></span>  
  
## <a name="update-function"></a><span data-ttu-id="1b4ac-390">Update 函数</span><span class="sxs-lookup"><span data-stu-id="1b4ac-390">Update Function</span></span>  
 <span data-ttu-id="1b4ac-391">示例策略“Order”</span><span class="sxs-lookup"><span data-stu-id="1b4ac-391">Example policy "Order"</span></span>  
  
 <span data-ttu-id="1b4ac-392">**"InventoryCheck"规则**</span><span class="sxs-lookup"><span data-stu-id="1b4ac-392">**"InventoryCheck" Rule**</span></span>  
  
```  
IF Inventory.AllocateInventory == True  
THEN Order.inventoryAvailable == True  
   Update(Order)  
```  
  
 <span data-ttu-id="1b4ac-393">**"发货"规则**</span><span class="sxs-lookup"><span data-stu-id="1b4ac-393">**"Ship" Rule**</span></span>  
  
```  
IF Order.inventoryAvailable == True  
THEN Shipment.ShipOrder  
```  
  
 <span data-ttu-id="1b4ac-394">**输出：**</span><span class="sxs-lookup"><span data-stu-id="1b4ac-394">**Output:**</span></span>  
  
 <span data-ttu-id="1b4ac-395">对于 RULESET 的规则引擎跟踪： 排序 2004 年 3 月 17 日上午 10:31:17</span><span class="sxs-lookup"><span data-stu-id="1b4ac-395">RULE ENGINE TRACE for RULESET: Order 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="1b4ac-396">事实活动 3/17/2004 10:31:17 AM</span><span class="sxs-lookup"><span data-stu-id="1b4ac-396">FACT ACTIVITY 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="1b4ac-397">规则引擎实例标识符： 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="1b4ac-397">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="1b4ac-398">Ruleset 名称： 顺序</span><span class="sxs-lookup"><span data-stu-id="1b4ac-398">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="1b4ac-399">操作: 添加</span><span class="sxs-lookup"><span data-stu-id="1b4ac-399">Operation: Assert</span></span>  
  
 <span data-ttu-id="1b4ac-400">对象类型： TestClasses.Order</span><span class="sxs-lookup"><span data-stu-id="1b4ac-400">Object Type: TestClasses.Order</span></span>  
  
 <span data-ttu-id="1b4ac-401">对象实例标识符： 448</span><span class="sxs-lookup"><span data-stu-id="1b4ac-401">Object Instance Identifier: 448</span></span>  
  
 <span data-ttu-id="1b4ac-402">条件评估测试(匹配) 3/17/2004 10:31:17 AM</span><span class="sxs-lookup"><span data-stu-id="1b4ac-402">CONDITION EVALUATION TEST (MATCH) 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="1b4ac-403">规则引擎实例标识符： 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="1b4ac-403">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="1b4ac-404">Ruleset 名称： 顺序</span><span class="sxs-lookup"><span data-stu-id="1b4ac-404">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="1b4ac-405">测试表达式： TestClasses.Order.inventoryAvailable = = True</span><span class="sxs-lookup"><span data-stu-id="1b4ac-405">Test Expression: TestClasses.Order.inventoryAvailable == True</span></span>  
  
 <span data-ttu-id="1b4ac-406">左操作数的值： null</span><span class="sxs-lookup"><span data-stu-id="1b4ac-406">Left Operand Value: null</span></span>  
  
 <span data-ttu-id="1b4ac-407">右操作数的值： True</span><span class="sxs-lookup"><span data-stu-id="1b4ac-407">Right Operand Value: True</span></span>  
  
 <span data-ttu-id="1b4ac-408">测试结果： False</span><span class="sxs-lookup"><span data-stu-id="1b4ac-408">Test Result: False</span></span>  
  
 <span data-ttu-id="1b4ac-409">事实活动 3/17/2004 10:31:17 AM</span><span class="sxs-lookup"><span data-stu-id="1b4ac-409">FACT ACTIVITY 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="1b4ac-410">规则引擎实例标识符： 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="1b4ac-410">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="1b4ac-411">Ruleset 名称： 顺序</span><span class="sxs-lookup"><span data-stu-id="1b4ac-411">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="1b4ac-412">操作: 添加</span><span class="sxs-lookup"><span data-stu-id="1b4ac-412">Operation: Assert</span></span>  
  
 <span data-ttu-id="1b4ac-413">对象类型： TestClasses.Shipment</span><span class="sxs-lookup"><span data-stu-id="1b4ac-413">Object Type: TestClasses.Shipment</span></span>  
  
 <span data-ttu-id="1b4ac-414">对象实例标识符： 447</span><span class="sxs-lookup"><span data-stu-id="1b4ac-414">Object Instance Identifier: 447</span></span>  
  
 <span data-ttu-id="1b4ac-415">事实活动 3/17/2004 10:31:17 AM</span><span class="sxs-lookup"><span data-stu-id="1b4ac-415">FACT ACTIVITY 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="1b4ac-416">规则引擎实例标识符： 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="1b4ac-416">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="1b4ac-417">Ruleset 名称： 顺序</span><span class="sxs-lookup"><span data-stu-id="1b4ac-417">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="1b4ac-418">操作: 添加</span><span class="sxs-lookup"><span data-stu-id="1b4ac-418">Operation: Assert</span></span>  
  
 <span data-ttu-id="1b4ac-419">对象类型： TestClasses.Inventory</span><span class="sxs-lookup"><span data-stu-id="1b4ac-419">Object Type: TestClasses.Inventory</span></span>  
  
 <span data-ttu-id="1b4ac-420">对象实例标识符： 446</span><span class="sxs-lookup"><span data-stu-id="1b4ac-420">Object Instance Identifier: 446</span></span>  
  
 <span data-ttu-id="1b4ac-421">条件评估测试(匹配) 3/17/2004 10:31:17 AM</span><span class="sxs-lookup"><span data-stu-id="1b4ac-421">CONDITION EVALUATION TEST (MATCH) 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="1b4ac-422">规则引擎实例标识符： 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="1b4ac-422">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="1b4ac-423">Ruleset 名称： 顺序</span><span class="sxs-lookup"><span data-stu-id="1b4ac-423">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="1b4ac-424">测试表达式： TestClasses.Inventory.AllocateInventory = = True</span><span class="sxs-lookup"><span data-stu-id="1b4ac-424">Test Expression: TestClasses.Inventory.AllocateInventory == True</span></span>  
  
 <span data-ttu-id="1b4ac-425">左操作数的值： True</span><span class="sxs-lookup"><span data-stu-id="1b4ac-425">Left Operand Value: True</span></span>  
  
 <span data-ttu-id="1b4ac-426">右操作数的值： True</span><span class="sxs-lookup"><span data-stu-id="1b4ac-426">Right Operand Value: True</span></span>  
  
 <span data-ttu-id="1b4ac-427">测试结果： True</span><span class="sxs-lookup"><span data-stu-id="1b4ac-427">Test Result: True</span></span>  
  
 <span data-ttu-id="1b4ac-428">日程更新 3/17/2004 10:31:17 AM</span><span class="sxs-lookup"><span data-stu-id="1b4ac-428">AGENDA UPDATE 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="1b4ac-429">规则引擎实例标识符： 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="1b4ac-429">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="1b4ac-430">Ruleset 名称： 顺序</span><span class="sxs-lookup"><span data-stu-id="1b4ac-430">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="1b4ac-431">操作： 添加</span><span class="sxs-lookup"><span data-stu-id="1b4ac-431">Operation: Add</span></span>  
  
 <span data-ttu-id="1b4ac-432">规则名称： InventoryCheck</span><span class="sxs-lookup"><span data-stu-id="1b4ac-432">Rule Name: InventoryCheck</span></span>  
  
 <span data-ttu-id="1b4ac-433">冲突解决标准： 0</span><span class="sxs-lookup"><span data-stu-id="1b4ac-433">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="1b4ac-434">触发的规则 3/17/2004 10:31:17 AM</span><span class="sxs-lookup"><span data-stu-id="1b4ac-434">RULE FIRED 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="1b4ac-435">规则引擎实例标识符： 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="1b4ac-435">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="1b4ac-436">Ruleset 名称： 顺序</span><span class="sxs-lookup"><span data-stu-id="1b4ac-436">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="1b4ac-437">规则名称： InventoryCheck</span><span class="sxs-lookup"><span data-stu-id="1b4ac-437">Rule Name: InventoryCheck</span></span>  
  
 <span data-ttu-id="1b4ac-438">冲突解决标准： 0</span><span class="sxs-lookup"><span data-stu-id="1b4ac-438">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="1b4ac-439">事实活动 3/17/2004 10:31:17 AM</span><span class="sxs-lookup"><span data-stu-id="1b4ac-439">FACT ACTIVITY 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="1b4ac-440">规则引擎实例标识符： 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="1b4ac-440">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="1b4ac-441">Ruleset 名称： 顺序</span><span class="sxs-lookup"><span data-stu-id="1b4ac-441">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="1b4ac-442">操作： 更新</span><span class="sxs-lookup"><span data-stu-id="1b4ac-442">Operation: Update</span></span>  
  
 <span data-ttu-id="1b4ac-443">对象类型： TestClasses.Order</span><span class="sxs-lookup"><span data-stu-id="1b4ac-443">Object Type: TestClasses.Order</span></span>  
  
 <span data-ttu-id="1b4ac-444">对象实例标识符： 448</span><span class="sxs-lookup"><span data-stu-id="1b4ac-444">Object Instance Identifier: 448</span></span>  
  
 <span data-ttu-id="1b4ac-445">条件评估测试(匹配) 3/17/2004 10:31:17 AM</span><span class="sxs-lookup"><span data-stu-id="1b4ac-445">CONDITION EVALUATION TEST (MATCH) 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="1b4ac-446">规则引擎实例标识符： 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="1b4ac-446">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="1b4ac-447">Ruleset 名称： 顺序</span><span class="sxs-lookup"><span data-stu-id="1b4ac-447">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="1b4ac-448">测试表达式： TestClasses.Order.inventoryAvailable = = True</span><span class="sxs-lookup"><span data-stu-id="1b4ac-448">Test Expression: TestClasses.Order.inventoryAvailable == True</span></span>  
  
 <span data-ttu-id="1b4ac-449">左操作数的值： True</span><span class="sxs-lookup"><span data-stu-id="1b4ac-449">Left Operand Value: True</span></span>  
  
 <span data-ttu-id="1b4ac-450">右操作数的值： True</span><span class="sxs-lookup"><span data-stu-id="1b4ac-450">Right Operand Value: True</span></span>  
  
 <span data-ttu-id="1b4ac-451">测试结果： True</span><span class="sxs-lookup"><span data-stu-id="1b4ac-451">Test Result: True</span></span>  
  
 <span data-ttu-id="1b4ac-452">日程更新 3/17/2004 10:31:17 AM</span><span class="sxs-lookup"><span data-stu-id="1b4ac-452">AGENDA UPDATE 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="1b4ac-453">规则引擎实例标识符： 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="1b4ac-453">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="1b4ac-454">Ruleset 名称： 顺序</span><span class="sxs-lookup"><span data-stu-id="1b4ac-454">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="1b4ac-455">操作： 添加</span><span class="sxs-lookup"><span data-stu-id="1b4ac-455">Operation: Add</span></span>  
  
 <span data-ttu-id="1b4ac-456">规则名称： 发货</span><span class="sxs-lookup"><span data-stu-id="1b4ac-456">Rule Name: Ship</span></span>  
  
 <span data-ttu-id="1b4ac-457">冲突解决标准： 0</span><span class="sxs-lookup"><span data-stu-id="1b4ac-457">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="1b4ac-458">触发的规则 3/17/2004 10:31:17 AM</span><span class="sxs-lookup"><span data-stu-id="1b4ac-458">RULE FIRED 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="1b4ac-459">规则引擎实例标识符： 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="1b4ac-459">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="1b4ac-460">Ruleset 名称： 顺序</span><span class="sxs-lookup"><span data-stu-id="1b4ac-460">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="1b4ac-461">规则名称： 发货</span><span class="sxs-lookup"><span data-stu-id="1b4ac-461">Rule Name: Ship</span></span>  
  
 <span data-ttu-id="1b4ac-462">冲突解决标准： 0</span><span class="sxs-lookup"><span data-stu-id="1b4ac-462">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="1b4ac-463">事实活动 3/17/2004 10:31:17 AM</span><span class="sxs-lookup"><span data-stu-id="1b4ac-463">FACT ACTIVITY 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="1b4ac-464">规则引擎实例标识符： 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="1b4ac-464">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="1b4ac-465">Ruleset 名称： 顺序</span><span class="sxs-lookup"><span data-stu-id="1b4ac-465">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="1b4ac-466">操作： 收回</span><span class="sxs-lookup"><span data-stu-id="1b4ac-466">Operation: Retract</span></span>  
  
 <span data-ttu-id="1b4ac-467">对象类型： TestClasses.Order</span><span class="sxs-lookup"><span data-stu-id="1b4ac-467">Object Type: TestClasses.Order</span></span>  
  
 <span data-ttu-id="1b4ac-468">对象实例标识符： 448</span><span class="sxs-lookup"><span data-stu-id="1b4ac-468">Object Instance Identifier: 448</span></span>  
  
 <span data-ttu-id="1b4ac-469">事实活动 3/17/2004 10:31:17 AM</span><span class="sxs-lookup"><span data-stu-id="1b4ac-469">FACT ACTIVITY 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="1b4ac-470">规则引擎实例标识符： 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="1b4ac-470">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="1b4ac-471">Ruleset 名称： 顺序</span><span class="sxs-lookup"><span data-stu-id="1b4ac-471">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="1b4ac-472">操作： 收回</span><span class="sxs-lookup"><span data-stu-id="1b4ac-472">Operation: Retract</span></span>  
  
 <span data-ttu-id="1b4ac-473">对象类型： TestClasses.Shipment</span><span class="sxs-lookup"><span data-stu-id="1b4ac-473">Object Type: TestClasses.Shipment</span></span>  
  
 <span data-ttu-id="1b4ac-474">对象实例标识符： 447</span><span class="sxs-lookup"><span data-stu-id="1b4ac-474">Object Instance Identifier: 447</span></span>  
  
 <span data-ttu-id="1b4ac-475">事实活动 3/17/2004 10:31:17 AM</span><span class="sxs-lookup"><span data-stu-id="1b4ac-475">FACT ACTIVITY 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="1b4ac-476">规则引擎实例标识符： 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="1b4ac-476">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="1b4ac-477">Ruleset 名称： 顺序</span><span class="sxs-lookup"><span data-stu-id="1b4ac-477">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="1b4ac-478">操作： 收回</span><span class="sxs-lookup"><span data-stu-id="1b4ac-478">Operation: Retract</span></span>  
  
 <span data-ttu-id="1b4ac-479">对象类型： TestClasses.Inventory</span><span class="sxs-lookup"><span data-stu-id="1b4ac-479">Object Type: TestClasses.Inventory</span></span>  
  
 <span data-ttu-id="1b4ac-480">对象实例标识符： 446</span><span class="sxs-lookup"><span data-stu-id="1b4ac-480">Object Instance Identifier: 446</span></span>  
  
 <span data-ttu-id="1b4ac-481">在本示例中，第一次检查与 Ship 规则相关联的条件时，该条件的计算结果为 False。</span><span class="sxs-lookup"><span data-stu-id="1b4ac-481">In this example, the condition associated with the Ship rule evaluates to False the first time it is checked.</span></span>  <span data-ttu-id="1b4ac-482">但是，在触发 InventoryCheck 规则时，将更改“Order”上的“inventoryAvailable”字段，并在引擎上为“Order”对象发出 Update 命令。</span><span class="sxs-lookup"><span data-stu-id="1b4ac-482">However, when the InventoryCheck rule fires, the inventoryAvailable field on the Order is changed and an Update command is issued on the engine for the Order object.</span></span>  <span data-ttu-id="1b4ac-483">这将导致对 Ship 规则进行重新计算。</span><span class="sxs-lookup"><span data-stu-id="1b4ac-483">This causes the Ship rule to be reevaluated.</span></span>  <span data-ttu-id="1b4ac-484">重新计算后，该条件的计算结果为 True，从而触发 Ship 规则。</span><span class="sxs-lookup"><span data-stu-id="1b4ac-484">This time the condition evaluates to true and the Ship rule fires.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b4ac-485">如果不正确地编写了规则，则具有 Update 函数的正向链接可能会导致无限循环。</span><span class="sxs-lookup"><span data-stu-id="1b4ac-485">If your rules are written incorrectly, forward chaining with the Update function may cause an infinite loop.</span></span>  <span data-ttu-id="1b4ac-486">如果出现这种情况，则在业务规则编辑器中测试策略时会收到错误消息，该消息文本为“规则引擎检测到执行循环”。</span><span class="sxs-lookup"><span data-stu-id="1b4ac-486">If this occurs, you will receive an error message when testing the policy in the Business Rule Composer with the text "The rule engine detected an execution loop."</span></span>