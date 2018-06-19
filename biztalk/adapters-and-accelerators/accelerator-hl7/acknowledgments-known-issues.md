---
title: 确认已知的问题 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- known issues, acknowledgements
- acknowledgements, known issues
ms.assetid: cb45f80e-ba89-4b3f-a770-4b1cf9b8e220
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af5964e94f2ddc1d53d5259b174f8e551353711d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204573"
---
# <a name="acknowledgments-known-issues"></a>确认已知的问题
本节包含可以帮助您避免确认 (ACK) 错误的有用信息。  
  
## <a name="hl7-v21-acknowledgment-message-accepted-even-if-it-contains-msa6-field"></a>即使它包含 MSA6 字段接受通信 HL7 2.1 版的确认消息  
 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 将接受 HL7 V2.1 确认消息，即使包含 MSA6 字段。  
  
## <a name="msa-01-value-not-generated-for-commit-acknowledgment-errors"></a>MSA-01 值不会提交确认错误的生成  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]不生成提交确认错误 (CE) MSA-01 确认代码。  
  
## <a name="two-way-mllp-adapter-might-not-detect-a-problem-with-an-ack"></a>双向 MLLP 适配器可能不会检测 ACK 问题  
 当[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]收到 ACK 双向 MLLP 适配器，适配器执行 ACK 以确定其有效性轻型验证。 如果找到有效，则提取 MSA1 字段，而且根据其值，该适配器将重试、 将挂起，或删除原始消息回复 ACK。 但是，由于执行适配器验证不是完整的验证，很可能该适配器将不会检测确认问题 例如，该适配器无法确定 ACK 无效，并且删除原始消息，而管道将确定 ACK 不是格式良好，挂起的确认消息。  
  
## <a name="v2xml-acks-with-multiple-errors-will-fail-validation"></a>V2。使用多个错误的 XML 确认将未通过验证  
 如果传入 V2。XML 消息包含多个错误，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]分析器可能会生成 V2。与错误字段中的多个错误的 XML ACK。 此类 V2。XML ACK 将未通过验证，因为 HL7 标准指定分析器可以报告 V2 中的只有一个错误。XML ACK 错误字段。  
  
## <a name="mllp-performance-counters-do-not-count-acks"></a>MLLP 性能计数器进行计数确认  
 一个度量值[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]性能将由 MLLP 适配器，处理的消息数，如 MLLP 性能计数器所示。 此计数测量接收或传输的消息的数量。 但是，计数不衡量 Ack 接收或发送的数。  
  
## <a name="nak-generated-by-two-way-mllp-adapter"></a>生成的双向 MLLP 适配器否认  
 何时双向 MLLP 适配器挂起消息，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]生成否认 （否定确认） 并将其放在 MessageBox 数据库中。 这可能是意外的行为。 你可能想要从 MessageBox 数据库中删除否认或将其映射到另一条消息。  
  
## <a name="data-type-of-an-ack-to-a-batch-message"></a>数据类型的批处理消息的确认  
 在批处理消息响应中生成一条确认消息，在 MSH10 字段 (消息控件 ID) 将使用的 GUID，而不是基于批处理消息中的 MSH10 字段的数据类型。  
  
## <a name="generated-acknowledgments-doc-type"></a>生成的确认文档类型  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]生成使用文档类型 http:// 确认[!INCLUDE[btsCoName](../../includes/btsconame-md.md)].com/HealthCare/HL7/2X#ACK_24_GLO_DEF 或 http://[!INCLUDE[btsCoName](../../includes/btsconame-md.md)].com/HealthCare/HL7/2X #ACK_25_GLO_DEF。 如果你的目标方使用不同的命名空间，你必须应用中发送端口; 正文映射否则，可能会遇到序列化错误。  
  
## <a name="see-also"></a>另请参阅  
 [已知问题](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)