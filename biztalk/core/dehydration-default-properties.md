---
title: "冻结默认属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 68c59def-d73b-4880-9884-ccbe5d982f4b
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff78b1e096f1a73675ffc02550794f5a300f5614
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="dehydration-default-properties"></a><span data-ttu-id="27f9b-102">冻结默认属性</span><span class="sxs-lookup"><span data-stu-id="27f9b-102">Dehydration Default Properties</span></span>
<span data-ttu-id="27f9b-103">以下是冻结属性的名称及其默认值。</span><span class="sxs-lookup"><span data-stu-id="27f9b-103">Following are the names of the dehydration properties and their default values.</span></span> <span data-ttu-id="27f9b-104">这些属性在[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]中配置，或作为 XML 在 BizTalk 配置文件（BTSNTSvc.exe.config 或 BTSNTSvc64.exe.config）中配置。</span><span class="sxs-lookup"><span data-stu-id="27f9b-104">These properties are configurable in [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] or as XML in the BizTalk configuration file (BTSNTSvc.exe.config or BTSNTSvc64.exe.config).</span></span> <span data-ttu-id="27f9b-105">将首先应用 BizTalk 配置文件中的值，</span><span class="sxs-lookup"><span data-stu-id="27f9b-105">The values in the BizTalk configuration file are applied first.</span></span> <span data-ttu-id="27f9b-106">然后应用[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]设置。</span><span class="sxs-lookup"><span data-stu-id="27f9b-106">Then, the [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] settings are applied.</span></span> <span data-ttu-id="27f9b-107">所有包含业务流程的主机实例启动后，将读取冻结属性。</span><span class="sxs-lookup"><span data-stu-id="27f9b-107">The dehydration properties are read when all host instances containing an orchestration start.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="27f9b-108">不是所有业务流程设置都在[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]中公开。</span><span class="sxs-lookup"><span data-stu-id="27f9b-108">Not all orchestrations settings are exposed in [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)].</span></span> <span data-ttu-id="27f9b-109">对于这些设置，将使用 BizTalk 配置文件（BTSNTSvc.exe.config 或 BTSNTSvc64.exe.config）。</span><span class="sxs-lookup"><span data-stu-id="27f9b-109">For these settings, the BizTalk configuration file (BTSNTSvc.exe.config or BTSNTSvc64.exe.config) is used.</span></span> <span data-ttu-id="27f9b-110">使用 BizTalk 配置文件时，许多属性并未列出，</span><span class="sxs-lookup"><span data-stu-id="27f9b-110">When using the BizTalk configuration file, many properties are not listed.</span></span> <span data-ttu-id="27f9b-111">但这些属性及其默认值仍然适用，即使并未在配置文件中明确指定它们。</span><span class="sxs-lookup"><span data-stu-id="27f9b-111">These properties and their default values are still applied, even if they are not explicitly specified in the configuration file.</span></span>  
  
 <span data-ttu-id="27f9b-112">若要更改默认值，可以使用[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]或将它们显式添加到 BizTalk 配置文件。</span><span class="sxs-lookup"><span data-stu-id="27f9b-112">To change the default values, you can use [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] or explicitly add them to the BizTalk configuration file.</span></span> <span data-ttu-id="27f9b-113">有关详细信息，请参阅[BizTalk Server 性能优化使用设置仪表板](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)和[BTSNTSvc.exe.config 文件](../core/btsntsvc-exe-config-file.md)。</span><span class="sxs-lookup"><span data-stu-id="27f9b-113">For more information, see [Using Settings Dashboard for BizTalk Server Performance Tuning](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md) and [BTSNTSvc.exe.config File](../core/btsntsvc-exe-config-file.md).</span></span>  
  
 <span data-ttu-id="27f9b-114">**冻结**</span><span class="sxs-lookup"><span data-stu-id="27f9b-114">**Dehydration**</span></span>  
  
-   <span data-ttu-id="27f9b-115">**MaxThreshold** = 1800年</span><span class="sxs-lookup"><span data-stu-id="27f9b-115">**MaxThreshold** = 1800</span></span>  
  
-   <span data-ttu-id="27f9b-116">**MinThreshold** = 1</span><span class="sxs-lookup"><span data-stu-id="27f9b-116">**MinThreshold** = 1</span></span>  
  
