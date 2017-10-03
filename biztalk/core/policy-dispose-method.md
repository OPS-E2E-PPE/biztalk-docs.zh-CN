---
title: "Policy.Dispose 方法 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: db37c6b9-acf0-42ee-9356-4d1567934862
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba4713616edf55c149a215a6f7842cd5d0353dfe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="policydispose-method"></a>Policy.Dispose 方法
**Policy.Dispose**方法释放所使用的资源**策略**类，并且还返回**策略**到缓存的对象。 再次调用相同的策略时，已缓存**策略**使用对象，该命令创建新的所需的时间可保存**策略**对象。  
  
 如果不显式调用**Policy.Dispose**方法，则策略不会返回给缓存之前的.NET 运行时在垃圾回收进程期间释放的对象。 因此，应调用**Policy.Dispose**与完成之后**策略**对象。  
  
 使用的示例代码**Policy.Dispose**方法是，如下所示：  
  
```  
xmlDocument = IncomingXMLMessage.XMLCase;  
typedXmlDocument = new Microsoft.RuleEngine.TypedXmlDocument("Microsoft.Samples.BizTalk.LoansProcessor.Case",xmlDocument);  
policy = new Microsoft.RuleEngine.Policy("LoanProcessing");  
policy.Execute(typedXmlDocument);  
OutgoingXMLMessage.XMLCase = xmlDocument;  
policy.Dispose();  
```