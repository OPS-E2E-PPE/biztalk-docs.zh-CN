---
title: "浏览、 搜索和获取 Oracle E-business Suite 元数据 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b516c6e9-dbb3-4977-bb27-aa039e021912
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ce665ef71cbf0849caab334cf62c5f7a659ea96
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="browse-search-and-get-oracle-e-business-suite-metadata"></a>浏览、 搜索和获取 Oracle E-business Suite 元数据
元数据，[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]从 Oracle E-business Suite 和基础的 Oracle 数据库的图面描述用于与 Oracle E-business Suite 使用适配器进行通信的消息结构。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]为检索元数据支持两个接口。  
  
-   MetadataExchange 由[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]。 WCF 提供了元数据交换终结点的所有 WCF 绑定，它使客户端从 Oracle E-business Suite 获取元数据。  
  
-   IMetadataRetrievalContract 由[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]，它支持浏览和搜索功能的适配器的元数据。  
  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]呈现 Oracle E-business Suite 和基础数据库项目和相应的适配器客户端可以调用的操作。 本主题中后面讨论了这些操作。  
  
 适配器客户端用于浏览、 搜索和检索元数据：  
  
-   在 Visual Studio 中创建 BizTalk 项目  
  
-   使用 WCF 通道模型  
  
-   使用 WCF 服务模型  
  
 在使用 BizTalk 项目，你必须使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]生成你想要在 Oracle E-business Suite 中执行的操作的元数据。 在使用 WCF 服务模型，你必须使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]生成在 Oracle E-business Suite 中执行操作的代理类。 有关浏览、 搜索和检索元数据中使用的详细信息[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]或[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，请参阅[获取用于在 Visual Studio 中的 Oracle E-business Suite 操作的元数据](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)。  
  
## <a name="browsing-metadata"></a>浏览元数据  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]允许适配器客户端浏览接口表、 界面视图、 并发程序，以及请求 Oracle E-business Suite 和表、 视图、 存储的过程、 函数和基础数据库中的包中的集。 作为元数据浏览操作的一部分，该适配器还显示可以对 Oracle 数据库中，包括被适配器支持某些自定义操作执行的操作。 这些操作仅从可用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]， [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]，和[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]呈现大部分在以下三个节点的操作：  
  
1.  **基于应用程序的视图**： 包含 Oracle E-business Suite 项目的每个应用程序按分组的操作。  
  
2.  **基于项目的视图**： 包含分组通过 Oracle E-business Suite 和基础数据库中的项目类型 （如接口表、 界面视图等） 的操作。  
  
3.  **基于架构的视图**： 包含按每个架构的基础数据库项目分组的操作。  
  
 有一些适用于两个节点的一般操作在根级别上公开。 此外，不同的操作中加以表示基于操作的类型： 站或出站。  
  
 下表列出了显示的出站和入站操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]:  
  
|出站操作|入站的操作|  
|-------------------------|------------------------|  
|**基于应用程序的视图**:<br /><br /> 包含基础 Oracle E-business Suite 中的 Oracle 应用程序的列表。 展开 Oracle 应用程序节点以查看以下项目：<br /><br /> <ul><li>**接口表**： 接口的所有表的列表。 选择接口的表以查看插入、 选择、 更新和删除操作。</li><li>**接口视图**： 所有接口视图的列表。 选择接口视图之间进行切换的选择操作。</li><li>**并发程序**： 对并发程序执行以下操作：<br /><br /> <ul><li>所有的并发程序特定于 Oracle 应用程序作为操作公开一组。</li><li>要获取的并发程序状态的 Get_Status 操作。</li><li>要等待的请求在返回状态之前完成的 Wait_For_Request 操作。</li><li>若要调用或通过指定的并发程序执行所需的参数执行并发程序 Submit_Request 操作。</li></ul></li><li>**请求集**： 一组的所有请求设置特定于公开作为操作 Oracle 应用程序。</li></ul>|**基于应用程序的视图**:<br /><br /> 包含基础 Oracle E-business Suite 中的 Oracle 应用程序的列表。 展开 Oracle 应用程序节点以查看以下项目：<br /><br /> -   **接口表**: 轮询操作接口表，使适配器客户端从 Oracle E-business Suite 获取入站的数据基于适配器支持的查询轮询机制。<br />-   **接口视图**: 轮询操作界面视图，使适配器客户端从 Oracle E-business Suite 获取入站的数据基于适配器支持的查询轮询机制。|  
|**基于项目的视图**:<br /><br /> 包含 Oracle E-business Suite 和基础数据库中的所有项目。 展开项目节点以查看 Oracle 应用程序或基于的源的项目 （应用程序或数据库） 的架构的列表。 例如，**接口表**节点将显示 Oracle 应用程序的列表，而**表**节点将显示数据库架构的列表。<br /><br /> **基于项目的视图**显示下列出的项目**基于应用程序的视图**和**基于架构的视图**。 每个项目节点列出了 Oracle 应用程序或数据库架构相关的操作。|**基于项目的视图**:<br /><br /> 并发程序和请求集，除包含 Oracle E-business Suite 中的所有项目和基础数据库中的所有项目。 展开项目节点以查看 Oracle 应用程序或基于的源的项目 （应用程序或数据库） 的架构的列表。 例如，**接口表**节点将显示 Oracle 应用程序的列表，而**表**节点将显示数据库架构的列表。<br /><br /> **基于项目的视图**显示下列出的项目**基于应用程序的视图**和**基于架构的视图**。 每个项目节点列出了 Oracle 应用程序或数据库架构相关的操作。|  
|**基于架构的视图**:<br /><br /> 包含基础的 Oracle 数据库中的架构的列表。 展开架构节点以查看以下项目：<br /><br /> -   **PL/SQL Api**： 所有 PL/SQL Api 的列表。 选择要查看的打包的过程和函数作为操作公开一个 PL/SQL API。<br />-   **过程**： 架构中公开作为操作的过程的列表。<br />-   **函数**： 公开作为操作架构中的函数的列表。<br />-   **表**： 所有表的列表。 选择一个表以查看插入、 选择、 更新和删除操作。<br />-   **视图**： 所有视图的列表。 选择要查看选择操作的视图。|**基于架构的视图**:<br /><br /> 包含基础的 Oracle 数据库中的架构的列表。 展开架构节点以查看以下项目：<br /><br /> -   **PL/SQL Api**： 所有 PL/SQL Api 的列表。 选择要查看的打包的过程和函数作为进行轮询的操作公开一个 PL/SQL API。<br />-   **过程**： 架构中公开作为操作进行轮询的过程的列表。<br />-   **函数**： 架构中作为进行轮询的操作公开的函数的列表。<br />-   **表**： 所有表的列表。 选择要查看针对表的轮询操作的表。<br />-   **视图**： 所有视图的列表。 选择要查看视图轮询操作的视图。|  
|[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]还公开以下泛型根级别的出站操作： ExecuteReader、 ExecuteScalar 和 ExecuteNonQuery。 有关这些操作的信息，请参阅[支持 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)。|[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]还公开允许接收来自 Oracle E-business Suite 数据库更改通知消息的适配器客户端的根级别的通知操作。 有关通知操作的详细信息，请参阅[接收数据库更改通知时的注意事项](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md)。|  
  
 有关元数据的分类方式的详细信息，请参阅[浏览、 搜索和检索用于 Oracle E-business 操作的元数据](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)。  
  
