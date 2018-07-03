---
title: BizTalk Server 提供高可用性 |Microsoft Docs
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
ms.openlocfilehash: c6de74c7efb9aa4f900d555c265318bb17118082
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023699"
---
# <a name="increasing-availability-for-biztalk-server"></a><span data-ttu-id="84486-102">BizTalk Server 提供高可用性</span><span class="sxs-lookup"><span data-stu-id="84486-102">Increasing Availability for BizTalk Server</span></span>
<span data-ttu-id="84486-103">本部分介绍可提升的可用性的方法在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统。</span><span class="sxs-lookup"><span data-stu-id="84486-103">This section describes ways you can increase the availability of your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system.</span></span>  
  
## <a name="strategies-for-increasing-availability"></a><span data-ttu-id="84486-104">用于提高可用性的策略</span><span class="sxs-lookup"><span data-stu-id="84486-104">Strategies for Increasing Availability</span></span>  
 <span data-ttu-id="84486-105">用于提高可用性的策略包括：</span><span class="sxs-lookup"><span data-stu-id="84486-105">Strategies for increasing availability include the following:</span></span>  
  
- <span data-ttu-id="84486-106">**提供使用 Windows Server 2003 服务器群集或 Windows Server 2008 故障转移群集实现高可用性**。</span><span class="sxs-lookup"><span data-stu-id="84486-106">**Providing high availability using Windows Server 2003 server clustering or Windows Server 2008 failover clustering**.</span></span> <span data-ttu-id="84486-107">服务器/故障转移群集是一组独立的计算机系统，名为节点，作为单个系统以确保关键应用程序和资源始终可由客户端一起工作。</span><span class="sxs-lookup"><span data-stu-id="84486-107">A server/failover cluster is a group of independent computer systems, known as nodes, working together as a single system to ensure that critical applications and resources remain available to clients.</span></span> <span data-ttu-id="84486-108">如果某个节点由于故障或维护停机时间要求而不可用，另一个节点就会立即开始提供服务 （该过程称为故障转移）。</span><span class="sxs-lookup"><span data-stu-id="84486-108">If one of the nodes becomes unavailable as a result of failure or maintenance downtime requirements, another node immediately begins providing service (a process known as failover).</span></span>  
  
  - <span data-ttu-id="84486-109">对于运行用于容装的 SQL Server 的计算机通常建议服务器/故障转移群集，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。</span><span class="sxs-lookup"><span data-stu-id="84486-109">A server/failover cluster is typically recommended for the computers running SQL Server that house the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span>  
  
  - <span data-ttu-id="84486-110">服务器群集可能需要某些 BizTalk 适配器提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="84486-110">A server cluster may be required to provide high availability for certain BizTalk adapters.</span></span>  
  
  - <span data-ttu-id="84486-111">服务器群集通常建议使用企业单一登录主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="84486-111">A server cluster is typically recommended for the Enterprise Single Sign-On master secret server.</span></span>  
  
- <span data-ttu-id="84486-112">**提供使用窗体的负载均衡的高可用性**。</span><span class="sxs-lookup"><span data-stu-id="84486-112">**Providing high availability using a form of load balancing**.</span></span>  
  
  - <span data-ttu-id="84486-113">网络负载平衡 (NLB)。</span><span class="sxs-lookup"><span data-stu-id="84486-113">Network load balancing (NLB).</span></span> <span data-ttu-id="84486-114">NLB 将传入网络流量重定向到使用 NLB 群集主机，如果主机发生故障或处于脱机状态，以提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="84486-114">NLB delivers high availability by redirecting incoming network traffic to working NLB cluster hosts if a host fails or is offline.</span></span> <span data-ttu-id="84486-115">与不同的服务器群集，NLB 不需要特殊硬件。</span><span class="sxs-lookup"><span data-stu-id="84486-115">Unlike server clusters, NLB does not require special hardware.</span></span>  
  
  - <span data-ttu-id="84486-116">BizTalk 主机负载平衡。</span><span class="sxs-lookup"><span data-stu-id="84486-116">BizTalk host load balancing.</span></span> <span data-ttu-id="84486-117">BizTalk 主机提供负载平衡的 BizTalk 主机添加多个服务器运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]组，然后配置这些服务器上运行的进程内主机的多个实例。</span><span class="sxs-lookup"><span data-stu-id="84486-117">BizTalk host load balancing is provided for BizTalk Hosts by adding multiple servers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] group and then configuring multiple instances of an in-process host to run on these servers.</span></span> <span data-ttu-id="84486-118">这可以跨主机的多个实例分发在该主机中配置的服务和项目的执行，这可增强其可用性与可伸缩性。</span><span class="sxs-lookup"><span data-stu-id="84486-118">This distributes the execution of services and artifacts configured in that host across multiple instances of the host, which enhances its availability and scalability.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="84486-119">对于进程内主机提供主机负载平衡功能。</span><span class="sxs-lookup"><span data-stu-id="84486-119">Host load balancing functionality is available for in-process hosts only.</span></span>  
  
  - <span data-ttu-id="84486-120">通过使用 SAN 或通过添加多个 MessageBox 数据库的 SQL Server 磁盘提供负载平衡。</span><span class="sxs-lookup"><span data-stu-id="84486-120">Load balancing is provided for SQL Server disks through the use of a SAN or by adding multiple MessageBox databases.</span></span>  
  
