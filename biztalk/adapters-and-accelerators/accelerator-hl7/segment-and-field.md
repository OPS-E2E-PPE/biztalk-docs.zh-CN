---
title: 段和字段 |Microsoft Docs
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
- segments, messages
ms.assetid: e68864e6-590c-47f3-8c9e-81831aec2642
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 527774808bc2015189015adc41a894824c5208ec
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65289641"
---
# <a name="segment-and-field"></a>段和字段
段表定义 HL7 段。 每个段定义遵循如下所示的模式。  
  
|SEQ|LEN|DT|选择|RP/#|TBL#|ITEM#|元素名称|  
|---------|---------|--------|---------|------------|-----------|------------|------------------|  
|1|4|SI|O|||00104|设置 ID 的 PID|  
|2|20|CX|B|||00105|患者 ID|  
|3|250|CX|R|Y||00106|患者标识符列表|  
|4|20|CX|B|Y||00107|备用患者 ID-PID|  
|5|250|XPN|R|Y||00108|患者的名称|  
|..||||||||  
|..||||||||  
|37|80|ST|O|||01541|压力|  
|38|250|CE|O|2|0429|01542|生产类代码|  
  
 HL7 还包括文本定义的每个字段。 三个字符段标记和序列号唯一标识段中的每个字段。 例如，对于患者标识段中，标记 PID 和序列号"5"唯一标识患者名称字段。 XML 编码和接口文档都使用此约定以标识段中的字段。 段定义还包括每个字段，以及将应用于编码元素的表数的数据类型声明。  
  
 在新版本中，仅可以在一个段的末尾添加字段并不能删除字段。 如果添加的字段将替换现有字段的功能，第一个字段保持向后兼容性。 (这可通过"B"中查看 （可选） 在上列 PID.2 和 PID.3。)  
  
 Microsoft BizTalk Accelerator for HL7 的以下函数 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 支持这些要求：  
  
- [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 支持所有 HL7 版本从 2.1 版的标准段上。  
  
- 当构造接口规范和实现接口时，可以标记是可选作为必需或不受支持，标准中的功能要求的字段。  
  
- 您可以创建 Z 段在需要时进行本地化。  
  
- 可以重新定义的字段的语义，也可以将字段添加到段在需要时进行本地化。 请注意，此属于不合法的本地化的标题。 但是，在某些情况下在需要此功能以支持旧接口或接口连接到旧系统。  
  
## <a name="see-also"></a>请参阅  
 [处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [消息处理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [使用 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)