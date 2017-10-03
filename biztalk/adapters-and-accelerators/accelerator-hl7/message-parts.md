---
title: "消息部分 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, segments
- messages, fields
- messages, message parts
- segments, messages
ms.assetid: 2bb6557e-cd4a-42b7-8bc2-f8b53a59517e
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9b6b02096a0cc75460552a6cd1dd56ef9e6c4e9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="message-parts"></a>消息部分
HL7 消息包含以下部分： 段、 数据字段、 组件和 （可选） 子组件。 HL7 消息具有以下层次结构：  
  
 段  
  
 数据字段  
  
 组件  
  
 子组件 （可选）  
  
 **段**  
  
 段是数据字段的逻辑分组。 段是在消息层次结构最高级别 （深度为 1）。 每个段都有一个名称，包含三个字符的文本值。 下表显示了段名称包含的 ADT 消息类型的示例。  
  
|段代码|Description|  
|------------------|-----------------|  
|MSH|消息标头|  
|EVN|事件类型|  
|PID|患者信息|  
  
 HL7 消息具有*消息标头*和*正文*。 MSH 段定义消息的标头和所有其他类型的段窗体消息的正文。  
  
 **数据字段**  
  
 数据字段出现在消息层次结构的深度 2 的字符的字符串。 数据类型定义数据字段： 简单和复杂。  
  
 下面的示例显示 MSH 和 EVN 段，其中包含 MSH.1 和 EVN.1 数据字段的分层消息结构：  
  
 MSH  
  
 MSH.1  
  
 EVN  
  
 EVN.1  
  
 **组件和子组件**  
  
 组件和子组件进一步包含在数据字段的数据。 组件和子组件可以重复执行相同字段中。  
  
## <a name="see-also"></a>另请参阅  
 [处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [消息处理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [使用 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)