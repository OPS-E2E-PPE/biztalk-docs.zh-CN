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
# <a name="message-schemas-for-the-basic-insert-update-delete-and-select-operations-on-tables-and-views"></a>消息架构进行基本插入、 更新、 删除和选择表和视图的操作
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]图面基本 Insert、 Update、 Delete 和 Select 操作为每个表并查看 Oracle 数据库中。 这些操作执行适当的 SQL 语句的 WHERE 子句的限定。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]这些操作中使用强类型的记录和记录集。  

## <a name="message-structure-for-basic-table-operations"></a>基本的表操作的消息结构  
 下表显示了通过公开的基本表操作的 XML 消息结构[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]对 Oracle 数据库表。 操作的目标表中的消息操作指定和也会出现在目标命名空间。  

### <a name="insert"></a>Insert  
有以下类型的插入操作。 消息可以包含仅一种类型的插入操作。

- 多个记录插入到目标表中插入强类型化数据提供的记录的集。
- 对于在多个记录插入每个记录，可以指定一个名为可选属性的值**InlineValue**。 如果指定，它将替代该元素的值。
- 大容量插入将插入到目标表的查询元素中指定的 SELECT 查询返回的记录集。 这是通过使用 COLUMN_NAMES 元素中指定的列以逗号分隔的列表。

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

SQL 适配器执行： `INSERT INTO TABLE_NAME (FIELD1_NAME, FIELD2_NAME, …)VALUES (value1, value2, …);`


**大容量插入**  
```
<Insert xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">
<COLUMN_NAMES>[COLUMN_list]</COLUMN_NAMES>
<QUERY>[SELECT_query]</QUERY>
</Insert>
```

SQL 适配器执行： `INSERT INTO TABLE_NAME (COLUMN_list) SELECT_query;`

### <a name="insert-response"></a>将响应插入
InsertResult 元素中返回插入的行数。

#### <a name="xml-message"></a>XML 消息  

```
<InsertResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<InsertResult>[rows inserted]</InsertResult> 
</InsertResponse>
```

### <a name="select"></a>选择
使用 WHERE 子句筛选器元素中指定的目标表执行 SELECT 查询。 结果集包含 COLUMN_NAMES 元素中指定的列名称的逗号分隔的列表中的列。

#### <a name="xml-message"></a>XML 消息  
```
<Select xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<COLUMN_NAMES>[COLUMN_list]</COLUMN_NAMES>   
<FILTER>WHERE_clause</FILTER> 
</Select>
```

SQL 适配器执行： `SELECT COLUMN_list FROM TABLE_NAME WHERE WHERE_clause;`

### <a name="select-response"></a>选择响应
SELECT 查询生成的结果集。

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
位置匹配的行筛选器元素中指定的子句更新到记录集中指定的值。 指定在记录集中的列中每个匹配行更新。

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

SQL 适配器执行： `UPDATE [TABLE_NAME] SET [FIELD1_NAME] = value1, [FIELD2_NAME] = value2, … WHERE WHERE_clause;`

### <a name="update-response"></a>更新响应
UpdateResult 元素中返回更新的行数。

#### <a name="xml-message"></a>XML 消息  
```
<UpdateResponse xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<UpdateResult>[rows inserted]</UpdateResult> 
</UpdateResponse>
```

### <a name="delete"></a>DELETE
删除行匹配的 WHERE 子句中指定的筛选器元素。

#### <a name="xml-message"></a>XML 消息 
```
<Delete xmlns="[VERSION]/[SCHEMA]/Table/[TABLE_NAME]">   
<FILTER>WHERE_clause</FILTER> 
</Delete>
```

SQL 适配器执行： `DELETE FROM [TABLE_NAME] WHERE WHERE_clause;`

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
  | [版本] | 消息版本字符串;例如， `http://Microsoft.LobServices.OracleDB/2007/03`|
  | [架构] | Oracle 项目; 的集合例如， `SCOTT`|
  | [TABLE_NAME] | 名称的表;例如， `EMP`|
  | [FIELD1_NAME] | 表字段名称;例如， `EMPNAME`|
  | [COLUMN_list] | 以逗号分隔的列;例如， `NAME`|
  | [SELECT_query] | Bulk Insert 操作; 在查询元素中指定一个 SQL SELECT 语句例如， `SELECT * from MyTable`|
  | [WHERE_clause] | SELECT 语句用于执行的操作; WHERE_clause例如， `ID > 10`|

> [!IMPORTANT]
>  在视图上的基本表操作的消息结构不相同的表，但该操作的命名空间指定一个视图，而不是一个表： `<Insert xmlns ="[VERSION]/[SCHEMA]/``View``/[VIEW_NAME]">`。  

## <a name="message-actions-for-basic-table-operations"></a>基本的表操作的消息操作  
 下表显示了使用的消息操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]对表的基本表操作。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用的消息操作中指定的表名称来确定该操作的目标表。  


|    运算    |                    消息操作                     |                                    示例                                    |
|-----------------|-------------------------------------------------------|-------------------------------------------------------------------------------|
|     Insert      |     [VERSION] / [SCHEMA] /Table/ [TABLE_NAME] / 插入      |     http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert      |
| 将响应插入 | [VERSION] / [SCHEMA] /Table/ [TABLE_NAME] / 插入/响应 | http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert/response |
|     选择      |     [VERSION] / [SCHEMA] /Table/ [TABLE_NAME] / 选择      |     http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Select      |
| 选择响应 | [VERSION] / [SCHEMA] /Table/ [TABLE_NAME] / 选择/响应 | http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Select/response |
|     Update      |     [VERSION] / [SCHEMA] /Table/ [TABLE_NAME] / 更新      |     http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update      |
| 更新响应 | [VERSION] / [SCHEMA] /Table/ [TABLE_NAME] / 更新/响应 | http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update/response |
|     DELETE      |     [VERSION] / [SCHEMA] /Table/ [TABLE_NAME] / 删除      |     http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete      |
| 删除响应 | [VERSION] / [SCHEMA] /Table/ [TABLE_NAME] / Delete/响应 | http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete/response |

 [VERSION] = 消息版本字符串;例如， http://Microsoft.LobServices.OracleDB/2007/03。  

 [架构] = Oracle 集合项目;例如，SCOTT。  

 [TABLE_NAME] = 名称表;例如，EMP。  

> [!IMPORTANT]
>  在视图上的操作的消息操作是相同的表的不同之处在于"视图"替换"表";例如， `http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/``View``/EMPVIEW/Insert`。  

## <a name="see-also"></a>请参阅  
 [Oracle 数据库的 BizTalk 适配器的消息和消息架构](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)