-   <span data-ttu-id="27f9b-117">**ConstantThreshold** =-1</span><span class="sxs-lookup"><span data-stu-id="27f9b-117">**ConstantThreshold** = -1</span></span>  
  
 <span data-ttu-id="27f9b-118">**VirtualMemoryThrottlingCriteria**</span><span class="sxs-lookup"><span data-stu-id="27f9b-118">**VirtualMemoryThrottlingCriteria**</span></span>  
  
-   <span data-ttu-id="27f9b-119">**OptimalUsage** = 900</span><span class="sxs-lookup"><span data-stu-id="27f9b-119">**OptimalUsage** = 900</span></span>  
  
-   <span data-ttu-id="27f9b-120">**MaximalUsage** = 1300年</span><span class="sxs-lookup"><span data-stu-id="27f9b-120">**MaximalUsage** =  1300</span></span>  
  
-   <span data-ttu-id="27f9b-121">**IsActive** = true</span><span class="sxs-lookup"><span data-stu-id="27f9b-121">**IsActive** = true</span></span>  
  
 <span data-ttu-id="27f9b-122">**PrivateMemoryThrottlingCriteria**</span><span class="sxs-lookup"><span data-stu-id="27f9b-122">**PrivateMemoryThrottlingCriteria**</span></span>  
  
-   <span data-ttu-id="27f9b-123">**OptimalUsage** = 50</span><span class="sxs-lookup"><span data-stu-id="27f9b-123">**OptimalUsage** = 50</span></span>  
  
-   <span data-ttu-id="27f9b-124">**MaximalUsage** = 350</span><span class="sxs-lookup"><span data-stu-id="27f9b-124">**MaximalUsage** =  350</span></span>  
  
-   <span data-ttu-id="27f9b-125">**IsActive** = true</span><span class="sxs-lookup"><span data-stu-id="27f9b-125">**IsActive** = true</span></span>  
  
 <span data-ttu-id="27f9b-126">**PhysicalMemoryThrottlingCriteria**</span><span class="sxs-lookup"><span data-stu-id="27f9b-126">**PhysicalMemoryThrottlingCriteria**</span></span>  
  
-   <span data-ttu-id="27f9b-127">**OptimalUsage** = 90</span><span class="sxs-lookup"><span data-stu-id="27f9b-127">**OptimalUsage** = 90</span></span>  
  
-   <span data-ttu-id="27f9b-128">**MaximalUsage** = 95</span><span class="sxs-lookup"><span data-stu-id="27f9b-128">**MaximalUsage** =  95</span></span>  
  
-   <span data-ttu-id="27f9b-129">**IsActive** = false</span><span class="sxs-lookup"><span data-stu-id="27f9b-129">**IsActive** = false</span></span>  
  
 <span data-ttu-id="27f9b-130">下面对每一个属性详细说明。</span><span class="sxs-lookup"><span data-stu-id="27f9b-130">Each of these properties is described in detail next.</span></span>  
  
