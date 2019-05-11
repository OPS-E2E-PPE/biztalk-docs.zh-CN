---
title: 文档验证 XML 拆装器管道组件中的 |Microsoft Docs
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
ms.openlocfilehash: 8015fdae6bce4b9ac163770d3909206f0325e7c7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350936"
---
# <a name="document-validation-in-the-xml-disassembler-pipeline-component"></a><span data-ttu-id="fd443-102">XML 拆装器管道组件中的文档验证</span><span class="sxs-lookup"><span data-stu-id="fd443-102">Document Validation in the XML Disassembler Pipeline Component</span></span>
<span data-ttu-id="fd443-103">默认情况下，XML 拆装器不会验证根据架构对 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="fd443-103">By default, the XML Disassembler does not validate XML documents against a schema.</span></span> <span data-ttu-id="fd443-104">但是，可以配置 XML 拆装器就可以通过设置验证 XML 文档**验证文档结构**属性。</span><span class="sxs-lookup"><span data-stu-id="fd443-104">However, you can configure the XML Disassembler to validate an XML document by setting the **Validate Document Structure** property.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="fd443-105">如果升级的字段用简单的数据类型声明，但包含复杂的数据，则属性升级将导致不可预知的结果。</span><span class="sxs-lookup"><span data-stu-id="fd443-105">If a field for promotion is declared with a simple data type but contains complex data, the property promotion will cause unpredictable results.</span></span> <span data-ttu-id="fd443-106">若要避免这种情况，配置 XML 拆装器执行文档验证通过设置**验证文档结构**属性设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="fd443-106">To avoid this scenario, configure the XML Disassembler to perform document validation by setting the **Validate Document Structure** property to **True**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd443-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="fd443-107">See Also</span></span>  
 <span data-ttu-id="fd443-108">[XML 拆装器管道组件](../core/xml-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="fd443-108">[XML Disassembler Pipeline Component](../core/xml-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="fd443-109">如何配置 XML 拆装器管道组件</span><span class="sxs-lookup"><span data-stu-id="fd443-109">How to Configure the XML Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)