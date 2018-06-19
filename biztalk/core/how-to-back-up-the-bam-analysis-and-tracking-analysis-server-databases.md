---
title: 如何备份 BAM 分析和跟踪 Analysis Server 数据库 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- backing up, DTS packages
- backing up [BAM], Tracking Analysis Server database
- backing up [BAM], OLAP cubes
- backing up [BAM], DTS packages
- purging, OLAP cubes
- Analysis database [BAM], backing up
- scheduling, BAM backups
- backing up [BAM], Analysis database
- OLAP cubes, purging
- backing up, BAM
- backing up [BAM], database order
- DTS packages, backing up
- backing up [BAM], Star Schema database
- backing up [BAM], scheduling
- Tracking Analysis Server database [BAM], backing up
- Star Schema database [BAM], backing up
ms.assetid: d39e3491-ab54-44f2-990a-7b8ee86f0501
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: effa2f5787f04493713ea6972562fe768081f4bc
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970267"
---
# <a name="how-to-back-up-the-bam-analysis-and-tracking-analysis-server-databases"></a><span data-ttu-id="0c57e-102">如何备份 BAM 分析数据库和跟踪分析服务器数据库</span><span class="sxs-lookup"><span data-stu-id="0c57e-102">How to Back Up the BAM Analysis and Tracking Analysis Server Databases</span></span>
<span data-ttu-id="0c57e-103">业务活动监视 (BAM) 分析数据库和跟踪分析服务器数据库存储 SQL Server Analysis Services 多维数据集中的内容。</span><span class="sxs-lookup"><span data-stu-id="0c57e-103">The Business Activity Monitoring (BAM) Analysis database and the Tracking Analysis Server database store content in SQL Server Analysis Services cubes.</span></span> <span data-ttu-id="0c57e-104">备份 BizTalk Server 作业不备份这些数据库。</span><span class="sxs-lookup"><span data-stu-id="0c57e-104">The Backup BizTalk Server job does not back up these databases.</span></span> <span data-ttu-id="0c57e-105">若要备份这些数据库，必须使用 SQL Server 分析管理器。</span><span class="sxs-lookup"><span data-stu-id="0c57e-105">Instead, to backup these databases, you must use SQL Server Analysis Manager.</span></span>  
  
 <span data-ttu-id="0c57e-106">备份完这些数据库后，您可能希望清除 OLAP 多维数据集。</span><span class="sxs-lookup"><span data-stu-id="0c57e-106">After you back up these databases, you may want to purge the OLAP cubes.</span></span> <span data-ttu-id="0c57e-107">清除 OLAP 多维数据集时，还必须执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="0c57e-107">When you purge the OLAP cubes, you must also perform the following steps:</span></span>  
  
1.  <span data-ttu-id="0c57e-108">在清除 OLAP 多维数据集之前，在 BAMStarSchema 数据库中截断要清除的多维数据集的事实表。</span><span class="sxs-lookup"><span data-stu-id="0c57e-108">Before you purge the OLAP cubes, in the BAMStarSchema database, truncate the fact table(s) for the cube you want to purge.</span></span> <span data-ttu-id="0c57e-109">表命名约定是将"bam_*\<多维数据集名称\>*_Facts"。</span><span class="sxs-lookup"><span data-stu-id="0c57e-109">The table naming convention is "bam_*\<CubeName\>*_Facts".</span></span>  
  
