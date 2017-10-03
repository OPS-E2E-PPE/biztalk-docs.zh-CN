---
title: "BizTalk Server 层向外缩放 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 35674e89d8f8104a35718531f2a87f95e8bc67e6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="scaling-out-the-biztalk-server-tier"></a><span data-ttu-id="61b03-102">向外扩展 BizTalk Server 层</span><span class="sxs-lookup"><span data-stu-id="61b03-102">Scaling Out the BizTalk Server Tier</span></span>
<span data-ttu-id="61b03-103">为扩展 BizTalk 层，应向现有拓扑结构添加其他硬件。</span><span class="sxs-lookup"><span data-stu-id="61b03-103">To scale out the BizTalk tier, add more hardware to the existing topology.</span></span> <span data-ttu-id="61b03-104">如果出现以下情况，则建议您添加硬件：</span><span class="sxs-lookup"><span data-stu-id="61b03-104">It is recommended that you add hardware in the following scenarios:</span></span>  
  
-   <span data-ttu-id="61b03-105">BizTalk Server 成为瓶颈。</span><span class="sxs-lookup"><span data-stu-id="61b03-105">BizTalk Server becomes a bottleneck.</span></span> <span data-ttu-id="61b03-106">该瓶颈本身可能是由于以下问题之一而导致的：</span><span class="sxs-lookup"><span data-stu-id="61b03-106">The bottleneck itself may be caused by one of the following problems:</span></span>  
  
-   <span data-ttu-id="61b03-107">CPU： 如果本方案使用 CPU 密集型管道、 地图或业务流程，BizTalk 服务器将不具有任何额外的 CPU 预留空间。</span><span class="sxs-lookup"><span data-stu-id="61b03-107">CPU: If the scenario uses CPU intensive pipelines, maps, or orchestrations, the BizTalk servers will not have any extra CPU headroom.</span></span>  
  
-   <span data-ttu-id="61b03-108">内存和 I/O：如果现有计算机已达到其对内存和 IO 的最大限制，则添加资源的唯一方法是添加其他物理计算机。</span><span class="sxs-lookup"><span data-stu-id="61b03-108">Memory and I/O: If the existing computers have reached their maximum limit on memory and IO, the only way to add resources is to add another physical computer.</span></span>  
  
-   <span data-ttu-id="61b03-109">向上扩展的成本十分高昂。</span><span class="sxs-lookup"><span data-stu-id="61b03-109">Scaling up is too expensive.</span></span> <span data-ttu-id="61b03-110">例如，假设一个 BizTalk Server 拓扑结构中 BizTalk CPU 已达到其最高容量。</span><span class="sxs-lookup"><span data-stu-id="61b03-110">For example, consider the 1 BizTalk Server topology where the BizTalk CPU is at maximum capacity.</span></span> <span data-ttu-id="61b03-111">如果添加额外的双处理器计算机的成本低于将双处理器升级到四处理器的成本，则应当改为扩展您的系统。</span><span class="sxs-lookup"><span data-stu-id="61b03-111">If it is cheaper to add extra dual processor machines instead of upgrading the dual processor to a quad processor, you should instead scale-outyour system.</span></span>  
  
