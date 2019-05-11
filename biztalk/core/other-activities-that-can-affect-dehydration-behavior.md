---
title: 可能会影响冻结行为的其他活动 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ed940448-d3b1-4308-9b38-887904e03bd0
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb3fcbb2799cba8e808c2bd2da66c09706fe7a33
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393455"
---
# <a name="other-activities-that-can-affect-dehydration-behavior"></a>其他可影响冻结行为的活动
以下活动直接或间接影响冻结行为和总体性能，因此应考虑到所有测试方案。  
  
- **BizTalk Server 管理控制台查询。** 这些查询会消耗资源并影响总体吞吐量，具体取决于的类型和查询的频率。  
  
- **备份、 存档和清除活动。** 这些活动也消耗资源，应考虑到所有测试方案。  
  
- **混合的 32 位和 64 位主机。** 下面是使用混合的 32 位和 64 位主机时要考虑一些事项：  
  
  - 在高负荷下我们测量已使用的虚拟和物理内存，并与特定的阈值进行比较的。 在 64 位系统中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]过程使用更多的内存，因此在冻结策略区别的 32 位使用相同的系统和相同的默认值。 请确保单独的业务流程、 接收、 发送和消息框主机。  
  
     没有存在明显的差异对于 64 位系统，使用默认 32 位阈值时，只要只有业务流程主机是在 64 位计算机上。 但是，在压力的各种**MemoryThrottlingCriteria**设置应至少增加一倍或增加两倍 （只要有足够的内存），但方案进行调整，因为有许多最大化吞吐量派上用场的因素。 应调整各个冻结阈值，若要查找什么是它们的最佳的压力下。  
  
  - 冻结行为依赖于每个订阅; 的传送时间历史记录对于不同的订阅因此请这考虑在优化冻结属性值，则历史记录可能会有所不同。  
  
  - 当业务流程主机服务回收在一台主机上但不是在另一台，则历史记录将不同。  
  
  - 当服务器使用不同版本的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，将两者之间的冻结策略区别。  
  
## <a name="see-also"></a>请参阅  
 [BTSNTSvc.exe.config 文件](../core/btsntsvc-exe-config-file.md)