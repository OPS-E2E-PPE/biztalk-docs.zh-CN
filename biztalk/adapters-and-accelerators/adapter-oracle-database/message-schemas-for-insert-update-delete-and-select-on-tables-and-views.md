---
title: 基本的 Insert、 Update、 delete，消息架构，并选择表和视图操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- operations on tables, message actions for
- table operations, message actions for
- table operations, message structure for
- operations on tables, message schemas for
- table operations, message schemas for
- operations on tables, message structure for
ms.assetid: 8228d5e6-14af-49e0-b34b-be03aea59189
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7f815f88144c2cb3659614c517fdc224c601e27
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989190"
---
# <a name="message-schemas-for-the-basic-insert-update-delete-and-select-operations-on-tables-and-views"></a><span data-ttu-id="c3aa9-102">消息架构进行基本插入、 更新、 删除和选择表和视图的操作</span><span class="sxs-lookup"><span data-stu-id="c3aa9-102">Message Schemas for the Basic Insert, Update, Delete, and Select Operations on Tables and Views</span></span>
<span data-ttu-id="c3aa9-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]图面基本 Insert、 Update、 Delete 和 Select 操作为每个表并查看 Oracle 数据库中。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces basic Insert, Update, Delete, and Select operations for each table and view in the Oracle database.</span></span> <span data-ttu-id="c3aa9-104">这些操作执行适当的 SQL 语句的 WHERE 子句的限定。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-104">These operations perform the appropriate SQL statement qualified by a WHERE clause.</span></span> <span data-ttu-id="c3aa9-105">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]这些操作中使用强类型的记录和记录集。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-105">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] uses strongly-typed records and record sets in these operations.</span></span>  

## <a name="message-structure-for-basic-table-operations"></a><span data-ttu-id="c3aa9-106">基本的表操作的消息结构</span><span class="sxs-lookup"><span data-stu-id="c3aa9-106">Message Structure for Basic Table Operations</span></span>  
 <span data-ttu-id="c3aa9-107">下表显示了通过公开的基本表操作的 XML 消息结构[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]对 Oracle 数据库表。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-107">The following table shows the XML message structure for the basic table operations exposed by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] on Oracle database tables.</span></span> <span data-ttu-id="c3aa9-108">操作的目标表中的消息操作指定和也会出现在目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-108">The target table for an operation is specified in the message action and also appears in the target namespace.</span></span>  

### <a name="insert"></a><span data-ttu-id="c3aa9-109">Insert</span><span class="sxs-lookup"><span data-stu-id="c3aa9-109">Insert</span></span>  
<span data-ttu-id="c3aa9-110">有以下类型的插入操作。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-110">There are the following types of Insert operations.</span></span> <span data-ttu-id="c3aa9-111">消息可以包含仅一种类型的插入操作。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-111">A message can contain only one kind of Insert operation.</span></span>

- <span data-ttu-id="c3aa9-112">多个记录插入到目标表中插入强类型化数据提供的记录的集。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-112">Multiple Record Insert inserts the supplied record set of strongly-typed data into the target table.</span></span>
- <span data-ttu-id="c3aa9-113">对于在多个记录插入每个记录，可以指定一个名为可选属性的值**InlineValue**。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-113">For each record in a multiple record insert, you can specify value for an optional attribute called **InlineValue**.</span></span> <span data-ttu-id="c3aa9-114">如果指定，它将替代该元素的值。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-114">If specified, it overrides the value of the element.</span></span>
- <span data-ttu-id="c3aa9-115">大容量插入将插入到目标表的查询元素中指定的 SELECT 查询返回的记录集。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-115">Bulk Insert inserts the record set returned by a SELECT query specified in the QUERY element into the target table.</span></span> <span data-ttu-id="c3aa9-116">这是通过使用 COLUMN_NAMES 元素中指定的列以逗号分隔的列表。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-116">This is done by using the comma-separated list of columns specified in the COLUMN_NAMES element.</span></span>

#### <a name="xml-message"></a><span data-ttu-id="c3aa9-117">XML 消息</span><span class="sxs-lookup"><span data-stu-id="c3aa9-117">XML message</span></span>  

<span data-ttu-id="c3aa9-118">**多个记录插入**</span><span class="sxs-lookup"><span data-stu-id="c3aa9-118">**Multiple record insert**</span></span>  
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

