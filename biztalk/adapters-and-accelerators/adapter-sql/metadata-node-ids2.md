---
title: "BizTalk 适配器包中的 SQL 适配器的元数据节点 Id |Microsoft 文档"
description: "元数据，搜索、 检索节点类型和用于公开 SQL Server 适配器-BizTalk 适配器包 (BAP) 中的 SQL 组件的 Id"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8601a328-5380-4577-a121-c926e0fd3140
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a6e603643ba1d969534e9954733572dc92acd04a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="node-types-and-ids-for-the-sql-server-adapter"></a>节点类型和 SQL Server 适配器 Id

## <a name="metadata-node-ids"></a>元数据节点 Id
[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]曲面 SQL Server 数据库项目以分层方式。 下表列出的节点类型和 SQL Server 数据库项目的节点 Id，[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]图面。 节点 ID 是在中使用的节点的绝对路径**IMetadataRetrievalContractBrowse**，**搜索**，和**GetMetadata**方法。  
  
|项目显示名称|节点类型|节点 ID|示例|Description|  
|---------------------------|---------------|-------------|-------------|-----------------|  
|--|类别|/|/|[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]根节点。 返回所有第一级节点;这包括 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作节点和对于出站操作，所有架构节点和入站操作轮询操作节点。|  
|ExecuteNonQuery|出站操作|GenericOp/ExecuteNonQuery|GenericOp/ExecuteNonQuery|ExecuteNonQuery 操作节点。 ExecuteNonQuery 操作返回 WSDL。|  
|ExecuteReader|出站操作|GenericOp/ExecuteReader|GenericOp/ExecuteReader|ExecuteReader 操作节点。 返回 ExecuteReader 操作的 WSDL。|  
|ExecuteScalar|出站操作|GenericOp/ExecuteScalar|GenericOp/ExecuteScalar|ExecuteScalar 操作节点。 返回 ExecuteScalar 操作的 WSDL。|  
|轮询|入站的操作|轮询|轮询|轮询操作节点。 轮询操作返回 WSDL。|  
|通知|入站的操作|通知|通知|通知操作节点。 返回通知操作的 WSDL。|  
|过程|类别|过程 /|过程 /|架构过程节点。 返回指定的架构的所有过程。|  
|[DB_PROCEDURE]|出站操作|过程 / [DB_SCHEMA] / [Procedure_Name]|过程/dbo/ADD_EMP_DETAILS|过程节点。 返回指定过程的 WSDL。|  
|表|类别|表 /|表 /|架构表节点。 返回指定的架构的所有表节点。|  
|[DB_TABLE]|类别|-|-|表节点。 返回指定表的所有操作节点 （插入、 选择、 更新、 删除和组）。<br /><br /> 设置操作时，才返回包含任何以下数据类型的列的表： varchar （max）、 nvarchar (max) 或 varbinary （max）。|  
|Insert|出站操作|TableOp/Insert / [DB_SCHEMA] / [DB_TABLE]|TableOp/Insert/dbo/员工|表插入操作节点。 返回指定的表的 Insert 操作的 WSDL。|  
|选择|出站操作|TableOp/选择 / [DB_SCHEMA] / [DB_TABLE]|TableOp/选择/dbo/员工|表选择操作节点。 返回有关指定表选择操作的 WSDL。|  
|Update|出站操作|TableOp/更新 / [DB_SCHEMA] / [DB_TABLE]|TableOp/更新/dbo/员工|表更新操作节点。 返回指定表更新操作的 WSDL。|  
|DELETE|出站操作|TableOp/删除 / [DB_SCHEMA] / [DB_TABLE]|TableOp/删除/dbo/员工|表删除操作节点。 返回指定表的删除操作的 WSDL。|  
|设置 [COLUMN_NAME]|出站操作|TableOp/WriteText / [DB_SCHEMA] / [DB_TABLE] / [COLUMN_NAME]|TableOp/WriteText/dbo/员工/Job_Description|表组操作节点。 返回为表中指定的列设置操作的 WSDL。 (仅显示如果表包含与任意以下数据类型的列: (Max)，nvarchar (max) 或 Varbinary(Max))。|  
|视图|类别|视图 /|视图 /|架构视图节点。 返回指定的架构的所有视图节点。|  
|[DB_VIEW]|类别|-|-|视图节点。 返回有关指定的视图的所有操作节点 （插入、 Select、 更新和 Delete）。|  
|Insert|出站操作|ViewOp/Insert / [DB_SCHEMA] / [DB_VIEW]|ViewOp/Insert/dbo/Employee_View|视图插入操作节点。 返回指定的视图插入操作的 WSDL。|  
|选择|出站操作|ViewOp/选择 / [DB_SCHEMA] / [DB_VIEW]|ViewOp/选择/dbo/Employee_View|视图选择操作节点。 返回指定的视图的选择操作的 WSDL。|  
|Update|出站操作|ViewOp/更新 / [DB_SCHEMA] / [DB_VIEW]|ViewOp/更新/dbo/Employee_View|查看更新操作节点。 返回指定的视图的更新操作的 WSDL。|  
|DELETE|出站操作|ViewOp/删除 / [DB_SCHEMA] / [DB_VIEW]|ViewOp/删除/dbo/Employee_View|查看删除操作节点。 返回指定的视图的删除操作的 WSDL。|  
|标量函数|类别|ScalarFunctions /|ScalarFunctions /|架构标量函数节点。 返回指定的架构的所有标量函数。|  
|[DB_SCLR_FUNCTION]|出站操作|ScalarFunction / [DB_SCHEMA] / [DB_SCLR_FUNCTION]|ScalarFunction/dbo/GET_EMP_ID|标量函数节点。 返回指定的标量函数的 WSDL。|  
|表值的函数|类别|TableFunctions /|TableFunctions /|架构表值的函数节点。 返回指定的架构的所有表值函数。|  
|[DB_TBL_FUNCTION]|出站操作|TableFunction / [DB_SCHEMA] / [DB_TBL_FUNCTION]|TableFunction/dbo/TVF_EMPLOYEE|表值的函数节点。 返回指定的表值函数的 WSDL。|  
  
 [DB_SCHEMA] = SQL Server 集合项目;例如，dbo。  
  
 [DB_TABLE] = SQL Server 表; 的名称例如，员工。  
  
 [DB_VIEW] = SQL Server 视图; 的名称例如，Employee_View。  
  
 [DB_PROCEDURE] = SQL Server 存储过程; 的名称例如，ADD_EMP_DETAILS。  
  
 [DB_SCLR_FUNCTION] = SQL Server 标量函数; 的名称例如，GET_EMP_ID。  
  
 [DB_TBL_FUNCTION] = 一个 SQL Server 表值函数; 的名称例如，TVF_EMPLOYEE。  
  
