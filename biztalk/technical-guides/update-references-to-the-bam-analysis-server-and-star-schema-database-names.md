---
title: 更新到 BAM Analysis Server 和星型架构数据库名称的引用 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 319caa26-1292-4453-a316-efca4fbffdb6
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 184ab156770b0a62208a8e24c7870afa43d3a128
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302229"
---
# <a name="update-references-to-the-bam-analysis-server-and-star-schema-database-names"></a><span data-ttu-id="32466-102">更新引用到 BAM Analysis Server 和星型架构数据库名称</span><span class="sxs-lookup"><span data-stu-id="32466-102">Update References to the BAM Analysis Server and Star Schema Database Names</span></span>
<span data-ttu-id="32466-103">如果备份了 BAM 分析数据库，则在系统或数据发生故障时，可以将该备份还原到其他计算机上，然后重命名该备份。</span><span class="sxs-lookup"><span data-stu-id="32466-103">If you backed up your BAM Analysis database, in the event of a system or data failure you can restore that backup to a different computer and you can rename the backup.</span></span>  
  
 <span data-ttu-id="32466-104">若要还原的 BAM 分析和星型架构的数据库，执行中的步骤[如何还原数据库备份 BizTalk Server 作业](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)。</span><span class="sxs-lookup"><span data-stu-id="32466-104">To restore the BAM Analysis and Star Schema databases, perform the steps in [How to Restore Databases in the Backup BizTalk Server Job](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md).</span></span> <span data-ttu-id="32466-105">此外，必须更新 BAM [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Integration Services (SSIS) 包的新服务器名称和数据库名称。</span><span class="sxs-lookup"><span data-stu-id="32466-105">In addition, you must update the BAM [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Integration Services (SSIS) packages with the new server name and database name.</span></span>  
  
## <a name="how-to-update-references-to-bam-analysis-server-and-star-schema-database-names"></a><span data-ttu-id="32466-106">如何更新对 BAM Analysis Server 和星型架构数据库名称的引用</span><span class="sxs-lookup"><span data-stu-id="32466-106">How to Update References to BAM Analysis Server and Star Schema Database Names</span></span>  
 <span data-ttu-id="32466-107">有关如何更新对 BAM Analysis server 数据库的引用的说明，请参阅[更新到新的 BAM 分析数据库的引用](../technical-guides/how-to-move-the-bam-analysis-database1.md#BKMK_AnalyUpdate)。</span><span class="sxs-lookup"><span data-stu-id="32466-107">For instructions on how to update references to BAM Analysis server databases, see [Updating References to the New BAM Analysis Database](../technical-guides/how-to-move-the-bam-analysis-database1.md#BKMK_AnalyUpdate).</span></span> <span data-ttu-id="32466-108">有关如何更新对 BAM 星型架构数据库的引用的说明，请参阅[更新引用添加到新的 BAM 星型架构数据库](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarUpdate)。</span><span class="sxs-lookup"><span data-stu-id="32466-108">For instructions on how to update references to the BAM Star Schema databases, see [Updating References to the New BAM Star Schema Database](../technical-guides/how-to-move-the-bam-star-schema-database2.md#BKMK_StarUpdate).</span></span>