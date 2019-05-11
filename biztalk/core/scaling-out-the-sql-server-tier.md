---
title: SQL Server 层向外缩放 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- scaling, MessageBox database
- scaling, scaling out
- SQL Server, scaling
- MessageBox database, scaling
- scaling, strategies
ms.assetid: d5b2ebba-401e-4fde-8818-407fa626043a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c49a6bd83b6647170574106dd06825e2e5aba75
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65309023"
---
# <a name="scaling-out-the-sql-server-tier"></a><span data-ttu-id="eed06-102">SQL Server 层向外缩放</span><span class="sxs-lookup"><span data-stu-id="eed06-102">Scaling Out the SQL Server Tier</span></span>
<span data-ttu-id="eed06-103">对于每个 BizTalk 组，您将添加一个主 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="eed06-103">For each BizTalk group, you add one Master MessageBox database.</span></span> <span data-ttu-id="eed06-104">所有后续 MessageBox 数据库，您将添加称为辅助 Messagebox。</span><span class="sxs-lookup"><span data-stu-id="eed06-104">All the subsequent MessageBox databases that you add are called secondary MessageBoxes.</span></span> <span data-ttu-id="eed06-105">主 MessageBox 处理所有订阅和消息路由。</span><span class="sxs-lookup"><span data-stu-id="eed06-105">The Master MessageBox handles all subscriptions and message routing.</span></span> <span data-ttu-id="eed06-106">它还可以发布消息。</span><span class="sxs-lookup"><span data-stu-id="eed06-106">It can also publish messages.</span></span> <span data-ttu-id="eed06-107">辅助 MessageBox 数据库仅将发布消息时专门配置，以执行此操作。</span><span class="sxs-lookup"><span data-stu-id="eed06-107">Secondary MessageBox databases will only publish messages when specifically configured to do so.</span></span>  
  
## <a name="how-to-add-a-secondary-messagebox-database"></a><span data-ttu-id="eed06-108">如何添加辅助 MessageBox 数据库</span><span class="sxs-lookup"><span data-stu-id="eed06-108">How to Add a Secondary MessageBox Database</span></span>  
 <span data-ttu-id="eed06-109">有两种方法来添加辅助 MessageBox 数据库：</span><span class="sxs-lookup"><span data-stu-id="eed06-109">There are two ways to add secondary MessageBox databases:</span></span>  
  
- <span data-ttu-id="eed06-110">在同一物理服务器上添加辅助 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="eed06-110">Add the secondary MessageBox database on the same physical server.</span></span>  
  
   <span data-ttu-id="eed06-111">如果现有 MessageBox 物理服务器具有足够的 CPU 和 I/O 资源，并且仅遇到锁争用瓶颈，则执行此操作。</span><span class="sxs-lookup"><span data-stu-id="eed06-111">Do this if the existing MessageBox physical server has enough CPU and I/O resources and is only bottlenecked by lock contention.</span></span> <span data-ttu-id="eed06-112">不同的 IO 驱动器上创建辅助 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="eed06-112">Create the secondary MessageBox database on separate IO drives.</span></span>  
  
   <span data-ttu-id="eed06-113">优点：</span><span class="sxs-lookup"><span data-stu-id="eed06-113">Advantages:</span></span>  
  
  -   <span data-ttu-id="eed06-114">另一个消息框通过利用额外的 CPU 余量</span><span class="sxs-lookup"><span data-stu-id="eed06-114">The extra CPU headroom can be utilized by another message-box</span></span>  
  
  -   <span data-ttu-id="eed06-115">所需较少的 SQL server 许可证</span><span class="sxs-lookup"><span data-stu-id="eed06-115">Fewer SQL server licenses are required</span></span>  
  
  -   <span data-ttu-id="eed06-116">消除的网络跃点</span><span class="sxs-lookup"><span data-stu-id="eed06-116">Network hop is eliminated</span></span>  
  
