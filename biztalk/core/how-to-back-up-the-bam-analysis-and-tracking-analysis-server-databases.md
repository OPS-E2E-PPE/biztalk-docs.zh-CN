---
title: 如何备份 BAM 分析和跟踪分析服务器数据库 |Microsoft Docs
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
ms.openlocfilehash: f2fdd707375404f26f9310c6c2d38a6f2dfcb4ae
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387119"
---
# <a name="how-to-back-up-the-bam-analysis-and-tracking-analysis-server-databases"></a><span data-ttu-id="2b00c-102">如何备份 BAM 分析数据库和跟踪分析服务器数据库</span><span class="sxs-lookup"><span data-stu-id="2b00c-102">How to Back Up the BAM Analysis and Tracking Analysis Server Databases</span></span>
<span data-ttu-id="2b00c-103">业务活动监视 (BAM) 分析数据库和跟踪分析服务器数据库存储在 SQL Server Analysis Services 多维数据集中的内容。</span><span class="sxs-lookup"><span data-stu-id="2b00c-103">The Business Activity Monitoring (BAM) Analysis database and the Tracking Analysis Server database store content in SQL Server Analysis Services cubes.</span></span> <span data-ttu-id="2b00c-104">备份 BizTalk Server 作业不会备份这些数据库。</span><span class="sxs-lookup"><span data-stu-id="2b00c-104">The Backup BizTalk Server job does not back up these databases.</span></span> <span data-ttu-id="2b00c-105">相反，若要备份这些数据库，必须使用 SQL Server 分析管理器。</span><span class="sxs-lookup"><span data-stu-id="2b00c-105">Instead, to backup these databases, you must use SQL Server Analysis Manager.</span></span>  
  
 <span data-ttu-id="2b00c-106">备份这些数据库后，你可能想要清除 OLAP 多维数据集。</span><span class="sxs-lookup"><span data-stu-id="2b00c-106">After you back up these databases, you may want to purge the OLAP cubes.</span></span> <span data-ttu-id="2b00c-107">当清除 OLAP 多维数据集时，您还必须执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="2b00c-107">When you purge the OLAP cubes, you must also perform the following steps:</span></span>  
  
1. <span data-ttu-id="2b00c-108">在清除 OLAP 多维数据集之前, BAMStarSchema 数据库中截断要清除的多维数据集的事实表。</span><span class="sxs-lookup"><span data-stu-id="2b00c-108">Before you purge the OLAP cubes, in the BAMStarSchema database, truncate the fact table(s) for the cube you want to purge.</span></span> <span data-ttu-id="2b00c-109">表命名约定为"bam_*\<多维数据集名称\>*_Facts"。</span><span class="sxs-lookup"><span data-stu-id="2b00c-109">The table naming convention is "bam_*\<CubeName\>*_Facts".</span></span>  
  
