---
title: 计划备份的 BizTalk Server 作业 |Microsoft 文档
description: 配置备份 BizTalk Server 作业参数，并将计划设置为运行每月、 每周、 每日或每小时
ms.custom: ''
ms.date: 11/02/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e89fff4-da87-4cdc-acc4-46f03c3269fc
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f09ca97f65605ac3bf427d1c1fcc322a14feb53
ms.sourcegitcommit: 9aaed443492b74729171fef79c634bff561af929
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2017
ms.locfileid: "23980749"
---
# <a name="schedule-the-backup-biztalk-server-job"></a><span data-ttu-id="ac761-103">计划备份的 BizTalk Server 作业</span><span class="sxs-lookup"><span data-stu-id="ac761-103">Schedule the Backup BizTalk Server Job</span></span>
<span data-ttu-id="ac761-104">备份[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]作为 SQL Server 代理服务计划的作业运行。</span><span class="sxs-lookup"><span data-stu-id="ac761-104">The Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job runs as scheduled by the SQL Server Agent service.</span></span> <span data-ttu-id="ac761-105">如果要修改备份频率，可使用 SQL Server Management Studio 来更改备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 作业的计划。</span><span class="sxs-lookup"><span data-stu-id="ac761-105">If you want to create more frequent or less frequent backups, you can change the schedule of the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job by using SQL Server Management Studio.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ac761-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="ac761-106">Prerequisites</span></span>  
<span data-ttu-id="ac761-107">使用 SQL Server sysadmin 固定服务器角色的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="ac761-107">Sign in with an account that is a member of the SQL Server sysadmin fixed server role.</span></span>  
  
## <a name="schedule-the-backup-biztalk-server-job"></a><span data-ttu-id="ac761-108">计划备份 BizTalk Server 作业</span><span class="sxs-lookup"><span data-stu-id="ac761-108">Schedule the Backup BizTalk Server job</span></span>
  
1.  <span data-ttu-id="ac761-109">在承载 BizTalk 管理数据库的 SQL 服务器，打开**SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="ac761-109">On the SQL Server that hosts the BizTalk Management database, open **SQL Server Management Studio**.</span></span>

2.  <span data-ttu-id="ac761-110">在**连接到服务器**，输入 SQL Server 数据库所驻留，BizTalk 服务器在其中选择身份验证类型的名称，然后**连接**。</span><span class="sxs-lookup"><span data-stu-id="ac761-110">In **Connect to Server**, enter the name of the SQL Server where the BizTalk Server databases reside, select the authentication type, and then **Connect**.</span></span>  
  
3.  <span data-ttu-id="ac761-111">在对象资源管理器中，双击**SQL Server 代理**，然后选择**作业**。</span><span class="sxs-lookup"><span data-stu-id="ac761-111">In the Object Explorer, double-click **SQL Server Agent**, and then select **Jobs**.</span></span>  
  
4.  <span data-ttu-id="ac761-112">在细节窗格中，右键单击**备份 BizTalk Server (BizTalkMgmtDb)**，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="ac761-112">In the details pane, right-click **Backup BizTalk Server (BizTalkMgmtDb)**, and then select **Properties**.</span></span>  
  
5.  <span data-ttu-id="ac761-113">在**作业属性-备份 BizTalk Server (BizTalkMgmtDb)** 下**选择页**，选择**步骤**。</span><span class="sxs-lookup"><span data-stu-id="ac761-113">In the **Job Properties - Backup BizTalk Server (BizTalkMgmtDb)**, under **Select a page**, select **Steps**.</span></span>  
  
6.  <span data-ttu-id="ac761-114">在**作业步骤列表**，选择**BackupFull**，然后选择**编辑**。</span><span class="sxs-lookup"><span data-stu-id="ac761-114">In the **Job step list**, select **BackupFull**, and then select **Edit**.</span></span>  
  
7.  <span data-ttu-id="ac761-115">在**作业步骤属性-BackupFull**中**命令**框中，通过更改运行完整备份的频率更新命令： **'h'** （每小时），**具有** （每天）、 **w** （每周一次），**我**（按月） **y** （每年）。</span><span class="sxs-lookup"><span data-stu-id="ac761-115">In the **Job Step Properties - BackupFull**, in the **Command** box, update the command by changing the frequency to run a full backup: **'h'** (hourly), **'d'** (daily), **'w'** (weekly), **'m'** (monthly), **'y'** (yearly).</span></span> <span data-ttu-id="ac761-116">选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="ac761-116">Select **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ac761-117">首次备份的 BizTalk Server 作业运行时，它将完成的完整备份。</span><span class="sxs-lookup"><span data-stu-id="ac761-117">The first time the Backup BizTalk Server job runs, it completes a full backup.</span></span>  
    
