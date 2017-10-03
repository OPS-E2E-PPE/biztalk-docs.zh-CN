---
title: "演练： 将规则添加到策略 |Microsoft 文档"
ms.custom: 
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b2a682c0-a5d7-4550-924d-be9fa29b84d2
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 343dc2e9c7965ffb27a806d18944da99777dd3ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="walkthrough-adding-a-rule-to-the-policy"></a><span data-ttu-id="23deb-102">演练： 将规则添加到策略</span><span class="sxs-lookup"><span data-stu-id="23deb-102">Walkthrough: Adding a Rule to the Policy</span></span>
<span data-ttu-id="23deb-103">本演练提供了分步过程添加一个名为规则**DeniedRule**到**ProcessPurchaseOrder**策略。</span><span class="sxs-lookup"><span data-stu-id="23deb-103">This walkthrough provides step-by-step procedures for adding a rule named **DeniedRule** to the **ProcessPurchaseOrder** policy.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="23deb-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="23deb-104">Prerequisites</span></span>  
 <span data-ttu-id="23deb-105">必须完成[演练： 创建和使用该策略中的词汇](../core/walkthrough-creating-and-using-a-vocabulary-in-the-policy.md)执行本演练之前的演练。</span><span class="sxs-lookup"><span data-stu-id="23deb-105">You must complete the [Walkthrough: Creating and Using a Vocabulary in the Policy](../core/walkthrough-creating-and-using-a-vocabulary-in-the-policy.md) walkthrough before performing this walkthrough.</span></span>  
  
## <a name="overview-of-this-walkthrough"></a><span data-ttu-id="23deb-106">本演练的概述</span><span class="sxs-lookup"><span data-stu-id="23deb-106">Overview of This Walkthrough</span></span>  
 <span data-ttu-id="23deb-107">本演练包含三个过程，如下表所述。</span><span class="sxs-lookup"><span data-stu-id="23deb-107">This walkthrough contains three procedures, as described in the following table.</span></span>  
  
|<span data-ttu-id="23deb-108">过程标题</span><span class="sxs-lookup"><span data-stu-id="23deb-108">Procedure title</span></span>|<span data-ttu-id="23deb-109">过程说明</span><span class="sxs-lookup"><span data-stu-id="23deb-109">Procedure description</span></span>|  
|---------------------|---------------------------|  
|<span data-ttu-id="23deb-110">若要将 DeniedRule 添加到 ProcessPurchaseOrder 策略</span><span class="sxs-lookup"><span data-stu-id="23deb-110">To add DeniedRule to the ProcessPurchaseOrder policy</span></span>|<span data-ttu-id="23deb-111">提供将添加一个名为的新规则的分步说明**DeniedRule**到**ProcessPurchaseOrder**策略。</span><span class="sxs-lookup"><span data-stu-id="23deb-111">Provides step-by-step instructions for adding a new rule named **DeniedRule** to the **ProcessPurchaseOrder** policy.</span></span> <span data-ttu-id="23deb-112">**DeniedRule**规则设置的值**状态**字段**拒绝**如果的值**数量**大于 500。</span><span class="sxs-lookup"><span data-stu-id="23deb-112">The **DeniedRule** rule sets the value of the **Status** field to **Denied** if the value of the **Quantity** is greater than 500.</span></span>|  
|<span data-ttu-id="23deb-113">若要使用业务规则编辑器进行测试</span><span class="sxs-lookup"><span data-stu-id="23deb-113">To test with Business Rule Composer</span></span>|<span data-ttu-id="23deb-114">提供用于测试的分步说明**ProcessPurchaseOrder**通过业务规则编辑器的策略。</span><span class="sxs-lookup"><span data-stu-id="23deb-114">Provides step-by-step instructions for testing the **ProcessPurchaseOrder** policy by using Business Rule Composer.</span></span>|  
|<span data-ttu-id="23deb-115">若要测试解决方案</span><span class="sxs-lookup"><span data-stu-id="23deb-115">To test the solution</span></span>|<span data-ttu-id="23deb-116">提供用于测试解决方案的分步说明。</span><span class="sxs-lookup"><span data-stu-id="23deb-116">Provides step-by-step instructions for testing the solution.</span></span>|  
  
### <a name="to-add-deniedrule-to-the-processpurchaseorder-policy"></a><span data-ttu-id="23deb-117">若要将 DeniedRule 添加到 ProcessPurchaseOrder 策略</span><span class="sxs-lookup"><span data-stu-id="23deb-117">To add DeniedRule to the ProcessPurchaseOrder policy</span></span>  
  