## <a name="dehydration"></a><span data-ttu-id="27f9b-131">冻结</span><span class="sxs-lookup"><span data-stu-id="27f9b-131">Dehydration</span></span>  
 <span data-ttu-id="27f9b-132">**MaxThreshold**和**MinThreshold**上限，并且在中较低层边界，秒，可以在订阅 （即，被阻止接收、 侦听或延迟） 之前的冻结拒绝业务流程的时间。</span><span class="sxs-lookup"><span data-stu-id="27f9b-132">**MaxThreshold** and **MinThreshold** are the upper and lower bounds, in seconds, of the time that an orchestration can be blocked at a subscription (that is, blocked by a receive, listen, or delay) before being dehydrated.</span></span> <span data-ttu-id="27f9b-133">也将一个值在运行时计算，调用**TestThreshold**，且其值，以秒，单位为之间**MinThreshold**和**MaxThreshold**。</span><span class="sxs-lookup"><span data-stu-id="27f9b-133">There will also be a value calculated at run-time, called **TestThreshold**, and its value, measured in seconds, is between **MinThreshold** and **MaxThreshold**.</span></span>  
  
 <span data-ttu-id="27f9b-134">如果你设置除了默认值为-1 值**ConstantThreshold**，不会运行时值**TestThreshold**。</span><span class="sxs-lookup"><span data-stu-id="27f9b-134">If you set a value besides the default of -1 for **ConstantThreshold**, there will not be a run-time value **TestThreshold**.</span></span> <span data-ttu-id="27f9b-135">当业务流程阻止在一个订阅，并且该业务流程的所有实例多长时间被都阻止在该订阅的历史记录大于的值**TestThreshold**，则业务流程将冻结。</span><span class="sxs-lookup"><span data-stu-id="27f9b-135">When an orchestration is blocked at a subscription, and the history of how long all instances of that orchestration have been blocked at that subscription is greater than the value of **TestThreshold**, then the orchestration will dehydrate.</span></span> <span data-ttu-id="27f9b-136">否则为如果历史记录是小于**TestThreshold**业务流程将未冻结的值。</span><span class="sxs-lookup"><span data-stu-id="27f9b-136">Otherwise, if the history is less than **TestThreshold** value the orchestration will not dehydrate.</span></span> <span data-ttu-id="27f9b-137">此外，即使历史记录指示，冻结不会发生，如果当前的阻塞时间达到 2 ***TestThreshold**，则冻结，会进行。</span><span class="sxs-lookup"><span data-stu-id="27f9b-137">Also, even if the history indicates that dehydration will not take place, if the current blocking time reaches 2***TestThreshold**, then the dehydration will take place.</span></span> <span data-ttu-id="27f9b-138">历史记录由最后 10 个等待时间的平均值定义（秒），或者历史记录中所有等待时间的平均值定义（如果等待次数少于 10）。</span><span class="sxs-lookup"><span data-stu-id="27f9b-138">The history is defined by the average of the last 10 waiting times in seconds, or the average of however many waiting times there are in the history if the waiting times are less than 10.</span></span>  
  
 <span data-ttu-id="27f9b-139">时的值**TestThreshold**往往推进到**MinThreshold**内存使用率增加时调用"内存情况基于冻结限制"。</span><span class="sxs-lookup"><span data-stu-id="27f9b-139">When the value of **TestThreshold** tends toward **MinThreshold** as memory usage increases, it is called "memory based dehydration throttling."</span></span> <span data-ttu-id="27f9b-140">基于内存的冻结阻止允许更多的业务流程实例生存，因为当其中的任何实例因等待工作（即等待消息或延迟）而被阻止时，会被冻结并从内存中撤出。</span><span class="sxs-lookup"><span data-stu-id="27f9b-140">Memory-based dehydration throttling allows more orchestration instances to be live because when any of them are blocked waiting for work (that is, waiting for a message or a delay), they can be dehydrated and taken out of memory.</span></span> <span data-ttu-id="27f9b-141">**TestThreshold**是单调递减函数的内存使用情况，它是与内存使用量成反比。</span><span class="sxs-lookup"><span data-stu-id="27f9b-141">**TestThreshold** is a monotonically decreasing function of memory usage, it is inversely proportional to memory usage.</span></span>  
  
 <span data-ttu-id="27f9b-142">以下是各个冻结属性的说明：</span><span class="sxs-lookup"><span data-stu-id="27f9b-142">Following are descriptions of the individual Dehydration properties:</span></span>  
  
-   <span data-ttu-id="27f9b-143">**MaxThreshold**： 上限，以秒为单位，可以在订阅，然后才能被冻结拒绝业务流程的时间。</span><span class="sxs-lookup"><span data-stu-id="27f9b-143">**MaxThreshold**: the upper bounds, in seconds, of the time that an orchestration can be blocked at a subscription before being dehydrated.</span></span>  
  
-   <span data-ttu-id="27f9b-144">**MinThreshold**： 下限，以秒为单位，可以在订阅，然后才能被冻结拒绝业务流程的时间。</span><span class="sxs-lookup"><span data-stu-id="27f9b-144">**MinThreshold**: the lower bounds, in seconds, of the time that an orchestration can be blocked at a subscription before being dehydrated.</span></span>  
  
