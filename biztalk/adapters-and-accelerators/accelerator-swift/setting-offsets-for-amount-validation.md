---
title: 设置量验证偏移量 |Microsoft 文档
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
ms.openlocfilehash: 7cfae474407daa7dd3c0b95db3fed076a581cf1c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961251"
---
# <a name="setting-offsets-for-amount-validation"></a>设置量验证偏移量
通过其各自的验证策略中的规则进行验证的消息类型 MT102，MT103 和 MT103PLUS 量字段使用规则。 量字段可以完全匹配，或可以验证为金额的范围之内。  
  
 若要启用的范围内的验证，可以在相关验证策略中的方法调用中指定偏移量的百分比。 例如，如果量为字段设置为 100，且偏移量的百分比为 10%，有效金额将从 90 为 110，包括任何值。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]为 MT102、 MT102PLUS 和 MT103 消息类型提供此支持。  
  
 中指定的偏移量的百分比**IsValidSettlementAmount**或**IsValidInterbankSettledAmount**验证策略中的方法。 **IsValidSettlementAmount**方法实现 MT102 和 MT102PLUS 消息量字段的用法规则。 **IsValidInterbankSettledAmount**方法实现的 MT103 消息量字段的用法规则。 OffsetPercent 参数，即任一这些方法的第 10 个自变量中指定的偏移量的百分比。  
  
 百分比偏移量设置时，适用于以下字段：  
  
|消息类型|字段验证偏移量|  
|------------------|-----------------------------------|  
|MT102 或 MT102PLUS|32<br /><br /> 33B|  
|MT103|19，序列 C<br /><br /> 31A，序列 C<br /><br /> 72 G|  
  
### <a name="to-set-an-offset-percentage"></a>若要设置偏移量的百分比  
  
1.  打开文本编辑器，例如记事本。  
  
2.  在编辑器中，浏览到你要在其中设置偏移量的百分比的消息验证策略的位置。 例如，你可以找到消息验证策略对于 MT103 消息类型，MT103_Validation_Policy.xml，在*\<驱动器\>*: files\ Microsoft BizTalk Accelerator for SWIFT \<版本\>消息 Pack\SWIFT Messages\A4SWIFT SRG\<版本\>\Category 1\MT103。 打开验证策略。  
  
3.  在策略中，搜索上 IsValidSettlementAmount MT102 和 MT102PLUS 消息或 IsValidInterbankSettledAmount MT103 消息。  
  
4.  倒计时到第 10 个自变量。 参数中输入的偏移量的百分比。  
  
5.  保存该文件，，然后关闭编辑器。