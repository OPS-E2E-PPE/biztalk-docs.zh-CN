---
title: 策略测试跟踪输出示例 |Microsoft Docs
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
ms.openlocfilehash: 365d962c7a21721e75eb3c0c5abd6e2d93bfd5aa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394951"
---
# <a name="policy-test-trace-output-examples"></a><span data-ttu-id="3d5a8-102">策略测试跟踪输出示例</span><span class="sxs-lookup"><span data-stu-id="3d5a8-102">Policy Test Trace Output Examples</span></span>
<span data-ttu-id="3d5a8-103">本部分包含不同类型的事实的策略测试输出的示例。</span><span class="sxs-lookup"><span data-stu-id="3d5a8-103">This section contains examples of the policy test output for different types of facts.</span></span>  
  
## <a name="net-class"></a><span data-ttu-id="3d5a8-104">.Net 类</span><span class="sxs-lookup"><span data-stu-id="3d5a8-104">.Net Class</span></span>  
 <span data-ttu-id="3d5a8-105">策略"LoanProcessing"中的示例规则"TestRule1":</span><span class="sxs-lookup"><span data-stu-id="3d5a8-105">Example rule "TestRule1" in policy "LoanProcessing":</span></span>  
  
```  
IF test.get_ID > 0  
THEN <do something>  
```  
  
 <span data-ttu-id="3d5a8-106">**输出：**</span><span class="sxs-lookup"><span data-stu-id="3d5a8-106">**Output:**</span></span>  
  
 <span data-ttu-id="3d5a8-107">规则集的规则引擎跟踪：LoanProcessing 2004 年 3 月 16 日上午 9:50:28</span><span class="sxs-lookup"><span data-stu-id="3d5a8-107">RULE ENGINE TRACE for RULESET: LoanProcessing 3/16/2004 9:50:28 AM</span></span>  
  
 <span data-ttu-id="3d5a8-108">事实活动 2004 年 3 月 16 日上午 9:50:28</span><span class="sxs-lookup"><span data-stu-id="3d5a8-108">FACT ACTIVITY 3/16/2004 9:50:28 AM</span></span>  
  
 <span data-ttu-id="3d5a8-109">规则引擎实例标识符：9effe3f9-d3ad-4125-99fa-56bb379188f7</span><span class="sxs-lookup"><span data-stu-id="3d5a8-109">Rule Engine Instance Identifier: 9effe3f9-d3ad-4125-99fa-56bb379188f7</span></span>  
  
 <span data-ttu-id="3d5a8-110">规则集名称：LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="3d5a8-110">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="3d5a8-111">操作：ActualRebinds</span><span class="sxs-lookup"><span data-stu-id="3d5a8-111">Operation: Assert</span></span>  
  
 <span data-ttu-id="3d5a8-112">对象类型：MyTest.test</span><span class="sxs-lookup"><span data-stu-id="3d5a8-112">Object Type: MyTest.test</span></span>  
  
 <span data-ttu-id="3d5a8-113">对象实例标识符：872</span><span class="sxs-lookup"><span data-stu-id="3d5a8-113">Object Instance Identifier: 872</span></span>  
  
 <span data-ttu-id="3d5a8-114">条件评估测试 （匹配） 2004 年 3 月 16 日上午 9:50:28</span><span class="sxs-lookup"><span data-stu-id="3d5a8-114">CONDITION EVALUATION TEST (MATCH) 3/16/2004 9:50:28 AM</span></span>  
  
 <span data-ttu-id="3d5a8-115">规则引擎实例标识符：9effe3f9-d3ad-4125-99fa-56bb379188f7</span><span class="sxs-lookup"><span data-stu-id="3d5a8-115">Rule Engine Instance Identifier: 9effe3f9-d3ad-4125-99fa-56bb379188f7</span></span>  
  
 <span data-ttu-id="3d5a8-116">规则集名称：LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="3d5a8-116">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="3d5a8-117">测试表达式：MyTest.test.get_ID > 0</span><span class="sxs-lookup"><span data-stu-id="3d5a8-117">Test Expression: MyTest.test.get_ID > 0</span></span>  
  
 <span data-ttu-id="3d5a8-118">左的操作数的值：100</span><span class="sxs-lookup"><span data-stu-id="3d5a8-118">Left Operand Value: 100</span></span>  
  
 <span data-ttu-id="3d5a8-119">右操作数的值：0</span><span class="sxs-lookup"><span data-stu-id="3d5a8-119">Right Operand Value: 0</span></span>  
  
 <span data-ttu-id="3d5a8-120">测试结果：True</span><span class="sxs-lookup"><span data-stu-id="3d5a8-120">Test Result: True</span></span>  
  
 <span data-ttu-id="3d5a8-121">议程更新 2004 年 3 月 16 日上午 9:50:28</span><span class="sxs-lookup"><span data-stu-id="3d5a8-121">AGENDA UPDATE 3/16/2004 9:50:28 AM</span></span>  
  
 <span data-ttu-id="3d5a8-122">规则引擎实例标识符：9effe3f9-d3ad-4125-99fa-56bb379188f7</span><span class="sxs-lookup"><span data-stu-id="3d5a8-122">Rule Engine Instance Identifier: 9effe3f9-d3ad-4125-99fa-56bb379188f7</span></span>  
  
 <span data-ttu-id="3d5a8-123">规则集名称：LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="3d5a8-123">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="3d5a8-124">操作：添加</span><span class="sxs-lookup"><span data-stu-id="3d5a8-124">Operation: Add</span></span>  
  
 <span data-ttu-id="3d5a8-125">规则名称：TestRule1</span><span class="sxs-lookup"><span data-stu-id="3d5a8-125">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="3d5a8-126">冲突解决标准：0</span><span class="sxs-lookup"><span data-stu-id="3d5a8-126">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="3d5a8-127">规则触发 2004 年 3 月 16 日上午 9:50:28</span><span class="sxs-lookup"><span data-stu-id="3d5a8-127">RULE FIRED 3/16/2004 9:50:28 AM</span></span>  
  
 <span data-ttu-id="3d5a8-128">规则引擎实例标识符：9effe3f9-d3ad-4125-99fa-56bb379188f7</span><span class="sxs-lookup"><span data-stu-id="3d5a8-128">Rule Engine Instance Identifier: 9effe3f9-d3ad-4125-99fa-56bb379188f7</span></span>  
  
 <span data-ttu-id="3d5a8-129">规则集名称：LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="3d5a8-129">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="3d5a8-130">规则名称：TestRule1</span><span class="sxs-lookup"><span data-stu-id="3d5a8-130">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="3d5a8-131">冲突解决标准：0</span><span class="sxs-lookup"><span data-stu-id="3d5a8-131">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="3d5a8-132">事实活动 2004 年 3 月 16 日上午 9:50:28</span><span class="sxs-lookup"><span data-stu-id="3d5a8-132">FACT ACTIVITY 3/16/2004 9:50:28 AM</span></span>  
  
 <span data-ttu-id="3d5a8-133">规则引擎实例标识符：9effe3f9-d3ad-4125-99fa-56bb379188f7</span><span class="sxs-lookup"><span data-stu-id="3d5a8-133">Rule Engine Instance Identifier: 9effe3f9-d3ad-4125-99fa-56bb379188f7</span></span>  
  
 <span data-ttu-id="3d5a8-134">规则集名称：LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="3d5a8-134">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="3d5a8-135">操作：收回</span><span class="sxs-lookup"><span data-stu-id="3d5a8-135">Operation: Retract</span></span>  
  
 <span data-ttu-id="3d5a8-136">对象类型：MyTest.test</span><span class="sxs-lookup"><span data-stu-id="3d5a8-136">Object Type: MyTest.test</span></span>  
  
 <span data-ttu-id="3d5a8-137">对象实例标识符：872</span><span class="sxs-lookup"><span data-stu-id="3d5a8-137">Object Instance Identifier: 872</span></span>  
  
## <a name="dataconnectiontypeddatarow"></a><span data-ttu-id="3d5a8-138">DataConnection/TypedDataRow</span><span class="sxs-lookup"><span data-stu-id="3d5a8-138">DataConnection/TypedDataRow</span></span>  
 <span data-ttu-id="3d5a8-139">策略"LoanProcessing"中的示例规则"TestRule1":</span><span class="sxs-lookup"><span data-stu-id="3d5a8-139">Example rule "TestRule1" in policy "LoanProcessing":</span></span>  
  
