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
ms.openlocfilehash: c61a82f051349b69d72089093f4646325490a943
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292606"
---
# <a name="unrecognized-messages-in-the-xml-assembler-pipeline-component"></a>XML 组装器管道组件中无法识别的消息
XML 组装器组件将作为"无法识别"如果消息具有一条消息：  
  
-   没有正文部分。  
  
-   正文部分为空。  
  
-   正文部分中没有数据。  
  
-   部署没有关联的架构。  
  
> [!NOTE]
>  非 XML 消息始终被视为无法识别。  
  
 XML 组装器处理无法识别的消息的方式受**XMLNorm.AllowUnrecognizedMessage**消息上下文属性。  
  
 当**XMLNorm.AllowUnrecognizedMessage**设置为**True**，XML 组装器处理 XML 文档，如下所示：  
  
- 为正文部分为空或空数据中将原封不动地通过组装器没有正文部分、 或的消息。  
  
- 没有与它关联的已部署的架构的文档将原封不动通过组装器。  
  
- （而不考虑是否显式组件属性中引用该架构或将其架构解析过程中找到） 组装器处理具有关联的已部署架构的文档。  
  
  如果**XMLNorm.AllowUnrecognizedMessage**设置为**False**，XML 组装器处理 XML 文档，如下所示：  
  
- 未处理的消息没有正文部分、 或正文部分为空或正文部分中的空数据。 报告错误并挂起该消息。  
  
- 没有与它关联的已部署的架构的消息不处理。 报告错误并挂起该消息。  
  
- （而不考虑是否显式组件属性中引用该架构或将其架构解析过程中找到） 组装器处理具有关联的已部署架构的文档。  
  
- 默认情况下，XML 组装器组件不允许无法识别的消息 (即**XMLNorm.AllowUnrecognizedMessages**被视为**False**如果未设置在消息上下文)。  
  
## <a name="see-also"></a>请参阅  
 [XML 组装器管道组件](../core/xml-assembler-pipeline-component.md)   
 [如何配置 XML 组装器管道组件](../core/how-to-configure-the-xml-assembler-pipeline-component.md)   
 [Pipelines-AssemblerDisassembler（BizTalk Server 示例文件夹）](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)