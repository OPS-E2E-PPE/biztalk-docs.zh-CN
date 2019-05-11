---
title: 消息架构的 Insert、 Update、 Delete，然后选择表和视图操作 |Microsoft Docs
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
ms.openlocfilehash: ebff9c7996b853a41b11b5e2c082f66224ec04d3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368449"
---
# <a name="message-schemas-for-insert-update-delete-and-select-operations-on-tables-and-views"></a>消息架构进行插入、 更新、 删除和选择表和视图的操作
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] Insert、 Update、 Delete 和 Select 操作为每个表和 SQL Server 数据库中的视图的图面。 这些操作执行的适当的 SQL 语句，由 WHERE 子句限定。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]这些操作中使用强类型的记录和记录集。  
  
## <a name="message-structure-for-table-operations"></a>表操作的消息结构  
 下表显示了通过公开的基本表操作的 XML 消息结构[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]对 SQL Server 上的数据库表。 操作的目标表中的消息操作指定和也会出现在目标命名空间。  
  
|操作|XML 消息|Description|适配器执行的 SQL|  
|---------------|-----------------|-----------------|---------------------------------|  
|Insert|`<Insert xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <Rows>     <[TABLE_NAME]>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </[TABLE_NAME]>   </Rows> </Insert>`|将提供的记录集的强类型化数据插入到目标表。|`INSERT INTO TABLE_NAME (FIELD1_NAME, FIELD2_NAME, …) VALUES (value1, value2, …);`|  
|将响应|`<InsertResponse xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <InsertResult>     <long>[Value]</long>   </InsertResult> </InsertResponse>`|插入的响应消息包含长整型数据类型的数组。 如果有，该数组存储插入的行的标识值。 如果在表中没有标识列，返回值为 NULL。|--|  
|选择|选择所有记录：<br /><br /> `<Select xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <Columns>*</COLUMNS>   <Query></Query> </Select>`<br /><br /> 选择特定列中的一组记录：<br /><br /> `<Select xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <Columns>[COLUMN_list]</COLUMNS>   <Query>where [WHERE_clause]</Query> </Select>`<br /><br /> 选择操作过程中更新记录：<br /><br /> `<Select xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <Columns>[COLUMN_list]</Columns>   <Query>where [WHERE_clause];UPDATE [TABLE_NAME] SET [FIELD1_NAME] = [value1] where [WHERE_clause]</Query> </Select>`|使用 WHERE 子句在元素中指定的目标表执行 SELECT 查询。 结果集包含的列名称中指定的以逗号分隔的列表中的列\<列\>元素。<br /><br /> 中提供值，必须\<列\>元素。 如果要在表或视图中检索所有列都有 * 中，必须指定\<列\>元素。 如果要检索特定列，必须由逗号分隔，列名称，并将其指定的相同顺序为它们在表或视图定义中。<br /><br /> 它是必须在 SELECT 语句中包括 WHERE 子句。 如果您不想要指定 WHERE 子句，则可以删除\<查询\>元素或将其留空。<br /><br /> 可以更新使用选择操作的记录。 UPDATE 语句置于\<查询\>以分号分隔的 WHERE 子句中选择请求 XML 元素。 请注意，UPDATE 语句的作用不在 SELECT 语句的结果集的操作。|选择所有记录：<br /><br /> `SELECT * FROM [TABLE_NAME] WHERE [WHERE_clause];`<br /><br /> 选择特定列中的一组记录：<br /><br /> `SELECT [COLUMN_list] FROM [TABLE_NAME] WHERE [WHERE_clause];`<br /><br /> 选择操作过程中更新记录：<br /><br /> `SELECT [COLUMN_list] FROM [TABLE_NAME] WHERE [WHERE_clause]; UPDATE [TABLE_NAME] SET [FIELD1_NAME] = value1 [WHERE_clause];`|  
|选择响应|`<SelectResponse  xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <SelectResult>     <[TABLE_NAME]>       <[FIELD1_NAME]>[value1]</[FIELD1_NAME]>       <[FIELD2_NAME]>[value2]</[FIELD2_NAME]>       …     </[TABLE_NAME]>   </SelectResult> <SelectResponse>`|SELECT 查询生成的强类型化结果集。|--|  
|Update|`<SelectResponse  xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <SelectResult>     <[TABLE_NAME]>       <[FIELD1_NAME]>[value1]</[FIELD1_NAME]>       <[FIELD2_NAME]>[value2]</[FIELD2_NAME]>       …     </[TABLE_NAME]>   </SelectResult> </SelectResponse>`<br /><br /> `<Update xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <Rows>     <RowPair>       <After>         <[FIELD1_NAME]>[value1]</[FIELD1_NAME]>         <[FIELD2_NAME]>[value2]</[FIELD2_NAME]>         …       </After>       <Before>         <[FIELD1_NAME]>[value3]</[FIELD1_NAME]>         <[FIELD2_NAME]>[value4]</[FIELD2_NAME]>         …       </Before>     </RowPair>   </Rows> </Update>`|将记录对的数组作为输入。 每个记录对是强类型化的两条记录的集合：<br /><br /> 第一条记录 (在`<After>`元素) 对应于需要更新的新值。<br /><br /> 第二个记录 (在`<Before>`) 对应的行的旧值。|`UPDATE [TABLE_NAME] SET [FIELD1_NAME] = value1, [FIELD2_NAME] = value2, … WHERE [FIELD1_NAME] = value3, [FIELD2_NAME] = value4, …;`|  
|更新响应|`<UpdateResponse xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <UpdateResult>[rows updated]</UpdateResult> </UpdateResponse>`|在返回更新的行数**UpdateResult**元素。|--|  
|DELETE|`<Delete xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <Rows>     <[TABLE_NAME]>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </[TABLE_NAME]>   </Rows> </Delete>`|--|`DELETE FROM [TABLE_NAME] WHERE [FIELD1_NAME] = value1, [FIELD2_NAME] = value2, …;`|  
|删除响应|`<DeleteResponse xmlns="[VERSION]/TableOp/[SCHEMA]/[TABLE_NAME]">   <DeleteResult>[rows deleted]</DeleteResult> </DeleteResponse>`|删除的行数返回在**DeleteResult**元素。|--|  
  
 [VERSION] = 消息版本字符串;例如， http://schemas.microsoft.com/Sql/2008/05。  
  
 [架构] = 集合的 SQL Server 项目;例如，dbo。  
  
 [TABLE_NAME] = 名称表;例如，员工。  
  
 [FIELD1_NAME] = 表字段名称;例如，名称。  
  
 [COLUMN_list] = 逗号分隔列表的列;例如，名称、 年龄、 名称。  
  
 [SELECT_query] = 大容量插入操作; 在查询元素中指定的 SQL SELECT 语句例如，"选择 * 从 MyTable"  
  
 [WHERE_clause] = WHERE_clause 用于 SELECT 语句用于执行的操作;例如，ID > 10。  
  
