---
title: 如何更新对 BAM 存档数据库名称的引用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Archive database [BAM], restoring
- restoring, BAM
- restoring [BAM], Archive database
- restoring [BAM], updating references
- Archive database [BAM], updating references
- BAM, restoring
ms.assetid: a0b8543e-6fc1-412e-b74e-683352d9c49e
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3fcba19a3852a70c402276fed1ca56ea1b8f0c4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333716"
---
# <a name="how-to-update-references-to-the-bam-archive-database-name"></a><span data-ttu-id="91b54-102">如何更新对 BAM 存档数据库名称的引用</span><span class="sxs-lookup"><span data-stu-id="91b54-102">How to Update References to the BAM Archive Database Name</span></span>
<span data-ttu-id="91b54-103">如果备份了 BAMArchive 数据库，在系统或数据发生故障时可以还原该备份并将其重命名。</span><span class="sxs-lookup"><span data-stu-id="91b54-103">If you backed up your BAMArchive databases, in the event of a system or data failure you can restore that backup and rename it.</span></span>  
  
 <span data-ttu-id="91b54-104">若要还原 BAMArchive 数据库，请执行中的步骤[如何还原您数据库](../core/how-to-restore-your-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="91b54-104">To restore the BAMArchive databases, perform the steps in [How to Restore Your Databases](../core/how-to-restore-your-databases.md).</span></span> <span data-ttu-id="91b54-105">此外，还必须执行下列常规步骤后, 跟介绍详细信息中的步骤的过程：</span><span class="sxs-lookup"><span data-stu-id="91b54-105">In addition, you must perform these general steps, which are followed by a procedure that describes the steps in detail:</span></span>  
  
-   <span data-ttu-id="91b54-106">使用新的服务器名称和数据库名称更新 BAM DTS 包。</span><span class="sxs-lookup"><span data-stu-id="91b54-106">Update the BAM DTS packages with the new server name and database name.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="91b54-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="91b54-107">Prerequisites</span></span>  
 <span data-ttu-id="91b54-108">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="91b54-108">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group to perform this procedure.</span></span>  
  
### <a name="to-update-references-to-the-bam-archive-database-name-sql-server-2008-r2sp1"></a><span data-ttu-id="91b54-109">若要更新对 BAM 存档数据库名称 (SQL Server 2008 R2/SP1) 的引用</span><span class="sxs-lookup"><span data-stu-id="91b54-109">To update references to the BAM Archive database name (SQL Server 2008 R2/SP1)</span></span>  
  
1.  <span data-ttu-id="91b54-110">停止任何 BAM 多维数据集更新和数据维护 DTS 包，或者阻止它们运行，直到 BAMArchive 数据库的还原。</span><span class="sxs-lookup"><span data-stu-id="91b54-110">Stop any BAM cube update and data maintenance DTS packages, or prevent them from running until you have restored the BAMArchive database.</span></span>  
  
2.  <span data-ttu-id="91b54-111">停止 BizTalk 应用程序服务 （其中包括 BAM 事件总线服务） 以便不会尝试导入数据库的更多的数据。</span><span class="sxs-lookup"><span data-stu-id="91b54-111">Stop the BizTalk Application service (which includes the BAM Event Bus service) so it does not try to import more data into the database.</span></span>  
  
    1.  <span data-ttu-id="91b54-112">单击**启动**，单击**运行**，然后键入**services.msc**。</span><span class="sxs-lookup"><span data-stu-id="91b54-112">Click **Start**, click **Run**, and then type **services.msc**.</span></span>  
  
    2.  <span data-ttu-id="91b54-113">右键单击**BizTalk 服务 BizTalk 组：BizTalkServerApplication**服务，然后单击**停止**。</span><span class="sxs-lookup"><span data-stu-id="91b54-113">Right-click the **BizTalk Service BizTalk Group: BizTalkServerApplication** service and then click **Stop**.</span></span>  
  
3.  <span data-ttu-id="91b54-114">单击**启动**，单击**程序**，单击**Microsoft SQL Server 2008 R2**，然后单击**SQL Server Business Intelligence Development Studio**.</span><span class="sxs-lookup"><span data-stu-id="91b54-114">Click **Start**, click **Programs**, click **Microsoft SQL Server 2008 R2**, and then click **SQL Server Business Intelligence Development Studio**.</span></span>  
  
4.  <span data-ttu-id="91b54-115">在 SQL Server Business Intelligence Development Studio，创建新项目。</span><span class="sxs-lookup"><span data-stu-id="91b54-115">In SQL Server Business Intelligence Development Studio, create a new project.</span></span> <span data-ttu-id="91b54-116">单击**文件**，单击**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="91b54-116">Click **File**, click **New**, and then click **Project**.</span></span>  
  
5.  <span data-ttu-id="91b54-117">在中**新的项目**对话框中**模板**，单击**Integration Services 项目**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="91b54-117">In the **New Project** dialog box, in **Templates**, click **Integration Services Project**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="91b54-118">在中**Integration Services 项目**对话框中**解决方案资源管理器**，右键单击**SSIS 包**，然后单击**添加现有包**.</span><span class="sxs-lookup"><span data-stu-id="91b54-118">In the **Integration Services Project** dialog box, in **Solution Explorer**, right-click **SSIS Packages**, and then click **Add Existing Package**.</span></span>  
  
7.  <span data-ttu-id="91b54-119">在中**添加现有包副本**对话框中**Server**下拉列表框中，选择包含 BAM_DM 包的服务器。</span><span class="sxs-lookup"><span data-stu-id="91b54-119">In the **Add Copy of Existing Package** dialog box, in the **Server** drop-down list box, select the server that contains the BAM_DM package.</span></span>  
  
8.  <span data-ttu-id="91b54-120">在中**包路径**，请单击省略号按钮。</span><span class="sxs-lookup"><span data-stu-id="91b54-120">In **Package Path**, click the ellipses button.</span></span>  
  
9. <span data-ttu-id="91b54-121">在中**SSIS 包**对话框框中，选择 BAM_DM 包，单击**确定**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="91b54-121">In the **SSIS Package** dialog box, select the BAM_DM package, click **OK**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="91b54-122">包现在列在解决方案资源管理器。</span><span class="sxs-lookup"><span data-stu-id="91b54-122">The package is now listed in Solution Explorer.</span></span>  
  
10. <span data-ttu-id="91b54-123">在中**解决方案资源管理器**，双击该 BAM_DM 包。</span><span class="sxs-lookup"><span data-stu-id="91b54-123">In **Solution Explorer**, double-click the BAM_DM package.</span></span> <span data-ttu-id="91b54-124">在中**连接管理器**，双击数据库编号 3(MSDB 数据库）。</span><span class="sxs-lookup"><span data-stu-id="91b54-124">In **Connection Managers**, double-click database number 3 (MSDB database).</span></span>  
  
11. <span data-ttu-id="91b54-125">在中**连接管理器**对话框中**服务器名称**框中，输入 MSDB 服务器的名称，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="91b54-125">In the **Connection Manager** dialog box, in the **Server name** box, enter the name of the MSDB server, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="91b54-126">单击**包资源管理器**选项卡上，双击**变量**文件夹，然后更新主导入服务器名称和主键的值导入数据库名称。</span><span class="sxs-lookup"><span data-stu-id="91b54-126">Click the **Package Explorer** tab, double-click the **Variables** folder, and then update the values for the primary import server name and primary import database name.</span></span>  
  
13. <span data-ttu-id="91b54-127">单击**文件**，然后单击**全部保存**。</span><span class="sxs-lookup"><span data-stu-id="91b54-127">Click **File**, and then click **Save All**.</span></span>  
  
14. <span data-ttu-id="91b54-128">在中**Microsoft SQL Server Management Studio**，单击**Connect**。</span><span class="sxs-lookup"><span data-stu-id="91b54-128">In **Microsoft SQL Server Management Studio**, click **Connect**.</span></span>  
  
15. <span data-ttu-id="91b54-129">单击**Integration Services**，双击**存储的包**，单击**MSDB**，右键单击该 BAM_DM 包，并单击**导入包**.</span><span class="sxs-lookup"><span data-stu-id="91b54-129">Click **Integration Services**, double-click **Stored Packages**, click **MSDB**, right-click the BAM_DM package, and then click **Import Package**.</span></span>  
  
16. <span data-ttu-id="91b54-130">在中**导入包**对话框中**包位置**，选择**文件系统**。</span><span class="sxs-lookup"><span data-stu-id="91b54-130">In the **Import Package** dialog box, in **Package location**, select **File System**.</span></span>  
  
17. <span data-ttu-id="91b54-131">在中**包路径**，导航到保存的项目，选择 BAM_DM\*.dtsx 文件，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="91b54-131">In **Package Path**, navigate to your saved project, select the BAM_DM\*.dtsx file, and then click **Open**.</span></span>  
  
18. <span data-ttu-id="91b54-132">在单击**包名称**框以自动填充此框。</span><span class="sxs-lookup"><span data-stu-id="91b54-132">Click inside the **Package Name** box to automatically populate the box.</span></span>  
  
19. <span data-ttu-id="91b54-133">单击**确定**，然后单击**是**覆盖。</span><span class="sxs-lookup"><span data-stu-id="91b54-133">Click **OK**, and then click **Yes** to overwrite.</span></span>  
  
20. <span data-ttu-id="91b54-134">重新启动 BizTalk 应用程序服务。</span><span class="sxs-lookup"><span data-stu-id="91b54-134">Restart the BizTalk Application service.</span></span>  
  
    1.  <span data-ttu-id="91b54-135">单击**启动**，单击**运行**，然后键入**services.msc**。</span><span class="sxs-lookup"><span data-stu-id="91b54-135">Click **Start**, click **Run**, and then type **services.msc**.</span></span>  
  
    2.  <span data-ttu-id="91b54-136">右键单击**BizTalk 服务 BizTalk 组：BizTalkServerApplication**服务，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="91b54-136">Right-click the **BizTalk Service BizTalk Group: BizTalkServerApplication** service and then click **Start**.</span></span>  
  
21. <span data-ttu-id="91b54-137">启用任何 BAM 多维数据集更新和数据维护 SSIS 包。</span><span class="sxs-lookup"><span data-stu-id="91b54-137">Enable any BAM cube update and data maintenance SSIS packages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91b54-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="91b54-138">See Also</span></span>  
 [<span data-ttu-id="91b54-139">备份和还原 BAM</span><span class="sxs-lookup"><span data-stu-id="91b54-139">Backing Up and Restoring BAM</span></span>](../core/backing-up-and-restoring-bam.md)