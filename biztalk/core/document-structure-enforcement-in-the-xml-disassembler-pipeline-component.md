---
title: 文档中的 XML 反汇编程序管道组件的结构强制 |Microsoft 文档
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
ms.openlocfilehash: 9e14b20292b23a0f50362940e3b873fa37a3f5bd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22238501"
---
# <a name="document-structure-enforcement-in-the-xml-disassembler-pipeline-component"></a><span data-ttu-id="c6890-102">XML 反汇编程序管道组件中的文档结构强制</span><span class="sxs-lookup"><span data-stu-id="c6890-102">Document Structure Enforcement in the XML Disassembler Pipeline Component</span></span>
<span data-ttu-id="c6890-103">如果在 XML 拆装器中显式引用文档架构或信封架构，则 XML 拆装器只处理消息类型符合该架构的文档。</span><span class="sxs-lookup"><span data-stu-id="c6890-103">If a document or envelope schema is explicitly referenced in the XML Disassembler, the XML Disassembler processes only those documents with message types conforming to the schema.</span></span> <span data-ttu-id="c6890-104">其他文档均不处理，而不管是否为其引用了已部署的架构。</span><span class="sxs-lookup"><span data-stu-id="c6890-104">No other documents are processed, regardless of whether a deployed schema is referenced for them.</span></span>  
  
 <span data-ttu-id="c6890-105">XML 拆装器强制要求指定的信封架构顺序；但不强制要求文档架构的顺序。</span><span class="sxs-lookup"><span data-stu-id="c6890-105">The XML Disassembler enforces the specified order of envelope schemas; however, the order of document schemas is not enforced.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6890-106">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c6890-106">See Also</span></span>  
 <span data-ttu-id="c6890-107">[XML 反汇编程序管道组件](../core/xml-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="c6890-107">[XML Disassembler Pipeline Component](../core/xml-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="c6890-108">如何将 XML 反汇编程序管道组件配置</span><span class="sxs-lookup"><span data-stu-id="c6890-108">How to Configure the XML Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)