- <span data-ttu-id="84486-121">提供的策略**提高了可用性**。</span><span class="sxs-lookup"><span data-stu-id="84486-121">Strategies for providing **increased availability**.</span></span> <span data-ttu-id="84486-122">这些策略提供更高的可用性，但通常也需要管理员执行在运行时的一个或多个操作。</span><span class="sxs-lookup"><span data-stu-id="84486-122">These strategies provide increased availability but usually also require that an administrator perform one or more actions at runtime.</span></span> <span data-ttu-id="84486-123">因此这些策略是通常认为提供更高的可用性，而不是高可用性：</span><span class="sxs-lookup"><span data-stu-id="84486-123">Therefore these strategies are typically thought of as providing increased availability as opposed to high availability:</span></span>  
  
  - <span data-ttu-id="84486-124">增加可用性使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]日志传送和灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="84486-124">Increasing availability using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] log shipping and disaster recovery.</span></span>  
  
  - <span data-ttu-id="84486-125">提高可用性通过实现相应的监视和维护的策略。</span><span class="sxs-lookup"><span data-stu-id="84486-125">Increasing availability through implementation of the appropriate monitoring and maintenance strategies.</span></span>  
  
## <a name="difference-between-clustering-and-disaster-recovery"></a><span data-ttu-id="84486-126">聚类分析之间的差异和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="84486-126">Difference Between Clustering and Disaster Recovery</span></span>  
 <span data-ttu-id="84486-127">虽然群集和灾难恢复这两种提高可用性，它们之间的主要差异是群集通常提供比灾难恢复速度快得多的恢复时间。</span><span class="sxs-lookup"><span data-stu-id="84486-127">While clusters and disaster recovery both increase availability, a key difference between them is that clusters typically provide much faster recovery time than disaster recovery does.</span></span> <span data-ttu-id="84486-128">因此服务器/故障转移群集上生成解决方案或负载平衡广泛被认为提供高可用性而不是只提供可用性。</span><span class="sxs-lookup"><span data-stu-id="84486-128">Therefore a solution built on server/failover clusters or load balancing is commonly thought of as providing high availability as opposed to merely providing availability.</span></span>  
  
 <span data-ttu-id="84486-129">灾难恢复，可恢复操作失败的系统，但通常是一个手动过程并且需要比高可用性实现的更多恢复时间。</span><span class="sxs-lookup"><span data-stu-id="84486-129">Disaster recovery allows you to resume operation of a failed system but is typically a manual process and requires more recovery time than a high-availability implementation.</span></span> <span data-ttu-id="84486-130">因此，灾难恢复实现提供可用性，但不是需要高可用性。</span><span class="sxs-lookup"><span data-stu-id="84486-130">Therefore, a disaster recovery implementation provides availability but not high availability.</span></span> <span data-ttu-id="84486-131">通过服务器/故障转移群集和负载均衡的高可用性和灾难恢复，在生产环境中的可用性，应使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。</span><span class="sxs-lookup"><span data-stu-id="84486-131">You should employ both high availability through server/failover clusters and load balancing, and availability through disaster recovery, in a production [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="84486-132">本节内容</span><span class="sxs-lookup"><span data-stu-id="84486-132">In This Section</span></span>  
  
-   [<span data-ttu-id="84486-133">提供高可用性</span><span class="sxs-lookup"><span data-stu-id="84486-133">Providing High Availability</span></span>](../technical-guides/providing-high-availability.md)  
  
-   [<span data-ttu-id="84486-134">灾难恢复</span><span class="sxs-lookup"><span data-stu-id="84486-134">Disaster Recovery</span></span>](../technical-guides/disaster-recovery.md)  
  
## <a name="see-also"></a><span data-ttu-id="84486-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="84486-135">See Also</span></span>  
 <span data-ttu-id="84486-136">[清单： 提供高可用性容错或负载平衡](../technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md) </span><span class="sxs-lookup"><span data-stu-id="84486-136">[Checklist: Providing High Availability with Fault Tolerance or Load Balancing](../technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md) </span></span>  
 [<span data-ttu-id="84486-137">清单：提供高可用性灾难恢复</span><span class="sxs-lookup"><span data-stu-id="84486-137">Checklist: Increasing Availability with Disaster Recovery</span></span>](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)