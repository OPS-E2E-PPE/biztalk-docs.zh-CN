---
title: "密钥的 Oracle E-business Suite 的 BizTalk 适配器中的功能 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a43091ab-f81c-4c4f-bcc3-e6abe16d3d77
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d89da490f604e50924544e54cb5ffe7018a8724e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="key-features-in-biztalk-adapter-for-oracle-e-business-suite"></a>用于 Oracle E-business Suite 的 BizTalk adapter 中的主要功能
本部分列出中的关键功能[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]。  
  
## <a name="technology-related-features"></a>技术相关功能  
  
|功能|注释|  
|-------------|-------------|  
|Windows Communication Foundation (WCF) 的使用|[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]之上生成[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]([!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)])。 反过来，[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]基于 WCF。 作为 WCF 通道向适配器客户端公开适配器。 这使连接、 元数据交换和与外部系统的业务数据交换。|  
|对 WCF 通道模型和 WCF 服务模型的支持|在 WCF*通道*适配器客户端可以使用模型，[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]通过直接发送和接收 XML 消息。<br /><br /> 在 WCF*服务*模型，适配器客户端可以生成的.NET 代理类从 Web 服务描述语言 (WSDL) 使用获取[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。|  
|ODP.NET 的使用|[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使用 Oracle 数据提供程序的.NET (ODP.NET) 与 Oracle E-business Suite 的接口。|  
|两种方法将连接到 Oracle E-business Suite|通过使用 net 服务名称 tnsnames.ora 文件中或者通过直接指定连接参数，并因此不再需要使用 net 服务名称或 tnsnames.ora 文件，适配器客户端可以连接到 Oracle E-business Suite。 不需要 tnsnames.ora 文件以连接到 Oracle E-business Suite 将保存你的麻烦的手动更新的连接参数 （net 服务名称） 从在每个客户端计算机上的 tnsnames.ora 文件时添加或更新中的 Oracle 服务器你环境。 有关详细信息，请参阅[配置连接到 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-connection-uri-for-oracle-e-business-suite.md)。|  
|支持 Windows 身份验证|适配器客户端可以使用 Windows 身份验证以连接到 Oracle E-business Suite。 Windows 身份验证使您能够确定用户的标识基于的 Windows 登录凭据，并因此可帮助你利用内置的安全的 Windows 环境。 有关中的 Windows 身份验证的详细信息[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，请参阅[连接到 Oracle E-business Suite 使用 Windows 身份验证](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-oracle-e-business-suite-using-windows-authentication.md)。|  
|支持使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]与 Microsoft Office SharePoint Server (MOSS)|适配器可用于从 Oracle E-business Suite 到 MOSS 门户上显示数据。 有关详细信息，请参阅[与 Microsoft Office SharePoint Server 一起使用 Oracle E-business 适配器](https://msdn.microsoft.com/library/dd788485.aspx)。|  
  
## <a name="metadata-related-features"></a>元数据相关的功能  
  
|功能|注释|  
|-------------|-------------|  
|批量检索的元数据|适配器客户端可以浏览和搜索由 Oracle E-business Suite 和基础数据库的所有项目的元数据。 项目会显示基于连接的用户的凭据，并将其：<br /><br /> -按每个应用程序的 Oracle E-business Suite 项目分组。<br />-按 Oracle E-business Suite 和基础数据库中每个项目分组。<br />-按基础数据库项目的每个架构分组。|  
  
## <a name="performance-related-features"></a>与性能相关的功能  
  
|功能|注释|  
|-------------|-------------|  
|连接池|[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使客户端能够使用 ODP.NET 连接池通过配置**UseOracleConnectionPool**绑定属性。 有关此绑定属性的详细信息，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。|  
|缓存管理|[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使客户端可以通过配置使用 ODP.NET 缓存管理**StatementCachePurge**和**StatementCacheSize**绑定属性。 有关此绑定属性的详细信息，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。|  
|对性能计数器的支持|[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]以适配器客户端使用支持基于 WCF 的性能计数器。 有关性能计数器的详细信息，请参阅[使用性能计数器与 SQL 适配器](../../adapters-and-accelerators/adapter-sql/use-performance-counters-with-the-sql-adapter.md)。|  
  
## <a name="operations-related-features"></a>与操作相关的功能  
  
|功能|注释|  
|-------------|-------------|  
|接口表和界面视图上的操作的支持|适配器客户端可以执行基本的插入、 更新、 删除和对 Oracle E-business Suite 接口表选择操作。 仅可以对 Oracle E-business Suite 界面视图执行选择操作。|  
|用于执行 PL/SQL Api 的支持|适配器客户端可以在 Oracle E-business Suite 中执行 PL/SQL Api。 PL/SQL Api 包含存储的过程和函数在一个包内。|  
|正在执行的并发程序的支持|适配器客户端可以在 Oracle E-business Suite 中执行并发程序。|  
|用于执行请求集的支持|适配器客户端可以在 Oracle E-business Suite 中执行请求集。 请求集是一套并发程序，可以用于使用预定义的参数运行多个并发程序。 请求集将按阶段执行。 有关请求集的详细信息，请参阅[http://go.microsoft.com/fwlink/?LinkId=129539](http://go.microsoft.com/fwlink/?LinkId=129539)。|  
|在插入操作中指定内联值的支持|你可以使用**InlineValue**中将计算的值插入接口表和 Oracle 中的数据库表执行插入操作的属性。 这是一个可选属性，可用于插入操作中的所有简单数据记录。 如果指定此属性的值，它将重写的记录指定的值。 有关 InlineValue 属性的详细信息，请参阅[接口表和接口视图上的操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-interface-tables-and-interface-views.md)。|  
|使用轮询的入站调用的支持|[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]接收"轮询基于"数据更改的消息适配器指定的 SQL 语句、 存储的过程、 函数或过程在包中，将执行其中的支持检索数据，然后将提供给客户端的结果。|  
|对调用函数和过程的支持|适配器客户端可以调用函数和基础的 Oracle 数据库中的过程。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]显示为可以在基础的 Oracle 数据库执行的操作的函数和过程。|  
|对复合操作的支持|[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使适配器客户端能够在 Oracle E-business Suite 中执行复合操作。 复合操作可以包含任意数量的以下操作，并按任何顺序：<br /><br /> -针对接口表、 界面视图、 表和视图的操作。<br />存储过程、 函数和过程中加以表示的包内作为适配器中的操作。|  
|用于执行任意 SQL 语句和 PL/SQL 块的支持|[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]使适配器客户端来执行任意 SQL 语句或 PL/SQL 块使用 ExecuteReader、 ExecuteScalar 和 ExecuteNonQuery 操作。 有关这些操作的详细信息，请参阅[支持 ExecuteNonQuery、 ExecuteReader 和 ExecuteScalar 操作](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-executenonquery-executereader-and-executescalar-operations.md)。|  
|支持用户定义类型 (Udt)、 布尔参数和 PL/SQL 表类型|在存储的过程和包含布尔参数和 PL/SQL 表类型的函数，就可以支持包含 Udt 的项目中的操作和操作进行适配器客户端。 有关 UDT 支持的信息，请参阅[支持 Oracle User-Defined 类型](../../adapters-and-accelerators/adapter-oracle-ebs/support-for-oracle-user-defined-types2.md)。|  
|支持的输入和输出 REF CURSOR|适配器的客户端可以运行使用输入和输出上过程和函数的 REF CURSOR。|  
|PL/SQL 记录数据类型支持|适配器客户端可以采用与记录和运行存储的过程或函数中的嵌套的记录类型。|  
|中 PL/SQL API 的重载的函数和过程的支持|适配器客户端可以调用重载的函数和 PL/SQL Api 中的过程。 但是，[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]不支持重载过程使用强类型和弱类型化的 REF CURSOR 的使用。 在内部，该适配器将这两个强类型和弱类型 REF CURSOR 视为只 REF CURSOR。|  
|对数据库更改通知的支持|适配器客户端可以接收来自基于触发的 SELECT 语句的 Oracle 数据库的数据库更改通知。 向作为适配器客户端和在结果集的 SELECT 语句更改时，将 Oracle 数据库发送通知。 有关数据库更改通知的详细信息，请参阅[注意事项接收数据库更改通知使用 ORacle 数据库适配器](../../adapters-and-accelerators/adapter-oracle-database/before-you-receive-database-change-notifications-using-the-oracle-db-adapter.md)。|  
|同义词的支持|适配器客户端可以执行操作上为表、 视图、 存储的过程、 函数和包创建的同义词。 有关同义词，以及你如何使用详细信息[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]若要对同义词执行操作，请参阅[对同义词的操作](../../adapters-and-accelerators/adapter-oracle-ebs/operations-on-synonyms2.md)。|  
  
## <a name="other-features"></a>其他功能  
  
|功能|注释|  
|-------------|-------------|  
|多语言支持 (MLS)|适配器客户端可以使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]Oracle E-business Suite 和具有多个安装的语言包的基础数据库中执行操作。 这意味着适配器客户端可以在多个语言中执行对数据的操作。 例如，可以在接口视图中，查看本地化 （非英语） 数据，或在表中插入本地化的数据。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]支持多语言支持的基础的 Oracle E-business Suite 安装。<br /><br /> [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]公开**MlsSettings**绑定属性来配置多个语言支持功能。 有关绑定属性的详细信息，请参阅[了解针对 Oracle E-business Suite 绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)。|  
  
## <a name="see-also"></a>另请参阅  
 [了解有关 Oracle E-business Suite 的 BizTalk Adapter](../../adapters-and-accelerators/adapter-oracle-ebs/understand-biztalk-adapter-for-oracle-e-business-suite.md)