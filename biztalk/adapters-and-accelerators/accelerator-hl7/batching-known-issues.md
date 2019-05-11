---
title: 批处理的已知的问题 |Microsoft Docs
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
ms.openlocfilehash: ae2c9fb3abf43d7eb62c0c78d03c30a33b45995c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65251797"
---
# <a name="batching-known-issues"></a>批处理的已知的问题
本部分包含可帮助你避免批处理错误的有用信息。  
  
## <a name="batch-trailer-segment-fts-and-bts-fields-are-accepted-even-if-they-are-strings"></a>即使它们是字符串接受批处理尾部段 （FTS 和 BTS） 字段  
 HL7 中以不同的方式在各种版本的 HL7 FTS 和 BTS 段指定的字段。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 所有字段定义为字符串数据类型，以避免出现不一致。  
  
## <a name="data-type-of-an-ack-to-a-batch-message"></a>数据类型的批处理消息的确认  
 在为批处理消息，如果碎片源参与方已关闭，则 MSH10 响应中生成的确认 (ACK) 消息字段 (消息控件 ID) 将是一个 GUID，而不是任何其他数据类型的批处理消息中的 MSH10 字段。  
  
## <a name="btahl7-configuration-explorer-and-create-batch-orchestrations-are-not-two-way-synchronized"></a>BTAHL7 配置资源管理器和创建批处理业务流程不是双向同步  
 您可能无法查看批处理控制计划的当前状态，即使您按 F5 在[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器，并可能需要检查[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]当前的配置资源管理器和运行状况与活动跟踪 (HAT) 工具批处理控制计划的状态。  
  
## <a name="two-parsing-errors-logged-when-messages-in-batch-inbatch-out-scenario-contain-validation-errors"></a>两个分析错误记录时中的消息中批处理 / 出批处理方案包含验证错误  
 第一个批处理中的消息时在 / 批处理出方案 （多个消息批处理没有批处理标头） 包含验证错误，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]事件日志中记录两个错误。 第二个错误相关的消息的其余部分和与批处理中的第一个消息相关的第一个错误。  
  
## <a name="subscription-using-the-btsmessagetype-property-for-the-batch-inbatch-out-scenario-with-fragmentation-disabled-is-not-supported"></a>使用 BTS 的订阅。MessageType 属性批处理中不支持批处理出方案具有禁用的碎片  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] 不支持订阅使用**BTS。MessageType**属性批处理中 / 出站批处理方案与碎片可能包含多个消息类型的交换中禁用。  
  
## <a name="entire-batch-suspended-after-erroneous-message-in-the-batch-inbatch-out-scenario"></a>在批处理中的错误消息后挂起整个批次中 / 出站批处理方案  
 如果具有致命分析器错误的消息 (例如， [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] MSH 9 或加载失败的消息的 MSH 12 或正文架构未分析) 时遇到的零碎的批处理中 / Batch 扩展方案中，甚至是挂起的错误消息后的任何数据如果已启用可恢复的交换的支持。  
  
## <a name="batch-of-acks-get-routed-to-the-source-party-of-the-first-message-in-batch-inbatch-out-scenario"></a>批处理确认路由到批处理中的第一个消息的源参与方中 / 出站批处理方案  
 在批处理中 / 方案批处理确认的批处理出获取根据路由源参与方信息的第一条消息，因为此功能假定为入站中的所有消息进行都批处理的源和目标参与方都相同。  
  
## <a name="batch-of-acks-does-not-get-routed-to-the-source-party-when-two-way-receive-port-is-used-in-batch-in-batch-out-scenario"></a>确认的批处理不会不会路由至源参与方时双向接收端口可在批处理中 / 出站批处理方案  
 对于请求-响应接收的端口 ACK/NACK 批处理不会不会路由至 BIBO 方案的源参与方。  
  
## <a name="see-also"></a>请参阅  
 [已知问题](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)