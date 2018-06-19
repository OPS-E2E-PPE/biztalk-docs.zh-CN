---
title: 插入、 更新、 删除或选择中使用 WCF 服务模型的 SQL 操作 |Microsoft 文档
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
ms.openlocfilehash: d2bc522a1b0b60a9ba0b8407228dd1db65c4e6f0
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
ms.locfileid: "22226085"
---
# <a name="insert-update-delete-or-select-operations-in-sql-using-the-wcf-service-model"></a><span data-ttu-id="2c58a-102">插入、 更新、 删除或选择中使用 WCF 服务模型的 SQL 操作</span><span class="sxs-lookup"><span data-stu-id="2c58a-102">Insert, update, delete, or select operations in SQL using the WCF service model</span></span>
<span data-ttu-id="2c58a-103">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]发现一组的 SQL Server 数据库表和视图的基本 Insert、 Select、 Update 和 Delete 操作。</span><span class="sxs-lookup"><span data-stu-id="2c58a-103">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] discovers a set of basic Insert, Select, Update, and Delete operations on SQL Server database tables and views.</span></span> <span data-ttu-id="2c58a-104">通过使用这些操作，你可以执行简单的 SQL Insert、 Select、 Update 和 Delete 语句由 Where 限定目标表或视图上的子句。</span><span class="sxs-lookup"><span data-stu-id="2c58a-104">By using these operations, you can perform simple SQL Insert, Select, Update, and Delete statements qualified by a Where clause on a target table or view.</span></span> <span data-ttu-id="2c58a-105">本主题将说明了如何使用 WCF 服务模型执行这些操作。</span><span class="sxs-lookup"><span data-stu-id="2c58a-105">This topic provides instructions on how to perform these operations using the WCF service model.</span></span>  
  
 <span data-ttu-id="2c58a-106">有关如何的适配器支持这些操作的详细信息，请参阅[插入、 更新、 删除和选择操作对表和视图与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/insert-update-delete-and-select-on-tables-and-views-with-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="2c58a-106">For more information on how the adapter supports these operations, see [Insert, Update, Delete, and Select Operations on Tables and Views with the SQL adapter](../../adapters-and-accelerators/adapter-sql/insert-update-delete-and-select-on-tables-and-views-with-the-sql-adapter.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2c58a-107">如果您正在执行包含的用户定义类型的列的表上的操作，请确保您参考[对表和视图使用了 SQL 适配器的用户定义类型的操作](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md)开始开发你的应用程序之前。</span><span class="sxs-lookup"><span data-stu-id="2c58a-107">If you are performing operation on tables that have columns of user-defined types, make sure you refer to [Operations on Tables and Views with User-Defined Types using the SQL adapter](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md) before you start developing your application.</span></span>  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="2c58a-108">有关在本主题中使用的示例</span><span class="sxs-lookup"><span data-stu-id="2c58a-108">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="2c58a-109">本主题中的示例对执行操作员工表。</span><span class="sxs-lookup"><span data-stu-id="2c58a-109">The example in this topic performs operations on the Employee table.</span></span> <span data-ttu-id="2c58a-110">员工表是通过运行这些示例使用提供的 SQL 脚本创建的。</span><span class="sxs-lookup"><span data-stu-id="2c58a-110">The Employee table is created by running the SQL script provided with the samples.</span></span> <span data-ttu-id="2c58a-111">有关示例的详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="2c58a-111">For more information about samples, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span> <span data-ttu-id="2c58a-112">示例中， **EmployeeBasicOps**，后者基于本主题中，还提供了与[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="2c58a-112">A sample, **EmployeeBasicOps**, which is based on this topic, is also provided with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] samples.</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="2c58a-113">WCF 客户端类</span><span class="sxs-lookup"><span data-stu-id="2c58a-113">The WCF Client Class</span></span>  
 <span data-ttu-id="2c58a-114">WCF 客户端生成的基本 SQL 操作的名称，[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]发现基于名称的表或视图，如以下表中列出。</span><span class="sxs-lookup"><span data-stu-id="2c58a-114">The name of the WCF client generated for the basic SQL operations that the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] discovers is based on the name of the table or view, as listed in the following table.</span></span>  
  
|<span data-ttu-id="2c58a-115">SQL Server 数据库项目</span><span class="sxs-lookup"><span data-stu-id="2c58a-115">SQL Server Database Artifact</span></span>|<span data-ttu-id="2c58a-116">WCF 客户端名称</span><span class="sxs-lookup"><span data-stu-id="2c58a-116">WCF Client Name</span></span>|  
|----------------------------------|---------------------|  
|<span data-ttu-id="2c58a-117">表</span><span class="sxs-lookup"><span data-stu-id="2c58a-117">Table</span></span>|<span data-ttu-id="2c58a-118">TableOp_[Schema]_[TABLE_NAME]Client</span><span class="sxs-lookup"><span data-stu-id="2c58a-118">TableOp_[Schema]_[TABLE_NAME]Client</span></span>|  
|<span data-ttu-id="2c58a-119">视图</span><span class="sxs-lookup"><span data-stu-id="2c58a-119">View</span></span>|<span data-ttu-id="2c58a-120">ViewOp_[Schema]_[VIEW_NAME]Client</span><span class="sxs-lookup"><span data-stu-id="2c58a-120">ViewOp_[Schema]_[VIEW_NAME]Client</span></span>|  
  
 <span data-ttu-id="2c58a-121">[架构] = SQL Server 集合项目;例如，dbo。</span><span class="sxs-lookup"><span data-stu-id="2c58a-121">[SCHEMA] = Collection of SQL Server artifacts; for example, dbo.</span></span>  
  
 <span data-ttu-id="2c58a-122">[TABLE_NAME] = 表; 的名称例如，员工。</span><span class="sxs-lookup"><span data-stu-id="2c58a-122">[TABLE_NAME] = The name of the table; for example, Employee.</span></span>  
  
 <span data-ttu-id="2c58a-123">[VIEW_NAME] = 视图; 的名称例如，Employee_View。</span><span class="sxs-lookup"><span data-stu-id="2c58a-123">[VIEW_NAME] = The name of the view; for example, Employee_View.</span></span>  
  
### <a name="method-signature-for-invoking-operations-on-tables"></a><span data-ttu-id="2c58a-124">调用对表的操作的方法签名</span><span class="sxs-lookup"><span data-stu-id="2c58a-124">Method Signature for Invoking Operations on Tables</span></span>  
 <span data-ttu-id="2c58a-125">下表显示对表的基本操作的方法签名。</span><span class="sxs-lookup"><span data-stu-id="2c58a-125">The following table shows the method signatures for the basic operations on a table.</span></span> <span data-ttu-id="2c58a-126">签名是相同的视图，只不过视图命名空间和名称替换那些表。</span><span class="sxs-lookup"><span data-stu-id="2c58a-126">The signatures are the same for a view, except that the view namespace and name replace those of the table.</span></span>  
  
|<span data-ttu-id="2c58a-127">运算</span><span class="sxs-lookup"><span data-stu-id="2c58a-127">Operation</span></span>|<span data-ttu-id="2c58a-128">方法签名</span><span class="sxs-lookup"><span data-stu-id="2c58a-128">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="2c58a-129">Insert</span><span class="sxs-lookup"><span data-stu-id="2c58a-129">Insert</span></span>|<span data-ttu-id="2c58a-130">long[] Insert([TABLE_NS].[TABLE_NAME][] Rows);</span><span class="sxs-lookup"><span data-stu-id="2c58a-130">long[] Insert([TABLE_NS].[TABLE_NAME][] Rows);</span></span>|  
|<span data-ttu-id="2c58a-131">选择</span><span class="sxs-lookup"><span data-stu-id="2c58a-131">Select</span></span>|<span data-ttu-id="2c58a-132">[TABLE_NS].[TABLE_NAME][] Select(string COLUMNS, string QUERY);</span><span class="sxs-lookup"><span data-stu-id="2c58a-132">[TABLE_NS].[TABLE_NAME][] Select(string COLUMNS, string QUERY);</span></span>|  
|<span data-ttu-id="2c58a-133">Update</span><span class="sxs-lookup"><span data-stu-id="2c58a-133">Update</span></span>|<span data-ttu-id="2c58a-134">int Update([TABLE_NS].[TABLE_NAME].RowPair[] Rows);</span><span class="sxs-lookup"><span data-stu-id="2c58a-134">int Update([TABLE_NS].[TABLE_NAME].RowPair[] Rows);</span></span>|  
|<span data-ttu-id="2c58a-135">删除</span><span class="sxs-lookup"><span data-stu-id="2c58a-135">Delete</span></span>|<span data-ttu-id="2c58a-136">int Delete([TABLE_NS].[TABLE_NAME][] Rows);</span><span class="sxs-lookup"><span data-stu-id="2c58a-136">int Delete([TABLE_NS].[TABLE_NAME][] Rows);</span></span>|  
  
 <span data-ttu-id="2c58a-137">[TABLE_NS] = 表命名空间; 的名称例如，schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee。</span><span class="sxs-lookup"><span data-stu-id="2c58a-137">[TABLE_NS] = The name of the table namespace; for example, schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee.</span></span>  
  
 <span data-ttu-id="2c58a-138">[TABLE_NAME] = 表; 的名称例如，员工。</span><span class="sxs-lookup"><span data-stu-id="2c58a-138">[TABLE_NAME] = The name of the table; for example, Employee.</span></span>  
  
 <span data-ttu-id="2c58a-139">例如，下面的代码演示生成的默认"dbo"架构下的员工表上的删除、 插入、 选择和更新操作的 WCF 客户端类的方法签名。</span><span class="sxs-lookup"><span data-stu-id="2c58a-139">As an example, the following code shows the method signatures for a WCF client class generated for the Delete, Insert, Select and Update operations on the Employee table under the default “dbo” schema.</span></span>  
  
```  
public partial class TableOp_dbo_EmployeeClient : System.ServiceModel.ClientBase<TableOp_dbo_Employee>, TableOp_dbo_Employee {      
    public int Delete(schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] Rows);  
  
    public long[] Insert(schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] Rows);  
  
    public schemas.microsoft.com.Sql._2008._05.Types.Tables.dbo.Employee[] Select(string Columns, string Query);  
  
    public int Update(schemas.microsoft.com.Sql._2008._05.TableOp.dbo.Employee.RowPair[] Rows);  
}  
```  
  
 <span data-ttu-id="2c58a-140">在此代码段，TableOp_dbo_EmployeeClient 是 WCF 中的类的生成的 SqlAdapterBindingClient.cs 名称[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2c58a-140">In this snippet, TableOp_dbo_EmployeeClient is the name of the WCF class in the SqlAdapterBindingClient.cs generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
### <a name="parameters-for-table-operations"></a><span data-ttu-id="2c58a-141">参数用于表操作</span><span class="sxs-lookup"><span data-stu-id="2c58a-141">Parameters for Table Operations</span></span>  
 <span data-ttu-id="2c58a-142">本部分提供每个表操作所需的参数</span><span class="sxs-lookup"><span data-stu-id="2c58a-142">This section provides the parameters required by each table operation</span></span>  
  
 <span data-ttu-id="2c58a-143">**插入操作**</span><span class="sxs-lookup"><span data-stu-id="2c58a-143">**Insert Operation**</span></span>  
  
|<span data-ttu-id="2c58a-144">插入操作类型</span><span class="sxs-lookup"><span data-stu-id="2c58a-144">Insert operation type</span></span>|<span data-ttu-id="2c58a-145">记录集</span><span class="sxs-lookup"><span data-stu-id="2c58a-145">RECORDSET</span></span>|  
|---------------------------|---------------|  
|<span data-ttu-id="2c58a-146">多个记录</span><span class="sxs-lookup"><span data-stu-id="2c58a-146">Multiple record</span></span>|<span data-ttu-id="2c58a-147">应插入到表的 INSERTRECORDS 的集合。</span><span class="sxs-lookup"><span data-stu-id="2c58a-147">A collection of INSERTRECORDS that should be inserted into the table.</span></span>|  
  
 <span data-ttu-id="2c58a-148">插入操作返回的长整型数据类型的数组，并将存储插入的行中，标识值，如果有的话。</span><span class="sxs-lookup"><span data-stu-id="2c58a-148">The insert operation returns an array of Long data type and stores the identity values of the inserted rows, if any.</span></span> <span data-ttu-id="2c58a-149">如果表中没有标识列，返回值为 NULL。</span><span class="sxs-lookup"><span data-stu-id="2c58a-149">If there is no identity column in a table, the return value is NULL.</span></span>  
  
 <span data-ttu-id="2c58a-150">**选择操作**</span><span class="sxs-lookup"><span data-stu-id="2c58a-150">**Select Operation**</span></span>  
  
|<span data-ttu-id="2c58a-151">COLUMN_NAMES</span><span class="sxs-lookup"><span data-stu-id="2c58a-151">COLUMN_NAMES</span></span>|<span data-ttu-id="2c58a-152">QUERY</span><span class="sxs-lookup"><span data-stu-id="2c58a-152">QUERY</span></span>|  
|-------------------|-----------|  
|<span data-ttu-id="2c58a-153">以逗号分隔的目标; 中的列名称列表例如，"Employee_ID，指定内容"。</span><span class="sxs-lookup"><span data-stu-id="2c58a-153">A comma-delimited list of column names in the target; for example, "Employee_ID, Designation".</span></span> <span data-ttu-id="2c58a-154">列列表指定应在结果集中返回目标的列。</span><span class="sxs-lookup"><span data-stu-id="2c58a-154">The column list specifies the columns of the target that should be returned in the result set.</span></span> <span data-ttu-id="2c58a-155">未指定列列表中的列将设置为其.NET 默认值中返回的记录集。</span><span class="sxs-lookup"><span data-stu-id="2c58a-155">Columns not specified in the column list will be set to their .NET default values in the returned record set.</span></span> <span data-ttu-id="2c58a-156">对于 nillable 列，此值是**null**。</span><span class="sxs-lookup"><span data-stu-id="2c58a-156">For nillable columns, this value is **null**.</span></span>|<span data-ttu-id="2c58a-157">指定的查询; 的目标行的 SQL WHERE 子句的内容例如，"指定内容 = '经理'"。</span><span class="sxs-lookup"><span data-stu-id="2c58a-157">The contents of a SQL WHERE clause that specifies the target rows of the query; for example, "Designation = 'Manager'".</span></span> <span data-ttu-id="2c58a-158">你可以将此参数设置为**null**返回目标的所有行。</span><span class="sxs-lookup"><span data-stu-id="2c58a-158">You can set this parameter to **null** to return all rows of the target.</span></span>|  
  
 <span data-ttu-id="2c58a-159">选择操作的返回值是一个强类型化结果集包含指定的列和目标表或视图中的行。</span><span class="sxs-lookup"><span data-stu-id="2c58a-159">The return value of the Select operation is a strongly-typed result set that contains the specified columns and rows from the target table or view.</span></span>  
  
 <span data-ttu-id="2c58a-160">**更新操作**</span><span class="sxs-lookup"><span data-stu-id="2c58a-160">**Update Operation**</span></span>  
  
|<span data-ttu-id="2c58a-161">对的第一行</span><span class="sxs-lookup"><span data-stu-id="2c58a-161">First row of the pair</span></span>|<span data-ttu-id="2c58a-162">第二行对</span><span class="sxs-lookup"><span data-stu-id="2c58a-162">Second row of the pair</span></span>|  
|---------------------------|----------------------------|  
|<span data-ttu-id="2c58a-163">对对应于需要可更新的新值的记录的第一个记录，即它对应于 UPDATE 语句的 SET 子句。</span><span class="sxs-lookup"><span data-stu-id="2c58a-163">The first record of the record pair corresponds to new values that need to be updated, that is, it corresponds to the SET clause of the UPDATE statement.</span></span> <span data-ttu-id="2c58a-164">可以使用设置这`RowPair.After`。</span><span class="sxs-lookup"><span data-stu-id="2c58a-164">This can be set using `RowPair.After`.</span></span>|<span data-ttu-id="2c58a-165">记录对的第二个记录对应的行的旧值，即，它对应于 UPDATE 语句的 WHERE 子句。</span><span class="sxs-lookup"><span data-stu-id="2c58a-165">The second record of the record pair corresponds to the old values of the rows, that is, it corresponds to the WHERE clause of the UPDATE statement.</span></span> <span data-ttu-id="2c58a-166">可以使用设置这`RowPair.Before`。</span><span class="sxs-lookup"><span data-stu-id="2c58a-166">This can be set using `RowPair.Before`.</span></span>|  
  
 <span data-ttu-id="2c58a-167">更新操作的返回值是 Int32 数据类型，表示更新的行数。</span><span class="sxs-lookup"><span data-stu-id="2c58a-167">The return value of the Update operation is of Int32 data type, and denotes the number of rows updated.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2c58a-168">时指定包含要更新的记录，你必须在提供值时的所有列，即使所有的值不会被更新。</span><span class="sxs-lookup"><span data-stu-id="2c58a-168">While specifying the record that has to be updated, you must provide values for all the columns, even if all values are not being updated.</span></span> <span data-ttu-id="2c58a-169">例如，如果行具有五个列和更新操作更新仅 2 列作为 RowPair.Before 的一部分，则必须传递所有 5 列的值。</span><span class="sxs-lookup"><span data-stu-id="2c58a-169">For example, if a row has five columns and the Update operation updates only 2 columns, as part of RowPair.Before, you must pass all the 5 column values.</span></span> <span data-ttu-id="2c58a-170">但是，对于 RowPair.After，可以指定仅将更新的列。</span><span class="sxs-lookup"><span data-stu-id="2c58a-170">However, for RowPair.After, you can specify only the columns that will be updated.</span></span>  
  
 <span data-ttu-id="2c58a-171">**删除操作**</span><span class="sxs-lookup"><span data-stu-id="2c58a-171">**Delete Operation**</span></span>  
  
 <span data-ttu-id="2c58a-172">删除操作将作为一个强类型的输入数组的记录。</span><span class="sxs-lookup"><span data-stu-id="2c58a-172">The Delete operation takes as input a strongly-typed array of records.</span></span> <span data-ttu-id="2c58a-173">删除操作的返回值是 Int32 数据类型，表示删除的行数。</span><span class="sxs-lookup"><span data-stu-id="2c58a-173">The return value of the Delete operation is of Int32 data type, and denotes the number of rows deleted.</span></span>  
  
## <a name="creating-a-wcf-client-to-invoke-operations-on-tables-and-views"></a><span data-ttu-id="2c58a-174">创建 WCF 客户端来调用操作对表和视图</span><span class="sxs-lookup"><span data-stu-id="2c58a-174">Creating a WCF Client to Invoke Operations on Tables and Views</span></span>  
 <span data-ttu-id="2c58a-175">泛型的执行 SQL Server 使用 WCF 客户端上的操作所需的操作集涉及到一组任务中所述[与 SQL 适配器的 WCF 服务模型概述](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-service-model-with-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="2c58a-175">The generic set of actions required to perform an operation on SQL Server using a WCF client involves a set of tasks described in [Overview of the WCF Service Model with the SQL adapter](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-service-model-with-the-sql-adapter.md).</span></span> <span data-ttu-id="2c58a-176">本部分介绍如何创建 WCF 客户端来调用基本插入、 选择、 更新表的删除操作。</span><span class="sxs-lookup"><span data-stu-id="2c58a-176">This section describes how to create a WCF client to invoke basic Insert, Select, Update, Delete operations on a table.</span></span>  
  
#### <a name="to-create-a-wcf-client-to-perform-operations-on-tables"></a><span data-ttu-id="2c58a-177">若要创建的 WCF 客户端，以对表执行操作</span><span class="sxs-lookup"><span data-stu-id="2c58a-177">To create a WCF client to perform operations on tables</span></span>  
  
1.  <span data-ttu-id="2c58a-178">在 Visual Studio 中创建 Visual C# 项目。</span><span class="sxs-lookup"><span data-stu-id="2c58a-178">Create a Visual C# project in Visual Studio.</span></span> <span data-ttu-id="2c58a-179">有关本主题中，创建一个控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="2c58a-179">For this topic, create a console application.</span></span>  
  
2.  <span data-ttu-id="2c58a-180">生成 WCF 客户端类插入、 选择、 更新和删除员工表上的操作。</span><span class="sxs-lookup"><span data-stu-id="2c58a-180">Generate the WCF client class for the Insert, Select, Update, and Delete operation on the Employee table.</span></span> <span data-ttu-id="2c58a-181">有关生成 WCF 客户端类的详细信息，请参阅[为 SQL Server 项目生成 WCF 客户端或 WCF 服务协定](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="2c58a-181">For more information about generating a WCF client class, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="2c58a-182">在生成 WCF 客户端类前, 请确保你设置**EnableBizTalkCompatibilityMode**绑定属性为 false。</span><span class="sxs-lookup"><span data-stu-id="2c58a-182">Before generating the WCF client class, make sure you set the **EnableBizTalkCompatibilityMode** binding property to false.</span></span>  
  
3.  <span data-ttu-id="2c58a-183">在解决方案资源管理器，添加对引用`Microsoft.Adapters.Sql`和`Microsoft.ServiceModel.Channels`。</span><span class="sxs-lookup"><span data-stu-id="2c58a-183">In the Solution Explorer, add reference to `Microsoft.Adapters.Sql` and `Microsoft.ServiceModel.Channels`.</span></span>  
  
4.  <span data-ttu-id="2c58a-184">打开 Program.cs 文件并创建客户端，如下面的代码段中所述。</span><span class="sxs-lookup"><span data-stu-id="2c58a-184">Open the Program.cs file and create a client as described in the snippet below.</span></span>  
  
    ```  
  
              TableOp_dbo_EmployeeClient client = new TableOp_dbo_EmployeeClient("SqlAdapterBinding_TableOp_dbo_Employee");  
    client.ClientCredentials.UserName.UserName = "<Enter user name here>";  
    client.ClientCredentials.UserName.Password = "<Enter password here>";  
    ```  
  
     <span data-ttu-id="2c58a-185">在此代码段，`TableOp_dbo_EmployeeClient`是 SqlAdapterBindingClient.cs 中定义的 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="2c58a-185">In this snippet, `TableOp_dbo_EmployeeClient` is the WCF client defined in SqlAdapterBindingClient.cs.</span></span> <span data-ttu-id="2c58a-186">此文件由生成[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2c58a-186">This file is generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="2c58a-187">`SqlAdapterBinding_TableOp_dbo_Employee` 是客户端终结点配置的名称，并在 app.config 中定义。此文件也会生成由[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，其中包含的绑定属性和其他配置设置。</span><span class="sxs-lookup"><span data-stu-id="2c58a-187">`SqlAdapterBinding_TableOp_dbo_Employee` is the name of the client endpoint configuration and is defined in the app.config. This file is also generated by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and contains the binding properties and other configuration settings.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2c58a-188">在此代码段中，你使用的绑定和终结点地址从配置文件。</span><span class="sxs-lookup"><span data-stu-id="2c58a-188">In this snippet, you use the binding and endpoint address from the configuration file.</span></span> <span data-ttu-id="2c58a-189">你还可显式指定这些值在代码中。</span><span class="sxs-lookup"><span data-stu-id="2c58a-189">You can also explicitly specify these values in your code.</span></span> <span data-ttu-id="2c58a-190">指定客户端绑定的不同方法的详细信息，请参阅[为该 SQL 适配器配置客户端绑定](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="2c58a-190">For more information on the different ways of specifying client binding, see [Configure a Client Binding for the SQL Adapter](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md).</span></span>  
  
5.  <span data-ttu-id="2c58a-191">下面的代码段中所述，请打开客户端：</span><span class="sxs-lookup"><span data-stu-id="2c58a-191">Open the client as described in the snippet below:</span></span>  
  
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
  
6.  <span data-ttu-id="2c58a-192">调用上员工表的插入操作。</span><span class="sxs-lookup"><span data-stu-id="2c58a-192">Invoke the Insert operation on the Employee table.</span></span>  
  
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
  
     <span data-ttu-id="2c58a-193">你可以替换前面的代码段，来执行选择、 更新或删除操作以及。</span><span class="sxs-lookup"><span data-stu-id="2c58a-193">You can replace the preceding code snippet to perform Select, Update, or Delete operations as well.</span></span> <span data-ttu-id="2c58a-194">你还可以将代码片段，可在单个应用程序中执行所有操作。</span><span class="sxs-lookup"><span data-stu-id="2c58a-194">You can also append the code snippets to perform all operation in a single application.</span></span> <span data-ttu-id="2c58a-195">有关如何执行这些操作的代码段。</span><span class="sxs-lookup"><span data-stu-id="2c58a-195">For code snippets on how to perform these operations.</span></span>  
  
7.  <span data-ttu-id="2c58a-196">关闭客户端，如下面的代码段中所述：</span><span class="sxs-lookup"><span data-stu-id="2c58a-196">Close the client as described in the snippet below:</span></span>  
  
    ```  
    client.Close();  
    Console.WriteLine("Press any key to exit...");  
    Console.ReadLine();  
    ```  
  
8.  <span data-ttu-id="2c58a-197">生成项目，然后运行它。</span><span class="sxs-lookup"><span data-stu-id="2c58a-197">Build the project and then run it.</span></span> <span data-ttu-id="2c58a-198">应用程序在员工表中插入一条记录。</span><span class="sxs-lookup"><span data-stu-id="2c58a-198">The application inserts a record in the Employee table.</span></span>  
  
###   <a name="select-operation"></a><span data-ttu-id="2c58a-199">选择操作</span><span class="sxs-lookup"><span data-stu-id="2c58a-199">Select Operation</span></span>  
 <span data-ttu-id="2c58a-200">下面的代码演示了面向员工表选择操作。</span><span class="sxs-lookup"><span data-stu-id="2c58a-200">The following code shows a Select operation that targets the Employee table.</span></span> <span data-ttu-id="2c58a-201">选择操作选择的最新记录插入到表。</span><span class="sxs-lookup"><span data-stu-id="2c58a-201">The Select operation selects the last record inserted into the table.</span></span> <span data-ttu-id="2c58a-202">返回的记录将写入控制台。</span><span class="sxs-lookup"><span data-stu-id="2c58a-202">The returned records are written to the console.</span></span>  
  
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
  
###   <a name="update-operation"></a><span data-ttu-id="2c58a-203">更新操作</span><span class="sxs-lookup"><span data-stu-id="2c58a-203">Update Operation</span></span>  
 <span data-ttu-id="2c58a-204">下面的代码演示了面向员工表的更新操作。</span><span class="sxs-lookup"><span data-stu-id="2c58a-204">The following code shows an Update operation that targets the Employee table.</span></span>  
  
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
  
###   <a name="delete-operation"></a><span data-ttu-id="2c58a-205">删除操作</span><span class="sxs-lookup"><span data-stu-id="2c58a-205">Delete Operation</span></span>  
 <span data-ttu-id="2c58a-206">下面的代码演示了面向员工表的删除操作。</span><span class="sxs-lookup"><span data-stu-id="2c58a-206">The following code shows a Delete operation that targets the Employee table.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2c58a-207">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2c58a-207">See Also</span></span>  
[<span data-ttu-id="2c58a-208">使用 WCF 服务模型开发应用程序</span><span class="sxs-lookup"><span data-stu-id="2c58a-208">Develop applications using the WCF Service model</span></span>](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)