<span data-ttu-id="c3aa9-119">SQL 适配器执行： `INSERT INTO TABLE_NAME (FIELD1_NAME, FIELD2_NAME, …)VALUES (value1, value2, …);`</span><span class="sxs-lookup"><span data-stu-id="c3aa9-119">SQL executed by the adapter: `INSERT INTO TABLE_NAME (FIELD1_NAME, FIELD2_NAME, …)VALUES (value1, value2, …);`</span></span>


<span data-ttu-id="c3aa9-120">**大容量插入**</span><span class="sxs-lookup"><span data-stu-id="c3aa9-120">**Bulk Insert**</span></span>  
```
<Insert xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">
<COLUMN_NAMES>[COLUMN_list]</COLUMN_NAMES>
<QUERY>[SELECT_query]</QUERY>
</Insert>
```

<span data-ttu-id="c3aa9-121">SQL 适配器执行： `INSERT INTO TABLE_NAME (COLUMN_list) SELECT_query;`</span><span class="sxs-lookup"><span data-stu-id="c3aa9-121">SQL executed by the adapter: `INSERT INTO TABLE_NAME (COLUMN_list) SELECT_query;`</span></span>

### <a name="insert-response"></a><span data-ttu-id="c3aa9-122">将响应插入</span><span class="sxs-lookup"><span data-stu-id="c3aa9-122">Insert Response</span></span>
<span data-ttu-id="c3aa9-123">InsertResult 元素中返回插入的行数。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-123">The number of rows inserted is returned in the InsertResult element.</span></span>

#### <a name="xml-message"></a><span data-ttu-id="c3aa9-124">XML 消息</span><span class="sxs-lookup"><span data-stu-id="c3aa9-124">XML message</span></span>  

```
<InsertResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<InsertResult>[rows inserted]</InsertResult> 
</InsertResponse>
```

### <a name="select"></a><span data-ttu-id="c3aa9-125">选择</span><span class="sxs-lookup"><span data-stu-id="c3aa9-125">Select</span></span>
<span data-ttu-id="c3aa9-126">使用 WHERE 子句筛选器元素中指定的目标表执行 SELECT 查询。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-126">A SELECT query is performed on the target table using the WHERE clause specified in the FILTER element.</span></span> <span data-ttu-id="c3aa9-127">结果集包含 COLUMN_NAMES 元素中指定的列名称的逗号分隔的列表中的列。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-127">The result set contains the columns in the comma-separated list of column names specified in the COLUMN_NAMES element.</span></span>

#### <a name="xml-message"></a><span data-ttu-id="c3aa9-128">XML 消息</span><span class="sxs-lookup"><span data-stu-id="c3aa9-128">XML message</span></span>  
```
<Select xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<COLUMN_NAMES>[COLUMN_list]</COLUMN_NAMES>   
<FILTER>WHERE_clause</FILTER> 
</Select>
```

<span data-ttu-id="c3aa9-129">SQL 适配器执行： `SELECT COLUMN_list FROM TABLE_NAME WHERE WHERE_clause;`</span><span class="sxs-lookup"><span data-stu-id="c3aa9-129">SQL executed by the adapter: `SELECT COLUMN_list FROM TABLE_NAME WHERE WHERE_clause;`</span></span>

### <a name="select-response"></a><span data-ttu-id="c3aa9-130">选择响应</span><span class="sxs-lookup"><span data-stu-id="c3aa9-130">Select Response</span></span>
<span data-ttu-id="c3aa9-131">SELECT 查询生成的结果集。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-131">The result set generated by the SELECT query.</span></span>

#### <a name="xml-message"></a><span data-ttu-id="c3aa9-132">XML 消息</span><span class="sxs-lookup"><span data-stu-id="c3aa9-132">XML message</span></span>  
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

### <a name="update"></a><span data-ttu-id="c3aa9-133">Update</span><span class="sxs-lookup"><span data-stu-id="c3aa9-133">Update</span></span>
<span data-ttu-id="c3aa9-134">位置匹配的行筛选器元素中指定的子句更新到记录集中指定的值。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-134">Rows that match the where clause specified in the FILTER element are updated to the values specified in the RECORDSET.</span></span> <span data-ttu-id="c3aa9-135">指定在记录集中的列中每个匹配行更新。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-135">Only the columns that are specified in the RECORDSET are updated in each matching row.</span></span>

#### <a name="xml-message"></a><span data-ttu-id="c3aa9-136">XML 消息</span><span class="sxs-lookup"><span data-stu-id="c3aa9-136">XML message</span></span>  
```
<Update xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<RECORDSET>     
<[FIELD1_NAME]>value1</[FIELD1_NAME]>     
<[FIELD2_NAME]>value2</[FIELD2_NAME]>       
…   
</RECORDSET>   
<FILTER>WHERE_clause</FILTER> </Update>
```

