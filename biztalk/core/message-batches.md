---
title: 消息批处理 |Microsoft Docs
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
ms.openlocfilehash: 78222848258ea4c1840b645c1357bceb49c0ac14
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65531168"
---
# <a name="message-batches"></a><span data-ttu-id="97807-102">消息批</span><span class="sxs-lookup"><span data-stu-id="97807-102">Message Batches</span></span>
<span data-ttu-id="97807-103">当您的适配器具有一组需要一次处理的消息时，你应执行批处理这些消息，以优化性能。</span><span class="sxs-lookup"><span data-stu-id="97807-103">When your adapter has a group of messages that need to be processed at one time, you should batch these messages to optimize performance.</span></span> <span data-ttu-id="97807-104">以编程方式，消息批是具有关联的操作的消息的集合。</span><span class="sxs-lookup"><span data-stu-id="97807-104">Programmatically, message batches are collections of messages with an associated operation.</span></span> <span data-ttu-id="97807-105">通过对批中的消息进行分组，而不是逐个提交每个消息，你可以优化资源和处理任务的使用。</span><span class="sxs-lookup"><span data-stu-id="97807-105">By grouping messages in a batch rather than submitting each message individually, you optimize the use of resources and processing tasks.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="97807-106">使用批处理执行：</span><span class="sxs-lookup"><span data-stu-id="97807-106">uses batching to:</span></span>  

- <span data-ttu-id="97807-107">在许多消息范围内分摊交易成本。</span><span class="sxs-lookup"><span data-stu-id="97807-107">Amortize the cost of the transaction across many messages.</span></span>  

- <span data-ttu-id="97807-108">通过减少数据库的内部数量的增加速度往返。</span><span class="sxs-lookup"><span data-stu-id="97807-108">Increase speed by reducing the internal number of database round trips.</span></span>  

- <span data-ttu-id="97807-109">更有效地使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]以异步方式处理消息的线程池。</span><span class="sxs-lookup"><span data-stu-id="97807-109">Make more efficient use of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] thread pool by processing the messages asynchronously.</span></span>  

  <span data-ttu-id="97807-110">批是原子工作单元。</span><span class="sxs-lookup"><span data-stu-id="97807-110">A batch is a unit of work that is atomic.</span></span> <span data-ttu-id="97807-111">也就是说，在它的所有操作都成功，或在它的所有操作都失败。</span><span class="sxs-lookup"><span data-stu-id="97807-111">That is, either all operations in it succeed or all operations in it fail.</span></span> <span data-ttu-id="97807-112">如果在批处理中的一个操作成功，但另一个操作失败，构成批的所有操作都将都失效，必须重新提交消息。</span><span class="sxs-lookup"><span data-stu-id="97807-112">If one operation in a batch succeeds but another operation fails, all the operations that make up the batch are invalidated and the messages must be resubmitted.</span></span> <span data-ttu-id="97807-113">这意味着适配器必须一批失败的响应中的三个操作：</span><span class="sxs-lookup"><span data-stu-id="97807-113">This means that an adapter must do three things in response to a failed batch:</span></span>  

- <span data-ttu-id="97807-114">确定失败的消息。</span><span class="sxs-lookup"><span data-stu-id="97807-114">Determine which messages failed.</span></span>  

- <span data-ttu-id="97807-115">确定应如何处理失败的消息。</span><span class="sxs-lookup"><span data-stu-id="97807-115">Decide what to do with the failed messages.</span></span>  

- <span data-ttu-id="97807-116">重新提交未失败的消息。</span><span class="sxs-lookup"><span data-stu-id="97807-116">Resubmit the messages that did not fail.</span></span>
