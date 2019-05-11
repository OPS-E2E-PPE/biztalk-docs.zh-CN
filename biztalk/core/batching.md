---
title: 批处理 |Microsoft Docs
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
ms.openlocfilehash: 941ded3f6b88c835c2eae819099449ed7d4e6974
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65529094"
---
# <a name="batching"></a><span data-ttu-id="ecbe4-102">批处理</span><span class="sxs-lookup"><span data-stu-id="ecbe4-102">Batching</span></span>
<span data-ttu-id="ecbe4-103">*批处理*是一种允许将用于优化数据库往返过程的一组消息的序列化的处理。</span><span class="sxs-lookup"><span data-stu-id="ecbe4-103">*Batching* is a serialized processing of a set of messages that allows for optimizations with respect to database round trips.</span></span> <span data-ttu-id="ecbe4-104">一批是原子; 工作单元也就是说，它要么全部成功要么所有失败。</span><span class="sxs-lookup"><span data-stu-id="ecbe4-104">A batch is a unit of work that is atomic; that is, it either all succeeds or all fails.</span></span> <span data-ttu-id="ecbe4-105">如果在批处理中的一个操作成功，但另一个操作失败，构成批的所有操作都将失效，并且必须重复。</span><span class="sxs-lookup"><span data-stu-id="ecbe4-105">If one operation in a batch succeeds but another operation fails, all the operations that make up the batch are invalidated and must be repeated.</span></span>  
  
 <span data-ttu-id="ecbe4-106">BizTalk Server 使用批处理执行：</span><span class="sxs-lookup"><span data-stu-id="ecbe4-106">BizTalk Server uses batching to:</span></span>  
  
-   <span data-ttu-id="ecbe4-107">在许多消息范围内分摊交易成本。</span><span class="sxs-lookup"><span data-stu-id="ecbe4-107">Amortize the cost of the transaction across many messages.</span></span>  
  
-   <span data-ttu-id="ecbe4-108">通过减少数据库的内部数量的增加速度往返。</span><span class="sxs-lookup"><span data-stu-id="ecbe4-108">Increase speed by reducing the internal number of database round trips.</span></span>  
  
-   <span data-ttu-id="ecbe4-109">使用 BizTalk Server 异步 API 发出更有效地使用 BizTalk Server 线程池。</span><span class="sxs-lookup"><span data-stu-id="ecbe4-109">Make more efficient use of the BizTalk Server thread pool by using the BizTalk Server Asynchronous API.</span></span>  
  
## <a name="applying-batching"></a><span data-ttu-id="ecbe4-110">应用批处理</span><span class="sxs-lookup"><span data-stu-id="ecbe4-110">Applying Batching</span></span>  
 <span data-ttu-id="ecbe4-111">批处理的接收位置的高级属性中配置和发送端口端自动启用。</span><span class="sxs-lookup"><span data-stu-id="ecbe4-111">Batching is configured in the advanced properties for a receive location and is enabled automatically on the send port side.</span></span>  
  
## <a name="lowering-the-batch-size"></a><span data-ttu-id="ecbe4-112">减小批大小</span><span class="sxs-lookup"><span data-stu-id="ecbe4-112">Lowering the Batch Size</span></span>  
 <span data-ttu-id="ecbe4-113">如果在以下情况下，应减小批大小：</span><span class="sxs-lookup"><span data-stu-id="ecbe4-113">You should lower the batch size if in the following instances:</span></span>  
  
-   <span data-ttu-id="ecbe4-114">处理大消息时</span><span class="sxs-lookup"><span data-stu-id="ecbe4-114">When processing large messages</span></span>  
  
-   <span data-ttu-id="ecbe4-115">当数据库往返行程不是瓶颈所在</span><span class="sxs-lookup"><span data-stu-id="ecbe4-115">When database round trips are not your bottleneck</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ecbe4-116">更改时要小心**LargeMessageThreshold**设置。</span><span class="sxs-lookup"><span data-stu-id="ecbe4-116">Be careful when changing the **LargeMessageThreshold** setting.</span></span> <span data-ttu-id="ecbe4-117">批大小乘以平均消息大小应小于**LargeMessageThreshold**设置，除非批大小为 1。</span><span class="sxs-lookup"><span data-stu-id="ecbe4-117">The batch size multiplied by the average message size should be less than the **LargeMessageThreshold** setting unless the batch size is 1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecbe4-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="ecbe4-118">See Also</span></span>  
 <span data-ttu-id="ecbe4-119">[消息引擎](../core/the-messaging-engine.md) </span><span class="sxs-lookup"><span data-stu-id="ecbe4-119">[The Messaging Engine](../core/the-messaging-engine.md) </span></span>  
 <span data-ttu-id="ecbe4-120">[批处理消息的接收处理](../core/batching-messages-for-receive-processing.md) </span><span class="sxs-lookup"><span data-stu-id="ecbe4-120">[Batching Messages for Receive Processing](../core/batching-messages-for-receive-processing.md) </span></span>  
 [<span data-ttu-id="ecbe4-121">为发送处理批处理消息</span><span class="sxs-lookup"><span data-stu-id="ecbe4-121">Batching Messages for Send Processing</span></span>](../core/batching-messages-for-send-processing.md)