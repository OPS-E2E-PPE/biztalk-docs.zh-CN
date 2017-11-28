---
title: "文档中的平面文件反汇编程序管道组件的验证 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Validate Document Structure property
- FFDasm.ValidateDocumentStructure property
- Flat File Disassembler [pipeline component], validating documents
- pipeline components, Flat File Disassembler
ms.assetid: 8cd777e4-8aba-4c17-92e8-958e5dd57d09
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 120d4664f922a653d0d532ca25213f3cb60a4e67
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="document-validation-in-the-flat-file-disassembler-pipeline-component"></a><span data-ttu-id="056fb-102">平面文件反汇编程序管道组件中的文档验证</span><span class="sxs-lookup"><span data-stu-id="056fb-102">Document Validation in the Flat File Disassembler Pipeline Component</span></span>
<span data-ttu-id="056fb-103">默认情况下，平面文件拆装器组件不会对所处理的文档进行验证。</span><span class="sxs-lookup"><span data-stu-id="056fb-103">By default, the Flat File Disassembler component does not validate documents it processes.</span></span> <span data-ttu-id="056fb-104">但是，你可以打开验证通过设置**验证文档结构**到组件的属性**True**，或通过设置**FFDasm.ValidateDocumentStructure**消息上下文属性**True**。</span><span class="sxs-lookup"><span data-stu-id="056fb-104">However, you can turn validation on by setting the **Validate document structure** property on the component to **True**, or by setting the **FFDasm.ValidateDocumentStructure** message context property to **True**.</span></span> <span data-ttu-id="056fb-105">如果设置运行文档验证，则平面文件拆装器将验证文档结构以及头部和尾部的结构，以确保符合文档、头部和尾部的架构。</span><span class="sxs-lookup"><span data-stu-id="056fb-105">When document validation is set to run, the Flat File Disassembler validates the document structure as well as the header and trailer structures to ensure that they conform to the document, header, and trailer schemas.</span></span>  
  
 <span data-ttu-id="056fb-106">平面文件反汇编程序可以删除空字段，并记录时**suppress_empty_nodes ="True"**指定**schemaInfo**平面文件 XSD 架构中的批注。</span><span class="sxs-lookup"><span data-stu-id="056fb-106">The Flat File Disassembler can remove empty fields and records when **suppress_empty_nodes="True"** is specified by the **schemaInfo** annotation in the flat file XSD schema.</span></span> <span data-ttu-id="056fb-107">如果你使用**schemaInfo**以这种方式的批注，平面文件反汇编程序中移除空字段和而不考虑它们是否可选的记录。</span><span class="sxs-lookup"><span data-stu-id="056fb-107">If you use the **schemaInfo** annotation in this way, the Flat File Disassembler removes empty fields and records regardless of whether they are optional.</span></span> <span data-ttu-id="056fb-108">如果使用 XML 验证，这可能会导致验证错误 (通过设置平面文件反汇编程序**验证文档结构**属性**True**或通过使用 XML 验证器管道组件).</span><span class="sxs-lookup"><span data-stu-id="056fb-108">This may cause validation errors if you use XML validation (either by setting the Flat File Disassembler **Validate document structure** property to **True** or by using the XML Validator pipeline component).</span></span> <span data-ttu-id="056fb-109">如果发生验证错误，则会挂起消息。</span><span class="sxs-lookup"><span data-stu-id="056fb-109">If a validation error occurs, the message is suspended.</span></span> <span data-ttu-id="056fb-110">有关 suppress_empty_nodes 属性的详细信息，请参阅[其他平面文件属性](../core/additional-flat-file-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="056fb-110">For more information about the suppress_empty_nodes property, see [Additional Flat File Properties](../core/additional-flat-file-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="056fb-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="056fb-111">See Also</span></span>  
 <span data-ttu-id="056fb-112">[平面文件反汇编程序管道组件](../core/flat-file-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="056fb-112">[Flat File Disassembler Pipeline Component](../core/flat-file-disassembler-pipeline-component.md) </span></span>  
 <span data-ttu-id="056fb-113">[如何配置平面文件反汇编程序管道组件](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="056fb-113">[How to Configure the Flat File Disassembler Pipeline Component](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="056fb-114">管道 AssemblerDisassembler （BizTalk Server 示例文件夹中）</span><span class="sxs-lookup"><span data-stu-id="056fb-114">Pipelines-AssemblerDisassembler (BizTalk Server Samples Folder)</span></span>](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)