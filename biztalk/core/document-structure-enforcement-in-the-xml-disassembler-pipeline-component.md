---
title: 文档结构强制规定在 XML 拆装器管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML Disassembler [pipeline component], document structure
- pipeline components, XML Disassembler
ms.assetid: ac405bf2-f92b-4b45-8256-dd188ec9510a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7e4c7d2d99874684d80c7c413040d7da8ecf0b8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350916"
---
# <a name="document-structure-enforcement-in-the-xml-disassembler-pipeline-component"></a><span data-ttu-id="8f3b1-102">XML 拆装器管道组件中的文档结构强制规定</span><span class="sxs-lookup"><span data-stu-id="8f3b1-102">Document Structure Enforcement in the XML Disassembler Pipeline Component</span></span>
<span data-ttu-id="8f3b1-103">如果在 XML 拆装器中显式引用文档或信封架构，XML 拆装器与符合架构的消息类型处理仅这些文档。</span><span class="sxs-lookup"><span data-stu-id="8f3b1-103">If a document or envelope schema is explicitly referenced in the XML Disassembler, the XML Disassembler processes only those documents with message types conforming to the schema.</span></span> <span data-ttu-id="8f3b1-104">不处理任何其他文档，而不考虑它们是否引用了已部署的架构。</span><span class="sxs-lookup"><span data-stu-id="8f3b1-104">No other documents are processed, regardless of whether a deployed schema is referenced for them.</span></span>  
  
 <span data-ttu-id="8f3b1-105">XML 拆装器强制实施的信封架构; 指定的顺序但是，文档架构的顺序不强制执行。</span><span class="sxs-lookup"><span data-stu-id="8f3b1-105">The XML Disassembler enforces the specified order of envelope schemas; however, the order of document schemas is not enforced.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f3b1-106">请参阅</span><span class="sxs-lookup"><span data-stu-id="8f3b1-106">See Also</span></span>  
 <span data-ttu-id="8f3b1-107">[XML 拆装器管道组件](../core/xml-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="8f3b1-107">[XML Disassembler Pipeline Component](../core/xml-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="8f3b1-108">如何配置 XML 拆装器管道组件</span><span class="sxs-lookup"><span data-stu-id="8f3b1-108">How to Configure the XML Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)