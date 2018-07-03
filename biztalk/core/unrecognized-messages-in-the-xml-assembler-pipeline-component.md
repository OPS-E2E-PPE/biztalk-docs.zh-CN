---
title: 无法识别的消息中 XML 组装器管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XMLNorm.AllowUnrecognizedMessage property
- XML Assembler [pipeline component], unrecognized messages
- pipeline components, XML Assembler
ms.assetid: dd98512a-33a4-4b2e-977e-1b3a30747c6a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de9f072fc09126d56397725f93505afaca46adf4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974814"
---
# <a name="unrecognized-messages-in-the-xml-assembler-pipeline-component"></a>XML 组装器管道组件中无法识别的消息
如果消息符合以下情况，则 XML 组装器组件将该消息视为“无法识别”：  
  
-   没有正文部分。  
  
-   正文部分为空。  
  
-   正文部分中没有数据。  
  
-   没有部署关联的架构。  
  
> [!NOTE]
>  非 XML 消息始终被视为无法识别的消息。  
  
 XML 组装器处理无法识别的消息的方式受**XMLNorm.AllowUnrecognizedMessage**消息上下文属性。  
  
 当**XMLNorm.AllowUnrecognizedMessage**设置为**True**，XML 组装器处理 XML 文档，如下所示：  
  
- 没有正文部分、正文部分为空或正文部分中数据为空的消息将原封不动地通过组装器。  
  
- 未部署关联架构的文档将原封不动地通过组装器。  
  
- 部署了关联架构的文档将由组装器进行处理（无论是组件属性中显式引用了架构还是在架构解析过程中找到了架构）。  
  
  如果**XMLNorm.AllowUnrecognizedMessage**设置为**False**，XML 组装器处理 XML 文档，如下所示：  
  
- 没有正文部分、正文部分为空或正文部分中数据为空的消息不进行处理。 组装器将报告错误并挂起该消息。  
  
- 未部署关联架构的消息不进行处理。 组装器将报告错误并挂起该消息。  
  
- 部署了关联架构的文档将由组装器进行处理（无论是组件属性中显式引用了架构还是在架构解析过程中找到了架构）。  
  
- 默认情况下，XML 组装器组件不允许无法识别的消息 (即**XMLNorm.AllowUnrecognizedMessages**被视为**False**如果未设置在消息上下文)。  
  
## <a name="see-also"></a>请参阅  
 [XML 组装器管道组件](../core/xml-assembler-pipeline-component.md)   
 [如何配置 XML 组装器管道组件](../core/how-to-configure-the-xml-assembler-pipeline-component.md)   
 [Pipelines-AssemblerDisassembler（BizTalk Server 示例文件夹）](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)