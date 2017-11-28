---
title: "分析模式 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], code samples
- pipeline components [custom], parsing
ms.assetid: b1188720-e5ae-47ae-ab8e-16d7ed08b778
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf8f9b2618b8cafd7813f08217457227a0f21809
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="parsing-modes"></a><span data-ttu-id="8b420-102">分析模式</span><span class="sxs-lookup"><span data-stu-id="8b420-102">Parsing Modes</span></span>
<span data-ttu-id="8b420-103">分析模式是一个属性的 schemaInfo 记录，两种模式： 速度和复杂性。</span><span class="sxs-lookup"><span data-stu-id="8b420-103">The parsing mode is an attribute on the schemaInfo record, with two modes: speed and complexity.</span></span> <span data-ttu-id="8b420-104">在 BizTalk 架构编辑器中，可以配置分析器优化属性。</span><span class="sxs-lookup"><span data-stu-id="8b420-104">The Parser Optimization property can be configured within the BizTalk Schema Editor.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b420-105">示例</span><span class="sxs-lookup"><span data-stu-id="8b420-105">Example</span></span>  
  
```  
<b:schemaInfo count_positions_by_byte="false" standard="Flat File"   
root_reference="document" parser_optimization="complexity" />.  
```  
  
 <span data-ttu-id="8b420-106">在速度模式下，分析器将尝试在流中显示适合数据。</span><span class="sxs-lookup"><span data-stu-id="8b420-106">In speed mode, the parser tries to fit data as they appear in the stream.</span></span> <span data-ttu-id="8b420-107">例如，给定以下架构。</span><span class="sxs-lookup"><span data-stu-id="8b420-107">For example, given the following schema.</span></span>  
  
```  
<schema>  
   Root ("," prefix)  
      Field1   opt  
      Field2   opt  
      Field3   opt  
      Field4   opt  
      Record ("," infix)  
            Field5  
            Field6  
</schema>  
```  
  
 <span data-ttu-id="8b420-108">和输入的消息。</span><span class="sxs-lookup"><span data-stu-id="8b420-108">and input message.</span></span>  
  
```  
,1,2,3,4  
```  
  
 <span data-ttu-id="8b420-109">速度模式下下面的 XML 文档被获得。</span><span class="sxs-lookup"><span data-stu-id="8b420-109">with speed mode the following XML document is obtained.</span></span>  
  
```  
<Root>  
   <Field1>1</Field1>  
   <Field2>2</Field2>  
   <Field3>3</Field3>  
   <Field4>4</Field4>  
</Root>  
```  
  
 <span data-ttu-id="8b420-110">复杂性模式中，相同的架构生成以下输出。</span><span class="sxs-lookup"><span data-stu-id="8b420-110">With complexity mode, the same schema produces the following output.</span></span>  
  
```  
<Root>  
   <Field1>1</Field1>  
   <Field2>2</Field2>  
      <Record>  
         <Field5>3</Field5>  
         <Field6>4</Field6>  
      </Record>  
</Root>  
```  
  
 <span data-ttu-id="8b420-111">在复杂性模式下，平面文件分析引擎使用自顶向下和自下而上的分析过程中，并尝试以更准确地适应数据。</span><span class="sxs-lookup"><span data-stu-id="8b420-111">In complexity mode, the flat file parsing engine uses both top-down and bottom-up parsing, and tries to fit data more accurately.</span></span> <span data-ttu-id="8b420-112">在速度模式下，分析器将尝试在流中显示适合数据。</span><span class="sxs-lookup"><span data-stu-id="8b420-112">In speed mode, the parser tries to fit data as they appear in the stream.</span></span>  
  
 <span data-ttu-id="8b420-113">如果例如具有具有必需的元素的可选元素。</span><span class="sxs-lookup"><span data-stu-id="8b420-113">If you have optional elements with required elements, for example.</span></span>  
  
```  
<schema>  
   Root  
      Record1 (required)  
  
      Record2 (optional)  
  
      Record3 (required)  
  
```  
  
 <span data-ttu-id="8b420-114">你必须使用复杂性模式来正确分析数据，因为分析器表示的架构内部作为。</span><span class="sxs-lookup"><span data-stu-id="8b420-114">you must use complexity mode to correctly parse the data, because the parser represents the schema internally as.</span></span>  
  
```  
<schema>  
   Root  
      Record1 (required)  
      <sequence> (optional)  
         Record2 (required)  
         Record3 (required)  
```  
  
## <a name="see-also"></a><span data-ttu-id="8b420-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8b420-115">See Also</span></span>  
 [<span data-ttu-id="8b420-116">使用平面文件分析引擎</span><span class="sxs-lookup"><span data-stu-id="8b420-116">Using the Flat File Parsing Engine</span></span>](../core/using-the-flat-file-parsing-engine.md)