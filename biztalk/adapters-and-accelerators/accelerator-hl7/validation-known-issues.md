---
title: "验证已知问题 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- known issues, validating
- validating, known issues
ms.assetid: 136596f2-ee0f-4ea9-918c-3608f2ee1be3
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69400c5196b31a53d49055e500356c7ce3430e58
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="validation-known-issues"></a>验证已知问题
本节包含可以帮助您避免验证错误的有用信息。  
  
## <a name="disabling-xml-validation"></a>禁用 XML 验证  
 "验证正文段"标志中[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器控制 XML 正文验证，并且不包括验证意外的分隔符和尾随分隔符。 如果消息不具有适当的分隔符，则无法成功分析消息。 如果无法成功分析一条消息，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]无法生成有效的中间 XML。 禁用"验证正文段"标志将产生以下结果：  
  
1.  空的必填的字段。  
  
2.  未验证的数据类型。  
  
3.  不验证段结构 （不验证的段的顺序）。  
  
## <a name="v2xml-acks-with-multiple-errors-will-fail-validation"></a>V2。使用多个错误的 XML 确认将未通过验证  
 如果传入 V2。XML 消息包含多个错误， [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 分析器可能会生成 V2。与错误字段中的多个错误的 XML 确认 (ACK)。 此类 V2。XML ACK 将未通过验证，因为 HL7 标准指定分析器可以报告 V2 中的只有一个错误。XML ACK 错误字段。  
  
## <a name="two-parsing-errors-are-logged-when-messages-in-the-batch-inbatch-out-scenario-contain-validation-errors"></a>记录两个分析错误时批处理中的消息中批处理出方案包含验证错误  
 第一个批处理中的消息时在 / 批处理出方案 （多个消息批处理不带批处理标头） 包含验证错误[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]记录事件日志中的两个错误。 第一个错误与批处理中的第一条和第二个错误与消息的其余部分。  
  
## <a name="restrictions-in-validating-field-length"></a>验证字段长度的限制  
 复杂数据类型组成组件和子组件的 HL7 与关联的字段。 HL7 规则指定的长度和 optionality 在字段级别而不是在组件/子组件级别。 例如在 V2.4，HL7 控制 MSH3 为 HD 数据类型和 180 个字符最大长度。 HD 是复合数据类型并带有 HD1 设为 IS、 HD2 设为表 ST 和 HD3 设为 id。 字段长度限制意味着 （包括这两个组件分隔符） 的三个组件中的数据应小于或等于 180。 但是，未指定三种数据类型的 optionality;这意味着所有或某些组件可能存在。 此外，数据类型为 ST 和 IS 是用户定义的因此[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]不能为感知的长度分布的三个组件，因为这些通常是定义的站点。  
  
 由于这些和其他的复杂性，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]不会验证字段长度。 但是，你可以应用长度限制在每个单个组件/子组件 （的数据类型简单） 使用 BizTalk 编辑器中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将验证在处理过程。  
  
## <a name="validation-of-batch-and-file-headerstrailers-are-affected-by-enabling-fragmentation"></a>启用碎片会影响的批处理和文件的标头/拖车的验证  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]当 FHS3 字段包含已启用的碎片的当事方，则不会验证批处理和文件标头/拖车安排。  
  
## <a name="see-also"></a>另请参阅  
 [已知问题](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)