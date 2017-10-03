---
title: "XML 反汇编程序和汇编程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- disassembler, XML
- assembler, XML
ms.assetid: 242a7a96-2342-4ab5-9d3f-1acbcc7ffd14
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4978484f888290377986ee4ae8bf049c14a1b31
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="xml-disassembler-and-assembler"></a>XML 反汇编程序和汇编程序
XML 反汇编程序和汇编程序确保[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 不仅支持 HL7 编码消息，但也支持传入和/或传出的 XML 消息。  
  
## <a name="xml-disassembler"></a>XML 反汇编程序  
 XML 反汇编程序分析到 XML 段，用来处理传入的 XML 消息。 它会分析消息，拆装器执行以下任务：  
  
-   句柄转义序列  
  
-   处理检查必需/可选属性  
  
-   声明 Z 段的句柄  
  
 它会分析消息，如 dissassembler 执行下列任务：  
  
-   语法验证  
  
-   架构验证 （如果启用）  
  
## <a name="xml-assembler"></a>XML 汇编程序  
 XML 汇编程序传出的 XML 消息序列化为 XML 段。 XML 汇编程序支持，并创建以下确认 (ACK) 消息：  
  
-   静态  
  
-   原始模式  
  
-   增强的模式  
  
 XML 汇编程序还能够将延迟的 ACK 消息路由。  
  
## <a name="see-also"></a>另请参阅  
 [BTAHL72XML 处理](../../adapters-and-accelerators/accelerator-hl7/btahl72xml-processing.md)   
 [BizTalk Accelerator for HL7 组件](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)