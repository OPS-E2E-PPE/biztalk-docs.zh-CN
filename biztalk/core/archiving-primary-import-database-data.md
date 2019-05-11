---
title: 将主导入数据库数据存档 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Primary Import database [BAM], archiving data
- archived data, BAM
- managing [BAM], archiving data
- data, archiving [BAM]
ms.assetid: 4a014a59-0578-41fa-9441-8b582f54bbe8
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fff7fe5720df0b73ea84f9387d47a4d35b96051
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530617"
---
# <a name="archiving-primary-import-database-data"></a>将主导入数据库数据存档
管理员可以指定存档主导入数据库中的活动实例数据的时间窗口。 BAMPrimaryImport 数据库中 BAM_Metadata_Activities 表中使用 OnlineWindowTimeUnit 和 OnlineWindowTimeLength 属性。  
  
 如果业务用户部署了多个活动，则可以指定一个不同的时间窗口为每个活动。 有关部署活动的信息，请参阅"定义业务活动"中*信息工作者用户指南*。  
  
 下表介绍可用于 OnlineWindowTimeUnit 和 OnlineWindowTimeLength 的值。  
  
|属性|ReplTest1|  
|--------------|-----------|  
|OnlineWindowTimeUnit|此属性可以是： 月、 日、 小时或分钟。 此属性的默认值为月。|  
|OnlineWindowTimeLength|此属性必须是整数。 此属性的默认值为 6。|  
  
 当分区低于的联机时段 （当前时间-OnlineWindowTimeLength 的 OnlineWindowTimeUnit） 时，BAM 按分区，移动数据从 BAM 主导入数据库。 例如，对于 OnlineWindowTimeLength = 5 和 OnlineWindowTimeUnit 不是删除 5 天 = 日，较旧的分区。  
  
 BAM 将已存档的活动实例数据移到 BAM 存档数据库。 指定 BAM 存档数据库在 BizTalk BAM 配置过程。 有关 BizTalk BAM 配置的信息，请参阅[BAM 配置架构](../core/bam-configuration-schema.md)。  
  
 如果尚未运行 BAM 多维数据集更新到活动多维数据集处理实例数据的数据转换服务 (DTS) 包，BAM 将不会存档活动实例数据。  
  
 有关运行 BAM 数据维护 DTS 包的信息，请参阅[BAM DTS 包](../core/bam-dts-packages.md)。  
  
 随着时间的推移 BAMArchive 数据库将在大小增大添加活动实例数据。 尽管没有简单方法来截断整个数据库，但可以定期截断数据库事务日志，以降低存储要求，并且可以定期备份和存档整个 BAMArchive 数据库。 "截断事务日志"，请参阅 SQL Server 联机丛书中有关详细信息。  
  
## <a name="see-also"></a>请参阅  
 [定义时间范围和时间切片属性](../core/defining-the-time-window-and-time-slice-properties.md)   
 [管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md)