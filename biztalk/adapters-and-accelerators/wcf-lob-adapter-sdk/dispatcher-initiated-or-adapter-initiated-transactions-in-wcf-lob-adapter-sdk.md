---
title: "使用 WCF LOB 适配器 SDK 配置调度程序启动或适配器启动事务 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 85b9ef8d-3922-4838-a41a-32db5e005dc0
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa8105b4b6f8eb77d68471faf9b702419f6a1f90
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configure-dispatcher-initiated-or-adapter-initiated-transactions-with-the-wcf-lob-adapter-sdk"></a>使用 WCF LOB 适配器 SDK 配置调度程序启动或适配器启动事务
## <a name="inbound-transactions"></a>入站的事务  
 有两种方法的实现与入站操作的事务： 调度程序启动，或者适配器启动。 适配器要求规定应使用哪种方法。 值`SupportsTransactedInbound`属性指示哪种类型的事务将实现你的适配器。  
  
 下表比较了调度程序启动与适配器启动事务。  
  
|SupportsTransactedInbound|事务行为|  
|-------------------------------|----------------------------|  
|True （调度程序启动）|-TryReceive 始终将在事务的上下文内调用。<br />的该消息返回给服务实现后，将提交事务。<br />的将创建一个新事务的每个 IInputChannel.Receive 调用。 事务跨越多个接收依赖于服务主机，并不是适配器开发人员。 **注意：**如果主机未在使用 WCF 调度程序 （服务主机），而使用通道级编程，应遵循主机**TransactedReceiveEnabled**的 WCF 绑定的属性，应相应进行所有对 IInputChannel.Receive 在事务中的调用。 **注意：**适配器使用调度程序启动事务，并且与 Biztalk Server 一起使用，如果设置`SupportedInboundChannels`属性`SupportedInboundChannels.IInputChannel`以指示的适配器仅支持单向通道。 如果未设置，BizTalk Server 将尝试使用双向通道。|  
|False （适配器启动）|-适配器开发人员必须实现该适配器中的事务逻辑。<br />-双向的消息传送 （答复通道） 模型只能处理适配器启动事务。<br />-一个事务可以跨多个消息，因为依赖克隆将调度程序创建为每个消息。|  
  
### <a name="dispatcher-initiated-transactions"></a>调度程序启动事务  
 当 SupportsTransactedInbound 设置为**true**，WCF 调度程序然后将自动创建事务时调用**TryReceive**的适配器的方法，将提交事务后该消息返回给服务实现中。 这不需要任何特定事务代码实现中设置以外的适配器`SupportsTransactedInbound`属性**true**。 但是，这是依赖于在使用 WCF 调度程序服务主机内承载的适配器，如果你正在使用通道级编程，将不会发生。 在使用通道级编程，应遵循主机`TransactedReceiveEnabled`的 WCF 绑定，使所有接收到调用在事务中的属性。  
  
 下面演示了客户端创建事务，以及然后调用适配器使用通道级编程。  
  
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
 当`SupportsTransactedInbound`属性设置为**false**，必须通过创建一个新的事务适配器代码中实现的事务支持。 在返回的消息之前**TryReceive**，事务必须通过调用附加到消息**设置**方法**TransactionMessageProperty**类。 此实现需要在适配器代码中，显式事务支持，并提供更好地控制适配器的事务行为。  
  
 下面演示了如何创建依赖的事务，并将此附加到消息之前它将返回到客户端。  
  
```csharp  
  
Transaction transaction = inboundConnection.CurrentTransaction; //Existing transaction  
DependentTransaction dt = transaction.DependentClone(DependentCloneOption.BlockCommitUntilComplete);  
TransactionMessageProperty.Set(dt, message);  
inboundReply.DependentTransaction = dt; //this will later be closed during Reply processing  
```  
  
## <a name="see-also"></a>另请参阅  
 [开发活动](../../esb-toolkit/development-activities.md)