```  
IF NorthWind.CustInfo.CreditCardBalance > 0  
THEN <do something>  
```  
  
 <span data-ttu-id="3d5a8-140">**输出：**</span><span class="sxs-lookup"><span data-stu-id="3d5a8-140">**Output:**</span></span>  
  
 <span data-ttu-id="3d5a8-141">规则集的规则引擎跟踪：LoanProcessing 2004 年 3 月 16 日上午 8:30:16</span><span class="sxs-lookup"><span data-stu-id="3d5a8-141">RULE ENGINE TRACE for RULESET: LoanProcessing 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="3d5a8-142">事实活动 2004 年 3 月 16 日上午 8:30:16</span><span class="sxs-lookup"><span data-stu-id="3d5a8-142">FACT ACTIVITY 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="3d5a8-143">规则引擎实例标识符：1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="3d5a8-143">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="3d5a8-144">规则集名称：LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="3d5a8-144">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="3d5a8-145">操作：ActualRebinds</span><span class="sxs-lookup"><span data-stu-id="3d5a8-145">Operation: Assert</span></span>  
  
 <span data-ttu-id="3d5a8-146">对象类型：DataConnection:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="3d5a8-146">Object Type: DataConnection:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="3d5a8-147">对象实例标识符：874</span><span class="sxs-lookup"><span data-stu-id="3d5a8-147">Object Instance Identifier: 874</span></span>  
  
 <span data-ttu-id="3d5a8-148">条件评估测试 （匹配） 2004 年 3 月 16 日上午 8:30:16</span><span class="sxs-lookup"><span data-stu-id="3d5a8-148">CONDITION EVALUATION TEST (MATCH) 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="3d5a8-149">规则引擎实例标识符：1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="3d5a8-149">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="3d5a8-150">规则集名称：LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="3d5a8-150">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="3d5a8-151">测试表达式： 选择 \* 从 [CustInfo] 其中 [CreditCardBalance] > 0</span><span class="sxs-lookup"><span data-stu-id="3d5a8-151">Test Expression: select \* from [CustInfo] where [CreditCardBalance] > 0</span></span>  
  
 <span data-ttu-id="3d5a8-152">左的操作数的值：</span><span class="sxs-lookup"><span data-stu-id="3d5a8-152">Left Operand Value:</span></span>  
  
 <span data-ttu-id="3d5a8-153">右操作数的值：</span><span class="sxs-lookup"><span data-stu-id="3d5a8-153">Right Operand Value:</span></span>  
  
 <span data-ttu-id="3d5a8-154">测试结果：True</span><span class="sxs-lookup"><span data-stu-id="3d5a8-154">Test Result: True</span></span>  
  
 <span data-ttu-id="3d5a8-155">事实活动 2004 年 3 月 16 日上午 8:30:16</span><span class="sxs-lookup"><span data-stu-id="3d5a8-155">FACT ACTIVITY 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="3d5a8-156">规则引擎实例标识符：1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="3d5a8-156">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="3d5a8-157">规则集名称：LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="3d5a8-157">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="3d5a8-158">操作：ActualRebinds</span><span class="sxs-lookup"><span data-stu-id="3d5a8-158">Operation: Assert</span></span>  
  
 <span data-ttu-id="3d5a8-159">对象类型：TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="3d5a8-159">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="3d5a8-160">对象实例标识符：177556</span><span class="sxs-lookup"><span data-stu-id="3d5a8-160">Object Instance Identifier: 177556</span></span>  
  
 <span data-ttu-id="3d5a8-161">议程更新 2004 年 3 月 16 日上午 8:30:16</span><span class="sxs-lookup"><span data-stu-id="3d5a8-161">AGENDA UPDATE 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="3d5a8-162">规则引擎实例标识符：1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="3d5a8-162">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="3d5a8-163">规则集名称：LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="3d5a8-163">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="3d5a8-164">操作：添加</span><span class="sxs-lookup"><span data-stu-id="3d5a8-164">Operation: Add</span></span>  
  
 <span data-ttu-id="3d5a8-165">规则名称：TestRule1</span><span class="sxs-lookup"><span data-stu-id="3d5a8-165">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="3d5a8-166">冲突解决标准：0</span><span class="sxs-lookup"><span data-stu-id="3d5a8-166">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="3d5a8-167">事实活动 2004 年 3 月 16 日上午 8:30:16</span><span class="sxs-lookup"><span data-stu-id="3d5a8-167">FACT ACTIVITY 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="3d5a8-168">规则引擎实例标识符：1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="3d5a8-168">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="3d5a8-169">规则集名称：LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="3d5a8-169">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="3d5a8-170">操作：ActualRebinds</span><span class="sxs-lookup"><span data-stu-id="3d5a8-170">Operation: Assert</span></span>  
  
 <span data-ttu-id="3d5a8-171">对象类型：TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="3d5a8-171">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="3d5a8-172">对象实例标识符：177559</span><span class="sxs-lookup"><span data-stu-id="3d5a8-172">Object Instance Identifier: 177559</span></span>  
  
 <span data-ttu-id="3d5a8-173">议程更新 2004 年 3 月 16 日上午 8:30:16</span><span class="sxs-lookup"><span data-stu-id="3d5a8-173">AGENDA UPDATE 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="3d5a8-174">规则引擎实例标识符：1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="3d5a8-174">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="3d5a8-175">规则集名称：LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="3d5a8-175">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="3d5a8-176">操作：添加</span><span class="sxs-lookup"><span data-stu-id="3d5a8-176">Operation: Add</span></span>  
  
 <span data-ttu-id="3d5a8-177">规则名称：TestRule1</span><span class="sxs-lookup"><span data-stu-id="3d5a8-177">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="3d5a8-178">冲突解决标准：0</span><span class="sxs-lookup"><span data-stu-id="3d5a8-178">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="3d5a8-179">事实活动 2004 年 3 月 16 日上午 8:30:16</span><span class="sxs-lookup"><span data-stu-id="3d5a8-179">FACT ACTIVITY 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="3d5a8-180">规则引擎实例标识符：1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="3d5a8-180">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="3d5a8-181">规则集名称：LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="3d5a8-181">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="3d5a8-182">操作：ActualRebinds</span><span class="sxs-lookup"><span data-stu-id="3d5a8-182">Operation: Assert</span></span>  
  
 <span data-ttu-id="3d5a8-183">对象类型：TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="3d5a8-183">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="3d5a8-184">对象实例标识符：177558</span><span class="sxs-lookup"><span data-stu-id="3d5a8-184">Object Instance Identifier: 177558</span></span>  
  
 <span data-ttu-id="3d5a8-185">议程更新 2004 年 3 月 16 日上午 8:30:16</span><span class="sxs-lookup"><span data-stu-id="3d5a8-185">AGENDA UPDATE 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="3d5a8-186">规则引擎实例标识符：1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="3d5a8-186">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="3d5a8-187">规则集名称：LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="3d5a8-187">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="3d5a8-188">操作：添加</span><span class="sxs-lookup"><span data-stu-id="3d5a8-188">Operation: Add</span></span>  
  
 <span data-ttu-id="3d5a8-189">规则名称：TestRule1</span><span class="sxs-lookup"><span data-stu-id="3d5a8-189">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="3d5a8-190">冲突解决标准：0</span><span class="sxs-lookup"><span data-stu-id="3d5a8-190">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="3d5a8-191">规则触发 2004 年 3 月 16 日上午 8:30:16</span><span class="sxs-lookup"><span data-stu-id="3d5a8-191">RULE FIRED 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="3d5a8-192">规则引擎实例标识符：1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="3d5a8-192">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="3d5a8-193">规则集名称：LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="3d5a8-193">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="3d5a8-194">规则名称：TestRule1</span><span class="sxs-lookup"><span data-stu-id="3d5a8-194">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="3d5a8-195">冲突解决标准：0</span><span class="sxs-lookup"><span data-stu-id="3d5a8-195">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="3d5a8-196">规则触发 2004 年 3 月 16 日上午 8:30:16</span><span class="sxs-lookup"><span data-stu-id="3d5a8-196">RULE FIRED 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="3d5a8-197">规则引擎实例标识符：1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="3d5a8-197">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="3d5a8-198">规则集名称：LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="3d5a8-198">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="3d5a8-199">规则名称：TestRule1</span><span class="sxs-lookup"><span data-stu-id="3d5a8-199">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="3d5a8-200">冲突解决标准：0</span><span class="sxs-lookup"><span data-stu-id="3d5a8-200">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="3d5a8-201">规则触发 2004 年 3 月 16 日上午 8:30:16</span><span class="sxs-lookup"><span data-stu-id="3d5a8-201">RULE FIRED 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="3d5a8-202">规则引擎实例标识符：1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="3d5a8-202">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="3d5a8-203">规则集名称：LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="3d5a8-203">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="3d5a8-204">规则名称：TestRule1</span><span class="sxs-lookup"><span data-stu-id="3d5a8-204">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="3d5a8-205">冲突解决标准：0</span><span class="sxs-lookup"><span data-stu-id="3d5a8-205">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="3d5a8-206">事实活动 2004 年 3 月 16 日上午 8:30:16</span><span class="sxs-lookup"><span data-stu-id="3d5a8-206">FACT ACTIVITY 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="3d5a8-207">规则引擎实例标识符：1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="3d5a8-207">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="3d5a8-208">规则集名称：LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="3d5a8-208">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="3d5a8-209">操作：收回</span><span class="sxs-lookup"><span data-stu-id="3d5a8-209">Operation: Retract</span></span>  
  
 <span data-ttu-id="3d5a8-210">对象类型：DataConnection:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="3d5a8-210">Object Type: DataConnection:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="3d5a8-211">对象实例标识符：874</span><span class="sxs-lookup"><span data-stu-id="3d5a8-211">Object Instance Identifier: 874</span></span>  
  
 <span data-ttu-id="3d5a8-212">事实活动 2004 年 3 月 16 日上午 8:30:16</span><span class="sxs-lookup"><span data-stu-id="3d5a8-212">FACT ACTIVITY 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="3d5a8-213">规则引擎实例标识符：1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="3d5a8-213">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="3d5a8-214">规则集名称：LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="3d5a8-214">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="3d5a8-215">操作：收回</span><span class="sxs-lookup"><span data-stu-id="3d5a8-215">Operation: Retract</span></span>  
  
 <span data-ttu-id="3d5a8-216">对象类型：TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="3d5a8-216">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="3d5a8-217">对象实例标识符：177559</span><span class="sxs-lookup"><span data-stu-id="3d5a8-217">Object Instance Identifier: 177559</span></span>  
  
 <span data-ttu-id="3d5a8-218">事实活动 2004 年 3 月 16 日上午 8:30:16</span><span class="sxs-lookup"><span data-stu-id="3d5a8-218">FACT ACTIVITY 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="3d5a8-219">规则引擎实例标识符：1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="3d5a8-219">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="3d5a8-220">规则集名称：LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="3d5a8-220">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="3d5a8-221">操作：收回</span><span class="sxs-lookup"><span data-stu-id="3d5a8-221">Operation: Retract</span></span>  
  
 <span data-ttu-id="3d5a8-222">对象类型：TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="3d5a8-222">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="3d5a8-223">对象实例标识符：177558</span><span class="sxs-lookup"><span data-stu-id="3d5a8-223">Object Instance Identifier: 177558</span></span>  
  
 <span data-ttu-id="3d5a8-224">事实活动 2004 年 3 月 16 日上午 8:30:16</span><span class="sxs-lookup"><span data-stu-id="3d5a8-224">FACT ACTIVITY 3/16/2004 8:30:16 AM</span></span>  
  
 <span data-ttu-id="3d5a8-225">规则引擎实例标识符：1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span><span class="sxs-lookup"><span data-stu-id="3d5a8-225">Rule Engine Instance Identifier: 1aad35bb-0599-470b-b0fa-73b3fa1dfb83</span></span>  
  
 <span data-ttu-id="3d5a8-226">规则集名称：LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="3d5a8-226">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="3d5a8-227">操作：收回</span><span class="sxs-lookup"><span data-stu-id="3d5a8-227">Operation: Retract</span></span>  
  
 <span data-ttu-id="3d5a8-228">对象类型：TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="3d5a8-228">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="3d5a8-229">对象实例标识符：177556</span><span class="sxs-lookup"><span data-stu-id="3d5a8-229">Object Instance Identifier: 177556</span></span>  
  
 <span data-ttu-id="3d5a8-230">上面的示例指示 CustInfo 表中的三个行满足规则中的条件。</span><span class="sxs-lookup"><span data-stu-id="3d5a8-230">The example above indicates that three rows in the CustInfo table met the condition in the rule.</span></span>  <span data-ttu-id="3d5a8-231">这导致三个唯一的 Typeddatarow 被添加到引擎和议程更新和规则触发对每个实例。</span><span class="sxs-lookup"><span data-stu-id="3d5a8-231">This caused three unique TypedDataRows to be asserted into the engine and an agenda update and rule firing to occur for each instance.</span></span>  
  
