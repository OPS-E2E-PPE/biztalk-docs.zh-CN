---
title: "还原 Analysis Services 和支持的数据库 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 490ad0fb-7805-4ebc-9bc5-117d52d7c3a8
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da16bde7b69071b71b794c4c46407feab3ef4512
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="restoring-analysis-services-and-supporting-databases"></a><span data-ttu-id="7b38a-102">还原 Analysis Services 和支持的数据库</span><span class="sxs-lookup"><span data-stu-id="7b38a-102">Restoring Analysis Services and Supporting Databases</span></span>
<span data-ttu-id="7b38a-103">有两个[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，必须在灾难恢复方案中还原的 Analysis Services 数据库：</span><span class="sxs-lookup"><span data-stu-id="7b38a-103">There are two [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Analysis Services databases that must be restored in a disaster recovery scenario:</span></span>  
  
-   <span data-ttu-id="7b38a-104">BAM 分析 (BAMAnalysis)</span><span class="sxs-lookup"><span data-stu-id="7b38a-104">BAM Analysis (BAMAnalysis)</span></span>  
  
-   <span data-ttu-id="7b38a-105">跟踪 Analysis Server (BizTalkAnalysisdb)</span><span class="sxs-lookup"><span data-stu-id="7b38a-105">Tracking Analysis Server (BizTalkAnalysisdb)</span></span>  
  
 <span data-ttu-id="7b38a-106">BAM[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库可能会进行备份的备份 BizTalk Server 作业一部分如果 BAM 已启用但尚未配置。</span><span class="sxs-lookup"><span data-stu-id="7b38a-106">The BAM [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] databases may be backed up as part of the Backup BizTalk Server job if BAM is enabled but not configured.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7b38a-107">BAM 主导入始终备份数据库的备份 BizTalk Server 作业一部分因为它参与 DTC 事务。</span><span class="sxs-lookup"><span data-stu-id="7b38a-107">The BAM Primary Import database is always backed up as part of the Backup BizTalk Server job because it participates in DTC transactions.</span></span>  
  
 <span data-ttu-id="7b38a-108">以下的 BAM 数据库将 BizTalk Server 中备份作业的一部分，如果 BAM 已启用但尚未配置：</span><span class="sxs-lookup"><span data-stu-id="7b38a-108">The following BAM databases will be part of the Backup BizTalk Server job if BAM is enabled but not configured:</span></span>  
  
-   <span data-ttu-id="7b38a-109">BAMStarSchema</span><span class="sxs-lookup"><span data-stu-id="7b38a-109">BAMStarSchema</span></span>  
  
-   <span data-ttu-id="7b38a-110">BAMArchive</span><span class="sxs-lookup"><span data-stu-id="7b38a-110">BAMArchive</span></span>  
  
 <span data-ttu-id="7b38a-111">按照中的步骤[如何还原数据库备份 BizTalk Server 作业](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md)还原这些数据库。</span><span class="sxs-lookup"><span data-stu-id="7b38a-111">Follow the steps in [How to Restore Databases in the Backup BizTalk Server Job](../technical-guides/how-to-restore-databases-in-the-backup-biztalk-server-job.md) to restore these databases.</span></span>  
  
 <span data-ttu-id="7b38a-112">**否则为**</span><span class="sxs-lookup"><span data-stu-id="7b38a-112">**Otherwise,**</span></span>  
 <span data-ttu-id="7b38a-113">**如果 BAM 已启用，而且还配置使用 BM.exe，正确的一套 BAM 数据库必须为一组一起还原。**</span><span class="sxs-lookup"><span data-stu-id="7b38a-113">**if BAM is enabled and is also configured with BM.exe, the correct set of BAM databases must be restored together as a set.**</span></span> <span data-ttu-id="7b38a-114">若要确保恢复一组完整的已存档的数据，BAM 存档备份数据库分区复制到 BAM 存档之后，但之前从 BAM 主导入数据库中删除分区。</span><span class="sxs-lookup"><span data-stu-id="7b38a-114">To ensure that a complete set of archived data is recovered, the BAM Archive database is backed up after the partition is copied into the BAM Archive, but before the partition is deleted from the BAM Primary Import database.</span></span> <span data-ttu-id="7b38a-115">通过修改每个活动数据维护 SSIS 包的方法是插入 BAM 存档数据库备份，最后一个步骤"结束存档。"之前的步骤执行此操作</span><span class="sxs-lookup"><span data-stu-id="7b38a-115">This is performed by modifying the data maintenance SSIS package for each activity by inserting a step to back up the BAM Archive database before the last step "End Archiving."</span></span>  
  
 <span data-ttu-id="7b38a-116">BAM 数据库还原过程是： 如果 x 的最后备份日期还原 BAM 主导入数据库，则将对应的 BAM 存档和 BAM 星型架构的数据库的副本还原到数据维护 SSIS 包时的最新日期在 x 的日期之前运行。</span><span class="sxs-lookup"><span data-stu-id="7b38a-116">The restore procedure for the BAM databases is: If the BAM Primary Import database is restored with the last backup date of x, restore the copies of the BAM Archive and BAM Star Schema databases that correspond to the latest date when the data maintenance SSIS package was run before the date of x.</span></span>  
  
 <span data-ttu-id="7b38a-117">标识正确的一套 BAM 数据库之后，将还原[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Analysis Services 数据库中所述使用标准过程[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]有关还原联机丛书[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]数据库和[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]Analysis Services 数据库。</span><span class="sxs-lookup"><span data-stu-id="7b38a-117">After the correct set of BAM databases is identified, restore the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Analysis Services databases using standard procedures as documented in the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Books Online for restoring [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] databases and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Analysis Services databases.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b38a-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7b38a-118">See Also</span></span>  
 [<span data-ttu-id="7b38a-119">备份 BAM 分析和跟踪 Analysis Server 数据库</span><span class="sxs-lookup"><span data-stu-id="7b38a-119">Backing Up the BAM Analysis and Tracking Analysis Server Databases</span></span>](../technical-guides/backing-up-the-bam-analysis-and-tracking-analysis-server-databases.md)