-   <span data-ttu-id="61b03-112">向上扩展没有解决瓶颈。</span><span class="sxs-lookup"><span data-stu-id="61b03-112">Scaling-up does not fix the bottleneck.</span></span> <span data-ttu-id="61b03-113">在以下情况中，向上扩展可能不起作用：</span><span class="sxs-lookup"><span data-stu-id="61b03-113">Scaling up may not work in the following scenarios:</span></span>  
  
    -   <span data-ttu-id="61b03-114">IO 达到 BizTalk 计算机允许的最大级别，因此需要其他计算机以扩展 IO。</span><span class="sxs-lookup"><span data-stu-id="61b03-114">IO is at the maximum level for the BizTalk computer so you need another computer to scale the IO.</span></span>  
  
    -   <span data-ttu-id="61b03-115">内存达到操作系统允许的最大级别。</span><span class="sxs-lookup"><span data-stu-id="61b03-115">Memory is at the maximum level for your operating system.</span></span> <span data-ttu-id="61b03-116">在这种情况下，扩展系统的唯一方法是向拓扑结构添加额外的 BizTalk 计算机。</span><span class="sxs-lookup"><span data-stu-id="61b03-116">In this scenario, the only way to scale your system is to add an extra BizTalk computermachine to the topology.</span></span>  
  
 <span data-ttu-id="61b03-117">在某些情况下，您可能需要专用的服务器来分别进行消息接收、消息发送和消息处理。</span><span class="sxs-lookup"><span data-stu-id="61b03-117">In some scenarios, you may want dedicated servers for receiving messages, sending messages, and processing them.</span></span> <span data-ttu-id="61b03-118">如果具有专用的服务器，则可以更容易地解决问题并在不影响其他计算机的情况下维护计算机。</span><span class="sxs-lookup"><span data-stu-id="61b03-118">When you have dedicated servers, it is easier to isolate problems and do maintenance on one computer without impacting the others.</span></span> <span data-ttu-id="61b03-119">您可以通过扩展 BizTalk 层来添加这些计算机。</span><span class="sxs-lookup"><span data-stu-id="61b03-119">You can add these computers by scaling our the BizTalk tier.</span></span>  
  
## <a name="when-you-cant-scale-out-the-biztalk-tier"></a><span data-ttu-id="61b03-120">当你不能向外缩放 BizTalk 层</span><span class="sxs-lookup"><span data-stu-id="61b03-120">When You Can’t Scale Out the BizTalk Tier</span></span>  
  
-   <span data-ttu-id="61b03-121">MessageBox 数据库是瓶颈。</span><span class="sxs-lookup"><span data-stu-id="61b03-121">The MessageBox database is the bottleneck.</span></span>  
  
-   <span data-ttu-id="61b03-122">适配器成为瓶颈。</span><span class="sxs-lookup"><span data-stu-id="61b03-122">An adapter becomes the bottleneck.</span></span> <span data-ttu-id="61b03-123">例如，如果使用的是 SQL 适配器，则在增加 BizTalk 接收器的数目后，BizTalk SQL 适配器从其请求数据的 SQL 数据库上的锁争用现象会增加。</span><span class="sxs-lookup"><span data-stu-id="61b03-123">For example, if you are using the SQL adapter, after you increase the number of BizTalk receivers, lock contention increases on the SQL database where the BizTalk SQL adapter is pulling data from.</span></span> <span data-ttu-id="61b03-124">这样限制了扩展 SQL 适配器的能力。</span><span class="sxs-lookup"><span data-stu-id="61b03-124">This limits your ability to scale out the SQL adapter.</span></span>  
  
 <span data-ttu-id="61b03-125">下图显示了如何扩展 BizTalk 层的示例：</span><span class="sxs-lookup"><span data-stu-id="61b03-125">The following figure shows an example of how you might scale out the BizTalk tier.</span></span>  
  
 <span data-ttu-id="61b03-126">![向外缩放 BTS](../core/media/scaleoutbts.gif "ScaleOutBTS")</span><span class="sxs-lookup"><span data-stu-id="61b03-126">![Scaleout BTS](../core/media/scaleoutbts.gif "ScaleOutBTS")</span></span>  
  
 <span data-ttu-id="61b03-127">此图显示了一个经过扩展的 BizTalk 拓扑结构，该拓扑结构从一个 BizTalk Server 扩展到 2 个 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="61b03-127">This figure shows a scaled-out BizTalk topology, scaling from one BizTalk server to 2 BizTalk servers.</span></span> <span data-ttu-id="61b03-128">在由一个 BizTalk Server 构成的拓扑结构中，三个主机实例共享 BizTalk 计算机资源。</span><span class="sxs-lookup"><span data-stu-id="61b03-128">In the one BizTalk server topology, three host instances are sharing the BizTalk computer resources.</span></span> <span data-ttu-id="61b03-129">在由两个 BizTalk Server 构成的拓扑结构中，传输主机位于其他服务器上，从而提高了吞吐量。</span><span class="sxs-lookup"><span data-stu-id="61b03-129">In the two BizTalk server topology, the transmit host is separated onto a different server, which achieves more throughput.</span></span>  
  
