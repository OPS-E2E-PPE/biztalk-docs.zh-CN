---
title: 纵向扩展 SQL Server 层 |Microsoft Docs
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
- SQL Server, scaling
- scaling, scaling up
- scaling, strategies
ms.assetid: 4352c4af-6861-43d9-b433-9ca25668b439
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7642b09a9380dd33231fce7be85caee19e31a5fa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308708"
---
# <a name="scaling-up-the-sql-server-tier"></a><span data-ttu-id="de00d-102">纵向扩展 SQL Server 层</span><span class="sxs-lookup"><span data-stu-id="de00d-102">Scaling Up the SQL Server Tier</span></span>
<span data-ttu-id="de00d-103">在此模式下，现有 SQL MessageBox 数据库都将升级到根据吞吐量或延迟中要求的规模。</span><span class="sxs-lookup"><span data-stu-id="de00d-103">In this pattern, the existing SQL MessageBox database is upgraded to scale according to the requirements in throughput or latency.</span></span>  
  
 <span data-ttu-id="de00d-104">下图显示了主 MessageBox 数据库从 4 处理器服务器升级到 8 处理器服务器的方案。</span><span class="sxs-lookup"><span data-stu-id="de00d-104">The following figure shows a scenario where the master MessageBox database is upgraded from quad processor server to 8 processor server.</span></span>  
  
 <span data-ttu-id="de00d-105">![缩放&#45;向上 MSGBOX](../core/media/scaleupmsgbox2.gif "ScaleUpMsgBox2")</span><span class="sxs-lookup"><span data-stu-id="de00d-105">![Scale&#45;up MSGBOX](../core/media/scaleupmsgbox2.gif "ScaleUpMsgBox2")</span></span>  
  
## <a name="when-to-scale-up-the-sql-tier"></a><span data-ttu-id="de00d-106">何时向上扩展 SQL 层</span><span class="sxs-lookup"><span data-stu-id="de00d-106">When to Scale-up the SQL Tier</span></span>  
  
-   <span data-ttu-id="de00d-107">当您可以扩展主 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="de00d-107">When you can scale up the master MessageBox database.</span></span>  
  
-   <span data-ttu-id="de00d-108">当主 MessageBox 数据库成为瓶颈。</span><span class="sxs-lookup"><span data-stu-id="de00d-108">When the master MessageBox database becomes the bottleneck.</span></span> <span data-ttu-id="de00d-109">可以是这些瓶颈：</span><span class="sxs-lookup"><span data-stu-id="de00d-109">Those bottlenecks can be:</span></span>  
  
    -   <span data-ttu-id="de00d-110">**CPU**非常昂贵且复杂的业务流程方案，在消息框会占用大量 CPU 资源。</span><span class="sxs-lookup"><span data-stu-id="de00d-110">**CPU** In case of very expensive and complex orchestration scenarios, Message box consumes heavy CPU resources.</span></span> <span data-ttu-id="de00d-111">向上扩展 SQL server 通过添加更多的 Cpu 应缩放方案。</span><span class="sxs-lookup"><span data-stu-id="de00d-111">Scaling-up the SQL server by adding more CPUs should scale the scenario.</span></span>  
  
    -   <span data-ttu-id="de00d-112">**内存或 I/O**内存或 I/O 可能是瓶颈，并且可以升级。</span><span class="sxs-lookup"><span data-stu-id="de00d-112">**Memory or I/O** Memory or I/O can be bottleneck and can be upgraded.</span></span>  
  
-   <span data-ttu-id="de00d-113">当向上扩展是比向外扩展更便宜，向上扩展可以解决瓶颈问题。</span><span class="sxs-lookup"><span data-stu-id="de00d-113">When scaling-up is cheaper than scaling-out and scaling-up can address the bottleneck.</span></span> <span data-ttu-id="de00d-114">例如，如果主 MessageBox 数据库存在 SQL 锁争用问题，无法通过向上扩展来解决此问题。</span><span class="sxs-lookup"><span data-stu-id="de00d-114">For example, if the master MessageBox database has an issue with SQL lock contention, this issue cannot be solved by scaling-up.</span></span>  
  
## <a name="when-do-you-decide-sql-cannot-scale-up"></a><span data-ttu-id="de00d-115">何时确定 SQL 无法向上扩展？</span><span class="sxs-lookup"><span data-stu-id="de00d-115">When do you decide SQL cannot scale-up?</span></span>  
 <span data-ttu-id="de00d-116">向上扩展不能解决 SQL 层上的锁争用瓶颈。</span><span class="sxs-lookup"><span data-stu-id="de00d-116">Scale-up cannot address lock contention bottlenecks on the SQL tier.</span></span> <span data-ttu-id="de00d-117">如果命中这些类型的瓶颈，向外扩展是比向上扩展更好的选择。</span><span class="sxs-lookup"><span data-stu-id="de00d-117">If these kinds of bottlenecks are hit, scale-out is better option than scale-up.</span></span>  
  
## <a name="strategies-and-considerations-for-scaling-up-the-sql-tier"></a><span data-ttu-id="de00d-118">策略和纵向扩展 SQL 层的注意事项</span><span class="sxs-lookup"><span data-stu-id="de00d-118">Strategies and Considerations for Scaling Up the SQL Tier</span></span>  
  
-   <span data-ttu-id="de00d-119">向上扩展主 MessageBox 数据库第一次，然后向外扩展。</span><span class="sxs-lookup"><span data-stu-id="de00d-119">Scale-up the master MessageBox database first and then scale-out.</span></span>  
  
-   <span data-ttu-id="de00d-120">主 MessageBox 数据库最终会成为瓶颈。</span><span class="sxs-lookup"><span data-stu-id="de00d-120">The master MessageBox database will eventually be the bottleneck.</span></span> <span data-ttu-id="de00d-121">因此，主 MessageBox 数据库应更快、 更大 （例如，基于 Itanium 的 64 位或基于 x64 的双核计算机）。</span><span class="sxs-lookup"><span data-stu-id="de00d-121">So, the master MessageBox database should be faster and bigger (for example, an Itanium-based 64-bit or x64-based, dual core computer).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de00d-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="de00d-122">See Also</span></span>  
 <span data-ttu-id="de00d-123">[向外扩展 BizTalk Server 层](../core/scaling-out-the-biztalk-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="de00d-123">[Scaling Out the BizTalk Server Tier](../core/scaling-out-the-biztalk-server-tier.md) </span></span>  
 <span data-ttu-id="de00d-124">[纵向扩展 BizTalk Server 层](../core/scaling-up-the-biztalk-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="de00d-124">[Scaling Up the BizTalk Server Tier](../core/scaling-up-the-biztalk-server-tier.md) </span></span>  
 <span data-ttu-id="de00d-125">[SQL Server 层向外缩放](../core/scaling-out-the-sql-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="de00d-125">[Scaling Out the SQL Server Tier](../core/scaling-out-the-sql-server-tier.md) </span></span>  
 <span data-ttu-id="de00d-126">[向外扩展接收主机](../core/scaled-out-receiving-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="de00d-126">[Scaled-Out Receiving Hosts](../core/scaled-out-receiving-hosts.md) </span></span>  
 <span data-ttu-id="de00d-127">[向外扩展处理主机](../core/scaled-out-processing-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="de00d-127">[Scaled-Out Processing Hosts](../core/scaled-out-processing-hosts.md) </span></span>  
 <span data-ttu-id="de00d-128">[向外扩展发送主机](../core/scaled-out-sending-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="de00d-128">[Scaled-Out Sending Hosts](../core/scaled-out-sending-hosts.md) </span></span>  
 <span data-ttu-id="de00d-129">[使用 Windows Server 群集为 BizTalk Server 主机 2 提供高可用性](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="de00d-129">[Using Windows Server Cluster to Provide High Availability for BizTalk Server Hosts2](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span></span>  
 <span data-ttu-id="de00d-130">[向外扩展数据库](../core/scaled-out-databases.md) </span><span class="sxs-lookup"><span data-stu-id="de00d-130">[Scaled-Out Databases](../core/scaled-out-databases.md) </span></span>  
 [<span data-ttu-id="de00d-131">聚类分析 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="de00d-131">Clustering the BizTalk Server Databases</span></span>](../core/clustering-the-biztalk-server-databases1.md)