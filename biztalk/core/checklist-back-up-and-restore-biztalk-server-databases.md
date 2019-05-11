---
title: 清单：备份和还原 BizTalk Server 数据库 |Microsoft Docs
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
ms.openlocfilehash: b3233d941e17e23e07895586b711d47ee86cdc15
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357456"
---
# <a name="checklist-back-up-and-restore-biztalk-server-databases"></a><span data-ttu-id="dc91a-102">清单：备份和还原 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="dc91a-102">Checklist: Back Up and Restore BizTalk Server Databases</span></span>
<span data-ttu-id="dc91a-103">然后再尝试备份或还原 BizTalk Server，请务必熟悉所涉及的过程。</span><span class="sxs-lookup"><span data-stu-id="dc91a-103">Before attempting to back up or restore BizTalk Server, be sure to familiarize yourself with the processes involved.</span></span>  
  
## <a name="backing-up-biztalk-server"></a><span data-ttu-id="dc91a-104">备份 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="dc91a-104">Backing Up BizTalk Server</span></span>  
  
|<span data-ttu-id="dc91a-105">步骤</span><span class="sxs-lookup"><span data-stu-id="dc91a-105">Step</span></span>|<span data-ttu-id="dc91a-106">参考</span><span class="sxs-lookup"><span data-stu-id="dc91a-106">Reference</span></span>|  
|----------|---------------|  
|<span data-ttu-id="dc91a-107">了解如何备份和还原 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="dc91a-107">Learn how to back up and restore BizTalk Server.</span></span>|[<span data-ttu-id="dc91a-108">备份和还原数据库的最佳做法</span><span class="sxs-lookup"><span data-stu-id="dc91a-108">Best Practices for Backing Up and Restoring Databases</span></span>](../core/best-practices-for-backing-up-and-restoring-databases.md)<br /><br /> [<span data-ttu-id="dc91a-109">备份和还原 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="dc91a-109">Backing Up and Restoring BizTalk Server Databases</span></span>](../core/backing-up-and-restoring-biztalk-server-databases.md)|  
|<span data-ttu-id="dc91a-110">请确保您具有相应的权限来备份和还原 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="dc91a-110">Ensure that you have appropriate permissions to back up and restore BizTalk Server.</span></span>|[<span data-ttu-id="dc91a-111">最低安全用户权限</span><span class="sxs-lookup"><span data-stu-id="dc91a-111">Minimum Security User Rights</span></span>](../core/minimum-security-user-rights.md)|  
|<span data-ttu-id="dc91a-112">配置备份 BizTalk Server 作业。</span><span class="sxs-lookup"><span data-stu-id="dc91a-112">Configure the Backup BizTalk Server job.</span></span>|[<span data-ttu-id="dc91a-113">如何配置备份 BizTalk Server 作业</span><span class="sxs-lookup"><span data-stu-id="dc91a-113">How to Configure the Backup BizTalk Server Job</span></span>](../core/how-to-configure-the-backup-biztalk-server-job.md)|  
|<span data-ttu-id="dc91a-114">配置存储备份的服务器。</span><span class="sxs-lookup"><span data-stu-id="dc91a-114">Configure the server where backups will be stored.</span></span>|[<span data-ttu-id="dc91a-115">如何配置日志传送目标系统</span><span class="sxs-lookup"><span data-stu-id="dc91a-115">How to Configure the Destination System for Log Shipping</span></span>](../core/how-to-configure-the-destination-system-for-log-shipping.md)|  
|<span data-ttu-id="dc91a-116">如果使用业务活动监视 (BAM)，备份 BAM 数据库。</span><span class="sxs-lookup"><span data-stu-id="dc91a-116">If you are using Business Activity Monitoring (BAM), back up the BAM databases.</span></span>|[<span data-ttu-id="dc91a-117">备份和还原 BAM</span><span class="sxs-lookup"><span data-stu-id="dc91a-117">Backing Up and Restoring BAM</span></span>](../core/backing-up-and-restoring-bam.md)|  
|<span data-ttu-id="dc91a-118">如果使用企业单一登录，请备份主密钥。</span><span class="sxs-lookup"><span data-stu-id="dc91a-118">If you are using Enterprise Single Sign-on, back up the master secret.</span></span>|[<span data-ttu-id="dc91a-119">管理主密钥</span><span class="sxs-lookup"><span data-stu-id="dc91a-119">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)|  
  
