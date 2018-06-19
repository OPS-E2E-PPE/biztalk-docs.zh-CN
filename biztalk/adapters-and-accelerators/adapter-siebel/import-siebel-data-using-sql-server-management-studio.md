---
title: 导入使用 SQL Server Management Studio 的 Siebel 数据 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SQL Server Management Studio, importing data by using
- how to, import data by using SQL Server Management Studio
ms.assetid: 67da7f7b-37ea-4a31-89ef-a9f6974ff976
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a17d3061721006c9e98517a7bf2bf7ab11d7052d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223717"
---
# <a name="import-siebel-data-using-sql-server-management-studio"></a><span data-ttu-id="a492c-102">导入 Siebel 数据使用 SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="a492c-102">Import Siebel Data Using SQL Server Management Studio</span></span>
<span data-ttu-id="a492c-103">本部分提供有关如何使用 SQL Server Management Studio 从 Siebel 系统到 SQL Server 数据库导入数据的信息。</span><span class="sxs-lookup"><span data-stu-id="a492c-103">This section provides information about how to use SQL Server Management Studio to import data from a Siebel system into a SQL Server database.</span></span> <span data-ttu-id="a492c-104">它还提供有关如何创建和执行 SSIS 包导入此数据的说明。</span><span class="sxs-lookup"><span data-stu-id="a492c-104">It also provides instructions on how to create and execute an SSIS package to import this data.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a492c-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="a492c-105">Prerequisites</span></span>  
 <span data-ttu-id="a492c-106">执行本主题中提供过程之前，请确保：</span><span class="sxs-lookup"><span data-stu-id="a492c-106">Before performing the procedures provided in this topic, make sure:</span></span>  
  
-   <span data-ttu-id="a492c-107">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]计算机上安装。</span><span class="sxs-lookup"><span data-stu-id="a492c-107">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] is installed on the computer.</span></span>  
  
-   <span data-ttu-id="a492c-108">在计算机上安装 SQL Server Business Intelligence Development Studio。</span><span class="sxs-lookup"><span data-stu-id="a492c-108">SQL Server Business Intelligence Development Studio is installed on the computer.</span></span>  
  
## <a name="importing-data-by-using-sql-server-management-studio"></a><span data-ttu-id="a492c-109">使用 SQL Server Management Studio 导入数据</span><span class="sxs-lookup"><span data-stu-id="a492c-109">Importing Data by Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="a492c-110">执行以下步骤从 Siebel 系统使用导入数据[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]使用 SQL Server Management Studio。</span><span class="sxs-lookup"><span data-stu-id="a492c-110">Perform the following steps to import data from Siebel system using [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] with SQL Server Management Studio.</span></span>  
  
#### <a name="to-import-data-by-using-sql-server-management-studio"></a><span data-ttu-id="a492c-111">若要使用 SQL Server Management Studio 导入数据</span><span class="sxs-lookup"><span data-stu-id="a492c-111">To import data by using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="a492c-112">启动 SQL Server Management Studio。</span><span class="sxs-lookup"><span data-stu-id="a492c-112">Start the SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="a492c-113">在**连接到服务器**对话框框中，指定的值以连接到 SQL Server 数据库，然后单击**连接**。</span><span class="sxs-lookup"><span data-stu-id="a492c-113">In the **Connect to Server** dialog box, specify the values to connect to a SQL Server database, and then click **Connect**.</span></span> <span data-ttu-id="a492c-114">Microsoft SQL Server Management Studio 将打开。</span><span class="sxs-lookup"><span data-stu-id="a492c-114">Microsoft SQL Server Management Studio opens.</span></span>  
  
3.  <span data-ttu-id="a492c-115">在对象资源管理器，展开 SQL Server 名称，展开**数据库**，然后右键单击在其中你将会导出表从 Siebel 系统数据库。</span><span class="sxs-lookup"><span data-stu-id="a492c-115">In Object Explorer, expand the SQL Server name, expand **Databases**, and right-click the database into which you will be exporting the tables from the Siebel system.</span></span> <span data-ttu-id="a492c-116">从上下文菜单中，指向**任务**，然后单击**导入数据**。</span><span class="sxs-lookup"><span data-stu-id="a492c-116">From the context menu, point to **Tasks**, and then click **Import Data**.</span></span> <span data-ttu-id="a492c-117">这将启动 SQL Server 导入和导出向导。</span><span class="sxs-lookup"><span data-stu-id="a492c-117">This starts the SQL Server Import and Export Wizard.</span></span>  
  
