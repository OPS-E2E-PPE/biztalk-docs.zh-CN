---
title: 如何备份和还原 SQL 代理作业 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f82fc5a5-5ea5-476c-bed1-c5d41a50e673
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea39b09736904a6ba9ef7d19dc20e833b1d1f351
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342489"
---
# <a name="how-to-back-up-and-restore-sql-agent-jobs"></a><span data-ttu-id="937e6-102">如何备份和还原 SQL 代理作业</span><span class="sxs-lookup"><span data-stu-id="937e6-102">How to Back Up and Restore SQL Agent Jobs</span></span>
<span data-ttu-id="937e6-103">本主题介绍如何备份和还原 SQL Server 代理作业。</span><span class="sxs-lookup"><span data-stu-id="937e6-103">This topic describes how to back up and restore SQL Server Agent Jobs.</span></span> <span data-ttu-id="937e6-104">在配置它们之后，应备份 SQL 作业。</span><span class="sxs-lookup"><span data-stu-id="937e6-104">You should back up your SQL jobs after you configure them.</span></span>  
  
## <a name="biztalk-server-jobs"></a><span data-ttu-id="937e6-105">BizTalk Server 作业</span><span class="sxs-lookup"><span data-stu-id="937e6-105">BizTalk Server Jobs</span></span>  
 <span data-ttu-id="937e6-106">以下 SQL Server 代理作业与 BizTalk Server 相关联。</span><span class="sxs-lookup"><span data-stu-id="937e6-106">The following SQL Server Agent jobs are associated with BizTalk Server.</span></span> <span data-ttu-id="937e6-107">每个服务器上安装的作业是安装和配置的功能而异。</span><span class="sxs-lookup"><span data-stu-id="937e6-107">The jobs installed on each server are different depending on which features are installed and configured.</span></span> <span data-ttu-id="937e6-108">BizTalk Server 安装过程中创建大多数这些作业。</span><span class="sxs-lookup"><span data-stu-id="937e6-108">Most of these jobs are created during BizTalk Server setup.</span></span> <span data-ttu-id="937e6-109">配置日志传送时创建多个。</span><span class="sxs-lookup"><span data-stu-id="937e6-109">Several are created when configuring log shipping.</span></span>  
  
-   <span data-ttu-id="937e6-110">备份 BizTalk Server (BizTalkMgmtDb)</span><span class="sxs-lookup"><span data-stu-id="937e6-110">Backup BizTalk Server (BizTalkMgmtDb)</span></span>  
  
-   <span data-ttu-id="937e6-111">CleanupBTFExpiredEntriesJob_BizTalkMgmtDb</span><span class="sxs-lookup"><span data-stu-id="937e6-111">CleanupBTFExpiredEntriesJob_BizTalkMgmtDb</span></span>  
  
-   <span data-ttu-id="937e6-112">DTA 清除和存档 (BizTalkDTADb)</span><span class="sxs-lookup"><span data-stu-id="937e6-112">DTA Purge and Archive (BizTalkDTADb)</span></span>  
  
-   <span data-ttu-id="937e6-113">MessageBox_DeadProcesses_Cleanup_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="937e6-113">MessageBox_DeadProcesses_Cleanup_BizTalkMsgBoxDb</span></span>  
  
-   <span data-ttu-id="937e6-114">MessageBox_Message_Cleanup_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="937e6-114">MessageBox_Message_Cleanup_BizTalkMsgBoxDb</span></span>  
  
-   <span data-ttu-id="937e6-115">MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="937e6-115">MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb</span></span>  
  
-   <span data-ttu-id="937e6-116">MessageBox_Parts_Cleanup_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="937e6-116">MessageBox_Parts_Cleanup_BizTalkMsgBoxDb</span></span>  
  
-   <span data-ttu-id="937e6-117">MessageBox_UpdateStats_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="937e6-117">MessageBox_UpdateStats_BizTalkMsgBoxDb</span></span>  
  
-   <span data-ttu-id="937e6-118">Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="937e6-118">Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb</span></span>  
  
-   <span data-ttu-id="937e6-119">PurgeSubscriptionsJob_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="937e6-119">PurgeSubscriptionsJob_BizTalkMsgBoxDb</span></span>  
  
-   <span data-ttu-id="937e6-120">Rules_Database_Cleanup_BizTalkRuleEngineDb</span><span class="sxs-lookup"><span data-stu-id="937e6-120">Rules_Database_Cleanup_BizTalkRuleEngineDb</span></span>  
  
