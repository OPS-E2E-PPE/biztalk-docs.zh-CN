---
title: 使用 WCF LOB 适配器 SDK 配置已启动调度程序或适配器的事务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 85b9ef8d-3922-4838-a41a-32db5e005dc0
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98ad767d0da4816e1d0c0658db898ebec282ffa9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363613"
---
# <a name="configure-dispatcher-initiated-or-adapter-initiated-transactions-with-the-wcf-lob-adapter-sdk"></a>使用 WCF LOB 适配器 SDK 配置已启动调度程序或适配器的事务
## <a name="inbound-transactions"></a>入站的事务  
 有两种方法的实现具有入站操作的事务： 已启动调度程序或适配器的。 适配器的要求规定应使用哪种方法。 值`SupportsTransactedInbound`属性指示哪种类型的事务将实现您的适配器。  
  
 下表比较了已启动调度程序与适配器启动事务。  
  
|SupportsTransactedInbound|事务行为|  
|-------------------------------|----------------------------|  
|True （已启动调度程序）|-TryReceive 始终将事务的上下文中调用。<br />的消息返回到服务实现后，将提交事务。<br />的将创建一个新事务的每个 IInputChannel.Receive 调用。 事务跨越多个接收依赖于服务主机并不是适配器开发人员。 **注意：** 如果主机未在使用 WCF 调度程序 （服务主机），而使用通道级编程，应使用主机**TransactedReceiveEnabled**属性的 WCF 绑定，并且应该对所有调用在事务内 IInputChannel.Receive。 **注意：** 如果适配器使用调度程序启动事务，并且与 Biztalk Server 一起使用，则设置`SupportedInboundChannels`属性设置为`SupportedInboundChannels.IInputChannel`以指示适配器仅支持单向通道。 如果未设置，则 BizTalk Server 将尝试使用双向通道。|  
|False （适配器发起）|-适配器开发人员必须实现适配器内的事务逻辑。<br />-适配器启动事务可以仅适用于双向消息传送 （答复通道） 模型。<br />-一个事务可以跨多条消息，因为每个消息调度程序创建依赖的克隆。|  
  
### <a name="dispatcher-initiated-transactions"></a>调度程序启动事务  
 当 SupportsTransactedInbound 设置为 **，则返回 true**，WCF 调度程序然后将自动创建事务时调用**TryReceive**方法的适配器，并将提交事务后的消息返回到服务实现。 这不需要任何特定的事务性代码实现中设置之外的适配器`SupportsTransactedInbound`属性设置为**true**。 但是，这取决于在使用 WCF 调度程序的服务主机内承载的适配器，且不会发生，如果使用通道级编程。 在使用通道级编程，应使用主机`TransactedReceiveEnabled`使所有接收到调用的事务中的 WCF 绑定的属性。  
  
 以下代码演示了客户端创建事务，并调用适配器使用通道级编程。  
  
```csharp  
Message message;  
//Use a new TransactionScope  
using (System.Transactions.TransactionScope tx = new System.Transactions.TransactionScope())  
{  
    message = channel.Receive(TimeSpan.FromMinutes(2));  
    tx.Complete();  
}  
```  
  
### <a name="adapter-initiated-transactions"></a>适配器启动事务  
 当`SupportsTransactedInbound`属性设置为**false**，必须通过创建一个新的事务适配器代码中实现事务支持。 返回从一条消息之前**TryReceive**，事务必须通过调用附加到消息**设置**方法**TransactionMessageProperty**类。 此实现需要适配器代码中的显式事务支持，并提供更好地控制适配器的事务行为。  
  
 下面演示了如何创建依赖的事务，并将此附加到消息返回到客户端之前。  
  
```csharp  
  
Transaction transaction = inboundConnection.CurrentTransaction; //Existing transaction  
DependentTransaction dt = transaction.DependentClone(DependentCloneOption.BlockCommitUntilComplete);  
TransactionMessageProperty.Set(dt, message);  
inboundReply.DependentTransaction = dt; //this will later be closed during Reply processing  
```  
  
## <a name="see-also"></a>请参阅  
 [开发活动](../../esb-toolkit/development-activities.md)