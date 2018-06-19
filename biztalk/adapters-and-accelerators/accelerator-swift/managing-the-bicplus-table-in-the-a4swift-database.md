---
title: 管理 A4SWIFT 数据库中的 Bicplus 表 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Bank Identifier Code (BIC), Bicplus table
- A4SWIFT database, Bicplus table
- Bicplus table
ms.assetid: a255cdea-5ed4-4481-97f1-8425877a76d6
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a58396a9dd6627f2913da8e3845a99b17cf7698
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25962099"
---
# <a name="managing-the-bicplus-table-in-the-a4swift-database"></a><span data-ttu-id="7e313-102">管理 A4SWIFT 数据库中的 Bicplus 表</span><span class="sxs-lookup"><span data-stu-id="7e313-102">Managing the Bicplus Table in the A4SWIFT Database</span></span>
[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]<span data-ttu-id="7e313-103">使用 BIC 条目的表来执行 BIC 验证。</span><span class="sxs-lookup"><span data-stu-id="7e313-103"> uses a table of BIC entries to perform BIC validation.</span></span> <span data-ttu-id="7e313-104">此表可以是中的 Bicplus 表[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]数据库或自定义数据库表。</span><span class="sxs-lookup"><span data-stu-id="7e313-104">This table can be either the Bicplus table in the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] database or a table in a custom database.</span></span>  
  
 <span data-ttu-id="7e313-105">若要管理此表，必须使用从 SWIFT BIC 值填充。</span><span class="sxs-lookup"><span data-stu-id="7e313-105">To manage this table, you must populate it with BIC values from SWIFT.</span></span> <span data-ttu-id="7e313-106">如果你使用自定义数据库，必须还将导出中的 SQL 视图[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]到自定义数据库的数据库。</span><span class="sxs-lookup"><span data-stu-id="7e313-106">If you use a custom database, you must also export SQL views in the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] database into the custom database.</span></span>  
  
## <a name="importing-bic-data-from-the-swift-bicplus-database"></a><span data-ttu-id="7e313-107">从 SWIFT Bicplus 数据库导入 BIC 数据</span><span class="sxs-lookup"><span data-stu-id="7e313-107">Importing BIC data from the SWIFT Bicplus database</span></span>  
 <span data-ttu-id="7e313-108">你必须填充 BIC 条目 （默认值或自定义的表） 中 SWIFT BIC 值的表。</span><span class="sxs-lookup"><span data-stu-id="7e313-108">You must populate the table of BIC entries (either the default or the custom table) with BIC values from SWIFT.</span></span> <span data-ttu-id="7e313-109">SWIFT BIC 数据可用于[!INCLUDE[btsExcel](../../includes/btsexcel-md.md)]电子表格或每月更新 Oracle 数据库中。</span><span class="sxs-lookup"><span data-stu-id="7e313-109">The SWIFT BIC data is available in an [!INCLUDE[btsExcel](../../includes/btsexcel-md.md)] spreadsheet or in an Oracle database that is updated monthly.</span></span> <span data-ttu-id="7e313-110">SWIFT BIC 数据有关的详细信息，请转到[http://go.microsoft.com/fwlink/?LinkId=27885](http://go.microsoft.com/fwlink/?LinkId=27885)。</span><span class="sxs-lookup"><span data-stu-id="7e313-110">For more information about SWIFT BIC data, go to [http://go.microsoft.com/fwlink/?LinkId=27885](http://go.microsoft.com/fwlink/?LinkId=27885).</span></span>  
  
 <span data-ttu-id="7e313-111">如果你使用自定义数据库，必须将 BIC 数据从 SWIFT Bicplus 数据库导出到自定义的数据库。</span><span class="sxs-lookup"><span data-stu-id="7e313-111">If you use a custom database, you must export BIC data from the SWIFT Bicplus database into the custom database.</span></span> <span data-ttu-id="7e313-112">你必须</span><span class="sxs-lookup"><span data-stu-id="7e313-112">You must</span></span>  
  
 <span data-ttu-id="7e313-113">你可以将数据从 BIC [!INCLUDE[btsExcel](../../includes/btsexcel-md.md)] SWIFT Bicplus 表中提供的电子表格[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]数据库，因为它们互相兼容。</span><span class="sxs-lookup"><span data-stu-id="7e313-113">You can import data from the BIC [!INCLUDE[btsExcel](../../includes/btsexcel-md.md)] spreadsheet provided by SWIFT into the Bicplus table in the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] database, because they are compatible.</span></span> <span data-ttu-id="7e313-114">如果你导入数据从 SWIFT 电子表格到非[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]数据库，请确保字段和数据库，尤其是 BIC 列中的列与 SWIFT 电子表格兼容。</span><span class="sxs-lookup"><span data-stu-id="7e313-114">If you import the data from the SWIFT spreadsheet into a non-[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] database, make sure that the fields and columns in your database, particularly the BIC column, are compatible with the SWIFT spreadsheet.</span></span>  
  
 <span data-ttu-id="7e313-115">在其发布 SWIFT 表中的代码更新目标表时，导入操作不会删除任何未发布的 BIC 代码。</span><span class="sxs-lookup"><span data-stu-id="7e313-115">The import operation does not remove any unpublished BIC codes when it updates the destination table with the codes published in the SWIFT table.</span></span>  
  
 <span data-ttu-id="7e313-116">向的 Bicplus 表所做的更改[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]数据库登录[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]日志文件。</span><span class="sxs-lookup"><span data-stu-id="7e313-116">The changes made to the Bicplus table of the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] database are logged in the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] log file.</span></span>  
  
