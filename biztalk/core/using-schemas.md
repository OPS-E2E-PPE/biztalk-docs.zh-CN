---
title: "使用架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], examples
- pipeline components [custom], code samples
- pipeline components [custom], schemas
ms.assetid: 07e60532-1032-422d-865e-0bd65c45dab6
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a7cb71319fef61d3b6cb854b04b41e3815a6129
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-schemas"></a><span data-ttu-id="52a56-102">使用架构</span><span class="sxs-lookup"><span data-stu-id="52a56-102">Using Schemas</span></span>
<span data-ttu-id="52a56-103">本部分包含的代码示例的与使用架构相关联的常见任务。</span><span class="sxs-lookup"><span data-stu-id="52a56-103">This section contains code examples for common tasks associated with using schemas.</span></span>  
  
## <a name="using-xsd-schemas"></a><span data-ttu-id="52a56-104">使用 XSD 架构</span><span class="sxs-lookup"><span data-stu-id="52a56-104">Using XSD schemas</span></span>  
 <span data-ttu-id="52a56-105">`IDocumentSpec Interface`接口表示一个文档形状定义 XML 架构定义语言 (XSD) 架构; 形状已取得 root 权限通过 XSD 的顶级元素。</span><span class="sxs-lookup"><span data-stu-id="52a56-105">The `IDocumentSpec Interface` interface represents a document shape defined by an XML Schema definition language (XSD) schema; the shape is rooted by a top-level element of the XSD.</span></span> <span data-ttu-id="52a56-106">它通过调用安装架构后，可以进行检索`IPipelineContext.GetDocumentSpecByType Method`或`IPipelineContext.GetDocumentSpecByName Method`中的方法**IPipelineContext**接口。</span><span class="sxs-lookup"><span data-stu-id="52a56-106">After the schema is installed, it can be retrieved by calling the `IPipelineContext.GetDocumentSpecByType Method` or `IPipelineContext.GetDocumentSpecByName Method` methods in the **IPipelineContext** interface.</span></span>  
  
```  
IDocumentSpec docspec = pipeineContext.GetDocumentSpecByType("myschema#root");  
```  
  
## <a name="using-xsd-flat-file-schemas"></a><span data-ttu-id="52a56-107">使用 XSD 平面文件架构</span><span class="sxs-lookup"><span data-stu-id="52a56-107">Using XSD flat file schemas</span></span>  
 <span data-ttu-id="52a56-108">这两个**GetDocumentSpecByType**和**GetDocumentSpecByName**方法返回**IDocumentSpec**接口。</span><span class="sxs-lookup"><span data-stu-id="52a56-108">Both the **GetDocumentSpecByType** and **GetDocumentSpecByName** methods return the **IDocumentSpec** interface.</span></span> <span data-ttu-id="52a56-109">如果架构，则实际的平面文件架构 （一个包含其他平面文件特定批注），可以转换**IDocumentSpec**到**IFFDocumentSpec**并启动分析和序列化从该处的序列。</span><span class="sxs-lookup"><span data-stu-id="52a56-109">If the schema is actually a flat file schema (one that has additional flat file-specific annotations), you can typecast the **IDocumentSpec** into **IFFDocumentSpec** and initiate parsing and serializing sequences from there.</span></span>  
  
```  
IFFDocumentSpec docspec = (IFFDocumentSpec) pipeineContext.GetDocumentSpecByType("myschema#root");  
```  
  
## <a name="see-also"></a><span data-ttu-id="52a56-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="52a56-110">See Also</span></span>  

[<span data-ttu-id="52a56-111">使用了分析和序列化引擎</span><span class="sxs-lookup"><span data-stu-id="52a56-111">Using the Parsing and Serializing Engines</span></span>](../core/using-the-parsing-and-serializing-engines.md)