## <a name="restoring-biztalk-server"></a><span data-ttu-id="dc91a-120">还原 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="dc91a-120">Restoring BizTalk Server</span></span>  
  
|<span data-ttu-id="dc91a-121">步骤</span><span class="sxs-lookup"><span data-stu-id="dc91a-121">Step</span></span>|<span data-ttu-id="dc91a-122">参考</span><span class="sxs-lookup"><span data-stu-id="dc91a-122">Reference</span></span>|  
|----------|---------------|  
|<span data-ttu-id="dc91a-123">还原数据库。</span><span class="sxs-lookup"><span data-stu-id="dc91a-123">Restore your databases.</span></span>|[<span data-ttu-id="dc91a-124">如何还原数据库</span><span class="sxs-lookup"><span data-stu-id="dc91a-124">How to Restore Your Databases</span></span>](../core/how-to-restore-your-databases.md)|  
|<span data-ttu-id="dc91a-125">更新对 BAM 数据库名称的引用。</span><span class="sxs-lookup"><span data-stu-id="dc91a-125">Update references to the BAM database names.</span></span>|[<span data-ttu-id="dc91a-126">如何备份 BAM 分析和跟踪分析服务器数据库</span><span class="sxs-lookup"><span data-stu-id="dc91a-126">How to Back Up the BAM Analysis and Tracking Analysis Server Databases</span></span>](../core/how-to-back-up-the-bam-analysis-and-tracking-analysis-server-databases.md)<br /><br /> [<span data-ttu-id="dc91a-127">如何更新对 BAM 分析服务器和星型架构数据库名称的引用</span><span class="sxs-lookup"><span data-stu-id="dc91a-127">How to Update References to the BAM Analysis Server and Star Schema Database Names</span></span>](../core/update-references-to-the-bam-analysis-server-and-star-schema-database-names.md)<br /><br /> [<span data-ttu-id="dc91a-128">如何更新对 BAM 存档数据库名称的引用</span><span class="sxs-lookup"><span data-stu-id="dc91a-128">How to Update References to the BAM Archive Database Name</span></span>](../core/how-to-update-references-to-the-bam-archive-database-name.md)<br /><br /> [<span data-ttu-id="dc91a-129">如何更新对 BAM 主导入数据库名称和连接字符串引用</span><span class="sxs-lookup"><span data-stu-id="dc91a-129">How to Update References to the BAM Primary Import Database Name and Connection String</span></span>](../core/update-references-to-bam-primary-import-database-name-and-connection-string.md)<br /><br /> [<span data-ttu-id="dc91a-130">如何更新对 BAM Notification Services 数据库</span><span class="sxs-lookup"><span data-stu-id="dc91a-130">How to Update References to the BAM Notification Services Databases</span></span>](../core/how-to-update-references-to-the-bam-notification-services-databases.md)<br /><br /> [<span data-ttu-id="dc91a-131">如何解析不完整的活动实例</span><span class="sxs-lookup"><span data-stu-id="dc91a-131">How to Resolve Incomplete Activity Instances</span></span>](../core/how-to-resolve-incomplete-activity-instances.md)|  
|<span data-ttu-id="dc91a-132">如果使用企业单一登录，则还原主密钥。</span><span class="sxs-lookup"><span data-stu-id="dc91a-132">If you are using Enterprise Single Sign-on, restore the master secret.</span></span>|[<span data-ttu-id="dc91a-133">管理主密钥</span><span class="sxs-lookup"><span data-stu-id="dc91a-133">Managing the Master Secret</span></span>](../core/managing-the-master-secret.md)|  
  
## <a name="see-also"></a><span data-ttu-id="dc91a-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="dc91a-134">See Also</span></span>  
 [<span data-ttu-id="dc91a-135">备份和还原 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="dc91a-135">Backing Up and Restoring the BizTalk Server Databases</span></span>](../core/backing-up-and-restoring-the-biztalk-server-databases.md)