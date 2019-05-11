---
title: 演练：跟踪 BizTalk Server 中的策略执行 |Microsoft Docs
description: 本教程启用跟踪，并在 BizTalk Server 中查看策略的跟踪详细信息
ms.custom: ''
ms.date: 04/05/2016
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ef88eae7-f0f8-4f3f-85d0-3961a47395b6
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2285353afb1049574e5f78eafeba41931102ac56
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395948"
---
# <a name="walkthrough-tracking-policy-execution"></a><span data-ttu-id="cc9b1-103">演练：跟踪策略执行</span><span class="sxs-lookup"><span data-stu-id="cc9b1-103">Walkthrough: Tracking Policy Execution</span></span>
<span data-ttu-id="cc9b1-104">有关启用跟踪的分步过程**ProcessPurchaseOrder**策略，并执行策略后查看跟踪信息。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-104">Step-by-step procedures for enabling tracking for the **ProcessPurchaseOrder** policy, and for viewing the tracking information after the policy is executed.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cc9b1-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="cc9b1-105">Prerequisites</span></span>  
<span data-ttu-id="cc9b1-106">完成[演练：修改策略](../core/walkthrough-modifying-the-policy.md)执行本演练中之前的演练。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-106">Complete the [Walkthrough: Modifying the Policy](../core/walkthrough-modifying-the-policy.md) walkthrough before performing this walkthrough.</span></span>  
  
## <a name="enable-tracking-for-the-processpurchaseorder-policy"></a><span data-ttu-id="cc9b1-107">启用 ProcessPurchaseOrder 策略跟踪</span><span class="sxs-lookup"><span data-stu-id="cc9b1-107">Enable tracking for the ProcessPurchaseOrder policy</span></span>  
  
1.  <span data-ttu-id="cc9b1-108">打开 **“BizTalk Server 管理”**。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-108">Open **BizTalk Server Administration**.</span></span> <span data-ttu-id="cc9b1-109">如果已打开，请按 f5 键刷新。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-109">If it's already open, press F5 to refresh it.</span></span>  
  
2.  <span data-ttu-id="cc9b1-110">展开**控制台根节点**，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开**RuleTestApp**。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-110">Expand **Console Root**, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **RuleTestApp**.</span></span>  
  
3.  <span data-ttu-id="cc9b1-111">右键单击**策略**，选择**添加**，然后选择**策略**。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-111">Right-click **Policies**, select **Add**, and then select **Policy**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cc9b1-112">若要启用跟踪的策略，你必须将策略添加到 BizTalk 应用程序通过使用 BizTalk Server 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-112">To enable tracking for a policy, you must add the policy to a BizTalk application by using the BizTalk Server Administration console.</span></span>  
  
4.  <span data-ttu-id="cc9b1-113">在中**添加策略**对话框框中，展开**ProcessPurchaseOrder**，然后选择版本**1.3**。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-113">In the **Add Policies** dialog box, expand **ProcessPurchaseOrder**, and select Version **1.3**.</span></span>  
  
5.  <span data-ttu-id="cc9b1-114">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-114">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="cc9b1-115">如果没有看到**ProcessPurchaseOrder**在列表中，选择 f5 键以刷新视图。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-115">If you don't see **ProcessPurchaseOrder** in the list, select F5 to refresh the view.</span></span>
  
7.  <span data-ttu-id="cc9b1-116">右键单击**ProcessPurchaseOrder**，然后选择**跟踪。**</span><span class="sxs-lookup"><span data-stu-id="cc9b1-116">Right-click **ProcessPurchaseOrder**, and then select **Tracking.**</span></span>  
  
8.  <span data-ttu-id="cc9b1-117">在中**策略跟踪选项**对话框中，选择所有复选都框**事实活动**，**条件评估**，**规则触发**，并**议程更新**。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-117">In the **Policy Tracking Options** dialog box, select all the check boxes for **Fact activity**, **Condition evaluation**, **Rule firings**, and **Agenda updates**.</span></span>  
  
9. <span data-ttu-id="cc9b1-118">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-118">Click **OK**.</span></span>  
  
## <a name="test-the-solution-and-view-the-tracking-information"></a><span data-ttu-id="cc9b1-119">测试解决方案和查看跟踪信息</span><span class="sxs-lookup"><span data-stu-id="cc9b1-119">Test the solution and view the tracking information</span></span>  
  
1.  <span data-ttu-id="cc9b1-120">打开**SamplePO.xml**并**SamplePO2.xml**在记事本中，并将的值更改**状态**字段**XYZ**。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-120">Open **SamplePO.xml** and **SamplePO2.xml** in notepad, and change the value of the **Status** field to **XYZ**.</span></span>  
  
