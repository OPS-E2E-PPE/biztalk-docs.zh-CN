---
title: "捕获和消息修复扩展解决方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- repairing messages, errors
- code samples, errors
- errors, code sample
- repairing messages, code sample
- ErrorCollection objects
ms.assetid: 93f463a0-ecff-4f3e-a145-7c506f42c767
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bb2f5fb1960a149c96a179ba596c67c9f402016
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="extending-the-solution-for-capture-and-message-repair"></a><span data-ttu-id="79415-102">捕获和消息修复扩展解决方案</span><span class="sxs-lookup"><span data-stu-id="79415-102">Extending the Solution for Capture and Message Repair</span></span>
<span data-ttu-id="79415-103">此帮助中的 MT103 端到端教程演示如何构造订阅失败 SWIFT 消息 BizTalk 业务流程。</span><span class="sxs-lookup"><span data-stu-id="79415-103">The MT103 End-to-End Tutorial in this Help shows you how to construct a BizTalk orchestration that subscribes to failed SWIFT messages.</span></span>  
  
 <span data-ttu-id="79415-104">业务流程 MT103 端到端教程中的使用的帮助器类的静态方法**ErrorExtractor**，即可从消息中提取的错误一部分和正文，以字符串形式。</span><span class="sxs-lookup"><span data-stu-id="79415-104">The orchestration in the MT103 End-to-End Tutorial uses the static methods of a helper class, **ErrorExtractor**, to extract the error part and body from the message as strings.</span></span> <span data-ttu-id="79415-105">然后，业务流程将单独的文件的部分。</span><span class="sxs-lookup"><span data-stu-id="79415-105">The orchestration then writes the parts to separate files.</span></span>  
  
 <span data-ttu-id="79415-106">因为错误部分的失败消息的序列化**ErrorCollection**构造的管道组件，你可以反序列化集合并使用它来自动执行多个错误报告和处理。</span><span class="sxs-lookup"><span data-stu-id="79415-106">Because the error part of the failed message is a serialization of the **ErrorCollection** constructed by the pipeline component, you can deserialize the collection and use it to automate more of the error reporting and handling.</span></span> <span data-ttu-id="79415-107">以下[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)]代码片段阐释了如何反序列化错误消息部分的失败的消息，并循环访问集合中的分析错误。</span><span class="sxs-lookup"><span data-stu-id="79415-107">The following [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)] code fragment illustrates how to deserialize the error message part of a failed message and iterate over the parsing errors in the collection.</span></span> <span data-ttu-id="79415-108">中的代码片段省略可读性的命名空间限定内容：</span><span class="sxs-lookup"><span data-stu-id="79415-108">The code fragment omits namespace qualifications for readability:</span></span>  
  
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
  
 <span data-ttu-id="79415-109">**ErrorCollection**包括用于循环访问由类型也与循环访问集合中的错误的所有错误的方法。</span><span class="sxs-lookup"><span data-stu-id="79415-109">The **ErrorCollection** includes methods for iterating over errors by type as well as for iterating over all of the errors in the collection.</span></span> <span data-ttu-id="79415-110">有关详细信息**ErrorCollection**，请参阅 ErrorCollection 成员。</span><span class="sxs-lookup"><span data-stu-id="79415-110">For more information about the **ErrorCollection**, see ErrorCollection Members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79415-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="79415-111">See Also</span></span>  
 [<span data-ttu-id="79415-112">失败的消息和 ErrorCollection 对象</span><span class="sxs-lookup"><span data-stu-id="79415-112">Failed Messages and ErrorCollection Objects</span></span>](../../adapters-and-accelerators/accelerator-swift/failed-messages-and-errorcollection-objects.md)