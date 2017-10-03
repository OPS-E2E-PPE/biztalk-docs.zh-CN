---
title: "导入使用 Visual Studio 的 SAP 数据 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- importing SAP data, how to
- importing SAP data, using Visual Studio
- Visual Studio, importing SAP data
ms.assetid: 70cce089-232d-4ab9-81bd-6b0d6f0097d7
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1295f763815872bacedf2262f7c022d6813bd75
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="import-sap-data-using-visual-studio"></a><span data-ttu-id="a3063-102">使用 Visual Studio 的导入 SAP 数据</span><span class="sxs-lookup"><span data-stu-id="a3063-102">Import SAP Data Using Visual Studio</span></span>
<span data-ttu-id="a3063-103">本部分提供有关如何使用 Microsoft 的信息[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]从某个 SAP 系统到 SQL Server 数据库导入数据。</span><span class="sxs-lookup"><span data-stu-id="a3063-103">This section provides information on how to use Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] to import data from an SAP system into a SQL Server database.</span></span> <span data-ttu-id="a3063-104">本部分提供有关如何创建 SSIS 包，您可以执行数据导入指令。</span><span class="sxs-lookup"><span data-stu-id="a3063-104">This section provides instruction on how to create an SSIS package that you can execute to import data.</span></span> <span data-ttu-id="a3063-105">本部分还提供有关如何执行 SSIS 包的信息。</span><span class="sxs-lookup"><span data-stu-id="a3063-105">This section also provides information on how to execute the SSIS package.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a3063-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="a3063-106">Prerequisites</span></span>  
 <span data-ttu-id="a3063-107">执行本主题中提供过程之前，请确保：</span><span class="sxs-lookup"><span data-stu-id="a3063-107">Before performing the procedures provided in this topic, make sure:</span></span>  
  
-   [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]<span data-ttu-id="a3063-108">计算机上安装。</span><span class="sxs-lookup"><span data-stu-id="a3063-108"> is installed on the computer.</span></span>  
  
-   [!INCLUDE[btsVStudio2008](../../includes/btsvstudio2008-md.md)]<span data-ttu-id="a3063-109">计算机上安装。</span><span class="sxs-lookup"><span data-stu-id="a3063-109"> is installed on the computer.</span></span>  
  
### <a name="to-import-data-using-visual-studio"></a><span data-ttu-id="a3063-110">若要使用 Visual Studio 导入数据</span><span class="sxs-lookup"><span data-stu-id="a3063-110">To import data using Visual Studio</span></span>  
  