-   <span data-ttu-id="27f9b-145">**ConstantThreshold**： 指定的最小和最大值之间通常根据不断变化的动态阈值。</span><span class="sxs-lookup"><span data-stu-id="27f9b-145">**ConstantThreshold**: the dynamic threshold, which usually fluctuates between the minimum and maximum values specified.</span></span> <span data-ttu-id="27f9b-146">不过，可通过设置此属性使阈值成为不变值。</span><span class="sxs-lookup"><span data-stu-id="27f9b-146">However, you can make the threshold a fixed value by setting this property.</span></span> <span data-ttu-id="27f9b-147">如果值为 -1，表示引擎不使用常数阈值。</span><span class="sxs-lookup"><span data-stu-id="27f9b-147">A value of -1 tells the engine not to use a constant threshold.</span></span> <span data-ttu-id="27f9b-148">不要将此属性设置为除 -1 之外的值，因为这样会禁用基于冻结的阻止。</span><span class="sxs-lookup"><span data-stu-id="27f9b-148">Don't set this property to a value other than -1 because it will disable dehydration based throttling.</span></span>  
  
## <a name="virtualmemorythrottlingcriteria"></a><span data-ttu-id="27f9b-149">VirtualMemoryThrottlingCriteria</span><span class="sxs-lookup"><span data-stu-id="27f9b-149">VirtualMemoryThrottlingCriteria</span></span>  
 <span data-ttu-id="27f9b-150">目前，虚拟内存会由于未托管的堆碎片而成为 32 位计算机上的瓶颈，因此，你应该根据此资源进行阻止。</span><span class="sxs-lookup"><span data-stu-id="27f9b-150">Currently, virtual memory can become a bottleneck on 32-bit machines due to unmanaged heap fragmentation, so you should throttle by this resource as well.</span></span> <span data-ttu-id="27f9b-151">你应该重新配置是否设置 /3GB 或者主机是否运行在 64 位平台上。</span><span class="sxs-lookup"><span data-stu-id="27f9b-151">You should re-configure if /3GB is set or if the hosts are running on a 64-bit platform.</span></span> <span data-ttu-id="27f9b-152">最佳使用量和最大使用量的单位为 MB。</span><span class="sxs-lookup"><span data-stu-id="27f9b-152">Optimal and maximal usages are in MB.</span></span>  
  
 <span data-ttu-id="27f9b-153">以下是各个 VirtualMemoryThrottlingCriteria 属性的说明：</span><span class="sxs-lookup"><span data-stu-id="27f9b-153">Following are descriptions of the individual VirtualMemoryThrottlingCriteria properties:</span></span>  
  
-   <span data-ttu-id="27f9b-154">**OptimalUsage**： 的虚拟内存使用量的冻结限制开始处生效。</span><span class="sxs-lookup"><span data-stu-id="27f9b-154">**OptimalUsage**: The amount of virtual memory usage at which dehydration throttling begins to take effect.</span></span> <span data-ttu-id="27f9b-155">此时， **TestThreshold**具有值**MaxThreshold**和任何内存使用率大于**OptimalUsage**导致**TestThreshold**要小于**MaxThreshold**。</span><span class="sxs-lookup"><span data-stu-id="27f9b-155">At this point, **TestThreshold** has the value **MaxThreshold** and any memory usage greater than **OptimalUsage** causes **TestThreshold** to be less than **MaxThreshold**.</span></span>  
  
-   <span data-ttu-id="27f9b-156">**MaximalUsage**： 的虚拟内存使用量的最大限制是在哪个冻结。</span><span class="sxs-lookup"><span data-stu-id="27f9b-156">**MaximalUsage**: The amount of virtual memory usage at which dehydration throttling is at a maximum.</span></span> <span data-ttu-id="27f9b-157">此时， **TestThreshold**具有值**MinThreshold**和任何内存使用率小于**MaximalUsage**导致**TestThreshold**晚于**MinThreshold**。</span><span class="sxs-lookup"><span data-stu-id="27f9b-157">At this point, **TestThreshold** has the value **MinThreshold** and any memory usage less than **MaximalUsage** causes **TestThreshold** to be greater than **MinThreshold**.</span></span>  
  
-   <span data-ttu-id="27f9b-158">**IsActive**： 一个布尔值，该值指示虚拟内存限制是否处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="27f9b-158">**IsActive**: A boolean value indicating if virtual memory throttling is active.</span></span>  
  
