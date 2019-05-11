---
title: 演练：修改策略 |Microsoft Docs
ms.custom: ''
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9dd74440-2a45-4a1a-8e36-98796e1e1392
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c0c6027d4aea6aa522b506845cba9f64baf4208d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395324"
---
# <a name="walkthrough-modifying-the-policy"></a><span data-ttu-id="770e7-102">演练：修改策略</span><span class="sxs-lookup"><span data-stu-id="770e7-102">Walkthrough: Modifying the Policy</span></span>
<span data-ttu-id="770e7-103">本演练提供了创建的新版本的分步说明**POVocabulary**，创建的新版本**ProcessPurchaseOrder**策略，以及使用的最新版本**POVocabulary**中的新版本**ProcessPurchaseOrder**策略。</span><span class="sxs-lookup"><span data-stu-id="770e7-103">This walkthrough provides step-by-step instructions for creating a new version of the **POVocabulary**, creating a new version of the **ProcessPurchaseOrder** policy, and using the latest version of the **POVocabulary** in the new version of the **ProcessPurchaseOrder** policy.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="770e7-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="770e7-104">Prerequisites</span></span>  
 <span data-ttu-id="770e7-105">必须完成[演练：向策略添加规则](../core/walkthrough-adding-a-rule-to-the-policy.md)执行本演练中之前的演练。</span><span class="sxs-lookup"><span data-stu-id="770e7-105">You must complete the [Walkthrough: Adding a Rule to the Policy](../core/walkthrough-adding-a-rule-to-the-policy.md) walkthrough before performing this walkthrough.</span></span>  
  
## <a name="overview-of-this-walkthrough"></a><span data-ttu-id="770e7-106">本演练概述</span><span class="sxs-lookup"><span data-stu-id="770e7-106">Overview of This Walkthrough</span></span>  
 <span data-ttu-id="770e7-107">本演练包含三个过程，如下表中所述。</span><span class="sxs-lookup"><span data-stu-id="770e7-107">This walkthrough contains three procedures, as described in the following table.</span></span>  
  
|<span data-ttu-id="770e7-108">过程标题</span><span class="sxs-lookup"><span data-stu-id="770e7-108">Procedure title</span></span>|<span data-ttu-id="770e7-109">过程说明</span><span class="sxs-lookup"><span data-stu-id="770e7-109">Procedure description</span></span>|  
|---------------------|---------------------------|  
|<span data-ttu-id="770e7-110">若要修改 POVocabulary 词汇</span><span class="sxs-lookup"><span data-stu-id="770e7-110">To modify the POVocabulary vocabulary</span></span>|<span data-ttu-id="770e7-111">提供用于创建新的词汇版本的分步说明，若要修改的值**项允许的最大数**从**500**到**1000年**。</span><span class="sxs-lookup"><span data-stu-id="770e7-111">Provides step-by-step instructions for creating a new vocabulary version to modify the value of **Maximum number of items allowed** from **500** to **1000**.</span></span>|  
|<span data-ttu-id="770e7-112">若要修改 ProcessPurchaseOrder 策略以使用更新后的词汇</span><span class="sxs-lookup"><span data-stu-id="770e7-112">To modify the ProcessPurchaseOrder policy to use the updated vocabulary</span></span>|<span data-ttu-id="770e7-113">提供创建的新版本的分步说明**ProcessPurchaseOrder**策略使用的新版本**POVocabulary**。</span><span class="sxs-lookup"><span data-stu-id="770e7-113">Provides step-by-step instructions for creating a new version of the **ProcessPurchaseOrder** policy to use the new version of **POVocabulary**.</span></span>|  
|<span data-ttu-id="770e7-114">若要测试解决方案</span><span class="sxs-lookup"><span data-stu-id="770e7-114">To test the solution</span></span>|<span data-ttu-id="770e7-115">提供分步说明了测试解决方案和验证新策略会生效。</span><span class="sxs-lookup"><span data-stu-id="770e7-115">Provides step-by-step instructions for testing the solution and verifying that the new policy is in effect.</span></span>|  
  
### <a name="to-modify-the-povocabulary-vocabulary"></a><span data-ttu-id="770e7-116">若要修改 POVocabulary 词汇</span><span class="sxs-lookup"><span data-stu-id="770e7-116">To modify the POVocabulary vocabulary</span></span>  
  
