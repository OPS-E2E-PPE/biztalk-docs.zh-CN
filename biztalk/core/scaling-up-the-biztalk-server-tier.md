---
title: "BizTalk Server 层向上缩放 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, scaling
- scaling, examples
- scaling, scaling up
ms.assetid: 9002006a-f301-4e15-94b9-6caffd7c527c
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d55176072cd33e20dd1024bf2d9d1c39bca4567a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="scaling-up-the-biztalk-server-tier"></a><span data-ttu-id="9af27-102">BizTalk Server 层向上扩展</span><span class="sxs-lookup"><span data-stu-id="9af27-102">Scaling Up the BizTalk Server Tier</span></span>
<span data-ttu-id="9af27-103">若要向上扩展 BizTalk 层，则需要升级 CPU、内存、输入/输出以及其他资源。</span><span class="sxs-lookup"><span data-stu-id="9af27-103">To scale up the BizTalk tier, you upgrade the CPU, memory, IO and other resources.</span></span> <span data-ttu-id="9af27-104">以下示例图显示了如何从双处理器计算机向上扩展 BizTalk 层到具有四个处理器的计算机：</span><span class="sxs-lookup"><span data-stu-id="9af27-104">The following figure shows an example of how you might scale up the BizTalk tier from a two processor computer to a four processor computer.</span></span>  
  
 <span data-ttu-id="9af27-105">![缩放 &#45; 向上 BTS](../core/media/scaleupbts.gif "ScaleUpBTS")</span><span class="sxs-lookup"><span data-stu-id="9af27-105">![Scale&#45;up BTS](../core/media/scaleupbts.gif "ScaleUpBTS")</span></span>  
  
 <span data-ttu-id="9af27-106">向上扩展 BizTalk 层的方案与选择扩展时相似：</span><span class="sxs-lookup"><span data-stu-id="9af27-106">The scenarios for scaling up your BizTalk tier are similar to when you choose to scale out:</span></span>  
  
-   <span data-ttu-id="9af27-107">BizTalk Server 成为瓶颈。</span><span class="sxs-lookup"><span data-stu-id="9af27-107">BizTalk Server becomes a bottleneck.</span></span> <span data-ttu-id="9af27-108">该瓶颈本身可能是由于以下问题之一而导致的：</span><span class="sxs-lookup"><span data-stu-id="9af27-108">The bottleneck itself may be caused by one of the following problems:</span></span>  
  
-   <span data-ttu-id="9af27-109">CPU： 如果本方案使用 CPU 密集型管道、 地图或业务流程，BizTalk 服务器将不具有任何额外的 CPU 预留空间。</span><span class="sxs-lookup"><span data-stu-id="9af27-109">CPU: If the scenario uses CPU intensive pipelines, maps, or orchestrations, the BizTalk servers will not have any extra CPU headroom.</span></span>  
  
-   <span data-ttu-id="9af27-110">内存和输入/输出：如果现有计算机已达到其对内存和输入/输出的最大限制，则该计算机需要升级。</span><span class="sxs-lookup"><span data-stu-id="9af27-110">Memory and I/O: If the existing computers have reached their maximum limit on memory and IO, and the computer needs to be upgraded.</span></span>  
  
-   <span data-ttu-id="9af27-111">扩展的成本十分高昂。</span><span class="sxs-lookup"><span data-stu-id="9af27-111">Scaling out is too expensive.</span></span>  
  
-   <span data-ttu-id="9af27-112">如果扩展不能解决瓶颈问题。</span><span class="sxs-lookup"><span data-stu-id="9af27-112">If scale-out does not address the bottleneck.</span></span> <span data-ttu-id="9af27-113">例如，扩展不能解决以下瓶颈问题：</span><span class="sxs-lookup"><span data-stu-id="9af27-113">For example, scaling out does not address the following bottlenecks:</span></span>  
  
    -   <span data-ttu-id="9af27-114">大型消息转换</span><span class="sxs-lookup"><span data-stu-id="9af27-114">Large Message Transforms</span></span>  
  
    -   <span data-ttu-id="9af27-115">每个交换中的大量消息</span><span class="sxs-lookup"><span data-stu-id="9af27-115">Large number of messages per interchange</span></span>  
  
    -   <span data-ttu-id="9af27-116">某些 BTS 组件（例如，管道或适配器）的高内存使用率</span><span class="sxs-lookup"><span data-stu-id="9af27-116">High memory utilization by some of BTS components, such as pipelines or adapters</span></span>  
  
    -   <span data-ttu-id="9af27-117">传输，例如 EDI</span><span class="sxs-lookup"><span data-stu-id="9af27-117">A transport, such as EDI</span></span>  
  
## <a name="when-you-cant-scale-up-the-biztalk-tier"></a><span data-ttu-id="9af27-118">在无法向上扩展 BizTalk 层时</span><span class="sxs-lookup"><span data-stu-id="9af27-118">When You Can’t Scale Up the BizTalk Tier</span></span>  
  
-   <span data-ttu-id="9af27-119">MessageBox 数据库是瓶颈。</span><span class="sxs-lookup"><span data-stu-id="9af27-119">The MessageBox database is the bottleneck.</span></span>  
  
-   <span data-ttu-id="9af27-120">适配器成为瓶颈。</span><span class="sxs-lookup"><span data-stu-id="9af27-120">An adapter becomes the bottleneck.</span></span> <span data-ttu-id="9af27-121">例如，如果你使用适配器之后增加 BizTalk 接收方的数量，可能在其中 BizTalk 适配器中提取的数据从后端应用程序上增加锁争用。</span><span class="sxs-lookup"><span data-stu-id="9af27-121">For example, if you are using an adapter, after you increase the number of BizTalk receivers, lock contention might increase on the backend application where the BizTalk adapter is pulling data from.</span></span> <span data-ttu-id="9af27-122">这限制适配器向上扩展的能力。</span><span class="sxs-lookup"><span data-stu-id="9af27-122">This limits your ability to scale up the adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9af27-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9af27-123">See Also</span></span>  
 <span data-ttu-id="9af27-124">[BizTalk Server 层向外缩放](../core/scaling-out-the-biztalk-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="9af27-124">[Scaling Out the BizTalk Server Tier](../core/scaling-out-the-biztalk-server-tier.md) </span></span>  
 <span data-ttu-id="9af27-125">[SQL Server 层向上扩展](../core/scaling-up-the-sql-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="9af27-125">[Scaling Up the SQL Server Tier](../core/scaling-up-the-sql-server-tier.md) </span></span>  
 <span data-ttu-id="9af27-126">[SQL Server 层向外缩放](../core/scaling-out-the-sql-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="9af27-126">[Scaling Out the SQL Server Tier](../core/scaling-out-the-sql-server-tier.md) </span></span>  
 <span data-ttu-id="9af27-127">[向外扩展接收主机](../core/scaled-out-receiving-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="9af27-127">[Scaled-Out Receiving Hosts](../core/scaled-out-receiving-hosts.md) </span></span>  
 <span data-ttu-id="9af27-128">[向外扩展的处理主机](../core/scaled-out-processing-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="9af27-128">[Scaled-Out Processing Hosts](../core/scaled-out-processing-hosts.md) </span></span>  
 <span data-ttu-id="9af27-129">[向外扩展的发送主机](../core/scaled-out-sending-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="9af27-129">[Scaled-Out Sending Hosts](../core/scaled-out-sending-hosts.md) </span></span>  
 <span data-ttu-id="9af27-130">[Windows Server 群集用于 BizTalk Server Hosts2 为提供高可用性](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="9af27-130">[Using Windows Server Cluster to Provide High Availability for BizTalk Server Hosts2](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span></span>  
 <span data-ttu-id="9af27-131">[向外扩展的数据库](../core/scaled-out-databases.md) </span><span class="sxs-lookup"><span data-stu-id="9af27-131">[Scaled-Out Databases](../core/scaled-out-databases.md) </span></span>  
 [<span data-ttu-id="9af27-132">群集的 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="9af27-132">Clustering the BizTalk Server Databases</span></span>](../core/clustering-the-biztalk-server-databases1.md)