<span data-ttu-id="c3aa9-137">SQL 适配器执行： `UPDATE [TABLE_NAME] SET [FIELD1_NAME] = value1, [FIELD2_NAME] = value2, … WHERE WHERE_clause;`</span><span class="sxs-lookup"><span data-stu-id="c3aa9-137">SQL executed by the adapter: `UPDATE [TABLE_NAME] SET [FIELD1_NAME] = value1, [FIELD2_NAME] = value2, … WHERE WHERE_clause;`</span></span>

### <a name="update-response"></a><span data-ttu-id="c3aa9-138">更新响应</span><span class="sxs-lookup"><span data-stu-id="c3aa9-138">Update Response</span></span>
<span data-ttu-id="c3aa9-139">UpdateResult 元素中返回更新的行数。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-139">The number of rows updated is returned in the UpdateResult element.</span></span>

#### <a name="xml-message"></a><span data-ttu-id="c3aa9-140">XML 消息</span><span class="sxs-lookup"><span data-stu-id="c3aa9-140">XML message</span></span>  
```
<UpdateResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<UpdateResult>[rows inserted]</UpdateResult> 
</UpdateResponse>
```

### <a name="delete"></a><span data-ttu-id="c3aa9-141">DELETE</span><span class="sxs-lookup"><span data-stu-id="c3aa9-141">Delete</span></span>
<span data-ttu-id="c3aa9-142">删除行匹配的 WHERE 子句中指定的筛选器元素。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-142">Rows matching the WHERE clause specified by the FILTER element are deleted.</span></span>

#### <a name="xml-message"></a><span data-ttu-id="c3aa9-143">XML 消息</span><span class="sxs-lookup"><span data-stu-id="c3aa9-143">XML message</span></span> 
```
<Delete xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<FILTER>WHERE_clause</FILTER> 
</Delete>
```

<span data-ttu-id="c3aa9-144">SQL 适配器执行： `DELETE FROM [TABLE_NAME] WHERE WHERE_clause;`</span><span class="sxs-lookup"><span data-stu-id="c3aa9-144">SQL executed by the adapter: `DELETE FROM [TABLE_NAME] WHERE WHERE_clause;`</span></span>

### <a name="delete-response"></a><span data-ttu-id="c3aa9-145">删除响应</span><span class="sxs-lookup"><span data-stu-id="c3aa9-145">Delete Response</span></span>
<span data-ttu-id="c3aa9-146">删除的行数返回 DeleteResult 元素中。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-146">The number of rows deleted is returned in the DeleteResult element.</span></span>

