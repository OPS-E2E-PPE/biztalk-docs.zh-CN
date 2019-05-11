---
title: 定义专用业务流程的业务规则 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae4657e82c99630cc5d9a31915246b2bf3ebc02c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283747"
---
# <a name="defining-a-business-rule-for-a-private-process-orchestration"></a><span data-ttu-id="9bf1f-102">定义专用业务流程的业务规则</span><span class="sxs-lookup"><span data-stu-id="9bf1f-102">Defining a Business Rule for a Private Process Orchestration</span></span>
<span data-ttu-id="9bf1f-103">在确认专用流程中，可以定义使用的业务规则。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-103">You can define a business rule for use in an acknowledgement private process.</span></span> <span data-ttu-id="9bf1f-104">这样可以动态修改业务规则，而无需停止专用业务流程。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-104">This lets you to modify the business rule dynamically without stopping the private-process orchestration.</span></span> <span data-ttu-id="9bf1f-105">此过程使用 Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]业务规则引擎。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-105">This process uses the Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Business Rule Engine.</span></span> <span data-ttu-id="9bf1f-106">此过程涉及以下步骤：</span><span class="sxs-lookup"><span data-stu-id="9bf1f-106">This process involves the following steps:</span></span>  
  
1. <span data-ttu-id="9bf1f-107">添加新词汇。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-107">Adding a new vocabulary.</span></span> <span data-ttu-id="9bf1f-108">这包括定义至少一个词汇常数值。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-108">This involves defining at least one vocabulary constant value.</span></span> <span data-ttu-id="9bf1f-109">这将设置业务规则阈值。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-109">This sets a business-rule threshold.</span></span> <span data-ttu-id="9bf1f-110">它还包括定义 XML 文档`Get`和`Set`元素。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-110">It also involves defining XML document `Get` and `Set` elements.</span></span> <span data-ttu-id="9bf1f-111">这将确定如何 Microsoft[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]使用该阈值。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-111">This establishes how Microsoft [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] uses the threshold.</span></span>  
  
2. <span data-ttu-id="9bf1f-112">添加新策略。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-112">Adding a new policy.</span></span> <span data-ttu-id="9bf1f-113">这涉及到创建策略、 创建一组规则，，然后保存、 发布和部署策略。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-113">This involves creating a policy, creating a set of rules, and then saving, publishing, and deploying the policy.</span></span>  
  
3. <span data-ttu-id="9bf1f-114">从专用业务流程调用业务规则。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-114">Calling the business rule from the private-process orchestration.</span></span> <span data-ttu-id="9bf1f-115">这涉及到添加**调用规则**向业务流程的形状。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-115">This involves adding a **Call Rules** shape to the orchestration.</span></span>  
  
   <span data-ttu-id="9bf1f-116">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK 包括了示例[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]业务策略 samplebtarnpolicy.xml，它在\<*驱动器*\>: \Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\PipAutomation\3A4。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-116">The [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK includes a sample [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] business policy, samplebtarnpolicy.xml, in \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\PipAutomation\3A4.</span></span> <span data-ttu-id="9bf1f-117">有关详细信息，请参阅[BTARN 业务策略示例](../../adapters-and-accelerators/accelerator-rosettanet/sample-btarn-business-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-117">For more information, see [Sample BTARN Business Policy](../../adapters-and-accelerators/accelerator-rosettanet/sample-btarn-business-policy.md).</span></span>  
  
   <span data-ttu-id="9bf1f-118">PIP3A4PrivateResponder.odx 业务流程是用于演示如何实现合作伙伴接口流程 (PIP) 的示例专用业务流程业务流程的特定响应方专用流程合并了业务规则。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-118">PIP3A4PrivateResponder.odx orchestration is a sample private-process orchestration that demonstrates how to implement a Partner Interface Process (PIP)-specific responder private process incorporating a business rule.</span></span> <span data-ttu-id="9bf1f-119">有关此示例的详细信息，请参阅[3A4 专用响应方业务流程使用业务规则](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-119">For more information about this sample, see [3A4 Private Responder Orchestration Using a Business Rule](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md).</span></span>  
  
   <span data-ttu-id="9bf1f-120">有关词汇和策略的详细信息，请参阅 BizTalk Server 中的"开发与业务规则"主题。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-120">For more information about vocabularies and policies, see the "Developing with Business Rules" topic in BizTalk Server.</span></span>  
  
### <a name="to-add-a-new-vocabulary"></a><span data-ttu-id="9bf1f-121">若要添加新词汇</span><span class="sxs-lookup"><span data-stu-id="9bf1f-121">To add a new vocabulary</span></span>  
  
