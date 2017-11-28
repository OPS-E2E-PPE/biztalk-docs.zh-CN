---
title: "其他故障排除 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: troubleshooting
ms.assetid: 6ebc1867-b5d3-46de-b3bd-69e570ed2b2c
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 765b32895fa76c0c77b740b76e2e6a03f0571351
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="miscellaneous-troubleshooting"></a><span data-ttu-id="f326d-102">其他故障排除</span><span class="sxs-lookup"><span data-stu-id="f326d-102">Miscellaneous Troubleshooting</span></span>
## <a name="leading-zeroes-validation-is-not-performed-for-fields-that-use-the-checkleadingzeroesinelement-method-to-validate-a-field-in-the-message-validation-policy"></a><span data-ttu-id="f326d-103">前导零的 CheckLeadingZeroesInElement 方法用于验证消息验证策略中的字段的字段不执行验证。</span><span class="sxs-lookup"><span data-stu-id="f326d-103">Leading zeroes validation is not performed for fields that use the CheckLeadingZeroesInElement method to validate a field in the message Validation Policy.</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="f326d-104">故障现象</span><span class="sxs-lookup"><span data-stu-id="f326d-104">Symptom</span></span>  
 <span data-ttu-id="f326d-105">如果包含一个字段中的前导零提交一条消息，即使前导零不允许为该字段并验证策略包括执行此验证的字段的规则，则不返回任何 BRE 验证错误。</span><span class="sxs-lookup"><span data-stu-id="f326d-105">No BRE validation error is returned if a message is submitted with leading zeroes in a field, even though leading zeroes are not permitted for the field and the validation policy includes a rule for the field that performs this validation.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="f326d-106">可能的原因</span><span class="sxs-lookup"><span data-stu-id="f326d-106">Possible Cause</span></span>  
 <span data-ttu-id="f326d-107">**CheckLeadingZeroInElement**方法包含在消息类型的验证策略中的业务规则。</span><span class="sxs-lookup"><span data-stu-id="f326d-107">The **CheckLeadingZeroInElement** method is included in a business rule in the validation policy for the message type.</span></span> <span data-ttu-id="f326d-108">不推荐使用此方法。</span><span class="sxs-lookup"><span data-stu-id="f326d-108">This method is deprecated.</span></span> <span data-ttu-id="f326d-109">函数调用的目的是导致验证失败，如果没有前导零的函数调用中提供的元素。</span><span class="sxs-lookup"><span data-stu-id="f326d-109">The purpose of the function call is to cause validation to fail if there is a leading zero in the element provided in the function call.</span></span> <span data-ttu-id="f326d-110">但是，此方法不会导致验证失败，即使没有前导零的字段中。</span><span class="sxs-lookup"><span data-stu-id="f326d-110">However, this method does not cause validation to fail, even if there is a leading zero in the field.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="f326d-111">解决方案</span><span class="sxs-lookup"><span data-stu-id="f326d-111">Solution</span></span>  
 <span data-ttu-id="f326d-112">如果你想要检查前导零，则必须实现**CheckLeadingZero**方法而不是**CheckLeadingZeroInElement**方法。</span><span class="sxs-lookup"><span data-stu-id="f326d-112">If you want to check leading zeroes, you must implement the **CheckLeadingZero** method instead of the **CheckLeadingZeroInElement** method.</span></span> <span data-ttu-id="f326d-113">**CheckLeadingZero**将导致验证错误，如果没有前导零的函数的字符串输入。</span><span class="sxs-lookup"><span data-stu-id="f326d-113">**CheckLeadingZero** causes a validation error if there is a leading zero in the string input to the function.</span></span>  
  
 <span data-ttu-id="f326d-114">若要实现**CheckLeadingZero**方法中，你必须创建时，将调用的自定义方法**CheckLeadingZero**从自定义函数中的方法并提供到它作为一个字符串，此值为验证前导零。</span><span class="sxs-lookup"><span data-stu-id="f326d-114">To implement the **CheckLeadingZero** method, you must create a custom method that invokes the **CheckLeadingZero** method from within the custom function and provides to it as a string the value to be validated for leading zeroes.</span></span> <span data-ttu-id="f326d-115">这是因为**CheckLeadingZero**不会记录错误，而是只是返回布尔值 False 如果输入的字符串不是有效的 SWIFT 数字段或字符串输入中包含前导零。</span><span class="sxs-lookup"><span data-stu-id="f326d-115">This is because **CheckLeadingZero** does not log an error, but instead simply returns a Boolean False if the input string is not a valid SWIFT Number field or if the string input has a leading zero.</span></span> <span data-ttu-id="f326d-116">否则，它将返回 True。</span><span class="sxs-lookup"><span data-stu-id="f326d-116">Otherwise, it returns True.</span></span> <span data-ttu-id="f326d-117">自定义方法然后可以相应地记录的错误。</span><span class="sxs-lookup"><span data-stu-id="f326d-117">Your custom method can then log errors accordingly.</span></span>  
  
