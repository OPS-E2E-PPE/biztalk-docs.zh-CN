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
ms.openlocfilehash: 907bd9f9b47db10a199f5a93a828558dfb3ae210
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981958"
---
# <a name="dehydration-default-properties"></a>冻结默认属性
以下是冻结属性的名称及其默认值。 这些属性在[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]中配置，或作为 XML 在 BizTalk 配置文件（BTSNTSvc.exe.config 或 BTSNTSvc64.exe.config）中配置。 将首先应用 BizTalk 配置文件中的值， 然后应用[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]设置。 所有包含业务流程的主机实例启动后，将读取冻结属性。  
  
> [!IMPORTANT]
>  不是所有业务流程设置都在[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]中公开。 对于这些设置，将使用 BizTalk 配置文件（BTSNTSvc.exe.config 或 BTSNTSvc64.exe.config）。 使用 BizTalk 配置文件时，许多属性并未列出， 但这些属性及其默认值仍然适用，即使并未在配置文件中明确指定它们。  
  
 若要更改默认值，可以使用[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]或将它们显式添加到 BizTalk 配置文件。 有关详细信息，请参阅[使用设置仪表板进行 BizTalk Server 性能调整](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)并[BTSNTSvc.exe.config 文件](../core/btsntsvc-exe-config-file.md)。  
  
 **冻结**  
  
- **MaxThreshold** = 1800年  
  
- **MinThreshold** = 1  
  
- **ConstantThreshold** =-1  
  
  **VirtualMemoryThrottlingCriteria**  
  
- **OptimalUsage** = 900  
  
- **MaximalUsage** = 1300年  
  
- **IsActive** = true  
  
  **PrivateMemoryThrottlingCriteria**  
  
- **OptimalUsage** = 50  
  
- **MaximalUsage** = 350  
  
- **IsActive** = true  
  
  **PhysicalMemoryThrottlingCriteria**  
  
- **OptimalUsage** = 90  
  
- **MaximalUsage** = 95  
  
- **IsActive** = false  
  
  下面对每一个属性详细说明。  
  
## <a name="dehydration"></a>冻结  
 **MaxThreshold**并**MinThreshold**是右上并降低在秒，可以在订阅 （即，被阻止接收、 侦听或延迟） 被冻结之前阻止业务流程的时间的指定边界。 也将值计算在运行时，调用**TestThreshold**，且其值，以秒为单位之间**MinThreshold**并**MaxThreshold**。  
  
 如果您设置一个值除默认值为-1，表示**ConstantThreshold**，不会运行时值**TestThreshold**。 当在一个订阅，阻止业务流程并多长时间阻止在该订阅业务流程的所有实例的历史记录的值大于**TestThreshold**，然后将该业务流程冻结。 否则为如果历史记录是小于**TestThreshold**业务流程不冻结的值。 此外，即使历史记录指示冻结将不会发生，如果当前阻止时间达到 2<em>**TestThreshold</em>*，则冻结会发生。 历史记录由最后 10 个等待时间的平均值定义（秒），或者历史记录中所有等待时间的平均值定义（如果等待次数少于 10）。  
  
 时的值**TestThreshold**趋向于**MinThreshold**内存使用率增加时，调用"基于内存的冻结阻止。" 基于内存的冻结阻止允许更多的业务流程实例生存，因为当其中的任何实例因等待工作（即等待消息或延迟）而被阻止时，会被冻结并从内存中撤出。 **TestThreshold**是单调递减函数的内存使用量，它是与内存使用率成反比。  
  
 以下是各个冻结属性的说明：  
  
-   **MaxThreshold**： 上限，以秒为单位，可以在订阅被冻结之前阻止业务流程的时间。  
  
-   **MinThreshold**： 下限，以秒为单位，可以在订阅被冻结之前阻止业务流程的时间。  
  
-   **ConstantThreshold**： 指定的最小值和最大值之间通常根据不断变化的动态阈值。 不过，可通过设置此属性使阈值成为不变值。 如果值为 -1，表示引擎不使用常数阈值。 不要将此属性设置为除 -1 之外的值，因为这样会禁用基于冻结的阻止。  
  
