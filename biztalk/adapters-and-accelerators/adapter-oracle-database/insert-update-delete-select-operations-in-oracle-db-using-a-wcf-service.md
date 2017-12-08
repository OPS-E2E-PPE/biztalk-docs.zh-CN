---
title: "插入、 更新、 删除或使用 WCF 服务模型的 Oracle 数据库中选择操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF service model, Delete operation
- WCF service model, Select operation
- WCF service model, Insert operation
- WCF service model, Update operation
ms.assetid: d1a9f44f-ea0b-4dd6-9489-fa0d963848c4
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f312f0fa967c08fabbc27c9269abaae68b9ac958
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="insert-update-delete-or-select-operations-in-oracle-database-using-the-wcf-service-model"></a><span data-ttu-id="ca42c-102">插入、 更新、 删除或使用 WCF 服务模型的 Oracle 数据库中选择操作</span><span class="sxs-lookup"><span data-stu-id="ca42c-102">Insert, update, delete, or select operations in Oracle Database using the WCF Service Model</span></span>
<span data-ttu-id="ca42c-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]呈现一套基本 Insert、 Update、 Delete 和 Oracle 数据库表和视图的 Select 操作。</span><span class="sxs-lookup"><span data-stu-id="ca42c-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces a set of basic Insert, Update, Delete, and Select operations on Oracle database tables and views.</span></span> <span data-ttu-id="ca42c-104">通过使用这些操作，你可以执行简单的 SQL 插入、 更新选择、 和 DELETE 语句由目标表或视图的 WHERE 子句限定。</span><span class="sxs-lookup"><span data-stu-id="ca42c-104">By using these operations, you can perform simple SQL INSERT, UPDATE, SELECT, and DELETE statements qualified by a WHERE clause on a target table or view.</span></span> <span data-ttu-id="ca42c-105">若要执行更复杂的操作，例如 SQL 选择使用的查询联接运算符，可以使用 SQLEXECUTE 操作。</span><span class="sxs-lookup"><span data-stu-id="ca42c-105">To perform more complex operations, for example a SQL SELECT query that uses the JOIN operator, you can use the SQLEXECUTE operation.</span></span> <span data-ttu-id="ca42c-106">有关 SQLEXECUTE 操作的详细信息，请参阅[在 Oracle 数据库中使用 WCF 服务模型执行 SQLEXECUTE 操作](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model.md)。</span><span class="sxs-lookup"><span data-stu-id="ca42c-106">For more information about the SQLEXECUTE operation, see [Performing a SQLEXECUTE Operation in Oracle Database Using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/run-sqlexecute-operation-in-oracle-database-using-the-wcf-service-model.md).</span></span>  
  
 <span data-ttu-id="ca42c-107">下表总结了基本的 SQL 操作的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]对表和视图的图面。</span><span class="sxs-lookup"><span data-stu-id="ca42c-107">The following table summarizes the basic SQL operations that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] surfaces on tables and views.</span></span> <span data-ttu-id="ca42c-108">有关这些操作的完整说明，请参阅[基本插入、 更新、 删除和选择表和视图上的操作的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)。</span><span class="sxs-lookup"><span data-stu-id="ca42c-108">For a complete description of these operations, see [Message Schemas for the Basic Insert, Update, Delete, and Select Operations on Tables and Views](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md).</span></span>  
  
|<span data-ttu-id="ca42c-109">运算</span><span class="sxs-lookup"><span data-stu-id="ca42c-109">Operation</span></span>|<span data-ttu-id="ca42c-110">Description</span><span class="sxs-lookup"><span data-stu-id="ca42c-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="ca42c-111">Insert</span><span class="sxs-lookup"><span data-stu-id="ca42c-111">Insert</span></span>|<span data-ttu-id="ca42c-112">插入操作支持多个记录或大容量插入到目标表或视图：</span><span class="sxs-lookup"><span data-stu-id="ca42c-112">The Insert operation supports multiple record or bulk inserts into the target table or view:</span></span><br /><br /> <span data-ttu-id="ca42c-113">-A 多个记录插入操作将行插入到表或视图基于提供的记录集。</span><span class="sxs-lookup"><span data-stu-id="ca42c-113">-   A multiple record Insert operation inserts rows into a table or view based on a supplied record set.</span></span><br /><span data-ttu-id="ca42c-114">-A 大容量插入操作将行插入到表或视图基于提供 SQL SELECT 查询和列列表。</span><span class="sxs-lookup"><span data-stu-id="ca42c-114">-   A bulk Insert operation inserts rows into a table or view based on a supplied SQL SELECT query and column list.</span></span> <span data-ttu-id="ca42c-115">查询返回的记录插入到目标表基于列列表。</span><span class="sxs-lookup"><span data-stu-id="ca42c-115">The records that the query returns are inserted into the target table based on the column list.</span></span>|  
|<span data-ttu-id="ca42c-116">选择</span><span class="sxs-lookup"><span data-stu-id="ca42c-116">Select</span></span>|<span data-ttu-id="ca42c-117">基于提供的列名称和一个筛选器字符串，指定的 SQL WHERE 子句列表的目标表中执行的 SQL SELECT 查询。</span><span class="sxs-lookup"><span data-stu-id="ca42c-117">Performs a SQL SELECT query on the target table based on a supplied list of column names and a filter string that specifies a SQL WHERE clause.</span></span>|  
|<span data-ttu-id="ca42c-118">Update</span><span class="sxs-lookup"><span data-stu-id="ca42c-118">Update</span></span>|<span data-ttu-id="ca42c-119">在目标表上执行更新。</span><span class="sxs-lookup"><span data-stu-id="ca42c-119">Performs an UPDATE on the target table.</span></span> <span data-ttu-id="ca42c-120">要更新的记录都由一个筛选器字符串，指定的 SQL WHERE 子句指定。</span><span class="sxs-lookup"><span data-stu-id="ca42c-120">The records to be updated are specified by a filter string that specifies a SQL WHERE clause.</span></span> <span data-ttu-id="ca42c-121">模板记录中指定的更新的值。</span><span class="sxs-lookup"><span data-stu-id="ca42c-121">The values for the update are specified in a template record.</span></span>|  
|<span data-ttu-id="ca42c-122">DELETE</span><span class="sxs-lookup"><span data-stu-id="ca42c-122">Delete</span></span>|<span data-ttu-id="ca42c-123">基于筛选器字符串中指定的 SQL WHERE 子句的目标表执行删除。</span><span class="sxs-lookup"><span data-stu-id="ca42c-123">Performs a DELETE on the target table based on a SQL WHERE clause that is specified in a filter string.</span></span>|  
  