#### <a name="to-import-bic-data-from-the-swift-bicplus-database"></a><span data-ttu-id="7e313-117">若要从 SWIFT Bicplus 数据库导入 BIC 数据</span><span class="sxs-lookup"><span data-stu-id="7e313-117">To import BIC data from the SWIFT Bicplus database</span></span>  
  
1.  <span data-ttu-id="7e313-118">单击**启动**，指向**所有程序**，指向 inistalled 版本的 SQL Server，然后单击**SQL Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="7e313-118">Click **Start**, point to **All Programs**, point to the inistalled version of SQL Server, and then click **SQL Server Management Studio**.</span></span>  
  
2.  <span data-ttu-id="7e313-119">在连接到服务器对话框中，单击**连接**。</span><span class="sxs-lookup"><span data-stu-id="7e313-119">In the Connect to Server dialog box, click **Connect**.</span></span>  
  
3.  <span data-ttu-id="7e313-120">在 Microsoft SQL Server Management Studio 窗口中，展开服务器节点，然后**数据库**。</span><span class="sxs-lookup"><span data-stu-id="7e313-120">In the Microsoft SQL Server Management Studio window, expand your server node, and then **Databases**.</span></span>  
  
4.  <span data-ttu-id="7e313-121">右键单击**A4SWIFT**，指向**任务**，然后单击**导入数据**。</span><span class="sxs-lookup"><span data-stu-id="7e313-121">Right-click **A4SWIFT**, point to **Tasks**, and then click **Import Data**.</span></span>  
  
5.  <span data-ttu-id="7e313-122">在 SQL Server 导入和导出向导欢迎页上，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7e313-122">On the SQL Server Import and Export Wizard welcome page, click **Next**.</span></span>  
  
