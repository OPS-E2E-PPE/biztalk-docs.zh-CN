---
title: 插入、 更新、 删除或在 SQL 中使用 WCF 服务模型中选择操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 340048ad-ce28-4acf-ae4e-f18bdb3b6f47
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dcf58b5ff9a379b7b28647e0d5b07475d08310db
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011164"
---
# <a name="insert-update-delete-or-select-operations-in-sql-using-the-wcf-service-model"></a><span data-ttu-id="8f0e8-102">插入、 更新、 删除或在 SQL 中使用 WCF 服务模型中选择操作</span><span class="sxs-lookup"><span data-stu-id="8f0e8-102">Insert, update, delete, or select operations in SQL using the WCF service model</span></span>
<span data-ttu-id="8f0e8-103">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]发现一组基本的 Insert、 Select、 Update 和 Delete 操作上 SQL Server 数据库表和视图。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-103">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] discovers a set of basic Insert, Select, Update, and Delete operations on SQL Server database tables and views.</span></span> <span data-ttu-id="8f0e8-104">通过使用这些操作，你可以执行简单 SQL Insert、 Select、 Update 和 Delete 语句限定由 Where 子句对目标表或视图。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-104">By using these operations, you can perform simple SQL Insert, Select, Update, and Delete statements qualified by a Where clause on a target table or view.</span></span> <span data-ttu-id="8f0e8-105">本主题将说明了如何使用 WCF 服务模型执行这些操作。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-105">This topic provides instructions on how to perform these operations using the WCF service model.</span></span>  
  
 <span data-ttu-id="8f0e8-106">适配器如何支持这些操作的详细信息，请参阅[Insert、 Update、 Delete 和选择操作对表和视图与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/insert-update-delete-and-select-on-tables-and-views-with-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-106">For more information on how the adapter supports these operations, see [Insert, Update, Delete, and Select Operations on Tables and Views with the SQL adapter](../../adapters-and-accelerators/adapter-sql/insert-update-delete-and-select-on-tables-and-views-with-the-sql-adapter.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8f0e8-107">如果您正在执行对具有用户定义类型的列的表操作，请确保您参考[对表和视图使用 SQL 适配器的用户定义类型的操作](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md)开始开发应用程序之前。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-107">If you are performing operation on tables that have columns of user-defined types, make sure you refer to [Operations on Tables and Views with User-Defined Types using the SQL adapter](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md) before you start developing your application.</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="8f0e8-108">有关使用在本主题中的示例</span><span class="sxs-lookup"><span data-stu-id="8f0e8-108">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="8f0e8-109">本主题中的示例执行在 Employee 表上的操作。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-109">The example in this topic performs operations on the Employee table.</span></span> <span data-ttu-id="8f0e8-110">通过运行这些示例提供的 SQL 脚本创建员工表。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-110">The Employee table is created by running the SQL script provided with the samples.</span></span> <span data-ttu-id="8f0e8-111">有关示例的详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-111">For more information about samples, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span> <span data-ttu-id="8f0e8-112">示例中， **EmployeeBasicOps**，后者基于本主题中，还提供与[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-112">A sample, **EmployeeBasicOps**, which is based on this topic, is also provided with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] samples.</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="8f0e8-113">WCF 客户端类</span><span class="sxs-lookup"><span data-stu-id="8f0e8-113">The WCF Client Class</span></span>  
 <span data-ttu-id="8f0e8-114">WCF 客户端生成的基本 SQL 操作的名称，[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]可发现下表中列出基于表或视图的名称。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-114">The name of the WCF client generated for the basic SQL operations that the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] discovers is based on the name of the table or view, as listed in the following table.</span></span>  
  
|<span data-ttu-id="8f0e8-115">SQL Server 数据库项目</span><span class="sxs-lookup"><span data-stu-id="8f0e8-115">SQL Server Database Artifact</span></span>|<span data-ttu-id="8f0e8-116">WCF 客户端名称</span><span class="sxs-lookup"><span data-stu-id="8f0e8-116">WCF Client Name</span></span>|  
|----------------------------------|---------------------|  
|<span data-ttu-id="8f0e8-117">表</span><span class="sxs-lookup"><span data-stu-id="8f0e8-117">Table</span></span>|<span data-ttu-id="8f0e8-118">TableOp_[Schema]_[TABLE_NAME]Client</span><span class="sxs-lookup"><span data-stu-id="8f0e8-118">TableOp_[Schema]_[TABLE_NAME]Client</span></span>|  
|<span data-ttu-id="8f0e8-119">“查看”</span><span class="sxs-lookup"><span data-stu-id="8f0e8-119">View</span></span>|<span data-ttu-id="8f0e8-120">ViewOp_[Schema]_[VIEW_NAME]Client</span><span class="sxs-lookup"><span data-stu-id="8f0e8-120">ViewOp_[Schema]_[VIEW_NAME]Client</span></span>|  
  
 <span data-ttu-id="8f0e8-121">[架构] = 集合的 SQL Server 项目;例如，dbo。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-121">[SCHEMA] = Collection of SQL Server artifacts; for example, dbo.</span></span>  
  
 <span data-ttu-id="8f0e8-122">[TABLE_NAME] = 表; 的名称例如，员工。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-122">[TABLE_NAME] = The name of the table; for example, Employee.</span></span>  
  
 <span data-ttu-id="8f0e8-123">[VIEW_NAME] = 视图; 的名称例如，Employee_View。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-123">[VIEW_NAME] = The name of the view; for example, Employee_View.</span></span>  
  
### <a name="method-signature-for-invoking-operations-on-tables"></a><span data-ttu-id="8f0e8-124">调用表操作的方法签名</span><span class="sxs-lookup"><span data-stu-id="8f0e8-124">Method Signature for Invoking Operations on Tables</span></span>  
 <span data-ttu-id="8f0e8-125">下表显示了对表的基本操作的方法签名。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-125">The following table shows the method signatures for the basic operations on a table.</span></span> <span data-ttu-id="8f0e8-126">签名是相同的视图，只不过视图命名空间和名称替换这些表。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-126">The signatures are the same for a view, except that the view namespace and name replace those of the table.</span></span>  
  
|<span data-ttu-id="8f0e8-127">运算</span><span class="sxs-lookup"><span data-stu-id="8f0e8-127">Operation</span></span>|<span data-ttu-id="8f0e8-128">方法签名</span><span class="sxs-lookup"><span data-stu-id="8f0e8-128">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="8f0e8-129">Insert</span><span class="sxs-lookup"><span data-stu-id="8f0e8-129">Insert</span></span>|<span data-ttu-id="8f0e8-130">long[] Insert([TABLE_NS].[TABLE_NAME][] Rows);</span><span class="sxs-lookup"><span data-stu-id="8f0e8-130">long[] Insert([TABLE_NS].[TABLE_NAME][] Rows);</span></span>|  
|<span data-ttu-id="8f0e8-131">选择</span><span class="sxs-lookup"><span data-stu-id="8f0e8-131">Select</span></span>|<span data-ttu-id="8f0e8-132">[TABLE_NS]。[TABLE_NAME][选择 （字符串列，查询字符串）;]</span><span class="sxs-lookup"><span data-stu-id="8f0e8-132">[TABLE_NS].[TABLE_NAME][] Select(string COLUMNS, string QUERY);</span></span>|  
|<span data-ttu-id="8f0e8-133">Update</span><span class="sxs-lookup"><span data-stu-id="8f0e8-133">Update</span></span>|<span data-ttu-id="8f0e8-134">int Update([TABLE_NS].[TABLE_NAME].RowPair[] Rows);</span><span class="sxs-lookup"><span data-stu-id="8f0e8-134">int Update([TABLE_NS].[TABLE_NAME].RowPair[] Rows);</span></span>|  
|<span data-ttu-id="8f0e8-135">DELETE</span><span class="sxs-lookup"><span data-stu-id="8f0e8-135">Delete</span></span>|<span data-ttu-id="8f0e8-136">int Delete ([TABLE_NS]。 [TABLE_NAME] [] 行）;</span><span class="sxs-lookup"><span data-stu-id="8f0e8-136">int Delete([TABLE_NS].[TABLE_NAME][] Rows);</span></span>|  
  
 <span data-ttu-id="8f0e8-137">[TABLE_NS] = 表命名空间; 的名称例如，schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-137">[TABLE_NS] = The name of the table namespace; for example, schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee.</span></span>  
  
 <span data-ttu-id="8f0e8-138">[TABLE_NAME] = 表; 的名称例如，员工。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-138">[TABLE_NAME] = The name of the table; for example, Employee.</span></span>  
  
 <span data-ttu-id="8f0e8-139">例如，下面的代码演示对 Employee 表下的默认"dbo"架构的 Delete、 Insert、 Select 和 Update 操作生成的 WCF 客户端类的方法签名。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-139">As an example, the following code shows the method signatures for a WCF client class generated for the Delete, Insert, Select and Update operations on the Employee table under the default “dbo” schema.</span></span>  
  
```  
public partial class TableOp_dbo_EmployeeClient : System.ServiceModel.ClientBase<TableOp_dbo_Employee>, TableOp_dbo_Employee {      
    public int Delete(schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] Rows);  
  
    public long[] Insert(schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] Rows);  
  
    public schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] Select(string Columns, string Query);  
  
    public int Update(schemas.microsoft.com.Sql._2008._05.TableOp.dbo.Employee.RowPair[] Rows);  
}  
```  
  
 <span data-ttu-id="8f0e8-140">在此代码段，TableOp_dbo_EmployeeClient 是 WCF 中的类的生成的 SqlAdapterBindingClient.cs 名称[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-140">In this snippet, TableOp_dbo_EmployeeClient is the name of the WCF class in the SqlAdapterBindingClient.cs generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
### <a name="parameters-for-table-operations"></a><span data-ttu-id="8f0e8-141">用于表操作的参数</span><span class="sxs-lookup"><span data-stu-id="8f0e8-141">Parameters for Table Operations</span></span>  
 <span data-ttu-id="8f0e8-142">本部分提供了每个表操作所需的参数</span><span class="sxs-lookup"><span data-stu-id="8f0e8-142">This section provides the parameters required by each table operation</span></span>  
  
 <span data-ttu-id="8f0e8-143">**插入操作**</span><span class="sxs-lookup"><span data-stu-id="8f0e8-143">**Insert Operation**</span></span>  
  
|<span data-ttu-id="8f0e8-144">插入操作类型</span><span class="sxs-lookup"><span data-stu-id="8f0e8-144">Insert operation type</span></span>|<span data-ttu-id="8f0e8-145">记录集</span><span class="sxs-lookup"><span data-stu-id="8f0e8-145">RECORDSET</span></span>|  
|---------------------------|---------------|  
|<span data-ttu-id="8f0e8-146">多个记录</span><span class="sxs-lookup"><span data-stu-id="8f0e8-146">Multiple record</span></span>|<span data-ttu-id="8f0e8-147">应插入到表的 INSERTRECORDS 的集合。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-147">A collection of INSERTRECORDS that should be inserted into the table.</span></span>|  
  
 <span data-ttu-id="8f0e8-148">插入操作返回的 Long 数据类型的数组，并将存储插入的行的标识值，如果有。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-148">The insert operation returns an array of Long data type and stores the identity values of the inserted rows, if any.</span></span> <span data-ttu-id="8f0e8-149">如果在表中没有标识列，返回值为 NULL。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-149">If there is no identity column in a table, the return value is NULL.</span></span>  
  
 <span data-ttu-id="8f0e8-150">**选择操作**</span><span class="sxs-lookup"><span data-stu-id="8f0e8-150">**Select Operation**</span></span>  
  
|<span data-ttu-id="8f0e8-151">COLUMN_NAMES</span><span class="sxs-lookup"><span data-stu-id="8f0e8-151">COLUMN_NAMES</span></span>|<span data-ttu-id="8f0e8-152">QUERY</span><span class="sxs-lookup"><span data-stu-id="8f0e8-152">QUERY</span></span>|  
|-------------------|-----------|  
|<span data-ttu-id="8f0e8-153">以逗号分隔的目标; 中的列名称列表例如，"Employee_ID，指定"。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-153">A comma-delimited list of column names in the target; for example, "Employee_ID, Designation".</span></span> <span data-ttu-id="8f0e8-154">列列表中指定的目标应在结果集中返回的列。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-154">The column list specifies the columns of the target that should be returned in the result set.</span></span> <span data-ttu-id="8f0e8-155">未指定列列表中的列将设置为其返回的记录集的.NET 默认值。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-155">Columns not specified in the column list will be set to their .NET default values in the returned record set.</span></span> <span data-ttu-id="8f0e8-156">对于 nillable 列，此值是**null**。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-156">For nillable columns, this value is **null**.</span></span>|<span data-ttu-id="8f0e8-157">指定的查询; 目标行的 SQL WHERE 子句的内容例如，"名称 = Manager"。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-157">The contents of a SQL WHERE clause that specifies the target rows of the query; for example, "Designation = 'Manager'".</span></span> <span data-ttu-id="8f0e8-158">可以将此参数设置为**null**返回目标的所有行。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-158">You can set this parameter to **null** to return all rows of the target.</span></span>|  
  
 <span data-ttu-id="8f0e8-159">选择操作的返回值是强类型化结果集包含指定的列和目标表或视图中的行。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-159">The return value of the Select operation is a strongly-typed result set that contains the specified columns and rows from the target table or view.</span></span>  
  
 <span data-ttu-id="8f0e8-160">**更新操作**</span><span class="sxs-lookup"><span data-stu-id="8f0e8-160">**Update Operation**</span></span>  
  
|<span data-ttu-id="8f0e8-161">该对的第一行</span><span class="sxs-lookup"><span data-stu-id="8f0e8-161">First row of the pair</span></span>|<span data-ttu-id="8f0e8-162">该对的第二行</span><span class="sxs-lookup"><span data-stu-id="8f0e8-162">Second row of the pair</span></span>|  
|---------------------------|----------------------------|  
|<span data-ttu-id="8f0e8-163">对与需要进行更新的新值相对应的记录的第一个记录，即它对应于 UPDATE 语句的 SET 子句。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-163">The first record of the record pair corresponds to new values that need to be updated, that is, it corresponds to the SET clause of the UPDATE statement.</span></span> <span data-ttu-id="8f0e8-164">可以使用设置这`RowPair.After`。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-164">This can be set using `RowPair.After`.</span></span>|<span data-ttu-id="8f0e8-165">记录对的第二个记录对应的行的旧值，也就是说，它对应于 UPDATE 语句的 WHERE 子句。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-165">The second record of the record pair corresponds to the old values of the rows, that is, it corresponds to the WHERE clause of the UPDATE statement.</span></span> <span data-ttu-id="8f0e8-166">可以使用设置这`RowPair.Before`。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-166">This can be set using `RowPair.Before`.</span></span>|  
  
 <span data-ttu-id="8f0e8-167">更新操作的返回值是 Int32 数据类型，表示更新的行数。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-167">The return value of the Update operation is of Int32 data type, and denotes the number of rows updated.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8f0e8-168">同时指定要更新的记录，必须提供值的所有列，即使无法获得更新的所有值。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-168">While specifying the record that has to be updated, you must provide values for all the columns, even if all values are not being updated.</span></span> <span data-ttu-id="8f0e8-169">例如，如果某行具有五个列和更新操作更新仅 2 列作为 RowPair.Before 的一部分，则必须传递所有 5 个列的值。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-169">For example, if a row has five columns and the Update operation updates only 2 columns, as part of RowPair.Before, you must pass all the 5 column values.</span></span> <span data-ttu-id="8f0e8-170">但是，对于 RowPair.After，可以指定仅将更新的列。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-170">However, for RowPair.After, you can specify only the columns that will be updated.</span></span>  
  
 <span data-ttu-id="8f0e8-171">**删除操作**</span><span class="sxs-lookup"><span data-stu-id="8f0e8-171">**Delete Operation**</span></span>  
  
 <span data-ttu-id="8f0e8-172">删除操作将作为强类型的输入数组的记录。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-172">The Delete operation takes as input a strongly-typed array of records.</span></span> <span data-ttu-id="8f0e8-173">删除操作的返回值是 Int32 数据类型，表示删除的行数。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-173">The return value of the Delete operation is of Int32 data type, and denotes the number of rows deleted.</span></span>  
  
## <a name="creating-a-wcf-client-to-invoke-operations-on-tables-and-views"></a><span data-ttu-id="8f0e8-174">创建 WCF 客户端以调用上表和视图的操作</span><span class="sxs-lookup"><span data-stu-id="8f0e8-174">Creating a WCF Client to Invoke Operations on Tables and Views</span></span>  
 <span data-ttu-id="8f0e8-175">通用组对 SQL Server 使用 WCF 客户端执行操作所需的操作涉及到一组任务中所述[与 SQL 适配器的 WCF 服务模型概述](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-service-model-with-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-175">The generic set of actions required to perform an operation on SQL Server using a WCF client involves a set of tasks described in [Overview of the WCF Service Model with the SQL adapter](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-service-model-with-the-sql-adapter.md).</span></span> <span data-ttu-id="8f0e8-176">本部分介绍如何创建 WCF 客户端以调用基本的 Insert、 Select、 Update 对表的删除操作。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-176">This section describes how to create a WCF client to invoke basic Insert, Select, Update, Delete operations on a table.</span></span>  
  
#### <a name="to-create-a-wcf-client-to-perform-operations-on-tables"></a><span data-ttu-id="8f0e8-177">若要创建 WCF 客户端以对表执行操作</span><span class="sxs-lookup"><span data-stu-id="8f0e8-177">To create a WCF client to perform operations on tables</span></span>  
  
1. <span data-ttu-id="8f0e8-178">在 Visual Studio 中创建一个 Visual C# 项目。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-178">Create a Visual C# project in Visual Studio.</span></span> <span data-ttu-id="8f0e8-179">有关本主题中，创建一个控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-179">For this topic, create a console application.</span></span>  
  
2. <span data-ttu-id="8f0e8-180">生成 WCF 客户端类的 Insert、 Select、 Update 和删除 Employee 表上的操作。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-180">Generate the WCF client class for the Insert, Select, Update, and Delete operation on the Employee table.</span></span> <span data-ttu-id="8f0e8-181">有关生成 WCF 客户端类的详细信息，请参阅[为 SQL Server 项目生成 WCF 客户端或 WCF 服务约定](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-181">For more information about generating a WCF client class, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="8f0e8-182">生成 WCF 客户端类之前，请确保设置**EnableBizTalkCompatibilityMode**属性绑定到 false。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-182">Before generating the WCF client class, make sure you set the **EnableBizTalkCompatibilityMode** binding property to false.</span></span>  
  
3. <span data-ttu-id="8f0e8-183">在解决方案资源管理器，添加对引用`Microsoft.Adapters.Sql`和`Microsoft.ServiceModel.Channels`。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-183">In the Solution Explorer, add reference to `Microsoft.Adapters.Sql` and `Microsoft.ServiceModel.Channels`.</span></span>  
  
4. <span data-ttu-id="8f0e8-184">打开 Program.cs 文件，如下面的代码段中所述创建客户端。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-184">Open the Program.cs file and create a client as described in the snippet below.</span></span>  
  
   ```  
  
             TableOp_dbo_EmployeeClient client = new TableOp_dbo_EmployeeClient("SqlAdapterBinding_TableOp_dbo_Employee");  
   client.ClientCredentials.UserName.UserName = "<Enter user name here>";  
   client.ClientCredentials.UserName.Password = "<Enter password here>";  
   ```  
  
    <span data-ttu-id="8f0e8-185">在此代码段，`TableOp_dbo_EmployeeClient`是 SqlAdapterBindingClient.cs 中定义的 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-185">In this snippet, `TableOp_dbo_EmployeeClient` is the WCF client defined in SqlAdapterBindingClient.cs.</span></span> <span data-ttu-id="8f0e8-186">此文件由生成[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-186">This file is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="8f0e8-187">`SqlAdapterBinding_TableOp_dbo_Employee` 客户端终结点配置的名称，并在 app.config 中定义。此文件也由生成[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，其中包含的绑定属性和其他配置设置。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-187">`SqlAdapterBinding_TableOp_dbo_Employee` is the name of the client endpoint configuration and is defined in the app.config. This file is also generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and contains the binding properties and other configuration settings.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="8f0e8-188">在此片段中，您使用的绑定和终结点地址从配置文件。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-188">In this snippet, you use the binding and endpoint address from the configuration file.</span></span> <span data-ttu-id="8f0e8-189">在代码中，可以显式指定这些值。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-189">You can also explicitly specify these values in your code.</span></span> <span data-ttu-id="8f0e8-190">指定客户端绑定的不同方法的详细信息，请参阅[为 SQL 适配器配置客户端绑定](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-190">For more information on the different ways of specifying client binding, see [Configure a Client Binding for the SQL Adapter](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md).</span></span>  
  
5. <span data-ttu-id="8f0e8-191">打开客户端，如下面的代码段中所述：</span><span class="sxs-lookup"><span data-stu-id="8f0e8-191">Open the client as described in the snippet below:</span></span>  
  
   ```  
   try  
   {  
      Console.WriteLine("Opening Client...");  
      client.Open();  
   }  
   catch (Exception ex)  
   {  
      Console.WriteLine("Exception: " + ex.Message);  
      throw;  
   }  
   ```  
  
6. <span data-ttu-id="8f0e8-192">调用上的 Employee 表的插入操作。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-192">Invoke the Insert operation on the Employee table.</span></span>  
  
   ```  
   long[] recordsInserted;  
  
   schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] insertRecord =  
   new schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[1];  
  
   insertRecord[0] = new schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee();  
   insertRecord[0].Name = "John Smith";  
   insertRecord[0].Designation = "Manager";  
   insertRecord[0].Salary = 500000;  
  
   try  
   {  
      Console.WriteLine("Inserting new table entry...");  
      recordsInserted = client.Insert(insertRecord);  
   }  
   catch (Exception ex)  
   {  
      Console.WriteLine("Exception: " + ex.Message);  
      throw;  
   }  
  
   Console.WriteLine("Record inserted");  
   Console.WriteLine("Press any key to continue ...");  
   Console.ReadLine();  
   ```  
  
    <span data-ttu-id="8f0e8-193">您可以替换上述代码段中执行 Select、 Update 或 Delete 操作。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-193">You can replace the preceding code snippet to perform Select, Update, or Delete operations as well.</span></span> <span data-ttu-id="8f0e8-194">也可以附加代码片段，可在单个应用程序中执行所有操作。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-194">You can also append the code snippets to perform all operation in a single application.</span></span> <span data-ttu-id="8f0e8-195">有关如何执行这些操作的代码片段。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-195">For code snippets on how to perform these operations.</span></span>  
  
7. <span data-ttu-id="8f0e8-196">关闭客户端，如下面的代码段中所述：</span><span class="sxs-lookup"><span data-stu-id="8f0e8-196">Close the client as described in the snippet below:</span></span>  
  
   ```  
   client.Close();  
   Console.WriteLine("Press any key to exit...");  
   Console.ReadLine();  
   ```  
  
8. <span data-ttu-id="8f0e8-197">生成项目，然后运行它。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-197">Build the project and then run it.</span></span> <span data-ttu-id="8f0e8-198">应用程序在 Employee 表中插入一条记录。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-198">The application inserts a record in the Employee table.</span></span>  
  
###   <a name="select-operation"></a><span data-ttu-id="8f0e8-199">选择操作</span><span class="sxs-lookup"><span data-stu-id="8f0e8-199">Select Operation</span></span>  
 <span data-ttu-id="8f0e8-200">下面的代码演示了面向 Employee 表的选择操作。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-200">The following code shows a Select operation that targets the Employee table.</span></span> <span data-ttu-id="8f0e8-201">选择操作选择插入到表中的最后一个记录。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-201">The Select operation selects the last record inserted into the table.</span></span> <span data-ttu-id="8f0e8-202">返回的记录写入到控制台中。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-202">The returned records are written to the console.</span></span>  
  
```  
schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] selectRecords;  
  
try  
{  
   Console.WriteLine("Selecting Row...");  
   selectRecords = client.Select("*", "where [Employee_ID] = (select IDENT_CURRENT('Employee'))");  
}  
  
catch (Exception ex)  
{  
   Console.WriteLine("Exception: " + ex.Message);  
   throw;  
}  
  
Console.WriteLine("The details of the newly added employee are:");  
Console.WriteLine("********************************************");  
for (int i = 0; i < selectRecords.Length; i++)  
{  
   Console.WriteLine("Employee ID        : " + selectRecords[i].Employee_ID);  
   Console.WriteLine("Employee Name      : " + selectRecords[i].Name);  
   Console.WriteLine("Employee Desigation: " + selectRecords[i].Designation);  
   Console.WriteLine();  
}  
Console.WriteLine("********************************************");  
Console.WriteLine("Press any key to continue ...");  
Console.ReadLine();  
```  
  
###   <a name="update-operation"></a><span data-ttu-id="8f0e8-203">更新操作</span><span class="sxs-lookup"><span data-stu-id="8f0e8-203">Update Operation</span></span>  
 <span data-ttu-id="8f0e8-204">下面的代码演示了面向 Employee 表的更新操作。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-204">The following code shows an Update operation that targets the Employee table.</span></span>  
  
```  
int result;  
  
schemas.microsoft.com.Sql._2008._05.TableOp.dbo.Employee.RowPair updateRecordPair =  
   new schemas.microsoft.com.Sql._2008._05.TableOp.dbo.Employee.RowPair();  
  
schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee updateRecord =   
   new schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee();  
  
schemas.microsoft.com.Sql._2008._05.TableOp.dbo.Employee.RowPair[] updateArray =  
   new schemas.microsoft.com.Sql._2008._05.TableOp.dbo.Employee.RowPair[1];  
  
updateRecord = insertRecord[0];  
updateRecord.Name = "Jeff Smith";  
  
updateRecordPair.After = updateRecord;  
updateRecordPair.Before = selectRecords[0];  
  
updateArray[0] = updateRecordPair;  
  
try  
{  
   Console.WriteLine("Updating the database...");  
   result = client.Update(updateArray);  
}  
catch (Exception ex)  
{  
   Console.WriteLine("Exception: " + ex.Message);  
   throw;  
}  
  
Console.WriteLine("Updated Record for {0}", updateRecordPair.Before.Name);  
Console.WriteLine("The new name for the employee is {0}", updateRecordPair.After.Name);  
Console.WriteLine("Press any key to continue ...");  
Console.ReadLine();  
```  
  
###   <a name="delete-operation"></a><span data-ttu-id="8f0e8-205">删除操作</span><span class="sxs-lookup"><span data-stu-id="8f0e8-205">Delete Operation</span></span>  
 <span data-ttu-id="8f0e8-206">下面的代码演示的删除操作的目标的 Employee 表。</span><span class="sxs-lookup"><span data-stu-id="8f0e8-206">The following code shows a Delete operation that targets the Employee table.</span></span>  
  
```  
int deleteSuccess;  
  
schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] deleteRecords =  
   new schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[1];  
  
deleteRecords = client.Select("*", "where [Employee_ID] = (select IDENT_CURRENT('Employee'))");  
  
Console.WriteLine("Following employees will be deleted from the database:");  
for (int i = 0; i < deleteRecords.Length; i++)  
{  
   Console.WriteLine("Name: {0}", deleteRecords[i].Name);  
}  
Console.WriteLine("Press any key to begin deletion...");  
Console.ReadLine();  
  
try  
{  
   Console.WriteLine("Deleting employee record...");  
   deleteSuccess = client.Delete(deleteRecords);  
}  
  
catch (Exception ex)  
{  
   Console.WriteLine("Exception: " + ex.Message);  
   throw;  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="8f0e8-207">请参阅</span><span class="sxs-lookup"><span data-stu-id="8f0e8-207">See Also</span></span>  
[<span data-ttu-id="8f0e8-208">使用 WCF 服务模型开发应用程序</span><span class="sxs-lookup"><span data-stu-id="8f0e8-208">Develop applications using the WCF Service model</span></span>](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)