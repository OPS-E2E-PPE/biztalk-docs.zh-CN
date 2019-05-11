---
title: 浏览、 搜索和获取 Oracle E-business Suite 元数据 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b516c6e9-dbb3-4977-bb27-aa039e021912
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da46c48fe16ae4a6ce121cb770d5a963aff79326
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375739"
---
# <a name="browse-search-and-get-oracle-e-business-suite-metadata"></a>浏览、 搜索和获取 Oracle E-business Suite 元数据
元数据的[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]从 Oracle E-business Suite 和基础的 Oracle 数据库的图面介绍用于与 Oracle E-business Suite 使用适配器进行通信的消息结构。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]支持两个接口用于检索元数据。  
  
- 通过提供 MetadataExchange [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]。 WCF 提供了元数据交换终结点的所有 WCF 绑定，它允许客户端从 Oracle E-business Suite 获取元数据。  
  
- 通过提供 IMetadataRetrievalContract [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]，它支持的元数据浏览和搜索功能的适配器。  
  
  [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite 和基础数据库项目和相应适配器客户端可以调用的操作的图面。 本主题后面将讨论这些操作。  
  
  适配器客户端用于浏览、 搜索和检索的元数据：  
  
- 在 Visual Studio 中创建 BizTalk 项目  
  
- 使用 WCF 通道模型  
  
- 使用 WCF 服务模型  
  
  在使用 BizTalk 项目，您必须使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]生成你想要执行 Oracle E-business Suite 中的操作的元数据。 使用 WCF 服务模型时，必须使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]生成用于 Oracle E-business Suite 中执行操作的代理类。 有关浏览、 搜索和检索元数据中使用的详细信息[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，请参阅[获取用于 Visual Studio 中的 Oracle E-business Suite 操作的元数据](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)。  
  
## <a name="browsing-metadata"></a>浏览元数据  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使适配器客户端能够浏览接口表、 界面视图、 并发程序，并请求 Oracle E-business Suite 和表、 视图、 存储的过程、 函数和基础数据库中的包中的集。 作为元数据浏览操作的一部分，该适配器还显示可以对 Oracle 数据库，包括适配器支持某些自定义操作执行的操作。 这些操作是可从[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]显示大部分的以下三个节点下的操作：  
  
1. **基于应用程序的视图**:包含每个应用程序在 Oracle E-business Suite 项目分组的操作。  
  
2. **基于项目的视图**:包含由 Oracle E-business Suite 和基础数据库中的项目类型 （如接口表、 界面视图等） 进行分组的操作。  
  
3. **基于架构的视图**:包含按基础数据库项目的每个架构分组的操作。  
  
   有一些适用于两个节点的一般操作在根级别公开。 此外，不同的操作会显示根据操作类型： 出站或入站。  
  
   下表列出了显示的出站和入站操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]:  
  
|                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            出站操作                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |                                                                                                                                                                                                                                                                                                                                                                     入站的操作                                                                                                                                                                                                                                                                                                                                                                      |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **基于应用程序的视图**:<br /><br /> 包含一系列基础 Oracle E-business Suite 中的 Oracle 应用程序。 展开一个 Oracle 应用程序节点以查看以下项目：<br /><br /> <ul><li>**接口表**:所有接口表的列表。 选择一个接口表以查看插入、 选择、 更新和删除操作。</li><li>**界面视图**:所有界面视图的列表。 选择一个接口视图选择的操作。</li><li>**并发程序**:并发程序的以下操作：<br /><br /> <ul><li>所有的并发程序特定于 Oracle 应用程序公开作为操作的一组。</li><li>Get_Status 操作以获取并发程序的状态。</li><li>要等待的请求都完成后才返回状态的 Wait_For_Request 操作。</li><li>要调用或通过指定并发程序的执行所需的参数执行并发程序的 Submit_Request 操作。</li></ul></li><li>**请求集**:所有请求的一组设置特定于 Oracle 应用程序公开的操作。</li></ul> |                                                 **基于应用程序的视图**:<br /><br /> 包含一系列基础 Oracle E-business Suite 中的 Oracle 应用程序。 展开一个 Oracle 应用程序节点以查看以下项目：<br /><br /> -   **接口表**:轮询操作的接口表，使适配器客户端从 Oracle E-business Suite 获取入站的数据基于轮询机制适配器支持的查询。<br />-   **界面视图**:界面视图，使适配器客户端从 Oracle E-business Suite 获取入站的数据的轮询操作以轮询机制适配器支持的查询为基础。                                                  |
|                                                                                                                                                                                                                                                                    **基于项目的视图**:<br /><br /> 包含在 Oracle E-business Suite 和基础数据库中的所有项目。 展开项目节点，请参阅 Oracle 应用程序或基于 （应用程序或数据库） 的项目的源架构的列表。 例如，**接口表**节点将显示一组 Oracle 应用程序，而**表**节点将显示数据库架构的列表。<br /><br /> **基于项目的视图**下列出的项目将显示**基于应用程序的视图**并**基于架构的视图**。 每个项目节点列出了针对 Oracle 应用程序或数据库架构的相关操作。                                                                                                                                                                                                                                                                     |            **基于项目的视图**:<br /><br /> 除并发程序请求集以及包含 Oracle E-business Suite 中的所有项目和基础数据库中的所有项目。 展开项目节点，请参阅 Oracle 应用程序或基于 （应用程序或数据库） 的项目的源架构的列表。 例如，**接口表**节点将显示一组 Oracle 应用程序，而**表**节点将显示数据库架构的列表。<br /><br /> **基于项目的视图**下列出的项目将显示**基于应用程序的视图**并**基于架构的视图**。 每个项目节点列出了针对 Oracle 应用程序或数据库架构的相关操作。             |
|                                                                                                                                                                                                                                       **基于架构的视图**:<br /><br /> 包含一系列基础的 Oracle 数据库中的架构。 展开 schema 节点以查看以下项目：<br /><br /> -   **PL/SQL Api**:所有 PL/SQL Api 的列表。 选择要查看的打包的过程和函数公开为操作的 PL/SQL API。<br />-   **过程**:在架构中公开作为操作的过程的列表。<br />-   **函数**:在架构中作为操作公开的函数的列表。<br />-   **表**:所有表的列表。 选择一个表以查看插入、 选择、 更新和删除操作。<br />-   **视图**:所有视图的列表。 选择要查看在选择操作的视图。                                                                                                                                                                                                                                       | **基于架构的视图**:<br /><br /> 包含一系列基础的 Oracle 数据库中的架构。 展开 schema 节点以查看以下项目：<br /><br /> -   **PL/SQL Api**:所有 PL/SQL Api 的列表。 选择要查看的打包的过程和函数公开为操作的轮询的 PL/SQL API。<br />-   **过程**:公开作为操作的轮询架构中的过程的列表。<br />-   **函数**:在架构中作为用于轮询的操作公开的函数的列表。<br />-   **表**:所有表的列表。 选择要查看表的轮询操作的表。<br />-   **视图**:所有视图的列表。 选择要查看轮询操作视图的视图。 |
|                                                                                                                                                                                                                                                                                                                                                              [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]还公开了根级别上的以下泛型出站操作：ExecuteReader、 ExecuteScalar 和 ExecuteNonQuery。 有关这些操作的信息，请参阅[支持 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)。                                                                                                                                                                                                                                                                                                                                                               |                                                                                                             [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]还公开了使适配器客户端能够从 Oracle E-business Suite 接收数据库更改通知消息的根级别的通知操作。 通知操作有关的详细信息，请参阅[接收数据库更改通知时的注意事项](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md)。                                                                                                             |
  
 有关元数据的分类方式的详细信息，请参阅[浏览、 搜索和检索用于 Oracle E-business 操作的元数据](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)。  
  
