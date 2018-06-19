---
title: 对于基本 Insert、 Update、 Delete 消息架构，然后选择表和视图上的操作 |Microsoft 文档
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
ms.openlocfilehash: 571a6a192ca85eb0bd3e5abeb8ef8f3715818236
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215997"
---
# <a name="message-schemas-for-the-basic-insert-update-delete-and-select-operations-on-tables-and-views"></a>消息架构的基本的插入、 更新、 删除和选择表和视图上的操作
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]曲面基本插入、 更新，删除，并选择操作为每个表，然后查看 Oracle 数据库中。 这些操作执行的适当的 SQL 语句，由 WHERE 子句限定。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]这些操作中使用强类型的记录和记录集。  
  
## <a name="message-structure-for-basic-table-operations"></a>基本的表操作的消息结构  
 下表显示通过公开的基本的表操作的 XML 消息结构[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]Oracle 数据库表。 操作的目标表中的消息操作指定，也会出现在目标命名空间。  

### <a name="insert"></a>Insert  
有以下类型的插入操作。 一条消息可以包含仅一种类型的插入操作。

- 多个记录插入到目标表中插入强类型化数据提供的记录的集。
- 为在多个记录插入每个记录，你可以为指定值调用一个可选属性**InlineValue**。 如果指定，它将重写元素的值。
- 大容量插入将插入到目标表的查询元素中指定 SELECT 查询返回的记录集。 这可通过使用 COLUMN_NAMES 元素中指定的列的逗号分隔列表。

#### <a name="xml-message"></a>XML 消息  

**多个记录插入**  
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

SQL 适配器执行：`INSERT INTO TABLE_NAME (FIELD1_NAME, FIELD2_NAME, …)VALUES (value1, value2, …);`


**大容量插入**  
```
<Insert xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">
<COLUMN_NAMES>[COLUMN_list]</COLUMN_NAMES>
<QUERY>[SELECT_query]</QUERY>
</Insert>
```

SQL 适配器执行：`INSERT INTO TABLE_NAME (COLUMN_list) SELECT_query;`

### <a name="insert-response"></a>将响应
InsertResult 元素中返回插入的行数。

#### <a name="xml-message"></a>XML 消息  

```
<InsertResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<InsertResult>[rows inserted]</InsertResult> 
</InsertResponse>
```

### <a name="select"></a>选择
SELECT 查询执行使用 WHERE 子句筛选器元素中指定的目标表中。 结果集包含 COLUMN_NAMES 元素中指定的列名称的逗号分隔的列表中的列。

#### <a name="xml-message"></a>XML 消息  
```
<Select xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<COLUMN_NAMES>[COLUMN_list]</COLUMN_NAMES>   
<FILTER>WHERE_clause</FILTER> 
</Select>
```

SQL 适配器执行：`SELECT COLUMN_list FROM TABLE_NAME WHERE WHERE_clause;`

### <a name="select-response"></a>选择响应
由 SELECT 查询生成的结果集。

#### <a name="xml-message"></a>XML 消息  
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

### <a name="update"></a>Update
行匹配 where 子句筛选器元素中指定更新到记录集中指定的值。 仅在记录集中指定的列会更新到每个匹配行。

#### <a name="xml-message"></a>XML 消息  
```
<Update xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<RECORDSET>     
<[FIELD1_NAME]>value1</[FIELD1_NAME]>     
<[FIELD2_NAME]>value2</[FIELD2_NAME]>       
…   
</RECORDSET>   
<FILTER>WHERE_clause</FILTER> </Update>
```

SQL 适配器执行：`UPDATE [TABLE_NAME] SET [FIELD1_NAME] = value1, [FIELD2_NAME] = value2, … WHERE WHERE_clause;`

### <a name="update-response"></a>更新响应
UpdateResult 元素中返回更新的行数。

#### <a name="xml-message"></a>XML 消息  
```
<UpdateResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<UpdateResult>[rows inserted]</UpdateResult> 
</UpdateResponse>
```

### <a name="delete"></a>DELETE
删除行匹配筛选器元素指定 WHERE 子句。

#### <a name="xml-message"></a>XML 消息 
```
<Delete xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<FILTER>WHERE_clause</FILTER> 
</Delete>
```

SQL 适配器执行：`DELETE FROM [TABLE_NAME] WHERE WHERE_clause;`

### <a name="delete-response"></a>删除响应
删除的行数返回 DeleteResult 元素中。

#### <a name="xml-message"></a>XML 消息 
```
<DeleteResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<DeleteResult>[rows inserted]</DeleteResult> 
</DeleteResponse>
```
  
  | 占位符值| Description |
  | --- | --- |
  | [VERSION] | 消息版本字符串;例如，`http://Microsoft.LobServices.OracleDB/2007/03`|
  | [架构] | Oracle 项目; 的集合例如，`SCOTT`|
  | [TABLE_NAME] | 表; 的名称例如，`EMP`|
  | [FIELD1_NAME] | 表字段名称;例如，`EMPNAME`|
  | [COLUMN_list] | 逗号分隔列表的其中一列。例如，`NAME`|
  | [SELECT_query] | 大容量插入的操作; 查询元素中指定 SQL SELECT 语句例如，`SELECT * from MyTable`|
  | [WHERE_clause] | SELECT 语句用于执行的操作; WHERE_clause例如，`ID > 10`|
  
> [!IMPORTANT]
>  视图上的基本的表操作的消息结构是相同的表，但该操作的命名空间指定视图而不是表： `<Insert xmlns ="[VERSION]/[SCHEMA]/``View``/[VIEW_NAME]">`。  
  
## <a name="message-actions-for-basic-table-operations"></a>基本的表操作的消息操作  
 下表显示使用的消息操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]表上的基本的表操作。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用的消息操作中指定的表名称来确定该操作的目标表。  
  
|运算|消息操作|示例|  
|---------------|--------------------|-------------|  
|Insert|[VERSION] / [架构] /Table/ [TABLE_NAME] / 插入|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert|  
|将响应|[VERSION] / [架构] /Table/ [TABLE_NAME] / 插入/响应|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert/response|  
|选择|[VERSION] / [架构] /Table/ [TABLE_NAME] / 选择|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Select|  
|选择响应|[VERSION] / [架构] /Table/ [TABLE_NAME] / 选择/响应|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Select/response|  
|Update|[VERSION] / [架构] /Table/ [TABLE_NAME] / 更新|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update|  
|更新响应|[VERSION] / [架构] /Table/ [TABLE_NAME] / 更新/响应|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update/response|  
|DELETE|[VERSION] / [架构] /Table/ [TABLE_NAME] / 删除|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete|  
|删除响应|[VERSION] / [架构] /Table/ [TABLE_NAME] / 删除/响应|http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete/response|  
  
 [VERSION] = 消息版本字符串;例如，http://Microsoft.LobServices.OracleDB/2007/03。  
  
 [架构] = Oracle 集合项目;例如，SCOTT。  
  
 [TABLE_NAME] = 表; 的名称例如，EMP。  
  
> [!IMPORTANT]
>  在视图上的操作的消息操作相同的表只是"视图"替换"Table";例如， `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/``View``/EMPVIEW/Insert`。  
  
## <a name="see-also"></a>另请参阅  
 [消息和用于 Oracle 数据库的 BizTalk Adapter 的消息架构](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)