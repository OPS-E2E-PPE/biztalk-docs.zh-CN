---
title: 配置 Oracle 数据库适配器的 Oracle 客户端 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a2186f4ea5400d01f477d0ab98c282e37e32d60
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376699"
---
# <a name="configure-the-oracle-client-for-the-oracle-database-adapter"></a>配置 Oracle 数据库适配器的 Oracle 客户端
> [!IMPORTANT]
>  本主题是只适用于 tnsnames.ora 您用来连接到 Oracle 数据库。  
  
 [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]连接到 Oracle 数据库通过您的计算机上安装了 Oracle 客户端。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]将 net 服务名称传递到 Oracle 客户端来连接到 Oracle 数据库的连接 URI 中指定。 网络服务名称是 Oracle 客户端用于获取目标 Oracle 数据库服务的连接信息的别名。  
  
 Net 服务名称根据命名方法，它配置为使用 Oracle 客户端解析。 用于 Oracle 网络配置助手配置 Oracle 客户端使用的命名方法。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]支持用于连接到 Oracle 数据库的本地命名方法。 此方法使用本地文件，tnsnames.ora，net 服务名称解析。  
  
 使用 net 服务名称连接包含 Oracle 客户端来建立与特定的 Oracle 数据库服务 （实例） 建立连接所需的信息的描述符 tnsnames.ora 文件相关联。 以下是从 tnsnames.ora 的示例条目。  
  
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
  
 在此示例条目中，适配器是 net 服务名称。 连接描述符指定地址信息和与适配器相关联的 Oracle 数据库服务的服务名称。 您可以使用 Oracle Net Configuration Assistant 来创建和配置 tnsnames.ora 中的 net 服务名称。 配置网络服务名称后，您可以如以下示例所示的连接 URI 中指定它。  
  
```  
oracledb://ADAPTER  
```  
  
 有关使用 Oracle Net Configuration Assistant 和 tnsnames.ora 的详细信息，请参阅 Oracle 数据库 Net 服务管理员的指南。 为特定安装，请咨询数据库管理员有关配置详细信息。  
  
## <a name="see-also"></a>请参阅  
[创建与 Oracle 数据库的连接](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md)