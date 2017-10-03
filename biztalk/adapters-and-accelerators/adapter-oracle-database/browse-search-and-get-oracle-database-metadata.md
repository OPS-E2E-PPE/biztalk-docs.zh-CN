---
title: "浏览、 搜索和获取 Oracle 数据库元数据 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MetadataExchange
- metadata, searching
- metadata, browsing
- POLLINGSTMT
- metadata, retrieving
- IMetadataRetrievalContract
- SQLEXECUTE
ms.assetid: 828d5a8e-f0a3-47b4-8298-5571cff64b52
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 765663d51fa1bab4f700aa3aff726085e5464716
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="browse-search-and-get-oracle-database-metadata"></a>浏览、 搜索和获取 Oracle 数据库元数据
[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]曲面元数据从 Oracle 数据库，用于描述与使用适配器 Oracle 数据库通信的消息结构。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]为检索元数据支持两个接口。  
  
-   MetadataExchange 由[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]。 WCF 提供了元数据交换终结点的所有 WCF 绑定，它使客户端从 Oracle 数据库中获取元数据。  
  
-   IMetadataRetrievalContract 由[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]，它支持浏览和搜索功能的适配器的元数据。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]曲面 Oracle 数据库项目和相应的适配器客户端可以调用的操作。 适配器还显示可以用于执行对 Oracle 数据库的特定操作的 SQLEXECUTE、 POLLINGSTMT 和通知操作。 本主题中后面讨论了这些操作。  
  
 适配器客户端可以浏览、 搜索和检索元数据，使用 WCF 通道模型，使用 WCF 服务模型时，或在 Visual Studio 中创建 BizTalk 项目。 在使用 WCF 服务模型，你必须使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]生成代理类在 Oracle 数据库上执行操作。 在使用 BizTalk 项目，你必须使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]生成你想要对 Oracle 数据库执行的操作的元数据。 有关浏览、 搜索和检索元数据中使用的详细信息[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，请参阅[为 Visual Studio 中的 Oracle 数据库操作获取元数据](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)。  
  
## <a name="browsing-metadata"></a>浏览元数据  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使适配器客户端可以浏览数据库表、 表视图、 存储的过程、 函数和可用的 Oracle 数据库中的包。 作为元数据浏览操作的一部分，该适配器还显示可以对 Oracle 数据库中，包括被适配器支持某些自定义操作执行的操作。 这些操作仅从可用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]呈现以下操作：  
  
 **出站操作**  
  
 包含基础的 Oracle 数据库中的架构的列表。 展开某个架构节点可查看以下项目：  
  
-   **表**： 架构中的所有表的列表。 选择一个表以查看插入、 选择、 更新和删除操作。  
  
-   **过程**： 架构中公开作为操作的存储过程的列表。  
  
-   **函数**： 公开作为操作架构中的函数的列表。  
  
-   **包**： 架构中的所有包的列表。 选择要查看的过程和函数在包内的作为操作公开包。  
  
-   **视图**： 架构中的所有视图的列表。 选择视图以查看插入、 选择、 更新和删除操作。  
  
 除此之外，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]还公开**SQLEXECUTE**出站操作，从而使适配器客户端能够在 Oracle 数据库中执行任何一般数据操作语言 (DML) 或存储的过程。 当你选择的根节点 （/），SQLEXECUTE 操作才可用。 请注意，SQLEXECUTE 的输出数组的数据读取器 （泛型记录的数组作为输出）。 因此，任何简单 out 参数将不显示使用 SQLEXECUTE 操作。 有关操作的详细信息，请参阅[Oracle 数据库中的 SQLEXECUTE 操作](../../adapters-and-accelerators/adapter-oracle-database/sqlexecute-operation-in-oracle-database.md)。  
  
 **入站的操作**  
  
 包含基础的 Oracle 数据库中的架构的列表。 展开某个架构节点可查看以下项目：  
  
-   **过程**： 架构中公开作为操作进行轮询的存储过程的列表。  
  
-   **函数**： 架构中作为进行轮询的操作公开的函数的列表。  
  
-   **包**： 架构中的包的列表。 选择要查看的打包的过程和函数作为进行轮询的操作公开包。  
  
 除此之外，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]还公开**POLLINGSTMT**和**通知**入站操作。 POLLINGSTMT 操作允许适配器客户端获取入站的数据从 Oracle 数据库基于轮询机制适配器支持的查询。 通知操作使适配器客户端能够注册为在数据库中，通知查询的 SELECT 语句和数据库以对适配器客户端及其在结果集的 SELECT 语句更改时发送通知。 当选择根节点 （/），则在 POLLINGSTMT 和通知操作才可用。 有关操作的详细信息，请参阅[支持基于接收轮询的数据更改消息](../../adapters-and-accelerators/adapter-oracle-database/support-for-receiving-polling-based-data-changed-messages-in-oracle-database.md).md) 和[接收数据库转换器通知使用 Oracle 数据库适配器的注意事项](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md).  
  
 有关元数据的分类方式的详细信息，请参阅[元数据的节点 Id](../../adapters-and-accelerators/adapter-oracle-database/metadata-node-ids3.md)。  
  
## <a name="searching-metadata"></a>搜索元数据  
 与[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，可以使用 LIKE 运算符与兼容的 Oracle 搜索表达式对 Oracle 数据库中执行搜索查询。 例如，适配器客户端可以使用如"EMP %"搜索表达式以获取开头 EMP 的表。 适配器将此转换为以下 SQL 查询：  
  
```  
SELECT TABLE_NAME FROM ALL_TABLES WHERE TABLE_NAME LIKE 'EMP%' AND OWNER = 'SCOTT'  
```  
  
 其中，SCOTT 是架构的 Oracle 数据库项目的集合。  
  
 下表列出了可以用于搜索和其解释的特殊字符[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
|特殊字符|解释|  
|-----------------------|--------------------|  
|_（下划线）|完全匹配一个字符<br /><br /> 例如，A_ 匹配 AB、 AC、 AD。|  
|%（百分比）|匹配零个或多个字符。<br /><br /> 例如，%匹配 A，AB，ABC。|  
|\ （转义）|转义的特殊含义的 %和 _<br /><br /> 例如，A\\_B 匹配 A_B。|  
  
> [!IMPORTANT]
>  元数据的搜索作用域仅限于从该处执行搜索操作的节点在紧靠的级别。 例如，若要搜索的函数，您必须搜索下\\[架构] \Functions。 不支持递归搜索。  
  
## <a name="retrieving-metadata"></a>检索元数据  
 检索元数据时,[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]数据库的子集的对象使用相应的对象和操作参数或可以提取在架构包括所有的元数据。 该适配器显示在 XML 中的元素名称，并且从 Oracle 数据库的实体。 由于下划线是可以包含的仅允许特殊字符，元素名称中的所有其他特殊字符进行编码使用下划线。 例如，`emp$name`被编码为`emp_x0024_name`。  
  
## <a name="see-also"></a>另请参阅  
 [用于 Oracle 数据库的 BizTalk Adapter 的概述](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)   
 [了解 BizTalk 适配器用于 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/understand-the-biztalk-adapter-for-oracle-database.md)   
[获取 Visual Studio 中的 Oracle 数据库操作的元数据](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)