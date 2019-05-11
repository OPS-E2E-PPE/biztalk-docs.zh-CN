---
title: 向外扩展 BizTalk Server 层 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, scaling
- scaling, planning
- scaling, load balancing
- host instances, scaling
- scaling, examples
- fault tolerance
- scaling, scaling out
- scaling, fault tolerance
- NLB system, scaling
- scaling, host instances
ms.assetid: 01d1ab20-d7a9-4d0b-a61e-65e56fe5010e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e04050f1d7346f06d8b0d0a7163ac28f8d538f0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308970"
---
# <a name="scaling-out-the-biztalk-server-tier"></a><span data-ttu-id="23e7d-102">向外扩展 BizTalk Server 层</span><span class="sxs-lookup"><span data-stu-id="23e7d-102">Scaling Out the BizTalk Server Tier</span></span>
<span data-ttu-id="23e7d-103">若要横向扩展 BizTalk 层，请向现有拓扑添加更多的硬件。</span><span class="sxs-lookup"><span data-stu-id="23e7d-103">To scale out the BizTalk tier, add more hardware to the existing topology.</span></span> <span data-ttu-id="23e7d-104">建议在以下方案中添加硬件：</span><span class="sxs-lookup"><span data-stu-id="23e7d-104">It is recommended that you add hardware in the following scenarios:</span></span>  
  
- <span data-ttu-id="23e7d-105">BizTalk Server 成为瓶颈。</span><span class="sxs-lookup"><span data-stu-id="23e7d-105">BizTalk Server becomes a bottleneck.</span></span> <span data-ttu-id="23e7d-106">该瓶颈本身可能会造成以下问题之一导致:</span><span class="sxs-lookup"><span data-stu-id="23e7d-106">The bottleneck itself may be caused by one of the following problems:</span></span>  
  
- <span data-ttu-id="23e7d-107">CPU:如果本方案使用 CPU 密集型管道、 映射或业务流程，BizTalk server 将没有任何额外的 CPU 余量。</span><span class="sxs-lookup"><span data-stu-id="23e7d-107">CPU: If the scenario uses CPU intensive pipelines, maps, or orchestrations, the BizTalk servers will not have any extra CPU headroom.</span></span>  
  
- <span data-ttu-id="23e7d-108">内存和 I/O:如果现有计算机已达到其对内存和 IO 的最大限制，将资源添加的唯一方法是添加另一台物理计算机。</span><span class="sxs-lookup"><span data-stu-id="23e7d-108">Memory and I/O: If the existing computers have reached their maximum limit on memory and IO, the only way to add resources is to add another physical computer.</span></span>  
  
- <span data-ttu-id="23e7d-109">向上扩展成本十分高昂。</span><span class="sxs-lookup"><span data-stu-id="23e7d-109">Scaling up is too expensive.</span></span> <span data-ttu-id="23e7d-110">例如，考虑其中 BizTalk CPU 已达到最大容量的 1 BizTalk Server 拓扑。</span><span class="sxs-lookup"><span data-stu-id="23e7d-110">For example, consider the 1 BizTalk Server topology where the BizTalk CPU is at maximum capacity.</span></span> <span data-ttu-id="23e7d-111">如果它是更便宜，若要添加额外的双处理器计算机，而不是双处理器升级到四核处理器，则应改为横向低于系统。</span><span class="sxs-lookup"><span data-stu-id="23e7d-111">If it is cheaper to add extra dual processor machines instead of upgrading the dual processor to a quad processor, you should instead scale-outyour system.</span></span>  
  
