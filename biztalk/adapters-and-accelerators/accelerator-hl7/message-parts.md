---
title: 消息部分 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, segments
- messages, fields
- messages, message parts
- segments, messages
ms.assetid: 2bb6557e-cd4a-42b7-8bc2-f8b53a59517e
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2c67694dbfe2e0cdfbc330e36d51dcf8e5a3fccd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65303688"
---
# <a name="message-parts"></a>消息部分
HL7 消息包含以下几个部分： 段、 数据字段、 组件和 （可选） 子组件。 HL7 消息具有以下层次结构：  
  
 段  
  
 数据字段  
  
 组件  
  
 子组件 （可选）  
  
 **段**  
  
 一个段是数据字段的逻辑分组。 段在消息层次结构的最高级别 （深度为 1）。 每个分段有一个包括三个字符的文本值的名称。 下表显示了段名称所包含的 ADT 消息类型的示例。  
  
|段代码|Description|  
|------------------|-----------------|  
|MSH|消息标头|  
|EVN|事件类型|  
|PID|患者信息|  
  
 HL7 消息具有*消息标头*并*正文*。 MSH 段定义消息的标头和所有其他类型的段构成消息的正文。  
  
 **数据字段**  
  
 数据字段是发生在消息层次结构的深度 2 的字符的字符串。 数据类型定义数据字段：简单和复杂。  
  
 下面的示例显示了包含 MSH.1 和 EVN.1 数据字段的 MSH 和 EVN 段的层次结构的消息结构：  
  
 MSH  
  
 MSH.1  
  
 EVN  
  
 EVN.1  
  
 **组件和子组件**  
  
 组件和子组件进一步包含数据字段中的数据。 组件和子组件可以重复相同的字段中。  
  
## <a name="see-also"></a>请参阅  
 [处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [消息处理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [使用 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)