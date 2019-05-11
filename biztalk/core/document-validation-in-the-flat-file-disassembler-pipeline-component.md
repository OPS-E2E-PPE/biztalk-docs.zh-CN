---
title: 文档中的平面文件拆装器管道组件的验证 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Validate Document Structure property
- FFDasm.ValidateDocumentStructure property
- Flat File Disassembler [pipeline component], validating documents
- pipeline components, Flat File Disassembler
ms.assetid: 8cd777e4-8aba-4c17-92e8-958e5dd57d09
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43802cde810d9803daa80ee8c070aecd8023eb57
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530815"
---
# <a name="document-validation-in-the-flat-file-disassembler-pipeline-component"></a>平面文件拆装器管道组件中的文档验证
默认情况下，平面文件拆装器组件不会验证处理的文档进行。 但是，您可以打开验证通过设置**验证文档结构**到组件的属性**True**，或通过设置**FFDasm.ValidateDocumentStructure**消息上下文属性设置为 **，则返回 True**。 当文档验证设置运行时，平面文件拆装器将验证文档结构，以及标头和尾部结构，以确保它们符合文档、 标头和尾部架构。  
  
 平面文件拆装器可以删除空的字段和记录**suppress_empty_nodes ="True"** 通过指定**schemaInfo**平面文件 XSD 架构中的批注。 如果您使用**schemaInfo**这种方式中的批注，平面文件拆装器中删除空字段和记录而不考虑它们是否可选。 如果您使用 XML 验证，这可能会导致验证错误 (通过设置平面文件拆装器**验证文档结构**属性设置为**True**或通过使用 XML 验证器管道组件). 如果发生验证错误，则挂起消息。 有关 suppress_empty_nodes 属性的详细信息，请参阅[其他平面文件属性](../core/additional-flat-file-properties.md)。  
  
## <a name="see-also"></a>请参阅  
 [平面文件拆装器管道组件](../core/flat-file-disassembler-pipeline-component.md)   
 [如何配置平面文件拆装器管道组件](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)   
 [Pipelines-AssemblerDisassembler（BizTalk Server 示例文件夹）](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)