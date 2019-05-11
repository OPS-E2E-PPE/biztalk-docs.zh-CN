---
title: 与 BizTalk Server 相关的属性 |Microsoft Docs
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
ms.openlocfilehash: 2259a0bed420fdaf9c8b0dbe3f07d27cd8bbc454
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398506"
---
# <a name="properties-related-to-biztalk-server"></a>与 BizTalk Server 相关的属性
MQSeries 适配器将值分配给不直接与 MQSeries 相关但仍可在应用程序中的某些上下文属性。  
  
 所有属性在发送和接收除期间都收到的值**BizTalk_CorrelationID**。 **BizTalk_CorrelationID**属性仅在接收过程的值。  
  
|“属性”|类型|Description|  
|----------|----------|-----------------|  
|**BizTalk_CorrelationID**|string|此属性用于使 MQSeries 服务器生成用于消息的相关标识符。<br /><br /> 有关详细信息，请参阅[关联的消息使用请求-答复](../core/correlating-messages-using-request-reply.md)。|  
|**DataConversion**|string|对于 Windows，该消息转换为 MQSeries 服务器的 ANSI 代码页。 在发送时，如果消息格式不是 MQFMT_STRING，则不进行转换。<br /><br /> 选择**是**来执行从 Unicode 到 ANSI 的转换。<br /><br /> 默认值：否|  
|**排序**|string|将 MQSeries 设置保持消息的顺序从接收或发送到 MQSeries 队列。<br /><br /> 该属性具有不同的用于发送和接收的值集。 有关值的信息，请参阅。 [如何配置 MQSeries 适配器接收位置和发送端口](../core/how-to-configure-mqseries-adapter-receive-locations-and-send-ports.md)。<br /><br /> 默认值：否|  
|**SegmentationAllowed**|string|将 MQSeries 组装已分段的消息，或获取消息原样设置。 该属性具有不同的用于发送和接收的值集。<br /><br /> 在接收时，使用**No Action**从 MQSeries 队列读取消息，但不启用分段; 使用**完整消息**可使 MQSeries 传递到前会组装已分段的消息适配器。<br /><br /> 默认值：执行任何操作<br /><br /> 在发送时，选择**是**可使 MQSeries 将已分段的消息放在队列中。<br /><br /> 默认值：否|  
|**SSOAffiliateApplication**|string|设置单一登录 (SSO) 关联应用程序。 使用用户 ID 和密码的 SSO **MQMD_UserIdentifier**，并**MQIIH_Authenticator** (或**MQCIH_Authenticator**) 属性分别。<br /><br /> 仅当发送消息时，才使用。<br /><br /> 默认值：空白|  
|**CompleteMessage**|string|指定是否检索"完整消息"时检索已分段的消息从队列。<br /><br /> 将此设置为**是**检索"完整消息"已分段的消息在队列中的。<br /><br /> 默认值：否|  
|**DynamicReceive**|string|指定是否要从队列动态接收消息。<br /><br /> 将此设置为**是**时动态地从队列接收消息。 与要求响应发送端口结合使用此功能。<br /><br /> 如果指定匹配选项 （MessageID、 CorrelationID 或 GroupID），则将检索与匹配条件关联的消息。|  
|**TransactionSupported**|string|此适配器开始 BizTalk Server 和 MQSeries 服务器之间的 Microsoft 分布式事务处理协调器 (DTC) 事务。 如果设置为**否**，则无法保证消息传递。<br /><br /> 默认值：是|  
|**WaitInterval**|string|指定以秒为单位，MQ 系统等待适当消息到达的大致时间。 如果没有适当的消息已在此时间内到达，则调用失败。 **注意：** 这只能在业务流程内设置。 <br /><br /> 默认值：3|  
  
## <a name="see-also"></a>请参阅  
 [MQSeries 适配器属性](../core/mqseries-adapter-properties.md)   
 [属性的数据类型转换](../core/data-type-conversion-of-properties.md)   
 [MQSeries 上下文属性](../core/mqseries-context-properties.md)