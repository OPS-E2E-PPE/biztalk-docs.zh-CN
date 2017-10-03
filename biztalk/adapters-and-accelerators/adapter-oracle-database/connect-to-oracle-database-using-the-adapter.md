---
title: "使用连接到 Oracle 数据库适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- connection string
- uniform resource identifier
- Oracle database, connecting to
- URI
- connection URI
ms.assetid: 5d5598e5-aba0-4c73-8e97-9156475b93c4
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01b04a615d0b0b8cd83b9ed7516cd096b2c85a54
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="connect-to-oracle-database-using-the-adapter"></a>使用连接到 Oracle 数据库适配器
[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] ODP.NET 11.1.0.7 用于连接到 Oracle 数据库。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]要求适配器客户端提供连接字符串，调用统一资源标识符 (URI)，以连接到 Oracle 数据库的连接。 在内部，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]将 URI 映射到一个数据库连接字符串以连接到 Oracle 数据库。 通过连接 URI 适配器客户端可以指定要连接到外部系统的连接参数。  
  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]允许适配器客户端连接到 Oracle 数据库在以下两种方法：  
  
-   **使用 tnsnames.ora**： 连接适配器客户端提供的 URI 包含仅在 tnsnames.ora 文件中指定的 net 服务名称。 适配器从 tnsnames.ora 文件中的 net 服务名称条目提取如服务器名称、 服务名称和端口号的连接参数。 若要使用此方法，必须配置运行 Oracle 客户端的计算机为 tnsnames.ora 文件中包括 Oracle 数据库的 net 服务名称。  
  
    > [!IMPORTANT]
    >  由于 Oracle 客户端存在的限制， **DataSourceName**中的参数 （net 服务名称）[配置 Oracle 数据库适配器的连接 URI](../../adapters-and-accelerators/adapter-oracle-database/configure-the-connection-uri-for-the-oracle-database-adapter.md)不能包含超过 39 个字符，如果你在事务中执行操作。 因此，请确保为指定的值**DataSourceName**参数是否小于或等于 39 个字符如果你将在事务中执行操作。  
  
-   **而无需使用 tnsnames.ora**： 连接 URI 的适配器客户端提供包含如服务器名称、 服务名称和端口号的连接参数。 在这种情况下，在 tnsnames.ora 文件中或实际 tnsnames.ora 文件本身，net 服务名称不必存在于客户端计算机上。 如果有大量的用户连接到 Oracle 数据库中您的组织，并添加/更新服务器不会导致手动添加/更新每个客户端计算机上的 tnsnames.ora 文件中的连接详细信息，这非常有用。  
  
    > [!IMPORTANT]
    >  如果你在事务中执行操作，则不支持这种模式的连接。 这是因为 Oracle 客户端的限制。  
  
 有关连接到 Oracle 数据库的详细信息，请参阅[创建与 Oracle 数据库的连接](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md)。  
  
 请确保您遵守安全指导原则建立与 Oracle 数据库的连接时。 有关安全指导原则的详细信息，请参阅[保护 Oracle 数据库应用程序](../../adapters-and-accelerators/adapter-oracle-database/secure-your-oracle-database-applications.md)。  
  
## <a name="windows-authentication"></a>Windows 身份验证  
 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]连接到 Oracle 数据库时，支持 Windows 身份验证。 使用 Windows 身份验证适配器客户端可以确定用户的标识基于的 Windows 登录凭据，而且可以利用 Windows 环境的内置安全性。 有关使用 Windows 身份验证连接到 Oracle 数据库的信息，请参阅[连接到 Oracle 数据库使用 Windows 身份验证](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)。  
  
## <a name="see-also"></a>另请参阅  
 [用于 Oracle 数据库的 BizTalk Adapter 的概述](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)