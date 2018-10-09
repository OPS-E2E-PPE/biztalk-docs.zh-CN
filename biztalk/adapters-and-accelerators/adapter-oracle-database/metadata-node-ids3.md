---
title: BizTalk 适配器包中的 Oracle DB 适配器的元数据节点 Id |Microsoft Docs
description: 元数据，搜索、 检索节点类型和公开 Oracle DB 适配器的 BizTalk 适配器包 (BAP) 中的 Oracle 组件中使用的 Id
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 523c7611-b21f-4598-ac77-ba71075db073
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a131cc8e70311f6f57154b90e98ea1067ec5dc02
ms.sourcegitcommit: 51ce182c5b71d3999a3920dd884bc9ec8334a899
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "36969654"
---
# <a name="node-types-and-ids-for-the-oracle-database-adapter"></a>节点类型和 Oracle 数据库适配器的 Id

## <a name="metadata-node-types-and-ids"></a>元数据节点类型和 Id 
[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]表面 Oracle 数据库项目以分层方式。 下表列出的节点类型和 Oracle 数据库项目的节点 Id 的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]图面。 节点 ID 是在中使用的节点的绝对路径**IMetadataRetrievalContractBrowse**，**搜索**，并**GetMetadata**方法。  


| 项目显示名称 | 节点类型 |                           节点 ID                           |                                        示例                                         |                                                                                                     描述                                                                                                     |
|-----------------------|-----------|-------------------------------------------------------------|----------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|          --           | 类别  |                              /                              |                                           /                                            | [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] 根节点。 返回第一级别的所有节点;这包括 SQLEXECUTE 操作节点、 POLLINGSTMT 操作节点，以及所有架构节点 |
|      SQLEXECUTE       | OPERATION |                    [VERSION] / SQLEXECUTE                     |                http://Microsoft.LobServices.OracleDB/2007/03/SQLEXECUTE                |                                                                        SQLEXECUTE 操作节点。 SQLEXECUTE 操作的返回 WSDL。                                                                        |
|      POLLINGSTMT      | OPERATION |                    [VERSION] / POLLINGSTMT                    |               http://Microsoft.LobServices。 OracleDB/2007年/03/POLLINGSTMT               |                                                                       POLLINGSTMT 操作节点。 返回 WSDL POLLINGSTMT 操作。                                                                       |
|      [DB_SCHEMA]      | 类别  |                    [VERSION] / [DB_SCHEMA]                    |                  http://Microsoft.LobServices.OracleDB/2007/03/SCOTT                   |                                                架构节点。 返回指定的架构的常规类别节点 （表、 视图、 过程、 函数和包）。                                                |
|         表         | 类别  |                 [VERSION] / [DB_SCHEMA] / 表                 |               http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table                |                                                                        架构表节点。 返回指定架构的所有表节点。                                                                        |
|      [DB_TABLE]       | 类别  |           [VERSION] / [DB_SCHEMA] /Table/ [DB_TABLE]            |             http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP              |      表节点。 返回指定表的所有操作节点 （Insert、 Select、 Update、 Delete、 ReadLOB 和 UpdateLOB）。 （ReadLOB 和 UpdateLOB 仅返回包含 LOB 列的表。）      |
|        Insert         | OPERATION |        [VERSION] / [DB_SCHEMA] /Table/ [DB_TABLE] / 插入        |          http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert          |                                                             表的插入操作节点。 返回指定表的 Insert 操作的 WSDL。                                                             |
|        选择         | OPERATION |        [VERSION] / [DB_SCHEMA] /Table/ [DB_TABLE] / 选择        |          http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Select          |                                                             表选择操作节点。 返回指定表选择操作的 WSDL。                                                             |
|        Update         | OPERATION |        [VERSION] / [DB_SCHEMA] /Table/ [DB_TABLE] / 更新        |          http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update          |                                                             表更新操作节点。 返回指定表的更新操作的 WSDL。                                                             |
|        DELETE         | OPERATION |        [VERSION] / [DB_SCHEMA] /Table/ [DB_TABLE] / 删除        |          http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete          |                                                             表删除操作节点。 返回指定表的删除操作的 WSDL。                                                             |
|        ReadLOB        | OPERATION |       [VERSION] / [DB_SCHEMA] /Table/ [DB_TABLE] / ReadLOB        |         http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/ReadLOB          |                                  表 ReadLOB 操作节点。 返回指定表的 ReadLOB 操作的 WSDL。 （仅显示如果表包含 LOB 列。）                                  |
|       UpdateLOB       | OPERATION |      [VERSION] / [DB_SCHEMA] /Table/ [DB_TABLE] / UpdateLOB       |        http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/UpdateLOB         |                                表 UpdateLOB 操作节点。 返回指定表的 UpdateLOB 操作的 WSDL。 （仅显示如果表包含 LOB 列。）                                |
|         “查看”          | 类别  |                 [VERSION] / [DB_SCHEMA] / 视图                  |                http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/View                |                                                                         架构视图节点。 返回指定架构的所有视图节点。                                                                         |
|       [DB_VIEW]       | 类别  |            [VERSION] / [DB_SCHEMA] /View/ [DB_VIEW]             |          http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/View/SALES_VIEW           |       视图节点。 返回指定视图的所有操作节点 （Insert、 Select、 Update、 Delete、 ReadLOB 和 UpdateLOB）。 （ReadLOB 和 UpdateLOB 仅返回包含 LOB 列的视图。）        |
|        Insert         | OPERATION |         [VERSION] / [DB_SCHEMA] /View/ [DB_VIEW] / 插入         |       http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/View/SALES_VIEW/Insert       |                                                              查看插入操作节点。 返回指定的视图的 Insert 操作的 WSDL。                                                              |
|        选择         | OPERATION |         [VERSION] / [DB_SCHEMA] /View/ [DB_VIEW] / 选择         |       http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/View/SALES_VIEW/Select       |                                                              视图选择操作节点。 返回指定的视图的选择操作的 WSDL。                                                              |
|        Update         | OPERATION |         [VERSION] / [DB_SCHEMA] /View/ [DB_VIEW] / 更新         |       http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/View/SALES_VIEW/Update       |                                                              查看更新操作节点。 返回指定的视图的更新操作的 WSDL。                                                              |
|        DELETE         | OPERATION |         [VERSION] / [DB_SCHEMA] /View/ [DB_VIEW] / 删除         |       http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/View/SALES_VIEW/Delete       |                                                              查看删除操作节点。 返回指定的视图的 Delete 操作的 WSDL。                                                              |
|        ReadLOB        | OPERATION |        [VERSION] / [DB_SCHEMA] /View/ [DB_VIEW] / ReadLOB         |      http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/View/SALES_VIEW/ReadLOB       |                                   查看 ReadLOB 操作节点。 返回指定的视图的 ReadLOB 操作的 WSDL。 （仅显示如果视图包含 LOB 列。）                                    |
|       UpdateLOB       | OPERATION |       [VERSION] / [DB_SCHEMA] /View/ [DB_VIEW] / UpdateLOB        |     http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/View/SALES_VIEW/UpdateLOB      |                                  查看更新操作节点。 返回指定表的 UpdateLOB 操作的 WSDL。 （仅显示如果视图包含 LOB 列。）                                   |
|       过程       | 类别  |               [VERSION] / [DB_SCHEMA] / 过程               |             http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Procedure              |                                                                      过程 schema 节点。 返回指定的架构的所有过程。                                                                       |
|    [DB_PROCEDURE]     | OPERATION |       [VERSION] / [DB_SCHEMA] /Procedure/ [DB_PROCEDURE]        |       http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Procedure/SP_GENREPORT       |                                                                            过程节点。 返回指定过程的 WSDL。                                                                            |
|       函数        | 类别  |               [VERSION] / [DB_SCHEMA] / 函数                |              http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Function              |                                                                       函数 schema 节点。 返回指定架构的所有函数。                                                                        |
|     [DB_FUNCTION]     | OPERATION |        [VERSION] / [DB_SCHEMA] /Function/ [DB_FUNCTION]         |       http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Function/FN_GETUSERID        |                                                                             函数节点。 返回指定函数的 WSDL。                                                                             |
|        “包”        | 类别  |                [VERSION] / [DB_SCHEMA] / 包                |              http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package               |                                                                        架构包节点。 返回指定的架构的所有包。                                                                         |
|     [DB_PACKAGE]      | 类别  |         [VERSION] / [DB_SCHEMA] /Package/ [DB_PACKAGE]          |        http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG         |                                                                    包节点。 返回所有过程和函数为指定的包。                                                                    |
|   [PACK_PROCEDURE]    | OPERATION | [VERSION] / [DB_SCHEMA] /Package/ [DB_PACKAGE] / [PACK_PROCEDURE] |  http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/GET_ACCOUNT   |                                                                    包过程节点。 返回指定的包过程的 WSDL。                                                                    |
|    [PACK_FUNCTION]    | OPERATION | [VERSION] / [DB_SCHEMA] /Package/ [DB_PACKAGE] / [PACK_FUNCTION]  | http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Package/ACCOUNT_PKG/CREATE_ACCOUNT |                                                                     包函数节点。 返回指定的包函数的 WSDL。                                                                     |

 [VERSION] =; 在版本字符串例如， http://Microsoft.LobServices.OracleDB/2007/03。  

 [DB_SCHEMA] = Oracle 集合项目;例如，SCOTT。  

 [DB_TABLE] = Oracle 表; 的名称例如，EMP。  

 [DB_VIEW] = Oracle 视图; 的名称例如，SALES_VIEW。  

 [DB_PROCEDURE] = Oracle 过程; 的名称例如，SP_GENREPORT。  

 [DB_FUNCTION] = Oracle 函数; 的名称例如，FN_GETUSERID。  

 [DB_PACKAGE] = Oracle 包; 的名称例如，ACCOUNT_PKG。  

 [PACK_PROCEDURE] = 包过程; 的名称例如，GET_ACCOUNT。  

 [PACK_FUNCTION] = 包函数; 的名称例如，CREATE_ACCOUNT。  