- <span data-ttu-id="23e7d-112">向上扩展不能解决瓶颈。</span><span class="sxs-lookup"><span data-stu-id="23e7d-112">Scaling-up does not fix the bottleneck.</span></span> <span data-ttu-id="23e7d-113">向上扩展可能无法在以下方案中：</span><span class="sxs-lookup"><span data-stu-id="23e7d-113">Scaling up may not work in the following scenarios:</span></span>  
  
  -   <span data-ttu-id="23e7d-114">因此，您需要另一台计算机，以扩展 IO，IO 将是 BizTalk 计算机的最大级别。</span><span class="sxs-lookup"><span data-stu-id="23e7d-114">IO is at the maximum level for the BizTalk computer so you need another computer to scale the IO.</span></span>  
  
  -   <span data-ttu-id="23e7d-115">内存是在您的操作系统的最大级别。</span><span class="sxs-lookup"><span data-stu-id="23e7d-115">Memory is at the maximum level for your operating system.</span></span> <span data-ttu-id="23e7d-116">在此方案中，扩展您的系统的唯一方法是将额外的 BizTalk 计算机添加到拓扑。</span><span class="sxs-lookup"><span data-stu-id="23e7d-116">In this scenario, the only way to scale your system is to add an extra BizTalk computermachine to the topology.</span></span>  
  
  <span data-ttu-id="23e7d-117">在某些情况下，您可能希望用于接收消息、 发送消息，以及处理它们的专用的服务器。</span><span class="sxs-lookup"><span data-stu-id="23e7d-117">In some scenarios, you may want dedicated servers for receiving messages, sending messages, and processing them.</span></span> <span data-ttu-id="23e7d-118">如果具有专用的服务器，更加容易地解决问题并执行在一台计算机上的执行维护操作而不会影响其他。</span><span class="sxs-lookup"><span data-stu-id="23e7d-118">When you have dedicated servers, it is easier to isolate problems and do maintenance on one computer without impacting the others.</span></span> <span data-ttu-id="23e7d-119">您可以通过缩放添加这些计算机我们 BizTalk 层。</span><span class="sxs-lookup"><span data-stu-id="23e7d-119">You can add these computers by scaling our the BizTalk tier.</span></span>  
  
## <a name="when-you-cant-scale-out-the-biztalk-tier"></a><span data-ttu-id="23e7d-120">时，无法横向扩展 BizTalk 层</span><span class="sxs-lookup"><span data-stu-id="23e7d-120">When You Can’t Scale Out the BizTalk Tier</span></span>  
  
- <span data-ttu-id="23e7d-121">MessageBox 数据库是瓶颈。</span><span class="sxs-lookup"><span data-stu-id="23e7d-121">The MessageBox database is the bottleneck.</span></span>  
  
- <span data-ttu-id="23e7d-122">适配器成为瓶颈。</span><span class="sxs-lookup"><span data-stu-id="23e7d-122">An adapter becomes the bottleneck.</span></span> <span data-ttu-id="23e7d-123">例如，如果使用 SQL 适配器后增加 BizTalk 接收器的数量，锁争用现象会增加，BizTalk SQL 适配器从其请求数据的 SQL 数据库上。</span><span class="sxs-lookup"><span data-stu-id="23e7d-123">For example, if you are using the SQL adapter, after you increase the number of BizTalk receivers, lock contention increases on the SQL database where the BizTalk SQL adapter is pulling data from.</span></span> <span data-ttu-id="23e7d-124">这将限制你能够向外扩展 SQL 适配器。</span><span class="sxs-lookup"><span data-stu-id="23e7d-124">This limits your ability to scale out the SQL adapter.</span></span>  
  
  <span data-ttu-id="23e7d-125">下图显示了如何扩展 BizTalk 层的示例。</span><span class="sxs-lookup"><span data-stu-id="23e7d-125">The following figure shows an example of how you might scale out the BizTalk tier.</span></span>  
  
  <span data-ttu-id="23e7d-126">![Scaleout BTS](../core/media/scaleoutbts.gif "ScaleOutBTS")</span><span class="sxs-lookup"><span data-stu-id="23e7d-126">![Scaleout BTS](../core/media/scaleoutbts.gif "ScaleOutBTS")</span></span>  
  
  <span data-ttu-id="23e7d-127">此图显示了向外扩展 BizTalk 拓扑，从一台 BizTalk 服务器扩展到 2 个 BizTalk server。</span><span class="sxs-lookup"><span data-stu-id="23e7d-127">This figure shows a scaled-out BizTalk topology, scaling from one BizTalk server to 2 BizTalk servers.</span></span> <span data-ttu-id="23e7d-128">在一个 BizTalk server 拓扑中，三个主机实例共享 BizTalk 计算机资源。</span><span class="sxs-lookup"><span data-stu-id="23e7d-128">In the one BizTalk server topology, three host instances are sharing the BizTalk computer resources.</span></span> <span data-ttu-id="23e7d-129">在两个 BizTalk server 拓扑中，传输主机位于其他服务器，从而提高了吞吐量上。</span><span class="sxs-lookup"><span data-stu-id="23e7d-129">In the two BizTalk server topology, the transmit host is separated onto a different server, which achieves more throughput.</span></span>  
  
