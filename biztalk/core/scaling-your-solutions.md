---
title: "缩放您的解决方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- performance, scaling
- scaling, scaling out
- scaling, performance
- scaling, about scaling
- scaling, scaling up
- scaling
ms.assetid: e2acbaa4-29d3-4c89-ac1f-c0641cfa0442
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5417e303ea8486ef5bdee8e57c66d4783fb197ed
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="scaling-your-solutions"></a><span data-ttu-id="4a19d-102">缩放您的解决方案</span><span class="sxs-lookup"><span data-stu-id="4a19d-102">Scaling Your Solutions</span></span>
<span data-ttu-id="4a19d-103">BizTalk Server 结构为可伸缩性提供了非常好的支持。</span><span class="sxs-lookup"><span data-stu-id="4a19d-103">BizTalk Server architecture provides a very good support for scalability.</span></span> <span data-ttu-id="4a19d-104">您选择的扩展模式取决于方案的复杂性、硬件和吞吐量/延迟要求。</span><span class="sxs-lookup"><span data-stu-id="4a19d-104">The scaling patterns that you choose depend on complexity of your scenario, hardware and the throughput/Latency requirements.</span></span> <span data-ttu-id="4a19d-105">最初应从较小的拓扑开始，然后尝试按照本部分中的指导进行向上或向下扩展。</span><span class="sxs-lookup"><span data-stu-id="4a19d-105">You should start with a smaller topology initially and try to scale-up or down based on the guidelines in this section.</span></span>  
  
## <a name="scaling-out-and-scaling-up"></a><span data-ttu-id="4a19d-106">向外扩展和向上扩展</span><span class="sxs-lookup"><span data-stu-id="4a19d-106">Scaling Out and Scaling Up</span></span>  
 <span data-ttu-id="4a19d-107">可以通过以下两种方式来扩展 BizTalk Server 系统：</span><span class="sxs-lookup"><span data-stu-id="4a19d-107">There are two ways to scale your BizTalk Server system:</span></span>  
  
-   <span data-ttu-id="4a19d-108">向外扩展是添加其他计算机的过程。</span><span class="sxs-lookup"><span data-stu-id="4a19d-108">Scaling-out is the process of adding additional computers.</span></span> <span data-ttu-id="4a19d-109">例如，如果 BizTalk Server 由于 CPU 资源出现瓶颈，则添加另一个服务器可以提供双倍的 CPU 资源，从而可以提供双倍的吞吐量。</span><span class="sxs-lookup"><span data-stu-id="4a19d-109">For example, if BizTalk Server is bottlenecked by CPU resources, adding another server provides double the CPU resources which may provide double the throughput.</span></span>  
  
-   <span data-ttu-id="4a19d-110">向上扩展是升级现有计算机的过程。</span><span class="sxs-lookup"><span data-stu-id="4a19d-110">Scaling-up is process of upgrading the existing computer.</span></span> <span data-ttu-id="4a19d-111">例如，可以将 BizTalk Server 计算机从 4 处理器计算机升级到 8 处理器。</span><span class="sxs-lookup"><span data-stu-id="4a19d-111">For example, you can upgrade a BizTalk Server computer from a 4 processor machine to an 8 processor.</span></span>  
  
 <span data-ttu-id="4a19d-112">BizTalk Server 系统有两层：BizTalk Server 层和 SQL Server 层，后者包含 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="4a19d-112">A BizTalk Server system has two tiers: the BizTalk Server tier and the SQL Server tier, which contains your MessageBox databases.</span></span> <span data-ttu-id="4a19d-113">在任何方案中，都可以向外扩展或向上扩展每一层。</span><span class="sxs-lookup"><span data-stu-id="4a19d-113">In any scenario, you can scale out or scale up each tier.</span></span> <span data-ttu-id="4a19d-114">也就是说，可以向外扩展 BizTalk Server 和 MessageBox 数据库，也可以对它们进行向上扩展。</span><span class="sxs-lookup"><span data-stu-id="4a19d-114">That is, you can scale-out BizTalk Server and the MessageBox database, or scale up both of them.</span></span>  
  
 <span data-ttu-id="4a19d-115">在大多数情况下，BizTalk 层会首先成为瓶颈，因此通过对其进行向外扩展来开始提高性能。但是，某些情况下（具体取决于系统复杂性和所使用的硬件），无法继续向外扩展 BizTalk 层，SQL Server 层则成为瓶颈。</span><span class="sxs-lookup"><span data-stu-id="4a19d-115">In most cases, the BizTalk tier becomes a bottleneck first, and you start improving performance by scaling it out. But, at some point, depending on complexity of your system and the hardware you use, you can’t scale out the BizTalk tier anymore and the SQL Server tier becomes the bottleneck.</span></span> <span data-ttu-id="4a19d-116">那么，需要向上扩展 SQL Server 层，然后通过添加更多 MessageBox 数据库对其进行向外扩展。</span><span class="sxs-lookup"><span data-stu-id="4a19d-116">Then, you scale up the SQL Server tier, and next scale it out by adding more MessageBox databases.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4a19d-117">此处，新的 MessageBox 数据库并不一定意味着另一台服务器。</span><span class="sxs-lookup"><span data-stu-id="4a19d-117">A new MessageBox database does not necessarily mean another server here.</span></span> <span data-ttu-id="4a19d-118">单个 SQL Server 可以具有多个 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="4a19d-118">A single SQL server can have multiple MessageBox databases.</span></span> <span data-ttu-id="4a19d-119">另外，如果数据库位于不同的计算机上，则多个 MessageBox 数据库会导致 DTC 开销和网络跃点。</span><span class="sxs-lookup"><span data-stu-id="4a19d-119">Also, multiple MessageBox databases incur DTC cost and network hop if the databases are on different computers.</span></span>  
  
 <span data-ttu-id="4a19d-120">理论上，只要主 MessageBox 数据库未达饱和，SQL Server 层就可以无限向外扩展。</span><span class="sxs-lookup"><span data-stu-id="4a19d-120">In theory, the SQL Server tier can scale out indefinitely as long as the master MessageBox database is not saturated.</span></span>  
  
 <span data-ttu-id="4a19d-121">本部分中的主题更详细地介绍了这些扩展模式。</span><span class="sxs-lookup"><span data-stu-id="4a19d-121">The topics in this section describe these scaling patterns in more detail.</span></span> <span data-ttu-id="4a19d-122">还介绍了如何扩展每个模式，以及如何确定可以不再使用该模式来扩展系统的时间。</span><span class="sxs-lookup"><span data-stu-id="4a19d-122">They also explain how to scale each pattern and how to determine when you can no longer use that pattern to scale your system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4a19d-123">本节内容</span><span class="sxs-lookup"><span data-stu-id="4a19d-123">In This Section</span></span>  
  
