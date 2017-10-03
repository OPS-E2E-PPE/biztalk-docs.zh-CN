---
title: "管理 BAM 数据库 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [BAM], databases
- databases [BAM], managing
- databases, BAM
ms.assetid: ce3c472e-2da1-4d67-816a-befe4ded20d9
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1dbe8cdb2c7806ab62b67db80c4741d64560fba9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="managing-bam-databases"></a><span data-ttu-id="37dab-102">管理 BAM 数据库</span><span class="sxs-lookup"><span data-stu-id="37dab-102">Managing BAM Databases</span></span>
<span data-ttu-id="37dab-103">管理员使用 BAM 管理实用程序 (bm.exe) 可以安装、管理和更新 BAM 数据库。</span><span class="sxs-lookup"><span data-stu-id="37dab-103">Administrators use the BAM Management utility (bm.exe) to set up, manage, and update the BAM databases.</span></span> <span data-ttu-id="37dab-104">本部分介绍如何使用 BAM 管理实用程序来执行 BAM 数据库的这些通用管理员任务，如下表所述。</span><span class="sxs-lookup"><span data-stu-id="37dab-104">This section shows you how to use the BAM Management utility to perform these common administrator tasks for the BAM databases, which are described in the following table.</span></span>  
  
 <span data-ttu-id="37dab-105">有关备份和还原的 BAM 数据库的信息，请参阅[备份和还原 BAM](../core/backing-up-and-restoring-bam.md)。</span><span class="sxs-lookup"><span data-stu-id="37dab-105">For information about backing up and restoring the BAM databases, see [Backing Up and Restoring BAM](../core/backing-up-and-restoring-bam.md).</span></span>  
  
|<span data-ttu-id="37dab-106">数据库</span><span class="sxs-lookup"><span data-stu-id="37dab-106">Database</span></span>|<span data-ttu-id="37dab-107">默认数据库名称</span><span class="sxs-lookup"><span data-stu-id="37dab-107">Default database name</span></span>|<span data-ttu-id="37dab-108">Description</span><span class="sxs-lookup"><span data-stu-id="37dab-108">Description</span></span>|  
|--------------|---------------------------|-----------------|  
|<span data-ttu-id="37dab-109">BAM 主导入数据库</span><span class="sxs-lookup"><span data-stu-id="37dab-109">BAM Primary Import database</span></span>|<span data-ttu-id="37dab-110">BAMPrimaryImport</span><span class="sxs-lookup"><span data-stu-id="37dab-110">BAMPrimaryImport</span></span>|<span data-ttu-id="37dab-111">BAM 收集原始跟踪数据的地方。</span><span class="sxs-lookup"><span data-stu-id="37dab-111">Where BAM collects raw tracking data.</span></span>|  
|<span data-ttu-id="37dab-112">BAM 通知服务应用程序数据库</span><span class="sxs-lookup"><span data-stu-id="37dab-112">BAM Notification Services Application database</span></span>|<span data-ttu-id="37dab-113">BAMAlertsApplication</span><span class="sxs-lookup"><span data-stu-id="37dab-113">BAMAlertsApplication</span></span>|<span data-ttu-id="37dab-114">包含 BAM 通知的警报信息。</span><span class="sxs-lookup"><span data-stu-id="37dab-114">Contains alert information for BAM notifications.</span></span> <span data-ttu-id="37dab-115">例如，在使用 BAM 门户创建警报时，会将指定与警报相关的条件和事件的条目以及支持警报数据项的其他条目插入该数据库中。</span><span class="sxs-lookup"><span data-stu-id="37dab-115">For example, when you create an alert using the BAM portal, entries are inserted in the database specifying the conditions and events to which the alert pertains, as well as other supporting data items for the alert.</span></span>|  
|<span data-ttu-id="37dab-116">BAM 通知服务实例数据库</span><span class="sxs-lookup"><span data-stu-id="37dab-116">BAM Notification Services Instance database</span></span>|<span data-ttu-id="37dab-117">BAMAlertsNSMain</span><span class="sxs-lookup"><span data-stu-id="37dab-117">BAMAlertsNSMain</span></span>|<span data-ttu-id="37dab-118">包含指定 Notification Services 如何连接到 BAM 正在监视的系统的实例信息。</span><span class="sxs-lookup"><span data-stu-id="37dab-118">Contains instance information specifying how the notification services connect to the system that BAM is monitoring.</span></span>|  
|<span data-ttu-id="37dab-119">BAM 星型架构数据库</span><span class="sxs-lookup"><span data-stu-id="37dab-119">BAM Star Schema database</span></span>|<span data-ttu-id="37dab-120">BAMStarSchema</span><span class="sxs-lookup"><span data-stu-id="37dab-120">BAMStarSchema</span></span>|<span data-ttu-id="37dab-121">包含中间临时表、度量值表和维度表。</span><span class="sxs-lookup"><span data-stu-id="37dab-121">Contains the staging table, and the measure and dimension tables.</span></span>|  
|<span data-ttu-id="37dab-122">BAM 分析数据库</span><span class="sxs-lookup"><span data-stu-id="37dab-122">BAM Analysis database</span></span>|<span data-ttu-id="37dab-123">BAMAnalysis</span><span class="sxs-lookup"><span data-stu-id="37dab-123">BAMAnalysis</span></span>|<span data-ttu-id="37dab-124">包含用于进行联机和脱机分析的 BAM OLAP 多维数据集。</span><span class="sxs-lookup"><span data-stu-id="37dab-124">Contains BAM OLAP cubes for both online and offline analysis.</span></span>|  
|<span data-ttu-id="37dab-125">BAM 存档数据库</span><span class="sxs-lookup"><span data-stu-id="37dab-125">BAM Archive database</span></span>|<span data-ttu-id="37dab-126">BAMArchive</span><span class="sxs-lookup"><span data-stu-id="37dab-126">BAMArchive</span></span>|<span data-ttu-id="37dab-127">存档旧的业务活动数据。</span><span class="sxs-lookup"><span data-stu-id="37dab-127">Archives old business activity data.</span></span> <span data-ttu-id="37dab-128">您可以创建 BAM 存档数据库，以最大限度地减少 BAM 主导入数据库中的业务活动数据的累积。</span><span class="sxs-lookup"><span data-stu-id="37dab-128">You can create a BAM Archive database to minimize the accumulation of business activity data in the BAM Primary Import database.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="37dab-129">本节内容</span><span class="sxs-lookup"><span data-stu-id="37dab-129">In This Section</span></span>  
  