## <a name="about-the-examples-used-in-this-topic"></a><span data-ttu-id="ca42c-124">有关在本主题中使用的示例</span><span class="sxs-lookup"><span data-stu-id="ca42c-124">About the Examples Used in this Topic</span></span>  
 <span data-ttu-id="ca42c-125">本主题中的示例使用 /SCOTT/ACCOUNTACTIVITY 表。</span><span class="sxs-lookup"><span data-stu-id="ca42c-125">The examples in this topic use the /SCOTT/ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="ca42c-126">使用 SDK 示例提供了一个脚本来生成此表。</span><span class="sxs-lookup"><span data-stu-id="ca42c-126">A script to generate this table is supplied with the SDK samples.</span></span> <span data-ttu-id="ca42c-127">有关 SDK 示例的详细信息，请参阅[SDK 中的示例](../../core/samples-in-the-sdk.md)。</span><span class="sxs-lookup"><span data-stu-id="ca42c-127">For more information about the SDK samples, see [Samples in the SDK](../../core/samples-in-the-sdk.md).</span></span>  
  
## <a name="the-wcf-client-class"></a><span data-ttu-id="ca42c-128">WCF 客户端类</span><span class="sxs-lookup"><span data-stu-id="ca42c-128">The WCF Client Class</span></span>  
 <span data-ttu-id="ca42c-129">WCF 客户端生成的基本 SQL 操作的名称，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]图面基于表或视图，如下所示的以下表的名称。</span><span class="sxs-lookup"><span data-stu-id="ca42c-129">The name of the WCF client generated for the basic SQL operations that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] surfaces is based on the name of the table or view, as in the following table.</span></span>  
  
|<span data-ttu-id="ca42c-130">Oracle 数据库项目</span><span class="sxs-lookup"><span data-stu-id="ca42c-130">Oracle Database Artifact</span></span>|<span data-ttu-id="ca42c-131">WCF 客户端名称</span><span class="sxs-lookup"><span data-stu-id="ca42c-131">WCF Client Name</span></span>|  
|------------------------------|---------------------|  
|<span data-ttu-id="ca42c-132">表</span><span class="sxs-lookup"><span data-stu-id="ca42c-132">Table</span></span>|<span data-ttu-id="ca42c-133">[架构]表 [TABLE_NAME] 客户端</span><span class="sxs-lookup"><span data-stu-id="ca42c-133">[SCHEMA]Table[TABLE_NAME]Client</span></span>|  
|<span data-ttu-id="ca42c-134">视图</span><span class="sxs-lookup"><span data-stu-id="ca42c-134">View</span></span>|<span data-ttu-id="ca42c-135">[架构]视图 [VIEW_NAME] 客户端</span><span class="sxs-lookup"><span data-stu-id="ca42c-135">[SCHEMA]View[VIEW_NAME]Client</span></span>|  
  
 <span data-ttu-id="ca42c-136">[架构] = Oracle 集合项目;例如，SCOTT。</span><span class="sxs-lookup"><span data-stu-id="ca42c-136">[SCHEMA] = Collection of Oracle artifacts; for example, SCOTT.</span></span>  
  
 <span data-ttu-id="ca42c-137">[TABLE_NAME] = 表; 的名称例如，ACCOUNTACTIVITY。</span><span class="sxs-lookup"><span data-stu-id="ca42c-137">[TABLE_NAME] = The name of the table; for example, ACCOUNTACTIVITY.</span></span>  
  
 <span data-ttu-id="ca42c-138">[VIEW_NAME] = 视图的名称。</span><span class="sxs-lookup"><span data-stu-id="ca42c-138">[VIEW_NAME] = The name of the view.</span></span>  
  
 <span data-ttu-id="ca42c-139">下表显示对表的基本 SQL 操作的方法签名。</span><span class="sxs-lookup"><span data-stu-id="ca42c-139">The following table shows the method signatures for the basic SQL operations on a table.</span></span> <span data-ttu-id="ca42c-140">签名是相同的视图，只不过视图命名空间和名称替换那些表。</span><span class="sxs-lookup"><span data-stu-id="ca42c-140">The signatures are the same for a view, except that the view namespace and name replace those of the table.</span></span>  
  
