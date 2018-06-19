---
title: 如何备份和还原 SQL 代理作业 |Microsoft 文档
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
ms.openlocfilehash: 253055f9a45dfdb9864d4d5202661e750d28b1b1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247197"
---
# <a name="how-to-back-up-and-restore-sql-agent-jobs"></a><span data-ttu-id="55a0a-102">如何备份和还原 SQL 代理作业</span><span class="sxs-lookup"><span data-stu-id="55a0a-102">How to Back Up and Restore SQL Agent Jobs</span></span>
<span data-ttu-id="55a0a-103">本主题介绍如何备份和恢复 SQL Server 代理作业。</span><span class="sxs-lookup"><span data-stu-id="55a0a-103">This topic describes how to back up and restore SQL Server Agent Jobs.</span></span> <span data-ttu-id="55a0a-104">配置 SQL 作业之后应对其进行备份。</span><span class="sxs-lookup"><span data-stu-id="55a0a-104">You should back up your SQL jobs after you configure them.</span></span>  
  
## <a name="biztalk-server-jobs"></a><span data-ttu-id="55a0a-105">BizTalk Server 作业</span><span class="sxs-lookup"><span data-stu-id="55a0a-105">BizTalk Server Jobs</span></span>  
 <span data-ttu-id="55a0a-106">以下 SQL Server 代理作业与 BizTalk Server 相关联。</span><span class="sxs-lookup"><span data-stu-id="55a0a-106">The following SQL Server Agent jobs are associated with BizTalk Server.</span></span> <span data-ttu-id="55a0a-107">每个服务器上安装的作业有所不同，具体视安装和配置的功能而定。</span><span class="sxs-lookup"><span data-stu-id="55a0a-107">The jobs installed on each server are different depending on which features are installed and configured.</span></span> <span data-ttu-id="55a0a-108">大多数作业是在 BizTalk Server 安装过程中创建的。</span><span class="sxs-lookup"><span data-stu-id="55a0a-108">Most of these jobs are created during BizTalk Server setup.</span></span> <span data-ttu-id="55a0a-109">部分作业是在配置日志传送时创建的。</span><span class="sxs-lookup"><span data-stu-id="55a0a-109">Several are created when configuring log shipping.</span></span>  
  
-   <span data-ttu-id="55a0a-110">备份 BizTalk Server (BizTalkMgmtDb)</span><span class="sxs-lookup"><span data-stu-id="55a0a-110">Backup BizTalk Server (BizTalkMgmtDb)</span></span>  
  
-   <span data-ttu-id="55a0a-111">CleanupBTFExpiredEntriesJob_BizTalkMgmtDb</span><span class="sxs-lookup"><span data-stu-id="55a0a-111">CleanupBTFExpiredEntriesJob_BizTalkMgmtDb</span></span>  
  
-   <span data-ttu-id="55a0a-112">DTA 清除和存档 (BizTalkDTADb)</span><span class="sxs-lookup"><span data-stu-id="55a0a-112">DTA Purge and Archive (BizTalkDTADb)</span></span>  
  
-   <span data-ttu-id="55a0a-113">MessageBox_DeadProcesses_Cleanup_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="55a0a-113">MessageBox_DeadProcesses_Cleanup_BizTalkMsgBoxDb</span></span>  
  
-   <span data-ttu-id="55a0a-114">MessageBox_Message_Cleanup_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="55a0a-114">MessageBox_Message_Cleanup_BizTalkMsgBoxDb</span></span>  
  
-   <span data-ttu-id="55a0a-115">MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="55a0a-115">MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb</span></span>  
  
-   <span data-ttu-id="55a0a-116">MessageBox_Parts_Cleanup_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="55a0a-116">MessageBox_Parts_Cleanup_BizTalkMsgBoxDb</span></span>  
  
-   <span data-ttu-id="55a0a-117">MessageBox_UpdateStats_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="55a0a-117">MessageBox_UpdateStats_BizTalkMsgBoxDb</span></span>  
  
-   <span data-ttu-id="55a0a-118">Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="55a0a-118">Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb</span></span>  
  
-   <span data-ttu-id="55a0a-119">PurgeSubscriptionsJob_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="55a0a-119">PurgeSubscriptionsJob_BizTalkMsgBoxDb</span></span>  
  
-   <span data-ttu-id="55a0a-120">Rules_Database_Cleanup_BizTalkRuleEngineDb</span><span class="sxs-lookup"><span data-stu-id="55a0a-120">Rules_Database_Cleanup_BizTalkRuleEngineDb</span></span>  
  