- <span data-ttu-id="eed06-117">不同的物理服务器上添加辅助 MessageBox 数据库</span><span class="sxs-lookup"><span data-stu-id="eed06-117">Add the secondary MessageBox database on a different physical server</span></span>  
  
   <span data-ttu-id="eed06-118">在这种情况下，专用物理服务器与自己的 IO 使用作为额外的 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="eed06-118">In this case, use a dedicated physical server with its own IO as the extra MessageBox database.</span></span>  
  
  <span data-ttu-id="eed06-119">下图显示了其中 SQL 层向外扩展从一个 MessageBox 数据库到三个 MessageBoxes 数据库的方案。</span><span class="sxs-lookup"><span data-stu-id="eed06-119">The following figure shows a scenario where SQL tier is scaled-out from one MessageBox database to three MessageBoxes databases.</span></span>  
  
  <span data-ttu-id="eed06-120">![向外扩展 MSGBOX](../core/media/scaleoutmsgbox.gif "ScaleOutMSGBOX")</span><span class="sxs-lookup"><span data-stu-id="eed06-120">![Scale out MSGBOX](../core/media/scaleoutmsgbox.gif "ScaleOutMSGBOX")</span></span>  
  
## <a name="when-to-scale-out-the-messagebox-database"></a><span data-ttu-id="eed06-121">当向外扩展 MessageBox 数据库</span><span class="sxs-lookup"><span data-stu-id="eed06-121">When to Scale-out the MessageBox database</span></span>  
  
-   <span data-ttu-id="eed06-122">MessageBox 数据库成为瓶颈。</span><span class="sxs-lookup"><span data-stu-id="eed06-122">The MessageBox database becomes the bottleneck.</span></span> <span data-ttu-id="eed06-123">可以是这些瓶颈：</span><span class="sxs-lookup"><span data-stu-id="eed06-123">Those bottlenecks can be:</span></span>  
  
    -   <span data-ttu-id="eed06-124">**CPU**非常昂贵且复杂的业务流程方案中，如果 MessageBox 数据库会占用大量 CPU 资源。</span><span class="sxs-lookup"><span data-stu-id="eed06-124">**CPU** In case of very expensive and complex orchestration scenarios, the MessageBox database consumes heavy CPU resources.</span></span> <span data-ttu-id="eed06-125">添加其他发布 MessageBox 数据库应有助于增加吞吐量。</span><span class="sxs-lookup"><span data-stu-id="eed06-125">Adding another publishing the MessageBox database should help increase the throughput.</span></span>  
  
    -   <span data-ttu-id="eed06-126">**锁争用**具有多个主机实例或业务流程的复杂方案往往会在 MessageBox 数据库上创建锁争用。</span><span class="sxs-lookup"><span data-stu-id="eed06-126">**Lock Contention** Complex scenarios with multiple host instances or orchestrations tend to create lock contention on the MessageBox database.</span></span> <span data-ttu-id="eed06-127">同样，添加其他发布 MessageBox 数据库应有助于增加吞吐量。</span><span class="sxs-lookup"><span data-stu-id="eed06-127">Again, adding another publishing MessageBox database should help increase the throughput.</span></span>  
  
-   <span data-ttu-id="eed06-128">向上扩展没有解决瓶颈问题。</span><span class="sxs-lookup"><span data-stu-id="eed06-128">Scaling up doesn’t address the bottleneck.</span></span> <span data-ttu-id="eed06-129">例如，如果主 MessageBox 数据库出现锁争用，向外扩展是唯一的选项。</span><span class="sxs-lookup"><span data-stu-id="eed06-129">For example, if the Master MessageBox database is lock contention bound, scaling-out is the only option.</span></span>  
  
-   <span data-ttu-id="eed06-130">向上扩展成本十分高昂。</span><span class="sxs-lookup"><span data-stu-id="eed06-130">Scaling-up is too expensive.</span></span> <span data-ttu-id="eed06-131">例如，如果将现有 4 处理器服务器升级到 8 路服务器比添加另一个 4 处理器开销更大，向外扩展是更好的选择。</span><span class="sxs-lookup"><span data-stu-id="eed06-131">For example, if upgrading the existing quad proc server to 8 way server is more expensive than adding another quad proc, scale-out is better option.</span></span>  
  