## <a name="typedatatabletypeddatarow"></a><span data-ttu-id="3d5a8-232">TypeDataTable/TypedDataRow</span><span class="sxs-lookup"><span data-stu-id="3d5a8-232">TypeDataTable/TypedDataRow</span></span>  
 <span data-ttu-id="3d5a8-233">策略"LoanProcessing"中的示例规则"TestRule1":</span><span class="sxs-lookup"><span data-stu-id="3d5a8-233">Example rule "TestRule1" in policy "LoanProcessing":</span></span>  
  
```  
IF NorthWind.CustInfo.CreditCardBalance > 0  
THEN <do something>  
```  
  
 <span data-ttu-id="3d5a8-234">**输出：**</span><span class="sxs-lookup"><span data-stu-id="3d5a8-234">**Output:**</span></span>  
  
 <span data-ttu-id="3d5a8-235">规则集的规则引擎跟踪：LoanProcessing 2004 年 3 月 17 日上午 11:27:35</span><span class="sxs-lookup"><span data-stu-id="3d5a8-235">RULE ENGINE TRACE for RULESET: LoanProcessing 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="3d5a8-236">事实活动 2004 年 3 月 17 日上午 11:27:35</span><span class="sxs-lookup"><span data-stu-id="3d5a8-236">FACT ACTIVITY 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="3d5a8-237">规则引擎实例标识符：0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="3d5a8-237">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="3d5a8-238">规则集名称：LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="3d5a8-238">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="3d5a8-239">操作：ActualRebinds</span><span class="sxs-lookup"><span data-stu-id="3d5a8-239">Operation: Assert</span></span>  
  
 <span data-ttu-id="3d5a8-240">对象类型：TypedDataTable:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="3d5a8-240">Object Type: TypedDataTable:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="3d5a8-241">对象实例标识符：377</span><span class="sxs-lookup"><span data-stu-id="3d5a8-241">Object Instance Identifier: 377</span></span>  
  
 <span data-ttu-id="3d5a8-242">事实活动 2004 年 3 月 17 日上午 11:27:35</span><span class="sxs-lookup"><span data-stu-id="3d5a8-242">FACT ACTIVITY 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="3d5a8-243">规则引擎实例标识符：0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="3d5a8-243">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="3d5a8-244">规则集名称：LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="3d5a8-244">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="3d5a8-245">操作：ActualRebinds</span><span class="sxs-lookup"><span data-stu-id="3d5a8-245">Operation: Assert</span></span>  
  
 <span data-ttu-id="3d5a8-246">对象类型：TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="3d5a8-246">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="3d5a8-247">对象实例标识符：376</span><span class="sxs-lookup"><span data-stu-id="3d5a8-247">Object Instance Identifier: 376</span></span>  
  
 <span data-ttu-id="3d5a8-248">条件评估测试 （匹配） 2004 年 3 月 17 日上午 11:27:35</span><span class="sxs-lookup"><span data-stu-id="3d5a8-248">CONDITION EVALUATION TEST (MATCH) 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="3d5a8-249">规则引擎实例标识符：0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="3d5a8-249">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="3d5a8-250">规则集名称：LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="3d5a8-250">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="3d5a8-251">测试表达式：TypedDataRow:Northwind:CustInfo.CreditCardBalance > 0</span><span class="sxs-lookup"><span data-stu-id="3d5a8-251">Test Expression: TypedDataRow:Northwind:CustInfo.CreditCardBalance > 0</span></span>  
  
 <span data-ttu-id="3d5a8-252">左的操作数的值：500</span><span class="sxs-lookup"><span data-stu-id="3d5a8-252">Left Operand Value: 500</span></span>  
  
 <span data-ttu-id="3d5a8-253">右操作数的值：0</span><span class="sxs-lookup"><span data-stu-id="3d5a8-253">Right Operand Value: 0</span></span>  
  
 <span data-ttu-id="3d5a8-254">测试结果：True</span><span class="sxs-lookup"><span data-stu-id="3d5a8-254">Test Result: True</span></span>  
  
 <span data-ttu-id="3d5a8-255">议程更新 2004 年 3 月 17 日上午 11:27:35</span><span class="sxs-lookup"><span data-stu-id="3d5a8-255">AGENDA UPDATE 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="3d5a8-256">规则引擎实例标识符：0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="3d5a8-256">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="3d5a8-257">规则集名称：LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="3d5a8-257">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="3d5a8-258">操作：添加</span><span class="sxs-lookup"><span data-stu-id="3d5a8-258">Operation: Add</span></span>  
  
 <span data-ttu-id="3d5a8-259">规则名称：TestRule1</span><span class="sxs-lookup"><span data-stu-id="3d5a8-259">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="3d5a8-260">冲突解决标准：0</span><span class="sxs-lookup"><span data-stu-id="3d5a8-260">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="3d5a8-261">事实活动 2004 年 3 月 17 日上午 11:27:35</span><span class="sxs-lookup"><span data-stu-id="3d5a8-261">FACT ACTIVITY 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="3d5a8-262">规则引擎实例标识符：0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="3d5a8-262">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="3d5a8-263">规则集名称：LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="3d5a8-263">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="3d5a8-264">操作：ActualRebinds</span><span class="sxs-lookup"><span data-stu-id="3d5a8-264">Operation: Assert</span></span>  
  
 <span data-ttu-id="3d5a8-265">对象类型：TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="3d5a8-265">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="3d5a8-266">对象实例标识符：375</span><span class="sxs-lookup"><span data-stu-id="3d5a8-266">Object Instance Identifier: 375</span></span>  
  
 <span data-ttu-id="3d5a8-267">条件评估测试 （匹配） 2004 年 3 月 17 日上午 11:27:35</span><span class="sxs-lookup"><span data-stu-id="3d5a8-267">CONDITION EVALUATION TEST (MATCH) 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="3d5a8-268">规则引擎实例标识符：0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="3d5a8-268">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="3d5a8-269">规则集名称：LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="3d5a8-269">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="3d5a8-270">测试表达式：TypedDataRow:Northwind:CustInfo.CreditCardBalance > 0</span><span class="sxs-lookup"><span data-stu-id="3d5a8-270">Test Expression: TypedDataRow:Northwind:CustInfo.CreditCardBalance > 0</span></span>  
  
 <span data-ttu-id="3d5a8-271">左的操作数的值：1000</span><span class="sxs-lookup"><span data-stu-id="3d5a8-271">Left Operand Value: 1000</span></span>  
  
 <span data-ttu-id="3d5a8-272">右操作数的值：0</span><span class="sxs-lookup"><span data-stu-id="3d5a8-272">Right Operand Value: 0</span></span>  
  
 <span data-ttu-id="3d5a8-273">测试结果：True</span><span class="sxs-lookup"><span data-stu-id="3d5a8-273">Test Result: True</span></span>  
  
 <span data-ttu-id="3d5a8-274">议程更新 2004 年 3 月 17 日上午 11:27:35</span><span class="sxs-lookup"><span data-stu-id="3d5a8-274">AGENDA UPDATE 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="3d5a8-275">规则引擎实例标识符：0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="3d5a8-275">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="3d5a8-276">规则集名称：LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="3d5a8-276">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="3d5a8-277">操作：添加</span><span class="sxs-lookup"><span data-stu-id="3d5a8-277">Operation: Add</span></span>  
  
 <span data-ttu-id="3d5a8-278">规则名称：TestRule1</span><span class="sxs-lookup"><span data-stu-id="3d5a8-278">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="3d5a8-279">冲突解决标准：0</span><span class="sxs-lookup"><span data-stu-id="3d5a8-279">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="3d5a8-280">事实活动 2004 年 3 月 17 日上午 11:27:35</span><span class="sxs-lookup"><span data-stu-id="3d5a8-280">FACT ACTIVITY 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="3d5a8-281">规则引擎实例标识符：0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="3d5a8-281">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="3d5a8-282">规则集名称：LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="3d5a8-282">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="3d5a8-283">操作：ActualRebinds</span><span class="sxs-lookup"><span data-stu-id="3d5a8-283">Operation: Assert</span></span>  
  
 <span data-ttu-id="3d5a8-284">对象类型：TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="3d5a8-284">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="3d5a8-285">对象实例标识符：374</span><span class="sxs-lookup"><span data-stu-id="3d5a8-285">Object Instance Identifier: 374</span></span>  
  
 <span data-ttu-id="3d5a8-286">条件评估测试 （匹配） 2004 年 3 月 17 日上午 11:27:35</span><span class="sxs-lookup"><span data-stu-id="3d5a8-286">CONDITION EVALUATION TEST (MATCH) 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="3d5a8-287">规则引擎实例标识符：0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="3d5a8-287">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="3d5a8-288">规则集名称：LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="3d5a8-288">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="3d5a8-289">测试表达式：TypedDataRow:Northwind:CustInfo.CreditCardBalance > 0</span><span class="sxs-lookup"><span data-stu-id="3d5a8-289">Test Expression: TypedDataRow:Northwind:CustInfo.CreditCardBalance > 0</span></span>  
  
 <span data-ttu-id="3d5a8-290">左的操作数的值：35000</span><span class="sxs-lookup"><span data-stu-id="3d5a8-290">Left Operand Value: 35000</span></span>  
  
 <span data-ttu-id="3d5a8-291">右操作数的值：0</span><span class="sxs-lookup"><span data-stu-id="3d5a8-291">Right Operand Value: 0</span></span>  
  
 <span data-ttu-id="3d5a8-292">测试结果：True</span><span class="sxs-lookup"><span data-stu-id="3d5a8-292">Test Result: True</span></span>  
  
 <span data-ttu-id="3d5a8-293">议程更新 2004 年 3 月 17 日上午 11:27:35</span><span class="sxs-lookup"><span data-stu-id="3d5a8-293">AGENDA UPDATE 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="3d5a8-294">规则引擎实例标识符：0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="3d5a8-294">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="3d5a8-295">规则集名称：LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="3d5a8-295">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="3d5a8-296">操作：添加</span><span class="sxs-lookup"><span data-stu-id="3d5a8-296">Operation: Add</span></span>  
  
 <span data-ttu-id="3d5a8-297">规则名称：TestRule1</span><span class="sxs-lookup"><span data-stu-id="3d5a8-297">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="3d5a8-298">冲突解决标准：0</span><span class="sxs-lookup"><span data-stu-id="3d5a8-298">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="3d5a8-299">规则触发 2004 年 3 月 17 日上午 11:27:35</span><span class="sxs-lookup"><span data-stu-id="3d5a8-299">RULE FIRED 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="3d5a8-300">规则引擎实例标识符：0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="3d5a8-300">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="3d5a8-301">规则集名称：LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="3d5a8-301">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="3d5a8-302">规则名称：TestRule1</span><span class="sxs-lookup"><span data-stu-id="3d5a8-302">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="3d5a8-303">冲突解决标准：0</span><span class="sxs-lookup"><span data-stu-id="3d5a8-303">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="3d5a8-304">规则触发 2004 年 3 月 17 日上午 11:27:35</span><span class="sxs-lookup"><span data-stu-id="3d5a8-304">RULE FIRED 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="3d5a8-305">规则引擎实例标识符：0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="3d5a8-305">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="3d5a8-306">规则集名称：LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="3d5a8-306">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="3d5a8-307">规则名称：TestRule1</span><span class="sxs-lookup"><span data-stu-id="3d5a8-307">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="3d5a8-308">冲突解决标准：0</span><span class="sxs-lookup"><span data-stu-id="3d5a8-308">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="3d5a8-309">规则触发 2004 年 3 月 17 日上午 11:27:35</span><span class="sxs-lookup"><span data-stu-id="3d5a8-309">RULE FIRED 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="3d5a8-310">规则引擎实例标识符：0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="3d5a8-310">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="3d5a8-311">规则集名称：LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="3d5a8-311">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="3d5a8-312">规则名称：TestRule1</span><span class="sxs-lookup"><span data-stu-id="3d5a8-312">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="3d5a8-313">冲突解决标准：0</span><span class="sxs-lookup"><span data-stu-id="3d5a8-313">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="3d5a8-314">事实活动 2004 年 3 月 17 日上午 11:27:35</span><span class="sxs-lookup"><span data-stu-id="3d5a8-314">FACT ACTIVITY 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="3d5a8-315">规则引擎实例标识符：0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="3d5a8-315">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="3d5a8-316">规则集名称：LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="3d5a8-316">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="3d5a8-317">操作：收回</span><span class="sxs-lookup"><span data-stu-id="3d5a8-317">Operation: Retract</span></span>  
  
 <span data-ttu-id="3d5a8-318">对象类型：TypedDataTable:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="3d5a8-318">Object Type: TypedDataTable:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="3d5a8-319">对象实例标识符：377</span><span class="sxs-lookup"><span data-stu-id="3d5a8-319">Object Instance Identifier: 377</span></span>  
  
 <span data-ttu-id="3d5a8-320">事实活动 2004 年 3 月 17 日上午 11:27:35</span><span class="sxs-lookup"><span data-stu-id="3d5a8-320">FACT ACTIVITY 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="3d5a8-321">规则引擎实例标识符：0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="3d5a8-321">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="3d5a8-322">规则集名称：LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="3d5a8-322">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="3d5a8-323">操作：收回</span><span class="sxs-lookup"><span data-stu-id="3d5a8-323">Operation: Retract</span></span>  
  
 <span data-ttu-id="3d5a8-324">对象类型：TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="3d5a8-324">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="3d5a8-325">对象实例标识符：375</span><span class="sxs-lookup"><span data-stu-id="3d5a8-325">Object Instance Identifier: 375</span></span>  
  
 <span data-ttu-id="3d5a8-326">事实活动 2004 年 3 月 17 日上午 11:27:35</span><span class="sxs-lookup"><span data-stu-id="3d5a8-326">FACT ACTIVITY 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="3d5a8-327">规则引擎实例标识符：0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="3d5a8-327">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="3d5a8-328">规则集名称：LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="3d5a8-328">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="3d5a8-329">操作：收回</span><span class="sxs-lookup"><span data-stu-id="3d5a8-329">Operation: Retract</span></span>  
  
 <span data-ttu-id="3d5a8-330">对象类型：TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="3d5a8-330">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="3d5a8-331">对象实例标识符：374</span><span class="sxs-lookup"><span data-stu-id="3d5a8-331">Object Instance Identifier: 374</span></span>  
  
 <span data-ttu-id="3d5a8-332">事实活动 2004 年 3 月 17 日上午 11:27:35</span><span class="sxs-lookup"><span data-stu-id="3d5a8-332">FACT ACTIVITY 3/17/2004 11:27:35 AM</span></span>  
  
 <span data-ttu-id="3d5a8-333">规则引擎实例标识符：0f7bcdf3-8103-4990-a740-acaeee386439</span><span class="sxs-lookup"><span data-stu-id="3d5a8-333">Rule Engine Instance Identifier: 0f7bcdf3-8103-4990-a740-acaeee386439</span></span>  
  
 <span data-ttu-id="3d5a8-334">规则集名称：LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="3d5a8-334">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="3d5a8-335">操作：收回</span><span class="sxs-lookup"><span data-stu-id="3d5a8-335">Operation: Retract</span></span>  
  
 <span data-ttu-id="3d5a8-336">对象类型：TypedDataRow:Northwind:CustInfo</span><span class="sxs-lookup"><span data-stu-id="3d5a8-336">Object Type: TypedDataRow:Northwind:CustInfo</span></span>  
  
 <span data-ttu-id="3d5a8-337">对象实例标识符：376</span><span class="sxs-lookup"><span data-stu-id="3d5a8-337">Object Instance Identifier: 376</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3d5a8-338">上面的示例显示 TypedDataTable 包含三个行，并且每个均作为 typeddatarow 添加。</span><span class="sxs-lookup"><span data-stu-id="3d5a8-338">The example above shows that the TypedDataTable contained three rows, and each was asserted as a TypedDataRow.</span></span>  <span data-ttu-id="3d5a8-339">每个计算结果为 True 的条件中导致要添加到议程的规则和触发。</span><span class="sxs-lookup"><span data-stu-id="3d5a8-339">Each evaluated to True in the condition and caused the rule to be added to the agenda and fired.</span></span>  
  