-   <span data-ttu-id="55a0a-121">TrackedMessages_Copy_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="55a0a-121">TrackedMessages_Copy_BizTalkMsgBoxDb</span></span>  
  
-   <span data-ttu-id="55a0a-122">BTS 日志传送获取备份历史记录</span><span class="sxs-lookup"><span data-stu-id="55a0a-122">BTS Log Shipping Get Backup History</span></span>  
  
-   <span data-ttu-id="55a0a-123">BTS 日志传送还原数据库</span><span class="sxs-lookup"><span data-stu-id="55a0a-123">BTS Log Shipping Restore Database</span></span>  
  
-   <span data-ttu-id="55a0a-124">BTS 日志传送还原到标记</span><span class="sxs-lookup"><span data-stu-id="55a0a-124">BTS Log Shipping Restore To Mark</span></span>  
  
## <a name="back-up-a-job-using-a-script"></a><span data-ttu-id="55a0a-125">备份使用脚本的作业</span><span class="sxs-lookup"><span data-stu-id="55a0a-125">Back up a job using a script</span></span>  
  
1.  <span data-ttu-id="55a0a-126">打开**SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="55a0a-126">Open **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="55a0a-127">展开 **“SQL Server 代理”**，然后展开 **“作业”**。</span><span class="sxs-lookup"><span data-stu-id="55a0a-127">Expand **SQL Server Agent**, and expand **Jobs**.</span></span>  
  
3.  <span data-ttu-id="55a0a-128">右键单击你想要创建的备份脚本，然后选择的作业**作为脚本作业**。</span><span class="sxs-lookup"><span data-stu-id="55a0a-128">Right-click the job you want to create a backup script for, and then select **Script Job as**.</span></span>  
  
4.  <span data-ttu-id="55a0a-129">选择**创建到**或**拖放到**，然后选择**新查询编辑器窗口**，**文件**，或**剪贴板**若要选择脚本目标。</span><span class="sxs-lookup"><span data-stu-id="55a0a-129">Select **CREATE To** or **DROP To**, then select **New Query Editor Window**, **File**, or **Clipboard** to select a destination for the script.</span></span> <span data-ttu-id="55a0a-130">通常情况下，目标是为此文件 **.sql**扩展。</span><span class="sxs-lookup"><span data-stu-id="55a0a-130">Typically, the destination is a file with a **.sql** extension.</span></span>  
  
5.  <span data-ttu-id="55a0a-131">为你要编写脚本的每个作业重复步骤 3 以后的过程。</span><span class="sxs-lookup"><span data-stu-id="55a0a-131">Repeat this procedure from Step 3 for each job you want to script.</span></span> <span data-ttu-id="55a0a-132">请参考与 BizTalk Server 相关的作业列表，以确定你需要为哪些作业编写脚本。</span><span class="sxs-lookup"><span data-stu-id="55a0a-132">Refer to the list of BizTalk Server related jobs to determine which jobs you need to script.</span></span>  
  
     <span data-ttu-id="55a0a-133">至少，你应备份**备份 BizTalk Server (BizTalkMgmtDb)** 作业后配置。</span><span class="sxs-lookup"><span data-stu-id="55a0a-133">At a minimum, you should back up the **Backup BizTalk Server (BizTalkMgmtDb)** job after it is configured.</span></span>  
  
## <a name="restore-a-job-from-a-script"></a><span data-ttu-id="55a0a-134">从脚本中还原作业</span><span class="sxs-lookup"><span data-stu-id="55a0a-134">Restore a job from a script</span></span>  
  
1.  <span data-ttu-id="55a0a-135">打开**SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="55a0a-135">Open **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="55a0a-136">上**文件**菜单上，**打开**包含已编写脚本的作业的文件。</span><span class="sxs-lookup"><span data-stu-id="55a0a-136">On the **File** menu, **Open** the file containing the scripted job.</span></span>  
  
3.  <span data-ttu-id="55a0a-137">执行该脚本以创建作业。</span><span class="sxs-lookup"><span data-stu-id="55a0a-137">Execute the script to create the job.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="55a0a-138">后续步骤</span><span class="sxs-lookup"><span data-stu-id="55a0a-138">Next Steps</span></span>  
 [<span data-ttu-id="55a0a-139">如何备份和还原 SQL Server 登录名</span><span class="sxs-lookup"><span data-stu-id="55a0a-139">How to Back Up and Restore SQL Server Logins</span></span>](../core/how-to-back-up-and-restore-sql-server-logins.md)