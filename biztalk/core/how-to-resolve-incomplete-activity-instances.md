---
title: "如何解决未完成的活动实例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- instances, incomplete [BAM]
- restoring, BAM
- Primary Import database [BAM], incomplete instances
- restoring [BAM], Primary Import database
- Primary Import database [BAM], restoring
- BAM, restoring
ms.assetid: 8adbcb66-58ad-42c5-ba16-7dc07572099e
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81df9ee8b004a2dbd4a672eecb4f34894421a432
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-resolve-incomplete-activity-instances"></a>如何解析不完整的活动实例
BAM 将未完成的活动实例的数据存储在一个特殊*活动实例*BAMPrimaryImport 数据库表中的。  
  
 如果某些实例记录是在最近一次备份 BAMPrimaryImport 数据库之前启动的，但在完成备份之后才完成这些记录，则这些实例记录将保留在活动的实例表中。 这是因为在还原 BAMPrimaryImport 数据库后，这些实例的完成记录将会丢失。  
  
 尽管活动的实例表中的记录不会妨碍 BAM 正常运行，但仍建议您将这些记录标记为“已完成”，然后将它们移出活动的实例表。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 BizTalk Server Administrators 组成员的身份登录，才能执行此过程。  
  
### <a name="to-generate-a-list-of-incomplete-activityids-for-an-activity"></a>生成活动的不完整 ActivityID 列表  
  
1.  请对 BAMPrimaryImport 数据库运行以下查询：  
  
    ```  
    Select ActivityID from bam_<ActivityName>_Active where IsComplete = 0  
    ```  
  
2.  如果来自外部系统的数据指明查出的活动实例实际上已完成，请运行以下查询以手动完成该实例：  
  
    ```  
    exec bam_<ActivityName>_PrimaryImport @ActivityID=N'<ActivityID>', @IsStartNew=0, @IsComplete=1  
    ```  
  
> [!NOTE]
>  用 ContinuationID 代替 ActivityID，重复同样的过程可完成继续符活动。  
  
> [!NOTE]
>  只要主跟踪有任何活动的继续符跟踪，则该主跟踪将一直保持活动状态，直到继续符跟踪完成。  
  
## <a name="see-also"></a>另请参阅  
 [备份和还原 BAM](../core/backing-up-and-restoring-bam.md)