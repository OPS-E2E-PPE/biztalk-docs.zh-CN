---
title: 冻结默认属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 68c59def-d73b-4880-9884-ccbe5d982f4b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8905a476f967fc7156a81c239ac0f5f76aee6349
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389698"
---
# <a name="dehydration-default-properties"></a><span data-ttu-id="43de4-102">冻结默认属性</span><span class="sxs-lookup"><span data-stu-id="43de4-102">Dehydration Default Properties</span></span>
<span data-ttu-id="43de4-103">以下是冻结属性及其默认值的名称。</span><span class="sxs-lookup"><span data-stu-id="43de4-103">Following are the names of the dehydration properties and their default values.</span></span> <span data-ttu-id="43de4-104">这些属性是可在中配置[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]或作为 XML 在 BizTalk 配置文件 （BTSNTSvc.exe.config 或 BTSNTSvc64.exe.config）。</span><span class="sxs-lookup"><span data-stu-id="43de4-104">These properties are configurable in [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] or as XML in the BizTalk configuration file (BTSNTSvc.exe.config or BTSNTSvc64.exe.config).</span></span> <span data-ttu-id="43de4-105">首先应用 BizTalk 配置文件中的值。</span><span class="sxs-lookup"><span data-stu-id="43de4-105">The values in the BizTalk configuration file are applied first.</span></span> <span data-ttu-id="43de4-106">然后，[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]应用设置。</span><span class="sxs-lookup"><span data-stu-id="43de4-106">Then, the [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] settings are applied.</span></span> <span data-ttu-id="43de4-107">所有主机实例包含业务流程开始时将读取冻结属性。</span><span class="sxs-lookup"><span data-stu-id="43de4-107">The dehydration properties are read when all host instances containing an orchestration start.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="43de4-108">并非所有的业务流程设置都在[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="43de4-108">Not all orchestrations settings are exposed in [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)].</span></span> <span data-ttu-id="43de4-109">这些设置，请使用 BizTalk 配置文件 （BTSNTSvc.exe.config 或 BTSNTSvc64.exe.config）。</span><span class="sxs-lookup"><span data-stu-id="43de4-109">For these settings, the BizTalk configuration file (BTSNTSvc.exe.config or BTSNTSvc64.exe.config) is used.</span></span> <span data-ttu-id="43de4-110">使用 BizTalk 配置文件时，不会列出许多属性。</span><span class="sxs-lookup"><span data-stu-id="43de4-110">When using the BizTalk configuration file, many properties are not listed.</span></span> <span data-ttu-id="43de4-111">这些属性和它们的默认值仍然适用，即使它们未显式指定配置文件中。</span><span class="sxs-lookup"><span data-stu-id="43de4-111">These properties and their default values are still applied, even if they are not explicitly specified in the configuration file.</span></span>  
  
 <span data-ttu-id="43de4-112">若要更改默认值，可以使用[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]或将它们显式添加到 BizTalk 配置文件。</span><span class="sxs-lookup"><span data-stu-id="43de4-112">To change the default values, you can use [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] or explicitly add them to the BizTalk configuration file.</span></span> <span data-ttu-id="43de4-113">有关详细信息，请参阅[使用设置仪表板进行 BizTalk Server 性能调整](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)并[BTSNTSvc.exe.config 文件](../core/btsntsvc-exe-config-file.md)。</span><span class="sxs-lookup"><span data-stu-id="43de4-113">For more information, see [Using Settings Dashboard for BizTalk Server Performance Tuning](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md) and [BTSNTSvc.exe.config File](../core/btsntsvc-exe-config-file.md).</span></span>  
  
 <span data-ttu-id="43de4-114">**冻结**</span><span class="sxs-lookup"><span data-stu-id="43de4-114">**Dehydration**</span></span>  
  
- <span data-ttu-id="43de4-115">**MaxThreshold** = 1800</span><span class="sxs-lookup"><span data-stu-id="43de4-115">**MaxThreshold** = 1800</span></span>  
  
- <span data-ttu-id="43de4-116">**MinThreshold** = 1</span><span class="sxs-lookup"><span data-stu-id="43de4-116">**MinThreshold** = 1</span></span>  
  
