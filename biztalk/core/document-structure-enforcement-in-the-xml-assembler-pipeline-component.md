---
title: 文档结构强制规定在 XML 组装器管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Add XML declaration property
- pipeline components, XML Assembler
ms.assetid: c121ec4b-c02b-4626-a5be-2937500dbefa
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ef167df5aaef827e11d33fc73191d46b68afb2c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389527"
---
# <a name="document-structure-enforcement-in-the-xml-assembler-pipeline-component"></a><span data-ttu-id="e2604-102">XML 组装器管道组件中的文档结构强制规定</span><span class="sxs-lookup"><span data-stu-id="e2604-102">Document Structure Enforcement in the XML Assembler Pipeline Component</span></span>
<span data-ttu-id="e2604-103">如果在 XML 组装器中显式引用文档或信封架构，XML 组装器可确保与对应于引用的架构的消息类型的唯一文档进行处理。</span><span class="sxs-lookup"><span data-stu-id="e2604-103">If document or envelope schemas are explicitly referenced in the XML Assembler, the XML Assembler ensures that only documents with the message type corresponding to referenced schemas are processed.</span></span> <span data-ttu-id="e2604-104">不会对其他所有文档进行处理，即使可能已为这些文档部署了架构也是如此。</span><span class="sxs-lookup"><span data-stu-id="e2604-104">All the other documents are not processed even though a schema may be deployed for them.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e2604-105">信封架构仅取自第一条消息。</span><span class="sxs-lookup"><span data-stu-id="e2604-105">The envelope schema is taken from the first message only.</span></span> <span data-ttu-id="e2604-106">信封的属性始终取自第一条消息。</span><span class="sxs-lookup"><span data-stu-id="e2604-106">The properties for the envelope are always taken from the first message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2604-107">请参阅</span><span class="sxs-lookup"><span data-stu-id="e2604-107">See Also</span></span>  
 <span data-ttu-id="e2604-108">[XML 组装器管道组件](../core/xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="e2604-108">[XML Assembler Pipeline Component](../core/xml-assembler-pipeline-component.md) </span></span>  
 <span data-ttu-id="e2604-109">[如何配置 XML 组装器管道组件](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="e2604-109">[How to Configure the XML Assembler Pipeline Component](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="e2604-110">Pipelines-AssemblerDisassembler（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="e2604-110">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)