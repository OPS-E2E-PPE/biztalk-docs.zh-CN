---
title: 更新对 BAM 存档数据库名称的引用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eed328e0-2826-4acb-952d-4a3a2844689e
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1479ef9776920e357e117351dc26966fec3f555
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400586"
---
# <a name="update-references-to-the-bam-archive-database-name"></a><span data-ttu-id="bfa20-102">更新对 BAM 存档数据库名称的引用</span><span class="sxs-lookup"><span data-stu-id="bfa20-102">Update References to the BAM Archive Database Name</span></span>
<span data-ttu-id="bfa20-103">如果备份了 BAM 存档数据库，在系统或数据发生故障时您可以将该备份还原到其他计算机，并可以重命名该备份。</span><span class="sxs-lookup"><span data-stu-id="bfa20-103">If you backed up your BAM Archive databases, in the event of a system or data failure you can restore that backup to a different computer, and you can rename the backup.</span></span>  
  
 <span data-ttu-id="bfa20-104">若要还原 BAM 存档数据库，请执行中的步骤[如何还原数据库备份 BizTalk Server 作业中](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)。</span><span class="sxs-lookup"><span data-stu-id="bfa20-104">To restore the BAM Archive databases, perform the steps in [How to Restore Databases in the Backup BizTalk Server Job](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md).</span></span> <span data-ttu-id="bfa20-105">此外，您必须使用新的服务器名称和数据库名称更新 BAM SSIS 包。</span><span class="sxs-lookup"><span data-stu-id="bfa20-105">In addition, you must update the BAM SSIS packages with the new server name and database name.</span></span>  
  
## <a name="how-to-update-references-to-bam-archive-database"></a><span data-ttu-id="bfa20-106">如何更新对 BAM 存档数据库的引用</span><span class="sxs-lookup"><span data-stu-id="bfa20-106">How to Update References to BAM Archive Database</span></span>  
 <span data-ttu-id="bfa20-107">有关如何更新对 BAM 存档数据库的引用的说明，请参阅[更新到新的 BAM 存档数据库的引用](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_UpdateArch)。</span><span class="sxs-lookup"><span data-stu-id="bfa20-107">For instructions on how to update references to BAM Archive database, see [Updating References to the New BAM Archive Database](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_UpdateArch).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfa20-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="bfa20-108">See Also</span></span>  
 [<span data-ttu-id="bfa20-109">备份 BAM 分析和跟踪 Analysis Server 数据库</span><span class="sxs-lookup"><span data-stu-id="bfa20-109">Backing Up the BAM Analysis and Tracking Analysis Server Databases</span></span>](../technical-guides/backing-up-the-bam-analysis-and-tracking-analysis-server-databases.md)