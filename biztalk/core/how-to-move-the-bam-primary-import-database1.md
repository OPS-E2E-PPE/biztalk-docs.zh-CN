---
title: 如何移动 BAM 主导入数据库 1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migrating, Primary Import database [BAM]
- Primary Import database [BAM], migrating
ms.assetid: fab13fea-5c35-4a9f-977d-cc45545c54b2
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5035be00b043b7ea35c76fcecabd50663ef91f26
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65335860"
---
# <a name="how-to-move-the-bam-primary-import-database"></a><span data-ttu-id="7df75-102">如何移动 BAM 主导入数据库</span><span class="sxs-lookup"><span data-stu-id="7df75-102">How to Move the BAM Primary Import Database</span></span>
<span data-ttu-id="7df75-103">可以使用此过程将 BAM 主导入数据库移到另一台服务器。</span><span class="sxs-lookup"><span data-stu-id="7df75-103">You can use this procedure to move the BAM Primary Import database to another server.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7df75-104">先决条件</span><span class="sxs-lookup"><span data-stu-id="7df75-104">Prerequisites</span></span>  
 <span data-ttu-id="7df75-105">您必须是 SQL Server sysadmin 固定服务器角色的成员才能执行此过程的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="7df75-105">You must be logged on with an account that is a member of the SQL Server sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-move-the-bam-primary-import-database"></a><span data-ttu-id="7df75-106">移动 BAM 主导入数据库</span><span class="sxs-lookup"><span data-stu-id="7df75-106">To move the BAM Primary Import database</span></span>  
  
1. <span data-ttu-id="7df75-107">停止所有 BizTalk Server 服务。</span><span class="sxs-lookup"><span data-stu-id="7df75-107">Stop all BizTalk Server services.</span></span> <span data-ttu-id="7df75-108">有关详细信息，请参阅[如何启动、 停止、 暂停、 继续或重新启动 BizTalk Server Services](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md)。</span><span class="sxs-lookup"><span data-stu-id="7df75-108">For more information, see [How to Start, Stop, Pause, Resume, or Restart BizTalk Server Services](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md).</span></span>  
  
2. <span data-ttu-id="7df75-109">停止 IIS 服务。</span><span class="sxs-lookup"><span data-stu-id="7df75-109">Stop the IIS service.</span></span>  
  
3. <span data-ttu-id="7df75-110">停止 BAM 警报 Notification Service:</span><span class="sxs-lookup"><span data-stu-id="7df75-110">Stop the BAM Alerts Notification Service:</span></span>  
  
   1.  <span data-ttu-id="7df75-111">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7df75-111">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
   2.  <span data-ttu-id="7df75-112">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="7df75-112">At the command prompt, type:</span></span>  
  
       ```  
       Net stop NS$BamAlerts  
       ```  
  
4. <span data-ttu-id="7df75-113">按照 SQL Server 联机丛书中的说明在旧服务器上备份 BAM 主导入数据库。</span><span class="sxs-lookup"><span data-stu-id="7df75-113">Follow the instructions in SQL Server Books Online to back up the BAM Primary Import database on the old server.</span></span>  
  
5. <span data-ttu-id="7df75-114">将 BAM 主导入数据库复制到新的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="7df75-114">Copy the BAM Primary Import database to the new SQL Server.</span></span>  
  
6. <span data-ttu-id="7df75-115">按照 SQL Server 联机丛书中的说明来还原新服务器上的 BAM 主导入数据库。</span><span class="sxs-lookup"><span data-stu-id="7df75-115">Follow the instructions in SQL Server Books Online to restore the BAM Primary Import database on the new server.</span></span>  
  
7. <span data-ttu-id="7df75-116">运行的计算机上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，浏览到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="7df75-116">On a computer running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], browse to the following folder:</span></span>  
  
    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="7df75-117">Schema\Restore</span><span class="sxs-lookup"><span data-stu-id="7df75-117">Schema\Restore</span></span>  
  
8. <span data-ttu-id="7df75-118">右键单击**SampleUpdateInfo.xml**，然后单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="7df75-118">Right-click **SampleUpdateInfo.xml**, and then click **Edit**.</span></span>  
  
9. <span data-ttu-id="7df75-119">在该文件的主导入数据库部分，将为**SourceServer**的源系统，然后替换名称 **"DestinationServer"** 与目标系统的名称。</span><span class="sxs-lookup"><span data-stu-id="7df75-119">In the Primary Import Database section of the file, replace **"SourceServer"** with the name of the source system, and then replace **"DestinationServer"** with the name of the destination system.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="7df75-120">包括源和目标系统的名称周围的引号。</span><span class="sxs-lookup"><span data-stu-id="7df75-120">Include the quotation marks around the name of the source and destination systems.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7df75-121">如果您重命名任何 BizTalk Server 数据库，还必须更新相应数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="7df75-121">If you renamed any of the BizTalk Server databases, you must also update the database names as appropriate.</span></span>  
  