## <a name="privatememorythrottlingcriteria"></a><span data-ttu-id="27f9b-159">PrivateMemoryThrottlingCriteria</span><span class="sxs-lookup"><span data-stu-id="27f9b-159">PrivateMemoryThrottlingCriteria</span></span>  
 <span data-ttu-id="27f9b-160">此属性是一个用于阻止的有用标准，但其值是否合适取决于计算机是否运行其他 Windows 服务。</span><span class="sxs-lookup"><span data-stu-id="27f9b-160">This property is a useful criterion for throttling, but appropriate values depend on whether the computer is running other windows services.</span></span> <span data-ttu-id="27f9b-161">如果计算机有大量内存，并且不与其他 Windows 服务共享，你可以大幅增加这些值。</span><span class="sxs-lookup"><span data-stu-id="27f9b-161">If the computer has a lot of memory and is not being shared with other windows services, then you can increase these values significantly.</span></span>  
  
 <span data-ttu-id="27f9b-162">以下是各个 PrivateMemoryThrottlingCriteria 属性的说明：</span><span class="sxs-lookup"><span data-stu-id="27f9b-162">Following are descriptions of the individual PrivateMemoryThrottlingCriteria properties:</span></span>  
  
-   <span data-ttu-id="27f9b-163">**OptimalUsage**： 的专用内存使用量，以 mb 为单位，哪些冻结限制开始处生效。</span><span class="sxs-lookup"><span data-stu-id="27f9b-163">**OptimalUsage**: the amount of private memory usage, in MB, at which dehydration throttling begins to take effect.</span></span> <span data-ttu-id="27f9b-164">此时**TestThreshold**具有值**MaxThreshold**和任何内存使用率大于**OptimalUsage**导致**TestThreshold**要小于**MaxThreshold**。</span><span class="sxs-lookup"><span data-stu-id="27f9b-164">At this point **TestThreshold** has the value **MaxThreshold** and any memory usage greater than **OptimalUsage** causes **TestThreshold** to be less than **MaxThreshold**.</span></span>  
  
-   <span data-ttu-id="27f9b-165">**MaximalUsage**： 的专用内存使用量，以 mb 为单位的最大限制是在哪个冻结。</span><span class="sxs-lookup"><span data-stu-id="27f9b-165">**MaximalUsage**: the amount of private memory usage, in MB, at which dehydration throttling is at a maximum.</span></span> <span data-ttu-id="27f9b-166">此时**TestThreshold**具有值**MinThreshold**和任何内存使用率小于**MaximalUsage**导致**TestThreshold**晚于**MinThreshold**。</span><span class="sxs-lookup"><span data-stu-id="27f9b-166">At this point **TestThreshold** has the value **MinThreshold** and any memory usage less than **MaximalUsage** causes **TestThreshold** to be greater than **MinThreshold**.</span></span>  
  
-   <span data-ttu-id="27f9b-167">**IsActive**： 一个布尔值，该值专用内存限制是否处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="27f9b-167">**IsActive**: a boolean value indicating if private memory throttling is active.</span></span>  
  
## <a name="physicalmemorythrottlingcriteria"></a><span data-ttu-id="27f9b-168">PhysicalMemoryThrottlingCriteria</span><span class="sxs-lookup"><span data-stu-id="27f9b-168">PhysicalMemoryThrottlingCriteria</span></span>  
 <span data-ttu-id="27f9b-169">另外，还有物理内存阻止，其度量单位为内存使用百分比，而不是 MB。</span><span class="sxs-lookup"><span data-stu-id="27f9b-169">There is also a physical memory throttling where numbers are measured in percentage of memory used rather than MB.</span></span> <span data-ttu-id="27f9b-170">默认情况下，此属性禁用，但你可以根据需要启用它。</span><span class="sxs-lookup"><span data-stu-id="27f9b-170">This property is disabled by default, but you can enable if needed.</span></span>  
  
 <span data-ttu-id="27f9b-171">以下是各个 PhysicalMemoryThrottlingCriteria 属性的说明：</span><span class="sxs-lookup"><span data-stu-id="27f9b-171">Following are descriptions of the individual PhysicalMemoryThrottlingCriteria properties:</span></span>  
  