## <a name="considerations-when-scaling-out-the-biztalk-tier"></a><span data-ttu-id="61b03-130">在缩放时的注意事项 Out BizTalk 层</span><span class="sxs-lookup"><span data-stu-id="61b03-130">Considerations When Scaling Out the BizTalk Tier</span></span>  
 <span data-ttu-id="61b03-131">在添加其他 BizTalk Server 计算机之前，必须考虑以下问题：</span><span class="sxs-lookup"><span data-stu-id="61b03-131">You must consider the following questions before you add another BizTalk Server computer:</span></span>  
  
#### <a name="how-do-i-configure-the-system-for-load-balancing-and-fault-tolerance-when-i-scale-out-the-biztalk-tier"></a><span data-ttu-id="61b03-132">在扩展 BizTalk 层时，如何对系统进行配置以实现负载平衡和容错？</span><span class="sxs-lookup"><span data-stu-id="61b03-132">How do I configure the system for load balancing and fault tolerance when I scale out the BizTalk tier?</span></span>  
 <span data-ttu-id="61b03-133">负载平衡和容错技术的选择取决于具体情况下要使用的适配器。</span><span class="sxs-lookup"><span data-stu-id="61b03-133">The selection of load balancing and fault tolerance technology depends on the adapter that is being used in the scenario.</span></span> <span data-ttu-id="61b03-134">对于 SOAP 和 HTTP 适配器，建议使用 NLB。</span><span class="sxs-lookup"><span data-stu-id="61b03-134">For SOAP and HTTP adapters, the recommended way is to use NLB.</span></span> <span data-ttu-id="61b03-135">有关详细信息，请参阅 NLB 文档。</span><span class="sxs-lookup"><span data-stu-id="61b03-135">Refer to NLB documentation for more details.</span></span>  
  
#### <a name="how-do-i-refactor-the-host-instances"></a><span data-ttu-id="61b03-136">如何重构主机实例？</span><span class="sxs-lookup"><span data-stu-id="61b03-136">How do I refactor the host instances?</span></span>  
 <span data-ttu-id="61b03-137">没有统一的规则可确定在扩展 BizTalk 层时应重构主机实例的方式。</span><span class="sxs-lookup"><span data-stu-id="61b03-137">There is no one rule to determine how you should refactor the host instances when you scale out the BizTalk tier.</span></span> <span data-ttu-id="61b03-138">何时重构主机实例，这取决于具体情况的复杂度。</span><span class="sxs-lookup"><span data-stu-id="61b03-138">When you factor the host instances depends on the complexity of scenario.</span></span> <span data-ttu-id="61b03-139">下面是一些如何重构主机实例的示例。</span><span class="sxs-lookup"><span data-stu-id="61b03-139">Following are some examples how to factor the host instances.</span></span>  
  
##### <a name="scenario-1"></a><span data-ttu-id="61b03-140">方案 1</span><span class="sxs-lookup"><span data-stu-id="61b03-140">Scenario 1</span></span>  
 <span data-ttu-id="61b03-141">一个 BizTalk server 配置，并接收和发送实例位于同一台计算机的主机。</span><span class="sxs-lookup"><span data-stu-id="61b03-141">One BizTalk server configuration, and receive and transmit host instances are on the same computer.</span></span>  
  
 <span data-ttu-id="61b03-142">假定存在 CPU 瓶颈。</span><span class="sxs-lookup"><span data-stu-id="61b03-142">Assume there is a CPU bottleneck.</span></span> <span data-ttu-id="61b03-143">如果将另一台相同的 BizTalk 计算机添加到该组中以进行扩展，您可以通过两种方法来重构主机实例。</span><span class="sxs-lookup"><span data-stu-id="61b03-143">You add another identical BizTalk computer to the group to scale-out, giving you two ways to factor the host instances.</span></span>  
  
 <span data-ttu-id="61b03-144">下面列出了此问题的两个解决方案：</span><span class="sxs-lookup"><span data-stu-id="61b03-144">Here are two solutions to this problem:</span></span>  
  
