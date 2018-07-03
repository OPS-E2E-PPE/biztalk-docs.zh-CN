---
title: 一般性的指导原则，用于提高网络性能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 286c10d2-9262-4e3c-adde-f7b5780c2736
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8cc4c27ef977a4bd8789adc569f9d8d78aa11ce
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996998"
---
# <a name="general-guidelines-for-improving-network-performance"></a><span data-ttu-id="53cac-102">优化网络性能的通用指南</span><span class="sxs-lookup"><span data-stu-id="53cac-102">General Guidelines for Improving Network Performance</span></span>
<span data-ttu-id="53cac-103">具有已调整为最佳值的网络设置显示可以有效地解决网络瓶颈并提高网络中 BizTalk Server 解决方案的总体性能。</span><span class="sxs-lookup"><span data-stu-id="53cac-103">Adjusting network settings to optimal values has been shown to effectively address network bottlenecks and improve overall network performance in BizTalk Server solutions.</span></span> <span data-ttu-id="53cac-104">这应在解决方案中，包括 BizTalk Server 计算机、 SQL Server 计算机和任何其他服务器计算机所涉及的所有计算机上。</span><span class="sxs-lookup"><span data-stu-id="53cac-104">This should be done on all computers involved in the solution, including BizTalk Server computers, SQL Server computers, and any other server computers.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="53cac-105">网络 IO 是 BizTalk Server 环境中的瓶颈的最常见指示器是计数器"SQL Server： 等待 Statistics\Network IO 等待"。</span><span class="sxs-lookup"><span data-stu-id="53cac-105">The most common indicator that Network IO is a bottleneck in a BizTalk Server environment is the counter “SQL Server:Wait Statistics\Network IO waits”.</span></span> <span data-ttu-id="53cac-106">时的值**平均等待时间**在此计数器是大于零上的一个或多个 SQL Server 计算机，则网络 IO 是瓶颈。</span><span class="sxs-lookup"><span data-stu-id="53cac-106">When the value for **Avg Wait Time** in this counter is greater than zero on one or more of your SQL Server computers, then Network IO is a bottleneck.</span></span>  
  
 <span data-ttu-id="53cac-107">以下建议可用于提高网络性能：</span><span class="sxs-lookup"><span data-stu-id="53cac-107">The following recommendation can be used to increase network performance:</span></span>  
  
## <a name="add-additional-network-cards-to-computers-in-the-biztalk-server-environment"></a><span data-ttu-id="53cac-108">将附加网络接口卡添加到 BizTalk Server 环境中的计算机</span><span class="sxs-lookup"><span data-stu-id="53cac-108">Add additional network cards to computers in the BizTalk Server environment</span></span>  
 <span data-ttu-id="53cac-109">只需添加额外的硬盘可以提高磁盘性能、 添加附加网络接口卡可以提高网络性能。</span><span class="sxs-lookup"><span data-stu-id="53cac-109">Just as adding additional hard drives can improve disk performance, adding additional network cards can improve network performance.</span></span> <span data-ttu-id="53cac-110">如果在 BizTalk Server 环境中的计算机上的网络卡趋于饱和，卡是一个瓶颈，请考虑添加一个或多个附加网络接口卡来提高性能。</span><span class="sxs-lookup"><span data-stu-id="53cac-110">If the network cards on the computers in your BizTalk Server environment are saturated and the card is a bottleneck, consider adding one or more additional network cards to improve performance.</span></span>  
  
