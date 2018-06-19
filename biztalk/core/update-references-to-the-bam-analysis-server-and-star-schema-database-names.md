---
title: 如何更新对 BAM Analysis Server 和星型架构数据库名称的引用 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- restoring [BAM], Analysis database
- Analysis database [BAM], restoring
- restoring, BAM
- restoring [BAM], updating references
- BAM, restoring
- Analysis database [BAM], updating references
ms.assetid: cbe5e500-0a25-427e-bc76-1eae24b3e5f3
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4f98129efd2f7c027ecb6c3e69d494ff2e96e8b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287445"
---
# <a name="how-to-update-references-to-the-bam-analysis-server-and-star-schema-database-names"></a><span data-ttu-id="cac23-102">如何更新对 BAM 分析服务器和 BAM 星型架构数据库名称的引用</span><span class="sxs-lookup"><span data-stu-id="cac23-102">How to Update References to the BAM Analysis Server and Star Schema Database Names</span></span>
<span data-ttu-id="cac23-103">如果备份了 BAMAnalysis 和 BAMStarSchema 数据库，则在系统或数据发生故障时，可以将该备份还原到其他计算机上，然后重命名该备份。</span><span class="sxs-lookup"><span data-stu-id="cac23-103">If you backed up your BAMAnalysis and BAMStarSchema databases, in the event of a system or data failure you can restore that backup to a different computer and you can rename the backup.</span></span>  
  
 <span data-ttu-id="cac23-104">若要还原 BAM 分析服务器或 BAMStarSchema 数据库，执行中的步骤[如何还原您的数据库](../core/how-to-restore-your-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="cac23-104">To restore the BAM Analysis Server or BAMStarSchema databases, perform the steps in [How to Restore Your Databases](../core/how-to-restore-your-databases.md).</span></span> <span data-ttu-id="cac23-105">此外，还必须用新的服务器名称和数据库名称更新 BAM 数据转换服务 (DTS) 包。</span><span class="sxs-lookup"><span data-stu-id="cac23-105">In addition, you must update the BAM Data Transformation Services (DTS) packages with the new server name and database name.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cac23-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="cac23-106">Prerequisites</span></span>  
 <span data-ttu-id="cac23-107">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators 组成员的身份登录，才能执行此过程。</span><span class="sxs-lookup"><span data-stu-id="cac23-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group to perform this procedure.</span></span>  
  
### <a name="to-update-references-to-the-bam-analysis-server-and-bam-star-schema-database-name-sql-server-2008-r2sp1"></a><span data-ttu-id="cac23-108">更新对 BAM 分析服务器和 BAM 星型架构数据库名称 (SQL Server 2008 R2/SP1) 的引用</span><span class="sxs-lookup"><span data-stu-id="cac23-108">To update references to the BAM Analysis Server and BAM Star Schema database name (SQL Server 2008 R2/SP1)</span></span>  
  
1.  <span data-ttu-id="cac23-109">停止任何 BAM 多维数据集更新和数据维护 SSIS 包，或者阻止它们运行，直到 BAMAnalysis 或 BAMStarSchema 数据库的还原完成为止。</span><span class="sxs-lookup"><span data-stu-id="cac23-109">Stop any BAM cube update and data maintenance SSIS packages, or prevent them from running until you have restored the BAMAnalysis or BAMStarSchema databases.</span></span>  
  
2.  <span data-ttu-id="cac23-110">停止 BizTalk 应用程序服务（包含 BAM 事件总线服务），以便它不再将更多数据导入到数据库中。</span><span class="sxs-lookup"><span data-stu-id="cac23-110">Stop the BizTalk Application service (which includes the BAM Event Bus service) so it does not try to import more data into the databases.</span></span>  
  
    1.  <span data-ttu-id="cac23-111">单击**启动**，单击**运行**，然后键入**services.msc**。</span><span class="sxs-lookup"><span data-stu-id="cac23-111">Click **Start**, click **Run**, and then type **services.msc**.</span></span>  
  
    2.  <span data-ttu-id="cac23-112">右键单击**BizTalk 服务 BizTalk 组： BizTalkServerApplication**服务，然后单击**停止**。</span><span class="sxs-lookup"><span data-stu-id="cac23-112">Right-click the **BizTalk Service BizTalk Group: BizTalkServerApplication** service and then click **Stop**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="cac23-113">另一种方法来停止服务是使用**Net 停止**命令。</span><span class="sxs-lookup"><span data-stu-id="cac23-113">Another way to stop a service is to use the **Net Stop** command.</span></span> <span data-ttu-id="cac23-114">若要停止使用 Net 停止的 BizTalk 服务，打开**命令提示符**(如果使用 Windows Server 2008 或 Windows Vista，启动命令提示符处使用**以管理员身份运行**) 并键入以下命令： `Net Stop BTSSvc$BizTalkServerApplication`然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="cac23-114">To stop the BizTalk service using Net Stop, open a **Command Prompt** (If using Windows Server 2008 or Windows Vista, start the Command Prompt using **Run As Administrator**) and type the following: `Net Stop BTSSvc$BizTalkServerApplication` then press **Enter**.</span></span>  
  
3.  <span data-ttu-id="cac23-115">单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 R2**，然后单击**SQL Server Business Intelligence Development Studio**.</span><span class="sxs-lookup"><span data-stu-id="cac23-115">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 R2**, and then click **SQL Server Business Intelligence Development Studio**.</span></span>  
  
4.  <span data-ttu-id="cac23-116">在 SQL Server Business Intelligence Development Studio 中，创建一个新项目。</span><span class="sxs-lookup"><span data-stu-id="cac23-116">In SQL Server Business Intelligence Development Studio, create a new project.</span></span> <span data-ttu-id="cac23-117">单击**文件**，单击**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="cac23-117">Click **File**, click **New**, and then click **Project**.</span></span>  
  
5.  <span data-ttu-id="cac23-118">在**新项目**对话框中，在**模板**，单击**Integration Services 项目**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="cac23-118">In the **New Project** dialog box, in **Templates**, click **Integration Services Project**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="cac23-119">在**Integration Services 项目**对话框中，在**解决方案资源管理器**，右键单击**SSIS 包**，然后单击**添加现有包**.</span><span class="sxs-lookup"><span data-stu-id="cac23-119">In the **Integration Services Project** dialog box, in **Solution Explorer**, right-click **SSIS Packages**, and then click **Add Existing Package**.</span></span>  
  
7.  <span data-ttu-id="cac23-120">在**添加现有包副本**对话框中，在**服务器**下拉列表框中，选择包含 BAM_AN 包的服务器。</span><span class="sxs-lookup"><span data-stu-id="cac23-120">In the **Add Copy of Existing Package** dialog box, in the **Server** drop-down list box, select the server that contains the BAM_AN package.</span></span>  
  
8.  <span data-ttu-id="cac23-121">在**包路径**，单击省略号按钮。</span><span class="sxs-lookup"><span data-stu-id="cac23-121">In **Package Path**, click the ellipses button.</span></span>  
  
9. <span data-ttu-id="cac23-122">在**SSIS 包**对话框框中，选择 BAM_AN 包，单击**确定**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="cac23-122">In the **SSIS Package** dialog box, select the BAM_AN package, click **OK**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="cac23-123">现在，该包列在解决方案资源管理器中。</span><span class="sxs-lookup"><span data-stu-id="cac23-123">The package is now listed in Solution Explorer.</span></span>  
  
10. <span data-ttu-id="cac23-124">在**解决方案资源管理器**，双击 BAM_AN 包。</span><span class="sxs-lookup"><span data-stu-id="cac23-124">In **Solution Explorer**, double-click the BAM_AN package.</span></span> <span data-ttu-id="cac23-125">在**连接管理器**，双击数据库的编号 3 （MSDB 数据库）。</span><span class="sxs-lookup"><span data-stu-id="cac23-125">In **Connection Managers**, double-click database number 3 (MSDB database).</span></span>  
  
11. <span data-ttu-id="cac23-126">在**连接管理器**对话框中，在**服务器名称**框中，输入 MSDB 服务器的名称，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="cac23-126">In the **Connection Manager** dialog box, in the **Server name** box, enter the name of the MSDB server, and then click **OK**.</span></span>  
  
12. <span data-ttu-id="cac23-127">单击**包资源管理器**选项卡上，双击**变量**文件夹，然后更新主导入服务器名称和主的值导入数据库名称。</span><span class="sxs-lookup"><span data-stu-id="cac23-127">Click the **Package Explorer** tab, double-click the **Variables** folder, and then update the values for the primary import server name and primary import database name.</span></span>  
  
13. <span data-ttu-id="cac23-128">单击**文件**，然后单击**保存所有**。</span><span class="sxs-lookup"><span data-stu-id="cac23-128">Click **File**, and then click **Save All**.</span></span>  
  
14. <span data-ttu-id="cac23-129">在**Microsoft SQL Server Management Studio**，单击**连接**。</span><span class="sxs-lookup"><span data-stu-id="cac23-129">In **Microsoft SQL Server Management Studio**, click **Connect**.</span></span>  
  
15. <span data-ttu-id="cac23-130">单击**Integration Services**，双击**存储的包**，单击**MSDB**，右击 BAM_AN 包，然后单击**导入包**.</span><span class="sxs-lookup"><span data-stu-id="cac23-130">Click **Integration Services**, double-click **Stored Packages**, click **MSDB**, right-click the BAM_AN package, and then click **Import Package**.</span></span>  
  
16. <span data-ttu-id="cac23-131">在**导入包**对话框中，在**包位置**，选择**文件系统**。</span><span class="sxs-lookup"><span data-stu-id="cac23-131">In the **Import Package** dialog box, in **Package location**, select **File System**.</span></span>  
  
17. <span data-ttu-id="cac23-132">在**包路径**，导航到已保存项目，选择 BAM_AN\*.dtsx 文件，然后单击**打开**。</span><span class="sxs-lookup"><span data-stu-id="cac23-132">In **Package Path**, navigate to your saved project, select the BAM_AN\*.dtsx file, and then click **Open**.</span></span>  
  
18. <span data-ttu-id="cac23-133">在内部单击**包名称**框以在框中自动填充。</span><span class="sxs-lookup"><span data-stu-id="cac23-133">Click inside the **Package Name** box to automatically populate the box.</span></span>  
  
19. <span data-ttu-id="cac23-134">单击**确定**，然后单击**是**覆盖。</span><span class="sxs-lookup"><span data-stu-id="cac23-134">Click **OK**, and then click **Yes** to overwrite.</span></span>  
  
20. <span data-ttu-id="cac23-135">重新启动 BizTalk 应用程序服务。</span><span class="sxs-lookup"><span data-stu-id="cac23-135">Restart the BizTalk Application service.</span></span>  
  
    1.  <span data-ttu-id="cac23-136">单击**启动**，单击**运行**，然后键入**services.msc**。</span><span class="sxs-lookup"><span data-stu-id="cac23-136">Click **Start**, click **Run**, and then type **services.msc**.</span></span>  
  
    2.  <span data-ttu-id="cac23-137">右键单击**BizTalk 服务 BizTalk 组： BizTalkServerApplication**服务，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="cac23-137">Right-click the **BizTalk Service BizTalk Group: BizTalkServerApplication** service and then click **Start**.</span></span>  
  
21. <span data-ttu-id="cac23-138">启用任何 BAM 多维数据集更新和数据维护 SSIS 包。</span><span class="sxs-lookup"><span data-stu-id="cac23-138">Enable any BAM cube update and data maintenance SSIS packages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cac23-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cac23-139">See Also</span></span>  
 [<span data-ttu-id="cac23-140">备份和还原 BAM</span><span class="sxs-lookup"><span data-stu-id="cac23-140">Backing Up and Restoring BAM</span></span>](../core/backing-up-and-restoring-bam.md)