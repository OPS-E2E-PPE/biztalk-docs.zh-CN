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
ms.openlocfilehash: ed8c37dbcca5c15e777cf6a98e50227f8752e324
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979294"
---
# <a name="other-activities-that-can-affect-dehydration-behavior"></a>其他可影响冻结行为的活动
以下活动直接或间接影响冻结行为和总体性能，因此在所有的测试方案中都应考虑这些活动。  
  
- **BizTalk Server 管理控制台查询。** 这些查询会消耗资源并影响总体吞吐量，具体取决于查询的类型和频率。  
  
- **备份、 存档和清除活动。** 这些活动也会消耗资源，在所有测试方案中都应考虑到这些活动。  
  
- **混合的 32 位和 64 位主机。** 混合使用 32 位和 64 位主机时应注意以下事项：  
  
  - 在任务繁忙的情况下，应测量所消耗的虚拟内存和物理内存，并将其与特定的阈值进行比较。 在 64 位系统中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]过程使用更多的内存，因此在冻结策略区别的 32 位使用相同的系统和相同的默认值。 请确保将业务流程、接收主机、发送主机和消息框主机分离开。  
  
     只要 64 位系统上只有业务流程主机，则对 64 位系统使用默认的 32 位阈值时不会存在明显的差异。 但是，在压力的各种**MemoryThrottlingCriteria**设置应至少增加一倍或增加两倍 （只要有足够的内存），但方案进行调整，因为有许多最大化吞吐量派上用场的因素。 应在任务繁忙时调整各个冻结阈值以找出它们的最佳值。  
  
  - 冻结行为依赖于每个订阅的传送时间历史记录；订阅不同其历史记录可能也会不同，因此在调整冻结属性值时应考虑到这一点。  
  
  - 如果回收了一台主机上的业务流程主机服务，而没有回收另一台主机上的业务流程主机服务，则历史记录将不同。  
  
  - 当服务器使用不同版本的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 时，这两个版本之间的冻结策略将存在差别。  
  
## <a name="see-also"></a>请参阅  
 [BTSNTSvc.exe.config 文件](../core/btsntsvc-exe-config-file.md)