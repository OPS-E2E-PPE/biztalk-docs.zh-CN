---
title: 确认处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- acknowledgements, processing
ms.assetid: 705bc12d-69ac-4641-a45e-4f1fab507e4a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb8bf0620c3e336317382cbeb299cf2d6d17faa2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969462"
---
# <a name="acknowledgments-processing"></a>确认处理
HL7 规范支持两种格式中的消息交换：  
  
- 未经请求的更新和其确认 (ACK)  
  
- 查询和其响应  
  
  起始应用程序的消息响应，响应的应用程序使用一条消息，包括数据或错误指示做出响应。 起始应用程序可能会收到指示响应方应用程序未正确收到消息的响应方应用程序从拒绝状态。 在这两种情况下，消息交换的过程包括两个实体，起始和响应应用程序。 每个是发送方和接收方的消息。 起始应用程序将发送第一次，然后接收，而响应系统接收，然后将发送。  
  
## <a name="unsolicited-updates"></a>未经请求的更新  
 业务线 (LOB) 应用程序发布消息，或触发事件发生时启动的信息传输时发生未经请求的更新。 例如，为患者实验室结果可用时，可能有需要实验室结果发送到多个其他系统。 这些更新是 ACK 响应的未经请求的更新。  
  
## <a name="queries"></a>查询  
 在查询时，需要的信息的应用程序将查询发送到另一个应用程序，并接收应用程序响应查询。 例如，一个药学应用程序可能会发送包含订单条目 (CPOE) 系统对患者 ID 号的请求消息和接收包含所需的数据，以允许订单处理的响应。 此请求的事务是一个查询，并且不同的未经请求的更新中。 在响应中包含两个应用程序之间流动的信息。 响应本身不需要带有第四个消息的确认。 但是，您可以修改此使用确认进行响应的某些环境中 Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 根据配置使用确认进行响应。 查询/响应交换的示例，请参阅[询问教程](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [验证消息](../../adapters-and-accelerators/accelerator-hl7/validating-messages.md)  
  
-   [ACK 消息模式](../../adapters-and-accelerators/accelerator-hl7/ack-message-modes.md)  
  
-   [ACK 进程模型](../../adapters-and-accelerators/accelerator-hl7/ack-process-model.md)