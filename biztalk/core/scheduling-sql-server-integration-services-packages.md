---
title: 计划 SQL Server Integration Services 包 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 037ae2cf-c352-4823-95df-9a723f2b5a81
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43ce70dc97de2958add5c583646b7825d981982b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001790"
---
# <a name="scheduling-sql-server-integration-services-packages"></a><span data-ttu-id="00e8d-102">计划 SQL Server Integration Services 包</span><span class="sxs-lookup"><span data-stu-id="00e8d-102">Scheduling SQL Server Integration Services Packages</span></span>
<span data-ttu-id="00e8d-103">用户可以创建基于存储在联机分析处理 (OLAP) 多维数据集中的数据的 BAM 视图。</span><span class="sxs-lookup"><span data-stu-id="00e8d-103">Users create BAM views based on data stored in an online analytical processing (OLAP) cube.</span></span> <span data-ttu-id="00e8d-104">多维数据集更新集成服务包将刷新多维数据集中的数据，以便 OLAP 视图可以反映正确的数据。</span><span class="sxs-lookup"><span data-stu-id="00e8d-104">The Cube Update Integration Services package refreshes the data in the cube so that OLAP views reflect the correct data.</span></span>  
  
 <span data-ttu-id="00e8d-105">你必须至少运行一次此包才能使 OLAP 视图可以工作。</span><span class="sxs-lookup"><span data-stu-id="00e8d-105">You must run this package at least once for the OLAP views to work.</span></span> <span data-ttu-id="00e8d-106">如果要进行实时维护，则应该安排该包定期运行。</span><span class="sxs-lookup"><span data-stu-id="00e8d-106">For ongoing maintenance, you should schedule the package to run on a regular basis.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="00e8d-107">如果你在运行多维数据集更新集成服务包之前还原了 BAM 星型架构数据库或停止了 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]，则必须先在 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 分析管理器中刷新数据源或者重新启动 OLAP 服务，然后才能成功运行该程序包。</span><span class="sxs-lookup"><span data-stu-id="00e8d-107">If you restored the BAM Star Schema database or stopped [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] before running the Cube Update Integration Services package, you must refresh the data sources in [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Analysis Manager or restart the OLAP service before you can run the package successfully.</span></span>  
  
 <span data-ttu-id="00e8d-108">你可以将保存的程序包安排在特定时间执行，既可以执行一次也可以按重复的时间间隔执行。</span><span class="sxs-lookup"><span data-stu-id="00e8d-108">You can schedule a saved package to execute at specific times, either once or at recurring intervals.</span></span> <span data-ttu-id="00e8d-109">例如：</span><span class="sxs-lookup"><span data-stu-id="00e8d-109">For example:</span></span>  
  
- <span data-ttu-id="00e8d-110">每天的午夜。</span><span class="sxs-lookup"><span data-stu-id="00e8d-110">Daily at midnight.</span></span>  
  
- <span data-ttu-id="00e8d-111">每个周日的 06:00。</span><span class="sxs-lookup"><span data-stu-id="00e8d-111">Weekly on Sunday at 06:00.</span></span>  
  
- <span data-ttu-id="00e8d-112">每月的第一天或者最后一天。</span><span class="sxs-lookup"><span data-stu-id="00e8d-112">The first or last day of the month.</span></span>  
  
  <span data-ttu-id="00e8d-113">已安排的程序包将作为一项作业由 [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] 执行。</span><span class="sxs-lookup"><span data-stu-id="00e8d-113">A scheduled package is executed by [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] as a job.</span></span>  
  
  <span data-ttu-id="00e8d-114">有关运行信息[!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)]包，请参阅[ http://go.microsoft.com/fwlink/?LinkId=125738 ](http://go.microsoft.com/fwlink/?LinkId=125738)。</span><span class="sxs-lookup"><span data-stu-id="00e8d-114">For information about running [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] packages, see [http://go.microsoft.com/fwlink/?LinkId=125738](http://go.microsoft.com/fwlink/?LinkId=125738).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="00e8d-115">默认情况下，会打开归档 BAM SSIS 程序包以及计算其立方的日志记录，并将该日志记录存储在 msdb 数据库中。</span><span class="sxs-lookup"><span data-stu-id="00e8d-115">By default, logging for archiving and cubing BAM SSIS packages is turned on and is stored in the msdb database.</span></span> <span data-ttu-id="00e8d-116">一段时间后，大量 BAM 活动或频繁执行由 BAM 所有的 SSIS 程序包可能会造成数目庞大的 SSIS 事件日志数据。</span><span class="sxs-lookup"><span data-stu-id="00e8d-116">Overtime, this may result in a significant volume of SSIS event log data caused by large number of BAM activities or frequent execution of BAM owned SSIS packages.</span></span> <span data-ttu-id="00e8d-117">可以删除旧的日志项以解决此问题，因为这些日志项主要用于调试目的。</span><span class="sxs-lookup"><span data-stu-id="00e8d-117">To resolve this, you can delete the old log entries because these entries are used primarily for debugging.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="00e8d-118">必要條件</span><span class="sxs-lookup"><span data-stu-id="00e8d-118">Prerequisites</span></span>  
 <span data-ttu-id="00e8d-119">必须以 BizTalk Server Administrators 组成员的身份登录，才能执行这些过程。</span><span class="sxs-lookup"><span data-stu-id="00e8d-119">You must be logged on as a member of the BizTalk Server Administrators group to perform these procedures.</span></span>  
  
### <a name="to-run-the-cube-update-integration-services-package"></a><span data-ttu-id="00e8d-120">运行多维数据集更新集成服务包</span><span class="sxs-lookup"><span data-stu-id="00e8d-120">To run the Cube Update Integration Services package</span></span>  
  
1.  <span data-ttu-id="00e8d-121">单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 SP1**或者**Microsoft SQL Server 2008 R2**，然后单击**SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="00e8d-121">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 SP1** or **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="00e8d-122">在中**连接到服务器**对话框中**服务器类型**下拉列表中，选择**Integration Services**。</span><span class="sxs-lookup"><span data-stu-id="00e8d-122">In the **Connect to server** dialog box, in the **Server type** drop-down list, select **Integration Services**.</span></span>  
  
3.  <span data-ttu-id="00e8d-123">在中**服务器名称**下拉列表中，选择运行包的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="00e8d-123">In the **Server name** drop-down list, select the name of the server on which you are running the package.</span></span>  
  
4.  <span data-ttu-id="00e8d-124">在中**身份验证**下拉列表中，选择您用来连接到服务器的身份验证的类型。</span><span class="sxs-lookup"><span data-stu-id="00e8d-124">In the **Authentication** drop-down list, select the type of authentication that you are using to connect to the server.</span></span>  
  
5.  <span data-ttu-id="00e8d-125">如有必要，请键入你的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="00e8d-125">If necessary, type your user name and password.</span></span>  
  
6.  <span data-ttu-id="00e8d-126">单击 **“连接”**。</span><span class="sxs-lookup"><span data-stu-id="00e8d-126">Click **Connect**.</span></span>  
  
7.  <span data-ttu-id="00e8d-127">在控制台树中，展开**Integration Services**，展开**存储的包**，然后单击**MSDB**。</span><span class="sxs-lookup"><span data-stu-id="00e8d-127">In the console tree, expand **Integration Services**, expand **Stored Packages**, and then click **MSDB**.</span></span>  
  
8.  <span data-ttu-id="00e8d-128">右键单击**BAM_AN_\<视图名称\>** 打包，然后依次**运行包**。</span><span class="sxs-lookup"><span data-stu-id="00e8d-128">Right-click the **BAM_AN_\<View name\>** package, and then click **Run Package**.</span></span>  
  
### <a name="to-run-the-maintaining-bam-data-integration-services-package"></a><span data-ttu-id="00e8d-129">运行维护 BAM 数据集成服务包</span><span class="sxs-lookup"><span data-stu-id="00e8d-129">To run the Maintaining BAM Data Integration Services package</span></span>  
  
1.  <span data-ttu-id="00e8d-130">单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 SP1**或者**Microsoft SQL Server 2008 R2**，然后单击**SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="00e8d-130">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 SP1** or **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="00e8d-131">在中**连接到服务器**对话框中**服务器类型**下拉列表中，选择**Integration Services**。</span><span class="sxs-lookup"><span data-stu-id="00e8d-131">In the **Connect to server** dialog box, in the **Server type** drop-down list, select **Integration Services**.</span></span>  
  
3.  <span data-ttu-id="00e8d-132">在中**服务器名称**下拉列表中，选择运行包的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="00e8d-132">In the **Server name** drop-down list, select the name of the server on which you are running the package.</span></span>  
  
4.  <span data-ttu-id="00e8d-133">在中**身份验证**下拉列表中，选择您用来连接到服务器的身份验证的类型。</span><span class="sxs-lookup"><span data-stu-id="00e8d-133">In the **Authentication** drop-down list, select the type of authentication that you are using to connect to the server.</span></span>  
  
5.  <span data-ttu-id="00e8d-134">如有必要，请键入你的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="00e8d-134">If necessary, type your user name and password.</span></span>  
  
6.  <span data-ttu-id="00e8d-135">单击 **“连接”**。</span><span class="sxs-lookup"><span data-stu-id="00e8d-135">Click **Connect**.</span></span>  
  
7.  <span data-ttu-id="00e8d-136">在控制台树中，展开**Integration Services**，展开**存储的包**，然后单击**MSDB**。</span><span class="sxs-lookup"><span data-stu-id="00e8d-136">In the console tree, expand **Integration Services**, expand **Stored Packages**, and then click **MSDB**.</span></span>  
  
8.  <span data-ttu-id="00e8d-137">右键单击**BAM_DM_\<活动名称\>** 打包，然后依次**运行包**。</span><span class="sxs-lookup"><span data-stu-id="00e8d-137">Right-click the **BAM_DM_\<Activity name\>** package, and then click **Run Package**.</span></span>  
  
### <a name="to-schedule-the-packages-to-run-regularly"></a><span data-ttu-id="00e8d-138">安排包进行定期运行</span><span class="sxs-lookup"><span data-stu-id="00e8d-138">To schedule the packages to run regularly</span></span>  
  
1.  <span data-ttu-id="00e8d-139">单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 SP1**或者**Microsoft SQL Server 2008 R2**，然后单击**SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="00e8d-139">Click **Start**, click **All Programs**, click **Microsoft SQL Server 2008 SP1** or **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="00e8d-140">在中**连接到服务器**对话框中**服务器类型**下拉列表中，选择**数据库引擎**。</span><span class="sxs-lookup"><span data-stu-id="00e8d-140">In the **Connect to server** dialog box, in the **Server type** drop-down list, select **Database Engine**.</span></span>  
  
3.  <span data-ttu-id="00e8d-141">在中**服务器名称**下拉列表中，选择运行包的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="00e8d-141">In the **Server name** drop-down list, select the name of the server on which you are running the package.</span></span>  
  
4.  <span data-ttu-id="00e8d-142">在中**身份验证**下拉列表中，选择您用来连接到服务器的身份验证的类型。</span><span class="sxs-lookup"><span data-stu-id="00e8d-142">In the **Authentication** drop-down list, select the type of authentication that you are using to connect to the server.</span></span>  
  
5.  <span data-ttu-id="00e8d-143">如有必要，请键入你的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="00e8d-143">If necessary, type your user name and password.</span></span>  
  
6.  <span data-ttu-id="00e8d-144">单击 **“连接”**。</span><span class="sxs-lookup"><span data-stu-id="00e8d-144">Click **Connect**.</span></span>  
  
7.  <span data-ttu-id="00e8d-145">在控制台树中，展开您的服务器，然后选择**SQL Server 代理**。</span><span class="sxs-lookup"><span data-stu-id="00e8d-145">In the console tree, expand your server, and select **SQL Server Agent**.</span></span>  
  
8.  <span data-ttu-id="00e8d-146">如果**SQL Server 代理**已禁用，右键单击**SQL Server 代理**，然后选择**启动**。</span><span class="sxs-lookup"><span data-stu-id="00e8d-146">If **SQL Server Agent** is disabled, right-click **SQL Server Agent**, and then select **Start**.</span></span>  
  
9. <span data-ttu-id="00e8d-147">右键单击**SQL Server 代理**，然后选择**新作业**。</span><span class="sxs-lookup"><span data-stu-id="00e8d-147">Right-click **SQL Server Agent**, and select  **New Job**.</span></span>  
  
10. <span data-ttu-id="00e8d-148">在中**新的作业**对话框中，键入的名称中的作业**名称**文本框。</span><span class="sxs-lookup"><span data-stu-id="00e8d-148">In the **New Job** dialog box, type a name for the job in the **Name** text box.</span></span>  
  
11. <span data-ttu-id="00e8d-149">在中**选择页**窗口中，单击**步骤**，然后单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="00e8d-149">In the **Select a page** window, click **Steps**, and then click **New**.</span></span> <span data-ttu-id="00e8d-150">这将打开**新建作业步骤**对话框。</span><span class="sxs-lookup"><span data-stu-id="00e8d-150">This opens the **New Job Step** dialog box.</span></span>  
  
12. <span data-ttu-id="00e8d-151">在中**步骤名称**文字框中，键入在步骤的标识名称。</span><span class="sxs-lookup"><span data-stu-id="00e8d-151">In the **Step name** text box, type an identifying name for the step.</span></span>  
  
13. <span data-ttu-id="00e8d-152">在中**类型**下拉列表中，选择**SQL Server Integration Services 包**并在**包源**下拉列表中，选择**SSIS 包存储区**.</span><span class="sxs-lookup"><span data-stu-id="00e8d-152">In the **Type** drop-down list, select **SQL Server Integration Services Package** and in the **Package source** drop-down list, select **SSIS Package Store**.</span></span>  
  
14. <span data-ttu-id="00e8d-153">在中**Server**下拉列表中，选择运行作业的服务器。</span><span class="sxs-lookup"><span data-stu-id="00e8d-153">In the **Server** drop-down list, select the server on which you are running the job.</span></span>  
  
15. <span data-ttu-id="00e8d-154">单击的文件选择器按钮**包**文字框中，选择要安排的包 (任一**BAM_DM_\<活动名称\>** 或**BAM_AN_\<视图名称\>** 包)，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="00e8d-154">Click the file selector button for the **Package** text box, select the package you are scheduling (either the **BAM_DM_\<Activity name\>** or **BAM_AN_\<View name\>** package), and then click **OK**.</span></span>  
  
16. <span data-ttu-id="00e8d-155">在中**选择页**窗口中，单击**计划**，然后单击**新建**。</span><span class="sxs-lookup"><span data-stu-id="00e8d-155">In the **Select a page** window, click **Schedules**, and then click **New**.</span></span> <span data-ttu-id="00e8d-156">这将打开**新建作业计划**对话框。</span><span class="sxs-lookup"><span data-stu-id="00e8d-156">This opens the **New Job Schedule** dialog box.</span></span>  
  
17. <span data-ttu-id="00e8d-157">在中**名称**文本框中，为计划键入一个名称。</span><span class="sxs-lookup"><span data-stu-id="00e8d-157">In the **Name** text box, type a name for the schedule.</span></span>  
  
18. <span data-ttu-id="00e8d-158">使用频率字段创建你的计划。</span><span class="sxs-lookup"><span data-stu-id="00e8d-158">Create your schedule using the frequency fields.</span></span>  
  
19. <span data-ttu-id="00e8d-159">单击 **“确定”** 保存作业。</span><span class="sxs-lookup"><span data-stu-id="00e8d-159">Click **OK** to save the job.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="00e8d-160">如果使用 SQL Server 的非默认实例配置 BAM，则将不能正确计划/执行 BAM_AN_POCube DTSPackage。</span><span class="sxs-lookup"><span data-stu-id="00e8d-160">If BAM is configured with a non-default instance of SQL Server, then the BAM_AN_POCube DTSPackage does not get scheduled/executed accurately.</span></span> <span data-ttu-id="00e8d-161">需要修改配置文件以允许包继续运行。</span><span class="sxs-lookup"><span data-stu-id="00e8d-161">You need to modify the configuration file to allow packages to continue running.</span></span> <span data-ttu-id="00e8d-162">有关详细信息，请参阅"修改配置文件内容"部分[ http://go.microsoft.com/fwlink/?LinkId=196768 ](http://go.microsoft.com/fwlink/?LinkId=196768)。</span><span class="sxs-lookup"><span data-stu-id="00e8d-162">For more information, refer to the "Modifying the Contents of the Configuration File" section at [http://go.microsoft.com/fwlink/?LinkId=196768](http://go.microsoft.com/fwlink/?LinkId=196768).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00e8d-163">请参阅</span><span class="sxs-lookup"><span data-stu-id="00e8d-163">See Also</span></span>  
 [<span data-ttu-id="00e8d-164">管理 BAM 数据库</span><span class="sxs-lookup"><span data-stu-id="00e8d-164">Managing BAM Databases</span></span>](../core/managing-bam-databases.md)