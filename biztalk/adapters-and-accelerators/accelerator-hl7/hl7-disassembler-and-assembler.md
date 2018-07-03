---
title: HL7 反汇编程序和汇编程序 |Microsoft Docs
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
ms.openlocfilehash: d603e74defeac983b1287f16c7f562b706b8c54d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994990"
---
# <a name="hl7-disassembler-and-assembler"></a>HL7 反汇编程序和汇编程序
HL7 反汇编程序和汇编程序为 HL7 编码的消息提供支持。 因为 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]处理本机格式为 XML，Microsoft BizTalk Accelerator for HL7 消息 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 使用 HL7 反汇编程序和汇编程序进行[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]HL7 集成引擎。  
  
## <a name="hl7-disassembler"></a>HL7 反汇编程序  
 HL7 拆装器将传入 HL7 编码的消息分析为进行处理的 XML 段。 它将执行验证的消息头和正文的基本验证。 便可确定它使用来分析 HL7 消息架构 (请参阅[架构确定 HL7 2.X 拆装器](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-disassembler.md))，确定源参与方的消息，并执行其他验证的主体 (如果启用了参与方）。  
  
## <a name="hl7-assembler"></a>HL7 组装器  
 HL7 组装器序列化到传出的 HL7 消息的 XML 段。 便可确定它使用序列化 HL7 消息架构 (请参阅[架构确定 HL7 2.X 汇编程序](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-assembler.md))，确定目标参与方的消息，并执行验证的主体 （如果已启用的参与方）。  
  
 在组装器可以序列化以下确认 (ACK) 消息：  
  
- 静态  
  
- 原始模式  
  
- 增强的模式  
  
  HL7 组装器还具有将延迟的确认消息路由功能。  
  
## <a name="see-also"></a>请参阅  
 [BTAHL72X 平面文件处理](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md)   
 [BizTalk Accelerator for HL7 组件](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)