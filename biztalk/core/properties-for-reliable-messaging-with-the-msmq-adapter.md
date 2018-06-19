---
title: 使用 MSMQ 适配器可靠消息传递的属性 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, properties
- queues, MSMQ adapters
- MSMQ adapters, dead letters
- queues, failures [MSMQ adapters]
- MSMQ adapters, impersonation
- MSMQ adapters, remote queues
- queues
- reliability, MSMQ adapters
- impersonation, MSMQ adapters
- MSMQ adapters, queue failures
- clustering, MSMQ adapters
- queues, remote
- MSMQ adapters, reliability
- MSMQ adapters, clustering
ms.assetid: 34bfe028-b2aa-4816-a437-3679d19dffb2
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49aebf12c86ae72d5dcb224d078c62afefcb8f46
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268845"
---
# <a name="properties-for-reliable-messaging-with-the-msmq-adapter"></a>使用 MSMQ 适配器可靠消息传递的属性
通过配置 MSMQ 适配器，可以提高使用 MSMQ 适配器发送和接收消息的可靠性。 本主题将介绍使用多个配置属性进行可靠的消息传送。  
  
## <a name="running-msmq-adapter-handlers-within-a-clustered-biztalk-host"></a>在群集的 BizTalk 主机内运行 MSMQ 适配器处理程序  
 确保高可用性的一个方法是：在不同的 BizTalk Server 上的多个主机实例中同时运行适配器处理程序。 对于 MSMQ 适配器处理程序，不建议使用此方法，因为 MSMQ 不支持远程事务性读取，并且 MSMQ 发送处理程序对于 MSMQ 服务的本地运行实例具有依存关系。 为了提高 MSMQ 发送和接收处理程序的可用性，建议您在 BizTalk 主机的群集实例中运行 MSMQ 适配器处理程序。 有关详细信息，请参阅[在群集主机内运行适配器处理程序的注意事项](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)。  
  
## <a name="queue-failure-and-the-dead-letter-queue"></a>队列错误和死信队列  
 消息成功发送后，如果禁用或删除接收队列，则后续消息不会出错。 这种情况会导致消息丢失。  
  
 设置**使用死信队列**配置属性设置为**True**防止丢失消息。 当该属性是`True`（默认值）、 队列没有接收的消息就可进入死信队列。  
  
## <a name="impersonation-and-remote-queues"></a>模拟和远程队列  
 你还必须设置**使用死信队列**配置属性设置为**True**当你使用远程队列。 如果 MSMQ 适配器在没有远程队列使用权限的情况下模拟用户，则消息会丢失。  
  
 当该属性是**True**和模拟的用户没有使用远程队列的权限，该消息在本地或远程计算机上将转到死信队列。 在事务性发送中，消息将进入本地计算机的死信队列。 在非事务性发送中，消息将进入远程计算机的死信队列。  
  
## <a name="recoverable-and-use-journal-queue-properties"></a>“可恢复”和“使用日志队列”属性  
 这两个**可恢复**和**使用日记队列**属性保存发送消息的副本。 有关这些属性的详细信息，请参阅[如何配置 MSMQ 接收位置](../core/how-to-configure-an-msmq-receive-location.md)和[如何配置 MSMQ 发送端口](../core/how-to-configure-an-msmq-send-port.md)。  
  
## <a name="see-also"></a>另请参阅  
 [使用 MSMQ 适配器可靠消息传递](../core/reliable-messaging-with-the-msmq-adapter.md)   
 [运行在群集主机内的适配器处理程序的注意事项](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)