1. <span data-ttu-id="9bf1f-122">单击**启动**，依次指向**所有程序**，指向**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**业务规则编辑器**。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-122">Click **Start**, point to **All Programs**, point to **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **Business Rule Composer**.</span></span>  
  
2. <span data-ttu-id="9bf1f-123">如果**打开规则存储**打开对话框中，选择**BizTalk 规则引擎**数据库，您在当前服务器上设置，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-123">If the **Open Rule Store** dialog box opens, select the **BizTalk Rule Engine** database that you set up on the current server, and then click **OK**.</span></span>  
  
3. <span data-ttu-id="9bf1f-124">在 Microsoft 业务规则编辑器，在事实浏览器窗格中，右键单击**词汇**，然后单击**添加新词汇**。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-124">In Microsoft Business Rule Composer, in the Facts Explorer pane, right-click **Vocabularies**, and then click **Add New Vocabulary**.</span></span>  
  
4. <span data-ttu-id="9bf1f-125">在左下方的属性窗格中，将**名称**属性设置为相应词汇，再按名称**Enter**。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-125">In the Property pane (lower left), set the **Name** property to the name of the appropriate vocabulary, and then press **Enter**.</span></span>  
  
5. <span data-ttu-id="9bf1f-126">展开刚创建的词汇文件夹，右键单击**版本 1.0 （未保存）**，然后单击**添加新定义**。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-126">Expand the vocabulary folder you just created, right-click **Version 1.0 (not saved)**, and then click **Add New Definition**.</span></span>  
  
6. <span data-ttu-id="9bf1f-127">上**词汇定义向导**页上，选择**常数值、 值的范围或值的集合**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-127">On the **Vocabulary Definition Wizard** page, select **Constant Value, Range of Values, or Set of Values**, and then click **Next**.</span></span>  
  
7. <span data-ttu-id="9bf1f-128">上**常数值、 值的范围或值的集合**页上，在**定义名称**框中，键入相应词汇常数值的名称类似于**允许的最大数量**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-128">On the **Constant Value, Range of Values, or Set of Values** page, in the **Definition Name** box, type the name of the appropriate vocabulary constant value, such as **Maximum Quantity Allowed**, and then click **Next**.</span></span>  
  
8. <span data-ttu-id="9bf1f-129">上**定义常数值**页上，在**值字段**框中，键入阈值，，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-129">On the **Define a Constant Value** page, in the **Value Field** box, type the threshold, and then click **Finish**.</span></span>  
  
### <a name="to-define-get-and-set-elements"></a><span data-ttu-id="9bf1f-130">若要定义 Get 和 Set 元素</span><span class="sxs-lookup"><span data-stu-id="9bf1f-130">To define Get and Set elements</span></span>  
  
1.  <span data-ttu-id="9bf1f-131">在业务规则编辑器中，在事实浏览器窗格中，在"添加新词汇过程"，创建的词汇文件夹下右键单击**版本 1.0 （未保存）**，然后单击**添加新定义**.</span><span class="sxs-lookup"><span data-stu-id="9bf1f-131">In Business Rule Composer, in the Facts Explorer pane, under the vocabulary folder created in the "To add a new vocabulary procedure", right-click **Version 1.0 (not saved)**, and then click **Add New Definition**.</span></span>  
  
2.  <span data-ttu-id="9bf1f-132">上**词汇定义向导**页上，选择**XML 文档元素或属性**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-132">On the **Vocabulary Definition Wizard** page, select **XML Document Element or Attribute**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="9bf1f-133">上**XML 文档元素或属性**页上，在定义名称文本框中，键入的名称**获取**元素。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-133">On the **XML Document Element or Attribute** page, in the Definition Name text box, type a name for a **Get** element.</span></span>  
  
4.  <span data-ttu-id="9bf1f-134">单击**浏览**，转到你想要使用，选择架构文件，然后单击该架构的位置**打开**。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-134">Click **Browse**, move to the location of the schema that you want to use, select the schema file, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="9bf1f-135">如果**选择根节点**页打开时，选择要浏览的根节点。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-135">If the **Select Root Node** page opens, select the root node to browse.</span></span>  
  
6.  <span data-ttu-id="9bf1f-136">上**选择绑定**页上，将移动到你想要定义的阈值，该字段，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-136">On the **Select Binding** page, move to the field for which you want to define the threshold, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="9bf1f-137">在中**文档类型**框中，键入文档的名称。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-137">In the **Document Type** box, type the name of the document.</span></span>  
  
