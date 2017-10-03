---
title: "如何确定 BAM 主导入数据库中的瓶颈 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0372f1f1-d892-4f7d-b6c4-e0f2b5a02f1c
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: decf27009eea6aff0ff5ed9088ae49ef2014b1cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-identify-bottlenecks-in-the-bam-primary-import-database"></a>如何确定 BAM 主导入数据库中的瓶颈
若要确定业务活动监视 (BAM) 数据库中的瓶颈，执行以下步骤：  
  
1.  确保活动实例数不再增加。  
  
2.  确保 SQL 代理服务正在运行。  
  
3.  如果配置 OLAP 分析，确保 BAM_AN_\<activityname > 应按定期间隔运行作业。  
  
4.  确保该 BAM_DM_\<activityname > （数据维护） 作业计划以定期间隔运行。  
  
    > [!NOTE]  
    >  在高使用率方案 BAM 数据库活动可能会影响其他 BizTalk Server 数据库，这将影响整体 BizTalk Server 性能的性能。 在这种情况下，请考虑采取以下措施：  
    >   
    >  -   请考虑减少不再是默认值 （6 个月） 的所有 BAM 活动的持续时间为 1 个月或更少。 这将减少为其 BAM 数据会保持在 BAMPrimaryImport 数据库在存档之前的时间段。 使用 BAM 管理实用程序`set-activitywindow`命令来修改 BAM 活动的持续时间。 BAM 管理实用程序的活动管理有关的详细信息请参阅命令[活动管理命令](http://go.microsoft.com/fwlink/?LinkId=210417)(http://go.microsoft.com/fwlink/?LinkId=210417)。  
    > -   将 BAM 存档数据库移到未承载任何 BizTalk MessageBox 数据库的 SQL Server 的实例。 这将防止这些数据库争用资源，并改进整体性能。  
  
5.  使用专用的主机，对其进行跟踪和度量值负载下的主机 Queue Length 性能计数器。  
  
6.  随着时间的推移检查上升趋势的假脱机表大小性能计数器。  
  
7.  检查长执行时间的存档/清除作业执行持续时间。  
  
8.  检查磁盘响应能力 （读/写性能计数器每次磁盘） 上承载 BizTalk 跟踪数据库的磁盘。  
  
## <a name="see-also"></a>另请参阅  
 [数据库层中的瓶颈](../technical-guides/bottlenecks-in-the-database-tier.md)