## <a name="an-error-is-returned-by-the-message-validation-policy-if-the-swift-number-field-has-a-leading-zero"></a><span data-ttu-id="f326d-118">如果 SWIFT 号字段具有前导零，返回错误的消息验证策略</span><span class="sxs-lookup"><span data-stu-id="f326d-118">An error is returned by the message validation policy if the SWIFT Number field has a leading zero</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="f326d-119">故障现象</span><span class="sxs-lookup"><span data-stu-id="f326d-119">Symptom</span></span>  
 <span data-ttu-id="f326d-120">如果邮件提交包含字段中的前导零即使前导零允许为该字段，则返回 BRE 验证错误。</span><span class="sxs-lookup"><span data-stu-id="f326d-120">A BRE validation error is returned if a message is submitted with leading zeroes in a field even though leading zeroes are permitted for the field.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="f326d-121">可能的原因</span><span class="sxs-lookup"><span data-stu-id="f326d-121">Possible Cause</span></span>  
 <span data-ttu-id="f326d-122">如果以下方法之一用于验证问题，通常在规则的操作部分中的规则中的 SWIFT 数字段会出现此问题。</span><span class="sxs-lookup"><span data-stu-id="f326d-122">This can occur if one of the following methods is used to validate a SWIFT Number field in the rule concerned, usually in the Action part of the rule.</span></span> <span data-ttu-id="f326d-123">这可能是量、 速率、 价格或数量字段中。</span><span class="sxs-lookup"><span data-stu-id="f326d-123">This may occur in an Amount, Rate, Price, or Quantity field.</span></span>  
  
-   <span data-ttu-id="f326d-124">**CheckCurrencyAmount**</span><span class="sxs-lookup"><span data-stu-id="f326d-124">**CheckCurrencyAmount**</span></span>  
  
-   <span data-ttu-id="f326d-125">**CheckValidAmount**</span><span class="sxs-lookup"><span data-stu-id="f326d-125">**CheckValidAmount**</span></span>  
  
-   <span data-ttu-id="f326d-126">**CheckValidCurrencyAndPriceCode**</span><span class="sxs-lookup"><span data-stu-id="f326d-126">**CheckValidCurrencyAndPriceCode**</span></span>  
  
-   <span data-ttu-id="f326d-127">**CheckValidSignCurrencyAmount**</span><span class="sxs-lookup"><span data-stu-id="f326d-127">**CheckValidSignCurrencyAmount**</span></span>  
  
-   <span data-ttu-id="f326d-128">**CheckValidSignDateCurrencyAmount**</span><span class="sxs-lookup"><span data-stu-id="f326d-128">**CheckValidSignDateCurrencyAmount**</span></span>  
  
-   <span data-ttu-id="f326d-129">**CheckValidSignRate**</span><span class="sxs-lookup"><span data-stu-id="f326d-129">**CheckValidSignRate**</span></span>  
  
-   <span data-ttu-id="f326d-130">**IsValidTransactionDetailsCurrencyAmount**</span><span class="sxs-lookup"><span data-stu-id="f326d-130">**IsValidTransactionDetailsCurrencyAmount**</span></span>  
  
### <a name="solution"></a><span data-ttu-id="f326d-131">解决方案</span><span class="sxs-lookup"><span data-stu-id="f326d-131">Solution</span></span>  
 <span data-ttu-id="f326d-132">如果有更高版本，列表中的方法除外**CheckValidSignRate**，在验证策略中，启用前导零中所述的规则中使用[量字段验证中支持前导零](../../adapters-and-accelerators/accelerator-swift/supporting-leading-zeros-in-amount-field-validations.md).</span><span class="sxs-lookup"><span data-stu-id="f326d-132">If any of the methods in the list above, except for **CheckValidSignRate**, is used in the rule in the Validation policy, enable leading zeros as described in [Supporting Leading Zeros in Amount Field Validations](../../adapters-and-accelerators/accelerator-swift/supporting-leading-zeros-in-amount-field-validations.md).</span></span>  
  
 <span data-ttu-id="f326d-133">如果**CheckValidSignRate**方法用于返回此错误的规则，以支持前导零的唯一方法是从验证策略中删除此规则。</span><span class="sxs-lookup"><span data-stu-id="f326d-133">If the **CheckValidSignRate** method is used in the rule that returned this error, the only way to support leading zeroes is to remove this rule from the Validation policy.</span></span> <span data-ttu-id="f326d-134">请按照以下步骤来完成此操作：</span><span class="sxs-lookup"><span data-stu-id="f326d-134">Follow the steps below to accomplish this:</span></span>  
  
