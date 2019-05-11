---
title: 调整限制阈值：何时以及为何 |Microsoft Docs
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
ms.openlocfilehash: 3fa8ad1a9c8c9c94bc41bc4ca33b3fb8763d2b69
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65360112"
---
# <a name="adjusting-throttling-thresholds-when-and-why"></a><span data-ttu-id="23c2f-102">调整限制阈值：时间和原因</span><span class="sxs-lookup"><span data-stu-id="23c2f-102">Adjusting Throttling Thresholds: When and Why</span></span>
<span data-ttu-id="23c2f-103">谈到限制，一个大小根本不够。</span><span class="sxs-lookup"><span data-stu-id="23c2f-103">When it comes to throttling, one size does not fit all.</span></span> <span data-ttu-id="23c2f-104">有一系列因素，以确定最佳设置应该是什么。</span><span class="sxs-lookup"><span data-stu-id="23c2f-104">There are a range of factors that will determine what the optimal settings should be.</span></span> <span data-ttu-id="23c2f-105">默认情况下，BizTalk Server 提供的默认值，已通过测试，来有效保护系统的情况下被证实喜欢积压工作超额部分。</span><span class="sxs-lookup"><span data-stu-id="23c2f-105">Out of the box, BizTalk Server provides default values that have been proven through testing to effectively protect a system from things like backlog overages.</span></span> <span data-ttu-id="23c2f-106">但是，对于某些情况下，这可能过高。</span><span class="sxs-lookup"><span data-stu-id="23c2f-106">However, for some scenarios, this may be too aggressive.</span></span> <span data-ttu-id="23c2f-107">以下示例说明了这一点。</span><span class="sxs-lookup"><span data-stu-id="23c2f-107">The following examples illustrate this point.</span></span>  
  
## <a name="example-1-peak-loads-and-database-size"></a><span data-ttu-id="23c2f-108">示例 1：高峰负载和数据库大小</span><span class="sxs-lookup"><span data-stu-id="23c2f-108">Example 1: Peak Loads and Database Size</span></span>  
 <span data-ttu-id="23c2f-109">BizTalk Server 上构建每个解决方案都有最大可承受吞吐量 (MST)。</span><span class="sxs-lookup"><span data-stu-id="23c2f-109">Each solution built on BizTalk Server has a maximum sustainable throughput (MST).</span></span> <span data-ttu-id="23c2f-110">只要负载低于此级别，系统可以承受该负载无限期地，通过定义。</span><span class="sxs-lookup"><span data-stu-id="23c2f-110">As long as load stays below this level, the system can sustain that load indefinitely, by definition.</span></span> <span data-ttu-id="23c2f-111">在实践中，但是，它是更常见的是与具有恒定的负载不会随着时间的推移而变化的相比有高峰和低谷负载配置文件中。</span><span class="sxs-lookup"><span data-stu-id="23c2f-111">In practice, however, it is more common to have peaks and valleys in the load profile than it is to have a steady load that doesn’t vary over time.</span></span>  
  
 <span data-ttu-id="23c2f-112">而不是生成一个系统能够承受的最高的峰值，无限期地加载，它是更具成本效益构建系统可以处理在峰值负载时，一些积压工作和低谷期间恢复。</span><span class="sxs-lookup"><span data-stu-id="23c2f-112">Rather than build a system that is capable of sustaining the highest peak loads indefinitely, it is more cost effective to build a system that can handle some backlog under peak load, and recover during the valleys.</span></span> <span data-ttu-id="23c2f-113">但是，如果加载峰值期间预计的积压高于默认限制数据库大小值然后系统将通过阻止输入来阻止积压工作。</span><span class="sxs-lookup"><span data-stu-id="23c2f-113">However, if the backlog expected during the peak loads is higher than the default throttling value for database size, then the system will block the backlog by throttling the input.</span></span> <span data-ttu-id="23c2f-114">如果不需要这样做，例如，因为您需要的所有输入文件被作为快速，然后解决方案是提高数据库大小阈值，若要阻止之前接受预计的积压。</span><span class="sxs-lookup"><span data-stu-id="23c2f-114">If this is not desirable, for example, because you need all of the input files to be consumed as quickly as possible, then the solution is to raise the database size threshold to accept the expected backlog before throttling.</span></span>  
  
## <a name="example-2-memory-usage-optimization"></a><span data-ttu-id="23c2f-115">示例 2：内存使用情况的优化</span><span class="sxs-lookup"><span data-stu-id="23c2f-115">Example 2: Memory Usage Optimization</span></span>  
 <span data-ttu-id="23c2f-116">限制使用来衡量处理速度的另一个资源是内存量是可用于的主机进程。</span><span class="sxs-lookup"><span data-stu-id="23c2f-116">Another resource that throttling uses in order to gauge processing speed is how much memory is available to host processes.</span></span> <span data-ttu-id="23c2f-117">如果与阈值相比，可用内存获取太小，限制将会减慢引擎检索从主机队列要处理的消息数。</span><span class="sxs-lookup"><span data-stu-id="23c2f-117">If the available memory gets too small compared to the threshold, throttling will slow down the number of messages the engine retrieves from the host queues to be worked on.</span></span> <span data-ttu-id="23c2f-118">给定的量和可用性如今的企业级服务器上的内存中的可变性，尤其是在使用 x64 支持在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，阈值很可能需要以引发或降低以优化内存使用情况。</span><span class="sxs-lookup"><span data-stu-id="23c2f-118">Given the variability in the amount and availability of memory on today’s enterprise class servers, especially with x64 support in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], the threshold may very well need to be raised or lowered to optimize memory usage.</span></span>  
  
## <a name="recommendation"></a><span data-ttu-id="23c2f-119">建议</span><span class="sxs-lookup"><span data-stu-id="23c2f-119">Recommendation</span></span>  
 <span data-ttu-id="23c2f-120">中的阻止行为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]默认提供良好的保护现成的系统配置。</span><span class="sxs-lookup"><span data-stu-id="23c2f-120">Throttling in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is configured by default to provide good protection for the system out of the box.</span></span> <span data-ttu-id="23c2f-121">默认设置应不是，但是，想当然当作最佳配置。</span><span class="sxs-lookup"><span data-stu-id="23c2f-121">The default settings should not, however, be taken for granted as optimal.</span></span> <span data-ttu-id="23c2f-122">监视性能计数器限制状态，以查看是否限制的位置，然后自行衡量阻止行为的资源为基础 （例如，数据库大小或内存使用率） 的利用情况下或通过，然后调整限制阈值相应地增减。</span><span class="sxs-lookup"><span data-stu-id="23c2f-122">Monitor the performance counters for throttling states to see if throttling is taking place, then gauge for yourself if the resource on which throttling is based (for example, database size or memory usage) is under or over utilized, then adjust the throttling thresholds up or down accordingly.</span></span>