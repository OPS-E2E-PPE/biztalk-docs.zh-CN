---
title: 如何找出跟踪数据库的瓶颈 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9b72e726-6225-47a0-8e1d-0f5a9cf745d3
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc63ae8f673b25c4acbd2f7c066c38f2cb58d914
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011014"
---
# <a name="how-to-identify-bottlenecks-in-the-tracking-database"></a>如何找出跟踪数据库的瓶颈
若要确定 BizTalk 跟踪 (BizTalkDTADb) 数据库的瓶颈，执行以下步骤：  
  
1. 确保 SQL 代理服务正在运行。  
  
2. 确保存档/清除作业正在运行并成功完成。  
  
3. 确保 TrackedMessages_Copy_BizTalkMsgBoxDB 作业正在运行，成功完成。  
  
4. 验证有足够的磁盘空间可用于 DTADb 存档和数据库增长。  
  
5. 使用专用的主机对其进行跟踪和度量值负载下的主机队列长度性能计数器。  
  
6. 随着时间的推移检查为增长趋势的后台处理表大小性能计数器。  
  
7. 检查长执行时间的存档/清除作业执行持续时间。  
  
8. 检查磁盘响应能力 （读/写性能计数器每秒磁盘） 上承载 BizTalk 跟踪数据库的磁盘。  
  
   我们强烈建议优化 dtasp_BackupAndPurgeTrackingDatabase 或 dtasp_PurgeTrackingDatabase 调用 DTA 清除和存档作业的以下参数值：  
  
- @nLiveHours tinyint — 任何已完成实例早于 （生存小时数） + （生存天数） 也会删除所有关联的数据。 默认值为 0 小时。  
  
- @nLiveDays tinyint — 任何已完成实例早于 （生存小时数） + （生存天数） 也会删除所有关联的数据。 默认间隔为 1 天。  
  
- @nHardDeleteDays tinyint — 所有数据 （即使数据不完整） 早于此将被删除。 为 HardDeleteDays 指定的时间间隔应大于数据生存时段。 数据生存时段是维护 BizTalk 跟踪 (BizTalkDTADb) 数据库中的跟踪数据所需的时间间隔。 早于此间隔的所有内容都应在下一次存档时进行存档，然后清除。 默认值为 30 天。  
  
  应根据数据保留策略在生产环境中，设置这些参数，而在性能实验室测试中，建议你使用的值，如下所示：  
  
  声明@dtLastBackup设置的日期时间@dtLastBackup= getutcdate （）  
  exec dtasp_PurgeTrackingDatabase 1，0，1， @dtLastBackup  
  
## <a name="see-also"></a>请参阅  
 [数据库层的瓶颈](../technical-guides/bottlenecks-in-the-database-tier.md)