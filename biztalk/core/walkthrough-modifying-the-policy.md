---
title: "演练： 修改策略 |Microsoft 文档"
ms.custom: 
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9dd74440-2a45-4a1a-8e36-98796e1e1392
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7292d541adaf0ae2242d1c504f1a845dde66f5dd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="walkthrough-modifying-the-policy"></a><span data-ttu-id="bdb63-102">演练： 修改策略</span><span class="sxs-lookup"><span data-stu-id="bdb63-102">Walkthrough: Modifying the Policy</span></span>
<span data-ttu-id="bdb63-103">本演练提供有关创建的新版本的分步说明**POVocabulary**，创建的新版本**ProcessPurchaseOrder**策略，以及使用的最新版本**POVocabulary**的新版本中**ProcessPurchaseOrder**策略。</span><span class="sxs-lookup"><span data-stu-id="bdb63-103">This walkthrough provides step-by-step instructions for creating a new version of the **POVocabulary**, creating a new version of the **ProcessPurchaseOrder** policy, and using the latest version of the **POVocabulary** in the new version of the **ProcessPurchaseOrder** policy.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="bdb63-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="bdb63-104">Prerequisites</span></span>  
 <span data-ttu-id="bdb63-105">必须完成[演练： 将规则添加到策略](../core/walkthrough-adding-a-rule-to-the-policy.md)执行本演练之前的演练。</span><span class="sxs-lookup"><span data-stu-id="bdb63-105">You must complete the [Walkthrough: Adding a Rule to the Policy](../core/walkthrough-adding-a-rule-to-the-policy.md) walkthrough before performing this walkthrough.</span></span>  
  
## <a name="overview-of-this-walkthrough"></a><span data-ttu-id="bdb63-106">本演练的概述</span><span class="sxs-lookup"><span data-stu-id="bdb63-106">Overview of This Walkthrough</span></span>  
 <span data-ttu-id="bdb63-107">本演练包含三个过程，如下表所述。</span><span class="sxs-lookup"><span data-stu-id="bdb63-107">This walkthrough contains three procedures, as described in the following table.</span></span>  
  
|<span data-ttu-id="bdb63-108">过程标题</span><span class="sxs-lookup"><span data-stu-id="bdb63-108">Procedure title</span></span>|<span data-ttu-id="bdb63-109">过程说明</span><span class="sxs-lookup"><span data-stu-id="bdb63-109">Procedure description</span></span>|  
|---------------------|---------------------------|  
|<span data-ttu-id="bdb63-110">若要修改的 POVocabulary 词汇</span><span class="sxs-lookup"><span data-stu-id="bdb63-110">To modify the POVocabulary vocabulary</span></span>|<span data-ttu-id="bdb63-111">提供创建新的词汇版本以修改的值的指导**项允许的最大数目**从**500**到**1000年**。</span><span class="sxs-lookup"><span data-stu-id="bdb63-111">Provides step-by-step instructions for creating a new vocabulary version to modify the value of **Maximum number of items allowed** from **500** to **1000**.</span></span>|  
|<span data-ttu-id="bdb63-112">若要修改 ProcessPurchaseOrder 策略，以使用更新的词汇</span><span class="sxs-lookup"><span data-stu-id="bdb63-112">To modify the ProcessPurchaseOrder policy to use the updated vocabulary</span></span>|<span data-ttu-id="bdb63-113">提供有关创建的新版本的分步说明**ProcessPurchaseOrder**要使用新版本的策略**POVocabulary**。</span><span class="sxs-lookup"><span data-stu-id="bdb63-113">Provides step-by-step instructions for creating a new version of the **ProcessPurchaseOrder** policy to use the new version of **POVocabulary**.</span></span>|  
|<span data-ttu-id="bdb63-114">若要测试解决方案</span><span class="sxs-lookup"><span data-stu-id="bdb63-114">To test the solution</span></span>|<span data-ttu-id="bdb63-115">提供测试解决方案和验证新策略是否有效的分步说明。</span><span class="sxs-lookup"><span data-stu-id="bdb63-115">Provides step-by-step instructions for testing the solution and verifying that the new policy is in effect.</span></span>|  
  
### <a name="to-modify-the-povocabulary-vocabulary"></a><span data-ttu-id="bdb63-116">若要修改的 POVocabulary 词汇</span><span class="sxs-lookup"><span data-stu-id="bdb63-116">To modify the POVocabulary vocabulary</span></span>  
  
