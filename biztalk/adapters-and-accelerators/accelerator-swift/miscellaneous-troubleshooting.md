---
title: 其他故障排除 |Microsoft Docs
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
ms.openlocfilehash: eb284d6d869834e3e6d148e2582043e3789f43ca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377190"
---
# <a name="miscellaneous-troubleshooting"></a>其他故障排除
## <a name="leading-zeroes-validation-is-not-performed-for-fields-that-use-the-checkleadingzeroesinelement-method-to-validate-a-field-in-the-message-validation-policy"></a>前导零的 CheckLeadingZeroesInElement 方法用于验证消息验证策略中的字段的字段不执行验证。  
  
### <a name="symptom"></a>故障现象  
 如果将消息提交用前导零的字段中，即使为该字段不允许前导零，并且验证策略包括用于执行此验证的字段的规则，则不返回任何 BRE 验证错误。  
  
### <a name="possible-cause"></a>可能的原因  
 **CheckLeadingZeroInElement**方法包含在业务规则中的消息类型的验证策略。 此方法已弃用。 函数调用的目的是导致验证失败是否存在一个前导零的函数调用中提供的元素。 但是，此方法不会导致验证失败，即使没有前导零的字段中。  
  
### <a name="solution"></a>解决方案  
 如果你想要检查前导零，则必须实现**CheckLeadingZero**方法而不是**CheckLeadingZeroInElement**方法。 **CheckLeadingZero**会导致验证错误，如果没有前导零的函数的字符串输入。  
  
 若要实现**CheckLeadingZero**方法，必须创建自定义调用的方法， **CheckLeadingZero**从自定义函数中的方法，并提供到它作为一个字符串，此值为验证前导零。 这是因为**CheckLeadingZero**不会记录一个错误，而是只需返回布尔值 False 如果输入的字符串不是有效的 SWIFT 数字字段或字符串输入的前导零。 否则，返回 True。 自定义方法然后可以相应地记录错误。  
  
## <a name="an-error-is-returned-by-the-message-validation-policy-if-the-swift-number-field-has-a-leading-zero"></a>如果 SWIFT 编号字段具有前导零，返回错误的消息验证策略  
  
### <a name="symptom"></a>故障现象  
 如果将消息提交与字段中的前导零即使前导零允许为字段，则返回 BRE 验证错误。  
  
### <a name="possible-cause"></a>可能的原因  
 如果以下方法之一用于验证规则而言，通常在该规则的操作部分中的 SWIFT 数字字段，这可能发生。 这可能是量、 速率、 价格或数量字段中。  
  
-   **CheckCurrencyAmount**  
  
-   **CheckValidAmount**  
  
-   **CheckValidCurrencyAndPriceCode**  
  
-   **CheckValidSignCurrencyAmount**  
  
-   **CheckValidSignDateCurrencyAmount**  
  
-   **CheckValidSignRate**  
  
-   **IsValidTransactionDetailsCurrencyAmount**  
  
### <a name="solution"></a>解决方案  
 如果有更高版本，列表中的方法除外**CheckValidSignRate**，在验证策略中，启用前导零，如中所述在规则中使用[金额字段验证中支持前导零](../../adapters-and-accelerators/accelerator-swift/supporting-leading-zeros-in-amount-field-validations.md).  
  
 如果**CheckValidSignRate**方法中返回此错误的规则，以支持前导零的唯一方法是从验证策略中删除此规则。 请按照以下步骤来完成此操作：  
  
1.  在业务规则编辑器中，右键单击**版本**节点的包含规则使用的已部署策略**CheckValidSignRate**方法。 单击**取消部署**。  
  
2.  右键单击**版本**节点作为同一个策略，然后单击**副本**。  
  
3.  右键单击**Validation_Policy**节点作为同一个策略，然后单击**粘贴**。  
  
4.  展开新的未保存的策略版本。 右键单击具有该规则**CheckValidSignRate**方法调用，然后单击**删除**。  
  
5.  右键单击该策略的新未保存**版本**节点，并单击**保存**。 右键单击同一个节点，然后单击**发布**。 右键单击同一个节点，然后单击**部署**。  
  
## <a name="a4swift-database-requires-archiving"></a>A4SWIFT 数据库需要存档  
  
### <a name="symptom"></a>故障现象  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]数据库增长得过大。  
  
### <a name="possible-cause"></a>可能的原因  
 中的历史记录表[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]数据库不会自动存档。 此表存储有关消息修复和新提交，包括谁执行了哪些任务和有关业务流程进程的数据的数据。 此表会继续增加执行消息修复和新提交操作。  
  
### <a name="solution"></a>解决方案  
 若要限制的增长[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]数据库、 定期存档数据移出历史记录表，使用您存档过程的标准。  
  
## <a name="see-also"></a>请参阅  
 [故障排除：问题和解决方法](../../adapters-and-accelerators/accelerator-swift/troubleshooting-issues-and-resolutions1.md)