4.  <span data-ttu-id="a492c-118">阅读欢迎屏幕上的信息，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="a492c-118">Read the information on the Welcome screen, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="a492c-119">在**选择数据源**对话框中，从**数据源**下拉列表中，选择**Siebel eBusiness Applications 的.NET Framework 数据提供程序**。</span><span class="sxs-lookup"><span data-stu-id="a492c-119">In the **Choose a Data Source** dialog box, from the **Data Source** drop-down list, select **.NET Framework Data Provider for Siebel eBusiness Applications**.</span></span> <span data-ttu-id="a492c-120">指定的不同的连接属性的值[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]连接字符串。</span><span class="sxs-lookup"><span data-stu-id="a492c-120">Specify values for the different connection properties for the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] connection string.</span></span> <span data-ttu-id="a492c-121">有关连接字符串属性的详细信息，请参阅[Siebel 连接字符串的数据提供程序属性](../../adapters-and-accelerators/adapter-siebel/data-provider-properties-for-the-siebel-connection-string.md)。</span><span class="sxs-lookup"><span data-stu-id="a492c-121">For more information about the connection string properties, see [Data provider properties for the Siebel connection string](../../adapters-and-accelerators/adapter-siebel/data-provider-properties-for-the-siebel-connection-string.md).</span></span>  
  
     <span data-ttu-id="a492c-122">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="a492c-122">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="a492c-123">在**选择目标**对话框中：</span><span class="sxs-lookup"><span data-stu-id="a492c-123">In the **Choose a Destination** dialog box:</span></span>  
  
    1.  <span data-ttu-id="a492c-124">从**目标**下拉列表中，选择**SQL Native Client**。</span><span class="sxs-lookup"><span data-stu-id="a492c-124">From the **Destination** drop-down list, select **SQL Native Client**.</span></span>  
  
    2.  <span data-ttu-id="a492c-125">从**服务器名称**下拉列表中，选择 SQL Server 名称。</span><span class="sxs-lookup"><span data-stu-id="a492c-125">From the **Server name** drop-down list, select a SQL Server name.</span></span>  
  
    3.  <span data-ttu-id="a492c-126">选择身份验证模式。</span><span class="sxs-lookup"><span data-stu-id="a492c-126">Select an authentication mode.</span></span>  
  
    4.  <span data-ttu-id="a492c-127">从**数据库**下拉列表中，选择你想要导入 Siebel 表的数据库。</span><span class="sxs-lookup"><span data-stu-id="a492c-127">From the **Database** drop-down list, select the database to which you want to import the Siebel table.</span></span>  
  
    5.  <span data-ttu-id="a492c-128">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="a492c-128">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="a492c-129">在**指定表复制或查询**对话框框中，选择**编写查询以指定要传输的数据**选项。</span><span class="sxs-lookup"><span data-stu-id="a492c-129">In the **Specify Table Copy or Query** dialog box, choose the **Write a query to specify the data to transfer** option.</span></span>  
  
8.  <span data-ttu-id="a492c-130">在**提供源查询**对话框框中，指定 SELECT 查询来筛选要导入到 SQL Server 的数据。</span><span class="sxs-lookup"><span data-stu-id="a492c-130">In the **Provide a Source Query** dialog box, specify a SELECT query to filter the data to be imported into the SQL Server.</span></span> <span data-ttu-id="a492c-131">有关语法的详细信息，以进行 SELECT 查询[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]，请参阅[为 Siebel 中 SELECT 语句的语法](../../adapters-and-accelerators/adapter-siebel/syntax-for-a-select-statement-in-siebel.md)。</span><span class="sxs-lookup"><span data-stu-id="a492c-131">For more information about the grammar for a SELECT query for the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], see [Syntax for a SELECT Statement in Siebel](../../adapters-and-accelerators/adapter-siebel/syntax-for-a-select-statement-in-siebel.md).</span></span>  
  
     <span data-ttu-id="a492c-132">单击**分析**按钮来验证查询时，单击**确定**在弹出对话框中，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="a492c-132">Click the **Parse** button to validate the query, click **OK** in the pop-up dialog box, and then click **Next**.</span></span>  
  
