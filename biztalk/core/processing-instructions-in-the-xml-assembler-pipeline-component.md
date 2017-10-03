---
title: "处理 XML 汇编程序管道组件中的说明 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85ac6045084c0aea672b0c1e9d6dfb1b4a742d55
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="processing-instructions-in-the-xml-assembler-pipeline-component"></a>处理 XML 汇编程序管道组件中的说明
处理指令向处理 XML 文档的应用程序提供信息。 这些信息可能包括有关如何处理文档、如何显示文档等的指令。  
  
 处理指令添加到 XML 文档由**添加处理指令**属性 (或同等**XMLNorm.ProcessingInstructionOption**消息上下文属性)。 处理指令文本的情况下指定**添加处理指令文本**属性 (或同等**XMLNorm.ProcessingInstruction**消息上下文属性)。  
  
 **添加处理指令**属性 (或**XMLNorm.ProcessingInstructionOption**属性) 具有三个可能的值，如下表所述。  
  
|值|值|Description|  
|-----------|-----------|-----------------|  
|追加|0|将 XML 组装器中的新处理指令附加到文档开头处的处理指令。|  
|创建新的|1|XML 组装器中的新处理指令将覆盖文档开头处的现有处理指令。|  
|Ignore|2|将删除文档开头处的处理指令。|  
  
 消息上下文中指定的处理指令对（或消息上下文属性）的优先级高于管道设计器中指定的属性对。 例如，如果**XMLNorm.ProcessingInstructionOption**指定为**新建**(1) 和**XMLNorm.ProcessingInstruction**未指定，空处理指令将替换现有的处理指令。  
  
 再举一例，如果**XMLNorm.ProcessingInstruction**指定但**XMLNorm.ProcessingInstructionOption**不，没有从消息上下文属性使用。 在这种情况下，将使用管道设计器中的处理指令。  
  
 默认情况下，**添加处理指令**设置为**追加**，和**添加处理指令文本**为空。  
  
## <a name="processing-properties-and-envelopes"></a>处理属性和信封  
 由于对信封不保留处理指令，因此以下组合的平面文件组装器设置导致只有最外层信封才具有处理指令：  
  
-   **处理指令作用域**属性设置为"封套"。  
  
-   **添加处理指令**属性设置为"追加"。  
  
 信封的情况下将使用的汇编中指定的处理指令**添加处理指令文本**属性。  
  
 传入消息中所指定的外层信封或内层信封中的任何现有处理指令都不会出现在输出消息中。  
  
## <a name="see-also"></a>另请参阅  
 [XML 汇编程序管道组件](../core/xml-assembler-pipeline-component.md)   
 [如何将 XML 汇编程序管道组件配置](../core/how-to-configure-the-xml-assembler-pipeline-component.md)   
 [管道 AssemblerDisassembler （BizTalk Server 示例文件夹中）](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)