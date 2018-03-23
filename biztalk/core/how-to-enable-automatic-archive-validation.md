---
title: 如何启用自动存档验证 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- validating, archives [Tracking database]
- archiving [Tracking database], validating archive
ms.assetid: 406ca54a-6b1f-4bdb-9bad-bea5ea0f6e66
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e654d22a08a7b07210ded9c319953c288065927a
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
---
# <a name="how-to-enable-automatic-archive-validation"></a><span data-ttu-id="b373f-102">如何启用自动存档验证</span><span class="sxs-lookup"><span data-stu-id="b373f-102">How to Enable Automatic Archive Validation</span></span>
<span data-ttu-id="b373f-103">使用存档验证可以在创建存档时对其进行验证。</span><span class="sxs-lookup"><span data-stu-id="b373f-103">Archive validation enables you to validate the archives as they are created.</span></span> <span data-ttu-id="b373f-104">启用自动存档验证之前，必须先设置一个辅助数据库服务器，也称为验证服务器。</span><span class="sxs-lookup"><span data-stu-id="b373f-104">Before you can enable automatic archive validation, you must set up a secondary database server, also called a validation server.</span></span> <span data-ttu-id="b373f-105">由于存档进程是一个简单备份，因此存储在磁盘上的实际图像可能由于硬件问题而受损。</span><span class="sxs-lookup"><span data-stu-id="b373f-105">Because the archiving process is a simple backup, it is possible that the actual image stored on the disk can be corrupted due to a hardware issue.</span></span>  
  
 <span data-ttu-id="b373f-106">使用存档验证功能，可确保存档（备份）成功并且可以进行还原。</span><span class="sxs-lookup"><span data-stu-id="b373f-106">Using the archive validation feature, you can ensure the archive (backup) was successful and can be restored.</span></span> <span data-ttu-id="b373f-107">在创建存档后，将通知验证服务器已创建了新的存档。</span><span class="sxs-lookup"><span data-stu-id="b373f-107">After an archive is created, the validation server is notified that a new archive has been created.</span></span> <span data-ttu-id="b373f-108">验证服务器将尝试还原该存档。</span><span class="sxs-lookup"><span data-stu-id="b373f-108">The validation server attempts to restore the archive.</span></span> <span data-ttu-id="b373f-109">验证服务器必须是另一个 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 实例，与运行该作业的实例不同。</span><span class="sxs-lookup"><span data-stu-id="b373f-109">A validation server must be another instance of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] different from the one in which the job is running.</span></span> <span data-ttu-id="b373f-110">验证服务器上的 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 版本必须和用于驻留数据库的 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 版本相同。</span><span class="sxs-lookup"><span data-stu-id="b373f-110">The version of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] on the validation server must be the same version as the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] used to host the databases.</span></span>  
  
 <span data-ttu-id="b373f-111">如果还原成功，则验证服务器会将此信息发送回 BizTalk 跟踪 (BizTalkDTADb) 数据库。</span><span class="sxs-lookup"><span data-stu-id="b373f-111">If the restore is successful, the validation server communicates this information back to the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="b373f-112">在成功完成还原之前，清除作业将不清除其他任何数据。</span><span class="sxs-lookup"><span data-stu-id="b373f-112">Until a successful restore is completed, the purge job will not purge any more data.</span></span>  
  
 <span data-ttu-id="b373f-113">如果还原不成功，则验证服务器会将此信息发送回 BizTalk 跟踪数据库。</span><span class="sxs-lookup"><span data-stu-id="b373f-113">If the restore is not successful, the validation server communicates this information back to the BizTalk Tracking database.</span></span> <span data-ttu-id="b373f-114">清除作业将创建另一个存档并等待对该新存档进行验证。</span><span class="sxs-lookup"><span data-stu-id="b373f-114">The purge job creates another archive and awaits validation of the new archive.</span></span> <span data-ttu-id="b373f-115">这样可避免由于存档损坏而导致丢失跟踪数据的可能性。</span><span class="sxs-lookup"><span data-stu-id="b373f-115">This prevents the possibility of a corrupted archive causing you to lose tracking data.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b373f-116">先决条件</span><span class="sxs-lookup"><span data-stu-id="b373f-116">Prerequisites</span></span>  
 <span data-ttu-id="b373f-117">若要执行此过程，登录使用的帐户必须是 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin 固定服务器角色的成员。</span><span class="sxs-lookup"><span data-stu-id="b373f-117">You must be logged on with an account that is a member of the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-enable-automatic-archive-validation"></a><span data-ttu-id="b373f-118">启用自动存档验证的步骤</span><span class="sxs-lookup"><span data-stu-id="b373f-118">To enable automatic archive validation</span></span>  
  
