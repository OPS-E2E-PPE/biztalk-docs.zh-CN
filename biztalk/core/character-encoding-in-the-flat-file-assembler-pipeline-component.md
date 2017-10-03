---
title: "平面文件汇编管道组件中的字符编码 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Flat File Assembler [pipeline component], character encoding
- IBaseMessagePart.Charset property
- pipeline components, Flat File Assembler
- Codepage property
- XMLNorm.SourceCharset property
- XMLNorm.TargetCharset property
- Target Charset property
ms.assetid: 0cf3c0fd-f036-4190-83ce-9064ef4e823c
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af38855c81129cd4bafff50544f2aee15e6f3fab
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="character-encoding-in-the-flat-file-assembler-pipeline-component"></a>平面文件汇编管道组件中的字符编码
平面文件组装器可以使用用户指定的字符编码生成消息。 您可以在多个级别指定字符编码：  
  
-   **架构。** 设置**代码页**文档的平面文件架构中的属性。  
  
-   **组件。** 设置**目标 Charset**管道设计器中的组件属性。  
  
-   **消息。** 设置**XMLNorm.TargetCharset**消息上下文属性。  
  
 对消息上下文设置的属性值将始终覆盖在管道设计器中设置的属性值。 此外，管道设计器中始终设置的值将覆盖的值设置为**代码页**平面文件文档架构中的属性。  
  
 平面文件组装器使用以下算法来确定输出消息要使用的编码：  
  
-   如果**XMLNorm.TargetCharset**上下文属性设置，则其值用于编码。  
  
-   否则为如果**目标 charset**指定管道设计器中的属性，则使用其值。  
  
-   否则为如果**代码页**指定平面文件架构中的属性，则使用其值。  
  
-   否则为如果**XMLNorm.SourceCharset**指定属性，则使用其值。  
  
-   否则，将使用“UTF-8”。 请注意，使用 UTF-8 编码时，平面文件组装器管道组件不会在传出消息上添加字节顺序标记。  
  
 平面文件汇编器将保存在中的 BizTalk 消息对象的正文部分的信息进行编码**IBaseMessagePart.Charset**属性。  
  
## <a name="see-also"></a>另请参阅  
 [平面文件汇编管道组件](../core/flat-file-assembler-pipeline-component.md)   
 [如何配置平面文件汇编管道组件](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md)   
 [管道 AssemblerDisassembler （BizTalk Server 示例文件夹中）](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)