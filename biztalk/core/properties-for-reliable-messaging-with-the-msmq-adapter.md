---
title: 使用 MSMQ 适配器可靠消息传送属性 |Microsoft Docs
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
ms.openlocfilehash: 54a33fdd3ced15230d2b0c1417d1f5398678f183
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398495"
---
# <a name="properties-for-reliable-messaging-with-the-msmq-adapter"></a>可靠消息传送的 MSMQ 适配器属性
可以提高可靠性的发送和接收消息使用 MSMQ 适配器配置 MSMQ 适配器的方式。 本主题讨论如何使用可靠消息传送的多个配置属性。  
  
## <a name="running-msmq-adapter-handlers-within-a-clustered-biztalk-host"></a>在群集 BizTalk 主机内运行 MSMQ 适配器处理程序  
 高可用性的一种方法是运行适配器处理程序中多个主机实例在不同 BizTalk 服务器上同时。 不建议使用此方法对于 MSMQ 适配器处理程序，因为 MSMQ 不支持远程事务性的读取，MSMQ 发送处理程序具有依存的 MSMQ 服务的本地运行实例。 若要提供高可用性的 MSMQ 发送和接收处理程序建议在群集 BizTalk 主机的实例中运行 MSMQ 适配器处理程序。 有关详细信息，请参阅[群集主机内运行适配器处理程序的注意事项](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)。  
  
## <a name="queue-failure-and-the-dead-letter-queue"></a>队列错误和死信队列  
 已成功发送一条消息后, 没有错误的后续消息如果禁用或删除接收队列。 这种情况下可能会导致消息丢失。  
  
 设置**使用死信队列**配置属性设置为**True**防止丢失消息。 当该属性是`True`（默认值），进入死信队列的队列不会接收的消息。  
  
## <a name="impersonation-and-remote-queues"></a>模拟和远程队列  
 您还必须设置**使用死信队列**配置属性设置为**True**当你使用远程队列。 如果 MSMQ 适配器模拟而无需使用远程队列的权限的用户，该消息可能会丢失。  
  
 当该属性是 **，则返回 True**和模拟的用户不具有使用远程队列的权限，消息将进入死信队列在本地或远程计算机上。 在事务性发送中，消息将发送到死信队列在本地计算机上。 在非事务性发送中，消息将发送到死信队列在远程计算机上。  
  
## <a name="recoverable-and-use-journal-queue-properties"></a>可恢复，并使用日志队列属性  
 这两个**可恢复**并**使用日志队列**属性都可保存发送消息的副本。 有关这些属性的详细信息，请参阅[如何配置 MSMQ 接收位置](../core/how-to-configure-an-msmq-receive-location.md)并[如何配置 MSMQ 发送端口](../core/how-to-configure-an-msmq-send-port.md)。  
  
## <a name="see-also"></a>请参阅  
 [使用 MSMQ 适配器可靠消息传送](../core/reliable-messaging-with-the-msmq-adapter.md)   
 [在群集主机内运行适配器处理程序的注意事项](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)