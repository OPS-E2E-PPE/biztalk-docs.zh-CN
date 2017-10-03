---
title: "为该 SQL 适配器配置客户端绑定 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 146e6f51-e33b-45be-a302-8c9250e79501
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af27363e5156ca88f2c6b3e06a67d0609bf52afe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configure-a-client-binding-for-the-sql-adapter"></a>为该 SQL 适配器配置客户端绑定
在你生成 WCF 客户端类后，可以创建一个 WCF 客户端 （实例） 并调用其方法来使用[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]。 有关如何生成操作的 WCF 客户端类和帮助程序代码，[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]公开，请参阅[为 SQL Server 项目生成 WCF 客户端或 WCF 服务协定](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)。  
  
 若要创建 WCF 客户端，必须指定终结点地址和绑定。 终结点地址必须包含有效的 SQL 连接 URI，并且绑定必须是 SQL 绑定的一个实例 (**sqlBinding**)。 有关 SQL 连接 URI 的详细信息，请参阅[创建 SQL Server 连接 URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)。 作为连接 URI 的一部分，必须指定的用户凭据。 你可以使用**ClientCredentials**的 WCF 客户端，如本主题中所述的属性。  
  
 在你的代码或配置文件中，可以指定 SQL 绑定和终结点地址。 当你使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]若要生成 WCF 客户端类，创建配置文件 (app.config) 还为你的项目。 此文件包含反映的绑定属性和连接信息 （除凭据） 连接到的 SQL 数据库时指定的配置设置[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
## <a name="specifying-the-binding-and-endpoint-address-in-code"></a>在代码中指定的绑定和终结点地址  
 下面的代码演示如何通过使用在代码中指定的绑定和终结点地址创建 WCF 客户端**ClientCredentials**的 WCF 客户端的属性。  
  
```  
SqlAdapterBinding binding = new SqlAdapterBinding();  
EndpointAddress sqlAddress = new EndpointAddress("mssql://<sql_server_name>//<database_name>?");  
  
TableOp_dbo_CustomerClient client = new TableOp_dbo_CustomerClient (binding, sqlAddress);  
  
client.ClientCredentials.UserName.UserName = "USER";  
client.ClientCredentials.UserName.Password = "PASSWORD";  
  
client.Open();  
```  
  
## <a name="specifying-the-binding-and-endpoint-address-in-a-configuration-file"></a>在配置文件中指定的绑定和终结点地址  
 下面的代码演示如何通过 app.config 文件中指定的绑定和终结点地址创建 WCF 客户端。  
  
```  
TableOp_dbo_CustomerClient client = new TableOp_dbo_CustomerClient("SqlAdapterBinding_TableOp_dbo_Customer");  
  
client.ClientCredentials.UserName.UserName = "USER";  
client.ClientCredentials.UserName.Password = "PASSWORD";  
  
client.Open();  
```  
  
 下面的 XML 演示通过客户表所创建的配置文件[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 此文件包含在前面的示例中引用的客户端终结点配置。  
  
```  
\<?xml version="1.0" encoding="utf-8"?>  
<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">  
    \<system.serviceModel>  
        <bindings>  
            <sqlBinding>  
                <binding name="SqlAdapterBinding" closeTimeout="00:01:00" openTimeout="00:01:00"  
                    receiveTimeout="00:10:00" sendTimeout="00:01:00" maxConnectionPoolSize="100"  
                    encrypt="false" useAmbientTransaction="true" batchSize="20"  
                    polledDataAvailableStatement="" pollingStatement="" pollingIntervalInSeconds="30"  
                    pollWhileDataFound="false" notificationStatement="" notifyOnListenerStart="true"  
                    enableBizTalkCompatibilityMode="true" chunkSize="4194304"  
                    inboundOperationType="Polling" useDatabaseNameInXsdNamespace="false"  
                    allowIdentityInsert="false" enablePerformanceCounters="false"  
                    xmlStoredProcedureRootNodeName="" xmlStoredProcedureRootNodeNamespace="" />  
            </sqlBinding>  
        </bindings>  
        <client>  
            <endpoint address="mssql://<sql_server_name>//<database_name>?" binding="sqlBinding"  
                bindingConfiguration="SqlAdapterBinding" contract="TableOp_dbo_Customer"  
                name="SqlAdapterBinding_TableOp_dbo_Customer" />  
        </client>  
    \</system.serviceModel>  
</configuration>  
```  
  
 如果一个项目具有多个 WCF 客户端，将有多个客户端配置文件中定义的终结点条目。 WCF 客户端的每个条目将具有唯一的名称基于它的绑定配置和目标 SQL Server 项目;例如，"`SqlAdapterBinding_TableOp_dbo_Customer`"。 如果你连接多个项目中创建 WCF 客户端的时机，多个绑定配置条目将创建，一个用于每个连接。 这些绑定配置条目将被命名为按以下方式： SqlAdapterBinding、 SqlAdapterBinding1，依次类推。 在特定的连接过程中创建的每个客户端终结点条目将引用在该连接过程中创建的绑定项。  
  
## <a name="see-also"></a>另请参阅  
[开发 SQL 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)   
 [为 SQL Server 项目生成 WCF 客户端或 WCF 服务协定](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)   
[创建 SQL Server 连接 URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)