## <a name="typedxmldocument"></a><span data-ttu-id="3d5a8-340">TypedXmlDocument</span><span class="sxs-lookup"><span data-stu-id="3d5a8-340">TypedXmlDocument</span></span>  
 <span data-ttu-id="3d5a8-341">策略"LoanProcessing"中的示例规则"TestRule1":</span><span class="sxs-lookup"><span data-stu-id="3d5a8-341">Example rule "TestRule1" in policy "LoanProcessing":</span></span>  
  
```  
IF Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType.TimeInMonths >= 4  
THEN <do something>  
```  
  
 <span data-ttu-id="3d5a8-342">**输出：**</span><span class="sxs-lookup"><span data-stu-id="3d5a8-342">**Output:**</span></span>  
  
 <span data-ttu-id="3d5a8-343">规则集的规则引擎跟踪：LoanProcessing 2004 年 3 月 17 日上午 9:23:05</span><span class="sxs-lookup"><span data-stu-id="3d5a8-343">RULE ENGINE TRACE for RULESET: LoanProcessing 3/17/2004 9:23:05 AM</span></span>  
  
 <span data-ttu-id="3d5a8-344">事实活动 2004 年 3 月 17 日上午 9:23:05</span><span class="sxs-lookup"><span data-stu-id="3d5a8-344">FACT ACTIVITY 3/17/2004 9:23:05 AM</span></span>  
  
 <span data-ttu-id="3d5a8-345">规则引擎实例标识符：51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span><span class="sxs-lookup"><span data-stu-id="3d5a8-345">Rule Engine Instance Identifier: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span></span>  
  
 <span data-ttu-id="3d5a8-346">规则集名称：LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="3d5a8-346">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="3d5a8-347">操作：ActualRebinds</span><span class="sxs-lookup"><span data-stu-id="3d5a8-347">Operation: Assert</span></span>  
  
 <span data-ttu-id="3d5a8-348">对象类型：TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case</span><span class="sxs-lookup"><span data-stu-id="3d5a8-348">Object Type: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case</span></span>  
  
 <span data-ttu-id="3d5a8-349">对象实例标识符：858</span><span class="sxs-lookup"><span data-stu-id="3d5a8-349">Object Instance Identifier: 858</span></span>  
  
 <span data-ttu-id="3d5a8-350">事实活动 2004 年 3 月 17 日上午 9:23:05</span><span class="sxs-lookup"><span data-stu-id="3d5a8-350">FACT ACTIVITY 3/17/2004 9:23:05 AM</span></span>  
  
 <span data-ttu-id="3d5a8-351">规则引擎实例标识符：51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span><span class="sxs-lookup"><span data-stu-id="3d5a8-351">Rule Engine Instance Identifier: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span></span>  
  
 <span data-ttu-id="3d5a8-352">规则集名称：LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="3d5a8-352">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="3d5a8-353">操作：ActualRebinds</span><span class="sxs-lookup"><span data-stu-id="3d5a8-353">Operation: Assert</span></span>  
  
 <span data-ttu-id="3d5a8-354">对象类型：TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType</span><span class="sxs-lookup"><span data-stu-id="3d5a8-354">Object Type: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType</span></span>  
  
 <span data-ttu-id="3d5a8-355">对象实例标识符：853</span><span class="sxs-lookup"><span data-stu-id="3d5a8-355">Object Instance Identifier: 853</span></span>  
  
 <span data-ttu-id="3d5a8-356">条件评估测试 （匹配） 2004 年 3 月 17 日上午 9:23:05</span><span class="sxs-lookup"><span data-stu-id="3d5a8-356">CONDITION EVALUATION TEST (MATCH) 3/17/2004 9:23:05 AM</span></span>  
  
 <span data-ttu-id="3d5a8-357">规则引擎实例标识符：51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span><span class="sxs-lookup"><span data-stu-id="3d5a8-357">Rule Engine Instance Identifier: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span></span>  
  
 <span data-ttu-id="3d5a8-358">规则集名称：LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="3d5a8-358">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="3d5a8-359">测试表达式：TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType.TimeInMonths >= 4</span><span class="sxs-lookup"><span data-stu-id="3d5a8-359">Test Expression: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType.TimeInMonths >= 4</span></span>  
  
 <span data-ttu-id="3d5a8-360">左的操作数的值：6</span><span class="sxs-lookup"><span data-stu-id="3d5a8-360">Left Operand Value: 6</span></span>  
  
 <span data-ttu-id="3d5a8-361">右操作数的值：4</span><span class="sxs-lookup"><span data-stu-id="3d5a8-361">Right Operand Value: 4</span></span>  
  
 <span data-ttu-id="3d5a8-362">测试结果：True</span><span class="sxs-lookup"><span data-stu-id="3d5a8-362">Test Result: True</span></span>  
  
 <span data-ttu-id="3d5a8-363">议程更新 2004 年 3 月 17 日上午 9:23:05</span><span class="sxs-lookup"><span data-stu-id="3d5a8-363">AGENDA UPDATE 3/17/2004 9:23:05 AM</span></span>  
  
 <span data-ttu-id="3d5a8-364">规则引擎实例标识符：51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span><span class="sxs-lookup"><span data-stu-id="3d5a8-364">Rule Engine Instance Identifier: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span></span>  
  
 <span data-ttu-id="3d5a8-365">规则集名称：LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="3d5a8-365">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="3d5a8-366">操作：添加</span><span class="sxs-lookup"><span data-stu-id="3d5a8-366">Operation: Add</span></span>  
  
 <span data-ttu-id="3d5a8-367">规则名称：TestRule1</span><span class="sxs-lookup"><span data-stu-id="3d5a8-367">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="3d5a8-368">冲突解决标准：0</span><span class="sxs-lookup"><span data-stu-id="3d5a8-368">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="3d5a8-369">规则触发 2004 年 3 月 17 日上午 9:23:05</span><span class="sxs-lookup"><span data-stu-id="3d5a8-369">RULE FIRED 3/17/2004 9:23:05 AM</span></span>  
  
 <span data-ttu-id="3d5a8-370">规则引擎实例标识符：51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span><span class="sxs-lookup"><span data-stu-id="3d5a8-370">Rule Engine Instance Identifier: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span></span>  
  
 <span data-ttu-id="3d5a8-371">规则集名称：LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="3d5a8-371">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="3d5a8-372">规则名称：TestRule1</span><span class="sxs-lookup"><span data-stu-id="3d5a8-372">Rule Name: TestRule1</span></span>  
  
 <span data-ttu-id="3d5a8-373">冲突解决标准：0</span><span class="sxs-lookup"><span data-stu-id="3d5a8-373">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="3d5a8-374">事实活动 2004 年 3 月 17 日上午 9:23:05</span><span class="sxs-lookup"><span data-stu-id="3d5a8-374">FACT ACTIVITY 3/17/2004 9:23:05 AM</span></span>  
  
 <span data-ttu-id="3d5a8-375">规则引擎实例标识符：51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span><span class="sxs-lookup"><span data-stu-id="3d5a8-375">Rule Engine Instance Identifier: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span></span>  
  
 <span data-ttu-id="3d5a8-376">规则集名称：LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="3d5a8-376">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="3d5a8-377">操作：收回</span><span class="sxs-lookup"><span data-stu-id="3d5a8-377">Operation: Retract</span></span>  
  
 <span data-ttu-id="3d5a8-378">对象类型：TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case</span><span class="sxs-lookup"><span data-stu-id="3d5a8-378">Object Type: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case</span></span>  
  
 <span data-ttu-id="3d5a8-379">对象实例标识符：858</span><span class="sxs-lookup"><span data-stu-id="3d5a8-379">Object Instance Identifier: 858</span></span>  
  
 <span data-ttu-id="3d5a8-380">事实活动 2004 年 3 月 17 日上午 9:23:05</span><span class="sxs-lookup"><span data-stu-id="3d5a8-380">FACT ACTIVITY 3/17/2004 9:23:05 AM</span></span>  
  
 <span data-ttu-id="3d5a8-381">规则引擎实例标识符：51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span><span class="sxs-lookup"><span data-stu-id="3d5a8-381">Rule Engine Instance Identifier: 51ffbea4-468f-4ce8-8ab7-977cadda2e2b</span></span>  
  
 <span data-ttu-id="3d5a8-382">规则集名称：LoanProcessing</span><span class="sxs-lookup"><span data-stu-id="3d5a8-382">Ruleset Name: LoanProcessing</span></span>  
  
 <span data-ttu-id="3d5a8-383">操作：收回</span><span class="sxs-lookup"><span data-stu-id="3d5a8-383">Operation: Retract</span></span>  
  
 <span data-ttu-id="3d5a8-384">对象类型：TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType</span><span class="sxs-lookup"><span data-stu-id="3d5a8-384">Object Type: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType</span></span>  
  
 <span data-ttu-id="3d5a8-385">对象实例标识符：853</span><span class="sxs-lookup"><span data-stu-id="3d5a8-385">Object Instance Identifier: 853</span></span>  
  
 <span data-ttu-id="3d5a8-386">此示例演示**TypedXmlDocument**已添加到文档类型为"Microsoft.Samples.BizTalk.LoansProcessor.Case"引擎。</span><span class="sxs-lookup"><span data-stu-id="3d5a8-386">This example shows that a **TypedXmlDocument** was asserted into the engine with a document type of "Microsoft.Samples.BizTalk.LoansProcessor.Case".</span></span>  <span data-ttu-id="3d5a8-387">引擎根据规则中定义的 XPath 选择器，然后创建和添加"Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType"基于文档类型和选择器字符串类型的子级 TypedXmlDocument。</span><span class="sxs-lookup"><span data-stu-id="3d5a8-387">Based on the XPath selector defined in the rule, the engine then created and asserted a child TypedXmlDocument with type  "Microsoft.Samples.BizTalk.LoansProcessor.Case:/Root/EmploymentType" based on the document type and selector string.</span></span>  
  
 <span data-ttu-id="3d5a8-388">此子级 TypedXmlDocument 计算结果为 True 在条件中，从而导致议程更新和规则触发。</span><span class="sxs-lookup"><span data-stu-id="3d5a8-388">This child TypedXmlDocument evaluated to True in the condition, causing an agenda update and rule firing.</span></span>  <span data-ttu-id="3d5a8-389">父级和子级**TypedXmlDocument**的然后，取消。</span><span class="sxs-lookup"><span data-stu-id="3d5a8-389">The parent and child **TypedXmlDocument**'s were then retracted.</span></span>  
  
