---
title: 段和字段 |Microsoft 文档
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
ms.openlocfilehash: 6ca948748bc30f8c8a56f7c257b775b37a990625
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206477"
---
# <a name="segment-and-field"></a>段和字段
段表定义一个 HL7 段。 每个段定义遵循下面所示的模式。  
  
|SEQ|LEN|DT|选择|RP / #|TBL #|项 #|元素名称|  
|---------|---------|--------|---------|------------|-----------|------------|------------------|  
|1|4|SI|O|||00104|设置 PID 的 ID-|  
|2|20|CX|B|||00105|患者 ID|  
|3|250|CX|R|是||00106|患者标识符列表|  
|4|20|CX|B|是||00107|备用患者 ID-PID|  
|5|250|XPN|R|是||00108|患者名称|  
|..||||||||  
|..||||||||  
|37|80|ST|O|||01541|大的压力|  
|38|250|CE|O|2|0429|01542|生产类代码|  
  
 HL7 还包括每个字段的文本定义。 三个字符段标记和序列号唯一标识在段内的每个字段。 例如，对于患者标识段中，标记 PID 和序列号"5"唯一标识患者名称字段。 XML 编码和接口文档都使用此约定以标识数据段中的字段。 段定义还包括每个字段，以及将应用于编码元素的表数的数据类型声明。  
  
 在新版本中，只能在一段的末尾添加字段和不能删除字段。 如果添加的字段将替换现有字段的功能，第一个字段将保持为向后兼容性。 (这可以通过"B"看到，在可以选择上面 PID.2 和列 PID.3。)  
  
 下列函数[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 支持这些要求：  
  
-   [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]支持标准段，用来从 2.1 版的所有 HL7 版本上。  
  
-   在构造接口规范和实现接口时，可以标记是必需的或不受支持，作为标准中可选基于功能的要求的字段。  
  
-   你可以创建 Z 将在需要时进行本地化。  
  
-   可以重新定义的字段的语义，也可以将字段添加到段在需要时进行本地化。 请注意此所属非法本地化的标题。 但是，在某些情况下你需要此功能以支持旧接口或对旧版系统的接口。  
  
## <a name="see-also"></a>另请参阅  
 [处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [消息处理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [使用 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)