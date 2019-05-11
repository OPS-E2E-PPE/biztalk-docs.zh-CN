---
title: 如何启用自动存档验证 |Microsoft Docs
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
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 257e6de9ce64b8d9e1f2c27bd401b453a1a47cda
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337983"
---
# <a name="how-to-enable-automatic-archive-validation"></a><span data-ttu-id="d1bc1-102">如何启用自动存档验证</span><span class="sxs-lookup"><span data-stu-id="d1bc1-102">How to Enable Automatic Archive Validation</span></span>
<span data-ttu-id="d1bc1-103">存档验证可以验证存档，因为它们创建。</span><span class="sxs-lookup"><span data-stu-id="d1bc1-103">Archive validation enables you to validate the archives as they are created.</span></span> <span data-ttu-id="d1bc1-104">可以启用自动存档验证之前，必须设置一个辅助数据库服务器，也称为验证服务器。</span><span class="sxs-lookup"><span data-stu-id="d1bc1-104">Before you can enable automatic archive validation, you must set up a secondary database server, also called a validation server.</span></span> <span data-ttu-id="d1bc1-105">由于存档进程是一个简单备份，就可以在磁盘上存储的实际图像可能会损坏由于硬件问题。</span><span class="sxs-lookup"><span data-stu-id="d1bc1-105">Because the archiving process is a simple backup, it is possible that the actual image stored on the disk can be corrupted due to a hardware issue.</span></span>  
  
 <span data-ttu-id="d1bc1-106">使用存档验证功能，可以确保存档 （备份） 成功并且可以进行还原。</span><span class="sxs-lookup"><span data-stu-id="d1bc1-106">Using the archive validation feature, you can ensure the archive (backup) was successful and can be restored.</span></span> <span data-ttu-id="d1bc1-107">创建存档后，通知验证服务器已创建一个新的存档。</span><span class="sxs-lookup"><span data-stu-id="d1bc1-107">After an archive is created, the validation server is notified that a new archive has been created.</span></span> <span data-ttu-id="d1bc1-108">验证服务器尝试还原该存档。</span><span class="sxs-lookup"><span data-stu-id="d1bc1-108">The validation server attempts to restore the archive.</span></span> <span data-ttu-id="d1bc1-109">验证服务器必须是另一个实例的[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]不同于在其中运行作业。</span><span class="sxs-lookup"><span data-stu-id="d1bc1-109">A validation server must be another instance of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] different from the one in which the job is running.</span></span> <span data-ttu-id="d1bc1-110">版本[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]的验证服务器必须与相同的版本[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]用来承载数据库。</span><span class="sxs-lookup"><span data-stu-id="d1bc1-110">The version of [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] on the validation server must be the same version as the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] used to host the databases.</span></span>  
  
 <span data-ttu-id="d1bc1-111">如果还原成功，则验证服务器会此信息发送回 BizTalk 跟踪 (BizTalkDTADb) 数据库。</span><span class="sxs-lookup"><span data-stu-id="d1bc1-111">If the restore is successful, the validation server communicates this information back to the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="d1bc1-112">成功还原完成之前，清除作业将不会清除任何更多的数据。</span><span class="sxs-lookup"><span data-stu-id="d1bc1-112">Until a successful restore is completed, the purge job will not purge any more data.</span></span>  
  
 <span data-ttu-id="d1bc1-113">如果还原不成功，则验证服务器会此信息发送回 BizTalk 跟踪数据库。</span><span class="sxs-lookup"><span data-stu-id="d1bc1-113">If the restore is not successful, the validation server communicates this information back to the BizTalk Tracking database.</span></span> <span data-ttu-id="d1bc1-114">清除作业创建另一个存档并等待新存档的验证。</span><span class="sxs-lookup"><span data-stu-id="d1bc1-114">The purge job creates another archive and awaits validation of the new archive.</span></span> <span data-ttu-id="d1bc1-115">这可以防止存档损坏而导致丢失跟踪数据的可能性。</span><span class="sxs-lookup"><span data-stu-id="d1bc1-115">This prevents the possibility of a corrupted archive causing you to lose tracking data.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d1bc1-116">先决条件</span><span class="sxs-lookup"><span data-stu-id="d1bc1-116">Prerequisites</span></span>  
 <span data-ttu-id="d1bc1-117">您必须是的成员的帐户登录[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]sysadmin 固定的服务器角色才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="d1bc1-117">You must be logged on with an account that is a member of the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-enable-automatic-archive-validation"></a><span data-ttu-id="d1bc1-118">若要启用自动存档验证</span><span class="sxs-lookup"><span data-stu-id="d1bc1-118">To enable automatic archive validation</span></span>  
  
1. <span data-ttu-id="d1bc1-119">在验证服务器上，单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 SP2**，然后单击**SQL Server Management Studio**.</span><span class="sxs-lookup"><span data-stu-id="d1bc1-119">On the validation server, click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 SP2**, and then click **SQL Server Management Studio**.</span></span>  
  
