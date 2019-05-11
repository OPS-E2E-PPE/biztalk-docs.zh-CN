---
title: 使用架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], examples
- pipeline components [custom], code samples
- pipeline components [custom], schemas
ms.assetid: 07e60532-1032-422d-865e-0bd65c45dab6
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d0343514562effd3de12141f5c569ece1f5de29b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395373"
---
# <a name="using-schemas"></a><span data-ttu-id="b8e6f-102">使用架构</span><span class="sxs-lookup"><span data-stu-id="b8e6f-102">Using Schemas</span></span>
<span data-ttu-id="b8e6f-103">本部分包含与使用的架构相关联的常见任务的代码示例。</span><span class="sxs-lookup"><span data-stu-id="b8e6f-103">This section contains code examples for common tasks associated with using schemas.</span></span>  
  
## <a name="using-xsd-schemas"></a><span data-ttu-id="b8e6f-104">使用 XSD 架构</span><span class="sxs-lookup"><span data-stu-id="b8e6f-104">Using XSD schemas</span></span>  
 <span data-ttu-id="b8e6f-105">`IDocumentSpec Interface`接口表示 XML 架构定义语言 (XSD) 架构所定义的文档形状; 形状已取得 root 权限的 XSD 的顶级元素。</span><span class="sxs-lookup"><span data-stu-id="b8e6f-105">The `IDocumentSpec Interface` interface represents a document shape defined by an XML Schema definition language (XSD) schema; the shape is rooted by a top-level element of the XSD.</span></span> <span data-ttu-id="b8e6f-106">安装架构后，它可以检索通过调用`IPipelineContext.GetDocumentSpecByType Method`或`IPipelineContext.GetDocumentSpecByName Method`中的方法**IPipelineContext**接口。</span><span class="sxs-lookup"><span data-stu-id="b8e6f-106">After the schema is installed, it can be retrieved by calling the `IPipelineContext.GetDocumentSpecByType Method` or `IPipelineContext.GetDocumentSpecByName Method` methods in the **IPipelineContext** interface.</span></span>  
  
```  
IDocumentSpec docspec = pipeineContext.GetDocumentSpecByType("myschema#root");  
```  
  
## <a name="using-xsd-flat-file-schemas"></a><span data-ttu-id="b8e6f-107">使用 XSD 平面文件架构</span><span class="sxs-lookup"><span data-stu-id="b8e6f-107">Using XSD flat file schemas</span></span>  
 <span data-ttu-id="b8e6f-108">这两个**GetDocumentSpecByType**并**GetDocumentSpecByName**方法将返回**IDocumentSpec**接口。</span><span class="sxs-lookup"><span data-stu-id="b8e6f-108">Both the **GetDocumentSpecByType** and **GetDocumentSpecByName** methods return the **IDocumentSpec** interface.</span></span> <span data-ttu-id="b8e6f-109">如果架构为实际的平面文件架构 （一个具有附加的平面特定于文件的批注），可以类型转换**IDocumentSpec**成**IFFDocumentSpec**并启动解析和序列化从此处的序列。</span><span class="sxs-lookup"><span data-stu-id="b8e6f-109">If the schema is actually a flat file schema (one that has additional flat file-specific annotations), you can typecast the **IDocumentSpec** into **IFFDocumentSpec** and initiate parsing and serializing sequences from there.</span></span>  
  
```  
IFFDocumentSpec docspec = (IFFDocumentSpec) pipeineContext.GetDocumentSpecByType("myschema#root");  
```  
  
## <a name="see-also"></a><span data-ttu-id="b8e6f-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="b8e6f-110">See Also</span></span>  

[<span data-ttu-id="b8e6f-111">使用解析和序列化引擎</span><span class="sxs-lookup"><span data-stu-id="b8e6f-111">Using the Parsing and Serializing Engines</span></span>](../core/using-the-parsing-and-serializing-engines.md)