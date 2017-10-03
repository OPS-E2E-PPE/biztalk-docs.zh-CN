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
# <a name="configure-a-client-binding-for-the-sql-adapter"></a><span data-ttu-id="f2b9e-102">为该 SQL 适配器配置客户端绑定</span><span class="sxs-lookup"><span data-stu-id="f2b9e-102">Configure a Client Binding for the SQL Adapter</span></span>
<span data-ttu-id="f2b9e-103">在你生成 WCF 客户端类后，可以创建一个 WCF 客户端 （实例） 并调用其方法来使用[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f2b9e-103">After you have generated the WCF client class, you can create a WCF client (instance) and invoke its methods to consume the [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)].</span></span> <span data-ttu-id="f2b9e-104">有关如何生成操作的 WCF 客户端类和帮助程序代码，[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]公开，请参阅[为 SQL Server 项目生成 WCF 客户端或 WCF 服务协定](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="f2b9e-104">For information about how to generate the WCF client class and helper code for operations that the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] exposes, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  
  
 <span data-ttu-id="f2b9e-105">若要创建 WCF 客户端，必须指定终结点地址和绑定。</span><span class="sxs-lookup"><span data-stu-id="f2b9e-105">To create the WCF client, you must specify an endpoint address and a binding.</span></span> <span data-ttu-id="f2b9e-106">终结点地址必须包含有效的 SQL 连接 URI，并且绑定必须是 SQL 绑定的一个实例 (**sqlBinding**)。</span><span class="sxs-lookup"><span data-stu-id="f2b9e-106">The endpoint address must contain a valid SQL connection URI, and the binding must be an instance of a SQL Binding (**sqlBinding**).</span></span> <span data-ttu-id="f2b9e-107">有关 SQL 连接 URI 的详细信息，请参阅[创建 SQL Server 连接 URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="f2b9e-107">For more information about the SQL connection URI, see [Create the SQL Server connection URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).</span></span> <span data-ttu-id="f2b9e-108">作为连接 URI 的一部分，必须指定的用户凭据。</span><span class="sxs-lookup"><span data-stu-id="f2b9e-108">You must specify the user credentials as part of the connection URI.</span></span> <span data-ttu-id="f2b9e-109">你可以使用**ClientCredentials**的 WCF 客户端，如本主题中所述的属性。</span><span class="sxs-lookup"><span data-stu-id="f2b9e-109">You may use the **ClientCredentials** property of the WCF client, as explained in this topic.</span></span>  
  
 <span data-ttu-id="f2b9e-110">在你的代码或配置文件中，可以指定 SQL 绑定和终结点地址。</span><span class="sxs-lookup"><span data-stu-id="f2b9e-110">You can specify the SQL binding and the endpoint address in your code or in a configuration file.</span></span> <span data-ttu-id="f2b9e-111">当你使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]若要生成 WCF 客户端类，创建配置文件 (app.config) 还为你的项目。</span><span class="sxs-lookup"><span data-stu-id="f2b9e-111">When you use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] to generate the WCF client class, a configuration file (app.config) is also created for your project.</span></span> <span data-ttu-id="f2b9e-112">此文件包含反映的绑定属性和连接信息 （除凭据） 连接到的 SQL 数据库时指定的配置设置[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f2b9e-112">This file contains configuration settings that reflect the binding properties and connection information (except credentials) that you specified when you connected to the SQL database with the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
## <a name="specifying-the-binding-and-endpoint-address-in-code"></a><span data-ttu-id="f2b9e-113">在代码中指定的绑定和终结点地址</span><span class="sxs-lookup"><span data-stu-id="f2b9e-113">Specifying the Binding and Endpoint Address in Code</span></span>  
 <span data-ttu-id="f2b9e-114">下面的代码演示如何通过使用在代码中指定的绑定和终结点地址创建 WCF 客户端**ClientCredentials**的 WCF 客户端的属性。</span><span class="sxs-lookup"><span data-stu-id="f2b9e-114">The following code shows how to create a WCF client by specifying the binding and endpoint address in code by using the **ClientCredentials** property of the WCF client.</span></span>  
  
```  
SqlAdapterBinding binding = new SqlAdapterBinding();  
EndpointAddress sqlAddress = new EndpointAddress("mssql://<sql_server_name>//<database_name>?");  
  
TableOp_dbo_CustomerClient client = new TableOp_dbo_CustomerClient (binding, sqlAddress);  
  
client.ClientCredentials.UserName.UserName = "USER";  
client.ClientCredentials.UserName.Password = "PASSWORD";  
  
client.Open();  
```  
  
## <a name="specifying-the-binding-and-endpoint-address-in-a-configuration-file"></a><span data-ttu-id="f2b9e-115">在配置文件中指定的绑定和终结点地址</span><span class="sxs-lookup"><span data-stu-id="f2b9e-115">Specifying the Binding and Endpoint Address in a Configuration File</span></span>  
 <span data-ttu-id="f2b9e-116">下面的代码演示如何通过 app.config 文件中指定的绑定和终结点地址创建 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="f2b9e-116">The following code shows how to create a WCF client by specifying the binding and endpoint address in an app.config file.</span></span>  
  
```  
TableOp_dbo_CustomerClient client = new TableOp_dbo_CustomerClient("SqlAdapterBinding_TableOp_dbo_Customer");  
  
client.ClientCredentials.UserName.UserName = "USER";  
client.ClientCredentials.UserName.Password = "PASSWORD";  
  
client.Open();  
```  
  
 <span data-ttu-id="f2b9e-117">下面的 XML 演示通过客户表所创建的配置文件[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f2b9e-117">The following XML shows the configuration file created for the Customer table by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="f2b9e-118">此文件包含在前面的示例中引用的客户端终结点配置。</span><span class="sxs-lookup"><span data-stu-id="f2b9e-118">This file contains the client endpoint configuration referenced in the preceding example.</span></span>  
  
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
  
 <span data-ttu-id="f2b9e-119">如果一个项目具有多个 WCF 客户端，将有多个客户端配置文件中定义的终结点条目。</span><span class="sxs-lookup"><span data-stu-id="f2b9e-119">If a project has more than one WCF client, there will be multiple client endpoint entries defined in the configuration file.</span></span> <span data-ttu-id="f2b9e-120">WCF 客户端的每个条目将具有唯一的名称基于它的绑定配置和目标 SQL Server 项目;例如，"`SqlAdapterBinding_TableOp_dbo_Customer`"。</span><span class="sxs-lookup"><span data-stu-id="f2b9e-120">Each WCF client entry will have a unique name based on its binding configuration and target SQL Server artifact; for example, "`SqlAdapterBinding_TableOp_dbo_Customer`".</span></span> <span data-ttu-id="f2b9e-121">如果你连接多个项目中创建 WCF 客户端的时机，多个绑定配置条目将创建，一个用于每个连接。</span><span class="sxs-lookup"><span data-stu-id="f2b9e-121">If you connect multiple times to create the WCF clients in your project, multiple binding configuration entries will be created, one for each connection.</span></span> <span data-ttu-id="f2b9e-122">这些绑定配置条目将被命名为按以下方式： SqlAdapterBinding、 SqlAdapterBinding1，依次类推。</span><span class="sxs-lookup"><span data-stu-id="f2b9e-122">These binding configuration entries will be named in the following manner: SqlAdapterBinding, SqlAdapterBinding1, and so on.</span></span> <span data-ttu-id="f2b9e-123">在特定的连接过程中创建的每个客户端终结点条目将引用在该连接过程中创建的绑定项。</span><span class="sxs-lookup"><span data-stu-id="f2b9e-123">Each client endpoint entry created during a specific connection will reference the binding entry created during that connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2b9e-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f2b9e-124">See Also</span></span>  
<span data-ttu-id="f2b9e-125">[开发 SQL 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md) </span><span class="sxs-lookup"><span data-stu-id="f2b9e-125">[Develop SQL applications using the WCF Service model](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md) </span></span>  
 <span data-ttu-id="f2b9e-126">[为 SQL Server 项目生成 WCF 客户端或 WCF 服务协定](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md) </span><span class="sxs-lookup"><span data-stu-id="f2b9e-126">[Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md) </span></span>  
[<span data-ttu-id="f2b9e-127">创建 SQL Server 连接 URI</span><span class="sxs-lookup"><span data-stu-id="f2b9e-127">Create the SQL Server connection URI</span></span>](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)