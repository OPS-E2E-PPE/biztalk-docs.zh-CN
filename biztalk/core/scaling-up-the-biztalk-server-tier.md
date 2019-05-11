---
title: 纵向扩展 BizTalk Server 层 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, scaling
- scaling, examples
- scaling, scaling up
ms.assetid: 9002006a-f301-4e15-94b9-6caffd7c527c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6debecada3269374e2fd6f91a06d9e120c2538e6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308811"
---
# <a name="scaling-up-the-biztalk-server-tier"></a><span data-ttu-id="fe069-102">纵向扩展 BizTalk Server 层</span><span class="sxs-lookup"><span data-stu-id="fe069-102">Scaling Up the BizTalk Server Tier</span></span>
<span data-ttu-id="fe069-103">若要纵向扩展 BizTalk 层，你需要升级 CPU、 内存、 IO 和其他资源。</span><span class="sxs-lookup"><span data-stu-id="fe069-103">To scale up the BizTalk tier, you upgrade the CPU, memory, IO and other resources.</span></span> <span data-ttu-id="fe069-104">下图显示了如何您可能会纵向扩展 BizTalk 层从双处理器计算机为四个处理器的计算机的示例。</span><span class="sxs-lookup"><span data-stu-id="fe069-104">The following figure shows an example of how you might scale up the BizTalk tier from a two processor computer to a four processor computer.</span></span>  
  
 <span data-ttu-id="fe069-105">![缩放&#45;向上 BTS](../core/media/scaleupbts.gif "ScaleUpBTS")</span><span class="sxs-lookup"><span data-stu-id="fe069-105">![Scale&#45;up BTS](../core/media/scaleupbts.gif "ScaleUpBTS")</span></span>  
  
 <span data-ttu-id="fe069-106">纵向扩展 BizTalk 层的情况是类似于当您选择向外扩展：</span><span class="sxs-lookup"><span data-stu-id="fe069-106">The scenarios for scaling up your BizTalk tier are similar to when you choose to scale out:</span></span>  
  
-   <span data-ttu-id="fe069-107">BizTalk Server 成为瓶颈。</span><span class="sxs-lookup"><span data-stu-id="fe069-107">BizTalk Server becomes a bottleneck.</span></span> <span data-ttu-id="fe069-108">该瓶颈本身可能会造成以下问题之一导致:</span><span class="sxs-lookup"><span data-stu-id="fe069-108">The bottleneck itself may be caused by one of the following problems:</span></span>  
  
-   <span data-ttu-id="fe069-109">CPU:如果本方案使用 CPU 密集型管道、 映射或业务流程，BizTalk server 将没有任何额外的 CPU 余量。</span><span class="sxs-lookup"><span data-stu-id="fe069-109">CPU: If the scenario uses CPU intensive pipelines, maps, or orchestrations, the BizTalk servers will not have any extra CPU headroom.</span></span>  
  
-   <span data-ttu-id="fe069-110">内存和 I/O:如果现有计算机已达到其对内存和 IO 和要升级的计算机需要的最大限制。</span><span class="sxs-lookup"><span data-stu-id="fe069-110">Memory and I/O: If the existing computers have reached their maximum limit on memory and IO, and the computer needs to be upgraded.</span></span>  
  
-   <span data-ttu-id="fe069-111">向外扩展成本十分高昂。</span><span class="sxs-lookup"><span data-stu-id="fe069-111">Scaling out is too expensive.</span></span>  
  
-   <span data-ttu-id="fe069-112">如果是横向扩展不能解决瓶颈。</span><span class="sxs-lookup"><span data-stu-id="fe069-112">If scale-out does not address the bottleneck.</span></span> <span data-ttu-id="fe069-113">例如，向外扩展不能解决以下瓶颈问题：</span><span class="sxs-lookup"><span data-stu-id="fe069-113">For example, scaling out does not address the following bottlenecks:</span></span>  
  
    -   <span data-ttu-id="fe069-114">大消息转换</span><span class="sxs-lookup"><span data-stu-id="fe069-114">Large Message Transforms</span></span>  
  
    -   <span data-ttu-id="fe069-115">大量的每个交换的消息</span><span class="sxs-lookup"><span data-stu-id="fe069-115">Large number of messages per interchange</span></span>  
  
    -   <span data-ttu-id="fe069-116">某些 BTS 组件，例如，管道或适配器的高内存使用率</span><span class="sxs-lookup"><span data-stu-id="fe069-116">High memory utilization by some of BTS components, such as pipelines or adapters</span></span>  
  
    -   <span data-ttu-id="fe069-117">传输，例如 EDI</span><span class="sxs-lookup"><span data-stu-id="fe069-117">A transport, such as EDI</span></span>  
  
## <a name="when-you-cant-scale-up-the-biztalk-tier"></a><span data-ttu-id="fe069-118">当您无法纵向扩展 BizTalk 层</span><span class="sxs-lookup"><span data-stu-id="fe069-118">When You Can’t Scale Up the BizTalk Tier</span></span>  
  
-   <span data-ttu-id="fe069-119">MessageBox 数据库是瓶颈。</span><span class="sxs-lookup"><span data-stu-id="fe069-119">The MessageBox database is the bottleneck.</span></span>  
  
-   <span data-ttu-id="fe069-120">适配器成为瓶颈。</span><span class="sxs-lookup"><span data-stu-id="fe069-120">An adapter becomes the bottleneck.</span></span> <span data-ttu-id="fe069-121">例如，如果使用适配器后增加 BizTalk 接收器的数量，锁争用可能会增加在其中的 BizTalk 适配器从其请求数据的后端应用程序。</span><span class="sxs-lookup"><span data-stu-id="fe069-121">For example, if you are using an adapter, after you increase the number of BizTalk receivers, lock contention might increase on the backend application where the BizTalk adapter is pulling data from.</span></span> <span data-ttu-id="fe069-122">这将限制增加该适配器的能力。</span><span class="sxs-lookup"><span data-stu-id="fe069-122">This limits your ability to scale up the adapter.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe069-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="fe069-123">See Also</span></span>  
 <span data-ttu-id="fe069-124">[向外扩展 BizTalk Server 层](../core/scaling-out-the-biztalk-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="fe069-124">[Scaling Out the BizTalk Server Tier](../core/scaling-out-the-biztalk-server-tier.md) </span></span>  
 <span data-ttu-id="fe069-125">[纵向扩展 SQL Server 层](../core/scaling-up-the-sql-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="fe069-125">[Scaling Up the SQL Server Tier](../core/scaling-up-the-sql-server-tier.md) </span></span>  
 <span data-ttu-id="fe069-126">[SQL Server 层向外缩放](../core/scaling-out-the-sql-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="fe069-126">[Scaling Out the SQL Server Tier](../core/scaling-out-the-sql-server-tier.md) </span></span>  
 <span data-ttu-id="fe069-127">[向外扩展接收主机](../core/scaled-out-receiving-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="fe069-127">[Scaled-Out Receiving Hosts](../core/scaled-out-receiving-hosts.md) </span></span>  
 <span data-ttu-id="fe069-128">[向外扩展处理主机](../core/scaled-out-processing-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="fe069-128">[Scaled-Out Processing Hosts](../core/scaled-out-processing-hosts.md) </span></span>  
 <span data-ttu-id="fe069-129">[向外扩展发送主机](../core/scaled-out-sending-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="fe069-129">[Scaled-Out Sending Hosts](../core/scaled-out-sending-hosts.md) </span></span>  
 <span data-ttu-id="fe069-130">[使用 Windows Server 群集为 BizTalk Server 主机 2 提供高可用性](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="fe069-130">[Using Windows Server Cluster to Provide High Availability for BizTalk Server Hosts2](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span></span>  
 <span data-ttu-id="fe069-131">[向外扩展数据库](../core/scaled-out-databases.md) </span><span class="sxs-lookup"><span data-stu-id="fe069-131">[Scaled-Out Databases](../core/scaled-out-databases.md) </span></span>  
 [<span data-ttu-id="fe069-132">聚类分析 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="fe069-132">Clustering the BizTalk Server Databases</span></span>](../core/clustering-the-biztalk-server-databases1.md)