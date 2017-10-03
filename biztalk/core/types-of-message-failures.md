---
title: "类型的消息失败 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 466c7c21fd1a00e192307dd82384dc613b6697a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="types-of-message-failures"></a>类型的消息失败
本主题列出了可能会发生消息失败的点。  
  
 **在反汇编阶段失败**  
  
 处理也可能在拆装阶段失败；即在某个管道组件中失败。 例如，由于在处理服务器上没有解密证书而导致解密失败，或者由于架构或消息中的问题而导致解析失败。  
  
 **路由中的故障**  
  
 当消息拆装成功后，下一个可能的故障点就是路由过程；例如，用户启用某个业务流程的相应接收位置，而忘记登记该业务流程。 在这种情况下，从接收位置提取的消息将无法进行路由，MessageBox 数据库将会生成路由故障报告。  
  
 路由故障报告将作为不可恢复的挂起消息列出于 BizTalk Server 管理控制台中。 每个路由故障报告都包含一个在路由故障发生时拍取的消息属性快照。 您可以使用每个报告中的信息为其相关联的消息确定路由失败的原因。 如果相关联的消息可恢复，则可以更正路由问题并恢复该消息，这样，就可以继续进行处理。 将在结果列表中列出路由故障报告，其中服务名和服务类型为空。 在终止已挂起的实例时，Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb 作业将自动删除与已挂起的实例相关联的路由故障报告，默认情况下，该作业每隔一分钟运行一次。 有关 Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb 作业的详细信息，请参阅[数据库结构和作业](../core/database-structure-and-jobs.md)。  
  
 **转换阶段期间出现的故障**  
  
-   **收到消息**。 从接收位置收到消息后，会将消息进行拆装（例如解密或解析），通过接收端口上指定的入站映射可能会选择将消息转换成其他格式，并将其发布到 MessageBox 以路由至业务流程或发送端口。 在这种情况下，在转换阶段中可能会由于入站映射不正确或者架构或收到的消息中存在问题而导致处理失败。  
  
-   **已发送的邮件**。 在将消息发送到发送位置时，在发送端口上配置的出站映射可能会选择转换该消息。 然后，对转换后的消息进行组装，并将其传送给适配器，以最终传输到发送位置。 在这种情况下，在转换阶段中可能会由于出站映射不正确或者架构或源消息中存在问题而导致处理失败。  
  
 **在消息的程序集阶段失败**  
  
 处理也可以在消息组装阶段失败 – 换句话说 ， 在管道组件中失败 。 当消息成功组装后，下一个可能的故障点会出现在向发送位置进行传输的过程中；例如，发送位置（属于合作伙伴）可能已关闭或不存在。  
  
## <a name="see-also"></a>另请参阅  
 [调查业务流程、 端口和消息失败](../core/investigating-orchestration-port-and-message-failures.md)