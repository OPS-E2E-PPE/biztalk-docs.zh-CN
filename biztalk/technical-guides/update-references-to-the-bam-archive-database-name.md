---
title: 更新对 BAM 存档数据库名称的引用 |Microsoft 文档
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
ms.openlocfilehash: 16a04471e9f42744e4247f4202506839d2ade937
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302189"
---
# <a name="update-references-to-the-bam-archive-database-name"></a><span data-ttu-id="0c96e-102">更新对 BAM 存档数据库名称的引用</span><span class="sxs-lookup"><span data-stu-id="0c96e-102">Update References to the BAM Archive Database Name</span></span>
<span data-ttu-id="0c96e-103">如果备份 BAM 存档数据库时，出现系统或数据故障时你可以将该备份还原到另一台计算机，并且您可以重命名备份。</span><span class="sxs-lookup"><span data-stu-id="0c96e-103">If you backed up your BAM Archive databases, in the event of a system or data failure you can restore that backup to a different computer, and you can rename the backup.</span></span>  
  
 <span data-ttu-id="0c96e-104">若要还原的 BAM 存档数据库，执行中的步骤[如何还原数据库备份 BizTalk Server 作业](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)。</span><span class="sxs-lookup"><span data-stu-id="0c96e-104">To restore the BAM Archive databases, perform the steps in [How to Restore Databases in the Backup BizTalk Server Job](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md).</span></span> <span data-ttu-id="0c96e-105">此外，你必须使用新的服务器名称和数据库名称来更新 BAM SSIS 包。</span><span class="sxs-lookup"><span data-stu-id="0c96e-105">In addition, you must update the BAM SSIS packages with the new server name and database name.</span></span>  
  
## <a name="how-to-update-references-to-bam-archive-database"></a><span data-ttu-id="0c96e-106">如何更新对 BAM 存档数据库的引用</span><span class="sxs-lookup"><span data-stu-id="0c96e-106">How to Update References to BAM Archive Database</span></span>  
 <span data-ttu-id="0c96e-107">有关如何更新对 BAM 存档数据库引用的说明，请参阅[更新引用添加到新的 BAM 存档数据库](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_UpdateArch)。</span><span class="sxs-lookup"><span data-stu-id="0c96e-107">For instructions on how to update references to BAM Archive database, see [Updating References to the New BAM Archive Database](../technical-guides/how-to-move-the-bam-archive-database1.md#BKMK_UpdateArch).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c96e-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0c96e-108">See Also</span></span>  
 [<span data-ttu-id="0c96e-109">备份 BAM 分析和跟踪 Analysis Server 数据库</span><span class="sxs-lookup"><span data-stu-id="0c96e-109">Backing Up the BAM Analysis and Tracking Analysis Server Databases</span></span>](../technical-guides/backing-up-the-bam-analysis-and-tracking-analysis-server-databases.md)