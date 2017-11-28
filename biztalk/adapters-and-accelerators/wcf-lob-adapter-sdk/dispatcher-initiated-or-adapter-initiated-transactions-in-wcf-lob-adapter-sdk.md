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
# <a name="configure-dispatcher-initiated-or-adapter-initiated-transactions-with-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="07c56-102">使用 WCF LOB 适配器 SDK 配置调度程序启动或适配器启动事务</span><span class="sxs-lookup"><span data-stu-id="07c56-102">Configure dispatcher-initiated or adapter-initiated transactions with the WCF LOB Adapter SDK</span></span>
## <a name="inbound-transactions"></a><span data-ttu-id="07c56-103">入站的事务</span><span class="sxs-lookup"><span data-stu-id="07c56-103">Inbound Transactions</span></span>  
 <span data-ttu-id="07c56-104">有两种方法的实现与入站操作的事务： 调度程序启动，或者适配器启动。</span><span class="sxs-lookup"><span data-stu-id="07c56-104">There are two methods of implementing transactions with inbound operations: dispatcher-initiated or adapter-initiated.</span></span> <span data-ttu-id="07c56-105">适配器要求规定应使用哪种方法。</span><span class="sxs-lookup"><span data-stu-id="07c56-105">The requirements of the adapter dictate which method should be used.</span></span> <span data-ttu-id="07c56-106">值`SupportsTransactedInbound`属性指示哪种类型的事务将实现你的适配器。</span><span class="sxs-lookup"><span data-stu-id="07c56-106">The value of the `SupportsTransactedInbound` property indicates which type of transaction your adapter will implement.</span></span>  
  
 <span data-ttu-id="07c56-107">下表比较了调度程序启动与适配器启动事务。</span><span class="sxs-lookup"><span data-stu-id="07c56-107">The following table compares dispatcher-initiated with adapter-initiated transactions.</span></span>  
  
|<span data-ttu-id="07c56-108">SupportsTransactedInbound</span><span class="sxs-lookup"><span data-stu-id="07c56-108">SupportsTransactedInbound</span></span>|<span data-ttu-id="07c56-109">事务行为</span><span class="sxs-lookup"><span data-stu-id="07c56-109">Transactional Behavior</span></span>|  
|-------------------------------|----------------------------|  
|<span data-ttu-id="07c56-110">True （调度程序启动）</span><span class="sxs-lookup"><span data-stu-id="07c56-110">True (dispatcher-initiated)</span></span>|<span data-ttu-id="07c56-111">-TryReceive 始终将在事务的上下文内调用。</span><span class="sxs-lookup"><span data-stu-id="07c56-111">-   TryReceive will always be called within the context of a transaction.</span></span><br /><span data-ttu-id="07c56-112">的该消息返回给服务实现后，将提交事务。</span><span class="sxs-lookup"><span data-stu-id="07c56-112">-   The transaction will be committed after the message is returned to the service implementation.</span></span><br /><span data-ttu-id="07c56-113">的将创建一个新事务的每个 IInputChannel.Receive 调用。</span><span class="sxs-lookup"><span data-stu-id="07c56-113">-   A new transaction will be created for each IInputChannel.Receive call.</span></span> <span data-ttu-id="07c56-114">事务跨越多个接收依赖于服务主机，并不是适配器开发人员。</span><span class="sxs-lookup"><span data-stu-id="07c56-114">Spanning a transaction across multiple receives is dependent on the service host and not the adapter developer.</span></span> <span data-ttu-id="07c56-115">**注意：**如果主机未在使用 WCF 调度程序 （服务主机），而使用通道级编程，应遵循主机**TransactedReceiveEnabled**的 WCF 绑定的属性，应相应进行所有对 IInputChannel.Receive 在事务中的调用。</span><span class="sxs-lookup"><span data-stu-id="07c56-115">**Note:**  If the host is not using the WCF dispatcher (service host) and is instead using channel level programming, the host should honor the **TransactedReceiveEnabled** property of the WCF binding, and should make all calls to IInputChannel.Receive within a transaction.</span></span> <span data-ttu-id="07c56-116">**注意：**适配器使用调度程序启动事务，并且与 Biztalk Server 一起使用，如果设置`SupportedInboundChannels`属性`SupportedInboundChannels.IInputChannel`以指示的适配器仅支持单向通道。</span><span class="sxs-lookup"><span data-stu-id="07c56-116">**Note:**  If the adapter uses dispatcher-initiated transactions, and is used with Biztalk Server, set the `SupportedInboundChannels` property to `SupportedInboundChannels.IInputChannel` to indicate that the adapter only supports one-way channels.</span></span> <span data-ttu-id="07c56-117">如果未设置，BizTalk Server 将尝试使用双向通道。</span><span class="sxs-lookup"><span data-stu-id="07c56-117">If this is not set, BizTalk Server will attempt to use two-way channels.</span></span>|  
|<span data-ttu-id="07c56-118">False （适配器启动）</span><span class="sxs-lookup"><span data-stu-id="07c56-118">False (adapter-initiated)</span></span>|<span data-ttu-id="07c56-119">-适配器开发人员必须实现该适配器中的事务逻辑。</span><span class="sxs-lookup"><span data-stu-id="07c56-119">-   The adapter developer must implement transaction logic within the adapter.</span></span><br /><span data-ttu-id="07c56-120">-双向的消息传送 （答复通道） 模型只能处理适配器启动事务。</span><span class="sxs-lookup"><span data-stu-id="07c56-120">-   Adapter-initiated transactions can only work with a two-way messaging (Reply Channel) model.</span></span><br /><span data-ttu-id="07c56-121">-一个事务可以跨多个消息，因为依赖克隆将调度程序创建为每个消息。</span><span class="sxs-lookup"><span data-stu-id="07c56-121">-   One transaction can span multiple messages, since dependent clones will be created for each message by the dispatcher.</span></span>|  
  
