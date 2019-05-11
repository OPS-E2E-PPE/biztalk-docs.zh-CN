---
title: 消息如何流经 BTAHL7 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, message processing
- messages, message flow
- BTAHL7, message flow
ms.assetid: dd4599af-500d-4e52-85b2-8b6a28fd3f0a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2b048ee47ca90b47644286cef90b9937b8a20bb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65296379"
---
# <a name="how-messages-flow-through-btahl7"></a>如何将消息流通过 BTAHL7
安装 Microsoft BizTalk Accelerator for HL7 时 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 添加 MicrosoftBizTalk Server 之上[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]组件[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]体系结构。 下图显示了组合的系统提供的体系结构概述[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/bcd-hl7-sys-archc.gif "bcd_hl7_sys_archc")  
  
## <a name="message-processing-flow"></a>消息处理流  
 当业务线应用程序发送一条消息[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]系统中，将发生以下情况：  
  
1. 如果消息是 HL7 消息，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]接收通过适配器 （通常 MLLP 适配器）。 如果它是一条 XML 消息，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]接收通过适配器 （通常 HTTP 适配器）。  
  
   > [!NOTE]
   >  可以通过任何适配器; 传输 2.X 和 2.xml XML 消息但是，通常会传输 V2。X 消息通过 MLLP 适配器，并且您通常会通过 HTTP 适配器传输 2.XML 消息。  
  
2. 通过分析由拆装器和验证的接收管道路由消息。  
  
   1. 如果传入消息的 HL7 消息，平面文件拆装器 (DASM) 会将其分解为 XML。 如果传入消息是一条 XML 消息，XML DASM 分解它。  
  
   2. 如果传入消息批消息，拆装器将分解为各个消息。 (有关更多详细信息，请参阅[批处理消息](../../adapters-and-accelerators/accelerator-hl7/batch-message-processing.md)并[消息批处理](../../adapters-and-accelerators/accelerator-hl7/message-batching.md)。)  
  
   3. DASM 然后验证消息。  
  
   4. 如果您使用的双向 MLLP 接收适配器，并且如果拆装器已验证消息，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]向通过相同的适配器接收原始消息的消息的原始发件人发送确认 (ACK)。 如果没有，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]发送否定确认 (NAK)。 （如何完成此步骤取决于确认配置。 有关详细信息，请参阅[ACK 消息模式](../../adapters-and-accelerators/accelerator-hl7/ack-message-modes.md)。)  
  
   5. 如果不使用双向 MLLP 接收适配器，然后[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]生成确认或确认 （NAK 或 NAKs），并放到 MessageBox 数据库。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 然后将它路由到相应的部门根据发送端口配置可使用任何其他适配器 （除了 MLLP)。  
  
      在平面文件和 XML 拆装器中执行的进程的完整的列表，请参阅[BizTalk Accelerator for HL7 组件](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)。  
  
3. 通过在适配器和接收管道中，该消息会传递后[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将消息传递到 MessageBox 数据库。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 然后确定接下来发送消息的位置。 如果消息是业务流程的一部分，它将消息发送到业务流程引擎。  
  
4. 业务流程引擎处理的消息。  
  
   1. 如果映射会影响该消息，该映射将转换根据其规则的消息。  
  
   2. 如果已经设置了业务规则，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]调用管道中，可能会以业务流程引擎外部业务规则引擎 (BRE)。  
  
   3. 业务流程引擎将消息发送回 MessageBox 数据库，然后继续处理业务流程。  
  
5. 根据该订阅，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]将消息路由到发送端口。  
  
6. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 通过以下处理 （如果适用） 的发送管道将消息路由： 程序集和验证。  
  
   1. 如果该消息将 HL7 2.X 消息[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将消息从 XML 组合到 HL7 的平面文件组装器 (ASM)。 如果传入消息将是一条 XML 消息，XML DASM 组合它们。  
  
   2. 如果该消息将属于批处理消息，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将每个消息组装为批处理消息。 (有关更多详细信息，请参阅[批处理消息](../../adapters-and-accelerators/accelerator-hl7/batch-message-processing.md)并[消息批处理](../../adapters-and-accelerators/accelerator-hl7/message-batching.md)。)  
  
   3. ASM 验证消息 （如果启用通过发送参与方配置设置）。  
  
      在平面文件和 XML 组装器中执行的进程的完整的列表，请参阅[BizTalk Accelerator for HL7 组件](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)。  
  
7. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 通过适配器将消息发送。  
  
   > [!NOTE]
   >  您可以在的适配器; 内传输 2.X 消息和 2.XML 消息但是，大多数系统传输 MLLP 适配器，通过 2.X 消息和 2.通过 HTTP 适配器的 XML 消息。  
  
## <a name="see-also"></a>请参阅  
 [BTAHL7 如何路由消息](../../adapters-and-accelerators/accelerator-hl7/how-btahl7-routes-messages.md)