---
title: 解析不完整的活动实例 |Microsoft Docs
description: BAM 活动实例备份 BizTalk Server 中的 BAMPrimaryImport 数据库后保持活动状态
ms.custom: ''
ms.date: 01/17/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8adbcb66-58ad-42c5-ba16-7dc07572099e
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 83510267108754985e9121bf473c25215b9a08a1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334913"
---
# <a name="resolve-incomplete-bam-activity-instances---biztalk-server"></a>解析不完整的 BAM 活动实例的 BizTalk Server
BAM 将不完整的活动实例的数据存储在一个特殊*活动的实例*BAMPrimaryImport 数据库表中的。  
  
 如果某些实例记录是在 BAMPrimaryImport 数据库的上次备份之前启动但在完成备份后，这些实例记录将保留在活动实例表。 这是因为在还原 BAMPrimaryImport 数据库后，这些实例的完成记录都将丢失。  
  
 尽管活动的实例表中的记录不会妨碍 BAM 正常，但我们建议将这些记录标记为"已完成"，然后将它们移出活动实例表。  
  
## <a name="prerequisites"></a>先决条件  
以 BizTalk Server Administrators 组的成员身份登录。  
  
## <a name="create-a-list-of-incomplete-activityids"></a>创建不完整 Activityid 的列表 
  
1.  对 BAMPrimaryImport 数据库运行以下查询：  
  
    ```  
    Select ActivityID from bam_<ActivityName>_Active where IsComplete = 0  
    ```  
  
2.  如果从外部系统的数据指明查出的活动实例实际上已完成，运行以下查询来手动完成该实例：  
  
    ```  
    begin transaction
    exec bam_<ActivityName>_PrimaryImport @ActivityID=N'<ActivityID>', @IsStartNew=0, @IsComplete=1  
    commit transaction
    ```  
  
> [!NOTE]
>  可以按照相同的过程，通过替换来完成继续符活动`ActivityID`与`ContinuationID`。  
> 
>  如果主跟踪有任何活动的继续符跟踪，它将保持活动的继续符跟踪在完成之前。  

## <a name="remove-incomplete-instances"></a>删除未完成的实例
此外可以从使用自定义 SQL 脚本，在 BAMPrimaryImport 数据库删除不完整的活动实例。 请参阅[删除不完整的活动实例](how-to-remove-incomplete-activity-instances.md)有关的示例。

## <a name="see-also"></a>请参阅  
 [备份和还原 BAM](../core/backing-up-and-restoring-bam.md)
