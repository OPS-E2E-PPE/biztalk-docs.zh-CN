---
title: "演练： 创建和使用该策略中的词汇 |Microsoft 文档"
ms.custom: 
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2c306a6e-3384-4f43-9c75-c5407cd9aed2
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f44ebd8cb41f96260b48910410014da90bbed0c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="walkthrough-creating-and-using-a-vocabulary-in-the-policy"></a><span data-ttu-id="c4b5a-102">演练： 创建和使用该策略中的词汇</span><span class="sxs-lookup"><span data-stu-id="c4b5a-102">Walkthrough: Creating and Using a Vocabulary in the Policy</span></span>
<span data-ttu-id="c4b5a-103">本演练提供了分步过程来创建词汇和使用中的词汇**ProcessPurchaseOrder**策略。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-103">This walkthrough provides step-by-step procedures for creating a vocabulary and using the vocabulary in the **ProcessPurchaseOrder** policy.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c4b5a-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="c4b5a-104">Prerequisites</span></span>  
 <span data-ttu-id="c4b5a-105">必须完成[演练： 创建简单的业务策略](../core/walkthrough-creating-a-simple-business-policy.md)执行本演练之前的演练。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-105">You must complete the [Walkthrough: Creating a Simple Business Policy](../core/walkthrough-creating-a-simple-business-policy.md) walkthrough before performing this walkthrough.</span></span> <span data-ttu-id="c4b5a-106">不过，我们建议你完成本文档中在本演练之前列出的所有演练。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-106">However, we recommend that you complete all the walkthroughs that are listed before this walkthrough in the documentation.</span></span>  
  
## <a name="overview-of-this-walkthrough"></a><span data-ttu-id="c4b5a-107">本演练的概述</span><span class="sxs-lookup"><span data-stu-id="c4b5a-107">Overview of This Walkthrough</span></span>  
 <span data-ttu-id="c4b5a-108">本演练包含三个过程，如下表所述。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-108">This walkthrough contains three procedures, as described in the following table.</span></span>  
  
|<span data-ttu-id="c4b5a-109">过程标题</span><span class="sxs-lookup"><span data-stu-id="c4b5a-109">Procedure title</span></span>|<span data-ttu-id="c4b5a-110">过程 descritpion</span><span class="sxs-lookup"><span data-stu-id="c4b5a-110">Procedure descritpion</span></span>|  
|---------------------|---------------------------|  
|<span data-ttu-id="c4b5a-111">创建 POVocabulary 词汇</span><span class="sxs-lookup"><span data-stu-id="c4b5a-111">To create the POVocabulary vocabulary</span></span>|<span data-ttu-id="c4b5a-112">提供有关创建的分步说明**POVocabulary**具有三个定义的词汇： 请求的数量，最大数量的项允许，并且请求状态。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-112">Provides step-by-step instructions for creating the **POVocabulary** vocabulary with three definitions: Requested Quantity, Maximum Number of Items Allowed, and Request Status.</span></span>|  
|<span data-ttu-id="c4b5a-113">在 ProcessPurchaseOrder 策略中使用 POVocabulary</span><span class="sxs-lookup"><span data-stu-id="c4b5a-113">To use the POVocabulary in the ProcessPurchaseOrder policy</span></span>|<span data-ttu-id="c4b5a-114">提供有关创建的新版本的分步说明**ProcessPurchaseOrder**策略使用**POVocabulary**。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-114">Provides step-by-step instructions for creating a new version of the **ProcessPurchaseOrder** policy using **POVocabulary**.</span></span>|  
|<span data-ttu-id="c4b5a-115">若要测试解决方案</span><span class="sxs-lookup"><span data-stu-id="c4b5a-115">To test the solution</span></span>|<span data-ttu-id="c4b5a-116">提供用于测试解决方案的分步说明。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-116">Provides step-by-step instructions for testing the solution.</span></span>|  
  
### <a name="to-create-the-povocabulary-vocabulary"></a><span data-ttu-id="c4b5a-117">创建 POVocabulary 词汇</span><span class="sxs-lookup"><span data-stu-id="c4b5a-117">To create the POVocabulary vocabulary</span></span>  
  
