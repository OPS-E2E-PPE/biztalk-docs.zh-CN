---
title: "配置 Oracle 数据库适配器 Oracle 客户端 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- net service name
- tnsnames.ora
- configuring, the Oracle client
- connect descriptor
- Oracle client, configuring
- Oracle Net Configuration Assistant
- Oracle Net Configuration Assistant, using the
ms.assetid: 2d4c0f20-b3a6-453f-a9b3-65fd5a38c020
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 209d5603a9f8ff8c09185093efb976afb6432d65
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-oracle-client-for-the-oracle-database-adapter"></a>配置 Oracle 数据库适配器 Oracle 客户端
> [!IMPORTANT]
>  本主题是仅当使用 tnsnames.ora 来连接到 Oracle 数据库相关。  
  
 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]连接到 Oracle 数据库中，通过在计算机上安装 Oracle 客户端。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]将 net 服务名称传递到 Oracle 客户端建立与 Oracle 数据库的连接的连接 URI 中指定。 网络服务名称是 Oracle 客户端用于获取目标 Oracle 数据库服务的连接信息的别名。  
  
 Net 服务名称根据命名方法，它配置为使用 Oracle 客户端解析。 用于 Oracle Net Configuration Assistant 配置 Oracle 客户端使用的命名方法。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]支持用于连接到 Oracle 数据库的本地命名方法。 此方法使用本地文件，tnsnames.ora，若要解决的 net 服务名称。  
  
 使用 net 服务名称连接包含 Oracle 客户端需要建立与特定的 Oracle 数据库服务 （实例） 的连接的信息的描述符 tnsnames.ora 文件相关联。 下面是从 tnsnames.ora 示例条目。  
  
```  
ADAPTER =  
  (DESCRIPTION =  
    (ADDRESS_LIST =  
      (ADDRESS = (PROTOCOL = TCP)(HOST = yourOracleServer)(PORT = 1521))  
    )  
    (CONNECT_DATA =  
      (SERVICE_NAME = yourOracleDatabaseServiceName)  
    )  
  )  
```  
  
 在此示例条目，适配器是网络服务名称。 连接描述符指定地址信息和与适配器关联的 Oracle 数据库服务的服务名称。 你可以使用 Oracle Net Configuration Assistant 创建和配置 tnsnames.ora net 服务名称。 配置网络服务名称后，可以指定它在连接中的 URI，如以下示例所示。  
  
```  
oracledb://ADAPTER  
```  
  
 有关使用 Oracle Net Configuration Assistant 以及 tnsnames.ora 的详细信息，请参阅 Oracle 数据库 Net 服务管理员的指南。 用于特定安装，请查阅你的数据库管理员，了解配置详细信息。  
  
## <a name="see-also"></a>另请参阅  
[创建与 Oracle 数据库的连接](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md)