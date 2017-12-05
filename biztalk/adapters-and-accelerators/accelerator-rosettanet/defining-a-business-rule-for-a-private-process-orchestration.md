---
title: "为私有进程业务流程中定义的业务规则 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, policies
- vocabularies, saving
- private processes, orchestrations
- business rules, private processes
- creating, vocabularies
- vocabularies, business rules
- business rules, vocabularies
- policies, deploying
- vocabularies, creating
- orchestrations, private-process orchestrations
- private processes, customizing
- policies, publishing
- business rules, Set elements
- creating, policies
- customizing private processes
- Set elements
- business rules, orchestrations
- publishing, vocabularies
- vocabularies, publishing
- creating, rules
- business rules, Get elements
- policies, saving
- publishing, policies
- Get elements
- orchestrations, business rules
- rules
- private processes, business rules
- policies, creating
ms.assetid: 5d2b0257-1b15-482b-a562-798b808e9a2d
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8dd0ebb22bcf6253604e4e8bf7fd858deb776b0
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="defining-a-business-rule-for-a-private-process-orchestration"></a><span data-ttu-id="8b67a-102">为私有进程业务流程中定义的业务规则</span><span class="sxs-lookup"><span data-stu-id="8b67a-102">Defining a Business Rule for a Private Process Orchestration</span></span>
<span data-ttu-id="8b67a-103">你可以定义确认专用流程中使用的业务规则。</span><span class="sxs-lookup"><span data-stu-id="8b67a-103">You can define a business rule for use in an acknowledgement private process.</span></span> <span data-ttu-id="8b67a-104">这使你可以动态修改业务规则，而无须停止专用业务流程。</span><span class="sxs-lookup"><span data-stu-id="8b67a-104">This lets you to modify the business rule dynamically without stopping the private-process orchestration.</span></span> <span data-ttu-id="8b67a-105">此过程使用 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 业务规则引擎，</span><span class="sxs-lookup"><span data-stu-id="8b67a-105">This process uses the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Business Rule Engine.</span></span> <span data-ttu-id="8b67a-106">它包括以下步骤：</span><span class="sxs-lookup"><span data-stu-id="8b67a-106">This process involves the following steps:</span></span>  
  
1.  <span data-ttu-id="8b67a-107">添加新词汇。</span><span class="sxs-lookup"><span data-stu-id="8b67a-107">Adding a new vocabulary.</span></span> <span data-ttu-id="8b67a-108">此步骤需要定义至少一个词汇常数值。</span><span class="sxs-lookup"><span data-stu-id="8b67a-108">This involves defining at least one vocabulary constant value.</span></span> <span data-ttu-id="8b67a-109">此常数值设置业务规则阈值。</span><span class="sxs-lookup"><span data-stu-id="8b67a-109">This sets a business-rule threshold.</span></span> <span data-ttu-id="8b67a-110">此步骤还包括定义 XML 文档的 `Get` 和 `Set` 元素。</span><span class="sxs-lookup"><span data-stu-id="8b67a-110">It also involves defining XML document `Get` and `Set` elements.</span></span> <span data-ttu-id="8b67a-111">这将确定如何[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]使用阈值。</span><span class="sxs-lookup"><span data-stu-id="8b67a-111">This establishes how [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] uses the threshold.</span></span>  
  
2.  <span data-ttu-id="8b67a-112">添加新策略。</span><span class="sxs-lookup"><span data-stu-id="8b67a-112">Adding a new policy.</span></span> <span data-ttu-id="8b67a-113">此步骤涉及创建策略、创建一套规则，然后保存、发布和部署该策略。</span><span class="sxs-lookup"><span data-stu-id="8b67a-113">This involves creating a policy, creating a set of rules, and then saving, publishing, and deploying the policy.</span></span>  
  
