---
title: 如何执行策略 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rules Framework, policies
- Business Rules Framework, code samples
- Business Rules Framework, programming
ms.assetid: 90d28d9d-0204-47de-a927-26e284c886e4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4eaf60193a3435808c0901ca1c441527a67884f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337821"
---
# <a name="how-to-execute-policies"></a>如何执行策略
下面的示例代码演示如何调用规则引擎，通过以编程方式执行策略**策略**类**Microsoft.RuleEngine**程序集。  
  
```  
xmlDocument = IncomingXMLMessage.XMLCase;  
typedXmlDocument = new Microsoft.RuleEngine.TypedXmlDocument("Microsoft.Samples.BizTalk.LoansProcessor.Case",xmlDocument);  
policy = new Microsoft.RuleEngine.Policy("LoanProcessing");  
policy.Execute(typedXmlDocument);  
OutgoingXMLMessage.XMLCase = xmlDocument;  
policy.Dispose();  
```  
  
## <a name="important-methods-of-the-policy-class"></a>Policy 类的重要方法  
 以下是 Policy 类和及其说明的重要方法。  
  
|Policy 类中的方法|Description|  
|--------------------------------|-----------------|  
|Execute|将指定的短期事实添加到规则引擎工作内存和执行使用匹配-冲突解决-操作算法策略。 匹配-冲突解决-操作算法的详细信息，请参阅[条件评估和操作执行](../core/condition-evaluation-and-action-execution.md)。|  
|释放|释放由执行策略的规则引擎使用的资源。|  
|Clear|清除或重置的工作内存和议程为执行策略创建的规则引擎实例。|  
  
## <a name="see-also"></a>请参阅  
 [Policy.Dispose 方法](../core/policy-dispose-method.md)