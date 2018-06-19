---
title: BTAHL72XML 处理 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- 2.XML messages, processing
- acknowledgements, 2.XML messages
- 2.XML messages, message modes
- message modes, 2.XML message
- 2.XML messages
- validating, 2.XML messages
- 2.XML messages, acknowledgements
- 2.XML messages, validating
ms.assetid: 2f12cb44-816c-4773-9db0-9cbc3d1b1aee
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e86697884c28d71fa9fb91c8b276293f7d36a588
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204677"
---
# <a name="btahl72xml-processing"></a>BTAHL72XML 处理
中的以下组件[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 处理 HL7 2.XML （XML 编码） 消息：  
  
-   管道和核心库： [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]。PipelineCommon.dll 和[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]。PipelineMessageCore.dll  
  
-   汇编程序和反汇编程序库： [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]。HL72XmlAsm.dll 和[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]。HL72XmlDAsm.dll  
  
-   用于双向 MLLP 确认 (ACK) 验证库发送适配器： [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]。HL7ACKHelper.dll  
  
## <a name="xml-message-modes"></a>XML 消息模式  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2.XML 消息支持以下的消息模式：  
  
-   发布服务器订阅服务器 （发布-订阅） 模式  
  
     为订阅服务器，为声明性或一个未经请求方广播发布服务器更新。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]提供灵活地此模式下，因为你可以在设计时后管理订阅和方。  
  
-   请求-响应模式  
  
     来自特定实体的特定请求导致响应消息 interrogative 或查询消息交换。  
  
## <a name="xml-validation"></a>XML 验证  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]提供以下的 2.验证 XML 消息：  
  
-   XML 读取器  
  
-   示意图  
  
     启用或禁用由方示意图验证。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]由 MSH9.3 消息结构标头字段和 MSH12 版本 ID 字段 （2.3.1、 2.4 或 2.5），请直接对此处理中，使用 HL7 2.XML 架构。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]使用中的标准 XML 处理功能[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]。  
  
-   Z 段  
  
     [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]验证未声明的 Z 段中包含没有声明的段。  
  
## <a name="ack-generation"></a>ACK 生成  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2.XML 消息支持以下类型的确认 (Ack)。 HL7 错误类型和[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]使用 （备用） 错误类型：  
  
-   HL7 原始确认  
  
-   HL7 增强确认  
  
     提交接受和应用程序接受  
  
## <a name="see-also"></a>另请参阅  
 [消息处理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [使用 HL7 2.XML 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)