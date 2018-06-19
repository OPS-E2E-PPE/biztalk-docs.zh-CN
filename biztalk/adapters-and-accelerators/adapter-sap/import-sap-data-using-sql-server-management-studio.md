---
title: 导入 SAP 数据使用 SQL Server Management Studio |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- importing SAP data, how to
- SQL Server Management Studio, importing data
ms.assetid: c8151c6d-4b33-40fe-9b83-9bed27df9a99
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28981d2130e82a094e470de1e2b6904382be56b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217829"
---
# <a name="import-sap-data-using-sql-server-management-studio"></a><span data-ttu-id="cbeac-102">使用 SQL Server Management Studio 导入 SAP 数据</span><span class="sxs-lookup"><span data-stu-id="cbeac-102">Import SAP Data Using SQL Server Management Studio</span></span>
<span data-ttu-id="cbeac-103">此部分提供有关如何使用 SQL Server Management Studio 从某个 SAP 系统到 SQL Server 数据库导入数据的信息。</span><span class="sxs-lookup"><span data-stu-id="cbeac-103">This section provides information on how to use the SQL Server Management Studio to import data from an SAP system into a SQL Server database.</span></span> <span data-ttu-id="cbeac-104">本部分提供有关如何创建 SSIS 包，您可以执行数据导入指令。</span><span class="sxs-lookup"><span data-stu-id="cbeac-104">This section provides instruction on how to create an SSIS package that you can execute to import data.</span></span> <span data-ttu-id="cbeac-105">本部分还提供有关如何执行 SSIS 包的信息。</span><span class="sxs-lookup"><span data-stu-id="cbeac-105">This section also provides information on how to execute the SSIS package.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cbeac-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="cbeac-106">Prerequisites</span></span>  
 <span data-ttu-id="cbeac-107">执行本主题中提供过程之前，请确保：</span><span class="sxs-lookup"><span data-stu-id="cbeac-107">Before performing the procedures provided in this topic, make sure:</span></span>  
  
-   [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]<span data-ttu-id="cbeac-108">计算机上安装。</span><span class="sxs-lookup"><span data-stu-id="cbeac-108"> is installed on the computer.</span></span>  
  
-   <span data-ttu-id="cbeac-109">在计算机上安装 SQL Server Business Intelligence Development Studio。</span><span class="sxs-lookup"><span data-stu-id="cbeac-109">SQL Server Business Intelligence Development Studio is installed on the computer.</span></span>  
  
### <a name="to-import-data-using-sql-server-management-studio"></a><span data-ttu-id="cbeac-110">若要使用 SQL Server Management Studio 导入数据</span><span class="sxs-lookup"><span data-stu-id="cbeac-110">To import data using SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="cbeac-111">启动 SQL Server Management Studio。</span><span class="sxs-lookup"><span data-stu-id="cbeac-111">Start the SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="cbeac-112">在**连接到服务器**对话框框中，指定的值连接到 SQL Server 数据库并单击**连接**。</span><span class="sxs-lookup"><span data-stu-id="cbeac-112">In the **Connect to Server** dialog box, specify the values to connect to a SQL Server database and click **Connect**.</span></span> <span data-ttu-id="cbeac-113">**Microsoft SQL Server Management Studio**打开。</span><span class="sxs-lookup"><span data-stu-id="cbeac-113">The **Microsoft SQL Server Management Studio** opens.</span></span>  
  
3.  <span data-ttu-id="cbeac-114">在**对象资源管理器**，展开 SQL Server 名称，展开**数据库**，然后右键单击在其中你将会导出表从 SAP 系统数据库。</span><span class="sxs-lookup"><span data-stu-id="cbeac-114">In the **Object Explorer**, expand the SQL Server name, expand **Databases**, and right-click the database into which you will be exporting the tables from the SAP system.</span></span> <span data-ttu-id="cbeac-115">从上下文菜单中，指向**任务**，然后单击**导入数据**。</span><span class="sxs-lookup"><span data-stu-id="cbeac-115">From the context menu, point to **Tasks**, and click **Import Data**.</span></span> <span data-ttu-id="cbeac-116">这将启动**SQL Server 导入和导出向导**。</span><span class="sxs-lookup"><span data-stu-id="cbeac-116">This starts the **SQL Server Import and Export Wizard**.</span></span>  
  
