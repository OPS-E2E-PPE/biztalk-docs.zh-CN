---
title: 如何消息流经 BTAHL7 |Microsoft 文档
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
ms.openlocfilehash: 33f06c896b58b2ba57c8c1bcee598d23f81b7700
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008318"
---
# <a name="how-messages-flow-through-btahl7"></a>如何消息流经 BTAHL7
当你安装[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 的顶部[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Server 中，你将添加[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]组件[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]体系结构。 下图显示了组合的系统提供的体系结构概述[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]。  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/bcd-hl7-sys-archc.gif "bcd_hl7_sys_archc")  
  
## <a name="message-processing-flow"></a>消息处理流程  
 当业务线应用程序发送一条消息给[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]系统，将发生以下情况：  
  
1.  如果消息的 HL7 消息，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]接收通过适配器 （通常 MLLP 适配器）。 如果它是一条 XML 消息，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]接收通过适配器 （通常 HTTP 适配器）。  
  
    > [!NOTE]
    >  你可以通过任何适配器; 传输 2.X 和 2.XML 消息但是，你通常将传输 V2。通过 MLLP 适配器，并且你的 X 消息通常会通过 HTTP 适配器传输 2.XML 消息。  
  
2.  将消息路由通过分析通过反汇编程序，并验证接收管道。  
  
    1.  如果传入消息的 HL7 消息，平面文件反汇编程序 (DASM) 会将其分解为 XML。 如果传入消息是一条 XML 消息，则 XML DASM 反汇编它。  
  
    2.  如果传入消息批处理消息，拆装器将分解为单独的消息。 (有关更多详细信息，请参阅[批处理消息](../../adapters-and-accelerators/accelerator-hl7/batch-message-processing.md)和[消息批处理](../../adapters-and-accelerators/accelerator-hl7/message-batching.md)。)  
  
    3.  DASM 然后验证消息。  
  
    4.  如果你使用的双向 MLLP 接收适配器，并且如果拆装器已验证消息，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将确认 (ACK) 发送到同一个适配器接收原始消息通过消息的原始发送方。 如果没有，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将发送否定确认 （否认）。 （如何完成此步骤依赖于 ACK 配置。 有关详细信息，请参阅[ACK 消息模式](../../adapters-and-accelerators/accelerator-hl7/ack-message-modes.md)。)  
  
    5.  如果未使用的双向 MLLP 接收适配器，然后[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]生成 ACK 或确认 （或否认或 NAKs），并放入 MessageBox 数据库。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]然后将它路由到相应的部门基于发送端口配置，可以使用它的任何其他适配器 （除了 MLLP)。  
  
     在平面文件和 XML 反汇编程序中执行的进程的更完整列表，请参阅[BizTalk Accelerator for HL7 组件](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)。  
  
3.  消息传递和接收管道中，该适配器后[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将该消息传递到 MessageBox 数据库。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]然后，确定下一步将消息发送到何处。 如果消息是业务流程的一部分，它会将消息发送到业务流程引擎。  
  
4.  业务流程引擎处理的消息。  
  
    1.  如果地图会影响消息，该映射将根据其规则消息转换。  
  
    2.  如果已经设置了业务规则，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]调用外部管道，可能在业务流程引擎业务规则引擎 (BRE)。  
  
    3.  业务流程引擎将消息发送回 MessageBox 数据库，然后继续处理业务流程。  
  
5.  根据订阅，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]将消息路由到发送端口。  
  
6.  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将以下的处理，（如果适用） 发送管道通过消息路由： 程序集和验证。  
  
    1.  如果该消息将是 HL7 2.X 消息[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将消息从 XML 组合到 HL7 通过平面文件汇编器 (ASM)。 如果传入的消息将一条 XML 消息，则 XML DASM 汇编它。  
  
    2.  如果该消息将作为一部分的批处理消息，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]组合成批处理消息的每条消息。 (有关更多详细信息，请参阅[批处理消息](../../adapters-and-accelerators/accelerator-hl7/batch-message-processing.md)和[消息批处理](../../adapters-and-accelerators/accelerator-hl7/message-batching.md)。)  
  
    3.  ASM 验证消息 （如果启用通过发送方配置设置）。  
  
     平面文件和 XML 汇编程序中执行的进程的更完整列表，请参阅[BizTalk Accelerator for HL7 组件](../../adapters-and-accelerators/accelerator-hl7/biztalk-accelerator-for-hl7-components.md)。  
  
7.  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]将通过适配器消息发送。  
  
    > [!NOTE]
    >  你可以在大量的适配器; 传输 2.X 消息和 2.XML 消息但是，大多数系统传输 MLLP 适配器，通过的 2.X 消息和 2.通过 HTTP 适配器的 XML 消息。  
  
## <a name="see-also"></a>另请参阅  
 [BTAHL7 如何路由消息](../../adapters-and-accelerators/accelerator-hl7/how-btahl7-routes-messages.md)