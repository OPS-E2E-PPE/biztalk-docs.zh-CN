---
title: 标记为已完成 BAM 中正在进行事务 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BAM, data recovery
- data recovery, BAM
- BAM, data loss
- data loss, BAM
ms.assetid: 8f734953-483a-481a-9ded-b48923859199
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 508001fcc1023acfd54b7d28bea7f246cb6a1a2d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262365"
---
# <a name="marking-in-progress-transactions-as-complete-in-bam"></a>在 BAM 中将正在进行的事务标记为“已完成”
业务活动监视 (BAM) 将未完成的跟踪实例的数据保存在特殊的活动实例表中。 如果某些实例记录是在最近一次备份之前启动的，但在完成备份之后才完成这些实例记录，则这些记录将保留在活动实例表中。 尽管这不会妨碍系统正常运转，但您可以手动将这些记录标记为“已完成”，以便可以将它们移出活动实例表。  
  
 要确定给定活动的未完成 ActivityID 列表，可对 BAM 主导入数据库执行以下查询：  
  
```  
Select ActivityID from bam_<ActivityName> where IsComplete = 0  
```  
  
 如果来自外部系统的数据指明查出的活动实例实际上已完成，您可以使用以下查询来手动完成该实例：  
  
```  
exec bam_<ActivityName>_PrimaryImport @ActivityID=N'<ActivityID>', @IsStartNew=0, @IsComplete=1  
```  
  
## <a name="see-also"></a>另请参阅  
 [解决数据丢失](../core/resolving-data-loss.md)