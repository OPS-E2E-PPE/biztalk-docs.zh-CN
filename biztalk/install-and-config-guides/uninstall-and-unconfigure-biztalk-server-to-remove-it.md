---
title: 卸载并取消配置 BizTalk Server 将其删除 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e9ea8757-ca49-421b-bf7b-89344201398a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ab66d347795a0b8264a8bb6238149ab1b64572b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990630"
---
# <a name="uninstall-and-unconfigure-biztalk-server-to-remove-it"></a><span data-ttu-id="0bf03-102">卸载 BizTalk Server 并取消配置以将其删除</span><span class="sxs-lookup"><span data-stu-id="0bf03-102">Uninstall and unconfigure BizTalk Server to remove it</span></span>
<span data-ttu-id="0bf03-103">卸载并取消对 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的配置。</span><span class="sxs-lookup"><span data-stu-id="0bf03-103">Uninstall and unconfigure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> 
  
##  <a name="BKMK_BeforeYouBegin"></a> <span data-ttu-id="0bf03-104">开始之前</span><span class="sxs-lookup"><span data-stu-id="0bf03-104">Before You Begin</span></span>  
  
- <span data-ttu-id="0bf03-105">卸载之前，你必须取消对 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的配置。</span><span class="sxs-lookup"><span data-stu-id="0bf03-105">Before you uninstall, you must un-configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
- <span data-ttu-id="0bf03-106">本主题列出了要删除的不同作业、包和数据库。</span><span class="sxs-lookup"><span data-stu-id="0bf03-106">This topic lists the different jobs, packages, and databases to be deleted.</span></span> <span data-ttu-id="0bf03-107">列出的名称是默认名称。</span><span class="sxs-lookup"><span data-stu-id="0bf03-107">The names listed are the default names.</span></span> <span data-ttu-id="0bf03-108">你的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境可以使用非默认名称。</span><span class="sxs-lookup"><span data-stu-id="0bf03-108">Your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment may be using non-default names.</span></span>  
  
- <span data-ttu-id="0bf03-109">按列出的顺序完成各步骤。</span><span class="sxs-lookup"><span data-stu-id="0bf03-109">Complete the steps in the order listed.</span></span> <span data-ttu-id="0bf03-110">否则，卸载会不完整。</span><span class="sxs-lookup"><span data-stu-id="0bf03-110">Otherwise, the uninstall is not complete.</span></span>  
  
##  <a name="BKMK_Unconfigure"></a> <span data-ttu-id="0bf03-111">取消对 BizTalk Server 的配置</span><span class="sxs-lookup"><span data-stu-id="0bf03-111">Un-configure BizTalk Server</span></span>  
  
