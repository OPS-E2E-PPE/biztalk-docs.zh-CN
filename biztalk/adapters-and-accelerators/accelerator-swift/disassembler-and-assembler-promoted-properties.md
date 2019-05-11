---
title: 反汇编程序和汇编程序的已提升属性 |Microsoft Docs
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
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9df908cc9ecaab15c6b464b31f0d04c444fe57d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377885"
---
# <a name="disassembler-and-assembler-promoted-properties"></a>反汇编程序和汇编程序的已提升属性
拆装器和组装器属性分为两类： 路由属性，用于路由和筛选;和运行时属性，以进行内部处理。  
  
本主题提供了一组被添加到，并进行发布到 MessageBox 数据库 SWIFT 反汇编程序的所有消息属性。  
  
## <a name="routing-properties"></a>路由属性

SWIFT 反汇编程序升级的路由的属性。 您可以将这些属性用于基于内容的路由 （发送端口筛选器） 和接收在业务流程中进行筛选。  
  
|升级的名称|Description|数据类型|值范围|用法示例|  
|-------------------|-----------------|---------------|-----------------|-------------------|  
|**A4SWIFT_BatchId**|处理入站的批处理时动态生成 SWIFT 反汇编程序的全局唯一标识符。 拆装器将此批处理标识符分配给发布到 MessageBox 数据库从同一个批处理发出的所有消息。<br /><br /> 设置为**为-1**的单个消息 （不来自入站批处理）。|String|"-1"或*全局唯一标识符 (GUID)*|相同的关联消息**A4SWIFT_BatchId**值将恢复到最初抵达在同一个批处理对它们进行分组。|  
|**A4SWIFT_BreValidationErrors**|指示业务规则引擎 (BRE) 验证过程中遇到的验证错误数。|Numeric|>= 0|用于未失败 BRE 验证的消息筛选器 (**A4SWIFT_BREValidationErrors**等于零)。|  
|**A4SWIFT_Failed**|指示是否消息处理 （分析和验证） 期间出现任何故障。 设置为 **，则返回 True**如果**A4SWIFT_ParseErrors** + **A4SWIFT_XmlValidationErrors** + **A4SWIFT_BreValidationErrors** > 0。|Boolean|True、False|用于唯一有效的 SWIFT 消息筛选器 (**A4SWIFT_Failed**等于**False**)。|  
|**A4SWIFT_ParseErrors**|指示在分析过程中遇到分析错误数。|Numeric|>= 0|用于未失败分析的消息筛选器 (**A4SWIFT_ParseErrors**等于零)。|  
|**A4SWIFT_PosInBatch**|指示从入站批处理发出一条消息的序号位置。 为一个批，其中包含*n*消息， **A4SWIFT_PosInBatch**采用值从 1 到*n*，对应于在批中消息的序号位置。<br /><br /> 设置为**0**如果消息是一个批处理标头。<br /><br /> 设置为**n + 1**如果消息为批处理尾部。<br /><br /> 设置为**1**如果消息本身则整个批次 （已禁用批处理碎片）。<br /><br /> 设置为**为-1**的单个消息 （不来自入站批处理）。|Numeric|>= -1|对来自同一个入站批处理的消息按到达的原始顺序进行排序。|  
|**A4SWIFT_XmlValidationErrors**|指示 XML 验证过程中遇到的验证错误数。|Numeric|>= 0|用于未失败 XML 验证的消息筛选器 (**A4SWIFT_XmlValidationErrors**等于零)。|  
  
> [!NOTE]
>  一般情况下，所有的路由或筛选器表达式应该评估**A4SWIFT_Failed**之前评估任何其他路由的属性。 仅**A4SWIFT_Failed**保证可升级且可用。 其余属性不可用的有效单个消息 （非批处理消息） 发布到 MessageBox 数据库。 其他属性仅用于提升*失败*单消息和批次的消息 （有效或失败）。  

## <a name="runtime-properties"></a>运行时属性