> [!IMPORTANT]
>  对视图的基本表操作的消息结构是相同的表不同之处在于该视图替换该表： `Insert xmlns="[VERSION]/ViewOp/[SCHEMA]/[VIEW_NAME]"`。  
  
## <a name="message-actions-for-basic-table-operations"></a>基本的表操作的消息操作  
 下表显示了使用的消息操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]对表的基本表操作。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用的消息操作中指定的表名称来确定该操作的目标表。  
  
|操作|消息操作|示例|  
|---------------|--------------------|-------------|  
|Insert|TableOp/Insert/[SCHEMA]/[TABLE_NAME]|TableOp/Insert/dbo/Employee|  
|将响应|TableOp/Insert/[SCHEMA]/[TABLE_NAME]/response|TableOp/Insert/dbo/Employee/response|  
|选择|TableOp/Select/[SCHEMA]/[TABLE_NAME]|TableOp/Select/dbo/Employee|  
|选择响应|TableOp/Select/[SCHEMA]/[TABLE_NAME]/response|TableOp/Select/dbo/Employee/response|  
|Update|TableOp/Update/[SCHEMA]/[TABLE_NAME]|TableOp/Update/dbo/Employee|  
|更新响应|TableOp/Update/[SCHEMA]/[TABLE_NAME]/response|TableOp/Update/dbo/Employee/response|  
|DELETE|TableOp/Delete/[SCHEMA]/[TABLE_NAME]|TableOp/Delete/dbo/Employee|  
|删除响应|TableOp/Delete/[SCHEMA]/[TABLE_NAME]/response|TableOp/Delete/dbo/Employee/response|  
  
 [架构] = 集合的 SQL Server 项目;例如，dbo。  
  
 [TABLE_NAME] = 名称表;例如，员工。  
  
> [!IMPORTANT]
>  上一个视图的操作的消息操作是相同的表的不同之处在于"ViewOp"替换"TableOp";例如， `ViewOp``/Insert/dbo/Employee_View`。  
  
## <a name="see-also"></a>请参阅  
 [消息和用于 SQL Server 的 BizTalk 适配器的消息架构](../../adapters-and-accelerators/adapter-sql/messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)