1.  <span data-ttu-id="23deb-118">上**启动**菜单上，打开**业务规则编辑器**。</span><span class="sxs-lookup"><span data-stu-id="23deb-118">On the **Start** menu, open **Business Rule Composer**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="23deb-119">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="23deb-119">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="23deb-120">要执行此操作，右键单击该应用程序，，然后选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="23deb-120">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="23deb-121">在策略资源管理器窗口中，展开**策略**，展开**ProcessPurchaseOrder**，右键单击**版本 1.1**，然后单击**复制**.</span><span class="sxs-lookup"><span data-stu-id="23deb-121">In the Policy Explorer window, expand **Policies**, expand **ProcessPurchaseOrder**, right-click **Version 1.1**, and then click **Copy**.</span></span>  
  
3.  <span data-ttu-id="23deb-122">右键单击**ProcessPurchaseOrder**，然后单击**粘贴的策略版本**。</span><span class="sxs-lookup"><span data-stu-id="23deb-122">Right-click **ProcessPurchaseOrder**, and then click **Paste Policy Version**.</span></span>  
  
4.  <span data-ttu-id="23deb-123">右键单击**（不保存） 1.2 版**，单击**添加新规则**，然后将更改到规则的名称**DeniedRule**。</span><span class="sxs-lookup"><span data-stu-id="23deb-123">Right-click **Version 1.2(not saved)**, click **Add New Rule**, and then change the name of the rule to **DeniedRule**.</span></span>  
  
5.  <span data-ttu-id="23deb-124">如果你忘记更改到规则的名称**DeniedRule**在步骤 4 中，单击**规则 1**，和名称更改为**DeniedRule**属性窗口中。</span><span class="sxs-lookup"><span data-stu-id="23deb-124">If you forgot to change the name of the rule to **DeniedRule** in step 4, click **Rule1**, and change the name to **DeniedRule** in the Properties window.</span></span>  
  
6.  <span data-ttu-id="23deb-125">在 IF 窗格中，右键单击**条件**，指向**谓词**，然后单击**大于**。</span><span class="sxs-lookup"><span data-stu-id="23deb-125">In the IF pane, right-click **Conditions**, point to **Predicates**, and then click **Greater Than**.</span></span>  
  
7.  <span data-ttu-id="23deb-126">在事实浏览器窗口中，单击**词汇**选项卡。</span><span class="sxs-lookup"><span data-stu-id="23deb-126">In the Facts Explorer window, click the **Vocabularies** tab.</span></span>  
  
8.  <span data-ttu-id="23deb-127">展开**词汇**，展开**POVocabulary**，展开**版本 1.0-发布**，然后拖动**请求数量**到**argument1**如果窗格中。</span><span class="sxs-lookup"><span data-stu-id="23deb-127">Expand **Vocabularies**, expand **POVocabulary**, expand **Version 1.0 - Published**, and then drag **Request Quantity** to **argument1** in the IF pane.</span></span>  
  
9. <span data-ttu-id="23deb-128">拖动**项允许的最大数目**到**argument2**如果窗格中。</span><span class="sxs-lookup"><span data-stu-id="23deb-128">Drag **Maximum number of items allowed** to **argument2** in the IF pane.</span></span>  
  
10. <span data-ttu-id="23deb-129">拖动**请求状态**到然后窗格。</span><span class="sxs-lookup"><span data-stu-id="23deb-129">Drag **Request Status** to the THEN pane.</span></span>  
  
11. <span data-ttu-id="23deb-130">单击**\<空字符串 >**然后键入**拒绝**。</span><span class="sxs-lookup"><span data-stu-id="23deb-130">Click **\<empty string>** and then type **Denied**.</span></span>  
  
12. <span data-ttu-id="23deb-131">右键单击**（不保存） 1.2 版**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="23deb-131">Right-click **Version 1.2 (not saved)**, and then click **Save**.</span></span>  
  
13. <span data-ttu-id="23deb-132">右键单击**版本 1.2**，然后单击**发布**。</span><span class="sxs-lookup"><span data-stu-id="23deb-132">Right-click **Version 1.2**, and then click **Publish**.</span></span>  
  
14. <span data-ttu-id="23deb-133">右键单击**版本 1.2**，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="23deb-133">Right-click **Version 1.2**, and then click **Deploy**.</span></span>  
  
