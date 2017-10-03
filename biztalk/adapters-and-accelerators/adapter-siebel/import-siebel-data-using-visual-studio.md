---
title: "导入使用 Visual Studio 的 Siebel 数据 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SSIS
- Data Provider for Siebel, importing Siebel data by using Visual Studio
ms.assetid: 33701361-eca2-4795-a5e0-78162a98e9ba
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0671459b39462422768e42e18bf16336a469f43
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="import-siebel-data-using-visual-studio"></a><span data-ttu-id="3696e-102">使用 Visual Studio 的 Siebel 数据导入</span><span class="sxs-lookup"><span data-stu-id="3696e-102">Import Siebel Data Using Visual Studio</span></span>
<span data-ttu-id="3696e-103">本部分提供有关如何使用 Microsoft 的信息[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]从 Siebel 系统到 SQL Server 数据库导入数据。</span><span class="sxs-lookup"><span data-stu-id="3696e-103">This section provides information about how to use Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to import data from a Siebel system into a SQL Server database.</span></span> <span data-ttu-id="3696e-104">它还提供有关如何创建和执行 SSIS 包导入此数据的说明。</span><span class="sxs-lookup"><span data-stu-id="3696e-104">It also provides instructions on how to create and execute an SSIS package to import this data.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3696e-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="3696e-105">Prerequisites</span></span>  
 <span data-ttu-id="3696e-106">执行本主题中提供过程之前，请确保：</span><span class="sxs-lookup"><span data-stu-id="3696e-106">Before performing the procedures provided in this topic, make sure:</span></span>  
  
-   <span data-ttu-id="3696e-107">[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]计算机上安装。</span><span class="sxs-lookup"><span data-stu-id="3696e-107">The [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] is installed on the computer.</span></span>  
  
-   <span data-ttu-id="3696e-108">Microsoft[!INCLUDE[vs2010](../../includes/vs2010-md.md)]计算机上安装。</span><span class="sxs-lookup"><span data-stu-id="3696e-108">Microsoft [!INCLUDE[vs2010](../../includes/vs2010-md.md)] is installed on the computer.</span></span>  
  
