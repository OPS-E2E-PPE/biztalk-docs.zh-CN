---
title: 为 Insert、 Update、 Delete 消息架构，然后选择操作 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5b8de271-67db-4279-8f95-0b4dd92fa3c4
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15bb515eee9a052852952f0ec245f8c954953a9e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218229"
---
# <a name="message-schemas-for-insert-update-delete-and-select-operations"></a>消息架构为插入、 更新、 删除和选择操作
[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]呈现基本 Insert、 Update、 Delete 和用于 Oracle E-business Suite 中的每个接口表和基础数据库中的每个表选择操作。 适配器还显示 Oracle E-business Suite 中的每个接口视图和基础数据库中的每个视图的选择操作。 这些操作执行的适当的 SQL 语句，由 WHERE 子句限定。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]这些操作中使用强类型的记录和记录集。  
  
## <a name="message-structure-for-basic-operations"></a>基本操作的消息结构  
 下表显示由公开的基本操作的 XML 消息结构[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]和基础数据库表和视图上 Oracle E-business Suite 接口表和界面视图。 操作的目标对象中的消息操作指定，也会出现在目标命名空间。  
  
> [!NOTE]
>  在表后，请参阅属性说明。  
  
|运算|XML 消息|Description|适配器执行的 SQL|  
|---------------|-----------------|-----------------|---------------------------------|  
|Insert|`<Insert xmlns="[VERSION]/InterfaceTables/[SCHEMA]/[APP_NAME]/[INTERFACETABLE_NAME]">   <RECORDSET>     <InsertRecord>       <[FIELD1_NAME] InlineValue="value">[value1]</[FIELD1_NAME]>       <[FIELD2_NAME] InlineValue="value">[value2]</[FIELD2_NAME]>       …     </InsertRecord>   </RECORDSET> </Insert>`|值**InlineValue**特性，如果指定，将重写元素的值。|`INSERT INTO TABLE_NAME (FIELD1_NAME, FIELD2_NAME, …) VALUES (value1, value2, …);`|  
|将响应|`<InsertResponse xmlns="[VERSION]/InterfaceTables/[SCHEMA]/[APP_NAME]/[INTERFACETABLE_NAME]">   <InsertResult>[rows inserted]</InsertResult> </InsertResponse>`|在中返回插入的行数**InsertResult**元素。|--|  
|选择|`<Select xmlns="[VERSION]/InterfaceTables/[SCHEMA]/[APP_NAME]/[INTERFACETABLE_NAME]">   <COLUMN_NAMES>[COLUMN_list]</COLUMN_NAMES>   <FILTER>WHERE_clause</FILTER> </Select>`|SELECT 查询执行使用 WHERE 子句筛选器元素中指定的目标表中。 结果集包含的列名称中指定逗号分隔的列表中的列**COLUMN_NAMES**元素。<br /><br /> **重要说明：** 这是适用于接口视图和数据库视图的唯一操作。|`SELECT COLUMN_list FROM TABLE_NAME WHERE WHERE_clause;`|  
|选择响应|`<SelectResponse  xmlns="[VERSION]/InterfaceTables/[SCHEMA]/[APP_NAME]/[INTERFACETABLE_NAME]">   <SelectResult>     <SelectRecord>       <[FIELD1_NAME]>value1</[FIELD1_NAME]>       <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …     </SelectRecord>   </SelectResult> </SelectResponse>`|由 SELECT 查询生成的结果集。|--|  
|Update|`<Update xmlns="[VERSION]/InterfaceTables/[SCHEMA]/[APP_NAME]/[INTERFACETABLE_NAME]">   <RECORDSET>     <[FIELD1_NAME]>value1</[FIELD1_NAME]>     <[FIELD2_NAME]>value2</[FIELD2_NAME]>       …   </RECORDSET>   <FILTER>WHERE_clause</FILTER> </Update>`|行匹配 where 子句中指定**筛选器**元素会更新中指定的值为**记录集**。 仅在指定的列**记录集**元素在每个匹配行中进行更新。|`UPDATE [TABLE_NAME] SET [FIELD1_NAME] = value1, [FIELD2_NAME] = value2, … WHERE WHERE_clause;`|  
|更新响应|`<UpdateResponse xmlns="[VERSION]/InterfaceTables/[SCHEMA]/[APP_NAME]/[INTERFACETABLE_NAME]">   <UpdateResult>[rows inserted]</UpdateResult> </UpdateResponse>`|在返回更新的行数**UpdateResult**元素。|--|  
|DELETE|`<Delete xmlns="[VERSION]/InterfaceTables/[SCHEMA]/[APP_NAME]/[INTERFACETABLE_NAME]">   <FILTER>WHERE_clause</FILTER> </Delete>`|匹配的行指定 WHERE 子句**筛选器**元素被删除。|`DELETE FROM [TABLE_NAME] WHERE WHERE_clause;`|  
|删除响应|`<DeleteResponse xmlns="[VERSION]/InterfaceTables/[SCHEMA]/[APP_NAME]/[INTERFACETABLE_NAME]">   <DeleteResult>[rows deleted]</DeleteResult> </DeleteResponse>`|删除的行数返回在**DeleteResult**元素。|--|  
  
 属性说明：  
  
 [VERSION] = 消息版本字符串;例如， http://schemas.microsoft.com/OracleEBS/2008/05 。  
  
 [架构] = Oracle 集合项目;例如，SCOTT。  
  
 [APP_NAME] = 应用程序短名称。  
  
 [INTERFACETABLE_NAME] = 接口表的名称。  
  
 [FIELD1_NAME] = 表字段名称。  
  
 [COLUMN_list] = 列的逗号分隔列表。  
  
 [WHERE_clause] = WHERE_clause 用于 SELECT 语句用于执行的操作;例如，ID > 10。  
  
