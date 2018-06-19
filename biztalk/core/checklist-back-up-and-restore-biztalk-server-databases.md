---
title: 清单： 备份和还原 BizTalk Server 数据库 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- backing up, BizTalk Server
- restoring, checklists
- maintaining, restoring
- maintaining, checklists
- restoring, BizTalk Server
- maintaining, backing up
- checklists, backing up
- backing up, checklists
- BizTalk Server, backing up
- checklists, restoring
- BizTalk Server, restoring
ms.assetid: 12f7e02e-57b1-4e55-8e44-7fe2d7920f5a
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f3c8c68eb62273562b0f703ae79c0db76ec837c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232701"
---
# <a name="checklist-back-up-and-restore-biztalk-server-databases"></a><span data-ttu-id="d20b3-102">清单： 备份和还原 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="d20b3-102">Checklist: Back Up and Restore BizTalk Server Databases</span></span>
<span data-ttu-id="d20b3-103">尝试备份或还原 BizTalk Server 之前，请确保您熟悉所涉及的过程。</span><span class="sxs-lookup"><span data-stu-id="d20b3-103">Before attempting to back up or restore BizTalk Server, be sure to familiarize yourself with the processes involved.</span></span>  
  
## <a name="backing-up-biztalk-server"></a><span data-ttu-id="d20b3-104">备份 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="d20b3-104">Backing Up BizTalk Server</span></span>  
  
|<span data-ttu-id="d20b3-105">步骤</span><span class="sxs-lookup"><span data-stu-id="d20b3-105">Step</span></span>|<span data-ttu-id="d20b3-106">参考</span><span class="sxs-lookup"><span data-stu-id="d20b3-106">Reference</span></span>|  
|----------|---------------|  
|<span data-ttu-id="d20b3-107">学习如何备份和还原 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="d20b3-107">Learn how to back up and restore BizTalk Server.</span></span>|[<span data-ttu-id="d20b3-108">备份和还原数据库的最佳实践</span><span class="sxs-lookup"><span data-stu-id="d20b3-108">Best Practices for Backing Up and Restoring Databases</span></span>](../core/best-practices-for-backing-up-and-restoring-databases.md)<br /><br /> [<span data-ttu-id="d20b3-109">备份和还原 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="d20b3-109">Backing Up and Restoring BizTalk Server Databases</span></span>](../core/backing-up-and-restoring-biztalk-server-databases.md)|  
|<span data-ttu-id="d20b3-110">确保您有适当的权限备份和还原 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="d20b3-110">Ensure that you have appropriate permissions to back up and restore BizTalk Server.</span></span>|[<span data-ttu-id="d20b3-111">最低安全用户权限</span><span class="sxs-lookup"><span data-stu-id="d20b3-111">Minimum Security User Rights</span></span>](../core/minimum-security-user-rights.md)|  
|<span data-ttu-id="d20b3-112">配置备份 BizTalk Server 作业。</span><span class="sxs-lookup"><span data-stu-id="d20b3-112">Configure the Backup BizTalk Server job.</span></span>|[<span data-ttu-id="d20b3-113">如何配置备份 BizTalk Server 作业</span><span class="sxs-lookup"><span data-stu-id="d20b3-113">How to Configure the Backup BizTalk Server Job</span></span>](../core/how-to-configure-the-backup-biztalk-server-job.md)|  
|<span data-ttu-id="d20b3-114">配置存储备份的服务器。</span><span class="sxs-lookup"><span data-stu-id="d20b3-114">Configure the server where backups will be stored.</span></span>|[<span data-ttu-id="d20b3-115">如何为日志传送配置的目标系统</span><span class="sxs-lookup"><span data-stu-id="d20b3-115">How to Configure the Destination System for Log Shipping</span></span>](../core/how-to-configure-the-destination-system-for-log-shipping.md)|  
|<span data-ttu-id="d20b3-116">如果在使用业务活动监视 (BAM)，请备份 BAM 数据库。</span><span class="sxs-lookup"><span data-stu-id="d20b3-116">If you are using Business Activity Monitoring (BAM), back up the BAM databases.</span></span>|[<span data-ttu-id="d20b3-117">备份和还原 BAM</span><span class="sxs-lookup"><span data-stu-id="d20b3-117">Backing Up and Restoring BAM</span></span>](../core/backing-up-and-restoring-bam.md)|  
|<span data-ttu-id="d20b3-118">如果要使用企业单一登录，请备份主密钥。</span><span class="sxs-lookup"><span data-stu-id="d20b3-118">If you are using Enterprise Single Sign-on, back up the master secret.</span></span>|[<span data-ttu-id="d20b3-119">管理主密钥</span><span class="sxs-lookup"><span data-stu-id="d20b3-119">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)|  
  
