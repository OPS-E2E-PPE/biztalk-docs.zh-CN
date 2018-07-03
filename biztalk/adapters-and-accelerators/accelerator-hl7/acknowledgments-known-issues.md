---
title: 确认已知的问题 |Microsoft Docs
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
ms.openlocfilehash: 1f585c9f0b147f50bd915bb757a3ed3c09a56ee8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966150"
---
# <a name="acknowledgments-known-issues"></a>确认已知的问题
本部分包含可帮助你避免确认 (ACK) 错误的有用信息。  
  
## <a name="hl7-v21-acknowledgment-message-accepted-even-if-it-contains-msa6-field"></a>HL7 2.1 版的确认消息，即使它包含 MSA6 字段会被接受  
 Microsoft [!INCLUDE[btaBTAHL7NoNumber](../../includes/btabtahl7nonumber-md.md)] ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 将接受，即使包含 MSA6 字段一 HL7 2.1 版的确认消息。  
  
## <a name="msa-01-value-not-generated-for-commit-acknowledgment-errors"></a>MSA 01 值不生成的提交确认错误  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 不会生成提交确认错误 (CE) 的 MSA 01 确认代码。  
  
## <a name="two-way-mllp-adapter-might-not-detect-a-problem-with-an-ack"></a>双向处的 MLLP 适配器可能没有检测到一个 ACK 的问题  
 当[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]收到 ACK 上双向处的 MLLP 适配器，适配器执行轻量验证上确认以确定其有效性。 如果找到有效，提取 MSA1 字段，并根据其值，适配器将重试次数、 挂起或删除原始消息回复确认。 但是，由于适配器执行的验证不是完整的验证，则可能适配器将不会检测问题的确认。 例如，适配器可以确定将确认有效，并且删除原始消息，而该管道会确定确认不是格式正确，并挂起的确认消息。  
  
## <a name="v2xml-acks-with-multiple-errors-will-fail-validation"></a>V2。带有多个错误的 XML Ack 验证将失败  
 如果传入 V2。XML 消息包含多个错误，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]分析器可能会生成 V2。在错误字段中的多个错误的 XML 确认。 此类第 2 版。XML 确认将验证失败，因为 HL7 标准指定分析器可以报告 V2 中的只有一个错误。XML 确认错误字段。  
  
## <a name="mllp-performance-counters-do-not-count-acks"></a>MLLP 性能计数器进行计数的 Ack  
 一个度量值的[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]性能将 MLLP 适配器，处理的消息数，如 MLLP 性能计数器所示。 此计数度量值接收或传输的消息的数。 但是，计数不衡量确认已接收或发送数。  
  
## <a name="nak-generated-by-two-way-mllp-adapter"></a>生成的双向处的 MLLP 适配器 NAK  
 双向处的 MLLP 适配器挂起消息，当[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]生成 NAK （否定确认），并将它放在 MessageBox 数据库。 这可能会出现意外的行为。 您可能想要从 MessageBox 数据库删除 NAK 或将其映射到另一条消息。  
  
## <a name="data-type-of-an-ack-to-a-batch-message"></a>数据类型的批处理消息的确认  
 在响应的批处理消息中生成的确认消息，MSH10 字段 (消息控件 ID) 将是一个 GUID，而不是基于批处理消息中的 MSH10 字段的数据类型。  
  
## <a name="generated-acknowledgments-doc-type"></a>生成的确认文档类型  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 生成使用文档类型的确认http://Microsoft.com/HealthCare/HL7/2X#ACK_24_GLO_DEF或http://Microsoft.com/HealthCare/HL7/2X#ACK_25_GLO_DEF。 如果目标参与方使用不同的命名空间，则必须应用的正文映射中的发送端口;否则，可能会遇到序列化错误。  
  
## <a name="see-also"></a>请参阅  
 [已知问题](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)