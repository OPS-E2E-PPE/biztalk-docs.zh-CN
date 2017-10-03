---
title: "如何执行策略 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Business Rules Framework, policies
- Business Rules Framework, code samples
- Business Rules Framework, programming
ms.assetid: 90d28d9d-0204-47de-a927-26e284c886e4
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b0aa834150f0d5c84ebb4c757769a2be38f3942
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-execute-policies"></a>如何执行策略
下面的示例代码演示如何调用要通过使用以编程方式执行策略的规则引擎**策略**类**Microsoft.RuleEngine**程序集。  
  
```  
xmlDocument = IncomingXMLMessage.XMLCase;  
typedXmlDocument = new Microsoft.RuleEngine.TypedXmlDocument("Microsoft.Samples.BizTalk.LoansProcessor.Case",xmlDocument);  
policy = new Microsoft.RuleEngine.Policy("LoanProcessing");  
policy.Execute(typedXmlDocument);  
OutgoingXMLMessage.XMLCase = xmlDocument;  
policy.Dispose();  
```  
  
## <a name="important-methods-of-the-policy-class"></a>策略类的重要方法  
 以下是 Policy 类的重要方法及其说明。  
  
|Policy 类中的方法|Description|  
|--------------------------------|-----------------|  
|Execute|将指定的短期事实添加到规则引擎的工作内存中，并使用匹配-冲突解决-操作算法执行策略。 匹配冲突解决操作算法的详细信息，请参阅[条件计算和操作执行](../core/condition-evaluation-and-action-execution.md)。|  
|释放|释放由规则引擎用来执行策略的资源。|  
|Clear|清除或重置为执行策略而创建的规则引擎实例的工作内存和议程。|  
  
## <a name="see-also"></a>另请参阅  
 [Policy.Dispose 方法](../core/policy-dispose-method.md)