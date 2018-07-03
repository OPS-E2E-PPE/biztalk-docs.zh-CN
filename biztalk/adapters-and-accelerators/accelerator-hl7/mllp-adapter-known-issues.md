---
title: MLLP 适配器已知问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MLLP adapters, known issues
- known issues, MLLP adapters
ms.assetid: 66af8fcc-981a-4a77-80b7-84824bfae608
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb90c62baebb8fc73b939c0a3ea20eb85e9b0e28
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970830"
---
# <a name="mllp-adapter-known-issues"></a>MLLP 适配器已知问题
本部分包含可帮助你避免最少的较低层协议 (MLLP) 适配器错误的有用信息。  
  
## <a name="two-way-mllp-adapter-might-not-detect-a-problem-with-an-ack"></a>双向处的 MLLP 适配器可能没有检测到一个 ACK 的问题  
 当 Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]) 接收的确认 (ACK) 上的双向 MLLP 适配器，适配器将执行上确认以确定其有效性的轻量验证。 如果找到有效，提取 MSA1 字段，并根据其值，适配器将重试次数、 挂起或删除原始消息回复确认。 但是，由于适配器执行的验证不是完整的验证，则可能适配器将不会检测问题的确认。 例如，适配器可以确定将确认有效，并且删除原始消息，而该管道会确定确认不是格式正确，并挂起的确认消息。  
  
## <a name="mllp-performance-counters-do-not-count-acks"></a>MLLP 性能计数器进行计数的 Ack  
 一个性能度量值将由 MLLP 适配器，处理的消息数，如 MLLP 性能计数器所示。 此计数度量值接收或传输的消息的数。 但是，计数不衡量确认已接收或发送数。  
  
## <a name="mllp-adapter-connection-names-are-not-guaranteed-to-be-unique"></a>MLLP 适配器连接名称不能保证是唯一的  
 [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)] 不保证处的 MLLP 适配器的属性页中输入的连接名称的唯一性。 请确保该名称在此必填字段中输入的描述性和相关连接。 尝试了解连接的行为时，使用表示业务线应用程序的连接名称可能会很有用。 例如，PerfMon 计数器使用的连接名称。  
  
> [!NOTE]
>  BTAHL7 确保唯一性的接收位置或发送端口名称。  
  
## <a name="two-way-mllp-adapters-do-not-send-commit-acks-for-all-messages-in-a-batch"></a>双向 MLLP 适配器不会发送一批中的所有消息的提交确认  
 生成了提交确认，批处理中配置每个消息和系统发送到批处理时双向 MLLP 接收适配器，适配器仅发送与批处理中的第一个消息对应提交确认。  
  
> [!NOTE]
>  建议使用单向处的 MLLP 适配器传输批。  
  
## <a name="nak-generated-by-two-way-mllp-adapter"></a>生成的双向处的 MLLP 适配器 NAK  
 双向处的 MLLP 适配器将挂起任何消息，当处的 MLLP 适配器生成 NAK （否定确认），并将其放置在 MessageBox 数据库中。 这可能会出现意外的行为。 您可能想要从 MessageBox 数据库删除 NAK 或将其映射到另一条消息。  
  
## <a name="two-way-mllp-adapter-only-supports-the-2x-message-format"></a>双向处的 MLLP 适配器仅支持 2.X 消息格式  
 双向处的 MLLP 适配器目前支持仅 2.X 消息格式。  
  
## <a name="two-way-mllp-adapter-does-not-support-static-acknowledgments"></a>双向处的 MLLP 适配器不支持静态确认  
 双向发送适配器不支持处理静态确认。  
  
## <a name="see-also"></a>请参阅  
 [已知问题](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)