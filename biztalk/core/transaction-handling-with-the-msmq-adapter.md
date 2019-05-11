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
# <a name="transaction-handling-with-the-msmq-adapter"></a><span data-ttu-id="babf5-102">使用 MSMQ 适配器处理事务</span><span class="sxs-lookup"><span data-stu-id="babf5-102">Transaction Handling with the MSMQ Adapter</span></span>
<span data-ttu-id="babf5-103">本部分介绍在接收和发送的事务处理方式。</span><span class="sxs-lookup"><span data-stu-id="babf5-103">This section discusses how transactions work in receiving and sending.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="babf5-104">MSMQ 适配器的事务从扩展 BizTalk MessageBox 数据库到本地消息队列队列即使使用远程队列。</span><span class="sxs-lookup"><span data-stu-id="babf5-104">For the MSMQ adapter, a transaction extends from the BizTalk MessageBox database to the local Message Queuing queue even if you are using a remote queue.</span></span>  
  
 <span data-ttu-id="babf5-105">您可以使用事务，在这两个发送和接收使用 MSMQ 适配器。</span><span class="sxs-lookup"><span data-stu-id="babf5-105">You can use transactions on both send and receive with the MSMQ adapter.</span></span> <span data-ttu-id="babf5-106">在事务性发送适配器将累积消息，直到它具有完整的一批。</span><span class="sxs-lookup"><span data-stu-id="babf5-106">On transacted sends, the adapter accumulates messages until it has a complete batch.</span></span> <span data-ttu-id="babf5-107">然后，适配器作为单个事务提交到本地消息队列服务的批处理。</span><span class="sxs-lookup"><span data-stu-id="babf5-107">The adapter then submits the batch to the local Message Queuing service as a single transaction.</span></span> <span data-ttu-id="babf5-108">如果提交失败，适配器将尝试重新提交批处理。</span><span class="sxs-lookup"><span data-stu-id="babf5-108">If the submission fails, the adapter tries to resubmit the batch.</span></span> <span data-ttu-id="babf5-109">如果重新提交失败，适配器将转至次要传输。</span><span class="sxs-lookup"><span data-stu-id="babf5-109">If the resubmission fails, the adapter moves to the secondary transport.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="babf5-110">该适配器支持 Message Queuing 4.0 或更高版本的远程队列进行事务性读取。</span><span class="sxs-lookup"><span data-stu-id="babf5-110">The adapter supports transactional reads of remote queues with Message Queuing 4.0 or later only.</span></span> <span data-ttu-id="babf5-111">在此方案中 BizTalk Server 和远程消息队列服务器必须运行消息队列 4.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="babf5-111">In this scenario both the BizTalk Server and the remote Message Queuing server must be running Message Queuing 4.0 or later.</span></span>  
  
 <span data-ttu-id="babf5-112">在事务性接收，则适配器将挂起失败的消息，以便它不会丢失任何一个消息。</span><span class="sxs-lookup"><span data-stu-id="babf5-112">On transacted receives, the adapter suspends failed messages so that it does not lose any one of the messages.</span></span> <span data-ttu-id="babf5-113">在事务性接收适配器将消息添加到一批完成批处理之前。</span><span class="sxs-lookup"><span data-stu-id="babf5-113">During a transacted receive the adapter adds messages to a batch until the batch is complete.</span></span> <span data-ttu-id="babf5-114">然后，它将提交批处理：</span><span class="sxs-lookup"><span data-stu-id="babf5-114">It then submits the batch:</span></span>  
  
- <span data-ttu-id="babf5-115">如果没有任何问题，并且服务器接收消息，则适配器提交事务。</span><span class="sxs-lookup"><span data-stu-id="babf5-115">If there are no problems and the server receives the messages, the adapter commits the transaction.</span></span>  
  