## <a name="metadata-search-and-node-ids"></a>元数据搜索和节点 Id  
 元数据搜索是一款强大功能[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]作为的一部分的图面其**MetadataRetrievalContract**接口。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使用此功能来支持以下 SQL Server 项目进行搜索。 元数据的搜索作用域仅限于从该处执行搜索操作的节点在紧靠的级别。 例如，若要搜索的标量函数，你必须是下搜索/标量函数 / [架构]。 不支持递归搜索。  
  
|项目|节点 ID|返回的节点类型|Description|  
|--------------|-------------|------------------------|-----------------|  
|/ （即根节点）|/|类别|返回与搜索表达式匹配的所有架构节点。|  
|[DB_PROCEDURE]|/Procedure/ [DB_SCHEMA]|出站操作|返回与搜索表达式匹配的指定架构的过程的所有节点。|  
|[DB_TABLE]|/Table/ [DB_SCHEMA]|类别|返回与搜索表达式匹配的指定架构的表的所有节点。|  
|[DB_VIEW]|/View/ [DB_SCHEMA]|类别|返回与搜索表达式匹配的指定架构的视图的所有节点。|  
|[DB_SCLR_FUNCTION]|/ScalarFunction/ [DB_SCHEMA]|出站操作|返回与搜索表达式匹配的指定架构的标量函数的所有节点。|  
|[DB_TBL_FUNCTION]|/TableFunction/ [DB_SCHEMA]|出站操作|返回与搜索表达式匹配的指定架构的表值函数的所有节点。|  
  
 [DB_SCHEMA] = SQL Server 集合项目;例如，dbo。  
  
 [DB_TABLE] = SQL Server 表; 的名称例如，员工。  
  
 [DB_VIEW] = SQL Server 视图; 的名称例如，Employee_View。  
  
 [DB_PROCEDURE] = SQL Server 过程; 的名称例如，ADD_EMP_DETAILS。  
  
 [DB_SCLR_FUNCTION] = SQL Server 标量函数; 的名称例如，GET_EMP_ID。  
  
 [DB_TBL_FUNCTION] = 一个 SQL Server 表值函数; 的名称例如，TVF_EMPLOYEE。  
  
 你可以指定与用于 SQL Server LIKE 运算符的任何有效表达式兼容的搜索表达式。 例如，若要包含在架构中，对表执行的搜索[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]执行下面的 SQL: `SELECT TABLE_NAME FROM ALL_TABLES WHERE TABLE_NAME LIKE ‘[SEARCH_STR]’`。  
  
 下表列出这两个特殊字符[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]在搜索表达式中支持。  
  