1.  <span data-ttu-id="770e7-117">上**启动**菜单中，打开**业务规则编辑器**。</span><span class="sxs-lookup"><span data-stu-id="770e7-117">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="770e7-118">如果您有业务规则编辑器已打开，请按 F5 或单击**重新加载**上**文件**菜单进行刷新。</span><span class="sxs-lookup"><span data-stu-id="770e7-118">If you have Business Rule Composer already open, press F5 or click **Reload** on the **File** menu to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="770e7-119">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="770e7-119">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="770e7-120">要执行此操作，右键单击该应用程序，并选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="770e7-120">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="770e7-121">在事实浏览器窗口中，展开**词汇**，然后展开**POVocabulary**。</span><span class="sxs-lookup"><span data-stu-id="770e7-121">In the Facts Explorer window, expand **Vocabularies**, and then expand **POVocabulary**.</span></span>  
  
3.  <span data-ttu-id="770e7-122">右键单击**版本 1.0-已发布**，然后单击**副本**。</span><span class="sxs-lookup"><span data-stu-id="770e7-122">Right-click **Version 1.0 - Published**, and then click **Copy**.</span></span>  
  
4.  <span data-ttu-id="770e7-123">右键单击**POVocabulary**，然后单击**粘贴词汇版本**。</span><span class="sxs-lookup"><span data-stu-id="770e7-123">Right-click **POVocabulary**, and then click **Paste Vocabulary Version**.</span></span>  
  
5.  <span data-ttu-id="770e7-124">双击**最大允许的项数**中**版本 1.1 （未保存）** 启动词汇定义向导。</span><span class="sxs-lookup"><span data-stu-id="770e7-124">Double-click **Maximum Number of Items Allowed** in **Version 1.1 (not saved)** to start the Vocabulary Definition Wizard.</span></span>  
  
6.  <span data-ttu-id="770e7-125">单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="770e7-125">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="770e7-126">单击“下一步” 。</span><span class="sxs-lookup"><span data-stu-id="770e7-126">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="770e7-127">将值从**500**到**1000年**。</span><span class="sxs-lookup"><span data-stu-id="770e7-127">Change the value from **500** to **1000**.</span></span>  
  
9. <span data-ttu-id="770e7-128">单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="770e7-128">Click **Finish**.</span></span>  
  
10. <span data-ttu-id="770e7-129">右键单击**版本 1.1 （未保存）**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="770e7-129">Right-click **Version 1.1 (not saved)**, and then click **Save**.</span></span>  
  
11. <span data-ttu-id="770e7-130">右键单击**1.1 版**，然后单击**发布**。</span><span class="sxs-lookup"><span data-stu-id="770e7-130">Right-click **Version 1.1**, and then click **Publish**.</span></span>  
  
### <a name="to-modify-the-processpurchaseorder-policy-to-use-the-updated-vocabulary"></a><span data-ttu-id="770e7-131">若要修改 ProcessPurchaseOrder 策略以使用更新后的词汇</span><span class="sxs-lookup"><span data-stu-id="770e7-131">To modify the ProcessPurchaseOrder policy to use the updated vocabulary</span></span>  
  
1.  <span data-ttu-id="770e7-132">在策略浏览器中，展开**策略**，然后展开**ProcessPurchaseOrder**。</span><span class="sxs-lookup"><span data-stu-id="770e7-132">In Policy Explorer, expand **Policies**, and then expand **ProcessPurchaseOrder**.</span></span>  
  
2.  <span data-ttu-id="770e7-133">右键单击**版本 1.2**，然后单击**副本**。</span><span class="sxs-lookup"><span data-stu-id="770e7-133">Right-click **Version 1.2**, and then click **Copy**.</span></span>  
  
3.  <span data-ttu-id="770e7-134">右键单击**ProcessPurchaseOrder**，然后单击**PastePolicyVersion**。</span><span class="sxs-lookup"><span data-stu-id="770e7-134">Right-click **ProcessPurchaseOrder**, and then click **PastePolicyVersion**.</span></span>  
  
4.  <span data-ttu-id="770e7-135">单击**ApprovalRule**中**版本 1.3 （未保存）**。</span><span class="sxs-lookup"><span data-stu-id="770e7-135">Click **ApprovalRule** in **Version 1.3 (not saved)**.</span></span>  
  
5.  <span data-ttu-id="770e7-136">在事实浏览器中，展开**词汇**，展开**POVocabulary**，然后展开**版本 1.1 的已发布**。</span><span class="sxs-lookup"><span data-stu-id="770e7-136">In Facts Explorer, expand **Vocabularies**, expand **POVocabulary**, and then expand **Version 1.1 - Published**.</span></span>  
  
6.  <span data-ttu-id="770e7-137">拖动**最大允许的项数**中**版本 1.1 的已发布**替换**最大允许的项数**如果窗格中的版本 1.0。</span><span class="sxs-lookup"><span data-stu-id="770e7-137">Drag **Maximum Number of Items Allowed** in **Version 1.1 - Published** to replace **Maximum Number of Items Allowed** of version 1.0 in the IF pane.</span></span>  
  
