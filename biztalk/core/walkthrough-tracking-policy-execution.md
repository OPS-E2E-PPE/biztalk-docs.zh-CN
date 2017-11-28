---
title: "演练： 跟踪 BizTalk Server 中的策略执行 |Microsoft 文档"
description: "教程启用跟踪，并在 BizTalk Server 中查看策略跟踪详细信息"
ms.custom: 
ms.date: 04/05/2016
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef88eae7-f0f8-4f3f-85d0-3961a47395b6
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f1baca3a561702546ca2fae10b1c567042cd387
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="walkthrough-tracking-policy-execution"></a><span data-ttu-id="f345e-103">演练： 跟踪策略执行</span><span class="sxs-lookup"><span data-stu-id="f345e-103">Walkthrough: Tracking Policy Execution</span></span>
<span data-ttu-id="f345e-104">启用跟踪的分步过程**ProcessPurchaseOrder**策略，以及执行策略后，请查看跟踪信息。</span><span class="sxs-lookup"><span data-stu-id="f345e-104">Step-by-step procedures for enabling tracking for the **ProcessPurchaseOrder** policy, and for viewing the tracking information after the policy is executed.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f345e-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="f345e-105">Prerequisites</span></span>  
<span data-ttu-id="f345e-106">完成[演练： 修改策略](../core/walkthrough-modifying-the-policy.md)执行本演练之前的演练。</span><span class="sxs-lookup"><span data-stu-id="f345e-106">Complete the [Walkthrough: Modifying the Policy](../core/walkthrough-modifying-the-policy.md) walkthrough before performing this walkthrough.</span></span>  
  
## <a name="enable-tracking-for-the-processpurchaseorder-policy"></a><span data-ttu-id="f345e-107">启用跟踪 ProcessPurchaseOrder 策略</span><span class="sxs-lookup"><span data-stu-id="f345e-107">Enable tracking for the ProcessPurchaseOrder policy</span></span>  
  
1.  <span data-ttu-id="f345e-108">打开 **“BizTalk Server 管理”**。</span><span class="sxs-lookup"><span data-stu-id="f345e-108">Open **BizTalk Server Administration**.</span></span> <span data-ttu-id="f345e-109">如果已打开，按 F5 刷新它。</span><span class="sxs-lookup"><span data-stu-id="f345e-109">If it's already open, press F5 to refresh it.</span></span>  
  
2.  <span data-ttu-id="f345e-110">展开**控制台根节点**，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开**RuleTestApp**。</span><span class="sxs-lookup"><span data-stu-id="f345e-110">Expand **Console Root**, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **RuleTestApp**.</span></span>  
  
3.  <span data-ttu-id="f345e-111">右键单击**策略**，选择**添加**，然后选择**策略**。</span><span class="sxs-lookup"><span data-stu-id="f345e-111">Right-click **Policies**, select **Add**, and then select **Policy**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f345e-112">若要启用策略跟踪，则必须使用 BizTalk Server 管理控制台，向 BizTalk 应用程序添加策略。</span><span class="sxs-lookup"><span data-stu-id="f345e-112">To enable tracking for a policy, you must add the policy to a BizTalk application by using the BizTalk Server Administration console.</span></span>  
  
4.  <span data-ttu-id="f345e-113">在**添加策略**对话框框中，展开**ProcessPurchaseOrder**，并选择版本**1.3**。</span><span class="sxs-lookup"><span data-stu-id="f345e-113">In the **Add Policies** dialog box, expand **ProcessPurchaseOrder**, and select Version **1.3**.</span></span>  
  
5.  <span data-ttu-id="f345e-114">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="f345e-114">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="f345e-115">如果看不到**ProcessPurchaseOrder**在列表中，选择 f5 键以刷新视图。</span><span class="sxs-lookup"><span data-stu-id="f345e-115">If you don't see **ProcessPurchaseOrder** in the list, select F5 to refresh the view.</span></span>
  
7.  <span data-ttu-id="f345e-116">右键单击**ProcessPurchaseOrder**，然后选择**跟踪。**</span><span class="sxs-lookup"><span data-stu-id="f345e-116">Right-click **ProcessPurchaseOrder**, and then select **Tracking.**</span></span>  
  
