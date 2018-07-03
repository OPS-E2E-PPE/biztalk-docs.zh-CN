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
ms.openlocfilehash: e55494175029fd8edda1a457298af1d829be3087
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980918"
---
# <a name="transaction-handling-with-the-msmq-adapter"></a>使用 MSMQ 适配器处理事务
本部分将介绍事务在接收和发送时的工作方式。  
  
> [!NOTE]
>  对于 MSMQ 适配器，即使使用远程队列，事务也会从 BizTalk MessageBox 数据库扩展到本地消息队列。  
  
 使用 MSMQ 适配器，可以对发送和接收使用事务性功能。 在事务性发送中，适配器将累积消息，直到具有完整的一批消息。 然后，适配器将该批消息作为单个事务提交给本地消息队列服务。 如果提交失败，则适配器将尝试重新提交该批消息。 如果重新提交失败，则适配器将转至次要传输。  
  
> [!NOTE]
>  适配器仅支持使用 Message Queuing 4.0 或更高版本对远程队列进行事务性读取。 在此方案中 BizTalk Server 和远程消息队列服务器必须运行消息队列 4.0 或更高版本。  
  
 在事务性接收中，适配器将挂起失败消息，以便不丢失任何一个消息。 在事务性接收过程中，适配器会将消息添加到一批中，直至该批消息完整， 然后提交该批消息：  
  
- 如果没有任何问题，并且服务器接收到消息，则适配器提交事务。  
  
- 如果出现问题，适配器将在当前事务中创建一个新批。 随后将所有问题消息移至该新批中。 然后，适配器重新提交第一批消息，并将该新的一批消息作为挂起的消息进行提交。 如果在此重新提交过程中没有任何问题，则适配器提交事务。  
  
  如果在群集的 BizTalk 主机实例中运行 MSMQ 适配器发送处理程序，则应在同一个群集组中对 MSMQ 服务进行群集以确保事务一致性。  
  
  如果在 DCOMCNFG 实用工具中禁用了“网络 DTC 访问”，则 MSMQ 事务性远程接收操作将失败，并带有隐含的错误消息。  若要使用 MSMQ 适配器来执行事务性远程接收，必须启用“网络 DTC 访问”。 可在找到更多信息[ http://go.microsoft.com/fwlink/?LinkId=124623 ](http://go.microsoft.com/fwlink/?LinkId=124623)。  
  
  如果在群集的 BizTalk 主机实例中运行 MSMQ 适配器接收处理程序，则应在同一个群集组中对 MSMQ 服务进行群集以支持本地事务性读取，因为 MSMQ 不支持远程事务性读取。 有关在群集 BizTalk 主机的实例中运行 MSMQ 适配器处理程序的详细信息，请参阅[有关在群集主机内运行适配器处理程序的注意事项](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)。  
  
## <a name="see-also"></a>请参阅  
 [使用 MSMQ 适配器实现可靠消息传送](../core/reliable-messaging-with-the-msmq-adapter.md)