|特殊字符|解释|  
|-----------------------|--------------------|  
|%（百分比）|匹配零个或多个字符。<br /><br /> 例如，"%"匹配"A"、"AB"，"ABC"等。|  
|_（下划线）|匹配恰好有一个字符。<br /><br /> 例如，"A_"匹配"AB"、"AC"、"AD"，依次类推。|  
|[ ]|-进行转义的特殊含义的 _ 和 %。<br />-指定一个范围或一组要显示的字符。<br /><br /> 例如：<br /><br /> -%[%] %匹配包括 %符号的所有名称。<br />-[a f] 匹配具有字符之间和包括 a 和 f 的所有名称。<br />-[abc] 匹配具有字符 a，b 的所有名称和 c。|  
|[^]|指定的区域或组的字符不存在。<br /><br /> 例如：<br /><br /> -[^ a-f] 与不具有字符之间也包括 a 和 f 的所有名称相都匹配。<br />-[^ abc] 匹配的所有名称都不具有字符 a，b 和 c。|  
  
## <a name="metadata-retrieval-and-node-ids"></a>元数据检索和节点 Id  
 下表总结了返回的元数据特征[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
|项目|元数据特征|  
|--------------|------------------------------|  
|表或视图|<ul><li>表名。</li><li>表字段名称。</li><li>表的字段数据类型映射到简单或复杂 WSDL 类型。</li><li>表字段长度映射到方面 maxLength。</li><li>表字段主键约束映射到方面 minOccurs = 1。</li><li>表字段为空的约束映射到方面 isNillable = true。</li><li>表操作<br /><br /> <ul><li>Insert</li><li>SELECT</li><li>UPDATE</li><li>DELETE</li><li>设置\<列名称\></li></ul></li></ul>|  
|过程或函数|的为操作名称将映射过程或函数名称。<br />-过程或函数的参数名称。<br />-过程或函数的参数数据类型映射到 WSDL 类型。<br />-过程或函数的参数方向映射到 WSDL 参数方向。<br />过程参数或函数参数数据类型长度映射到方面 maxLength。<br />-过程或函数的参数顺序映射到元素序列。<br />函数返回数据类型映射到 WSDL 类型。<br />函数返回数据类型长度映射到方面 maxLength。|  
  
 有关格式的元数据的详细信息，[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]公开特定项目和操作上的 SQL Server 数据库，请参阅[消息和消息架构用于 SQL Server 的 BizTalk Adapter](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)。  
  