## <a name="importing-data-by-using-visual-studio"></a><span data-ttu-id="3696e-109">使用 Visual Studio 中导入数据</span><span class="sxs-lookup"><span data-stu-id="3696e-109">Importing Data by Using Visual Studio</span></span>  
 <span data-ttu-id="3696e-110">执行以下步骤以使用导入数据[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="3696e-110">Perform the following steps to import data using [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  
  
#### <a name="to-import-data-by-using-visual-studio"></a><span data-ttu-id="3696e-111">若要通过使用 Visual Studio 导入数据</span><span class="sxs-lookup"><span data-stu-id="3696e-111">To import data by using Visual Studio</span></span>  
  
1.  <span data-ttu-id="3696e-112">启动[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]并创建一个集成服务项目。</span><span class="sxs-lookup"><span data-stu-id="3696e-112">Start [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and create an Integration Service project.</span></span>  
  
2.  <span data-ttu-id="3696e-113">从**项目**菜单上，选择**SSIS 导入和导出向导**。</span><span class="sxs-lookup"><span data-stu-id="3696e-113">From the **Project** menu, select **SSIS Import and Export Wizard**.</span></span> <span data-ttu-id="3696e-114">这将启动 SQL Server 导入和导出向导。</span><span class="sxs-lookup"><span data-stu-id="3696e-114">This starts the SQL Server Import and Export Wizard.</span></span>  
  
3.  <span data-ttu-id="3696e-115">阅读欢迎屏幕上的信息，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="3696e-115">Read the information on the Welcome screen, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="3696e-116">在**选择数据源**对话框中，从**数据源**下拉列表**Siebel eBusiness Applications 的.NET Framework 数据提供程序**。</span><span class="sxs-lookup"><span data-stu-id="3696e-116">In the **Choose a Data Source** dialog box, from the **Data Source** drop-down list **.NET Framework Data Provider for Siebel eBusiness Applications**.</span></span> <span data-ttu-id="3696e-117">指定的不同的连接属性的值[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]连接字符串。</span><span class="sxs-lookup"><span data-stu-id="3696e-117">Specify values for the different connection properties for the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)] connection string.</span></span> <span data-ttu-id="3696e-118">有关连接字符串属性的详细信息，请参阅[Siebel 连接字符串的数据提供程序属性](../../adapters-and-accelerators/adapter-siebel/data-provider-properties-for-the-siebel-connection-string.md)。</span><span class="sxs-lookup"><span data-stu-id="3696e-118">For more information about the connection string properties, see [Data provider properties for the Siebel connection string](../../adapters-and-accelerators/adapter-siebel/data-provider-properties-for-the-siebel-connection-string.md).</span></span>  
  
     <span data-ttu-id="3696e-119">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="3696e-119">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="3696e-120">在**选择目标**对话框中：</span><span class="sxs-lookup"><span data-stu-id="3696e-120">In the **Choose a Destination** dialog box:</span></span>  
  
    1.  <span data-ttu-id="3696e-121">从**目标**下拉列表中，选择**SQL Native Client**。</span><span class="sxs-lookup"><span data-stu-id="3696e-121">From the **Destination** drop-down list, select **SQL Native Client**.</span></span>  
  
    2.  <span data-ttu-id="3696e-122">从**服务器名称**下拉列表中，选择 SQL Server 名称。</span><span class="sxs-lookup"><span data-stu-id="3696e-122">From the **Server name** drop-down list, select a SQL Server name.</span></span>  
  
    3.  <span data-ttu-id="3696e-123">选择身份验证模式。</span><span class="sxs-lookup"><span data-stu-id="3696e-123">Select an authentication mode.</span></span>  
  
    4.  <span data-ttu-id="3696e-124">从**数据库**下拉列表中，选择你想要导入 Siebel 表的数据库。</span><span class="sxs-lookup"><span data-stu-id="3696e-124">From the **Database** drop-down list, select the database to which you want to import the Siebel table.</span></span>  
  
    5.  <span data-ttu-id="3696e-125">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="3696e-125">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="3696e-126">在**指定表复制或查询**对话框框中，选择**编写查询以指定要传输的数据**选项。</span><span class="sxs-lookup"><span data-stu-id="3696e-126">In the **Specify Table Copy or Query** dialog box, choose the **Write a query to specify the data to transfer** option.</span></span>  
  
7.  <span data-ttu-id="3696e-127">在**提供源查询**对话框框中，指定 SELECT 查询来筛选要导入到 SQL Server 的数据。</span><span class="sxs-lookup"><span data-stu-id="3696e-127">In the **Provide a Source Query** dialog box, specify a SELECT query to filter the data to be imported into the SQL Server.</span></span> <span data-ttu-id="3696e-128">有关语法的详细信息，以进行 SELECT 查询[!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)]，请参阅[为 Siebel 中 SELECT 语句的语法](../../adapters-and-accelerators/adapter-siebel/syntax-for-a-select-statement-in-siebel.md)。</span><span class="sxs-lookup"><span data-stu-id="3696e-128">For more information about the grammar for a SELECT query for the [!INCLUDE[adoprovidersiebelshort](../../includes/adoprovidersiebelshort-md.md)], see [Syntax for a SELECT Statement in Siebel](../../adapters-and-accelerators/adapter-siebel/syntax-for-a-select-statement-in-siebel.md).</span></span>  
  
8.  <span data-ttu-id="3696e-129">若要验证查询，请单击**分析**菜单上，单击**确定**在弹出对话框中，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="3696e-129">To validate the query, click the **Parse** button, click **OK** in the pop-up dialog box, and then click **Next**.</span></span>  
  
9. <span data-ttu-id="3696e-130">在**选择源表和源视图**对话框框中，选中针对源和目标表的复选框。</span><span class="sxs-lookup"><span data-stu-id="3696e-130">In the **Select Source Tables and Views** dialog box, select the check box against the source and destination tables.</span></span> <span data-ttu-id="3696e-131">源是您指定从 Siebel 检索数据的查询。</span><span class="sxs-lookup"><span data-stu-id="3696e-131">The source is the query you specified to retrieve data from Siebel.</span></span> <span data-ttu-id="3696e-132">目标将是将 SQL Server 数据库中创建的表。</span><span class="sxs-lookup"><span data-stu-id="3696e-132">The destination will be the table that will be created in the SQL Server database.</span></span>  
  