### <a name="to-test-with-business-rule-composer"></a><span data-ttu-id="23deb-134">若要使用业务规则编辑器进行测试</span><span class="sxs-lookup"><span data-stu-id="23deb-134">To test with Business Rule Composer</span></span>  
  
1.  <span data-ttu-id="23deb-135">在记事本中打开的 SamplePO.xml 和 SamplePO2.xml 文件并将更改的值**状态**字段**XYZ**。</span><span class="sxs-lookup"><span data-stu-id="23deb-135">Open the SamplePO.xml and SamplePO2.xml files in Notepad and change the value of the **Status** field to **XYZ**.</span></span>  
  
2.  <span data-ttu-id="23deb-136">在策略资源管理器窗口中，展开**策略**，展开**ProcessPurchaseOrder**，右键单击**版本 1.2**，然后单击**测试策略**.</span><span class="sxs-lookup"><span data-stu-id="23deb-136">In the Policy Explorer window, expand **Policies**, expand **ProcessPurchaseOrder**, right-click **Version 1.2**, and then click **Test Policy**.</span></span>  
  
3.  <span data-ttu-id="23deb-137">下**XMLDocuments**节点中，选择**RuleTest.PO**，然后单击**添加实例**。</span><span class="sxs-lookup"><span data-stu-id="23deb-137">Under the **XMLDocuments** node, select **RuleTest.PO**, and then click **Add Instance**.</span></span>  
  
4.  <span data-ttu-id="23deb-138">选择**SamplePO.xml**，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="23deb-138">Select **SamplePO.xml**, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="23deb-139">单击**测试**。</span><span class="sxs-lookup"><span data-stu-id="23deb-139">Click **Test**.</span></span>  
  
6.  <span data-ttu-id="23deb-140">查看**安排更新**部分在输出中，并请注意，只有**ApprovalRule**添加到安排。</span><span class="sxs-lookup"><span data-stu-id="23deb-140">Look at the **Agenda Update** section in the output, and notice that only **ApprovalRule** is added to the agenda.</span></span> <span data-ttu-id="23deb-141">因此，它是引发的唯一规则（执行与该规则关联的操作）。</span><span class="sxs-lookup"><span data-stu-id="23deb-141">Therefore it is the only rule that fires (actions associated with the rule are executed).</span></span>  
  
7.  <span data-ttu-id="23deb-142">打开**SamplePO.xml**中记事本，并请注意，值**状态**字段设置为**已批准**。</span><span class="sxs-lookup"><span data-stu-id="23deb-142">Open **SamplePO.xml** in Notepad and notice that the value of the **Status** field is set to **Approved**.</span></span>  
  
8.  <span data-ttu-id="23deb-143">在策略资源管理器窗口中，展开**策略**，展开**ProcessPurchaseOrder**，右键单击**版本 1.2**，然后单击**测试策略。**</span><span class="sxs-lookup"><span data-stu-id="23deb-143">In the Policy Explorer window, expand **Policies**, expand **ProcessPurchaseOrder**, right-click **Version 1.2**, and then click **Test Policy.**</span></span>  
  
9. <span data-ttu-id="23deb-144">选择**SamplePO.xml**，单击**删除实例**，然后单击**添加实例**。</span><span class="sxs-lookup"><span data-stu-id="23deb-144">Select **SamplePO.xml**, click **Remove instance**, and then click **Add Instance**.</span></span>  
  
10. <span data-ttu-id="23deb-145">选择**SamplePO2.xml**，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="23deb-145">Select **SamplePO2.xml**, and then click **Open**.</span></span>  
  
11. <span data-ttu-id="23deb-146">单击**测试**。</span><span class="sxs-lookup"><span data-stu-id="23deb-146">Click **Test**.</span></span>  
  
12. <span data-ttu-id="23deb-147">查看**安排更新**部分在输出中，并请注意，只有**DeniedRule**添加到安排。</span><span class="sxs-lookup"><span data-stu-id="23deb-147">Look at the **Agenda Update** section in the output, and notice that only **DeniedRule** is added to the agenda.</span></span> <span data-ttu-id="23deb-148">因此，它是引发的唯一规则。</span><span class="sxs-lookup"><span data-stu-id="23deb-148">Therefore it is the only rule that fires.</span></span>  
  
13. <span data-ttu-id="23deb-149">打开**SamplePO2.xml**中记事本，并请注意，值**状态**字段是**拒绝**。</span><span class="sxs-lookup"><span data-stu-id="23deb-149">Open **SamplePO2.xml** in Notepad and notice that the value of the **Status** field is **Denied**.</span></span>  
  