## <a name="metadata-search-and-node-ids"></a>元数据搜索和节点 Id  
 元数据搜索是一项强大功能[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]图面作为的一部分其**MetadataRetrievalContract**接口。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用此功能来支持以下 Oracle 项目上进行搜索。 元数据搜索范围仅限于紧下方的节点执行搜索操作的间隔级别。 例如，若要搜索一个函数，您必须搜索下\\[Schema] \Functions。 不支持递归搜索。  

|项目|节点 ID|返回节点类型|描述|  
|--------------|-------------|------------------------|-----------------|  
|[DB_SCHEMA]|/ （即根节点）|类别|返回与搜索表达式匹配的所有架构节点。|  
|[DB_TABLE]|/ [VERSION] / [DB_SCHEMA] / 表|类别|在指定的架构相匹配的搜索表达式中返回表的所有节点。|  
|[DB_VIEW]|/ [VERSION] / [DB_SCHEMA] / 视图|类别|在指定的架构相匹配的搜索表达式中返回视图的所有节点。|  
|[DB_PROCEDURE]|/ [VERSION] / [DB_SCHEMA] / 过程|OPERATION|在指定的架构相匹配的搜索表达式中返回过程的所有节点。|  
|[DB_FUNCTION]|/ [VERSION] / [DB_SCHEMA] / 函数|OPERATION|在指定的架构相匹配的搜索表达式中返回所有函数节点。|  
|[DB_PACKAGE]|/ [VERSION] / [DB_SCHEMA] / 包|类别|返回在指定的架构相匹配的搜索表达式中的所有包节点 （类别）。|  
|[PACK_PROCEDURE] 和 [PACK_FUNCTION]|/ [VERSION] / [DB_SCHEMA] /Package/ [DB_PACKAGE]|OPERATION|返回指定的包相匹配的搜索表达式中所有的函数和过程节点 （操作）。|  

 [VERSION] =; 在版本字符串例如， http://Microsoft.LobServices/2007/03。  

 [DB_SCHEMA] = Oracle 集合项目;例如，SCOTT。  

 [DB_TABLE] = Oracle 表; 的名称例如，EMP。  

 [DB_VIEW] = Oracle 视图; 的名称例如，SALES_VIEW。  

 [DB_PROCEDURE] = Oracle 过程; 的名称例如，SP_GENREPORT。  

 [DB_FUNCTION] = Oracle 函数; 的名称例如，FN_GETUSERID。  

 [DB_PACKAGE] = Oracle 包; 的名称例如，ACCOUNT_PKG。  

 [PACK_PROCEDURE] = 包过程; 的名称例如，GET_ACCOUNT。  

 [PACK_FUNCTION] = 包函数; 的名称例如，CREATE_ACCOUNT。  

 您可以指定任何有效的表达式，用于 Oracle LIKE 运算符与兼容的搜索表达式。 例如，若要包含在架构中，对表执行的搜索[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]执行以下 SQL: `SELECT TABLE_NAME FROM ALL_TABLES WHERE OWNER = '[OWNER_NAME]' AND TABLE_NAME LIKE ‘[SEARCH_STR]’`。  

 下表列出了这两个特殊字符[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]支持搜索表达式中。  