10. <span data-ttu-id="7df75-122">取消注释的 xml 文件中的以下行：</span><span class="sxs-lookup"><span data-stu-id="7df75-122">Uncomment the following lines in the xml file:</span></span>  
  
    ```  
    - <UpdateConfiguration>  
      <MessageBoxDB oldDBName="BizTalkMsgboxDb" oldDBServer="Server01" newDBName="BizTalkMsgboxDb" newDBServer="Server01" IsMaster="1" />   
      <TrackingDB oldDBName="BizTalkDTADb" oldDBServer="Server01" newDBName="BizTalkDTADb" newDBServer="Server01" />   
      <ManagementDB oldDBName="BizTalkMgmtDb" oldDBServer="Server01" newDBName="BizTalkMgmtDb" newDBServer="Server01" />   
    - <BAM>  
    - <DeploymentUnit Name="OldPrimaryImportDatabase">  
      <Property Name="ServerName">Server01</Property>   
      <Property Name="DatabaseName">BAMPrimaryImport</Property>   
      </DeploymentUnit>  
    - <DeploymentUnit Name="PrimaryImportDatabase">  
      <Property Name="ServerName">Server02</Property>   
      <Property Name="DatabaseName">BAMPrimaryImport</Property>   
      </DeploymentUnit>  
    - <DeploymentUnit Name="ArchivingDatabase">  
      <Property Name="ServerName">Server01</Property>   
      <Property Name="DatabaseName">BAMArchive</Property>   
      </DeploymentUnit>  
    - <DeploymentUnit Name="AnalysisDatabase">  
      <Property Name="ServerName">Server01</Property>   
      <Property Name="DatabaseName">BAMAnalysis</Property>   
      </DeploymentUnit>  
    - <DeploymentUnit Name="StarSchemaDatabase">  
      <Property Name="ServerName">Server01</Property>   
      <Property Name="DatabaseName">BAMStarSchema</Property>   
      </DeploymentUnit>  
    - <DeploymentUnit Name="Alert">  
      <Property Name="DBServer">Server01</Property>   
      <Property Name="InstanceDatabaseName">BAMAlerts</Property>   
      </DeploymentUnit>  
      </BAM>  
    - <OtherDatabases>  
      <Database Name="SSO" oldDBName="SSODB" oldDBServer="Server01" newDBName="SSODB" newDBServer="Server01" />   
      </OtherDatabases>  
      </UpdateConfiguration>  
    ```  
  
11. <span data-ttu-id="7df75-123">在完成编辑文件，请将其保存并退出。</span><span class="sxs-lookup"><span data-stu-id="7df75-123">When you are finished editing the file, save it and exit.</span></span>  
  
12. <span data-ttu-id="7df75-124">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7df75-124">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
13. <span data-ttu-id="7df75-125">在命令提示符处，导航到以下目录：</span><span class="sxs-lookup"><span data-stu-id="7df75-125">At the command prompt, navigate to the following directory:</span></span>  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="7df75-126">Schema\Restore</span><span class="sxs-lookup"><span data-stu-id="7df75-126">Schema\Restore</span></span>  
  
14. <span data-ttu-id="7df75-127">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="7df75-127">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="7df75-128">**cscript UpdateDatabase.vbs SampleUpdateInfo.xml**</span><span class="sxs-lookup"><span data-stu-id="7df75-128">**cscript UpdateDatabase.vbs SampleUpdateInfo.xml**</span></span>  
  
15. <span data-ttu-id="7df75-129">更新对 BAM 主导入数据库中所有 BAM 实时数据 Microsoft Excel 文件的引用。</span><span class="sxs-lookup"><span data-stu-id="7df75-129">Update the reference to BAM Primary Import Database in all BAM Livedata Microsoft Excel files.</span></span> <span data-ttu-id="7df75-130">对于每个文件：</span><span class="sxs-lookup"><span data-stu-id="7df75-130">For each file:</span></span>  
  
    1.  <span data-ttu-id="7df75-131">打开 Excel 实时数据文件。</span><span class="sxs-lookup"><span data-stu-id="7df75-131">Open the Excel live data file.</span></span> <span data-ttu-id="7df75-132">以 _LiveData.xls 结尾的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="7df75-132">The file name ends with _LiveData.xls.</span></span>  
  
    2.  <span data-ttu-id="7df75-133">上**BAM**菜单上，单击**BAM 数据库连接**。</span><span class="sxs-lookup"><span data-stu-id="7df75-133">On the **BAM** menu, click **BAM DB Connection**.</span></span>  
  
    3.  <span data-ttu-id="7df75-134">在中**选择 BAM 数据库**对话框中，输入 SQL Server 和 BAMPrimaryImport 数据库，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7df75-134">In the **Select BAM Database** dialog box, enter the SQL Server and BAMPrimaryImport database, and then click **OK**.</span></span>  
  
    4.  <span data-ttu-id="7df75-135">上**文件**菜单上，单击**关闭并返回到 Microsoft Excel**。</span><span class="sxs-lookup"><span data-stu-id="7df75-135">On the **File** menu, click **Close and Return to Microsoft Excel**.</span></span>  
  
    5.  <span data-ttu-id="7df75-136">在“文件”菜单上，单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="7df75-136">On the **File** menu, click **Save**.</span></span>  
  
