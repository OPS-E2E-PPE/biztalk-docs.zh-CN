---
title: 批处理 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- batching
- Messaging Engine, batching
- batching, batch size
- batching, about batching
- batching, configuring
- batching, Messaging Engine
ms.assetid: eadc177a-d395-4f99-8dab-aa706fd8ea00
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca31344e60daa88a37c21d0f90b6cf2d2a8aa5a7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230885"
---
# <a name="batching"></a><span data-ttu-id="65cc0-102">批处理</span><span class="sxs-lookup"><span data-stu-id="65cc0-102">Batching</span></span>
<span data-ttu-id="65cc0-103">*批处理*是一种允许与目标为数据库优化往返的一组消息的序列化的处理。</span><span class="sxs-lookup"><span data-stu-id="65cc0-103">*Batching* is a serialized processing of a set of messages that allows for optimizations with respect to database round trips.</span></span> <span data-ttu-id="65cc0-104">批是原子工作单元；也就是说，它或者全部成功，或者全部失败。</span><span class="sxs-lookup"><span data-stu-id="65cc0-104">A batch is a unit of work that is atomic; that is, it either all succeeds or all fails.</span></span> <span data-ttu-id="65cc0-105">如果批中的某个操作成功，但另一个操作失败，则构成该批的所有操作都将失效，必须重新执行。</span><span class="sxs-lookup"><span data-stu-id="65cc0-105">If one operation in a batch succeeds but another operation fails, all the operations that make up the batch are invalidated and must be repeated.</span></span>  
  
 <span data-ttu-id="65cc0-106">BizTalk Server 使用批处理执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="65cc0-106">BizTalk Server uses batching to:</span></span>  
  
-   <span data-ttu-id="65cc0-107">对于不同的许多消息分摊事务的成本。</span><span class="sxs-lookup"><span data-stu-id="65cc0-107">Amortize the cost of the transaction across many messages.</span></span>  
  
-   <span data-ttu-id="65cc0-108">通过减少数据库内部数量的增加速度往返。</span><span class="sxs-lookup"><span data-stu-id="65cc0-108">Increase speed by reducing the internal number of database round trips.</span></span>  
  
-   <span data-ttu-id="65cc0-109">通过使用 BizTalk Server 异步 API 更高效地使用 BizTalk Server 线程池。</span><span class="sxs-lookup"><span data-stu-id="65cc0-109">Make more efficient use of the BizTalk Server thread pool by using the BizTalk Server Asynchronous API.</span></span>  
  
## <a name="applying-batching"></a><span data-ttu-id="65cc0-110">应用批处理</span><span class="sxs-lookup"><span data-stu-id="65cc0-110">Applying Batching</span></span>  
 <span data-ttu-id="65cc0-111">批处理在接收位置的高级属性中进行配置，并且在发送端口端自动启用。</span><span class="sxs-lookup"><span data-stu-id="65cc0-111">Batching is configured in the advanced properties for a receive location and is enabled automatically on the send port side.</span></span>  
  
## <a name="lowering-the-batch-size"></a><span data-ttu-id="65cc0-112">减小批大小</span><span class="sxs-lookup"><span data-stu-id="65cc0-112">Lowering the Batch Size</span></span>  
 <span data-ttu-id="65cc0-113">在以下情况下应减小批大小：</span><span class="sxs-lookup"><span data-stu-id="65cc0-113">You should lower the batch size if in the following instances:</span></span>  
  
-   <span data-ttu-id="65cc0-114">在处理大的消息时</span><span class="sxs-lookup"><span data-stu-id="65cc0-114">When processing large messages</span></span>  
  
-   <span data-ttu-id="65cc0-115">当数据库往返过程并非瓶颈所在时</span><span class="sxs-lookup"><span data-stu-id="65cc0-115">When database round trips are not your bottleneck</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="65cc0-116">更改时要小心**LargeMessageThreshold**设置。</span><span class="sxs-lookup"><span data-stu-id="65cc0-116">Be careful when changing the **LargeMessageThreshold** setting.</span></span> <span data-ttu-id="65cc0-117">乘以平均消息大小的批处理大小应该小于**LargeMessageThreshold**设置，除非批处理大小为 1。</span><span class="sxs-lookup"><span data-stu-id="65cc0-117">The batch size multiplied by the average message size should be less than the **LargeMessageThreshold** setting unless the batch size is 1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65cc0-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="65cc0-118">See Also</span></span>  
 <span data-ttu-id="65cc0-119">[消息传送的引擎](../core/the-messaging-engine.md) </span><span class="sxs-lookup"><span data-stu-id="65cc0-119">[The Messaging Engine](../core/the-messaging-engine.md) </span></span>  
 <span data-ttu-id="65cc0-120">[批处理消息接收处理](../core/batching-messages-for-receive-processing.md) </span><span class="sxs-lookup"><span data-stu-id="65cc0-120">[Batching Messages for Receive Processing](../core/batching-messages-for-receive-processing.md) </span></span>  
 [<span data-ttu-id="65cc0-121">对消息进行批处理的发送处理</span><span class="sxs-lookup"><span data-stu-id="65cc0-121">Batching Messages for Send Processing</span></span>](../core/batching-messages-for-send-processing.md)