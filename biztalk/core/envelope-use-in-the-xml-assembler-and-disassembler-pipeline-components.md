---
title: 在 XML 组装器和拆装器管道组件中的使用信封 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a435b0f87eb955bc3534c2892894a3a13afdc13
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966454"
---
# <a name="envelope-use-in-the-xml-assembler-and-disassembler-pipeline-components"></a><span data-ttu-id="22520-102">在 XML 组装器和拆装器管道组件中使用信封</span><span class="sxs-lookup"><span data-stu-id="22520-102">Envelope Use in the XML Assembler and Disassembler Pipeline Components</span></span>
<span data-ttu-id="22520-103">XML 消息可以包含零个或多个信封。</span><span class="sxs-lookup"><span data-stu-id="22520-103">An XML message can include zero or more envelopes.</span></span> <span data-ttu-id="22520-104">下面的示例显示了一个包装 XML 文档的信封（以粗体显示）：</span><span class="sxs-lookup"><span data-stu-id="22520-104">The following example shows an envelope (in bold) wrapping an XML document.</span></span>  
  
```  
<ns1:document xmlns:ns1="http://myDocumentNamespaceURI.org">  
   <message>Hello</message>  
</ns1:document>  
  
```  
  
 <span data-ttu-id="22520-105">信封有两种用途：</span><span class="sxs-lookup"><span data-stu-id="22520-105">Envelopes serve two purposes:</span></span>  
  
- <span data-ttu-id="22520-106">它们可以包含用于属性升级和降级的字段值。</span><span class="sxs-lookup"><span data-stu-id="22520-106">They can include field values to use for property promotion and demotion.</span></span>  
  
   <span data-ttu-id="22520-107">XML 拆装器组件用于对属性进行升级，XML 组装器组件用于对属性进行降级。</span><span class="sxs-lookup"><span data-stu-id="22520-107">The XML Disassembler component promotes properties, and the XML Assembler component demotes properties.</span></span> <span data-ttu-id="22520-108">属性升级和降级也可以在 XML 文档中进行。</span><span class="sxs-lookup"><span data-stu-id="22520-108">Property promotion and demotion can also occur in XML documents.</span></span>  
  
- <span data-ttu-id="22520-109">它们可以将若干 XML 文档合并到单个交换中。</span><span class="sxs-lookup"><span data-stu-id="22520-109">They can combine several XML documents into a single interchange.</span></span>  
  
   <span data-ttu-id="22520-110">由于格式正确的 XML 文档只能有一个根元素，因此使用信封可以合并多个 XML 文档以共享一个根元素。</span><span class="sxs-lookup"><span data-stu-id="22520-110">Because a well-formed XML document can have only one root element, an envelope enables you to combine multiple XML documents to share one root element.</span></span>  
  
  <span data-ttu-id="22520-111">可以通过使用指定信封顺序强制使用规范格式**架构集合属性编辑器**对话框，通过单击省略号以访问此对话框**信封架构**XML 组装器中的设计时属性。</span><span class="sxs-lookup"><span data-stu-id="22520-111">You can enforce the canonical form by specifying the envelope order by using the **Schema Collection Property Editor** dialog which is accessed by clicking the ellipses for the **Envelope schemas** design-time property in the XML Assembler.</span></span> <span data-ttu-id="22520-112">此外可以使用**XMLNORM。EnvelopeSpecNames**运行 XML 组装器之前消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="22520-112">You can also use the **XMLNORM.EnvelopeSpecNames** message context property before the XML Assembler is run.</span></span> <span data-ttu-id="22520-113">XML 组装器以规范格式生成封装的文档。</span><span class="sxs-lookup"><span data-stu-id="22520-113">The XML Assembler produces an enveloped document in canonical form.</span></span>  
  
## <a name="nesting-envelopes"></a><span data-ttu-id="22520-114">嵌套信封</span><span class="sxs-lookup"><span data-stu-id="22520-114">Nesting envelopes</span></span>  
 <span data-ttu-id="22520-115">可以通过嵌套信封形成复杂的文档结构，在该结构中，可以将若干封装的 XML 文档合并到一个更大的交换中。</span><span class="sxs-lookup"><span data-stu-id="22520-115">You can nest envelopes to form complex document structures where several enveloped XML documents can be combined into a larger interchange.</span></span> <span data-ttu-id="22520-116">下面的示例显示了使用两个信封包装的交换：</span><span class="sxs-lookup"><span data-stu-id="22520-116">The following example shows an interchange wrapped by two envelopes.</span></span>  
  
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
  
 <span data-ttu-id="22520-117">上面的示例阐释了一种灵活的格式，该格式意味着文档可以与信封位于同一层次级别中。</span><span class="sxs-lookup"><span data-stu-id="22520-117">The preceding example illustrates a flexible form, which means that a document can be on the same hierarchy level as an envelope.</span></span> <span data-ttu-id="22520-118">在拆装封装的文档之后，将创建四个独立的文档（document1、document2，依此类推）。</span><span class="sxs-lookup"><span data-stu-id="22520-118">After disassembling the enveloped document, four separate documents are created (document1, document2, and so on).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22520-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="22520-119">See Also</span></span>  
 [<span data-ttu-id="22520-120">管道组件</span><span class="sxs-lookup"><span data-stu-id="22520-120">Pipeline Components</span></span>](../core/pipeline-components.md)