> [!IMPORTANT]
>  在界面视图、 数据库表和数据库视图的基本操作的消息结构位于相同接口表，但该操作的命名空间指定接口视图、 数据库表或数据库视图而不是不是接口表。  
  
## <a name="message-actions-for-basic-operations"></a>基本操作的消息操作  
 下表显示的消息操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]用于接口表以及在 Oracle E-business Suite 接口视图和表和基础数据库中的视图的基本操作。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使用接口表、 接口视图、 数据库表或指定的消息操作中的数据库视图来确定操作的目标。  
  
> [!NOTE]
>  在表后，请参阅实体说明。  
  
|运算|消息操作|示例|  
|---------------|--------------------|-------------|  
|Insert|**应用程序**: InterfaceTables/Insert / [SHORT_NAME] / [APP_NAME] / [TABLE_NAME]<br /><br /> **数据库**： 表/Insert / [架构] / [TABLE_NAME]|**应用程序**: InterfaceTables/插入/SQLGL/GL/GL_ALLOC_HISTORY<br /><br /> **数据库**： 表/插入/GL/GL_ALLOC_HISTORY|  
|将响应|**应用程序**: InterfaceTables/Insert / [SHORT_NAME] / [APP_NAME] / [TABLE_NAME] / 响应<br /><br /> **数据库**： 表/Insert / [架构] / [TABLE_NAME] / 响应|**应用程序**: InterfaceTables/插入/SQLGL/GL/GL_ALLOC_HISTORY/响应<br /><br /> **数据库**： 表/插入/GL/GL_ALLOC_HISTORY/响应|  
|选择|**应用程序**: InterfaceTables/选择 / [SHORT_NAME] / [APP_NAME] / [TABLE_NAME]<br /><br /> **数据库**： 表/选择 / [架构] / [TABLE_NAME]|**应用程序**: InterfaceTables/选择/SQLGL/GL/GL_ALLOC_HISTORY<br /><br /> **数据库**： 表/选择/GL/GL_ALLOC_HISTORY|  
|选择响应|**应用程序**: InterfaceTables/选择 / [SHORT_NAME] / [APP_NAME] / [TABLE_NAME] / 响应<br /><br /> **数据库**： 表/选择 / [架构] / [TABLE_NAME] / 响应|**应用程序**: InterfaceTables/选择/SQLGL/GL/GL_ALLOC_HISTORY/响应<br /><br /> **数据库**： 表/选择/GL/GL_ALLOC_HISTORY/响应|  
|Update|**应用程序**: InterfaceTables/更新 / [SHORT_NAME] / [APP_NAME] / [TABLE_NAME]<br /><br /> **数据库**： 表/更新 / [架构] / [TABLE_NAME]|**应用程序**: InterfaceTables/更新/SQLGL/GL/GL_ALLOC_HISTORY<br /><br /> **数据库**： 表/更新/GL/GL_ALLOC_HISTORY|  
|更新响应|**应用程序**: InterfaceTables/更新 / [SHORT_NAME] / [APP_NAME] / [TABLE_NAME] / 响应<br /><br /> **数据库**： 表/更新 / [架构] / [TABLE_NAME] / 响应|**应用程序**: InterfaceTables/更新/SQLGL/GL/GL_ALLOC_HISTORY/响应<br /><br /> **数据库**： 表/更新/GL/GL_ALLOC_HISTORY/响应|  
|DELETE|**应用程序**: InterfaceTables/删除 / [SHORT_NAME] / [APP_NAME] / [TABLE_NAME]<br /><br /> **数据库**： 表/删除 / [架构] / [TABLE_NAME]|**应用程序**: InterfaceTables/删除/SQLGL/GL/GL_ALLOC_HISTORY<br /><br /> **数据库**： 表/删除/GL/GL_ALLOC_HISTORY|  
|删除响应|**应用程序**: InterfaceTables/删除 / [SHORT_NAME] / [APP_NAME] / [TABLE_NAME] / 响应<br /><br /> **数据库**： 表/删除 / [架构] / [TABLE_NAME] / 响应|**应用程序**: InterfaceTables/删除/SQLGL/GL/GL_ALLOC_HISTORY/响应<br /><br /> **数据库**： 表/删除/GL/GL_ALLOC_HISTORY/响应|  
  
 实体说明：  
  
-   [架构]-集合的 Oracle 项目 (例如，GL)。  
  
-   [TABLE_NAME]-表 (例如，GL_ALLOC_HISTORY) 的名称。  
  
> [!IMPORTANT]
>  消息在接口视图上执行选择操作的操作是相同接口表中，只不过"InterfaceViews"替换"InterfaceTables。" 同样，对数据库视图的选择操作的消息操作相同的数据库表中，只是"视图"替换"Tables"。  
  
## <a name="see-also"></a>另请参阅  
 [消息和用于 Oracle E-business Suite 的 BizTalk Adapter 的消息架构](../../adapters-and-accelerators/adapter-oracle-ebs/messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)