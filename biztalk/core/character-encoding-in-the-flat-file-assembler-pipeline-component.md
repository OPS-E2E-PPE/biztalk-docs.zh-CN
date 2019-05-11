---
title: 平面文件组装器管道组件中的字符编码 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b97a92ed1dd842f6b65b49d1c312ffd84eb8dac
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357481"
---
# <a name="character-encoding-in-the-flat-file-assembler-pipeline-component"></a>平面文件组装器管道组件中的字符编码
平面文件组装器可以生成用户指定的字符编码的消息。 您可以指定在多个级别的字符编码：  
  
- **架构。** 设置**代码页**文档的平面文件架构中的属性。  
  
- **组件。** 设置**目标字符集**管道设计器中的组件属性。  
  
- **消息。** 设置**XMLNorm.TargetCharset**消息上下文属性。  
  
  始终在消息上下文上设置的属性的值将覆盖在管道设计器中的一个集。 此外，始终在管道设计器中设置的值将覆盖设置为值**代码页**平面文件文档架构中的属性。  
  
  平面文件组装器使用以下算法来确定要用于输出消息的编码：  
  
- 如果**XMLNorm.TargetCharset**上下文属性设置，则其值用于编码。  
  
- 否则为如果**目标字符集**指定管道设计器中的属性，则使用其值。  
  
- 否则为如果**代码页**指定平面文件架构中的属性，则使用其值。  
  
- 否则为如果**XMLNorm.SourceCharset**指定属性，则使用其值。  
  
- 否则，使用"utf-8"。 请注意，平面文件组装器管道组件不会将字节顺序标记对传出消息时使用 utf-8 编码。  
  
  平面文件组装器将保存在中的 BizTalk 消息对象正文部分的信息进行编码**IBaseMessagePart.Charset**属性。  
  
## <a name="see-also"></a>请参阅  
 [平面文件组装器管道组件](../core/flat-file-assembler-pipeline-component.md)   
 [如何配置平面文件组装器管道组件](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md)   
 [Pipelines-AssemblerDisassembler（BizTalk Server 示例文件夹）](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)