---
title: "插入、 更新、 删除和选择表和视图与 SQL 适配器上的操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d0cc39d5-16f2-454a-8e1d-c031592439ae
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cae4dfff287414c4f9b1081face9a33bbf9da545
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="insert-update-delete-and-select-operations-on-tables-and-views-with-the-sql-adapter"></a>插入、 更新、 删除和选择表和视图与 SQL 适配器上的操作
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]呈现一组的每个表和视图中的 SQL Server 数据库上的标准操作。 通过使用这些操作，你可以执行简单的 INSERT、 UPDATE、 SELECT、 和 DELETE 语句，由对目标表或视图的 WHERE 子句限定。 这些操作也称为数据操作语言 (DML) 操作。  
  
 下表显示的 DML 操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]支持：  
  
|运算|Description|  
|---------------|-----------------|  
|Insert|执行对目标表或视图插入操作。<br /><br /> -插入操作将记录的数组作为输入。 每个记录强类型化为目标表，并映射到表中插入的行。<br />-你可以在提供的值的标识列中插入值**AllowIdentityInsert**绑定属性设置为 TRUE。 有关详细信息**AllowIdentityInsert**绑定属性，请参阅[了解针对 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。<br />的插入操作返回值为 Long 数据类型的数组。 如果有，则此数组存储插入的行中，标识值。 如果表中没有标识列，返回值为 NULL。<br /><br /> 通过以下方式处理插入操作消息中的某些值[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]:<br /><br /> -为计算的列以及时间戳列指定的值将被忽略。<br />-如果标识列的节点为 null，则忽略它。<br /><br /> 对于插入操作消息中的所有其他值：<br /><br /> -如果为列指定的值，该值使用 INSERT 语句中。<br />-如果某个特定列的节点为 null，NULL 则使用 INSERT 语句中。 **注意：**如果对于特定的记录，没有可以在 INSERT 语句中使用的值 （即，没有值指定的任何列或所有列的值被都忽略），适配器执行以下 SQL 语句：`insert into <table_name> default values`|  
|选择|对目标表或视图基于数组中的记录 （列） 和一个查询字符串，指定 WHERE 子句中执行 SELECT 语句。<br /><br /> 的必须为 SELECT 语句中列的列表中指定值。 如果所有列都必须在表或视图，检索 * 必须在 SELECT 语句中指定。 如果特定的列必须检索，必须用逗号分隔的列名称，并将其指定的相同顺序为它们在表或视图定义中。<br />-WHERE 子句必须包含在 SELECT 语句。 但是，如果您不想要在 WHERE 子句中指定一个值，你可以删除`Query`元素或留空。<br />-选择操作还允许你执行更新操作。 在这种情况下，将 UPDATE 语句放置在`Query`的 SELECT 语句的元素。<br /><br /> 选择操作的返回值是一个强类型化结果集包含指定的列和目标表或视图中的行。|  
|Update|执行对目标表或视图的更新操作。<br /><br /> -更新操作将记录对的数组作为输入。 每个记录对两个记录的集合，并且每个记录强类型化为目标表。<br /><br /> -在第一个记录对应于需要更新的新值，即，它对应于 UPDATE 语句的 SET 子句。 <br />的第二个记录对应的行的旧值，即，它对应于 UPDATE 语句的 WHERE 子句。 **注意：**记录配对如果对特定的记录，没有可以在 SET 子句中使用的值，执行任何更新语句。 <br />-您可以更新中提供的值的标识列的值**AllowIdentityInsert**绑定属性设置为 TRUE。 有关详细信息**AllowIdentityInsert**绑定属性，请参阅[了解针对 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。 <br />的更新操作返回值是 Int32 数据类型，表示更新的行数。<br /> 通过以下方式中处理更新操作消息中的某些值[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]:<br /><br /> -为计算的列和消息的 SET 子句中的时间戳列指定的值将被忽略。<br />-如果用户定义类型 (UDT) 不是字节进行排序，UDT 列指定的值在 WHERE 子句是被忽略。<br />-如果标识列的节点为 null 的消息的 SET 子句中，则忽略它。<br />-如果的标识或时间戳列的节点为 null 的消息的 WHERE 子句中，则忽略它。<br />-如果图像、 XML、 Text 或 Ntext 列的节点不在消息的 WHERE 子句中为 null，则忽略为它们指定的值，因为这些值不能进行比较。<br /><br /> 对于更新操作消息中的所有其他值：<br /><br /> -如果为 UPDATE 语句的 SET 子句中的列指定一个值，该语句的 SET 子句中使用的值 (`set <column_name> = <value>`)。<br />-如果某个特定列的节点为 null 的 SET 子句中，更新语句中使用 NULL (`set <column_name> = null`)。<br />-如果指定的值是列中 UPDATE 语句的 WHERE 子句，该语句的 WHERE 子句中使用的值 (`where <column_name> = <value>`)。<br />-如果某个特定列的节点为 null 的 UPDATE 语句的 WHERE 子句中，更新语句中使用 NULL (`where <column_name> is null`)。|  
|DELETE|执行 Delete 操作的目标表或视图基于强类型化数组的目标表和一个筛选器字符串，指定 WHERE 子句的记录 （列表的列名称）。<br /><br /> 删除操作的返回值是 Int32 数据类型，表示删除的行数。<br /><br /> Delete 操作消息中的某些值视为按以下方式通过[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]:<br /><br /> -如果图像、 XML、 Text 或 Ntext 列的节点不在消息的 WHERE 子句中为 null，则忽略为它们指定的值，因为这些值不能进行比较。<br />-如果的标识或时间戳列的节点为 null，则忽略它。<br />-如果 UDT 不是字节进行排序，UDT 列指定的值在 WHERE 子句是被忽略。<br /><br /> Delete 操作消息中的所有其他值：<br /><br /> -如果为列指定的值，DELETE 语句的 WHERE 子句中使用的值 (`where <column_name> = <value>`)。<br />-如果某个特定列的节点为 null，DELETE 语句中使用 NULL (`where <column_name> is null`)。 **注意：**如果对于特定的记录，没有可以在 DELETE 语句 （即，没有值指定的任何列或如果存在的所有列值被都忽略） 中使用的值，该适配器不执行任何 DELETE 语句。|  
  
 有关详细信息：  
  
-   执行这些操作使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[插入、 更新、 删除或 BizTalk 服务器与 SQL 适配器一起使用的 select 操作](../../adapters-and-accelerators/adapter-sql/insert-update-delete-or-select-using-the-sql-adapter-in-biztalk-server.md)。  
  
-   消息结构和用于执行 DML 操作的 SOAP 操作，请参阅[插入、 更新、 删除和选择表和视图上的操作的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)。  
  
## <a name="see-also"></a>另请参阅  
 [连接到 SAP 系统使用适配器](../../adapters-and-accelerators/adapter-sap/connect-to-an-sap-system-using-the-adapter.md)