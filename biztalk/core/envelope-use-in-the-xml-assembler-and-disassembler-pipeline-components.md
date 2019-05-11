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
ms.openlocfilehash: 9841a9abcf188623afb46c8387d42c94982d0119
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389066"
---
# <a name="envelope-use-in-the-xml-assembler-and-disassembler-pipeline-components"></a><span data-ttu-id="a0d9f-102">在 XML 组装器和拆装器管道组件中使用信封</span><span class="sxs-lookup"><span data-stu-id="a0d9f-102">Envelope Use in the XML Assembler and Disassembler Pipeline Components</span></span>
<span data-ttu-id="a0d9f-103">一条 XML 消息可以包含零个或多个信封。</span><span class="sxs-lookup"><span data-stu-id="a0d9f-103">An XML message can include zero or more envelopes.</span></span> <span data-ttu-id="a0d9f-104">下面的示例显示了信封包装 XML 文档 （以粗体显示）。</span><span class="sxs-lookup"><span data-stu-id="a0d9f-104">The following example shows an envelope (in bold) wrapping an XML document.</span></span>  
  
```  
<ns1:document xmlns:ns1="http://myDocumentNamespaceURI.org">  
   <message>Hello</message>  
</ns1:document>  
  
```  
  
 <span data-ttu-id="a0d9f-105">信封有两种用途：</span><span class="sxs-lookup"><span data-stu-id="a0d9f-105">Envelopes serve two purposes:</span></span>  
  
- <span data-ttu-id="a0d9f-106">它们可以包括要用于属性升级和降级的字段值。</span><span class="sxs-lookup"><span data-stu-id="a0d9f-106">They can include field values to use for property promotion and demotion.</span></span>  
  
   <span data-ttu-id="a0d9f-107">XML 拆装器组件将升级属性和 XML 组装器组件将降级属性。</span><span class="sxs-lookup"><span data-stu-id="a0d9f-107">The XML Disassembler component promotes properties, and the XML Assembler component demotes properties.</span></span> <span data-ttu-id="a0d9f-108">属性升级和降级也会出现在 XML 文档中。</span><span class="sxs-lookup"><span data-stu-id="a0d9f-108">Property promotion and demotion can also occur in XML documents.</span></span>  
  
- <span data-ttu-id="a0d9f-109">它们可以将多个 XML 文档合并到单个交换。</span><span class="sxs-lookup"><span data-stu-id="a0d9f-109">They can combine several XML documents into a single interchange.</span></span>  
  
   <span data-ttu-id="a0d9f-110">格式正确的 XML 文档只能有一个根元素，因为信封可以合并多个 XML 文档以共享一个根元素。</span><span class="sxs-lookup"><span data-stu-id="a0d9f-110">Because a well-formed XML document can have only one root element, an envelope enables you to combine multiple XML documents to share one root element.</span></span>  
  
  <span data-ttu-id="a0d9f-111">可以通过使用指定信封顺序强制使用规范格式**架构集合属性编辑器**对话框，通过单击省略号以访问此对话框**信封架构**XML 组装器中的设计时属性。</span><span class="sxs-lookup"><span data-stu-id="a0d9f-111">You can enforce the canonical form by specifying the envelope order by using the **Schema Collection Property Editor** dialog which is accessed by clicking the ellipses for the **Envelope schemas** design-time property in the XML Assembler.</span></span> <span data-ttu-id="a0d9f-112">此外可以使用**XMLNORM。EnvelopeSpecNames**运行 XML 组装器之前消息上下文属性。</span><span class="sxs-lookup"><span data-stu-id="a0d9f-112">You can also use the **XMLNORM.EnvelopeSpecNames** message context property before the XML Assembler is run.</span></span> <span data-ttu-id="a0d9f-113">XML 组装器生成采用规范格式封装的文档。</span><span class="sxs-lookup"><span data-stu-id="a0d9f-113">The XML Assembler produces an enveloped document in canonical form.</span></span>  
  
## <a name="nesting-envelopes"></a><span data-ttu-id="a0d9f-114">嵌套信封</span><span class="sxs-lookup"><span data-stu-id="a0d9f-114">Nesting envelopes</span></span>  
 <span data-ttu-id="a0d9f-115">可以通过嵌套的信封到窗体复杂的文档结构，可以将若干封装的 XML 文档合并到更大的交换。</span><span class="sxs-lookup"><span data-stu-id="a0d9f-115">You can nest envelopes to form complex document structures where several enveloped XML documents can be combined into a larger interchange.</span></span> <span data-ttu-id="a0d9f-116">下面的示例演示两个信封包装的交换。</span><span class="sxs-lookup"><span data-stu-id="a0d9f-116">The following example shows an interchange wrapped by two envelopes.</span></span>  
  
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
  
 <span data-ttu-id="a0d9f-117">前面的示例说明了灵活的窗体，这意味着文档可以与信封相同的层次结构级别。</span><span class="sxs-lookup"><span data-stu-id="a0d9f-117">The preceding example illustrates a flexible form, which means that a document can be on the same hierarchy level as an envelope.</span></span> <span data-ttu-id="a0d9f-118">在拆装封装的文档后, 四个单独的文档 （document1、 document2，等） 创建。</span><span class="sxs-lookup"><span data-stu-id="a0d9f-118">After disassembling the enveloped document, four separate documents are created (document1, document2, and so on).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0d9f-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="a0d9f-119">See Also</span></span>  
 [<span data-ttu-id="a0d9f-120">管道组件</span><span class="sxs-lookup"><span data-stu-id="a0d9f-120">Pipeline Components</span></span>](../core/pipeline-components.md)