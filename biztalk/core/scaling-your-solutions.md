---
title: 缩放你的解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance, scaling
- scaling, scaling out
- scaling, performance
- scaling, about scaling
- scaling, scaling up
- scaling
ms.assetid: e2acbaa4-29d3-4c89-ac1f-c0641cfa0442
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 068bea9427ad82621307b0db41714aa2f9db49d8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308689"
---
# <a name="scaling-your-solutions"></a><span data-ttu-id="2a617-102">缩放你的解决方案</span><span class="sxs-lookup"><span data-stu-id="2a617-102">Scaling Your Solutions</span></span>
<span data-ttu-id="2a617-103">BizTalk Server 体系结构提供可扩展性很好的支持。</span><span class="sxs-lookup"><span data-stu-id="2a617-103">BizTalk Server architecture provides a very good support for scalability.</span></span> <span data-ttu-id="2a617-104">你选择的缩放模式取决于你的方案、 硬件和吞吐量/延迟要求的复杂性。</span><span class="sxs-lookup"><span data-stu-id="2a617-104">The scaling patterns that you choose depend on complexity of your scenario, hardware and the throughput/Latency requirements.</span></span> <span data-ttu-id="2a617-105">您应启动较小的拓扑最初并尝试纵向扩展或向下本部分中的准则。</span><span class="sxs-lookup"><span data-stu-id="2a617-105">You should start with a smaller topology initially and try to scale-up or down based on the guidelines in this section.</span></span>  
  
## <a name="scaling-out-and-scaling-up"></a><span data-ttu-id="2a617-106">向外扩展和向上扩展</span><span class="sxs-lookup"><span data-stu-id="2a617-106">Scaling Out and Scaling Up</span></span>  
 <span data-ttu-id="2a617-107">有两种方法来扩展 BizTalk Server 系统：</span><span class="sxs-lookup"><span data-stu-id="2a617-107">There are two ways to scale your BizTalk Server system:</span></span>  
  
- <span data-ttu-id="2a617-108">向外扩展是添加其他计算机的过程。</span><span class="sxs-lookup"><span data-stu-id="2a617-108">Scaling-out is the process of adding additional computers.</span></span> <span data-ttu-id="2a617-109">例如，如果 BizTalk Server 通过 CPU 资源出现瓶颈，添加另一台服务器提供双倍的 CPU 资源，从而可以提供双倍的吞吐量。</span><span class="sxs-lookup"><span data-stu-id="2a617-109">For example, if BizTalk Server is bottlenecked by CPU resources, adding another server provides double the CPU resources which may provide double the throughput.</span></span>  
  
- <span data-ttu-id="2a617-110">向上扩展是升级现有计算机的过程。</span><span class="sxs-lookup"><span data-stu-id="2a617-110">Scaling-up is process of upgrading the existing computer.</span></span> <span data-ttu-id="2a617-111">例如，可以在 BizTalk Server 计算机从 4 处理器计算机升级到 8 处理器。</span><span class="sxs-lookup"><span data-stu-id="2a617-111">For example, you can upgrade a BizTalk Server computer from a 4 processor machine to an 8 processor.</span></span>  
  
  <span data-ttu-id="2a617-112">BizTalk Server 系统有两个层： BizTalk Server 层和 SQL Server 层，其中包含您的 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="2a617-112">A BizTalk Server system has two tiers: the BizTalk Server tier and the SQL Server tier, which contains your MessageBox databases.</span></span> <span data-ttu-id="2a617-113">在任何方案中，可以向外扩展或纵向扩展每个层。</span><span class="sxs-lookup"><span data-stu-id="2a617-113">In any scenario, you can scale out or scale up each tier.</span></span> <span data-ttu-id="2a617-114">也就是说，可以横向扩展 BizTalk Server 和 MessageBox 数据库中，也可以纵向扩展这两个值。</span><span class="sxs-lookup"><span data-stu-id="2a617-114">That is, you can scale-out BizTalk Server and the MessageBox database, or scale up both of them.</span></span>  
  
  <span data-ttu-id="2a617-115">在大多数情况下，BizTalk 层则成为瓶颈第一次，并开始通过进行扩展来提高性能。但是，在某些时候，具体取决于您的系统以及所使用的硬件的复杂程度，您不能向外扩展 BizTalk 层不再而且 SQL Server 层则成为瓶颈。</span><span class="sxs-lookup"><span data-stu-id="2a617-115">In most cases, the BizTalk tier becomes a bottleneck first, and you start improving performance by scaling it out. But, at some point, depending on complexity of your system and the hardware you use, you can’t scale out the BizTalk tier anymore and the SQL Server tier becomes the bottleneck.</span></span> <span data-ttu-id="2a617-116">然后，纵向扩展 SQL Server 层，并对其进行横向扩展通过添加多个 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="2a617-116">Then, you scale up the SQL Server tier, and next scale it out by adding more MessageBox databases.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2a617-117">新的 MessageBox 数据库并不一定意味着此处另一台服务器。</span><span class="sxs-lookup"><span data-stu-id="2a617-117">A new MessageBox database does not necessarily mean another server here.</span></span> <span data-ttu-id="2a617-118">单个 SQL server 可以有多个 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="2a617-118">A single SQL server can have multiple MessageBox databases.</span></span> <span data-ttu-id="2a617-119">此外，多个 MessageBox 数据库会导致 DTC 开销和网络跃点如果数据库位于不同的计算机上。</span><span class="sxs-lookup"><span data-stu-id="2a617-119">Also, multiple MessageBox databases incur DTC cost and network hop if the databases are on different computers.</span></span>  
  
 <span data-ttu-id="2a617-120">从理论上讲，SQL Server 层可以无限向外扩展，只要主 MessageBox 数据库未达饱和。</span><span class="sxs-lookup"><span data-stu-id="2a617-120">In theory, the SQL Server tier can scale out indefinitely as long as the master MessageBox database is not saturated.</span></span>  
  
 <span data-ttu-id="2a617-121">在本部分中的主题介绍这些扩展模式更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="2a617-121">The topics in this section describe these scaling patterns in more detail.</span></span> <span data-ttu-id="2a617-122">此外介绍了如何扩展每个模式以及如何确定何时不再可以使用该模式来扩展系统。</span><span class="sxs-lookup"><span data-stu-id="2a617-122">They also explain how to scale each pattern and how to determine when you can no longer use that pattern to scale your system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2a617-123">本节内容</span><span class="sxs-lookup"><span data-stu-id="2a617-123">In This Section</span></span>  
  
