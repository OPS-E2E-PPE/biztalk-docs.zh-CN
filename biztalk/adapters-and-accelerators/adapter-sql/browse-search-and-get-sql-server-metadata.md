---
title: "浏览、 搜索和获取 SQL Server 元数据 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 368dd5ca-456c-4cae-9e85-bcf504c4e7ed
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5abb42ff1cae700077c44c391a1112c7309048c6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="browse-search-and-get-sql-server-metadata"></a>浏览、 搜索和获取 SQL Server 元数据
元数据，[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]从 SQL Server 数据库的图面描述用于与 SQL Server 数据库使用适配器进行通信的消息结构。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]为检索元数据支持两个接口。  
  
-   MetadataExchange 由[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]。 WCF 提供了元数据交换终结点的所有 WCF 绑定，这使客户端可以从 SQL Server 数据库中获取元数据。  
  
-   IMetadataRetrievalContract 由[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]，它支持浏览和搜索功能的适配器的元数据。  
  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]曲面 SQL Server 数据库项目和相应的适配器客户端可以调用的操作。 适配器还显示可以用于执行 SQL Server 数据库上的特定操作的操作 （如 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar）。 本主题中后面讨论了这些操作。  
  
> [!NOTE]
>  [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]呈现当前连接的用户有权访问 SQL Server 数据库中的所有架构中的项目。 这意味着，除了默认架构 (dbo) 中，适配器客户端还可以执行对项目的操作中的 SQL Server 数据库中的其他架构，提供用户凭据用于连接使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]有权访问在这些架构SQL Server 数据库中。 有关 SQL Server 数据库中的架构的信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=130148](http://go.microsoft.com/fwlink/?LinkId=130148)。  
  
 适配器客户端用于浏览、 搜索和检索元数据：  
  
-   在 Visual Studio 中创建 BizTalk 项目  
  
-   使用 WCF 服务模型  
  
-   使用 WCF 通道模型  
  
 在使用 BizTalk 项目，你必须使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]生成你想要在 SQL Server 数据库上执行的操作的元数据。 在使用 WCF 服务模型，你必须使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]生成代理类，在 SQL Server 数据库上执行操作。 有关浏览、 搜索和检索元数据中使用的详细信息[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，请参阅[为使用 SQL 适配器的 Visual Studio 中的 SQL Server 操作获取元数据](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)。  
  
## <a name="browsing-metadata"></a>浏览元数据  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使适配器客户端可以浏览数据库表、 视图、 存储的过程和函数中的 SQL Server 数据库可用。 作为元数据浏览操作的一部分，该适配器还显示可以包括适配器支持某些自定义操作的 SQL Server 数据库执行的操作。 这些操作仅从可用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]呈现以下操作：  
  
-   对表、 视图、 过程、 标量函数和表值函数的操作。 例如，[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]可能外围 Insert、 Update、 选择和删除员工表的操作。  
  
-   集\<列名称 > 的表和视图，使适配器客户端要在流式处理方式写入大数据值的操作。 设置操作时，才返回这些表和视图包含与任意以下数据类型的列： varchar （max）、 nvarchar (max) 或 varbinary （max）。 有关详细信息，请参阅[对表和视图包含使用 SQL 适配器的较大的数据类型的操作](../../adapters-and-accelerators/adapter-sql/supported-operations-on-tables-and-views-with-large-data-types-with-sql-adapter.md)。  
  
-   ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作，使适配器客户端在 SQL Server 中执行任意 SQL 语句。 有关这些操作的详细信息，请参阅[支持 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)。  
  
-   要从 SQL Server 接收传入的消息的轮询间隔和通知操作。 轮询操作有关的信息，请参阅[支持为入站调用使用轮询](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md); 有关通知操作的相关信息，请参阅[接收查询通知使用 SQL 的注意事项适配器](../../adapters-and-accelerators/adapter-sql/considerations-for-receiving-query-notifications-using-the-sql-adapter.md)。  
  
 有关元数据的分类方式的详细信息，请参阅[元数据的节点 Id](../../adapters-and-accelerators/adapter-sql/metadata-node-ids2.md)。  
  
## <a name="searching-metadata"></a>搜索元数据  
 与[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，可以使用 LIKE 运算符与兼容的 SQL Server 搜索表达式在 SQL Server 数据库上执行搜索查询。 例如，适配器客户端可以使用如"EMP %"搜索表达式以获取开头 EMP 的表。 适配器将此转换为以下 SQL 查询：  
  
```  
SELECT TABLE_NAME FROM ALL_TABLES WHERE TABLE_NAME LIKE 'EMP%'  
```  
  
 下表列出了可以用于搜索和其解释的特殊字符[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
|特殊字符|解释|  
|-----------------------|--------------------|  
|_（下划线）|完全匹配一个字符。<br /><br /> 例如，"A_"匹配"AB"、"AC"、"AD"。|  
|%（百分比）|匹配零个或多个字符。<br /><br /> 例如，"%"匹配"A"，"AB"，"ABC"。|  
|[ ]|-进行转义的特殊含义的 _ 和 %。<br />-指定一个范围或一组要显示的字符。<br /><br /> 例如：<br /><br /> -%[%] %匹配包括 %符号的所有名称。<br />-[a f] 匹配具有字符之间和包括 a 和 f 的所有名称。<br />-[abc] 匹配具有字符 a，b 的所有名称和 c。|  
|[^]|指定的区域或组的字符不存在。<br /><br /> 例如：<br /><br /> -[^ a-f] 与不具有字符之间也包括 a 和 f 的所有名称相都匹配。<br />-[^ abc] 匹配的所有名称都不具有字符 a，b 和 c。|  
  
> [!IMPORTANT]
>  元数据的搜索作用域仅限于从该处执行搜索操作的节点在紧靠的级别。 例如，若要搜索的标量函数，你必须是下搜索/标量函数 / [架构]。 不支持多级搜索。  
  
## <a name="retrieving-metadata"></a>检索元数据  
 检索元数据时,[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]数据库的子集的对象使用相应的对象和操作参数或可以提取在架构包括所有的元数据。 适配器显示在 XML 中的元素名称，并且从 SQL Server 数据库的实体。 由于下划线是可以包含的仅允许特殊字符，元素名称中的所有其他特殊字符进行编码使用下划线。 例如，`emp$name`被编码为`emp_x0024_name`。  
  
## <a name="see-also"></a>另请参阅  
 [用于 SQL Server 的 BizTalk Adapter 的概述](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md)   
 [理解 SQL Server 的 BizTalk Adapter](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)   
 [使用 SQL 适配器的 Visual Studio 中的 SQL Server 操作中获取元数据](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)