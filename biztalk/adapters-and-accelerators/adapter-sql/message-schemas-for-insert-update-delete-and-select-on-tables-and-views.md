---
title: 为 Insert、 Update、 Delete 消息架构，然后选择表和视图上的操作 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4fff9cd3-26c0-4d5c-8162-3fd7966a5020
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 73270b3d096a8d72de5b339835737cc74d264c9c
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2018
ms.locfileid: "25967211"
---
# <a name="message-schemas-for-insert-update-delete-and-select-operations-on-tables-and-views"></a>消息架构为插入、 更新、 删除和选择表和视图上的操作
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]呈现插入、 更新、 删除和每个表和 SQL Server 数据库中的视图的 Select 操作。 这些操作执行的适当的 SQL 语句，由 WHERE 子句限定。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]这些操作中使用强类型的记录和记录集。  
  
## <a name="message-structure-for-table-operations"></a>表操作的消息结构  
 下表显示通过公开的基本的表操作的 XML 消息结构[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]上 SQL Server 数据库表。 操作的目标表中的消息操作指定，也会出现在目标命名空间。  
  
|运算|XML 消息|Description|适配器执行的 SQL|  
|---------------|-----------------|-----------------|---------------------------------|  
|Insert|`<Insert xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <Rows>     <[TABLE_NAME]>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </[TABLE_NAME]>   </Rows> </Insert>`|将强类型数据的提供的记录集插入到目标表。|`INSERT INTO TABLE_NAME (FIELD1_NAME, FIELD2_NAME, …) VALUES (value1, value2, …);`|  
|将响应|`<InsertResponse xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <InsertResult>     <long>[Value]</long>   </InsertResult> </InsertResponse>`|插入响应消息包含长整型数据类型的数组。 如果有，则数组存储插入的行中，标识值。 如果表中没有标识列，返回值为 NULL。|--|  
|选择|选择所有记录：<br /><br /> `<Select xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <Columns>*</COLUMNS>   <Query></Query> </Select>`<br /><br /> 在一组记录中选择特定列：<br /><br /> `<Select xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <Columns>[COLUMN_list]</COLUMNS>   <Query>where [WHERE_clause]</Query> </Select>`<br /><br /> 更新记录作为选择操作的一部分：<br /><br /> `<Select xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <Columns>[COLUMN_list]</Columns>   <Query>where [WHERE_clause];UPDATE [TABLE_NAME] SET [FIELD1_NAME] = [value1] where [WHERE_clause]</Query> </Select>`|SELECT 查询执行使用 WHERE 子句的元素中指定的目标表中。 结果集包含的列名称中指定逗号分隔的列表中的列\<列\>元素。<br /><br /> 它是必需的提供中的值\<列\>元素。 如果所有列都必须在表或视图，检索 * 必须在指定\<列\>元素。 如果特定的列必须检索，必须用逗号分隔的列名称，并将其指定的相同顺序为它们在表或视图定义中。<br /><br /> 它是必需的 SELECT 语句中包括 WHERE 子句。 如果您不想要指定 WHERE 子句，则可以删除\<查询\>元素或留空。<br /><br /> 你可以更新使用选择的操作的记录。 UPDATE 语句放入\<查询\>通过用分号分隔的 WHERE 子句和选择请求 XML 元素。 请注意，UPDATE 语句不会不在 SELECT 语句的结果集上的操作。|选择所有记录：<br /><br /> `SELECT * FROM [TABLE_NAME] WHERE [WHERE_clause];`<br /><br /> 在一组记录中选择特定列：<br /><br /> `SELECT [COLUMN_list] FROM [TABLE_NAME] WHERE [WHERE_clause];`<br /><br /> 更新记录作为选择操作的一部分：<br /><br /> `SELECT [COLUMN_list] FROM [TABLE_NAME] WHERE [WHERE_clause]; UPDATE [TABLE_NAME] SET [FIELD1_NAME] = value1 [WHERE_clause];`|  
|选择响应|`<SelectResponse  xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <SelectResult>     <[TABLE_NAME]>       <[FIELD1_NAME]>[value1]</[FIELD1_NAME]>       <[FIELD2_NAME]>[value2]</[FIELD2_NAME]>       …     </[TABLE_NAME]>   </SelectResult> <SelectResponse>`|由 SELECT 查询生成的强类型化结果集。|--|  
|Update|`<SelectResponse  xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <SelectResult>     <[TABLE_NAME]>       <[FIELD1_NAME]>[value1]</[FIELD1_NAME]>       <[FIELD2_NAME]>[value2]</[FIELD2_NAME]>       …     </[TABLE_NAME]>   </SelectResult> </SelectResponse>`<br /><br /> `<Update xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <Rows>     <RowPair>       <After>         <[FIELD1_NAME]>[value1]</[FIELD1_NAME]>         <[FIELD2_NAME]>[value2]</[FIELD2_NAME]>         …       </After>       <Before>         <[FIELD1_NAME]>[value3]</[FIELD1_NAME]>         <[FIELD2_NAME]>[value4]</[FIELD2_NAME]>         …       </Before>     </RowPair>   </Rows> </Update>`|将记录对的数组作为输入。 每个记录对是两个强类型的记录的集合：<br /><br /> 首先记录 (在`<After>`元素) 对应于需要更新的新值。<br /><br /> 第二个记录 (在`<Before>`) 对应的行的旧值。|`UPDATE [TABLE_NAME] SET [FIELD1_NAME] = value1, [FIELD2_NAME] = value2, … WHERE [FIELD1_NAME] = value3, [FIELD2_NAME] = value4, …;`|  
|更新响应|`<UpdateResponse xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <UpdateResult>[rows updated]</UpdateResult> </UpdateResponse>`|在返回更新的行数**UpdateResult**元素。|--|  
|删除|`<Delete xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <Rows>     <[TABLE_NAME]>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </[TABLE_NAME]>   </Rows> </Delete>`|--|`DELETE FROM [TABLE_NAME] WHERE [FIELD1_NAME] = value1, [FIELD2_NAME] = value2, …;`|  
|删除响应|`<DeleteResponse xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <DeleteResult>[rows deleted]</DeleteResult> </DeleteResponse>`|删除的行数返回在**DeleteResult**元素。|--|  
  
 [VERSION] = 消息版本字符串;例如 http://schemas.microsoft.com/Sql/2008/05 。  
  
 [架构] = SQL Server 集合项目;例如，dbo。  
  
 [TABLE_NAME] = 表; 的名称例如，员工。  
  
 [FIELD1_NAME] = 表字段名称;例如，名称。  
  
 [COLUMN_list] = 以逗号分隔列表的其中一列。例如，名称，保留时间，表示形式。  
  
 [SELECT_query] = 大容量插入的操作; 查询元素中指定的 SQL SELECT 语句例如，"选择 * 从 MyTable"  
  
 [WHERE_clause] = WHERE_clause 用于 SELECT 语句用于执行的操作;例如，ID > 10。  
  
