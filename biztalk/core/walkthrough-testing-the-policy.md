---
title: 演练： 测试策略 |Microsoft 文档
ms.custom: ''
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53ed915d-0f3a-48ea-bfd5-a1f89b9b689c
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a6f879111a28d5cbf9b2a75c7b3f3b3b865fb38
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
---
# <a name="walkthrough-testing-the-policy"></a><span data-ttu-id="2a6bd-102">演练： 测试策略</span><span class="sxs-lookup"><span data-stu-id="2a6bd-102">Walkthrough: Testing the Policy</span></span>
<span data-ttu-id="2a6bd-103">本演练中提供的测试中创建的策略的分步过程[演练： 创建简单的业务策略](../core/walkthrough-creating-a-simple-business-policy.md)演练。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-103">This walkthrough provides step-by-step procedures for testing the policy you created in the [Walkthrough: Creating a Simple Business Policy](../core/walkthrough-creating-a-simple-business-policy.md) walkthrough.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2a6bd-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="2a6bd-104">Prerequisites</span></span>  
 <span data-ttu-id="2a6bd-105">必须完成[演练： 创建简单的业务策略](../core/walkthrough-creating-a-simple-business-policy.md)演练在执行本演练之前。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-105">You must complete the [Walkthrough: Creating a Simple Business Policy](../core/walkthrough-creating-a-simple-business-policy.md) walkthrough before you perform this walkthrough.</span></span>  
  
## <a name="overview-of-this-walkthrough"></a><span data-ttu-id="2a6bd-106">本演练的概述</span><span class="sxs-lookup"><span data-stu-id="2a6bd-106">Overview of This Walkthrough</span></span>  
 <span data-ttu-id="2a6bd-107">本概览包含两个过程，如下表所述。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-107">This walkthrough contains two procedures, as described in the following table.</span></span>  
  
|<span data-ttu-id="2a6bd-108">过程标题</span><span class="sxs-lookup"><span data-stu-id="2a6bd-108">Procedure title</span></span>|<span data-ttu-id="2a6bd-109">过程说明</span><span class="sxs-lookup"><span data-stu-id="2a6bd-109">Procedure description</span></span>|  
|---------------------|---------------------------|  
|<span data-ttu-id="2a6bd-110">若要创建测试文件</span><span class="sxs-lookup"><span data-stu-id="2a6bd-110">To create the test files</span></span>|<span data-ttu-id="2a6bd-111">提供分步说明，创建两个示例 XML 文件，另一个使用为 400 数量字段的值 (\<= 500) 和另一个为 700 (> 500) 数量字段的值。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-111">Provides step-by-step instructions for creating two sample XML files, one with the value of the Quantity field as 400 (\<= 500) and the other one with the value of the Quantity field as 700 (> 500).</span></span>|  
|<span data-ttu-id="2a6bd-112">测试 ProcessPurchaseOrder 策略</span><span class="sxs-lookup"><span data-stu-id="2a6bd-112">To test the ProcessPurchaseOrder policy</span></span>|<span data-ttu-id="2a6bd-113">提供使用业务规则编辑器来测试该策略的逐步说明。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-113">Provides step-by-step instructions for testing the policy using Business Rule Composer.</span></span>|  
  
### <a name="to-create-the-test-files"></a><span data-ttu-id="2a6bd-114">若要创建测试文件</span><span class="sxs-lookup"><span data-stu-id="2a6bd-114">To create the test files</span></span>  
  
1.  <span data-ttu-id="2a6bd-115">上 **启动** 菜单上，打开 **记事本**。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-115">On the **Start** menu, open **Notepad**.</span></span>  
  
2.  <span data-ttu-id="2a6bd-116">将下列 XML 复制到记事本中：</span><span class="sxs-lookup"><span data-stu-id="2a6bd-116">Copy the following XML to Notepad:</span></span>  
  
    ```  
    <ns0:PurchaseOrder xmlns:ns0="http://EAISolution.PurchaseOrder">  
      <Header>  
        <ReqID>ReqID_0</ReqID>  
        <Date>Date_0</Date>  
      </Header>  
      <Item>  
        <Description>Description_0</Description>  
        <Quantity>400</Quantity>  
        <UnitPrice>20</UnitPrice>  
      </Item>  
      <Status>XYZ</Status>  
    </ns0:PurchaseOrder>    
    ```  
  
3.  <span data-ttu-id="2a6bd-117">上 **文件** 菜单上，单击 **TextFile1.txt 另存为**。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-117">On the **File** menu, click **Save TextFile1.txt As**.</span></span>  
  
4.  <span data-ttu-id="2a6bd-118">值更改 **另存为类型** 从 **文本文档 (\*.txt)** 到 **所有文件**。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-118">Change the value for **Save As type** from **Text Documents(\*.txt)** to **All Files**.</span></span>  
  
5.  <span data-ttu-id="2a6bd-119">将目录更改为 **C:\BRE-Walkthroughs**。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-119">Change the directory to **C:\BRE-Walkthroughs**.</span></span>  
  
6.  <span data-ttu-id="2a6bd-120">类型 **SamplePO.xml** 为 **文件名**, ，然后单击 **保存**。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-120">Type **SamplePO.xml** for **File name**, and then click **Save**.</span></span>  
  
7.  <span data-ttu-id="2a6bd-121">在“文件”  菜单上，单击“新建” 。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-121">On the **File** menu, click **New**.</span></span>  
  