10. <span data-ttu-id="3696e-133">该向导创建的源和目标之间的默认映射表字段。</span><span class="sxs-lookup"><span data-stu-id="3696e-133">The wizard creates a default mapping between the source and destination table fields.</span></span> <span data-ttu-id="3696e-134">但是，你可以根据你的要求更改映射。</span><span class="sxs-lookup"><span data-stu-id="3696e-134">However, you can change the mappings according to your requirement.</span></span> <span data-ttu-id="3696e-135">若要更改的字段映射，请单击**编辑映射**。</span><span class="sxs-lookup"><span data-stu-id="3696e-135">To change the field mappings, click **Edit Mappings**.</span></span>  
  
11. <span data-ttu-id="3696e-136">在**列映射**对话框中，你可以：</span><span class="sxs-lookup"><span data-stu-id="3696e-136">In the **Column Mappings** dialog box, you can:</span></span>  
  
    -   <span data-ttu-id="3696e-137">更改目标表中的列的名称。</span><span class="sxs-lookup"><span data-stu-id="3696e-137">Change the names of columns in the destination table.</span></span>  
  
    -   <span data-ttu-id="3696e-138">忽略目标表中的某些列。</span><span class="sxs-lookup"><span data-stu-id="3696e-138">Ignore certain columns in the destination table.</span></span>  
  
    -   <span data-ttu-id="3696e-139">更改目标表中的字段的数据类型。</span><span class="sxs-lookup"><span data-stu-id="3696e-139">Change the data type for fields in destination table.</span></span>  
  
    -   <span data-ttu-id="3696e-140">更改其他字段属性，如可以为 null，大小、 精度和小数位数。</span><span class="sxs-lookup"><span data-stu-id="3696e-140">Change other field attributes such as nullable, size, precision, and scale.</span></span>  
  
    -   <span data-ttu-id="3696e-141">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="3696e-141">Click **OK**.</span></span>  
  
     <span data-ttu-id="3696e-142">![Siebel 和 SQL 表之间的列映射](../../adapters-and-accelerators/adapter-siebel/media/a3047801-3fa6-496b-91d8-3888dfbb0169.gif "a3047801-3fa6-496b-91d8-3888dfbb0169")</span><span class="sxs-lookup"><span data-stu-id="3696e-142">![Column mappings between Siebel and SQL table](../../adapters-and-accelerators/adapter-siebel/media/a3047801-3fa6-496b-91d8-3888dfbb0169.gif "a3047801-3fa6-496b-91d8-3888dfbb0169")</span></span>  
  
12. <span data-ttu-id="3696e-143">在**选择源表和源视图**对话框中，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="3696e-143">In the **Select Source Tables and Views** dialog box, click **Next**.</span></span>  
  
13. <span data-ttu-id="3696e-144">在**完成向导**对话框框中，检查的操作，该向导将执行，然后单击摘要**完成**。</span><span class="sxs-lookup"><span data-stu-id="3696e-144">In the **Complete the Wizard** dialog box, review the summary of actions that the wizard will perform, and then click **Finish**.</span></span>  
  
14. <span data-ttu-id="3696e-145">在**执行操作**对话框中，向导开始执行任务以将信息从 Siebel 导入 SQL Server 数据库表。</span><span class="sxs-lookup"><span data-stu-id="3696e-145">In the **Performing Operations** dialog box, the wizard starts executing tasks to import the information from Siebel into a SQL Server database table.</span></span> <span data-ttu-id="3696e-146">在向导中显示每个任务的状态。</span><span class="sxs-lookup"><span data-stu-id="3696e-146">The status for each task is displayed in the wizard.</span></span>  
  
15. <span data-ttu-id="3696e-147">已成功执行所有任务后，单击**关闭**。</span><span class="sxs-lookup"><span data-stu-id="3696e-147">After all the tasks are successfully executed, click **Close**.</span></span> <span data-ttu-id="3696e-148">如果任务失败，请参阅相应的错误消息、 修复该问题，并重新运行该向导。</span><span class="sxs-lookup"><span data-stu-id="3696e-148">If a task fails, see the corresponding error message, fix the issue, and rerun the wizard.</span></span>  
  
