---
title: 配置 E-business Suite 适配器的 Oracle 客户端 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 842b6ecc-5334-4cc0-af10-baa7f692ad23
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ada64bf6f54c95f3d6e1c8f968a506476dbbc6fd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214765"
---
# <a name="configure-the-oracle-client-for-the-e-business-suite-adapter"></a>配置 Oracle 客户端为 E-business Suite 适配器
> [!IMPORTANT]
>  本主题是仅当使用 tnsnames.ora 来连接到 Oracle 数据库相关。  
  
 若要建立的连接[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]，适配器连接到您的计算机上安装了 Oracle 客户端通过基础的 Oracle 数据库。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]将 net 服务名称传递到 Oracle 客户端来建立连接到 Oracle E-business Suite 连接 URI 中指定。 网络服务名称是 Oracle 客户端用于获取目标 Oracle 数据库服务的连接信息的别名。  
  
 Net 服务名称根据命名方法，它配置为使用 Oracle 客户端解析。 用于 Oracle Net Configuration Assistant 配置 Oracle 客户端使用的命名方法。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]将连接到 Oracle E-business Suite 支持本地命名方法。 此方法使用本地文件，tnsnames.ora，若要解决的 net 服务名称。  
  
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
oracleebs://ADAPTER  
```  
  
 有关使用 Oracle Net Configuration Assistant 以及 tnsnames.ora 的详细信息，请参阅 Oracle 数据库 Net 服务管理员的指南。 用于特定安装，请查阅你的数据库管理员，了解配置详细信息。  
  
## <a name="see-also"></a>另请参阅  
 [创建与 Oracle E-business Suite 的连接](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-connection-to-oracle-e-business-suite.md)