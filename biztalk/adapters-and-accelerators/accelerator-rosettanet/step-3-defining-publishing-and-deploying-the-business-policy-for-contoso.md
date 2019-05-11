---
title: 步骤 3：定义、 发布和部署 Contoso 业务策略 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- policies, deploying
- policies, publishing
- private process tutorial, creating policies
- policies, creating
ms.assetid: 529b16d8-226b-4046-a95d-64162ebd59a3
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d0b94deb38356325c81dd1b5192c726e75a43ff0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281105"
---
# <a name="step-3-defining-publishing-and-deploying-the-business-policy-for-contoso"></a><span data-ttu-id="afcec-102">步骤 3：定义、 发布和部署 Contoso 业务策略</span><span class="sxs-lookup"><span data-stu-id="afcec-102">Step 3: Defining, Publishing, and Deploying the Business Policy for Contoso</span></span>
<span data-ttu-id="afcec-103">在此步骤中，创建一个业务策略，保留一定的 Contoso 所制造用于在紧急情况下每个产品的数量。</span><span class="sxs-lookup"><span data-stu-id="afcec-103">In this step, you create a business policy that reserves a set quantity of units for each product that Contoso manufactures to be used in case of an emergency.</span></span>  
  
### <a name="to-add-a-new-policy"></a><span data-ttu-id="afcec-104">若要添加新的策略</span><span class="sxs-lookup"><span data-stu-id="afcec-104">To add a new policy</span></span>  
  
1.  <span data-ttu-id="afcec-105">在策略浏览器窗格中的业务规则编辑器中右键单击**策略**，然后单击**添加新策略**。</span><span class="sxs-lookup"><span data-stu-id="afcec-105">In the Business Rule Composer, in the Policy Explorer pane, right-click **Policies**, and then click **Add New Policy**.</span></span>  
  
2.  <span data-ttu-id="afcec-106">新策略命名**3A2PriceAvailabilityPolicy**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="afcec-106">Name the new policy **3A2PriceAvailabilityPolicy**, and then press **Enter**.</span></span>  
  
### <a name="to-add-a-policy-rule-to-enforce-the-emergency-quantity-needs"></a><span data-ttu-id="afcec-107">若要添加策略规则，以实施应急数量需求</span><span class="sxs-lookup"><span data-stu-id="afcec-107">To add a policy rule to enforce the emergency quantity needs</span></span>  
  
1.  <span data-ttu-id="afcec-108">右键单击**版本 1.0 （未保存）** 下**3A2PriceAvailabilityPolicy**，然后单击**添加新规则**。</span><span class="sxs-lookup"><span data-stu-id="afcec-108">Right-click **Version 1.0 (not saved)** under **3A2PriceAvailabilityPolicy**, and then click **Add New Rule**.</span></span>  
  
2.  <span data-ttu-id="afcec-109">命名规则**应急供应规则-数量已尽**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="afcec-109">Name the rule **Emergency Supply Rule - Quantity Exhausted**, and then press **Enter**.</span></span>  
  
3.  <span data-ttu-id="afcec-110">在业务规则编辑器中，在右窗格中，右键单击**条件**在如果窗格中，依次指向**谓词**，然后单击**小于等于**谓词。</span><span class="sxs-lookup"><span data-stu-id="afcec-110">In the Business Rule Composer, in the right pane, right-click **Conditions** under the IF pane, point to **Predicates**, and then click the **Less than equal** predicate.</span></span>  
  
4.  <span data-ttu-id="afcec-111">在事实浏览器窗格中，展开**词汇**，展开**3A2PriceAvailabilityVocabulary**，展开**版本 1.0-已发布**，选择**数量可用**，并将其拖动到`argument1`占位符上编辑器图面。</span><span class="sxs-lookup"><span data-stu-id="afcec-111">In the Facts Explorer pane, expand **Vocabularies**, expand **3A2PriceAvailabilityVocabulary**, expand **Version 1.0 - Published**, select **Quantity Available**, and drag it onto the `argument1` placeholder on the composer surface.</span></span>  
  
5.  <span data-ttu-id="afcec-112">重复步骤 4 通过拖动**紧急情况下所需的数量**拖动到`argument2`占位符。</span><span class="sxs-lookup"><span data-stu-id="afcec-112">Repeat step 4 by dragging **Emergency Quantity Needed** onto the `argument2` placeholder.</span></span>  
  
6.  <span data-ttu-id="afcec-113">选择**最终可用数量**，然后将其拖到拖**操作**那么窗格中。</span><span class="sxs-lookup"><span data-stu-id="afcec-113">Select **Final Quantity Available**, and then drag it onto **Actions** in the THEN pane.</span></span>  
  
### <a name="to-add-a-policy-to-revise-the-number-available-field-in-the-response"></a><span data-ttu-id="afcec-114">若要添加用于修改响应中的可用数量字段的策略</span><span class="sxs-lookup"><span data-stu-id="afcec-114">To add a policy to revise the Number Available field in the response</span></span>  
  