2.  <span data-ttu-id="0c57e-110">清除完 OLAP 多维数据集后，必须彻底处理活动的、已完成的和虚拟的多维数据集。</span><span class="sxs-lookup"><span data-stu-id="0c57e-110">After you purge the OLAP cubes, you must fully process active, completed, and virtual cubes.</span></span>  
  
 <span data-ttu-id="0c57e-111">有关备份分析数据库的说明，请参阅 SQL Server 联机丛书中的“存档 Analysis Services 数据库”。</span><span class="sxs-lookup"><span data-stu-id="0c57e-111">For instructions about backing up the analysis databases, see "Archiving an Analysis Services Database" in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="0c57e-112">**计划 BAM 数据库的备份**</span><span class="sxs-lookup"><span data-stu-id="0c57e-112">**Scheduling backups for the BAM databases**</span></span>  
  
 <span data-ttu-id="0c57e-113">如果要使用 BAM，请验证备份包在按计划运行时 BAM 多维数据集处理和数据维护数据转换服务 (DTS) 包都不会运行。</span><span class="sxs-lookup"><span data-stu-id="0c57e-113">If you are using BAM, verify that neither the BAM cube process nor data maintenance Data Transformation Services (DTS) packages are running when the backup package is scheduled to run.</span></span>  
  
 <span data-ttu-id="0c57e-114">若要确保所有 BAM 数据库的架构一致，请在每次部署或取消部署 BAM 活动时都备份 BAM 数据库和 DTS 包。</span><span class="sxs-lookup"><span data-stu-id="0c57e-114">To ensure consistent schema across all BAM databases, back up the BAM databases and DTS packages each time you deploy or undeploy a BAM activity.</span></span>  
  
 <span data-ttu-id="0c57e-115">每次部署或取消部署 BAM 视图时都备份 BAM 分析数据库和 BAMStarSchema 数据库。</span><span class="sxs-lookup"><span data-stu-id="0c57e-115">Back up the BAM Analysis database and BAMStarSchema database each time you deploy or undeploy a BAM view.</span></span>  
  
 <span data-ttu-id="0c57e-116">按以下顺序备份 BAM 数据库：</span><span class="sxs-lookup"><span data-stu-id="0c57e-116">Back up the BAM databases in the following order:</span></span>  
  
1.  <span data-ttu-id="0c57e-117">运行备份 BizTalk Server 作业备份 BAMPrimaryImport 数据库和其他 BizTalk Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="0c57e-117">Run the Backup BizTalk Server job to back up the BAMPrimaryImport database and your other BizTalk Server databases.</span></span>  
  
2.  <span data-ttu-id="0c57e-118">运行所有活动的 BAM 数据维护 DTS 包。</span><span class="sxs-lookup"><span data-stu-id="0c57e-118">Run the BAM data maintenance DTS package for all activities.</span></span>  
  
     <span data-ttu-id="0c57e-119">将这些步骤并入 DTS 包，然后安排该 DTS 包定期运行。</span><span class="sxs-lookup"><span data-stu-id="0c57e-119">Incorporate these steps into a DTS package, and schedule the package to run on a regular basis.</span></span> <span data-ttu-id="0c57e-120">为了确保数据完整性，请确保此备份包在按计划运行时没有其他 BAM 多维数据集或数据维护 DTS 包在运行。</span><span class="sxs-lookup"><span data-stu-id="0c57e-120">To ensure data integrity, make sure no other BAM cubing or data maintenance DTS packages run when this backup package is scheduled to run.</span></span>  
  
     <span data-ttu-id="0c57e-121">若要确保 BAMArchive 数据库发生故障时能够完整地恢复存档数据，请在将分区复制到 BAMArchive 数据库之后，且在从 BAMPrimaryImport 数据库删除分区之前备份 BAMArchive 数据库。</span><span class="sxs-lookup"><span data-stu-id="0c57e-121">To ensure that you can recover a complete set of archived data if the BAMArchive database fails, back up the BAMArchive database after you copy the partition into the BAMArchive database, but before you delete the partition from the BAMPrimaryImport database.</span></span> <span data-ttu-id="0c57e-122">为此，请修改每个活动的数据维护 DTS 包，在 DTS 包的最后一步“结束存档”之前插入备份 BAMArchive 数据库这一步。</span><span class="sxs-lookup"><span data-stu-id="0c57e-122">To do this, modify the data maintenance DTS package for each activity to insert a step to back up the BAMArchive database before the last step in the DTS package, "End Archiving."</span></span>  
  
3.  <span data-ttu-id="0c57e-123">备份 BAMAnalysis 数据库，然后备份 BAMStarSchema 数据库。</span><span class="sxs-lookup"><span data-stu-id="0c57e-123">Back up the BAMAnalysis database, and then the BAMStarSchema database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c57e-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0c57e-124">See Also</span></span>  
 [<span data-ttu-id="0c57e-125">备份和还原 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="0c57e-125">Backing Up and Restoring the BizTalk Server Databases</span></span>](../core/backing-up-and-restoring-the-biztalk-server-databases.md)