---
title: 使用上下文属性 |Microsoft Docs
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
ms.openlocfilehash: b13af4b6325cddb4a642a24bcd61c42a102531e1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980678"
---
# <a name="using-context-properties"></a>使用上下文属性
BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 消息引擎和及其组件在内部使用上下文属性。 不建议更改引擎为某些上下文属性设置的值，因为它可能会影响引擎的执行逻辑。 但是，可以更改大量的属性不由引擎设置。 可用于创建发送端口上的筛选器表达式的上下文属性 (有关详细信息，请参阅[发送端口设置筛选器表达式](../../adapters-and-accelerators/accelerator-hl7/setting-filter-expressions-on-send-ports.md))。 为业务流程，还可以在筛选表达式中使用上下文属性。 属性是可用于筛选器表达式，只要一个项目具有对全局属性架构的引用 (其中[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]时使用一个常用模板创建)。  
  
 下表包含一系列[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]消息消息引擎将使用的上下文属性。 引擎将使用其中的许多属性的路由。 序列化程序使用其他人进行其处理。 这些属性具有前缀[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]。  
  
 有关详细信息[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]上下文属性 （标识的那些在筛选表达式中的 BTS 前缀），请参阅 BizTalk Server 帮助中的"消息上下文属性"。 **BTS。SchemaStrongName**和**BTS。MessageType**两个属性的[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]引擎使用。  
  
 下表中将提升，而是必需的列具有以下效果：  
  
- 当 IsPromoted 是"N"[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将值写入到上下文，而不是要升级。  
  
- IsRequired 时为布尔值类型，"N"[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]写入仅值如果为 true。  
  
- IsRequired 时对于字符串类型，"N"[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]写入值，如果不为空，或存在默认值。  
  
|                                           属性名称                                            | 提升 | 是必需的 |                                                                                                                                                                      说明                                                                                                                                                                       |
|----------------------------------------------------------------------------------------------------|-------------|-------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                           BatchDateTime                                            |      是      |      否      |                                                                                                [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 处理批处理消息时，将升级此属性。                                                                                                 |
| [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]MessageType |      是      |      是      | 序列化程序使用此属性来区分单个和批处理消息。 HL7 拆装器将其设置仅对消息进行批处理。 该属性指示该消息是一条消息、 入站的批处理消息或出站批消息。 如果序列化程序找不到它，则假定该消息是一条消息。 |
|                                               FHS10                                                |      是      |      否      |                                                                                                [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 处理批处理消息时，将升级此属性。                                                                                                 |
|                                                FHS3                                                |      是      |      否      |                                                                                                [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 处理批处理消息时，将升级此属性。                                                                                                 |
|                                                FHS4                                                |      是      |      否      |                                                                                                [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 处理批处理消息时，将升级此属性。                                                                                                 |
|                                                FHS5                                                |      是      |      否      |                                                                                                [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 处理批处理消息时，将升级此属性。                                                                                                 |
|                                                FHS6                                                |      是      |      否      |                                                                                                [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 处理批处理消息时，将升级此属性。                                                                                                 |
|                                            FileDateTime                                            |      是      |      否      |                                                                                                [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 处理批处理消息时，将升级此属性。                                                                                                 |
|                                    LastSegmentDelimiter 缺少                                    |      否      |      否      |                                                                                                [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 处理批处理消息时，将升级此属性。                                                                                                 |
|                                            邮件类                                            |      是      |      是      |                                                                                                                  包含**MessageClass2X**或**MessageClass2Xml**消息的两个类之间进行区分。                                                                                                                  |
|                                                MSA1                                                |      是      |      是      |                                                                                                                                                        仅适用于 ACK 消息。                                                                                                                                                         |
|                                                MSH1                                                |      否      |      是      |                                                                                                                                   包含字段分隔符的字段。 序列化程序使用此属性。                                                                                                                                   |
|                                                MSH2                                                |      否      |      是      |                                                                                    序列化程序使用此属性。 包含编码字符 （复合元素分隔符、 重复分隔符、 转义符和子组件分隔符） 的字段。                                                                                    |
|                                               MSH3_1                                               |      是      |      否      |                                                                                                                                              发送应用程序字段的第一个组件。                                                                                                                                               |
|                                               MSH3_2                                               |      是      |      否      |                                                                                                                                              发送应用程序字段的第二个组件。                                                                                                                                              |
|                                               MSH3_3                                               |      是      |      否      |                                                                                                                                              发送应用程序字段的第三个组件。                                                                                                                                               |
|                                               MSH5_1                                               |      是      |      否      |                                                                                                                                             接收应用程序字段的第一个组件。                                                                                                                                              |
|                                               MSH5_2                                               |      是      |      否      |                                                                                                                                             接收应用程序字段的第二个组件。                                                                                                                                             |
|                                               MSH5_3                                               |      是      |      否      |                                                                                                                                             接收应用程序字段的第三个组件。                                                                                                                                              |
|                                             ParseError                                             |      是      |      是      |                                                                                                                                                 指示在分析期间发生错误。                                                                                                                                                 |
|                                       SegmentDelimiter2Char                                        |      否      |      否      |                                                                                                                                                      用于分隔段的字符。                                                                                                                                                       |
|                                            ToBeBatched                                             |      是      |      否      |                       如果设置为 false，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]未缓冲的消息进行批处理更高版本; 否则为[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]作为批处理的一部分发送消息。                       |
|                                            ZPartPresent                                            |      是      |      否      |                                                                                                                                              指示是否存在未声明的 Z 段。                                                                                                                                               |
  
## <a name="in-this-section"></a>本节内容  
  
-   [在发送端口上设置筛选表达式](../../adapters-and-accelerators/accelerator-hl7/setting-filter-expressions-on-send-ports.md)