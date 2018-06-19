---
title: 与 BizTalk Server 相关的属性 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [MQSeries adapters], properties
- CompleteMessage property [MQSeries adapters]
- SSOAffiliateApplication property [MQSeries adapters]
- Ordered property [MQSeries adapters]
- TransactionSupported property [MQSeries adapters]
- BizTalk_CorrelationID property [MQSeries adapters]
- SegmentationAllowed property [MQSeries adapters]
- DynamicReceive property [MQSeries adapters]
- MQSeries adapters, properties
- DataConversion property [MQSeries adapters]
ms.assetid: c27d7f9c-8198-4624-9952-054ba8ea1c7c
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f729e4ab359471e002029efc04c0c8ad21e0d99b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269653"
---
# <a name="properties-related-to-biztalk-server"></a>与 BizTalk Server 相关的属性
MQSeries 适配器可以为某些不直接与 MQSeries 相关但仍在应用程序中有用的上下文属性赋值。  
  
 所有属性在发送和接收除期间都接收值**BizTalk_CorrelationID**。 **BizTalk_CorrelationID**属性具有仅在接收过程的值。  
  
|Name|类型|Description|  
|----------|----------|-----------------|  
|**BizTalk_CorrelationID**|string|使用此属性可使 MQSeries 服务器生成用于消息的相关标识符。<br /><br /> 有关详细信息，请参阅[关联消息使用请求-答复](../core/correlating-messages-using-request-reply.md)。|  
|**数据转换**|string|将消息转换为 MQSeries Server for Windows 的 ANSI 代码页。 在发送时，如果消息格式不是 MQFMT_STRING，则不会进行转换。<br /><br /> 选择**是**来执行从 Unicode 此转换为 ANSI。<br /><br /> **默认值：** 否|  
|**排序**|string|将 MQSeries 设置为从 MQSeries 队列接收消息或向其发送消息时保持消息的顺序。<br /><br /> 该属性对于接收和发送具有不同的值的集合。 有关值的信息，请参阅。 [如何配置 MQSeries 适配器接收位置和发送端口](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md)。<br /><br /> **默认值：** 否|  
|**SegmentationAllowed**|string|将 MQSeries 设置为组装已分段的消息，或设置为按原样获取消息。 该属性对于接收和发送具有不同的值的集合。<br /><br /> 在接收时，使用**No Action**从 MQSeries 队列读取消息，而不启用分段; 使用**完整的消息**能够 MQSeries 之前将它们传递给上装配分段的消息适配器。<br /><br /> **默认值：** 任何操作<br /><br /> 发送时，选择**是**来获得 MQSeries 分段的消息放入队列。<br /><br /> **默认值：** 否|  
|**SSOAffiliateApplication**|string|设置单一登录 (SSO) 关联应用程序。 你使用的用户 ID 和密码的 SSO **MQMD_UserIdentifier**，和**MQIIH_Authenticator** (或**MQCIH_Authenticator**) 属性分别。<br /><br /> 仅在发送消息时使用。<br /><br /> **默认值：** 空白|  
|**CompleteMessage**|string|指定在从队列中检索已分段的消息时是否检索“完整消息”。<br /><br /> 将其设置为**是**若要检索的"完成消息"的分段队列中的消息。<br /><br /> **默认值：** 否|  
|**DynamicReceive**|string|指定是否从队列中动态地检索消息。<br /><br /> 将其设置为**是**在动态从队列接收消息时。 此功能与要求响应发送端口结合使用。<br /><br /> 如果指定匹配选项（MessageID、CorrelationID 或 GroupID），则仅检索与匹配条件相关的消息。|  
|**TransactionSupported**|string|此适配器将在 BizTalk Server 和 MQSeries 服务器之间开始 Microsoft 分布式事务处理协调器 (DTC) 事务。 当设置为**否**，就不能保证的消息传递。<br /><br /> **默认值：** 是|  
|**WaitInterval**|string|指定 MQ 系统等待适当消息到达的大致时间（以秒表示）。 如果在此时间内没有适当的消息到达，则该调用失败。 **注意：** 这可以在一个业务流程中设置。 <br /><br /> **默认值：** 3|  
  
## <a name="see-also"></a>另请参阅  
 [MQSeries 适配器属性](../core/mqseries-adapter-properties.md)   
 [数据类型转换的属性](../core/data-type-conversion-of-properties.md)   
 [MQSeries 上下文属性](../core/mqseries-context-properties.md)