1.  <span data-ttu-id="bdb63-117">上**启动**菜单上，打开**业务规则编辑器**。</span><span class="sxs-lookup"><span data-stu-id="bdb63-117">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="bdb63-118">如果必须业务规则编辑器已打开，按 F5 或单击**重新加载**上**文件**菜单可对其进行刷新。</span><span class="sxs-lookup"><span data-stu-id="bdb63-118">If you have Business Rule Composer already open, press F5 or click **Reload** on the **File** menu to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bdb63-119">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="bdb63-119">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="bdb63-120">要执行此操作，右键单击该应用程序，，然后选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="bdb63-120">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="bdb63-121">在事实浏览器窗口中，展开**词汇**，然后展开**POVocabulary**。</span><span class="sxs-lookup"><span data-stu-id="bdb63-121">In the Facts Explorer window, expand **Vocabularies**, and then expand **POVocabulary**.</span></span>  
  
3.  <span data-ttu-id="bdb63-122">右键单击**版本 1.0-发布**，然后单击**复制**。</span><span class="sxs-lookup"><span data-stu-id="bdb63-122">Right-click **Version 1.0 - Published**, and then click **Copy**.</span></span>  
  
4.  <span data-ttu-id="bdb63-123">右键单击**POVocabulary**，然后单击**粘贴词汇版本**。</span><span class="sxs-lookup"><span data-stu-id="bdb63-123">Right-click **POVocabulary**, and then click **Paste Vocabulary Version**.</span></span>  
  
5.  <span data-ttu-id="bdb63-124">双击**数目的项允许的最大**中**（不保存） 1.1 版**以启动词汇定义向导。</span><span class="sxs-lookup"><span data-stu-id="bdb63-124">Double-click **Maximum Number of Items Allowed** in **Version 1.1 (not saved)** to start the Vocabulary Definition Wizard.</span></span>  
  
6.  <span data-ttu-id="bdb63-125">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="bdb63-125">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="bdb63-126">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="bdb63-126">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="bdb63-127">将值从**500**到**1000年**。</span><span class="sxs-lookup"><span data-stu-id="bdb63-127">Change the value from **500** to **1000**.</span></span>  
  
9. <span data-ttu-id="bdb63-128">单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="bdb63-128">Click **Finish**.</span></span>  
  
10. <span data-ttu-id="bdb63-129">右键单击**（不保存） 1.1 版**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="bdb63-129">Right-click **Version 1.1 (not saved)**, and then click **Save**.</span></span>  
  
11. <span data-ttu-id="bdb63-130">右键单击**版本 1.1**，然后单击**发布**。</span><span class="sxs-lookup"><span data-stu-id="bdb63-130">Right-click **Version 1.1**, and then click **Publish**.</span></span>  
  
### <a name="to-modify-the-processpurchaseorder-policy-to-use-the-updated-vocabulary"></a><span data-ttu-id="bdb63-131">若要修改 ProcessPurchaseOrder 策略，以使用更新的词汇</span><span class="sxs-lookup"><span data-stu-id="bdb63-131">To modify the ProcessPurchaseOrder policy to use the updated vocabulary</span></span>  
  
1.  <span data-ttu-id="bdb63-132">在策略资源管理器中，展开**策略**，然后展开**ProcessPurchaseOrder**。</span><span class="sxs-lookup"><span data-stu-id="bdb63-132">In Policy Explorer, expand **Policies**, and then expand **ProcessPurchaseOrder**.</span></span>  
  
2.  <span data-ttu-id="bdb63-133">右键单击**版本 1.2**，然后单击**复制**。</span><span class="sxs-lookup"><span data-stu-id="bdb63-133">Right-click **Version 1.2**, and then click **Copy**.</span></span>  
  
3.  <span data-ttu-id="bdb63-134">右键单击**ProcessPurchaseOrder**，然后单击**PastePolicyVersion**。</span><span class="sxs-lookup"><span data-stu-id="bdb63-134">Right-click **ProcessPurchaseOrder**, and then click **PastePolicyVersion**.</span></span>  
  
4.  <span data-ttu-id="bdb63-135">单击**ApprovalRule**中**版本 1.3 （不保存）**。</span><span class="sxs-lookup"><span data-stu-id="bdb63-135">Click **ApprovalRule** in **Version 1.3 (not saved)**.</span></span>  
  
5.  <span data-ttu-id="bdb63-136">在事实数据资源管理器中，展开**词汇**，展开**POVocabulary**，然后展开**版本 1.1-发布**。</span><span class="sxs-lookup"><span data-stu-id="bdb63-136">In Facts Explorer, expand **Vocabularies**, expand **POVocabulary**, and then expand **Version 1.1 - Published**.</span></span>  
  
6.  <span data-ttu-id="bdb63-137">拖动**数目的项允许的最大**中**版本 1.1-发布**替换**数目的项允许的最大**如果窗格中的版本 1.0。</span><span class="sxs-lookup"><span data-stu-id="bdb63-137">Drag **Maximum Number of Items Allowed** in **Version 1.1 - Published** to replace **Maximum Number of Items Allowed** of version 1.0 in the IF pane.</span></span>  
  