- <span data-ttu-id="43de4-117">**ConstantThreshold** = -1</span><span class="sxs-lookup"><span data-stu-id="43de4-117">**ConstantThreshold** = -1</span></span>  
  
  <span data-ttu-id="43de4-118">**VirtualMemoryThrottlingCriteria**</span><span class="sxs-lookup"><span data-stu-id="43de4-118">**VirtualMemoryThrottlingCriteria**</span></span>  
  
- <span data-ttu-id="43de4-119">**OptimalUsage** = 900</span><span class="sxs-lookup"><span data-stu-id="43de4-119">**OptimalUsage** = 900</span></span>  
  
- <span data-ttu-id="43de4-120">**MaximalUsage** = 1300年</span><span class="sxs-lookup"><span data-stu-id="43de4-120">**MaximalUsage** =  1300</span></span>  
  
- <span data-ttu-id="43de4-121">**IsActive** = true</span><span class="sxs-lookup"><span data-stu-id="43de4-121">**IsActive** = true</span></span>  
  
  <span data-ttu-id="43de4-122">**PrivateMemoryThrottlingCriteria**</span><span class="sxs-lookup"><span data-stu-id="43de4-122">**PrivateMemoryThrottlingCriteria**</span></span>  
  
- <span data-ttu-id="43de4-123">**OptimalUsage** = 50</span><span class="sxs-lookup"><span data-stu-id="43de4-123">**OptimalUsage** = 50</span></span>  
  
- <span data-ttu-id="43de4-124">**MaximalUsage** = 350</span><span class="sxs-lookup"><span data-stu-id="43de4-124">**MaximalUsage** =  350</span></span>  
  
- <span data-ttu-id="43de4-125">**IsActive** = true</span><span class="sxs-lookup"><span data-stu-id="43de4-125">**IsActive** = true</span></span>  
  
  <span data-ttu-id="43de4-126">**PhysicalMemoryThrottlingCriteria**</span><span class="sxs-lookup"><span data-stu-id="43de4-126">**PhysicalMemoryThrottlingCriteria**</span></span>  
  
- <span data-ttu-id="43de4-127">**OptimalUsage** = 90</span><span class="sxs-lookup"><span data-stu-id="43de4-127">**OptimalUsage** = 90</span></span>  
  
- <span data-ttu-id="43de4-128">**MaximalUsage** = 95</span><span class="sxs-lookup"><span data-stu-id="43de4-128">**MaximalUsage** =  95</span></span>  
  
- <span data-ttu-id="43de4-129">**IsActive** = false</span><span class="sxs-lookup"><span data-stu-id="43de4-129">**IsActive** = false</span></span>  
  
  <span data-ttu-id="43de4-130">每个属性是下一步了详细说明。</span><span class="sxs-lookup"><span data-stu-id="43de4-130">Each of these properties is described in detail next.</span></span>  
  
