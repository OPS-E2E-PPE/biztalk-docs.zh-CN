---
title: "将主导入数据库数据存档 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Primary Import database [BAM], archiving data
- archived data, BAM
- managing [BAM], archiving data
- data, archiving [BAM]
ms.assetid: 4a014a59-0578-41fa-9441-8b582f54bbe8
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c0fdfd55681fabd1b6cfc72f68b7e33150a121f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="archiving-primary-import-database-data"></a>将主导入数据库数据存档
管理员可以指定存档主导入数据库中的活动实例数据的时段。 您可以在 BAMPrimaryImport 数据库的 BAM_Metadata_Activities 表中使用 OnlineWindowTimeUnit 和 OnlineWindowTimeLength 属性。  
  
 如果业务用户已部署了多个活动，则可为每个活动指定不同时段。 有关部署活动的信息，请参阅"定义业务活动"中*信息工作者用户指南*。  
  
 下表说明了可用于 OnlineWindowTimeUnit 和 OnlineWindowTimeLength 的值。  
  
|属性|值|  
|--------------|-----------|  
|OnlineWindowTimeUnit|此属性可以是： 月、 日、 小时或分钟。 此属性的默认值为“月”。|  
|OnlineWindowTimeLength|此属性必须为整数。 此属性的默认值为 6。|  
  
 当分区为早于联机窗口 （当前时间-OnlineWindowTimeLength OnlineWindowTimeUnit） 时，BAM 按分区，移动数据从 BAM 主导入数据库。 例如，对于 OnlineWindowTimeLength = 5 和 OnlineWindowTimeUnit 不是删除 5 天 = 日，较旧的分区。  
  
 BAM 将存档的活动实例数据移动到 BAM 存档数据库。 指定 BAM 数据库存档在 BizTalk BAM 配置过程。 有关 BizTalk BAM 配置的信息，请参阅[BAM 配置架构](../core/bam-configuration-schema.md)。  
  
 BAM 将存档活动实例数据，如果你尚未运行 BAM 多维数据集更新到活动多维数据集处理实例数据的数据转换服务 (DTS) 包。  
  
 有关运行 BAM 数据维护 DTS 包的信息，请参阅[BAM DTS 包](../core/bam-dts-packages.md)。  
  
 随着时间的推移，BAMArchive 数据库的大小会随着活动实例数据的添加而增大。 尽管没有简便的方法来截断整个数据库，但可以定期截断数据库事务日志以减少存储需求，也可以定期备份和存档整个 BAMArchive 数据库。 有关详细信息，请参阅 SQL Server 联机丛书中的“截断事务日志”。  
  
## <a name="see-also"></a>另请参阅  
 [定义时间窗口中，然后时间切片属性](../core/defining-the-time-window-and-time-slice-properties.md)   
 [管理 BAM 动态基础结构](../core/managing-the-bam-dynamic-infrastructure.md)