-   <span data-ttu-id="61b03-145">**解决方案 1**： 在此方案中分解的最简单方法是克隆主机实例将分解从第一台计算机到另一台计算机。</span><span class="sxs-lookup"><span data-stu-id="61b03-145">**Solution 1**: The easiest way of factoring in this scenario is to clone the host instance factoring from first computer to second computer.</span></span> <span data-ttu-id="61b03-146">因此，在功能方面，第二台计算机是第一台计算机的完整副本；它也可以同时具有接收主机和发送主机。</span><span class="sxs-lookup"><span data-stu-id="61b03-146">So, the second computer is an exact copy of the first in term of functionality; it can also have both receive and send hosts.</span></span> <span data-ttu-id="61b03-147">假设不存在其他任何瓶颈，则可以获得扩展因子 2，因为 CPU 资源增加了一倍。</span><span class="sxs-lookup"><span data-stu-id="61b03-147">Assuming there is no other bottleneck, you may get a scaling factor of 2 as the CPU resources are doubled.</span></span>  
  
-   <span data-ttu-id="61b03-148">**解决方案 2**： 考虑主机实例的另一种方法是来隔离接收和发送函数拖放到不同的计算机。</span><span class="sxs-lookup"><span data-stu-id="61b03-148">**Solution 2**: Another way to factor the host instances is to isolate the receive and send functions onto different computers.</span></span> <span data-ttu-id="61b03-149">因此，其中一个 BizTalk Server 将专用于接收，另一个 BizTalk Server 则专用于发送。</span><span class="sxs-lookup"><span data-stu-id="61b03-149">So, one of the BizTalk servers is dedicated for receiving and other for sending.</span></span>  
  
 <span data-ttu-id="61b03-150">**比较解决方案 1 和解决方案 2**</span><span class="sxs-lookup"><span data-stu-id="61b03-150">**Comparing Solution 1 and Solution 2**</span></span>  
  
 <span data-ttu-id="61b03-151">在解决方案 1 中，主机实例数是由一个 BTS 构成的配置的两倍。</span><span class="sxs-lookup"><span data-stu-id="61b03-151">In solution 1, the number of host instances is doubled from 1 BTS configuration.</span></span> <span data-ttu-id="61b03-152">这意味着 SQL 服务器上的锁争用现象将增加。</span><span class="sxs-lookup"><span data-stu-id="61b03-152">This means that lock contention on the SQL server will increase.</span></span> <span data-ttu-id="61b03-153">锁争用现象的增加量将确定扩展因子。</span><span class="sxs-lookup"><span data-stu-id="61b03-153">How much it increases in lock contention will determine the scaling factor.</span></span> <span data-ttu-id="61b03-154">如果锁争用尚未超过成为瓶颈的限制，则扩展因子为 2。</span><span class="sxs-lookup"><span data-stu-id="61b03-154">If the lock contention is well within limits of becoming a bottleneck, you can see a scaling factor of 2.</span></span>  
  
 <span data-ttu-id="61b03-155">解决方案 2 的优点是，你拥有只有两个主机实例，以便在 SQL server 上的锁争用应小于相比解决方案 1。</span><span class="sxs-lookup"><span data-stu-id="61b03-155">The advantage of solution 2 is that you have only two host instances, so the lock contention on the SQL server should be less compared to solution 1.</span></span> <span data-ttu-id="61b03-156">但是，缩放因子完全依赖于接收的复杂性和发送主机实例。</span><span class="sxs-lookup"><span data-stu-id="61b03-156">But, the scaling factor depends completely on the complexity of the receive and send host instances.</span></span> <span data-ttu-id="61b03-157">假设在解决方案 2 中存在以下情况：</span><span class="sxs-lookup"><span data-stu-id="61b03-157">Consider the following cases in solution 2:</span></span>  
  
 <span data-ttu-id="61b03-158">假设接收主机实例和传输主机实例占用同样多的系统资源，在由一个 BizTalk Server 构成的拓扑结构中它们分别使用 50% 的 CPU。</span><span class="sxs-lookup"><span data-stu-id="61b03-158">Assume that both the receive and transmit host instances are equally intensive and they each use 50% of the CPU in the one BizTalk server topology.</span></span> <span data-ttu-id="61b03-159">在由两个 BizTalk Server 构成的拓扑结构中，您将传输主机实例移至其他计算机上，现在，传输和接收都将获得双倍的资源。</span><span class="sxs-lookup"><span data-stu-id="61b03-159">In the two BizTalk server topology, you move the transmit host instance to different computer, and now both receive and transmit get double the resources.</span></span> <span data-ttu-id="61b03-160">这样，假设不存在其他任何瓶颈，则扩展因子应为 2。</span><span class="sxs-lookup"><span data-stu-id="61b03-160">This should provide a scaling factor of 2, assuming that there is no other bottleneck.</span></span> <span data-ttu-id="61b03-161">这种情况优于解决方案 1，因为只存在两个主机实例，从而减少了锁争用。</span><span class="sxs-lookup"><span data-stu-id="61b03-161">This case is better than Solution 1 because there are only two host instances and hence les lock contention.</span></span>  
  
 <span data-ttu-id="61b03-162">假设传输占用的系统资源多于接收所占用的资源，在由一个 BizTalk Server 构成的拓扑结构中传输使用了 80% 的 CPU 资源。</span><span class="sxs-lookup"><span data-stu-id="61b03-162">Assume that transmit is way more intensive than receive, and uses 80% CPU resources in the one BizTalk server topology.</span></span> <span data-ttu-id="61b03-163">通过将传输主机实例移至其他计算机，只能获得其他 20% 的 CPU 资源，因此，最大扩展因子将为 1.2。</span><span class="sxs-lookup"><span data-stu-id="61b03-163">By moving the transmit host instance to another machine, you gain only 20% more CPU resources so the maximum scaling factor will be 1.2.</span></span> <span data-ttu-id="61b03-164">此外，具有接收主机实例的计算机将只使用 20-30% 的 CPU 资源，这样，扩展的优势将大为减少。</span><span class="sxs-lookup"><span data-stu-id="61b03-164">Moreover, the computer with the receive host instance will use only 20-30% CPU resources so the advantage of scaling-out is much less.</span></span>  
  
 <span data-ttu-id="61b03-165">假设下图中包含四个 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="61b03-165">Consider the following figure that has four BizTalk servers.</span></span> <span data-ttu-id="61b03-166">每台计算机既是接收方也是发送方，总共为您提供了每种类型（接收和传输）的四个主机实例。</span><span class="sxs-lookup"><span data-stu-id="61b03-166">Each computer is both receiver and sender, giving you a  total of four host instances of each type (receive and transmit).</span></span>  
  
 <span data-ttu-id="61b03-167">![报告 （&） #45; 分解的主机实例](../core/media/refactoringhostinstances.gif "RefactoringHostinstances")</span><span class="sxs-lookup"><span data-stu-id="61b03-167">![Re&#45;factoring host instances](../core/media/refactoringhostinstances.gif "RefactoringHostinstances")</span></span>  
  
 <span data-ttu-id="61b03-168">此拓扑结构可能不是最佳的结构。</span><span class="sxs-lookup"><span data-stu-id="61b03-168">This topology might not be the best possible one possible.</span></span> <span data-ttu-id="61b03-169">根据具体情况的复杂度，还应测试其他重构排列方案。</span><span class="sxs-lookup"><span data-stu-id="61b03-169">You should also test other factoring permutations, depending on the complexity of scenario.</span></span> <span data-ttu-id="61b03-170">例如：</span><span class="sxs-lookup"><span data-stu-id="61b03-170">For example:</span></span>  
  
-   <span data-ttu-id="61b03-171">将两台计算机专用于接收，其他两台计算机专用于传输。</span><span class="sxs-lookup"><span data-stu-id="61b03-171">Dedicate two computers for receiving and  two for transmitting.</span></span> <span data-ttu-id="61b03-172">如果接收和发送占用同样多的系统资源，则这样可提供可能的最佳扩展。</span><span class="sxs-lookup"><span data-stu-id="61b03-172">This will give you the best possible scaling when both receive and send are equally intensive.</span></span>  
  
-   <span data-ttu-id="61b03-173">如果接收占用的系统资源多于传输所占用的资源，则将三台计算机专用于接收，另一台计算机专用于传输。</span><span class="sxs-lookup"><span data-stu-id="61b03-173">Dedicate three computersfor receiving and one for transmitting, if receiving is more intensive than transmit.</span></span>  
  
-   <span data-ttu-id="61b03-174">如果传输占用的系统资源多于接收所占用的资源，则将一台计算机专用于接收，其他三台计算机专用于传输。</span><span class="sxs-lookup"><span data-stu-id="61b03-174">Dedicate one computer for receive and three for transmitting if transmitting is more intensive than receive.</span></span>  
  
 <span data-ttu-id="61b03-175">在所有情况下，都建议您将每个主机的主机实例数降至最低，以便减少 MessageBox 数据库上的争用现象，同时最大限度地利用计算机资源。</span><span class="sxs-lookup"><span data-stu-id="61b03-175">In all scenarios, it is recommended that you minimize the number of host instances of each host so that contention on the MessageBox database is reduced and at the same time use the computer resources are use to the fullest.</span></span> <span data-ttu-id="61b03-176">最佳的重构排列方案取决于具体情况的复杂度和瓶颈类型。</span><span class="sxs-lookup"><span data-stu-id="61b03-176">The best factoring permutation depends on the complexity of scenario and type of bottleneck.</span></span> <span data-ttu-id="61b03-177">在最终确定排列方案前，应始终对重构进行测试。</span><span class="sxs-lookup"><span data-stu-id="61b03-177">Always test your factoring before you finalize a permutation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61b03-178">另请参阅</span><span class="sxs-lookup"><span data-stu-id="61b03-178">See Also</span></span>  
 <span data-ttu-id="61b03-179">[BizTalk Server 层向上扩展](../core/scaling-up-the-biztalk-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="61b03-179">[Scaling Up the BizTalk Server Tier](../core/scaling-up-the-biztalk-server-tier.md) </span></span>  
 <span data-ttu-id="61b03-180">[SQL Server 层向上扩展](../core/scaling-up-the-sql-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="61b03-180">[Scaling Up the SQL Server Tier](../core/scaling-up-the-sql-server-tier.md) </span></span>  
 <span data-ttu-id="61b03-181">[SQL Server 层向外缩放](../core/scaling-out-the-sql-server-tier.md) </span><span class="sxs-lookup"><span data-stu-id="61b03-181">[Scaling Out the SQL Server Tier](../core/scaling-out-the-sql-server-tier.md) </span></span>  
 <span data-ttu-id="61b03-182">[向外扩展接收主机](../core/scaled-out-receiving-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="61b03-182">[Scaled-Out Receiving Hosts](../core/scaled-out-receiving-hosts.md) </span></span>  
 <span data-ttu-id="61b03-183">[向外扩展的处理主机](../core/scaled-out-processing-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="61b03-183">[Scaled-Out Processing Hosts](../core/scaled-out-processing-hosts.md) </span></span>  
 <span data-ttu-id="61b03-184">[向外扩展的发送主机](../core/scaled-out-sending-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="61b03-184">[Scaled-Out Sending Hosts](../core/scaled-out-sending-hosts.md) </span></span>  
 <span data-ttu-id="61b03-185">[Windows Server 群集用于 BizTalk Server Hosts2 为提供高可用性](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="61b03-185">[Using Windows Server Cluster to Provide High Availability for BizTalk Server Hosts2](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span></span>  
 <span data-ttu-id="61b03-186">[向外扩展的数据库](../core/scaled-out-databases.md) </span><span class="sxs-lookup"><span data-stu-id="61b03-186">[Scaled-Out Databases](../core/scaled-out-databases.md) </span></span>  
 [<span data-ttu-id="61b03-187">群集的 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="61b03-187">Clustering the BizTalk Server Databases</span></span>](../core/clustering-the-biztalk-server-databases1.md)