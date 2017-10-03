---
title: "Insert、 Update、 Delete 和 Oracle 表和视图的 Select 操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- operations, on tables and views
- operations, performing
- data manipulation language
- Delete operation
- Insert operation
- Update operation
- DELETE statement
- DML operation
- Select operation
- INSERT statement
- UPDATE statement
ms.assetid: af65fac4-3c16-40c4-ae7a-9c1757223f99
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04770dd5004d46df93da71b910cc228be1751ae7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="insert-update-delete-and-select-operations-on-oracle-tables-and-views"></a>插入、 更新、 删除和选择 Oracle 表和视图上的操作
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]呈现一组的每个 Oracle 数据库表和视图上的标准操作。 通过使用这些操作，你可以执行简单的 SQL 插入、 更新选择、 和 DELETE 语句限定由 WHERE 子句对目标表 （或视图）。 这些操作也称为数据操作语言 (DML) 操作。 若要执行更复杂的操作，例如 SQL 选择使用的查询联接运算符，可以使用 SQLEXECUTE 操作。 有关 SQLEXECUTE 操作的详细信息，请参阅[Oracle 数据库中的 SQLEXECUTE 操作](../../adapters-and-accelerators/adapter-oracle-database/sqlexecute-operation-in-oracle-database.md)。  
  
 下表显示的 DML 操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]支持：  
  
|运算|Description|  
|---------------|-----------------|  
|Insert|执行对目标表或视图插入操作。 插入操作支持多个记录或大容量插入到目标表或视图：<br /><br /> -A 多个记录插入操作将行插入到表或视图基于提供的记录集。<br /><br /> -A 大容量插入操作将行插入到表或视图基于提供 SQL SELECT 查询和列列表。 查询返回的记录插入到目标表基于列列表。<br /><br /> 插入操作的返回值是插入的行数。<br /><br /> **注意：**这两个多个记录插入和大容量插入不能组合在同一条消息。<br /><br /> **InlineValue**<br /><br /> 对于多个记录的插入操作中的所有简单数据记录，你可以选择通过指定调用一个可选属性的值覆盖记录的值**InlineValue**。 InlineValue 属性可用来将计算的值插入到表或视图，例如填充到日期列的主键列使用序列或将其插入 （使用 SYSDATE） 的系统日期。 例如，在以下的 INSERT 语句：<br /><br /> `<Insert xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY">   <RECORDSET>     <ACCOUNTACTIVITYRECORDINSERT>       <ACCOUNT>10001</ACCOUNT>       <EMPNAME>John</EMPNAME>       <AMOUNT>1500</AMOUNT>       <TRANSDATE InlineValue="SYSDATE">2008-06-21T15:52:19</TRANSDATE>       </ACCOUNTACTIVITYRECORDINSERT >   </RECORDSET> </Insert>`<br /><br /> 即使"2008年-06-21T15:52:19"被指定为交易记录日期列，InlineValue 属性，"SYSDATE，"的值的值 （系统日期） 会插入到目标表。<br /><br /> 在使用 InlineValue 属性：<br /><br /> -请避免使用 InlineValue 属性的常量值。 例如，在 INSERT 语句中，如果你指定`<EMPNAME InlineValue="John"/>`然后它将导致错误。 这是因为 InlineValue 属性的值作为传递根据-于 Oracle，并在此情况下*John*传递到 Oracle 数据库时，这不是预期值 (预期值是*John*)。 你将必须使用在员工名称的前后的单引号。 例如： `<EMPNAME InlineValue="’John’"/>`。<br /><br /> -如果你想要用于该 InlineValue 属性的 select 查询，必须用括号括起来的 SELECT 语句，并还确保 select 查询提取单个记录。 例如： `<EMPNAME InlineValue="(SELECT NAME FROM MS_SAMPLE_EMPLOYEES WHERE ID=123)"/>`。<br /><br /> **注意：**如果元素被标记为 NOT NULL Oracle 数据库中，你必须指定该元素的值，即使你指定的内联值。 如果不这样做将导致架构验证失败。|  
|选择|对目标表或视图基于提供的列名称和一个筛选器字符串，指定的 SQL WHERE 子句列表的方式执行 SQL SELECT 查询。<br /><br /> 选择操作的返回值是一个强类型化结果集包含指定的列和行。|  
|Update|执行对目标表或视图的更新操作。 要更新的记录都由一个筛选器字符串，指定的 SQL WHERE 子句指定。 模板记录中指定的更新的值。<br /><br /> 对于更新操作的返回值是更新的行数。|  
|DELETE|执行 Delete 操作的目标表或基于筛选器字符串中指定的 SQL WHERE 子句的视图。<br /><br /> 删除操作的返回值是删除的行数。|  
  
 有关详细信息：  
  
-   执行这些操作使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[Insert、 Update、 Delete 和通过使用 BizTalk Server 选择操作](../../adapters-and-accelerators/adapter-oracle-database/insert-update-delete-select-operations-using-biztalk-server-with-oracle-db.md)。  
  
-   执行这些操作使用 WCF 服务模型时，请参阅[Insert、 Update、 Delete 和通过使用 WCF 服务模型的选择操作](../../adapters-and-accelerators/adapter-oracle-database/insert-update-delete-select-operations-in-oracle-db-using-a-wcf-service.md)。  
  
-   执行这些操作使用 WCF 通道模型，请参阅[使用 WCF 通道模型的 Oracle 数据库中运行插入操作](../../adapters-and-accelerators/adapter-oracle-database/run-an-insert-operation-in-oracle-database-using-the-wcf-channel-model.md)。  
  
-   消息结构和用于执行 DML 操作的 SOAP 操作，请参阅[基本插入、 更新、 删除和选择表和视图上的操作的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)。  
  
## <a name="see-also"></a>另请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)