1.  <span data-ttu-id="b373f-119">在验证服务器上，单击 **启动**, ，单击 **所有程序**, ，单击 **Microsoft SQL Server 2008 SP2**, ，然后单击 **SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="b373f-119">On the validation server, click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 SP2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="b373f-120">在**连接到服务器**对话框框中，指定的名称[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]其中你可以通过执行测试还原过程中，验证存档，然后单击**连接**连接到相应的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="b373f-120">In the **Connect to Server** dialog box, specify the name of the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] where you can validate the archive by performing a test of the restore process, and then click **Connect** to connect to the appropriate SQL Server.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b373f-121">由于在验证存档时会降低系统性能，因此，此服务器不应同时用作其他 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的数据库服务器。</span><span class="sxs-lookup"><span data-stu-id="b373f-121">This server should not be another [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] database server as it reduces system performance when validating the archive.</span></span>  
  
3.  <span data-ttu-id="b373f-122">在 **Microsoft SQL Server Management Studio**, ，单击 **文件**, ，单击 **打开**, ，然后单击 **文件**。</span><span class="sxs-lookup"><span data-stu-id="b373f-122">In **Microsoft SQL Server Management Studio**, click **File**, click **Open**, and then click **File**.</span></span>  
  
4.  <span data-ttu-id="b373f-123">在 **打开的文件** 对话框中，浏览到以下 SQL 脚本︰</span><span class="sxs-lookup"><span data-stu-id="b373f-123">In the **Open File** dialog box, browse to the following SQL script:</span></span>  
  
    ```  
    %SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\BTS_Tracking_ValidateArchive.sql  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="b373f-124">你可能需要将脚本从运行 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的计算机复制到验证服务器。</span><span class="sxs-lookup"><span data-stu-id="b373f-124">You might need to copy the script from the computer running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to the validation server.</span></span>  
  
5.  <span data-ttu-id="b373f-125">单击 **查询** 菜单，，然后单击 **执行**。</span><span class="sxs-lookup"><span data-stu-id="b373f-125">Click the **Query** menu, and then click **Execute**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b373f-126">只有当将 BizTalk 跟踪 (BizTalkDTADb) 数据库存档到其中的文件夹是网络共享时，BTS_Tracking_ValidateArchive.sql 脚本才能正常工作。</span><span class="sxs-lookup"><span data-stu-id="b373f-126">The BTS_Tracking_ValidateArchive.sql script only works if the folder where you are archiving your BizTalk Tracking (BizTalkDTADb) database is a network share.</span></span>  
  
     <span data-ttu-id="b373f-127">BTS_Tracking_ValidateArchive.sql 脚本将创建一个名为 ValidateArchive 的 SQL Server 代理作业。</span><span class="sxs-lookup"><span data-stu-id="b373f-127">The BTS_Tracking_ValidateArchive.sql script creates a SQL Server Agent job called ValidateArchive.</span></span>  
  
6.  <span data-ttu-id="b373f-128">存档和清除进程可能访问和/或更新数据库在不同的 SQL 服务器，因此你必须设置所涉及的 SQL Server 实例之间的链接服务器。</span><span class="sxs-lookup"><span data-stu-id="b373f-128">The archiving and purging process potentially accesses and/or updates databases in different SQL Servers, so you must set up linked servers between the involved SQL Server instances.</span></span> <span data-ttu-id="b373f-129">在 **SQL Server Management Studio**, ，双击 **Server 对象**, ，右键单击 **链接服务器**, ，然后单击 **新链接服务器**。</span><span class="sxs-lookup"><span data-stu-id="b373f-129">In **SQL Server Management Studio**, double-click **Server Objects**, right-click **Linked Servers**, and then click **New Linked Server**.</span></span>  
  
     <span data-ttu-id="b373f-130">你必须设置之间的链接服务器︰</span><span class="sxs-lookup"><span data-stu-id="b373f-130">You must set up linked server between:</span></span>  
  
    -   <span data-ttu-id="b373f-131">每个 BizTalk MessageBox (BizTalkMsgBoxDb) 数据库和 BizTalk 跟踪 (BizTalkDTADb) 数据库（如果它们驻留在不同的服务器上）。</span><span class="sxs-lookup"><span data-stu-id="b373f-131">Each of your BizTalk MessageBox (BizTalkMsgBoxDb) databases and the BizTalk Tracking (BizTalkDTADb) database if they reside on different servers.</span></span>  
  
    -   <span data-ttu-id="b373f-132">BizTalk 跟踪 (BizTalkDTADb) 数据库以及用于存档验证的验证服务器。</span><span class="sxs-lookup"><span data-stu-id="b373f-132">The BizTalk Tracking (BizTalkDTADb) database and the validating server for archive validation.</span></span>  
  
    -   <span data-ttu-id="b373f-133">BizTalk MessageBox (BizTalkMsgBoxDb) 数据库的宿主计算机上的 SQL Server 代理的服务帐户必须对链接服务器上的 BizTalk 跟踪 (BizTalkDTADb) 数据库具有 db_datareader 和 db_datawriter 权限。</span><span class="sxs-lookup"><span data-stu-id="b373f-133">The service accounts for the SQL Server Agent on the computer hosting the BizTalk MessageBox (BizTalkMsgBoxDb) database must have the db_datareader and db_datawriter permissions for the BizTalk Tracking (BizTalkDTADb) database on the linked server.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b373f-134">运行作业所使用的帐户对链接的双方数据库都应具有数据库操作员 (DBO) 权限。</span><span class="sxs-lookup"><span data-stu-id="b373f-134">The account used for running the job should have Database Operator (DBO) privileges on both the databases.</span></span>  
  
7.  <span data-ttu-id="b373f-135">在 **新链接服务器** 对话框中，在 **常规** 页上，在 **链接服务器**, ，输入你想要链接到的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="b373f-135">In the **New Linked Server** dialog box, on the **General** page, in **Linked server**, enter the name of the server you want to link to.</span></span>  
  
     <span data-ttu-id="b373f-136">例如，BizTalk MessageBox (BizTalkMsgBoxDb) 数据库、BizTalk 跟踪 (BizTalkDTADb) 数据库或验证服务器的宿主服务器。</span><span class="sxs-lookup"><span data-stu-id="b373f-136">For example, the server hosting the BizTalk MessageBox (BizTalkMsgBoxDb) database, BizTalk Tracking (BizTalkDTADb) database, or the validation server.</span></span>  
  
8.  <span data-ttu-id="b373f-137">下 **服务器类型**, ，单击 **SQL Server**, ，然后单击 **确定**。</span><span class="sxs-lookup"><span data-stu-id="b373f-137">Under **Server type**, click **SQL Server**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="b373f-138">在 **Microsoft SQL Server Management Studio**, ，双击 **SQL Server 代理**, ，然后单击 **作业**。</span><span class="sxs-lookup"><span data-stu-id="b373f-138">In **Microsoft SQL Server Management Studio**, double-click **SQL Server Agent**, and then click **Jobs**.</span></span>  
  
10. <span data-ttu-id="b373f-139">在 **对象资源管理器详细信息** 窗格中，右键单击 **ValidateArchive**, ，然后单击 **属性**。</span><span class="sxs-lookup"><span data-stu-id="b373f-139">In the **Object Explorer Details** pane, right-click **ValidateArchive**, and then click **Properties**.</span></span>  
  
11. <span data-ttu-id="b373f-140">在 **作业属性-ValidateArchive** 对话框中，在 **选择页**, ，单击 **步骤**。</span><span class="sxs-lookup"><span data-stu-id="b373f-140">In the **Job Properties - ValidateArchive** dialog box, under **Select a page**, click **Steps**.</span></span>  
  
12. <span data-ttu-id="b373f-141">在 **作业步骤列表**, ，单击 **验证**, ，然后单击 **编辑**。</span><span class="sxs-lookup"><span data-stu-id="b373f-141">In the **Job step list**, click **validate**, and then click **Edit**.</span></span>  
  
13. <span data-ttu-id="b373f-142">上 **常规** 页上，在 **命令** 框中，在命令中， **exec dtasp_ValidateArchive null，null**, ，替换 null，null 替换承载 BizTalk 跟踪数据库，括在单引号后, 跟用引号引起来，BizTalk 跟踪数据库的名称的服务器的名称，然后单击 **确定**。</span><span class="sxs-lookup"><span data-stu-id="b373f-142">On the **General** page, in the **Command** box, in the command, **exec dtasp_ValidateArchive null, null**, replace null, null with the name of the server hosting the BizTalk Tracking database, surrounded by single quotes, followed by the name of the BizTalk Tracking database, surrounded by quotes, and then click **OK**.</span></span> <span data-ttu-id="b373f-143">例如：</span><span class="sxs-lookup"><span data-stu-id="b373f-143">For example:</span></span>  
  
     <span data-ttu-id="b373f-144">**exec dtasp_ValidateArchive '** *\<TrackingServerName\>* **', '** *\<TrackingDatabaseName\>* **'**</span><span class="sxs-lookup"><span data-stu-id="b373f-144">**exec dtasp_ValidateArchive '** *\<TrackingServerName\>* **', '** *\<TrackingDatabaseName\>* **'**</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b373f-145">ValidateArchive 作业没有计划并且不应为其配置计划。</span><span class="sxs-lookup"><span data-stu-id="b373f-145">The ValidateArchive job does not have a schedule and you should not configure a schedule for it.</span></span> <span data-ttu-id="b373f-146">相反，在创建存档时 DTA 清除和存档 (BizTalkDTADb) 作业将自动启动此作业。</span><span class="sxs-lookup"><span data-stu-id="b373f-146">Instead, the DTA Purge and Archive (BizTalkDTADb) job starts this job automatically when an archive is created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b373f-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b373f-147">See Also</span></span>  
 [<span data-ttu-id="b373f-148">存档和清除 BizTalk 跟踪数据库</span><span class="sxs-lookup"><span data-stu-id="b373f-148">Archiving and Purging the BizTalk Tracking Database</span></span>](../core/archiving-and-purging-the-biztalk-tracking-database.md)