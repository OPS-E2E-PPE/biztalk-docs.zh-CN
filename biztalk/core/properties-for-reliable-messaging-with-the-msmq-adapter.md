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
# <a name="properties-for-reliable-messaging-with-the-msmq-adapter"></a><span data-ttu-id="26c6a-102">可靠消息传送的 MSMQ 适配器属性</span><span class="sxs-lookup"><span data-stu-id="26c6a-102">Properties for Reliable Messaging with the MSMQ Adapter</span></span>
<span data-ttu-id="26c6a-103">可以提高可靠性的发送和接收消息使用 MSMQ 适配器配置 MSMQ 适配器的方式。</span><span class="sxs-lookup"><span data-stu-id="26c6a-103">You can improve the reliability of sending and receiving messages with the MSMQ adapter by the way you configure the MSMQ adapter.</span></span> <span data-ttu-id="26c6a-104">本主题讨论如何使用可靠消息传送的多个配置属性。</span><span class="sxs-lookup"><span data-stu-id="26c6a-104">This topic discusses using several configuration properties for reliable messaging.</span></span>  
  
## <a name="running-msmq-adapter-handlers-within-a-clustered-biztalk-host"></a><span data-ttu-id="26c6a-105">在群集 BizTalk 主机内运行 MSMQ 适配器处理程序</span><span class="sxs-lookup"><span data-stu-id="26c6a-105">Running MSMQ Adapter Handlers Within a Clustered BizTalk Host</span></span>  
 <span data-ttu-id="26c6a-106">高可用性的一种方法是运行适配器处理程序中多个主机实例在不同 BizTalk 服务器上同时。</span><span class="sxs-lookup"><span data-stu-id="26c6a-106">One approach to high availability is to run adapter handlers in multiple host instances on different BizTalk servers simultaneously.</span></span> <span data-ttu-id="26c6a-107">不建议使用此方法对于 MSMQ 适配器处理程序，因为 MSMQ 不支持远程事务性的读取，MSMQ 发送处理程序具有依存的 MSMQ 服务的本地运行实例。</span><span class="sxs-lookup"><span data-stu-id="26c6a-107">This approach is not recommended for the MSMQ adapter handlers, because MSMQ does not support remote transacted reads and because the MSMQ send handler maintains a dependency on the locally running instance of the MSMQ service.</span></span> <span data-ttu-id="26c6a-108">若要提供高可用性的 MSMQ 发送和接收处理程序建议在群集 BizTalk 主机的实例中运行 MSMQ 适配器处理程序。</span><span class="sxs-lookup"><span data-stu-id="26c6a-108">To provide high availability for the MSMQ send and receive handlers it is recommended that you run the MSMQ adapter handlers in a clustered instance of a BizTalk Host.</span></span> <span data-ttu-id="26c6a-109">有关详细信息，请参阅[群集主机内运行适配器处理程序的注意事项](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)。</span><span class="sxs-lookup"><span data-stu-id="26c6a-109">For more information, see [Considerations for Running Adapter Handlers within a Clustered Host](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md).</span></span>  
  
## <a name="queue-failure-and-the-dead-letter-queue"></a><span data-ttu-id="26c6a-110">队列错误和死信队列</span><span class="sxs-lookup"><span data-stu-id="26c6a-110">Queue Failure and the Dead Letter Queue</span></span>  
 <span data-ttu-id="26c6a-111">已成功发送一条消息后, 没有错误的后续消息如果禁用或删除接收队列。</span><span class="sxs-lookup"><span data-stu-id="26c6a-111">After successfully sending a message, there is no error for subsequent messages if the receiving queue is disabled or deleted.</span></span> <span data-ttu-id="26c6a-112">这种情况下可能会导致消息丢失。</span><span class="sxs-lookup"><span data-stu-id="26c6a-112">This situation could cause loss of messages.</span></span>  
  
 <span data-ttu-id="26c6a-113">设置**使用死信队列**配置属性设置为**True**防止丢失消息。</span><span class="sxs-lookup"><span data-stu-id="26c6a-113">Setting the **Use Dead Letter Queue** configuration property to **True** prevents you from losing messages.</span></span> <span data-ttu-id="26c6a-114">当该属性是`True`（默认值），进入死信队列的队列不会接收的消息。</span><span class="sxs-lookup"><span data-stu-id="26c6a-114">When the property is `True` (the default), messages that the queue does not receive go into the dead letter queue.</span></span>  
  
