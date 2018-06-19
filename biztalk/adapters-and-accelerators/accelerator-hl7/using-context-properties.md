---
title: 使用上下文属性 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, context properties
- messages, promoted properties
- promoted properties, context properties
- context properties, messages
ms.assetid: 306127a9-df03-4aaf-8dd8-76df51eb193d
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a3fad82b8d537fcc017dfed175c5348cc1529d3
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006750"
---
# <a name="using-context-properties"></a>使用上下文属性
HL7 BizTalk 快捷键 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) Messaging Engine 和其组件在内部使用上下文属性。 不建议更改由某些上下文属性的引擎设置的值，因为它可能会影响引擎的执行逻辑。 但是，你可以更改大量的属性不由引擎设置。 可用于创建发送端口上的筛选器表达式的上下文属性 (有关详细信息，请参阅[发送端口上设置筛选器表达式](../../adapters-and-accelerators/accelerator-hl7/setting-filter-expressions-on-send-ports.md))。 业务流程，还可以在筛选表达式中使用上下文属性。 只要一个项目具有对全局属性架构的引用的属性是可用于筛选器表达式 (其[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]时使用的常见模板之一创建)。  
  
 下表列出了[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]消息消息引擎使用的上下文属性。 引擎将使用其中的许多属性进行布线。 序列化程序将使用其他人进行其处理。 这些属性具有前缀[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]。  
  
 有关详细信息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]上下文属性 （那些由 BTS 前缀筛选器表达式中标识），请参阅 BizTalk Server 帮助中的"消息上下文属性"。 **BTS。SchemaStrongName**和**BTS。MessageType**两个属性，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]引擎使用。  
  
 在以下表中，将提升，而是必需的列具有以下效果：  
  
-   IsPromoted 时"N"[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]写入的上下文中，而不是要升级的值。  
  
-   IsRequired 时为布尔值类型，"N"[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]写入的值仅当为 true。  
  
-   IsRequired 时对于字符串类型，"N"[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]写入的值是否不为空或者是否存在默认值。  
  
|属性名称|提升|是必需的|说明|  
|-------------------|-----------------|-----------------|-----------|  
|BatchDateTime|是|否|[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]在处理批处理消息时，将提升此属性。|  
|[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]MessageType|是|是|序列化程序使用此属性来区分单个和批处理消息。 HL7 反汇编程序将其设置仅对消息进行批处理。 属性指示消息是一条消息、 入站的批处理消息或出站批处理消息。 如果序列化程序未找到它，则假定该消息是一条消息。|  
|FHS10|是|否|[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]在处理批处理消息时，将提升此属性。|  
|FHS3|是|否|[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]在处理批处理消息时，将提升此属性。|  
|FHS4|是|否|[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]在处理批处理消息时，将提升此属性。|  
|FHS5|是|否|[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]在处理批处理消息时，将提升此属性。|  
|FHS6|是|否|[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]在处理批处理消息时，将提升此属性。|  
|FileDateTime|是|否|[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]在处理批处理消息时，将提升此属性。|  
|LastSegmentDelimiter 缺少|否|否|[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]在处理批处理消息时，将提升此属性。|  
|邮件类|是|是|包含以下任一**MessageClass2X**或**MessageClass2Xml**消息的两个类之间进行区分。|  
|MSA1|是|是|仅适用于 ACK 消息。|  
|MSH1|否|是|包含字段分隔符的字段。 序列化程序使用此属性。|  
|MSH2|否|是|序列化程序使用此属性。 包含编码字符 （组件分隔符、 重复分隔符、 转义符和子组件分隔符） 的字段。|  
|MSH3_1|是|否|发送应用程序域的第一个组件。|  
|MSH3_2|是|否|发送应用程序字段第二个组件。|  
|MSH3_3|是|否|发送应用程序字段第三个组件。|  
|MSH5_1|是|否|接收的应用程序域的第一个组件。|  
|MSH5_2|是|否|接收的应用程序字段第二个组件。|  
|MSH5_3|是|否|接收的应用程序字段第三个组件。|  
|ParseError|是|是|指示在分析期间发生错误。|  
|SegmentDelimiter2Char|否|否|用于分隔段的字符。|  
|ToBeBatched|是|否|当设置为 false，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]不缓冲消息更高版本; 否则为要批处理[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]作为批处理的一部分发送消息。|  
|ZPartPresent|是|否|指示未声明的 Z 段是否存在。|  
  
## <a name="in-this-section"></a>本节内容  
  
-   [在发送端口上设置筛选表达式](../../adapters-and-accelerators/accelerator-hl7/setting-filter-expressions-on-send-ports.md)