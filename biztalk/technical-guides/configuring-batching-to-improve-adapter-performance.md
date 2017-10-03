---
title: "配置批处理，以便提高适配器性能 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 65589925-af94-45f1-b501-37c21618b2cf
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0dbee8e5b238af0a6dc7f15d54b85d85e0c4b26c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-batching-to-improve-adapter-performance"></a><span data-ttu-id="766c3-102">配置批处理，以便提高适配器性能</span><span class="sxs-lookup"><span data-stu-id="766c3-102">Configuring Batching to Improve Adapter Performance</span></span>
<span data-ttu-id="766c3-103">一个适配器处理批处理的方式可以带来明显影响性能。</span><span class="sxs-lookup"><span data-stu-id="766c3-103">The way an adapter processes a batch can have a significant effect on performance.</span></span> <span data-ttu-id="766c3-104">因为存在与每个事务相关联的固定延迟，所以，您应该通过将多个操作合并为单个批，尝试尽量减少事务的数目。</span><span class="sxs-lookup"><span data-stu-id="766c3-104">Because there is a fixed delay associated with each transaction, you should try to minimize the number of transactions by combining more than one operation into a single batch.</span></span>  
  
 <span data-ttu-id="766c3-105">如果您要提交到的消息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]分批情况下，不限制批次大小仅根据消息计数。</span><span class="sxs-lookup"><span data-stu-id="766c3-105">If you are submitting messages to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in batches, do not limit the batch size based only on the message count.</span></span> <span data-ttu-id="766c3-106">例如，如果批次大小为两个且适配器获取的四个消息分别大小 4 KB，8 KB、 1 MB 和 5 MB 将第一批的大小 12 KB 和第二个批处理将的大小 6 MB。</span><span class="sxs-lookup"><span data-stu-id="766c3-106">For example, if the batch size is two and the adapter gets four messages of size 4 KB, 8 KB, 1 MB, and 5 MB respectively, the first batch will be of size 12 KB, and the second batch will be of size 6 MB.</span></span> <span data-ttu-id="766c3-107">因为 BizTalk 消息引擎顺序处理单个批中的所有消息，所以，在此示例中，对第二个批的处理速度比对第一个批的处理速度要慢得多。</span><span class="sxs-lookup"><span data-stu-id="766c3-107">Because the BizTalk Messaging Engine processes all messages in a single batch sequentially, the second batch in this example will be processed much more slowly than the first batch.</span></span> <span data-ttu-id="766c3-108">此操作的效果是降低的吞吐量。</span><span class="sxs-lookup"><span data-stu-id="766c3-108">The effect of this is reduced throughput.</span></span>  
  
 <span data-ttu-id="766c3-109">若要处理此问题，我们建议你批处理基于消息计数和总批处理 （即，以字节为单位的批大小） 中的字节数。</span><span class="sxs-lookup"><span data-stu-id="766c3-109">To handle this problem, we recommend that you batch based on both the message count and the total number of bytes in the batch (that is, batch size in bytes).</span></span> <span data-ttu-id="766c3-110">没有任何最佳数量的总字节数。</span><span class="sxs-lookup"><span data-stu-id="766c3-110">There is no optimal number for total bytes.</span></span> <span data-ttu-id="766c3-111">但是，在正常处理方案中，如果批大小超过 1 MB，首先将遇到较差的并发性和吞吐量。</span><span class="sxs-lookup"><span data-stu-id="766c3-111">However, in a normal processing scenario, if the batch size exceeds 1 MB, you will start encountering poor concurrency and throughput.</span></span>  
  
 <span data-ttu-id="766c3-112">适配器通常处理在生产环境中的不同大小的消息。</span><span class="sxs-lookup"><span data-stu-id="766c3-112">Adapters generally process messages of varying size in the production environment.</span></span> <span data-ttu-id="766c3-113">传入消息的大小很可能有很大差异。</span><span class="sxs-lookup"><span data-stu-id="766c3-113">The sizes of incoming messages are likely to vary significantly.</span></span> <span data-ttu-id="766c3-114">因此，始终使用消息计数和总字节数来生成批处理。</span><span class="sxs-lookup"><span data-stu-id="766c3-114">As a result, always use message count and total bytes to build the batch.</span></span>