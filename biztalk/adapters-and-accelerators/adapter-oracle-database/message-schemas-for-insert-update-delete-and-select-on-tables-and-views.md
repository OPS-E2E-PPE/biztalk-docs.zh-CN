---
title: "对于基本 Insert、 Update、 Delete 消息架构，然后选择表和视图上的操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- operations on tables, message actions for
- table operations, message actions for
- table operations, message structure for
- operations on tables, message schemas for
- table operations, message schemas for
- operations on tables, message structure for
ms.assetid: 8228d5e6-14af-49e0-b34b-be03aea59189
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 571a6a192ca85eb0bd3e5abeb8ef8f3715818236
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="message-schemas-for-the-basic-insert-update-delete-and-select-operations-on-tables-and-views"></a><span data-ttu-id="4a3f2-102">消息架构的基本的插入、 更新、 删除和选择表和视图上的操作</span><span class="sxs-lookup"><span data-stu-id="4a3f2-102">Message Schemas for the Basic Insert, Update, Delete, and Select Operations on Tables and Views</span></span>
<span data-ttu-id="4a3f2-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]曲面基本插入、 更新，删除，并选择操作为每个表，然后查看 Oracle 数据库中。</span><span class="sxs-lookup"><span data-stu-id="4a3f2-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces basic Insert, Update, Delete, and Select operations for each table and view in the Oracle database.</span></span> <span data-ttu-id="4a3f2-104">这些操作执行的适当的 SQL 语句，由 WHERE 子句限定。</span><span class="sxs-lookup"><span data-stu-id="4a3f2-104">These operations perform the appropriate SQL statement qualified by a WHERE clause.</span></span> <span data-ttu-id="4a3f2-105">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]这些操作中使用强类型的记录和记录集。</span><span class="sxs-lookup"><span data-stu-id="4a3f2-105">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] uses strongly-typed records and record sets in these operations.</span></span>  
  
## <a name="message-structure-for-basic-table-operations"></a><span data-ttu-id="4a3f2-106">基本的表操作的消息结构</span><span class="sxs-lookup"><span data-stu-id="4a3f2-106">Message Structure for Basic Table Operations</span></span>  
 <span data-ttu-id="4a3f2-107">下表显示通过公开的基本的表操作的 XML 消息结构[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]Oracle 数据库表。</span><span class="sxs-lookup"><span data-stu-id="4a3f2-107">The following table shows the XML message structure for the basic table operations exposed by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] on Oracle database tables.</span></span> <span data-ttu-id="4a3f2-108">操作的目标表中的消息操作指定，也会出现在目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="4a3f2-108">The target table for an operation is specified in the message action and also appears in the target namespace.</span></span>  

### <a name="insert"></a><span data-ttu-id="4a3f2-109">Insert</span><span class="sxs-lookup"><span data-stu-id="4a3f2-109">Insert</span></span>  
<span data-ttu-id="4a3f2-110">有以下类型的插入操作。</span><span class="sxs-lookup"><span data-stu-id="4a3f2-110">There are the following types of Insert operations.</span></span> <span data-ttu-id="4a3f2-111">一条消息可以包含仅一种类型的插入操作。</span><span class="sxs-lookup"><span data-stu-id="4a3f2-111">A message can contain only one kind of Insert operation.</span></span>

- <span data-ttu-id="4a3f2-112">多个记录插入到目标表中插入强类型化数据提供的记录的集。</span><span class="sxs-lookup"><span data-stu-id="4a3f2-112">Multiple Record Insert inserts the supplied record set of strongly-typed data into the target table.</span></span>
- <span data-ttu-id="4a3f2-113">为在多个记录插入每个记录，你可以为指定值调用一个可选属性**InlineValue**。</span><span class="sxs-lookup"><span data-stu-id="4a3f2-113">For each record in a multiple record insert, you can specify value for an optional attribute called **InlineValue**.</span></span> <span data-ttu-id="4a3f2-114">如果指定，它将重写元素的值。</span><span class="sxs-lookup"><span data-stu-id="4a3f2-114">If specified, it overrides the value of the element.</span></span>
- <span data-ttu-id="4a3f2-115">大容量插入将插入到目标表的查询元素中指定 SELECT 查询返回的记录集。</span><span class="sxs-lookup"><span data-stu-id="4a3f2-115">Bulk Insert inserts the record set returned by a SELECT query specified in the QUERY element into the target table.</span></span> <span data-ttu-id="4a3f2-116">这可通过使用 COLUMN_NAMES 元素中指定的列的逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="4a3f2-116">This is done by using the comma-separated list of columns specified in the COLUMN_NAMES element.</span></span>