|<span data-ttu-id="ca42c-141">运算</span><span class="sxs-lookup"><span data-stu-id="ca42c-141">Operation</span></span>|<span data-ttu-id="ca42c-142">方法签名</span><span class="sxs-lookup"><span data-stu-id="ca42c-142">Method Signature</span></span>|  
|---------------|----------------------|  
|<span data-ttu-id="ca42c-143">Insert</span><span class="sxs-lookup"><span data-stu-id="ca42c-143">Insert</span></span>|<span data-ttu-id="ca42c-144">长时间插入 ([TABLE_NS]。 [TABLE_NAME] RECORDINSERT [] 记录集，字符串 COLUMN_NAMES，查询字符串);</span><span class="sxs-lookup"><span data-stu-id="ca42c-144">long Insert([TABLE_NS].[TABLE_NAME]RECORDINSERT[] RECORDSET, string COLUMN_NAMES, string QUERY);</span></span>|  
|<span data-ttu-id="ca42c-145">选择</span><span class="sxs-lookup"><span data-stu-id="ca42c-145">Select</span></span>|<span data-ttu-id="ca42c-146">[TABLE_NS]。[TABLE_NAME]RECORDSELECT [] 选择 （字符串 COLUMN_NAMES，字符串筛选器）;</span><span class="sxs-lookup"><span data-stu-id="ca42c-146">[TABLE_NS].[TABLE_NAME]RECORDSELECT[] Select(string COLUMN_NAMES, string FILTER);</span></span>|  
|<span data-ttu-id="ca42c-147">Update</span><span class="sxs-lookup"><span data-stu-id="ca42c-147">Update</span></span>|<span data-ttu-id="ca42c-148">长时间更新 ([TABLE_NS]。 [TABLE_NAME] RECORDUPDATE 记录集，筛选器字符串）;</span><span class="sxs-lookup"><span data-stu-id="ca42c-148">long Update([TABLE_NS].[TABLE_NAME]RECORDUPDATE RECORDSET, string FILTER);</span></span>|  
|<span data-ttu-id="ca42c-149">DELETE</span><span class="sxs-lookup"><span data-stu-id="ca42c-149">Delete</span></span>|<span data-ttu-id="ca42c-150">长时间删除 （字符串筛选器）;</span><span class="sxs-lookup"><span data-stu-id="ca42c-150">Long Delete(string FILTER);</span></span>|  
  
 <span data-ttu-id="ca42c-151">[TABLE_NS] = 表命名空间; 的名称例如，microsoft.lobservices.oracledb._2007._03.SCOTT。Table.ACCOUNTACTIVITY。</span><span class="sxs-lookup"><span data-stu-id="ca42c-151">[TABLE_NS] = The name of the table namespace; for example, microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.</span></span>  
  
 <span data-ttu-id="ca42c-152">[TABLE_NAME] = 表; 的名称例如，ACCOUNTACTIVITY。</span><span class="sxs-lookup"><span data-stu-id="ca42c-152">[TABLE_NAME] = The name of the table; for example, ACCOUNTACTIVITY.</span></span>  
  
 <span data-ttu-id="ca42c-153">由 Insert、 Update 和 Select 操作使用的记录类型所有表中定义，或查看命名空间。</span><span class="sxs-lookup"><span data-stu-id="ca42c-153">The record types used by the Insert, Update, and Select operations are all defined in the table or view namespace.</span></span>  
  
 <span data-ttu-id="ca42c-154">以下代码所示的 WCF 客户端类的方法签名为 Delete、 Insert、 Select 和 Update 生成/SCOTT/ACCOUNTACTIVITY 表上的操作。</span><span class="sxs-lookup"><span data-stu-id="ca42c-154">The following code shows the method signatures for a WCF client class generated for the Delete, Insert, Select and Update operations on the /SCOTT/ACCOUNTACTIVITY table.</span></span>  
  
```  
public partial class SCOTTTableACCOUNTACTIVITYClient : System.ServiceModel.ClientBase<SCOTTTableACCOUNTACTIVITY>, SCOTTTableACCOUNTACTIVITY {  
  
    public long Delete(string FILTER);  
  
    public long Insert(microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDINSERT[] RECORDSET, string COLUMN_NAMES, string QUERY);  
  
    public microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDSELECT[] Select(string COLUMN_NAMES, string FILTER);  
  
    public long Update(microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDUPDATE RECORDSET, string FILTER);  
}  
```  
  
## <a name="invoking-the-basic-sql-operations"></a><span data-ttu-id="ca42c-155">调用的基本 SQL 操作</span><span class="sxs-lookup"><span data-stu-id="ca42c-155">Invoking the Basic SQL Operations</span></span>  
 <span data-ttu-id="ca42c-156">若要使用 WCF 客户端调用表或视图的基本 SQL 操作，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="ca42c-156">To invoke the basic SQL operations on a table or view by using a WCF client, perform the following steps.</span></span>  
  
1.  <span data-ttu-id="ca42c-157">生成的目标表或视图的 WCF 客户端类。</span><span class="sxs-lookup"><span data-stu-id="ca42c-157">Generate a WCF client class for the target table or view.</span></span> <span data-ttu-id="ca42c-158">此类应包含的操作，将在目标项目上调用的方法。</span><span class="sxs-lookup"><span data-stu-id="ca42c-158">This class should contain methods for the operations that you will invoke on the target artifact.</span></span>  
  
2.  <span data-ttu-id="ca42c-159">创建 WCF 客户端类的实例并调用其方法来对表或视图执行操作。</span><span class="sxs-lookup"><span data-stu-id="ca42c-159">Create an instance of the WCF client class and invoke its methods to perform operations on the table or view.</span></span>  
  
 <span data-ttu-id="ca42c-160">有关详细信息，有关如何创建一个 WCF 客户端类，在调用操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[与 Oracle 数据库适配器的 WCF 服务模型概述](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-service-model-with-the-oracle-database-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="ca42c-160">For more detailed information about how to create a WCF client class and invoke operations on the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Overview of the WCF Service Model with the Oracle Database Adapter](../../adapters-and-accelerators/adapter-oracle-database/overview-of-the-wcf-service-model-with-the-oracle-database-adapter.md).</span></span>  
  
 <span data-ttu-id="ca42c-161">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]对 Oracle 数据库执行事务内的每个操作。</span><span class="sxs-lookup"><span data-stu-id="ca42c-161">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] executes each operation inside of a transaction on the Oracle database.</span></span> <span data-ttu-id="ca42c-162">你可以通过设置控制此事务的隔离级别**TransactionIsolationLevel**绑定属性。</span><span class="sxs-lookup"><span data-stu-id="ca42c-162">You can control the isolation level of this transaction by setting the **TransactionIsolationLevel** binding property.</span></span> <span data-ttu-id="ca42c-163">有关详细信息[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]绑定属性，请参阅[Oracle 数据库绑定属性的使用 BizTalk Adapter](https://msdn.microsoft.com/library/dd788467.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ca42c-163">For more information about the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] binding properties, see [Working with BizTalk Adapter for Oracle Database Binding Properties](https://msdn.microsoft.com/library/dd788467.aspx).</span></span>  
  
 <span data-ttu-id="ca42c-164">以下部分提供有关如何以调用在代码中的每个基本 SQL 操作的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ca42c-164">The following sections provide details about how to invoke each basic SQL operation in your code.</span></span>  
  
###  <a name="BKMK_InsertOperation"></a><span data-ttu-id="ca42c-165">插入操作</span><span class="sxs-lookup"><span data-stu-id="ca42c-165">Insert Operation</span></span>  
 <span data-ttu-id="ca42c-166">下表显示如何为多个记录插入设置参数和大容量插入操作。</span><span class="sxs-lookup"><span data-stu-id="ca42c-166">The following table shows how to set parameters for multiple record Insert and bulk Insert operations.</span></span>  
  
|<span data-ttu-id="ca42c-167">插入操作类型</span><span class="sxs-lookup"><span data-stu-id="ca42c-167">Insert operation type</span></span>|<span data-ttu-id="ca42c-168">记录集</span><span class="sxs-lookup"><span data-stu-id="ca42c-168">RECORDSET</span></span>|<span data-ttu-id="ca42c-169">COLUMN_NAMES</span><span class="sxs-lookup"><span data-stu-id="ca42c-169">COLUMN_NAMES</span></span>|<span data-ttu-id="ca42c-170">QUERY</span><span class="sxs-lookup"><span data-stu-id="ca42c-170">QUERY</span></span>|  
|---------------------------|---------------|-------------------|-----------|  
|<span data-ttu-id="ca42c-171">多个记录</span><span class="sxs-lookup"><span data-stu-id="ca42c-171">Multiple record</span></span>|<span data-ttu-id="ca42c-172">应将插入到目标的 INSERTRECORDS 的集合。</span><span class="sxs-lookup"><span data-stu-id="ca42c-172">A collection of INSERTRECORDS that should be inserted into the target.</span></span>|<span data-ttu-id="ca42c-173">null</span><span class="sxs-lookup"><span data-stu-id="ca42c-173">null</span></span>|<span data-ttu-id="ca42c-174">null</span><span class="sxs-lookup"><span data-stu-id="ca42c-174">null</span></span>|  
|<span data-ttu-id="ca42c-175">大容量</span><span class="sxs-lookup"><span data-stu-id="ca42c-175">Bulk</span></span>|<span data-ttu-id="ca42c-176">null</span><span class="sxs-lookup"><span data-stu-id="ca42c-176">null</span></span>|<span data-ttu-id="ca42c-177">以逗号分隔的目标; 中的列名称列表例如，"TID，帐户"。</span><span class="sxs-lookup"><span data-stu-id="ca42c-177">A comma-delimited list of column names in the target; for example, "TID, ACCOUNT".</span></span> <span data-ttu-id="ca42c-178">列列表指定在其中查询结果应放在每个插入的行的列。</span><span class="sxs-lookup"><span data-stu-id="ca42c-178">The column list specifies the columns into which the query results should be placed in each inserted row.</span></span> <span data-ttu-id="ca42c-179">查询必须返回匹配数量和类型中的列列表中指定的列的结果集。</span><span class="sxs-lookup"><span data-stu-id="ca42c-179">The query must return a result set that matches the columns specified in the column list in both number and type.</span></span>|<span data-ttu-id="ca42c-180">对数据库表或视图返回的结果集以将插入到目标; SQL SELECT 查询例如，"选择 （TID，帐户） 从 NEW_TRANSACTIONS WHERE 帐户 = 100001"。</span><span class="sxs-lookup"><span data-stu-id="ca42c-180">A SQL SELECT query on a database table or view that returns a result set to insert into the target; for example, "SELECT (TID, ACCOUNT) FROM NEW_TRANSACTIONS WHERE ACCOUNT = 100001".</span></span> <span data-ttu-id="ca42c-181">结果集必须与数量和类型中的列列表匹配。</span><span class="sxs-lookup"><span data-stu-id="ca42c-181">The result set must match the column list in both number and type.</span></span>|  
  
 <span data-ttu-id="ca42c-182">插入操作将返回插入到目标的记录数。</span><span class="sxs-lookup"><span data-stu-id="ca42c-182">The Insert operation returns the number of records inserted into the target.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ca42c-183">在 WCF 服务模型中，在插入操作中使用记录集是强类型。</span><span class="sxs-lookup"><span data-stu-id="ca42c-183">In the WCF service model, the record set used in the Insert operation is strongly-typed.</span></span> <span data-ttu-id="ca42c-184">你可以设置为 nillable 列的值**null**在一条记录以排除该列从插入操作中; 但是，你不能设置为非 nillable 列的值**null**。</span><span class="sxs-lookup"><span data-stu-id="ca42c-184">You can set the value of a nillable column to **null** in a record to exclude that column from the Insert operation; however, you cannot set the value of a non-nillable column to **null**.</span></span> <span data-ttu-id="ca42c-185">这意味着，在多个记录插入操作中，您必须提供每个记录中的所有非 nillable 列的值。</span><span class="sxs-lookup"><span data-stu-id="ca42c-185">This means that in a multiple record Insert operation, you must supply values for all non-nillable columns in each record.</span></span> <span data-ttu-id="ca42c-186">此外，没有流式处理支持的基本 SQL 操作时使用 WCF 服务模型。</span><span class="sxs-lookup"><span data-stu-id="ca42c-186">In addition, there is no streaming support for the basic SQL operations when you use the WCF service model.</span></span> <span data-ttu-id="ca42c-187">如果你的多个记录插入操作涉及大型的记录集，这可能是一个重要的注意事项。</span><span class="sxs-lookup"><span data-stu-id="ca42c-187">If your multiple record Insert operation involves a large record set, this may be an important consideration.</span></span> <span data-ttu-id="ca42c-188">有关详细信息，请参阅[基本的 SQL 操作调用使用 WCF 服务模型的限制](#BKMK_LimitationsInvoking)。</span><span class="sxs-lookup"><span data-stu-id="ca42c-188">For more information, see [Limitations of Invoking the Basic SQL Operations by Using the WCF Service Model](#BKMK_LimitationsInvoking).</span></span>  
  
 <span data-ttu-id="ca42c-189">下面的代码演示了面向 ACCOUNTACTIVITY 表的多个记录插入操作 （两个记录）。</span><span class="sxs-lookup"><span data-stu-id="ca42c-189">The following code shows a multiple record Insert operation (two records) that targets the ACCOUNTACTIVITY table.</span></span>  
  
```  
// Insert records  
                using (SCOTTTableACCOUNTACTIVITYClient aaTableClient =   
                    new SCOTTTableACCOUNTACTIVITYClient("OracleDBBinding_SCOTT.Table.ACCOUNTACTIVITY"))  
                {  
                    long recsInserted;  
  
                    aaTableClient.ClientCredentials.UserName.UserName = "SCOTT";  
                    aaTableClient.ClientCredentials.UserName.Password = "TIGER";  
  
                    try  
                    {  
                        aaTableClient.Open();  
                    }  
                    catch (Exception ex)  
                    {  
                        // handle exception  
                        Console.WriteLine("Exception: " + ex.Message);  
                        throw;  
                    }  
  
                    // Do a multiple record Insert of 2 records for account 100001  
  
                    microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDINSERT[] insertRecs =  
                        new microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDINSERT[2];  
  
                                  TID__COMPLEX_TYPE tid = new TID__COMPLEX_TYPE();  
                                  tid.InlineValue = "tidSequence.NextVal()";  
  
                                  ACCOUNT__COMPLEX_TYPE account = new ACCOUNT__COMPLEX_TYPE();  
                                  account.Value = 100001;  
  
                    AMOUNT__COMPLEX_TYPE amount = new AMOUNT__COMPLEX_TYPE();  
                    amount.Value = 400;  
  
                    TRANSDATE__COMPLEX_TYPE transdate = new TRANSDATE__COMPLEX_TYPE();  
                    transdate.Value = DateTime.Now.Date;  
  
                    PROCESSED__COMPLEX_TYPE processed = new PROCESSED__COMPLEX_TYPE();  
                    processed.Value = "n";  
  
                    DESCRIPTION__COMPLEX_TYPE description1 = new DESCRIPTION__COMPLEX_TYPE();  
                    description1.Value = "Inserted Record #1";  
  
                    DESCRIPTION__COMPLEX_TYPE description2 = new DESCRIPTION__COMPLEX_TYPE();  
                    description2.Value = "Inserted Record #2";  
  
                    insertRecs[0] =   
                        new microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDINSERT();  
                    insertRecs[0].TID = tid;  
                    insertRecs[0].ACCOUNT = account;  
                    insertRecs[0].AMOUNT = amount;  
                    insertRecs[0].TRANSDATE = transdate;  
                    insertRecs[0].DESCRIPTION = description1;  
                    insertRecs[0].PROCESSED = processed;  
  
                    insertRecs[1] =   
                        new microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDINSERT();  
                    insertRecs[1].TID = tid;  
                    insertRecs[1].ACCOUNT = account;  
                    insertRecs[1].AMOUNT = amount;  
                    insertRecs[1].TRANSDATE = transdate;  
                    insertRecs[1].DESCRIPTION = description2;  
                    insertRecs[1].PROCESSED = processed;  
  
                    try  
                    {  
                        recsInserted = aaTableClient.Insert(insertRecs, null, null);  
                    }  
                    catch (Exception ex)  
                    {  
                        // handle exception  
                        Console.WriteLine("Exception: " + ex.Message);  
                        throw;  
                    }  
  
                    Console.WriteLine("Insert Done: {0} records inserted", recsInserted);  
```  
  
### <a name="select-operation"></a><span data-ttu-id="ca42c-190">选择操作</span><span class="sxs-lookup"><span data-stu-id="ca42c-190">Select Operation</span></span>  
 <span data-ttu-id="ca42c-191">下表显示了选择操作的参数。</span><span class="sxs-lookup"><span data-stu-id="ca42c-191">The following table shows the parameters for the Select operation.</span></span>  
  
|<span data-ttu-id="ca42c-192">COLUMN_NAMES</span><span class="sxs-lookup"><span data-stu-id="ca42c-192">COLUMN_NAMES</span></span>|<span data-ttu-id="ca42c-193">FILTER</span><span class="sxs-lookup"><span data-stu-id="ca42c-193">FILTER</span></span>|  
|-------------------|------------|  
|<span data-ttu-id="ca42c-194">以逗号分隔的目标; 中的列名称列表例如，"TID，帐户"。</span><span class="sxs-lookup"><span data-stu-id="ca42c-194">A comma-delimited list of column names in the target; for example, "TID, ACCOUNT".</span></span> <span data-ttu-id="ca42c-195">列列表指定应在结果集中返回目标的列。</span><span class="sxs-lookup"><span data-stu-id="ca42c-195">The column list specifies the columns of the target that should be returned in the result set.</span></span> <span data-ttu-id="ca42c-196">未指定列列表中的列将设置为其.NET 默认值中返回的记录集。</span><span class="sxs-lookup"><span data-stu-id="ca42c-196">Columns not specified in the column list will be set to their .NET default values in the returned record set.</span></span> <span data-ttu-id="ca42c-197">对于 nillable 列，此值是**null**。</span><span class="sxs-lookup"><span data-stu-id="ca42c-197">For nillable columns, this value is **null**.</span></span>|<span data-ttu-id="ca42c-198">指定的查询; 的目标行的 SQL WHERE 子句的内容例如，"说明 = Insert 录音 #1"。</span><span class="sxs-lookup"><span data-stu-id="ca42c-198">The contents of a SQL WHERE clause that specifies the target rows of the query; for example, "DESCRIPTION = 'Insert Record #1'".</span></span> <span data-ttu-id="ca42c-199">你可以将此参数设置为**null**返回目标的所有行。</span><span class="sxs-lookup"><span data-stu-id="ca42c-199">You can set this parameter to **null** to return all rows of the target.</span></span>|  
  
 <span data-ttu-id="ca42c-200">选择操作将返回基于目标的行类型的强类型的记录集。</span><span class="sxs-lookup"><span data-stu-id="ca42c-200">The Select operation returns a strongly-typed record set based on the row type of the target.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ca42c-201">使用 WCF 服务模型时的基本 SQL 操作不流式处理支持。</span><span class="sxs-lookup"><span data-stu-id="ca42c-201">There is no streaming support for the basic SQL operations when you use the WCF service model.</span></span> <span data-ttu-id="ca42c-202">如果你的查询返回较大的记录集，你可以通过使用 WCF 通道模型来提高性能。</span><span class="sxs-lookup"><span data-stu-id="ca42c-202">If your query returns a large record set, you might be able to improve performance by using the WCF channel model.</span></span> <span data-ttu-id="ca42c-203">有关详细信息，请参阅[基本的 SQL 操作调用使用 WCF 服务模型的限制](#BKMK_LimitationsInvoking)。</span><span class="sxs-lookup"><span data-stu-id="ca42c-203">For more information, see [Limitations of Invoking the Basic SQL Operations by Using the WCF Service Model](#BKMK_LimitationsInvoking).</span></span>  
  
 <span data-ttu-id="ca42c-204">下面的代码演示了面向 ACCOUNTACTIVITY 表选择操作。</span><span class="sxs-lookup"><span data-stu-id="ca42c-204">The following code shows a Select operation that targets the ACCOUNTACTIVITY table.</span></span> <span data-ttu-id="ca42c-205">返回的记录将写入控制台。</span><span class="sxs-lookup"><span data-stu-id="ca42c-205">The returned records are written to the console.</span></span>  
  
```  
// Declare a variable to hold the result set  
microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDSELECT[] selectRecords;  
  
// Select all records and write them to the console  
try  
{  
    selectRecords = aaTableClient.Select("*", null);  
}  
catch (Exception ex)  
{  
    // handle exception  
}  
  
Console.WriteLine("ACCOUNTACTIVITY before any operations");  
for (int i = 0; i \< selectRecords.Length; i++)  
{  
    Console.WriteLine("{0}\t{1}\t{2}\t{3}\t{4}", selectRecords[i].TID,  
    selectRecords[i].ACCOUNT,  
    selectRecords[i].AMOUNT,  
    selectRecords[i].TRANSDATE,  
    selectRecords[i].DESCRIPTION);  
}  
```  
  
> [!NOTE]
>  <span data-ttu-id="ca42c-206">此代码省略步骤来创建、 配置和打开 WCF 客户端实例。</span><span class="sxs-lookup"><span data-stu-id="ca42c-206">This code omits steps to create, configure, and open the WCF client instance.</span></span> <span data-ttu-id="ca42c-207">有关示例，其中包括以下步骤，请参阅[插入操作](#BKMK_InsertOperation)。</span><span class="sxs-lookup"><span data-stu-id="ca42c-207">For an example that includes these steps, see [Insert Operation](#BKMK_InsertOperation).</span></span>  
  
### <a name="update-operation"></a><span data-ttu-id="ca42c-208">更新操作</span><span class="sxs-lookup"><span data-stu-id="ca42c-208">Update Operation</span></span>  
 <span data-ttu-id="ca42c-209">下表显示了更新操作的参数。</span><span class="sxs-lookup"><span data-stu-id="ca42c-209">The following table shows the parameters for the Update operation.</span></span>  
  
|<span data-ttu-id="ca42c-210">记录集</span><span class="sxs-lookup"><span data-stu-id="ca42c-210">RECORDSET</span></span>|<span data-ttu-id="ca42c-211">FILTER</span><span class="sxs-lookup"><span data-stu-id="ca42c-211">FILTER</span></span>|  
|---------------|------------|  
|<span data-ttu-id="ca42c-212">一个基于目标的行类型的强类型的模板记录。</span><span class="sxs-lookup"><span data-stu-id="ca42c-212">A strongly-typed template record based on the row type of the target.</span></span> <span data-ttu-id="ca42c-213">模板记录指定目标行的更新的值。</span><span class="sxs-lookup"><span data-stu-id="ca42c-213">The template record specifies the update values for the target rows.</span></span> <span data-ttu-id="ca42c-214">对于 nillable 行的列，可以指定一个 null 值，以指示应在目标行中更新列。</span><span class="sxs-lookup"><span data-stu-id="ca42c-214">For nillable row columns, you can specify a null value to indicate that the column should not be updated in the target rows.</span></span>|<span data-ttu-id="ca42c-215">目标中指定要更新的行的 SQL WHERE 子句的内容。</span><span class="sxs-lookup"><span data-stu-id="ca42c-215">The contents of a SQL WHERE clause that specifies the rows to be updated in the target.</span></span> <span data-ttu-id="ca42c-216">例如，"说明 = 插入录音 #1"。</span><span class="sxs-lookup"><span data-stu-id="ca42c-216">For example, "DESCRIPTION= 'Inserted Record #1'".</span></span>|  
  
 <span data-ttu-id="ca42c-217">更新操作将返回从目标中删除的行数。</span><span class="sxs-lookup"><span data-stu-id="ca42c-217">The Update operation returns the number of rows deleted from the target.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ca42c-218">在 WCF 服务模型中，在更新操作中使用的模板记录是强类型。</span><span class="sxs-lookup"><span data-stu-id="ca42c-218">In the WCF service model, the template record used in the Update operation is strongly-typed.</span></span> <span data-ttu-id="ca42c-219">如果列可为零，则可以省略更新操作的列，通过将其值设置为**null**中的模板记录中; 但是，如果列不为零，则必须设置模板记录中的其值。</span><span class="sxs-lookup"><span data-stu-id="ca42c-219">If a column is nillable, you can omit the column from the Update operation by setting its value to **null** in the template record; however, if a column is not nillable, then you must set its value in the template record.</span></span> <span data-ttu-id="ca42c-220">例如，如果列是主键，它必须包含一个值。</span><span class="sxs-lookup"><span data-stu-id="ca42c-220">For example, if a column is a primary key, it must contain a value.</span></span> <span data-ttu-id="ca42c-221">有关详细信息，请参阅[基本的 SQL 操作调用使用 WCF 服务模型的限制](#BKMK_LimitationsInvoking)。</span><span class="sxs-lookup"><span data-stu-id="ca42c-221">For more information, see [Limitations of Invoking the Basic SQL Operations by Using the WCF Service Model](#BKMK_LimitationsInvoking).</span></span>  
  
 <span data-ttu-id="ca42c-222">下面的代码演示了面向 ACCOUNTACTIVITY 表的更新操作。</span><span class="sxs-lookup"><span data-stu-id="ca42c-222">The following code shows an Update operation that targets the ACCOUNTACTIVITY table.</span></span>  
  
```  
long recsUpdated;  
  
...  
  
// Create updated template. The TID, TIME, AMOUNT, and DESCRIPTION fields will be updated  
microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDUPDATE updateRecord =  
    new microsoft.lobservices.oracledb._2007._03.SCOTT.Table.ACCOUNTACTIVITY.ACCOUNTACTIVITYRECORDUPDATE();  
        updateRecord.TID = tidSequence.NextVal();  
        updateRecord.ACCOUNT = null;  
        updateRecord.AMOUNT = 300;  
        updateRecord.TRANSDATE = DateTime.Now.Date;  
        updateRecord.DESCRIPTION = "Updated Record #2";  
        updateRecord.PROCESSED = null;  
  
// Set filter string to specify the target record by using the DESCRIPTION field  
string filter = "DESCRIPTION = 'Inserted Record #2'";  
  
try  
{  
    recsUpdated = aaTableClient.Update(updateRecord, filter);  
}  
catch (Exception ex)  
{  
    // handle exception  
    ...  
}  
  
Console.WriteLine("{0} records updated", recsUpdated);  
```  
  
> [!NOTE]
>  <span data-ttu-id="ca42c-223">此代码省略步骤来创建、 配置和打开 WCF 客户端实例。</span><span class="sxs-lookup"><span data-stu-id="ca42c-223">This code omits steps to create, configure, and open the WCF client instance.</span></span> <span data-ttu-id="ca42c-224">有关示例，其中包括以下步骤，请参阅[插入操作](#BKMK_InsertOperation)。</span><span class="sxs-lookup"><span data-stu-id="ca42c-224">For an example that includes these steps, see [Insert Operation](#BKMK_InsertOperation).</span></span>  
  
### <a name="delete-operation"></a><span data-ttu-id="ca42c-225">删除操作</span><span class="sxs-lookup"><span data-stu-id="ca42c-225">Delete Operation</span></span>  
 <span data-ttu-id="ca42c-226">下表显示删除操作的参数。</span><span class="sxs-lookup"><span data-stu-id="ca42c-226">The following table shows the parameters for the Delete operation.</span></span>  
  
|<span data-ttu-id="ca42c-227">FILTER</span><span class="sxs-lookup"><span data-stu-id="ca42c-227">FILTER</span></span>|  
|------------|  
|<span data-ttu-id="ca42c-228">指定要从目标中删除的行的 SQL WHERE 子句的内容。</span><span class="sxs-lookup"><span data-stu-id="ca42c-228">The contents of a SQL WHERE clause that specifies the rows to be deleted from the target.</span></span> <span data-ttu-id="ca42c-229">例如，"说明 = 插入录音 #1"。</span><span class="sxs-lookup"><span data-stu-id="ca42c-229">For example, "DESCRIPTION= 'Inserted Record #1'".</span></span>|  
  
 <span data-ttu-id="ca42c-230">删除操作将返回从目标中删除的行数。</span><span class="sxs-lookup"><span data-stu-id="ca42c-230">The Delete operation returns the number of rows deleted from the target.</span></span> <span data-ttu-id="ca42c-231">下面的代码演示了面向 ACCOUNTACTIVITY 表的删除操作。</span><span class="sxs-lookup"><span data-stu-id="ca42c-231">The following code shows a Delete operation that targets the ACCOUNTACTIVITY table.</span></span>  
  
```  
// Set filter string equal to the DESCRIPTION field of the target record  
string filter = "DESCRIPTION = 'Inserted Record #1'";  
  
try  
{  
    recsDeleted = aaTableClient.Delete(filter);  
}  
catch (Exception ex)  
{  
    // handle exception  
  
    ...  
}  
Console.WriteLine("{0} records deleted", recsDeleted);  
```  
  
> [!NOTE]
>  <span data-ttu-id="ca42c-232">此代码省略步骤来创建、 配置和打开 WCF 客户端实例。</span><span class="sxs-lookup"><span data-stu-id="ca42c-232">This code omits steps to create, configure, and open the WCF client instance.</span></span> <span data-ttu-id="ca42c-233">有关示例，其中包括以下步骤，请参阅[插入操作](#BKMK_InsertOperation)。</span><span class="sxs-lookup"><span data-stu-id="ca42c-233">For an example that includes these steps, see the [Insert Operation](#BKMK_InsertOperation).</span></span>  
  
##  <a name="BKMK_LimitationsInvoking"></a><span data-ttu-id="ca42c-234">通过使用 WCF 服务模型中调用的基本 SQL 操作的限制</span><span class="sxs-lookup"><span data-stu-id="ca42c-234">Limitations of Invoking the Basic SQL Operations by Using the WCF Service Model</span></span>  
 <span data-ttu-id="ca42c-235">在使用 WCF 客户端调用的基本 SQL 操作时，存在以下限制：</span><span class="sxs-lookup"><span data-stu-id="ca42c-235">The following limitations exist when you invoke the basic SQL operations by using a WCF client:</span></span>  
  
-   <span data-ttu-id="ca42c-236">**插入操作。**</span><span class="sxs-lookup"><span data-stu-id="ca42c-236">**Insert operation.**</span></span> <span data-ttu-id="ca42c-237">在多个记录的插入操作中使用的记录集是强类型，并因此包含行的所有列。</span><span class="sxs-lookup"><span data-stu-id="ca42c-237">The record set used in a multiple record Insert operation is strongly-typed and therefore includes all row columns.</span></span> <span data-ttu-id="ca42c-238">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]解释表示的记录中的 null 值，应从插入操作中排除列; 但是，非 nillable 列，无法排除不能将它们设置为 null 值。</span><span class="sxs-lookup"><span data-stu-id="ca42c-238">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] interprets a null value in a record to mean that the column should be excluded from the Insert operation; however, non-nillable columns cannot be excluded because you cannot set them to a null value.</span></span> <span data-ttu-id="ca42c-239">因此，必须指定非 nillable 列的值时执行多个记录的插入操作。</span><span class="sxs-lookup"><span data-stu-id="ca42c-239">Therefore, you must specify values for non-nillable columns when you perform a multiple record Insert operation.</span></span>  
  
-   <span data-ttu-id="ca42c-240">**插入操作。**</span><span class="sxs-lookup"><span data-stu-id="ca42c-240">**Insert operation.**</span></span> <span data-ttu-id="ca42c-241">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]解释**DbNull** nillable 数据列表示应从多个记录的插入操作中排除列中的值。</span><span class="sxs-lookup"><span data-stu-id="ca42c-241">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] interprets a **DbNull** value in a nillable data column to mean that the column should be excluded from a multiple record Insert operation.</span></span> <span data-ttu-id="ca42c-242">这意味着，你不能设置为 nillable 列**DbNull**在多个记录中对 Oracle 数据库插入操作。</span><span class="sxs-lookup"><span data-stu-id="ca42c-242">This means that you cannot set a nillable column to **DbNull** on the Oracle database in a multiple record Insert operation.</span></span>  
  
