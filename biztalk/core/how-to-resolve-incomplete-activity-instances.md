---
title: 解决未完成的活动实例 |Microsoft 文档
description: BAM 活动实例备份 BizTalk Server 中的 BAMPrimaryImport 数据库之后保持活动状态
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
ms.openlocfilehash: 616ba096062da7ede8d78122e5a6faaca2befdc4
ms.sourcegitcommit: 20d33d8b74bf129a8d1a506ac4a1ad960184966d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/18/2018
ms.locfileid: "27873413"
---
# <a name="resolve-incomplete-bam-activity-instances---biztalk-server"></a>解决不完整的 BAM 活动实例的 BizTalk Server
BAM 将未完成的活动实例的数据存储在一个特殊 *活动实例* BAMPrimaryImport 数据库表中的。  
  
 如果某些实例记录是在最近一次备份 BAMPrimaryImport 数据库之前启动的，但在完成备份之后才完成这些记录，则这些实例记录将保留在活动的实例表中。 这是因为在还原 BAMPrimaryImport 数据库后，这些实例的完成记录将会丢失。  
  
 尽管活动的实例表中的记录不会妨碍 BAM 正常运行，但仍建议您将这些记录标记为“已完成”，然后将它们移出活动的实例表。  
  
## <a name="prerequisites"></a>必要條件  
BizTalk Server Administrators 组的成员登录。  
  
## <a name="create-a-list-of-incomplete-activityids"></a>创建不完整 ActivityIDs 的列表 
  
1.  请对 BAMPrimaryImport 数据库运行以下查询：  
  
    ```  
    Select ActivityID from bam_<ActivityName>_Active where IsComplete = 0  
    ```  
  
2.  如果来自外部系统的数据指明查出的活动实例实际上已完成，请运行以下查询以手动完成该实例：  
  
    ```  
    begin transaction
    exec bam_<ActivityName>_PrimaryImport @ActivityID=N'<ActivityID>', @IsStartNew=0, @IsComplete=1  
    commit transaction
    ```  
  
> [!NOTE]
>  您可以遵循相同的过程来通过替换来完成延续活动`ActivityID`与`ContinuationID`。  
> 
>  只要主跟踪有任何活动的继续符跟踪，则该主跟踪将一直保持活动状态，直到继续符跟踪完成。  

## <a name="remove-incomplete-instances"></a>删除不完整的实例
你还可以从使用自定义 SQL 脚本 BAMPrimaryImport 数据库中删除不完整的活动实例。 请参阅[删除不完整的活动实例](how-to-remove-incomplete-activity-instances.md)有关的示例。

## <a name="see-also"></a>另请参阅  
 [备份和还原 BAM](../core/backing-up-and-restoring-bam.md)