-   <span data-ttu-id="937e6-121">TrackedMessages_Copy_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="937e6-121">TrackedMessages_Copy_BizTalkMsgBoxDb</span></span>  
  
-   <span data-ttu-id="937e6-122">BTS 日志传送获取备份历史记录</span><span class="sxs-lookup"><span data-stu-id="937e6-122">BTS Log Shipping Get Backup History</span></span>  
  
-   <span data-ttu-id="937e6-123">BTS 日志传送还原数据库</span><span class="sxs-lookup"><span data-stu-id="937e6-123">BTS Log Shipping Restore Database</span></span>  
  
-   <span data-ttu-id="937e6-124">BTS 日志传送还原到标记</span><span class="sxs-lookup"><span data-stu-id="937e6-124">BTS Log Shipping Restore To Mark</span></span>  
  
## <a name="back-up-a-job-using-a-script"></a><span data-ttu-id="937e6-125">备份作业使用的脚本</span><span class="sxs-lookup"><span data-stu-id="937e6-125">Back up a job using a script</span></span>  
  
1.  <span data-ttu-id="937e6-126">打开 SQL Server Management Studio。</span><span class="sxs-lookup"><span data-stu-id="937e6-126">Open **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="937e6-127">展开 **“SQL Server 代理”**，然后展开 **“作业”**。</span><span class="sxs-lookup"><span data-stu-id="937e6-127">Expand **SQL Server Agent**, and expand **Jobs**.</span></span>  
  
3.  <span data-ttu-id="937e6-128">右键单击你想要创建备份脚本，然后选择的作业**编写作业脚本为**。</span><span class="sxs-lookup"><span data-stu-id="937e6-128">Right-click the job you want to create a backup script for, and then select **Script Job as**.</span></span>  
  
4.  <span data-ttu-id="937e6-129">选择**创建到**或**拖放到**，然后选择**新查询编辑器窗口**，**文件**，或**剪贴板**若要选择脚本目标。</span><span class="sxs-lookup"><span data-stu-id="937e6-129">Select **CREATE To** or **DROP To**, then select **New Query Editor Window**, **File**, or **Clipboard** to select a destination for the script.</span></span> <span data-ttu-id="937e6-130">通常情况下，目标是文件，并且 **.sql**扩展。</span><span class="sxs-lookup"><span data-stu-id="937e6-130">Typically, the destination is a file with a **.sql** extension.</span></span>  
  
5.  <span data-ttu-id="937e6-131">重复此过程步骤 3 中的为每个要编写脚本的作业。</span><span class="sxs-lookup"><span data-stu-id="937e6-131">Repeat this procedure from Step 3 for each job you want to script.</span></span> <span data-ttu-id="937e6-132">到的列表，请参阅 BizTalk Server 相关的作业，以确定哪些作业需要脚本。</span><span class="sxs-lookup"><span data-stu-id="937e6-132">Refer to the list of BizTalk Server related jobs to determine which jobs you need to script.</span></span>  
  
     <span data-ttu-id="937e6-133">至少，您应该备份**备份 BizTalk Server (BizTalkMgmtDb)** 作业配置后。</span><span class="sxs-lookup"><span data-stu-id="937e6-133">At a minimum, you should back up the **Backup BizTalk Server (BizTalkMgmtDb)** job after it is configured.</span></span>  
  
## <a name="restore-a-job-from-a-script"></a><span data-ttu-id="937e6-134">从脚本还原作业</span><span class="sxs-lookup"><span data-stu-id="937e6-134">Restore a job from a script</span></span>  
  
1.  <span data-ttu-id="937e6-135">打开 SQL Server Management Studio。</span><span class="sxs-lookup"><span data-stu-id="937e6-135">Open **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="937e6-136">上**文件**菜单中，**打开**包含已编写脚本的作业的文件。</span><span class="sxs-lookup"><span data-stu-id="937e6-136">On the **File** menu, **Open** the file containing the scripted job.</span></span>  
  
3.  <span data-ttu-id="937e6-137">执行脚本以创建作业。</span><span class="sxs-lookup"><span data-stu-id="937e6-137">Execute the script to create the job.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="937e6-138">后续步骤</span><span class="sxs-lookup"><span data-stu-id="937e6-138">Next Steps</span></span>  
 [<span data-ttu-id="937e6-139">如何备份和还原 SQL Server 登录名</span><span class="sxs-lookup"><span data-stu-id="937e6-139">How to Back Up and Restore SQL Server Logins</span></span>](../core/how-to-back-up-and-restore-sql-server-logins.md)