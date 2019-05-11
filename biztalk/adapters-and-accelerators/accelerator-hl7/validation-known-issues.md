---
title: 验证的已知问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- known issues, validating
- validating, known issues
ms.assetid: 136596f2-ee0f-4ea9-918c-3608f2ee1be3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 236cdfaca89068ad67b8f70138d926f4b60cedf1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65286443"
---
# <a name="validation-known-issues"></a>验证的已知问题
本部分包含可帮助您避免验证错误的有用信息。  
  
## <a name="disabling-xml-validation"></a>禁用 XML 验证  
 在"验证正文段"标志[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器控制 XML 正文验证并不包括验证意外的分隔符和尾部分隔符。 如果消息不具有适当的分隔符，不能成功分析该消息。 如果不能成功分析一条消息，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]无法生成有效的中间 XML。 禁用"验证正文段"标志将导致以下结果：  
  
1.  空的必填的字段。  
  
2.  未验证的数据类型。  
  
3.  不验证段结构 （不验证段的顺序）。  
  
## <a name="v2xml-acks-with-multiple-errors-will-fail-validation"></a>V2。带有多个错误的 XML Ack 验证将失败  
 如果传入 V2。XML 消息包含多个错误，Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 分析器可能会生成 V2。在错误字段中的多个错误的 XML 确认 (ACK)。 此类第 2 版。XML 确认将验证失败，因为 HL7 标准指定分析器可以报告 V2 中的只有一个错误。XML 确认错误字段。  
  
## <a name="two-parsing-errors-are-logged-when-messages-in-the-batch-inbatch-out-scenario-contain-validation-errors"></a>记录了两个分析错误时批中的消息中批处理出方案包含验证错误  
 第一个批处理中的消息时在 / 批处理出方案 （多个消息批处理没有批处理标头） 包含验证错误，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]事件日志中记录两个错误。 第二个错误相关的消息的其余部分和与批处理中的第一个消息相关的第一个错误。  
  
## <a name="restrictions-in-validating-field-length"></a>验证字段长度的限制  
 HL7 复杂数据类型组成的组件和子组件与关联的字段。 HL7 规则指定的长度和字段级别而不是在组件/子组件级别的可选性。 例如在于 V2.4，HL7 控制 MSH3 的 HD 数据类型和 180 个字符最大长度。 HD 是复合数据类型使用 HD1 集按原样、 HD2 设为 ST 和 HD3 设为 id。 字段长度限制表示三个组件 （包括两个组件分隔符） 中的数据应小于或等于 180。 但是，未指定三个数据类型的可选性;这意味着所有或某些组件可能存在。 此外，ST 和 IS 的数据类型是用户定义的因此[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]不能为长度分布在三个组件之间的注意，因为这些通常是站点定义。  
  
 由于这些和其他复杂问题，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]不会验证字段长度。 不过，您可以应用长度限制在每个单个组件/子组件 （的数据类型简单） 使用 BizTalk 编辑器中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 将验证在处理过程。  
  
## <a name="validation-of-batch-and-file-headerstrailers-are-affected-by-enabling-fragmentation"></a>启用碎片会影响批处理和文件的标头/尾部的验证  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 当 FHS3 字段包含具有启用的碎片的参与方时，不会验证 batch 和文件的标头/尾部。  
  
## <a name="see-also"></a>请参阅  
 [已知问题](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)