7.  <span data-ttu-id="bdb63-138">重复步骤 4-6 与**DeniedRule**。</span><span class="sxs-lookup"><span data-stu-id="bdb63-138">Repeat steps 4-6 with **DeniedRule**.</span></span>  
  
8.  <span data-ttu-id="bdb63-139">右键单击**版本 1.3 （不保存）**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="bdb63-139">Right-click **Version 1.3 (not saved)**, and then click **Save**.</span></span>  
  
9. <span data-ttu-id="bdb63-140">右键单击**版本 1.3**，然后单击**发布**。</span><span class="sxs-lookup"><span data-stu-id="bdb63-140">Right-click **Version 1.3**, and then click **Publish**.</span></span>  
  
10. <span data-ttu-id="bdb63-141">右键单击**版本 1.3**，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="bdb63-141">Right-click **Version 1.3**, and then click **Deploy**.</span></span>  
  
### <a name="to-test-the-solution"></a><span data-ttu-id="bdb63-142">若要测试解决方案</span><span class="sxs-lookup"><span data-stu-id="bdb63-142">To test the solution</span></span>  
  
1.  <span data-ttu-id="bdb63-143">单击**启动**，打开**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="bdb63-143">Click **Start**, open **BizTalk Server Administration**.</span></span> <span data-ttu-id="bdb63-144">如果 BizTalk Server 管理控制台已经打开，则按下 F5 键以便刷新它。</span><span class="sxs-lookup"><span data-stu-id="bdb63-144">If you have the BizTalk Server Administration console already open, press F5 to refresh it.</span></span>  
  
2.  <span data-ttu-id="bdb63-145">右键单击**RuleTestApp**，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="bdb63-145">Right-click **RuleTestApp**, and then click **Start**.</span></span> <span data-ttu-id="bdb63-146">如果**启动**是禁用，应用程序已在运行，你可以忽略下一步。</span><span class="sxs-lookup"><span data-stu-id="bdb63-146">If **Start** is disabled, the application is already running and you can ignore the next step.</span></span>  
  
3.  <span data-ttu-id="bdb63-147">单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="bdb63-147">Click **Start**.</span></span>  
  
4.  <span data-ttu-id="bdb63-148">复制**SamplePO2.xml**文件从 C:\BRE-Walkthroughs 目录到 C:\BRE-Walkthroughs\RuleTestSol\Input 目录业务流程。</span><span class="sxs-lookup"><span data-stu-id="bdb63-148">Copy the **SamplePO2.xml** file from the C:\BRE-Walkthroughs directory to the C:\BRE-Walkthroughs\RuleTestSol\Input directory for the orchestration.</span></span>  
  
5.  <span data-ttu-id="bdb63-149">您应该在 C:\BRE-Walkthroughs\RuleTestSol\Output 目录中看到输出文件。</span><span class="sxs-lookup"><span data-stu-id="bdb63-149">You should see an output file in the C:\BRE-Walkthroughs\RuleTestSol\Output directory.</span></span> <span data-ttu-id="bdb63-150">打开输出 XML 文件，可以看到的值**状态**字段设置为**已批准**。</span><span class="sxs-lookup"><span data-stu-id="bdb63-150">Open the output XML file and notice that the value of the **Status** field is set to **Approved**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bdb63-151">值**数量**中 SamplePO2.xml 字段是 700。</span><span class="sxs-lookup"><span data-stu-id="bdb63-151">The value of the **Quantity** field in SamplePO2.xml is 700.</span></span> <span data-ttu-id="bdb63-152">1.3 版**ProcessPurchaseOrder**策略将使用 1000 个而不是与进行比较来 500 版本 1.2 像此值进行比较。</span><span class="sxs-lookup"><span data-stu-id="bdb63-152">Version 1.3 of the **ProcessPurchaseOrder** policy compares this value with 1000 instead of comparing it with 500 as version 1.2 did.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="bdb63-153">注释</span><span class="sxs-lookup"><span data-stu-id="bdb63-153">Comments</span></span>  
  
-   <span data-ttu-id="bdb63-154">已发布的策略不能修改。</span><span class="sxs-lookup"><span data-stu-id="bdb63-154">A published policy cannot be modified.</span></span> <span data-ttu-id="bdb63-155">必须创建一个新的策略版本才能修改它。</span><span class="sxs-lookup"><span data-stu-id="bdb63-155">You must create a new version of the policy to modify it.</span></span> <span data-ttu-id="bdb63-156">同样，已发布的词汇不能修改。</span><span class="sxs-lookup"><span data-stu-id="bdb63-156">Similarly, a published vocabulary cannot be modified.</span></span> <span data-ttu-id="bdb63-157">必须创建一个新的词汇版本才能修改它。</span><span class="sxs-lookup"><span data-stu-id="bdb63-157">You must create a new version of the vocabulary to modify it.</span></span>  
  