7.  <span data-ttu-id="770e7-138">重复步骤 4 到 6 **DeniedRule**。</span><span class="sxs-lookup"><span data-stu-id="770e7-138">Repeat steps 4-6 with **DeniedRule**.</span></span>  
  
8.  <span data-ttu-id="770e7-139">右键单击**版本 1.3 （未保存）**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="770e7-139">Right-click **Version 1.3 (not saved)**, and then click **Save**.</span></span>  
  
9. <span data-ttu-id="770e7-140">右键单击**版本 1.3**，然后单击**发布**。</span><span class="sxs-lookup"><span data-stu-id="770e7-140">Right-click **Version 1.3**, and then click **Publish**.</span></span>  
  
10. <span data-ttu-id="770e7-141">右键单击**版本 1.3**，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="770e7-141">Right-click **Version 1.3**, and then click **Deploy**.</span></span>  
  
### <a name="to-test-the-solution"></a><span data-ttu-id="770e7-142">若要测试解决方案</span><span class="sxs-lookup"><span data-stu-id="770e7-142">To test the solution</span></span>  
  
1.  <span data-ttu-id="770e7-143">单击**启动**，打开**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="770e7-143">Click **Start**, open **BizTalk Server Administration**.</span></span> <span data-ttu-id="770e7-144">如果你有在 BizTalk Server 管理控制台已打开，请按 f5 键刷新。</span><span class="sxs-lookup"><span data-stu-id="770e7-144">If you have the BizTalk Server Administration console already open, press F5 to refresh it.</span></span>  
  
2.  <span data-ttu-id="770e7-145">右键单击**RuleTestApp**，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="770e7-145">Right-click **RuleTestApp**, and then click **Start**.</span></span> <span data-ttu-id="770e7-146">如果**启动**为禁用状态，已在运行该应用程序，你可以忽略下一步。</span><span class="sxs-lookup"><span data-stu-id="770e7-146">If **Start** is disabled, the application is already running and you can ignore the next step.</span></span>  
  
3.  <span data-ttu-id="770e7-147">单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="770e7-147">Click **Start**.</span></span>  
  
4.  <span data-ttu-id="770e7-148">复制**SamplePO2.xml**文件从 C:\BRE-Walkthroughs 目录的 C:\BRE-Walkthroughs\RuleTestSol\Input 目录到业务流程。</span><span class="sxs-lookup"><span data-stu-id="770e7-148">Copy the **SamplePO2.xml** file from the C:\BRE-Walkthroughs directory to the C:\BRE-Walkthroughs\RuleTestSol\Input directory for the orchestration.</span></span>  
  
5.  <span data-ttu-id="770e7-149">您应看到 C:\BRE-Walkthroughs\RuleTestSol\Output 目录中的输出文件。</span><span class="sxs-lookup"><span data-stu-id="770e7-149">You should see an output file in the C:\BRE-Walkthroughs\RuleTestSol\Output directory.</span></span> <span data-ttu-id="770e7-150">打开输出 XML 文件，可以看到的值**状态**字段设置为**Approved**。</span><span class="sxs-lookup"><span data-stu-id="770e7-150">Open the output XML file and notice that the value of the **Status** field is set to **Approved**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="770e7-151">值**数量**SamplePO2.xml 中的字段为 700。</span><span class="sxs-lookup"><span data-stu-id="770e7-151">The value of the **Quantity** field in SamplePO2.xml is 700.</span></span> <span data-ttu-id="770e7-152">版本 1.3 **ProcessPurchaseOrder**策略将此值与 1000，而不是像版本 1.2 那样比较其与 500 进行比较。</span><span class="sxs-lookup"><span data-stu-id="770e7-152">Version 1.3 of the **ProcessPurchaseOrder** policy compares this value with 1000 instead of comparing it with 500 as version 1.2 did.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="770e7-153">注释</span><span class="sxs-lookup"><span data-stu-id="770e7-153">Comments</span></span>  
  
-   <span data-ttu-id="770e7-154">不能修改已发布的策略。</span><span class="sxs-lookup"><span data-stu-id="770e7-154">A published policy cannot be modified.</span></span> <span data-ttu-id="770e7-155">必须创建要对其进行修改的策略的新版本。</span><span class="sxs-lookup"><span data-stu-id="770e7-155">You must create a new version of the policy to modify it.</span></span> <span data-ttu-id="770e7-156">同样，不能修改已发布的词汇。</span><span class="sxs-lookup"><span data-stu-id="770e7-156">Similarly, a published vocabulary cannot be modified.</span></span> <span data-ttu-id="770e7-157">必须创建新版本的词汇来对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="770e7-157">You must create a new version of the vocabulary to modify it.</span></span>  
  