#### <a name="xml-message"></a><span data-ttu-id="c3aa9-147">XML 消息</span><span class="sxs-lookup"><span data-stu-id="c3aa9-147">XML message</span></span> 
```
<DeleteResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<DeleteResult>[rows inserted]</DeleteResult> 
</DeleteResponse>
```

  | <span data-ttu-id="c3aa9-148">占位符值</span><span class="sxs-lookup"><span data-stu-id="c3aa9-148">Placeholder value</span></span>| <span data-ttu-id="c3aa9-149">Description</span><span class="sxs-lookup"><span data-stu-id="c3aa9-149">Description</span></span> |
  | --- | --- |
  | <span data-ttu-id="c3aa9-150">[版本]</span><span class="sxs-lookup"><span data-stu-id="c3aa9-150">[VERSION]</span></span> | <span data-ttu-id="c3aa9-151">消息版本字符串;例如， `http://Microsoft.LobServices.OracleDB/2007/03`</span><span class="sxs-lookup"><span data-stu-id="c3aa9-151">The message version string; for example, `http://Microsoft.LobServices.OracleDB/2007/03`</span></span>|
  | <span data-ttu-id="c3aa9-152">[架构]</span><span class="sxs-lookup"><span data-stu-id="c3aa9-152">[SCHEMA]</span></span> | <span data-ttu-id="c3aa9-153">Oracle 项目; 的集合例如， `SCOTT`</span><span class="sxs-lookup"><span data-stu-id="c3aa9-153">Collection of Oracle artifacts; for example, `SCOTT`</span></span>|
  | <span data-ttu-id="c3aa9-154">[TABLE_NAME]</span><span class="sxs-lookup"><span data-stu-id="c3aa9-154">[TABLE_NAME]</span></span> | <span data-ttu-id="c3aa9-155">名称的表;例如， `EMP`</span><span class="sxs-lookup"><span data-stu-id="c3aa9-155">Name of the table; for example, `EMP`</span></span>|
  | <span data-ttu-id="c3aa9-156">[FIELD1_NAME]</span><span class="sxs-lookup"><span data-stu-id="c3aa9-156">[FIELD1_NAME]</span></span> | <span data-ttu-id="c3aa9-157">表字段名称;例如， `EMPNAME`</span><span class="sxs-lookup"><span data-stu-id="c3aa9-157">Table field name; for example, `EMPNAME`</span></span>|
  | <span data-ttu-id="c3aa9-158">[COLUMN_list]</span><span class="sxs-lookup"><span data-stu-id="c3aa9-158">[COLUMN_list]</span></span> | <span data-ttu-id="c3aa9-159">以逗号分隔的列;例如， `NAME`</span><span class="sxs-lookup"><span data-stu-id="c3aa9-159">Comma-separated list of columns; for example, `NAME`</span></span>|
  | <span data-ttu-id="c3aa9-160">[SELECT_query]</span><span class="sxs-lookup"><span data-stu-id="c3aa9-160">[SELECT_query]</span></span> | <span data-ttu-id="c3aa9-161">Bulk Insert 操作; 在查询元素中指定一个 SQL SELECT 语句例如， `SELECT * from MyTable`</span><span class="sxs-lookup"><span data-stu-id="c3aa9-161">A SQL SELECT statement specified in the QUERY element of a Bulk Insert operation; for example, `SELECT * from MyTable`</span></span>|
  | <span data-ttu-id="c3aa9-162">[WHERE_clause]</span><span class="sxs-lookup"><span data-stu-id="c3aa9-162">[WHERE_clause]</span></span> | <span data-ttu-id="c3aa9-163">SELECT 语句用于执行的操作; WHERE_clause例如， `ID > 10`</span><span class="sxs-lookup"><span data-stu-id="c3aa9-163">WHERE_clause for the SELECT statement used for the operation; for example, `ID > 10`</span></span>|

> [!IMPORTANT]
>  <span data-ttu-id="c3aa9-164">在视图上的基本表操作的消息结构不相同的表，但该操作的命名空间指定一个视图，而不是一个表： `<Insert xmlns ="[VERSION]/[SCHEMA]/``View``/[VIEW_NAME]">`。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-164">The message structure for the basic table operations on views is the same as that on tables, but the namespace for the operation specifies a view rather than a table: `<Insert xmlns ="[VERSION]/[SCHEMA]/``View``/[VIEW_NAME]">`.</span></span>  

## <a name="message-actions-for-basic-table-operations"></a><span data-ttu-id="c3aa9-165">基本的表操作的消息操作</span><span class="sxs-lookup"><span data-stu-id="c3aa9-165">Message Actions for Basic Table Operations</span></span>  
 <span data-ttu-id="c3aa9-166">下表显示了使用的消息操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]对表的基本表操作。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-166">The following table shows the message actions that are used by the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] for the basic table operations on tables.</span></span> <span data-ttu-id="c3aa9-167">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用的消息操作中指定的表名称来确定该操作的目标表。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-167">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] uses the table name specified in the message action to determine the target table of the operation.</span></span>  


