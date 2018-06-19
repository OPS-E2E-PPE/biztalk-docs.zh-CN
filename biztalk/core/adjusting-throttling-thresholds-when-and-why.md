---
title: 调整限制阈值： 何时和为何 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9afb26c8-e5f4-4b78-9a45-a1263e3cb6ab
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b49ae78d4b2d0cf2dabfc69af9023b1e8676dea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22229925"
---
# <a name="adjusting-throttling-thresholds-when-and-why"></a><span data-ttu-id="3421d-102">调整限制阈值： 何时和为何</span><span class="sxs-lookup"><span data-stu-id="3421d-102">Adjusting Throttling Thresholds: When and Why</span></span>
<span data-ttu-id="3421d-103">对于阻止操作而言，一个大小根本不够。</span><span class="sxs-lookup"><span data-stu-id="3421d-103">When it comes to throttling, one size does not fit all.</span></span> <span data-ttu-id="3421d-104">将由一系列因素确定应采用的最佳设置。</span><span class="sxs-lookup"><span data-stu-id="3421d-104">There are a range of factors that will determine what the optimal settings should be.</span></span> <span data-ttu-id="3421d-105">BizTalk Server 本身提供了默认值，这些默认值经测试证明可有效地防止系统发生积压过多等现象。</span><span class="sxs-lookup"><span data-stu-id="3421d-105">Out of the box, BizTalk Server provides default values that have been proven through testing to effectively protect a system from things like backlog overages.</span></span> <span data-ttu-id="3421d-106">然而，在某些情况下，这些默认值可能过于严格。</span><span class="sxs-lookup"><span data-stu-id="3421d-106">However, for some scenarios, this may be too aggressive.</span></span> <span data-ttu-id="3421d-107">下面的示例阐释了这一点。</span><span class="sxs-lookup"><span data-stu-id="3421d-107">The following examples illustrate this point.</span></span>  
  
## <a name="example-1-peak-loads-and-database-size"></a><span data-ttu-id="3421d-108">示例 1： 高峰负载和数据库大小</span><span class="sxs-lookup"><span data-stu-id="3421d-108">Example 1: Peak Loads and Database Size</span></span>  
 <span data-ttu-id="3421d-109">在 BizTalk Server 上构建的每个解决方案都有最大可承受吞吐量 (MST)。</span><span class="sxs-lookup"><span data-stu-id="3421d-109">Each solution built on BizTalk Server has a maximum sustainable throughput (MST).</span></span> <span data-ttu-id="3421d-110">根据定义，只要负载低于此级别，系统就能够无限制地承受该负载。</span><span class="sxs-lookup"><span data-stu-id="3421d-110">As long as load stays below this level, the system can sustain that load indefinitely, by definition.</span></span> <span data-ttu-id="3421d-111">在实践中，但是，它是更常见的是具有高峰和低谷中的负载配置文件与具有恒定的负载，不会随时间而有所不同。</span><span class="sxs-lookup"><span data-stu-id="3421d-111">In practice, however, it is more common to have peaks and valleys in the load profile than it is to have a steady load that doesn’t vary over time.</span></span>  
  
 <span data-ttu-id="3421d-112">从经济角度而言，与其构建一个可无限制地承受最高峰值负载的数据库，还不如构建一个适当的系统，此系统在峰值负载下可以处理一些积压，但在低谷期可以恢复正常。</span><span class="sxs-lookup"><span data-stu-id="3421d-112">Rather than build a system that is capable of sustaining the highest peak loads indefinitely, it is more cost effective to build a system that can handle some backlog under peak load, and recover during the valleys.</span></span> <span data-ttu-id="3421d-113">然而，如果峰值负载期间预计的积压高于数据库大小的默认阻止值，则系统将通过阻止输入来阻止积压。</span><span class="sxs-lookup"><span data-stu-id="3421d-113">However, if the backlog expected during the peak loads is higher than the default throttling value for database size, then the system will block the backlog by throttling the input.</span></span> <span data-ttu-id="3421d-114">如果这一点不可行（例如，您需要尽快使用所有输入文件），此解决方案将提高数据库大小阈值，以便在阻止之前接受预计的积压。</span><span class="sxs-lookup"><span data-stu-id="3421d-114">If this is not desirable, for example, because you need all of the input files to be consumed as quickly as possible, then the solution is to raise the database size threshold to accept the expected backlog before throttling.</span></span>  
  
## <a name="example-2-memory-usage-optimization"></a><span data-ttu-id="3421d-115">示例 2： 内存使用情况的优化</span><span class="sxs-lookup"><span data-stu-id="3421d-115">Example 2: Memory Usage Optimization</span></span>  
 <span data-ttu-id="3421d-116">阻止过程用来衡量处理速度的另一个资源是主机进程可以使用多少内存。</span><span class="sxs-lookup"><span data-stu-id="3421d-116">Another resource that throttling uses in order to gauge processing speed is how much memory is available to host processes.</span></span> <span data-ttu-id="3421d-117">如果与阈值相比，可用内存过小，则阻止过程将减少引擎从要处理的主机队列中检索的消息数。</span><span class="sxs-lookup"><span data-stu-id="3421d-117">If the available memory gets too small compared to the threshold, throttling will slow down the number of messages the engine retrieves from the host queues to be worked on.</span></span> <span data-ttu-id="3421d-118">鉴于现今的企业级服务器能够容纳大量内存并且内存不难获得（尤其是由于在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中提供了 64 位支持），因此有充分的理由需要提高和降低阈值，以优化内存使用率。</span><span class="sxs-lookup"><span data-stu-id="3421d-118">Given the variability in the amount and availability of memory on today’s enterprise class servers, especially with x64 support in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], the threshold may very well need to be raised or lowered to optimize memory usage.</span></span>  
  
## <a name="recommendation"></a><span data-ttu-id="3421d-119">建议</span><span class="sxs-lookup"><span data-stu-id="3421d-119">Recommendation</span></span>  
 <span data-ttu-id="3421d-120">默认情况下，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中的阻止行为被配置为随时向系统提供良好的保护。</span><span class="sxs-lookup"><span data-stu-id="3421d-120">Throttling in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is configured by default to provide good protection for the system out of the box.</span></span> <span data-ttu-id="3421d-121">然而，不应将默认设置当作最佳配置。</span><span class="sxs-lookup"><span data-stu-id="3421d-121">The default settings should not, however, be taken for granted as optimal.</span></span> <span data-ttu-id="3421d-122">应监视性能计数器以了解阻止状态，从而确定是否发生了阻止行为，接着自行衡量阻止行为所依据的资源（例如，数据库大小或内存使用率）是处于欠利用状态还是处于过利用状态，然后相应地调整阻止阈值的大小。</span><span class="sxs-lookup"><span data-stu-id="3421d-122">Monitor the performance counters for throttling states to see if throttling is taking place, then gauge for yourself if the resource on which throttling is based (for example, database size or memory usage) is under or over utilized, then adjust the throttling thresholds up or down accordingly.</span></span>