> [!IMPORTANT]
>  视图上的基本的表操作的消息结构位于相同表只不过视图替换该表： `Insert xmlns="[VERSION]/ViewOp/[SCHEMA]/[VIEW_NAME]"`。  
  
## <a name="message-actions-for-basic-table-operations"></a>基本的表操作的消息操作  
 下表显示使用的消息操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]表上的基本的表操作。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用的消息操作中指定的表名称来确定该操作的目标表。  
  
|运算|消息操作|示例|  
|---------------|--------------------|-------------|  
|Insert|TableOp/Insert/[SCHEMA]/[TABLE_NAME]|TableOp/Insert/dbo/Employee|  
|将响应|TableOp/Insert/[SCHEMA]/[TABLE_NAME]/response|TableOp/Insert/dbo/Employee/response|  
|选择|TableOp/Select/[SCHEMA]/[TABLE_NAME]|TableOp/Select/dbo/Employee|  
|选择响应|TableOp/Select/[SCHEMA]/[TABLE_NAME]/response|TableOp/Select/dbo/Employee/response|  
|Update|TableOp/Update/[SCHEMA]/[TABLE_NAME]|TableOp/Update/dbo/Employee|  
|更新响应|TableOp/Update/[SCHEMA]/[TABLE_NAME]/response|TableOp/Update/dbo/Employee/response|  
|删除|TableOp/Delete/[SCHEMA]/[TABLE_NAME]|TableOp/Delete/dbo/Employee|  
|删除响应|TableOp/Delete/[SCHEMA]/[TABLE_NAME]/response|TableOp/Delete/dbo/Employee/response|  
  
 [架构] = SQL Server 集合项目;例如，dbo。  
  
 [TABLE_NAME] = 表; 的名称例如，员工。  
  
> [!IMPORTANT]
>  在视图上的操作的消息操作相同的表只是"ViewOp"替换"TableOp";例如， `ViewOp``/Insert/dbo/Employee_View`。  
  
## <a name="see-also"></a>另请参阅  
 [消息和用于 SQL Server 的 BizTalk Adapter 的消息架构](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)