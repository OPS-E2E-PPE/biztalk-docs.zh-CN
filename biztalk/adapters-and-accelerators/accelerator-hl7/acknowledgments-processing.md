---
title: "确认处理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: acknowledgements, processing
ms.assetid: 705bc12d-69ac-4641-a45e-4f1fab507e4a
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b726eb4698eaa9887703d7df01dc0f6cadf5eefc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="acknowledgments-processing"></a>处理的确认
HL7 规范支持消息的交换的两种格式：  
  
-   未经请求的更新和其确认 (ACK)  
  
-   查询和其响应  
  
 以响应来自启动应用程序的一条消息时，响应的应用程序响应消息，其中包含数据或错误的含义。 启动应用程序可能会受到指示响应方应用程序未正确收到消息的响应方应用程序拒绝状态。 在这两种情况下，消息交换的过程包括两个实体，启动并且能够响应应用程序。 每个是发件人和消息的接收器。 启动应用程序将首先发送，，然后接收，而响应系统接收，然后将发送。  
  
## <a name="unsolicited-updates"></a>未经请求的更新  
 业务线 (LOB) 应用程序发布消息，或触发器事件发生时启动的信息的传输时发生的未经请求的更新。 例如，当一个患者实验室结果可用时，可能有需要实验室结果发送给多个其他系统。 这些更新是 ACK 响应的未经请求的更新。  
  
## <a name="queries"></a>查询  
 在查询时，需要信息的应用程序将查询发送到另一个应用程序，并接收应用程序响应该查询。 例如，药房应用程序可能会发送一条包含到顺序条目 (CPOE) 系统将患者 ID 号的请求消息和接收包含所需的数据，以允许了订单处理的响应。 此请求的事务是一个查询，并且不同的未经请求的更新中。 在响应中包含两个应用程序之间流动的信息。 响应本身不需要使用第四个消息的确认。 但是，你可以修改这在某些环境中使用确认进行响应 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 根据配置中将使用确认进行响应。 查询/响应交换的示例，请参阅[Interrogative 教程](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [验证消息](../../adapters-and-accelerators/accelerator-hl7/validating-messages.md)  
  
-   [ACK 消息模式](../../adapters-and-accelerators/accelerator-hl7/ack-message-modes.md)  
  
-   [ACK 进程模型](../../adapters-and-accelerators/accelerator-hl7/ack-process-model.md)