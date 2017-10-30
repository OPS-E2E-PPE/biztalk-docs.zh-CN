---
title: "SQL Server 的密钥中的 BizTalk Adapter 功能 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d6beab8d-c2c4-4add-860c-054b9aed8d70
caps.latest.revision: "30"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42acb4f91a3b09b202e646e1220c0ea819103f04
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="key-features-in-biztalk-adapter-for-sql-server"></a>用于 SQL Server 的 BizTalk Adapter 中的主要功能
本部分列出中的功能[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]。  
  
> [!NOTE]
>  已从早期版本使用本主题[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]帮助。  
  
## <a name="features-in-the-sql-adapter"></a>中的 SQL 适配器的功能  
 以下是在早期版本中引入的功能[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
### <a name="technology-related-features"></a>技术相关功能  
  
|功能|注释|  
|-------------|-------------|  
|Windows Communication Foundation (WCF) 的使用|[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]之上生成[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)] ([!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)])。 反过来，[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]基于 WCF。 适配器将公开为适配器客户端的 WCF 通道。 这使连接、 元数据交换和与外部系统的业务数据交换。|  
|对 WCF 通道模型和 WCF 服务模型的支持|在 WCF 通道模型中，适配器客户端可以使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]通过直接发送和接收 XML 消息。 在 WCF 服务模型中，适配器客户端可以生成的.NET 代理类从 Web 服务描述语言 (WSDL) 使用获取[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。|  
|支持 64 位平台|[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]现已可供 64 位平台。|  
  
### <a name="metadata-related-features"></a>元数据相关的功能  
  
|功能|注释|  
|-------------|-------------|  
|浏览、 搜索和检索元数据|适配器客户端可以浏览和搜索在批次中的元数据，通过指定批大小。 仅在编程插入适配器而不是通过使用适配器服务 BizTalk 项目外接程序时，提供了此功能。 在表、 视图、 过程、 标量函数和表值函数级别支持元数据搜索。 直接在 SQL 语句中使用的搜索字符串。|  
|为了调用具有不同的数据库中的相同名称的项目的支持|在[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，包含仅架构名称，并在某些情况下，对象名称的 XML 架构定义 (XSD) 文件中的命名空间。 但是，如果某个应用程序想要在不同的数据库中执行对具有相同名称的项目具有不同的元数据的操作，生成的元数据将发生冲突。 将元数据区分开来的唯一方法是在 XSD 命名空间中使用的数据库名称。<br /><br /> 当前版本的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]允许你通过以指定数据库名称 XSD 命名空间中的值设置**UseDatabaseNameInXsdNamespace**绑定属性为 TRUE。 绑定属性的默认值为 false，这意味着 XSD 命名空间将不包含数据库名称。 有关详细信息**UseDatabaseNameInXsdNamespace**绑定属性，请参阅[了解针对 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。|  
  
### <a name="performance-related-features"></a>与性能相关的功能  
  
|功能|注释|  
|-------------|-------------|  
|对性能计数器的支持|[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]以适配器客户端使用支持基于 WCF 的性能计数器。 有关性能计数器的详细信息，请参阅[使用性能计数器与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/use-performance-counters-with-the-sql-adapter.md)。|  
  
### <a name="operations-related-features"></a>与操作相关的功能  
  
|功能|注释|  
|-------------|-------------|  
|SQL Server 2005 和 SQL Server 2008 数据类型支持|[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]支持以下中引入的数据类型：<br /><br /> -   **SQL Server 2005**: XML、 varchar （max） 和 varbinary （max）。<br />-   **SQL Server 2008**： 日期、 时间、 Datetimeoffset、 Datetime2、 Hierarchyid、 Geography、 Geometry、 和 FILESTREAM。|  
|对用户定义类型 (Udt) 的支持|[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]支持对表和包含 Udt 的视图执行操作。 有关 Udt 支持的信息，请参阅[对表和视图使用了 SQL 适配器的用户定义类型的操作](../../adapters-and-accelerators/adapter-sql/operations-on-tables-and-views-with-user-defined-types-using-the-sql-adapter.md)。|  
|支持用于执行 TRANSACT-SQL 和 CLR 存储过程和函数|TRANSACT-SQL 和 CLR，可以执行适配器客户端：<br /><br /> 的 SQL Server 数据库中存储过程。<br />标量和 SQL Server 数据库中的表值函数。<br /><br /> 有关此的详细信息，请参阅[操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185435(v=bts.10).aspx)。|  
|执行存储的过程带有或不带 FOR XML 子句的支持|[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使您能够执行具有或不带 FOR XML 子句的 SELECT 语句的存储的过程。 以前版本的适配器支持仅在 SELECT 语句中已有的 FOR XML 子句这些存储的过程。 有关执行存储的过程的信息，请参阅[中使用的 SQL 适配器的 SQL Server 执行存储过程](../../adapters-and-accelerators/adapter-sql/execute-stored-procedures-in-sql-server-using-the-sql-adapter.md)。|  
|对大型对象的流式处理支持|适配器客户端可以流式传输大型字符和使用一组 SQL Server 数据库中的二进制字段\<列名称 > 操作，其中 < column_name > 是的类型 varchar （max）、 nvarchar (max) 或 varbinary （max） 列的名称。 集\<列名称 > 操作还可以插入或更新 SQL Server 2008 数据库中的 FILESTREAM 数据。 有关此的详细信息，请参阅[操作对表和视图，包含大型数据类型使用的 SQL 适配器](../../adapters-and-accelerators/adapter-sql/supported-operations-on-tables-and-views-with-large-data-types-with-sql-adapter.md)。 **注意：**读取字符和 SQL Server 表和视图中的二进制字段，适配器客户端使用选择的操作。|  
|对查询通知的支持|适配器客户端可以接收来自 SQL Server 中根据触发的 SELECT 语句或存储的过程的查询通知。 向作为适配器客户端和在结果集的 SELECT 语句或存储的过程更改时，将由 SQL Server 发送通知。 有关查询通知的详细信息，请参阅[接收查询通知使用 BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-sql-query-notifications-using-biztalk-server.md)。|  
|用于执行任意 SQL 语句的支持|[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]使适配器客户端可以执行使用 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作的任意 SQL 语句。 有关这些操作的详细信息，请参阅[支持 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)。|  
|对复合操作的支持|[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]允许适配器客户端执行 SQL Server 数据库上的复合操作。 复合操作可以包含任意数量的以下操作，并按任何顺序：<br /><br /> 的对表和视图 Insert、 Update 和 Delete 操作。<br />的作为适配器中的操作中加以表示存储过程。<br /><br /> 有关复合操作的详细信息，请参阅[复合操作的消息架构](../../adapters-and-accelerators/adapter-sql/message-schemas-for-composite-operations.md)。|  
|增强的轮询|[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]现在支持两种其他类型的轮询： **TypedPolling**和**XmlPolling**。 有关这些轮询类型的信息，请参阅[支持为入站调用使用轮询](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-inbound-calls-using-polling.md)。|  
|在多个架构中执行对项目的操作的支持|除了默认架构 (dbo) 中，适配器客户端还可以执行对项目的操作中的 SQL Server 数据库中的其他架构，提供用户凭据用于连接使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]有权访问这些架构中的 SQL Server数据库。 有关 SQL Server 数据库中的架构的信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=130148](http://go.microsoft.com/fwlink/?LinkId=130148)。|  
  
## <a name="see-also"></a>另请参阅  
 [用于 SQL Server 的 BizTalk Adapter 的概述](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md)