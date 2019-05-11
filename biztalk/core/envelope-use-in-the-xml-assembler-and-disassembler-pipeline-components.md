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
# <a name="envelope-use-in-the-xml-assembler-and-disassembler-pipeline-components"></a>在 XML 组装器和拆装器管道组件中使用信封
一条 XML 消息可以包含零个或多个信封。 下面的示例显示了信封包装 XML 文档 （以粗体显示）。  
  
```  
<ns1:document xmlns:ns1="http://myDocumentNamespaceURI.org">  
   <message>Hello</message>  
</ns1:document>  
  
```  
  
 信封有两种用途：  
  
- 它们可以包括要用于属性升级和降级的字段值。  
  
   XML 拆装器组件将升级属性和 XML 组装器组件将降级属性。 属性升级和降级也会出现在 XML 文档中。  
  
- 它们可以将多个 XML 文档合并到单个交换。  
  
   格式正确的 XML 文档只能有一个根元素，因为信封可以合并多个 XML 文档以共享一个根元素。  
  
  可以通过使用指定信封顺序强制使用规范格式**架构集合属性编辑器**对话框，通过单击省略号以访问此对话框**信封架构**XML 组装器中的设计时属性。 此外可以使用**XMLNORM。EnvelopeSpecNames**运行 XML 组装器之前消息上下文属性。 XML 组装器生成采用规范格式封装的文档。  
  
## <a name="nesting-envelopes"></a>嵌套信封  
 可以通过嵌套的信封到窗体复杂的文档结构，可以将若干封装的 XML 文档合并到更大的交换。 下面的示例演示两个信封包装的交换。  
  
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
  
 前面的示例说明了灵活的窗体，这意味着文档可以与信封相同的层次结构级别。 在拆装封装的文档后, 四个单独的文档 （document1、 document2，等） 创建。  
  
## <a name="see-also"></a>请参阅  
 [管道组件](../core/pipeline-components.md)