#### <a name="xml-message"></a><span data-ttu-id="4a3f2-117">XML 消息</span><span class="sxs-lookup"><span data-stu-id="4a3f2-117">XML message</span></span>  

<span data-ttu-id="4a3f2-118">**多个记录插入**</span><span class="sxs-lookup"><span data-stu-id="4a3f2-118">**Multiple record insert**</span></span>  
```
<Insert xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<RECORDSET>     
<[TABLE_NAME]RECORDINSERT>       
<[FIELD1_NAME InlineValue="value"]>value1</[FIELD1_NAME]>       
<[FIELD2_NAME InlineValue="value"]>value2</[FIELD2_NAME]>       
…     
</[TABLE_NAME]RECORDINSERT>       
<[TABLE_NAME]RECORDINSERT >       
<[FIELD1_NAME InlineValue="value"]>value1</[FIELD1_NAME]>       
<[FIELD2_NAME InlineValue="value"]>value2</[FIELD2_NAME]>       
…     
</[TABLE_NAME]RECORDINSERT>     
…   
</RECORDSET> 
</Insert>
```

<span data-ttu-id="4a3f2-119">SQL 适配器执行：`INSERT INTO TABLE_NAME (FIELD1_NAME, FIELD2_NAME, …)VALUES (value1, value2, …);`</span><span class="sxs-lookup"><span data-stu-id="4a3f2-119">SQL executed by the adapter: `INSERT INTO TABLE_NAME (FIELD1_NAME, FIELD2_NAME, …)VALUES (value1, value2, …);`</span></span>


<span data-ttu-id="4a3f2-120">**大容量插入**</span><span class="sxs-lookup"><span data-stu-id="4a3f2-120">**Bulk Insert**</span></span>  
```
<Insert xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">
<COLUMN_NAMES>[COLUMN_list]</COLUMN_NAMES>
<QUERY>[SELECT_query]</QUERY>
</Insert>
```

<span data-ttu-id="4a3f2-121">SQL 适配器执行：`INSERT INTO TABLE_NAME (COLUMN_list) SELECT_query;`</span><span class="sxs-lookup"><span data-stu-id="4a3f2-121">SQL executed by the adapter: `INSERT INTO TABLE_NAME (COLUMN_list) SELECT_query;`</span></span>

### <a name="insert-response"></a><span data-ttu-id="4a3f2-122">将响应</span><span class="sxs-lookup"><span data-stu-id="4a3f2-122">Insert Response</span></span>
<span data-ttu-id="4a3f2-123">InsertResult 元素中返回插入的行数。</span><span class="sxs-lookup"><span data-stu-id="4a3f2-123">The number of rows inserted is returned in the InsertResult element.</span></span>

#### <a name="xml-message"></a><span data-ttu-id="4a3f2-124">XML 消息</span><span class="sxs-lookup"><span data-stu-id="4a3f2-124">XML message</span></span>  

```
<InsertResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<InsertResult>[rows inserted]</InsertResult> 
</InsertResponse>
```

### <a name="select"></a><span data-ttu-id="4a3f2-125">选择</span><span class="sxs-lookup"><span data-stu-id="4a3f2-125">Select</span></span>
<span data-ttu-id="4a3f2-126">SELECT 查询执行使用 WHERE 子句筛选器元素中指定的目标表中。</span><span class="sxs-lookup"><span data-stu-id="4a3f2-126">A SELECT query is performed on the target table using the WHERE clause specified in the FILTER element.</span></span> <span data-ttu-id="4a3f2-127">结果集包含 COLUMN_NAMES 元素中指定的列名称的逗号分隔的列表中的列。</span><span class="sxs-lookup"><span data-stu-id="4a3f2-127">The result set contains the columns in the comma-separated list of column names specified in the COLUMN_NAMES element.</span></span>