1.  <span data-ttu-id="a3063-111">启动[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]并创建一个集成服务项目。</span><span class="sxs-lookup"><span data-stu-id="a3063-111">Start [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and create an Integration Service project.</span></span>  
  
2.  <span data-ttu-id="a3063-112">从**项目**菜单上，选择**SSIS 导入和导出向导**。</span><span class="sxs-lookup"><span data-stu-id="a3063-112">From the **Project** menu, select **SSIS Import and Export Wizard**.</span></span> <span data-ttu-id="a3063-113">这将启动**SQL Server 导入和导出向导**。</span><span class="sxs-lookup"><span data-stu-id="a3063-113">This starts the **SQL Server Import and Export Wizard**.</span></span>  
  
3.  <span data-ttu-id="a3063-114">阅读欢迎屏幕，然后单击上的信息**下一步**。</span><span class="sxs-lookup"><span data-stu-id="a3063-114">Read the information on the welcome screen and click **Next**.</span></span>  
  
4.  <span data-ttu-id="a3063-115">在**选择数据源**对话框中，从**数据源**下拉列表**mySAP Business Suite 的.NET Framework 数据提供程序**。</span><span class="sxs-lookup"><span data-stu-id="a3063-115">In the **Choose a Data Source** dialog box, from the **Data Source** drop-down list **.NET Framework Data Provider for mySAP Business Suite**.</span></span> <span data-ttu-id="a3063-116">该对话框列出要连接到 SAP 系统的不同的连接参数。</span><span class="sxs-lookup"><span data-stu-id="a3063-116">The dialog box lists the different connection parameters to connect to an SAP system.</span></span> <span data-ttu-id="a3063-117">一个典型的连接字符串以连接到 SAP 系统使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]需要：</span><span class="sxs-lookup"><span data-stu-id="a3063-117">A typical connection string to connect to an SAP system using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] requires:</span></span>  
  
    -   <span data-ttu-id="a3063-118">连接类型的连接参数。</span><span class="sxs-lookup"><span data-stu-id="a3063-118">The connection parameters for a connection type.</span></span> <span data-ttu-id="a3063-119">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]支持连接类型 A、 B 和 d。若要连接到 SAP 系统必须提供连接参数任何*一个*的这些连接类型。</span><span class="sxs-lookup"><span data-stu-id="a3063-119">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] supports connection types A, B, and D. To connect to an SAP system you must provide connection parameters for any *one* of these connection types.</span></span> <span data-ttu-id="a3063-120">例如，对于 A 的连接类型，必须提供应用程序服务器主机和系统编号的名称。</span><span class="sxs-lookup"><span data-stu-id="a3063-120">For example, for connection type A, you must provide the name of the application server host and the system number.</span></span>  
  
    -   <span data-ttu-id="a3063-121">要连接到 SAP 系统如用户名和密码的登录信息。</span><span class="sxs-lookup"><span data-stu-id="a3063-121">The login information to connect to an SAP system such as username and password.</span></span>  
  
     <span data-ttu-id="a3063-122">有关连接字符串以连接到 SAP 系统使用的详细信息[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，请参阅[SAP 连接字符串中读取有关数据提供程序](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)。</span><span class="sxs-lookup"><span data-stu-id="a3063-122">For more information about the connection string to connect to an SAP system using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see [Read about Data Provider for the SAP Connection String](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md).</span></span>  
  
     <span data-ttu-id="a3063-123">在**选择数据源**对话框框中，指定：</span><span class="sxs-lookup"><span data-stu-id="a3063-123">In the **Choose a Data Source** dialog box, specify:</span></span>  
  
    -   <span data-ttu-id="a3063-124">连接类型的参数的任何一个连接。</span><span class="sxs-lookup"><span data-stu-id="a3063-124">The connection parameters for any one connection type.</span></span>  
  
    -   <span data-ttu-id="a3063-125">要连接到 SAP 系统的登录信息。</span><span class="sxs-lookup"><span data-stu-id="a3063-125">The login information to connect to an SAP system.</span></span>  
  
    -   <span data-ttu-id="a3063-126">是否想要启用 SAP GUI 调试。</span><span class="sxs-lookup"><span data-stu-id="a3063-126">Whether you want to enable SAP GUI debugging.</span></span>  
  
    -   <span data-ttu-id="a3063-127">是否想要使用 RFC SDK 跟踪。</span><span class="sxs-lookup"><span data-stu-id="a3063-127">Whether you want to use RFC SDK tracing.</span></span>  
  
     <span data-ttu-id="a3063-128">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="a3063-128">Click **Next**.</span></span>  
  
5.  <span data-ttu-id="a3063-129">在**选择目标**对话框中：</span><span class="sxs-lookup"><span data-stu-id="a3063-129">In the **Choose a Destination** dialog box:</span></span>  
  
    1.  <span data-ttu-id="a3063-130">从**目标**下拉列表中，选择**SQL Native Client**。</span><span class="sxs-lookup"><span data-stu-id="a3063-130">From the **Destination** drop-down list, select **SQL Native Client**.</span></span>  
  
    2.  <span data-ttu-id="a3063-131">从**服务器名称**下拉列表中，选择 SQL server 名称。</span><span class="sxs-lookup"><span data-stu-id="a3063-131">From the **Server name** drop-down list, select a SQL server name.</span></span>  
  
    3.  <span data-ttu-id="a3063-132">选择身份验证模式。</span><span class="sxs-lookup"><span data-stu-id="a3063-132">Select an authentication mode.</span></span>  
  
    4.  <span data-ttu-id="a3063-133">从**数据库**下拉列表中，选择你想要导入 SAP 表的数据库。</span><span class="sxs-lookup"><span data-stu-id="a3063-133">From the **Database** drop-down list, select the database to which you want to import the SAP table.</span></span>  
  
    5.  <span data-ttu-id="a3063-134">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="a3063-134">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="a3063-135">在**指定表复制或查询**对话框框中，选择**编写查询以指定要传输的数据**选项，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="a3063-135">In the **Specify Table Copy or Query** dialog box, choose the **Write a query to specify the data to transfer** option and click **Next**.</span></span>  
  
7.  <span data-ttu-id="a3063-136">在**提供源查询**对话框框中，指定 SELECT 查询来筛选要导入到 SQL Server 的数据。</span><span class="sxs-lookup"><span data-stu-id="a3063-136">In the **Provide a Source Query** dialog box, specify a SELECT query to filter the data to be imported into the SQL Server.</span></span> <span data-ttu-id="a3063-137">有关语法的详细信息，以进行 SELECT 查询[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，请参阅[为 SAP 中 SELECT 语句的语法](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="a3063-137">For more information about the grammar for a SELECT query for the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see [Syntax for a SELECT Statement in SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md).</span></span>  
  
     <span data-ttu-id="a3063-138">单击**分析**按钮以验证查询，并单击**确定**在弹出对话框中。</span><span class="sxs-lookup"><span data-stu-id="a3063-138">Click the **Parse** button to validate the query and click **OK** in the pop-up dialog box.</span></span> <span data-ttu-id="a3063-139">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="a3063-139">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="a3063-140">在**选择源表和源视图**对话框框中，选中针对源和目标表的复选框。</span><span class="sxs-lookup"><span data-stu-id="a3063-140">In the **Select Source Tables and Views** dialog box, select the check box against the source and destination tables.</span></span> <span data-ttu-id="a3063-141">源是您指定从 SAP 检索数据的查询。</span><span class="sxs-lookup"><span data-stu-id="a3063-141">The source is the query you specified to retrieve data from SAP.</span></span> <span data-ttu-id="a3063-142">目标是将在 SQL Server 数据库中创建的表。</span><span class="sxs-lookup"><span data-stu-id="a3063-142">The destination is the table that will be created in the SQL Server database.</span></span>  
  
9. <span data-ttu-id="a3063-143">该向导创建的源和目标之间的默认映射表字段。</span><span class="sxs-lookup"><span data-stu-id="a3063-143">The wizard creates a default mapping between the source and destination table fields.</span></span> <span data-ttu-id="a3063-144">但是，你可以根据你的要求更改映射。</span><span class="sxs-lookup"><span data-stu-id="a3063-144">However, you can change the mappings according to your requirement.</span></span> <span data-ttu-id="a3063-145">若要更改的字段映射，请单击**编辑映射**。</span><span class="sxs-lookup"><span data-stu-id="a3063-145">To change the field mappings, click **Edit Mappings**.</span></span>  
  
     <span data-ttu-id="a3063-146">![SAP 和 SQL 表之间的列映射](../../adapters-and-accelerators/adapter-sap/media/73751f74-4cd0-47c6-85ea-de7f507131a0.gif "73751f74-4cd0-47c6-85ea-de7f507131a0")</span><span class="sxs-lookup"><span data-stu-id="a3063-146">![Column mappings between SAP and SQL tables](../../adapters-and-accelerators/adapter-sap/media/73751f74-4cd0-47c6-85ea-de7f507131a0.gif "73751f74-4cd0-47c6-85ea-de7f507131a0")</span></span>  
  
10. <span data-ttu-id="a3063-147">在**列映射**对话框中，你可以：</span><span class="sxs-lookup"><span data-stu-id="a3063-147">In the **Column Mappings** dialog box, you can:</span></span>  
  
    -   <span data-ttu-id="a3063-148">更改目标表中的列的名称。</span><span class="sxs-lookup"><span data-stu-id="a3063-148">Change the names of columns in the destination table.</span></span>  
  
    -   <span data-ttu-id="a3063-149">忽略目标表中的某些列。</span><span class="sxs-lookup"><span data-stu-id="a3063-149">Ignore certain columns in the destination table.</span></span>  
  
    -   <span data-ttu-id="a3063-150">更改目标表中的字段的数据类型。</span><span class="sxs-lookup"><span data-stu-id="a3063-150">Change the data type for fields in destination table.</span></span>  
  
    -   <span data-ttu-id="a3063-151">更改其他字段属性，如可以为 null，大小、 精度和小数位数。</span><span class="sxs-lookup"><span data-stu-id="a3063-151">Change other field attributes such as nullable, size, precision, and scale.</span></span>  
  
    -   <span data-ttu-id="a3063-152">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="a3063-152">Click **OK**.</span></span>  
  
11. <span data-ttu-id="a3063-153">在**选择源表和源视图**对话框中，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="a3063-153">In the **Select Source Tables and Views** dialog box, click **Next**.</span></span>  
  
12. <span data-ttu-id="a3063-154">在**完成向导**对话框框中，查看向导将执行，并单击的操作的摘要**完成**。</span><span class="sxs-lookup"><span data-stu-id="a3063-154">In the **Complete the Wizard** dialog box, review the summary of actions that the wizard will perform, and click **Finish**.</span></span>  
  
13. <span data-ttu-id="a3063-155">在**执行操作**对话框中，向导开始执行任务以将信息从 SAP 导入 SQL Server 数据库表。</span><span class="sxs-lookup"><span data-stu-id="a3063-155">In the **Performing Operation** dialog box, the wizard starts executing tasks to import the information from SAP into a SQL Server database table.</span></span> <span data-ttu-id="a3063-156">在向导中显示每个任务的状态。</span><span class="sxs-lookup"><span data-stu-id="a3063-156">The status for each task is displayed in the wizard.</span></span>  
  
14. <span data-ttu-id="a3063-157">已成功执行所有任务后，单击**关闭**。</span><span class="sxs-lookup"><span data-stu-id="a3063-157">After all the tasks are successfully executed, click **Close**.</span></span> <span data-ttu-id="a3063-158">如果任务失败，请参阅相应的错误消息、 修复该问题，并重新运行该向导。</span><span class="sxs-lookup"><span data-stu-id="a3063-158">If a task fails, see the corresponding error message, fix the issue, and rerun the wizard.</span></span>  
  
15. <span data-ttu-id="a3063-159">向导将 SSIS 包添加到你的集成服务项目。</span><span class="sxs-lookup"><span data-stu-id="a3063-159">The wizard adds an SSIS package to your Integration Service project.</span></span> <span data-ttu-id="a3063-160">保存集成服务项目。</span><span class="sxs-lookup"><span data-stu-id="a3063-160">Save the Integration Service project.</span></span>  
  
## <a name="running-the-ssis-package"></a><span data-ttu-id="a3063-161">运行 SSIS 包</span><span class="sxs-lookup"><span data-stu-id="a3063-161">Running the SSIS Package</span></span>  
 <span data-ttu-id="a3063-162">在集成服务项目内创建包后，你可以执行它从某个 SAP 系统到 SQL Server 数据库导入数据。</span><span class="sxs-lookup"><span data-stu-id="a3063-162">Once the package is created within an Integration Service project, you can execute it to import data from an SAP system into a SQL Server database.</span></span> <span data-ttu-id="a3063-163">执行以下步骤来导入 SAP 数据执行包。</span><span class="sxs-lookup"><span data-stu-id="a3063-163">Perform the following steps to import SAP data by executing the package.</span></span>  
  
#### <a name="to-run-the-package-from-visual-studio"></a><span data-ttu-id="a3063-164">若要从 Visual Studio 运行包</span><span class="sxs-lookup"><span data-stu-id="a3063-164">To run the package from Visual Studio</span></span>  
  
1.  <span data-ttu-id="a3063-165">导航到解决方案资源管理器中的 SSIS 包。</span><span class="sxs-lookup"><span data-stu-id="a3063-165">Navigate to the SSIS package in the Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="a3063-166">右键单击包名称并选择**执行包**。</span><span class="sxs-lookup"><span data-stu-id="a3063-166">Right-click the package name and select **Execute Package**.</span></span>  
  
 <span data-ttu-id="a3063-167">有关正在运行的包的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=94972](http://go.microsoft.com/fwlink/?LinkId=94972)。</span><span class="sxs-lookup"><span data-stu-id="a3063-167">For more information about running packages, see [http://go.microsoft.com/fwlink/?LinkId=94972](http://go.microsoft.com/fwlink/?LinkId=94972).</span></span> <span data-ttu-id="a3063-168">有关相关的 SSIS 包的任何其他信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=94973](http://go.microsoft.com/fwlink/?LinkId=94973)。</span><span class="sxs-lookup"><span data-stu-id="a3063-168">For any other information related to SSIS packages, see [http://go.microsoft.com/fwlink/?LinkId=94973](http://go.microsoft.com/fwlink/?LinkId=94973).</span></span>  
  
## <a name="verifying-the-results"></a><span data-ttu-id="a3063-169">验证结果</span><span class="sxs-lookup"><span data-stu-id="a3063-169">Verifying the Results</span></span>  
 <span data-ttu-id="a3063-170">后执行包，你必须通过登录到 SQL Server 并导航到 SAP 数据导入到的数据库验证结果。</span><span class="sxs-lookup"><span data-stu-id="a3063-170">After executing the package, you must verify the results by logging on to the SQL Server and navigating to the database to which the SAP data is imported.</span></span> <span data-ttu-id="a3063-171">执行包应已在目标数据库中创建一个表并使用 SAP 表中的值填充。</span><span class="sxs-lookup"><span data-stu-id="a3063-171">Executing the package should have created a table in destination database and populated with the values from the SAP table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3063-172">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a3063-172">See Also</span></span>  
 [<span data-ttu-id="a3063-173">为 SAP 使用 SSIS 中使用的数据提供程序</span><span class="sxs-lookup"><span data-stu-id="a3063-173">Use the Data Provider for SAP with SSIS</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssis.md)