6.  <span data-ttu-id="7e313-123">上**选择数据源**页上，如果从 SWIFT Bicplus 导入 BIC 数据[!INCLUDE[btsExcel](../../includes/btsexcel-md.md)]电子表格中，选择**Microsoft Excel**中**数据源**文本框。</span><span class="sxs-lookup"><span data-stu-id="7e313-123">On the **Choose a Data Source** page, if importing BIC data from the SWIFT Bicplus [!INCLUDE[btsExcel](../../includes/btsexcel-md.md)] spreadsheet, select **Microsoft Excel** in the **Data Source** text box.</span></span> <span data-ttu-id="7e313-124">浏览到的位置电子表格中，然后选择电子表格中的文件名称**Excel 文件路径**文本框。</span><span class="sxs-lookup"><span data-stu-id="7e313-124">Browse to the location of the spreadsheet, and select the file name of the spreadsheet in the **Excel file path** text box.</span></span> <span data-ttu-id="7e313-125">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="7e313-125">Click **Next**.</span></span>  
  
     <span data-ttu-id="7e313-126">如果 BIC 数据导入从 Oracle 数据库中，选择**Microsoft ODBC Driver for Oracle**中**数据源**文本框。</span><span class="sxs-lookup"><span data-stu-id="7e313-126">If importing BIC data from the Oracle database, select **Microsoft ODBC Driver for Oracle** in the **Data Source** text box.</span></span> <span data-ttu-id="7e313-127">输入与 Oracle 数据库的用户名和密码以连接到该服务器，然后单击所需的服务器**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7e313-127">Enter the server with the Oracle database, and the user name and password required to connect to that server, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="7e313-128">上**选择目标**页上，确认**Microsoft OLE DB Provider for SQL Server**中输入**目标**文本框中，且**使用Windows 身份验证**选择。</span><span class="sxs-lookup"><span data-stu-id="7e313-128">On the **Choose a Destination** page, verify that **Microsoft OLE DB Provider for SQL Server** is entered in the **Destination** text box, and that **Use Windows Authentication** is selected.</span></span> <span data-ttu-id="7e313-129">如果您在安装中的 Bicplus 表[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]数据库，请验证**A4SWIFT**中输入**数据库**文本框。</span><span class="sxs-lookup"><span data-stu-id="7e313-129">If you are populating the Bicplus table in the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] database, verify that **A4SWIFT** is entered in the **Database** text box.</span></span> <span data-ttu-id="7e313-130">如果你使用的是自定义的数据库，请输入在该数据库的名称**数据库**文本框。</span><span class="sxs-lookup"><span data-stu-id="7e313-130">If you are using a custom database, enter the name of that database in the **Database** text box.</span></span> <span data-ttu-id="7e313-131">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="7e313-131">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="7e313-132">上**选择表复制或查询**页上，确认**将数据从一个或多个表或视图复制**选择。</span><span class="sxs-lookup"><span data-stu-id="7e313-132">On the **Select Table Copy or Query** page, verify that **Copy data from one or more tables or views** is selected.</span></span> <span data-ttu-id="7e313-133">如果你需要使用查询来指定数据，请选择**编写查询以指定要传输的数据**。</span><span class="sxs-lookup"><span data-stu-id="7e313-133">If you need to use a query to specify the data, select **Write a query to specify the data to transfer**.</span></span> <span data-ttu-id="7e313-134">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="7e313-134">Click **Next**.</span></span>  
  
9. <span data-ttu-id="7e313-135">上**选择源表和源视图**页上，单击**Bicplus**中**源**列中，选择**Bicplus**中**目标**列，，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7e313-135">On the **Select Source Tables and Views** page, click **Bicplus** in the **Source** column, select **Bicplus** in the **Destination** column, and then click **Next**.</span></span>  
  
10. <span data-ttu-id="7e313-136">上**保存和执行包**页上，输入适当的计划信息，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="7e313-136">On the **Save and Execute Package** page, enter the appropriate schedule information, and then click **Next**.</span></span>  
  
11. <span data-ttu-id="7e313-137">上**完成向导**页上，查看摘要，然后单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="7e313-137">On the **Complete the Wizard** page, review the summary and then click **Finish**.</span></span>  
  
## <a name="importing-sql-views-from-the-a4swift-database-into-a-custom-database"></a><span data-ttu-id="7e313-138">将 SQL 视图从 A4SWIFT 数据库导入自定义数据库</span><span class="sxs-lookup"><span data-stu-id="7e313-138">Importing SQL views from the A4SWIFT database into a Custom Database</span></span>  
 <span data-ttu-id="7e313-139">[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]安装程序将安装中的两个 SQL 视图[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]数据库。</span><span class="sxs-lookup"><span data-stu-id="7e313-139">The [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] setup program installs two SQL views in the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] database.</span></span> <span data-ttu-id="7e313-140">其中一个视图是为 8 个字符 BICs 和另一个是 11 个字符 BICs 有关。</span><span class="sxs-lookup"><span data-stu-id="7e313-140">One view is for eight-character BICs and the other is for 11-character BICs.</span></span>  
  
 <span data-ttu-id="7e313-141">如果使用自定义数据库，而不是[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]数据库，你必须将这些 SQL 视图导入自定义的数据库。</span><span class="sxs-lookup"><span data-stu-id="7e313-141">If you use a custom database instead of the [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] database, you must importing these SQL views into the custom database.</span></span> <span data-ttu-id="7e313-142">通过在查询分析器执行 CreateBICViews.sql 脚本执行此操作。</span><span class="sxs-lookup"><span data-stu-id="7e313-142">You do so by executing the CreateBICViews.sql script in the Query Analyzer.</span></span> <span data-ttu-id="7e313-143">此脚本位于\<*驱动器*\>: files\microsoft BizTalk Accelerator for SWIFT/脚本。</span><span class="sxs-lookup"><span data-stu-id="7e313-143">This script is in \<*drive*\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT/Scripts.</span></span>  
  