8.  <span data-ttu-id="9bf1f-138">在中**操作类型**部分中，选择**执行"Get"操作**。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-138">In the **Operation Type** section, select **Perform “Get” operation**.</span></span>  
  
9. <span data-ttu-id="9bf1f-139">单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-139">Click **Finish**.</span></span>  
  
10. <span data-ttu-id="9bf1f-140">重复上述步骤，定义一个或多个`Set`操作中，选择**执行"Set"操作**有关**操作类型**。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-140">Repeat these steps to define one or more `Set` operations, select **Perform “Set” operation** for the **Operation Type**.</span></span>  
  
### <a name="to-save-and-publish-the-vocabulary"></a><span data-ttu-id="9bf1f-141">若要保存并发布词汇</span><span class="sxs-lookup"><span data-stu-id="9bf1f-141">To save and publish the vocabulary</span></span>  
  
1.  <span data-ttu-id="9bf1f-142">在业务规则编辑器中，你创建的词汇文件夹下的事实浏览器窗格中右键单击**版本 1.0 （未保存）**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-142">In Business Rule Composer, in the Facts Explorer pane, under the vocabulary folder that you created, right-click **Version 1.0 (not saved)**, and then click **Save**.</span></span>  
  
2.  <span data-ttu-id="9bf1f-143">在下 3A4PurchaseOrderVocabulary 文件夹下的事实浏览器窗格中右键单击**版本 1.0**，然后选择**发布**。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-143">In the Facts Explorer pane, under the 3A4PurchaseOrderVocabulary folder, right-click **Version 1.0**, and then select **Publish**.</span></span>  
  
### <a name="to-add-a-new-policy-and-rules"></a><span data-ttu-id="9bf1f-144">若要添加新策略和规则</span><span class="sxs-lookup"><span data-stu-id="9bf1f-144">To add a new policy and rules</span></span>  
  
1.  <span data-ttu-id="9bf1f-145">在业务规则编辑器中，在策略浏览器窗格中，右键单击**策略**，然后单击**添加新策略**。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-145">In Business Rule Composer, in the Policy Explorer pane, right-click **Policies**, and then click **Add New Policy**.</span></span>  
  
2.  <span data-ttu-id="9bf1f-146">单击**Policy1**。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-146">Click **Policy1**.</span></span>  
  
3.  <span data-ttu-id="9bf1f-147">在属性窗格中，将**名称**属性设置为相应的策略名称。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-147">In the Property pane, set the **Name** property to the appropriate policy name.</span></span>  
  
4.  <span data-ttu-id="9bf1f-148">为新策略文件夹下的策略浏览器窗格中右键单击**版本 1.0 （未保存）**，然后单击**添加新规则**。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-148">In the Policy Explorer pane, under the folder for the new policy, right-click **Version 1.0 (not saved)**, and then click **Add New Rule**.</span></span>  
  
5.  <span data-ttu-id="9bf1f-149">单击**Rule1**。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-149">Click **Rule1**.</span></span>  
  
6.  <span data-ttu-id="9bf1f-150">在属性窗格中，将**名称**想，规则名称的属性，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-150">In the Property pane, set the **Name** property to the rule name you want, and then press **Enter**.</span></span>  
  
7.  <span data-ttu-id="9bf1f-151">在规则编辑器下**IF**窗格中，右键单击**条件**，然后选择逻辑条件，如果适用。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-151">In the Rule Composer, under the **IF** pane, right-click **Conditions**, and then select a logical condition, if appropriate.</span></span>  
  
8.  <span data-ttu-id="9bf1f-152">在事实浏览器窗格下**词汇**，展开**谓词**，展开**版本 1.0-已发布**，选择你想将其拖到编辑器图面上，的谓词并将它放在**条件**或逻辑运算符。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-152">In the Facts Explorer pane, under **Vocabularies**, expand **Predicates**, expand **Version 1.0 - Published**, select the predicate you want, drag it to the composer surface, and then drop it on **Conditions** or the logical operator.</span></span>  
  
9. <span data-ttu-id="9bf1f-153">在事实浏览器窗格中的词汇文件夹下，展开你创建的词汇，展开**版本 1.0-已发布**，选择`Get`或`Set`元素中，将其拖到编辑器图面上，并将其放在**argument1**。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-153">In the Facts Explorer pane, under the Vocabularies folder, expand the vocabulary that you created, expand **Version 1.0 - Published**, select a `Get` or `Set` element, drag it to the composer surface, and drop it on **argument1**.</span></span>  
  
