---
title: Policy.Dispose 方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db37c6b9-acf0-42ee-9356-4d1567934862
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1eba833edcedd814fffd823bfe01729b77f0f033
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394955"
---
# <a name="policydispose-method"></a>Policy.Dispose 方法
**Policy.Dispose**方法将释放使用的资源**策略**类，并且还返回**策略**到缓存的对象。 当再次调用同一个策略的缓存**策略**使用对象，这将创建一个新的所需的时间保存**策略**对象。  
  
 如果不显式调用**Policy.Dispose**方法，则该策略不会返回到缓存之前的.NET 运行时在垃圾收集进程期间释放此对象。 因此，应调用**Policy.Dispose**当您使用完**策略**对象。  
  
 使用的示例代码**Policy.Dispose**方法如下所示：  
  
```  
xmlDocument = IncomingXMLMessage.XMLCase;  
typedXmlDocument = new Microsoft.RuleEngine.TypedXmlDocument("Microsoft.Samples.BizTalk.LoansProcessor.Case",xmlDocument);  
policy = new Microsoft.RuleEngine.Policy("LoanProcessing");  
policy.Execute(typedXmlDocument);  
OutgoingXMLMessage.XMLCase = xmlDocument;  
policy.Dispose();  
```