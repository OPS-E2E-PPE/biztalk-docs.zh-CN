---
title: 配置客户端绑定用于 Oracle 数据库 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- client binding, specifying in code
- WCF client, creating
- client binding, specifying in configuration file
ms.assetid: f18c7296-c28a-4dec-9514-5299c8c2dffe
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7de5eeb9a7b0022ce4da5f56591e863f48bd0b61
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214605"
---
# <a name="configure-a-client-binding-for-the-oracle-database"></a>配置客户端绑定用于 Oracle 数据库
在你生成 WCF 客户端类后，可以创建一个 WCF 客户端 （实例） 并调用其方法来使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 有关如何生成操作的 WCF 客户端类和帮助程序代码，[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]公开，请参阅[为 Oracle 数据库解决方案项目生成 WCF 客户端或 WCF 服务约定](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)。  
  
 若要创建 WCF 客户端，必须指定终结点地址和绑定。 终结点地址必须包含有效的 Oracle 连接 URI，并且绑定必须 Oracle DB 绑定的一个实例 (**OracleDBBinding**)。 有关 Oracle 连接 URI 的详细信息，请参阅[创建 Oracle 数据库连接 URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)。 我们建议你不要连接 URI 的一部分指定的用户凭据。 而改用**ClientCredentials**的 WCF 客户端，如本主题中所述的属性。  
  
 在你的代码或配置文件中，可以指定 Oracle DB 绑定和终结点地址。 当你使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]若要生成 WCF 客户端类，创建配置文件 (app.config) 还为你的项目。 此文件包含反映的绑定属性和连接信息 （除凭据） 连接到 Oracle 数据库时指定的配置设置[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
## <a name="specifying-the-binding-and-endpoint-address-in-code"></a>在代码中指定的绑定和终结点地址  
 下面的代码演示如何通过在代码中指定的绑定和终结点地址创建 WCF 客户端。 它是通过使用指定的 Oracle 凭据的好办法**ClientCredentials**的 WCF 客户端而不是连接的终结点地址为提供的 URI 中的属性。  
  
```  
// A WCF client that targets the /SCOTT/EMP table is created  
// by using a binding object and endpoint address  
OracleDBBinding odbBinding = new OracleDBBinding();  
EndpointAddress odbAddress = new EndpointAddress("OracleDb://ADAPTER");  
  
SCOTTTableEMPClient empClient = new SCOTTTableEMPClient(odbBinding, odbAddress);  
  
empClient.ClientCredentials.UserName.UserName = "SCOTT";  
empClient.ClientCredentials.UserName.Password = "TIGER";  
  
empClient.Open();  
```  
  
## <a name="specifying-the-binding-and-endpoint-address-in-a-configuration-file"></a>在配置文件中指定的绑定和终结点地址  
 下面的代码演示如何通过 app.config 文件中指定的绑定和终结点地址创建 WCF 客户端。  
  
```  
// A WCF client that targets the /SCOTT/EMP table is created  
// by specifying the client endpoint information in app.config  
SCOTTTableEMPClient empClient = new SCOTTTableEMPClient("OracleDBBinding_SCOTT.Table.EMP");  
  
empClient.ClientCredentials.UserName.UserName = "SCOTT";  
empClient.ClientCredentials.UserName.Password = "TIGER";  
  
empClient.Open();  
```  
  
 下面的 XML 演示通过 EMP 表所创建的配置文件[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 此文件包含在前面的示例中引用的客户端终结点配置。  
  
```  
\<?xml version="1.0" encoding="utf-8"?>  
<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">  
    \<system.serviceModel>  
        <bindings>  
            <oracleDBBinding>  
                <binding name="OracleDBBinding" closeTimeout="00:01:00" openTimeout="00:01:00"  
                    receiveTimeout="00:10:00" sendTimeout="00:01:00"  
                    dataFetchSize="65536" metadataPooling="true" statementCachePurge="false"  
                    statementCacheSize="10" longDatatypeColumnSize="32767" pollingStatement=""  
                    postPollStatement="" pollingInterval="500" useOracleConnectionPool="false"  
                    minPoolSize="1" maxPoolSize="100" incrPoolSize="5" decrPoolSize="1"  
                    connectionLifetime="0" transactionIsolationLevel="ReadCommitted"  
                    enablePerformanceCounters="false" acceptCredentialsInUri="false"  
                    enableBizTalkCompatibilityMode="false" />  
            </oracleDBBinding>  
        </bindings>  
        <client>  
            <endpoint address="oracledb://adapter/" binding="oracleDBBinding"  
                bindingConfiguration="OracleDBBinding" contract="SCOTTTableEMP"  
                name="OracleDBBinding_SCOTT.Table.EMP" />  
        </client>  
    \</system.serviceModel>  
</configuration>  
```  
  
 如果一个项目具有多个 WCF 客户端，将有多个客户端配置文件中定义的终结点条目。 WCF 客户端的每个条目将具有唯一的名称基于它的绑定配置和目标 Oracle 数据库项目;例如，"OracleDBBinding_SCOTT。Table.EMP"。 如果你连接多个项目中创建 WCF 客户端的时机，多个绑定配置条目将创建，一个用于每个连接。 这些绑定配置条目将被命名为按以下方式： OracleDBBinding1、 OracleDBBinding2，依次类推。 在特定的连接过程中创建的每个客户端终结点条目将引用在该连接过程中创建的绑定项。  
  
## <a name="see-also"></a>另请参阅  
 [通过使用 WCF 服务模型开发 Oracle 数据库应用程序](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md)   
 [为 Oracle 数据库解决方案项目生成 WCF 客户端或 WCF 服务协定](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)   
 [创建 Oracle 数据库连接 URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)   
 [通过使用 WCF 通道模型开发 Oracle 数据库应用程序](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)