---
title: 数据转换配置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 017f5b38c30acd37728fc1834ff39b3125f4f07f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352702"
---
# <a name="data-transformation-configuration"></a>数据转换配置
映射用于从元素，典型的可扩展样式表语言转换 (XSLT) 如下所示。  
  
```  
<xsl:attribute name='CatalogPurposeCode'>  
     <xsl:value-of select='BCT/BCT01/text()'/>  
</xsl:attribute>  
```  
  
 如果该元素**BCT01**包含混合内容，使用 text （） 就可访问仅第一个子元素，直到第一个文本如果有的话。 如果未在此 XSLT 语句中使用 text （），结果将是所有文本内容，加上任何文本内容的子元素将映射为一个文本字符串。 配置**源链接**属性的链接，可控制将被复制到目标架构所定义的结构的数据源。  
  
 当在显示的网格页中选择一个链接时，其中一个属性显示在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口是**源链接**属性。 你可以选择以下可能值为在映射中每个链接：  
  
-   **复制文本值。** 使用此值，该值为默认值，输入的实例消息中复制的元素或属性的值。 例如，如果相关元素为 BoldExample，如下所示：  
  
    ```  
    <BoldExample>This is a <B>Bold Text</B> example.</BoldExample>  
    ```  
  
     值复制到相关的元素或输出实例消息中的属性是"这是"。 对于此类的混合内容元素，此结果可能不是正确的结果。 但是，由于混合内容元素都是相对较少**复制文本值**设置为**源链接**适合属性可能在大多数情况下。  
  
-   **复制名称。** 使用此值复制输入的实例消息中的节点的名称。 对于中的示例**复制文本值**说明，结果为"BoldExample"，这是元素的实际名称。  
  
-   **复制文本和子内容值。** 此值用于连接的节点值和子节点输入的实例消息中的所有值。 对于中的示例**复制文本值**说明，结果为"This is"，这可能很好地定义为包含混合的内容的元素的相应结果。 Bold Text example。  
  
## <a name="see-also"></a>请参阅  
 [批量复制 Functoid](../core/mass-copy-functoid.md)   
 [如何设置源链接编译器值](../core/how-to-set-the-source-links-compiler-value.md)   
 [节点层次结构级匹配](../core/node-hierarchy-level-matching.md)