#### <a name="xml-message"></a><span data-ttu-id="4a3f2-128">XML 消息</span><span class="sxs-lookup"><span data-stu-id="4a3f2-128">XML message</span></span>  
```
<Select xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<COLUMN_NAMES>[COLUMN_list]</COLUMN_NAMES>   
<FILTER>WHERE_clause</FILTER> 
</Select>
```

<span data-ttu-id="4a3f2-129">SQL 适配器执行：`SELECT COLUMN_list FROM TABLE_NAME WHERE WHERE_clause;`</span><span class="sxs-lookup"><span data-stu-id="4a3f2-129">SQL executed by the adapter: `SELECT COLUMN_list FROM TABLE_NAME WHERE WHERE_clause;`</span></span>

### <a name="select-response"></a><span data-ttu-id="4a3f2-130">选择响应</span><span class="sxs-lookup"><span data-stu-id="4a3f2-130">Select Response</span></span>
<span data-ttu-id="4a3f2-131">由 SELECT 查询生成的结果集。</span><span class="sxs-lookup"><span data-stu-id="4a3f2-131">The result set generated by the SELECT query.</span></span>

#### <a name="xml-message"></a><span data-ttu-id="4a3f2-132">XML 消息</span><span class="sxs-lookup"><span data-stu-id="4a3f2-132">XML message</span></span>  
```
<SelectResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<SelectResult>     
<[TABLE_NAME]RECORDSELECT>       
<[FIELD1_NAME]>value1</[FIELD1_NAME]>       
<[FIELD2_NAME]>value2</[FIELD2_NAME]>       
…     
</[TABLE_NAME]RECORDSELECT>   
</SelectResult> 
</SelectResponse>
``` 

### <a name="update"></a><span data-ttu-id="4a3f2-133">Update</span><span class="sxs-lookup"><span data-stu-id="4a3f2-133">Update</span></span>
<span data-ttu-id="4a3f2-134">行匹配 where 子句筛选器元素中指定更新到记录集中指定的值。</span><span class="sxs-lookup"><span data-stu-id="4a3f2-134">Rows that match the where clause specified in the FILTER element are updated to the values specified in the RECORDSET.</span></span> <span data-ttu-id="4a3f2-135">仅在记录集中指定的列会更新到每个匹配行。</span><span class="sxs-lookup"><span data-stu-id="4a3f2-135">Only the columns that are specified in the RECORDSET are updated in each matching row.</span></span>

#### <a name="xml-message"></a><span data-ttu-id="4a3f2-136">XML 消息</span><span class="sxs-lookup"><span data-stu-id="4a3f2-136">XML message</span></span>  
```
<Update xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<RECORDSET>     
<[FIELD1_NAME]>value1</[FIELD1_NAME]>     
<[FIELD2_NAME]>value2</[FIELD2_NAME]>       
…   
</RECORDSET>   
<FILTER>WHERE_clause</FILTER> </Update>
```

<span data-ttu-id="4a3f2-137">SQL 适配器执行：`UPDATE [TABLE_NAME] SET [FIELD1_NAME] = value1, [FIELD2_NAME] = value2, … WHERE WHERE_clause;`</span><span class="sxs-lookup"><span data-stu-id="4a3f2-137">SQL executed by the adapter: `UPDATE [TABLE_NAME] SET [FIELD1_NAME] = value1, [FIELD2_NAME] = value2, … WHERE WHERE_clause;`</span></span>

### <a name="update-response"></a><span data-ttu-id="4a3f2-138">更新响应</span><span class="sxs-lookup"><span data-stu-id="4a3f2-138">Update Response</span></span>
<span data-ttu-id="4a3f2-139">UpdateResult 元素中返回更新的行数。</span><span class="sxs-lookup"><span data-stu-id="4a3f2-139">The number of rows updated is returned in the UpdateResult element.</span></span>

#### <a name="xml-message"></a><span data-ttu-id="4a3f2-140">XML 消息</span><span class="sxs-lookup"><span data-stu-id="4a3f2-140">XML message</span></span>  
```
<UpdateResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<UpdateResult>[rows inserted]</UpdateResult> 
</UpdateResponse>
```

### <a name="delete"></a><span data-ttu-id="4a3f2-141">DELETE</span><span class="sxs-lookup"><span data-stu-id="4a3f2-141">Delete</span></span>
<span data-ttu-id="4a3f2-142">删除行匹配筛选器元素指定 WHERE 子句。</span><span class="sxs-lookup"><span data-stu-id="4a3f2-142">Rows matching the WHERE clause specified by the FILTER element are deleted.</span></span>