## <a name="considerations-when-scaling-out-the-biztalk-tier"></a><span data-ttu-id="23e7d-130">在缩放时的注意事项扩展 BizTalk 层</span><span class="sxs-lookup"><span data-stu-id="23e7d-130">Considerations When Scaling Out the BizTalk Tier</span></span>  
 <span data-ttu-id="23e7d-131">添加另一台 BizTalk Server 计算机之前，必须考虑以下问题：</span><span class="sxs-lookup"><span data-stu-id="23e7d-131">You must consider the following questions before you add another BizTalk Server computer:</span></span>  
  
#### <a name="how-do-i-configure-the-system-for-load-balancing-and-fault-tolerance-when-i-scale-out-the-biztalk-tier"></a><span data-ttu-id="23e7d-132">当我向外扩展 BizTalk 层时，如何配置负载平衡和容错能力的系统？</span><span class="sxs-lookup"><span data-stu-id="23e7d-132">How do I configure the system for load balancing and fault tolerance when I scale out the BizTalk tier?</span></span>  
 <span data-ttu-id="23e7d-133">负载平衡和容错技术的选择取决于在方案中使用的适配器。</span><span class="sxs-lookup"><span data-stu-id="23e7d-133">The selection of load balancing and fault tolerance technology depends on the adapter that is being used in the scenario.</span></span> <span data-ttu-id="23e7d-134">对于 SOAP 和 HTTP 适配器的建议的方法是使用 NLB。</span><span class="sxs-lookup"><span data-stu-id="23e7d-134">For SOAP and HTTP adapters, the recommended way is to use NLB.</span></span> <span data-ttu-id="23e7d-135">请参阅 NLB 文档的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="23e7d-135">Refer to NLB documentation for more details.</span></span>  
  
#### <a name="how-do-i-refactor-the-host-instances"></a><span data-ttu-id="23e7d-136">如何重构主机实例？</span><span class="sxs-lookup"><span data-stu-id="23e7d-136">How do I refactor the host instances?</span></span>  
 <span data-ttu-id="23e7d-137">没有一个规则以确定如何应重构主机实例时，横向扩展 BizTalk 层。</span><span class="sxs-lookup"><span data-stu-id="23e7d-137">There is no one rule to determine how you should refactor the host instances when you scale out the BizTalk tier.</span></span> <span data-ttu-id="23e7d-138">何时重构主机实例取决于方案的复杂性。</span><span class="sxs-lookup"><span data-stu-id="23e7d-138">When you factor the host instances depends on the complexity of scenario.</span></span> <span data-ttu-id="23e7d-139">以下是一些示例如何重构主机实例。</span><span class="sxs-lookup"><span data-stu-id="23e7d-139">Following are some examples how to factor the host instances.</span></span>  
  
##### <a name="scenario-1"></a><span data-ttu-id="23e7d-140">方案 1</span><span class="sxs-lookup"><span data-stu-id="23e7d-140">Scenario 1</span></span>  
 <span data-ttu-id="23e7d-141">一个 BizTalk server 配置，并接收和传输的主机实例是同一台计算机。</span><span class="sxs-lookup"><span data-stu-id="23e7d-141">One BizTalk server configuration, and receive and transmit host instances are on the same computer.</span></span>  
  
 <span data-ttu-id="23e7d-142">假定存在 CPU 瓶颈。</span><span class="sxs-lookup"><span data-stu-id="23e7d-142">Assume there is a CPU bottleneck.</span></span> <span data-ttu-id="23e7d-143">将另一台相同的 BizTalk 计算机添加到该组中以横向扩展，为您提供两种方法来重构主机实例。</span><span class="sxs-lookup"><span data-stu-id="23e7d-143">You add another identical BizTalk computer to the group to scale-out, giving you two ways to factor the host instances.</span></span>  
  
 <span data-ttu-id="23e7d-144">下面是此问题的两个解决方案：</span><span class="sxs-lookup"><span data-stu-id="23e7d-144">Here are two solutions to this problem:</span></span>  
  
