---
title: 正在将事务标记为完成在 BAM |Microsoft Docs
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
ms.openlocfilehash: e975893867906d9f9570741e780abfcf10625f30
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65531100"
---
# <a name="marking-in-progress-transactions-as-complete-in-bam"></a><span data-ttu-id="bfa4d-102">正在将事务标记为完成在 BAM 中</span><span class="sxs-lookup"><span data-stu-id="bfa4d-102">Marking In-Progress Transactions as Complete in BAM</span></span>
<span data-ttu-id="bfa4d-103">业务活动监视 (BAM) 将未完成的跟踪实例的数据保存在特殊的活动实例表中。</span><span class="sxs-lookup"><span data-stu-id="bfa4d-103">Business Activity Monitoring (BAM) keeps data for incomplete trace instances in a special active instance table.</span></span> <span data-ttu-id="bfa4d-104">如果某些实例记录是在最近一次备份之前启动的，但在完成备份之后才完成这些实例记录，则这些记录将保留在活动实例表中。</span><span class="sxs-lookup"><span data-stu-id="bfa4d-104">If some instance records were started before the last backup but completed after the backup, those records will remain in the active instance table.</span></span> <span data-ttu-id="bfa4d-105">尽管这不会妨碍系统正常运转，但您可以手动将这些记录标记为“已完成”，以便可以将它们移出活动实例表。</span><span class="sxs-lookup"><span data-stu-id="bfa4d-105">Although this does not prevent the system from functioning, you can manually mark these records as completed so that they can be moved out of the active instance table.</span></span>  
  
 <span data-ttu-id="bfa4d-106">要确定给定活动的未完成 ActivityID 列表，可对 BAM 主导入数据库执行以下查询：</span><span class="sxs-lookup"><span data-stu-id="bfa4d-106">A list of incomplete ActivityIDs for a given activity can be determined by issuing the following query against the BAM Primary Import database:</span></span>  
  
```  
Select ActivityID from bam_<ActivityName> where IsComplete = 0  
```  
  
 <span data-ttu-id="bfa4d-107">如果来自外部系统的数据指明查出的活动实例实际上已完成，您可以使用以下查询来手动完成该实例：</span><span class="sxs-lookup"><span data-stu-id="bfa4d-107">If data from external systems indicates that the activity instance is complete, you can use the following query to manually complete the instance:</span></span>  
  
```  
exec bam_<ActivityName>_PrimaryImport @ActivityID=N'<ActivityID>', @IsStartNew=0, @IsComplete=1  
```  
  
## <a name="see-also"></a><span data-ttu-id="bfa4d-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="bfa4d-108">See Also</span></span>  
 [<span data-ttu-id="bfa4d-109">解决数据丢失问题</span><span class="sxs-lookup"><span data-stu-id="bfa4d-109">Resolving Data Loss</span></span>](../core/resolving-data-loss.md)