-   <span data-ttu-id="ca42c-243">**插入操作。**</span><span class="sxs-lookup"><span data-stu-id="ca42c-243">**Insert operation.**</span></span> <span data-ttu-id="ca42c-244">没有对涉及大型的记录集的多个记录插入操作流式处理支持。</span><span class="sxs-lookup"><span data-stu-id="ca42c-244">There is no streaming support for multiple record insert operations that involve a large record set.</span></span>  
  
-   <span data-ttu-id="ca42c-245">**更新操作。**</span><span class="sxs-lookup"><span data-stu-id="ca42c-245">**Update operation.**</span></span> <span data-ttu-id="ca42c-246">在更新操作中使用的模板记录是强类型，并因此包含行的所有列。</span><span class="sxs-lookup"><span data-stu-id="ca42c-246">The template record used in an Update operation is strongly-typed and therefore includes all row columns.</span></span> <span data-ttu-id="ca42c-247">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]解释此记录，以表示中的 null 值，应从更新操作中排除列; 但是，非 nillable 列，无法排除不它们能为 null 值。</span><span class="sxs-lookup"><span data-stu-id="ca42c-247">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] interprets a null value in this record to mean that the column should be excluded from the Update operation; however, non-nillable columns cannot be excluded because you cannot them to a null value.</span></span> <span data-ttu-id="ca42c-248">因此，当执行更新操作时必须指定非 nillable 列的值。</span><span class="sxs-lookup"><span data-stu-id="ca42c-248">Therefore, you must specify values for non-nillable columns when you perform an Update operation.</span></span>  
  
