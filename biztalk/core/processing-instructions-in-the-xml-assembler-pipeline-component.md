---
title: XML 组装器管道组件中的处理指令 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XMLNorm.ProcessingInstructionOption property
- envelopes, processing instructions
- XML Assembler [pipeline component], processing instructions
- Processing instruction scope property
- XMLNorm.ProcessingInstruction property
- envelopes, XML Assembler [pipeline component]
- pipeline components, XML Assembler
ms.assetid: d8ea453e-3b20-417d-bf25-9d424b0150fd
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df3b56a3703e56dd4b3f474b4846999bae9858f0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37016103"
---
# <a name="processing-instructions-in-the-xml-assembler-pipeline-component"></a>XML 组装器管道组件中的处理指令
处理指令向处理 XML 文档的应用程序提供信息。 这些信息可能包括有关如何处理文档、如何显示文档等的指令。  
  
 处理指令添加到 XML 文档由**添加处理指令**属性 (或等效**XMLNorm.ProcessingInstructionOption**消息上下文属性)。 处理指令文本与指定**添加处理指令文本**属性 (或等效**XMLNorm.ProcessingInstruction**消息上下文属性)。  
  
 **添加处理指令**属性 (或**XMLNorm.ProcessingInstructionOption**属性) 具有三个可能的值，如下表所述。  
  
|ReplTest1|ReplTest1|Description|  
|-----------|-----------|-----------------|  
|追加|0|将 XML 组装器中的新处理指令附加到文档开头处的处理指令。|  
|创建新的|@shouldalert|XML 组装器中的新处理指令将覆盖文档开头处的现有处理指令。|  
|Ignore|2|将删除文档开头处的处理指令。|  
  
 消息上下文中指定的处理指令对（或消息上下文属性）的优先级高于管道设计器中指定的属性对。 例如，如果**XMLNorm.ProcessingInstructionOption**指定为**新建**(1) 和**XMLNorm.ProcessingInstruction**未指定，则为空处理指令将替换现有的处理指令。  
  
 另举一例，如果**XMLNorm.ProcessingInstruction**指定但**XMLNorm.ProcessingInstructionOption**不使用任何从消息上下文属性。 在这种情况下，将使用管道设计器中的处理指令。  
  
 默认情况下**添加处理指令**设置为**追加**，并**添加处理指令文本**为空。  
  
## <a name="processing-properties-and-envelopes"></a>处理属性和信封  
 由于对信封不保留处理指令，因此以下组合的平面文件组装器设置导致只有最外层信封才具有处理指令：  
  
- **处理指令作用域**属性设置为"Envelope"。  
  
- **添加处理指令**属性设置为"附加"。  
  
  信封将使用在组装器中指定的处理指令**添加处理指令文本**属性。  
  
  传入消息中所指定的外层信封或内层信封中的任何现有处理指令都不会出现在输出消息中。  
  
## <a name="see-also"></a>请参阅  
 [XML 组装器管道组件](../core/xml-assembler-pipeline-component.md)   
 [如何配置 XML 组装器管道组件](../core/how-to-configure-the-xml-assembler-pipeline-component.md)   
 [Pipelines-AssemblerDisassembler（BizTalk Server 示例文件夹）](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)