## <a name="impersonation-and-remote-queues"></a><span data-ttu-id="26c6a-115">模拟和远程队列</span><span class="sxs-lookup"><span data-stu-id="26c6a-115">Impersonation and Remote Queues</span></span>  
 <span data-ttu-id="26c6a-116">您还必须设置**使用死信队列**配置属性设置为**True**当你使用远程队列。</span><span class="sxs-lookup"><span data-stu-id="26c6a-116">You also have to set the **Use Dead Letter Queue** configuration property to **True** when you use remote queues.</span></span> <span data-ttu-id="26c6a-117">如果 MSMQ 适配器模拟而无需使用远程队列的权限的用户，该消息可能会丢失。</span><span class="sxs-lookup"><span data-stu-id="26c6a-117">If the adapter for MSMQ impersonates a user without permission to use the remote queue, the message could be lost.</span></span>  
  
 <span data-ttu-id="26c6a-118">当该属性是 **，则返回 True**和模拟的用户不具有使用远程队列的权限，消息将进入死信队列在本地或远程计算机上。</span><span class="sxs-lookup"><span data-stu-id="26c6a-118">When the property is **True** and the impersonated user does not have permission to use the remote queue, the message goes to the dead letter queue on either the local or remote computer.</span></span> <span data-ttu-id="26c6a-119">在事务性发送中，消息将发送到死信队列在本地计算机上。</span><span class="sxs-lookup"><span data-stu-id="26c6a-119">In a transactional send, the message goes to the dead letter queue on the local computer.</span></span> <span data-ttu-id="26c6a-120">在非事务性发送中，消息将发送到死信队列在远程计算机上。</span><span class="sxs-lookup"><span data-stu-id="26c6a-120">In a non-transactional send, the message goes to the dead letter queue on the remote computer.</span></span>  
  
## <a name="recoverable-and-use-journal-queue-properties"></a><span data-ttu-id="26c6a-121">可恢复，并使用日志队列属性</span><span class="sxs-lookup"><span data-stu-id="26c6a-121">Recoverable and Use Journal Queue Properties</span></span>  
 <span data-ttu-id="26c6a-122">这两个**可恢复**并**使用日志队列**属性都可保存发送消息的副本。</span><span class="sxs-lookup"><span data-stu-id="26c6a-122">Both the **Recoverable** and **Use Journal Queue** properties save copies of sent messages.</span></span> <span data-ttu-id="26c6a-123">有关这些属性的详细信息，请参阅[如何配置 MSMQ 接收位置](../core/how-to-configure-an-msmq-receive-location.md)并[如何配置 MSMQ 发送端口](../core/how-to-configure-an-msmq-send-port.md)。</span><span class="sxs-lookup"><span data-stu-id="26c6a-123">For more information about these properties, see [How to Configure an MSMQ Receive Location](../core/how-to-configure-an-msmq-receive-location.md) and [How to Configure an MSMQ Send Port](../core/how-to-configure-an-msmq-send-port.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26c6a-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="26c6a-124">See Also</span></span>  
 <span data-ttu-id="26c6a-125">[使用 MSMQ 适配器可靠消息传送](../core/reliable-messaging-with-the-msmq-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="26c6a-125">[Reliable Messaging with the MSMQ Adapter](../core/reliable-messaging-with-the-msmq-adapter.md) </span></span>  
 [<span data-ttu-id="26c6a-126">在群集主机内运行适配器处理程序的注意事项</span><span class="sxs-lookup"><span data-stu-id="26c6a-126">Considerations for Running Adapter Handlers within a Clustered Host</span></span>](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)