8.  <span data-ttu-id="ac761-118">配置其他 **@frequency** 参数：</span><span class="sxs-lookup"><span data-stu-id="ac761-118">Configure additional **@frequency** parameters:</span></span>  
  
    - <span data-ttu-id="ac761-119">**@ForceFullBackupAfterPartialSetFailure**： 默认值是**false**。</span><span class="sxs-lookup"><span data-stu-id="ac761-119">**@ForceFullBackupAfterPartialSetFailure**: The default value is **false**.</span></span> <span data-ttu-id="ac761-120">当**false**，如果下一个周期进行完整备份是将等待，则完整备份将失败，系统。</span><span class="sxs-lookup"><span data-stu-id="ac761-120">When **false**, if the full backup fails, the system waits for the next cycle until the full backup is made.</span></span>  
    
        > [!NOTE]
        >  <span data-ttu-id="ac761-121">如果你 **@frequency** 设置长时间 （如每周、 每月、 每年），然后将设置此参数为**false**会非常危险。</span><span class="sxs-lookup"><span data-stu-id="ac761-121">If your **@frequency** setting is long (like weekly, monthly, yearly), then setting this parameter to **false** could be dangerous.</span></span> <span data-ttu-id="ac761-122">在此方案中，它可能是最好将此标志设置为**true**。</span><span class="sxs-lookup"><span data-stu-id="ac761-122">In this scenario, it may be best to set this flag to **true**.</span></span> <span data-ttu-id="ac761-123">当**true**，每次失败，则系统强制本身创建完整备份。</span><span class="sxs-lookup"><span data-stu-id="ac761-123">When **true**, every time there is a failure, the system forces itself to create a full backup.</span></span> <span data-ttu-id="ac761-124">存在可能会很小的性能影响，但它是 safter 具有可恢复的系统。</span><span class="sxs-lookup"><span data-stu-id="ac761-124">There may be a small performance impact, but it’s safter to have a recoverable system.</span></span>
  
    - <span data-ttu-id="ac761-125">**@BackupHour**： 默认值为 NULL。</span><span class="sxs-lookup"><span data-stu-id="ac761-125">**@BackupHour**: The default valueis NULL.</span></span> <span data-ttu-id="ac761-126">此参数直接相关 **@Frequency** 。</span><span class="sxs-lookup"><span data-stu-id="ac761-126">This parameter is directly related to **@Frequency**.</span></span> <span data-ttu-id="ac761-127">当将频率设置为**h** （每小时），设置你想要运行的完整备份的日期的小时。</span><span class="sxs-lookup"><span data-stu-id="ac761-127">When you set the frequency to **h** (hourly), you set which hour of the day you want the full backup to run.</span></span> <span data-ttu-id="ac761-128">你可以选择介于 0 （午夜） 到 23 （晚上 11 点） 之间的值。</span><span class="sxs-lookup"><span data-stu-id="ac761-128">You can choose a value between 0 (midnight) to 23 (11 PM).</span></span> <span data-ttu-id="ac761-129">如果留空，每小时都会运行完整备份。</span><span class="sxs-lookup"><span data-stu-id="ac761-129">If left blank, the full backup runs every hour.</span></span>  
    
       > [!NOTE]
        >  <span data-ttu-id="ac761-130">如果超出了 0 到 23 范围 （例如，100 或-1） 数量设置此参数，系统会将其强制为 0。</span><span class="sxs-lookup"><span data-stu-id="ac761-130">If you set this parameter with a number outside the 0 to 23 range (for example, 100 or -1), the system forces it to 0.</span></span>
  
    - <span data-ttu-id="ac761-131">**@UseLocalTime**： 状态为使用本地时间了额外的参数。</span><span class="sxs-lookup"><span data-stu-id="ac761-131">**@UseLocalTime**: An extra parameter that states to use local time.</span></span> <span data-ttu-id="ac761-132">默认情况下，作业适用于 UTC 时间。</span><span class="sxs-lookup"><span data-stu-id="ac761-132">By default, the job works with UTC time.</span></span> <span data-ttu-id="ac761-133">因此如果你的居住在澳大利亚 （这是 UTC + 10 小时），你的备份将在上午 10，而不是午夜运行。</span><span class="sxs-lookup"><span data-stu-id="ac761-133">So if you live in Australia (which is UTC + 10 hours), your backup runs at 10am rather than midnight.</span></span> <span data-ttu-id="ac761-134">作为最佳做法，建议将其设置为**1** (true)。</span><span class="sxs-lookup"><span data-stu-id="ac761-134">As a best practice, it is recommended to set this to **1** (true).</span></span>  
  
