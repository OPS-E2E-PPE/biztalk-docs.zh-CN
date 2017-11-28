---
title: "如何安排备份 BizTalk Server 作业 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- backing up, scheduling
- backing up, backup jobs
- scheduling, backup jobs
ms.assetid: 6e89fff4-da87-4cdc-acc4-46f03c3269fc
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d6b40ae933874e1c25cb3a93dbbeab514ef5dfe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-schedule-the-backup-biztalk-server-job"></a><span data-ttu-id="a1627-102">如何安排备份 BizTalk Server 作业</span><span class="sxs-lookup"><span data-stu-id="a1627-102">How to Schedule the Backup BizTalk Server Job</span></span>
<span data-ttu-id="a1627-103">备份[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]作为 SQL Server 代理服务计划的作业运行。</span><span class="sxs-lookup"><span data-stu-id="a1627-103">The Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job runs as scheduled by the SQL Server Agent service.</span></span> <span data-ttu-id="a1627-104">如果要修改备份频率，可使用 SQL Server Management Studio 来更改备份 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 作业的计划。</span><span class="sxs-lookup"><span data-stu-id="a1627-104">If you want to create more frequent or less frequent backups, you can change the schedule of the Backup [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] job by using SQL Server Management Studio.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a1627-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="a1627-105">Prerequisites</span></span>  
 <span data-ttu-id="a1627-106">若要执行此过程，必须以 SQL Server sysadmin 固定服务器角色成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="a1627-106">You must be logged on with an account that is a member of the SQL Server sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-schedule-the-backup-biztalk-server-job-sql-server-2008"></a><span data-ttu-id="a1627-107">若要计划备份 BizTalk Server 作业 (SQL Server 2008)</span><span class="sxs-lookup"><span data-stu-id="a1627-107">To schedule the Backup BizTalk Server job (SQL Server 2008)</span></span>  
  
1.  <span data-ttu-id="a1627-108">在包含 BizTalk 管理数据库的计算机，单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 R2**，然后单击**Microsoft SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="a1627-108">On the computer that contains the BizTalk Management database, click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, and then click **Microsoft SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="a1627-109">在**连接到服务器**对话框中，指定其中 BizTalk Server 数据库的 SQL server 名称驻留和键入，，然后单击适当的身份验证**连接**。</span><span class="sxs-lookup"><span data-stu-id="a1627-109">In the **Connect to Server** dialog box, specify the name of the SQL Server where the BizTalk Server databases reside and the appropriate authentication type, and then click **Connect**.</span></span>  
  
3.  <span data-ttu-id="a1627-110">在对象资源管理器中，双击**SQL Server 代理**，然后单击**作业**。</span><span class="sxs-lookup"><span data-stu-id="a1627-110">In the Object Explorer, double-click **SQL Server Agent**, and then click **Jobs**.</span></span>  
  
4.  <span data-ttu-id="a1627-111">在细节窗格中，右键单击**备份 BizTalk Server (BizTalkMgmtDb)**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="a1627-111">In the details pane, right-click **Backup BizTalk Server (BizTalkMgmtDb)**, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="a1627-112">在**作业属性-备份 BizTalk Server (BizTalkMgmtDb)**对话框中，在**选择页**，单击**步骤**。</span><span class="sxs-lookup"><span data-stu-id="a1627-112">In the **Job Properties - Backup BizTalk Server (BizTalkMgmtDb)** dialog box, under **Select a page**, click **Steps**.</span></span>  
  
6.  <span data-ttu-id="a1627-113">在**作业步骤列表**，单击**BackupFull**，然后单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="a1627-113">In the **Job step list**, click **BackupFull**, and then click **Edit**.</span></span>  
  
