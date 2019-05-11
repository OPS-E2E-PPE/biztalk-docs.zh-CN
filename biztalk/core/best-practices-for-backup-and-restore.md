---
title: 备份和还原最佳实践 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aaf721ba-50ce-4334-b86d-e856b54d3486
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 540e8660ccc60d1e927c544beab2548a357a781f
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530515"
---
# <a name="best-practices-for-backup-and-restore"></a><span data-ttu-id="4c811-102">有关备份和还原最佳实践</span><span class="sxs-lookup"><span data-stu-id="4c811-102">Best Practices for Backup and Restore</span></span>
-   <span data-ttu-id="4c811-103">**创建备份和还原计划**</span><span class="sxs-lookup"><span data-stu-id="4c811-103">**Create a backup and restore plan**</span></span>  
  
     <span data-ttu-id="4c811-104">确保备份计划中指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="4c811-104">Be sure your backup plan specifies:</span></span>  
  
    -   <span data-ttu-id="4c811-105">存储备份的计算机</span><span class="sxs-lookup"><span data-stu-id="4c811-105">The computer where backups will be stored</span></span>  
  
    -   <span data-ttu-id="4c811-106">用于备份系统的程序</span><span class="sxs-lookup"><span data-stu-id="4c811-106">The programs that you will use to back up your system</span></span>  
  
    -   <span data-ttu-id="4c811-107">要进行备份的计算机</span><span class="sxs-lookup"><span data-stu-id="4c811-107">The computers you want to back up</span></span>  
  
    -   <span data-ttu-id="4c811-108">安排进行备份的时间</span><span class="sxs-lookup"><span data-stu-id="4c811-108">The schedule when backups will occur</span></span>  
  
    -   <span data-ttu-id="4c811-109">存档备份的非现场位置</span><span class="sxs-lookup"><span data-stu-id="4c811-109">The offsite location where you will archive backups</span></span>  
  
-   <span data-ttu-id="4c811-110">**将 BizTalk Server 系统保留的所有更改的书面的记录**</span><span class="sxs-lookup"><span data-stu-id="4c811-110">**Keep a written record of all changes to your BizTalk Server system**</span></span>  
  
     <span data-ttu-id="4c811-111">确保记下对系统所做的所有更改，比如已经应用的 Service Pack、修补程序和 QFE。</span><span class="sxs-lookup"><span data-stu-id="4c811-111">Be sure to write down all changes to your system, such as service packs, hotfixes, and QFEs that have been applied.</span></span> <span data-ttu-id="4c811-112">这对于使系统尽可能地还原到发生硬件故障之前的状态至关重要。</span><span class="sxs-lookup"><span data-stu-id="4c811-112">This is crucial to getting your system restored as closely as possible to what existed before the hardware failure.</span></span>  
  
-   <span data-ttu-id="4c811-113">**采取以下措施来防止或尽量减轻灾难的影响：**</span><span class="sxs-lookup"><span data-stu-id="4c811-113">**Implement the following measures to help prevent or minimize the effect of a disaster:**</span></span>  
  
    -   <span data-ttu-id="4c811-114">使软件和固件更新随时可用。</span><span class="sxs-lookup"><span data-stu-id="4c811-114">Have your software and firmware updates available.</span></span>  
  
    -   <span data-ttu-id="4c811-115">使所有软件安装磁盘随时可用。</span><span class="sxs-lookup"><span data-stu-id="4c811-115">Have all software installation disks readily available.</span></span> <span data-ttu-id="4c811-116">这既包含系统软件（如专用驱动程序），也包含应用程序软件（如 BizTalk Server）。</span><span class="sxs-lookup"><span data-stu-id="4c811-116">This includes both system software such as specialized drivers, and application software such as BizTalk Server.</span></span>  
  
    -   <span data-ttu-id="4c811-117">制订计划主动监控服务器。</span><span class="sxs-lookup"><span data-stu-id="4c811-117">Have a plan to monitor servers proactively.</span></span> <span data-ttu-id="4c811-118">这点非常重要，因为在长达十分钟之内失败主机上的业务流程实例可能无法由另一台主机恢复。</span><span class="sxs-lookup"><span data-stu-id="4c811-118">This is very important, since orchestration instances on a failed host may not be recovered by a second host for up to ten minutes.</span></span>  
  
    -   <span data-ttu-id="4c811-119">保留硬件记录。</span><span class="sxs-lookup"><span data-stu-id="4c811-119">Maintain hardware records.</span></span>  
  
    -   <span data-ttu-id="4c811-120">保留软件记录。</span><span class="sxs-lookup"><span data-stu-id="4c811-120">Maintain software records.</span></span>  
  