## <a name="searching-metadata"></a>搜索元数据  
 使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，可以在 Oracle E-business Suite 中执行搜索查询并在基础使用 Oracle 的 Oracle 数据库上搜索符合 LIKE 运算符的表达式。 例如，适配器客户端可以使用如"EMP %"的搜索表达式以获取开头 EMP 的表。 该适配器将此转换为下面的 SQL 查询：  
  
```  
SELECT TABLE_NAME FROM ALL_TABLES WHERE TABLE_NAME LIKE 'EMP%' AND OWNER = 'SCOTT'  
```  
  
 其中，SCOTT，是使用 Oracle 数据库项目的集合的架构。  
  
 下表列出了可用于搜索和通过其解释的特殊字符[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
|特殊字符|解释|  
|-----------------------|--------------------|  
|_（下划线）|只匹配一个字符<br /><br /> 例如，A_ 匹配 AB、 交流和 AD。|  
|%（百分比）|匹配零个或多个字符。<br /><br /> 例如，%匹配一个，AB，ABC。|  
|\ （转义）|转义的特殊含义的 %和 _。 \ (Escape) 字符的通配符字符之前用来指示应将通配符字符解释为常规字符。<br /><br /> 例如，一个\\_B 匹配 A_B。|  
  
> [!IMPORTANT]
> - 区分大小写的搜索字符串。  
>   -   搜索适用于以不同的方式 （基于应用程序的视图中，基于项目的视图和基于架构的视图） 的不同视图。 若要了解可以如何搜索项目和每个视图下的操作，请参阅在"搜索在不同视图"[用于 Oracle E-business Suite 操作的搜索](../../adapters-and-accelerators/adapter-oracle-ebs/search-for-oracle-e-business-suite-operations.md)。  
>   -   若要搜索的应用程序可以指定友好名称或应用程序的短名称。 例如，若要搜索**应收帐款**应用程序可以为指定的搜索字符串**接收 %** 或**AR**。 AR 是应用程序短名称。  
>   -   若要搜索的并发程序可以指定友好名称或并发程序的实际名称。 例如，若要搜索**的客户界面**并发程序可以为指定的搜索字符串 **%客户接口 %** 或 **%RACUST%**。 RACUST 是并发程序的实际名称。 此外，搜索结果将始终包含标准的并发程序而不考虑其名称是否与指定的搜索字符串相匹配。  
  
## <a name="retrieving-metadata"></a>检索元数据  
 在检索元数据，[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]可以提取在架构包括所有的元数据或使用相应的对象和操作参数对象的数据库的子集。 适配器将从 Oracle E-business Suite 和基础的 Oracle 数据库实体表示为 XML 中的元素名称。 由于下划线是可以包含的唯一允许特殊字符，因此使用下划线进行编码的元素名称中的所有其他特殊字符。 例如，`emp$name`被编码为`emp_x0024_name`。 有关详细信息，请参阅[获取有关 Visual Studio 中使用 SQL 适配器中的 SQL Server 操作的元数据](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)。  
  
## <a name="see-also"></a>另请参阅  
 [了解用于 Oracle E-business Suite 的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)   
 [浏览、 搜索和检索 Oracle 电子商务操作的元数据](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)   
 [获取 Visual Studio 中的 Oracle E-business Suite 操作的元数据](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)