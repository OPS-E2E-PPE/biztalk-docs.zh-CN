---
title: HL7 反汇编程序和汇编程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- assembler, HL7
- disassembler, HL7
ms.assetid: 54e83a04-86c8-482f-bea3-dbbdeb4584d6
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e81d621656fc678196f7f6fb709b29de87a3aaf9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204925"
---
# <a name="hl7-disassembler-and-assembler"></a>HL7 反汇编程序和汇编程序
HL7 反汇编程序和汇编程序为 HL7 编码消息提供支持。 由于[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]处理以本机方式在 XML 格式的消息[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 使用 HL7 反汇编程序和汇编程序以使[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]HL7 集成引擎。  
  
## <a name="hl7-disassembler"></a>HL7 反汇编程序  
 HL7 反汇编程序以进行处理的 XML 分成分析传入 HL7 编码消息。 它将执行验证的消息头和正文的基本验证。 它将确定它使用来分析 HL7 消息的架构 (请参阅[HL7 中的架构确定 2.X 反汇编程序](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-disassembler.md))，确定该消息的源方，并执行其他验证正文的 (如果为启用当事方）。  
  
## <a name="hl7-assembler"></a>HL7 汇编程序  
 HL7 汇编程序传出的 HL7 消息序列化为 XML 段。 它将确定它用于序列化 HL7 消息的架构 (请参阅[HL7 中的架构确定 2.X 汇编程序](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-assembler.md))，确定目标参与方的消息，并执行验证的正文 （如果启用当事方）。  
  
 汇编程序可以序列化下面的确认 (ACK) 消息：  
  
-   静态  
  
-   原始模式  
  
-   增强的模式  
  
 HL7 汇编程序还能够将延迟的 ACK 消息路由。  
  
## <a name="see-also"></a>另请参阅  
 [BTAHL72X 平面文件处理](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md)   
 [BizTalk Accelerator for HL7 组件](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)