2.  <span data-ttu-id="cc9b1-121">复制**SamplePO.xml**中创建[演练：测试策略](../core/walkthrough-testing-the-policy.md)到业务流程的输入目录。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-121">Copy **SamplePO.xml** that you created in [Walkthrough: Testing the Policy](../core/walkthrough-testing-the-policy.md) to the input directory for the orchestration.</span></span>  
  
3.  <span data-ttu-id="cc9b1-122">您应看到业务流程的输出目录中输出文件。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-122">You should see an output file in the output directory for the orchestration.</span></span> <span data-ttu-id="cc9b1-123">打开输出 XML 文件，可以看到的值**状态**字段设置为**Approved**。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-123">Open the output XML file and notice that the value of the **Status** field is set to **Approved**.</span></span>  
  
4.  <span data-ttu-id="cc9b1-124">在中**BizTalk Server 管理**，请转到**组概述**页上，单击**组中心**选项卡，然后单击**跟踪的服务实例**.</span><span class="sxs-lookup"><span data-stu-id="cc9b1-124">In **BizTalk Server Administration**, go to the **Group Overview** page, click on the **Group Hub** tab, and then click on **Tracked Service Instances**.</span></span>  
  
5.  <span data-ttu-id="cc9b1-125">右键单击业务流程 (RuleTest.Orchestration_1) 的名称，然后单击**消息流**。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-125">Right-click the name of the Orchestration (RuleTest.Orchestration_1), and then click **Message Flow**.</span></span>  
  