9. <span data-ttu-id="a492c-133">在**选择源表和源视图**对话框框中，选中针对源和目标表的复选框。</span><span class="sxs-lookup"><span data-stu-id="a492c-133">In the **Select Source Tables and Views** dialog box, select the check box against the source and destination tables.</span></span> <span data-ttu-id="a492c-134">源是您指定从 Siebel 检索数据的查询。</span><span class="sxs-lookup"><span data-stu-id="a492c-134">The source is the query you specified to retrieve data from Siebel.</span></span> <span data-ttu-id="a492c-135">目标是将在 SQL Server 数据库中创建的表。</span><span class="sxs-lookup"><span data-stu-id="a492c-135">The destination is the table that will be created in the SQL Server database.</span></span>  
  
10. <span data-ttu-id="a492c-136">该向导创建的源和目标之间的默认映射表字段。</span><span class="sxs-lookup"><span data-stu-id="a492c-136">The wizard creates a default mapping between the source and destination table fields.</span></span> <span data-ttu-id="a492c-137">但是，你可以根据你的要求更改映射。</span><span class="sxs-lookup"><span data-stu-id="a492c-137">However, you can change the mappings according to your requirement.</span></span> <span data-ttu-id="a492c-138">若要更改的字段映射，请单击**编辑映射**。</span><span class="sxs-lookup"><span data-stu-id="a492c-138">To change the field mappings, click **Edit Mappings**.</span></span>  
  
     <span data-ttu-id="a492c-139">![Siebel 和 SQL 表之间的列映射](../../adapters-and-accelerators/adapter-siebel/media/a3047801-3fa6-496b-91d8-3888dfbb0169.gif "a3047801-3fa6-496b-91d8-3888dfbb0169")</span><span class="sxs-lookup"><span data-stu-id="a492c-139">![Column mappings between Siebel and SQL table](../../adapters-and-accelerators/adapter-siebel/media/a3047801-3fa6-496b-91d8-3888dfbb0169.gif "a3047801-3fa6-496b-91d8-3888dfbb0169")</span></span>  
  
11. <span data-ttu-id="a492c-140">在**列映射**对话框中，你可以：</span><span class="sxs-lookup"><span data-stu-id="a492c-140">In the **Column Mappings** dialog box, you can:</span></span>  
  
    -   <span data-ttu-id="a492c-141">更改目标表中的列的名称。</span><span class="sxs-lookup"><span data-stu-id="a492c-141">Change the names of columns in the destination table.</span></span>  
  
    -   <span data-ttu-id="a492c-142">忽略目标表中的某些列。</span><span class="sxs-lookup"><span data-stu-id="a492c-142">Ignore certain columns in the destination table.</span></span>  
  
    -   <span data-ttu-id="a492c-143">更改目标表中的字段的数据类型。</span><span class="sxs-lookup"><span data-stu-id="a492c-143">Change the data type for fields in destination table.</span></span>  
  
    -   <span data-ttu-id="a492c-144">更改其他字段属性，如可以为 null，大小、 精度和小数位数。</span><span class="sxs-lookup"><span data-stu-id="a492c-144">Change other field attributes such as nullable, size, precision, and scale.</span></span>  
  
         <span data-ttu-id="a492c-145">在完成后，单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="a492c-145">When you are finished, click **OK**.</span></span>  
  
12. <span data-ttu-id="a492c-146">在**选择源表和源视图**对话框中，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="a492c-146">In the **Select Source Tables and Views** dialog box, click **Next**.</span></span>  
  