|    <span data-ttu-id="c3aa9-168">运算</span><span class="sxs-lookup"><span data-stu-id="c3aa9-168">Operation</span></span>    |                    <span data-ttu-id="c3aa9-169">消息操作</span><span class="sxs-lookup"><span data-stu-id="c3aa9-169">Message Action</span></span>                     |                                    <span data-ttu-id="c3aa9-170">示例</span><span class="sxs-lookup"><span data-stu-id="c3aa9-170">Example</span></span>                                    |
|-----------------|-------------------------------------------------------|-------------------------------------------------------------------------------|
|     <span data-ttu-id="c3aa9-171">Insert</span><span class="sxs-lookup"><span data-stu-id="c3aa9-171">Insert</span></span>      |     <span data-ttu-id="c3aa9-172">[VERSION] / [SCHEMA] /Table/ [TABLE_NAME] / 插入</span><span class="sxs-lookup"><span data-stu-id="c3aa9-172">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Insert</span></span>      |     http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert      |
| <span data-ttu-id="c3aa9-173">将响应插入</span><span class="sxs-lookup"><span data-stu-id="c3aa9-173">Insert Response</span></span> | <span data-ttu-id="c3aa9-174">[VERSION] / [SCHEMA] /Table/ [TABLE_NAME] / 插入/响应</span><span class="sxs-lookup"><span data-stu-id="c3aa9-174">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Insert/response</span></span> | http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert/response |
|     <span data-ttu-id="c3aa9-175">选择</span><span class="sxs-lookup"><span data-stu-id="c3aa9-175">Select</span></span>      |     <span data-ttu-id="c3aa9-176">[VERSION] / [SCHEMA] /Table/ [TABLE_NAME] / 选择</span><span class="sxs-lookup"><span data-stu-id="c3aa9-176">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Select</span></span>      |     http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Select      |
| <span data-ttu-id="c3aa9-177">选择响应</span><span class="sxs-lookup"><span data-stu-id="c3aa9-177">Select Response</span></span> | <span data-ttu-id="c3aa9-178">[VERSION] / [SCHEMA] /Table/ [TABLE_NAME] / 选择/响应</span><span class="sxs-lookup"><span data-stu-id="c3aa9-178">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Select/response</span></span> | http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Select/response |
|     <span data-ttu-id="c3aa9-179">Update</span><span class="sxs-lookup"><span data-stu-id="c3aa9-179">Update</span></span>      |     <span data-ttu-id="c3aa9-180">[VERSION] / [SCHEMA] /Table/ [TABLE_NAME] / 更新</span><span class="sxs-lookup"><span data-stu-id="c3aa9-180">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Update</span></span>      |     http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update      |
| <span data-ttu-id="c3aa9-181">更新响应</span><span class="sxs-lookup"><span data-stu-id="c3aa9-181">Update Response</span></span> | <span data-ttu-id="c3aa9-182">[VERSION] / [SCHEMA] /Table/ [TABLE_NAME] / 更新/响应</span><span class="sxs-lookup"><span data-stu-id="c3aa9-182">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Update/response</span></span> | http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update/response |
|     <span data-ttu-id="c3aa9-183">DELETE</span><span class="sxs-lookup"><span data-stu-id="c3aa9-183">Delete</span></span>      |     <span data-ttu-id="c3aa9-184">[VERSION] / [SCHEMA] /Table/ [TABLE_NAME] / 删除</span><span class="sxs-lookup"><span data-stu-id="c3aa9-184">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Delete</span></span>      |     http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete      |
| <span data-ttu-id="c3aa9-185">删除响应</span><span class="sxs-lookup"><span data-stu-id="c3aa9-185">Delete Response</span></span> | <span data-ttu-id="c3aa9-186">[VERSION] / [SCHEMA] /Table/ [TABLE_NAME] / Delete/响应</span><span class="sxs-lookup"><span data-stu-id="c3aa9-186">[VERSION]/[SCHEMA]/Table/[TABLE_NAME]/Delete/response</span></span> | http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete/response |

 <span data-ttu-id="c3aa9-187">[VERSION] = 消息版本字符串;例如， http://Microsoft.LobServices.OracleDB/2007/03。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-187">[VERSION] = The message version string; for example, http://Microsoft.LobServices.OracleDB/2007/03.</span></span>  

 <span data-ttu-id="c3aa9-188">[架构] = Oracle 集合项目;例如，SCOTT。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-188">[SCHEMA] = Collection of Oracle artifacts; for example, SCOTT.</span></span>  

 <span data-ttu-id="c3aa9-189">[TABLE_NAME] = 名称表;例如，EMP。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-189">[TABLE_NAME] = Name of the table; for example, EMP.</span></span>  

> [!IMPORTANT]
>  <span data-ttu-id="c3aa9-190">在视图上的操作的消息操作是相同的表的不同之处在于"视图"替换"表";例如， `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/``View``/EMPVIEW/Insert`。</span><span class="sxs-lookup"><span data-stu-id="c3aa9-190">The message action for an operation on a view is the same as that for a table except that "View" replaces "Table"; for example, `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/``View``/EMPVIEW/Insert`.</span></span>  

## <a name="see-also"></a><span data-ttu-id="c3aa9-191">请参阅</span><span class="sxs-lookup"><span data-stu-id="c3aa9-191">See Also</span></span>  
 [<span data-ttu-id="c3aa9-192">Oracle 数据库的 BizTalk 适配器的消息和消息架构</span><span class="sxs-lookup"><span data-stu-id="c3aa9-192">Messages and Message Schemas for BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)