1.  <span data-ttu-id="afcec-115">右键单击**版本 1.0 （未保存）** 下**3A2PriceAvailabilityPolicy**，然后单击**添加新规则**。</span><span class="sxs-lookup"><span data-stu-id="afcec-115">Right-click **Version 1.0 (not saved)** under **3A2PriceAvailabilityPolicy**, and then click **Add New Rule**.</span></span>  
  
2.  <span data-ttu-id="afcec-116">新规则命名**应急供应规则-可用数量**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="afcec-116">Name the new rule **Emergency Supply Rule - Quantity Available**, and then press **Enter**.</span></span>  
  
3.  <span data-ttu-id="afcec-117">在业务规则编辑器中，在右窗格中，右键单击**条件**在如果窗格中，依次指向**谓词**，然后单击**大于**谓词。</span><span class="sxs-lookup"><span data-stu-id="afcec-117">In the Business Rule Composer, in the right pane, right click **Conditions** under the IF pane, point to **Predicates**, and then click the **Greater than** predicate.</span></span>  
  
4.  <span data-ttu-id="afcec-118">在事实浏览器窗格中，展开**词汇**，展开**3A2PriceAvailabilityVocabulary**，展开**版本 1.0-已发布**，选择**数量可用**，然后将其拖到拖`argument1`占位符上编辑器图面。</span><span class="sxs-lookup"><span data-stu-id="afcec-118">In the Facts Explorer pane, expand **Vocabularies**, expand **3A2PriceAvailabilityVocabulary**, expand **Version 1.0 - Published**, select **Quantity Available**, and then drag it onto the `argument1` placeholder on the composer surface.</span></span>  
  
5.  <span data-ttu-id="afcec-119">重复该步骤所需拖**紧急情况下所需的数量**拖动到`argument2`占位符。</span><span class="sxs-lookup"><span data-stu-id="afcec-119">Repeat that same step by dragging **Emergency Quantity Needed** onto the `argument2` placeholder.</span></span>  
  
6.  <span data-ttu-id="afcec-120">选择**最终可用数量**，然后将其拖到拖**操作**那么窗格中。</span><span class="sxs-lookup"><span data-stu-id="afcec-120">Select **Final Quantity Available**, and then drag it onto **Actions** in the THEN pane.</span></span>  
  
7.  <span data-ttu-id="afcec-121">在事实浏览器窗格中，展开**版本 1.0-已发布**下**函数**，并将其拖`Subtract`函数拖到**0**下一步参数**最终可用数量**那么窗格中。</span><span class="sxs-lookup"><span data-stu-id="afcec-121">In the Facts Explorer pane, expand **Version 1.0 - Published** under **Functions**, and drag the `Subtract` function onto the **0** argument next to **Final Quantity Available** in the THEN pane.</span></span>  
  
8.  <span data-ttu-id="afcec-122">拖动**Quantity Available** (下**3A2PriceAvailabilityVocabulary**) 并将其放置在`value1`那么窗格中的占位符。</span><span class="sxs-lookup"><span data-stu-id="afcec-122">Drag **Quantity Available** (under **3A2PriceAvailabilityVocabulary**) and drop it on the `value1` placeholder in the THEN pane.</span></span>  
  
9. <span data-ttu-id="afcec-123">拖动**紧急情况下所需的数量**，并将其放置在`value2`那么窗格中的占位符。</span><span class="sxs-lookup"><span data-stu-id="afcec-123">Drag **Emergency Quantity Needed**, and drop it on the `value2` placeholder in the THEN pane.</span></span>  
  
### <a name="to-save-publish-and-deploy-the-business-policy"></a><span data-ttu-id="afcec-124">若要保存、 发布和部署业务策略</span><span class="sxs-lookup"><span data-stu-id="afcec-124">To save, publish, and deploy the business policy</span></span>  
  
1.  <span data-ttu-id="afcec-125">在策略浏览器窗格中，右键单击**版本 1.0 （未保存）** 下**3A2PriceAvailabilityPolicy**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="afcec-125">In the Policy Explorer pane, right-click **Version 1.0 (not saved)** under **3A2PriceAvailabilityPolicy**, and then click **Save**.</span></span>  
  
2.  <span data-ttu-id="afcec-126">右键单击该同一个节点，然后依次**发布**。</span><span class="sxs-lookup"><span data-stu-id="afcec-126">Right-click that same node, and then click **Publish**.</span></span>  
  
3.  <span data-ttu-id="afcec-127">右键单击该同一个节点，然后依次**部署**。</span><span class="sxs-lookup"><span data-stu-id="afcec-127">Right-click that same node, and then click **Deploy**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afcec-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="afcec-128">See Also</span></span>  
 [<span data-ttu-id="afcec-129">步骤 4：创建 HeaderHelper 项目</span><span class="sxs-lookup"><span data-stu-id="afcec-129">Step 4: Creating the HeaderHelper Project</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-4-creating-the-headerhelper-project.md)