---
title: 文档中的 XML 反汇编程序管道组件的验证 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Validate Document Structure property
- pipeline components, XML Disassembler
- XML Disassembler [pipeline component], document validation
- XML Disassembler [pipeline component], warnings
ms.assetid: feb25033-46d3-48ed-8e1f-0cd123e94149
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2dcea790208bf0234c67c8c941e6355fb367d82
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239381"
---
# <a name="document-validation-in-the-xml-disassembler-pipeline-component"></a><span data-ttu-id="313b7-102">XML 反汇编程序管道组件中的文档验证</span><span class="sxs-lookup"><span data-stu-id="313b7-102">Document Validation in the XML Disassembler Pipeline Component</span></span>
<span data-ttu-id="313b7-103">默认情况下，XML 拆装器不会根据架构验证 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="313b7-103">By default, the XML Disassembler does not validate XML documents against a schema.</span></span> <span data-ttu-id="313b7-104">但是，你可以配置 XML 反汇编程序，以通过设置验证 XML 文档**验证文档结构**属性。</span><span class="sxs-lookup"><span data-stu-id="313b7-104">However, you can configure the XML Disassembler to validate an XML document by setting the **Validate Document Structure** property.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="313b7-105">如果要升级的字段声明为简单数据类型，但包含复杂数据，则属性升级将导致不可预知的结果。</span><span class="sxs-lookup"><span data-stu-id="313b7-105">If a field for promotion is declared with a simple data type but contains complex data, the property promotion will cause unpredictable results.</span></span> <span data-ttu-id="313b7-106">若要避免这种情况下，配置 XML 反汇编程序，通过设置执行文档验证**验证文档结构**属性**True**。</span><span class="sxs-lookup"><span data-stu-id="313b7-106">To avoid this scenario, configure the XML Disassembler to perform document validation by setting the **Validate Document Structure** property to **True**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="313b7-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="313b7-107">See Also</span></span>  
 <span data-ttu-id="313b7-108">[XML 反汇编程序管道组件](../core/xml-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="313b7-108">[XML Disassembler Pipeline Component](../core/xml-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="313b7-109">如何将 XML 反汇编程序管道组件配置</span><span class="sxs-lookup"><span data-stu-id="313b7-109">How to Configure the XML Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)