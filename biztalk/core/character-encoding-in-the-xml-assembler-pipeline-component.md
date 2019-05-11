---
title: XML 组装器管道组件中的字符编码 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IBaseMessagePart.Charset property
- XMLNorm.SourceCharset property
- pipeline components, XML Assembler
- XMLNorm.TargetCharset property
- Target Charset property
- XML Assembler [pipeline component], character encoding
ms.assetid: c031fbbf-f00f-41ba-8ac9-cec7d625cef6
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e01bbf7224da9abda8700721c1de3dd7efefb8f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357480"
---
# <a name="character-encoding-in-the-xml-assembler-pipeline-component"></a>XML 组装器管道组件中的字符编码
下表中所示，XML 组装器管道组件可以产生用户指定的字符编码两种方式中的消息。  
  
|编码级别|编码方法|  
|--------------------|---------------------|  
|组件|设置**目标字符集**管道设计器中的组件属性。|  
|消息|设置**XMLNorm.TargetCharset**消息上下文属性。 **注意：** 消息上下文属性将始终覆盖在管道设计器中设置的任何上下文属性。|  
  
 XML 组装器使用以下算法来确定输出消息编码：  
  
1. 如果**XMLNorm.TargetCharset**设置上下文属性，则使用其值。  
  
2. 否则为如果**目标字符集**属性指定管道设计器中使用它的值。  
  
3. 否则为如果**XMLNorm.SourceCharset**指定属性，则使用其值。  
  
4. 如果以上属性未设置，则使用 utf-8 编码。  
  
   XML 组装器将 BizTalk 消息对象中的编码信息保存`IBaseMessagePart.Charset`属性。 在使用 Unicode 或 utf-8 编码时，XML 组装器始终将字节顺序标记 (BOM) 添加到传出消息。  
  
   请注意，使用 XML 发送管道，其中包含 XML 组装器组件，默认值时生成的文档可能他们已提交到服务器，或可能如果创建的文档使用 utf-8 编码时使用字符集编码在服务器和**XMLNorm.TargetCharset**未指定。  
  
## <a name="see-also"></a>请参阅  
 [XML 组装器管道组件](../core/xml-assembler-pipeline-component.md)   
 [如何配置 XML 组装器管道组件](../core/how-to-configure-the-xml-assembler-pipeline-component.md)   
 [Pipelines-AssemblerDisassembler（BizTalk Server 示例文件夹）](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)