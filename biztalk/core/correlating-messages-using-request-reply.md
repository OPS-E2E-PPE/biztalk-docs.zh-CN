---
title: "使消息使用请求-答复关联 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, MQSeries adapters
- messages, correlating
- MQSeries adapters, correlating messages
ms.assetid: 4615b586-663b-41d8-949c-fefb6143c590
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f2f13d8dea9192e982f597311ca3ea13fa213ed0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="correlating-messages-using-request-reply"></a>使消息使用请求-答复关联
可通过两种方法使 IBM WebSphere MQ 的 BizTalk 业务流程中的消息相关，IBM WebSphere MQ 是 Windows 平台请求-答复方案的服务器组件。 第一种是通过设置这两个 MessageID 提供的相关标识符 (**MQMD_MSGID**) 和 CorrelationID (**MQMD_CorrelId**) 为相同的值。 第二个是使用**BizTalk_CorrelationId**上下文属性。  
  
## <a name="setting-mqmdmsgid-and-mqmdcorrelid-to-the-same-value"></a>将 MQMD_MsgId 和 MQMD_CorrelId 设置为相同值  
 当发送消息到 IBM WebSphere MQ 队列管理器，您可以设置的消息标识符 (**MQMD_MSGID**) 的相关标识符和 (**MQMD_CorrelId**) 为传出消息中相同的值. IBM WebSphere MQ 队列管理器会将消息 ID 复制到答复消息的相关 ID。 下图显示进程。  
  
 ![简单关联](../core/media/bts-dev-mqsimplecorrelation.gif "BTS_Dev_MQSimpleCorrelation")  
  
 可以将其初始化为传出消息并遵循相关设置使用的值的传入消息的相关集**MQMD_CorrelId**。  
  
## <a name="using-the-mqseriesbiztalkcorrelationid-context-property"></a>使用 MQSeries.BizTalk_CorrelationId 上下文属性  
 而不是设置为相同的值在传出消息的 MessageID 和 CorrelationID，你可以使用**BizTalk_CorrelationID**上下文属性与请求-响应发送 MQSeries 适配器的端口。 下图显示了这一过程：  
  
 ![使用请求作出 &#45;响应生成 CorrelationID](../core/media/bts-dev-mqgeneratedcorrelation.gif "BTS_Dev_MQGeneratedCorrelation")  
  
 若要将 IBM WebSphere MQ 服务器提供的标识符用于 BizTalk 业务流程中的相关，则 BizTalk Server 必须先获得该标识符。 应用程序可通过要求-响应请求来执行此操作。 通过使用 MQSeries 适配器，BizTalk Server 可向 IBM WebSphere MQ 服务器发送要求-响应请求。 反过来，接收到响应时使用的消息标识符 (**MQMD_MSGId**) 的相关标识符和 (**MQMD_CorrelId**)。  
  
 请求-响应发送端口中的传出消息，该适配器将复制**MQMD_MSGID**由服务器生成的 IBM WebSphere MQ 到**MQSeries.BizTalk_CorrelationId**上下文属性。  
  
 如果将接收消息，该适配器将复制**MQMD_CorrelId**到**MQSeries.BizTalk_CorrelationId**。 在这种情况下，使用相关集，可以将其初始化为传出消息并遵循相关设置传入的消息使用的相关集**MQSeries.BizTalk_CorrelationId**。  
  
## <a name="see-also"></a>另请参阅  
 [MQSCorrelationSetOrchestrationWithSolicitResponse （BizTalk Server 示例）](../core/mqscorrelationsetorchestrationwithsolicitresponse-biztalk-server-sample.md)