---
title: "更新到 BAM 主导入数据库的引用 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3da3b545-0d81-491b-bc37-0a980a7814b6
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ba37a32c82967e84b61bb46c58c62af9bf23b1b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="update-references-to-the-bam-primary-import-database"></a><span data-ttu-id="afbd7-102">更新到 BAM 主导入数据库的引用</span><span class="sxs-lookup"><span data-stu-id="afbd7-102">Update References to the BAM Primary Import Database</span></span>
<span data-ttu-id="afbd7-103">如果备份出现系统或数据故障时你 BAM 主导入数据库时，你可以将该备份还原到另一台计算机，并重命名备份。</span><span class="sxs-lookup"><span data-stu-id="afbd7-103">If you backed up your BAM Primary Import database in the event of a system or data failure, you can restore that backup to a different computer and rename the backup.</span></span>  
  
 <span data-ttu-id="afbd7-104">BAM 事件总线服务将事件数据从 MessageBox 数据库移到 BAM 主导入数据库。</span><span class="sxs-lookup"><span data-stu-id="afbd7-104">The BAM Event Bus service moves event data from the MessageBox database to the BAM Primary Import database.</span></span> <span data-ttu-id="afbd7-105">BAM 事件 Bus 服务包括故障容错逻辑，使它能够恢复并重新启动从意外的故障，而不会丢失任何数据。</span><span class="sxs-lookup"><span data-stu-id="afbd7-105">The BAM Event Bus service includes fault tolerance logic that enables it to recover and restart from an unexpected failure without losing any data.</span></span> <span data-ttu-id="afbd7-106">有关与 BAM 事件总线服务的详细信息，请参阅主题[管理 BAM 事件总线服务](http://go.microsoft.com/fwlink/?LinkID=154194)(http://go.microsoft.com/fwlink/?LinkID=154194)。</span><span class="sxs-lookup"><span data-stu-id="afbd7-106">For more information about the BAM Event Bus service, see the topic [Managing the BAM Event Bus Service](http://go.microsoft.com/fwlink/?LinkID=154194) (http://go.microsoft.com/fwlink/?LinkID=154194).</span></span>  
  
 <span data-ttu-id="afbd7-107">若要还原 BAM 主导入数据库，执行中的步骤[如何还原数据库备份 BizTalk Server 作业](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)。</span><span class="sxs-lookup"><span data-stu-id="afbd7-107">To restore the BAM Primary Import database, perform the steps in [How to Restore Databases in the Backup BizTalk Server Job](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md).</span></span> <span data-ttu-id="afbd7-108">此外，你必须使用新的服务器名称和数据库名称来更新 BAM SSIS 包。</span><span class="sxs-lookup"><span data-stu-id="afbd7-108">In addition, you must update the BAM SSIS packages with the new server name and database name.</span></span>  
  
## <a name="how-to-update-references-to-bam-primary-import-database"></a><span data-ttu-id="afbd7-109">如何更新对 BAM 主导入数据库的引用</span><span class="sxs-lookup"><span data-stu-id="afbd7-109">How to Update References to BAM Primary Import Database</span></span>  
 <span data-ttu-id="afbd7-110">有关如何更新 BAM 主导入数据库，对引用的说明[更新到新的 BAM 主导入数据库的引用](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_BAMPIRef)。</span><span class="sxs-lookup"><span data-stu-id="afbd7-110">For instructions on how to update references to BAM Primary Import database, [Updating References to the New BAM Primary Import Database](../technical-guides/how-to-move-the-bam-primary-import-database2.md#BKMK_BAMPIRef).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afbd7-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="afbd7-111">See Also</span></span>  
 [<span data-ttu-id="afbd7-112">备份 BAM 分析和跟踪 Analysis Server 数据库</span><span class="sxs-lookup"><span data-stu-id="afbd7-112">Backing Up the BAM Analysis and Tracking Analysis Server Databases</span></span>](../technical-guides/backing-up-the-bam-analysis-and-tracking-analysis-server-databases.md)