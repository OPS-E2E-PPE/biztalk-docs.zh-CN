---
title: "消息分隔符 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6e5cf3c013f0a9bedf8c412206aebe1ce2e3f16
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="message-delimiters"></a>消息分隔符
由 HL7 标准定义的消息事件采用以下形式：  
  
-   **平面文件**。 由 HL7 版本 2.4 及更早版本定义的消息事件采用平面文件的格式。  
  
-   **XML**。 由 HL7 版本 2.XML 和版本 3 的消息事件采用 XML 文件的格式。  
  
 由于标准 HL7 未遵循位置格式，它使用分隔符来定义段、 字段、 组件和子组件级别的平面文件。 下表列出由 HL7 平面文件的默认分隔符。  
  
|分隔符|值|用法|  
|---------------|-----------|-----------|  
|段终止符|\<cr >|返回一个回车符终止段记录。 无法更改此值。|  
|字段分隔符|&#124;|管道字符用于分隔段内的两个相邻的数据字段。 此字符，还会分隔分段 ID 从每个段中的第一个数据字段。|  
|复合元素分隔符|^|Hat 字符分隔相邻组成部分数据字段在允许的 HL7 标准。|  
|子组件分隔符|&|& 号字符分隔的数据的相邻子组件字段在允许的 HL7 标准。 如果有不需要子组件，则可以省略此字符。|  
|重复分隔符|~|波形符字符分隔的组件或字段中的子组件的多个匹配项在允许的 HL7 标准。|  
|转义字符|\|使用符合 ST、 德克萨斯州或 FT 数据类型，任何域或 ED 数据类型的数据 （第四个） 组件，你可以使用转义符。 如果在消息中不存在任何转义字符，则可以省略此字符。 但是，如果消息中使用子组件必须将其包含。|  
  
## <a name="see-also"></a>另请参阅  
 [处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [消息处理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [使用 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)