1. <span data-ttu-id="0bf03-112">右键单击“[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置”，然后单击“以管理员身份运行”。</span><span class="sxs-lookup"><span data-stu-id="0bf03-112">Right-click **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Configuration**, and select **Run as Administrator**.</span></span>  
  
2. <span data-ttu-id="0bf03-113">在“配置”中，选择“取消对功能的配置”。</span><span class="sxs-lookup"><span data-stu-id="0bf03-113">In the Configuration, select **Unconfigure Features**.</span></span>  
  
3. <span data-ttu-id="0bf03-114">选择要取消配置的功能，然后选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="0bf03-114">Select the features you want to unconfigure, and select **OK**.</span></span> <span data-ttu-id="0bf03-115">如果系统提示继续操作，请选择“是”。</span><span class="sxs-lookup"><span data-stu-id="0bf03-115">If prompted to proceed, select **Yes**.</span></span> <span data-ttu-id="0bf03-116">若要从计算机中完全删除，可以选择所有功能。</span><span class="sxs-lookup"><span data-stu-id="0bf03-116">To  remove everything from the computer, you can select all the features.</span></span>  
  
4. <span data-ttu-id="0bf03-117">选择“下一步”，然后继续完成向导。</span><span class="sxs-lookup"><span data-stu-id="0bf03-117">Select **Next**, and continue through the wizard.</span></span>  
  
   <span data-ttu-id="0bf03-118">日志文件生成于临时文件夹，如下所示：C:\Users\username\AppData\Local\Temp\ConfigLog(8-29-2016 0h37m59s).log。</span><span class="sxs-lookup"><span data-stu-id="0bf03-118">A log file is generated in a temp folder, similar to: C:\Users\username\AppData\Local\Temp\ConfigLog(8-29-2016 0h37m59s).log.</span></span>  
  
##  <a name="BKMK_Uninstall"></a> <span data-ttu-id="0bf03-119">卸载 BizTalk Server 运行时组件</span><span class="sxs-lookup"><span data-stu-id="0bf03-119">Uninstall BizTalk Server Runtime Components</span></span>  
  
1. <span data-ttu-id="0bf03-120">打开“程序和功能”。</span><span class="sxs-lookup"><span data-stu-id="0bf03-120">Open **Programs and Features**.</span></span>  
  
2. <span data-ttu-id="0bf03-121">从列表中选择 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 版本，然后选择“卸载”。</span><span class="sxs-lookup"><span data-stu-id="0bf03-121">Select  your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] version from the list, and  **Uninstall**.</span></span>  
  
3. <span data-ttu-id="0bf03-122">“删除”它，然后继续完成向导。</span><span class="sxs-lookup"><span data-stu-id="0bf03-122">**Remove** it, and continue through the wizard.</span></span>  
  
   <span data-ttu-id="0bf03-123">日志文件生成于临时文件夹，如下所示：C:\Users\\*username*\AppData\Local\Setup(083016 xxxxxx).htm</span><span class="sxs-lookup"><span data-stu-id="0bf03-123">A log file is generated in a temp folder, similar to: C:\Users\\*username*\AppData\Local\Setup(083016 xxxxxx).htm</span></span>  
  
##  <a name="BKMK_UninstallSSO"></a> <span data-ttu-id="0bf03-124">卸载企业单一登录</span><span class="sxs-lookup"><span data-stu-id="0bf03-124">Uninstall Enterprise Single Sign-On</span></span>  
  
1. <span data-ttu-id="0bf03-125">打开“程序和功能”。</span><span class="sxs-lookup"><span data-stu-id="0bf03-125">Open **Programs and Features**.</span></span>  
  
2. <span data-ttu-id="0bf03-126">从列表中选择“Microsoft 企业单一登录”，然后选择“卸载”。</span><span class="sxs-lookup"><span data-stu-id="0bf03-126">Select **Microsoft Enterprise Single Sign-On** from the list, and **Uninstall**.</span></span>  
  
3. <span data-ttu-id="0bf03-127">“删除”它，然后继续完成向导。</span><span class="sxs-lookup"><span data-stu-id="0bf03-127">**Remove** it, and continue through the wizard.</span></span>  
  
   <span data-ttu-id="0bf03-128">日志文件生成于临时文件夹，如下所示：C:\Users\\*username*\AppData\Local\Setup(083016 xxxxxx).htm</span><span class="sxs-lookup"><span data-stu-id="0bf03-128">A log file is generated in a temp folder, similar to: C:\Users\\*username*\AppData\Local\Setup(083016 xxxxxx).htm</span></span>  
  
##  <a name="BKMK_RemoveRemaining"></a> <span data-ttu-id="0bf03-129">删除 SQL 作业、数据库和包</span><span class="sxs-lookup"><span data-stu-id="0bf03-129">Delete SQL jobs, databases, and packages</span></span>  
  
#### <a name="delete-sql-server-agent-jobs"></a><span data-ttu-id="0bf03-130">删除 SQL Server 代理作业</span><span class="sxs-lookup"><span data-stu-id="0bf03-130">Delete SQL Server agent jobs</span></span>  
  