#### <a name="xml-message"></a><span data-ttu-id="4a3f2-143">XML 消息</span><span class="sxs-lookup"><span data-stu-id="4a3f2-143">XML message</span></span> 
```
<Delete xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<FILTER>WHERE_clause</FILTER> 
</Delete>
```

<span data-ttu-id="4a3f2-144">SQL 适配器执行：`DELETE FROM [TABLE_NAME] WHERE WHERE_clause;`</span><span class="sxs-lookup"><span data-stu-id="4a3f2-144">SQL executed by the adapter: `DELETE FROM [TABLE_NAME] WHERE WHERE_clause;`</span></span>

### <a name="delete-response"></a><span data-ttu-id="4a3f2-145">删除响应</span><span class="sxs-lookup"><span data-stu-id="4a3f2-145">Delete Response</span></span>
<span data-ttu-id="4a3f2-146">删除的行数返回 DeleteResult 元素中。</span><span class="sxs-lookup"><span data-stu-id="4a3f2-146">The number of rows deleted is returned in the DeleteResult element.</span></span>

#### <a name="xml-message"></a><span data-ttu-id="4a3f2-147">XML 消息</span><span class="sxs-lookup"><span data-stu-id="4a3f2-147">XML message</span></span> 
```
<DeleteResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<DeleteResult>[rows inserted]</DeleteResult> 
</DeleteResponse>
```
  
  | <span data-ttu-id="4a3f2-148">占位符值</span><span class="sxs-lookup"><span data-stu-id="4a3f2-148">Placeholder value</span></span>| <span data-ttu-id="4a3f2-149">Description</span><span class="sxs-lookup"><span data-stu-id="4a3f2-149">Description</span></span> |
  | --- | --- |
  | <span data-ttu-id="4a3f2-150">[VERSION]</span><span class="sxs-lookup"><span data-stu-id="4a3f2-150">[VERSION]</span></span> | <span data-ttu-id="4a3f2-151">消息版本字符串;例如，`http://Microsoft.LobServices.OracleDB/2007/03`</span><span class="sxs-lookup"><span data-stu-id="4a3f2-151">The message version string; for example, `http://Microsoft.LobServices.OracleDB/2007/03`</span></span>|
  | <span data-ttu-id="4a3f2-152">[架构]</span><span class="sxs-lookup"><span data-stu-id="4a3f2-152">[SCHEMA]</span></span> | <span data-ttu-id="4a3f2-153">Oracle 项目; 的集合例如，`SCOTT`</span><span class="sxs-lookup"><span data-stu-id="4a3f2-153">Collection of Oracle artifacts; for example, `SCOTT`</span></span>|
  | <span data-ttu-id="4a3f2-154">[TABLE_NAME]</span><span class="sxs-lookup"><span data-stu-id="4a3f2-154">[TABLE_NAME]</span></span> | <span data-ttu-id="4a3f2-155">表; 的名称例如，`EMP`</span><span class="sxs-lookup"><span data-stu-id="4a3f2-155">Name of the table; for example, `EMP`</span></span>|
  | <span data-ttu-id="4a3f2-156">[FIELD1_NAME]</span><span class="sxs-lookup"><span data-stu-id="4a3f2-156">[FIELD1_NAME]</span></span> | <span data-ttu-id="4a3f2-157">表字段名称;例如，`EMPNAME`</span><span class="sxs-lookup"><span data-stu-id="4a3f2-157">Table field name; for example, `EMPNAME`</span></span>|
  | <span data-ttu-id="4a3f2-158">[COLUMN_list]</span><span class="sxs-lookup"><span data-stu-id="4a3f2-158">[COLUMN_list]</span></span> | <span data-ttu-id="4a3f2-159">逗号分隔列表的其中一列。例如，`NAME`</span><span class="sxs-lookup"><span data-stu-id="4a3f2-159">Comma-separated list of columns; for example, `NAME`</span></span>|
  | <span data-ttu-id="4a3f2-160">[SELECT_query]</span><span class="sxs-lookup"><span data-stu-id="4a3f2-160">[SELECT_query]</span></span> | <span data-ttu-id="4a3f2-161">大容量插入的操作; 查询元素中指定 SQL SELECT 语句例如，`SELECT * from MyTable`</span><span class="sxs-lookup"><span data-stu-id="4a3f2-161">A SQL SELECT statement specified in the QUERY element of a Bulk Insert operation; for example, `SELECT * from MyTable`</span></span>|
  | <span data-ttu-id="4a3f2-162">[WHERE_clause]</span><span class="sxs-lookup"><span data-stu-id="4a3f2-162">[WHERE_clause]</span></span> | <span data-ttu-id="4a3f2-163">SELECT 语句用于执行的操作; WHERE_clause例如，`ID > 10`</span><span class="sxs-lookup"><span data-stu-id="4a3f2-163">WHERE_clause for the SELECT statement used for the operation; for example, `ID > 10`</span></span>|
  
