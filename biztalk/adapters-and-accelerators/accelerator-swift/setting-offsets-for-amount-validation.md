---
title: 为金额验证设置偏移量 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- amounts, validating
- validating, amounts
- amounts, offsets
- offsets
ms.assetid: 39d5510c-52e6-4fd9-9632-582b508f04d7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b194445499f2506b1dcb8309cb20f4aa17e6ca83
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377046"
---
# <a name="setting-offsets-for-amount-validation"></a>为金额验证设置偏移量
使用规则的消息类型 MT102，MT103 和 MT103PLUS 金额字段由其各自的验证策略中的规则进行验证。 金额字段可以精确匹配或可以对其进行验证，以在的金额范围内。  
  
 若要启用的范围内的验证，请相关验证策略中的方法调用中指定偏移量的百分比。 例如，如果为字段设置量为 100，且偏移量的百分比为 10%，有效金额将从 90 到为 110 时，非独占的任何值。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 为 MT102、 MT102PLUS 和 MT103 消息类型提供此支持。  
  
 中指定的偏移量的百分比**IsValidSettlementAmount**或**IsValidInterbankSettledAmount**中验证策略的方法。 **IsValidSettlementAmount**方法实现 MT102 和 MT102PLUS 消息量字段的用法规则。 **IsValidInterbankSettledAmount**方法实现的 MT103 消息量字段的用法规则。 OffsetPercent 参数，该变量的任一这些方法的第十个参数中指定的偏移量的百分比。  
  
 百分比偏移量设置时，适用于以下字段：  
  
|消息类型|字段的偏移量与验证|  
|------------------|-----------------------------------|  
|MT102 或 MT102PLUS|32<br /><br /> 33B|  
|MT103|19，序列 C<br /><br /> 31A，序列 C<br /><br /> 72G|  
  
### <a name="to-set-an-offset-percentage"></a>若要设置偏移量的百分比  
  
1.  打开文本编辑器，如记事本。  
  
2.  在编辑器中，浏览到想要设置偏移量的百分比的消息验证策略的位置。 例如，您可以找到消息验证策略对于 MT103 消息类型，MT103_Validation_Policy.xml，在*\<驱动器\>*: files\ Microsoft BizTalk Accelerator for SWIFT \<版本\>消息 Pack\SWIFT Messages\A4SWIFT SRG\<版本\>\Category 1\MT103。 打开验证策略。  
  
3.  在策略中，搜索 IsValidSettlementAmount MT102 和 MT102PLUS 消息或 IsValidInterbankSettledAmount 的 MT103 消息。  
  
4.  倒计数到第十个参数。 参数中输入偏移量的百分比。  
  
5.  保存该文件，然后关闭编辑器。