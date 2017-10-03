---
title: "影响最大可持续性能因素 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maximum sustainable throughput (MST), maintenance
- monitoring, maximum sustainable thoughput (MST)
- maintaining, maximum sustainable thoughput (MST)
- maximum sustainable throughput (MST), monitoring
- maximum sustainable throughput (MST), load patterns
- maximum sustainable throughput (MST), sustainable load test
- sustainable performance
ms.assetid: 99b99655-bc77-425c-a133-204781d7c430
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be96ad552abef66e2a401e334da1c27ee0e08cd5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="factors-that-affect-maximum-sustainable-performance"></a><span data-ttu-id="dab0b-102">影响最大可持续性能因素</span><span class="sxs-lookup"><span data-stu-id="dab0b-102">Factors that Affect Maximum Sustainable Performance</span></span>
<span data-ttu-id="dab0b-103">最大可承受吞吐量受一系列众多的因素（例如，可用服务器资源、解决方案中使用的功能类型、消息大小以及总体消息负载）直接影响。</span><span class="sxs-lookup"><span data-stu-id="dab0b-103">Maximum sustainable throughput is directly impacted by a wide range of factors such as available server resources, the type of features used in the solution, message size, and overall message load.</span></span> <span data-ttu-id="dab0b-104">还有其他因素需要考虑，尽管这些因素可能目前还不明显。</span><span class="sxs-lookup"><span data-stu-id="dab0b-104">There are other factors to be considered though that may not be immediately obvious.</span></span> <span data-ttu-id="dab0b-105">估计最大可持续性能时，还应考虑以下因素：</span><span class="sxs-lookup"><span data-stu-id="dab0b-105">The following factors should also be considered when estimating maximum sustainable performance:</span></span>  
  
## <a name="load-patterns"></a><span data-ttu-id="dab0b-106">负载模式</span><span class="sxs-lookup"><span data-stu-id="dab0b-106">Load Patterns</span></span>  
 <span data-ttu-id="dab0b-107">消息通常不会以可预测的一致速率传入生产 BizTalk Server 环境中。</span><span class="sxs-lookup"><span data-stu-id="dab0b-107">Messages do not typically flow into a production BizTalk Server environment at a predictable, consistent rate.</span></span> <span data-ttu-id="dab0b-108">更常见的情况是，业务要求 BizTalk Server 以展现出峰值和低谷的可变速率来处理消息。</span><span class="sxs-lookup"><span data-stu-id="dab0b-108">More typically, business needs dictate that BizTalk Server process messages at a variable rate which exhibits peaks and valleys.</span></span> <span data-ttu-id="dab0b-109">出现峰值时，BizTalk Server 的处理要求可能会从可忽略的情况迅速跳至消息接收速度超过其处理速度的过载情况。</span><span class="sxs-lookup"><span data-stu-id="dab0b-109">When peaks occur, the BizTalk Server processing requirements may quickly jump from negligible to an overdrive condition where messages are received faster than they are processed.</span></span> <span data-ttu-id="dab0b-110">在此方案中，已发布的消息将积压在 MessageBox 数据库中，直到 BizTalk 将这些积压的消息传递给相应的订户。</span><span class="sxs-lookup"><span data-stu-id="dab0b-110">In this scenario, published messages are backlogged in the MessageBox database until BizTalk delivers the backlogged messages to the appropriate subscribers.</span></span> <span data-ttu-id="dab0b-111">只要 BizTalk Server 能够处理在峰值负载周期之间累积的消息积压，则这样将不会出现问题。</span><span class="sxs-lookup"><span data-stu-id="dab0b-111">As long as BizTalk Server is able to process the backlog of messages accumulated between peak load periods then this is not problematic.</span></span>  
  
 <span data-ttu-id="dab0b-112">由于通常情况下消息以可变模式传入 BizTalk Server 环境中，因此应当在较长的时间段内运行测试方案，以确保该解决方案能够无限维持所需的吞吐量，从而可随时间的变化从所有峰值负载中恢复。</span><span class="sxs-lookup"><span data-stu-id="dab0b-112">Because of the typically variable pattern of message flow into a BizTalk Server environment, testing scenarios should be run for an extended period of time to ensure that the solution can sustain the desired throughput indefinitely, recovering from all peak loads over time.</span></span>  
  
## <a name="monitoring-and-maintenance-activities"></a><span data-ttu-id="dab0b-113">监视和维护活动</span><span class="sxs-lookup"><span data-stu-id="dab0b-113">Monitoring and Maintenance activities</span></span>  
 <span data-ttu-id="dab0b-114">在生产解决方案的生命期内，存在一个可以影响 BizTalk 性能的监视和维护活动主机，因此在所有测试方案中都应考虑到该主机。</span><span class="sxs-lookup"><span data-stu-id="dab0b-114">During the life of a production solution, there is a host of monitoring and maintenance activities that can impact BizTalk performance and so should be factored into any testing scenarios.</span></span> <span data-ttu-id="dab0b-115">这些活动包括：</span><span class="sxs-lookup"><span data-stu-id="dab0b-115">These activities include:</span></span>  
  
-   <span data-ttu-id="dab0b-116">**BizTalk 管理控制台查询**这些查询消耗资源，并会影响总体吞吐量根据的类型和查询的频率。</span><span class="sxs-lookup"><span data-stu-id="dab0b-116">**BizTalk Administration Console queries** These queries consume resources and affect overall throughput depending on the type and frequency of the query.</span></span>  
  
-   <span data-ttu-id="dab0b-117">**备份、 存档和清除活动**这些活动也消耗资源，应考虑任何测试的方案。</span><span class="sxs-lookup"><span data-stu-id="dab0b-117">**Backup, archiving, and purging activities** These activities also consume resources and should be factored into any testing scenarios.</span></span> <span data-ttu-id="dab0b-118">应当定期备份所有的 BizTalk Server 数据库并截断其事务日志。</span><span class="sxs-lookup"><span data-stu-id="dab0b-118">All BizTalk Server databases should be backed up periodically and their transaction logs truncated.</span></span> <span data-ttu-id="dab0b-119">如果不执行此操作，则事务日志可能会不受限制地增长，并占用该事务数据库的所有可用磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="dab0b-119">If this is not performed the transaction log may grow un-checked and consume all of the available disk space for the transaction database.</span></span> <span data-ttu-id="dab0b-120">如果正在使用跟踪，则必须定期清除跟踪数据库并将其存档（可选），以避免该数据库增长过大。</span><span class="sxs-lookup"><span data-stu-id="dab0b-120">If tracking is being used, the tracking database must periodically be purged and optionally archived to keep it from growing too large.</span></span> <span data-ttu-id="dab0b-121">有关维护 BizTalk Server 数据库的详细信息，请参阅[Backing Up and Restoring BizTalk Server Databases](../core/backing-up-and-restoring-biztalk-server-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="dab0b-121">For more information about maintaining BizTalk Server databases, please see [Backing Up and Restoring BizTalk Server Databases](../core/backing-up-and-restoring-biztalk-server-databases.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dab0b-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dab0b-122">See Also</span></span>  
 [<span data-ttu-id="dab0b-123">测量的最大可持续跟踪吞吐量</span><span class="sxs-lookup"><span data-stu-id="dab0b-123">Measuring Maximum Sustainable Tracking Throughput</span></span>](../core/measuring-maximum-sustainable-tracking-throughput.md)