- <span data-ttu-id="babf5-116">如果出现问题，适配器会创建新的批处理，当前事务的一部分。</span><span class="sxs-lookup"><span data-stu-id="babf5-116">If there are problems, the adapter creates a new batch as part of the current transaction.</span></span> <span data-ttu-id="babf5-117">然后，它将所有问题消息都移动到新的批。</span><span class="sxs-lookup"><span data-stu-id="babf5-117">It then moves any problem messages into the new batch.</span></span> <span data-ttu-id="babf5-118">然后重新提交第一批，并将新的批提交作为挂起的消息。</span><span class="sxs-lookup"><span data-stu-id="babf5-118">It then resubmits the first batch and submits the new batch as suspended messages.</span></span> <span data-ttu-id="babf5-119">如果在此重新提交过程没有任何问题，则适配器提交事务。</span><span class="sxs-lookup"><span data-stu-id="babf5-119">The adapter commits the transaction if there are no problems during this resubmission.</span></span>  
  
  <span data-ttu-id="babf5-120">如果在群集 BizTalk 主机实例中运行 MSMQ 适配器发送处理程序，应群集 MSMQ 服务中相同的群集组，以确保事务一致性。</span><span class="sxs-lookup"><span data-stu-id="babf5-120">If you are running an MSMQ adapter send handler in a clustered BizTalk Host instance, you should cluster the MSMQ service in the same cluster group to ensure transactional consistency.</span></span>  
  
  <span data-ttu-id="babf5-121">如果在 DCOMCNFG 实用工具中禁用"网络 DTC 访问"，则 MSMQ 事务性远程接收操作将失败并费解的错误消息。</span><span class="sxs-lookup"><span data-stu-id="babf5-121">If "Network DTC Access" is disabled in the DCOMCNFG utility, a MSMQ transactional remote receive operation will fail with a cryptic error message.</span></span>  <span data-ttu-id="babf5-122">若要执行事务性远程接收使用 MSMQ 适配器，必须启用"网络 DTC 访问"。</span><span class="sxs-lookup"><span data-stu-id="babf5-122">To do a transactional remote receive with the MSMQ adapter, "Network DTC Access" must be enabled.</span></span> <span data-ttu-id="babf5-123">可在找到更多信息[ http://go.microsoft.com/fwlink/?LinkId=124623 ](http://go.microsoft.com/fwlink/?LinkId=124623)。</span><span class="sxs-lookup"><span data-stu-id="babf5-123">More information can be found at [http://go.microsoft.com/fwlink/?LinkId=124623](http://go.microsoft.com/fwlink/?LinkId=124623).</span></span>  
  
  <span data-ttu-id="babf5-124">如果您正在运行 MSMQ 适配器接收处理程序在群集 BizTalk 主机实例中，应群集 MSMQ 服务中相同的群集组，以支持本地事务性的读取，因为 MSMQ 不支持远程事务性读取。</span><span class="sxs-lookup"><span data-stu-id="babf5-124">If you are running an MSMQ adapter receive handler in a clustered BizTalk Host instance, you should cluster the MSMQ service in the same cluster group to support local transacted reads because MSMQ does not support remote transactional reads.</span></span> <span data-ttu-id="babf5-125">有关在群集 BizTalk 主机的实例中运行 MSMQ 适配器处理程序的详细信息，请参阅[有关在群集主机内运行适配器处理程序的注意事项](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)。</span><span class="sxs-lookup"><span data-stu-id="babf5-125">For more information about running MSMQ adapter handlers in a clustered instance of a BizTalk Host, see [Considerations for Running Adapter Handlers within a Clustered Host](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="babf5-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="babf5-126">See Also</span></span>  
 [<span data-ttu-id="babf5-127">使用 MSMQ 适配器实现可靠消息传送</span><span class="sxs-lookup"><span data-stu-id="babf5-127">Reliable Messaging with the MSMQ Adapter</span></span>](../core/reliable-messaging-with-the-msmq-adapter.md)