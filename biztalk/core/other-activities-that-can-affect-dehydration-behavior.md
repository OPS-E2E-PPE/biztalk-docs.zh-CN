---
title: 可能会影响冻结行为的其他活动 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed940448-d3b1-4308-9b38-887904e03bd0
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb3fcbb2799cba8e808c2bd2da66c09706fe7a33
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393455"
---
# <a name="other-activities-that-can-affect-dehydration-behavior"></a><span data-ttu-id="8735c-102">其他可影响冻结行为的活动</span><span class="sxs-lookup"><span data-stu-id="8735c-102">Other Activities That Can Affect Dehydration Behavior</span></span>
<span data-ttu-id="8735c-103">以下活动直接或间接影响冻结行为和总体性能，因此应考虑到所有测试方案。</span><span class="sxs-lookup"><span data-stu-id="8735c-103">The following activities directly or indirectly impact dehydration and overall performance and so should be factored into any testing scenarios.</span></span>  
  
- <span data-ttu-id="8735c-104">**BizTalk Server 管理控制台查询。**</span><span class="sxs-lookup"><span data-stu-id="8735c-104">**BizTalk Server Administration Console queries.**</span></span> <span data-ttu-id="8735c-105">这些查询会消耗资源并影响总体吞吐量，具体取决于的类型和查询的频率。</span><span class="sxs-lookup"><span data-stu-id="8735c-105">These queries consume resources and affect overall throughput depending on the type and frequency of the query.</span></span>  
  
- <span data-ttu-id="8735c-106">**备份、 存档和清除活动。**</span><span class="sxs-lookup"><span data-stu-id="8735c-106">**Backup, archiving, and purging activities.**</span></span> <span data-ttu-id="8735c-107">这些活动也消耗资源，应考虑到所有测试方案。</span><span class="sxs-lookup"><span data-stu-id="8735c-107">These activities also consume resources and should be factored into any testing scenarios.</span></span>  
  
- <span data-ttu-id="8735c-108">**混合的 32 位和 64 位主机。**</span><span class="sxs-lookup"><span data-stu-id="8735c-108">**Mixed 32-bit and 64-bit hosts.**</span></span> <span data-ttu-id="8735c-109">下面是使用混合的 32 位和 64 位主机时要考虑一些事项：</span><span class="sxs-lookup"><span data-stu-id="8735c-109">Here are some things to consider when using mixed 32-bit and 64-bit hosts:</span></span>  
  
  - <span data-ttu-id="8735c-110">在高负荷下我们测量已使用的虚拟和物理内存，并与特定的阈值进行比较的。</span><span class="sxs-lookup"><span data-stu-id="8735c-110">Under stress we measure consumed virtual and physical memory and compare that against certain thresholds.</span></span> <span data-ttu-id="8735c-111">在 64 位系统中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]过程使用更多的内存，因此在冻结策略区别的 32 位使用相同的系统和相同的默认值。</span><span class="sxs-lookup"><span data-stu-id="8735c-111">In 64 bit systems the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] process uses more memory so there will be a difference in dehydration policy from 32-bits using the same system and the same default values.</span></span> <span data-ttu-id="8735c-112">请确保单独的业务流程、 接收、 发送和消息框主机。</span><span class="sxs-lookup"><span data-stu-id="8735c-112">Be sure to separate orchestration, receive, send and message box hosts.</span></span>  
  
     <span data-ttu-id="8735c-113">没有存在明显的差异对于 64 位系统，使用默认 32 位阈值时，只要只有业务流程主机是在 64 位计算机上。</span><span class="sxs-lookup"><span data-stu-id="8735c-113">There is not an obvious difference when using the default 32-bit thresholds for 64-bit systems, as long as only the orchestration host is on the 64 bit box.</span></span> <span data-ttu-id="8735c-114">但是，在压力的各种**MemoryThrottlingCriteria**设置应至少增加一倍或增加两倍 （只要有足够的内存），但方案进行调整，因为有许多最大化吞吐量派上用场的因素。</span><span class="sxs-lookup"><span data-stu-id="8735c-114">However, under stress the various **MemoryThrottlingCriteria** settings should be at least doubled or tripled (as long as you have enough memory), but the scenario should be tuned for maximizing throughput because there are many factors that come into play.</span></span> <span data-ttu-id="8735c-115">应调整各个冻结阈值，若要查找什么是它们的最佳的压力下。</span><span class="sxs-lookup"><span data-stu-id="8735c-115">You should tune the dehydration thresholds under stress to find what is optimal for them.</span></span>  
  
  - <span data-ttu-id="8735c-116">冻结行为依赖于每个订阅; 的传送时间历史记录对于不同的订阅因此请这考虑在优化冻结属性值，则历史记录可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="8735c-116">Dehydration behavior depends on delivery time history of every subscription; the histories could be different for different subscriptions so consider this in tuning your dehydration property values.</span></span>  
  
  - <span data-ttu-id="8735c-117">当业务流程主机服务回收在一台主机上但不是在另一台，则历史记录将不同。</span><span class="sxs-lookup"><span data-stu-id="8735c-117">When the orchestration host service is recycled on one host, but not on another, the histories will be different.</span></span>  
  
  - <span data-ttu-id="8735c-118">当服务器使用不同版本的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，将两者之间的冻结策略区别。</span><span class="sxs-lookup"><span data-stu-id="8735c-118">When servers are using different versions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], there will be a difference in dehydration policy between the two.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8735c-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="8735c-119">See Also</span></span>  
 [<span data-ttu-id="8735c-120">BTSNTSvc.exe.config 文件</span><span class="sxs-lookup"><span data-stu-id="8735c-120">BTSNTSvc.exe.config File</span></span>](../core/btsntsvc-exe-config-file.md)