---
title: 浏览、 搜索和获取 Oracle 数据库元数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4fb9d908e925ebfad42eb50aef28f94ae9f1972
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376789"
---
# <a name="browse-search-and-get-oracle-database-metadata"></a>浏览、 搜索和获取 Oracle 数据库元数据
[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]图面元数据从 Oracle 数据库描述与 Oracle 数据库使用的适配器通信的消息结构。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]支持两个接口用于检索元数据。  
  
- 通过提供 MetadataExchange [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]。 WCF 提供了元数据交换终结点的所有 WCF 绑定，它允许客户端从 Oracle 数据库中获取元数据。  
  
- 通过提供 IMetadataRetrievalContract [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]，它支持的元数据浏览和搜索功能的适配器。  
  
  [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]表面 Oracle 数据库项目和相应适配器客户端可以调用的操作。 适配器还显示可用于执行对 Oracle 数据库的特定操作的 SQLEXECUTE、 POLLINGSTMT 和通知操作。 本主题后面将讨论这些操作。  
  
  适配器客户端可以浏览、 搜索和检索元数据，使用 WCF 通道模型、 使用 WCF 服务模型，或在 Visual Studio 中创建 BizTalk 项目。 使用 WCF 服务模型时，必须使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]生成在 Oracle 数据库上执行操作的代理类。 在使用 BizTalk 项目，您必须使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]生成你想要对 Oracle 数据库执行的操作的元数据。 有关浏览、 搜索和检索元数据中使用的详细信息[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，请参阅[获取 Visual Studio 中的 Oracle 数据库操作的元数据](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)。  
  
## <a name="browsing-metadata"></a>浏览元数据  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使适配器客户端可以浏览数据库表、 表视图、 存储的过程、 函数和 Oracle 数据库中可用的包。 作为元数据浏览操作的一部分，该适配器还显示可以对 Oracle 数据库，包括适配器支持某些自定义操作执行的操作。 这些操作是可从[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]显示以下操作：  
  
 **出站操作**  
  
 包含一系列基础的 Oracle 数据库中的架构。 展开架构节点，请参阅以下项目：  
  
- **表**：在架构中的所有表的列表。 选择一个表以查看插入、 选择、 更新和删除操作。  
  
- **过程**:在架构中作为操作公开的存储过程的列表。  
  
- **函数**:在架构中作为操作公开的函数的列表。  
  
- **包**:在架构中的所有程序包的列表。 选择要查看的过程和函数在包内的公开作为操作的包。  
  
- **视图**:在架构中的所有视图的列表。 选择视图以查看插入、 选择、 更新和删除操作。  
  
  除此之外，这两[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]还公开**SQLEXECUTE**出站操作，这使适配器客户端能够在 Oracle 数据库中执行任何泛型数据操作语言 (DML) 或存储的过程。 当你选择的根节点 （/），SQLEXECUTE 操作才可用。 请注意，SQLEXECUTE 的输出数据读取器 （通用记录的数组作为输出） 的数组。 因此，任何简单的 out 参数不会显示使用 SQLEXECUTE 操作。 有关操作的详细信息，请参阅[SQLEXECUTE 操作 Oracle 数据库中](../../adapters-and-accelerators/adapter-oracle-database/sqlexecute-operation-in-oracle-database.md)。  
  
  **入站的操作**  
  
  包含一系列基础的 Oracle 数据库中的架构。 展开架构节点，请参阅以下项目：  
  
- **过程**:在架构中作为用于轮询的操作公开的存储过程的列表。  
  
- **函数**:在架构中作为用于轮询的操作公开的函数的列表。  
  
- **包**:在架构中的包的列表。 选择要查看的打包的过程和函数公开为操作的轮询的包。  
  
  除此之外，这两[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]还公开**POLLINGSTMT**并**通知**入站操作。 POLLINGSTMT 操作使适配器客户端能够从基于查询轮询机制适配器支持的 Oracle 数据库中获取入站的数据。 通知操作使适配器客户端能够注册为在数据库中，通知查询的 SELECT 语句和数据库将通知发送到适配器客户端和结果集的 SELECT 语句更改。 选择根节点 （/） 时可用的 POLLINGSTMT 和通知操作。 有关操作的详细信息，请参阅[对基于接收轮询的数据更改消息的支持](../../adapters-and-accelerators/adapter-oracle-database/support-for-receiving-polling-based-data-changed-messages-in-oracle-database.md).md) 和[接收数据库更改器通知使用的 Oracle 数据库适配器时的注意事项](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md).  
  
  有关元数据的分类方式的详细信息，请参阅[元数据节点 Id](../../adapters-and-accelerators/adapter-oracle-database/metadata-node-ids3.md)。  
  
## <a name="searching-metadata"></a>搜索元数据  
 使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，可以使用 LIKE 运算符与兼容的 Oracle 搜索表达式对 Oracle 数据库中执行搜索查询。 例如，适配器客户端可以使用如"EMP %"的搜索表达式以获取开头 EMP 的表。 该适配器将此转换为下面的 SQL 查询：  
  
```  
SELECT TABLE_NAME FROM ALL_TABLES WHERE TABLE_NAME LIKE 'EMP%' AND OWNER = 'SCOTT'  
```  
  
 其中，SCOTT，是使用 Oracle 数据库项目的集合的架构。  
  
 下表列出了可用于搜索和通过其解释的特殊字符[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
|特殊字符|解释|  
|-----------------------|--------------------|  
|_（下划线）|只匹配一个字符<br /><br /> 例如，A_ 匹配 AB，交流，AD。|  
|%（百分比）|匹配零个或多个字符。<br /><br /> 例如，%匹配一个，AB，ABC。|  
|\ （转义）|转义的特殊含义的 %和 _<br /><br /> 例如，一个\\_B 匹配 A_B。|  
  
> [!IMPORTANT]
>  元数据搜索范围仅限于紧下方的节点执行搜索操作的间隔级别。 例如，若要搜索一个函数，您必须搜索下\\[Schema] \Functions。 不支持递归搜索。  
  
## <a name="retrieving-metadata"></a>检索元数据  
 在检索元数据，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]可以提取在架构包括所有的元数据或使用相应的对象和操作参数对象的数据库的子集。 该适配器显示为 XML 元素名称从 Oracle 数据库的实体。 由于下划线是可以包含的唯一允许特殊字符，因此使用下划线进行编码的元素名称中的所有其他特殊字符。 例如，`emp$name`被编码为`emp_x0024_name`。  
  
## <a name="see-also"></a>请参阅  
 [用于 Oracle 数据库的 BizTalk 适配器概述](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)   
 [了解用于 Oracle 数据库的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-database/understand-the-biztalk-adapter-for-oracle-database.md)   
[获取 Visual Studio 中的 Oracle 数据库操作的元数据](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)