1.  <span data-ttu-id="0bf03-131">以管理员身份打开 **SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="0bf03-131">Open **SQL Server Management Studio** as Administrator.</span></span>  
  
2.  <span data-ttu-id="0bf03-132">在“SQL Server Management Studio”中，连接到“数据库引擎”，依次展开“SQL Server 代理”，然后展开“作业”。</span><span class="sxs-lookup"><span data-stu-id="0bf03-132">In **SQL Server Management Studio**, connect to **Database Engine**, expand **SQL Server Agent**, and expand  **Jobs**.</span></span>  
  
3.  <span data-ttu-id="0bf03-133">删除以下作业（右键单击作业，然后选择“删除”：</span><span class="sxs-lookup"><span data-stu-id="0bf03-133">Delete the following jobs (right-click the job, and select **Delete**):</span></span>  
  
    -   <span data-ttu-id="0bf03-134">备份 BizTalk Server (BizTalkMgmtDb)</span><span class="sxs-lookup"><span data-stu-id="0bf03-134">Backup BizTalk Server (BizTalkMgmtDb)</span></span>  
  
    -   <span data-ttu-id="0bf03-135">CleanupBTFExpiredEntriesJob_BizTalkMgmtDb</span><span class="sxs-lookup"><span data-stu-id="0bf03-135">CleanupBTFExpiredEntriesJob_BizTalkMgmtDb</span></span>  
  
    -   <span data-ttu-id="0bf03-136">DTA 清除和存档 (BizTalkDTADb)</span><span class="sxs-lookup"><span data-stu-id="0bf03-136">DTA Purge and Archive (BizTalkDTADb)</span></span>  
  
    -   <span data-ttu-id="0bf03-137">MessageBox_DeadProcesses_Cleanup_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="0bf03-137">MessageBox_DeadProcesses_Cleanup_BizTalkMsgBoxDb</span></span>  
  
    -   <span data-ttu-id="0bf03-138">MessageBox_Message_Cleanup_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="0bf03-138">MessageBox_Message_Cleanup_BizTalkMsgBoxDb</span></span>  
  
    -   <span data-ttu-id="0bf03-139">MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="0bf03-139">MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb</span></span>  
  
    -   <span data-ttu-id="0bf03-140">MessageBox_Parts_Cleanup_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="0bf03-140">MessageBox_Parts_Cleanup_BizTalkMsgBoxDb</span></span>  
  
    -   <span data-ttu-id="0bf03-141">MessageBox_UpdateStats_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="0bf03-141">MessageBox_UpdateStats_BizTalkMsgBoxDb</span></span>  
  
    -   <span data-ttu-id="0bf03-142">监视 BizTalk Server (BizTalkMgmtDb)</span><span class="sxs-lookup"><span data-stu-id="0bf03-142">Monitor BizTalk Server (BizTalkMgmtDb)</span></span>  
  
    -   <span data-ttu-id="0bf03-143">Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="0bf03-143">Operations_OperateOnInstances_OnMaster_BizTalkMsgBoxDb</span></span>  
  
    -   <span data-ttu-id="0bf03-144">PurgeSubscriptionsJob_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="0bf03-144">PurgeSubscriptionsJob_BizTalkMsgBoxDb</span></span>  
  
    -   <span data-ttu-id="0bf03-145">Rules_Database_Cleanup_BizTalkRuleEngineDb</span><span class="sxs-lookup"><span data-stu-id="0bf03-145">Rules_Database_Cleanup_BizTalkRuleEngineDb</span></span>  
  
    -   <span data-ttu-id="0bf03-146">TrackedMessages_Copy_BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="0bf03-146">TrackedMessages_Copy_BizTalkMsgBoxDb</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="0bf03-147">如果你部署了 BAM，可能需要删除 bam_\<*多维数据集名称*\>_\<*视图名称*\>作业。</span><span class="sxs-lookup"><span data-stu-id="0bf03-147">If you deployed BAM, you may also need to remove the bam_\<*Cube Name*\>_\<*View Name*\> job.</span></span>  
  
