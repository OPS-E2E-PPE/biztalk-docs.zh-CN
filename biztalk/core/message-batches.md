---
title: 消息批处理 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5f893d16-2670-4463-9a89-6f5be912a045
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25866ac076d77eae13d2ab5378a7582f584b6670
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262717"
---
# <a name="message-batches"></a><span data-ttu-id="0d90e-102">消息批</span><span class="sxs-lookup"><span data-stu-id="0d90e-102">Message Batches</span></span>
<span data-ttu-id="0d90e-103">当你的适配器具有一组需要一次处理的消息时，你应执行批处理这些消息来优化性能。</span><span class="sxs-lookup"><span data-stu-id="0d90e-103">When your adapter has a group of messages that need to be processed at one time, you should batch these messages to optimize performance.</span></span> <span data-ttu-id="0d90e-104">以编程方式，消息批次不会与关联的操作的消息的集合。</span><span class="sxs-lookup"><span data-stu-id="0d90e-104">Programmatically, message batches are collections of messages with an associated operation.</span></span> <span data-ttu-id="0d90e-105">通过对批处理中的消息进行分组，而不是单独提交每条消息，你可以优化使用资源和处理任务。</span><span class="sxs-lookup"><span data-stu-id="0d90e-105">By grouping messages in a batch rather than submitting each message individually, you optimize the use of resources and processing tasks.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0d90e-106">使用批处理到：</span><span class="sxs-lookup"><span data-stu-id="0d90e-106"> uses batching to:</span></span>  
  
-   <span data-ttu-id="0d90e-107">对于不同的许多消息分摊事务的成本。</span><span class="sxs-lookup"><span data-stu-id="0d90e-107">Amortize the cost of the transaction across many messages.</span></span>  
  
-   <span data-ttu-id="0d90e-108">通过减少数据库内部数量的增加速度往返。</span><span class="sxs-lookup"><span data-stu-id="0d90e-108">Increase speed by reducing the internal number of database round trips.</span></span>  
  
-   <span data-ttu-id="0d90e-109">通过异步处理消息更高效地使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 线程池。</span><span class="sxs-lookup"><span data-stu-id="0d90e-109">Make more efficient use of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] thread pool by processing the messages asynchronously.</span></span>  
  
 <span data-ttu-id="0d90e-110">批处理是工作的一套是工作的原子操作。</span><span class="sxs-lookup"><span data-stu-id="0d90e-110">A batch is a unit of work that is atomic.</span></span> <span data-ttu-id="0d90e-111">也就是说，在它的所有操作都成功，或在它的所有操作都失败。</span><span class="sxs-lookup"><span data-stu-id="0d90e-111">That is, either all operations in it succeed or all operations in it fail.</span></span> <span data-ttu-id="0d90e-112">如果批处理中的一个操作成功，但另一个操作将失败，构成批处理的所有操作都将都失效，并且必须重新提交消息。</span><span class="sxs-lookup"><span data-stu-id="0d90e-112">If one operation in a batch succeeds but another operation fails, all the operations that make up the batch are invalidated and the messages must be resubmitted.</span></span> <span data-ttu-id="0d90e-113">这意味着适配器必须三个操作以响应一批失败：</span><span class="sxs-lookup"><span data-stu-id="0d90e-113">This means that an adapter must do three things in response to a failed batch:</span></span>  
  
-   <span data-ttu-id="0d90e-114">确定失败的哪些消息。</span><span class="sxs-lookup"><span data-stu-id="0d90e-114">Determine which messages failed.</span></span>  
  
-   <span data-ttu-id="0d90e-115">决定如何处理失败的消息的内容。</span><span class="sxs-lookup"><span data-stu-id="0d90e-115">Decide what to do with the failed messages.</span></span>  
  
-   <span data-ttu-id="0d90e-116">重新提交未通过的消息。</span><span class="sxs-lookup"><span data-stu-id="0d90e-116">Resubmit the messages that did not fail.</span></span>