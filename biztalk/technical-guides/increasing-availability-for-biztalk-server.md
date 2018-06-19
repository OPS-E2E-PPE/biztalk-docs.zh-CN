---
title: 提高了可用性，BizTalk 服务器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 72d9ce5e-d775-4f8e-b1a4-bf3c7c05f571
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa48d7dada00ebadf089834f5025f3fdfdf25070
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22297997"
---
# <a name="increasing-availability-for-biztalk-server"></a><span data-ttu-id="174e5-102">BizTalk Server 用于提高可用性</span><span class="sxs-lookup"><span data-stu-id="174e5-102">Increasing Availability for BizTalk Server</span></span>
<span data-ttu-id="174e5-103">本部分介绍你可以增加的可用性的方式你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统。</span><span class="sxs-lookup"><span data-stu-id="174e5-103">This section describes ways you can increase the availability of your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system.</span></span>  
  
## <a name="strategies-for-increasing-availability"></a><span data-ttu-id="174e5-104">提高可用性的策略</span><span class="sxs-lookup"><span data-stu-id="174e5-104">Strategies for Increasing Availability</span></span>  
 <span data-ttu-id="174e5-105">提高可用性策略包括：</span><span class="sxs-lookup"><span data-stu-id="174e5-105">Strategies for increasing availability include the following:</span></span>  
  
-   <span data-ttu-id="174e5-106">**提供使用 Windows Server 2003 服务器群集或 Windows Server 2008 故障转移群集的高可用性**。</span><span class="sxs-lookup"><span data-stu-id="174e5-106">**Providing high availability using Windows Server 2003 server clustering or Windows Server 2008 failover clustering**.</span></span> <span data-ttu-id="174e5-107">服务器/故障转移群集是一组独立的计算机系统，称为节点，作为单个系统以确保关键应用程序和资源保持供客户端一起工作。</span><span class="sxs-lookup"><span data-stu-id="174e5-107">A server/failover cluster is a group of independent computer systems, known as nodes, working together as a single system to ensure that critical applications and resources remain available to clients.</span></span> <span data-ttu-id="174e5-108">如果其中一个节点变为因为故障或进行维护停机时间要求而不可用，另一个节点就会立即开始提供服务 （该过程称为故障转移）。</span><span class="sxs-lookup"><span data-stu-id="174e5-108">If one of the nodes becomes unavailable as a result of failure or maintenance downtime requirements, another node immediately begins providing service (a process known as failover).</span></span>  
  
    -   <span data-ttu-id="174e5-109">服务器/故障转移群集通常适用于运行该内部的 SQL Server 的计算机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。</span><span class="sxs-lookup"><span data-stu-id="174e5-109">A server/failover cluster is typically recommended for the computers running SQL Server that house the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span>  
  
    -   <span data-ttu-id="174e5-110">服务器群集可能需要提供高可用性，对于某些 BizTalk 适配器。</span><span class="sxs-lookup"><span data-stu-id="174e5-110">A server cluster may be required to provide high availability for certain BizTalk adapters.</span></span>  
  
    -   <span data-ttu-id="174e5-111">服务器群集通常适用于企业单一登录的主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="174e5-111">A server cluster is typically recommended for the Enterprise Single Sign-On master secret server.</span></span>  
  
-   <span data-ttu-id="174e5-112">**提供使用某种形式的负载平衡的高可用性**。</span><span class="sxs-lookup"><span data-stu-id="174e5-112">**Providing high availability using a form of load balancing**.</span></span>  
  
    -   <span data-ttu-id="174e5-113">网络负载平衡 (NLB)。</span><span class="sxs-lookup"><span data-stu-id="174e5-113">Network load balancing (NLB).</span></span> <span data-ttu-id="174e5-114">NLB 提供高可用性，通过将传入的网络流量重定向到正在工作 NLB 群集主机，如果某个主机故障或处于脱机状态。</span><span class="sxs-lookup"><span data-stu-id="174e5-114">NLB delivers high availability by redirecting incoming network traffic to working NLB cluster hosts if a host fails or is offline.</span></span> <span data-ttu-id="174e5-115">与不同的是服务器群集，NLB 不需要特殊硬件。</span><span class="sxs-lookup"><span data-stu-id="174e5-115">Unlike server clusters, NLB does not require special hardware.</span></span>  
  
    -   <span data-ttu-id="174e5-116">BizTalk 主机负载平衡。</span><span class="sxs-lookup"><span data-stu-id="174e5-116">BizTalk host load balancing.</span></span> <span data-ttu-id="174e5-117">通过添加多个服务器运行 BizTalk 主机负载平衡提供 BizTalk 主机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组中，然后配置这些服务器上运行的进程内主机的多个实例。</span><span class="sxs-lookup"><span data-stu-id="174e5-117">BizTalk host load balancing is provided for BizTalk Hosts by adding multiple servers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] group and then configuring multiple instances of an in-process host to run on these servers.</span></span> <span data-ttu-id="174e5-118">这可以跨主机的多个实例分发在该主机中配置的服务和项目的执行，这可增强其可用性与可伸缩性。</span><span class="sxs-lookup"><span data-stu-id="174e5-118">This distributes the execution of services and artifacts configured in that host across multiple instances of the host, which enhances its availability and scalability.</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="174e5-119">可用于进程内主机仅主机负载平衡功能。</span><span class="sxs-lookup"><span data-stu-id="174e5-119">Host load balancing functionality is available for in-process hosts only.</span></span>  
  
    -   <span data-ttu-id="174e5-120">通过使用 SAN 或通过添加 MessageBox 的多个数据库的 SQL Server 磁盘提供负载平衡。</span><span class="sxs-lookup"><span data-stu-id="174e5-120">Load balancing is provided for SQL Server disks through the use of a SAN or by adding multiple MessageBox databases.</span></span>  
  