-   <span data-ttu-id="4c811-121">**级别的硬件或软件在组织中实现容错功能**</span><span class="sxs-lookup"><span data-stu-id="4c811-121">**Implement fault tolerance in your organization at the hardware or software level**</span></span>  
  
     <span data-ttu-id="4c811-122">实现群集和独立磁盘冗余阵列 (RAID) 有助于确保您的系统幸免于硬件故障。</span><span class="sxs-lookup"><span data-stu-id="4c811-122">Implementing clusters and redundant array of independent disks (RAID) helps ensure that your system can survive a hardware failure.</span></span>  
  
-   <span data-ttu-id="4c811-123">**存档定期在安全的位置上的备份介质**</span><span class="sxs-lookup"><span data-stu-id="4c811-123">**Archive the backup media on a regular basis in a secure location**</span></span>  
  
     <span data-ttu-id="4c811-124">制订定期存档备份媒体的计划并将存档保存在安全的非现场位置。</span><span class="sxs-lookup"><span data-stu-id="4c811-124">Create a schedule for archiving your backup media on a regular basis and keep the archives in a secure, offsite location.</span></span> <span data-ttu-id="4c811-125">这样可以确保在需要备份时有可用备份。</span><span class="sxs-lookup"><span data-stu-id="4c811-125">This ensures that you have a backup available when you need it.</span></span>  
  
-   <span data-ttu-id="4c811-126">**验证备份完整性和不发生错误**</span><span class="sxs-lookup"><span data-stu-id="4c811-126">**Verify the integrity of your backups and that they occur without error**</span></span>  
  
     <span data-ttu-id="4c811-127">监视所有备份作业，并确保备份作业在不发生任何错误的情况下完成。</span><span class="sxs-lookup"><span data-stu-id="4c811-127">Monitor all of your backup jobs and ensure that they complete without any errors.</span></span>  
  
-   <span data-ttu-id="4c811-128">**保留相同的备用硬件**</span><span class="sxs-lookup"><span data-stu-id="4c811-128">**Keep identical spare hardware available**</span></span>  
  
     <span data-ttu-id="4c811-129">保留完全相同的备用硬件可以确保快速更换有故障的硬件，以便实现快速恢复并重新运行。</span><span class="sxs-lookup"><span data-stu-id="4c811-129">Having identical spare hardware available ensures that you can quickly replace defective hardware to get up-and-running more quickly.</span></span>  
  
-   <span data-ttu-id="4c811-130">**记载并测试恢复过程**</span><span class="sxs-lookup"><span data-stu-id="4c811-130">**Document and test your recovery procedures**</span></span>  
  
     <span data-ttu-id="4c811-131">理想情况下，灾难恢复测试应在运行生产系统之前进行。</span><span class="sxs-lookup"><span data-stu-id="4c811-131">Ideally, disaster recovery testing should be conducted before running your system in production.</span></span> <span data-ttu-id="4c811-132">制订好计划并执行预发布测试可确保您的 IT 员工能够恢复 BizTalk Server 系统。</span><span class="sxs-lookup"><span data-stu-id="4c811-132">Having plans in place and performing prerelease testing will ensure that your IT staff can recover your BizTalk Server systems.</span></span> <span data-ttu-id="4c811-133">这通常表示必须定期尝试将系统备份还原到您将使用的实际硬件</span><span class="sxs-lookup"><span data-stu-id="4c811-133">This generally means that you must periodically attempt to retore the system backup to the actual hardware you will use</span></span>  
  
-   <span data-ttu-id="4c811-134">**培训您的 IT 员工进行灾难恢复过程**</span><span class="sxs-lookup"><span data-stu-id="4c811-134">**Train your IT staff on disaster recovery procedures**</span></span>  
  
     <span data-ttu-id="4c811-135">确保您的 IT 员工在需要时随时可以对系统进行恢复。</span><span class="sxs-lookup"><span data-stu-id="4c811-135">Ensure that your IT staff is prepared to recover the system should the need arise.</span></span>  
  
-   <span data-ttu-id="4c811-136">**练习从测试环境中的备份中还原**</span><span class="sxs-lookup"><span data-stu-id="4c811-136">**Practice restoring from backup in a test environment**</span></span>  
  
     <span data-ttu-id="4c811-137">在测试环境中练习还原 BizTalk Server 系统可确保在发生故障时能够将系统还原到生产环境中。</span><span class="sxs-lookup"><span data-stu-id="4c811-137">Practice restoring your BizTalk Server system in a test environment to ensure that you can restore it to your production environment if a failure occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c811-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="4c811-138">See Also</span></span>  
 [<span data-ttu-id="4c811-139">备份和还原 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="4c811-139">Backing Up and Restoring BizTalk Server</span></span>](../core/backing-up-and-restoring-biztalk-server.md)