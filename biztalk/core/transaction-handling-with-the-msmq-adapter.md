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
# <a name="transaction-handling-with-the-msmq-adapter"></a><span data-ttu-id="3cdd9-102">使用 MSMQ 适配器处理事务</span><span class="sxs-lookup"><span data-stu-id="3cdd9-102">Transaction Handling with the MSMQ Adapter</span></span>
<span data-ttu-id="3cdd9-103">本部分将介绍事务在接收和发送时的工作方式。</span><span class="sxs-lookup"><span data-stu-id="3cdd9-103">This section discusses how transactions work in receiving and sending.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3cdd9-104">对于 MSMQ 适配器，即使使用远程队列，事务也会从 BizTalk MessageBox 数据库扩展到本地消息队列。</span><span class="sxs-lookup"><span data-stu-id="3cdd9-104">For the MSMQ adapter, a transaction extends from the BizTalk MessageBox database to the local Message Queuing queue even if you are using a remote queue.</span></span>  
  
 <span data-ttu-id="3cdd9-105">使用 MSMQ 适配器，可以对发送和接收使用事务性功能。</span><span class="sxs-lookup"><span data-stu-id="3cdd9-105">You can use transactions on both send and receive with the MSMQ adapter.</span></span> <span data-ttu-id="3cdd9-106">在事务性发送中，适配器将累积消息，直到具有完整的一批消息。</span><span class="sxs-lookup"><span data-stu-id="3cdd9-106">On transacted sends, the adapter accumulates messages until it has a complete batch.</span></span> <span data-ttu-id="3cdd9-107">然后，适配器将该批消息作为单个事务提交给本地消息队列服务。</span><span class="sxs-lookup"><span data-stu-id="3cdd9-107">The adapter then submits the batch to the local Message Queuing service as a single transaction.</span></span> <span data-ttu-id="3cdd9-108">如果提交失败，则适配器将尝试重新提交该批消息。</span><span class="sxs-lookup"><span data-stu-id="3cdd9-108">If the submission fails, the adapter tries to resubmit the batch.</span></span> <span data-ttu-id="3cdd9-109">如果重新提交失败，则适配器将转至次要传输。</span><span class="sxs-lookup"><span data-stu-id="3cdd9-109">If the resubmission fails, the adapter moves to the secondary transport.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3cdd9-110">适配器仅支持使用 Message Queuing 4.0 或更高版本对远程队列进行事务性读取。</span><span class="sxs-lookup"><span data-stu-id="3cdd9-110">The adapter supports transactional reads of remote queues with Message Queuing 4.0 or later only.</span></span> <span data-ttu-id="3cdd9-111">在此方案中 BizTalk Server 和远程消息队列服务器必须运行消息队列 4.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="3cdd9-111">In this scenario both the BizTalk Server and the remote Message Queuing server must be running Message Queuing 4.0 or later.</span></span>  
  
 <span data-ttu-id="3cdd9-112">在事务性接收中，适配器将挂起失败消息，以便不丢失任何一个消息。</span><span class="sxs-lookup"><span data-stu-id="3cdd9-112">On transacted receives, the adapter suspends failed messages so that it does not lose any one of the messages.</span></span> <span data-ttu-id="3cdd9-113">在事务性接收过程中，适配器会将消息添加到一批中，直至该批消息完整，</span><span class="sxs-lookup"><span data-stu-id="3cdd9-113">During a transacted receive the adapter adds messages to a batch until the batch is complete.</span></span> <span data-ttu-id="3cdd9-114">然后提交该批消息：</span><span class="sxs-lookup"><span data-stu-id="3cdd9-114">It then submits the batch:</span></span>  
  
- <span data-ttu-id="3cdd9-115">如果没有任何问题，并且服务器接收到消息，则适配器提交事务。</span><span class="sxs-lookup"><span data-stu-id="3cdd9-115">If there are no problems and the server receives the messages, the adapter commits the transaction.</span></span>  
  