> [!IMPORTANT]
>  <span data-ttu-id="4a3f2-164">视图上的基本的表操作的消息结构是相同的表，但该操作的命名空间指定视图而不是表： `<Insert xmlns ="[VERSION]/[SCHEMA]/``View``/[VIEW_NAME]">`。</span><span class="sxs-lookup"><span data-stu-id="4a3f2-164">The message structure for the basic table operations on views is the same as that on tables, but the namespace for the operation specifies a view rather than a table: `<Insert xmlns ="[VERSION]/[SCHEMA]/``View``/[VIEW_NAME]">`.</span></span>  
  
## <a name="message-actions-for-basic-table-operations"></a><span data-ttu-id="4a3f2-165">基本的表操作的消息操作</span><span class="sxs-lookup"><span data-stu-id="4a3f2-165">Message Actions for Basic Table Operations</span></span>  
 <span data-ttu-id="4a3f2-166">下表显示使用的消息操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]表上的基本的表操作。</span><span class="sxs-lookup"><span data-stu-id="4a3f2-166">The following table shows the message actions that are used by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] for the basic table operations on tables.</span></span> <span data-ttu-id="4a3f2-167">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用的消息操作中指定的表名称来确定该操作的目标表。</span><span class="sxs-lookup"><span data-stu-id="4a3f2-167">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] uses the table name specified in the message action to determine the target table of the operation.</span></span>  
  
