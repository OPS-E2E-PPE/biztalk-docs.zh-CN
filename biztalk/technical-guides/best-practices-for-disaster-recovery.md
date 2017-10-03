---
title: "灾难恢复的最佳实践 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: afbb0a57-0d31-4a2f-847c-02b40361c0ed
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e988055205203c5c4bc7a4d9d6e84706414967c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="best-practices-for-disaster-recovery"></a><span data-ttu-id="9f878-102">灾难恢复最佳方案</span><span class="sxs-lookup"><span data-stu-id="9f878-102">Best Practices for Disaster Recovery</span></span>
<span data-ttu-id="9f878-103">有关的灾难恢复最佳方案信息[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]，请参阅[的备份和还原最佳实践](http://go.microsoft.com/fwlink/?LinkId=151391)(http://go.microsoft.com/fwlink/?LinkId=151391) 中[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="9f878-103">For information about best practices for disaster recovery for [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], see [Best Practices for Backup and Restore](http://go.microsoft.com/fwlink/?LinkId=151391) (http://go.microsoft.com/fwlink/?LinkId=151391) in [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] Help.</span></span>  
  
 <span data-ttu-id="9f878-104">**创建备份和还原计划**</span><span class="sxs-lookup"><span data-stu-id="9f878-104">**Create a backup and restore plan**</span></span>  
  
-   <span data-ttu-id="9f878-105">确保备份计划中指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="9f878-105">Be sure your backup plan specifies:</span></span>  
  
    -   <span data-ttu-id="9f878-106">存储备份的计算机</span><span class="sxs-lookup"><span data-stu-id="9f878-106">The computer where backups will be stored</span></span>  
  
    -   <span data-ttu-id="9f878-107">用于备份系统的程序</span><span class="sxs-lookup"><span data-stu-id="9f878-107">The programs that you will use to back up your system</span></span>  
  
    -   <span data-ttu-id="9f878-108">要进行备份的计算机</span><span class="sxs-lookup"><span data-stu-id="9f878-108">The computers you want to back up</span></span>  
  
    -   <span data-ttu-id="9f878-109">安排进行备份的时间</span><span class="sxs-lookup"><span data-stu-id="9f878-109">The schedule when backups will occur</span></span>  
  
    -   <span data-ttu-id="9f878-110">存档备份的非现场位置</span><span class="sxs-lookup"><span data-stu-id="9f878-110">The offsite location where you will archive backups</span></span>  
  
 <span data-ttu-id="9f878-111">**记录写入的所有更改对你的 BizTalk Server 系统**</span><span class="sxs-lookup"><span data-stu-id="9f878-111">**Keep a written record of all changes to your BizTalk Server system**</span></span>  
  
-   <span data-ttu-id="9f878-112">确保记下对系统所做的所有更改，比如已经应用的 Service Pack、修补程序和 QFE。</span><span class="sxs-lookup"><span data-stu-id="9f878-112">Be sure to write down all changes to your system, such as service packs, hotfixes, and QFEs that have been applied.</span></span> <span data-ttu-id="9f878-113">这对于使系统尽可能地还原到发生硬件故障之前的状态至关重要。</span><span class="sxs-lookup"><span data-stu-id="9f878-113">This is crucial to getting your system restored as closely as possible to what existed before the hardware failure.</span></span>  
  
 <span data-ttu-id="9f878-114">**实现以下措施来帮助防止或最小灾难的影响**</span><span class="sxs-lookup"><span data-stu-id="9f878-114">**Implement the following measures to help prevent or minimize the effect of a disaster**</span></span>  
  
-   <span data-ttu-id="9f878-115">使软件和固件更新随时可用。</span><span class="sxs-lookup"><span data-stu-id="9f878-115">Have your software and firmware updates available.</span></span>  
  
-   <span data-ttu-id="9f878-116">使软件磁盘随时可用。</span><span class="sxs-lookup"><span data-stu-id="9f878-116">Have all software disks readily available.</span></span>  
  
-   <span data-ttu-id="9f878-117">制订计划主动监控服务器。</span><span class="sxs-lookup"><span data-stu-id="9f878-117">Have a plan to monitor servers proactively.</span></span> <span data-ttu-id="9f878-118">由于失败的主机上的业务流程实例可能没有恢复由第二个主机为 10 分钟，这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="9f878-118">This is very important since orchestration instances on a failed host may not be recovered by a second host for up to 10 minutes.</span></span>  
  
-   <span data-ttu-id="9f878-119">保留硬件记录。</span><span class="sxs-lookup"><span data-stu-id="9f878-119">Maintain hardware records.</span></span>  
  
-   <span data-ttu-id="9f878-120">保留软件记录。</span><span class="sxs-lookup"><span data-stu-id="9f878-120">Maintain software records.</span></span>  
  
 <span data-ttu-id="9f878-121">**在你的组织在硬件或软件级别中实现容错**</span><span class="sxs-lookup"><span data-stu-id="9f878-121">**Implement fault tolerance in your organization at the hardware or software level**</span></span>  
  
-   <span data-ttu-id="9f878-122">实现群集和独立磁盘冗余阵列 (RAID) 有助于确保您的系统幸免于硬件故障。</span><span class="sxs-lookup"><span data-stu-id="9f878-122">Implementing clusters and redundant array of independent disks (RAID) helps ensure that your system can survive a hardware failure.</span></span>  
  
 <span data-ttu-id="9f878-123">**存档在定期在安全的位置的备份介质**</span><span class="sxs-lookup"><span data-stu-id="9f878-123">**Archive the backup media on a regular basis in a secure location**</span></span>  
  
-   <span data-ttu-id="9f878-124">制订定期存档备份媒体的计划并将存档保存在安全的非现场位置。</span><span class="sxs-lookup"><span data-stu-id="9f878-124">Create a schedule for archiving your backup media on a regular basis and keep the archives in a secure, offsite location.</span></span> <span data-ttu-id="9f878-125">这样可以确保在需要备份时有可用备份。</span><span class="sxs-lookup"><span data-stu-id="9f878-125">This ensures that you have a backup available when you need it.</span></span>  
  
 <span data-ttu-id="9f878-126">**验证你的备份的完整性，并没有错误发生**</span><span class="sxs-lookup"><span data-stu-id="9f878-126">**Verify the integrity of your backups and that they occur without error**</span></span>  
  
-   <span data-ttu-id="9f878-127">监视所有备份作业，并确保备份作业在不发生任何错误的情况下完成。</span><span class="sxs-lookup"><span data-stu-id="9f878-127">Monitor all of your backup jobs and ensure that they complete without any errors.</span></span>  
  
 <span data-ttu-id="9f878-128">**提供的相同备用硬件**</span><span class="sxs-lookup"><span data-stu-id="9f878-128">**Keep identical spare hardware available**</span></span>  
  
-   <span data-ttu-id="9f878-129">有可用的相同备用硬件可以确保，可以快速替换出现故障的硬件，即可启动和更快地运行。</span><span class="sxs-lookup"><span data-stu-id="9f878-129">Having identical spare hardware available ensures that you can quickly replace defective hardware to get up and running more quickly.</span></span>  
  
 <span data-ttu-id="9f878-130">**文档和测试恢复过程**</span><span class="sxs-lookup"><span data-stu-id="9f878-130">**Document and test your recovery procedures**</span></span>  
  
-   <span data-ttu-id="9f878-131">灾难恢复测试应该在运行生产系统之前进行。</span><span class="sxs-lookup"><span data-stu-id="9f878-131">Disaster recovery testing should be conducted before ever running your system in production.</span></span> <span data-ttu-id="9f878-132">制订好计划并执行预发布测试可确保您的 IT 员工能够恢复 BizTalk Server 系统。</span><span class="sxs-lookup"><span data-stu-id="9f878-132">Having plans in place and performing prerelease testing will ensure that your IT staff can recover your BizTalk Server systems.</span></span>  
  
 <span data-ttu-id="9f878-133">**训练你的 IT 员工在灾难恢复过程**</span><span class="sxs-lookup"><span data-stu-id="9f878-133">**Train your IT staff on disaster recovery procedures**</span></span>  
  
-   <span data-ttu-id="9f878-134">确保您的 IT 员工在需要时随时可以对系统进行恢复。</span><span class="sxs-lookup"><span data-stu-id="9f878-134">Ensure that your IT staff is prepared to recover the system should the need arise.</span></span>  
  
 <span data-ttu-id="9f878-135">**练习从测试环境中的备份还原**</span><span class="sxs-lookup"><span data-stu-id="9f878-135">**Practice restoring from a backup in a test environment**</span></span>  
  
-   <span data-ttu-id="9f878-136">在测试环境中练习还原 BizTalk Server 系统可确保在发生故障时能够将系统还原到生产环境中。</span><span class="sxs-lookup"><span data-stu-id="9f878-136">Practice restoring your BizTalk Server system in a test environment to ensure that you can restore it to your production environment if a failure occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f878-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9f878-137">See Also</span></span>  
 [<span data-ttu-id="9f878-138">灾难恢复</span><span class="sxs-lookup"><span data-stu-id="9f878-138">Disaster Recovery</span></span>](../technical-guides/disaster-recovery.md)