---
title: 冻结默认属性 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 68c59def-d73b-4880-9884-ccbe5d982f4b
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff78b1e096f1a73675ffc02550794f5a300f5614
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="dehydration-default-properties"></a>冻结默认属性
以下是冻结属性的名称及其默认值。 这些属性在[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]中配置，或作为 XML 在 BizTalk 配置文件（BTSNTSvc.exe.config 或 BTSNTSvc64.exe.config）中配置。 将首先应用 BizTalk 配置文件中的值， 然后应用[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]设置。 所有包含业务流程的主机实例启动后，将读取冻结属性。  
  
> [!IMPORTANT]
>  不是所有业务流程设置都在[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]中公开。 对于这些设置，将使用 BizTalk 配置文件（BTSNTSvc.exe.config 或 BTSNTSvc64.exe.config）。 使用 BizTalk 配置文件时，许多属性并未列出， 但这些属性及其默认值仍然适用，即使并未在配置文件中明确指定它们。  
  
 若要更改默认值，可以使用[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]或将它们显式添加到 BizTalk 配置文件。 有关详细信息，请参阅[BizTalk Server 性能优化使用设置仪表板](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)和[BTSNTSvc.exe.config 文件](../core/btsntsvc-exe-config-file.md)。  
  
 **冻结**  
  
-   **MaxThreshold** = 1800年  
  
-   **MinThreshold** = 1  
  
-   **ConstantThreshold** =-1  
  
 **VirtualMemoryThrottlingCriteria**  
  
-   **OptimalUsage** = 900  
  
-   **MaximalUsage** = 1300年  
  
-   **IsActive** = true  
  
 **PrivateMemoryThrottlingCriteria**  
  
-   **OptimalUsage** = 50  
  
-   **MaximalUsage** = 350  
  
-   **IsActive** = true  
  
 **PhysicalMemoryThrottlingCriteria**  
  
-   **OptimalUsage** = 90  
  
-   **MaximalUsage** = 95  
  
-   **IsActive** = false  
  
 下面对每一个属性详细说明。  
  
## <a name="dehydration"></a>冻结  
 **MaxThreshold** 和 **MinThreshold** 上限，并且在中较低层边界，秒，可以在订阅 （即，被阻止接收、 侦听或延迟） 之前的冻结拒绝业务流程的时间。 也将一个值在运行时计算，调用 **TestThreshold**, ，且其值，以秒，单位为之间 **MinThreshold** 和 **MaxThreshold**。  
  
 如果你设置除了默认值为-1 值 **ConstantThreshold**, ，不会运行时值 **TestThreshold**。 当业务流程阻止在一个订阅，并且该业务流程的所有实例多长时间被都阻止在该订阅的历史记录大于的值 **TestThreshold**, ，然后将冻结业务流程。 否则为如果历史记录是小于 **TestThreshold** 业务流程将未冻结的值。 此外，即使历史记录指示，冻结不会发生，如果当前的阻塞时间达到 2 ***TestThreshold**, ，则冻结，会进行。 历史记录由最后 10 个等待时间的平均值定义（秒），或者历史记录中所有等待时间的平均值定义（如果等待次数少于 10）。  
  
 时的值 **TestThreshold** 往往推进到 **MinThreshold** 内存使用率增加时调用"内存情况基于冻结限制"。 基于内存的冻结阻止允许更多的业务流程实例生存，因为当其中的任何实例因等待工作（即等待消息或延迟）而被阻止时，会被冻结并从内存中撤出。 **TestThreshold** 是单调递减函数的内存使用情况，它是与内存使用量成反比。  
  
 以下是各个冻结属性的说明：  
  
-   **MaxThreshold**︰ 上限，以秒为单位，可以在订阅，然后才能被冻结拒绝业务流程的时间。  
  
-   **MinThreshold**︰ 下限，以秒为单位，可以在订阅，然后才能被冻结拒绝业务流程的时间。  
  
-   **ConstantThreshold**︰ 指定的最小和最大值之间通常根据不断变化的动态阈值。 不过，可通过设置此属性使阈值成为不变值。 如果值为 -1，表示引擎不使用常数阈值。 不要将此属性设置为除 -1 之外的值，因为这样会禁用基于冻结的阻止。  
  