-   [<span data-ttu-id="4a19d-124">可伸缩性是什么？</span><span class="sxs-lookup"><span data-stu-id="4a19d-124">What Is Scalability?</span></span>](../core/what-is-scalability.md)  
  
-   [<span data-ttu-id="4a19d-125">BizTalk Server 层向外缩放</span><span class="sxs-lookup"><span data-stu-id="4a19d-125">Scaling Out the BizTalk Server Tier</span></span>](../core/scaling-out-the-biztalk-server-tier.md)  
  
-   [<span data-ttu-id="4a19d-126">BizTalk Server 层向上扩展</span><span class="sxs-lookup"><span data-stu-id="4a19d-126">Scaling Up the BizTalk Server Tier</span></span>](../core/scaling-up-the-biztalk-server-tier.md)  
  
-   [<span data-ttu-id="4a19d-127">SQL Server 层向外缩放</span><span class="sxs-lookup"><span data-stu-id="4a19d-127">Scaling Out the SQL Server Tier</span></span>](../core/scaling-out-the-sql-server-tier.md)  
  
-   [<span data-ttu-id="4a19d-128">SQL Server 层向上扩展</span><span class="sxs-lookup"><span data-stu-id="4a19d-128">Scaling Up the SQL Server Tier</span></span>](../core/scaling-up-the-sql-server-tier.md)  
  
## <a name="see-also"></a><span data-ttu-id="4a19d-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4a19d-129">See Also</span></span>  
 <span data-ttu-id="4a19d-130">[向外扩展接收主机](../core/scaled-out-receiving-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="4a19d-130">[Scaled-Out Receiving Hosts](../core/scaled-out-receiving-hosts.md) </span></span>  
 <span data-ttu-id="4a19d-131">[向外扩展的处理主机](../core/scaled-out-processing-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="4a19d-131">[Scaled-Out Processing Hosts](../core/scaled-out-processing-hosts.md) </span></span>  
 <span data-ttu-id="4a19d-132">[向外扩展的发送主机](../core/scaled-out-sending-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="4a19d-132">[Scaled-Out Sending Hosts](../core/scaled-out-sending-hosts.md) </span></span>  
 <span data-ttu-id="4a19d-133">[Windows Server 群集用于 BizTalk Server Hosts2 为提供高可用性](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="4a19d-133">[Using Windows Server Cluster to Provide High Availability for BizTalk Server Hosts2](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span></span>  
 <span data-ttu-id="4a19d-134">[向外扩展的数据库](../core/scaled-out-databases.md) </span><span class="sxs-lookup"><span data-stu-id="4a19d-134">[Scaled-Out Databases](../core/scaled-out-databases.md) </span></span>  
 [<span data-ttu-id="4a19d-135">群集的 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="4a19d-135">Clustering the BizTalk Server Databases</span></span>](../core/clustering-the-biztalk-server-databases1.md)