13. <span data-ttu-id="a492c-147">在**保存和执行包**对话框中：</span><span class="sxs-lookup"><span data-stu-id="a492c-147">In the **Save and Execute Package** dialog box:</span></span>  
  
    -   <span data-ttu-id="a492c-148">选择**立即执行**复选框，以执行查询。</span><span class="sxs-lookup"><span data-stu-id="a492c-148">Select the **Execute immediately** check box to execute the query.</span></span>  
  
    -   <span data-ttu-id="a492c-149">选择**保存 SSIS 包**复选框以将查询另存为包和更高版本执行。</span><span class="sxs-lookup"><span data-stu-id="a492c-149">Select the **Save SSIS Package** check box to save the query as a package and execute it later.</span></span> <span data-ttu-id="a492c-150">如果你选择以保存包，你还必须指定是否想要将包保存在 SQL Server 或文件系统。</span><span class="sxs-lookup"><span data-stu-id="a492c-150">If you chose to save the package, you must also specify whether you want to save the package in the SQL Server or the file system.</span></span>  
  
    -   <span data-ttu-id="a492c-151">从**包保护级别**下拉列表中，选择保护级别包并指定凭据需要。</span><span class="sxs-lookup"><span data-stu-id="a492c-151">From the **Package protection level** drop-down list, select a protection level for the package and specify credentials where required.</span></span>  
  
    -   <span data-ttu-id="a492c-152">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="a492c-152">Click **Next**.</span></span>  
  
     <span data-ttu-id="a492c-153">如果你选择以保存包，则继续执行下一步。</span><span class="sxs-lookup"><span data-stu-id="a492c-153">If you chose to save the package, proceed to the next step.</span></span> <span data-ttu-id="a492c-154">否则，请跳到步骤 15。</span><span class="sxs-lookup"><span data-stu-id="a492c-154">Otherwise, skip to step 15.</span></span>  
  
14. <span data-ttu-id="a492c-155">在**保存 SSIS 包**对话框框中，指定下列各项：</span><span class="sxs-lookup"><span data-stu-id="a492c-155">In the **Save SSIS Package** dialog box, specify the following:</span></span>  
  
    -   <span data-ttu-id="a492c-156">包的名称</span><span class="sxs-lookup"><span data-stu-id="a492c-156">The name for the package</span></span>  
  
    -   <span data-ttu-id="a492c-157">程序包描述</span><span class="sxs-lookup"><span data-stu-id="a492c-157">The description for the package</span></span>  
  
    -   <span data-ttu-id="a492c-158">如果你选择将包保存到 SQL Server，选择从 SQL Server**服务器名称**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="a492c-158">If you chose to save the package to a SQL Server, select a SQL Server from the **Server name** drop-down list.</span></span>  
  
    -   <span data-ttu-id="a492c-159">如果你选择将包保存到文件系统，指定的名称和位置中的文件**文件名**文本框。</span><span class="sxs-lookup"><span data-stu-id="a492c-159">If you chose to save the package to the file system, specify the name and location of the file in the **File name** text box.</span></span>  
  
         <span data-ttu-id="a492c-160">在完成后，单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="a492c-160">When you are finished, click **Next**.</span></span>  
  
15. <span data-ttu-id="a492c-161">在**完成向导**对话框框中，检查的操作，该向导将执行，然后单击摘要**完成**。</span><span class="sxs-lookup"><span data-stu-id="a492c-161">In the **Complete the Wizard** dialog box, review the summary of actions that the wizard will perform, and then click **Finish**.</span></span>  
  
16. <span data-ttu-id="a492c-162">在**执行操作**对话框中，向导开始执行任务以将信息从 Siebel 导入 SQL Server 数据库表。</span><span class="sxs-lookup"><span data-stu-id="a492c-162">In the **Performing Operations** dialog box, the wizard starts executing tasks to import the information from Siebel into a SQL Server database table.</span></span> <span data-ttu-id="a492c-163">在向导中显示每个任务的状态。</span><span class="sxs-lookup"><span data-stu-id="a492c-163">The status for each task is displayed in the wizard.</span></span>  
  
17. <span data-ttu-id="a492c-164">已成功执行所有任务后，单击**关闭**。</span><span class="sxs-lookup"><span data-stu-id="a492c-164">After all the tasks are successfully executed, click **Close**.</span></span> <span data-ttu-id="a492c-165">如果任务失败，请参阅相应的错误消息、 修复该问题，并重新运行该向导。</span><span class="sxs-lookup"><span data-stu-id="a492c-165">If a task fails, see the corresponding error message, fix the issue, and rerun the wizard.</span></span>  
  
## <a name="running-the-ssis-package"></a><span data-ttu-id="a492c-166">运行 SSIS 包</span><span class="sxs-lookup"><span data-stu-id="a492c-166">Running the SSIS Package</span></span>  
 <span data-ttu-id="a492c-167">如果你选择保存 SSIS 包，你可以运行它从 Siebel 系统中检索的最新信息。</span><span class="sxs-lookup"><span data-stu-id="a492c-167">If you chose to save the SSIS package, you can run it to retrieve the most recent information from the Siebel system.</span></span> <span data-ttu-id="a492c-168">本部分提供有关如何运行包，如果你选择将其保存到文件系统信息。</span><span class="sxs-lookup"><span data-stu-id="a492c-168">This section provides information about how to run the package if you chose to save it to the file system.</span></span>  
  