### <a name="dispatcher-initiated-transactions"></a><span data-ttu-id="07c56-122">调度程序启动事务</span><span class="sxs-lookup"><span data-stu-id="07c56-122">Dispatcher-initiated Transactions</span></span>  
 <span data-ttu-id="07c56-123">当 SupportsTransactedInbound 设置为**true**，WCF 调度程序然后将自动创建事务时调用**TryReceive**的适配器的方法，将提交事务后该消息返回给服务实现中。</span><span class="sxs-lookup"><span data-stu-id="07c56-123">When SupportsTransactedInbound is set to **true**, the WCF dispatcher will then automatically create a transaction when calling the **TryReceive** method of the adapter, and will commit the transaction after the message is returned to the service implementation.</span></span> <span data-ttu-id="07c56-124">这不需要任何特定事务代码实现中设置以外的适配器`SupportsTransactedInbound`属性**true**。</span><span class="sxs-lookup"><span data-stu-id="07c56-124">This does not require any specific transactional code implementation within the adapter other than setting the `SupportsTransactedInbound` property to **true**.</span></span> <span data-ttu-id="07c56-125">但是，这是依赖于在使用 WCF 调度程序服务主机内承载的适配器，如果你正在使用通道级编程，将不会发生。</span><span class="sxs-lookup"><span data-stu-id="07c56-125">However, this is dependent on the adapter being hosted within a service host that uses the WCF dispatcher, and will not occur if you are using channel level programming.</span></span> <span data-ttu-id="07c56-126">在使用通道级编程，应遵循主机`TransactedReceiveEnabled`的 WCF 绑定，使所有接收到调用在事务中的属性。</span><span class="sxs-lookup"><span data-stu-id="07c56-126">When using channel level programming, the host should honor the `TransactedReceiveEnabled` property of the WCF binding and make all calls to Receive within a transaction.</span></span>  
  
 <span data-ttu-id="07c56-127">下面演示了客户端创建事务，以及然后调用适配器使用通道级编程。</span><span class="sxs-lookup"><span data-stu-id="07c56-127">The following demonstrates a client creating a transaction, and then calling the adapter using channel level programming.</span></span>  
  
```csharp  
Message message;  
//Use a new TransactionScope  
using (System.Transactions.TransactionScope tx = new System.Transactions.TransactionScope())  
{  
    message = channel.Receive(TimeSpan.FromMinutes(2));  
    tx.Complete();  
}  
```  
  
### <a name="adapter-initiated-transactions"></a><span data-ttu-id="07c56-128">适配器启动事务</span><span class="sxs-lookup"><span data-stu-id="07c56-128">Adapter-initiated Transactions</span></span>  
 <span data-ttu-id="07c56-129">当`SupportsTransactedInbound`属性设置为**false**，必须通过创建一个新的事务适配器代码中实现的事务支持。</span><span class="sxs-lookup"><span data-stu-id="07c56-129">When hte `SupportsTransactedInbound` property is set to **false**, transaction support must be implemented within the adapter code by creating a new transaction.</span></span> <span data-ttu-id="07c56-130">在返回的消息之前**TryReceive**，事务必须通过调用附加到消息**设置**方法**TransactionMessageProperty**类。</span><span class="sxs-lookup"><span data-stu-id="07c56-130">Before returning a message from **TryReceive**, the transaction must be attached to the message by calling the **Set** method of the **TransactionMessageProperty** class.</span></span> <span data-ttu-id="07c56-131">此实现需要在适配器代码中，显式事务支持，并提供更好地控制适配器的事务行为。</span><span class="sxs-lookup"><span data-stu-id="07c56-131">This implementation requires explicit transaction support in the adapter code, and provides greater control over the transactional behavior of the adapter.</span></span>  
  
 <span data-ttu-id="07c56-132">下面演示了如何创建依赖的事务，并将此附加到消息之前它将返回到客户端。</span><span class="sxs-lookup"><span data-stu-id="07c56-132">The following demonstrates creating a dependent transaction, and attaching this to the message before it is returned to the client.</span></span>  
  
```csharp  
  
Transaction transaction = inboundConnection.CurrentTransaction; //Existing transaction  
DependentTransaction dt = transaction.DependentClone(DependentCloneOption.BlockCommitUntilComplete);  
TransactionMessageProperty.Set(dt, message);  
inboundReply.DependentTransaction = dt; //this will later be closed during Reply processing  
```  
  
## <a name="see-also"></a><span data-ttu-id="07c56-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="07c56-133">See Also</span></span>  
 [<span data-ttu-id="07c56-134">开发活动</span><span class="sxs-lookup"><span data-stu-id="07c56-134">Development Activities</span></span>](../../esb-toolkit/development-activities.md)