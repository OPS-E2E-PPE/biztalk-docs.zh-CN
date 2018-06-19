---
title: 批处理已知的问题 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching, known issues
- known issues, batching
ms.assetid: 25c645eb-845d-483a-8f77-398e7dfe0c8f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b47246662c5945f8ef09040ec7a8aa49326f59db
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204493"
---
# <a name="batching-known-issues"></a>批处理的已知的问题
本节包含可以帮助您避免批处理错误的有用信息。  
  
## <a name="batch-trailer-segment-fts-and-bts-fields-are-accepted-even-if-they-are-strings"></a>即使它们是字符串接受批处理预告片段 （FT 和 BTS） 字段  
 HL7 以不同方式在各种版本的 HL7 的 ft 数和 BTS 段中指定的字段。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]作为要避免出现不一致的字符串数据类型中定义的所有字段。  
  
## <a name="data-type-of-an-ack-to-a-batch-message"></a>数据类型的批处理消息的确认  
 在确认 (ACK) 消息以响应批处理消息，如果源方的碎片处于关闭状态，然后 MSH10 生成字段 (消息控件 ID) 将使用的 GUID，而不是任何其他数据类型的批处理消息中的 MSH10 字段。  
  
## <a name="btahl7-configuration-explorer-and-create-batch-orchestrations-are-not-two-way-synchronized"></a>BTAHL7 配置资源管理器和创建批处理业务流程不是双向同步  
 你可能无法查看批处理控制计划的当前状态，即使按 F5 在[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器，并且可能必须同时检查[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]当前的配置资源管理器的运行状况和活动跟踪 (HAT) 工具批处理控制计划的状态。  
  
## <a name="two-parsing-errors-logged-when-messages-in-batch-inbatch-out-scenario-contain-validation-errors"></a>两个分析错误记录时中的消息中批处理 / 批处理出方案包含验证错误  
 第一个批处理中的消息时在 / 批处理出方案 （多个消息批处理不带批处理标头） 包含验证错误[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]记录事件日志中的两个错误。 第一个错误与批处理中的第一条和第二个错误与消息的其余部分。  
  
## <a name="subscription-using-the-btsmessagetype-property-for-the-batch-inbatch-out-scenario-with-fragmentation-disabled-is-not-supported"></a>使用 BTS 的订阅。批处理的 MessageType 属性中批处理出方案具有禁用的碎片不受支持  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]不支持订阅使用**BTS。MessageType**批处理的属性中 / 与碎片可能包含多个消息类型的交换中禁用批处理出方案。  
  
## <a name="entire-batch-suspended-after-erroneous-message-in-the-batch-inbatch-out-scenario"></a>在批处理中的错误消息之后挂起的整批中 / 批处理出方案  
 如果出现分析器错误的消息 (例如，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]不会分析 MSH 9 或加载失败的消息的 MSH 12 或正文架构) 中碎片的批次遇到中 / 批处理出方案中，甚至是挂起的错误消息后的任何数据如果已启用可恢复的交换支持。  
  
## <a name="batch-of-acks-get-routed-to-the-source-party-of-the-first-message-in-batch-inbatch-out-scenario"></a>批处理的确认路由到批处理中的第一个消息的源当事方在 / 批处理出方案  
 在批处理中 / 批处理出方案批处理的 Ack 获取根据路由源方信息的第一条消息，因为此功能可假定为入站中的所有消息都批处理源和目标方是相同。  
  
## <a name="batch-of-acks-does-not-get-routed-to-the-source-party-when-two-way-receive-port-is-used-in-batch-in-batch-out-scenario"></a>批处理的 Ack 不未获取路由到源方时双向接收在批处理作业中使用端口中 / 批处理出方案  
 如果请求-响应接收的端口 ACK/NACK 批处理不未获取路由到 BIBO 方案的源方。  
  
## <a name="see-also"></a>另请参阅  
 [已知问题](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)