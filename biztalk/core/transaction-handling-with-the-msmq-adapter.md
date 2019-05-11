---
title: 使用 MSMQ 适配器处理的事务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, transaction handling
- transactions, MSMQ adapters
ms.assetid: 2e5dd0da-3852-48bf-9372-b019ecab23be
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4fadd7f8d4edb388dd16c707bb0313191f9857d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65313275"
---
# <a name="transaction-handling-with-the-msmq-adapter"></a>使用 MSMQ 适配器处理事务
本部分介绍在接收和发送的事务处理方式。  
  
> [!NOTE]
>  MSMQ 适配器的事务从扩展 BizTalk MessageBox 数据库到本地消息队列队列即使使用远程队列。  
  
 您可以使用事务，在这两个发送和接收使用 MSMQ 适配器。 在事务性发送适配器将累积消息，直到它具有完整的一批。 然后，适配器作为单个事务提交到本地消息队列服务的批处理。 如果提交失败，适配器将尝试重新提交批处理。 如果重新提交失败，适配器将转至次要传输。  
  
> [!NOTE]
>  该适配器支持 Message Queuing 4.0 或更高版本的远程队列进行事务性读取。 在此方案中 BizTalk Server 和远程消息队列服务器必须运行消息队列 4.0 或更高版本。  
  
 在事务性接收，则适配器将挂起失败的消息，以便它不会丢失任何一个消息。 在事务性接收适配器将消息添加到一批完成批处理之前。 然后，它将提交批处理：  
  
- 如果没有任何问题，并且服务器接收消息，则适配器提交事务。  
  
- 如果出现问题，适配器会创建新的批处理，当前事务的一部分。 然后，它将所有问题消息都移动到新的批。 然后重新提交第一批，并将新的批提交作为挂起的消息。 如果在此重新提交过程没有任何问题，则适配器提交事务。  
  
  如果在群集 BizTalk 主机实例中运行 MSMQ 适配器发送处理程序，应群集 MSMQ 服务中相同的群集组，以确保事务一致性。  
  
  如果在 DCOMCNFG 实用工具中禁用"网络 DTC 访问"，则 MSMQ 事务性远程接收操作将失败并费解的错误消息。  若要执行事务性远程接收使用 MSMQ 适配器，必须启用"网络 DTC 访问"。 可在找到更多信息[ http://go.microsoft.com/fwlink/?LinkId=124623 ](http://go.microsoft.com/fwlink/?LinkId=124623)。  
  
  如果您正在运行 MSMQ 适配器接收处理程序在群集 BizTalk 主机实例中，应群集 MSMQ 服务中相同的群集组，以支持本地事务性的读取，因为 MSMQ 不支持远程事务性读取。 有关在群集 BizTalk 主机的实例中运行 MSMQ 适配器处理程序的详细信息，请参阅[有关在群集主机内运行适配器处理程序的注意事项](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)。  
  
## <a name="see-also"></a>请参阅  
 [使用 MSMQ 适配器实现可靠消息传送](../core/reliable-messaging-with-the-msmq-adapter.md)