#### <a name="delete-biztalk-server-databases"></a><span data-ttu-id="0bf03-148">删除 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="0bf03-148">Delete BizTalk Server databases</span></span>  
  
1.  <span data-ttu-id="0bf03-149">在“对象资源管理器”中，展开“数据库”。</span><span class="sxs-lookup"><span data-stu-id="0bf03-149">In **Object Explorer**, expand **Databases**.</span></span>  
  
2.  <span data-ttu-id="0bf03-150">删除以下数据库（右键单击数据库，然后选择“删除”）：</span><span class="sxs-lookup"><span data-stu-id="0bf03-150">Delete the following databases (right-click the database, and select **Delete**):</span></span>  
  
    -   <span data-ttu-id="0bf03-151">BAMArchive</span><span class="sxs-lookup"><span data-stu-id="0bf03-151">BAMArchive</span></span>  
  
    -   <span data-ttu-id="0bf03-152">BAMPrimaryImport</span><span class="sxs-lookup"><span data-stu-id="0bf03-152">BAMPrimaryImport</span></span>  
  
    -   <span data-ttu-id="0bf03-153">BAMStarSchema</span><span class="sxs-lookup"><span data-stu-id="0bf03-153">BAMStarSchema</span></span>  
  
    -   <span data-ttu-id="0bf03-154">BizTalkDTADb</span><span class="sxs-lookup"><span data-stu-id="0bf03-154">BizTalkDTADb</span></span>  
  
    -   <span data-ttu-id="0bf03-155">BizTalkMgmtDb</span><span class="sxs-lookup"><span data-stu-id="0bf03-155">BizTalkMgmtDb</span></span>  
  
    -   <span data-ttu-id="0bf03-156">BizTalkMsgBoxDb</span><span class="sxs-lookup"><span data-stu-id="0bf03-156">BizTalkMsgBoxDb</span></span>  
  
    -   <span data-ttu-id="0bf03-157">BizTalkRuleEngineDb</span><span class="sxs-lookup"><span data-stu-id="0bf03-157">BizTalkRuleEngineDb</span></span>  
  
    -   <span data-ttu-id="0bf03-158">SSODB</span><span class="sxs-lookup"><span data-stu-id="0bf03-158">SSODB</span></span>  
  
#### <a name="remove-sql-server-integration-services-packages"></a><span data-ttu-id="0bf03-159">删除 SQL Server Integration Services 包</span><span class="sxs-lookup"><span data-stu-id="0bf03-159">Remove SQL Server Integration Services packages</span></span>  
  
1.  <span data-ttu-id="0bf03-160">在“对象资源管理器”中，**连接**到 **Integration Services**。</span><span class="sxs-lookup"><span data-stu-id="0bf03-160">In **Object Explorer**,  **Connect** to **Integration Services**.</span></span>  
  
2.  <span data-ttu-id="0bf03-161">展开“已存储的包”，然后展开“MSDB”。</span><span class="sxs-lookup"><span data-stu-id="0bf03-161">Expand **Stored Packages**, and expand **MSDB**.</span></span>  
  
3.  <span data-ttu-id="0bf03-162">删除具有以下前缀的包（右键单击该包，然后选择“删除”：</span><span class="sxs-lookup"><span data-stu-id="0bf03-162">Delete the packages with the following prefixes (right-click the package, and select **Delete**):</span></span>  
  
    -   <span data-ttu-id="0bf03-163">BAM_AN_\<*多维数据集名称*\></span><span class="sxs-lookup"><span data-stu-id="0bf03-163">BAM_AN_\<*Cube Name*\></span></span>  
  
    -   <span data-ttu-id="0bf03-164">BAM_DM_\<*视图名称*\></span><span class="sxs-lookup"><span data-stu-id="0bf03-164">BAM_DM_\<*View Name*\></span></span>  
  