-   <span data-ttu-id="770e7-158">业务流程调用策略的使用**调用规则**形状将使用最新的部署的策略版本。</span><span class="sxs-lookup"><span data-stu-id="770e7-158">The orchestration invoking a policy by using the **Call Rules** shape uses the latest deployed version of the policy.</span></span> <span data-ttu-id="770e7-159">例如，如果具有版本 1.0、 1.1、 1.2 和 1.3 部署的策略，该业务流程使用版本 1.3。</span><span class="sxs-lookup"><span data-stu-id="770e7-159">For example, if you have versions 1.0, 1.1, 1.2, and 1.3 of the policy deployed, the orchestration uses version 1.3.</span></span> <span data-ttu-id="770e7-160">如果版本 1.3 未部署，版本 1.2 已部署该业务流程使用版本 1.2。</span><span class="sxs-lookup"><span data-stu-id="770e7-160">If version 1.3 is not deployed and version 1.2 is deployed, the orchestration uses version 1.2.</span></span> <span data-ttu-id="770e7-161">因此如果你想要切换回使用版本 1.2，您只需取消部署版本 1.3，并确保版本 1.2 已部署。</span><span class="sxs-lookup"><span data-stu-id="770e7-161">Therefore if you want to switch back to using version 1.2, you just need to undeploy version 1.3, and make sure that version 1.2 is deployed.</span></span>  
  
-   <span data-ttu-id="770e7-162">若要使用特定版本的业务流程中的策略，应使用**表达式**形状，然后调用规则引擎，以通过使用以编程方式执行策略**Policy.Execute**方法。</span><span class="sxs-lookup"><span data-stu-id="770e7-162">To use a specific version of a policy from an orchestration, you should use an **Expression** shape and invoke the rule engine to execute the policy programmatically by using the **Policy.Execute** method.</span></span>  
  
-   <span data-ttu-id="770e7-163">请注意该策略使用词汇定义从版本 1.0 和 1.1 版 POVocabulary 词汇的 1.3 版。</span><span class="sxs-lookup"><span data-stu-id="770e7-163">Note that version 1.3 of the policy uses the vocabulary definitions from both version 1.0 and version 1.1 of the POVocabulary vocabulary.</span></span> <span data-ttu-id="770e7-164">如果将策略的 1.3 版导出到 XML 文件，并导入，即可在另一台计算机上创建策略时，导入过程将查找词汇的两个版本。</span><span class="sxs-lookup"><span data-stu-id="770e7-164">If you export version 1.3 of the policy to an XML file, and import it to create the policy on a different computer, the import process looks for both versions of the vocabulary.</span></span> <span data-ttu-id="770e7-165">因此，您需要将版本 1.0 和版本 1.1 的词汇都导出和导入策略的 1.3 版之前将其导入。</span><span class="sxs-lookup"><span data-stu-id="770e7-165">Therefore you need to export both version 1.0 and version 1.1 of the vocabulary and import them before importing version 1.3 of the policy.</span></span>  
  
-   <span data-ttu-id="770e7-166">部署策略的较新版本后，应等待大约 60 秒，然后再测试该解决方案。</span><span class="sxs-lookup"><span data-stu-id="770e7-166">After you deploy a newer version of the policy, you should wait approximately 60 seconds before testing the solution.</span></span> <span data-ttu-id="770e7-167">规则引擎更新服务看起来有任何更新到策略每隔 60 秒 （1 分钟） 默认情况下。</span><span class="sxs-lookup"><span data-stu-id="770e7-167">The rule engine update service looks for any updates to a policy every 60 seconds (1 minute) by default.</span></span> <span data-ttu-id="770e7-168">如果有更新，它将刷新缓存的更新的信息。</span><span class="sxs-lookup"><span data-stu-id="770e7-168">If there are updates, it refreshes the cache with the updated information.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="770e7-169">后续步骤</span><span class="sxs-lookup"><span data-stu-id="770e7-169">Next Steps</span></span>  
  
-   <span data-ttu-id="770e7-170">现在，已完成本演练中，执行[演练：跟踪策略执行](../core/walkthrough-tracking-policy-execution.md)演练中，为您提供用于跟踪策略执行详细信息的分步说明。</span><span class="sxs-lookup"><span data-stu-id="770e7-170">Now that you have completed this walkthrough, perform the [Walkthrough: Tracking Policy Execution](../core/walkthrough-tracking-policy-execution.md) walkthrough, which gives you step-by-step instructions for tracking policy execution details.</span></span>