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
ms.openlocfilehash: ff5caa9120be64e919ab4b6050f8df0c62fa33a6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010606"
---
# <a name="how-to-move-the-bam-primary-import-database"></a><span data-ttu-id="3e397-102">如何移动 BAM 主导入数据库</span><span class="sxs-lookup"><span data-stu-id="3e397-102">How to Move the BAM Primary Import Database</span></span>
<span data-ttu-id="3e397-103">您可以使用此过程将 BAM 主导入数据库移至其他服务器。</span><span class="sxs-lookup"><span data-stu-id="3e397-103">You can use this procedure to move the BAM Primary Import database to another server.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3e397-104">必要條件</span><span class="sxs-lookup"><span data-stu-id="3e397-104">Prerequisites</span></span>  
 <span data-ttu-id="3e397-105">若要执行此过程，必须以 SQL Server sysadmin 固定服务器角色成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="3e397-105">You must be logged on with an account that is a member of the SQL Server sysadmin fixed server role to perform this procedure.</span></span>  
  
### <a name="to-move-the-bam-primary-import-database"></a><span data-ttu-id="3e397-106">移动 BAM 主导入数据库</span><span class="sxs-lookup"><span data-stu-id="3e397-106">To move the BAM Primary Import database</span></span>  
  
1. <span data-ttu-id="3e397-107">停止所有 BizTalk Server 服务。</span><span class="sxs-lookup"><span data-stu-id="3e397-107">Stop all BizTalk Server services.</span></span> <span data-ttu-id="3e397-108">有关详细信息，请参阅[如何启动、 停止、 暂停、 继续或重新启动 BizTalk Server Services](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md)。</span><span class="sxs-lookup"><span data-stu-id="3e397-108">For more information, see [How to Start, Stop, Pause, Resume, or Restart BizTalk Server Services](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md).</span></span>  
  
2. <span data-ttu-id="3e397-109">停止 IIS 服务。</span><span class="sxs-lookup"><span data-stu-id="3e397-109">Stop the IIS service.</span></span>  
  
3. <span data-ttu-id="3e397-110">停止 BAM 警报 Notification Service：</span><span class="sxs-lookup"><span data-stu-id="3e397-110">Stop the BAM Alerts Notification Service:</span></span>  
  
   1.  <span data-ttu-id="3e397-111">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3e397-111">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
   2.  <span data-ttu-id="3e397-112">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="3e397-112">At the command prompt, type:</span></span>  
  
       ```  
       Net stop NS$BamAlerts  
       ```  
  
4. <span data-ttu-id="3e397-113">按照 SQL Server 联机从书中的说明在旧服务器上备份 BAM 主导入数据库。</span><span class="sxs-lookup"><span data-stu-id="3e397-113">Follow the instructions in SQL Server Books Online to back up the BAM Primary Import database on the old server.</span></span>  
  
5. <span data-ttu-id="3e397-114">将 BAM 主导入数据库复制到新 SQL Server 中。</span><span class="sxs-lookup"><span data-stu-id="3e397-114">Copy the BAM Primary Import database to the new SQL Server.</span></span>  
  
6. <span data-ttu-id="3e397-115">按照 SQL Server 联机从书中的说明在新服务器上还原 BAM 主导入数据库。</span><span class="sxs-lookup"><span data-stu-id="3e397-115">Follow the instructions in SQL Server Books Online to restore the BAM Primary Import database on the new server.</span></span>  
  