#### <a name="to-import-sql-views-from-the-a4swift-database-into-a-custom-database"></a><span data-ttu-id="7e313-144">若要将 SQL 视图从 A4SWIFT 数据库导入自定义数据库</span><span class="sxs-lookup"><span data-stu-id="7e313-144">To import SQL views from the A4SWIFT database into a custom database</span></span>  
  
1.  <span data-ttu-id="7e313-145">在 Windows 资源管理器，移动到\<*驱动器*\>: files\microsoft BizTalk Accelerator for SWIFT\Scripts。</span><span class="sxs-lookup"><span data-stu-id="7e313-145">In Windows Explorer, move to \<*drive*\>:\Program Files\Microsoft BizTalk Accelerator for SWIFT\Scripts.</span></span> <span data-ttu-id="7e313-146">双击**CreateBICViews.sql**。</span><span class="sxs-lookup"><span data-stu-id="7e313-146">Double-click **CreateBICViews.sql**.</span></span>  
  
2.  <span data-ttu-id="7e313-147">在连接到服务器对话框中，单击**连接**。</span><span class="sxs-lookup"><span data-stu-id="7e313-147">In the Connect to Server dialog box, click **Connect**.</span></span>  
  
3.  <span data-ttu-id="7e313-148">在 Microsoft SQL Server Management Studio 窗口中，选择**A4SWIFT**在数据库文本框中。</span><span class="sxs-lookup"><span data-stu-id="7e313-148">In the Microsoft SQL Server Management Studio window, select **A4SWIFT** in the database text box.</span></span>  
  
4.  <span data-ttu-id="7e313-149">在查询窗格中，如果名为"Bicplus"以外的表中存储了 BICs，查找**dbo。Bicplus**视图中**dbo。Bic11**，并将它更改为适当的表名称。</span><span class="sxs-lookup"><span data-stu-id="7e313-149">In the query pane, if you are storing BICs in a table that is named other than "Bicplus", find **dbo.Bicplus** in the view **dbo.Bic11**, and change it to the appropriate table name.</span></span> <span data-ttu-id="7e313-150">为视图执行相同的**dbo。Bic8**。</span><span class="sxs-lookup"><span data-stu-id="7e313-150">Do the same for the view **dbo.Bic8**.</span></span>  
  
5.  <span data-ttu-id="7e313-151">如果名为"BIC"以外的列中存储了 BICs，查找**BIC**中**选择**，**其中**，和**ORDER BY**子句，并将其更改为相应的列名称。</span><span class="sxs-lookup"><span data-stu-id="7e313-151">If you are storing BICs in a column that is named other than "BIC", find **BIC** in the **SELECT**, **WHERE**, and **ORDER BY** clauses, and change it to the appropriate column name.</span></span>  
  
6.  <span data-ttu-id="7e313-152">单击 **“执行”**。</span><span class="sxs-lookup"><span data-stu-id="7e313-152">Click **Execute**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e313-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7e313-153">See Also</span></span>  
 [<span data-ttu-id="7e313-154">启用银行标识代码验证</span><span class="sxs-lookup"><span data-stu-id="7e313-154">Enabling Validation of Bank Identifier Codes</span></span>](../../adapters-and-accelerators/accelerator-swift/enabling-validation-of-bank-identifier-codes.md)