9.  <span data-ttu-id="ac761-135">在**作业属性-备份 BizTalk Server (BizTalkMgmtDb)** 下**选择页**，单击**计划**。</span><span class="sxs-lookup"><span data-stu-id="ac761-135">In the **Job Properties - Backup BizTalk Server (BizTalkMgmtDb)**, under **Select a page**, click **Schedules**.</span></span>  
  
10. <span data-ttu-id="ac761-136">在**计划列表**，单击**MarkAndBackupLogSched**，然后单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="ac761-136">In the **Schedule list**, click **MarkAndBackupLogSched**, and then click **Edit**.</span></span>  
  
11. <span data-ttu-id="ac761-137">在**作业计划属性-MarkAndBackupLogSched**，在计划类型中，选择**重复执行**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="ac761-137">In the **Job Schedule Properties - MarkAndBackupLogSched**, in Schedule type, select **Recurring** from the drop-down list.</span></span>  
  
     <span data-ttu-id="ac761-138">默认情况下，作业每 15 分钟运行一次。</span><span class="sxs-lookup"><span data-stu-id="ac761-138">By default, the job is scheduled to run every 15 minutes.</span></span>  
     
    > [!NOTE]
    >  <span data-ttu-id="ac761-139">你可以更改此值根据要求，但在非生产环境中的第一个测试。</span><span class="sxs-lookup"><span data-stu-id="ac761-139">You can change this value according to your requirements, but first test in non-production environment.</span></span> <span data-ttu-id="ac761-140">设置此值过低导致频繁地备份，并将添加到您的 SQL 环境中的后台负载。</span><span class="sxs-lookup"><span data-stu-id="ac761-140">Setting this value too low results in frequent backups, and adds to the background load in your SQL environment.</span></span> <span data-ttu-id="ac761-141">设置此值过高可能会增加事务日志的大小，影响性能。</span><span class="sxs-lookup"><span data-stu-id="ac761-141">Setting this value too high may increase the size of transaction logs, and impact performance.</span></span> <span data-ttu-id="ac761-142">在某些情况下，建议保留默认值。</span><span class="sxs-lookup"><span data-stu-id="ac761-142">In some situations, it is recommended to leave the default value.</span></span>    
  
12. <span data-ttu-id="ac761-143">更新的计划，如果需要，，然后选择**确定**。</span><span class="sxs-lookup"><span data-stu-id="ac761-143">Update the schedule if desired, and then select **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ac761-144">[计划作业](https://docs.microsoft.com/sql/ssms/agent/schedule-a-job)提供更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="ac761-144">[Scheduling Jobs](https://docs.microsoft.com/sql/ssms/agent/schedule-a-job) provides more details.</span></span>
  
13. <span data-ttu-id="ac761-145">在**作业属性-备份 BizTalk Server (BizTalkMgmtDb)**，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="ac761-145">In the **Job Properties - Backup BizTalk Server (BizTalkMgmtDb)**, click **OK**.</span></span>  
  
## <a name="more-good-stuff"></a><span data-ttu-id="ac761-146">更多有用内容</span><span class="sxs-lookup"><span data-stu-id="ac761-146">More good stuff</span></span>  
 <span data-ttu-id="ac761-147">[配置备份 BizTalk Server 作业](../core/how-to-configure-the-backup-biztalk-server-job.md) </span><span class="sxs-lookup"><span data-stu-id="ac761-147">[Configure the Backup BizTalk Server Job](../core/how-to-configure-the-backup-biztalk-server-job.md) </span></span>  
 <span data-ttu-id="ac761-148">[为日志传送配置的目标系统](../core/how-to-configure-the-destination-system-for-log-shipping.md) </span><span class="sxs-lookup"><span data-stu-id="ac761-148">[Configure the Destination System for Log Shipping](../core/how-to-configure-the-destination-system-for-log-shipping.md) </span></span>  
 <span data-ttu-id="ac761-149">[还原数据库](../core/how-to-restore-your-databases.md) </span><span class="sxs-lookup"><span data-stu-id="ac761-149">[Restore Your Databases](../core/how-to-restore-your-databases.md) </span></span>  
 [<span data-ttu-id="ac761-150">有关备份和还原的高级信息</span><span class="sxs-lookup"><span data-stu-id="ac761-150">Advanced Information About Backup and Restore</span></span>](../core/advanced-information-about-backup-and-restore1.md)