8.  <span data-ttu-id="f345e-117">在**策略跟踪选项**对话框中，选择所有的复选框**事实活动**，**条件评估**，**规则触发**，和**安排更新**。</span><span class="sxs-lookup"><span data-stu-id="f345e-117">In the **Policy Tracking Options** dialog box, select all the check boxes for **Fact activity**, **Condition evaluation**, **Rule firings**, and **Agenda updates**.</span></span>  
  
9. <span data-ttu-id="f345e-118">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="f345e-118">Click **OK**.</span></span>  
  
## <a name="test-the-solution-and-view-the-tracking-information"></a><span data-ttu-id="f345e-119">测试解决方案和查看跟踪信息</span><span class="sxs-lookup"><span data-stu-id="f345e-119">Test the solution and view the tracking information</span></span>  
  
1.  <span data-ttu-id="f345e-120">打开**SamplePO.xml**和**SamplePO2.xml**在记事本中，并将的值更改**状态**字段**XYZ**。</span><span class="sxs-lookup"><span data-stu-id="f345e-120">Open **SamplePO.xml** and **SamplePO2.xml** in notepad, and change the value of the **Status** field to **XYZ**.</span></span>  
  
2.  <span data-ttu-id="f345e-121">复制**SamplePO.xml**在中创建[演练： 测试策略](../core/walkthrough-testing-the-policy.md)到业务流程的输入目录。</span><span class="sxs-lookup"><span data-stu-id="f345e-121">Copy **SamplePO.xml** that you created in [Walkthrough: Testing the Policy](../core/walkthrough-testing-the-policy.md) to the input directory for the orchestration.</span></span>  
  
3.  <span data-ttu-id="f345e-122">你应该在输出目录中看到业务流程的输出文件。</span><span class="sxs-lookup"><span data-stu-id="f345e-122">You should see an output file in the output directory for the orchestration.</span></span> <span data-ttu-id="f345e-123">打开输出 XML 文件，可以看到的值**状态**字段设置为**已批准**。</span><span class="sxs-lookup"><span data-stu-id="f345e-123">Open the output XML file and notice that the value of the **Status** field is set to **Approved**.</span></span>  
  
4.  <span data-ttu-id="f345e-124">在**BizTalk Server 管理**，请转到**组概述**页上，单击**组中心数据库**选项卡上，然后单击**跟踪服务实例**.</span><span class="sxs-lookup"><span data-stu-id="f345e-124">In **BizTalk Server Administration**, go to the **Group Overview** page, click on the **Group Hub** tab, and then click on **Tracked Service Instances**.</span></span>  
  
5.  <span data-ttu-id="f345e-125">右击业务流程 (RuleTest.Orchestration_1) 的名称，然后单击**消息流**。</span><span class="sxs-lookup"><span data-stu-id="f345e-125">Right-click the name of the Orchestration (RuleTest.Orchestration_1), and then click **Message Flow**.</span></span>  
  
