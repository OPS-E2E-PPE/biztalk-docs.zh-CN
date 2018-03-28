---
title: 反汇编程序和汇编程序提升属性 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- disassembler, promoted properties
- promoted properties, assembler
- promoted properties, disassembler
- assembler, promoted properties
ms.assetid: 342b0250-bdf7-45ce-8964-3aeda89989b1
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab1e0cab902ded34f10cf03bc6e8229d28123be2
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="disassembler-and-assembler-promoted-properties"></a>反汇编程序和汇编程序提升属性
反汇编程序和汇编程序属性分为两类： 路由的属性，用于路由和筛选;和运行时属性，则对于内部处理。  
  
本主题提供的属性，会添加到，提升的所有消息发布到 MessageBox 数据库 SWIFT 反汇编程序的列表。  
  
## <a name="routing-properties"></a>路由属性

SWIFT 反汇编程序提升路由的属性。 您可以将这些属性用于基于内容的路由 （发送端口筛选器），并收到筛选在业务流程中。  
  
|提升的名称|Description|数据类型|值范围|用法示例|  
|-------------------|-----------------|---------------|-----------------|-------------------|  
|**A4SWIFT_BatchId**|在处理入站的批处理时动态生成 SWIFT 反汇编程序的全局唯一标识符。 反汇编程序将此批标识符分配给发布到 MessageBox 数据库从同一个批处理发出的所有消息。<br /><br /> 设置为**-1**单个消息 （不源自的入站批处理）。|字符串|"-1"或*全局唯一标识符 (GUID)*|具有相同关联消息**A4SWIFT_BatchId**要恢复到同一个批处理最初到达对其进行分组的值。|  
|**A4SWIFT_BreValidationErrors**|指示业务规则引擎 (BRE) 验证过程中遇到的验证错误的数。|数字|>= 0|未通过 BRE 验证的消息筛选器 (**A4SWIFT_BREValidationErrors**等于零)。|  
|**A4SWIFT_Failed**|指示是否在消息处理 （分析和验证） 期间出现任何故障。 设置为**True**如果**A4SWIFT_ParseErrors** + **A4SWIFT_XmlValidationErrors** + **A4SWIFT_BreValidationErrors** > 0。|Boolean|True、False|唯一有效的 SWIFT 消息筛选器 (**A4SWIFT_Failed**等于**False**)。|  
|**A4SWIFT_ParseErrors**|指示在分析过程中遇到分析错误数。|数字|>= 0|未通过分析的消息筛选器 (**A4SWIFT_ParseErrors**等于零)。|  
|**A4SWIFT_PosInBatch**|指示从入站批处理发出一条消息的序号位置。 用于批处理包含*n*消息， **A4SWIFT_PosInBatch**采用值从 1 到*n*，分别对应于在批处理中消息的序号位置。<br /><br /> 设置为**0**如果消息已批处理标头。<br /><br /> 设置为**n + 1**如果消息已批处理尾。<br /><br /> 设置为**1**如果消息本身整个批处理 （禁用批处理碎片）。<br /><br /> 设置为**-1**单个消息 （不源自的入站批处理）。|数字|>= -1|从同一个入站批处理到到达的原始顺序排序消息。|  
|**A4SWIFT_XmlValidationErrors**|指示 XML 验证过程中遇到的验证错误数。|数字|>= 0|未通过 XML 验证的消息筛选器 (**A4SWIFT_XmlValidationErrors**等于零)。|  
  
> [!NOTE]
>  一般情况下，应评估所有路由或筛选器表达式**A4SWIFT_Failed**之前评估路由的任何其他属性。 仅**A4SWIFT_Failed**保证可提升并可用。 其余属性不可用于有效单个消息 （非批处理消息） 发布到 MessageBox 数据库。 其他属性仅提升为*失败*单邮件以及对批次的邮件 （有效或失败）。  

## <a name="runtime-properties"></a>运行时属性

SWIFT 反汇编程序提升的运行时属性，并在运行时的内部进程对其进行使用。 它们只是提升和可用于路由在某些情况下，具体取决于上下文。 一般情况下，不要进行路由或筛选使用这些属性。 它们不能保证可提升并可用。 在某些情况下，可以检索或使用的路由的属性进行筛选后检查这些属性。 下表列出的运行时属性。  
  
|提升的名称|Description|数据类型|值范围|用法示例|  
|-------------------|-----------------|---------------|-----------------|-------------------|  
|**A4SWIFT_IsMessageHeaderValued**|指示数据是否存在于多部分消息的标头部分。 设置为**True**如果标头一部分包含数据 （消息信封标头中来自一批消息）。 设置为**False**的标题部分是否为空。|Boolean|True、False|决定是否检查 （例如，在消息修复业务流程） 检索到的消息的标头部分。|  
|**A4SWIFT_IsMessageTrailerValued**|指示数据是否存在于多部分消息的尾部部分。 设置为**True**如果尾部部分包含数据 （消息信封预告片来自一批消息）。 设置为**False**的尾部部分是否为空。|Boolean|True、False|决定是否检查 （例如，在消息修复业务流程） 检索到的消息的尾部部分。|  
|**A4SWIFT_MessageType**|指示 SWIFT SWIFT 标头中的三位数字消息类型 (**MT*xxx * * *)。|字符串|*3 个数字*|动态识别消息的 SWIFT 消息的类型。|  
|**A4SWIFT_MessageType2**|指示 SWIFT SWIFT 标头中的三位数字消息类型 (**MT*xxx * * *)。 仅当**A4SWIFT_MessageType** SWIFT 标头中找不到。|字符串|*3 个数字*|动态识别消息的 SWIFT 消息的类型。|  
|**A4SWIFT_NumberOfParts**|指示部分中多个部分的消息的数。<br /><br /> 设置为**1**如果仅正文部分存在 （包含不源自批处理或批处理标头或从批处理信封的批处理尾有效单个 SWIFT 消息）。<br /><br /> 设置为**2**的正文和错误部分如果存在 （包含失败的消息或批处理中，错误一部分包含的错误集合 XML 正文部分）。<br /><br /> 设置为**3**正文、 标头和预告片部分是否存在 （正文部分包含源自一批，标头部分包含消息信封标头，如果使用，则尾部一部分包含消息的有效单个 SWIFT 消息信封预告片，如果使用- **A4SWIFT_IsMessageHeaderValued**和**A4SWIFT_IsMessageTrailerValued**指示数据是否存在在标头和尾，部件)。|数字|1, 2, 3|具有给定数目的部分的消息的筛选器 (例如，筛选**A4SWIFT_NumberOfParts**适用于消息修复业务流程等于两个接收形状)。|  
|**A4SWIFT_SecondaryMessageType**|一个字符串值，该值指示 SWIFT SWIFT 标头中的消息的子类型 (**MT*xxx_XYZ * * *)。|字符串|*任何字符串*|动态识别消息的 SWIFT 消息子的类型。|  
  
 
## <a name="see-also"></a>另请参阅  
[ A4SWIFT_* 的已提升属性](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md)   