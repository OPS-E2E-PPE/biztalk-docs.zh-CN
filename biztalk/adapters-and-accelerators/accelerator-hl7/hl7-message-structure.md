---
title: HL7 消息结构 |Microsoft Docs
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
- trigger events
- messages, trigger events
- segments, messages
- messages, message structure
ms.assetid: 4dbef56d-97ae-466d-bc8a-dc96c40896f6
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b4f8f81087874c0b3ea0e15e30334630e03b21f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65293023"
---
# <a name="hl7-message-structure"></a>HL7 消息结构
HL7 消息是与触发器事件相关联的层次结构。 HL7 标准定义为"卫生保健 （，），所以需要在系统之间流动的数据的真实世界中的事件"的触发器事件。 每个触发器事件都与定义的消息需要支持的触发器事件的数据类型的抽象消息相关联。 抽象的消息是一系列段，并将重复和有关这些段包含的规则。 下表显示了与触发器事件 A04 – 注册患者相关联的抽象消息的示例。  
  
|触发器事件|抽象的消息|  
|-------------------|----------------------|  
|ADT^A04^ADT_A01|病人入院、 放电装置和传输|  
|MSH|消息标头|  
|EVN|事件类型|  
|PID|患者识别|  
|[  PD1  ]|其他人口统计信息|  
|[{ ROL }]|角色|  
|[{ NK1 }]|下一步的系列: / 相关联的参与方|  
|PV1|患者，请访问|  
|[  PV2  ]|患者访问的其他信息|  
|[{ ROL }]|角色|  
|[{ DB1 }]|伤残信息|  
|[{ OBX }]|观察/结果|  
|[{ AL1 }]|过敏信息|  
|[{ DG1 }]|诊断信息|  
|[  DRG  ]|诊断相关的组|  
|[{||  
|PR1|过程|  
|[{ ROL }]|角色|  
|}]||  
|[{ GT1 } ]|担保人担保|  
|[{||  
|IN1|保险|  
|[  IN2 ]|保险的其他信息|  
|[{ IN3 }]|保险的其他信息的证书。|  
|[{ ROL }]|角色|  
|}]||  
|[  ACC  ]|意外的信息|  
|[  UB1  ]|通用的帐单信息|  
|[  UB2  ]|通用帐单 92年信息|  
|[  PDA  ]|患者死亡和检查|  
  
 上面的方括号"["，"]"指示一段或一组段是可选的而大括号"{"，"}"指示段或段重复的组。  
  
 段是一组字段其中每个符合特定的数据类型。 字段可以具有简单或复杂的结构。 它们包含的组件根据其数据类型定义中定义的规则。 为了支持更复杂的数据类型，某些组件可能会包含子组件。  
  
> [!NOTE]
>  HL7 消息编码使用指定的分隔符的事实限制一名开发人员能够引入新的细分数据的方法。 可以是任何子子组件，因为这需要发明的新的分隔符类型。  
  
 第一个 HL7 规范未定义抽象的消息。 抽象的消息是与触发器事件相关联的段的模式。 同样，HL7 消息包含在一起，重复或分段组的段的集合。 第一个 HL7 规范未定义段组。 使用适用于版本 V2.3.1，开始，一直在后续版本中，这将更改由于需要支持 XML 编码。 例如，上面的触发器事件表中的消息结构的名称是"ADT_A01"。 这是相同的模式用于支持 A01 – 承认患者的线段。 为方便起见，对应于消息结构的名称 （在方面 HL7 文档内的位置） 的第一个触发事件，使用它们。 同样，触发器事件上表开头 IN1，包括输入 2、 IN3 和 ROL 中的段组重复作为一个组。 其名称，从版本 2.5 开始是"保险"组。  
  
 在版本 2 中，版本间的兼容性规则通过要求标准的后续版本，不包括以前的版本使之无效的结构支持的接口的演变。 这需要你未删除的触发器事件和执行不使用的触发器事件用于其他目的或使用不同的抽象消息比最初预期。 对于抽象的消息，这意味着，不能删除一个段从一条消息，也可以使可选必需段或重复段非重复。 如果添加一个段，您必须执行在消息的结尾或在消息中重复组的末尾。  
  
 Microsoft BizTalk Accelerator for HL7 的以下函数 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 支持这些要求：  
  
-   所有触发器事件和消息结构从 2.1 版开始，一直到版本 2.5 的支持。  
  
-   通过添加段并根据需要调整段和重复的本地化支持。  
  
## <a name="see-also"></a>请参阅  
 [处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [消息处理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [使用 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)