10. <span data-ttu-id="9bf1f-154">在词汇文件夹下选择`Get`或`Set`元素中，将其拖到编辑器图面上，并将其放在**argument2**。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-154">Under the vocabulary folder, select a `Get` or `Set` element, drag it to the composer surface and drop it on **argument2**.</span></span>  
  
11. <span data-ttu-id="9bf1f-155">在词汇文件夹下选择`Set`元素中，将其拖到编辑器图面上，并将其放**操作**框那么窗格中。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-155">Under the vocabulary folder, select a `Set` element, drag it to the composer surface, and drop it in the **Actions** box in the THEN pane.</span></span>  
  
12. <span data-ttu-id="9bf1f-156">如果变量与相关联`Set`元素中，单击该变量，根据需要，进行更改，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-156">If a variable is associated with the `Set` element, click the variable, make changes as appropriate, and then press **Enter**.</span></span> <span data-ttu-id="9bf1f-157">如果需要，重复与其他`Set`元素。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-157">If appropriate, repeat with other `Set` elements.</span></span>  
  
### <a name="to-save-publish-and-deploy-the-policy"></a><span data-ttu-id="9bf1f-158">若要保存、 发布和部署策略</span><span class="sxs-lookup"><span data-stu-id="9bf1f-158">To save, publish, and deploy the policy</span></span>  
  
1.  <span data-ttu-id="9bf1f-159">当您已完成定义规则，在业务规则编辑器，您创建的策略文件夹下的策略浏览器窗格中，右键单击**版本 1.0 （未保存）**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-159">When you have finished defining the rules, in Business Rule Composer, in the Policy Explorer pane, under the policy folder that you created, right-click **Version 1.0 (not saved)**, and then click **Save**.</span></span>  
  
2.  <span data-ttu-id="9bf1f-160">在你创建的策略文件夹下的策略浏览器窗格中右键单击**版本 1.0**，然后单击**发布**。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-160">In the Policy Explorer pane, under the policy folder that you created, right-click **Version 1.0**, and then click **Publish**.</span></span>  
  
3.  <span data-ttu-id="9bf1f-161">在你创建的策略文件夹下的策略浏览器窗格中右键单击**版本 1.0**，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-161">In the Policy Explorer pane, under the policy folder that you created, right-click **Version 1.0**, and then click **Deploy**.</span></span>  
  
### <a name="to-call-the-business-rule-from-the-orchestration"></a><span data-ttu-id="9bf1f-162">若要从业务流程调用业务规则</span><span class="sxs-lookup"><span data-stu-id="9bf1f-162">To call the business rule from the orchestration</span></span>  
  
1.  <span data-ttu-id="9bf1f-163">启动**Microsoft Visual Studio 2012**。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-163">Start **Microsoft Visual Studio 2012**.</span></span>  
  
2.  <span data-ttu-id="9bf1f-164">上**文件**菜单上，为打开，指向，然后单击**项目/解决方案**。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-164">On the **File** menu, point to Open, and then click **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="9bf1f-165">找到包含您必须调用，从业务规则，然后单击的业务流程的解决方案**打开**。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-165">Locate the solution that contains the orchestration that you must call the business rule from, and then click **Open**.</span></span>  
  
4.  <span data-ttu-id="9bf1f-166">单击**视图**，依次指向**其他 Windows**，然后单击**业务流程视图**。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-166">Click **View**, point to **Other Windows**, and then click **Orchestration View**.</span></span>  
  
5.  <span data-ttu-id="9bf1f-167">展开**变量**。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-167">Expand **Variables**.</span></span> <span data-ttu-id="9bf1f-168">请确保业务流程变量列表包含对应于从业务流程调用的业务策略中的每个参数的变量。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-168">Make sure that the orchestration variable list contains a variable that corresponds to each parameter in the business policy that you call from the orchestration.</span></span> <span data-ttu-id="9bf1f-169">请确保该变量具有与策略参数类型相同。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-169">Make sure that the variable has the same type as the policy parameter.</span></span> <span data-ttu-id="9bf1f-170">如果列表不包含的业务流程变量的每个策略参数，请右击**变量**，然后单击**新变量**。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-170">If the list does not contain an orchestration variable for each policy parameter, right-click **Variables**, and then click **New Variable**.</span></span> <span data-ttu-id="9bf1f-171">在业务流程视图中，键入变量名称，然后在属性窗口中，输入参数的类型。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-171">In Orchestration View, type a variable name, and then in the Properties window, enter the type of the parameter.</span></span>  
  
