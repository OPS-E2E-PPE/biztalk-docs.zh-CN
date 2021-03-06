---
title: 如何找出 BAM 主导入数据库的瓶颈 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0372f1f1-d892-4f7d-b6c4-e0f2b5a02f1c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 541e5bcce9420fdbca8af25de9bee24bfb607435
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253475"
---
# <a name="how-to-identify-bottlenecks-in-the-bam-primary-import-database"></a>如何找出 BAM 主导入数据库的瓶颈
若要标识业务活动监视 (BAM) 数据库的瓶颈，请执行以下步骤：  
  
1. 确保活动实例数不再增加。  
  
2. 确保 SQL 代理服务正在运行。  
  
3. 如果配置了 OLAP 分析，请确保 BAM_AN_\<activityname\> job 按周期性间隔运行。  
  
4. 请确保该 BAM_DM_\<activityname\> (Data Maintenance) 作业计划为按定期间隔运行。  
  
   > [!NOTE]
   >  使用率过高方案 BAM 数据库活动中可能会影响其他 BizTalk Server 数据库，这将影响 BizTalk 服务器的总体性能的性能。 在这种情况下请考虑执行下列操作：  
   > 
   > - 请考虑减少从默认值 （6 个月） 的所有 BAM 活动的持续时间为 1 个月或更少。 这将减少为其 BAM 数据会保持在 BAMPrimaryImport 数据库在存档之前的时间段。 使用 BAM 管理实用程序`set-activitywindow`命令修改 BAM 活动的持续时间。 有关 BAM 管理实用程序的活动管理命令请参阅[活动管理命令](http://go.microsoft.com/fwlink/?LinkId=210417)(http://go.microsoft.com/fwlink/?LinkId=210417)。  
   >   -   将 BAM 存档数据库移到未承载任何 BizTalk MessageBox 数据库的 SQL Server 的实例。 这将防止这些数据库争用资源，并改进整体性能。  
  
5. 使用专用的主机对其进行跟踪和度量值负载下的主机队列长度性能计数器。  
  
6. 随着时间的推移检查为增长趋势的后台处理表大小性能计数器。  
  
7. 检查长执行时间的存档/清除作业执行持续时间。  
  
8. 检查磁盘响应能力 （读/写性能计数器每秒磁盘） 上承载 BizTalk 跟踪数据库的磁盘。  
  
## <a name="see-also"></a>请参阅  
 [数据库层的瓶颈](../technical-guides/bottlenecks-in-the-database-tier.md)