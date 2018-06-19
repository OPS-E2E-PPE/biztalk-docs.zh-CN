---
title: HL7 消息结构 |Microsoft 文档
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
ms.openlocfilehash: d3e705d3c8a72b5ca1072157a227bf6f218035d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22205085"
---
# <a name="hl7-message-structure"></a>HL7 消息结构
HL7 消息是与触发器事件关联的层次结构。 标准 HL7 定义为"卫生保健 （，） 创建对数据在系统之间流动的需求将现实生活中的事件"的触发器事件。 每个触发器事件是与定义的消息需要支持的触发器事件的数据类型的抽象消息相关联。 抽象的消息是一个集合段，并包含重复和这些段的包含的规则。 下表显示与触发器事件 A04 – 注册患者关联抽象消息示例。  
  
|触发器事件|抽象的消息|  
|-------------------|----------------------|  
|ADT ^ A04 ^ ADT_A01|许可、 放电和传输|  
|MSH|消息标头|  
|EVN|事件类型|  
|PID|患者识别|  
|[PD1]|其他人口统计信息|  
|[{角色}]|角色|  
|[{NK1}]|下一步的系列 / 关联方|  
|PV1|患者，请访问|  
|[PV2]|患者访问的其他信息|  
|[{角色}]|角色|  
|[{DB1}]|障碍信息|  
|[{OBX}]|观察/结果|  
|[{AL1}]|过敏信息|  
|[{DG1}]|诊断信息|  
|[DRG]|诊断相关的组|  
|[{||  
|PR1|过程|  
|[{角色}]|角色|  
|}]||  
|[{GT1}]|担保人担保|  
|[{||  
|IN1|保险|  
|[输入 2]|保险的其他信息|  
|[{IN3}]|保险的其他信息的证书。|  
|[{角色}]|角色|  
|}]||  
|[ACC]|意外的信息|  
|[UB1]|通用的帐单信息|  
|[UB2]|通用帐单 92年信息|  
|[PDA]|患者死亡和检查|  
  
 上述方括号"["，"]"指示的段或组的段是可选的时大括号"{"，"}"指示段或重复的段的组。  
  
 段是一组字段其中每个符合特定的数据类型。 字段可以具有简单或复杂的结构。 它们包含的组件根据其数据类型定义中定义的规则。 为了支持更复杂的数据类型，某些组件可能包含子部分。  
  
> [!NOTE]
>  编码使用的 HL7 消息指定分隔符的事实限制一名开发人员能够引入细分数据的新方式。 因为这可能需要一种新型分隔符发明，可能会有任何子子组件。  
  
 第一个 HL7 规范未定义抽象的消息。 抽象的消息是与触发器事件相关联的段的模式。 同样，HL7 消息包含的段的重复一起使用，或段组的集合。 第一个 HL7 规范未定义段组。 着手 V2.3.1，以及在后续版本中继续操作，这将更改由于需要支持 XML 编码。 例如，在上述触发器事件表中，消息结构的名称是"ADT_A01"。 这是用于支持 A01 – 承认患者的段的相同模式。 为方便起见，消息结构的名称对应于第一个 （在方面 HL7 文档中的放置） 触发使用它们的事件。 同样的段中的触发器事件表上述开头 IN1，包括输入 2、 IN3 和角色，组重复作为一个组。 其名称-从版本 2.5 开始是"保险"组。  
  
 在版本 2 中，版本间的兼容性规则支持的接口的发展，通过要求的标准的后续版本不包括使以前的版本无效的结构。 这需要你未删除的触发器事件和，你并不使用的触发器事件的不同的用途或使用不同的抽象消息不按最初预期。 对于抽象的消息，这意味着你无法从消息中，删除段也才能使可选必需段或重复段非重复。 如果添加段，你必须这样一条消息的末尾或一条消息中的重复组的结尾。  
  
 下列函数[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 支持这些要求：  
  
-   支持所有触发器事件和消息的结构从 2.1 版开始，一直到 V2.5。  
  
-   通过添加段和 （可选） 调整段和重复的本地化支持。  
  
## <a name="see-also"></a>另请参阅  
 [处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [消息处理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [使用 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)