## <a name="virtualmemorythrottlingcriteria"></a>VirtualMemoryThrottlingCriteria  
 目前，虚拟内存会由于未托管的堆碎片而成为 32 位计算机上的瓶颈，因此，你应该根据此资源进行阻止。 你应该重新配置是否设置 /3GB 或者主机是否运行在 64 位平台上。 最佳使用量和最大使用量的单位为 MB。  
  
 以下是各个 VirtualMemoryThrottlingCriteria 属性的说明：  
  
-   **OptimalUsage**︰ 的虚拟内存使用量的冻结限制开始处生效。 此时， **TestThreshold** 具有值 **MaxThreshold** 和任何内存使用率大于 **OptimalUsage** 会导致 **TestThreshold** 要小于 **MaxThreshold**。  
  
-   **MaximalUsage**︰ 的虚拟内存使用量的最大限制是在哪个冻结。 此时， **TestThreshold** 具有值 **MinThreshold** 和任何内存使用率小于 **MaximalUsage** 会导致 **TestThreshold** 必须晚于 **MinThreshold**。  
  
-   **IsActive**︰ 一个布尔值，该值指示虚拟内存限制是否处于活动状态。  
  
## <a name="privatememorythrottlingcriteria"></a>PrivateMemoryThrottlingCriteria  
 此属性是一个用于阻止的有用标准，但其值是否合适取决于计算机是否运行其他 Windows 服务。 如果计算机有大量内存，并且不与其他 Windows 服务共享，你可以大幅增加这些值。  
  
 以下是各个 PrivateMemoryThrottlingCriteria 属性的说明：  
  
-   **OptimalUsage**︰ 的专用内存使用量，以 mb 为单位，哪些冻结限制开始处生效。 此时 **TestThreshold** 具有值 **MaxThreshold** 和任何内存使用率大于 **OptimalUsage** 导致 **TestThreshold** 要小于 **MaxThreshold**。  
  
-   **MaximalUsage**︰ 的专用内存使用量，以 mb 为单位的最大限制是在哪个冻结。 此时 **TestThreshold** 具有值 **MinThreshold** 和任何内存使用率小于 **MaximalUsage** 导致 **TestThreshold** 必须晚于 **MinThreshold**。  
  
-   **IsActive**︰ 一个布尔值，该值专用内存限制是否处于活动状态。  
  
## <a name="physicalmemorythrottlingcriteria"></a>PhysicalMemoryThrottlingCriteria  
 另外，还有物理内存阻止，其度量单位为内存使用百分比，而不是 MB。 默认情况下，此属性禁用，但你可以根据需要启用它。  
  
 以下是各个 PhysicalMemoryThrottlingCriteria 属性的说明：  
  
-   **OptimalUsage**︰ 要使用的主机实例的物理内存的最佳百分比。  
  
-   **MaximalUsage**︰ 要使用的主机实例的物理内存的最大百分比。  
  
-   **IsActive**︰ 布尔值，该值指示是否物理内存限制为活动状态。  
  
## <a name="dehydration-properties-behavior"></a>冻结属性行为  
 BizTalk Server 使用这些冻结属性来确定何时对业务流程冻结和解除冻结。 在正常的负载下，默认冻结值就足够了，但如果运行在较高的负载下，并且希望改变性能特征，应自己进行优化。  
  
 BizTalk Server 的冻结行为完全取决于有多少内存可用以及有多少内存正在使用中。 由于内存量不同以及 32 位和 64 位主机内存使用量不同，冻结行为也不同。  
  
 对于业务流程主机，冻结属性分“专用字节”和“虚拟字节”：  
  
-   **虚拟字节**。 这是当前大小，以字节为单位的进程正在使用的虚拟地址空间。 使用虚拟地址空间不一定意味着要使用磁盘或主内存页。 虚拟空间是有限的，进程可以限制其加载库的能力。  
  
-   **专用字节**。 是此进程分配的不能与其他进程共享的内存量的当前大小（以字节为单位）。