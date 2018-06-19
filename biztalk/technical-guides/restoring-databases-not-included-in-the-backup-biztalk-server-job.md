---
title: 不还原数据库备份的 BizTalk Server 作业中包含 |Microsoft 文档
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
ms.openlocfilehash: 3277886207e04a30fec8bb61f29b5fe8c5ec3545
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302117"
---
# <a name="restoring-databases-not-included-in-the-backup-biztalk-server-job"></a><span data-ttu-id="f8aa1-102">还原数据库备份的 BizTalk Server 作业中不包括</span><span class="sxs-lookup"><span data-stu-id="f8aa1-102">Restoring Databases Not Included in the Backup BizTalk Server Job</span></span>
<span data-ttu-id="f8aa1-103">本部分介绍如何还原总体 BizTalk 解决方案的一部分，但不是会备份 BizTalk Server 作业身份备份的数据库。</span><span class="sxs-lookup"><span data-stu-id="f8aa1-103">This section describes how to restore databases that are part of the overall BizTalk solution but are not backed up by the Backup BizTalk Server job.</span></span> <span data-ttu-id="f8aa1-104">使用以下除外备份 BizTalk Server 作业，将备份作为 BizTalk 解决方案的一部分的所有数据库：</span><span class="sxs-lookup"><span data-stu-id="f8aa1-104">All databases that are part of a BizTalk solution will be backed up by using the Backup BizTalk Server job except for the following:</span></span>  
  
-   [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]<span data-ttu-id="f8aa1-105">Analysis Services 数据库</span><span class="sxs-lookup"><span data-stu-id="f8aa1-105"> Analysis Services databases</span></span>  
  
-   <span data-ttu-id="f8aa1-106">BAM 数据库时 BAM 启用和配置使用 BM.exe</span><span class="sxs-lookup"><span data-stu-id="f8aa1-106">BAM databases when BAM is enabled and configured using BM.exe</span></span>  
  
 <span data-ttu-id="f8aa1-107">本部分还描述如何在还原上面列出的数据库后更新数据库引用，并包含有关解决不完整 BAM 活动实例的信息。</span><span class="sxs-lookup"><span data-stu-id="f8aa1-107">This section also describes how to update database references after restoring the databases listed above and includes information about resolving incomplete BAM activity instances.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f8aa1-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="f8aa1-108">In This Section</span></span>  
  
-   [<span data-ttu-id="f8aa1-109">还原 Analysis Services 和支持的数据库</span><span class="sxs-lookup"><span data-stu-id="f8aa1-109">Restoring Analysis Services and Supporting Databases</span></span>](../technical-guides/restoring-analysis-services-and-supporting-databases.md)  
  
-   [<span data-ttu-id="f8aa1-110">更新数据库引用</span><span class="sxs-lookup"><span data-stu-id="f8aa1-110">Updating Database References</span></span>](../technical-guides/updating-database-references.md)  
  
-   [<span data-ttu-id="f8aa1-111">如何解决不完整 BAM 活动实例</span><span class="sxs-lookup"><span data-stu-id="f8aa1-111">How to Resolve Incomplete BAM Activity Instances</span></span>](../technical-guides/how-to-resolve-incomplete-bam-activity-instances.md)