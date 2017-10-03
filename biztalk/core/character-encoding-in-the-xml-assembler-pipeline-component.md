---
title: "XML 汇编程序管道组件中的字符编码 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IBaseMessagePart.Charset property
- XMLNorm.SourceCharset property
- pipeline components, XML Assembler
- XMLNorm.TargetCharset property
- Target Charset property
- XML Assembler [pipeline component], character encoding
ms.assetid: c031fbbf-f00f-41ba-8ac9-cec7d625cef6
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82709af574e3577990cf99cd430e1a5e6a7f8485
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="character-encoding-in-the-xml-assembler-pipeline-component"></a>XML 汇编程序管道组件中的字符编码
XML 组装器管道组件可以采用下表所示的两种方式根据用户指定的字符编码来生成消息：  
  
|编码级别|编码方法|  
|--------------------|---------------------|  
|组件|设置**目标 charset**管道设计器中的组件属性。|  
|消息|设置**XMLNorm.TargetCharset**消息上下文属性。 **注意：** A 消息上下文属性始终重写管道设计器中设置任何上下文属性。|  
  
 XML 组装器使用以下算法来确定输出消息编码：  
  
1.  如果**XMLNorm.TargetCharset**上下文属性设置，则使用其值。  
  
2.  否则为如果**目标 charset**属性指定在管道设计器中，使用它的值。  
  
3.  否则为如果**XMLNorm.SourceCharset**指定属性，则使用其值。  
  
4.  如果以上属性均未设置，则使用 UTF-8 编码。  
  
 XML 汇编程序保存 BizTalk 消息对象中的编码信息`IBaseMessagePart.Charset`属性。 在使用 Unicode 或 UTF-8 编码时，XML 组装器始终向传出消息中添加字节顺序标记 (BOM)。  
  
 请注意，使用 XML 发送管道，其中包含 XML 汇编程序组件，默认值时生成的文档可能进行提交到该服务器，或可能如果创建的文档使用 utf-8 编码时，通过为相同的字符集编码在服务器和**XMLNorm.TargetCharset**未指定。  
  
## <a name="see-also"></a>另请参阅  
 [XML 汇编程序管道组件](../core/xml-assembler-pipeline-component.md)   
 [如何将 XML 汇编程序管道组件配置](../core/how-to-configure-the-xml-assembler-pipeline-component.md)   
 [管道 AssemblerDisassembler （BizTalk Server 示例文件夹中）](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)