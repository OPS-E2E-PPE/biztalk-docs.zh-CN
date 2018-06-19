---
title: 无法识别的消息，在 XML 汇编程序管道组件 |Microsoft 文档
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
ms.openlocfilehash: 6766554374413c3d1b6a3ce385f24d4046521c91
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286805"
---
# <a name="unrecognized-messages-in-the-xml-assembler-pipeline-component"></a>无法识别的消息中 XML 汇编程序管道组件
如果消息符合以下情况，则 XML 组装器组件将该消息视为“无法识别”：  
  
-   没有正文部分。  
  
-   正文部分为空。  
  
-   正文部分中没有数据。  
  
-   没有部署关联的架构。  
  
> [!NOTE]
>  非 XML 消息始终被视为无法识别的消息。  
  
 XML 汇编程序处理无法识别的消息方式，此受**XMLNorm.AllowUnrecognizedMessage**消息上下文属性。  
  
 当**XMLNorm.AllowUnrecognizedMessage**设置为**True**，XML 汇编程序处理 XML 文档，如下所示：  
  
-   没有正文部分、正文部分为空或正文部分中数据为空的消息将原封不动地通过组装器。  
  
-   未部署关联架构的文档将原封不动地通过组装器。  
  
-   部署了关联架构的文档将由组装器进行处理（无论是组件属性中显式引用了架构还是在架构解析过程中找到了架构）。  
  
 如果**XMLNorm.AllowUnrecognizedMessage**设置为**False**，XML 汇编程序处理 XML 文档，如下所示：  
  
-   没有正文部分、正文部分为空或正文部分中数据为空的消息不进行处理。 组装器将报告错误并挂起该消息。  
  
-   未部署关联架构的消息不进行处理。 组装器将报告错误并挂起该消息。  
  
-   部署了关联架构的文档将由组装器进行处理（无论是组件属性中显式引用了架构还是在架构解析过程中找到了架构）。  
  
-   默认情况下，XML 汇编程序组件不允许无法识别的消息 (即， **XMLNorm.AllowUnrecognizedMessages**被视为**False**如果未设置上的消息上下文)。  
  
## <a name="see-also"></a>另请参阅  
 [XML 汇编程序管道组件](../core/xml-assembler-pipeline-component.md)   
 [如何将 XML 汇编程序管道组件配置](../core/how-to-configure-the-xml-assembler-pipeline-component.md)   
 [管道 AssemblerDisassembler （BizTalk Server 示例文件夹中）](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)