2. <span data-ttu-id="d1bc1-120">在中**连接到服务器**对话框框中，指定的名称[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]其中您可以通过执行测试还原过程中，验证存档，然后单击**Connect**连接到相应的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="d1bc1-120">In the **Connect to Server** dialog box, specify the name of the [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] where you can validate the archive by performing a test of the restore process, and then click **Connect** to connect to the appropriate SQL Server.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="d1bc1-121">此服务器不应为另一个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库服务器，如验证存档时会降低系统性能。</span><span class="sxs-lookup"><span data-stu-id="d1bc1-121">This server should not be another [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] database server as it reduces system performance when validating the archive.</span></span>  
  
3. <span data-ttu-id="d1bc1-122">在中**Microsoft SQL Server Management Studio**，单击**文件**，单击**打开**，然后单击**文件**。</span><span class="sxs-lookup"><span data-stu-id="d1bc1-122">In **Microsoft SQL Server Management Studio**, click **File**, click **Open**, and then click **File**.</span></span>  
  
4. <span data-ttu-id="d1bc1-123">在中**打开的文件**对话框中，浏览到以下 SQL 脚本：</span><span class="sxs-lookup"><span data-stu-id="d1bc1-123">In the **Open File** dialog box, browse to the following SQL script:</span></span>  
  
   ```  
   %SystemDrive%\Program Files\Microsoft BizTalk Server <version>\Schema\BTS_Tracking_ValidateArchive.sql  
   ```  
  
   > [!NOTE]
   >  <span data-ttu-id="d1bc1-124">可能需要将该脚本从运行的计算机复制[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到验证服务器。</span><span class="sxs-lookup"><span data-stu-id="d1bc1-124">You might need to copy the script from the computer running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to the validation server.</span></span>  
  
5. <span data-ttu-id="d1bc1-125">单击**查询**菜单，并单击**Execute**。</span><span class="sxs-lookup"><span data-stu-id="d1bc1-125">Click the **Query** menu, and then click **Execute**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="d1bc1-126">只有存档 BizTalk 跟踪 (BizTalkDTADb) 数据库到其中的文件夹是网络共享时，BTS_Tracking_ValidateArchive.sql 脚本才能正常工作。</span><span class="sxs-lookup"><span data-stu-id="d1bc1-126">The BTS_Tracking_ValidateArchive.sql script only works if the folder where you are archiving your BizTalk Tracking (BizTalkDTADb) database is a network share.</span></span>  
  
    <span data-ttu-id="d1bc1-127">BTS_Tracking_ValidateArchive.sql 脚本将创建名为 ValidateArchive 的 SQL Server 代理作业。</span><span class="sxs-lookup"><span data-stu-id="d1bc1-127">The BTS_Tracking_ValidateArchive.sql script creates a SQL Server Agent job called ValidateArchive.</span></span>  
  
6. <span data-ttu-id="d1bc1-128">存档和清除进程可能会访问和/或更新其他的 SQL Server 中的数据库，因此必须设置所涉及的 SQL Server 实例之间的链接服务器。</span><span class="sxs-lookup"><span data-stu-id="d1bc1-128">The archiving and purging process potentially accesses and/or updates databases in different SQL Servers, so you must set up linked servers between the involved SQL Server instances.</span></span> <span data-ttu-id="d1bc1-129">在中**SQL Server Management Studio**，双击**Server 对象**，右键单击**链接服务器**，然后单击**新建链接服务器**.</span><span class="sxs-lookup"><span data-stu-id="d1bc1-129">In **SQL Server Management Studio**, double-click **Server Objects**, right-click **Linked Servers**, and then click **New Linked Server**.</span></span>  
  
    <span data-ttu-id="d1bc1-130">必须设置之间的链接服务器：</span><span class="sxs-lookup"><span data-stu-id="d1bc1-130">You must set up linked server between:</span></span>  
  
   -   <span data-ttu-id="d1bc1-131">每个 BizTalk MessageBox (BizTalkMsgBoxDb) 数据库和 BizTalk 跟踪 (BizTalkDTADb) 数据库，如果它们驻留在不同服务器上。</span><span class="sxs-lookup"><span data-stu-id="d1bc1-131">Each of your BizTalk MessageBox (BizTalkMsgBoxDb) databases and the BizTalk Tracking (BizTalkDTADb) database if they reside on different servers.</span></span>  
  
   -   <span data-ttu-id="d1bc1-132">BizTalk 跟踪 (BizTalkDTADb) 数据库和用于存档验证的验证服务器。</span><span class="sxs-lookup"><span data-stu-id="d1bc1-132">The BizTalk Tracking (BizTalkDTADb) database and the validating server for archive validation.</span></span>  
  
   -   <span data-ttu-id="d1bc1-133">承载 BizTalk MessageBox (BizTalkMsgBoxDb) 数据库的计算机上的 SQL Server 代理服务帐户必须在链接服务器上具有 BizTalk 跟踪 (BizTalkDTADb) 数据库的 db_datareader 和 db_datawriter 权限。</span><span class="sxs-lookup"><span data-stu-id="d1bc1-133">The service accounts for the SQL Server Agent on the computer hosting the BizTalk MessageBox (BizTalkMsgBoxDb) database must have the db_datareader and db_datawriter permissions for the BizTalk Tracking (BizTalkDTADb) database on the linked server.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="d1bc1-134">用于运行作业的帐户应具有两个数据库上的数据库操作员 (DBO) 权限。</span><span class="sxs-lookup"><span data-stu-id="d1bc1-134">The account used for running the job should have Database Operator (DBO) privileges on both the databases.</span></span>  
  
7. <span data-ttu-id="d1bc1-135">在中**新建链接服务器**对话框中，在**常规**页上，在**链接服务器**，输入你想要链接到的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="d1bc1-135">In the **New Linked Server** dialog box, on the **General** page, in **Linked server**, enter the name of the server you want to link to.</span></span>  
  
    <span data-ttu-id="d1bc1-136">例如，托管 BizTalk MessageBox (BizTalkMsgBoxDb) 数据库、 BizTalk 跟踪 (BizTalkDTADb) 数据库或验证服务器的服务器。</span><span class="sxs-lookup"><span data-stu-id="d1bc1-136">For example, the server hosting the BizTalk MessageBox (BizTalkMsgBoxDb) database, BizTalk Tracking (BizTalkDTADb) database, or the validation server.</span></span>  
  
8. <span data-ttu-id="d1bc1-137">下**服务器类型**，单击**SQL Server**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d1bc1-137">Under **Server type**, click **SQL Server**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="d1bc1-138">在中**Microsoft SQL Server Management Studio**，双击**SQL Server 代理**，然后单击**作业**。</span><span class="sxs-lookup"><span data-stu-id="d1bc1-138">In **Microsoft SQL Server Management Studio**, double-click **SQL Server Agent**, and then click **Jobs**.</span></span>  
  
10. <span data-ttu-id="d1bc1-139">在中**对象资源管理器详细信息**窗格中，右键单击**ValidateArchive**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="d1bc1-139">In the **Object Explorer Details** pane, right-click **ValidateArchive**, and then click **Properties**.</span></span>  
  
11. <span data-ttu-id="d1bc1-140">在中**作业属性-ValidateArchive**对话框中的**选择页**，单击**步骤**。</span><span class="sxs-lookup"><span data-stu-id="d1bc1-140">In the **Job Properties - ValidateArchive** dialog box, under **Select a page**, click **Steps**.</span></span>  
  
12. <span data-ttu-id="d1bc1-141">在中**作业步骤列表**，单击**验证**，然后单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="d1bc1-141">In the **Job step list**, click **validate**, and then click **Edit**.</span></span>  
  
13. <span data-ttu-id="d1bc1-142">上**常规**页上，在**命令**框中的，在命令中， **exec dtasp_ValidateArchive null，null**，替换为 null，null 与托管 BizTalk server 的名称跟踪数据库，括在单引号后, 跟用引号引起来，BizTalk 跟踪数据库的名称，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d1bc1-142">On the **General** page, in the **Command** box, in the command, **exec dtasp_ValidateArchive null, null**, replace null, null with the name of the server hosting the BizTalk Tracking database, surrounded by single quotes, followed by the name of the BizTalk Tracking database, surrounded by quotes, and then click **OK**.</span></span> <span data-ttu-id="d1bc1-143">例如：</span><span class="sxs-lookup"><span data-stu-id="d1bc1-143">For example:</span></span>  
  
     <span data-ttu-id="d1bc1-144">**exec dtasp_ValidateArchive '** *\<TrackingServerName\>* **', '** *\<TrackingDatabaseName\>* **'**</span><span class="sxs-lookup"><span data-stu-id="d1bc1-144">**exec dtasp_ValidateArchive '** *\<TrackingServerName\>* **', '** *\<TrackingDatabaseName\>* **'**</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d1bc1-145">ValidateArchive 作业没有计划并且不应为其配置计划。</span><span class="sxs-lookup"><span data-stu-id="d1bc1-145">The ValidateArchive job does not have a schedule and you should not configure a schedule for it.</span></span> <span data-ttu-id="d1bc1-146">相反，DTA 清除和存档 (BizTalkDTADb) 作业就会自动创建存档时此作业。</span><span class="sxs-lookup"><span data-stu-id="d1bc1-146">Instead, the DTA Purge and Archive (BizTalkDTADb) job starts this job automatically when an archive is created.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1bc1-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="d1bc1-147">See Also</span></span>  
 [<span data-ttu-id="d1bc1-148">存档和清除 BizTalk 跟踪数据库</span><span class="sxs-lookup"><span data-stu-id="d1bc1-148">Archiving and Purging the BizTalk Tracking Database</span></span>](../core/archiving-and-purging-the-biztalk-tracking-database.md)