6.  <span data-ttu-id="cc9b1-126">单击**单击此链接可查看该业务流程实例的策略执行详细信息**。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-126">Click **Follow this link to view the Policy execution details for this orchestration instance**.</span></span> <span data-ttu-id="cc9b1-127">请确保您看到的窗口的外观如下图所示：</span><span class="sxs-lookup"><span data-stu-id="cc9b1-127">Make sure you see the window that looks like the following figure:</span></span>  
  
     <span data-ttu-id="cc9b1-128">![BRE&#45;演练&#45;FirstScreen](../core/media/1e59fe9e-cf2d-407a-81cd-102b57a515d2.gif "1e59fe9e-cf2d-407a-81cd-102b57a515d2")</span><span class="sxs-lookup"><span data-stu-id="cc9b1-128">![BRE&#45;Walkthrough&#45;FirstScreen](../core/media/1e59fe9e-cf2d-407a-81cd-102b57a515d2.gif "1e59fe9e-cf2d-407a-81cd-102b57a515d2")</span></span>  
  
7. <span data-ttu-id="cc9b1-129">单击时间或**ProcessPurchaseOrder1.3**若要查看下面的屏幕。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-129">Click the time or **ProcessPurchaseOrder1.3** to see the following screen.</span></span> <span data-ttu-id="cc9b1-130">在此屏幕中，可以看到请求策略执行、 业务流程，该策略的执行的时间，ID 和策略的 ID 的服务 （业务流程）。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-130">In this screen, you can see the service (orchestration) that requested the policy execution, the ID of the orchestration, the time at which the policy was executed, and the ID of the policy.</span></span>  
  
     <span data-ttu-id="cc9b1-131">![BRE&#45;演练&#45;PolicyExecDetails](../core/media/a65fd48f-2a54-4cc5-9b45-4cd3c211da33.gif "a65fd48f-2a54-4cc5-9b45-4cd3c211da33")</span><span class="sxs-lookup"><span data-stu-id="cc9b1-131">![BRE&#45;Walkthrough&#45;PolicyExecDetails](../core/media/a65fd48f-2a54-4cc5-9b45-4cd3c211da33.gif "a65fd48f-2a54-4cc5-9b45-4cd3c211da33")</span></span>  
  
8. <span data-ttu-id="cc9b1-132">单击**事实活动**若要查看的事实 （数据），已添加到规则引擎工作内存和从规则引擎工作内存中取消的事实数据。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-132">Click **Fact Activity** to see the facts (data) that were asserted into the rule engine's working memory and the facts that were retracted from the rule engine's working memory.</span></span>  
  
     <span data-ttu-id="cc9b1-133">![BRE&#45;Walkthrough&#45;FactActivity](../core/media/27bc0d84-f202-4f5a-87a1-8b53006b3cee.gif "27bc0d84-f202-4f5a-87a1-8b53006b3cee")</span><span class="sxs-lookup"><span data-stu-id="cc9b1-133">![BRE&#45;Walkthrough&#45;FactActivity](../core/media/27bc0d84-f202-4f5a-87a1-8b53006b3cee.gif "27bc0d84-f202-4f5a-87a1-8b53006b3cee")</span></span>  
  
9. <span data-ttu-id="cc9b1-134">上**文件**菜单上，单击**Navigate 后**。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-134">On the **File** menu, click **Navigate back**.</span></span>  
  
10. <span data-ttu-id="cc9b1-135">单击**条件计算的**。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-135">Click **Conditions that Evaluated**.</span></span> <span data-ttu-id="cc9b1-136">请参阅有关已评估的条件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-136">You see the details about the conditions that were evaluated.</span></span> <span data-ttu-id="cc9b1-137">在这种情况下，在策略中，有两个规则和每个策略有一个条件。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-137">In this case, there are two rules in the policy, and each policy has a condition.</span></span> <span data-ttu-id="cc9b1-138">您可以看到，评估两个条件;其中一个计算结果为`true`，和另一个计算结果为`false`。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-138">You can see that two conditions were evaluated; one evaluated to `true`, and the other one evaluated to `false`.</span></span>  
  
     <span data-ttu-id="cc9b1-139">![BRE&#45;演练&#45;ConditionEvaluation](../core/media/ac772d01-919f-4b22-995b-409501a96848.gif "ac772d01-919f-4b22-995b-409501a96848")</span><span class="sxs-lookup"><span data-stu-id="cc9b1-139">![BRE&#45;Walkthrough&#45;ConditionEvaluation](../core/media/ac772d01-919f-4b22-995b-409501a96848.gif "ac772d01-919f-4b22-995b-409501a96848")</span></span>  
  
11. <span data-ttu-id="cc9b1-140">上**文件**菜单上，单击**Navigate 后**。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-140">On the **File** menu, click **Navigate back**.</span></span>  
  
12. <span data-ttu-id="cc9b1-141">单击**议程更新**。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-141">Click **Agenda Updates**.</span></span> <span data-ttu-id="cc9b1-142">您所见，只有 ApprovalRule 添加到议程。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-142">You can see that only the ApprovalRule is added to the agenda.</span></span> <span data-ttu-id="cc9b1-143">DeniedRule 并未添加到议程，因为其条件计算结果为`false`。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-143">The DeniedRule is not added to the agenda because its condition evaluates to `false`.</span></span>  
  
     <span data-ttu-id="cc9b1-144">![BRE&#45;Walkthrough&#45;Agenda](../core/media/bc85d9ea-fc76-44de-aa75-134f47a5ec20.gif "bc85d9ea-fc76-44de-aa75-134f47a5ec20")</span><span class="sxs-lookup"><span data-stu-id="cc9b1-144">![BRE&#45;Walkthrough&#45;Agenda](../core/media/bc85d9ea-fc76-44de-aa75-134f47a5ec20.gif "bc85d9ea-fc76-44de-aa75-134f47a5ec20")</span></span>  
  
13. <span data-ttu-id="cc9b1-145">单击**ApprovalRule**看到 ApprovalRule 的定义。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-145">Click **ApprovalRule** to see the definition of the ApprovalRule.</span></span>  
  
14. <span data-ttu-id="cc9b1-146">上**文件**菜单上，单击**Navigate 后**。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-146">On the **File** menu, click **Navigate back**.</span></span>  
  
15. <span data-ttu-id="cc9b1-147">上**文件**菜单上，单击**Navigate 后**试。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-147">On **File** menu, click **Navigate back** again.</span></span>  
  
16. <span data-ttu-id="cc9b1-148">单击**触发的规则**。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-148">Click **Rules that fired**.</span></span> <span data-ttu-id="cc9b1-149">您可以看到已触发只有 ApprovalRule （已执行针对 ApprovalRule 的操作）。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-149">You can see that only ApprovalRule was fired (actions for the ApprovalRule were executed).</span></span>  
  
17. <span data-ttu-id="cc9b1-150">上**文件**菜单上，单击**Navigate 后**。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-150">On the **File** menu, click **Navigate back**.</span></span>  
  
18. <span data-ttu-id="cc9b1-151">单击**没有启用的规则**。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-151">Click **Rules that did not fire**.</span></span> <span data-ttu-id="cc9b1-152">您可以看到，DeniedRule 并未触发，因为它不在议程中。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-152">You can see that DeniedRule was not fired because it was not in the agenda.</span></span>  
  
19. <span data-ttu-id="cc9b1-153">重复步骤 1-使用 18 **SamplePO2.xml**。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-153">Repeat steps 1-18 with **SamplePO2.xml**.</span></span>  
  
## <a name="key-details"></a><span data-ttu-id="cc9b1-154">关键详细信息</span><span class="sxs-lookup"><span data-stu-id="cc9b1-154">Key details</span></span>  
  
-   <span data-ttu-id="cc9b1-155">跟踪信息的策略是非常类似于测试策略时，将业务规则编辑器中显示的跟踪信息。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-155">The policy tracking information is very similar to the tracking information you see in Business Rule Composer when you test a policy.</span></span>  
  
-   <span data-ttu-id="cc9b1-156">尽管业务流程名称是 RuleTest.odx，但您看到的业务流程名称 orchestration_1，因为即使更改了名称，该业务流程类型名称设置为 Orchestration_1。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-156">Although the orchestration name is RuleTest.odx, you see the name of the orchestration as Orchestration_1, because the Type Name for the orchestration is set to Orchestration_1 even though the Name is changed.</span></span> <span data-ttu-id="cc9b1-157">跟踪显示业务流程名称采用格式\<Namespace\>。\<键入名称\>。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-157">Tracking is showing you the orchestration name in the format \<Namespace\>.\<Type Name\>.</span></span>  
  
-   <span data-ttu-id="cc9b1-158">如果使用 BizTalk Server 管理控制台从 BizTalk 应用程序删除策略，该工具将删除策略，不仅从应用程序，而且还从规则引擎数据库。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-158">If you delete a policy from a BizTalk application by using the BizTalk Server Administration console, the tool deletes the policy not only from the application, but also from the rule engine database.</span></span> <span data-ttu-id="cc9b1-159">你将无法再看到业务规则编辑器 （按 F5 刷新） 中的策略。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-159">You will no longer see the policy in Business Rule Composer (press F5 to refresh).</span></span> <span data-ttu-id="cc9b1-160">因此，你应从应用程序中删除策略时请小心。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-160">Therefore, you should be careful when deleting a policy from an application.</span></span>  
  
-   <span data-ttu-id="cc9b1-161">在停止 RuleTestApp 并选中**完全停止**选项，ProcessPurchaseOrder 策略 （版本 1.3） 将自动取消部署。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-161">When you stop the RuleTestApp and select the **Full Stop** option, the ProcessPurchaseOrder policy (version 1.3) is automatically undeployed.</span></span>  
  
-   <span data-ttu-id="cc9b1-162">如果策略由多个应用程序，创建单独的应用程序策略，并创建对它的客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-162">If a policy is used by multiple applications, create a separate application for the policy and then create references to it from the client applications.</span></span> <span data-ttu-id="cc9b1-163">如果将策略添加到所有客户端应用程序，当你停止其中一个客户端应用程序时，该策略将取消部署，并对其他客户端应用程序无需再使用该策略。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-163">If you add the policy to all the client applications, when you stop one of the client applications, the policy is undeployed, and the other client applications can no longer use the policy.</span></span> <span data-ttu-id="cc9b1-164">因此最好创建单独的应用程序的两个或多个应用程序间共享的策略。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-164">Therefore it is a good practice to create a separate application for a policy that is shared across two or more applications.</span></span>  
  
-   <span data-ttu-id="cc9b1-165">当你启动 RuleTestApp 时，ProcessPurchaseOrder 策略 （版本 1.3） 将自动部署。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-165">When you start the RuleTestApp, the ProcessPurchaseOrder policy (version 1.3) is automatically deployed.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="cc9b1-166">后续步骤</span><span class="sxs-lookup"><span data-stu-id="cc9b1-166">Next Steps</span></span>  
 <span data-ttu-id="cc9b1-167">现在，已完成本演练，请转到[演练：部署策略](../core/walkthrough-deploying-the-policy.md)演练中，为您提供用于部署策略的分步说明。</span><span class="sxs-lookup"><span data-stu-id="cc9b1-167">Now that you have completed this walkthrough, go to the [Walkthrough: Deploying the Policy](../core/walkthrough-deploying-the-policy.md) walkthrough, which gives you step-by-step instructions for deploying policies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc9b1-168">请参阅</span><span class="sxs-lookup"><span data-stu-id="cc9b1-168">See Also</span></span>  
 <span data-ttu-id="cc9b1-169">[如何配置跟踪的策略](../core/how-to-configure-tracking-for-a-policy.md) </span><span class="sxs-lookup"><span data-stu-id="cc9b1-169">[How to Configure Tracking for a Policy](../core/how-to-configure-tracking-for-a-policy.md) </span></span>  
 [<span data-ttu-id="cc9b1-170">管理策略</span><span class="sxs-lookup"><span data-stu-id="cc9b1-170">Managing Policies</span></span>](../core/managing-policies.md)