1.  <span data-ttu-id="c4b5a-118">上**启动**菜单上，打开**业务规则编辑器**。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-118">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="c4b5a-119">如果已打开业务规则编辑器，请按 F5 刷新。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-119">If you have the Business Rule Composer already open, press F5 to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c4b5a-120">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-120">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="c4b5a-121">要执行此操作，右键单击该应用程序，，然后选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-121">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="c4b5a-122">在事实浏览器窗口中，单击**词汇**选项卡。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-122">In the Facts Explorer window, click the **Vocabularies** tab.</span></span>  
  
3.  <span data-ttu-id="c4b5a-123">右键单击**词汇**，单击**添加新词汇**，然后键入**POVocabulary**作为词汇的名称。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-123">Right-click **Vocabularies**, click **Add New Vocabulary**, and then type **POVocabulary** as the name for the vocabulary.</span></span>  
  
4.  <span data-ttu-id="c4b5a-124">如果在步骤 3 中，不未将词汇表的名称更改为 POVocabulary，更改到词汇名称**POVocabulary**属性窗口中。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-124">If you did not change the name of the vocabulary to POVocabulary in step 3, change the name of the vocabulary to **POVocabulary**in the Properties window.</span></span>  
  
5.  <span data-ttu-id="c4b5a-125">右键单击**（不保存） 1.0 版**中**POVocabulary**，然后单击**添加新定义**。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-125">Right-click **Version 1.0(not saved)** in **POVocabulary**, and then click **Add New Definition**.</span></span>  
  
6.  <span data-ttu-id="c4b5a-126">在词汇定义向导中，选择**XML 文档元素或属性**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-126">In the Vocabulary Definition Wizard, select **XML Document Element or Attribute**, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="c4b5a-127">有关**定义名称**，类型**请求数量**。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-127">For the **Definition name**, type **Requested Quantity**.</span></span>  
  