-   <span data-ttu-id="174e5-121">提供策略**提高了可用性**。</span><span class="sxs-lookup"><span data-stu-id="174e5-121">Strategies for providing **increased availability**.</span></span> <span data-ttu-id="174e5-122">这些策略提供更高的可用性，但通常还需要管理员执行在运行时的一个或多个操作。</span><span class="sxs-lookup"><span data-stu-id="174e5-122">These strategies provide increased availability but usually also require that an administrator perform one or more actions at runtime.</span></span> <span data-ttu-id="174e5-123">因此这些策略是通常认为提供更高的可用性，而不是高可用性：</span><span class="sxs-lookup"><span data-stu-id="174e5-123">Therefore these strategies are typically thought of as providing increased availability as opposed to high availability:</span></span>  
  
    -   <span data-ttu-id="174e5-124">增加可用性使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]日志传送和灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="174e5-124">Increasing availability using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping and disaster recovery.</span></span>  
  
    -   <span data-ttu-id="174e5-125">提高可用性通过实现相应的监视和维护策略。</span><span class="sxs-lookup"><span data-stu-id="174e5-125">Increasing availability through implementation of the appropriate monitoring and maintenance strategies.</span></span>  
  
## <a name="difference-between-clustering-and-disaster-recovery"></a><span data-ttu-id="174e5-126">群集之间的差异和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="174e5-126">Difference Between Clustering and Disaster Recovery</span></span>  
 <span data-ttu-id="174e5-127">尽管群集和灾难恢复提高可用性，它们的主要区别是群集通常提供比灾难恢复速度快得多的恢复时间。</span><span class="sxs-lookup"><span data-stu-id="174e5-127">While clusters and disaster recovery both increase availability, a key difference between them is that clusters typically provide much faster recovery time than disaster recovery does.</span></span> <span data-ttu-id="174e5-128">因此在服务器/故障转移群集上生成的解决方案或负载平衡通常想象成提供高可用性而不是仅提供可用性。</span><span class="sxs-lookup"><span data-stu-id="174e5-128">Therefore a solution built on server/failover clusters or load balancing is commonly thought of as providing high availability as opposed to merely providing availability.</span></span>  
  
 <span data-ttu-id="174e5-129">灾难恢复，可恢复的失败的系统运行但通常是一个手动过程，并且需要比的高可用性实现的更多恢复时间。</span><span class="sxs-lookup"><span data-stu-id="174e5-129">Disaster recovery allows you to resume operation of a failed system but is typically a manual process and requires more recovery time than a high-availability implementation.</span></span> <span data-ttu-id="174e5-130">因此，灾难恢复实现提供可用性，但不是需要高可用性。</span><span class="sxs-lookup"><span data-stu-id="174e5-130">Therefore, a disaster recovery implementation provides availability but not high availability.</span></span> <span data-ttu-id="174e5-131">您应使用通过服务器/故障转移群集和负载平衡，高可用性和灾难恢复，在生产中通过可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。</span><span class="sxs-lookup"><span data-stu-id="174e5-131">You should employ both high availability through server/failover clusters and load balancing, and availability through disaster recovery, in a production [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="174e5-132">本节内容</span><span class="sxs-lookup"><span data-stu-id="174e5-132">In This Section</span></span>  
  
-   [<span data-ttu-id="174e5-133">提供高可用性</span><span class="sxs-lookup"><span data-stu-id="174e5-133">Providing High Availability</span></span>](../technical-guides/providing-high-availability.md)  
  
-   [<span data-ttu-id="174e5-134">灾难恢复</span><span class="sxs-lookup"><span data-stu-id="174e5-134">Disaster Recovery</span></span>](../technical-guides/disaster-recovery.md)  
  
## <a name="see-also"></a><span data-ttu-id="174e5-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="174e5-135">See Also</span></span>  
 <span data-ttu-id="174e5-136">[清单： 会提供高可用性容错或负载平衡](../technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md) </span><span class="sxs-lookup"><span data-stu-id="174e5-136">[Checklist: Providing High Availability with Fault Tolerance or Load Balancing](../technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md) </span></span>  
 [<span data-ttu-id="174e5-137">清单： 提高可用性与灾难恢复</span><span class="sxs-lookup"><span data-stu-id="174e5-137">Checklist: Increasing Availability with Disaster Recovery</span></span>](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)