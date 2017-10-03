---
title: "MLLP 适配器已知问题 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MLLP adapters, known issues
- known issues, MLLP adapters
ms.assetid: 66af8fcc-981a-4a77-80b7-84824bfae608
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5cbae1bf4bf04e2ecf4e643ad5107b9e0fd70f70
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="mllp-adapter-known-issues"></a>MLLP 适配器已知问题
本节包含可以帮助您避免最小较低层协议 (MLLP) 适配器错误的有用信息。  
  
## <a name="two-way-mllp-adapter-might-not-detect-a-problem-with-an-ack"></a>双向 MLLP 适配器可能不会检测 ACK 问题  
 当[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]) 收到确认 (ACK) 上的双向 MLLP 适配器，适配器执行 ACK 以确定其有效性轻型验证。 如果找到有效，则提取 MSA1 字段，而且根据其值，该适配器将重试、 将挂起，或删除原始消息回复 ACK。 但是，由于执行适配器验证不是完整的验证，很可能该适配器将不会检测确认问题 例如，该适配器无法确定 ACK 无效，并且删除原始消息，而管道将确定 ACK 不是格式良好，挂起的确认消息。  
  
## <a name="mllp-performance-counters-do-not-count-acks"></a>MLLP 性能计数器进行计数确认  
 性能的一个度量值将由 MLLP 适配器，处理的消息数，如 MLLP 性能计数器所示。 此计数测量接收或传输的消息的数量。 但是，计数不衡量 Ack 接收或发送的数。  
  
## <a name="mllp-adapter-connection-names-are-not-guaranteed-to-be-unique"></a>不保证 MLLP 适配器连接名称都是唯一的  
 [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]不保证 MLLP 适配器的属性页中输入的连接名称的唯一性。 确保在此必填字段中输入名称该具说明性且更相关连接。 尝试了解连接行为时，使用表示业务线应用程序的连接名称很有用。 例如，PerfMon 计数器使用的连接名称。  
  
> [!NOTE]
>  BTAHL7 可以确保的唯一性接收位置或发送端口名称。  
  
## <a name="two-way-mllp-adapters-do-not-send-commit-acks-for-all-messages-in-a-batch"></a>双向 MLLP 适配器不会发送一批中的所有消息提交确认  
 当在一个批次以生成提交的 ACK，配置每条消息，然后系统会将发送到批处理双向 MLLP 接收适配器，适配器就只会发送提交 ACK 对应批处理中的第一个消息。  
  
> [!NOTE]
>  建议使用单向 MLLP 适配器来传输批次。  
  
## <a name="nak-generated-by-two-way-mllp-adapter"></a>生成的双向 MLLP 适配器否认  
 当双向 MLLP 适配器将挂起任何消息时，MLLP 适配器生成否认 （否定确认），并将它放在 MessageBox 数据库中。 这可能是意外的行为。 你可能想要从 MessageBox 数据库中删除否认或将其映射到另一条消息。  
  
## <a name="two-way-mllp-adapter-only-supports-the-2x-message-format"></a>双向 MLLP 适配器仅支持 2.X 消息格式  
 双向 MLLP 适配器当前支持 2.X 的消息格式。  
  
## <a name="two-way-mllp-adapter-does-not-support-static-acknowledgments"></a>双向 MLLP 适配器不支持静态确认  
 双向发送适配器不支持处理静态确认。  
  
## <a name="see-also"></a>另请参阅  
 [已知问题](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)