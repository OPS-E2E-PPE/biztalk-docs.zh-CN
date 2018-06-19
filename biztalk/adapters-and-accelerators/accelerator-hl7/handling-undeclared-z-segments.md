---
title: 处理未声明的 Z 段 |Microsoft 文档
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
ms.openlocfilehash: 6ff982aedee39ed60820a9f03db11d7e4d051a34
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204669"
---
# <a name="handling-undeclared-z-segments"></a>处理未声明的 Z 段
有两种类型的 Z 段： 声明 Z 段和未声明的 Z 段。 尽管它们是类似方法，在用于本地目的，它们是非常不同中如何使用它们。  
  
 在消息架构中，包括声明的 Z 段的定义和[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 使用它来处理一条消息，就像由 HL7 标准定义的架构一样。 任何架构都没有定义一个未声明的 Z 段。 包含一条消息，末尾未声明的 Z 段和[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]传递而不会处理针对的架构。 分析器和序列化程序不会验证它。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]会将其视为二进制大型对象 (BLOB)。 唯一检查[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]未上未声明 Z 段验证 BLOB 不包括任何现有的三个字符架构标记。  
  
 包括作为第三部分或 Z 部分，多个部分的消息的未声明的 Z 段。 该消息包含标头、 正文和的 Z 部分。 Z 部件具有以字母"Z"开头的分段 ID。  
  
> [!NOTE]
>  Zpart 必须始终包含数据。 指定的错误条件中的流结果为 null。 如果没有数据包含在 Zpart，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]在 Zpart 中插入 word"空"。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]使用上下文属性**ZPartPresent**以确定是否序列化的 Z 部分。  
  
> [!CAUTION]
>  [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]ANSI 字符集，与 ANSI 字符的 Zsegment 行为是可预测的结果进行了测试 Zsegments。 但是，在 Zsegments 中使用其他字符集可能会导致不可预知的行为。  
  
## <a name="see-also"></a>另请参阅  
 [扩展 HL7 2.X 架构具有 Z 对象](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)   
 [创建声明的 Z 段](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md)   
 [在架构中创建自定义数据类型](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md)   
 [在架构中创建自定义的表](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md)