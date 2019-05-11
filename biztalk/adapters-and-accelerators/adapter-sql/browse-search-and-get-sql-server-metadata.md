---
title: 浏览、 搜索和获取 SQL Server 元数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 368dd5ca-456c-4cae-9e85-bcf504c4e7ed
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13d8746a78ffc57fa282abaa8891fda429bb8b86
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370073"
---
# <a name="browse-search-and-get-sql-server-metadata"></a>浏览、 搜索和获取 SQL Server 元数据
元数据的[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]从 SQL Server 数据库的图面介绍与 SQL Server 数据库使用的适配器通信的消息结构。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]支持两个接口用于检索元数据。  
  
- 通过提供 MetadataExchange [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]。 WCF 提供了元数据交换终结点的所有 WCF 绑定，它允许客户端从 SQL Server 数据库中获取元数据。  
  
- 通过提供 IMetadataRetrievalContract [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]，它支持的元数据浏览和搜索功能的适配器。  
  
  [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]表面 SQL Server 数据库项目和相应适配器客户端可以调用的操作。 适配器还显示可用于执行 SQL Server 数据库上的特定操作的操作 （如 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar）。 本主题后面将讨论这些操作。  
  
> [!NOTE]
>  [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]显示当前连接的用户有权访问 SQL Server 数据库中的所有架构中的项目。 这意味着，除了默认架构 (dbo) 中，适配器客户端还可以对项目的操作中执行的 SQL Server 数据库中的其他架构，提供用户凭据用于连接使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]有权访问这些架构中SQL Server 数据库中。 有关 SQL Server 数据库中的架构的信息，请参阅[ http://go.microsoft.com/fwlink/?LinkId=130148 ](http://go.microsoft.com/fwlink/?LinkId=130148)。  
  
 适配器客户端用于浏览、 搜索和检索的元数据：  
  
- 在 Visual Studio 中创建 BizTalk 项目  
  
- 使用 WCF 服务模型  
  
- 使用 WCF 通道模型  
  
  在使用 BizTalk 项目，您必须使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]生成你想要在 SQL Server 数据库上执行的操作的元数据。 使用 WCF 服务模型时，必须使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]生成在 SQL Server 数据库上执行操作的代理类。 有关浏览、 搜索和检索元数据中使用的详细信息[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，请参阅[获取 Visual Studio 中使用 SQL 适配器中的 SQL Server 操作的元数据](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)。  
  
## <a name="browsing-metadata"></a>浏览元数据  
 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使适配器客户端可以浏览数据库表、 视图、 存储的过程和 SQL Server 数据库中可用的函数。 作为元数据浏览操作的一部分，该适配器还显示可以对 SQL Server 数据库，包括适配器支持某些自定义操作执行的操作。 这些操作是可从[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]显示以下操作：  
  
- 对表、 视图、 过程、 标量函数和表值函数的操作。 例如，[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]可能图面 Insert、 Update、 Select、 然后删除 EMPLOYEE 表的操作。  
  
- 在集中\<列名\>使适配器客户端能够以流的形式写入大型数据值的表和视图的操作。 设置操作时，才返回这些表和包含具有以下数据类型的任何列的视图：Varchar （max）、 nvarchar （max） 或 varbinary （max）。 有关详细信息，请参阅[对表和视图包含使用 SQL 适配器的较大的数据类型的操作](../../adapters-and-accelerators/adapter-sql/supported-operations-on-tables-and-views-with-large-data-types-with-sql-adapter.md)。  
  
- ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作使适配器客户端可以在 SQL Server 中执行任意 SQL 语句。 有关这些操作的详细信息，请参阅[支持 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)。  
  
- 若要从 SQL Server 接收的入站的消息轮询和通知操作。 轮询操作有关的信息，请参阅[支持用于入站调用使用轮询](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md); 有关通知操作的相关信息，请参阅[接收查询通知使用 SQL 的注意事项适配器](../../adapters-and-accelerators/adapter-sql/considerations-for-receiving-query-notifications-using-the-sql-adapter.md)。  
  
  有关元数据的分类方式的详细信息，请参阅[元数据节点 Id](../../adapters-and-accelerators/adapter-sql/metadata-node-ids2.md)。  
  
## <a name="searching-metadata"></a>搜索元数据  
 使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，可以使用 LIKE 运算符与兼容的 SQL Server 搜索表达式对 SQL Server 数据库中执行搜索查询。 例如，适配器客户端可以使用如"EMP %"的搜索表达式以获取开头 EMP 的表。 该适配器将此转换为下面的 SQL 查询：  
  
```  
SELECT TABLE_NAME FROM ALL_TABLES WHERE TABLE_NAME LIKE 'EMP%'  
```  
  
 下表列出了可用于搜索和通过其解释的特殊字符[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
|特殊字符|解释|  
|-----------------------|--------------------|  
|_（下划线）|匹配一个字符。<br /><br /> 例如，"A_"匹配"AB"、"AC"、"AD"。|  
|%（百分比）|匹配零个或多个字符。<br /><br /> 例如，"%"匹配"A"，"AB"，"ABC"。|  
|[ ]|-转义的特殊含义的 _ 和 %。<br />-指定一个范围或一组字符必须存在。<br /><br /> 例如：<br /><br /> -%[%] %匹配所有包含 %字符的名称。<br />-[a-f] 匹配所有具有字符之间，其中包含 a 和 f 的名称。<br />-[abc] 匹配所有名称中使用了字符 a、 b 和 c。|  
|[^]|指定的范围或组的字符不会显示。<br /><br /> 例如：<br /><br /> -[^ a-f] 匹配不具有字符之间，其中包含 a 和 f 的所有名称。<br />-[^ abc] 匹配不包含字符 a、 b 的所有名称和 c。|  
  
> [!IMPORTANT]
>  元数据搜索范围仅限于紧下方的节点执行搜索操作的间隔级别。 例如，若要搜索的标量函数，您必须是下搜索/标量函数 / [Schema]。 不支持多级别的搜索。  
  
## <a name="retrieving-metadata"></a>检索元数据  
 在检索元数据，[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]可以提取在架构包括所有的元数据或使用相应的对象和操作参数对象的数据库的子集。 适配器将从 SQL Server 数据库的实体表示为 XML 中的元素名称。 由于下划线是可以包含的唯一允许特殊字符，因此使用下划线进行编码的元素名称中的所有其他特殊字符。 例如，`emp$name`被编码为`emp_x0024_name`。  
  
## <a name="see-also"></a>请参阅  
 [适用于 SQL Server 的 BizTalk 适配器概述](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md)   
 [了解适用于 SQL Server 的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/understand-biztalk-adapter-for-sql-server.md)   
 [获取 Visual Studio 中使用 SQL 适配器中的 SQL Server 操作的元数据](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)