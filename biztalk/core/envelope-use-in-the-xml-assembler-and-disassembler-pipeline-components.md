---
title: "在 XML 汇编程序和反汇编程序管道组件中的信封使用 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XMLNorm.EnvelopeSpecNames property
- XML Disassembler [pipeline component], envelopes
- envelopes, nesting
- envelopes, XML Disassembler [pipeline component]
- envelopes, XML Assembler [pipeline component]
- XML Assembler [pipeline component], envelopes
- Envelope Specification Names property
ms.assetid: ccffd2f7-c7b1-4103-a914-ae9b4b19bee3
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0ae57a65bad84f3d46ceb27e9b5415dc3d1bc31
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="envelope-use-in-the-xml-assembler-and-disassembler-pipeline-components"></a><span data-ttu-id="92764-102">在 XML 汇编程序和反汇编程序管道组件中的信封使用</span><span class="sxs-lookup"><span data-stu-id="92764-102">Envelope Use in the XML Assembler and Disassembler Pipeline Components</span></span>
<span data-ttu-id="92764-103">XML 消息可以包含零个或多个信封。</span><span class="sxs-lookup"><span data-stu-id="92764-103">An XML message can include zero or more envelopes.</span></span> <span data-ttu-id="92764-104">下面的示例显示了一个包装 XML 文档的信封（以粗体显示）：</span><span class="sxs-lookup"><span data-stu-id="92764-104">The following example shows an envelope (in bold) wrapping an XML document.</span></span>  
  
```  
<ns1:document xmlns:ns1="http://myDocumentNamespaceURI.org">  
   <message>Hello</message>  
</ns1:document>  
  
```  
  
 <span data-ttu-id="92764-105">信封有两种用途：</span><span class="sxs-lookup"><span data-stu-id="92764-105">Envelopes serve two purposes:</span></span>  
  
-   <span data-ttu-id="92764-106">它们可以包含用于属性升级和降级的字段值。</span><span class="sxs-lookup"><span data-stu-id="92764-106">They can include field values to use for property promotion and demotion.</span></span>  
  
     <span data-ttu-id="92764-107">XML 拆装器组件用于对属性进行升级，XML 组装器组件用于对属性进行降级。</span><span class="sxs-lookup"><span data-stu-id="92764-107">The XML Disassembler component promotes properties, and the XML Assembler component demotes properties.</span></span> <span data-ttu-id="92764-108">属性升级和降级也可以在 XML 文档中进行。</span><span class="sxs-lookup"><span data-stu-id="92764-108">Property promotion and demotion can also occur in XML documents.</span></span>  
  
-   <span data-ttu-id="92764-109">它们可以将若干 XML 文档合并到单个交换中。</span><span class="sxs-lookup"><span data-stu-id="92764-109">They can combine several XML documents into a single interchange.</span></span>  
  
     <span data-ttu-id="92764-110">由于格式正确的 XML 文档只能有一个根元素，因此使用信封可以合并多个 XML 文档以共享一个根元素。</span><span class="sxs-lookup"><span data-stu-id="92764-110">Because a well-formed XML document can have only one root element, an envelope enables you to combine multiple XML documents to share one root element.</span></span>  
  
 <span data-ttu-id="92764-111">可以通过使用指定的信封顺序来强制规范格式**架构集合属性编辑器**对话框可通过单击为省略号**信封架构**在 XML 汇编程序的设计时属性。</span><span class="sxs-lookup"><span data-stu-id="92764-111">You can enforce the canonical form by specifying the envelope order by using the **Schema Collection Property Editor** dialog which is accessed by clicking the ellipses for the **Envelope schemas** design-time property in the XML Assembler.</span></span> <span data-ttu-id="92764-112">你还可以使用**XMLNORM。EnvelopeSpecNames**之前运行 XML 汇编程序消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="92764-112">You can also use the **XMLNORM.EnvelopeSpecNames** message context property before the XML Assembler is run.</span></span> <span data-ttu-id="92764-113">XML 组装器以规范格式生成封装的文档。</span><span class="sxs-lookup"><span data-stu-id="92764-113">The XML Assembler produces an enveloped document in canonical form.</span></span>  
  
## <a name="nesting-envelopes"></a><span data-ttu-id="92764-114">嵌套信封</span><span class="sxs-lookup"><span data-stu-id="92764-114">Nesting envelopes</span></span>  
 <span data-ttu-id="92764-115">可以通过嵌套信封形成复杂的文档结构，在该结构中，可以将若干封装的 XML 文档合并到一个更大的交换中。</span><span class="sxs-lookup"><span data-stu-id="92764-115">You can nest envelopes to form complex document structures where several enveloped XML documents can be combined into a larger interchange.</span></span> <span data-ttu-id="92764-116">下面的示例显示了使用两个信封包装的交换：</span><span class="sxs-lookup"><span data-stu-id="92764-116">The following example shows an interchange wrapped by two envelopes.</span></span>  
  
```  
<envelope1>  
   <document1/>  
   <envelope2>  
      <document2/>  
      <document3/>  
   </envelope2>  
   <document4/>  
</envelope1>  
```  
  
 <span data-ttu-id="92764-117">上面的示例阐释了一种灵活的格式，该格式意味着文档可以与信封位于同一层次级别中。</span><span class="sxs-lookup"><span data-stu-id="92764-117">The preceding example illustrates a flexible form, which means that a document can be on the same hierarchy level as an envelope.</span></span> <span data-ttu-id="92764-118">在拆装封装的文档之后，将创建四个独立的文档（document1、document2，依此类推）。</span><span class="sxs-lookup"><span data-stu-id="92764-118">After disassembling the enveloped document, four separate documents are created (document1, document2, and so on).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92764-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="92764-119">See Also</span></span>  
 [<span data-ttu-id="92764-120">管道组件</span><span class="sxs-lookup"><span data-stu-id="92764-120">Pipeline Components</span></span>](../core/pipeline-components.md)