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
# <a name="configure-dispatcher-initiated-or-adapter-initiated-transactions-with-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="b0e94-102">使用 WCF LOB 适配器 SDK 配置已启动调度程序或适配器的事务</span><span class="sxs-lookup"><span data-stu-id="b0e94-102">Configure dispatcher-initiated or adapter-initiated transactions with the WCF LOB Adapter SDK</span></span>
## <a name="inbound-transactions"></a><span data-ttu-id="b0e94-103">入站的事务</span><span class="sxs-lookup"><span data-stu-id="b0e94-103">Inbound Transactions</span></span>  
 <span data-ttu-id="b0e94-104">有两种方法的实现具有入站操作的事务： 已启动调度程序或适配器的。</span><span class="sxs-lookup"><span data-stu-id="b0e94-104">There are two methods of implementing transactions with inbound operations: dispatcher-initiated or adapter-initiated.</span></span> <span data-ttu-id="b0e94-105">适配器的要求规定应使用哪种方法。</span><span class="sxs-lookup"><span data-stu-id="b0e94-105">The requirements of the adapter dictate which method should be used.</span></span> <span data-ttu-id="b0e94-106">值`SupportsTransactedInbound`属性指示哪种类型的事务将实现您的适配器。</span><span class="sxs-lookup"><span data-stu-id="b0e94-106">The value of the `SupportsTransactedInbound` property indicates which type of transaction your adapter will implement.</span></span>  
  
 <span data-ttu-id="b0e94-107">下表比较了已启动调度程序与适配器启动事务。</span><span class="sxs-lookup"><span data-stu-id="b0e94-107">The following table compares dispatcher-initiated with adapter-initiated transactions.</span></span>  
  
|<span data-ttu-id="b0e94-108">SupportsTransactedInbound</span><span class="sxs-lookup"><span data-stu-id="b0e94-108">SupportsTransactedInbound</span></span>|<span data-ttu-id="b0e94-109">事务行为</span><span class="sxs-lookup"><span data-stu-id="b0e94-109">Transactional Behavior</span></span>|  
|-------------------------------|----------------------------|  
|<span data-ttu-id="b0e94-110">True （已启动调度程序）</span><span class="sxs-lookup"><span data-stu-id="b0e94-110">True (dispatcher-initiated)</span></span>|<span data-ttu-id="b0e94-111">-TryReceive 始终将事务的上下文中调用。</span><span class="sxs-lookup"><span data-stu-id="b0e94-111">-   TryReceive will always be called within the context of a transaction.</span></span><br /><span data-ttu-id="b0e94-112">的消息返回到服务实现后，将提交事务。</span><span class="sxs-lookup"><span data-stu-id="b0e94-112">-   The transaction will be committed after the message is returned to the service implementation.</span></span><br /><span data-ttu-id="b0e94-113">的将创建一个新事务的每个 IInputChannel.Receive 调用。</span><span class="sxs-lookup"><span data-stu-id="b0e94-113">-   A new transaction will be created for each IInputChannel.Receive call.</span></span> <span data-ttu-id="b0e94-114">事务跨越多个接收依赖于服务主机并不是适配器开发人员。</span><span class="sxs-lookup"><span data-stu-id="b0e94-114">Spanning a transaction across multiple receives is dependent on the service host and not the adapter developer.</span></span> <span data-ttu-id="b0e94-115">**注意：** 如果主机未在使用 WCF 调度程序 （服务主机），而使用通道级编程，应使用主机**TransactedReceiveEnabled**属性的 WCF 绑定，并且应该对所有调用在事务内 IInputChannel.Receive。</span><span class="sxs-lookup"><span data-stu-id="b0e94-115">**Note:**  If the host is not using the WCF dispatcher (service host) and is instead using channel level programming, the host should honor the **TransactedReceiveEnabled** property of the WCF binding, and should make all calls to IInputChannel.Receive within a transaction.</span></span> <span data-ttu-id="b0e94-116">**注意：** 如果适配器使用调度程序启动事务，并且与 Biztalk Server 一起使用，则设置`SupportedInboundChannels`属性设置为`SupportedInboundChannels.IInputChannel`以指示适配器仅支持单向通道。</span><span class="sxs-lookup"><span data-stu-id="b0e94-116">**Note:**  If the adapter uses dispatcher-initiated transactions, and is used with Biztalk Server, set the `SupportedInboundChannels` property to `SupportedInboundChannels.IInputChannel` to indicate that the adapter only supports one-way channels.</span></span> <span data-ttu-id="b0e94-117">如果未设置，则 BizTalk Server 将尝试使用双向通道。</span><span class="sxs-lookup"><span data-stu-id="b0e94-117">If this is not set, BizTalk Server will attempt to use two-way channels.</span></span>|  
|<span data-ttu-id="b0e94-118">False （适配器发起）</span><span class="sxs-lookup"><span data-stu-id="b0e94-118">False (adapter-initiated)</span></span>|<span data-ttu-id="b0e94-119">-适配器开发人员必须实现适配器内的事务逻辑。</span><span class="sxs-lookup"><span data-stu-id="b0e94-119">-   The adapter developer must implement transaction logic within the adapter.</span></span><br /><span data-ttu-id="b0e94-120">-适配器启动事务可以仅适用于双向消息传送 （答复通道） 模型。</span><span class="sxs-lookup"><span data-stu-id="b0e94-120">-   Adapter-initiated transactions can only work with a two-way messaging (Reply Channel) model.</span></span><br /><span data-ttu-id="b0e94-121">-一个事务可以跨多条消息，因为每个消息调度程序创建依赖的克隆。</span><span class="sxs-lookup"><span data-stu-id="b0e94-121">-   One transaction can span multiple messages, since dependent clones will be created for each message by the dispatcher.</span></span>|  
  
