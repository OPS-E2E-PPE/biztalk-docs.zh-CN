---
title: 消息分隔符 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, events
- messages, XML messages
- events
- delimiters
- messages, delimiters
- flat files
- XML messages
- messages, flat files
ms.assetid: d25bf6db-5512-4c82-be0e-00da024c55d1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13568a08b804f172af3e7c461810b0df650cc372
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65303875"
---
# <a name="message-delimiters"></a>消息分隔符
HL7 标准中定义的消息事件采用以下格式：  
  
- **平面文件**。 HL7 版本 2.4 及更早版本中定义的消息事件采用平面文件的形式。  
  
- **XML**。 定义的 HL7 版本 2.XML 和版本 3 的消息事件采用 XML 文件的形式。  
  
  标准 HL7 不遵循位置格式，因为它使用分隔符来定义段、 字段、 组件和子组件级别的平面文件。 下表列出了 HL7 平面文件所使用的默认分隔符。  
  
|分隔符|ReplTest1|用法|  
|---------------|-----------|-----------|  
|段终止符|\<cr\>|返回一个回车符将终止段记录。 不能更改此值。|  
|字段分隔符|&#124;|管道字符用于分隔段中的两个相邻的数据字段。 此字符还用于分隔每个段中的第一个数据字段中的段 ID。|  
|复合元素分隔符|^|Hat 字符分隔相邻组件的数据字段在允许的 HL7 标准。|  
|子组件分隔符|&|一个 & 字符分隔相邻子组件的数据字段在允许的 HL7 标准。 如果不有任何子组件，则可以省略此字符。|  
|重复分隔符|~|波形符字符分隔组件或字段中的子组件的多个匹配项在允许的 HL7 标准。|  
|转义符|\|与符合到 ST、 德克萨斯州或 FT 数据类型，任何字段或 ED 数据类型的数据 （第四个） 组件，请使用转义符。 如果在消息中不存在任何转义字符，则可以省略此字符。 但是，如果消息中使用子组件必须将其包含。|  
  
## <a name="see-also"></a>请参阅  
 [处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [消息处理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [使用 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)