1.  <span data-ttu-id="f326d-135">在业务规则编辑器，右键单击**版本**节点部署的策略包含规则使用**CheckValidSignRate**方法。</span><span class="sxs-lookup"><span data-stu-id="f326d-135">In Business Rule Composer, right-click the **Version** node for the deployed policy that contains a rule using the **CheckValidSignRate** method.</span></span> <span data-ttu-id="f326d-136">单击**取消部署**。</span><span class="sxs-lookup"><span data-stu-id="f326d-136">Click **Undeploy**.</span></span>  
  
2.  <span data-ttu-id="f326d-137">右键单击**版本**作为相同的策略，然后单击的节点**复制**。</span><span class="sxs-lookup"><span data-stu-id="f326d-137">Right-click the **Version** node for the same policy, and then click **Copy**.</span></span>  
  
3.  <span data-ttu-id="f326d-138">右键单击**Validation_Policy**作为相同的策略，然后单击的节点**粘贴**。</span><span class="sxs-lookup"><span data-stu-id="f326d-138">Right-click the **Validation_Policy** node for the same policy, and then click **Paste**.</span></span>  
  
4.  <span data-ttu-id="f326d-139">展开新的未保存的版本的策略。</span><span class="sxs-lookup"><span data-stu-id="f326d-139">Expand the new unsaved version of the policy.</span></span> <span data-ttu-id="f326d-140">右键单击具有规则**CheckValidSignRate**方法调用，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="f326d-140">Right-click the rule that has the **CheckValidSignRate** method call, and then click **Delete**.</span></span>  
  
5.  <span data-ttu-id="f326d-141">右键单击新未保存的策略的**版本**节点，，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="f326d-141">Right-click the policy's new unsaved **Version** node, and then click **Save**.</span></span> <span data-ttu-id="f326d-142">右键单击同一节点，并依次**发布**。</span><span class="sxs-lookup"><span data-stu-id="f326d-142">Right-click the same node, and then click **Publish**.</span></span> <span data-ttu-id="f326d-143">右键单击同一节点，并依次**部署**。</span><span class="sxs-lookup"><span data-stu-id="f326d-143">Right-click the same node, and then click **Deploy**.</span></span>  
  
## <a name="a4swift-database-requires-archiving"></a><span data-ttu-id="f326d-144">A4SWIFT 数据库需要存档</span><span class="sxs-lookup"><span data-stu-id="f326d-144">A4SWIFT database requires archiving</span></span>  
  
### <a name="symptom"></a><span data-ttu-id="f326d-145">故障现象</span><span class="sxs-lookup"><span data-stu-id="f326d-145">Symptom</span></span>  
 <span data-ttu-id="f326d-146">[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]数据库增长过大。</span><span class="sxs-lookup"><span data-stu-id="f326d-146">The [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] database is growing too large.</span></span>  
  
### <a name="possible-cause"></a><span data-ttu-id="f326d-147">可能的原因</span><span class="sxs-lookup"><span data-stu-id="f326d-147">Possible Cause</span></span>  
 <span data-ttu-id="f326d-148">中的历史记录表[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]数据库不自动存档。</span><span class="sxs-lookup"><span data-stu-id="f326d-148">The History table in the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] database is not automatically archived.</span></span> <span data-ttu-id="f326d-149">此表存储有关消息修复和新的提交，包括谁执行了哪些任务和有关业务流程的数据的数据。</span><span class="sxs-lookup"><span data-stu-id="f326d-149">This table stores data about message repair and new submission, including who performed which tasks and data about orchestration processes.</span></span> <span data-ttu-id="f326d-150">此表将不断变大执行消息修复和新提交操作。</span><span class="sxs-lookup"><span data-stu-id="f326d-150">This table will continue to grow as you perform message repair and new submission operations.</span></span>  
  
### <a name="solution"></a><span data-ttu-id="f326d-151">解决方案</span><span class="sxs-lookup"><span data-stu-id="f326d-151">Solution</span></span>  
 <span data-ttu-id="f326d-152">若要限制的增长[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]数据库，请定期存档数据从历史记录表，使用你标准存档过程。</span><span class="sxs-lookup"><span data-stu-id="f326d-152">To limit growth of the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] database, routinely archive data out of the History table, using your standard archiving procedures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f326d-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f326d-153">See Also</span></span>  
 [<span data-ttu-id="f326d-154">疑难解答： 问题和解决方法</span><span class="sxs-lookup"><span data-stu-id="f326d-154">Troubleshooting: Issues and Resolutions</span></span>](../../adapters-and-accelerators/accelerator-swift/troubleshooting-issues-and-resolutions1.md)