## <a name="update-function"></a><span data-ttu-id="3d5a8-390">Update 函数</span><span class="sxs-lookup"><span data-stu-id="3d5a8-390">Update Function</span></span>  
 <span data-ttu-id="3d5a8-391">示例策略"Order"</span><span class="sxs-lookup"><span data-stu-id="3d5a8-391">Example policy "Order"</span></span>  
  
 <span data-ttu-id="3d5a8-392">**"InventoryCheck" Rule**</span><span class="sxs-lookup"><span data-stu-id="3d5a8-392">**"InventoryCheck" Rule**</span></span>  
  
```  
IF Inventory.AllocateInventory == True  
THEN Order.inventoryAvailable == True  
   Update(Order)  
```  
  
 <span data-ttu-id="3d5a8-393">**"Ship"规则**</span><span class="sxs-lookup"><span data-stu-id="3d5a8-393">**"Ship" Rule**</span></span>  
  
```  
IF Order.inventoryAvailable == True  
THEN Shipment.ShipOrder  
```  
  
 <span data-ttu-id="3d5a8-394">**输出：**</span><span class="sxs-lookup"><span data-stu-id="3d5a8-394">**Output:**</span></span>  
  
 <span data-ttu-id="3d5a8-395">规则集的规则引擎跟踪：订购 2004 年 3 月 17 日上午 10:31:17</span><span class="sxs-lookup"><span data-stu-id="3d5a8-395">RULE ENGINE TRACE for RULESET: Order 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="3d5a8-396">事实活动 2004 年 3 月 17 日上午 10:31:17</span><span class="sxs-lookup"><span data-stu-id="3d5a8-396">FACT ACTIVITY 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="3d5a8-397">规则引擎实例标识符：533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="3d5a8-397">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="3d5a8-398">规则集名称：订单</span><span class="sxs-lookup"><span data-stu-id="3d5a8-398">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="3d5a8-399">操作：ActualRebinds</span><span class="sxs-lookup"><span data-stu-id="3d5a8-399">Operation: Assert</span></span>  
  
 <span data-ttu-id="3d5a8-400">对象类型：TestClasses.Order</span><span class="sxs-lookup"><span data-stu-id="3d5a8-400">Object Type: TestClasses.Order</span></span>  
  
 <span data-ttu-id="3d5a8-401">对象实例标识符：448</span><span class="sxs-lookup"><span data-stu-id="3d5a8-401">Object Instance Identifier: 448</span></span>  
  
 <span data-ttu-id="3d5a8-402">条件评估测试 （匹配） 2004 年 3 月 17 日上午 10:31:17</span><span class="sxs-lookup"><span data-stu-id="3d5a8-402">CONDITION EVALUATION TEST (MATCH) 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="3d5a8-403">规则引擎实例标识符：533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="3d5a8-403">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="3d5a8-404">规则集名称：订单</span><span class="sxs-lookup"><span data-stu-id="3d5a8-404">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="3d5a8-405">测试表达式：TestClasses.Order.inventoryAvailable == True</span><span class="sxs-lookup"><span data-stu-id="3d5a8-405">Test Expression: TestClasses.Order.inventoryAvailable == True</span></span>  
  
 <span data-ttu-id="3d5a8-406">左操作数的值： null</span><span class="sxs-lookup"><span data-stu-id="3d5a8-406">Left Operand Value: null</span></span>  
  
 <span data-ttu-id="3d5a8-407">右操作数的值：True</span><span class="sxs-lookup"><span data-stu-id="3d5a8-407">Right Operand Value: True</span></span>  
  
 <span data-ttu-id="3d5a8-408">测试结果：False</span><span class="sxs-lookup"><span data-stu-id="3d5a8-408">Test Result: False</span></span>  
  
 <span data-ttu-id="3d5a8-409">事实活动 2004 年 3 月 17 日上午 10:31:17</span><span class="sxs-lookup"><span data-stu-id="3d5a8-409">FACT ACTIVITY 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="3d5a8-410">规则引擎实例标识符：533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="3d5a8-410">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="3d5a8-411">规则集名称：订单</span><span class="sxs-lookup"><span data-stu-id="3d5a8-411">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="3d5a8-412">操作：ActualRebinds</span><span class="sxs-lookup"><span data-stu-id="3d5a8-412">Operation: Assert</span></span>  
  
 <span data-ttu-id="3d5a8-413">对象类型：TestClasses.Shipment</span><span class="sxs-lookup"><span data-stu-id="3d5a8-413">Object Type: TestClasses.Shipment</span></span>  
  
 <span data-ttu-id="3d5a8-414">对象实例标识符：447</span><span class="sxs-lookup"><span data-stu-id="3d5a8-414">Object Instance Identifier: 447</span></span>  
  
 <span data-ttu-id="3d5a8-415">事实活动 2004 年 3 月 17 日上午 10:31:17</span><span class="sxs-lookup"><span data-stu-id="3d5a8-415">FACT ACTIVITY 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="3d5a8-416">规则引擎实例标识符：533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="3d5a8-416">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="3d5a8-417">规则集名称：订单</span><span class="sxs-lookup"><span data-stu-id="3d5a8-417">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="3d5a8-418">操作：ActualRebinds</span><span class="sxs-lookup"><span data-stu-id="3d5a8-418">Operation: Assert</span></span>  
  
 <span data-ttu-id="3d5a8-419">对象类型：TestClasses.Inventory</span><span class="sxs-lookup"><span data-stu-id="3d5a8-419">Object Type: TestClasses.Inventory</span></span>  
  
 <span data-ttu-id="3d5a8-420">对象实例标识符：446</span><span class="sxs-lookup"><span data-stu-id="3d5a8-420">Object Instance Identifier: 446</span></span>  
  
 <span data-ttu-id="3d5a8-421">条件评估测试 （匹配） 2004 年 3 月 17 日上午 10:31:17</span><span class="sxs-lookup"><span data-stu-id="3d5a8-421">CONDITION EVALUATION TEST (MATCH) 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="3d5a8-422">规则引擎实例标识符：533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="3d5a8-422">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="3d5a8-423">规则集名称：订单</span><span class="sxs-lookup"><span data-stu-id="3d5a8-423">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="3d5a8-424">测试表达式：TestClasses.Inventory.AllocateInventory == True</span><span class="sxs-lookup"><span data-stu-id="3d5a8-424">Test Expression: TestClasses.Inventory.AllocateInventory == True</span></span>  
  
 <span data-ttu-id="3d5a8-425">左的操作数的值：True</span><span class="sxs-lookup"><span data-stu-id="3d5a8-425">Left Operand Value: True</span></span>  
  
 <span data-ttu-id="3d5a8-426">右操作数的值：True</span><span class="sxs-lookup"><span data-stu-id="3d5a8-426">Right Operand Value: True</span></span>  
  
 <span data-ttu-id="3d5a8-427">测试结果：True</span><span class="sxs-lookup"><span data-stu-id="3d5a8-427">Test Result: True</span></span>  
  
 <span data-ttu-id="3d5a8-428">议程更新 2004 年 3 月 17 日上午 10:31:17</span><span class="sxs-lookup"><span data-stu-id="3d5a8-428">AGENDA UPDATE 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="3d5a8-429">规则引擎实例标识符：533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="3d5a8-429">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="3d5a8-430">规则集名称：订单</span><span class="sxs-lookup"><span data-stu-id="3d5a8-430">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="3d5a8-431">操作：添加</span><span class="sxs-lookup"><span data-stu-id="3d5a8-431">Operation: Add</span></span>  
  
 <span data-ttu-id="3d5a8-432">规则名称：InventoryCheck</span><span class="sxs-lookup"><span data-stu-id="3d5a8-432">Rule Name: InventoryCheck</span></span>  
  
 <span data-ttu-id="3d5a8-433">冲突解决标准：0</span><span class="sxs-lookup"><span data-stu-id="3d5a8-433">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="3d5a8-434">规则触发 2004 年 3 月 17 日上午 10:31:17</span><span class="sxs-lookup"><span data-stu-id="3d5a8-434">RULE FIRED 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="3d5a8-435">规则引擎实例标识符：533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="3d5a8-435">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="3d5a8-436">规则集名称：订单</span><span class="sxs-lookup"><span data-stu-id="3d5a8-436">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="3d5a8-437">规则名称：InventoryCheck</span><span class="sxs-lookup"><span data-stu-id="3d5a8-437">Rule Name: InventoryCheck</span></span>  
  
 <span data-ttu-id="3d5a8-438">冲突解决标准：0</span><span class="sxs-lookup"><span data-stu-id="3d5a8-438">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="3d5a8-439">事实活动 2004 年 3 月 17 日上午 10:31:17</span><span class="sxs-lookup"><span data-stu-id="3d5a8-439">FACT ACTIVITY 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="3d5a8-440">规则引擎实例标识符：533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="3d5a8-440">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="3d5a8-441">规则集名称：订单</span><span class="sxs-lookup"><span data-stu-id="3d5a8-441">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="3d5a8-442">操作：Update</span><span class="sxs-lookup"><span data-stu-id="3d5a8-442">Operation: Update</span></span>  
  
 <span data-ttu-id="3d5a8-443">对象类型：TestClasses.Order</span><span class="sxs-lookup"><span data-stu-id="3d5a8-443">Object Type: TestClasses.Order</span></span>  
  
 <span data-ttu-id="3d5a8-444">对象实例标识符：448</span><span class="sxs-lookup"><span data-stu-id="3d5a8-444">Object Instance Identifier: 448</span></span>  
  
 <span data-ttu-id="3d5a8-445">条件评估测试 （匹配） 2004 年 3 月 17 日上午 10:31:17</span><span class="sxs-lookup"><span data-stu-id="3d5a8-445">CONDITION EVALUATION TEST (MATCH) 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="3d5a8-446">规则引擎实例标识符：533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="3d5a8-446">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="3d5a8-447">规则集名称：订单</span><span class="sxs-lookup"><span data-stu-id="3d5a8-447">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="3d5a8-448">测试表达式：TestClasses.Order.inventoryAvailable == True</span><span class="sxs-lookup"><span data-stu-id="3d5a8-448">Test Expression: TestClasses.Order.inventoryAvailable == True</span></span>  
  
 <span data-ttu-id="3d5a8-449">左的操作数的值：True</span><span class="sxs-lookup"><span data-stu-id="3d5a8-449">Left Operand Value: True</span></span>  
  
 <span data-ttu-id="3d5a8-450">右操作数的值：True</span><span class="sxs-lookup"><span data-stu-id="3d5a8-450">Right Operand Value: True</span></span>  
  
 <span data-ttu-id="3d5a8-451">测试结果：True</span><span class="sxs-lookup"><span data-stu-id="3d5a8-451">Test Result: True</span></span>  
  
 <span data-ttu-id="3d5a8-452">议程更新 2004 年 3 月 17 日上午 10:31:17</span><span class="sxs-lookup"><span data-stu-id="3d5a8-452">AGENDA UPDATE 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="3d5a8-453">规则引擎实例标识符：533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="3d5a8-453">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="3d5a8-454">规则集名称：订单</span><span class="sxs-lookup"><span data-stu-id="3d5a8-454">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="3d5a8-455">操作：添加</span><span class="sxs-lookup"><span data-stu-id="3d5a8-455">Operation: Add</span></span>  
  
 <span data-ttu-id="3d5a8-456">规则名称：发货</span><span class="sxs-lookup"><span data-stu-id="3d5a8-456">Rule Name: Ship</span></span>  
  
 <span data-ttu-id="3d5a8-457">冲突解决标准：0</span><span class="sxs-lookup"><span data-stu-id="3d5a8-457">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="3d5a8-458">规则触发 2004 年 3 月 17 日上午 10:31:17</span><span class="sxs-lookup"><span data-stu-id="3d5a8-458">RULE FIRED 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="3d5a8-459">规则引擎实例标识符：533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="3d5a8-459">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="3d5a8-460">规则集名称：订单</span><span class="sxs-lookup"><span data-stu-id="3d5a8-460">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="3d5a8-461">规则名称：发货</span><span class="sxs-lookup"><span data-stu-id="3d5a8-461">Rule Name: Ship</span></span>  
  
 <span data-ttu-id="3d5a8-462">冲突解决标准：0</span><span class="sxs-lookup"><span data-stu-id="3d5a8-462">Conflict Resolution Criteria: 0</span></span>  
  
 <span data-ttu-id="3d5a8-463">事实活动 2004 年 3 月 17 日上午 10:31:17</span><span class="sxs-lookup"><span data-stu-id="3d5a8-463">FACT ACTIVITY 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="3d5a8-464">规则引擎实例标识符：533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="3d5a8-464">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="3d5a8-465">规则集名称：订单</span><span class="sxs-lookup"><span data-stu-id="3d5a8-465">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="3d5a8-466">操作：收回</span><span class="sxs-lookup"><span data-stu-id="3d5a8-466">Operation: Retract</span></span>  
  
 <span data-ttu-id="3d5a8-467">对象类型：TestClasses.Order</span><span class="sxs-lookup"><span data-stu-id="3d5a8-467">Object Type: TestClasses.Order</span></span>  
  
 <span data-ttu-id="3d5a8-468">对象实例标识符：448</span><span class="sxs-lookup"><span data-stu-id="3d5a8-468">Object Instance Identifier: 448</span></span>  
  
 <span data-ttu-id="3d5a8-469">事实活动 2004 年 3 月 17 日上午 10:31:17</span><span class="sxs-lookup"><span data-stu-id="3d5a8-469">FACT ACTIVITY 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="3d5a8-470">规则引擎实例标识符：533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="3d5a8-470">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="3d5a8-471">规则集名称：订单</span><span class="sxs-lookup"><span data-stu-id="3d5a8-471">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="3d5a8-472">操作：收回</span><span class="sxs-lookup"><span data-stu-id="3d5a8-472">Operation: Retract</span></span>  
  
 <span data-ttu-id="3d5a8-473">对象类型：TestClasses.Shipment</span><span class="sxs-lookup"><span data-stu-id="3d5a8-473">Object Type: TestClasses.Shipment</span></span>  
  
 <span data-ttu-id="3d5a8-474">对象实例标识符：447</span><span class="sxs-lookup"><span data-stu-id="3d5a8-474">Object Instance Identifier: 447</span></span>  
  
 <span data-ttu-id="3d5a8-475">事实活动 2004 年 3 月 17 日上午 10:31:17</span><span class="sxs-lookup"><span data-stu-id="3d5a8-475">FACT ACTIVITY 3/17/2004 10:31:17 AM</span></span>  
  
 <span data-ttu-id="3d5a8-476">规则引擎实例标识符：533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span><span class="sxs-lookup"><span data-stu-id="3d5a8-476">Rule Engine Instance Identifier: 533f2fb6-a91f-49c1-8f36-e03a27ca9d72</span></span>  
  
 <span data-ttu-id="3d5a8-477">规则集名称：订单</span><span class="sxs-lookup"><span data-stu-id="3d5a8-477">Ruleset Name: Order</span></span>  
  
 <span data-ttu-id="3d5a8-478">操作：收回</span><span class="sxs-lookup"><span data-stu-id="3d5a8-478">Operation: Retract</span></span>  
  
 <span data-ttu-id="3d5a8-479">对象类型：TestClasses.Inventory</span><span class="sxs-lookup"><span data-stu-id="3d5a8-479">Object Type: TestClasses.Inventory</span></span>  
  
 <span data-ttu-id="3d5a8-480">对象实例标识符：446</span><span class="sxs-lookup"><span data-stu-id="3d5a8-480">Object Instance Identifier: 446</span></span>  
  
 <span data-ttu-id="3d5a8-481">在此示例中，与 Ship 规则相关联的条件计算结果为 False 第一次对其进行检查。</span><span class="sxs-lookup"><span data-stu-id="3d5a8-481">In this example, the condition associated with the Ship rule evaluates to False the first time it is checked.</span></span>  <span data-ttu-id="3d5a8-482">但是，当在触发 InventoryCheck 规则触发时，更改顺序中的 inventoryavailable 字段，且在引擎上为 Order 对象发出 Update 命令。</span><span class="sxs-lookup"><span data-stu-id="3d5a8-482">However, when the InventoryCheck rule fires, the inventoryAvailable field on the Order is changed and an Update command is issued on the engine for the Order object.</span></span>  <span data-ttu-id="3d5a8-483">这将导致对 Ship 规则重新计算。</span><span class="sxs-lookup"><span data-stu-id="3d5a8-483">This causes the Ship rule to be reevaluated.</span></span>  <span data-ttu-id="3d5a8-484">此时间条件的计算结果为 true，并且 Ship 规则将触发。</span><span class="sxs-lookup"><span data-stu-id="3d5a8-484">This time the condition evaluates to true and the Ship rule fires.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3d5a8-485">如果你的规则编写不正确，则具有 Update 函数的正向链接可能会导致无限循环。</span><span class="sxs-lookup"><span data-stu-id="3d5a8-485">If your rules are written incorrectly, forward chaining with the Update function may cause an infinite loop.</span></span>  <span data-ttu-id="3d5a8-486">如果发生这种情况，你将收到一条错误消息中包含文本的业务规则编辑器测试策略时"规则引擎检测到执行循环。"</span><span class="sxs-lookup"><span data-stu-id="3d5a8-486">If this occurs, you will receive an error message when testing the policy in the Business Rule Composer with the text "The rule engine detected an execution loop."</span></span>