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
# <a name="dehydration-default-properties"></a>冻结默认属性
以下是冻结属性及其默认值的名称。 这些属性是可在中配置[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]或作为 XML 在 BizTalk 配置文件 （BTSNTSvc.exe.config 或 BTSNTSvc64.exe.config）。 首先应用 BizTalk 配置文件中的值。 然后，[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]应用设置。 所有主机实例包含业务流程开始时将读取冻结属性。  
  
> [!IMPORTANT]
>  并非所有的业务流程设置都在[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]。 这些设置，请使用 BizTalk 配置文件 （BTSNTSvc.exe.config 或 BTSNTSvc64.exe.config）。 使用 BizTalk 配置文件时，不会列出许多属性。 这些属性和它们的默认值仍然适用，即使它们未显式指定配置文件中。  
  
 若要更改默认值，可以使用[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]或将它们显式添加到 BizTalk 配置文件。 有关详细信息，请参阅[使用设置仪表板进行 BizTalk Server 性能调整](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)并[BTSNTSvc.exe.config 文件](../core/btsntsvc-exe-config-file.md)。  
  
 **冻结**  
  
- **MaxThreshold** = 1800  
  
- **MinThreshold** = 1  
  
- **ConstantThreshold** = -1  
  
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
  
  每个属性是下一步了详细说明。  
  
## <a name="dehydration"></a>冻结  
 **MaxThreshold**并**MinThreshold**是右上并降低在秒，可以在订阅 （即，被阻止接收、 侦听或延迟） 被冻结之前阻止业务流程的时间的指定边界。 也将值计算在运行时，调用**TestThreshold**，且其值，以秒为单位之间**MinThreshold**并**MaxThreshold**。  
  
 如果您设置一个值除默认值为-1，表示**ConstantThreshold**，不会运行时值**TestThreshold**。 当在一个订阅，阻止业务流程并多长时间阻止在该订阅业务流程的所有实例的历史记录的值大于**TestThreshold**，然后将该业务流程冻结。 否则为如果历史记录是小于**TestThreshold**业务流程不冻结的值。 此外，即使历史记录指示冻结将不会发生，如果当前阻止时间达到 2<em>* TestThreshold</em>，则冻结会发生。 但是如果等待时间小于 10，等待时间的历史记录中，将由最后 10 个等待时间 （秒），平均值或的平均值定义历史记录。  
  
 时的值**TestThreshold**趋向于**MinThreshold**内存使用率增加时，调用"基于内存的冻结阻止。" 基于内存的冻结阻止允许更多的业务流程实例，便会生效，因为其中任何一个阻止时等待工作 （即，等待消息或延迟），它们可冻结并从内存中撤出。 **TestThreshold**是单调递减函数的内存使用量，它是与内存使用率成反比。  
  
 以下是各个冻结属性的说明：  
  
-   **MaxThreshold**： 上限，以秒为单位，可以在订阅被冻结之前阻止业务流程的时间。  
  
-   **MinThreshold**： 下限，以秒为单位，可以在订阅被冻结之前阻止业务流程的时间。  
  
-   **ConstantThreshold**： 指定的最小值和最大值之间通常根据不断变化的动态阈值。 但是，您可以使阈值的固定的值通过设置此属性。 值为-1 指示引擎不使用常数阈值。 未将此属性设置为-1 以外的值，因为这样会禁用基于冻结的阻止。  
  
## <a name="virtualmemorythrottlingcriteria"></a>VirtualMemoryThrottlingCriteria  
 目前，虚拟内存可能成为瓶颈由于非托管的堆碎片的 32 位计算机上，因此应当限制也是此资源。 如果设置 /3GB 或者主机运行在 64 位平台上，你应该重新配置。 最佳和最大的用法是以 mb 为单位。  
  
 以下是各个 VirtualMemoryThrottlingCriteria 属性的说明：  
  
-   **OptimalUsage**:冻结限制开始生效的虚拟内存使用情况的量。 在此情况下， **TestThreshold**具有值**MaxThreshold** ，大于任何内存使用量**OptimalUsage**会导致**TestThreshold**为小于**MaxThreshold**。  
  
-   **MaximalUsage**:冻结限制为最大值的虚拟内存使用情况的量。 在此情况下， **TestThreshold**具有值**MinThreshold** ，任何内存使用量小于**MaximalUsage**会导致**TestThreshold**大于**MinThreshold**。  
  
-   **IsActive**:一个布尔值，该值指示虚拟内存阻止是否处于活动状态。  
  
## <a name="privatememorythrottlingcriteria"></a>PrivateMemoryThrottlingCriteria  
 此属性的有用标准，限制，但相应的值取决于计算机是否正在运行其他 windows 服务。 如果计算机具有大量内存，并且不与其他 windows 服务共享，则可以显著提高这些值。  
  
 以下是各个 PrivateMemoryThrottlingCriteria 属性的说明：  
  
-   **OptimalUsage**： 的专用内存使用量，以 mb 为单位，冻结限制开始生效。 此时**TestThreshold**具有值**MaxThreshold** ，大于任何内存使用量**OptimalUsage**会导致**TestThreshold**为小于**MaxThreshold**。  
  
-   **MaximalUsage**： 的专用内存使用量，以 mb 为单位的最大限制是冻结。 此时**TestThreshold**具有值**MinThreshold** ，任何内存使用量小于**MaximalUsage**会导致**TestThreshold**大于**MinThreshold**。  
  
-   **IsActive**： 一个布尔值，该值指示专用内存阻止是否处于活动状态。  
  
## <a name="physicalmemorythrottlingcriteria"></a>PhysicalMemoryThrottlingCriteria  
 没有还物理内存阻止，其中度量单位使用的内存的百分比而不是 MB。 默认情况下，禁用此属性，但可以根据需要启用。  
  
 以下是各个 PhysicalMemoryThrottlingCriteria 属性的说明：  
  
-   **OptimalUsage**： 的物理内存用于主机实例的最佳百分比。  
  
-   **MaximalUsage**： 要用于主机实例的物理内存的最大百分比。  
  
-   **IsActive**： 布尔值，该值指示物理内存阻止是否处于活动状态。  
  
## <a name="dehydration-properties-behavior"></a>冻结属性行为  
 BizTalk Server 使用这些冻结属性来确定何时冻结和解除冻结业务流程。 在正常负载时，默认冻结值就足够了，但如果在重负载下运行，并且希望改变性能特征，您应该自己进行优化。  
  
 BizTalk Server 的冻结行为完全取决于可用内存量是以及所使用的内存量。 冻结行为也不同于在不同数量的内存和内存使用 32 位和 64 位主机之间的差异。  
  
 冻结属性来区分专用字节数和虚拟字节数之间的业务流程主机：  
  
-   **虚拟字节**。 这是当前大小，以字节为单位的进程正在使用的虚拟地址空间。 使用虚拟地址空间不一定意味着使用相应的磁盘或主内存页。 虚拟空间是有限的而且进程可以限制其加载库的能力。  
  
-   **专用字节数**。 这是内存的当前大小 （字节），此进程已分配不能与其他进程共享。
