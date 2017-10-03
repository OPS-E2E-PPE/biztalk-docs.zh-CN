---
title: "数据转换配置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XSLT
- maps, compiling
- Source Links property
- BizTalk Mapper, compiler directives
- code samples, XSLT
- compiler directives, copy text and subcontentent value
- compiler directives, copy text value
- maps, XSLT
- compiler directives, copy name
- compiler directives
- maps, code sample [XSLT]
- XSLT, code samples
ms.assetid: 05abe091-5202-4590-99ec-e60ca53a4324
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8304d43f59f63e474a3257915521d5dc36c38d30
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="data-transformation-configuration"></a>数据转换配置
当映射的元素中，典型的可扩展样式表语言转换 (XSLT) 将如下所示。  
  
```  
<xsl:attribute name='CatalogPurposeCode'>  
     <xsl:value-of select='BCT/BCT01/text()'/>  
</xsl:attribute>  
```  
  
 如果元素**BCT01**包含混合内容，使用 text （） 会使它可以访问仅第一个子元素，直到第一个文本如果有的话。 如果未在此 XSLT 语句中使用 text （），结果将是所有文本内容，加上任何文本内容的子元素，将映射为一个文本字符串。 配置**源链接**用于链接的属性可以控制复制到目标架构中定义的结构的数据源。  
  
 当显示的网格页中选择一个链接时，其中一个属性显示在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口是**源链接**属性。 你可以选择你的代码图中每个链接以下可能的值：  
  
-   **复制文本值。** 使用此值（默认值）可复制输入实例消息中的元素或属性值。 例如，如果相关元素为 BoldExample，如下如示：  
  
    ```  
    <BoldExample>This is a <B>Bold Text</B> example.</BoldExample>  
    ```  
  
     则复制到输出实例消息中的相关元素或属性的值为“This is a ”。 对于这样的混合内容，结果可能不是所期望的内容。 但是，由于混合内容的元素都是相对很少，**复制文本值**设置**源链接**属性是在大多数情况下可能适用。  
  
-   **复制名称。** 使用此值可复制输入实例消息中的节点名称。 对于中的示例**复制文本值**说明，结果为"BoldExample"，这是元素的实际名称。  
  
-   **将文本复制和子内容的值。** 使用此值可将输入实例消息中的节点值及其子节点中的所有值连接到一起。 对于中的示例**复制文本值**说明，结果是"这是显示为粗体文本示例。"，这很好地可能会定义为包含混合的内容的元素的相应结果。  
  
## <a name="see-also"></a>另请参阅  
 [大容量复制 Functoid](../core/mass-copy-functoid.md)   
 [如何将源链接编译器值设置](../core/how-to-set-the-source-links-compiler-value.md)   
 [节点层次结构级别匹配](../core/node-hierarchy-level-matching.md)