3.  <span data-ttu-id="8b67a-114">从专用业务流程中调用该业务规则。</span><span class="sxs-lookup"><span data-stu-id="8b67a-114">Calling the business rule from the private-process orchestration.</span></span> <span data-ttu-id="8b67a-115">这涉及到添加**调用规则**形状上的与业务流程。</span><span class="sxs-lookup"><span data-stu-id="8b67a-115">This involves adding a **Call Rules** shape to the orchestration.</span></span>  
  
 <span data-ttu-id="8b67a-116">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK 包括一个示例，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]业务策略、 samplebtarnpolicy.xml，在\<*驱动器*\>: files\microsoft BizTalk\<版本\>RosettaNet\SDK\PipAutomation\3A4 快捷键。</span><span class="sxs-lookup"><span data-stu-id="8b67a-116">The [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK includes a sample [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] business policy, samplebtarnpolicy.xml, in \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\PipAutomation\3A4.</span></span> <span data-ttu-id="8b67a-117">有关详细信息，请参阅[示例 BTARN 业务策略](../../adapters-and-accelerators/accelerator-rosettanet/sample-btarn-business-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="8b67a-117">For more information, see [Sample BTARN Business Policy](../../adapters-and-accelerators/accelerator-rosettanet/sample-btarn-business-policy.md).</span></span>  
  
 <span data-ttu-id="8b67a-118">PIP3A4PrivateResponder.odx 业务流程是一个示例专用业务流程，该业务流程演示如何实现合并了业务规则的特定于合作伙伴接口流程 (PIP) 的响应方专用流程。</span><span class="sxs-lookup"><span data-stu-id="8b67a-118">PIP3A4PrivateResponder.odx orchestration is a sample private-process orchestration that demonstrates how to implement a Partner Interface Process (PIP)-specific responder private process incorporating a business rule.</span></span> <span data-ttu-id="8b67a-119">有关此示例的详细信息，请参阅[3A4 私有响应方业务流程使用业务规则](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)。</span><span class="sxs-lookup"><span data-stu-id="8b67a-119">For more information about this sample, see [3A4 Private Responder Orchestration Using a Business Rule](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md).</span></span>  
  
 <span data-ttu-id="8b67a-120">有关的词汇和策略的详细信息，请参阅 BizTalk Server 中的"开发与业务规则"主题。</span><span class="sxs-lookup"><span data-stu-id="8b67a-120">For more information about vocabularies and policies, see the "Developing with Business Rules" topic in BizTalk Server.</span></span>  
  
### <a name="to-add-a-new-vocabulary"></a><span data-ttu-id="8b67a-121">添加新词汇</span><span class="sxs-lookup"><span data-stu-id="8b67a-121">To add a new vocabulary</span></span>  
  
1.  <span data-ttu-id="8b67a-122">单击**启动**，指向**所有程序**，指向**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**业务规则编辑器**。</span><span class="sxs-lookup"><span data-stu-id="8b67a-122">Click **Start**, point to **All Programs**, point to **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **Business Rule Composer**.</span></span>  
  
2.  <span data-ttu-id="8b67a-123">如果**打开规则存储**对话框打开，请选择**BizTalk 规则引擎**数据库，你设置在当前服务器上，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="8b67a-123">If the **Open Rule Store** dialog box opens, select the **BizTalk Rule Engine** database that you set up on the current server, and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="8b67a-124">在[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]业务规则编辑器，事实数据资源管理器窗格中，右键单击**词汇**，然后单击**添加新词汇**。</span><span class="sxs-lookup"><span data-stu-id="8b67a-124">In [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Business Rule Composer, in the Facts Explorer pane, right-click **Vocabularies**, and then click **Add New Vocabulary**.</span></span>  
  
4.  <span data-ttu-id="8b67a-125">在属性窗格中 （左下角），设置**名称**属性设置为适当的词汇和然后按名称**Enter**。</span><span class="sxs-lookup"><span data-stu-id="8b67a-125">In the Property pane (lower left), set the **Name** property to the name of the appropriate vocabulary, and then press **Enter**.</span></span>  
  
5.  <span data-ttu-id="8b67a-126">展开你刚创建的词汇文件夹，右键单击**（不保存） 1.0 版**，然后单击**添加新定义**。</span><span class="sxs-lookup"><span data-stu-id="8b67a-126">Expand the vocabulary folder you just created, right-click **Version 1.0 (not saved)**, and then click **Add New Definition**.</span></span>  
  
6.  <span data-ttu-id="8b67a-127">上**词汇定义向导**页上，选择**常量值、 值的范围或设置的值**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="8b67a-127">On the **Vocabulary Definition Wizard** page, select **Constant Value, Range of Values, or Set of Values**, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="8b67a-128">上**常量值、 值的范围或设置的值**页上，在**定义名称**框中，键入的名称的相应的词汇常量值，如**允许的最大数量**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="8b67a-128">On the **Constant Value, Range of Values, or Set of Values** page, in the **Definition Name** box, type the name of the appropriate vocabulary constant value, such as **Maximum Quantity Allowed**, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="8b67a-129">上**定义的常量值**页上，在**值字段**框中，键入阈值，，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="8b67a-129">On the **Define a Constant Value** page, in the **Value Field** box, type the threshold, and then click **Finish**.</span></span>  
  
### <a name="to-define-get-and-set-elements"></a><span data-ttu-id="8b67a-130">定义 Get 和 Set 元素</span><span class="sxs-lookup"><span data-stu-id="8b67a-130">To define Get and Set elements</span></span>  
  
1.  <span data-ttu-id="8b67a-131">在业务规则编辑器，在事实数据资源管理器窗格中，在中"若要添加新的词汇过程"，创建的词汇文件夹下右键单击**（不保存） 1.0 版**，然后单击**添加新定义**.</span><span class="sxs-lookup"><span data-stu-id="8b67a-131">In Business Rule Composer, in the Facts Explorer pane, under the vocabulary folder created in the "To add a new vocabulary procedure", right-click **Version 1.0 (not saved)**, and then click **Add New Definition**.</span></span>  
  
2.  <span data-ttu-id="8b67a-132">上**词汇定义向导**页上，选择**XML 文档元素或属性**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="8b67a-132">On the **Vocabulary Definition Wizard** page, select **XML Document Element or Attribute**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="8b67a-133">上**XML 文档元素或属性**页上，在定义名称文本框中，键入的名称**获取**元素。</span><span class="sxs-lookup"><span data-stu-id="8b67a-133">On the **XML Document Element or Attribute** page, in the Definition Name text box, type a name for a **Get** element.</span></span>  
  
4.  <span data-ttu-id="8b67a-134">单击**浏览**，移到你想要使用，选择的架构文件，然后单击的架构的位置**打开**。</span><span class="sxs-lookup"><span data-stu-id="8b67a-134">Click **Browse**, move to the location of the schema that you want to use, select the schema file, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="8b67a-135">如果**选择根节点**页打开时，选择要浏览的根节点。</span><span class="sxs-lookup"><span data-stu-id="8b67a-135">If the **Select Root Node** page opens, select the root node to browse.</span></span>  
  
6.  <span data-ttu-id="8b67a-136">上**选择绑定**页上，将移动到你想要将阈值定义的字段，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="8b67a-136">On the **Select Binding** page, move to the field for which you want to define the threshold, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="8b67a-137">在**文档类型**框中，键入文档名称。</span><span class="sxs-lookup"><span data-stu-id="8b67a-137">In the **Document Type** box, type the name of the document.</span></span>  
  
8.  <span data-ttu-id="8b67a-138">在**操作类型**部分中，选择**执行"Get"操作**。</span><span class="sxs-lookup"><span data-stu-id="8b67a-138">In the **Operation Type** section, select **Perform “Get” operation**.</span></span>  
  
9. <span data-ttu-id="8b67a-139">单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="8b67a-139">Click **Finish**.</span></span>  
  
10. <span data-ttu-id="8b67a-140">重复上述步骤以定义一个或多个`Set`操作中，选择**执行"设置"操作**为**操作类型**。</span><span class="sxs-lookup"><span data-stu-id="8b67a-140">Repeat these steps to define one or more `Set` operations, select **Perform “Set” operation** for the **Operation Type**.</span></span>  
  
### <a name="to-save-and-publish-the-vocabulary"></a><span data-ttu-id="8b67a-141">保存和发布词汇</span><span class="sxs-lookup"><span data-stu-id="8b67a-141">To save and publish the vocabulary</span></span>  
  
1.  <span data-ttu-id="8b67a-142">在业务规则编辑器，在你创建的词汇文件夹下的事实数据资源管理器窗格中，右击**（不保存） 1.0 版**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="8b67a-142">In Business Rule Composer, in the Facts Explorer pane, under the vocabulary folder that you created, right-click **Version 1.0 (not saved)**, and then click **Save**.</span></span>  
  
2.  <span data-ttu-id="8b67a-143">在事实数据资源管理器窗格中的在 3A4PurchaseOrderVocabulary 文件夹，右键单击**版本 1.0**，然后选择**发布**。</span><span class="sxs-lookup"><span data-stu-id="8b67a-143">In the Facts Explorer pane, under the 3A4PurchaseOrderVocabulary folder, right-click **Version 1.0**, and then select **Publish**.</span></span>  
  
### <a name="to-add-a-new-policy-and-rules"></a><span data-ttu-id="8b67a-144">添加新策略和规则</span><span class="sxs-lookup"><span data-stu-id="8b67a-144">To add a new policy and rules</span></span>  
  
1.  <span data-ttu-id="8b67a-145">在业务规则编辑器，在策略资源管理器窗格中，右击**策略**，然后单击**添加新策略**。</span><span class="sxs-lookup"><span data-stu-id="8b67a-145">In Business Rule Composer, in the Policy Explorer pane, right-click **Policies**, and then click **Add New Policy**.</span></span>  
  
2.  <span data-ttu-id="8b67a-146">单击**策略 1**。</span><span class="sxs-lookup"><span data-stu-id="8b67a-146">Click **Policy1**.</span></span>  
  
3.  <span data-ttu-id="8b67a-147">在属性窗格中，设置**名称**到相应的策略名称的属性。</span><span class="sxs-lookup"><span data-stu-id="8b67a-147">In the Property pane, set the **Name** property to the appropriate policy name.</span></span>  
  
4.  <span data-ttu-id="8b67a-148">对于新策略，文件夹下的策略资源管理器窗格中右键单击**（不保存） 1.0 版**，然后单击**添加新规则**。</span><span class="sxs-lookup"><span data-stu-id="8b67a-148">In the Policy Explorer pane, under the folder for the new policy, right-click **Version 1.0 (not saved)**, and then click **Add New Rule**.</span></span>  
  
5.  <span data-ttu-id="8b67a-149">单击**规则 1**。</span><span class="sxs-lookup"><span data-stu-id="8b67a-149">Click **Rule1**.</span></span>  
  
6.  <span data-ttu-id="8b67a-150">在属性窗格中，设置**名称**想，规则名称的属性，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="8b67a-150">In the Property pane, set the **Name** property to the rule name you want, and then press **Enter**.</span></span>  
  
7.  <span data-ttu-id="8b67a-151">规则编辑器中，在下**如果**窗格中，右键单击**条件**，然后选择逻辑的条件，如果适用。</span><span class="sxs-lookup"><span data-stu-id="8b67a-151">In the Rule Composer, under the **IF** pane, right-click **Conditions**, and then select a logical condition, if appropriate.</span></span>  
  
8.  <span data-ttu-id="8b67a-152">在事实数据资源管理器窗格中，在**词汇**，展开**谓词**，展开**版本 1.0-发布**，选择你想，将其拖到编辑器图面，的谓词然后将它放在**条件**运算符或逻辑运算符。</span><span class="sxs-lookup"><span data-stu-id="8b67a-152">In the Facts Explorer pane, under **Vocabularies**, expand **Predicates**, expand **Version 1.0 - Published**, select the predicate you want, drag it to the composer surface, and then drop it on **Conditions** or the logical operator.</span></span>  
  
9. <span data-ttu-id="8b67a-153">在事实数据资源管理器窗格中的在词汇文件夹，展开你创建的词汇，展开**版本 1.0-发布**，选择`Get`或`Set`元素，将其拖到编辑器图面，并将其放在**argument1**。</span><span class="sxs-lookup"><span data-stu-id="8b67a-153">In the Facts Explorer pane, under the Vocabularies folder, expand the vocabulary that you created, expand **Version 1.0 - Published**, select a `Get` or `Set` element, drag it to the composer surface, and drop it on **argument1**.</span></span>  
  
10. <span data-ttu-id="8b67a-154">词汇文件夹下，选择`Get`或`Set`元素，将其拖到编辑器图面，并将其放在**argument2**。</span><span class="sxs-lookup"><span data-stu-id="8b67a-154">Under the vocabulary folder, select a `Get` or `Set` element, drag it to the composer surface and drop it on **argument2**.</span></span>  
  
11. <span data-ttu-id="8b67a-155">词汇文件夹下，选择`Set`元素，将其拖到编辑器图面，并将其放**操作**框然后窗格中。</span><span class="sxs-lookup"><span data-stu-id="8b67a-155">Under the vocabulary folder, select a `Set` element, drag it to the composer surface, and drop it in the **Actions** box in the THEN pane.</span></span>  
  
12. <span data-ttu-id="8b67a-156">如果变量关联`Set`元素中，单击该变量，根据需要，进行更改，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="8b67a-156">If a variable is associated with the `Set` element, click the variable, make changes as appropriate, and then press **Enter**.</span></span> <span data-ttu-id="8b67a-157">需要的话，对其他 `Set` 元素重复该步骤。</span><span class="sxs-lookup"><span data-stu-id="8b67a-157">If appropriate, repeat with other `Set` elements.</span></span>  
  
### <a name="to-save-publish-and-deploy-the-policy"></a><span data-ttu-id="8b67a-158">保存、发布并部署策略</span><span class="sxs-lookup"><span data-stu-id="8b67a-158">To save, publish, and deploy the policy</span></span>  
  
1.  <span data-ttu-id="8b67a-159">完成后在业务规则编辑器中的规则，定义你创建的策略文件夹下的策略资源管理器窗格中，右键单击**（不保存） 1.0 版**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="8b67a-159">When you have finished defining the rules, in Business Rule Composer, in the Policy Explorer pane, under the policy folder that you created, right-click **Version 1.0 (not saved)**, and then click **Save**.</span></span>  
  
2.  <span data-ttu-id="8b67a-160">在你创建的策略文件夹下的策略资源管理器窗格中，右键单击**版本 1.0**，然后单击**发布**。</span><span class="sxs-lookup"><span data-stu-id="8b67a-160">In the Policy Explorer pane, under the policy folder that you created, right-click **Version 1.0**, and then click **Publish**.</span></span>  
  
3.  <span data-ttu-id="8b67a-161">在你创建的策略文件夹下的策略资源管理器窗格中，右键单击**版本 1.0**，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="8b67a-161">In the Policy Explorer pane, under the policy folder that you created, right-click **Version 1.0**, and then click **Deploy**.</span></span>  
  
### <a name="to-call-the-business-rule-from-the-orchestration"></a><span data-ttu-id="8b67a-162">从业务流程调用业务规则</span><span class="sxs-lookup"><span data-stu-id="8b67a-162">To call the business rule from the orchestration</span></span>  
  
1.  <span data-ttu-id="8b67a-163">启动**Microsoft Visual Studio 2012**。</span><span class="sxs-lookup"><span data-stu-id="8b67a-163">Start **Microsoft Visual Studio 2012**.</span></span>  
  
2.  <span data-ttu-id="8b67a-164">上**文件**菜单上，指向打开，，然后单击**项目/解决方案**。</span><span class="sxs-lookup"><span data-stu-id="8b67a-164">On the **File** menu, point to Open, and then click **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="8b67a-165">找到包含你必须调用中的业务规则，然后单击的业务流程的解决方案**打开**。</span><span class="sxs-lookup"><span data-stu-id="8b67a-165">Locate the solution that contains the orchestration that you must call the business rule from, and then click **Open**.</span></span>  
  
4.  <span data-ttu-id="8b67a-166">单击**视图**，指向**其他窗口**，然后单击**业务流程视图**。</span><span class="sxs-lookup"><span data-stu-id="8b67a-166">Click **View**, point to **Other Windows**, and then click **Orchestration View**.</span></span>  
  
5.  <span data-ttu-id="8b67a-167">展开**变量**。</span><span class="sxs-lookup"><span data-stu-id="8b67a-167">Expand **Variables**.</span></span> <span data-ttu-id="8b67a-168">确保业务流程变量列表中包含分别与特定业务策略中每个参数相对应的变量，该特定业务策略是要从该业务流程调用的业务策略，</span><span class="sxs-lookup"><span data-stu-id="8b67a-168">Make sure that the orchestration variable list contains a variable that corresponds to each parameter in the business policy that you call from the orchestration.</span></span> <span data-ttu-id="8b67a-169">同时确保变量与策略参数具有相同的类型。</span><span class="sxs-lookup"><span data-stu-id="8b67a-169">Make sure that the variable has the same type as the policy parameter.</span></span> <span data-ttu-id="8b67a-170">如果列表不包含每个策略参数的业务流程变量，请右键单击**变量**，然后单击**新变量**。</span><span class="sxs-lookup"><span data-stu-id="8b67a-170">If the list does not contain an orchestration variable for each policy parameter, right-click **Variables**, and then click **New Variable**.</span></span> <span data-ttu-id="8b67a-171">在“业务流程视图”中，键入变量名，然后在“属性”窗口中输入该参数的类型。</span><span class="sxs-lookup"><span data-stu-id="8b67a-171">In Orchestration View, type a variable name, and then in the Properties window, enter the type of the parameter.</span></span>  
  
6.  <span data-ttu-id="8b67a-172">从**工具箱**，拖动**调用规则**形状变为业务流程设计图面，并将它下放**接收**形状。</span><span class="sxs-lookup"><span data-stu-id="8b67a-172">From the **Toolbox**, drag a **Call Rules** shape to the orchestration design surface, and then drop it under the **Receive** shape.</span></span>  
  
7.  <span data-ttu-id="8b67a-173">双击**调用规则**形状。</span><span class="sxs-lookup"><span data-stu-id="8b67a-173">Double-click the **Call Rules** shape.</span></span>  
  
8.  <span data-ttu-id="8b67a-174">在**选择你想要调用的业务策略**框中，从下拉列表中选择业务策略。</span><span class="sxs-lookup"><span data-stu-id="8b67a-174">In the **Select the business policy you wish to call** box, select the business policy from the drop-down list.</span></span>  
  
9. <span data-ttu-id="8b67a-175">所示，为第一个参数为**参数名称**，从下拉列表选择一个名称。</span><span class="sxs-lookup"><span data-stu-id="8b67a-175">For the first parameter shown, for **Parameter Name**, select a name from the drop-down list.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8b67a-176">BTARN 填充**策略参数**使用业务策略中的所有参数的列表。</span><span class="sxs-lookup"><span data-stu-id="8b67a-176">BTARN populates the **Policy Parameter** list with all the parameters in the business policy.</span></span> <span data-ttu-id="8b67a-177">对于列表中每个参数，BTARN 进入中的值**参数类型**从业务策略。</span><span class="sxs-lookup"><span data-stu-id="8b67a-177">For each parameter in the list, BTARN enters a value in **Parameter Type** from the business policy.</span></span> <span data-ttu-id="8b67a-178">与关联的下拉列表中**参数名称**，BTARN 进入从已与策略参数的类型相同的业务流程的变量列表的所有变量的名称。</span><span class="sxs-lookup"><span data-stu-id="8b67a-178">In the drop-down list associated with **Parameter Name**, BTARN enters the names of all variables from the orchestration's variable list that has the same type as the policy parameters.</span></span> <span data-ttu-id="8b67a-179">通过选择业务流程变量，可以将该变量与策略参数相关联。</span><span class="sxs-lookup"><span data-stu-id="8b67a-179">By selecting an orchestration variable, you are associating that variable with the policy parameter.</span></span> <span data-ttu-id="8b67a-180">你可以在“业务流程视图”中查看业务流程变量。</span><span class="sxs-lookup"><span data-stu-id="8b67a-180">You can view the orchestration variables in Orchestration View.</span></span>  
  
10. <span data-ttu-id="8b67a-181">对所有其他参数重复步骤 9。</span><span class="sxs-lookup"><span data-stu-id="8b67a-181">Repeat step 9 for all other parameters.</span></span>  
  
11. <span data-ttu-id="8b67a-182">在业务流程设计窗口中，输入所需的业务策略，包括添加与关联的处理的所有其他形状**决策**下调整**调用规则**形状。</span><span class="sxs-lookup"><span data-stu-id="8b67a-182">In the Orchestration Design window, enter all the additional shapes required for the processing associated with the business policy, including adding a **Decision** shape under the **Call Rules** shape.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8b67a-183">有关如何使用的示例**调用规则**形状中业务流程，请参阅 BTARN SDK 中包含 PIP3A4PrivateResponder.odx 业务流程。</span><span class="sxs-lookup"><span data-stu-id="8b67a-183">For an example of how to use a **Call Rules** shape in an orchestration, see the PIP3A4PrivateResponder.odx orchestration included in the BTARN SDK.</span></span> <span data-ttu-id="8b67a-184">它位于\<*驱动器*\>: files\microsoft BizTalk\<版本\>RosettaNet\SDK\PipAutomation\3A4\PR 快捷键。</span><span class="sxs-lookup"><span data-stu-id="8b67a-184">It is located at \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\PipAutomation\3A4\PR.</span></span> <span data-ttu-id="8b67a-185">有关详细信息，请参阅[3A4 私有响应方业务流程使用业务规则](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)。</span><span class="sxs-lookup"><span data-stu-id="8b67a-185">For more information, see [3A4 Private Responder Orchestration Using a Business Rule](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md).</span></span>  
  
12. <span data-ttu-id="8b67a-186">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="8b67a-186">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b67a-187">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8b67a-187">See Also</span></span>  
 <span data-ttu-id="8b67a-188">[编程指南](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md) </span><span class="sxs-lookup"><span data-stu-id="8b67a-188">[Programming Guide](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md) </span></span>  
 <span data-ttu-id="8b67a-189">[示例 BTARN 业务策略](../../adapters-and-accelerators/accelerator-rosettanet/sample-btarn-business-policy.md) </span><span class="sxs-lookup"><span data-stu-id="8b67a-189">[Sample BTARN Business Policy](../../adapters-and-accelerators/accelerator-rosettanet/sample-btarn-business-policy.md) </span></span>  
 [<span data-ttu-id="8b67a-190">使用业务规则的 3A4 专用响应方业务流程</span><span class="sxs-lookup"><span data-stu-id="8b67a-190">3A4 Private Responder Orchestration Using a Business Rule</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)