-   <span data-ttu-id="27f9b-172">**OptimalUsage**： 要使用的主机实例的物理内存的最佳百分比。</span><span class="sxs-lookup"><span data-stu-id="27f9b-172">**OptimalUsage**: the optimum percentage of physical memory to use for the host instances.</span></span>  
  
-   <span data-ttu-id="27f9b-173">**MaximalUsage**： 要使用的主机实例的物理内存的最大百分比。</span><span class="sxs-lookup"><span data-stu-id="27f9b-173">**MaximalUsage**: the maximum percentage of physical memory to use for the host instances.</span></span>  
  
-   <span data-ttu-id="27f9b-174">**IsActive**： 布尔值，该值指示是否物理内存限制为活动状态。</span><span class="sxs-lookup"><span data-stu-id="27f9b-174">**IsActive**: boolean value indicating if physical memory throttling is active.</span></span>  
  
## <a name="dehydration-properties-behavior"></a><span data-ttu-id="27f9b-175">冻结属性行为</span><span class="sxs-lookup"><span data-stu-id="27f9b-175">Dehydration Properties Behavior</span></span>  
 <span data-ttu-id="27f9b-176">BizTalk Server 使用这些冻结属性来确定何时对业务流程冻结和解除冻结。</span><span class="sxs-lookup"><span data-stu-id="27f9b-176">BizTalk Server uses these dehydration properties to decide when to dehydrate and rehydrate orchestrations.</span></span> <span data-ttu-id="27f9b-177">在正常的负载下，默认冻结值就足够了，但如果运行在较高的负载下，并且希望改变性能特征，应自己进行优化。</span><span class="sxs-lookup"><span data-stu-id="27f9b-177">Under normal load, the default dehydration values are sufficient, but if you are running under heavy load and want to change performance characteristics, you should do the tuning yourself.</span></span>  
  
 <span data-ttu-id="27f9b-178">BizTalk Server 的冻结行为完全取决于有多少内存可用以及有多少内存正在使用中。</span><span class="sxs-lookup"><span data-stu-id="27f9b-178">The dehydration behavior of BizTalk Server depends entirely on how much memory is available and how much memory is being used.</span></span> <span data-ttu-id="27f9b-179">由于内存量不同以及 32 位和 64 位主机内存使用量不同，冻结行为也不同。</span><span class="sxs-lookup"><span data-stu-id="27f9b-179">The dehydration behavior is different with different amounts of memory and differences in memory use between 32-bit and 64-bit hosts.</span></span>  
  
 <span data-ttu-id="27f9b-180">对于业务流程主机，冻结属性分“专用字节”和“虚拟字节”：</span><span class="sxs-lookup"><span data-stu-id="27f9b-180">The dehydration properties distinguish between Private Bytes and Virtual Bytes for the orchestration host:</span></span>  
  
-   <span data-ttu-id="27f9b-181">**虚拟字节**。</span><span class="sxs-lookup"><span data-stu-id="27f9b-181">**Virtual Bytes**.</span></span> <span data-ttu-id="27f9b-182">这是当前大小，以字节为单位的进程正在使用的虚拟地址空间。</span><span class="sxs-lookup"><span data-stu-id="27f9b-182">This is thecurrent size, in bytes, of the virtual address space the process is using.</span></span> <span data-ttu-id="27f9b-183">使用虚拟地址空间不一定意味着要使用磁盘或主内存页。</span><span class="sxs-lookup"><span data-stu-id="27f9b-183">Use of virtual address space does not necessarily imply corresponding use of either disk or main memory pages.</span></span> <span data-ttu-id="27f9b-184">虚拟空间是有限的，进程可以限制其加载库的能力。</span><span class="sxs-lookup"><span data-stu-id="27f9b-184">Virtual space is finite, and the process can limit its ability to load libraries.</span></span>  
  
-   <span data-ttu-id="27f9b-185">**专用字节**。</span><span class="sxs-lookup"><span data-stu-id="27f9b-185">**Private Bytes**.</span></span> <span data-ttu-id="27f9b-186">是此进程分配的不能与其他进程共享的内存量的当前大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="27f9b-186">This is the current size, in bytes, of memory that this process has allocated that cannot be shared with other processes.</span></span>