---
title: XML 拆装器和组装器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- disassembler, XML
- assembler, XML
ms.assetid: 242a7a96-2342-4ab5-9d3f-1acbcc7ffd14
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ccf8b71b08c35e94f710af12562060d477bf4abb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65285141"
---
# <a name="xml-disassembler-and-assembler"></a>XML 拆装器和组装器
XML 拆装器和组装器，请确保 Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 不仅支持 HL7 编码的消息，但也支持传入和/或传出 XML 消息。  
  
## <a name="xml-disassembler"></a>XML 拆装器  
 XML 拆装器将传入的 XML 消息分析为进行处理的 XML 段。 在分析消息，拆装器将执行以下任务：  
  
- 句柄转义序列  
  
- 处理检查必需/可选属性  
  
- 句柄声明的 Z 段  
  
  在分析消息，拆装器执行下列任务：  
  
- 语法验证  
  
- 架构验证 （如果启用）  
  
## <a name="xml-assembler"></a>XML 组装器  
 XML 组装器将传出 XML 消息序列化为 XML 段。 XML 组装器支持，并创建以下确认 (ACK) 消息：  
  
- Static  
  
- 原始模式  
  
- 增强的模式  
  
  XML 组装器还具有将延迟的确认消息路由功能。  
  
## <a name="see-also"></a>请参阅  
 [BTAHL72XML 处理](../../adapters-and-accelerators/accelerator-hl7/btahl72xml-processing.md)   
 [BizTalk Accelerator for HL7 组件](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)