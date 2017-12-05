---
title: "支持前导零量字段验证中的 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- amounts, amount fields
- amounts, leading zeros
- validating, amount fields
ms.assetid: 7c202422-019f-43da-9c2a-4b9fdf0b2859
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3559b63ec7588fa2d7451779947a476cf19b7bf0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="supporting-leading-zeros-in-amount-field-validations"></a>支持前导零量字段验证中
某些消息类型的验证策略对量字段进行验证。 若要启用量字段中的前导零，必须编辑消息类型的验证策略。 您可以创建新版本的默认验证策略，并编辑业务规则编辑器中的自变量或部署该策略之前，你可以编辑在文本编辑器中手动的默认策略。  
  
 下表列出的方法的启用或禁用前导零。 此表还指示你需要在方法中设置的自变量的序号。 为 true 以启用前导零，或为 False 可禁止它们设置到它。  
  
|方法|参数号|  
|------------|---------------------|  
|**CheckValidAmount**|6|  
|**CheckCurrencyAmount**|4|  
|**CheckValidSignCurrencyAmount**|3|  
|**CheckValidSignDateCurrencyAmount**|4|  
|**IsValidTransactionDetailsCurrencyAmount**|4|  
  
 上表中的每个方法包含在一个或多个消息验证策略。 若要将参数设置在策略中，你必须搜索以验证它是否包含策略的方法名称的选项。 一种方法可能会多次出现一条消息的策略中。  
  
### <a name="to-enable-or-disable-leading-zeros"></a>若要启用或禁用前导零  
  
1.  打开文本编辑器，例如记事本。  
  
2.  在编辑器中，浏览到想要启用或禁用前导零的消息验证策略的位置。 例如，你可以找到消息验证策略对于 MT103 消息类型，MT103_Validation_Policy.xml，在*\<驱动器\>*: / 程序文件/Microsoft BizTalk Accelerator for SWIFT/SWIFT 消息/ 类别 1/MT103。 打开验证策略。  
  
3.  在策略中，搜索**CheckValidAmount**方法。  
  
4.  如果找到该方法，递减至相应的自变量。 例如，对于**CheckValidAmount**方法下的第六个自变量的计数。 将参数设置为**True**启用前导零或 False，则禁用它们。  
  
5.  对于上表中每个方法重复步骤 3 和 4。  
  
6.  保存该文件，，然后关闭编辑器。