#### <a name="to-run-the-package-from-windows-explorer"></a><span data-ttu-id="a492c-169">若要从 Windows 资源管理器运行包</span><span class="sxs-lookup"><span data-stu-id="a492c-169">To run the package from Windows Explorer</span></span>  
  
1.  <span data-ttu-id="a492c-170">从**Windows 资源管理器**，导航到保存包的位置，然后双击包。</span><span class="sxs-lookup"><span data-stu-id="a492c-170">From **Windows Explorer**, navigate to the location where you saved the package, and double-click the package.</span></span>  
  
2.  <span data-ttu-id="a492c-171">在“执行包实用工具”对话框中，单击“执行”。</span><span class="sxs-lookup"><span data-stu-id="a492c-171">In the **Execute Package Utility** dialog box, click **Execute**.</span></span> <span data-ttu-id="a492c-172">**包的执行进度**对话框中显示的不同任务的进度。</span><span class="sxs-lookup"><span data-stu-id="a492c-172">The **Package Execution Progress** dialog box displays the progress of the different tasks.</span></span>  
  
3.  <span data-ttu-id="a492c-173">已成功执行所有任务后，单击**关闭**。</span><span class="sxs-lookup"><span data-stu-id="a492c-173">After all the tasks are successfully executed, click **Close**.</span></span>  
  
4.  <span data-ttu-id="a492c-174">在“执行包实用工具”对话框中，单击“关闭”。</span><span class="sxs-lookup"><span data-stu-id="a492c-174">In the **Execute Package Utility** dialog box, click **Close**.</span></span>  
  
 <span data-ttu-id="a492c-175">有关正在运行的包的详细信息，请参阅"正在运行的包"网址[http://go.microsoft.com/fwlink/?LinkId=94972](http://go.microsoft.com/fwlink/?LinkId=94972)。</span><span class="sxs-lookup"><span data-stu-id="a492c-175">For more information about running packages, see "Running Packages" at [http://go.microsoft.com/fwlink/?LinkId=94972](http://go.microsoft.com/fwlink/?LinkId=94972).</span></span> <span data-ttu-id="a492c-176">有关任何 SSIS 包，与相关的其他信息时，请参阅"包操作指南主题 (SSIS)" [http://go.microsoft.com/fwlink/?LinkId=94973](http://go.microsoft.com/fwlink/?LinkId=94973)。</span><span class="sxs-lookup"><span data-stu-id="a492c-176">For any other information related to SSIS packages, see "Package How-to Topics (SSIS)" at [http://go.microsoft.com/fwlink/?LinkId=94973](http://go.microsoft.com/fwlink/?LinkId=94973).</span></span>  
  
## <a name="verifying-the-results"></a><span data-ttu-id="a492c-177">验证结果</span><span class="sxs-lookup"><span data-stu-id="a492c-177">Verifying the Results</span></span>  
 <span data-ttu-id="a492c-178">后执行包，你必须通过转到 Siebel 数据导入到的 SQL Server 数据库来验证结果。</span><span class="sxs-lookup"><span data-stu-id="a492c-178">After executing the package, you must verify the results by going to the SQL Server database to which the Siebel data is imported.</span></span> <span data-ttu-id="a492c-179">执行包应已创建表目标数据库中。</span><span class="sxs-lookup"><span data-stu-id="a492c-179">Executing the package should have created a table in the destination database.</span></span> <span data-ttu-id="a492c-180">应使用 Siebel 表中的值填充此表。</span><span class="sxs-lookup"><span data-stu-id="a492c-180">This table should be populated with the values from the Siebel table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a492c-181">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a492c-181">See Also</span></span>  
 [<span data-ttu-id="a492c-182">使用用于 Siebel 使用 SSIS 数据提供程序</span><span class="sxs-lookup"><span data-stu-id="a492c-182">Use the Data Provider for Siebel with SSIS</span></span>](../../adapters-and-accelerators/adapter-siebel/use-the-data-provider-for-siebel-with-ssis.md)