## <a name="when-you-cant-scale-out-the-sql-tier"></a><span data-ttu-id="eed06-132">不能向外扩展 SQL 层</span><span class="sxs-lookup"><span data-stu-id="eed06-132">When You Can’t Scale-out the SQL Tier</span></span>  
 <span data-ttu-id="eed06-133">从理论上讲，应无限期地只要主 MessageBox 数据库不是瓶颈扩展 SQL 层。</span><span class="sxs-lookup"><span data-stu-id="eed06-133">In theory, the SQL tier should scale indefinitely as long as the Master MessageBox database is not the bottleneck.</span></span> <span data-ttu-id="eed06-134">若要实现此目的，请考虑使主 MessageBox 数据库成为非发布数据库，以便它仅执行路由。</span><span class="sxs-lookup"><span data-stu-id="eed06-134">To achieve this, consider making the Master MessageBox database a non-publishing database so it only does routing.</span></span> <span data-ttu-id="eed06-135">但是，一旦主锁争用出现瓶颈，不能缩放任何更多扩展 SQL 层。</span><span class="sxs-lookup"><span data-stu-id="eed06-135">But, once the Master is bottlenecked by lock contention, you cannot scale out the SQL tier any more.</span></span>  
  
## <a name="scale-out-strategies-and-considerations"></a><span data-ttu-id="eed06-136">向外缩放策略和注意事项</span><span class="sxs-lookup"><span data-stu-id="eed06-136">Scale-out Strategies and Considerations</span></span>  
  
-   <span data-ttu-id="eed06-137">首先向上扩展主 MessageBox 数据库，然后向外扩展。</span><span class="sxs-lookup"><span data-stu-id="eed06-137">First scale-up the Master MessageBox database and then scale out.</span></span>  
  
-   <span data-ttu-id="eed06-138">向外扩展从 1 到 3 个 SQL MessageBox 数据库，而不是 1 到 2。</span><span class="sxs-lookup"><span data-stu-id="eed06-138">Scaling-out from 1 to 3 SQL MessageBox databases instead of 1 to 2.</span></span> <span data-ttu-id="eed06-139">请考虑在上图中所示 1 的 SQL server 拓扑标题为"4 个 BizTalk Server，1 的 SQL Server 拓扑，"并认为 SQL server 是 CPU 绑定，换句话说，CPU 处理为瓶颈。</span><span class="sxs-lookup"><span data-stu-id="eed06-139">Consider the 1 SQL server topology illustrated in the figure above titled "4 BizTalk Server, 1 SQL Server Topology," and assume that the SQL server is CPU bound, in other words, the CPU processing is a bottleneck.</span></span> <span data-ttu-id="eed06-140">将只有一个 MessageBox 数据库添加到此拓扑中，如果主 Messagebox 仍将为 CPU 绑定且辅助 MessageBox 数据库将处于未充分利用。</span><span class="sxs-lookup"><span data-stu-id="eed06-140">If you add only one MessageBox database to this topology, the Master Messagebox will still be CPU bound and the secondary MessageBox database will be under-utilized.</span></span> <span data-ttu-id="eed06-141">因此，扩展因子是几乎为 1。</span><span class="sxs-lookup"><span data-stu-id="eed06-141">So, the scaling factor is almost 1.</span></span> <span data-ttu-id="eed06-142">如果在主 MessageBox 数据库上禁用发布，并且将专用主 MessageBox 数据库仅用于进行路由，则辅助 MessageBox 数据库将执行发布。</span><span class="sxs-lookup"><span data-stu-id="eed06-142">If you disable publishing on the Master MessageBox database and dedicate the Master MessageBox database only to do routing, the secondary MessageBox database will do the publishing.</span></span> <span data-ttu-id="eed06-143">这并不能增加总体吞吐量，但因为辅助 MessageBox 数据库只用作发布服务器并仍会成为瓶颈。</span><span class="sxs-lookup"><span data-stu-id="eed06-143">This will not help increase overall throughput though since the secondary MessageBox database is the only publisher and still becomes the bottleneck.</span></span> <span data-ttu-id="eed06-144">因此，添加 2 个辅助 MessageBox 数据库和主 MessageBox 数据库上禁用发布将在此方案中的横向扩展的建议的方法。</span><span class="sxs-lookup"><span data-stu-id="eed06-144">So, adding 2 secondary MessageBox databases and disabling the publishing on the Master MessageBox database would be the recommended way to scale-out in this scenario.</span></span>  
  
