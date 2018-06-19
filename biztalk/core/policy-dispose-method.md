---
title: Policy.Dispose 方法 |Microsoft 文档
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
ms.openlocfilehash: ba4713616edf55c149a215a6f7842cd5d0353dfe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263629"
---
# <a name="policydispose-method"></a><span data-ttu-id="d978a-102">Policy.Dispose 方法</span><span class="sxs-lookup"><span data-stu-id="d978a-102">Policy.Dispose Method</span></span>
<span data-ttu-id="d978a-103">**Policy.Dispose**方法释放所使用的资源**策略**类，并且还返回**策略**到缓存的对象。</span><span class="sxs-lookup"><span data-stu-id="d978a-103">The **Policy.Dispose** method releases resources used by the **Policy** class, and also returns the **Policy** object to the cache.</span></span> <span data-ttu-id="d978a-104">再次调用相同的策略时，已缓存**策略**使用对象，该命令创建新的所需的时间可保存**策略**对象。</span><span class="sxs-lookup"><span data-stu-id="d978a-104">When the same policy is invoked again, the cached **Policy** object is used, which saves the time needed for creating a new **Policy** object.</span></span>  
  
 <span data-ttu-id="d978a-105">如果不显式调用**Policy.Dispose**方法，则策略不会返回给缓存之前的.NET 运行时在垃圾回收进程期间释放的对象。</span><span class="sxs-lookup"><span data-stu-id="d978a-105">If you do not explicitly call the **Policy.Dispose** method, then the policy is not returned to the cache until the .NET runtime frees up the object during the garbage collection process.</span></span> <span data-ttu-id="d978a-106">因此，应调用**Policy.Dispose**与完成之后**策略**对象。</span><span class="sxs-lookup"><span data-stu-id="d978a-106">Therefore, you should call **Policy.Dispose** when you are finished with the **Policy** object.</span></span>  
  
 <span data-ttu-id="d978a-107">使用的示例代码**Policy.Dispose**方法是，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d978a-107">The sample code for using the **Policy.Dispose** method is as follows:</span></span>  
  
```  
xmlDocument = IncomingXMLMessage.XMLCase;  
typedXmlDocument = new Microsoft.RuleEngine.TypedXmlDocument("Microsoft.Samples.BizTalk.LoansProcessor.Case",xmlDocument);  
policy = new Microsoft.RuleEngine.Policy("LoanProcessing");  
policy.Execute(typedXmlDocument);  
OutgoingXMLMessage.XMLCase = xmlDocument;  
policy.Dispose();  
```