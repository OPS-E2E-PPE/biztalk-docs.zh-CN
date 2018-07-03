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
ms.openlocfilehash: e5d06842eab0def7846ab31419ce2feb0aeb2cd1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000870"
---
# <a name="character-encoding-in-the-xml-assembler-pipeline-component"></a>XML 组装器管道组件中的字符编码
XML 组装器管道组件可以采用下表所示的两种方式根据用户指定的字符编码来生成消息：  
  
|编码级别|编码方法|  
|--------------------|---------------------|  
|组件|设置**目标字符集**管道设计器中的组件属性。|  
|消息|设置**XMLNorm.TargetCharset**消息上下文属性。 **注意：** 一个消息上下文属性将始终覆盖在管道设计器中设置的任何上下文属性。|  
  
 XML 组装器使用以下算法来确定输出消息编码：  
  
1. 如果**XMLNorm.TargetCharset**设置上下文属性，则使用其值。  
  
2. 否则为如果**目标字符集**属性指定管道设计器中使用它的值。  
  
3. 否则为如果**XMLNorm.SourceCharset**指定属性，则使用其值。  
  
4. 如果以上属性均未设置，则使用 UTF-8 编码。  
  
   XML 组装器将 BizTalk 消息对象中的编码信息保存`IBaseMessagePart.Charset`属性。 在使用 Unicode 或 UTF-8 编码时，XML 组装器始终向传出消息中添加字节顺序标记 (BOM)。  
  
   请注意，使用 XML 发送管道，其中包含 XML 组装器组件，默认值时生成的文档可能他们已提交到服务器，或可能如果创建的文档使用 utf-8 编码时使用字符集编码在服务器和**XMLNorm.TargetCharset**未指定。  
  
## <a name="see-also"></a>请参阅  
 [XML 组装器管道组件](../core/xml-assembler-pipeline-component.md)   
 [如何配置 XML 组装器管道组件](../core/how-to-configure-the-xml-assembler-pipeline-component.md)   
 [Pipelines-AssemblerDisassembler（BizTalk Server 示例文件夹）](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)