|特殊字符|解释|  
|-----------------------|--------------------|  
|%（百分比）|匹配零个或多个字符;例如，"%"匹配"A"、"AB"，"ABC"等。|  
|_（下划线）|匹配刚好 1 字符;例如，"A_"匹配"AB"、"AC"、"AD"，依次类推。|  
|\ （转义）|转义的特殊含义的 %和 _;例如，"A\\_B"匹配"A_B"。|  

## <a name="metadata-retrieval-and-node-ids"></a>元数据检索和节点 Id  
 下表总结了返回的元数据特征[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  

|项目|元数据特征|  
|--------------|------------------------------|  
|“表或视图”|<ul><li>表名。</li><li>表字段名称。</li><li>为简单或复杂 WSDL 类型映射表字段数据类型。</li><li>为分面 maxLength 映射表字段长度。</li><li>表字段主键约束映射到 facet minOccurs = 1。</li><li>表字段为 NULL 约束映射到 facet isNillable = true。</li><li>表操作<br /><br /> <ul><li>Insert</li><li>SELECT</li><li>UPDATE</li><li>删除</li><li>READLOB （如果表包含 Oracle LOB 类型字段）</li><li>UPDATELOB （如果表包含 Oracle LOB 类型字段）</li></ul></li></ul>|  
|过程或函数|过程或函数名称映射到操作名称。<br />过程或函数的参数名称。<br />过程或函数的参数数据类型映射到 WSDL 类型中。<br />过程或函数的参数方向映射到 WSDL 参数方向。<br />过程参数或函数参数数据类型长度映射到 facet maxLength。<br />过程或函数的参数顺序映射到元素序列。<br />函数返回的数据类型映射到 WSDL 类型。<br />函数返回数据类型长度映射到 facet maxLength。|  
|包过程或函数。|包名称。<br />-其他过程和函数特征，以上列出。|  

 有关格式的元数据的详细信息，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]公开特定项目和操作对 Oracle 数据库，请参阅[消息和消息架构的 Oracle 数据库的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)。  

## <a name="see-also"></a>请参阅  
[在 Visual Studio 中获取 Oracle DB 操作的元数据](get-metadata-for-oracle-database-operations-in-visual-studio.md)