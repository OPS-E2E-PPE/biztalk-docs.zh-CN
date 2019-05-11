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
# <a name="resolve-incomplete-bam-activity-instances---biztalk-server"></a><span data-ttu-id="f1516-103">解析不完整的 BAM 活动实例的 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="f1516-103">Resolve incomplete BAM activity instances - BizTalk Server</span></span>
<span data-ttu-id="f1516-104">BAM 将不完整的活动实例的数据存储在一个特殊*活动的实例*BAMPrimaryImport 数据库表中的。</span><span class="sxs-lookup"><span data-stu-id="f1516-104">BAM stores data for incomplete activity instances in a special *active instance* table in the BAMPrimaryImport database.</span></span>  
  
 <span data-ttu-id="f1516-105">如果某些实例记录是在 BAMPrimaryImport 数据库的上次备份之前启动但在完成备份后，这些实例记录将保留在活动实例表。</span><span class="sxs-lookup"><span data-stu-id="f1516-105">If some instance records were started before the last backup of the BAMPrimaryImport database but completed after the backup, those instance records remain in an active instance table.</span></span> <span data-ttu-id="f1516-106">这是因为在还原 BAMPrimaryImport 数据库后，这些实例的完成记录都将丢失。</span><span class="sxs-lookup"><span data-stu-id="f1516-106">This is because after the BAMPrimaryImport database is restored, the completion records for these instances are lost.</span></span>  
  
 <span data-ttu-id="f1516-107">尽管活动的实例表中的记录不会妨碍 BAM 正常，但我们建议将这些记录标记为"已完成"，然后将它们移出活动实例表。</span><span class="sxs-lookup"><span data-stu-id="f1516-107">Although the records in the active instance table do not prevent BAM from functioning properly, we recommend that you mark these records as "completed," and then move them out of the active instance table.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f1516-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="f1516-108">Prerequisites</span></span>  
<span data-ttu-id="f1516-109">以 BizTalk Server Administrators 组的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="f1516-109">Sign in as a member of the BizTalk Server Administrators group.</span></span>  
  
## <a name="create-a-list-of-incomplete-activityids"></a><span data-ttu-id="f1516-110">创建不完整 Activityid 的列表</span><span class="sxs-lookup"><span data-stu-id="f1516-110">Create a list of incomplete ActivityIDs</span></span> 
  
1.  <span data-ttu-id="f1516-111">对 BAMPrimaryImport 数据库运行以下查询：</span><span class="sxs-lookup"><span data-stu-id="f1516-111">Run the following query against the BAMPrimaryImport database:</span></span>  
  
    ```  
    Select ActivityID from bam_<ActivityName>_Active where IsComplete = 0  
    ```  
  
2.  <span data-ttu-id="f1516-112">如果从外部系统的数据指明查出的活动实例实际上已完成，运行以下查询来手动完成该实例：</span><span class="sxs-lookup"><span data-stu-id="f1516-112">If data from external systems indicates that the activity instance is in fact completed, run the following query to manually complete the instance:</span></span>  
  
    ```  
    begin transaction
    exec bam_<ActivityName>_PrimaryImport @ActivityID=N'<ActivityID>', @IsStartNew=0, @IsComplete=1  
    commit transaction
    ```  
  
> [!NOTE]
>  <span data-ttu-id="f1516-113">可以按照相同的过程，通过替换来完成继续符活动`ActivityID`与`ContinuationID`。</span><span class="sxs-lookup"><span data-stu-id="f1516-113">You can follow the same process to complete a continuation activity by replacing `ActivityID` with `ContinuationID`.</span></span>  
> 
>  <span data-ttu-id="f1516-114">如果主跟踪有任何活动的继续符跟踪，它将保持活动的继续符跟踪在完成之前。</span><span class="sxs-lookup"><span data-stu-id="f1516-114">If the main trace has any active continuation traces, it remains active until the continuation traces are completed.</span></span>  

## <a name="remove-incomplete-instances"></a><span data-ttu-id="f1516-115">删除未完成的实例</span><span class="sxs-lookup"><span data-stu-id="f1516-115">Remove incomplete instances</span></span>
<span data-ttu-id="f1516-116">此外可以从使用自定义 SQL 脚本，在 BAMPrimaryImport 数据库删除不完整的活动实例。</span><span class="sxs-lookup"><span data-stu-id="f1516-116">You can also remove incomplete activity instances from the BAMPrimaryImport database using a custom SQL script.</span></span> <span data-ttu-id="f1516-117">请参阅[删除不完整的活动实例](how-to-remove-incomplete-activity-instances.md)有关的示例。</span><span class="sxs-lookup"><span data-stu-id="f1516-117">See [Remove incomplete activity instances](how-to-remove-incomplete-activity-instances.md) for a sample.</span></span>

## <a name="see-also"></a><span data-ttu-id="f1516-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="f1516-118">See Also</span></span>  
 [<span data-ttu-id="f1516-119">备份和还原 BAM</span><span class="sxs-lookup"><span data-stu-id="f1516-119">Backing Up and Restoring BAM</span></span>](../core/backing-up-and-restoring-bam.md)