-   <span data-ttu-id="eed06-145">主 MessageBox 数据库最终将成为瓶颈。</span><span class="sxs-lookup"><span data-stu-id="eed06-145">The Master MessageBox database will eventually be the bottleneck.</span></span> <span data-ttu-id="eed06-146">因此，承载主 MessageBox 数据库的物理计算机应更快、 更大。</span><span class="sxs-lookup"><span data-stu-id="eed06-146">So, the physical computer hosting the Master MessageBox database should be faster and bigger.</span></span>  
  
-   <span data-ttu-id="eed06-147">若要最小化发送的数据通过网络 （和关联的 DTC 开销），请考虑将多个 MessageBox 数据库放置在同一台物理计算机具有专用驱动器上。</span><span class="sxs-lookup"><span data-stu-id="eed06-147">To minimize sending data over the network (and the associated DTC overhead), consider placing multiple MessageBox databases on the same physical computer with dedicated drives.</span></span> <span data-ttu-id="eed06-148">在同一时间，请确保，拥有这些多个数据库的计算机不会出现瓶颈的资源由多个 MessageBox 数据库共享。</span><span class="sxs-lookup"><span data-stu-id="eed06-148">At the same time, make sure that the computer holding these multiple databases is not bottlenecked as the resources are being shared by multiple MessageBox databases.</span></span>  
  
-   <span data-ttu-id="eed06-149">所有辅助 MessageBox 数据库应使用相同的硬件，因为在发布 MessageBox 数据库之间均匀分布工作。</span><span class="sxs-lookup"><span data-stu-id="eed06-149">All secondary MessageBox databases should use comparable hardware because work is evenly distributed among the publishing MessageBox databases.</span></span>  
  
-   <span data-ttu-id="eed06-150">由于只要主 MessageBox 数据库没有瓶颈问题，可以横向扩展辅助 MessageBox 数据库，辅助 MessageBox 数据库可以运行具有较少的 CPU 资源所需的主 MessageBox 数据库服务器的计算机上。</span><span class="sxs-lookup"><span data-stu-id="eed06-150">Since you can scale out secondary MessageBox databases as long as the master MessageBox database is not bottlenecked, secondary MessageBox databases can run on computers with less CPU resources than is required by the master MessageBox database server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eed06-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="eed06-151">See Also</span></span>  
 <span data-ttu-id="eed06-152">[向外扩展 BizTalk Server 层](../core/scaling-out-the-biztalk-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="eed06-152">[Scaling Out the BizTalk Server Tier](../core/scaling-out-the-biztalk-server-tier.md) </span></span>  
 <span data-ttu-id="eed06-153">[纵向扩展 BizTalk Server 层](../core/scaling-up-the-biztalk-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="eed06-153">[Scaling Up the BizTalk Server Tier](../core/scaling-up-the-biztalk-server-tier.md) </span></span>  
 <span data-ttu-id="eed06-154">[纵向扩展 SQL Server 层](../core/scaling-up-the-sql-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="eed06-154">[Scaling Up the SQL Server Tier](../core/scaling-up-the-sql-server-tier.md) </span></span>  
 <span data-ttu-id="eed06-155">[向外扩展接收主机](../core/scaled-out-receiving-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="eed06-155">[Scaled-Out Receiving Hosts](../core/scaled-out-receiving-hosts.md) </span></span>  
 <span data-ttu-id="eed06-156">[向外扩展处理主机](../core/scaled-out-processing-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="eed06-156">[Scaled-Out Processing Hosts](../core/scaled-out-processing-hosts.md) </span></span>  
 <span data-ttu-id="eed06-157">[向外扩展发送主机](../core/scaled-out-sending-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="eed06-157">[Scaled-Out Sending Hosts](../core/scaled-out-sending-hosts.md) </span></span>  
 <span data-ttu-id="eed06-158">[使用 Windows Server 群集为 BizTalk Server 主机 2 提供高可用性](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="eed06-158">[Using Windows Server Cluster to Provide High Availability for BizTalk Server Hosts2](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span></span>  
 <span data-ttu-id="eed06-159">[向外扩展数据库](../core/scaled-out-databases.md) </span><span class="sxs-lookup"><span data-stu-id="eed06-159">[Scaled-Out Databases](../core/scaled-out-databases.md) </span></span>  
 [<span data-ttu-id="eed06-160">聚类分析 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="eed06-160">Clustering the BizTalk Server Databases</span></span>](../core/clustering-the-biztalk-server-databases1.md)