8.  <span data-ttu-id="2a6bd-122">将下列 XML 复制到记事本中：</span><span class="sxs-lookup"><span data-stu-id="2a6bd-122">Copy the following XML to Notepad:</span></span>  
  
    ```  
    <ns0:PurchaseOrder xmlns:ns0="http://EAISolution.PurchaseOrder">  
      <Header>  
        <ReqID>ReqID_0</ReqID>  
        <Date>Date_0</Date>  
      </Header>  
      <Item>  
        <Description>Description_0</Description>  
        <Quantity>700</Quantity>  
        <UnitPrice>20</UnitPrice>  
      </Item>  
      <Status>XYZ</Status>  
    </ns0:PurchaseOrder>   
    ```  
  
9. <span data-ttu-id="2a6bd-123">上 **文件** 菜单上，单击 **TextFile1.txt 另存为**。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-123">On the **File** menu, click **Save TextFile1.txt As**.</span></span>  
  
10. <span data-ttu-id="2a6bd-124">值更改 **另存为类型** 从 **文本文档 (\*.txt)** 到 **所有文件**。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-124">Change the value for **Save As type** from **Text Documents(\*.txt)** to **All Files**.</span></span>  
  
11. <span data-ttu-id="2a6bd-125">将目录更改为 **C:\BRE-Walkthroughs**。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-125">Change the directory to **C:\BRE-Walkthroughs**.</span></span>  
  
12. <span data-ttu-id="2a6bd-126">类型 **SamplePO2.xml** 为 **文件名**, ，然后单击 **保存**。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-126">Type **SamplePO2.xml** for **File name**, and then click **Save**.</span></span>  
  
13. <span data-ttu-id="2a6bd-127">关闭记事本。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-127">Close Notepad.</span></span>  
  
### <a name="to-test-the-processpurchaseorder-policy"></a><span data-ttu-id="2a6bd-128">测试 ProcessPurchaseOrder 策略</span><span class="sxs-lookup"><span data-stu-id="2a6bd-128">To test the ProcessPurchaseOrder policy</span></span>  
  
1.  <span data-ttu-id="2a6bd-129">上 **启动** 菜单上，打开 **业务规则编辑器**。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-129">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="2a6bd-130">如果已開啟 [商務規則編輯器]，請按下 F5 重新整理。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-130">If you have Business Rule Composer already open, press F5 to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2a6bd-131">在支援使用者帳戶控制 (UAC) 的系統上，您可能需要使用系統管理權限來執行工具。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-131">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="2a6bd-132">要执行此操作，右键单击该应用程序，，然后选择 **以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-132">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="2a6bd-133">在策略资源管理器窗口中，展开 **策略**, ，展开 **ProcessPurchaseOrder**, ，右键单击 **版本 1.0**, ，然后单击 **测试策略**。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-133">In the Policy Explorer window, expand **Policies**, expand **ProcessPurchaseOrder**, right-click **Version 1.0**, and then click **Test Policy**.</span></span>  
  