### <a name="to-test-the-solution"></a><span data-ttu-id="23deb-150">若要测试解决方案</span><span class="sxs-lookup"><span data-stu-id="23deb-150">To test the solution</span></span>  
  
1.  <span data-ttu-id="23deb-151">打开**SamplePO.xml**和**SamplePO2.xml**在记事本中，将的值更改**状态**字段**XYZ**。</span><span class="sxs-lookup"><span data-stu-id="23deb-151">Open **SamplePO.xml** and **SamplePO2.xml** in Notepad and change the value of the **Status** field to **XYZ**.</span></span>  
  
2.  <span data-ttu-id="23deb-152">复制**SamplePO.xml**文件从 C:\BRE-Walkthroughs 目录到 C:\BRE-Walkthroughs\RuleTestSol\Input 目录业务流程。</span><span class="sxs-lookup"><span data-stu-id="23deb-152">Copy the **SamplePO.xml** file from the C:\BRE-Walkthroughs directory to the C:\BRE-Walkthroughs\RuleTestSol\Input directory for the orchestration.</span></span>  
  
3.  <span data-ttu-id="23deb-153">你应该在业务流程的 C:\BRE-Walkthroughs\RuleTestSol\Output 目录中看到输出文件。</span><span class="sxs-lookup"><span data-stu-id="23deb-153">You should see an output file in the C:\BRE-Walkthroughs\RuleTestSol\Output directory for the orchestration.</span></span> <span data-ttu-id="23deb-154">打开输出 XML 文件，可以看到的值**状态**字段设置为**已批准**。</span><span class="sxs-lookup"><span data-stu-id="23deb-154">Open the output XML file and notice that the value of the **Status** field is set to **Approved**.</span></span>  
  
4.  <span data-ttu-id="23deb-155">重复步骤 2 和 3 的**SamplePO2.xml**，请注意，和的值**状态**字段设置为**拒绝**输出文档中。</span><span class="sxs-lookup"><span data-stu-id="23deb-155">Repeat steps 2 and 3 with **SamplePO2.xml**, and notice that the value of the **Status** field is set to **Denied** in the output document.</span></span> <span data-ttu-id="23deb-156">这样可证明业务流程使用的 1.2 版**ProcessPurchaseOrder**策略。</span><span class="sxs-lookup"><span data-stu-id="23deb-156">This proves that the orchestration is using version 1.2 of the **ProcessPurchaseOrder** policy.</span></span> <span data-ttu-id="23deb-157">业务流程使用最新部署的版本的**ProcessPurchaseOrder**策略，即**1.2**。</span><span class="sxs-lookup"><span data-stu-id="23deb-157">The orchestration uses the latest deployed version of the **ProcessPurchaseOrder** policy, which is **1.2**.</span></span> <span data-ttu-id="23deb-158">为了使用该策略的 1.2 版，您无需取消部署该策略的 1.1 版。</span><span class="sxs-lookup"><span data-stu-id="23deb-158">You do not need to undeploy version 1.1 of the policy to use version 1.2 of the policy.</span></span> <span data-ttu-id="23deb-159">但是，您需要等待大约 60 秒，然后再测试该解决方案。</span><span class="sxs-lookup"><span data-stu-id="23deb-159">However, you need to wait for approximately 60 seconds before testing the solution.</span></span> <span data-ttu-id="23deb-160">有关详细信息，请参阅备注部分。</span><span class="sxs-lookup"><span data-stu-id="23deb-160">For more information, see the Comments section.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="23deb-161">注释</span><span class="sxs-lookup"><span data-stu-id="23deb-161">Comments</span></span>  
  
-   <span data-ttu-id="23deb-162">一个策略可拥有一个或多个规则。</span><span class="sxs-lookup"><span data-stu-id="23deb-162">A policy can have one or more rules.</span></span> <span data-ttu-id="23deb-163">对于策略中规则的数目，不存在逻辑限制。</span><span class="sxs-lookup"><span data-stu-id="23deb-163">There is no logical limit on the number of rules in a policy.</span></span>  
  