- <span data-ttu-id="3cdd9-116">如果出现问题，适配器将在当前事务中创建一个新批。</span><span class="sxs-lookup"><span data-stu-id="3cdd9-116">If there are problems, the adapter creates a new batch as part of the current transaction.</span></span> <span data-ttu-id="3cdd9-117">随后将所有问题消息移至该新批中。</span><span class="sxs-lookup"><span data-stu-id="3cdd9-117">It then moves any problem messages into the new batch.</span></span> <span data-ttu-id="3cdd9-118">然后，适配器重新提交第一批消息，并将该新的一批消息作为挂起的消息进行提交。</span><span class="sxs-lookup"><span data-stu-id="3cdd9-118">It then resubmits the first batch and submits the new batch as suspended messages.</span></span> <span data-ttu-id="3cdd9-119">如果在此重新提交过程中没有任何问题，则适配器提交事务。</span><span class="sxs-lookup"><span data-stu-id="3cdd9-119">The adapter commits the transaction if there are no problems during this resubmission.</span></span>  
  
  <span data-ttu-id="3cdd9-120">如果在群集的 BizTalk 主机实例中运行 MSMQ 适配器发送处理程序，则应在同一个群集组中对 MSMQ 服务进行群集以确保事务一致性。</span><span class="sxs-lookup"><span data-stu-id="3cdd9-120">If you are running an MSMQ adapter send handler in a clustered BizTalk Host instance, you should cluster the MSMQ service in the same cluster group to ensure transactional consistency.</span></span>  
  
  <span data-ttu-id="3cdd9-121">如果在 DCOMCNFG 实用工具中禁用了“网络 DTC 访问”，则 MSMQ 事务性远程接收操作将失败，并带有隐含的错误消息。</span><span class="sxs-lookup"><span data-stu-id="3cdd9-121">If "Network DTC Access" is disabled in the DCOMCNFG utility, a MSMQ transactional remote receive operation will fail with a cryptic error message.</span></span>  <span data-ttu-id="3cdd9-122">若要使用 MSMQ 适配器来执行事务性远程接收，必须启用“网络 DTC 访问”。</span><span class="sxs-lookup"><span data-stu-id="3cdd9-122">To do a transactional remote receive with the MSMQ adapter, "Network DTC Access" must be enabled.</span></span> <span data-ttu-id="3cdd9-123">可在找到更多信息[ http://go.microsoft.com/fwlink/?LinkId=124623 ](http://go.microsoft.com/fwlink/?LinkId=124623)。</span><span class="sxs-lookup"><span data-stu-id="3cdd9-123">More information can be found at [http://go.microsoft.com/fwlink/?LinkId=124623](http://go.microsoft.com/fwlink/?LinkId=124623).</span></span>  
  
  <span data-ttu-id="3cdd9-124">如果在群集的 BizTalk 主机实例中运行 MSMQ 适配器接收处理程序，则应在同一个群集组中对 MSMQ 服务进行群集以支持本地事务性读取，因为 MSMQ 不支持远程事务性读取。</span><span class="sxs-lookup"><span data-stu-id="3cdd9-124">If you are running an MSMQ adapter receive handler in a clustered BizTalk Host instance, you should cluster the MSMQ service in the same cluster group to support local transacted reads because MSMQ does not support remote transactional reads.</span></span> <span data-ttu-id="3cdd9-125">有关在群集 BizTalk 主机的实例中运行 MSMQ 适配器处理程序的详细信息，请参阅[有关在群集主机内运行适配器处理程序的注意事项](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)。</span><span class="sxs-lookup"><span data-stu-id="3cdd9-125">For more information about running MSMQ adapter handlers in a clustered instance of a BizTalk Host, see [Considerations for Running Adapter Handlers within a Clustered Host](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cdd9-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="3cdd9-126">See Also</span></span>  
 [<span data-ttu-id="3cdd9-127">使用 MSMQ 适配器实现可靠消息传送</span><span class="sxs-lookup"><span data-stu-id="3cdd9-127">Reliable Messaging with the MSMQ Adapter</span></span>](../core/reliable-messaging-with-the-msmq-adapter.md)