16. <span data-ttu-id="7df75-137">更新所有 BAM 分析 DTS 包中，通过执行以下步骤带有"BAM_AN_"或"BAM_DM_"前缀的服务器和数据库名称：</span><span class="sxs-lookup"><span data-stu-id="7df75-137">Update the server and database names in all BAM analysis DTS packages, which are prefixed with "BAM_AN_" or "BAM_DM_" by following these steps:</span></span>  
  
    1.  <span data-ttu-id="7df75-138">在 BAM 的宿主服务器上，打开 SQL Server 企业管理器。</span><span class="sxs-lookup"><span data-stu-id="7df75-138">On the server hosting BAM, open SQL Server Enterprise Manager.</span></span>  
  
    2.  <span data-ttu-id="7df75-139">打开**Data Transformation Services**文件夹。</span><span class="sxs-lookup"><span data-stu-id="7df75-139">Open the **Data Transformation Services** folder.</span></span>  
  
    3.  <span data-ttu-id="7df75-140">打开**本地包**文件夹，然后打开 DTS 包。</span><span class="sxs-lookup"><span data-stu-id="7df75-140">Open the **Local Packages** folder, and then open the DTS packages.</span></span>  
  
    4.  <span data-ttu-id="7df75-141">上**包**菜单上，单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="7df75-141">On the **Package** menu, click **Properties**.</span></span>  
  
    5.  <span data-ttu-id="7df75-142">上**全局变量**选项卡上，更新主导入服务器和数据库的值。</span><span class="sxs-lookup"><span data-stu-id="7df75-142">On the **Global Variables** tab, update the values for the primary import server and database.</span></span>  
  
    6.  <span data-ttu-id="7df75-143">更改以下行，以匹配新的服务器和数据库：</span><span class="sxs-lookup"><span data-stu-id="7df75-143">Change the following lines to match your new server and database:</span></span>  
  
         <span data-ttu-id="7df75-144">PrimaryImportServer= "*\<ServerName\>*"</span><span class="sxs-lookup"><span data-stu-id="7df75-144">PrimaryImportServer= "*\<ServerName\>*"</span></span>  
  
         <span data-ttu-id="7df75-145">PrimaryImportDatabase = "*\<DatabaseName\>*"</span><span class="sxs-lookup"><span data-stu-id="7df75-145">PrimaryImportDatabase = "*\<DatabaseName\>*"</span></span>  
  
17. <span data-ttu-id="7df75-146">启动所有 BizTalk Server 服务。</span><span class="sxs-lookup"><span data-stu-id="7df75-146">Start all BizTalk Server services.</span></span> <span data-ttu-id="7df75-147">有关详细信息，请参阅[如何启动、 停止、 暂停、 继续或重新启动 BizTalk Server Services](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md)。</span><span class="sxs-lookup"><span data-stu-id="7df75-147">For more information, see [How to Start, Stop, Pause, Resume, or Restart BizTalk Server Services](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md).</span></span>  
  
18. <span data-ttu-id="7df75-148">启动 IIS 服务。</span><span class="sxs-lookup"><span data-stu-id="7df75-148">Start the IIS service.</span></span>  
  
19. <span data-ttu-id="7df75-149">启动 BAM 警报 Notification Service:</span><span class="sxs-lookup"><span data-stu-id="7df75-149">Start the BAM Alerts Notification Service:</span></span>  
  
    1.  <span data-ttu-id="7df75-150">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="7df75-150">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
    2.  <span data-ttu-id="7df75-151">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="7df75-151">At the command prompt, type:</span></span>  
  
        ```  
        Net start NS$BamAlerts  
        ```  
  
## <a name="see-also"></a><span data-ttu-id="7df75-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="7df75-152">See Also</span></span>  
 [<span data-ttu-id="7df75-153">移动 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="7df75-153">Moving BizTalk Server Databases</span></span>](../core/moving-biztalk-server-databases.md)