## <a name="dehydration"></a><span data-ttu-id="43de4-131">冻结</span><span class="sxs-lookup"><span data-stu-id="43de4-131">Dehydration</span></span>  
 <span data-ttu-id="43de4-132">**MaxThreshold**并**MinThreshold**是右上并降低在秒，可以在订阅 （即，被阻止接收、 侦听或延迟） 被冻结之前阻止业务流程的时间的指定边界。</span><span class="sxs-lookup"><span data-stu-id="43de4-132">**MaxThreshold** and **MinThreshold** are the upper and lower bounds, in seconds, of the time that an orchestration can be blocked at a subscription (that is, blocked by a receive, listen, or delay) before being dehydrated.</span></span> <span data-ttu-id="43de4-133">也将值计算在运行时，调用**TestThreshold**，且其值，以秒为单位之间**MinThreshold**并**MaxThreshold**。</span><span class="sxs-lookup"><span data-stu-id="43de4-133">There will also be a value calculated at run-time, called **TestThreshold**, and its value, measured in seconds, is between **MinThreshold** and **MaxThreshold**.</span></span>  
  
 <span data-ttu-id="43de4-134">如果您设置一个值除默认值为-1，表示**ConstantThreshold**，不会运行时值**TestThreshold**。</span><span class="sxs-lookup"><span data-stu-id="43de4-134">If you set a value besides the default of -1 for **ConstantThreshold**, there will not be a run-time value **TestThreshold**.</span></span> <span data-ttu-id="43de4-135">当在一个订阅，阻止业务流程并多长时间阻止在该订阅业务流程的所有实例的历史记录的值大于**TestThreshold**，然后将该业务流程冻结。</span><span class="sxs-lookup"><span data-stu-id="43de4-135">When an orchestration is blocked at a subscription, and the history of how long all instances of that orchestration have been blocked at that subscription is greater than the value of **TestThreshold**, then the orchestration will dehydrate.</span></span> <span data-ttu-id="43de4-136">否则为如果历史记录是小于**TestThreshold**业务流程不冻结的值。</span><span class="sxs-lookup"><span data-stu-id="43de4-136">Otherwise, if the history is less than **TestThreshold** value the orchestration will not dehydrate.</span></span> <span data-ttu-id="43de4-137">此外，即使历史记录指示冻结将不会发生，如果当前阻止时间达到 2<em>\* TestThreshold</em>，则冻结会发生。</span><span class="sxs-lookup"><span data-stu-id="43de4-137">Also, even if the history indicates that dehydration will not take place, if the current blocking time reaches 2<em>\*TestThreshold</em>, then the dehydration will take place.</span></span> <span data-ttu-id="43de4-138">但是如果等待时间小于 10，等待时间的历史记录中，将由最后 10 个等待时间 （秒），平均值或的平均值定义历史记录。</span><span class="sxs-lookup"><span data-stu-id="43de4-138">The history is defined by the average of the last 10 waiting times in seconds, or the average of however many waiting times there are in the history if the waiting times are less than 10.</span></span>  
  
 <span data-ttu-id="43de4-139">时的值**TestThreshold**趋向于**MinThreshold**内存使用率增加时，调用"基于内存的冻结阻止。"</span><span class="sxs-lookup"><span data-stu-id="43de4-139">When the value of **TestThreshold** tends toward **MinThreshold** as memory usage increases, it is called "memory based dehydration throttling."</span></span> <span data-ttu-id="43de4-140">基于内存的冻结阻止允许更多的业务流程实例，便会生效，因为其中任何一个阻止时等待工作 （即，等待消息或延迟），它们可冻结并从内存中撤出。</span><span class="sxs-lookup"><span data-stu-id="43de4-140">Memory-based dehydration throttling allows more orchestration instances to be live because when any of them are blocked waiting for work (that is, waiting for a message or a delay), they can be dehydrated and taken out of memory.</span></span> <span data-ttu-id="43de4-141">**TestThreshold**是单调递减函数的内存使用量，它是与内存使用率成反比。</span><span class="sxs-lookup"><span data-stu-id="43de4-141">**TestThreshold** is a monotonically decreasing function of memory usage, it is inversely proportional to memory usage.</span></span>  
  
 <span data-ttu-id="43de4-142">以下是各个冻结属性的说明：</span><span class="sxs-lookup"><span data-stu-id="43de4-142">Following are descriptions of the individual Dehydration properties:</span></span>  
  
-   <span data-ttu-id="43de4-143">**MaxThreshold**： 上限，以秒为单位，可以在订阅被冻结之前阻止业务流程的时间。</span><span class="sxs-lookup"><span data-stu-id="43de4-143">**MaxThreshold**: the upper bounds, in seconds, of the time that an orchestration can be blocked at a subscription before being dehydrated.</span></span>  
  
-   <span data-ttu-id="43de4-144">**MinThreshold**： 下限，以秒为单位，可以在订阅被冻结之前阻止业务流程的时间。</span><span class="sxs-lookup"><span data-stu-id="43de4-144">**MinThreshold**: the lower bounds, in seconds, of the time that an orchestration can be blocked at a subscription before being dehydrated.</span></span>  
  
