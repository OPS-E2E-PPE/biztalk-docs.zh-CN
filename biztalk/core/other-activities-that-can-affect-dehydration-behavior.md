---
title: 其他活动可以影响冻结行为 |Microsoft 文档
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
ms.openlocfilehash: 4622c77876607664b210de2581929154973b45d2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264037"
---
# <a name="other-activities-that-can-affect-dehydration-behavior"></a><span data-ttu-id="59a9f-102">其他活动可以影响冻结行为</span><span class="sxs-lookup"><span data-stu-id="59a9f-102">Other Activities That Can Affect Dehydration Behavior</span></span>
<span data-ttu-id="59a9f-103">以下活动直接或间接影响冻结行为和总体性能，因此在所有的测试方案中都应考虑这些活动。</span><span class="sxs-lookup"><span data-stu-id="59a9f-103">The following activities directly or indirectly impact dehydration and overall performance and so should be factored into any testing scenarios.</span></span>  
  
-   <span data-ttu-id="59a9f-104">**BizTalk Server 管理控制台的查询。**</span><span class="sxs-lookup"><span data-stu-id="59a9f-104">**BizTalk Server Administration Console queries.**</span></span> <span data-ttu-id="59a9f-105">这些查询会消耗资源并影响总体吞吐量，具体取决于查询的类型和频率。</span><span class="sxs-lookup"><span data-stu-id="59a9f-105">These queries consume resources and affect overall throughput depending on the type and frequency of the query.</span></span>  
  
-   <span data-ttu-id="59a9f-106">**备份、 存档和清除活动。**</span><span class="sxs-lookup"><span data-stu-id="59a9f-106">**Backup, archiving, and purging activities.**</span></span> <span data-ttu-id="59a9f-107">这些活动也会消耗资源，在所有测试方案中都应考虑到这些活动。</span><span class="sxs-lookup"><span data-stu-id="59a9f-107">These activities also consume resources and should be factored into any testing scenarios.</span></span>  
  
-   <span data-ttu-id="59a9f-108">**混合的 32 位和 64 位主机。**</span><span class="sxs-lookup"><span data-stu-id="59a9f-108">**Mixed 32-bit and 64-bit hosts.**</span></span> <span data-ttu-id="59a9f-109">混合使用 32 位和 64 位主机时应注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="59a9f-109">Here are some things to consider when using mixed 32-bit and 64-bit hosts:</span></span>  
  
    -   <span data-ttu-id="59a9f-110">在任务繁忙的情况下，应测量所消耗的虚拟内存和物理内存，并将其与特定的阈值进行比较。</span><span class="sxs-lookup"><span data-stu-id="59a9f-110">Under stress we measure consumed virtual and physical memory and compare that against certain thresholds.</span></span> <span data-ttu-id="59a9f-111">在 64 位系统中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]过程使用更多内存，因此将从 32 位使用相同的系统和相同的默认值在冻结策略不同。</span><span class="sxs-lookup"><span data-stu-id="59a9f-111">In 64 bit systems the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] process uses more memory so there will be a difference in dehydration policy from 32-bits using the same system and the same default values.</span></span> <span data-ttu-id="59a9f-112">请确保将业务流程、接收主机、发送主机和消息框主机分离开。</span><span class="sxs-lookup"><span data-stu-id="59a9f-112">Be sure to separate orchestration, receive, send and message box hosts.</span></span>  
  
         <span data-ttu-id="59a9f-113">只要 64 位系统上只有业务流程主机，则对 64 位系统使用默认的 32 位阈值时不会存在明显的差异。</span><span class="sxs-lookup"><span data-stu-id="59a9f-113">There is not an obvious difference when using the default 32-bit thresholds for 64-bit systems, as long as only the orchestration host is on the 64 bit box.</span></span> <span data-ttu-id="59a9f-114">但是，在压力各种**MemoryThrottlingCriteria**设置应至少增加了一倍或也增加三倍 （只要有足够的内存），但应针对最大化吞吐量，因为有许多优化方案派上用场的因素。</span><span class="sxs-lookup"><span data-stu-id="59a9f-114">However, under stress the various **MemoryThrottlingCriteria** settings should be at least doubled or tripled (as long as you have enough memory), but the scenario should be tuned for maximizing throughput because there are many factors that come into play.</span></span> <span data-ttu-id="59a9f-115">应在任务繁忙时调整各个冻结阈值以找出它们的最佳值。</span><span class="sxs-lookup"><span data-stu-id="59a9f-115">You should tune the dehydration thresholds under stress to find what is optimal for them.</span></span>  
  
    -   <span data-ttu-id="59a9f-116">冻结行为依赖于每个订阅的传送时间历史记录；订阅不同其历史记录可能也会不同，因此在调整冻结属性值时应考虑到这一点。</span><span class="sxs-lookup"><span data-stu-id="59a9f-116">Dehydration behavior depends on delivery time history of every subscription; the histories could be different for different subscriptions so consider this in tuning your dehydration property values.</span></span>  
  
    -   <span data-ttu-id="59a9f-117">如果回收了一台主机上的业务流程主机服务，而没有回收另一台主机上的业务流程主机服务，则历史记录将不同。</span><span class="sxs-lookup"><span data-stu-id="59a9f-117">When the orchestration host service is recycled on one host, but not on another, the histories will be different.</span></span>  
  
    -   <span data-ttu-id="59a9f-118">当服务器使用不同版本的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 时，这两个版本之间的冻结策略将存在差别。</span><span class="sxs-lookup"><span data-stu-id="59a9f-118">When servers are using different versions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], there will be a difference in dehydration policy between the two.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59a9f-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="59a9f-119">See Also</span></span>  
 [<span data-ttu-id="59a9f-120">BTSNTSvc.exe.config 文件</span><span class="sxs-lookup"><span data-stu-id="59a9f-120">BTSNTSvc.exe.config File</span></span>](../core/btsntsvc-exe-config-file.md)