16. <span data-ttu-id="3696e-149">向导将 SSIS 包添加到你的集成服务项目。</span><span class="sxs-lookup"><span data-stu-id="3696e-149">The wizard adds an SSIS package to your Integration Service project.</span></span> <span data-ttu-id="3696e-150">保存集成服务项目。</span><span class="sxs-lookup"><span data-stu-id="3696e-150">Save the Integration Service project.</span></span>  
  
## <a name="running-the-ssis-package"></a><span data-ttu-id="3696e-151">运行 SSIS 包</span><span class="sxs-lookup"><span data-stu-id="3696e-151">Running the SSIS Package</span></span>  
 <span data-ttu-id="3696e-152">在集成服务项目内创建包后，你可以执行它从 Siebel 系统到 SQL Server 数据库导入数据。</span><span class="sxs-lookup"><span data-stu-id="3696e-152">Once the package is created within an Integration Service project, you can execute it to import data from a Siebel system into a SQL Server database.</span></span> <span data-ttu-id="3696e-153">执行以下步骤 Siebel 数据导入通过执行包。</span><span class="sxs-lookup"><span data-stu-id="3696e-153">Perform the following steps to import Siebel data by executing the package.</span></span>  
  
#### <a name="to-run-the-package-from-visual-studio"></a><span data-ttu-id="3696e-154">若要从 Visual Studio 运行包</span><span class="sxs-lookup"><span data-stu-id="3696e-154">To run the package from Visual Studio</span></span>  
  
1.  <span data-ttu-id="3696e-155">导航到解决方案资源管理器中的 SSIS 包。</span><span class="sxs-lookup"><span data-stu-id="3696e-155">Navigate to the SSIS package in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="3696e-156">右键单击包名称，然后选择**执行包**。</span><span class="sxs-lookup"><span data-stu-id="3696e-156">Right-click the package name, and then select **Execute Package**.</span></span>  
  
 <span data-ttu-id="3696e-157">有关正在运行的包的详细信息，请参阅"正在运行的包"网址[http://go.microsoft.com/fwlink/?LinkId=94972](http://go.microsoft.com/fwlink/?LinkId=94972)。</span><span class="sxs-lookup"><span data-stu-id="3696e-157">For more information about running packages, see "Running Packages" at [http://go.microsoft.com/fwlink/?LinkId=94972](http://go.microsoft.com/fwlink/?LinkId=94972).</span></span> <span data-ttu-id="3696e-158">有关任何 SSIS 包，与相关的其他信息时，请参阅"包操作指南主题 (SSIS)" [http://go.microsoft.com/fwlink/?LinkId=94973](http://go.microsoft.com/fwlink/?LinkId=94973)。</span><span class="sxs-lookup"><span data-stu-id="3696e-158">For any other information related to SSIS packages, see "Package How-to Topics (SSIS)" at [http://go.microsoft.com/fwlink/?LinkId=94973](http://go.microsoft.com/fwlink/?LinkId=94973).</span></span>  
  
## <a name="verifying-the-results"></a><span data-ttu-id="3696e-159">验证结果</span><span class="sxs-lookup"><span data-stu-id="3696e-159">Verifying the Results</span></span>  
 <span data-ttu-id="3696e-160">后执行包，你必须通过登录到 SQL Server 并导航到 Siebel 数据导入到的数据库验证结果。</span><span class="sxs-lookup"><span data-stu-id="3696e-160">After executing the package, you must verify the results by logging on to the SQL Server and navigating to the database to which the Siebel data is imported.</span></span> <span data-ttu-id="3696e-161">执行包应已创建表目标数据库中。</span><span class="sxs-lookup"><span data-stu-id="3696e-161">Executing the package should have created a table in the destination database.</span></span> <span data-ttu-id="3696e-162">应使用 Siebel 表中的值填充此表。</span><span class="sxs-lookup"><span data-stu-id="3696e-162">This table should be populated with the values from the Siebel table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3696e-163">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3696e-163">See Also</span></span>  
 [<span data-ttu-id="3696e-164">使用用于 Siebel 使用 SSIS 数据提供程序</span><span class="sxs-lookup"><span data-stu-id="3696e-164">Use the Data Provider for Siebel with SSIS</span></span>](../../adapters-and-accelerators/adapter-siebel/use-the-data-provider-for-siebel-with-ssis.md)