-   <span data-ttu-id="23deb-164">规则引擎使用“条件评估-冲突解决-执行操作”算法。</span><span class="sxs-lookup"><span data-stu-id="23deb-164">The rule engine uses a Condition Evaluation - Conflict Resolution - Action Execution algorithm.</span></span> <span data-ttu-id="23deb-165">在**条件计算**阶段中，规则引擎计算中的所有规则的条件。</span><span class="sxs-lookup"><span data-stu-id="23deb-165">In the **Condition Evaluation** stage, the rule engine evaluates conditions in all the rules.</span></span> <span data-ttu-id="23deb-166">其条件评估结果为 true 的规则将成为用于执行的候选规则。</span><span class="sxs-lookup"><span data-stu-id="23deb-166">The rules whose conditions evaluate to true become candidate rules for execution.</span></span> <span data-ttu-id="23deb-167">在**冲突解决**阶段，在将规则添加到规则的优先级别顺序安排的候选。</span><span class="sxs-lookup"><span data-stu-id="23deb-167">In the **Conflict Resolution** stage, the candidate rules are added to the agenda in the order of the priority of the rule.</span></span> <span data-ttu-id="23deb-168">在**操作执行**阶段，在执行规则的候选的操作。</span><span class="sxs-lookup"><span data-stu-id="23deb-168">In the **Action Execution** stage, the actions in the candidate rules are executed.</span></span> <span data-ttu-id="23deb-169">如果候选规则具有相同的优先级，则不存在执行这些规则的操作的明确顺序。</span><span class="sxs-lookup"><span data-stu-id="23deb-169">If candidate rules have the same priority, there is no deterministic order in which the actions for those rules are executed.</span></span> <span data-ttu-id="23deb-170">您应该假定它们并行执行。</span><span class="sxs-lookup"><span data-stu-id="23deb-170">You should assume that they are executed in parallel.</span></span>  
  
-   <span data-ttu-id="23deb-171">在此情况下，对于任何给定的示例文件，只引发其中一个规则。</span><span class="sxs-lookup"><span data-stu-id="23deb-171">In this scenario, for any given sample file, only one of the rules is fired.</span></span> <span data-ttu-id="23deb-172">请确保更改的值**状态**字段之前运行测试。</span><span class="sxs-lookup"><span data-stu-id="23deb-172">Make sure that you change the value of the **Status** field before running a test.</span></span>  
  
-   <span data-ttu-id="23deb-173">在部署策略的新版本时，在测试前应该等待大约 60 秒。</span><span class="sxs-lookup"><span data-stu-id="23deb-173">When a new version of the policy is deployed, you should wait approximately 60 seconds before testing.</span></span> <span data-ttu-id="23deb-174">规则引擎更新服务将定期轮询规则引擎数据库（默认情况下为每 60 秒轮询一次），以便查找新部署的策略。</span><span class="sxs-lookup"><span data-stu-id="23deb-174">The rule engine update service polls the rule engine database on a periodic basis (every 60 seconds by default) to look for newly deployed policies.</span></span> <span data-ttu-id="23deb-175">规则引擎更新服务将用与来自规则引擎数据库的策略的最新部署版本有关的信息来更新内存中的策略对象。</span><span class="sxs-lookup"><span data-stu-id="23deb-175">The rule engine update service updates the policy object in memory with the information about the latest deployed version of the policy from the rule engine database.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="23deb-176">后续步骤</span><span class="sxs-lookup"><span data-stu-id="23deb-176">Next Steps</span></span>  
 <span data-ttu-id="23deb-177">现在，你已完成本演练中，执行[演练： 修改策略](../core/walkthrough-modifying-the-policy.md)演练中，提供有关修改的策略以批准与的值的采购订单的分步说明**数量**小于或等于 1000 （而不是 500)。</span><span class="sxs-lookup"><span data-stu-id="23deb-177">Now that you have completed this walkthrough, perform the [Walkthrough: Modifying the Policy](../core/walkthrough-modifying-the-policy.md) walkthrough, which gives you step-by-step instructions for modifying the policy to approve purchase orders with the value of **quantity** less than or equal to 1000 (instead of 500).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23deb-178">另请参阅</span><span class="sxs-lookup"><span data-stu-id="23deb-178">See Also</span></span>  
 <span data-ttu-id="23deb-179">[条件计算和操作执行](../core/condition-evaluation-and-action-execution.md) </span><span class="sxs-lookup"><span data-stu-id="23deb-179">[Condition Evaluation and Action Execution](../core/condition-evaluation-and-action-execution.md) </span></span>  
 [<span data-ttu-id="23deb-180">安排和优先级</span><span class="sxs-lookup"><span data-stu-id="23deb-180">Agenda and Priority</span></span>](../core/agenda-and-priority.md)