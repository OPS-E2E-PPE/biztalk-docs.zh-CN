---
title: 触发事件和消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- health care organizations, HL7 messages
- trigger events
- messages, trigger events
- messages, about messages
ms.assetid: e93b397c-8cbe-4589-aa88-e474d7722174
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 309d420d97cdc22c4f0eaca30bb6426e295cbe33
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971606"
---
# <a name="trigger-events-and-messages"></a>触发器事件和消息
在数字卫生保健系统中，应用程序由于实际发生的事件，例如放置在实验室的订单或药物顺序创建 HL7 消息。 HL7 组织撰写了 HL7 标准基于美国卫生保健的真实世界中的事件创建对数据以流的应用程序之间，即使这些应用程序跨异类系统的需求的假设。 HL7 标准调用此实际发生的事件*触发器事件*。 自动的系统必须系统地识别触发器事件。  
  
 若要扩展此概念，请考虑以下方案。 在一家医院到达时，患者在医院使用患者管理软件应用程序中注册。 上提交的患者记录，该应用程序需要通知其他医院应用程序 （如会计、 实验室中，依次类推） 有关的患者注册。 在应用程序之间共享此信息是必需的以便使用这些应用程序的实体可以提供所需的服务与患者。 注册一个患者是一种触发器事件。 Web 应用程序通常通过创建包含患者记录的数据的 HL7 消息创建此触发器事件。  
  
 触发事件始终导致创建一个或多个触发操作处理消息的应用程序中的消息。 触发器事件都相关的 IT 人员有嵌入的 Microsoft BizTalk Accelerator for HL7 的部署方案中 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 医院业务线应用程序中。 即使在部署这种情况下，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]不需要注意的触发器事件，仅触发器事件生成的消息。  
  
## <a name="see-also"></a>请参阅  
 [处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [使用 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)   
 [使用 HL7 2.xml 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)   
 [HL7 消息传送](../../adapters-and-accelerators/accelerator-hl7/hl7-messaging.md)