|<span data-ttu-id="4a3f2-168">运算</span><span class="sxs-lookup"><span data-stu-id="4a3f2-168">Operation</span></span>|<span data-ttu-id="4a3f2-169">消息操作</span><span class="sxs-lookup"><span data-stu-id="4a3f2-169">Message Action</span></span>|<span data-ttu-id="4a3f2-170">示例</span><span class="sxs-lookup"><span data-stu-id="4a3f2-170">Example</span></span>|  
|---------------|--------------------|-------------|  
|<span data-ttu-id="4a3f2-171">Insert</span><span class="sxs-lookup"><span data-stu-id="4a3f2-171">Insert</span></span>|<span data-ttu-id="4a3f2-172">[VERSION] / [架构] /Table/ [TABLE_NAME] / 插入</span><span class="sxs-lookup"><span data-stu-id="4a3f2-172">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Insert</span></span>|<span data-ttu-id="4a3f2-173">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert</span><span class="sxs-lookup"><span data-stu-id="4a3f2-173">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert</span></span>|  
|<span data-ttu-id="4a3f2-174">将响应</span><span class="sxs-lookup"><span data-stu-id="4a3f2-174">Insert Response</span></span>|<span data-ttu-id="4a3f2-175">[VERSION] / [架构] /Table/ [TABLE_NAME] / 插入/响应</span><span class="sxs-lookup"><span data-stu-id="4a3f2-175">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Insert/response</span></span>|<span data-ttu-id="4a3f2-176">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert/response</span><span class="sxs-lookup"><span data-stu-id="4a3f2-176">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert/response</span></span>|  
|<span data-ttu-id="4a3f2-177">选择</span><span class="sxs-lookup"><span data-stu-id="4a3f2-177">Select</span></span>|<span data-ttu-id="4a3f2-178">[VERSION] / [架构] /Table/ [TABLE_NAME] / 选择</span><span class="sxs-lookup"><span data-stu-id="4a3f2-178">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Select</span></span>|<span data-ttu-id="4a3f2-179">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Select</span><span class="sxs-lookup"><span data-stu-id="4a3f2-179">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Select</span></span>|  
|<span data-ttu-id="4a3f2-180">选择响应</span><span class="sxs-lookup"><span data-stu-id="4a3f2-180">Select Response</span></span>|<span data-ttu-id="4a3f2-181">[VERSION] / [架构] /Table/ [TABLE_NAME] / 选择/响应</span><span class="sxs-lookup"><span data-stu-id="4a3f2-181">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Select/response</span></span>|<span data-ttu-id="4a3f2-182">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Select/response</span><span class="sxs-lookup"><span data-stu-id="4a3f2-182">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Select/response</span></span>|  
|<span data-ttu-id="4a3f2-183">Update</span><span class="sxs-lookup"><span data-stu-id="4a3f2-183">Update</span></span>|<span data-ttu-id="4a3f2-184">[VERSION] / [架构] /Table/ [TABLE_NAME] / 更新</span><span class="sxs-lookup"><span data-stu-id="4a3f2-184">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Update</span></span>|<span data-ttu-id="4a3f2-185">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update</span><span class="sxs-lookup"><span data-stu-id="4a3f2-185">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update</span></span>|  
|<span data-ttu-id="4a3f2-186">更新响应</span><span class="sxs-lookup"><span data-stu-id="4a3f2-186">Update Response</span></span>|<span data-ttu-id="4a3f2-187">[VERSION] / [架构] /Table/ [TABLE_NAME] / 更新/响应</span><span class="sxs-lookup"><span data-stu-id="4a3f2-187">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Update/response</span></span>|<span data-ttu-id="4a3f2-188">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update/response</span><span class="sxs-lookup"><span data-stu-id="4a3f2-188">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update/response</span></span>|  
|<span data-ttu-id="4a3f2-189">DELETE</span><span class="sxs-lookup"><span data-stu-id="4a3f2-189">Delete</span></span>|<span data-ttu-id="4a3f2-190">[VERSION] / [架构] /Table/ [TABLE_NAME] / 删除</span><span class="sxs-lookup"><span data-stu-id="4a3f2-190">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Delete</span></span>|<span data-ttu-id="4a3f2-191">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete</span><span class="sxs-lookup"><span data-stu-id="4a3f2-191">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete</span></span>|  
|<span data-ttu-id="4a3f2-192">删除响应</span><span class="sxs-lookup"><span data-stu-id="4a3f2-192">Delete Response</span></span>|<span data-ttu-id="4a3f2-193">[VERSION] / [架构] /Table/ [TABLE_NAME] / 删除/响应</span><span class="sxs-lookup"><span data-stu-id="4a3f2-193">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Delete/response</span></span>|<span data-ttu-id="4a3f2-194">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete/response</span><span class="sxs-lookup"><span data-stu-id="4a3f2-194">http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete/response</span></span>|  
  
 <span data-ttu-id="4a3f2-195">[VERSION] = 消息版本字符串;例如，http://Microsoft.LobServices.OracleDB/2007/03。</span><span class="sxs-lookup"><span data-stu-id="4a3f2-195">[VERSION] = The message version string; for example, http://Microsoft.LobServices.OracleDB/2007/03.</span></span>  
  
 <span data-ttu-id="4a3f2-196">[架构] = Oracle 集合项目;例如，SCOTT。</span><span class="sxs-lookup"><span data-stu-id="4a3f2-196">[SCHEMA] = Collection of Oracle artifacts; for example, SCOTT.</span></span>  
  
 <span data-ttu-id="4a3f2-197">[TABLE_NAME] = 表; 的名称例如，EMP。</span><span class="sxs-lookup"><span data-stu-id="4a3f2-197">[TABLE_NAME] = Name of the table; for example, EMP.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4a3f2-198">在视图上的操作的消息操作相同的表只是"视图"替换"Table";例如， `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/``View``/EMPVIEW/Insert`。</span><span class="sxs-lookup"><span data-stu-id="4a3f2-198">The message action for an operation on a view is the same as that for a table except that "View" replaces "Table"; for example, `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/``View``/EMPVIEW/Insert`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a3f2-199">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4a3f2-199">See Also</span></span>  
 [<span data-ttu-id="4a3f2-200">消息和用于 Oracle 数据库的 BizTalk Adapter 的消息架构</span><span class="sxs-lookup"><span data-stu-id="4a3f2-200">Messages and Message Schemas for BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)