-   <span data-ttu-id="43de4-145">**ConstantThreshold**： 指定的最小值和最大值之间通常根据不断变化的动态阈值。</span><span class="sxs-lookup"><span data-stu-id="43de4-145">**ConstantThreshold**: the dynamic threshold, which usually fluctuates between the minimum and maximum values specified.</span></span> <span data-ttu-id="43de4-146">但是，您可以使阈值的固定的值通过设置此属性。</span><span class="sxs-lookup"><span data-stu-id="43de4-146">However, you can make the threshold a fixed value by setting this property.</span></span> <span data-ttu-id="43de4-147">值为-1 指示引擎不使用常数阈值。</span><span class="sxs-lookup"><span data-stu-id="43de4-147">A value of -1 tells the engine not to use a constant threshold.</span></span> <span data-ttu-id="43de4-148">未将此属性设置为-1 以外的值，因为这样会禁用基于冻结的阻止。</span><span class="sxs-lookup"><span data-stu-id="43de4-148">Don't set this property to a value other than -1 because it will disable dehydration based throttling.</span></span>  
  
## <a name="virtualmemorythrottlingcriteria"></a><span data-ttu-id="43de4-149">VirtualMemoryThrottlingCriteria</span><span class="sxs-lookup"><span data-stu-id="43de4-149">VirtualMemoryThrottlingCriteria</span></span>  
 <span data-ttu-id="43de4-150">目前，虚拟内存可能成为瓶颈由于非托管的堆碎片的 32 位计算机上，因此应当限制也是此资源。</span><span class="sxs-lookup"><span data-stu-id="43de4-150">Currently, virtual memory can become a bottleneck on 32-bit machines due to unmanaged heap fragmentation, so you should throttle by this resource as well.</span></span> <span data-ttu-id="43de4-151">如果设置 /3GB 或者主机运行在 64 位平台上，你应该重新配置。</span><span class="sxs-lookup"><span data-stu-id="43de4-151">You should re-configure if /3GB is set or if the hosts are running on a 64-bit platform.</span></span> <span data-ttu-id="43de4-152">最佳和最大的用法是以 mb 为单位。</span><span class="sxs-lookup"><span data-stu-id="43de4-152">Optimal and maximal usages are in MB.</span></span>  
  
 <span data-ttu-id="43de4-153">以下是各个 VirtualMemoryThrottlingCriteria 属性的说明：</span><span class="sxs-lookup"><span data-stu-id="43de4-153">Following are descriptions of the individual VirtualMemoryThrottlingCriteria properties:</span></span>  
  
-   <span data-ttu-id="43de4-154">**OptimalUsage**:冻结限制开始生效的虚拟内存使用情况的量。</span><span class="sxs-lookup"><span data-stu-id="43de4-154">**OptimalUsage**: The amount of virtual memory usage at which dehydration throttling begins to take effect.</span></span> <span data-ttu-id="43de4-155">在此情况下， **TestThreshold**具有值**MaxThreshold** ，大于任何内存使用量**OptimalUsage**会导致**TestThreshold**为小于**MaxThreshold**。</span><span class="sxs-lookup"><span data-stu-id="43de4-155">At this point, **TestThreshold** has the value **MaxThreshold** and any memory usage greater than **OptimalUsage** causes **TestThreshold** to be less than **MaxThreshold**.</span></span>  
  
-   <span data-ttu-id="43de4-156">**MaximalUsage**:冻结限制为最大值的虚拟内存使用情况的量。</span><span class="sxs-lookup"><span data-stu-id="43de4-156">**MaximalUsage**: The amount of virtual memory usage at which dehydration throttling is at a maximum.</span></span> <span data-ttu-id="43de4-157">在此情况下， **TestThreshold**具有值**MinThreshold** ，任何内存使用量小于**MaximalUsage**会导致**TestThreshold**大于**MinThreshold**。</span><span class="sxs-lookup"><span data-stu-id="43de4-157">At this point, **TestThreshold** has the value **MinThreshold** and any memory usage less than **MaximalUsage** causes **TestThreshold** to be greater than **MinThreshold**.</span></span>  
  
-   <span data-ttu-id="43de4-158">**IsActive**:一个布尔值，该值指示虚拟内存阻止是否处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="43de4-158">**IsActive**: A boolean value indicating if virtual memory throttling is active.</span></span>  
  