-   <span data-ttu-id="bdb63-158">业务流程调用通过使用策略**调用规则**形状使用最新的部署策略版本。</span><span class="sxs-lookup"><span data-stu-id="bdb63-158">The orchestration invoking a policy by using the **Call Rules** shape uses the latest deployed version of the policy.</span></span> <span data-ttu-id="bdb63-159">例如，如果已部署了策略的版本 1.0、版本 1.1、版本 1.2 和版本 1.3，则业务流程使用版本 1.3。</span><span class="sxs-lookup"><span data-stu-id="bdb63-159">For example, if you have versions 1.0, 1.1, 1.2, and 1.3 of the policy deployed, the orchestration uses version 1.3.</span></span> <span data-ttu-id="bdb63-160">如果版本 1.3 未部署，版本 1.2 已部署，则业务流程使用版本 1.2。</span><span class="sxs-lookup"><span data-stu-id="bdb63-160">If version 1.3 is not deployed and version 1.2 is deployed, the orchestration uses version 1.2.</span></span> <span data-ttu-id="bdb63-161">因此，如果希望转而使用版本 1.2，只需要取消部署版本 1.3，确保版本 1.2 已部署。</span><span class="sxs-lookup"><span data-stu-id="bdb63-161">Therefore if you want to switch back to using version 1.2, you just need to undeploy version 1.3, and make sure that version 1.2 is deployed.</span></span>  
  
-   <span data-ttu-id="bdb63-162">若要使用来自一个业务流程的策略的特定版本，你应使用**表达式**的形状，然后调用以通过使用以编程方式执行策略所需的规则引擎对**Policy.Execute**方法。</span><span class="sxs-lookup"><span data-stu-id="bdb63-162">To use a specific version of a policy from an orchestration, you should use an **Expression** shape and invoke the rule engine to execute the policy programmatically by using the **Policy.Execute** method.</span></span>  
  
-   <span data-ttu-id="bdb63-163">注意，策略的版本 1.3 使用来自 POVocabulary 词汇的版本 1.0 和版本 1.1 的词汇定义。</span><span class="sxs-lookup"><span data-stu-id="bdb63-163">Note that version 1.3 of the policy uses the vocabulary definitions from both version 1.0 and version 1.1 of the POVocabulary vocabulary.</span></span> <span data-ttu-id="bdb63-164">如果将策略的版本 1.3 导出至 XML 文件，然后再将其导入，以便在另一台计算机上创建策略，导入进程将同时查找词汇的两个版本。</span><span class="sxs-lookup"><span data-stu-id="bdb63-164">If you export version 1.3 of the policy to an XML file, and import it to create the policy on a different computer, the import process looks for both versions of the vocabulary.</span></span> <span data-ttu-id="bdb63-165">因此，您需要在导入策略的版本 1.3 之前导出词汇的版本 1.0 和版本 1.1，再导入这两个版本。</span><span class="sxs-lookup"><span data-stu-id="bdb63-165">Therefore you need to export both version 1.0 and version 1.1 of the vocabulary and import them before importing version 1.3 of the policy.</span></span>  
  
-   <span data-ttu-id="bdb63-166">在部署策略的较新版本后，在测试解决方案前应该等待大约 60 秒。</span><span class="sxs-lookup"><span data-stu-id="bdb63-166">After you deploy a newer version of the policy, you should wait approximately 60 seconds before testing the solution.</span></span> <span data-ttu-id="bdb63-167">默认情况下，规则引擎更新服务每隔 60 秒（1 分钟）就会查找策略的任何更新。</span><span class="sxs-lookup"><span data-stu-id="bdb63-167">The rule engine update service looks for any updates to a policy every 60 seconds (1 minute) by default.</span></span> <span data-ttu-id="bdb63-168">如果有更新，它将用更新信息刷新缓存。</span><span class="sxs-lookup"><span data-stu-id="bdb63-168">If there are updates, it refreshes the cache with the updated information.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="bdb63-169">后续步骤</span><span class="sxs-lookup"><span data-stu-id="bdb63-169">Next Steps</span></span>  
  
-   <span data-ttu-id="bdb63-170">现在，你已完成本演练中，执行[演练： 跟踪策略执行](../core/walkthrough-tracking-policy-execution.md)演练中，这为你提供用于跟踪策略执行详细信息的分步说明。</span><span class="sxs-lookup"><span data-stu-id="bdb63-170">Now that you have completed this walkthrough, perform the [Walkthrough: Tracking Policy Execution](../core/walkthrough-tracking-policy-execution.md) walkthrough, which gives you step-by-step instructions for tracking policy execution details.</span></span>