-   [<span data-ttu-id="2a617-124">可伸缩性概述</span><span class="sxs-lookup"><span data-stu-id="2a617-124">What Is Scalability?</span></span>](../core/what-is-scalability.md)  
  
-   [<span data-ttu-id="2a617-125">向外扩展 BizTalk Server 层</span><span class="sxs-lookup"><span data-stu-id="2a617-125">Scaling Out the BizTalk Server Tier</span></span>](../core/scaling-out-the-biztalk-server-tier.md)  
  
-   [<span data-ttu-id="2a617-126">纵向扩展 BizTalk Server 层</span><span class="sxs-lookup"><span data-stu-id="2a617-126">Scaling Up the BizTalk Server Tier</span></span>](../core/scaling-up-the-biztalk-server-tier.md)  
  
-   [<span data-ttu-id="2a617-127">SQL Server 层向外缩放</span><span class="sxs-lookup"><span data-stu-id="2a617-127">Scaling Out the SQL Server Tier</span></span>](../core/scaling-out-the-sql-server-tier.md)  
  
-   [<span data-ttu-id="2a617-128">纵向扩展 SQL Server 层</span><span class="sxs-lookup"><span data-stu-id="2a617-128">Scaling Up the SQL Server Tier</span></span>](../core/scaling-up-the-sql-server-tier.md)  
  
## <a name="see-also"></a><span data-ttu-id="2a617-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="2a617-129">See Also</span></span>  
 <span data-ttu-id="2a617-130">[向外扩展接收主机](../core/scaled-out-receiving-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="2a617-130">[Scaled-Out Receiving Hosts](../core/scaled-out-receiving-hosts.md) </span></span>  
 <span data-ttu-id="2a617-131">[向外扩展处理主机](../core/scaled-out-processing-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="2a617-131">[Scaled-Out Processing Hosts](../core/scaled-out-processing-hosts.md) </span></span>  
 <span data-ttu-id="2a617-132">[向外扩展发送主机](../core/scaled-out-sending-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="2a617-132">[Scaled-Out Sending Hosts](../core/scaled-out-sending-hosts.md) </span></span>  
 <span data-ttu-id="2a617-133">[使用 Windows Server 群集为 BizTalk Server 主机 2 提供高可用性](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="2a617-133">[Using Windows Server Cluster to Provide High Availability for BizTalk Server Hosts2](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span></span>  
 <span data-ttu-id="2a617-134">[向外扩展数据库](../core/scaled-out-databases.md) </span><span class="sxs-lookup"><span data-stu-id="2a617-134">[Scaled-Out Databases](../core/scaled-out-databases.md) </span></span>  
 [<span data-ttu-id="2a617-135">聚类分析 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="2a617-135">Clustering the BizTalk Server Databases</span></span>](../core/clustering-the-biztalk-server-databases1.md)