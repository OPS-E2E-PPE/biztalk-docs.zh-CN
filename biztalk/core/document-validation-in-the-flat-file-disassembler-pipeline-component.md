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
# <a name="document-validation-in-the-flat-file-disassembler-pipeline-component"></a>平面文件反汇编程序管道组件中的文档验证
默认情况下，平面文件拆装器组件不会对所处理的文档进行验证。 但是，你可以打开验证通过设置**验证文档结构**到组件的属性**True**，或通过设置**FFDasm.ValidateDocumentStructure**消息上下文属性**True**。 如果设置运行文档验证，则平面文件拆装器将验证文档结构以及头部和尾部的结构，以确保符合文档、头部和尾部的架构。  
  
 平面文件反汇编程序可以删除空字段，并记录时**suppress_empty_nodes ="True"**指定**schemaInfo**平面文件 XSD 架构中的批注。 如果你使用**schemaInfo**以这种方式的批注，平面文件反汇编程序中移除空字段和而不考虑它们是否可选的记录。 如果使用 XML 验证，这可能会导致验证错误 (通过设置平面文件反汇编程序**验证文档结构**属性**True**或通过使用 XML 验证器管道组件). 如果发生验证错误，则会挂起消息。 有关 suppress_empty_nodes 属性的详细信息，请参阅[其他平面文件属性](../core/additional-flat-file-properties.md)。  
  
## <a name="see-also"></a>另请参阅  
 [平面文件反汇编程序管道组件](../core/flat-file-disassembler-pipeline-component.md)   
 [如何配置平面文件反汇编程序管道组件](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)   
 [管道 AssemblerDisassembler （BizTalk Server 示例文件夹中）](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)