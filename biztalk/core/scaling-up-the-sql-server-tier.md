---
title: SQL Server 层向上缩放 |Microsoft 文档
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
ms.openlocfilehash: 6c654c4a3b1bba166ae8a49918f6ef31827cf041
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269677"
---
# <a name="scaling-up-the-sql-server-tier"></a><span data-ttu-id="a48ae-102">SQL Server 层向上扩展</span><span class="sxs-lookup"><span data-stu-id="a48ae-102">Scaling Up the SQL Server Tier</span></span>
<span data-ttu-id="a48ae-103">在此模式中，将根据吞吐量或延迟要求对现有 SQL MessageBox 数据库进行升级以实现扩展。</span><span class="sxs-lookup"><span data-stu-id="a48ae-103">In this pattern, the existing SQL MessageBox database is upgraded to scale according to the requirements in throughput or latency.</span></span>  
  
 <span data-ttu-id="a48ae-104">下图显示了一种将主 MessageBox 数据库从 4 处理器服务器升级到 8 处理器服务器的方案：</span><span class="sxs-lookup"><span data-stu-id="a48ae-104">The following figure shows a scenario where the master MessageBox database is upgraded from quad processor server to 8 processor server.</span></span>  
  
 <span data-ttu-id="a48ae-105">![缩放 &#45; 向上 MSGBOX](../core/media/scaleupmsgbox2.gif "ScaleUpMsgBox2")</span><span class="sxs-lookup"><span data-stu-id="a48ae-105">![Scale&#45;up MSGBOX](../core/media/scaleupmsgbox2.gif "ScaleUpMsgBox2")</span></span>  
  
## <a name="when-to-scale-up-the-sql-tier"></a><span data-ttu-id="a48ae-106">何时向上扩展 SQL 层</span><span class="sxs-lookup"><span data-stu-id="a48ae-106">When to Scale-up the SQL Tier</span></span>  
  
-   <span data-ttu-id="a48ae-107">当可向上扩展主 MessageBox 数据库时。</span><span class="sxs-lookup"><span data-stu-id="a48ae-107">When you can scale up the master MessageBox database.</span></span>  
  
-   <span data-ttu-id="a48ae-108">当主 MessageBox 数据库成为瓶颈时。</span><span class="sxs-lookup"><span data-stu-id="a48ae-108">When the master MessageBox database becomes the bottleneck.</span></span> <span data-ttu-id="a48ae-109">可以是那些瓶颈：</span><span class="sxs-lookup"><span data-stu-id="a48ae-109">Those bottlenecks can be:</span></span>  
  
    -   <span data-ttu-id="a48ae-110">**CPU**发生非常昂贵且复杂的业务流程方案中，消息框占用大量 CPU 资源。</span><span class="sxs-lookup"><span data-stu-id="a48ae-110">**CPU** In case of very expensive and complex orchestration scenarios, Message box consumes heavy CPU resources.</span></span> <span data-ttu-id="a48ae-111">通过添加更多的 CPU 来向上扩展 SQL 服务器可以对此方案进行扩展。</span><span class="sxs-lookup"><span data-stu-id="a48ae-111">Scaling-up the SQL server by adding more CPUs should scale the scenario.</span></span>  
  
    -   <span data-ttu-id="a48ae-112">**内存或 I/O**内存或 I/O 可能形成瓶颈和可升级。</span><span class="sxs-lookup"><span data-stu-id="a48ae-112">**Memory or I/O** Memory or I/O can be bottleneck and can be upgraded.</span></span>  
  
-   <span data-ttu-id="a48ae-113">当向上扩展比向外扩展成本更低，并且向上扩展可以解决瓶颈问题时。</span><span class="sxs-lookup"><span data-stu-id="a48ae-113">When scaling-up is cheaper than scaling-out and scaling-up can address the bottleneck.</span></span> <span data-ttu-id="a48ae-114">例如，如果主 MessageBox 数据库存在 SQL 锁争用问题，此问题无法通过向上扩展来解决。</span><span class="sxs-lookup"><span data-stu-id="a48ae-114">For example, if the master MessageBox database has an issue with SQL lock contention, this issue cannot be solved by scaling-up.</span></span>  
  
## <a name="when-do-you-decide-sql-cannot-scale-up"></a><span data-ttu-id="a48ae-115">何时确定 SQL 无法向上扩展？</span><span class="sxs-lookup"><span data-stu-id="a48ae-115">When do you decide SQL cannot scale-up?</span></span>  
 <span data-ttu-id="a48ae-116">向上扩展无法解决 SQL 层上的锁争用瓶颈。</span><span class="sxs-lookup"><span data-stu-id="a48ae-116">Scale-up cannot address lock contention bottlenecks on the SQL tier.</span></span> <span data-ttu-id="a48ae-117">如果遇到这些类型的瓶颈，向外扩展是比向上扩展更好的选择。</span><span class="sxs-lookup"><span data-stu-id="a48ae-117">If these kinds of bottlenecks are hit, scale-out is better option than scale-up.</span></span>  
  
## <a name="strategies-and-considerations-for-scaling-up-the-sql-tier"></a><span data-ttu-id="a48ae-118">策略和 SQL 层向上扩展的注意事项</span><span class="sxs-lookup"><span data-stu-id="a48ae-118">Strategies and Considerations for Scaling Up the SQL Tier</span></span>  
  
-   <span data-ttu-id="a48ae-119">首先向上扩展主 MessageBox 数据库，然后向外扩展。</span><span class="sxs-lookup"><span data-stu-id="a48ae-119">Scale-up the master MessageBox database first and then scale-out.</span></span>  
  
-   <span data-ttu-id="a48ae-120">Master MessageBox 数据库最终将瓶颈。</span><span class="sxs-lookup"><span data-stu-id="a48ae-120">The master MessageBox database will eventually be the bottleneck.</span></span> <span data-ttu-id="a48ae-121">因此，主 MessageBox 数据库应更快、更大（例如，采用基于 Itanium 的 64 位或基于 x64 的双核计算机）。</span><span class="sxs-lookup"><span data-stu-id="a48ae-121">So, the master MessageBox database should be faster and bigger (for example, an Itanium-based 64-bit or x64-based, dual core computer).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a48ae-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a48ae-122">See Also</span></span>  
 <span data-ttu-id="a48ae-123">[BizTalk Server 层向外缩放](../core/scaling-out-the-biztalk-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="a48ae-123">[Scaling Out the BizTalk Server Tier](../core/scaling-out-the-biztalk-server-tier.md) </span></span>  
 <span data-ttu-id="a48ae-124">[BizTalk Server 层向上扩展](../core/scaling-up-the-biztalk-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="a48ae-124">[Scaling Up the BizTalk Server Tier](../core/scaling-up-the-biztalk-server-tier.md) </span></span>  
 <span data-ttu-id="a48ae-125">[SQL Server 层向外缩放](../core/scaling-out-the-sql-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="a48ae-125">[Scaling Out the SQL Server Tier](../core/scaling-out-the-sql-server-tier.md) </span></span>  
 <span data-ttu-id="a48ae-126">[向外扩展接收主机](../core/scaled-out-receiving-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="a48ae-126">[Scaled-Out Receiving Hosts](../core/scaled-out-receiving-hosts.md) </span></span>  
 <span data-ttu-id="a48ae-127">[向外扩展的处理主机](../core/scaled-out-processing-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="a48ae-127">[Scaled-Out Processing Hosts](../core/scaled-out-processing-hosts.md) </span></span>  
 <span data-ttu-id="a48ae-128">[向外扩展的发送主机](../core/scaled-out-sending-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="a48ae-128">[Scaled-Out Sending Hosts](../core/scaled-out-sending-hosts.md) </span></span>  
 <span data-ttu-id="a48ae-129">[Windows Server 群集用于 BizTalk Server Hosts2 为提供高可用性](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="a48ae-129">[Using Windows Server Cluster to Provide High Availability for BizTalk Server Hosts2](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span></span>  
 <span data-ttu-id="a48ae-130">[向外扩展的数据库](../core/scaled-out-databases.md) </span><span class="sxs-lookup"><span data-stu-id="a48ae-130">[Scaled-Out Databases](../core/scaled-out-databases.md) </span></span>  
 [<span data-ttu-id="a48ae-131">群集的 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="a48ae-131">Clustering the BizTalk Server Databases</span></span>](../core/clustering-the-biztalk-server-databases1.md)