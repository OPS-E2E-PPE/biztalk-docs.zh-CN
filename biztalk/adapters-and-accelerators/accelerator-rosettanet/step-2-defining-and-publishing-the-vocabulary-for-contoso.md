---
title: 步骤 2： 定义和 contoso 发布词汇 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- vocabularies, creating
- vocabularies, publishing
- private process tutorial, creating vocabularies
ms.assetid: e23880c0-772c-48c6-a6b5-32eb951527c8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15937a1235cc1776be38fe2b0e5529c19d3f6fd5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22211085"
---
# <a name="step-2-defining-and-publishing-the-vocabulary-for-contoso"></a><span data-ttu-id="f25dd-102">步骤 2： 定义和 contoso 发布词汇</span><span class="sxs-lookup"><span data-stu-id="f25dd-102">Step 2: Defining and Publishing the Vocabulary for Contoso</span></span>
<span data-ttu-id="f25dd-103">在此方案中，Contoso 将实现一个业务策略，该策略确保在出现紧急情况时始终有可用库存。</span><span class="sxs-lookup"><span data-stu-id="f25dd-103">In this scenario, Contoso implements a business policy that makes sure that inventory is always on hand if an emergency occurs.</span></span> <span data-ttu-id="f25dd-104">您将使用 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 中的业务规则编辑器来创建业务策略。</span><span class="sxs-lookup"><span data-stu-id="f25dd-104">You create business policies using the Business Rule Composer in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="f25dd-105">在此步骤中，您将创建定义业务策略时所使用的词汇。</span><span class="sxs-lookup"><span data-stu-id="f25dd-105">In this step, you create the vocabulary to use when you define the business policy.</span></span>  
  
### <a name="to-add-a-new-vocabulary"></a><span data-ttu-id="f25dd-106">添加新词汇</span><span class="sxs-lookup"><span data-stu-id="f25dd-106">To add a new vocabulary</span></span>  
  
1.  <span data-ttu-id="f25dd-107">单击**启动**，指向**所有程序**，指向**Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**业务规则编辑器**。</span><span class="sxs-lookup"><span data-stu-id="f25dd-107">Click **Start**, point to **All Programs**, point to **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **Business Rule Composer**.</span></span>  
  
2.  <span data-ttu-id="f25dd-108">在打开规则存储对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="f25dd-108">In the Open Rule Store dialog box, click **OK**.</span></span>  
  
3.  <span data-ttu-id="f25dd-109">在事实数据资源管理器窗格中，在**词汇**选项卡上，右键单击**词汇**，然后单击**添加新词汇**。</span><span class="sxs-lookup"><span data-stu-id="f25dd-109">In the Facts Explorer pane, on the **Vocabularies** tab, right-click **Vocabularies**, and then click **Add New Vocabulary**.</span></span>  
  
4.  <span data-ttu-id="f25dd-110">命名词汇**3A2PriceAvailabilityVocabulary**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="f25dd-110">Name the vocabulary **3A2PriceAvailabilityVocabulary**, and then press **Enter**.</span></span>  
  
### <a name="to-define-a-constant-vocabulary-value"></a><span data-ttu-id="f25dd-111">定义词汇常数值</span><span class="sxs-lookup"><span data-stu-id="f25dd-111">To define a constant vocabulary value</span></span>  
  
1.  <span data-ttu-id="f25dd-112">在业务规则编辑器，单击**3A2PriceAvailabilityVocabulary**，右键单击 **（不保存） 1.0 版**，然后单击**添加新定义**。</span><span class="sxs-lookup"><span data-stu-id="f25dd-112">In Business Rule Composer, click **3A2PriceAvailabilityVocabulary**, right-click **Version 1.0(not saved)**, and then click **Add New Definition**.</span></span>  
  