8.  <span data-ttu-id="c4b5a-128">单击**浏览**，然后选择**PO.xsd**文件中创建[演练： 创建简单的业务策略](../core/walkthrough-creating-a-simple-business-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-128">Click **Browse**, and select the **PO.xsd** file you created in [Walkthrough: Creating a Simple Business Policy](../core/walkthrough-creating-a-simple-business-policy.md).</span></span>  
  
9. <span data-ttu-id="c4b5a-129">在**选择绑定**对话框框中，展开**PurchaseOrder**，展开**项**，然后双击**数量**。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-129">In the **Select Binding** dialog box, expand **PurchaseOrder**, expand **Item**, and then double-click **Quantity**.</span></span>  
  
10. <span data-ttu-id="c4b5a-130">请确保**文档类型**设置为**RuleTest.PO**。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-130">Make sure that the **document type** is set to **RuleTest.PO**.</span></span> <span data-ttu-id="c4b5a-131">如果不是这样，变为 RuleTest.PO 文档类型。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-131">If it is not, change the document type to RuleTest.PO.</span></span> <span data-ttu-id="c4b5a-132">此步骤非常重要。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-132">This step is very important.</span></span>  
  
     <span data-ttu-id="c4b5a-133">![BRE &#45;演练 &#45;ChangeDocType2](../core/media/090f0bce-0594-4a67-87d0-3cd22fbb1796.gif "090f0bce-0594-4a67-87d0-3cd22fbb1796")</span><span class="sxs-lookup"><span data-stu-id="c4b5a-133">![BRE&#45;Walkthrough&#45;ChangeDocType2](../core/media/090f0bce-0594-4a67-87d0-3cd22fbb1796.gif "090f0bce-0594-4a67-87d0-3cd22fbb1796")</span></span>  
  
11. <span data-ttu-id="c4b5a-134">指定**选择操作**中**选择操作**组作为**执行 Get 操作**。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-134">Specify the **select operation** in the **Select operation** group as **Perform Get Operation**.</span></span>  
  
     <span data-ttu-id="c4b5a-135">![BRE &#45;演练 &#45;SelectGet](../core/media/3034649a-2d81-4f08-8044-3ab66a201672.gif "3034649a-2d81-4f08-8044-3ab66a201672")</span><span class="sxs-lookup"><span data-stu-id="c4b5a-135">![BRE&#45;Walkthrough&#45;SelectGet](../core/media/3034649a-2d81-4f08-8044-3ab66a201672.gif "3034649a-2d81-4f08-8044-3ab66a201672")</span></span>  
  
12. <span data-ttu-id="c4b5a-136">单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-136">Click **Finish**.</span></span>  
  
13. <span data-ttu-id="c4b5a-137">右键单击**（不保存） 1.0 版**，然后单击**添加新定义**。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-137">Right-click **Version 1.0(not saved)**, and then click **Add New Definition**.</span></span>  
  
14. <span data-ttu-id="c4b5a-138">选择**XML 文档元素或属性**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-138">Select **XML Document Element or Attribute**, and then click **Next**.</span></span>  
  
15. <span data-ttu-id="c4b5a-139">有关**定义名称**，类型**请求状态**。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-139">For the **Definition name**, type **Request Status**.</span></span>  
  
16. <span data-ttu-id="c4b5a-140">单击**浏览**，然后选择**PO.xsd**文件。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-140">Click **Browse**, and select the **PO.xsd** file.</span></span>  
  
17. <span data-ttu-id="c4b5a-141">在**选择绑定**对话框框中，展开**PurchaseOrder**，然后双击**状态**。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-141">In the **Select Binding** dialog box, expand **PurchaseOrder**, and then double-click **Status**.</span></span>  
  
18. <span data-ttu-id="c4b5a-142">更改**文档类型**到**RuleTest.PO**。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-142">Change the **document type** to **RuleTest.PO**.</span></span> <span data-ttu-id="c4b5a-143">此步骤非常重要。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-143">This step is very important.</span></span>  
  
19. <span data-ttu-id="c4b5a-144">请确保**执行设置操作**选项选择后，，然后单击**下一步。**</span><span class="sxs-lookup"><span data-stu-id="c4b5a-144">Make sure that the  **Perform Set operation** option is selected, and then click **Next.**</span></span>  
  
20. <span data-ttu-id="c4b5a-145">单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-145">Click **Finish**.</span></span>  
  
21. <span data-ttu-id="c4b5a-146">右键单击**（不保存） 1.0 版**，然后单击**添加新定义**。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-146">Right-click **Version 1.0(not saved)**, and then click **Add New Definition**.</span></span>  
  
22. <span data-ttu-id="c4b5a-147">请确保**常量值、 值的范围或设置的值**已选择，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-147">Make sure that **Constant Value, Range of Values, or Set of Values** is selected, and then click **Next**.</span></span>  
  
23. <span data-ttu-id="c4b5a-148">有关**定义名称**，类型**数目的项允许的最大**。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-148">For the **Definition name**, type **Maximum Number of Items Allowed**.</span></span>  
  
24. <span data-ttu-id="c4b5a-149">请确保**常量值定义类型**已选择，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-149">Make sure that **Constant Value definition type** is selected, and then click **Next**.</span></span>  
  
25. <span data-ttu-id="c4b5a-150">类型**500**作为值，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-150">Type **500** for the value, and then click **Finish**.</span></span>  
  
26. <span data-ttu-id="c4b5a-151">右键单击**（不保存） 1.0 版**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-151">Right-click **Version 1.0(not saved)**, and then click **Save**.</span></span>  
  
27. <span data-ttu-id="c4b5a-152">右键单击**（不保存） 1.0 版**，然后单击**发布**。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-152">Right-click **Version 1.0(not saved)**, and then click **Publish**.</span></span>  
  
### <a name="to-use-the-povocabulary-in-the-processpurchaseorder-policy"></a><span data-ttu-id="c4b5a-153">在 ProcessPurchaseOrder 策略中使用 POVocabulary</span><span class="sxs-lookup"><span data-stu-id="c4b5a-153">To use the POVocabulary in the ProcessPurchaseOrder policy</span></span>  
  
1.  <span data-ttu-id="c4b5a-154">在策略资源管理器窗口中，展开**策略**，展开**ProcessPurchaseOrder**，右键单击**版本 1.0**，然后单击**复制**.</span><span class="sxs-lookup"><span data-stu-id="c4b5a-154">In the Policy Explorer window, expand **Policies**, expand **ProcessPurchaseOrder**, right-click **Version 1.0**, and then click **Copy**.</span></span>  
  
2.  <span data-ttu-id="c4b5a-155">右键单击**ProcessPurchaseOrder** ，然后单击**粘贴的策略版本**。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-155">Right-click **ProcessPurchaseOrder** and then click **Paste Policy Version**.</span></span>  
  
3.  <span data-ttu-id="c4b5a-156">单击**ApprovalRule**中**（不保存） 1.1 版**。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-156">Click **ApprovalRule** in **Version 1.1(not saved)**.</span></span>  
  
4.  <span data-ttu-id="c4b5a-157">在事实浏览器窗口中，展开**词汇**，展开**POVocabulary**，展开**版本 1.0**，然后拖动**请求数量**到如果窗格替换 LessThanOrEqual 谓词的左侧显示端 (LHS) 自变量。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-157">In the Facts Explorer window, expand **Vocabularies**, expand **POVocabulary**, expand **Version 1.0**, and then drag **Requested Quantity** to the IF pane to replace the left hand side (LHS) argument of the LessThanOrEqual predicate.</span></span>  
  
     <span data-ttu-id="c4b5a-158">![BRE &#45;演练 &#45; DragReqQty](../core/media/f5ec8bca-344e-4099-a347-0a2298a3f088.gif "f5ec8bca-344e-4099-a347-0a2298a3f088")</span><span class="sxs-lookup"><span data-stu-id="c4b5a-158">![BRE&#45;Walkthrough&#45;DragReqQty](../core/media/f5ec8bca-344e-4099-a347-0a2298a3f088.gif "f5ec8bca-344e-4099-a347-0a2298a3f088")</span></span>  
  
     <span data-ttu-id="c4b5a-159">![BRE &#45;演练 &#45;ReqQty](../core/media/7afddd71-31ce-4868-94c1-d7ffd81f1e47.gif "7afddd71-31ce-4868-94c1-d7ffd81f1e47")</span><span class="sxs-lookup"><span data-stu-id="c4b5a-159">![BRE&#45;Walkthrough&#45;ReqQty](../core/media/7afddd71-31ce-4868-94c1-d7ffd81f1e47.gif "7afddd71-31ce-4868-94c1-d7ffd81f1e47")</span></span>  
  
5.  <span data-ttu-id="c4b5a-160">拖动**数目的项允许的最大**替换的条件的右端 (RHS) 自变量 (**500**)。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-160">Drag **Maximum Number of Items Allowed** to replace the right hand side (RHS) argument of the condition (**500**).</span></span>  
  
6.  <span data-ttu-id="c4b5a-161">选择现有的操作，然后窗格中，右键单击，然后单击**删除操作**。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-161">Select the existing action in the THEN pane, right-click, and then click **Delete action**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c4b5a-162">你还可以在选择该操作后按 Delete 键，以便删除该操作。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-162">You can also press DELETE after selecting the action to delete the action.</span></span>  
  
7.  <span data-ttu-id="c4b5a-163">拖动**请求状态**到**然后**窗格。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-163">Drag **Request Status** to the **THEN** pane.</span></span>  
  
8.  <span data-ttu-id="c4b5a-164">单击**\<空字符串 >**然后键入**已批准**。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-164">Click **\<empty string>** and then type **Approved**.</span></span>  
  
9. <span data-ttu-id="c4b5a-165">右键单击**（不保存） 1.1 版**在策略浏览器窗口中，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-165">Right-click **Version 1.1(not saved)** in the Policy Explorer window, and then click **Save**.</span></span>  
  
10. <span data-ttu-id="c4b5a-166">右键单击**（不保存） 1.1 版**在策略浏览器窗口中，然后单击**发布**。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-166">Right-click **Version 1.1(not saved)** in the Policy Explorer window, and then click **Publish**.</span></span>  
  
### <a name="to-test-the-solution"></a><span data-ttu-id="c4b5a-167">若要测试解决方案</span><span class="sxs-lookup"><span data-stu-id="c4b5a-167">To test the solution</span></span>  
  
1.  <span data-ttu-id="c4b5a-168">在业务规则编辑器，展开**策略**，展开**ProcessPurchaseOrder**，右键单击**版本 1.0-部署**，然后单击**取消部署后再次**.</span><span class="sxs-lookup"><span data-stu-id="c4b5a-168">In Business Rule Composer, expand **Policies**, expand **ProcessPurchaseOrder**, right-click **Version 1.0 - Deployed**, and then click **Undeploy**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c4b5a-169">此步骤是可选的，因为业务流程始终挑选策略的最新部署的版本，在执行步骤 2 后该最新版本是 1.1。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-169">This step is optional because the orchestration always picks the latest deployed version of the policy, which is 1.1 after you perform step 2.</span></span>  
  
2.  <span data-ttu-id="c4b5a-170">右键单击**发布版本 1.1-**，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-170">Right-click **Version 1.1- Published**, and then click **Deploy**.</span></span>  
  
3.  <span data-ttu-id="c4b5a-171">等待大约**60**秒。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-171">Wait for approximately **60** seconds.</span></span> <span data-ttu-id="c4b5a-172">如果存在对其缓存的策略的任何更新，策略引擎更新服务将每 60 秒刷新其缓存。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-172">The rule engine update service refreshes its cache every 60 seconds if there are any updates to a policy that it caches.</span></span> <span data-ttu-id="c4b5a-173">是否执行步骤 1 并不重要，因为业务流程始终挑选策略的最新部署的版本，在此处是 1.1。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-173">It does not matter whether you perform step 1—the orchestration picks up the latest deployed version of the policy, which is 1.1</span></span>  
  
4.  <span data-ttu-id="c4b5a-174">打开**SamplePO.xml**和**SamplePO2.xml**在记事本中，将的值更改**状态**字段**XYZ**。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-174">Open **SamplePO.xml** and **SamplePO2.xml** in Notepad and change the value of the **Status** field to **XYZ**.</span></span>  
  
5.  <span data-ttu-id="c4b5a-175">复制**SamplePO.xml**文件从 C:\BRE-Walkthroughs 目录到 C:\BRE-Walkthroughs\RuleTestSol\Input 目录业务流程。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-175">Copy the **SamplePO.xml** file from C:\BRE-Walkthroughs directory to C:\BRE-Walkthroughs\RuleTestSol\Input directory for the orchestration.</span></span>  
  
6.  <span data-ttu-id="c4b5a-176">你应该在业务流程的 C:\BRE-Walkthroughs\RuleTestSol\Output 目录中看到输出文件。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-176">You should see an output file in the C:\BRE-Walkthroughs\RuleTestSol\Output directory for the orchestration.</span></span> <span data-ttu-id="c4b5a-177">打开输出 XML 文件，可以看到的值**状态**字段设置为**已批准**。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-177">Open the output XML file and notice that the value of the **Status** field is set to **Approved**.</span></span>  
  
7.  <span data-ttu-id="c4b5a-178">重复步骤 5 和 6 **SamplePO2.xml**，请注意，和的值**状态**输出文档中的字段是与输入文档中的相同 (**XYZ**)。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-178">Repeat steps 5 and 6 with **SamplePO2.xml**, and notice that the value of the **Status** field in the output document is the same as in the input document (**XYZ**).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c4b5a-179">值**状态**字段保持相同的 (XYZ)，因为规则引擎不会执行中的操作**ApprovalRule**规则，因为条件被评估为`false`。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-179">The value of the **Status** field remains the same (XYZ) because the rule engine does not execute the action in the **ApprovalRule** rule because the condition evaluated to `false`.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="c4b5a-180">注释</span><span class="sxs-lookup"><span data-stu-id="c4b5a-180">Comments</span></span>  
  
-   <span data-ttu-id="c4b5a-181">在你保存词汇后，仍可以修改它。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-181">After you save the vocabulary, you can still modify it.</span></span> <span data-ttu-id="c4b5a-182">但在你发布词汇后，就不能修改了。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-182">After you publish the vocabulary, you cannot modify it.</span></span>  
  
-   <span data-ttu-id="c4b5a-183">如果你需要修改某一定义、添加新定义或删除某一定义，则应创建词汇的新版本。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-183">If you need to modify a definition, add a new definition, or delete a definition, you should create a new version of the vocabulary.</span></span>  
  
-   <span data-ttu-id="c4b5a-184">只能将已发布的词汇用于策略。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-184">Only published vocabularies can be used in policies.</span></span>  
  
-   <span data-ttu-id="c4b5a-185">在"创建 POVocabulary 词汇"过程中，更改到的文档类型**RuleTest.PO**。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-185">In the "To create the POVocabulary vocabulary" procedure, you changed the document type to **RuleTest.PO**.</span></span> <span data-ttu-id="c4b5a-186">若要查看此更改后，结果在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，在解决方案资源管理器，单击**PO.xsd**。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-186">To see the results of this change, in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], in Solution Explorer, click **PO.xsd**.</span></span> <span data-ttu-id="c4b5a-187">注意，在属性窗口中， **RuleTest**是命名空间的名称和**PO**是的名称**类型**。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-187">In the Properties window, note that **RuleTest** is the name of the namespace, and **PO** is the name of the **Type**.</span></span>  
  
-   <span data-ttu-id="c4b5a-188">在本演练中，你只使用了 XML 文档作为该策略的事实。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-188">In this walkthrough, you used only an XML document as a fact to the policy.</span></span> <span data-ttu-id="c4b5a-189">在创建策略时，你还可以使用 .NET 事实和数据库事实。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-189">You can also use .NET facts and database facts when you create policies</span></span>  
  
-   <span data-ttu-id="c4b5a-190">当选择**执行"设置"操作**词汇定义向导的第二页，可以指定**显示格式字符串**遵循的页面上。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-190">When you select **Perform "Set" operation** on the second page of the Vocabulary Definition Wizard, you can specify a **Display format string** on the page that follows.</span></span> <span data-ttu-id="c4b5a-191">例如，您无法更改中的显示格式字符串**请求状态 {0}**到**请求状态是： {0}**之前单击**完成**中的步骤 20"创建词汇"过程。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-191">For example, you could change the display format string from **Request Status {0}** to **Request status is: {0}** before clicking **Finish** in the step 20 of the "create vocabulary" procedure.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="c4b5a-192">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c4b5a-192">Next Steps</span></span>  
 <span data-ttu-id="c4b5a-193">现在，你已完成本演练中，执行[演练： 将规则添加到策略](../core/walkthrough-adding-a-rule-to-the-policy.md)演练中，这为你提供将添加到新的规则的分步说明**ProcessPurchaseOrder**策略。</span><span class="sxs-lookup"><span data-stu-id="c4b5a-193">Now that you have completed this walkthrough, perform the [Walkthrough: Adding a Rule to the Policy](../core/walkthrough-adding-a-rule-to-the-policy.md) walkthrough, which gives you step-by-step instructions for adding a new rule to the **ProcessPurchaseOrder** policy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4b5a-194">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c4b5a-194">See Also</span></span>  
 <span data-ttu-id="c4b5a-195">[词汇表](../core/vocabularies.md) </span><span class="sxs-lookup"><span data-stu-id="c4b5a-195">[Vocabularies](../core/vocabularies.md) </span></span>  
 <span data-ttu-id="c4b5a-196">[如何开发词汇](../core/how-to-develop-vocabularies.md) </span><span class="sxs-lookup"><span data-stu-id="c4b5a-196">[How to Develop Vocabularies](../core/how-to-develop-vocabularies.md) </span></span>  
 <span data-ttu-id="c4b5a-197">[条件计算和操作执行](../core/condition-evaluation-and-action-execution.md) </span><span class="sxs-lookup"><span data-stu-id="c4b5a-197">[Condition Evaluation and Action Execution](../core/condition-evaluation-and-action-execution.md) </span></span>  
 [<span data-ttu-id="c4b5a-198">安排和优先级</span><span class="sxs-lookup"><span data-stu-id="c4b5a-198">Agenda and Priority</span></span>](../core/agenda-and-priority.md)