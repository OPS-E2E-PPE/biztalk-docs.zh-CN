---
title: 扩展的解决方案，用于捕获和消息修复 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- repairing messages, errors
- code samples, errors
- errors, code sample
- repairing messages, code sample
- ErrorCollection objects
ms.assetid: 93f463a0-ecff-4f3e-a145-7c506f42c767
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba6669f743a20cdde123eff397604fbad1ddb040
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377925"
---
# <a name="extending-the-solution-for-capture-and-message-repair"></a>捕获和消息修复扩展的解决方案
此帮助中的 MT103 端到端教程演示如何构造用于订阅失败的 SWIFT 消息的 BizTalk 业务流程。  
  
 MT103 端到端教程中的业务流程使用的帮助器类的静态方法**ErrorExtractor**，以从消息中提取错误部分和正文为字符串。 然后，业务流程都会写入单独的文件的部分。  
  
 因为失败的消息的错误部分的序列化**ErrorCollection**构造的管道组件，可以反序列化集合，并使用它来自动执行多个错误报告和处理。 以下 Microsoft[!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)]代码段演示了如何进行反序列化失败消息的错误消息部分，并循环访问集合中的分析错误。 代码片段省略命名空间限定，以提高可读性：  
  
```  
// instantiate an appropriate XmlTextReader  
// xm contains the message  
string sError = ErrorExtractor.GetErrorPartAsString(xm);  
StringReader sRdr = new StringReader(sError);  
XmlTextReader xRdr = new XmlTextReader(sRdr);  
  
// deserialize the collection  
ErrorCollection eC = ErrorCollection.GetErrorCollection(xRdr);  
  
// loop over the parsing errors in the collection  
IEnumerator pEnum = eC.GetParseErrorEnumerator();  
while(pEnum.MoveNext())   
{  
  // pEnum.Current() returns a ParseError object for processing  
}  
  
```  
  
 **ErrorCollection**包括用于循环访问与循环访问集合中的错误的所有类型的同时按错误的方法。 有关详细信息**ErrorCollection**，请参阅 ErrorCollection 成员。  
  
## <a name="see-also"></a>请参阅  
 [失败的消息和 ErrorCollection 对象](../../adapters-and-accelerators/accelerator-swift/failed-messages-and-errorcollection-objects.md)