4.  <span data-ttu-id="cbeac-117">阅读欢迎屏幕，然后单击上的信息**下一步**。</span><span class="sxs-lookup"><span data-stu-id="cbeac-117">Read the information on the welcome screen and click **Next**.</span></span>  
  
5.  <span data-ttu-id="cbeac-118">在**选择数据源**对话框中，从**数据源**下拉列表**mySAP Business Suite 的.NET Framework 数据提供程序**。</span><span class="sxs-lookup"><span data-stu-id="cbeac-118">In the **Choose a Data Source** dialog box, from the **Data Source** drop-down list **.NET Framework Data Provider for mySAP Business Suite**.</span></span> <span data-ttu-id="cbeac-119">该对话框列出要连接到 SAP 系统的不同的连接参数。</span><span class="sxs-lookup"><span data-stu-id="cbeac-119">The dialog box lists the different connection parameters to connect to an SAP system.</span></span> <span data-ttu-id="cbeac-120">一个典型的连接字符串以连接到 SAP 系统使用[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]需要：</span><span class="sxs-lookup"><span data-stu-id="cbeac-120">A typical connection string to connect to an SAP system using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] requires:</span></span>  
  
    -   <span data-ttu-id="cbeac-121">连接类型的连接参数。</span><span class="sxs-lookup"><span data-stu-id="cbeac-121">The connection parameters for a connection type.</span></span> <span data-ttu-id="cbeac-122">[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]支持连接类型 A、 B 和 d。若要连接到 SAP 系统必须提供连接参数任何*一个*的这些连接类型。</span><span class="sxs-lookup"><span data-stu-id="cbeac-122">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] supports connection types A, B, and D. To connect to an SAP system you must provide connection parameters for any *one* of these connection types.</span></span> <span data-ttu-id="cbeac-123">例如，对于 A 的连接类型，必须提供应用程序服务器主机和系统编号的名称。</span><span class="sxs-lookup"><span data-stu-id="cbeac-123">For example, for connection type A, you must provide the name of the application server host and the system number.</span></span>  
  
    -   <span data-ttu-id="cbeac-124">要连接到 SAP 系统如用户名和密码的登录信息。</span><span class="sxs-lookup"><span data-stu-id="cbeac-124">The login information to connect to an SAP system such as username and password.</span></span>  
  
     <span data-ttu-id="cbeac-125">有关连接字符串以连接到 SAP 系统使用的详细信息[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，请参阅[SAP 连接字符串中读取有关数据提供程序](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md)。</span><span class="sxs-lookup"><span data-stu-id="cbeac-125">For more information about the connection string to connect to an SAP system using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see [Read about Data Provider for the SAP Connection String](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md).</span></span>  
  
     <span data-ttu-id="cbeac-126">在**选择数据源**对话框框中，指定：</span><span class="sxs-lookup"><span data-stu-id="cbeac-126">In the **Choose a Data Source** dialog box, specify:</span></span>  
  
    -   <span data-ttu-id="cbeac-127">连接类型的参数的任何一个连接。</span><span class="sxs-lookup"><span data-stu-id="cbeac-127">The connection parameters for any one connection type.</span></span>  
  
    -   <span data-ttu-id="cbeac-128">要连接到 SAP 系统的登录信息。</span><span class="sxs-lookup"><span data-stu-id="cbeac-128">The login information to connect to an SAP system.</span></span>  
  
    -   <span data-ttu-id="cbeac-129">是否想要启用 SAP GUI 调试。</span><span class="sxs-lookup"><span data-stu-id="cbeac-129">Whether you want to enable SAP GUI debugging.</span></span>  
  
    -   <span data-ttu-id="cbeac-130">是否想要使用 RFC SDK 跟踪。</span><span class="sxs-lookup"><span data-stu-id="cbeac-130">Whether you want to use RFC SDK tracing.</span></span>  
  
     <span data-ttu-id="cbeac-131">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="cbeac-131">Click **Next**.</span></span>  
  
6.  <span data-ttu-id="cbeac-132">在**选择目标**对话框中：</span><span class="sxs-lookup"><span data-stu-id="cbeac-132">In the **Choose a Destination** dialog box:</span></span>  
  
    1.  <span data-ttu-id="cbeac-133">从**目标**下拉列表中，选择**SQL Native Client**。</span><span class="sxs-lookup"><span data-stu-id="cbeac-133">From the **Destination** drop-down list, select **SQL Native Client**.</span></span>  
  
    2.  <span data-ttu-id="cbeac-134">从**服务器名称**下拉列表中，选择 SQL server 名称。</span><span class="sxs-lookup"><span data-stu-id="cbeac-134">From the **Server name** drop-down list, select a SQL server name.</span></span>  
  
    3.  <span data-ttu-id="cbeac-135">选择身份验证模式。</span><span class="sxs-lookup"><span data-stu-id="cbeac-135">Select an authentication mode.</span></span>  
  
    4.  <span data-ttu-id="cbeac-136">从**数据库**下拉列表中，选择你想要导入 SAP 表的数据库。</span><span class="sxs-lookup"><span data-stu-id="cbeac-136">From the **Database** drop-down list, select the database to which you want to import the SAP table.</span></span>  
  
    5.  <span data-ttu-id="cbeac-137">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="cbeac-137">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="cbeac-138">在**指定表复制或查询**对话框框中，选择**编写查询以指定要传输的数据**选项，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="cbeac-138">In the **Specify Table Copy or Query** dialog box, choose the **Write a query to specify the data to transfer** option and click **Next**.</span></span>  
  
8.  <span data-ttu-id="cbeac-139">在**提供源查询**对话框框中，指定 SELECT 查询来筛选要导入到 SQL Server 的数据。</span><span class="sxs-lookup"><span data-stu-id="cbeac-139">In the **Provide a Source Query** dialog box, specify a SELECT query to filter the data to be imported into the SQL Server.</span></span> <span data-ttu-id="cbeac-140">有关语法的详细信息，以进行 SELECT 查询[!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)]，请参阅[选择语句 SAP 语法](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="cbeac-140">For more information about the grammar for a SELECT query for the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see [Syntax for a SELECT Statement SAP](../../adapters-and-accelerators/adapter-sap/syntax-for-a-select-statement-in-sap.md).</span></span>  
  
     <span data-ttu-id="cbeac-141">单击**分析**按钮以验证查询，并单击**确定**在弹出对话框中。</span><span class="sxs-lookup"><span data-stu-id="cbeac-141">Click the **Parse** button to validate the query and click **OK** in the pop-up dialog box.</span></span> <span data-ttu-id="cbeac-142">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="cbeac-142">Click **Next**.</span></span>  
  
9. <span data-ttu-id="cbeac-143">在**选择源表和源视图**对话框框中，选中针对源和目标表的复选框。</span><span class="sxs-lookup"><span data-stu-id="cbeac-143">In the **Select Source Tables and Views** dialog box, select the check box against the source and destination tables.</span></span> <span data-ttu-id="cbeac-144">源是您指定从 SAP 检索数据的查询。</span><span class="sxs-lookup"><span data-stu-id="cbeac-144">The source is the query you specified to retrieve data from SAP.</span></span> <span data-ttu-id="cbeac-145">目标是将在 SQL Server 数据库中创建的表。</span><span class="sxs-lookup"><span data-stu-id="cbeac-145">The destination is the table that will be created in the SQL Server database.</span></span>  
  
10. <span data-ttu-id="cbeac-146">该向导创建的源和目标之间的默认映射表字段。</span><span class="sxs-lookup"><span data-stu-id="cbeac-146">The wizard creates a default mapping between the source and destination table fields.</span></span> <span data-ttu-id="cbeac-147">但是，你可以根据你的要求更改映射。</span><span class="sxs-lookup"><span data-stu-id="cbeac-147">However, you can change the mappings according to your requirement.</span></span> <span data-ttu-id="cbeac-148">若要更改的字段映射，请单击**编辑映射**。</span><span class="sxs-lookup"><span data-stu-id="cbeac-148">To change the field mappings, click **Edit Mappings**.</span></span>  
  
     <span data-ttu-id="cbeac-149">![SAP 和 SQL 表之间的列映射](../../adapters-and-accelerators/adapter-sap/media/73751f74-4cd0-47c6-85ea-de7f507131a0.gif "73751f74-4cd0-47c6-85ea-de7f507131a0")</span><span class="sxs-lookup"><span data-stu-id="cbeac-149">![Column mappings between SAP and SQL tables](../../adapters-and-accelerators/adapter-sap/media/73751f74-4cd0-47c6-85ea-de7f507131a0.gif "73751f74-4cd0-47c6-85ea-de7f507131a0")</span></span>  
  
11. <span data-ttu-id="cbeac-150">在**列映射**对话框中，你可以：</span><span class="sxs-lookup"><span data-stu-id="cbeac-150">In the **Column Mappings** dialog box, you can:</span></span>  
  
    -   <span data-ttu-id="cbeac-151">更改目标表中的列的名称。</span><span class="sxs-lookup"><span data-stu-id="cbeac-151">Change the names of columns in the destination table.</span></span>  
  
    -   <span data-ttu-id="cbeac-152">忽略目标表中的某些列。</span><span class="sxs-lookup"><span data-stu-id="cbeac-152">Ignore certain columns in the destination table.</span></span>  
  
    -   <span data-ttu-id="cbeac-153">更改目标表中的字段的数据类型。</span><span class="sxs-lookup"><span data-stu-id="cbeac-153">Change the data type for fields in destination table.</span></span>  
  
    -   <span data-ttu-id="cbeac-154">更改其他字段属性，如可以为 null，大小、 精度和小数位数。</span><span class="sxs-lookup"><span data-stu-id="cbeac-154">Change other field attributes such as nullable, size, precision, and scale.</span></span>  
  
    -   <span data-ttu-id="cbeac-155">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="cbeac-155">Click **OK**.</span></span>  
  
12. <span data-ttu-id="cbeac-156">在**选择源表和源视图**对话框中，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="cbeac-156">In the **Select Source Tables and Views** dialog box, click **Next**.</span></span>  
  
13. <span data-ttu-id="cbeac-157">在**保存和执行包**对话框中，</span><span class="sxs-lookup"><span data-stu-id="cbeac-157">In the **Save and Execute Package** dialog box,</span></span>  
  
    -   <span data-ttu-id="cbeac-158">选择**立即执行**复选框，以执行查询。</span><span class="sxs-lookup"><span data-stu-id="cbeac-158">Select the **Execute immediately** check box to execute the query.</span></span>  
  
    -   <span data-ttu-id="cbeac-159">选择**保存 SSIS 包**复选框以将查询另存为包和更高版本执行。</span><span class="sxs-lookup"><span data-stu-id="cbeac-159">Select the **Save SSIS Package** check box to save the query as a package and execute it later.</span></span> <span data-ttu-id="cbeac-160">如果你选择以保存包，你还必须指定是否想要将包保存在 SQL Server 或文件系统。</span><span class="sxs-lookup"><span data-stu-id="cbeac-160">If you chose to save the package, you must also specify whether you want to save the package in the SQL Server or the file system.</span></span>  
  
    -   <span data-ttu-id="cbeac-161">从**包保护级别**下拉列表中，选择保护级别包并指定凭据需要。</span><span class="sxs-lookup"><span data-stu-id="cbeac-161">From the **Package protection level** drop-down list, select a protection level for the package and specify credentials where required.</span></span>  
  
    -   <span data-ttu-id="cbeac-162">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="cbeac-162">Click **Next**.</span></span>  
  
     <span data-ttu-id="cbeac-163">如果你选择以保存包，则继续执行下一步。</span><span class="sxs-lookup"><span data-stu-id="cbeac-163">If you chose to save the package, proceed to next step.</span></span> <span data-ttu-id="cbeac-164">否则，请跳到步骤 15。</span><span class="sxs-lookup"><span data-stu-id="cbeac-164">Otherwise, skip to step 15.</span></span>  
  
14. <span data-ttu-id="cbeac-165">在**保存 SSIS 包**对话框框中，指定：</span><span class="sxs-lookup"><span data-stu-id="cbeac-165">In the **Save SSIS Package** dialog box, specify:</span></span>  
  
    -   <span data-ttu-id="cbeac-166">包名称</span><span class="sxs-lookup"><span data-stu-id="cbeac-166">Name for the package</span></span>  
  
    -   <span data-ttu-id="cbeac-167">程序包描述</span><span class="sxs-lookup"><span data-stu-id="cbeac-167">Description for the package</span></span>  
  
    -   <span data-ttu-id="cbeac-168">如果你选择将包保存到 SQL server，选择从 SQL Server**服务器名称**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="cbeac-168">If you chose to save the package to a SQL server, select a SQL Server from the **Server name** drop-down list.</span></span>  
  
    -   <span data-ttu-id="cbeac-169">如果你选择将包保存到文件系统，指定的名称和位置中的文件**文件名**文本框。</span><span class="sxs-lookup"><span data-stu-id="cbeac-169">If you chose to save the package to the file system, specify the name and location of the file in the **File name** text box.</span></span>  
  
    -   <span data-ttu-id="cbeac-170">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="cbeac-170">Click **Next**.</span></span>  
  
15. <span data-ttu-id="cbeac-171">在**完成向导**对话框框中，查看向导将执行，并单击的操作的摘要**完成**。</span><span class="sxs-lookup"><span data-stu-id="cbeac-171">In the **Complete the Wizard** dialog box, review the summary of actions that the wizard will perform, and click **Finish**.</span></span>  
  
16. <span data-ttu-id="cbeac-172">在**执行操作**对话框中，向导开始执行任务以将信息从 SAP 导入 SQL Server 数据库表。</span><span class="sxs-lookup"><span data-stu-id="cbeac-172">In the **Performing Operations** dialog box, the wizard starts executing tasks to import the information from SAP into a SQL Server database table.</span></span> <span data-ttu-id="cbeac-173">在向导中显示每个任务的状态。</span><span class="sxs-lookup"><span data-stu-id="cbeac-173">The status for each task is displayed in the wizard.</span></span>  
  
17. <span data-ttu-id="cbeac-174">已成功执行所有任务后，单击**关闭**。</span><span class="sxs-lookup"><span data-stu-id="cbeac-174">After all the tasks are successfully executed, click **Close**.</span></span> <span data-ttu-id="cbeac-175">如果任务失败，请参阅相应的错误消息、 修复该问题，并重新运行该向导。</span><span class="sxs-lookup"><span data-stu-id="cbeac-175">If a task fails, see the corresponding error message, fix the issue, and rerun the wizard.</span></span>  
  
## <a name="running-the-ssis-package"></a><span data-ttu-id="cbeac-176">运行 SSIS 包</span><span class="sxs-lookup"><span data-stu-id="cbeac-176">Running the SSIS Package</span></span>  
 <span data-ttu-id="cbeac-177">如果你选择保存 SSIS 包，你可以运行它从 SAP 系统中检索的最新信息。</span><span class="sxs-lookup"><span data-stu-id="cbeac-177">If you chose to save the SSIS package, you can run it to retrieve the most recent information from the SAP system.</span></span> <span data-ttu-id="cbeac-178">此部分提供有关如何运行包，如果你选择将其保存到文件系统信息。</span><span class="sxs-lookup"><span data-stu-id="cbeac-178">This section provides information on how to run the package if you chose to save it to the file system.</span></span>  
  
#### <a name="to-run-the-package-from-windows-explorer"></a><span data-ttu-id="cbeac-179">若要从 Windows 资源管理器运行包</span><span class="sxs-lookup"><span data-stu-id="cbeac-179">To run the package from Windows Explorer</span></span>  
  
1.  <span data-ttu-id="cbeac-180">从**Windows 资源管理器**，导航到保存包的位置，然后双击包。</span><span class="sxs-lookup"><span data-stu-id="cbeac-180">From the **Windows Explorer**, navigate to the location where you saved the package, and double-click the package.</span></span>  
  
2.  <span data-ttu-id="cbeac-181">上**执行包实用工具**对话框中，单击**执行**。</span><span class="sxs-lookup"><span data-stu-id="cbeac-181">On the **Execute Package Utility** dialog box, click **Execute**.</span></span>  
  
3.  <span data-ttu-id="cbeac-182">**包的执行进度**对话框中显示的不同任务的进度。</span><span class="sxs-lookup"><span data-stu-id="cbeac-182">The **Package Execution Progress** dialog box displays the progress of the different tasks.</span></span>  
  
4.  <span data-ttu-id="cbeac-183">已成功执行所有任务后，单击**关闭**。</span><span class="sxs-lookup"><span data-stu-id="cbeac-183">After all the tasks are successfully executed, click **Close**.</span></span>  
  
5.  <span data-ttu-id="cbeac-184">上**执行包实用工具**对话框中，单击**关闭**。</span><span class="sxs-lookup"><span data-stu-id="cbeac-184">On the **Execute Package Utility** dialog box, click **Close**.</span></span>  
  
 <span data-ttu-id="cbeac-185">有关正在运行的包的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=94972](http://go.microsoft.com/fwlink/?LinkId=94972)。</span><span class="sxs-lookup"><span data-stu-id="cbeac-185">For more information about running packages, see [http://go.microsoft.com/fwlink/?LinkId=94972](http://go.microsoft.com/fwlink/?LinkId=94972).</span></span> <span data-ttu-id="cbeac-186">有关相关的 SSIS 包的任何其他信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=94973](http://go.microsoft.com/fwlink/?LinkId=94973)。</span><span class="sxs-lookup"><span data-stu-id="cbeac-186">For any other information related to SSIS packages, see [http://go.microsoft.com/fwlink/?LinkId=94973](http://go.microsoft.com/fwlink/?LinkId=94973).</span></span>  
  
## <a name="verifying-the-results"></a><span data-ttu-id="cbeac-187">验证结果</span><span class="sxs-lookup"><span data-stu-id="cbeac-187">Verifying the Results</span></span>  
 <span data-ttu-id="cbeac-188">后执行包，你必须通过转到 SAP 数据导入到的 SQL Server 数据库来验证结果。</span><span class="sxs-lookup"><span data-stu-id="cbeac-188">After executing the package, you must verify the results by going to the SQL Server database to which the SAP data is imported.</span></span> <span data-ttu-id="cbeac-189">执行包应已在目标数据库中创建一个表并使用 SAP 表中的值填充。</span><span class="sxs-lookup"><span data-stu-id="cbeac-189">Executing the package should have created a table in destination database and populated with the values from the SAP table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbeac-190">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cbeac-190">See Also</span></span>  
 [<span data-ttu-id="cbeac-191">使用 Data Provider for SSIS 与 SAP</span><span class="sxs-lookup"><span data-stu-id="cbeac-191">Using the Data Provider for SAP with SSIS</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssis.md)