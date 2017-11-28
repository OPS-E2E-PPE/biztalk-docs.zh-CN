---
title: "使用 MSMQ 适配器可靠消息传递的属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49aebf12c86ae72d5dcb224d078c62afefcb8f46
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="properties-for-reliable-messaging-with-the-msmq-adapter"></a><span data-ttu-id="78d5b-102">使用 MSMQ 适配器可靠消息传递的属性</span><span class="sxs-lookup"><span data-stu-id="78d5b-102">Properties for Reliable Messaging with the MSMQ Adapter</span></span>
<span data-ttu-id="78d5b-103">通过配置 MSMQ 适配器，可以提高使用 MSMQ 适配器发送和接收消息的可靠性。</span><span class="sxs-lookup"><span data-stu-id="78d5b-103">You can improve the reliability of sending and receiving messages with the MSMQ adapter by the way you configure the MSMQ adapter.</span></span> <span data-ttu-id="78d5b-104">本主题将介绍使用多个配置属性进行可靠的消息传送。</span><span class="sxs-lookup"><span data-stu-id="78d5b-104">This topic discusses using several configuration properties for reliable messaging.</span></span>  
  
## <a name="running-msmq-adapter-handlers-within-a-clustered-biztalk-host"></a><span data-ttu-id="78d5b-105">在群集的 BizTalk 主机内运行 MSMQ 适配器处理程序</span><span class="sxs-lookup"><span data-stu-id="78d5b-105">Running MSMQ Adapter Handlers Within a Clustered BizTalk Host</span></span>  
 <span data-ttu-id="78d5b-106">确保高可用性的一个方法是：在不同的 BizTalk Server 上的多个主机实例中同时运行适配器处理程序。</span><span class="sxs-lookup"><span data-stu-id="78d5b-106">One approach to high availability is to run adapter handlers in multiple host instances on different BizTalk servers simultaneously.</span></span> <span data-ttu-id="78d5b-107">对于 MSMQ 适配器处理程序，不建议使用此方法，因为 MSMQ 不支持远程事务性读取，并且 MSMQ 发送处理程序对于 MSMQ 服务的本地运行实例具有依存关系。</span><span class="sxs-lookup"><span data-stu-id="78d5b-107">This approach is not recommended for the MSMQ adapter handlers, because MSMQ does not support remote transacted reads and because the MSMQ send handler maintains a dependency on the locally running instance of the MSMQ service.</span></span> <span data-ttu-id="78d5b-108">为了提高 MSMQ 发送和接收处理程序的可用性，建议您在 BizTalk 主机的群集实例中运行 MSMQ 适配器处理程序。</span><span class="sxs-lookup"><span data-stu-id="78d5b-108">To provide high availability for the MSMQ send and receive handlers it is recommended that you run the MSMQ adapter handlers in a clustered instance of a BizTalk Host.</span></span> <span data-ttu-id="78d5b-109">有关详细信息，请参阅[在群集主机内运行适配器处理程序的注意事项](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)。</span><span class="sxs-lookup"><span data-stu-id="78d5b-109">For more information, see [Considerations for Running Adapter Handlers within a Clustered Host](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md).</span></span>  
  
## <a name="queue-failure-and-the-dead-letter-queue"></a><span data-ttu-id="78d5b-110">队列错误和死信队列</span><span class="sxs-lookup"><span data-stu-id="78d5b-110">Queue Failure and the Dead Letter Queue</span></span>  
 <span data-ttu-id="78d5b-111">消息成功发送后，如果禁用或删除接收队列，则后续消息不会出错。</span><span class="sxs-lookup"><span data-stu-id="78d5b-111">After successfully sending a message, there is no error for subsequent messages if the receiving queue is disabled or deleted.</span></span> <span data-ttu-id="78d5b-112">这种情况会导致消息丢失。</span><span class="sxs-lookup"><span data-stu-id="78d5b-112">This situation could cause loss of messages.</span></span>  
  
 <span data-ttu-id="78d5b-113">设置**使用死信队列**配置属性设置为**True**防止丢失消息。</span><span class="sxs-lookup"><span data-stu-id="78d5b-113">Setting the **Use Dead Letter Queue** configuration property to **True** prevents you from losing messages.</span></span> <span data-ttu-id="78d5b-114">当该属性是`True`（默认值）、 队列没有接收的消息就可进入死信队列。</span><span class="sxs-lookup"><span data-stu-id="78d5b-114">When the property is `True` (the default), messages that the queue does not receive go into the dead letter queue.</span></span>  
  