7.  <span data-ttu-id="a1627-114">在**作业步骤属性-BackupFull**对话框中，在**命令**框中，编辑该命令，通过更改为所需的间隔，在其中执行完整备份的频率： **'h'**（每小时），**具有**（每天）、 **w** （每周一次），**我**（按月） **y** （每年），然后单击**确定**.</span><span class="sxs-lookup"><span data-stu-id="a1627-114">In the **Job Step Properties - BackupFull** dialog box, in the **Command** box, edit the command by changing the frequency to the desired interval at which to perform a full backup: **'h'** (hourly), **'d'** (daily), **'w'** (weekly), **'m'** (monthly), **'y'** (yearly), and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a1627-115">当备份 BizTalk Server 作业在新周期内第一次运行时，就会执行一次完整备份。</span><span class="sxs-lookup"><span data-stu-id="a1627-115">The first time the Backup BizTalk Server job is run during a new period, a full backup is performed.</span></span>  
  
8.  <span data-ttu-id="a1627-116">在**作业属性-备份 BizTalk Server (BizTalkMgmtDb)**对话框中，在**选择页**，单击**计划**。</span><span class="sxs-lookup"><span data-stu-id="a1627-116">In the **Job Properties - Backup BizTalk Server (BizTalkMgmtDb)** dialog box, under **Select a page**, click **Schedules**.</span></span>  
  
9. <span data-ttu-id="a1627-117">在**计划列表**，单击**MarkAndBackupLogSched**，然后单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="a1627-117">In the **Schedule list**, click **MarkAndBackupLogSched**, and then click **Edit**.</span></span>  
  
10. <span data-ttu-id="a1627-118">在**作业计划属性-MarkAndBackupLogSched**对话框中，在计划类型，选择**重复执行**从下拉列表框中 （如果尚未选择）。</span><span class="sxs-lookup"><span data-stu-id="a1627-118">In the **Job Schedule Properties - MarkAndBackupLogSched** dialog box, in Schedule type, select **Recurring** from the drop-down list box (if it is not already selected).</span></span>  
  
     <span data-ttu-id="a1627-119">默认情况下，作业每 15 分钟运行一次。</span><span class="sxs-lookup"><span data-stu-id="a1627-119">By default, the job is scheduled to run every 15 minutes.</span></span>  
  
11. <span data-ttu-id="a1627-120">更新根据需要，计划，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a1627-120">Update the schedule as desired, and then click **OK**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a1627-121">有关计划 SQL Server 代理作业的详细信息，请参阅"[计划作业](http://go.microsoft.com/fwlink/?LinkId=195887)。"</span><span class="sxs-lookup"><span data-stu-id="a1627-121">For more information about scheduling SQL Server Agent jobs, see "[Scheduling Jobs](http://go.microsoft.com/fwlink/?LinkId=195887)."</span></span>  
  
12. <span data-ttu-id="a1627-122">在**作业属性-备份 BizTalk Server (BizTalkMgmtDb)**对话框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a1627-122">In the **Job Properties - Backup BizTalk Server (BizTalkMgmtDb)** dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1627-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a1627-123">See Also</span></span>  
 <span data-ttu-id="a1627-124">[如何配置备份 BizTalk Server 作业](../core/how-to-configure-the-backup-biztalk-server-job.md) </span><span class="sxs-lookup"><span data-stu-id="a1627-124">[How to Configure the Backup BizTalk Server Job](../core/how-to-configure-the-backup-biztalk-server-job.md) </span></span>  
 <span data-ttu-id="a1627-125">[如何为日志传送配置的目标系统](../core/how-to-configure-the-destination-system-for-log-shipping.md) </span><span class="sxs-lookup"><span data-stu-id="a1627-125">[How to Configure the Destination System for Log Shipping](../core/how-to-configure-the-destination-system-for-log-shipping.md) </span></span>  
 <span data-ttu-id="a1627-126">[如何还原数据库](../core/how-to-restore-your-databases.md) </span><span class="sxs-lookup"><span data-stu-id="a1627-126">[How to Restore Your Databases](../core/how-to-restore-your-databases.md) </span></span>  
 [<span data-ttu-id="a1627-127">有关备份和还原的高级的信息</span><span class="sxs-lookup"><span data-stu-id="a1627-127">Advanced Information About Backup and Restore</span></span>](../core/advanced-information-about-backup-and-restore1.md)