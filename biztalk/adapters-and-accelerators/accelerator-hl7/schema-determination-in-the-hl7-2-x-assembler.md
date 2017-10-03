---
title: "在 HL7 2.X 汇编程序架构确定 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schemas, assembler
- MSH5
- assembler, schemas
ms.assetid: 464c006e-4fae-4e2a-99ea-157301c0179e
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50a430750846ae2567f063f9aa77221bad9c97e0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="schema-determination-in-the-hl7-2x-assembler"></a>架构确定在 HL7 2.X 汇编程序
当一条消息都流向序列化程序，在序列化程序[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 使用 MSH5 （目标方） 以确定要在消息上执行的操作的消息。 此类操作包括：  
  
-   是否为正文段执行 XML 验证  
  
-   是否要验证正文段的自定义数据类型  
  
-   是否允许尾随分隔符在正文中  
  
-   序列化程序将使用的架构目标命名空间  
  
-   序列化程序是否需要来映射的标题  
  
 若要确定架构，序列化程序将执行以下操作：  
  
-   设置的目标命名空间 (**TargetNS**) 为目标方配置的命名空间相同的值  
  
-   提取**Rootnode**从**BTS。MessageType**提升属性  
  
 **Doctype**变得**TargetNS +"#"+ Rootnode**。  
  
## <a name="see-also"></a>另请参阅  
 [消息处理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [BTAHL72X 平面文件处理](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md)