## <a name="virtualmemorythrottlingcriteria"></a>VirtualMemoryThrottlingCriteria  
 目前，虚拟内存会由于未托管的堆碎片而成为 32 位计算机上的瓶颈，因此，你应该根据此资源进行阻止。 你应该重新配置是否设置 /3GB 或者主机是否运行在 64 位平台上。 最佳使用量和最大使用量的单位为 MB。  
  
 以下是各个 VirtualMemoryThrottlingCriteria 属性的说明：  
  
-   **OptimalUsage**： 的冻结阻止开始生效的虚拟内存使用量。 在此情况下， **TestThreshold**具有值**MaxThreshold** ，大于任何内存使用量**OptimalUsage**会导致**TestThreshold**为小于**MaxThreshold**。  
  
-   **MaximalUsage**： 的虚拟内存使用量冻结限制为最大值。 在此情况下， **TestThreshold**具有值**MinThreshold** ，任何内存使用量小于**MaximalUsage**会导致**TestThreshold**大于**MinThreshold**。  
  
-   **IsActive**： 一个布尔值，该值指示虚拟内存阻止是否处于活动状态。  
  
## <a name="privatememorythrottlingcriteria"></a>PrivateMemoryThrottlingCriteria  
 此属性是一个用于阻止的有用标准，但其值是否合适取决于计算机是否运行其他 Windows 服务。 如果计算机有大量内存，并且不与其他 Windows 服务共享，你可以大幅增加这些值。  
  
 以下是各个 PrivateMemoryThrottlingCriteria 属性的说明：  
  
-   **OptimalUsage**： 的专用内存使用量，以 mb 为单位，冻结限制开始生效。 此时**TestThreshold**具有值**MaxThreshold** ，大于任何内存使用量**OptimalUsage**会导致**TestThreshold**为小于**MaxThreshold**。  
  
-   **MaximalUsage**： 的专用内存使用量，以 mb 为单位的最大限制是冻结。 此时**TestThreshold**具有值**MinThreshold** ，任何内存使用量小于**MaximalUsage**会导致**TestThreshold**大于**MinThreshold**。  
  
-   **IsActive**： 一个布尔值，该值指示专用内存阻止是否处于活动状态。  
  
## <a name="physicalmemorythrottlingcriteria"></a>PhysicalMemoryThrottlingCriteria  
 另外，还有物理内存阻止，其度量单位为内存使用百分比，而不是 MB。 默认情况下，此属性禁用，但你可以根据需要启用它。  
  
 以下是各个 PhysicalMemoryThrottlingCriteria 属性的说明：  
  
-   **OptimalUsage**： 的物理内存用于主机实例的最佳百分比。  
  
-   **MaximalUsage**： 要用于主机实例的物理内存的最大百分比。  
  
-   **IsActive**： 布尔值，该值指示物理内存阻止是否处于活动状态。  
  
## <a name="dehydration-properties-behavior"></a>冻结属性行为  
 BizTalk Server 使用这些冻结属性来确定何时对业务流程冻结和解除冻结。 在正常的负载下，默认冻结值就足够了，但如果运行在较高的负载下，并且希望改变性能特征，应自己进行优化。  
  
 BizTalk Server 的冻结行为完全取决于有多少内存可用以及有多少内存正在使用中。 由于内存量不同以及 32 位和 64 位主机内存使用量不同，冻结行为也不同。  
  
 对于业务流程主机，冻结属性分“专用字节”和“虚拟字节”：  
  
-   **虚拟字节**。 这是当前大小，以字节为单位的进程正在使用的虚拟地址空间。 使用虚拟地址空间不一定意味着要使用磁盘或主内存页。 虚拟空间是有限的，进程可以限制其加载库的能力。  
  
-   **专用字节数**。 是此进程分配的不能与其他进程共享的内存量的当前大小（以字节为单位）。