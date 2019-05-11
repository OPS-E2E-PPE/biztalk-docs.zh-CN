---
title: 还原数据库不包含在备份 BizTalk Server 作业 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c7141980-d4a6-4409-be9b-c94a7f733376
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e4555b9a3f635d733d698109614c1ed673125f0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291253"
---
# <a name="restoring-databases-not-included-in-the-backup-biztalk-server-job"></a><span data-ttu-id="35cdc-102">还原数据库不包含在备份 BizTalk Server 作业</span><span class="sxs-lookup"><span data-stu-id="35cdc-102">Restoring Databases Not Included in the Backup BizTalk Server Job</span></span>
<span data-ttu-id="35cdc-103">本部分介绍如何还原作为整体的 BizTalk 解决方案的一部分，但不是由备份 BizTalk Server 作业备份的数据库。</span><span class="sxs-lookup"><span data-stu-id="35cdc-103">This section describes how to restore databases that are part of the overall BizTalk solution but are not backed up by the Backup BizTalk Server job.</span></span> <span data-ttu-id="35cdc-104">将备份作为 BizTalk 解决方案的一部分的所有数据库使用备份 BizTalk Server 作业，以下除外：</span><span class="sxs-lookup"><span data-stu-id="35cdc-104">All databases that are part of a BizTalk solution will be backed up by using the Backup BizTalk Server job except for the following:</span></span>  
  
- [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] <span data-ttu-id="35cdc-105">Analysis Services 数据库</span><span class="sxs-lookup"><span data-stu-id="35cdc-105">Analysis Services databases</span></span>  
  
- <span data-ttu-id="35cdc-106">如果启用了 BAM，并且使用 BM.exe 配置 BAM 数据库</span><span class="sxs-lookup"><span data-stu-id="35cdc-106">BAM databases when BAM is enabled and configured using BM.exe</span></span>  
  
  <span data-ttu-id="35cdc-107">本部分还介绍如何还原上面列出的数据库后更新数据库的引用，并且包括有关解决不完整的 BAM 活动实例的信息。</span><span class="sxs-lookup"><span data-stu-id="35cdc-107">This section also describes how to update database references after restoring the databases listed above and includes information about resolving incomplete BAM activity instances.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="35cdc-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="35cdc-108">In This Section</span></span>  
  
-   [<span data-ttu-id="35cdc-109">还原 Analysis Services 和支持数据库</span><span class="sxs-lookup"><span data-stu-id="35cdc-109">Restoring Analysis Services and Supporting Databases</span></span>](../technical-guides/restoring-analysis-services-and-supporting-databases.md)  
  
-   [<span data-ttu-id="35cdc-110">更新数据库引用</span><span class="sxs-lookup"><span data-stu-id="35cdc-110">Updating Database References</span></span>](../technical-guides/updating-database-references.md)  
  
-   [<span data-ttu-id="35cdc-111">如何解析不完整的 BAM 活动实例</span><span class="sxs-lookup"><span data-stu-id="35cdc-111">How to Resolve Incomplete BAM Activity Instances</span></span>](../technical-guides/how-to-resolve-incomplete-bam-activity-instances.md)