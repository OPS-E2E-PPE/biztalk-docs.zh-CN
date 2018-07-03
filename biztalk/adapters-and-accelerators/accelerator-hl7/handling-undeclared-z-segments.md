---
title: 处理未声明的 Z 段 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Z segments, 2.X schemas
- 2.X schemas, undeclared Z segments
- segments, undeclared [Z objects]
- Z objects, undeclared segments
ms.assetid: 8878bc93-1833-4bfc-b80e-305e4144739e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 633c1d338a87bef7c0fe53ff5df7f53438eac843
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990014"
---
# <a name="handling-undeclared-z-segments"></a>处理未声明的 Z 段
有两种类型的 Z 段： 声明的 Z 段和未声明的 Z 段。 用于本地目的，它们很相似，尽管它们是在您使用它们的方式大不相同。  
  
 包含声明的 Z 段的定义在消息架构和 Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 使用它来处理消息，就像由 HL7 标准定义的架构。 任何架构不定义的未声明的 Z 段。 包含一条消息，末尾的未声明的 Z 段和[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]传递而不会处理针对架构。 分析器和序列化程序进行验证。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 将其视为二进制大型对象 (BLOB)。 仅检查[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]does 上未声明的 Z 段验证该 BLOB 不包含任何现有的三个字符架构标记。  
  
 包括作为第三部分或 Z 部分，多部分消息的未声明的 Z 段。 该消息包含标头、 正文和 Z 一部分。 Z 部件具有以字母"Z"开头的段 ID。  
  
> [!NOTE]
>  Zpart 必须始终包含数据。 指定的错误条件中的流结果为 null。 如果没有数据包含在 Zpart [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Zpart 中插入 word"空"。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 使用上下文属性**ZPartPresent**以确定是否序列化的 Z 部分。  
> 
> [!CAUTION]
>  Microsoft 已测试 Zsegments 使用 ANSI 字符集，与 ANSI 字符 Zsegment 行为是可预测的结果。 但是，在 Zsegments 中使用其他字符集可能会导致不可预知的行为。  
  
## <a name="see-also"></a>请参阅  
 [使用 Z 对象扩展 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)   
 [创建声明的 Z 段](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md)   
 [在架构中创建自定义数据类型](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md)   
 [在架构中创建自定义表](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md)