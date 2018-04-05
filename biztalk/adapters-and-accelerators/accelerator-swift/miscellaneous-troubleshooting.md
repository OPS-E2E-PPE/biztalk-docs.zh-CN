---
title: 其他故障排除 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting
ms.assetid: 6ebc1867-b5d3-46de-b3bd-69e570ed2b2c
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 765b32895fa76c0c77b740b76e2e6a03f0571351
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="miscellaneous-troubleshooting"></a>其他故障排除
## <a name="leading-zeroes-validation-is-not-performed-for-fields-that-use-the-checkleadingzeroesinelement-method-to-validate-a-field-in-the-message-validation-policy"></a>前导零的 CheckLeadingZeroesInElement 方法用于验证消息验证策略中的字段的字段不执行验证。  
  
### <a name="symptom"></a>故障现象  
 如果包含一个字段中的前导零提交一条消息，即使前导零不允许为该字段并验证策略包括执行此验证的字段的规则，则不返回任何 BRE 验证错误。  
  
### <a name="possible-cause"></a>可能的原因  
 **CheckLeadingZeroInElement**方法包含在消息类型的验证策略中的业务规则。 不推荐使用此方法。 函数调用的目的是导致验证失败，如果没有前导零的函数调用中提供的元素。 但是，此方法不会导致验证失败，即使没有前导零的字段中。  
  
### <a name="solution"></a>解决方案  
 如果你想要检查前导零，则必须实现**CheckLeadingZero**方法而不是**CheckLeadingZeroInElement**方法。 **CheckLeadingZero**将导致验证错误，如果没有前导零的函数的字符串输入。  
  
 若要实现**CheckLeadingZero**方法中，你必须创建时，将调用的自定义方法**CheckLeadingZero**从自定义函数中的方法并提供到它作为一个字符串，此值为验证前导零。 这是因为**CheckLeadingZero**不会记录错误，而是只是返回布尔值 False 如果输入的字符串不是有效的 SWIFT 数字段或字符串输入中包含前导零。 否则，它将返回 True。 自定义方法然后可以相应地记录的错误。  
  
## <a name="an-error-is-returned-by-the-message-validation-policy-if-the-swift-number-field-has-a-leading-zero"></a>如果 SWIFT 号字段具有前导零，返回错误的消息验证策略  
  
### <a name="symptom"></a>故障现象  
 如果邮件提交包含字段中的前导零即使前导零允许为该字段，则返回 BRE 验证错误。  
  
### <a name="possible-cause"></a>可能的原因  
 如果以下方法之一用于验证问题，通常在规则的操作部分中的规则中的 SWIFT 数字段会出现此问题。 这可能是量、 速率、 价格或数量字段中。  
  
-   **CheckCurrencyAmount**  
  
-   **CheckValidAmount**  
  
-   **CheckValidCurrencyAndPriceCode**  
  
-   **CheckValidSignCurrencyAmount**  
  
-   **CheckValidSignDateCurrencyAmount**  
  
-   **CheckValidSignRate**  
  
-   **IsValidTransactionDetailsCurrencyAmount**  
  
### <a name="solution"></a>解决方案  
 如果有更高版本，列表中的方法除外**CheckValidSignRate**，在验证策略中，启用前导零中所述的规则中使用[量字段验证中支持前导零](../../adapters-and-accelerators/accelerator-swift/supporting-leading-zeros-in-amount-field-validations.md).  
  
 如果**CheckValidSignRate**方法用于返回此错误的规则，以支持前导零的唯一方法是从验证策略中删除此规则。 请按照以下步骤来完成此操作：  
  
1.  在业务规则编辑器，右键单击**版本**节点部署的策略包含规则使用**CheckValidSignRate**方法。 单击**取消部署**。  
  
2.  右键单击**版本**作为相同的策略，然后单击的节点**复制**。  
  
3.  右键单击**Validation_Policy**作为相同的策略，然后单击的节点**粘贴**。  
  
4.  展开新的未保存的版本的策略。 右键单击具有规则**CheckValidSignRate**方法调用，然后单击**删除**。  
  
5.  右键单击新未保存的策略的**版本**节点，，然后单击**保存**。 右键单击同一节点，并依次**发布**。 右键单击同一节点，并依次**部署**。  
  
## <a name="a4swift-database-requires-archiving"></a>A4SWIFT 数据库需要存档  
  
### <a name="symptom"></a>故障现象  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]数据库增长过大。  
  
### <a name="possible-cause"></a>可能的原因  
 中的历史记录表[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]数据库不自动存档。 此表存储有关消息修复和新的提交，包括谁执行了哪些任务和有关业务流程的数据的数据。 此表将不断变大执行消息修复和新提交操作。  
  
### <a name="solution"></a>解决方案  
 若要限制的增长[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]数据库，请定期存档数据从历史记录表，使用你标准存档过程。  
  
## <a name="see-also"></a>另请参阅  
 [疑难解答： 问题和解决方法](../../adapters-and-accelerators/accelerator-swift/troubleshooting-issues-and-resolutions1.md)