-   [<span data-ttu-id="37dab-130">将主导入数据库数据存档</span><span class="sxs-lookup"><span data-stu-id="37dab-130">Archiving Primary Import Database Data</span></span>](../core/archiving-primary-import-database-data.md)  
  
-   [<span data-ttu-id="37dab-131">在存档数据库中创建分区的视图</span><span class="sxs-lookup"><span data-stu-id="37dab-131">Creating a Partitioned View in the Archiving Database</span></span>](../core/creating-a-partitioned-view-in-the-archiving-database.md)  
  
-   [<span data-ttu-id="37dab-132">计划 SQL Server Integration Services 包</span><span class="sxs-lookup"><span data-stu-id="37dab-132">Scheduling SQL Server Integration Services Packages</span></span>](../core/scheduling-sql-server-integration-services-packages.md)  
  
-   [<span data-ttu-id="37dab-133">如何使用 BAM 管理实用工具 BAM 数据库设置</span><span class="sxs-lookup"><span data-stu-id="37dab-133">How to Set Up the BAM Databases Using the BAM Management Utility</span></span>](../core/how-to-set-up-the-bam-databases-using-the-bam-management-utility.md)  
  
-   [<span data-ttu-id="37dab-134">如何检索 BAM 配置文件使用 BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="37dab-134">How to Retrieve the BAM Configuration File Using the BAM Management Utility</span></span>](../core/how-to-retrieve-the-bam-configuration-file-using-the-bam-management-utility.md)  
  
-   [<span data-ttu-id="37dab-135">如何更新 BAM 配置使用 BAM 管理实用工具</span><span class="sxs-lookup"><span data-stu-id="37dab-135">How to Update the BAM Configuration Using the BAM Management Utility</span></span>](../core/how-to-update-the-bam-configuration-using-the-bam-management-utility.md)  
  
-   [<span data-ttu-id="37dab-136">如何引用其他 BAM 主导入数据库</span><span class="sxs-lookup"><span data-stu-id="37dab-136">How to Reference Additional BAM Primary Import Databases</span></span>](../core/how-to-reference-additional-bam-primary-import-databases.md)  
  
-   [<span data-ttu-id="37dab-137">如何禁用 BAM 主导入数据库参考</span><span class="sxs-lookup"><span data-stu-id="37dab-137">How to Disable a BAM Primary Import Database Reference</span></span>](../core/how-to-disable-a-bam-primary-import-database-reference.md)  
  
-   [<span data-ttu-id="37dab-138">如何列出所有引用数据库</span><span class="sxs-lookup"><span data-stu-id="37dab-138">How to List All Referenced Databases</span></span>](../core/how-to-list-all-referenced-databases.md)  
  
-   [<span data-ttu-id="37dab-139">如何删除不完整的活动实例</span><span class="sxs-lookup"><span data-stu-id="37dab-139">How to Remove Incomplete Activity Instances</span></span>](../core/how-to-remove-incomplete-activity-instances.md)  
  
-   [<span data-ttu-id="37dab-140">如何更新后的备份和还原的 BAM 管理实用程序配置</span><span class="sxs-lookup"><span data-stu-id="37dab-140">How to Update the BAM Management Utility Configuration After a Backup and Restore</span></span>](../core/update-the-bam-management-utility-configuration-after-a-backup-and-restore.md)  
  
-   [<span data-ttu-id="37dab-141">如何将与 SQL Server Reporting Services 集成 BAM</span><span class="sxs-lookup"><span data-stu-id="37dab-141">How to Integrate BAM with SQL Server Reporting Services</span></span>](../core/how-to-integrate-bam-with-sql-server-reporting-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="37dab-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="37dab-142">See Also</span></span>  
 [<span data-ttu-id="37dab-143">管理 BAM</span><span class="sxs-lookup"><span data-stu-id="37dab-143">Managing BAM</span></span>](../core/managing-bam.md)