-   <span data-ttu-id="ca42c-249">**更新操作。**</span><span class="sxs-lookup"><span data-stu-id="ca42c-249">**Update operation.**</span></span> <span data-ttu-id="ca42c-250">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]解释**DbNull**模板记录表示应从操作中排除列中的 nillable 数据列中的值。</span><span class="sxs-lookup"><span data-stu-id="ca42c-250">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] interprets a **DbNull** value in a nillable data column in the template record to mean that the column should be excluded from the operation.</span></span> <span data-ttu-id="ca42c-251">这意味着，你不能设置为 nillable 列**DbNull**通过更新操作对 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="ca42c-251">This means that you cannot set a nillable column to **DbNull** on the Oracle database by using the Update operation.</span></span>  
  
-   <span data-ttu-id="ca42c-252">**选择操作。**</span><span class="sxs-lookup"><span data-stu-id="ca42c-252">**Select operation.**</span></span> <span data-ttu-id="ca42c-253">没有用于返回较大的记录集的 SELECT 查询流式处理支持。</span><span class="sxs-lookup"><span data-stu-id="ca42c-253">There is no streaming support for SELECT queries that return a large record set.</span></span>  
  
 <span data-ttu-id="ca42c-254">对于这些限制其中面临的挑战的方案，可以使用 WCF 通道模型，因为调用该操作：</span><span class="sxs-lookup"><span data-stu-id="ca42c-254">For scenarios where these limitations present challenges, you can invoke the operation by using the WCF channel model because:</span></span>  
  
-   <span data-ttu-id="ca42c-255">通过使用 WCF 通道模型，你可以从更新和插入操作中排除特定的数据列。</span><span class="sxs-lookup"><span data-stu-id="ca42c-255">By using the WCF channel model, you can exclude specific data columns from Update and Insert operations.</span></span>  
  
-   <span data-ttu-id="ca42c-256">WCF 通道模型提供节点级别的流支持的基本 SQL 操作，它[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]公开。</span><span class="sxs-lookup"><span data-stu-id="ca42c-256">The WCF channel model provides node-level streaming support for the basic SQL operations that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] exposes.</span></span>  
  
 <span data-ttu-id="ca42c-257">有关使用具有 WCF 通道模型的详细信息[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[开发 Oracle 数据库应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)。</span><span class="sxs-lookup"><span data-stu-id="ca42c-257">For more information about using the WCF channel model with the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Develop Oracle Database Applications Using the WCF Channel Model](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca42c-258">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ca42c-258">See Also</span></span>  
 [<span data-ttu-id="ca42c-259">开发 Oracle 数据库应用程序使用 WCF 通道模型</span><span class="sxs-lookup"><span data-stu-id="ca42c-259">Develop Oracle Database Applications Using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)