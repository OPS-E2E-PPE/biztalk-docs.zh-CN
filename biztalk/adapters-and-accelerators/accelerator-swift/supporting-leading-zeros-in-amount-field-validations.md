---
title: 支持具有前导零金额字段验证 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- amounts, amount fields
- amounts, leading zeros
- validating, amount fields
ms.assetid: 7c202422-019f-43da-9c2a-4b9fdf0b2859
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e68cb3f776fd177bfaf437c6ae84b3e1da36f084
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529798"
---
# <a name="supporting-leading-zeros-in-amount-field-validations"></a>支持具有前导零金额字段验证
某些消息类型的验证策略在金额字段上执行验证。 若要启用在金额字段中的前导零，必须编辑消息类型的验证策略。 可以创建新版本的默认验证策略和编辑业务规则编辑器中的参数或部署该策略之前，可以编辑在文本编辑器中手动的默认策略。  
  
 下表列出了启用或禁用前导零的方法。 此表还指示您需要在方法中设置的参数的序号。 将其设置为 true 以启用前导零，或为 False 可禁用它们。  
  
|方法|参数号|  
|------------|---------------------|  
|**CheckValidAmount**|6|  
|**CheckCurrencyAmount**|4|  
|**CheckValidSignCurrencyAmount**|3|  
|**CheckValidSignDateCurrencyAmount**|4|  
|**IsValidTransactionDetailsCurrencyAmount**|4|  
  
 上表中的每个方法都包含在一个或多个消息验证策略。 若要在策略中设置参数，必须搜索要验证的策略是否包含它的方法名称。 一种方法可能会多次出现一条消息的策略中。  
  
### <a name="to-enable-or-disable-leading-zeros"></a>若要启用或禁用前导零  
  
1.  打开文本编辑器，如记事本。  
  
2.  在编辑器中，浏览到想要启用或禁用前导零的消息验证策略的位置。 例如，您可以找到消息验证策略对于 MT103 消息类型，MT103_Validation_Policy.xml，在 *\<驱动器\>* : / Program Files/Microsoft BizTalk Accelerator for SWIFT/SWIFT 消息/ 类别 1/MT103。 打开验证策略。  
  
3.  在策略中，搜索**CheckValidAmount**方法。  
  
4.  如果找到该方法，倒计时到相应的自变量。 例如，对于**CheckValidAmount**方法，向第六个参数的计数。 将参数设置为 **，则返回 True**启用前导零或为 False，则禁用它们。  
  
5.  对于上表中每个方法重复步骤 3 和 4。  
  
6.  保存该文件，然后关闭编辑器。