2.  <span data-ttu-id="f25dd-113">上**词汇定义向导**页上，选择**常量值、 值的范围或设置的值**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="f25dd-113">On the **Vocabulary Definition Wizard** page, select **Constant Value, Range of Values, or Set of Values**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="f25dd-114">上**常量值、 值的范围或设置的值**页上，在**定义名称**框中，键入**紧急数量需要**，然后单击**下一步**.</span><span class="sxs-lookup"><span data-stu-id="f25dd-114">On the **Constant Value, Range of Values, or Set of Values** page, in the **Definition name** box, type **Emergency Quantity Needed**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="f25dd-115">上**定义的常量值**页上，在**值**框中，键入**800**，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="f25dd-115">On the **Define a Constant Value** page, in the **Value** box, type **800**, and then click **Finish**.</span></span>  
  
### <a name="to-define-an-xml-document-get-element"></a><span data-ttu-id="f25dd-116">定义 XML 文档的“Get”元素</span><span class="sxs-lookup"><span data-stu-id="f25dd-116">To define an XML document 'Get' element</span></span>  
  
1.  <span data-ttu-id="f25dd-117">在业务规则编辑器，在事实数据资源管理器窗格中，右键单击 **（不保存） 1.0 版**下**3A2PriceAvailabilityVocabulary**，然后单击**添加新定义**.</span><span class="sxs-lookup"><span data-stu-id="f25dd-117">In Business Rule Composer, in the Facts Explorer pane, right-click **Version 1.0 (not saved)** under **3A2PriceAvailabilityVocabulary**, and then click **Add New Definition**.</span></span>  
  
2.  <span data-ttu-id="f25dd-118">上**VocabularyDefinition 向导**页上，选择**XML 文档元素或属性**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="f25dd-118">On the **VocabularyDefinition Wizard** page, select **XML Document Element or Attribute**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="f25dd-119">上**XML 文档元素或属性**页上，在**定义名称**框中，键入**数量可用**。</span><span class="sxs-lookup"><span data-stu-id="f25dd-119">On the **XML Document Element or Attribute** page, in the **Definition Name** box, type **Quantity Available**.</span></span>  
  
4.  <span data-ttu-id="f25dd-120">单击**浏览**(旁边**架构**字段)，将移到**ContosoPriceAndAvailability**解决方案文件夹，选择中的项目**ContosoPriceAndAvailability.xsd**架构，，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="f25dd-120">Click **Browse** (next to the **Schema** field), move to the **ContosoPriceAndAvailability** project in your solution folder, select the **ContosoPriceAndAvailability.xsd** schema, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="f25dd-121">在选择绑定对话框中，展开**rootPriceResponse**，展开**产品**，选择**NumberAvailable**元素，，然后单击**确定**.</span><span class="sxs-lookup"><span data-stu-id="f25dd-121">In the Select Binding dialog box, expand **rootPriceResponse**, expand **Products**, select the **NumberAvailable** element, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="f25dd-122">上**XML 文档元素或属性**页上，在**文档类型**框中，确保值**ContosoPriceAndAvailability.ContosoPriceSchema.rootPriceResponse**.</span><span class="sxs-lookup"><span data-stu-id="f25dd-122">On the **XML Document Element or Attribute** page, in the **Document Type** box, ensure that the value is **ContosoPriceAndAvailability.ContosoPriceSchema.rootPriceResponse**.</span></span>  
  
7.  <span data-ttu-id="f25dd-123">在**选择操作**部分中，选择**执行"Get"操作**，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="f25dd-123">In the **Select operation** section, select **Perform "Get" Operation**, and then click **Finish**.</span></span>  
  
### <a name="to-define-an-xml-document-set-element"></a><span data-ttu-id="f25dd-124">定义 XML 文档的“Set”元素</span><span class="sxs-lookup"><span data-stu-id="f25dd-124">To define an XML document 'Set' element</span></span>  
  
1.  <span data-ttu-id="f25dd-125">在业务规则编辑器，在事实数据资源管理器窗格中，右键单击 **（不保存） 1.0 版**下**3A2PriceAvailabilityVocabulary**，然后单击**添加新定义**.</span><span class="sxs-lookup"><span data-stu-id="f25dd-125">In Business Rule Composer, in the Facts Explorer pane, right-click **Version 1.0 (not saved)** under **3A2PriceAvailabilityVocabulary**, and then click **Add New Definition**.</span></span>  
  
