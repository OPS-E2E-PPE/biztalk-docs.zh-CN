---
title: 配置 Oracle 客户端 E-business Suite 适配器 |Microsoft Docs
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
ms.openlocfilehash: 13c29eef73f5268571c9c9eb33635a0f336954f6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375672"
---
# <a name="configure-the-oracle-client-for-the-e-business-suite-adapter"></a>配置 Oracle 客户端 E-business Suite 适配器
> [!IMPORTANT]
>  本主题是只适用于 tnsnames.ora 您用来连接到 Oracle 数据库。  
  
 若要建立与[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]，适配器将连接到您的计算机上安装了 Oracle 客户端通过基础的 Oracle 数据库。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]将 net 服务名称传递到 Oracle 客户端来连接到 Oracle E-business Suite 连接 URI 中指定。 网络服务名称是 Oracle 客户端用于获取目标 Oracle 数据库服务的连接信息的别名。  
  
 Net 服务名称根据命名方法，它配置为使用 Oracle 客户端解析。 用于 Oracle 网络配置助手配置 Oracle 客户端使用的命名方法。 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]用于连接到 Oracle E-business Suite 支持本地命名方法。 此方法使用本地文件，tnsnames.ora，net 服务名称解析。  
  
 使用 net 服务名称连接包含的 Oracle 客户端所需的信息来建立与特定的 Oracle 数据库服务 （实例） 的描述符 tnsnames.ora 文件相关联。 以下是从 tnsnames.ora 的示例条目。  
  
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
oracleebs://ADAPTER  
```  
  
 有关使用 Oracle Net Configuration Assistant 和 tnsnames.ora 的详细信息，请参阅 Oracle 数据库 Net 服务管理员的指南。 为特定安装，请咨询数据库管理员有关配置详细信息。  
  
## <a name="see-also"></a>请参阅  
 [创建与 Oracle E-business Suite 的连接](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-connection-to-oracle-e-business-suite.md)