6.  <span data-ttu-id="f345e-126">单击**点击此链接以查看此业务流程实例的策略执行详细信息**。</span><span class="sxs-lookup"><span data-stu-id="f345e-126">Click **Follow this link to view the Policy execution details for this orchestration instance**.</span></span> <span data-ttu-id="f345e-127">请确保你看到类似于下图窗口：</span><span class="sxs-lookup"><span data-stu-id="f345e-127">Make sure you see the window that looks like the following figure:</span></span>  
  
     <span data-ttu-id="f345e-128">![BRE &#45;演练 &#45;FirstScreen](../core/media/1e59fe9e-cf2d-407a-81cd-102b57a515d2.gif "1e59fe9e-cf2d-407a-81cd-102b57a515d2")</span><span class="sxs-lookup"><span data-stu-id="f345e-128">![BRE&#45;Walkthrough&#45;FirstScreen](../core/media/1e59fe9e-cf2d-407a-81cd-102b57a515d2.gif "1e59fe9e-cf2d-407a-81cd-102b57a515d2")</span></span>  
  
7. <span data-ttu-id="f345e-129">单击相应的时间或**ProcessPurchaseOrder1.3**以查看下面的屏幕。</span><span class="sxs-lookup"><span data-stu-id="f345e-129">Click the time or **ProcessPurchaseOrder1.3** to see the following screen.</span></span> <span data-ttu-id="f345e-130">在此屏幕中，你可看到请求策略执行的服务（业务流程）、业务流程的 ID、策略的执行时间以及策略的 ID。</span><span class="sxs-lookup"><span data-stu-id="f345e-130">In this screen, you can see the service (orchestration) that requested the policy execution, the ID of the orchestration, the time at which the policy was executed, and the ID of the policy.</span></span>  
  
     <span data-ttu-id="f345e-131">![BRE &#45;演练 &#45;PolicyExecDetails](../core/media/a65fd48f-2a54-4cc5-9b45-4cd3c211da33.gif "a65fd48f-2a54-4cc5-9b45-4cd3c211da33")</span><span class="sxs-lookup"><span data-stu-id="f345e-131">![BRE&#45;Walkthrough&#45;PolicyExecDetails](../core/media/a65fd48f-2a54-4cc5-9b45-4cd3c211da33.gif "a65fd48f-2a54-4cc5-9b45-4cd3c211da33")</span></span>  
  
8. <span data-ttu-id="f345e-132">单击**事实活动**若要查看已声明转换规则的事实数据 （数据） 引擎的工作内存和已收回从规则引擎的工作内存的事实数据。</span><span class="sxs-lookup"><span data-stu-id="f345e-132">Click **Fact Activity** to see the facts (data) that were asserted into the rule engine's working memory and the facts that were retracted from the rule engine's working memory.</span></span>  
  
     <span data-ttu-id="f345e-133">![BRE &#45;演练 &#45;FactActivity](../core/media/27bc0d84-f202-4f5a-87a1-8b53006b3cee.gif "27bc0d84-f202-4f5a-87a1-8b53006b3cee")</span><span class="sxs-lookup"><span data-stu-id="f345e-133">![BRE&#45;Walkthrough&#45;FactActivity](../core/media/27bc0d84-f202-4f5a-87a1-8b53006b3cee.gif "27bc0d84-f202-4f5a-87a1-8b53006b3cee")</span></span>  
  
9. <span data-ttu-id="f345e-134">上**文件**菜单上，单击**导航回**。</span><span class="sxs-lookup"><span data-stu-id="f345e-134">On the **File** menu, click **Navigate back**.</span></span>  
  
10. <span data-ttu-id="f345e-135">单击**条件计算**。</span><span class="sxs-lookup"><span data-stu-id="f345e-135">Click **Conditions that Evaluated**.</span></span> <span data-ttu-id="f345e-136">你将看到有关已评估的条件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f345e-136">You see the details about the conditions that were evaluated.</span></span> <span data-ttu-id="f345e-137">在本例中，策略中存在两条规则，并且每个策略都有一个条件。</span><span class="sxs-lookup"><span data-stu-id="f345e-137">In this case, there are two rules in the policy, and each policy has a condition.</span></span> <span data-ttu-id="f345e-138">你可以看到，评估两个条件;一个计算结果为`true`，和另一个计算结果为`false`。</span><span class="sxs-lookup"><span data-stu-id="f345e-138">You can see that two conditions were evaluated; one evaluated to `true`, and the other one evaluated to `false`.</span></span>  
  
     <span data-ttu-id="f345e-139">![BRE &#45;演练 &#45;ConditionEvaluation](../core/media/ac772d01-919f-4b22-995b-409501a96848.gif "ac772d01-919f-4b22-995b-409501a96848")</span><span class="sxs-lookup"><span data-stu-id="f345e-139">![BRE&#45;Walkthrough&#45;ConditionEvaluation](../core/media/ac772d01-919f-4b22-995b-409501a96848.gif "ac772d01-919f-4b22-995b-409501a96848")</span></span>  
  
11. <span data-ttu-id="f345e-140">上**文件**菜单上，单击**导航回**。</span><span class="sxs-lookup"><span data-stu-id="f345e-140">On the **File** menu, click **Navigate back**.</span></span>  
  
12. <span data-ttu-id="f345e-141">单击**安排更新**。</span><span class="sxs-lookup"><span data-stu-id="f345e-141">Click **Agenda Updates**.</span></span> <span data-ttu-id="f345e-142">可以看到，只有 ApprovalRule 添加到了议程中。</span><span class="sxs-lookup"><span data-stu-id="f345e-142">You can see that only the ApprovalRule is added to the agenda.</span></span> <span data-ttu-id="f345e-143">并未将 DeniedRule 添加到议程中，因为其条件的评估结果为 `false`。</span><span class="sxs-lookup"><span data-stu-id="f345e-143">The DeniedRule is not added to the agenda because its condition evaluates to `false`.</span></span>  
  
     <span data-ttu-id="f345e-144">![BRE &#45;演练 &#45;安排](../core/media/bc85d9ea-fc76-44de-aa75-134f47a5ec20.gif "bc85d9ea-fc76-44de-aa75-134f47a5ec20")</span><span class="sxs-lookup"><span data-stu-id="f345e-144">![BRE&#45;Walkthrough&#45;Agenda](../core/media/bc85d9ea-fc76-44de-aa75-134f47a5ec20.gif "bc85d9ea-fc76-44de-aa75-134f47a5ec20")</span></span>  
  
13. <span data-ttu-id="f345e-145">单击**ApprovalRule**若要查看 ApprovalRule 的定义。</span><span class="sxs-lookup"><span data-stu-id="f345e-145">Click **ApprovalRule** to see the definition of the ApprovalRule.</span></span>  
  
14. <span data-ttu-id="f345e-146">上**文件**菜单上，单击**导航回**。</span><span class="sxs-lookup"><span data-stu-id="f345e-146">On the **File** menu, click **Navigate back**.</span></span>  
  
15. <span data-ttu-id="f345e-147">上**文件**菜单上，单击**导航回**试。</span><span class="sxs-lookup"><span data-stu-id="f345e-147">On **File** menu, click **Navigate back** again.</span></span>  
  
16. <span data-ttu-id="f345e-148">单击**激发的规则**。</span><span class="sxs-lookup"><span data-stu-id="f345e-148">Click **Rules that fired**.</span></span> <span data-ttu-id="f345e-149">你可以看到，只触发了 ApprovalRule（已执行针对 ApprovalRule 的操作）。</span><span class="sxs-lookup"><span data-stu-id="f345e-149">You can see that only ApprovalRule was fired (actions for the ApprovalRule were executed).</span></span>  
  
17. <span data-ttu-id="f345e-150">上**文件**菜单上，单击**导航回**。</span><span class="sxs-lookup"><span data-stu-id="f345e-150">On the **File** menu, click **Navigate back**.</span></span>  
  
18. <span data-ttu-id="f345e-151">单击**未不会触发的规则**。</span><span class="sxs-lookup"><span data-stu-id="f345e-151">Click **Rules that did not fire**.</span></span> <span data-ttu-id="f345e-152">可以看到，DeniedRule 并未触发，因为它不在议程中。</span><span class="sxs-lookup"><span data-stu-id="f345e-152">You can see that DeniedRule was not fired because it was not in the agenda.</span></span>  
  
19. <span data-ttu-id="f345e-153">重复步骤 1-18 与**SamplePO2.xml**。</span><span class="sxs-lookup"><span data-stu-id="f345e-153">Repeat steps 1-18 with **SamplePO2.xml**.</span></span>  
  
## <a name="key-details"></a><span data-ttu-id="f345e-154">密钥的详细信息</span><span class="sxs-lookup"><span data-stu-id="f345e-154">Key details</span></span>  
  
-   <span data-ttu-id="f345e-155">当你测试策略时，策略跟踪信息非常类似于你在业务规则编辑器中看到的跟踪信息。</span><span class="sxs-lookup"><span data-stu-id="f345e-155">The policy tracking information is very similar to the tracking information you see in Business Rule Composer when you test a policy.</span></span>  
  
-   <span data-ttu-id="f345e-156">尽管业务流程名称是 RuleTest.odx，但你看到的业务流程名称却是 Orchestration_1，因为尽管“名称”改变，业务流程的“类型名”仍设置为 Orchestration_1。</span><span class="sxs-lookup"><span data-stu-id="f345e-156">Although the orchestration name is RuleTest.odx, you see the name of the orchestration as Orchestration_1, because the Type Name for the orchestration is set to Orchestration_1 even though the Name is changed.</span></span> <span data-ttu-id="f345e-157">跟踪显示你的业务流程名称格式\<Namespace >。\<键入名称 >。</span><span class="sxs-lookup"><span data-stu-id="f345e-157">Tracking is showing you the orchestration name in the format \<Namespace>.\<Type Name>.</span></span>  
  
-   <span data-ttu-id="f345e-158">如果使用 BizTalk Server 管理控制台从 BizTalk 应用程序中删除某个策略，则工具不仅将从应用程序中删除策略，而且还将从规则引擎数据库中删除策略。</span><span class="sxs-lookup"><span data-stu-id="f345e-158">If you delete a policy from a BizTalk application by using the BizTalk Server Administration console, the tool deletes the policy not only from the application, but also from the rule engine database.</span></span> <span data-ttu-id="f345e-159">你将无法在业务规则编辑器中看到策略（按 F5 刷新）。</span><span class="sxs-lookup"><span data-stu-id="f345e-159">You will no longer see the policy in Business Rule Composer (press F5 to refresh).</span></span> <span data-ttu-id="f345e-160">因此，在将策略从应用程序中删除时务必小心。</span><span class="sxs-lookup"><span data-stu-id="f345e-160">Therefore, you should be careful when deleting a policy from an application.</span></span>  
  
-   <span data-ttu-id="f345e-161">在停止 RuleTestApp 并选中**句号**选项，正在自动取消部署 ProcessPurchaseOrder 策略 （1.3 版）。</span><span class="sxs-lookup"><span data-stu-id="f345e-161">When you stop the RuleTestApp and select the **Full Stop** option, the ProcessPurchaseOrder policy (version 1.3) is automatically undeployed.</span></span>  
  
-   <span data-ttu-id="f345e-162">如果多个应用程序共享一个策略，则将为该策略创建一个单独的应用程序，然后从客户端应用程序创建对该应用程序的引用。</span><span class="sxs-lookup"><span data-stu-id="f345e-162">If a policy is used by multiple applications, create a separate application for the policy and then create references to it from the client applications.</span></span> <span data-ttu-id="f345e-163">如果将策略添加到所有客户端应用程序，那么，当你停止其中一个客户端应用程序时，该策略将取消部署，其他客户端应用程序将不再能够使用此策略。</span><span class="sxs-lookup"><span data-stu-id="f345e-163">If you add the policy to all the client applications, when you stop one of the client applications, the policy is undeployed, and the other client applications can no longer use the policy.</span></span> <span data-ttu-id="f345e-164">因此，如果两个或多个应用程序间共享某个策略，则最好为该策略创建一个单独的应用程序。</span><span class="sxs-lookup"><span data-stu-id="f345e-164">Therefore it is a good practice to create a separate application for a policy that is shared across two or more applications.</span></span>  
  
-   <span data-ttu-id="f345e-165">如果启动 RuleTestApp，ProcessPurchaseOrder 策略（版本 1.3）将自动部署。</span><span class="sxs-lookup"><span data-stu-id="f345e-165">When you start the RuleTestApp, the ProcessPurchaseOrder policy (version 1.3) is automatically deployed.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="f345e-166">后续步骤</span><span class="sxs-lookup"><span data-stu-id="f345e-166">Next Steps</span></span>  
 <span data-ttu-id="f345e-167">现在，你已完成本演练，请转到[演练： 部署策略](../core/walkthrough-deploying-the-policy.md)演练中，这为你提供部署策略的分步说明。</span><span class="sxs-lookup"><span data-stu-id="f345e-167">Now that you have completed this walkthrough, go to the [Walkthrough: Deploying the Policy](../core/walkthrough-deploying-the-policy.md) walkthrough, which gives you step-by-step instructions for deploying policies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f345e-168">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f345e-168">See Also</span></span>  
 <span data-ttu-id="f345e-169">[如何配置策略的跟踪](../core/how-to-configure-tracking-for-a-policy.md) </span><span class="sxs-lookup"><span data-stu-id="f345e-169">[How to Configure Tracking for a Policy](../core/how-to-configure-tracking-for-a-policy.md) </span></span>  
 [<span data-ttu-id="f345e-170">管理策略</span><span class="sxs-lookup"><span data-stu-id="f345e-170">Managing Policies</span></span>](../core/managing-policies.md)