## <a name="restoring-biztalk-server"></a><span data-ttu-id="d20b3-120">还原 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="d20b3-120">Restoring BizTalk Server</span></span>  
  
|<span data-ttu-id="d20b3-121">步骤</span><span class="sxs-lookup"><span data-stu-id="d20b3-121">Step</span></span>|<span data-ttu-id="d20b3-122">参考</span><span class="sxs-lookup"><span data-stu-id="d20b3-122">Reference</span></span>|  
|----------|---------------|  
|<span data-ttu-id="d20b3-123">还原数据库。</span><span class="sxs-lookup"><span data-stu-id="d20b3-123">Restore your databases.</span></span>|[<span data-ttu-id="d20b3-124">如何还原数据库</span><span class="sxs-lookup"><span data-stu-id="d20b3-124">How to Restore Your Databases</span></span>](../core/how-to-restore-your-databases.md)|  
|<span data-ttu-id="d20b3-125">更新对 BAM 数据库名称的引用。</span><span class="sxs-lookup"><span data-stu-id="d20b3-125">Update references to the BAM database names.</span></span>|[<span data-ttu-id="d20b3-126">如何备份 BAM 分析和跟踪 Analysis Server 数据库</span><span class="sxs-lookup"><span data-stu-id="d20b3-126">How to Back Up the BAM Analysis and Tracking Analysis Server Databases</span></span>](../core/how-to-back-up-the-bam-analysis-and-tracking-analysis-server-databases.md)<br /><br /> [<span data-ttu-id="d20b3-127">如何更新对 BAM Analysis Server 和星型架构数据库名称的引用</span><span class="sxs-lookup"><span data-stu-id="d20b3-127">How to Update References to the BAM Analysis Server and Star Schema Database Names</span></span>](../core/update-references-to-the-bam-analysis-server-and-star-schema-database-names.md)<br /><br /> [<span data-ttu-id="d20b3-128">如何更新对 BAM 存档数据库名称的引用</span><span class="sxs-lookup"><span data-stu-id="d20b3-128">How to Update References to the BAM Archive Database Name</span></span>](../core/how-to-update-references-to-the-bam-archive-database-name.md)<br /><br /> [<span data-ttu-id="d20b3-129">如何更新对 BAM 主导入数据库名称和连接字符串的引用</span><span class="sxs-lookup"><span data-stu-id="d20b3-129">How to Update References to the BAM Primary Import Database Name and Connection String</span></span>](../core/update-references-to-bam-primary-import-database-name-and-connection-string.md)<br /><br /> [<span data-ttu-id="d20b3-130">如何更新对 BAM 通知引用 Services 数据库</span><span class="sxs-lookup"><span data-stu-id="d20b3-130">How to Update References to the BAM Notification Services Databases</span></span>](../core/how-to-update-references-to-the-bam-notification-services-databases.md)<br /><br /> [<span data-ttu-id="d20b3-131">如何解决未完成的活动实例</span><span class="sxs-lookup"><span data-stu-id="d20b3-131">How to Resolve Incomplete Activity Instances</span></span>](../core/how-to-resolve-incomplete-activity-instances.md)|  
|<span data-ttu-id="d20b3-132">如果在使用企业单一登录，请还原主密钥。</span><span class="sxs-lookup"><span data-stu-id="d20b3-132">If you are using Enterprise Single Sign-on, restore the master secret.</span></span>|[<span data-ttu-id="d20b3-133">管理主密钥</span><span class="sxs-lookup"><span data-stu-id="d20b3-133">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)|  
  
## <a name="see-also"></a><span data-ttu-id="d20b3-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d20b3-134">See Also</span></span>  
 [<span data-ttu-id="d20b3-135">备份和还原的 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="d20b3-135">Backing Up and Restoring the BizTalk Server Databases</span></span>](../core/backing-up-and-restoring-the-biztalk-server-databases.md)