## <a name="privatememorythrottlingcriteria"></a><span data-ttu-id="43de4-159">PrivateMemoryThrottlingCriteria</span><span class="sxs-lookup"><span data-stu-id="43de4-159">PrivateMemoryThrottlingCriteria</span></span>  
 <span data-ttu-id="43de4-160">此属性的有用标准，限制，但相应的值取决于计算机是否正在运行其他 windows 服务。</span><span class="sxs-lookup"><span data-stu-id="43de4-160">This property is a useful criterion for throttling, but appropriate values depend on whether the computer is running other windows services.</span></span> <span data-ttu-id="43de4-161">如果计算机具有大量内存，并且不与其他 windows 服务共享，则可以显著提高这些值。</span><span class="sxs-lookup"><span data-stu-id="43de4-161">If the computer has a lot of memory and is not being shared with other windows services, then you can increase these values significantly.</span></span>  
  
 <span data-ttu-id="43de4-162">以下是各个 PrivateMemoryThrottlingCriteria 属性的说明：</span><span class="sxs-lookup"><span data-stu-id="43de4-162">Following are descriptions of the individual PrivateMemoryThrottlingCriteria properties:</span></span>  
  
-   <span data-ttu-id="43de4-163">**OptimalUsage**： 的专用内存使用量，以 mb 为单位，冻结限制开始生效。</span><span class="sxs-lookup"><span data-stu-id="43de4-163">**OptimalUsage**: the amount of private memory usage, in MB, at which dehydration throttling begins to take effect.</span></span> <span data-ttu-id="43de4-164">此时**TestThreshold**具有值**MaxThreshold** ，大于任何内存使用量**OptimalUsage**会导致**TestThreshold**为小于**MaxThreshold**。</span><span class="sxs-lookup"><span data-stu-id="43de4-164">At this point **TestThreshold** has the value **MaxThreshold** and any memory usage greater than **OptimalUsage** causes **TestThreshold** to be less than **MaxThreshold**.</span></span>  
  
-   <span data-ttu-id="43de4-165">**MaximalUsage**： 的专用内存使用量，以 mb 为单位的最大限制是冻结。</span><span class="sxs-lookup"><span data-stu-id="43de4-165">**MaximalUsage**: the amount of private memory usage, in MB, at which dehydration throttling is at a maximum.</span></span> <span data-ttu-id="43de4-166">此时**TestThreshold**具有值**MinThreshold** ，任何内存使用量小于**MaximalUsage**会导致**TestThreshold**大于**MinThreshold**。</span><span class="sxs-lookup"><span data-stu-id="43de4-166">At this point **TestThreshold** has the value **MinThreshold** and any memory usage less than **MaximalUsage** causes **TestThreshold** to be greater than **MinThreshold**.</span></span>  
  
-   <span data-ttu-id="43de4-167">**IsActive**： 一个布尔值，该值指示专用内存阻止是否处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="43de4-167">**IsActive**: a boolean value indicating if private memory throttling is active.</span></span>  
  
## <a name="physicalmemorythrottlingcriteria"></a><span data-ttu-id="43de4-168">PhysicalMemoryThrottlingCriteria</span><span class="sxs-lookup"><span data-stu-id="43de4-168">PhysicalMemoryThrottlingCriteria</span></span>  
 <span data-ttu-id="43de4-169">没有还物理内存阻止，其中度量单位使用的内存的百分比而不是 MB。</span><span class="sxs-lookup"><span data-stu-id="43de4-169">There is also a physical memory throttling where numbers are measured in percentage of memory used rather than MB.</span></span> <span data-ttu-id="43de4-170">默认情况下，禁用此属性，但可以根据需要启用。</span><span class="sxs-lookup"><span data-stu-id="43de4-170">This property is disabled by default, but you can enable if needed.</span></span>  
  
 <span data-ttu-id="43de4-171">以下是各个 PhysicalMemoryThrottlingCriteria 属性的说明：</span><span class="sxs-lookup"><span data-stu-id="43de4-171">Following are descriptions of the individual PhysicalMemoryThrottlingCriteria properties:</span></span>  
  