### <a name="dispatcher-initiated-transactions"></a><span data-ttu-id="b0e94-122">调度程序启动事务</span><span class="sxs-lookup"><span data-stu-id="b0e94-122">Dispatcher-initiated Transactions</span></span>  
 <span data-ttu-id="b0e94-123">当 SupportsTransactedInbound 设置为 **，则返回 true**，WCF 调度程序然后将自动创建事务时调用**TryReceive**方法的适配器，并将提交事务后的消息返回到服务实现。</span><span class="sxs-lookup"><span data-stu-id="b0e94-123">When SupportsTransactedInbound is set to **true**, the WCF dispatcher will then automatically create a transaction when calling the **TryReceive** method of the adapter, and will commit the transaction after the message is returned to the service implementation.</span></span> <span data-ttu-id="b0e94-124">这不需要任何特定的事务性代码实现中设置之外的适配器`SupportsTransactedInbound`属性设置为**true**。</span><span class="sxs-lookup"><span data-stu-id="b0e94-124">This does not require any specific transactional code implementation within the adapter other than setting the `SupportsTransactedInbound` property to **true**.</span></span> <span data-ttu-id="b0e94-125">但是，这取决于在使用 WCF 调度程序的服务主机内承载的适配器，且不会发生，如果使用通道级编程。</span><span class="sxs-lookup"><span data-stu-id="b0e94-125">However, this is dependent on the adapter being hosted within a service host that uses the WCF dispatcher, and will not occur if you are using channel level programming.</span></span> <span data-ttu-id="b0e94-126">在使用通道级编程，应使用主机`TransactedReceiveEnabled`使所有接收到调用的事务中的 WCF 绑定的属性。</span><span class="sxs-lookup"><span data-stu-id="b0e94-126">When using channel level programming, the host should honor the `TransactedReceiveEnabled` property of the WCF binding and make all calls to Receive within a transaction.</span></span>  
  
 <span data-ttu-id="b0e94-127">以下代码演示了客户端创建事务，并调用适配器使用通道级编程。</span><span class="sxs-lookup"><span data-stu-id="b0e94-127">The following demonstrates a client creating a transaction, and then calling the adapter using channel level programming.</span></span>  
  
```csharp  
Message message;  
//Use a new TransactionScope  
using (System.Transactions.TransactionScope tx = new System.Transactions.TransactionScope())  
{  
    message = channel.Receive(TimeSpan.FromMinutes(2));  
    tx.Complete();  
}  
```  
  
### <a name="adapter-initiated-transactions"></a><span data-ttu-id="b0e94-128">适配器启动事务</span><span class="sxs-lookup"><span data-stu-id="b0e94-128">Adapter-initiated Transactions</span></span>  
 <span data-ttu-id="b0e94-129">当`SupportsTransactedInbound`属性设置为**false**，必须通过创建一个新的事务适配器代码中实现事务支持。</span><span class="sxs-lookup"><span data-stu-id="b0e94-129">When hte `SupportsTransactedInbound` property is set to **false**, transaction support must be implemented within the adapter code by creating a new transaction.</span></span> <span data-ttu-id="b0e94-130">返回从一条消息之前**TryReceive**，事务必须通过调用附加到消息**设置**方法**TransactionMessageProperty**类。</span><span class="sxs-lookup"><span data-stu-id="b0e94-130">Before returning a message from **TryReceive**, the transaction must be attached to the message by calling the **Set** method of the **TransactionMessageProperty** class.</span></span> <span data-ttu-id="b0e94-131">此实现需要适配器代码中的显式事务支持，并提供更好地控制适配器的事务行为。</span><span class="sxs-lookup"><span data-stu-id="b0e94-131">This implementation requires explicit transaction support in the adapter code, and provides greater control over the transactional behavior of the adapter.</span></span>  
  
 <span data-ttu-id="b0e94-132">下面演示了如何创建依赖的事务，并将此附加到消息返回到客户端之前。</span><span class="sxs-lookup"><span data-stu-id="b0e94-132">The following demonstrates creating a dependent transaction, and attaching this to the message before it is returned to the client.</span></span>  
  
```csharp  
  
Transaction transaction = inboundConnection.CurrentTransaction; //Existing transaction  
DependentTransaction dt = transaction.DependentClone(DependentCloneOption.BlockCommitUntilComplete);  
TransactionMessageProperty.Set(dt, message);  
inboundReply.DependentTransaction = dt; //this will later be closed during Reply processing  
```  
  
## <a name="see-also"></a><span data-ttu-id="b0e94-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="b0e94-133">See Also</span></span>  
 [<span data-ttu-id="b0e94-134">开发活动</span><span class="sxs-lookup"><span data-stu-id="b0e94-134">Development Activities</span></span>](../../esb-toolkit/development-activities.md)