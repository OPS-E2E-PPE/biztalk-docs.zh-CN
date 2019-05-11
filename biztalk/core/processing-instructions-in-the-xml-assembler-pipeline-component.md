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
ms.openlocfilehash: 3366ed738020ebf90fadfb104f860f0cdb952168
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396990"
---
# <a name="processing-instructions-in-the-xml-assembler-pipeline-component"></a>XML 组装器管道组件中的处理指令
处理指令提供给处理 XML 文档的应用程序的信息。 此类信息可能包括有关如何处理文档，说明如何显示它，依次类推。  
  
 处理指令添加到 XML 文档由**添加处理指令**属性 (或等效**XMLNorm.ProcessingInstructionOption**消息上下文属性)。 处理指令文本与指定**添加处理指令文本**属性 (或等效**XMLNorm.ProcessingInstruction**消息上下文属性)。  
  
 **添加处理指令**属性 (或**XMLNorm.ProcessingInstructionOption**属性) 具有三个可能的值，如下表所述。  
  
|ReplTest1|ReplTest1|Description|  
|-----------|-----------|-----------------|  
|追加|0|XML 组装器中的新处理指令将追加到文档的开头处的处理指令。|  
|创建新的|1|XML 组装器中的新处理指令将覆盖现有开头处的文档的处理指令。|  
|Ignore|2|删除文档的开头处的处理指令。|  
  
 对处理说明 （或消息上下文属性） 的消息上下文中指定的优先级高于管道设计器中指定的属性对。 例如，如果**XMLNorm.ProcessingInstructionOption**指定为**新建**(1) 和**XMLNorm.ProcessingInstruction**未指定，则为空处理指令将替换现有的处理指令。  
  
 另举一例，如果**XMLNorm.ProcessingInstruction**指定但**XMLNorm.ProcessingInstructionOption**不使用任何从消息上下文属性。 在这种情况下，使用管道设计器中的处理指令。  
  
 默认情况下**添加处理指令**设置为**追加**，并**添加处理指令文本**为空。  
  
## <a name="processing-properties-and-envelopes"></a>处理属性和信封  
 由于对信封不保留处理指令，因此以下组合的平面文件组装器设置导致只有最外层信封才具有处理指令：  
  
- **处理指令作用域**属性设置为"Envelope"。  
  
- **添加处理指令**属性设置为"附加"。  
  
  信封将使用在组装器中指定的处理指令**添加处理指令文本**属性。  
  
  在任一外部信封或内层信封，传入消息中指定的任何现有处理指令不会出现在输出消息。  
  
## <a name="see-also"></a>请参阅  
 [XML 组装器管道组件](../core/xml-assembler-pipeline-component.md)   
 [如何配置 XML 组装器管道组件](../core/how-to-configure-the-xml-assembler-pipeline-component.md)   
 [Pipelines-AssemblerDisassembler（BizTalk Server 示例文件夹）](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)