3.  <span data-ttu-id="2a6bd-134">在 **XMLDocuments** 节点中，选择 **RuleTest.PO**, ，然后单击 **添加实例**。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-134">In the **XMLDocuments** node, select **RuleTest.PO**, and then click **Add Instance**.</span></span>  
  
     <span data-ttu-id="2a6bd-135">![业务规则编辑器&#45;TestPolicySelectFacts](../core/media/7115f0d4-0c12-4292-81a5-eb78d62c5543.gif "7115f0d4-0c12-4292-81a5-eb78d62c5543")</span><span class="sxs-lookup"><span data-stu-id="2a6bd-135">![Business Rule Composer&#45;TestPolicySelectFacts](../core/media/7115f0d4-0c12-4292-81a5-eb78d62c5543.gif "7115f0d4-0c12-4292-81a5-eb78d62c5543")</span></span>  
  
4.  <span data-ttu-id="2a6bd-136">选择 **SamplePO.xml** 文件之前创建，然后单击 **打开**。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-136">Select the **SamplePO.xml** file that you created earlier, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="2a6bd-137">单击 **测试**。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-137">Click **Test**.</span></span>  
  
6.  <span data-ttu-id="2a6bd-138">查看“输出”窗口中的输出。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-138">Review the output in the Output window.</span></span> <span data-ttu-id="2a6bd-139">查看“来自第一个测试的输出分析 (samplepo.xml)”部分，它解释了您所看到的输出。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-139">See the "Analysis of the Output from the First Test (samplepo.xml)" section for an explanation of the output you see.</span></span>  
  
7.  <span data-ttu-id="2a6bd-140">打开 **SamplePO.xml** 中记事本，并请注意，值 **状态** 字段设置为 **已批准**。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-140">Open **SamplePO.xml** in Notepad and notice that the value of the **Status** field is set to **Approved**.</span></span>  
  
8.  <span data-ttu-id="2a6bd-141">右键单击 **版本 1.0**, ，然后单击 **测试策略**。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-141">Right-click **Version 1.0**, and then click **Test Policy**.</span></span>  
  
9. <span data-ttu-id="2a6bd-142">选择 **SamplePO.xml**, ，单击 **删除实例**, ，然后单击 **添加实例**。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-142">Select **SamplePO.xml**, click **Remove instance**, and then click **Add Instance**.</span></span>  
  
10. <span data-ttu-id="2a6bd-143">选择 **SamplePO2.xml** 文件之前创建，然后单击 **打开**。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-143">Select the **SamplePO2.xml** file that you created earlier, and then click **Open**.</span></span>  
  
11. <span data-ttu-id="2a6bd-144">单击 **测试**。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-144">Click **Test**.</span></span> <span data-ttu-id="2a6bd-145">查看“来自第二个测试的输出分析 (samplepo2.xml)”部分，它解释了您所看到的输出。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-145">See the "Analysis of the Output from the Second Test (samplepo2.xml)" section for an explanation of the output you see.</span></span>  
  
12. <span data-ttu-id="2a6bd-146">打开 **SamplePO2.xml** 文件在记事本中，可以看到的值 **状态** 字段仍是 **XYZ**。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-146">Open the **SamplePO2.xml** file in Notepad and notice that the value of the **Status** field is still **XYZ**.</span></span>  
  
## <a name="analysis-of-the-output-from-the-first-test-samplepoxml"></a><span data-ttu-id="2a6bd-147">来自第一个测试的输出分析 (samplepo.xml)</span><span class="sxs-lookup"><span data-stu-id="2a6bd-147">Analysis of the Output from the First Test (samplepo.xml)</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2a6bd-148">输出文本为粗体并且在输出文本后跟有解释。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-148">The output text is bold and the explanation follows the output text.</span></span>  
  
 <span data-ttu-id="2a6bd-149">**对于 RULESET 的规则引擎跟踪︰ ProcessPurchaseOrder 2006 年 8 月 31 日下午 1:33:10**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-149">**RULE ENGINE TRACE for RULESET: ProcessPurchaseOrder 8/31/2006 1:33:10 PM**</span></span>  
  
 <span data-ttu-id="2a6bd-150">策略执行的规则引擎跟踪 **ProcessPurchaseOrder** 启动 2006 年 8 月 31 日下午 1:33:10。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-150">The rule engine trace for the execution of policy **ProcessPurchaseOrder** started at 8/31/2006 1:33:10 PM.</span></span>  
  
 <span data-ttu-id="2a6bd-151">**事实活动 2006 年 8 月 31 日下午 1:33:10**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-151">**FACT ACTIVITY 8/31/2006 1:33:10 PM**</span></span>  
  
 <span data-ttu-id="2a6bd-152">**规则引擎实例标识符︰ bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-152">**Rule Engine Instance Identifier: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span></span>  
  
 <span data-ttu-id="2a6bd-153">**Ruleset 名称︰ ProcessPurchaseOrder**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-153">**Ruleset Name: ProcessPurchaseOrder**</span></span>  
  
 <span data-ttu-id="2a6bd-154">**操作︰ 断言**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-154">**Operation: Assert**</span></span>  
  
 <span data-ttu-id="2a6bd-155">**对象类型︰ TypedXmlDocument:PurchaseOrder**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-155">**Object Type: TypedXmlDocument:PurchaseOrder**</span></span>  
  
 <span data-ttu-id="2a6bd-156">**对象实例标识符︰ 14626574**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-156">**Object Instance Identifier: 14626574**</span></span>  
  
 <span data-ttu-id="2a6bd-157">当你单击 **测试**, ，都会发生以下情况︰</span><span class="sxs-lookup"><span data-stu-id="2a6bd-157">When you click **Test**, the following things happen:</span></span>  
  
1.  <span data-ttu-id="2a6bd-158">业务规则编辑器创建 **RuleEngine.Policy** 对象，它能反过来创建新的规则引擎实例或获取从规则引擎缓存的规则引擎实例。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-158">The Business Rule Composer creates a **RuleEngine.Policy** object, which in turn creates a new rule engine instance or acquires a rule engine instance from the rule engine cache.</span></span>  
  
2.  <span data-ttu-id="2a6bd-159">业务规则编辑器创建 **TypedXmlDocument** 对象基于 SamplePO.xml 文件。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-159">The Business Rule Composer creates a **TypedXmlDocument** object based on the SamplePO.xml file.</span></span>  
  
3.  <span data-ttu-id="2a6bd-160">业务规则编辑器时，将调用 **Policy.Execute** 方法替换 **TypedXmlDocument** 对象作为参数。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-160">The Business Rule Composer invokes the **Policy.Execute** method with the **TypedXmlDocument** object as a parameter.</span></span>  
  
4.  <span data-ttu-id="2a6bd-161">**Policy.Execute** 方法断言 （添加） **TypedXmlDocument** 与的事实数据到规则引擎的工作内存的对象。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-161">The **Policy.Execute** method asserts (adds) the **TypedXmlDocument** object as a fact into the working memory of the rule engine.</span></span>  
  
5.  <span data-ttu-id="2a6bd-162">规则引擎会使用 **TypedXmlDocument** 对象与的事实数据并执行 **ProcessPurchaseOrder** 策略。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-162">The rule engine uses the **TypedXmlDocument** object as a fact and executes the **ProcessPurchaseOrder** policy.</span></span>  
  
 <span data-ttu-id="2a6bd-163">**事实活动 2006 年 8 月 31 日下午 1:33:10**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-163">**FACT ACTIVITY 8/31/2006 1:33:10 PM**</span></span>  
  
 <span data-ttu-id="2a6bd-164">**规则引擎实例标识符︰ bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-164">**Rule Engine Instance Identifier: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span></span>  
  
 <span data-ttu-id="2a6bd-165">**Ruleset 名称︰ ProcessPurchaseOrder**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-165">**Ruleset Name: ProcessPurchaseOrder**</span></span>  
  
 <span data-ttu-id="2a6bd-166">**操作︰ 断言**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-166">**Operation: Assert**</span></span>  
  
 <span data-ttu-id="2a6bd-167">**对象类型︰ TypedXmlDocument:PurchaseOrder: / PurchaseOrder**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-167">**Object Type: TypedXmlDocument:PurchaseOrder:/PurchaseOrder**</span></span>  
  
 <span data-ttu-id="2a6bd-168">**对象实例标识符︰ 64530307**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-168">**Object Instance Identifier: 64530307**</span></span>  
  
 <span data-ttu-id="2a6bd-169">**事实活动 2006 年 8 月 31 日下午 1:33:10**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-169">**FACT ACTIVITY 8/31/2006 1:33:10 PM**</span></span>  
  
 <span data-ttu-id="2a6bd-170">**规则引擎实例标识符︰ bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-170">**Rule Engine Instance Identifier: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span></span>  
  
 <span data-ttu-id="2a6bd-171">**Ruleset 名称︰ ProcessPurchaseOrder**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-171">**Ruleset Name: ProcessPurchaseOrder**</span></span>  
  
 <span data-ttu-id="2a6bd-172">**操作︰ 断言**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-172">**Operation: Assert**</span></span>  
  
 <span data-ttu-id="2a6bd-173">**对象类型︰ TypedXmlDocument:PurchaseOrder: / PurchaseOrder/项**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-173">**Object Type: TypedXmlDocument:PurchaseOrder:/PurchaseOrder/Item**</span></span>  
  
 <span data-ttu-id="2a6bd-174">**对象实例标识符︰ 43901854**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-174">**Object Instance Identifier: 43901854**</span></span>  
  
1.  <span data-ttu-id="2a6bd-175">规则引擎确定哪些子 **TypedXmlDocument** 对象来创建基于在规则中定义的 XPath 选择器。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-175">The rule engine determines which child **TypedXmlDocument** objects to create based on the XPath selectors defined in the rules.</span></span> <span data-ttu-id="2a6bd-176">XPath 选择器值生成业务规则编辑器中的规则时，默认为上方中所选节点的节点 **XML 架构** 事实数据资源管理器中的选项卡。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-176">When you build rules in the Business Rule Composer, the XPath selector value defaults to the node above the node selected in the **XML Schemas** tab in Facts Explorer.</span></span> <span data-ttu-id="2a6bd-177">XPath 的字段值默认为所选节点本身，相对于其父节点。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-177">The XPath field value defaults to the selected node itself, relative to its parent node.</span></span> <span data-ttu-id="2a6bd-178">但是，如果所选节点具有子节点，则只创建指向所选节点的 XPath 选择器绑定，而不创建任何 XPath 字段绑定。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-178">However, if the node you selected has children, only an XPath selector binding is created to point to the node that you selected, and no XPath field binding is created.</span></span>  
  
2.  <span data-ttu-id="2a6bd-179">下表显示了 XPath 选择器和 XPath 字段中使用的字段的绑定值 **ProcessPurchaseOrder** 策略。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-179">The following table shows the XPath Selector and XPath Field binding values for the fields used in the **ProcessPurchaseOrder** policy.</span></span> <span data-ttu-id="2a6bd-180">（该策略只具有一个规则，即 ApprovalRule。）</span><span class="sxs-lookup"><span data-stu-id="2a6bd-180">(The policy has only one rule, ApprovalRule.)</span></span>  
  
|<span data-ttu-id="2a6bd-181">字段名称</span><span class="sxs-lookup"><span data-stu-id="2a6bd-181">Field name</span></span>|<span data-ttu-id="2a6bd-182">XPath 选择器</span><span class="sxs-lookup"><span data-stu-id="2a6bd-182">XPath Selector</span></span>|<span data-ttu-id="2a6bd-183">XPath 字段</span><span class="sxs-lookup"><span data-stu-id="2a6bd-183">XPath Field</span></span>|<span data-ttu-id="2a6bd-184">XPath 选择器（简化形式）</span><span class="sxs-lookup"><span data-stu-id="2a6bd-184">XPath Selector (simplified form)</span></span>|<span data-ttu-id="2a6bd-185">XPath 字段</span><span class="sxs-lookup"><span data-stu-id="2a6bd-185">XPath Field</span></span><br /><br /> <span data-ttu-id="2a6bd-186">（简化形式）</span><span class="sxs-lookup"><span data-stu-id="2a6bd-186">(simplified form)</span></span>|  
|----------------|--------------------|-----------------|----------------------------------------|-----------------------------------------|  
|<span data-ttu-id="2a6bd-187">数量</span><span class="sxs-lookup"><span data-stu-id="2a6bd-187">Quantity</span></span>|<span data-ttu-id="2a6bd-188">/ * [本地名称 （) = PurchaseOrder 和 namespace-uri() = http://EAISolution.PurchaseOrder'] /\*[本地名称 （) = Item 和 namespace-uri() = ']</span><span class="sxs-lookup"><span data-stu-id="2a6bd-188">/*[local-name()='PurchaseOrder' and namespace-uri()='http://EAISolution.PurchaseOrder']/\*[local-name()='Item' and namespace-uri()='']</span></span>|<span data-ttu-id="2a6bd-189">\* [本地名称 （) = 数量和 namespace-uri() = ']</span><span class="sxs-lookup"><span data-stu-id="2a6bd-189">\*[local-name()='Quantity' and namespace-uri()='']</span></span>|<span data-ttu-id="2a6bd-190">/ PurchaseOrder/项</span><span class="sxs-lookup"><span data-stu-id="2a6bd-190">/PurchaseOrder/Item</span></span>|<span data-ttu-id="2a6bd-191">数量</span><span class="sxs-lookup"><span data-stu-id="2a6bd-191">Quantity</span></span>|  
|<span data-ttu-id="2a6bd-192">状态</span><span class="sxs-lookup"><span data-stu-id="2a6bd-192">Status</span></span>|<span data-ttu-id="2a6bd-193">/ \* [本地名称 （) = PurchaseOrder 和 namespace-uri() = http://EAISolution.PurchaseOrder']</span><span class="sxs-lookup"><span data-stu-id="2a6bd-193">/\*[local-name()='PurchaseOrder' and namespace-uri()='http://EAISolution.PurchaseOrder']</span></span>|<span data-ttu-id="2a6bd-194">\* [本地名称 （) = 'Status' 和 namespace-uri() = ']</span><span class="sxs-lookup"><span data-stu-id="2a6bd-194">\*[local-name()='Status' and namespace-uri()='']</span></span>|<span data-ttu-id="2a6bd-195">/ PurchaseOrder</span><span class="sxs-lookup"><span data-stu-id="2a6bd-195">/PurchaseOrder</span></span>|<span data-ttu-id="2a6bd-196">状态</span><span class="sxs-lookup"><span data-stu-id="2a6bd-196">Status</span></span>|  
  
#### <a name="to-view-the-xpath-selector-and-xpath-field-bindings-for-the-quantity-and-status-fields"></a><span data-ttu-id="2a6bd-197">查看“数量”字段和“状态”字段的 Xpath 选择器和 Xpath 字段绑定</span><span class="sxs-lookup"><span data-stu-id="2a6bd-197">To view the Xpath Selector and Xpath Field bindings for the Quantity and Status fields</span></span>  
  
1.  <span data-ttu-id="2a6bd-198">在策略资源管理器窗口中，展开 **策略**, ，展开 **ProcessPurchaseOrder**, ，然后展开 **版本 1.0**。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-198">In the Policy Explorer window, expand **Policies**, expand **ProcessPurchaseOrder**, and then expand **Version 1.0**.</span></span>  
  
2.  <span data-ttu-id="2a6bd-199">单击 **ApprovalRule**。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-199">Click **ApprovalRule**.</span></span>  
  
3.  <span data-ttu-id="2a6bd-200">在右侧的 IF 窗格中，单击 **PO: / PurchaseOrder/项/数量**。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-200">In the IF pane on the right, click **PO:/PurchaseOrder/Item/Quantity**.</span></span>  
  
4.  <span data-ttu-id="2a6bd-201">验证是否能看到显示有关前面的表中的值 **XPath 选择器** 和 **XPath 字段** 属性窗口中的绑定。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-201">Verify that you see the value shown in the preceding table for the **XPath Selector** and **XPath Field** bindings in the Properties window.</span></span>  
  
5.  <span data-ttu-id="2a6bd-202">重复步骤 3 和 4 **PO: / PurchaseOrder/状态** 字段。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-202">Repeat steps 3 and 4 for the **PO:/PurchaseOrder/Status** field.</span></span>  
  
 <span data-ttu-id="2a6bd-203">规则引擎创建子 **TypedXmlDocument** 对象与原始 **TypedXmlDocument** 提交每个 XPath 选择器。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-203">The rule engine creates a child **TypedXmlDocument** object from the original **TypedXmlDocument** you submitted for each XPath selector.</span></span> <span data-ttu-id="2a6bd-204">由于没有使用策略中的两个不同 XPath 选择器 (**/PurchaseOrder/项** 为 **数量** 字段和 **/PurchaseOrder** 为 **状态** 字段)，该规则引擎会创建两个子 **TypedXmlDocument** 对象和断言它们到工作内存的规则引擎。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-204">Because there are two distinct XPath selectors used in the policy (**/PurchaseOrder/Item** for the **Quantity** field and **/PurchaseOrder** for the **Status** field), the rule engine creates two child **TypedXmlDocument** objects and asserts them into the working memory of the rule engine.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2a6bd-205">若要查看跟踪输出试，请单击 **版本 1.0** 策略浏览器窗口中。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-205">To see the trace output again, click **Version 1.0** in the Policy Explorer window.</span></span>  
  
 <span data-ttu-id="2a6bd-206">**条件评估测试 （匹配） 2006 年 8 月 31 日下午 1:33:10**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-206">**CONDITION EVALUATION TEST (MATCH) 8/31/2006 1:33:10 PM**</span></span>  
  
 <span data-ttu-id="2a6bd-207">**规则引擎实例标识符︰ bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-207">**Rule Engine Instance Identifier: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span></span>  
  
 <span data-ttu-id="2a6bd-208">**Ruleset 名称︰ ProcessPurchaseOrder**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-208">**Ruleset Name: ProcessPurchaseOrder**</span></span>  
  
 <span data-ttu-id="2a6bd-209">**测试表达式︰ TypedXmlDocument:PurchaseOrder:/PurchaseOrder/Item.Quantity < = 500**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-209">**Test Expression: TypedXmlDocument:PurchaseOrder:/PurchaseOrder/Item.Quantity <= 500**</span></span>  
  
 <span data-ttu-id="2a6bd-210">**左操作数的值︰ 400**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-210">**Left Operand Value: 400**</span></span>  
  
 <span data-ttu-id="2a6bd-211">**右操作数的值︰ 500**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-211">**Right Operand Value: 500**</span></span>  
  
 <span data-ttu-id="2a6bd-212">**测试结果︰ True**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-212">**Test Result: True**</span></span>  
  
 <span data-ttu-id="2a6bd-213">**安排更新 2006 年 8 月 31 日下午 1:33:10**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-213">**AGENDA UPDATE 8/31/2006 1:33:10 PM**</span></span>  
  
 <span data-ttu-id="2a6bd-214">**规则引擎实例标识符︰ bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-214">**Rule Engine Instance Identifier: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span></span>  
  
 <span data-ttu-id="2a6bd-215">**Ruleset 名称︰ ProcessPurchaseOrder**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-215">**Ruleset Name: ProcessPurchaseOrder**</span></span>  
  
 <span data-ttu-id="2a6bd-216">**操作︰ 添加**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-216">**Operation: Add**</span></span>  
  
 <span data-ttu-id="2a6bd-217">**规则名称︰ ApprovalRule**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-217">**Rule Name: ApprovalRule**</span></span>  
  
 <span data-ttu-id="2a6bd-218">**冲突解决标准︰ 0**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-218">**Conflict Resolution Criteria: 0**</span></span>  
  
 <span data-ttu-id="2a6bd-219">规则引擎使用三阶段的算法（条件评估-冲突解决-执行操作）来执行策略。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-219">The rule engine uses the three-stage Condition Evaluation-Conflict Resolution-Action Execution algorithm to execute policies.</span></span> <span data-ttu-id="2a6bd-220">在条件计算阶段中，规则引擎中的策略中的所有规则的条件的计算结果，并将其条件计算结果为规则添加 `true` 到安排。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-220">In the Condition Evaluation stage, the rule engine evaluates the conditions in all the rules in the policy and adds the rules whose conditions evaluate to `true` to the agenda.</span></span> <span data-ttu-id="2a6bd-221">在此简单示例中， **ProcessPurchaseOrder** 策略具有只有一个规则， **ApprovalRule**。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-221">In this simple example, the **ProcessPurchaseOrder** policy has only one rule, **ApprovalRule**.</span></span> <span data-ttu-id="2a6bd-222">因此，规则引擎计算条件， **数量 < = 500**, 中 **ApprovalRule** 使用的值 **数量** 字段在提交 XML 文档中，这是 **400**。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-222">Therefore, the rule engine evaluates the condition, **Quantity <= 500**, in the **ApprovalRule** using the value of the **Quantity** field in the submitted XML document, which is **400**.</span></span> <span data-ttu-id="2a6bd-223">上面的输出显示左操作数、右操作数和测试结果的值。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-223">The output above shows you the values of the left operand, right operand, and test result.</span></span>  
  
 <span data-ttu-id="2a6bd-224">在第二个阶段中，冲突解决标准阶段，其条件计算结果为规则 `true` 添加到基于它们的优先级别顺序的安排。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-224">In the second stage, the Conflict Resolution Criteria stage, the rules whose conditions evaluate to `true` are added to the agenda in order based on their priority.</span></span> <span data-ttu-id="2a6bd-225">在此方案中，添加规则引擎 **ApprovalRule** 安排到因为的条件 **ApprovalRule** 计算结果为 `true`。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-225">In this scenario, the rule engine adds the **ApprovalRule** to the agenda because the condition for the **ApprovalRule** evaluated to `true`.</span></span> <span data-ttu-id="2a6bd-226">上面的输出中显示的冲突解决方法条件是仅对规则优先级 (**ApprovalRule**)。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-226">The Conflict Resolution Criteria shown in the output above is only the priority on the rule (**ApprovalRule**).</span></span> <span data-ttu-id="2a6bd-227">如果你单击 **ApprovalRule** 策略资源管理器窗口中的节点，你可以看到的值 **优先级** 属性作为属性窗口中的规则 **0**, ，这是一条规则的默认值。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-227">If you click the **ApprovalRule** node in the Policy Explorer window, you can see the value of the **Priority** property on the rule in the Properties window as **0**, which is the default value of a rule.</span></span> <span data-ttu-id="2a6bd-228">如果您在某个策略中具有多个规则，并且想要确保一个规则中的操作在另一个规则中的操作后执行，则应相应设置优先级。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-228">If you have multiple rules in a policy, and you want to make sure that actions in one rule are executed after actions in another rule, you should set the priority appropriately.</span></span> <span data-ttu-id="2a6bd-229">该数字越大，规则的优先级就越高。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-229">The larger the number, the higher the priority.</span></span>  
  
 <span data-ttu-id="2a6bd-230">**规则触发 2006 年 8 月 31 日下午 1:33:10**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-230">**RULE FIRED 8/31/2006 1:33:10 PM**</span></span>  
  
 <span data-ttu-id="2a6bd-231">**规则引擎实例标识符︰ bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-231">**Rule Engine Instance Identifier: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span></span>  
  
 <span data-ttu-id="2a6bd-232">**Ruleset 名称︰ ProcessPurchaseOrder**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-232">**Ruleset Name: ProcessPurchaseOrder**</span></span>  
  
 <span data-ttu-id="2a6bd-233">**规则名称︰ ApprovalRule**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-233">**Rule Name: ApprovalRule**</span></span>  
  
 <span data-ttu-id="2a6bd-234">**冲突解决标准︰ 0**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-234">**Conflict Resolution Criteria: 0**</span></span>  
  
 <span data-ttu-id="2a6bd-235">在最后一个阶段（执行操作阶段）中，规则引擎将开始执行规则中的操作。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-235">In the last stage, the Action Execution stage, the rule engine starts executing the actions in the rule.</span></span> <span data-ttu-id="2a6bd-236">中的一个操作 **ApprovalRule**, ，这会设置的值 **状态** 字段到提交的 XML 文档中 **已批准**。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-236">There is one action in the **ApprovalRule**, which sets the value of the **Status** field in the submitted XML document to **Approved**.</span></span>  
  
 <span data-ttu-id="2a6bd-237">**事实活动 2006 年 8 月 31 日下午 1:33:10**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-237">**FACT ACTIVITY 8/31/2006 1:33:10 PM**</span></span>  
  
 <span data-ttu-id="2a6bd-238">**规则引擎实例标识符︰ bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-238">**Rule Engine Instance Identifier: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span></span>  
  
 <span data-ttu-id="2a6bd-239">**Ruleset 名称︰ ProcessPurchaseOrder**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-239">**Ruleset Name: ProcessPurchaseOrder**</span></span>  
  
 <span data-ttu-id="2a6bd-240">**操作︰ 收回**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-240">**Operation: Retract**</span></span>  
  
 <span data-ttu-id="2a6bd-241">**对象类型︰ TypedXmlDocument:PurchaseOrder**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-241">**Object Type: TypedXmlDocument:PurchaseOrder**</span></span>  
  
 <span data-ttu-id="2a6bd-242">**对象实例标识符︰ 14626574**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-242">**Object Instance Identifier: 14626574**</span></span>  
  
 <span data-ttu-id="2a6bd-243">**事实活动 2006 年 8 月 31 日下午 1:33:10**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-243">**FACT ACTIVITY 8/31/2006 1:33:10 PM**</span></span>  
  
 <span data-ttu-id="2a6bd-244">**规则引擎实例标识符︰ bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-244">**Rule Engine Instance Identifier: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span></span>  
  
 <span data-ttu-id="2a6bd-245">**Ruleset 名称︰ ProcessPurchaseOrder**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-245">**Ruleset Name: ProcessPurchaseOrder**</span></span>  
  
 <span data-ttu-id="2a6bd-246">**操作︰ 收回**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-246">**Operation: Retract**</span></span>  
  
 <span data-ttu-id="2a6bd-247">**对象类型︰ TypedXmlDocument:PurchaseOrder: / PurchaseOrder/项**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-247">**Object Type: TypedXmlDocument:PurchaseOrder:/PurchaseOrder/Item**</span></span>  
  
 <span data-ttu-id="2a6bd-248">**对象实例标识符︰ 43901854**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-248">**Object Instance Identifier: 43901854**</span></span>  
  
 <span data-ttu-id="2a6bd-249">**事实活动 2006 年 8 月 31 日下午 1:33:10**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-249">**FACT ACTIVITY 8/31/2006 1:33:10 PM**</span></span>  
  
 <span data-ttu-id="2a6bd-250">**规则引擎实例标识符︰ bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-250">**Rule Engine Instance Identifier: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span></span>  
  
 <span data-ttu-id="2a6bd-251">**Ruleset 名称︰ ProcessPurchaseOrder**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-251">**Ruleset Name: ProcessPurchaseOrder**</span></span>  
  
 <span data-ttu-id="2a6bd-252">**操作︰ 收回**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-252">**Operation: Retract**</span></span>  
  
 <span data-ttu-id="2a6bd-253">**对象类型︰ TypedXmlDocument:PurchaseOrder: / PurchaseOrder**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-253">**Object Type: TypedXmlDocument:PurchaseOrder:/PurchaseOrder**</span></span>  
  
 <span data-ttu-id="2a6bd-254">**对象实例标识符︰** 64530307</span><span class="sxs-lookup"><span data-stu-id="2a6bd-254">**Object Instance Identifier:** 64530307</span></span>  
  
 <span data-ttu-id="2a6bd-255">提交的所有事实 (**PurchaseOrder**) 向规则引擎和规则引擎创建的子事实数据基于 XPath 选择器 (**\PurchaseOrder** 和 **\PurchaseOrder\Item**) 收回 （删除） 从规则引擎的工作内存。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-255">All the facts submitted (**PurchaseOrder**) to the rule engine and the child facts created by the rule engine based on XPath selectors (**\PurchaseOrder** and **\PurchaseOrder\Item**) are retracted (removed) from the working memory of the rule engine.</span></span>  
  
## <a name="analysis-of-the-output-from-the-second-test-samplepo2xml"></a><span data-ttu-id="2a6bd-256">来自第二个测试的输出分析 (samplepo2.xml)</span><span class="sxs-lookup"><span data-stu-id="2a6bd-256">Analysis of the Output from the Second Test (samplepo2.xml)</span></span>  
 <span data-ttu-id="2a6bd-257">**条件评估测试 （匹配） 9/5/2006年下午 5:24:42**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-257">**CONDITION EVALUATION TEST (MATCH) 9/5/2006 5:24:42 PM**</span></span>  
  
 <span data-ttu-id="2a6bd-258">**规则引擎实例标识符︰ b749d2fd-a883-4c2f-9974-5cf688010622**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-258">**Rule Engine Instance Identifier: b749d2fd-a883-4c2f-9974-5cf688010622**</span></span>  
  
 <span data-ttu-id="2a6bd-259">**Ruleset 名称︰ ProcessPurchaseOrder**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-259">**Ruleset Name: ProcessPurchaseOrder**</span></span>  
  
 <span data-ttu-id="2a6bd-260">**测试表达式︰ TypedXmlDocument:PurchaseOrder:/PurchaseOrder/Item.Quantity < = 500**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-260">**Test Expression: TypedXmlDocument:PurchaseOrder:/PurchaseOrder/Item.Quantity <= 500**</span></span>  
  
 <span data-ttu-id="2a6bd-261">**左操作数的值︰ 700**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-261">**Left Operand Value: 700**</span></span>  
  
 <span data-ttu-id="2a6bd-262">**右操作数的值︰ 500**</span><span class="sxs-lookup"><span data-stu-id="2a6bd-262">**Right Operand Value: 500**</span></span>  
  
 <span data-ttu-id="2a6bd-263">**测试结果︰** False</span><span class="sxs-lookup"><span data-stu-id="2a6bd-263">**Test Result:** False</span></span>  
  
 <span data-ttu-id="2a6bd-264">规则引擎计算条件 (**数量 < = 500**) 中 **ApprovalRule** 使用唯一 **项** 对象。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-264">The rule engine evaluates the condition (**Quantity <= 500**) in the **ApprovalRule** using the lone **Item** object.</span></span> <span data-ttu-id="2a6bd-265">你可以看到左的操作数的值是值 **数量** 在 XML 文档中，元素 **700**。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-265">You can see that left operand value is the value of the **Quantity** element in the XML document, **700**.</span></span> <span data-ttu-id="2a6bd-266">测试结果是 `false` 因为 **700 < = 500**, ，因此该规则不添加到规则引擎的安排。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-266">The test result is `false` because **700 <= 500**, so the rule is not added to the agenda of the rule engine.</span></span> <span data-ttu-id="2a6bd-267">议程中没有任何规则。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-267">There is no rule in the agenda.</span></span> <span data-ttu-id="2a6bd-268">因此，有无操作若要执行和的值 **状态** 字段保持 **XYZ**。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-268">Therefore, there are no actions to execute, and the value of the **Status** field remains **XYZ**.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="2a6bd-269">注释</span><span class="sxs-lookup"><span data-stu-id="2a6bd-269">Comments</span></span>  
  
-   <span data-ttu-id="2a6bd-270">建议您在客户端应用程序（例如 BizTalk 应用程序）中使用策略之前对策略进行测试。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-270">We recommend that you test the policies before using them from client applications such as BizTalk applications.</span></span>  
  
-   <span data-ttu-id="2a6bd-271">当测试使用与数据库事实数据的策略 **该组** 中业务规则编辑器中，绑定 **该组** 对象将自动为您生成。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-271">When you test a policy that uses database facts with the **DataConnection** binding in the Business Rule Composer, a **DataConnection** object is automatically built for you.</span></span> <span data-ttu-id="2a6bd-272">但是，当你调用相同的策略从业务流程使用 **调用规则** 形状，否 **该组** 自动对象传递给策略。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-272">However, when you call the same policy from an orchestration by using the **Call Rules** shape, no **DataConnection** object is passed to the policy automatically.</span></span> <span data-ttu-id="2a6bd-273">应创建 **该组** 业务流程中的对象并将其作为参数传递或创建的事实检索器组件，它断言 **该组** 对象，并配置要使用的事实检索器组件的策略。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-273">You should create a **DataConnection** object in the orchestration and pass it as a parameter or create a fact retriever component that asserts the **DataConnection** object, and configure the policy to use the fact retriever component.</span></span>  
  
-   <span data-ttu-id="2a6bd-274">若要测试使用.NET 事实的策略，你应创建事实创建者组件，并指定它在 **选择事实** 对话框。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-274">To test a policy that uses a .NET fact, you should create a fact creator component and specify it in the **Select Facts** dialog box.</span></span> <span data-ttu-id="2a6bd-275">有关创建事实创建者的详细信息，请参阅[如何创建事实检索器](../core/how-to-create-a-fact-retriever.md)。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-275">For more information about creating fact creators, see [How to Create a Fact Retriever](../core/how-to-create-a-fact-retriever.md).</span></span> <span data-ttu-id="2a6bd-276">当该策略使用数据库事实数据时，可以执行相同的操作 (**TypedDataConnection** 或 **TypedDataTable** 或 **TypedDataRow**) 或 XML 事实 (**TypedXmlDocument**)。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-276">You can do the same thing when the policy uses database facts (**TypedDataConnection** or **TypedDataTable** or **TypedDataRow**) or XML facts (**TypedXmlDocument**).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="2a6bd-277">后续步骤</span><span class="sxs-lookup"><span data-stu-id="2a6bd-277">Next Steps</span></span>  
 <span data-ttu-id="2a6bd-278">现在，你已完成本演练中，执行[演练： 调用从业务流程策略](../core/walkthrough-invoking-the-policy-from-an-orchestration.md)演练中，为你调用的分步说明**ProcessPurchaseOrder**从业务流程的策略。</span><span class="sxs-lookup"><span data-stu-id="2a6bd-278">Now that you have completed this walkthrough, perform the [Walkthrough: Invoking the Policy from an Orchestration](../core/walkthrough-invoking-the-policy-from-an-orchestration.md) walkthrough, which gives you step-by-step instructions for invoking the **ProcessPurchaseOrder** policy from an orchestration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a6bd-279">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2a6bd-279">See Also</span></span>  
 <span data-ttu-id="2a6bd-280">[策略测试跟踪输出](../core/policy-test-trace-output.md) </span><span class="sxs-lookup"><span data-stu-id="2a6bd-280">[Policy Test Trace Output](../core/policy-test-trace-output.md) </span></span>  
 <span data-ttu-id="2a6bd-281">[条件计算和操作执行](../core/condition-evaluation-and-action-execution.md) </span><span class="sxs-lookup"><span data-stu-id="2a6bd-281">[Condition Evaluation and Action Execution](../core/condition-evaluation-and-action-execution.md) </span></span>  
 [<span data-ttu-id="2a6bd-282">议程和优先级</span><span class="sxs-lookup"><span data-stu-id="2a6bd-282">Agenda and Priority</span></span>](../core/agenda-and-priority.md)