-   <span data-ttu-id="43de4-172">**OptimalUsage**： 的物理内存用于主机实例的最佳百分比。</span><span class="sxs-lookup"><span data-stu-id="43de4-172">**OptimalUsage**: the optimum percentage of physical memory to use for the host instances.</span></span>  
  
-   <span data-ttu-id="43de4-173">**MaximalUsage**： 要用于主机实例的物理内存的最大百分比。</span><span class="sxs-lookup"><span data-stu-id="43de4-173">**MaximalUsage**: the maximum percentage of physical memory to use for the host instances.</span></span>  
  
-   <span data-ttu-id="43de4-174">**IsActive**： 布尔值，该值指示物理内存阻止是否处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="43de4-174">**IsActive**: boolean value indicating if physical memory throttling is active.</span></span>  
  
## <a name="dehydration-properties-behavior"></a><span data-ttu-id="43de4-175">冻结属性行为</span><span class="sxs-lookup"><span data-stu-id="43de4-175">Dehydration Properties Behavior</span></span>  
 <span data-ttu-id="43de4-176">BizTalk Server 使用这些冻结属性来确定何时冻结和解除冻结业务流程。</span><span class="sxs-lookup"><span data-stu-id="43de4-176">BizTalk Server uses these dehydration properties to decide when to dehydrate and rehydrate orchestrations.</span></span> <span data-ttu-id="43de4-177">在正常负载时，默认冻结值就足够了，但如果在重负载下运行，并且希望改变性能特征，您应该自己进行优化。</span><span class="sxs-lookup"><span data-stu-id="43de4-177">Under normal load, the default dehydration values are sufficient, but if you are running under heavy load and want to change performance characteristics, you should do the tuning yourself.</span></span>  
  
 <span data-ttu-id="43de4-178">BizTalk Server 的冻结行为完全取决于可用内存量是以及所使用的内存量。</span><span class="sxs-lookup"><span data-stu-id="43de4-178">The dehydration behavior of BizTalk Server depends entirely on how much memory is available and how much memory is being used.</span></span> <span data-ttu-id="43de4-179">冻结行为也不同于在不同数量的内存和内存使用 32 位和 64 位主机之间的差异。</span><span class="sxs-lookup"><span data-stu-id="43de4-179">The dehydration behavior is different with different amounts of memory and differences in memory use between 32-bit and 64-bit hosts.</span></span>  
  
 <span data-ttu-id="43de4-180">冻结属性来区分专用字节数和虚拟字节数之间的业务流程主机：</span><span class="sxs-lookup"><span data-stu-id="43de4-180">The dehydration properties distinguish between Private Bytes and Virtual Bytes for the orchestration host:</span></span>  
  
-   <span data-ttu-id="43de4-181">**虚拟字节**。</span><span class="sxs-lookup"><span data-stu-id="43de4-181">**Virtual Bytes**.</span></span> <span data-ttu-id="43de4-182">这是当前大小，以字节为单位的进程正在使用的虚拟地址空间。</span><span class="sxs-lookup"><span data-stu-id="43de4-182">This is thecurrent size, in bytes, of the virtual address space the process is using.</span></span> <span data-ttu-id="43de4-183">使用虚拟地址空间不一定意味着使用相应的磁盘或主内存页。</span><span class="sxs-lookup"><span data-stu-id="43de4-183">Use of virtual address space does not necessarily imply corresponding use of either disk or main memory pages.</span></span> <span data-ttu-id="43de4-184">虚拟空间是有限的而且进程可以限制其加载库的能力。</span><span class="sxs-lookup"><span data-stu-id="43de4-184">Virtual space is finite, and the process can limit its ability to load libraries.</span></span>  
  
-   <span data-ttu-id="43de4-185">**专用字节数**。</span><span class="sxs-lookup"><span data-stu-id="43de4-185">**Private Bytes**.</span></span> <span data-ttu-id="43de4-186">这是内存的当前大小 （字节），此进程已分配不能与其他进程共享。</span><span class="sxs-lookup"><span data-stu-id="43de4-186">This is the current size, in bytes, of memory that this process has allocated that cannot be shared with other processes.</span></span>
