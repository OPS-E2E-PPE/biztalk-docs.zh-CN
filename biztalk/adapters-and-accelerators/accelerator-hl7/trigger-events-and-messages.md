---
title: 触发事件和消息 |Microsoft 文档
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
ms.openlocfilehash: 188d7f1e09ae3f96c953c6a83bbad42ccdce3643
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206533"
---
# <a name="trigger-events-and-messages"></a>触发事件和消息
在数字卫生保健系统中，应用程序由于实际事件，如放置实验室顺序或药品顺序创建 HL7 消息。 HL7 组织已写 HL7 标准基于卫生保健将现实生活中的事件创建对数据应用程序，之间流动，即使这些应用程序跨异类系统的需求的假设。 HL7 标准调用此实际事件*触发器事件*。 自动的系统必须系统地识别触发器事件。  
  
 若要展开此概念，请考虑以下方案。 在一家医院到达时，一个患者在医院使用患者管理软件应用程序中注册。 上提交的患者的记录，该应用程序需要通知其他医院应用程序 （例如会计、 实验室中，依次类推） 有关的患者的注册。 在应用程序之间共享此信息是必需的以便使用这些应用程序的实体可以提供与所需的服务将患者。 注册一个患者的行为是一种触发器事件。 Web 应用程序通常通过创建包含患者记录的数据的 HL7 消息来创建此触发器事件。  
  
 在创建一个或多个消息触发操作的应用程序处理的消息中的操作会导致触发事件。 触发事件时，才在 IT 人员有嵌入其中的部署方案中[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 医院业务线应用程序中。 即使在这种部署方案，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]不需要注意的触发器事件，仅触发器事件生成的消息。  
  
## <a name="see-also"></a>另请参阅  
 [处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [使用 HL7 2.X 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)   
 [使用 HL7 2.XML 架构](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)   
 [HL7 消息传送](../../adapters-and-accelerators/accelerator-hl7/hl7-messaging.md)