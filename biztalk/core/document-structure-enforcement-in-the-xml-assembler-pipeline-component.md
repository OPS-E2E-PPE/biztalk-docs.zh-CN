---
title: "文档中的 XML 汇编程序管道组件的结构强制 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Add XML declaration property
- pipeline components, XML Assembler
ms.assetid: c121ec4b-c02b-4626-a5be-2937500dbefa
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e46dbc613439b24403c66c345b9023151b409213
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="document-structure-enforcement-in-the-xml-assembler-pipeline-component"></a><span data-ttu-id="4bb86-102">XML 汇编程序管道组件中的文档结构强制</span><span class="sxs-lookup"><span data-stu-id="4bb86-102">Document Structure Enforcement in the XML Assembler Pipeline Component</span></span>
<span data-ttu-id="4bb86-103">如果在 XML 组装器中显式引用文档或信封架构，则 XML 组装器可确保仅处理消息类型与所引用的架构相应的文档。</span><span class="sxs-lookup"><span data-stu-id="4bb86-103">If document or envelope schemas are explicitly referenced in the XML Assembler, the XML Assembler ensures that only documents with the message type corresponding to referenced schemas are processed.</span></span> <span data-ttu-id="4bb86-104">不会对其他所有文档进行处理，即使可能已为这些文档部署了架构也是如此。</span><span class="sxs-lookup"><span data-stu-id="4bb86-104">All the other documents are not processed even though a schema may be deployed for them.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4bb86-105">信封架构仅取自第一条消息。</span><span class="sxs-lookup"><span data-stu-id="4bb86-105">The envelope schema is taken from the first message only.</span></span> <span data-ttu-id="4bb86-106">信封的属性始终取自第一条消息。</span><span class="sxs-lookup"><span data-stu-id="4bb86-106">The properties for the envelope are always taken from the first message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bb86-107">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4bb86-107">See Also</span></span>  
 <span data-ttu-id="4bb86-108">[XML 汇编程序管道组件](../core/xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="4bb86-108">[XML Assembler Pipeline Component](../core/xml-assembler-pipeline-component.md) </span></span>  
 <span data-ttu-id="4bb86-109">[如何将 XML 汇编程序管道组件配置](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="4bb86-109">[How to Configure the XML Assembler Pipeline Component](../core/how-to-configure-the-xml-assembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="4bb86-110">管道 AssemblerDisassembler （BizTalk Server 示例文件夹中）</span><span class="sxs-lookup"><span data-stu-id="4bb86-110">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)