- <span data-ttu-id="23e7d-145">**解决方案 1**:在此方案中分解的最简单的方法是克隆将主机实例结构从第一台计算机到第二台计算机。</span><span class="sxs-lookup"><span data-stu-id="23e7d-145">**Solution 1**: The easiest way of factoring in this scenario is to clone the host instance factoring from first computer to second computer.</span></span> <span data-ttu-id="23e7d-146">因此，第二台计算机是第一个完全相同的副本在这样的功能。它还可以同时具有接收和发送主机。</span><span class="sxs-lookup"><span data-stu-id="23e7d-146">So, the second computer is an exact copy of the first in term of functionality; it can also have both receive and send hosts.</span></span> <span data-ttu-id="23e7d-147">假定不没有其他任何瓶颈，如 CPU 资源会增加一倍可能会收到扩展因子为 2。</span><span class="sxs-lookup"><span data-stu-id="23e7d-147">Assuming there is no other bottleneck, you may get a scaling factor of 2 as the CPU resources are doubled.</span></span>  
  
- <span data-ttu-id="23e7d-148">**解决方案 2**:另一种方法来重构主机实例是隔离的接收和发送到不同的计算机上的函数。</span><span class="sxs-lookup"><span data-stu-id="23e7d-148">**Solution 2**: Another way to factor the host instances is to isolate the receive and send functions onto different computers.</span></span> <span data-ttu-id="23e7d-149">因此，BizTalk 服务器之一是专用于接收和发送其他。</span><span class="sxs-lookup"><span data-stu-id="23e7d-149">So, one of the BizTalk servers is dedicated for receiving and other for sending.</span></span>  
  
  <span data-ttu-id="23e7d-150">**比较解决方案 1 和 2 的解决方案**</span><span class="sxs-lookup"><span data-stu-id="23e7d-150">**Comparing Solution 1 and Solution 2**</span></span>  
  
  <span data-ttu-id="23e7d-151">在解决方案 1 中，主机实例数的增加一倍从 bts 构成的配置。</span><span class="sxs-lookup"><span data-stu-id="23e7d-151">In solution 1, the number of host instances is doubled from 1 BTS configuration.</span></span> <span data-ttu-id="23e7d-152">这意味着 SQL 服务器上的锁争用现象将增加。</span><span class="sxs-lookup"><span data-stu-id="23e7d-152">This means that lock contention on the SQL server will increase.</span></span> <span data-ttu-id="23e7d-153">锁争用现象的增加量将确定扩展因子。</span><span class="sxs-lookup"><span data-stu-id="23e7d-153">How much it increases in lock contention will determine the scaling factor.</span></span> <span data-ttu-id="23e7d-154">如果锁争用成为瓶颈的限制范围内良好，可以看到扩展因子为 2。</span><span class="sxs-lookup"><span data-stu-id="23e7d-154">If the lock contention is well within limits of becoming a bottleneck, you can see a scaling factor of 2.</span></span>  
  
  <span data-ttu-id="23e7d-155">解决方案 2 的优点是有只有两个主机实例，以便在 SQL server 上的锁争用现象应少于解决方案 1。</span><span class="sxs-lookup"><span data-stu-id="23e7d-155">The advantage of solution 2 is that you have only two host instances, so the lock contention on the SQL server should be less compared to solution 1.</span></span> <span data-ttu-id="23e7d-156">但是，扩展因子完全取决于接收的复杂性和发送主机实例。</span><span class="sxs-lookup"><span data-stu-id="23e7d-156">But, the scaling factor depends completely on the complexity of the receive and send host instances.</span></span> <span data-ttu-id="23e7d-157">请考虑以下情况中的解决方案 2:</span><span class="sxs-lookup"><span data-stu-id="23e7d-157">Consider the following cases in solution 2:</span></span>  
  
  <span data-ttu-id="23e7d-158">假定这两个接收和传输主机实例在同样密集型的它们都在一个 BizTalk server 拓扑使用 50%的 CPU。</span><span class="sxs-lookup"><span data-stu-id="23e7d-158">Assume that both the receive and transmit host instances are equally intensive and they each use 50% of the CPU in the one BizTalk server topology.</span></span> <span data-ttu-id="23e7d-159">在两个 BizTalk server 拓扑中，将传输主机实例移到其他计算机上，并且现在都接收和传输获得双倍的资源。</span><span class="sxs-lookup"><span data-stu-id="23e7d-159">In the two BizTalk server topology, you move the transmit host instance to different computer, and now both receive and transmit get double the resources.</span></span> <span data-ttu-id="23e7d-160">这会提供扩展因子为 2，假定不没有其他任何瓶颈。</span><span class="sxs-lookup"><span data-stu-id="23e7d-160">This should provide a scaling factor of 2, assuming that there is no other bottleneck.</span></span> <span data-ttu-id="23e7d-161">因为只有两个主机实例，从而减少了锁争用，这种情况下是优于解决方案 1。</span><span class="sxs-lookup"><span data-stu-id="23e7d-161">This case is better than Solution 1 because there are only two host instances and hence les lock contention.</span></span>  
  
  <span data-ttu-id="23e7d-162">假定的传输方式多于接收所占用和一个 BizTalk server 拓扑中使用 80%的 CPU 资源。</span><span class="sxs-lookup"><span data-stu-id="23e7d-162">Assume that transmit is way more intensive than receive, and uses 80% CPU resources in the one BizTalk server topology.</span></span> <span data-ttu-id="23e7d-163">通过将传输主机实例移动到另一台计算机，您将了解只有 20%的 CPU 资源，因此最大扩展因子将为 1.2。</span><span class="sxs-lookup"><span data-stu-id="23e7d-163">By moving the transmit host instance to another machine, you gain only 20% more CPU resources so the maximum scaling factor will be 1.2.</span></span> <span data-ttu-id="23e7d-164">此外，具有接收主机实例的计算机将仅 20-30%的 CPU 资源，因此向外扩展的优点是要少得多。</span><span class="sxs-lookup"><span data-stu-id="23e7d-164">Moreover, the computer with the receive host instance will use only 20-30% CPU resources so the advantage of scaling-out is much less.</span></span>  
  
  <span data-ttu-id="23e7d-165">请考虑下图中包含四个 BizTalk server。</span><span class="sxs-lookup"><span data-stu-id="23e7d-165">Consider the following figure that has four BizTalk servers.</span></span> <span data-ttu-id="23e7d-166">每台计算机都收件人和发件人，为您提供的每种类型的四个主机实例的总计 （接收和传输）。</span><span class="sxs-lookup"><span data-stu-id="23e7d-166">Each computer is both receiver and sender, giving you a  total of four host instances of each type (receive and transmit).</span></span>  
  
  <span data-ttu-id="23e7d-167">![Re&#45;重构主机实例](../core/media/refactoringhostinstances.gif "RefactoringHostinstances")</span><span class="sxs-lookup"><span data-stu-id="23e7d-167">![Re&#45;factoring host instances](../core/media/refactoringhostinstances.gif "RefactoringHostinstances")</span></span>  
  
  <span data-ttu-id="23e7d-168">此拓扑可能不是最可能一个可能的。</span><span class="sxs-lookup"><span data-stu-id="23e7d-168">This topology might not be the best possible one possible.</span></span> <span data-ttu-id="23e7d-169">您还应测试其他重构排列，具体取决于方案的复杂性。</span><span class="sxs-lookup"><span data-stu-id="23e7d-169">You should also test other factoring permutations, depending on the complexity of scenario.</span></span> <span data-ttu-id="23e7d-170">例如：</span><span class="sxs-lookup"><span data-stu-id="23e7d-170">For example:</span></span>  
  
- <span data-ttu-id="23e7d-171">将专用于接收的两台计算机和两个用于传输。</span><span class="sxs-lookup"><span data-stu-id="23e7d-171">Dedicate two computers for receiving and  two for transmitting.</span></span> <span data-ttu-id="23e7d-172">这将使您最可能的缩放，这两个接收和发送是同样密集型时。</span><span class="sxs-lookup"><span data-stu-id="23e7d-172">This will give you the best possible scaling when both receive and send are equally intensive.</span></span>  
  
- <span data-ttu-id="23e7d-173">将专用三个三台接收，另一个用于传输，如果接收是比传输更密集。</span><span class="sxs-lookup"><span data-stu-id="23e7d-173">Dedicate three computersfor receiving and one for transmitting, if receiving is more intensive than transmit.</span></span>  
  
- <span data-ttu-id="23e7d-174">将专用一台计算机用于接收和传输如果传输为多于接收更密集的三个。</span><span class="sxs-lookup"><span data-stu-id="23e7d-174">Dedicate one computer for receive and three for transmitting if transmitting is more intensive than receive.</span></span>  
  
  <span data-ttu-id="23e7d-175">在所有情况下，建议尽量减少每个主机的主机实例的数量，以便减少 MessageBox 数据库上的争用，并在相同时使用的计算机资源是最充分地使用。</span><span class="sxs-lookup"><span data-stu-id="23e7d-175">In all scenarios, it is recommended that you minimize the number of host instances of each host so that contention on the MessageBox database is reduced and at the same time use the computer resources are use to the fullest.</span></span> <span data-ttu-id="23e7d-176">最佳的重构排列取决于方案和瓶颈类型的复杂程度。</span><span class="sxs-lookup"><span data-stu-id="23e7d-176">The best factoring permutation depends on the complexity of scenario and type of bottleneck.</span></span> <span data-ttu-id="23e7d-177">始终对重构进行测试之前最终确定排列。</span><span class="sxs-lookup"><span data-stu-id="23e7d-177">Always test your factoring before you finalize a permutation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23e7d-178">请参阅</span><span class="sxs-lookup"><span data-stu-id="23e7d-178">See Also</span></span>  
 <span data-ttu-id="23e7d-179">[纵向扩展 BizTalk Server 层](../core/scaling-up-the-biztalk-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="23e7d-179">[Scaling Up the BizTalk Server Tier](../core/scaling-up-the-biztalk-server-tier.md) </span></span>  
 <span data-ttu-id="23e7d-180">[纵向扩展 SQL Server 层](../core/scaling-up-the-sql-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="23e7d-180">[Scaling Up the SQL Server Tier](../core/scaling-up-the-sql-server-tier.md) </span></span>  
 <span data-ttu-id="23e7d-181">[SQL Server 层向外缩放](../core/scaling-out-the-sql-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="23e7d-181">[Scaling Out the SQL Server Tier](../core/scaling-out-the-sql-server-tier.md) </span></span>  
 <span data-ttu-id="23e7d-182">[向外扩展接收主机](../core/scaled-out-receiving-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="23e7d-182">[Scaled-Out Receiving Hosts](../core/scaled-out-receiving-hosts.md) </span></span>  
 <span data-ttu-id="23e7d-183">[向外扩展处理主机](../core/scaled-out-processing-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="23e7d-183">[Scaled-Out Processing Hosts](../core/scaled-out-processing-hosts.md) </span></span>  
 <span data-ttu-id="23e7d-184">[向外扩展发送主机](../core/scaled-out-sending-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="23e7d-184">[Scaled-Out Sending Hosts](../core/scaled-out-sending-hosts.md) </span></span>  
 <span data-ttu-id="23e7d-185">[使用 Windows Server 群集为 BizTalk Server 主机 2 提供高可用性](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="23e7d-185">[Using Windows Server Cluster to Provide High Availability for BizTalk Server Hosts2](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span></span>  
 <span data-ttu-id="23e7d-186">[向外扩展数据库](../core/scaled-out-databases.md) </span><span class="sxs-lookup"><span data-stu-id="23e7d-186">[Scaled-Out Databases](../core/scaled-out-databases.md) </span></span>  
 [<span data-ttu-id="23e7d-187">聚类分析 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="23e7d-187">Clustering the BizTalk Server Databases</span></span>](../core/clustering-the-biztalk-server-databases1.md)