## <a name="searching-metadata"></a>搜索元数据  
 使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，你可以在 Oracle E-business Suite 中执行搜索查询并在使用 Oracle 基础的 Oracle 数据库上搜索符合 LIKE 运算符的表达式。 例如，适配器客户端可以使用如"EMP %"搜索表达式以获取开头 EMP 的表。 适配器将此转换为以下 SQL 查询：  
  
```  
SELECT TABLE_NAME FROM ALL_TABLES WHERE TABLE_NAME LIKE 'EMP%' AND OWNER = 'SCOTT'  
```  
  
 其中，SCOTT 是架构的 Oracle 数据库项目的集合。  
  
 下表列出了可以用于搜索和其解释的特殊字符[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
|特殊字符|解释|  
|-----------------------|--------------------|  
|_（下划线）|完全匹配一个字符<br /><br /> 例如，A_ 匹配 AB、 交流和 AD。|  
|%（百分比）|匹配零个或多个字符。<br /><br /> 例如，%匹配 A，AB，ABC。|  
|\ （转义）|转义的特殊含义的 %和 _。 \ (Escape) 字符的通配符字符之前使用以指示应将通配符字符解释为正则字符。<br /><br /> 例如，A\\_B 匹配 A_B。|  
  
> [!IMPORTANT]
>  -   区分大小写的搜索字符串。  
> -   搜索不同的视图 （基于应用程序的视图，基于项目的视图和基于架构的视图） 下工作方式。 若要了解可以如何搜索项目和每个视图下的操作，查看"搜索下不同的视图"中[用于 Oracle E-business Suite 操作的搜索](../../adapters-and-accelerators/adapter-oracle-ebs/search-for-oracle-e-business-suite-operations.md)。  
> -   若要搜索应用程序可以指定友好名称或应用程序的短名称。 例如，若要搜索**应收帐款**应用程序可以为指定的搜索字符串**接收 %**或**AR**。 AR 是应用程序短名称。  
> -   若要搜索的并发程序可以指定友好名称或并发程序的实际名称。 例如，若要搜索**客户接口**可以为指定的搜索字符串的并发程序**%客户接口 %**或**%RACUST%**。 RACUST 是程序的并发的实际名称。 此外，搜索结果将始终包含标准的并发程序而不考虑其名称是否与指定的搜索字符串相匹配。  
  
## <a name="retrieving-metadata"></a>检索元数据  
 检索元数据时,[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]数据库的子集的对象使用相应的对象和操作参数或可以提取在架构包括所有的元数据。 XML 中用作元素名称还原时，该适配器显示从 Oracle E-business Suite 和基础的 Oracle 数据库的实体。 由于下划线是可以包含的仅允许特殊字符，元素名称中的所有其他特殊字符进行编码使用下划线。 例如，`emp$name`被编码为`emp_x0024_name`。 有关详细信息，请参阅[获取元数据使用的 SQL 适配器的 Visual Studio 中的 SQL Server 操作](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)。  
  
## <a name="see-also"></a>另请参阅  
 [了解有关 Oracle E-business Suite 的 BizTalk Adapter](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)   
 [浏览、 搜索和检索用于 Oracle E-business 操作的元数据](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)   
 [获取 Visual Studio 中的 Oracle E-business Suite 操作的元数据](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)