2.  <span data-ttu-id="f25dd-126">上**VocabularyDefinition 向导**页上，选择**XML 文档元素或属性**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="f25dd-126">On the **VocabularyDefinition Wizard** page, select **XML Document Element or Attribute**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="f25dd-127">上**XML 文档元素或属性**页上，在**定义名称**框中，键入**最终数量可用**。</span><span class="sxs-lookup"><span data-stu-id="f25dd-127">On the **XML Document Element or Attribute** page, in the **Definition Name** box, type **Final Quantity Available**.</span></span>  
  
4.  <span data-ttu-id="f25dd-128">单击**浏览**(旁边**架构**字段)，将移到**ContosoPriceAndAvailability**解决方案文件夹，选择中的项目**ContosoPriceAndAvailability.xsd**架构，，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="f25dd-128">Click **Browse** (next to the **Schema** field), move to the **ContosoPriceAndAvailability** project in your solution folder, select the **ContosoPriceAndAvailability.xsd** schema, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="f25dd-129">在**选择绑定**对话框框中，展开**rootPriceResponse**，展开**产品**，然后选择**NumberAvailable**元素。</span><span class="sxs-lookup"><span data-stu-id="f25dd-129">In the **Select Binding** dialog box, expand **rootPriceResponse**, expand **Products**, and then select the **NumberAvailable** element.</span></span> <span data-ttu-id="f25dd-130">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="f25dd-130">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="f25dd-131">上**XML 文档元素或属性**页上，在**文档类型**框中，确保值**ContosoPriceAndAvailability.ContosoPriceSchema.rootPriceResponse**.</span><span class="sxs-lookup"><span data-stu-id="f25dd-131">On the **XML Document Element or Attribute** page, in the **Document Type** box, ensure that the value is **ContosoPriceAndAvailability.ContosoPriceSchema.rootPriceResponse**.</span></span>  
  
7.  <span data-ttu-id="f25dd-132">在**选择操作**部分中，选择**执行"设置"操作**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="f25dd-132">In the **Select operation** section, select **Perform "Set" Operation**, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="f25dd-133">在**指定的显示名称**页上，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="f25dd-133">In the **Specify the Display Name** page, click **Finish**.</span></span>  
  
### <a name="to-save-and-publish-the-vocabulary"></a><span data-ttu-id="f25dd-134">保存和发布词汇</span><span class="sxs-lookup"><span data-stu-id="f25dd-134">To save and publish the vocabulary</span></span>  
  
1.  <span data-ttu-id="f25dd-135">在业务规则编辑器，在事实数据资源管理器窗格中，右键单击 **（不保存） 1.0 版**下**3A2PriceAvailabilityVocabulary**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="f25dd-135">In Business Rule Composer, in the Facts Explorer pane, right-click **Version 1.0 (not saved)** under **3A2PriceAvailabilityVocabulary**, and then click **Save**.</span></span>  
  
2.  <span data-ttu-id="f25dd-136">右键单击该相同**版本 1.0**节点，然后单击**发布**。</span><span class="sxs-lookup"><span data-stu-id="f25dd-136">Right-click that same **Version 1.0** node and then click **Publish**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f25dd-137">保持业务规则编辑器为打开状态，以执行教程中的下一个步骤。</span><span class="sxs-lookup"><span data-stu-id="f25dd-137">Leave the Business Rule Composer open for the next step in the tutorial.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f25dd-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f25dd-138">See Also</span></span>  
 [<span data-ttu-id="f25dd-139">步骤 3： 定义、 发布和部署为 Contoso 的业务策略</span><span class="sxs-lookup"><span data-stu-id="f25dd-139">Step 3: Defining, Publishing, and Deploying the Business Policy for Contoso</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-defining-publishing-and-deploying-the-business-policy-for-contoso.md)