## <a name="implement-network-segmentation"></a><span data-ttu-id="53cac-111">实现网络分段</span><span class="sxs-lookup"><span data-stu-id="53cac-111">Implement network segmentation</span></span>  
 <span data-ttu-id="53cac-112">请按照中的建议**子网**一部分["BizTalk Server 数据库优化"白皮书](http://go.microsoft.com/fwlink/?LinkID=101578)(http://go.microsoft.com/fwlink/?LinkID=101578)。</span><span class="sxs-lookup"><span data-stu-id="53cac-112">Follow the recommendations in the **Subnets** section of the ["BizTalk Server Database Optimization" whitepaper](http://go.microsoft.com/fwlink/?LinkID=101578) (http://go.microsoft.com/fwlink/?LinkID=101578).</span></span>  
  
## <a name="where-possible-replace-hubs-with-switches"></a><span data-ttu-id="53cac-113">在可能的情况下，替换开关为中心</span><span class="sxs-lookup"><span data-stu-id="53cac-113">Where possible, replace hubs with switches</span></span>  
 <span data-ttu-id="53cac-114">交换机包含用于直接路由的源和目标之间的通信，而中心使用广播的模型将流量路由逻辑。</span><span class="sxs-lookup"><span data-stu-id="53cac-114">Switches contain logic to directly route traffic between the source and destination whereas hubs use a broadcast model to route traffic.</span></span> <span data-ttu-id="53cac-115">因此开关的效率更高，并提供改进的性能。</span><span class="sxs-lookup"><span data-stu-id="53cac-115">Therefore switches are more efficient and offer improved performance.</span></span>  
  
## <a name="remove-unnecessary-network-protocols"></a><span data-ttu-id="53cac-116">删除不必要的网络协议</span><span class="sxs-lookup"><span data-stu-id="53cac-116">Remove unnecessary network protocols</span></span>  
 <span data-ttu-id="53cac-117">Windows Server 计算机有时了多个网络服务和安装不是实际需要的协议。</span><span class="sxs-lookup"><span data-stu-id="53cac-117">Windows Server computers sometimes have more network services and protocols installed than are actually required.</span></span> <span data-ttu-id="53cac-118">每个额外的网络客户端、 服务或协议将放置其他开销系统资源。</span><span class="sxs-lookup"><span data-stu-id="53cac-118">Each additional network client, service or protocol places additional overhead on system resources.</span></span>  
<span data-ttu-id="53cac-119">此外，每个已安装的协议生成网络流量。</span><span class="sxs-lookup"><span data-stu-id="53cac-119">In addition, each installed protocol generates network traffic.</span></span> <span data-ttu-id="53cac-120">通过删除不必要的网络客户端、 服务和协议，系统资源都可供其他进程、 避免过多的网络流量和必须协商的网络绑定数减少到最少。</span><span class="sxs-lookup"><span data-stu-id="53cac-120">By removing unnecessary network clients, services and protocols, system resources are made available for other processes, excess network traffic is avoided and the number of network bindings that must be negotiated is reduced to a minimum.</span></span>  
<span data-ttu-id="53cac-121">若要查看当前安装的网络客户端，协议和服务，请按照下列步骤：</span><span class="sxs-lookup"><span data-stu-id="53cac-121">To see the currently installed network clients, protocols and services, follow these steps:</span></span>  
  
1. <span data-ttu-id="53cac-122">单击**启动**，然后单击**控制面板**。</span><span class="sxs-lookup"><span data-stu-id="53cac-122">Click **Start**, and then click **Control Panel**.</span></span>  
  
2. <span data-ttu-id="53cac-123">在控制面板中，执行以下项之一</span><span class="sxs-lookup"><span data-stu-id="53cac-123">In Control Panel, do one of the following</span></span>  
  
   1.  <span data-ttu-id="53cac-124">在**调整您的计算机的设置**，请设置**通过查看**到**类别**，单击**网络和 Internet**，然后单击**网络和共享中心**。</span><span class="sxs-lookup"><span data-stu-id="53cac-124">In **Adjust your computer’s settings**, set **View by** to **Category**, click **Network and Internet**, and then click **Network and Sharing Center**.</span></span>  
  
   2.  <span data-ttu-id="53cac-125">中**调整您的计算机的设置**，将**通过查看**至任一**大图标**或**小图标**，然后单击**网络和共享中心**。</span><span class="sxs-lookup"><span data-stu-id="53cac-125">In **Adjust your computer’s settings**, set **View by** to either **Large icons** or **Small icons**, and then click **Network and Sharing Center**.</span></span>  
  
3. <span data-ttu-id="53cac-126">在任务窗格中单击**更改适配器设置**。</span><span class="sxs-lookup"><span data-stu-id="53cac-126">In the Tasks pane, click **Change adapter settings**.</span></span>  
  
4. <span data-ttu-id="53cac-127">右键单击**本地连接**（或你的网络连接的条目），然后单击**属性**以显示网络连接属性对话框。</span><span class="sxs-lookup"><span data-stu-id="53cac-127">Right-click **Local Area Connection** (or the entry for your network connection), and then click **Properties** to display the properties dialog box for the network connection.</span></span>  
  
5. <span data-ttu-id="53cac-128">若要删除不必要的项目，请选择它，然后单击**卸载**。</span><span class="sxs-lookup"><span data-stu-id="53cac-128">To remove an unnecessary item, select it and click **Uninstall**.</span></span> <span data-ttu-id="53cac-129">若要禁用某项，只需清除与项关联的复选框。</span><span class="sxs-lookup"><span data-stu-id="53cac-129">To disable an item, simply clear the checkbox associated with the item.</span></span>  
  
   <span data-ttu-id="53cac-130">如果您不确定有关卸载连接的项的效果，请禁用项，而不是无需卸载它。</span><span class="sxs-lookup"><span data-stu-id="53cac-130">If you are unsure about the effects of uninstalling an item for the connection, then disable the item rather than uninstalling it.</span></span> <span data-ttu-id="53cac-131">禁用项，可确定哪些服务、 协议和客户端实际需要的系统上。</span><span class="sxs-lookup"><span data-stu-id="53cac-131">Disabling items allows you to determine which services, protocols and clients are actually required on a system.</span></span> <span data-ttu-id="53cac-132">时确定，禁用某项的服务器上有没有负面影响，然后可以卸载该项目。</span><span class="sxs-lookup"><span data-stu-id="53cac-132">When it has been determined that disabling an item has no adverse affect on the server, the item can then be uninstalled.</span></span>  
   <span data-ttu-id="53cac-133">在许多情况下，只有以下三个组件是标准的基于 TCP/IP 网络上的操作所必需的：</span><span class="sxs-lookup"><span data-stu-id="53cac-133">In many cases, only the following three components are required for operation on a standard TCP/IP based network:</span></span>  
  
-   <span data-ttu-id="53cac-134">Microsoft 网络客户端</span><span class="sxs-lookup"><span data-stu-id="53cac-134">Client for Microsoft Networks</span></span>  
  
-   <span data-ttu-id="53cac-135">文件和打印机共享 Microsoft 网络的</span><span class="sxs-lookup"><span data-stu-id="53cac-135">File and Printer Sharing for Microsoft Networks</span></span>  
  
-   <span data-ttu-id="53cac-136">Internet 协议 (TCP/IP)</span><span class="sxs-lookup"><span data-stu-id="53cac-136">Internet Protocol (TCP/IP)</span></span>  
  
## <a name="network-adapter-drivers-on-all-computers-in-the-biztalk-server-environment-should-be-tuned-for-performance"></a><span data-ttu-id="53cac-137">在 BizTalk Server 环境中的所有计算机上的网络适配器驱动程序应该优化性能</span><span class="sxs-lookup"><span data-stu-id="53cac-137">Network adapter drivers on all computers in the BizTalk Server environment should be tuned for performance</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="53cac-138">应用到网络适配器驱动程序始终优化之前在环境中安装网络卡的最新网络适配器设备驱动的程序。</span><span class="sxs-lookup"><span data-stu-id="53cac-138">Before applying tuning to network adapter drivers always install the latest network adapter device drivers for the network cards in the environment.</span></span>  
  
 <span data-ttu-id="53cac-139">调整网络适配器设备驱动程序，以最大限度地传入和传出数据包缓冲，可用的内存量。</span><span class="sxs-lookup"><span data-stu-id="53cac-139">Adjust the network adapter device drivers to maximize the amount of memory available for packet buffering, both incoming and outgoing.</span></span> <span data-ttu-id="53cac-140">此外最大化缓冲区计数，尤其是传输缓冲区并合并缓冲区。</span><span class="sxs-lookup"><span data-stu-id="53cac-140">Also maximize buffer counts, especially transmit buffers and coalesce buffers.</span></span> <span data-ttu-id="53cac-141">默认值为这些参数，并是否甚至提供，制造商和驱动程序版本之间的不同。</span><span class="sxs-lookup"><span data-stu-id="53cac-141">The default values for these parameters, and whether they are even provided, vary between manufacturers and driver versions.</span></span> <span data-ttu-id="53cac-142">目标是以最大程度提高通过网络适配器硬件，完成的工作并允许以减少网络流量喷发，并关联的拥塞的网络操作的最大可能的缓冲区空间。</span><span class="sxs-lookup"><span data-stu-id="53cac-142">The goal is to maximize the work done by the network adapter hardware, and to allow the greatest possible buffer space for network operations to mitigate network traffic bursts and associated congestion.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="53cac-143">要优化网络适配器驱动程序的步骤因制造商而异。</span><span class="sxs-lookup"><span data-stu-id="53cac-143">Steps to tune network adapter drivers vary by manufacturer.</span></span>  
  
 <span data-ttu-id="53cac-144">请执行以下步骤，若要访问的网络适配器的设置：</span><span class="sxs-lookup"><span data-stu-id="53cac-144">Follow these steps to access settings for network adapters:</span></span>  
  
1. <span data-ttu-id="53cac-145">单击**启动**，然后单击**控制面板**。</span><span class="sxs-lookup"><span data-stu-id="53cac-145">Click **Start** and then click **Control Panel**.</span></span>  
  
2. <span data-ttu-id="53cac-146">在控制面板中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="53cac-146">In Control Panel, do one of the following:</span></span>  
  
   1.  <span data-ttu-id="53cac-147">在**调整您的计算机的设置**，请设置**通过查看**到**类别**，单击**网络和 Internet**，然后单击**网络和共享中心**。</span><span class="sxs-lookup"><span data-stu-id="53cac-147">In **Adjust your computer’s settings**, set **View by** to **Category**, click **Network and Internet**, and then click **Network and Sharing Center**.</span></span>  
  
   2.  <span data-ttu-id="53cac-148">中**调整您的计算机的设置**，将**通过查看**至任一**大图标**或**小图标**，然后单击**网络和共享中心**。</span><span class="sxs-lookup"><span data-stu-id="53cac-148">In **Adjust your computer’s settings**, set **View by** to either **Large icons** or **Small icons**, and then click **Network and Sharing Center**.</span></span>  
  
3. <span data-ttu-id="53cac-149">在任务窗格中单击**更改适配器设置**。</span><span class="sxs-lookup"><span data-stu-id="53cac-149">In the Tasks pane, click **Change adapter settings**.</span></span>  
  
4. <span data-ttu-id="53cac-150">右键单击**本地连接**（或你的网络连接的名称），然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="53cac-150">Right-click **Local Area Connection** (or the name of your network connection), and then click **Properties**.</span></span>  
  
5. <span data-ttu-id="53cac-151">上**联网**选项卡上，单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="53cac-151">On the **Networking** tab, click **Configure**.</span></span>  
  
6. <span data-ttu-id="53cac-152">单击**高级**选项卡可以为该网络适配器配置的访问属性。</span><span class="sxs-lookup"><span data-stu-id="53cac-152">Click the **Advanced** tab to access properties that can be configured for the network adapter.</span></span>  
  
   <span data-ttu-id="53cac-153">应为 BizTalk Server 环境中每个网络适配器配置以下属性：</span><span class="sxs-lookup"><span data-stu-id="53cac-153">The following properties should be configured for each network adapter in the BizTalk Server environment:</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="53cac-154">您应用这些设置包括单个网络适配器成组网络适配器配置的聚合、 负载平衡或容错能力的集内每个物理网络适配器。</span><span class="sxs-lookup"><span data-stu-id="53cac-154">You apply these settings for each physical network adapter, including the individual network adapters within a teamed set of network adapters that are configured for aggregation, load balancing, or fault tolerance.</span></span> <span data-ttu-id="53cac-155">某些组合软件，可能需要将这些设置也应用于团队。</span><span class="sxs-lookup"><span data-stu-id="53cac-155">With some teaming software, you might need to apply these settings to the team also.</span></span> <span data-ttu-id="53cac-156">请注意，某些网络适配器自我调整，可能无法提供该选项来手动配置参数。</span><span class="sxs-lookup"><span data-stu-id="53cac-156">Note that some network adapters are self-tuning and may not offer the option to configure parameters manually.</span></span>  
  
- <span data-ttu-id="53cac-157">**电源选项**– 配置网络适配器驱动程序，以防止电源管理功能关闭网络适配器以节约电源。</span><span class="sxs-lookup"><span data-stu-id="53cac-157">**Power Option** – Configure the network adapter driver to prevent power management functionality from turning off the network adapter to save power.</span></span> <span data-ttu-id="53cac-158">此功能对于客户端计算机可能很有用，但应很少，如果曾经，在 BizTalk Server 或 SQL Server 计算机上使用。</span><span class="sxs-lookup"><span data-stu-id="53cac-158">This functionality may be useful for client computers but should seldom, if ever, be used on a BizTalk Server or SQL Server computer.</span></span>  
  
- <span data-ttu-id="53cac-159">**固定速度/双工 （不要使用 AUTO）** -它是非常重要的网络速度、 双工、 和流控制参数设置为对应于交换机上的设置它们所连接到。</span><span class="sxs-lookup"><span data-stu-id="53cac-159">**Fixed Speed/Duplex (do not use AUTO)** - It is very important that the network speed, duplex, and flow control parameters are set to correspond to the settings on the switch to which they are connected.</span></span> <span data-ttu-id="53cac-160">这将缓解定期"自动同步"这可能暂时需要连接离线的匹配项。</span><span class="sxs-lookup"><span data-stu-id="53cac-160">This will mitigate the occurrence of periodic “auto-synchronization” which may temporarily take connections off-line.</span></span>  
  
- <span data-ttu-id="53cac-161">**最大 Coalesce 缓冲区**-映射寄存器是用于将物理地址转换为适用于支持总线掌握的网络适配器的虚拟地址的系统资源。</span><span class="sxs-lookup"><span data-stu-id="53cac-161">**Max Coalesce Buffers** - Map registers are system resources used to convert physical addresses to virtual addresses for network adapters that support bus mastering.</span></span> <span data-ttu-id="53cac-162">Coalesce 缓冲区可供网络驱动程序如果驱动程序用尽了映射寄存器。</span><span class="sxs-lookup"><span data-stu-id="53cac-162">Coalesce buffers are available to the network driver if the driver runs out of map registers.</span></span> <span data-ttu-id="53cac-163">设置此尽可能最大性能的大值。</span><span class="sxs-lookup"><span data-stu-id="53cac-163">Set this value as high as possible for maximum performance.</span></span> <span data-ttu-id="53cac-164">在服务器上物理内存有限，这可能会产生负面影响，因为合并缓冲区使用的系统内存。</span><span class="sxs-lookup"><span data-stu-id="53cac-164">On servers with limited physical memory, this may have a negative impact as coalesce buffers consume system memory.</span></span> <span data-ttu-id="53cac-165">在大多数系统上但是，最大值设置可以应用而不会显著降低可用内存。</span><span class="sxs-lookup"><span data-stu-id="53cac-165">On most systems however, the maximum setting can be applied without significantly reducing available memory.</span></span>  
  
- <span data-ttu-id="53cac-166">**最大传输/发送描述符和发送缓冲区**-此设置指定多少传输控制缓冲区以供网络接口分配驱动程序。</span><span class="sxs-lookup"><span data-stu-id="53cac-166">**Max Transmit/Send Descriptors and Send Buffers** - This setting specifies how many transmit control buffers the driver allocates for use by the network interface.</span></span> <span data-ttu-id="53cac-167">这直接反映驱动程序可以在其"发送"队列中的未完成数据包数。</span><span class="sxs-lookup"><span data-stu-id="53cac-167">This directly reflects the number of outstanding packets the driver can have in its “send” queue.</span></span> <span data-ttu-id="53cac-168">设置此尽可能最大性能的大值。</span><span class="sxs-lookup"><span data-stu-id="53cac-168">Set this value as high as possible for maximum performance.</span></span> <span data-ttu-id="53cac-169">在服务器上物理内存有限，这可能会产生负面影响，作为发送缓冲区使用的系统内存。</span><span class="sxs-lookup"><span data-stu-id="53cac-169">On servers with limited physical memory, this may have a negative impact as send buffers consume system memory.</span></span> <span data-ttu-id="53cac-170">在大多数系统上但是，最大值设置可以应用而不会显著降低可用内存。</span><span class="sxs-lookup"><span data-stu-id="53cac-170">On most systems however, the maximum setting can be applied without significantly reducing available memory.</span></span>  
  
- <span data-ttu-id="53cac-171">**最大接收缓冲区**-此设置指定的网络接口驱动程序将数据复制到的协议内存时所使用的内存缓冲区量。</span><span class="sxs-lookup"><span data-stu-id="53cac-171">**Max Receive Buffers** - This setting specifies the amount of memory buffer used by the network interface driver when copying data to the protocol memory.</span></span> <span data-ttu-id="53cac-172">它通常默认情况下，为相对较低的值设置。</span><span class="sxs-lookup"><span data-stu-id="53cac-172">It is normally set by default to a relatively low value.</span></span> <span data-ttu-id="53cac-173">设置此尽可能最大性能的大值。</span><span class="sxs-lookup"><span data-stu-id="53cac-173">Set this value as high as possible for maximum performance.</span></span> <span data-ttu-id="53cac-174">在服务器上物理内存有限，这可能会产生负面影响，如接收缓冲区使用的系统内存。</span><span class="sxs-lookup"><span data-stu-id="53cac-174">On servers with limited physical memory, this may have a negative impact as receive buffers consume system memory.</span></span> <span data-ttu-id="53cac-175">在大多数系统上但是，最大值设置可以应用而不会显著降低可用内存。</span><span class="sxs-lookup"><span data-stu-id="53cac-175">On most systems however, the maximum setting can be applied without significantly reducing available memory.</span></span>  
  
- <span data-ttu-id="53cac-176">**所有上卸载选项**-在几乎所有情况下启用网络接口卸载功能时的性能得到改进。</span><span class="sxs-lookup"><span data-stu-id="53cac-176">**All offload options ON** - In almost all cases performance is improved when enabling network interface offload features.</span></span> <span data-ttu-id="53cac-177">某些网络适配器提供单独的参数来启用或禁用卸载用于发送和接收流量。</span><span class="sxs-lookup"><span data-stu-id="53cac-177">Some network adapters provide separate parameters to enable or disable offloading for send and receive traffic.</span></span> <span data-ttu-id="53cac-178">卸载任务从 CPU 卸载到网络适配器可以帮助降低 CPU 使用率将提高系统整体性能的服务器上。</span><span class="sxs-lookup"><span data-stu-id="53cac-178">Offloading tasks from the CPU to the network adapter can help lower CPU usage on the server which will improve overall system performance.</span></span> <span data-ttu-id="53cac-179">Microsoft TCP/IP 传输可以卸载一个或多个到具有相应功能的网络适配器的以下任务：</span><span class="sxs-lookup"><span data-stu-id="53cac-179">The Microsoft TCP/IP transport can offload one or more of the following tasks to a network adapter that has the appropriate capabilities:</span></span>  
  
  -   <span data-ttu-id="53cac-180">**校验和任务**;-TCP/IP 传输可以卸载计算并验证 IP 和 TCP 校验和的发送和接收到的网络适配器启用此选项，如果网络适配器驱动程序提供了此功能。</span><span class="sxs-lookup"><span data-stu-id="53cac-180">**Checksum tasks** - The TCP/IP transport can offload the calculation and validation of IP and TCP checksums for sends and receives to the network adapter; enable this option if the network adapter driver provides this capability.</span></span>  
  
  -   <span data-ttu-id="53cac-181">**IP 安全任务**-计算和的身份验证标头 (AH) 和封装安全有效负载 (ESP) 到网络适配器的加密校验和验证，可以将卸载 TCP/IP 传输。</span><span class="sxs-lookup"><span data-stu-id="53cac-181">**IP security tasks** - The TCP/IP transport can offload the calculation and validation of encrypted checksums for authentication headers (AH) and encapsulating security payloads (ESP) to the network adapter.</span></span> <span data-ttu-id="53cac-182">加密和解密到网络适配器的 ESP 有效负载，还可以将卸载 TCP/IP 传输。</span><span class="sxs-lookup"><span data-stu-id="53cac-182">The TCP/IP transport can also offload the encryption and decryption of ESP payloads to the network adapter.</span></span> <span data-ttu-id="53cac-183">如果网络适配器驱动程序提供了此功能，请启用这些选项。</span><span class="sxs-lookup"><span data-stu-id="53cac-183">Enable these options if the network adapter driver provides this capability.</span></span>  
  
  -   <span data-ttu-id="53cac-184">**大型 TCP 数据包分段**-TCP/IP 传输支持大量发送卸载 (LSO)。</span><span class="sxs-lookup"><span data-stu-id="53cac-184">**Segmentation of large TCP packets** - The TCP/IP transport supports large send offload (LSO).</span></span> <span data-ttu-id="53cac-185">此外，使用 TCP/IP 传输可以将卸载大型 TCP 数据包的分段。</span><span class="sxs-lookup"><span data-stu-id="53cac-185">With LSO, the TCP/IP transport can offload the segmentation of large TCP packets.</span></span>  
  
  -   <span data-ttu-id="53cac-186">**堆栈卸载**– 整个网络堆栈卸载到具有相应功能的网络适配器。</span><span class="sxs-lookup"><span data-stu-id="53cac-186">**Stack Offload** – The entire network stack can be offloaded to a network adapter that has the appropriate capabilities.</span></span> <span data-ttu-id="53cac-187">如果网络适配器驱动程序提供了此功能，请启用此选项。</span><span class="sxs-lookup"><span data-stu-id="53cac-187">Enable this option if the network adapter driver provides this capability.</span></span>  
  
- <span data-ttu-id="53cac-188">**LAN 唤醒 （除非使用时） 禁用**– 配置网络适配器驱动程序，以禁用唤醒 on lan 功能。</span><span class="sxs-lookup"><span data-stu-id="53cac-188">**Wake On LAN disabled (unless being used)** – Configure the network adapter driver to disable wake-on lan functionality.</span></span> <span data-ttu-id="53cac-189">此功能对于客户端计算机可能很有用，但应很少如果曾经使用 BizTalk Server 或 SQL Server 计算机上。</span><span class="sxs-lookup"><span data-stu-id="53cac-189">This functionality may be useful for client computers but should seldom if ever be used on a BizTalk Server or SQL Server computer.</span></span>  
  
  <span data-ttu-id="53cac-190">有关优化性能的网络适配器的详细信息，请参阅**网络设备设置**一部分["BizTalk Server 数据库优化"白皮书](http://go.microsoft.com/fwlink/?LinkID=101578)(http://go.microsoft.com/fwlink/?LinkID=101578)。</span><span class="sxs-lookup"><span data-stu-id="53cac-190">For more information about tuning network adapters for performance, see the **Network Device Settings** section of the ["BizTalk Server Database Optimization" whitepaper](http://go.microsoft.com/fwlink/?LinkID=101578) (http://go.microsoft.com/fwlink/?LinkID=101578).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53cac-191">请参阅</span><span class="sxs-lookup"><span data-stu-id="53cac-191">See Also</span></span>  
 [<span data-ttu-id="53cac-192">优化网络性能的可修改设置</span><span class="sxs-lookup"><span data-stu-id="53cac-192">Settings that can be Modified to Improve Network Performance</span></span>](../technical-guides/settings-that-can-be-modified-to-improve-network-performance.md)