SWIFT 反汇编程序将运行时的属性升级，并使用它们的内部进程转换在运行时。 它们只是升级并可用于路由在某些情况下，具体取决于上下文。 一般情况下，请不要用于这些属性的路由或筛选。 它们不能保证已升级且可用。 在某些情况下，可以检索或使用路由属性进行筛选后检查这些属性。 下表列出了运行时属性。  
  

|           升级的名称            |                                                                                                                                                                                                                                                                                                                                                                                                            Description                                                                                                                                                                                                                                                                                                                                                                                                             | 数据类型 |      值范围       |                                                                           用法示例                                                                           |
|------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------|------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **A4SWIFT_IsMessageHeaderValued**  |                                                                                                                                                                                                                                                                                               指示数据是否存在于多部分消息的标头部分。 设置为 **，则返回 True**如果标头部分包含数据 （来自批处理的消息的消息信封头）。 设置为**False**标头部分是否为空。                                                                                                                                                                                                                                                                                                |  Boolean  |      True、False       |                        决定是否要检查 （例如，在消息修复业务流程） 检索的消息的标头部分。                         |
| **A4SWIFT_IsMessageTrailerValued** |                                                                                                                                                                                                                                                                                             指示数据是否存在于多部分消息的尾部部分。 设置为 **，则返回 True**如果尾部部分包含数据 （来自批处理的消息的消息信封尾部）。 设置为**False**尾部部分是否为空。                                                                                                                                                                                                                                                                                              |  Boolean  |      True、False       |                        决定是否要检查 （例如，在消息修复业务流程） 检索的消息的尾部部分。                        |
|      **A4SWIFT_MessageType**       |                                                                                                                                                                                                                                                                                                                                                                     SWIFT 标头，该值指示 SWIFT 中的三位数字消息类型 (**MT\*xxx**\*)。                                                                                                                                                                                                                                                                                                                                                                      |  String   | *3 个数字* |                                                     动态识别的消息的 SWIFT 消息类型。                                                     |
|      **A4SWIFT_MessageType2**      |                                                                                                                                                                                                                                                                                                                              SWIFT 标头，该值指示 SWIFT 中的三位数字消息类型 (**MT\*xxx**<em>)。仅当\* \*A4SWIFT_MessageType</em> \* SWIFT 标头中找不到。                                                                                                                                                                                                                                                                                                                              |  String   | *3 个数字* |                                                     动态识别的消息的 SWIFT 消息类型。                                                     |
|     **A4SWIFT_NumberOfParts**      | 指示多部分消息中的部分数。<br /><br /> 设置为**1**如果只有正文部分存在 （包含不来自批处理或批处理标头或从批处理信封批处理尾部有效单个 SWIFT 消息）。<br /><br /> 设置为**2**的正文和错误部分是否存在 （包含失败的消息或批处理中，错误部分，其中包含错误集合 XML 正文部分）。<br /><br /> 设置为**3**正文、 标头和尾部部分是否存在 （正文部分包含源自于一个批处理中，标头部分包含消息信封标头，如果使用，而尾部部分包含消息的有效单个 SWIFT 消息如果使用的信封尾部 — **A4SWIFT_IsMessageHeaderValued**和**A4SWIFT_IsMessageTrailerValued**指示数据是否存在于标头和尾部部分)。 |  Numeric  |        1, 2, 3         | 为具有给定数量的部分的消息筛选器 (例如，筛选**A4SWIFT_NumberOfParts**等于两个用于消息修复业务流程接收形状)。 |
|  **A4SWIFT_SecondaryMessageType**  |                                                                                                                                                                                                                                                                                                                                                                    一个字符串值，该值指示 SWIFT SWIFT 标头中的消息的子类型 (**MT\*xxx_XYZ**\*)。                                                                                                                                                                                                                                                                                                                                                                    |  String   |      *任何字符串*      |                                                   动态识别的消息的 SWIFT 消息子类型。                                                    |
 
## <a name="see-also"></a>请参阅  
[ A4SWIFT_* 的已提升属性](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md)   