7. <span data-ttu-id="3e397-116">在运行 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的计算机中，浏览至以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="3e397-116">On a computer running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], browse to the following folder:</span></span>  
  
    [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="3e397-117">Schema\Restore</span><span class="sxs-lookup"><span data-stu-id="3e397-117">Schema\Restore</span></span>  
  
8. <span data-ttu-id="3e397-118">右键单击**SampleUpdateInfo.xml**，然后单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="3e397-118">Right-click **SampleUpdateInfo.xml**, and then click **Edit**.</span></span>  
  
9. <span data-ttu-id="3e397-119">在该文件的主导入数据库部分，将为**SourceServer**的源系统，然后替换名称 **"DestinationServer"** 与目标系统的名称。</span><span class="sxs-lookup"><span data-stu-id="3e397-119">In the Primary Import Database section of the file, replace **"SourceServer"** with the name of the source system, and then replace **"DestinationServer"** with the name of the destination system.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="3e397-120">用引号将源系统和目标系统的名称括起来。</span><span class="sxs-lookup"><span data-stu-id="3e397-120">Include the quotation marks around the name of the source and destination systems.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3e397-121">如果对任何 BizTalk Server 数据库进行了重命名，则必须也相应地更新这些数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="3e397-121">If you renamed any of the BizTalk Server databases, you must also update the database names as appropriate.</span></span>  
  
10. <span data-ttu-id="3e397-122">取消 xml 文件中以下行的注释：</span><span class="sxs-lookup"><span data-stu-id="3e397-122">Uncomment the following lines in the xml file:</span></span>  
  
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
  
11. <span data-ttu-id="3e397-123">编辑完此文件后，请进行保存然后退出。</span><span class="sxs-lookup"><span data-stu-id="3e397-123">When you are finished editing the file, save it and exit.</span></span>  
  
12. <span data-ttu-id="3e397-124">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3e397-124">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
13. <span data-ttu-id="3e397-125">在命令提示符下，导航到以下目录：</span><span class="sxs-lookup"><span data-stu-id="3e397-125">At the command prompt, navigate to the following directory:</span></span>  
  
     [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="3e397-126">Schema\Restore</span><span class="sxs-lookup"><span data-stu-id="3e397-126">Schema\Restore</span></span>  
  
14. <span data-ttu-id="3e397-127">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="3e397-127">At the command prompt, type:</span></span>  
  
     <span data-ttu-id="3e397-128">**cscript UpdateDatabase.vbs SampleUpdateInfo.xml**</span><span class="sxs-lookup"><span data-stu-id="3e397-128">**cscript UpdateDatabase.vbs SampleUpdateInfo.xml**</span></span>  
  
15. <span data-ttu-id="3e397-129">更新对 BAM 主导入数据库中所有 BAM 实时数据 Microsoft Excel 文件的引用。</span><span class="sxs-lookup"><span data-stu-id="3e397-129">Update the reference to BAM Primary Import Database in all BAM Livedata Microsoft Excel files.</span></span> <span data-ttu-id="3e397-130">对于每个文件：</span><span class="sxs-lookup"><span data-stu-id="3e397-130">For each file:</span></span>  
  
    1.  <span data-ttu-id="3e397-131">打开 Excel 实时数据文件。</span><span class="sxs-lookup"><span data-stu-id="3e397-131">Open the Excel live data file.</span></span> <span data-ttu-id="3e397-132">以 _LiveData.xls 结尾的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="3e397-132">The file name ends with _LiveData.xls.</span></span>  
  
    2.  <span data-ttu-id="3e397-133">上**BAM**菜单上，单击**BAM 数据库连接**。</span><span class="sxs-lookup"><span data-stu-id="3e397-133">On the **BAM** menu, click **BAM DB Connection**.</span></span>  
  
    3.  <span data-ttu-id="3e397-134">在中**选择 BAM 数据库**对话框中，输入 SQL Server 和 BAMPrimaryImport 数据库，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3e397-134">In the **Select BAM Database** dialog box, enter the SQL Server and BAMPrimaryImport database, and then click **OK**.</span></span>  
  
    4.  <span data-ttu-id="3e397-135">上**文件**菜单上，单击**关闭并返回到 Microsoft Excel**。</span><span class="sxs-lookup"><span data-stu-id="3e397-135">On the **File** menu, click **Close and Return to Microsoft Excel**.</span></span>  
  
    5.  <span data-ttu-id="3e397-136">在“文件”菜单上，单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="3e397-136">On the **File** menu, click **Save**.</span></span>  
  
16. <span data-ttu-id="3e397-137">按照以下步骤，更新所有 BAM 分析 DTS 包（带有“BAM_AN_”或“BAM_DM_”前缀）中的服务器名称和数据库名称：</span><span class="sxs-lookup"><span data-stu-id="3e397-137">Update the server and database names in all BAM analysis DTS packages, which are prefixed with "BAM_AN_" or "BAM_DM_" by following these steps:</span></span>  
  
    1.  <span data-ttu-id="3e397-138">在 BAM 的宿主服务器上，打开 SQL Server 企业管理器。</span><span class="sxs-lookup"><span data-stu-id="3e397-138">On the server hosting BAM, open SQL Server Enterprise Manager.</span></span>  
  
    2.  <span data-ttu-id="3e397-139">打开**Data Transformation Services**文件夹。</span><span class="sxs-lookup"><span data-stu-id="3e397-139">Open the **Data Transformation Services** folder.</span></span>  
  
    3.  <span data-ttu-id="3e397-140">打开**本地包**文件夹，然后打开 DTS 包。</span><span class="sxs-lookup"><span data-stu-id="3e397-140">Open the **Local Packages** folder, and then open the DTS packages.</span></span>  
  
    4.  <span data-ttu-id="3e397-141">上**包**菜单上，单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="3e397-141">On the **Package** menu, click **Properties**.</span></span>  
  
    5.  <span data-ttu-id="3e397-142">上**全局变量**选项卡上，更新主导入服务器和数据库的值。</span><span class="sxs-lookup"><span data-stu-id="3e397-142">On the **Global Variables** tab, update the values for the primary import server and database.</span></span>  
  
    6.  <span data-ttu-id="3e397-143">更改以下行，以匹配新的服务器和数据库：</span><span class="sxs-lookup"><span data-stu-id="3e397-143">Change the following lines to match your new server and database:</span></span>  
  
         <span data-ttu-id="3e397-144">PrimaryImportServer ="*\<ServerName\>*"</span><span class="sxs-lookup"><span data-stu-id="3e397-144">PrimaryImportServer= "*\<ServerName\>*"</span></span>  
  
         <span data-ttu-id="3e397-145">PrimaryImportDatabase ="*\<DatabaseName\>*"</span><span class="sxs-lookup"><span data-stu-id="3e397-145">PrimaryImportDatabase = "*\<DatabaseName\>*"</span></span>  
  
17. <span data-ttu-id="3e397-146">启动所有 BizTalk Server 服务。</span><span class="sxs-lookup"><span data-stu-id="3e397-146">Start all BizTalk Server services.</span></span> <span data-ttu-id="3e397-147">有关详细信息，请参阅[如何启动、 停止、 暂停、 继续或重新启动 BizTalk Server Services](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md)。</span><span class="sxs-lookup"><span data-stu-id="3e397-147">For more information, see [How to Start, Stop, Pause, Resume, or Restart BizTalk Server Services](../core/how-to-start-stop-pause-resume-or-restart-biztalk-server-services.md).</span></span>  
  
18. <span data-ttu-id="3e397-148">启动 IIS 服务。</span><span class="sxs-lookup"><span data-stu-id="3e397-148">Start the IIS service.</span></span>  
  
19. <span data-ttu-id="3e397-149">启动 BAM 警报 Notification Service：</span><span class="sxs-lookup"><span data-stu-id="3e397-149">Start the BAM Alerts Notification Service:</span></span>  
  
    1.  <span data-ttu-id="3e397-150">单击**启动**，单击**运行**，类型**cmd**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3e397-150">Click **Start**, click **Run**, type **cmd**, and then click **OK**.</span></span>  
  
    2.  <span data-ttu-id="3e397-151">在命令提示符下，键入：</span><span class="sxs-lookup"><span data-stu-id="3e397-151">At the command prompt, type:</span></span>  
  
        ```  
        Net start NS$BamAlerts  
        ```  
  
## <a name="see-also"></a><span data-ttu-id="3e397-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="3e397-152">See Also</span></span>  
 [<span data-ttu-id="3e397-153">移动 BizTalk Server 数据库</span><span class="sxs-lookup"><span data-stu-id="3e397-153">Moving BizTalk Server Databases</span></span>](../core/moving-biztalk-server-databases.md)