6.  <span data-ttu-id="9bf1f-172">从**工具箱**，拖动**调用规则**形状变为业务流程设计图面上，并将它下放**接收**形状。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-172">From the **Toolbox**, drag a **Call Rules** shape to the orchestration design surface, and then drop it under the **Receive** shape.</span></span>  
  
7.  <span data-ttu-id="9bf1f-173">双击**调用规则**形状。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-173">Double-click the **Call Rules** shape.</span></span>  
  
8.  <span data-ttu-id="9bf1f-174">在中**选择你想要调用的业务策略**框中，从下拉列表中选择的业务策略。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-174">In the **Select the business policy you wish to call** box, select the business policy from the drop-down list.</span></span>  
  
9. <span data-ttu-id="9bf1f-175">第一个参数所示，对于**参数名称**，从下拉列表中选择一个名称。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-175">For the first parameter shown, for **Parameter Name**, select a name from the drop-down list.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9bf1f-176">BTARN 将填充**策略参数**使用业务策略中的所有参数的列表。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-176">BTARN populates the **Policy Parameter** list with all the parameters in the business policy.</span></span> <span data-ttu-id="9bf1f-177">对于列表中每个参数，BTARN 会输入中的值**参数类型**来自业务策略。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-177">For each parameter in the list, BTARN enters a value in **Parameter Type** from the business policy.</span></span> <span data-ttu-id="9bf1f-178">在下拉列表中与相关联**参数名称**，BTARN 会输入从业务流程的变量列表，其中包含与策略参数类型相同的所有变量的名称。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-178">In the drop-down list associated with **Parameter Name**, BTARN enters the names of all variables from the orchestration's variable list that has the same type as the policy parameters.</span></span> <span data-ttu-id="9bf1f-179">通过选择业务流程变量，会将该变量与策略参数相关联。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-179">By selecting an orchestration variable, you are associating that variable with the policy parameter.</span></span> <span data-ttu-id="9bf1f-180">您可以在业务流程视图中查看业务流程变量。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-180">You can view the orchestration variables in Orchestration View.</span></span>  
  
10. <span data-ttu-id="9bf1f-181">对于所有其他参数重复步骤 9。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-181">Repeat step 9 for all other parameters.</span></span>  
  
11. <span data-ttu-id="9bf1f-182">在业务流程设计窗口中，输入所需的业务策略，包括添加与关联的处理的所有其他形状**决策**形状下**调用规则**形状。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-182">In the Orchestration Design window, enter all the additional shapes required for the processing associated with the business policy, including adding a **Decision** shape under the **Call Rules** shape.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9bf1f-183">有关如何使用的示例**调用规则**形状在业务流程中，请参阅 BTARN SDK 中包含的 PIP3A4PrivateResponder.odx 业务流程。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-183">For an example of how to use a **Call Rules** shape in an orchestration, see the PIP3A4PrivateResponder.odx orchestration included in the BTARN SDK.</span></span> <span data-ttu-id="9bf1f-184">它位于\<*驱动器*\>: \Program Files\Microsoft BizTalk\<版本\>Accelerator for rosettanet\sdk\pipautomation\3a4\pr。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-184">It is located at \<*drive*\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\PipAutomation\3A4\PR.</span></span> <span data-ttu-id="9bf1f-185">有关详细信息，请参阅[3A4 专用响应方业务流程使用业务规则](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-185">For more information, see [3A4 Private Responder Orchestration Using a Business Rule](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md).</span></span>  
  
12. <span data-ttu-id="9bf1f-186">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="9bf1f-186">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bf1f-187">请参阅</span><span class="sxs-lookup"><span data-stu-id="9bf1f-187">See Also</span></span>  
 <span data-ttu-id="9bf1f-188">[编程指南](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md) </span><span class="sxs-lookup"><span data-stu-id="9bf1f-188">[Programming Guide](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md) </span></span>  
 <span data-ttu-id="9bf1f-189">[BTARN 业务策略示例](../../adapters-and-accelerators/accelerator-rosettanet/sample-btarn-business-policy.md) </span><span class="sxs-lookup"><span data-stu-id="9bf1f-189">[Sample BTARN Business Policy](../../adapters-and-accelerators/accelerator-rosettanet/sample-btarn-business-policy.md) </span></span>  
 [<span data-ttu-id="9bf1f-190">使用业务规则的 3A4 专用响应方业务流程</span><span class="sxs-lookup"><span data-stu-id="9bf1f-190">3A4 Private Responder Orchestration Using a Business Rule</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)