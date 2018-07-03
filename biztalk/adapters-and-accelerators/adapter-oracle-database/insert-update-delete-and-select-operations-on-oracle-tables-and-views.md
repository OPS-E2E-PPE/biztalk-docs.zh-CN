---
title: Insert、 Update、 Delete 和 Oracle 表和视图的 Select 操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b8ea0ed25119e43565a29c6d7c94a2e81a6ca6e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989966"
---
# <a name="insert-update-delete-and-select-operations-on-oracle-tables-and-views"></a>插入、 更新、 删除和选择 Oracle 表和视图的操作
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]显示一组的每个 Oracle 数据库表和视图上的标准操作。 通过使用这些操作，可以执行简单的 SQL INSERT、 UPDATE、 SELECT 和删除语句限定由 WHERE 子句对目标表 （或视图）。 这些操作也称为数据操作语言 (DML) 操作。 若要执行更复杂的操作，例如 SQL SELECT 查询使用联接运算符，可以使用 SQLEXECUTE 操作。 SQLEXECUTE 操作的详细信息，请参阅[SQLEXECUTE 操作 Oracle 数据库中](../../adapters-and-accelerators/adapter-oracle-database/sqlexecute-operation-in-oracle-database.md)。  
  
 下表显示的 DML 操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]支持：  
  
|运算|Description|  
|---------------|-----------------|  
|Insert|执行插入操作的目标表或视图上。 插入操作支持多个记录或大容量插入到目标表或视图：<br /><br /> -多个记录的插入操作将行插入到表或视图基于提供的记录集。<br /><br /> -如果在大容量插入操作将行插入到表或视图的基础提供 SQL SELECT 查询和列列表。 该查询将返回的记录插入到目标表基于列的列表。<br /><br /> 插入操作的返回值是插入的行数。<br /><br /> **注意：** 这两个多个记录插入和大容量插入不能组合在同一消息中。<br /><br /> **InlineValue**<br /><br /> 对于多个记录的插入操作中的所有简单的数据记录，你可以选择通过指定一个名为可选属性的值来覆盖记录的值**InlineValue**。 InlineValue 属性可用来将计算的值插入到表或视图，例如填充到日期列的主键列使用一个序列，或将其插入 （使用 SYSDATE） 的系统日期。 例如，在下面的 INSERT 语句：<br /><br /> `<Insert xmlns="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/ACCOUNTACTIVITY">   <RECORDSET>     <ACCOUNTACTIVITYRECORDINSERT>       <ACCOUNT>10001</ACCOUNT>       <EMPNAME>John</EMPNAME>       <AMOUNT>1500</AMOUNT>       <TRANSDATE InlineValue="SYSDATE">2008-06-21T15:52:19</TRANSDATE>       </ACCOUNTACTIVITYRECORDINSERT >   </RECORDSET> </Insert>`<br /><br /> 即使"2008年-06-21T15:52:19"是指定为交易记录日期列，InlineValue 属性 （"SYSDATE，"） 的值的值 （系统日期） 将插入到目标表。<br /><br /> 同时使用 InlineValue 属性：<br /><br /> -避免 InlineValue 属性使用的常量值。 例如，在 INSERT 语句中，如果指定`<EMPNAME InlineValue="John"/>`则它将导致错误。 这是因为 InlineValue 属性的值以的方式传递的是到 Oracle，并且在此情况下*John*传递到 Oracle 数据库，这不是预期值 (预期值是*John*)。 您将必须使用单引号雇员姓名。 例如： `<EMPNAME InlineValue="’John’"/>`。<br /><br /> -如果你想要使用的 select 查询 InlineValue 属性，必须将 SELECT 语句括在括号中，并还确保在 select 查询提取单个记录。 例如： `<EMPNAME InlineValue="(SELECT NAME FROM MS_SAMPLE_EMPLOYEES WHERE ID=123)"/>`。<br /><br /> **注意：** 元素标记为 NOT NULL 的 Oracle 数据库中，您必须指定该元素的值，即使您指定的内联值。 无法执行此操作将导致架构验证失败。|  
|选择|对目标表或基于提供的列名称和一个筛选器字符串，指定 SQL WHERE 子句列表视图中执行 SQL SELECT 查询。<br /><br /> 选择操作的返回值是强类型化结果集包含指定的列和行。|  
|Update|执行更新操作上的目标表或视图。 由一个筛选器字符串，指定 SQL WHERE 子句指定要更新的记录。 模板记录中指定的更新的值。<br /><br /> 对于更新操作的返回值是更新的行数。|  
|DELETE|执行对目标表或视图基于筛选器字符串中指定的 SQL WHERE 子句删除操作。<br /><br /> 删除操作的返回值是删除的行数。|  
  
 有关详细信息：  
  
- 执行这些操作使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，请参阅[Insert、 Update、 Delete 和选择操作，它可以使用 BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/insert-update-delete-select-operations-using-biztalk-server-with-oracle-db.md)。  
  
- 在执行这些操作使用 WCF 服务模型，请参阅[Insert、 Update、 Delete 和通过使用 WCF 服务模型选择操作](../../adapters-and-accelerators/adapter-oracle-database/insert-update-delete-select-operations-in-oracle-db-using-a-wcf-service.md)。  
  
- 在执行这些操作使用 WCF 通道模型，请参阅[使用 WCF 通道模型的 Oracle 数据库中运行插入操作](../../adapters-and-accelerators/adapter-oracle-database/run-an-insert-operation-in-oracle-database-using-the-wcf-channel-model.md)。  
  
- 消息结构和 SOAP 操作用于在执行 DML 操作，请参见[基本插入、 更新、 删除和选择表和视图操作的消息架构](../../adapters-and-accelerators/adapter-oracle-database/message-schemas-for-insert-update-delete-and-select-on-tables-and-views.md)。  
  
## <a name="see-also"></a>请参阅  
 [哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)