## <a name="impersonation-and-remote-queues"></a><span data-ttu-id="78d5b-115">模拟和远程队列</span><span class="sxs-lookup"><span data-stu-id="78d5b-115">Impersonation and Remote Queues</span></span>  
 <span data-ttu-id="78d5b-116">你还必须设置**使用死信队列**配置属性设置为**True**当你使用远程队列。</span><span class="sxs-lookup"><span data-stu-id="78d5b-116">You also have to set the **Use Dead Letter Queue** configuration property to **True** when you use remote queues.</span></span> <span data-ttu-id="78d5b-117">如果 MSMQ 适配器在没有远程队列使用权限的情况下模拟用户，则消息会丢失。</span><span class="sxs-lookup"><span data-stu-id="78d5b-117">If the adapter for MSMQ impersonates a user without permission to use the remote queue, the message could be lost.</span></span>  
  
 <span data-ttu-id="78d5b-118">当该属性是**True**和模拟的用户没有使用远程队列的权限，该消息在本地或远程计算机上将转到死信队列。</span><span class="sxs-lookup"><span data-stu-id="78d5b-118">When the property is **True** and the impersonated user does not have permission to use the remote queue, the message goes to the dead letter queue on either the local or remote computer.</span></span> <span data-ttu-id="78d5b-119">在事务性发送中，消息将进入本地计算机的死信队列。</span><span class="sxs-lookup"><span data-stu-id="78d5b-119">In a transactional send, the message goes to the dead letter queue on the local computer.</span></span> <span data-ttu-id="78d5b-120">在非事务性发送中，消息将进入远程计算机的死信队列。</span><span class="sxs-lookup"><span data-stu-id="78d5b-120">In a non-transactional send, the message goes to the dead letter queue on the remote computer.</span></span>  
  
## <a name="recoverable-and-use-journal-queue-properties"></a><span data-ttu-id="78d5b-121">“可恢复”和“使用日志队列”属性</span><span class="sxs-lookup"><span data-stu-id="78d5b-121">Recoverable and Use Journal Queue Properties</span></span>  
 <span data-ttu-id="78d5b-122">这两个**可恢复**和**使用日记队列**属性保存发送消息的副本。</span><span class="sxs-lookup"><span data-stu-id="78d5b-122">Both the **Recoverable** and **Use Journal Queue** properties save copies of sent messages.</span></span> <span data-ttu-id="78d5b-123">有关这些属性的详细信息，请参阅[如何配置 MSMQ 接收位置](../core/how-to-configure-an-msmq-receive-location.md)和[如何配置 MSMQ 发送端口](../core/how-to-configure-an-msmq-send-port.md)。</span><span class="sxs-lookup"><span data-stu-id="78d5b-123">For more information about these properties, see [How to Configure an MSMQ Receive Location](../core/how-to-configure-an-msmq-receive-location.md) and [How to Configure an MSMQ Send Port](../core/how-to-configure-an-msmq-send-port.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78d5b-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="78d5b-124">See Also</span></span>  
 <span data-ttu-id="78d5b-125">[使用 MSMQ 适配器可靠消息传递](../core/reliable-messaging-with-the-msmq-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="78d5b-125">[Reliable Messaging with the MSMQ Adapter](../core/reliable-messaging-with-the-msmq-adapter.md) </span></span>  
 [<span data-ttu-id="78d5b-126">运行在群集主机内的适配器处理程序的注意事项</span><span class="sxs-lookup"><span data-stu-id="78d5b-126">Considerations for Running Adapter Handlers within a Clustered Host</span></span>](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)