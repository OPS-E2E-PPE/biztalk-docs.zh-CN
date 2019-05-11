---
title: 消息失败的类型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- transformation stage
- assembly stage
- errors, disassembly stage
- errors, assembly stage
- routing, errors
- errors, transformation stage
- errors, messages [HAT]
- errors, routing
- disassembly stage, errors
- messages, errors [HAT]
ms.assetid: 3a8e1c58-4b53-4439-837d-aaa233eb9158
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 34c72db5870f89525a6a0db5f88a54bbe2db3f24
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65268813"
---
# <a name="types-of-message-failures"></a>消息失败的类型
本主题列出了可能发生消息故障时的不同时间点。  
  
 **在拆装阶段失败**  
  
 在拆装阶段中; 也可能会失败处理也就是说，一个管道组件中的故障。 例如，解密失败，因为没有由于架构中或在消息中的问题进行分析失败的处理服务器上的解密证书。  
  
 **路由过程中失败**  
  
 当消息拆装成功后下, 一步的潜在故障点就路由;例如，相应的用户启用接收位置的业务流程，而忘记登记业务流程。 在这种情况下，无法从接收位置提取的消息进行路由，MessageBox 数据库会生成路由故障报告。  
  
 BizTalk Server 管理控制台中作为不可恢复的挂起消息列出路由故障报告。 每个路由故障报告包含消息属性时拍取路由故障发生。 可以使用每个报表中的信息来确定路由失败的原因为其关联的消息。 如果相关联的消息是可恢复，可以更正路由问题并恢复该消息，以便继续进行处理。 具有空白服务名称和服务类型的结果列表中列出路由故障报告。 终止挂起的实例时，默认情况下运行每隔一分钟的 Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb 作业自动删除与挂起的实例关联的路由故障报告。 有关 Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb 作业的详细信息，请参阅[数据库结构和作业](../core/database-structure-and-jobs.md)。  
  
 **在转换阶段失败**  
  
- **收到的消息**。 当从接收位置收到的消息时，该消息被拆装 （例如解密或解析），消息可能会根据需要转换为入站映射指定接收端口，并将发布到 MessageBox 中以便通过不同的格式路由到业务流程或发送端口。 在这种情况下，处理可能会在转换阶段，由于不正确的入站映射或架构中或在收到的消息时出现问题而失败。  
  
- **发送的消息，**。 当消息发送到发送位置时，发送端口上配置出站映射可能会选择转换该消息。 然后转换后的消息是收集组，并且传递到适配器以最终传输到发送位置。 在这种情况下，处理可能会在转换阶段，由于不正确的出站映射或架构或源消息中的问题而失败。  
  
  **在消息组装阶段中失败**  
  
  处理可能也会失败在消息组装阶段 – 换而言之，在管道组件中的失败。 当消息成功组装后下, 一步的潜在故障点将恢复传输到发送位置;例如，发送位置 （属于合作伙伴） 可能已关闭或不存在。  
  
## <a name="see-also"></a>请参阅  
 [调查业务流程、端口和消息失败](../core/investigating-orchestration-port-and-message-failures.md)