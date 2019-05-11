---
title: 将使用请求-答复消息相关联 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, MQSeries adapters
- messages, correlating
- MQSeries adapters, correlating messages
ms.assetid: 4615b586-663b-41d8-949c-fefb6143c590
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91790a879816efa7b2bfa7a5a16f4ea1dfbb13a2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390207"
---
# <a name="correlating-messages-using-request-reply"></a>使用请求-答复相关消息
有两种方法来将 IBM WebSphere MQ，Windows 平台请求-答复方案的服务器组件的 BizTalk 业务流程中的消息关联。 第一种是通过设置将消息 Id 提供相关标识符 (**MQMD_MSGID**) 和相关 Id (**MQMD_CorrelId**) 到相同的值。 第二个是使用**BizTalk_CorrelationId**上下文属性。  
  
## <a name="setting-mqmdmsgid-and-mqmdcorrelid-to-the-same-value"></a>将 MQMD_MsgId 和 MQMD_CorrelId 设置为相同的值  
 将消息发送到 IBM WebSphere MQ 队列管理器，您可以设置消息标识符 (**MQMD_MSGID**) 和相关标识符 (**MQMD_CorrelId**) 为传出消息中相同的值. IBM WebSphere MQ 队列管理器将消息 Id 复制到答复消息的 CorrelationID。 下图显示了该过程。  
  
 ![简单关联](../core/media/bts-dev-mqsimplecorrelation.gif "BTS_Dev_MQSimpleCorrelation")  
  
 您可以初始化传出消息和沿用这些相关集使用的值的传入消息的相关集**MQMD_CorrelId**。  
  
## <a name="using-the-mqseriesbiztalkcorrelationid-context-property"></a>使用 MQSeries.BizTalk_CorrelationId 上下文属性  
 而不是为传出消息中相同的值设置 MessageID 和 CorrelationID，可以使用**BizTalk_CorrelationID**上下文属性与要求响应发送端口的 MQSeries 适配器。 下图显示了此过程。  
  
 ![使用要求&#45;响应生成 CorrelationID](../core/media/bts-dev-mqgeneratedcorrelation.gif "BTS_Dev_MQGeneratedCorrelation")  
  
 若要使用在 BizTalk 业务流程中的关联性提供的 IBM WebSphere MQ 服务器标识符，BizTalk Server 必须先获得该标识符。 你的应用程序这都是通过要求-响应请求。 通过使用 MQSeries 适配器，BizTalk Server 将要求-响应请求发送到 IBM WebSphere MQ Server。 反过来，接收到响应时使用的消息标识符 (**MQMD_MSGId**) 和相关标识符 (**MQMD_CorrelId**)。  
  
 对于要求-响应发送端口中的传出消息，适配器将复制**MQMD_MSGID**生成的 IBM WebSphere MQ Server 到**MQSeries.BizTalk_CorrelationId**上下文属性。  
  
 适配器接收消息时，将复制**MQMD_CorrelId**到**MQSeries.BizTalk_CorrelationId**。 在这种情况下，使用相关集，您可以初始化传出消息和沿用这些相关集传入的消息使用的相关集**MQSeries.BizTalk_CorrelationId**。  
  
## <a name="see-also"></a>请参阅  
 [MQSCorrelationSetOrchestrationWithSolicitResponse（BizTalk Server 示例）](../core/mqscorrelationsetorchestrationwithsolicitresponse-biztalk-server-sample.md)