2. <span data-ttu-id="2b00c-110">清除 OLAP 多维数据集后，必须完全处理活动的、 已完成的、 和虚拟多维数据集。</span><span class="sxs-lookup"><span data-stu-id="2b00c-110">After you purge the OLAP cubes, you must fully process active, completed, and virtual cubes.</span></span>  
  
   <span data-ttu-id="2b00c-111">有关备份分析数据库的说明，请参阅"存档 Analysis Services 数据库"SQL Server 联机丛书中。</span><span class="sxs-lookup"><span data-stu-id="2b00c-111">For instructions about backing up the analysis databases, see "Archiving an Analysis Services Database" in SQL Server Books Online.</span></span>  
  
   <span data-ttu-id="2b00c-112">**计划备份 BAM 数据库**</span><span class="sxs-lookup"><span data-stu-id="2b00c-112">**Scheduling backups for the BAM databases**</span></span>  
  
   <span data-ttu-id="2b00c-113">如果在使用 BAM，验证备份包在按计划运行时运行两 BAM 多维数据集处理和数据维护数据转换服务 (DTS) 包。</span><span class="sxs-lookup"><span data-stu-id="2b00c-113">If you are using BAM, verify that neither the BAM cube process nor data maintenance Data Transformation Services (DTS) packages are running when the backup package is scheduled to run.</span></span>  
  
   <span data-ttu-id="2b00c-114">若要确保所有 BAM 数据库一致的架构，备份 BAM 数据库和 DTS 包每次部署或取消部署 BAM 活动。</span><span class="sxs-lookup"><span data-stu-id="2b00c-114">To ensure consistent schema across all BAM databases, back up the BAM databases and DTS packages each time you deploy or undeploy a BAM activity.</span></span>  
  
   <span data-ttu-id="2b00c-115">备份 BAM 分析数据库和 BAMStarSchema 数据库每次部署或取消部署 BAM 视图。</span><span class="sxs-lookup"><span data-stu-id="2b00c-115">Back up the BAM Analysis database and BAMStarSchema database each time you deploy or undeploy a BAM view.</span></span>  
  
   <span data-ttu-id="2b00c-116">备份 BAM 数据库按以下顺序：</span><span class="sxs-lookup"><span data-stu-id="2b00c-116">Back up the BAM databases in the following order:</span></span>  
  
3. <span data-ttu-id="2b00c-117">运行备份 BizTalk Server 作业备份 BAMPrimaryImport 数据库和其他 BizTalk Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="2b00c-117">Run the Backup BizTalk Server job to back up the BAMPrimaryImport database and your other BizTalk Server databases.</span></span>  
  
4. <span data-ttu-id="2b00c-118">运行的所有活动的 BAM 数据维护 DTS 包。</span><span class="sxs-lookup"><span data-stu-id="2b00c-118">Run the BAM data maintenance DTS package for all activities.</span></span>  
  
    <span data-ttu-id="2b00c-119">这些步骤并入 DTS 包，并计划定期运行的包。</span><span class="sxs-lookup"><span data-stu-id="2b00c-119">Incorporate these steps into a DTS package, and schedule the package to run on a regular basis.</span></span> <span data-ttu-id="2b00c-120">若要确保数据完整性，请确保没有其他 BAM 多维或数据维护 DTS 包运行时此备份包在按计划运行。</span><span class="sxs-lookup"><span data-stu-id="2b00c-120">To ensure data integrity, make sure no other BAM cubing or data maintenance DTS packages run when this backup package is scheduled to run.</span></span>  
  
    <span data-ttu-id="2b00c-121">若要确保 BAMArchive 数据库发生故障时，备份 BAMArchive 数据库将分区复制到 BAMArchive 数据库之后但在从 BAMPrimaryImport 数据库删除分区之前能够恢复完整的已存档的数据集。</span><span class="sxs-lookup"><span data-stu-id="2b00c-121">To ensure that you can recover a complete set of archived data if the BAMArchive database fails, back up the BAMArchive database after you copy the partition into the BAMArchive database, but before you delete the partition from the BAMPrimaryImport database.</span></span> <span data-ttu-id="2b00c-122">若要执行此操作，修改数据维护 DTS 包的每个活动以插入一个步骤来备份 BAMArchive 数据库之前，在 DTS 包的最后一步"结束存档"。</span><span class="sxs-lookup"><span data-stu-id="2b00c-122">To do this, modify the data maintenance DTS package for each activity to insert a step to back up the BAMArchive database before the last step in the DTS package, "End Archiving."</span></span>  
  
5. <span data-ttu-id="2b00c-123">备份 BAMAnalysis 数据库，然后备份 BAMStarSchema 数据库。</span><span class="sxs-lookup"><span data-stu-id="2b00c-123">Back up the BAMAnalysis database, and then the BAMStarSchema database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b00c-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="2b00c-124">See Also</span></span>  
 [<span data-ttu-id="2b00c-125">备份和还原 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="2b00c-125">Backing Up and Restoring the BizTalk Server Databases</span></span>](../core/backing-up-and-restoring-the-biztalk-server-databases.md)