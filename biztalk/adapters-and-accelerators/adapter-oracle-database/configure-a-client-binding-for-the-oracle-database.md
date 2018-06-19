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
# <a name="configure-a-client-binding-for-the-oracle-database"></a><span data-ttu-id="b3d01-102">配置客户端绑定用于 Oracle 数据库</span><span class="sxs-lookup"><span data-stu-id="b3d01-102">Configure a client binding for the Oracle Database</span></span>
<span data-ttu-id="b3d01-103">在你生成 WCF 客户端类后，可以创建一个 WCF 客户端 （实例） 并调用其方法来使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b3d01-103">After you have generated the WCF client class, you can create a WCF client (instance) and invoke its methods to consume the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="b3d01-104">有关如何生成操作的 WCF 客户端类和帮助程序代码，[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]公开，请参阅[为 Oracle 数据库解决方案项目生成 WCF 客户端或 WCF 服务约定](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="b3d01-104">For information about how to generate the WCF client class and helper code for operations that the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] exposes, see [Generate a WCF Client or a WCF Service Contract for Oracle Database Solution Artifacts](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md).</span></span>  
  
 <span data-ttu-id="b3d01-105">若要创建 WCF 客户端，必须指定终结点地址和绑定。</span><span class="sxs-lookup"><span data-stu-id="b3d01-105">To create the WCF client, you must specify an endpoint address and a binding.</span></span> <span data-ttu-id="b3d01-106">终结点地址必须包含有效的 Oracle 连接 URI，并且绑定必须 Oracle DB 绑定的一个实例 (**OracleDBBinding**)。</span><span class="sxs-lookup"><span data-stu-id="b3d01-106">The endpoint address must contain a valid Oracle connection URI, and the binding must be an instance of an Oracle DB Binding (**OracleDBBinding**).</span></span> <span data-ttu-id="b3d01-107">有关 Oracle 连接 URI 的详细信息，请参阅[创建 Oracle 数据库连接 URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="b3d01-107">For more information about the Oracle connection URI, see [Create the Oracle Database Connection URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md).</span></span> <span data-ttu-id="b3d01-108">我们建议你不要连接 URI 的一部分指定的用户凭据。</span><span class="sxs-lookup"><span data-stu-id="b3d01-108">We recommend that you do not specify the user credentials as part of the connection URI.</span></span> <span data-ttu-id="b3d01-109">而改用**ClientCredentials**的 WCF 客户端，如本主题中所述的属性。</span><span class="sxs-lookup"><span data-stu-id="b3d01-109">You may instead use the **ClientCredentials** property of the WCF client, as explained in this topic.</span></span>  
  
 <span data-ttu-id="b3d01-110">在你的代码或配置文件中，可以指定 Oracle DB 绑定和终结点地址。</span><span class="sxs-lookup"><span data-stu-id="b3d01-110">You can specify the Oracle DB Binding and the endpoint address in your code or in a configuration file.</span></span> <span data-ttu-id="b3d01-111">当你使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]若要生成 WCF 客户端类，创建配置文件 (app.config) 还为你的项目。</span><span class="sxs-lookup"><span data-stu-id="b3d01-111">When you use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] to generate the WCF client class, a configuration file (app.config) is also created for your project.</span></span> <span data-ttu-id="b3d01-112">此文件包含反映的绑定属性和连接信息 （除凭据） 连接到 Oracle 数据库时指定的配置设置[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b3d01-112">This file contains configuration settings that reflect the binding properties and connection information (except credentials) that you specified when you connected to the Oracle database with the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
## <a name="specifying-the-binding-and-endpoint-address-in-code"></a><span data-ttu-id="b3d01-113">在代码中指定的绑定和终结点地址</span><span class="sxs-lookup"><span data-stu-id="b3d01-113">Specifying the Binding and Endpoint Address in Code</span></span>  
 <span data-ttu-id="b3d01-114">下面的代码演示如何通过在代码中指定的绑定和终结点地址创建 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="b3d01-114">The following code shows how to create a WCF client by specifying the binding and endpoint address in code.</span></span> <span data-ttu-id="b3d01-115">它是通过使用指定的 Oracle 凭据的好办法**ClientCredentials**的 WCF 客户端而不是连接的终结点地址为提供的 URI 中的属性。</span><span class="sxs-lookup"><span data-stu-id="b3d01-115">It is good practice to specify the Oracle credentials by using the **ClientCredentials** property of the WCF client rather than in the connection URI supplied for the endpoint address.</span></span>  
  
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
  
## <a name="specifying-the-binding-and-endpoint-address-in-a-configuration-file"></a><span data-ttu-id="b3d01-116">在配置文件中指定的绑定和终结点地址</span><span class="sxs-lookup"><span data-stu-id="b3d01-116">Specifying the Binding and Endpoint Address in a Configuration File</span></span>  
 <span data-ttu-id="b3d01-117">下面的代码演示如何通过 app.config 文件中指定的绑定和终结点地址创建 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="b3d01-117">The following code shows how to create a WCF client by specifying the binding and endpoint address in an app.config file.</span></span>  
  
```  
// A WCF client that targets the /SCOTT/EMP table is created  
// by specifying the client endpoint information in app.config  
SCOTTTableEMPClient empClient = new SCOTTTableEMPClient("OracleDBBinding_SCOTT.Table.EMP");  
  
empClient.ClientCredentials.UserName.UserName = "SCOTT";  
empClient.ClientCredentials.UserName.Password = "TIGER";  
  
empClient.Open();  
```  
  
 <span data-ttu-id="b3d01-118">下面的 XML 演示通过 EMP 表所创建的配置文件[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b3d01-118">The following XML shows the configuration file created for the EMP table by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="b3d01-119">此文件包含在前面的示例中引用的客户端终结点配置。</span><span class="sxs-lookup"><span data-stu-id="b3d01-119">This file contains the client endpoint configuration referenced in the preceding example.</span></span>  
  
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
  
 <span data-ttu-id="b3d01-120">如果一个项目具有多个 WCF 客户端，将有多个客户端配置文件中定义的终结点条目。</span><span class="sxs-lookup"><span data-stu-id="b3d01-120">If a project has more than one WCF client, there will be multiple client endpoint entries defined in the configuration file.</span></span> <span data-ttu-id="b3d01-121">WCF 客户端的每个条目将具有唯一的名称基于它的绑定配置和目标 Oracle 数据库项目;例如，"OracleDBBinding_SCOTT。Table.EMP"。</span><span class="sxs-lookup"><span data-stu-id="b3d01-121">Each WCF client entry will have a unique name based on its binding configuration and target Oracle database artifact; for example, "OracleDBBinding_SCOTT.Table.EMP".</span></span> <span data-ttu-id="b3d01-122">如果你连接多个项目中创建 WCF 客户端的时机，多个绑定配置条目将创建，一个用于每个连接。</span><span class="sxs-lookup"><span data-stu-id="b3d01-122">If you connect multiple times to create the WCF clients in your project, multiple binding configuration entries will be created, one for each connection.</span></span> <span data-ttu-id="b3d01-123">这些绑定配置条目将被命名为按以下方式： OracleDBBinding1、 OracleDBBinding2，依次类推。</span><span class="sxs-lookup"><span data-stu-id="b3d01-123">These binding configuration entries will be named in the following manner: OracleDBBinding1, OracleDBBinding2, and so on.</span></span> <span data-ttu-id="b3d01-124">在特定的连接过程中创建的每个客户端终结点条目将引用在该连接过程中创建的绑定项。</span><span class="sxs-lookup"><span data-stu-id="b3d01-124">Each client endpoint entry created during a specific connection will reference the binding entry created during that connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3d01-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b3d01-125">See Also</span></span>  
 <span data-ttu-id="b3d01-126">[通过使用 WCF 服务模型开发 Oracle 数据库应用程序](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md) </span><span class="sxs-lookup"><span data-stu-id="b3d01-126">[Develop Oracle Database Applications by Using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md) </span></span>  
 <span data-ttu-id="b3d01-127">[为 Oracle 数据库解决方案项目生成 WCF 客户端或 WCF 服务协定](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md) </span><span class="sxs-lookup"><span data-stu-id="b3d01-127">[Generate a WCF Client or a WCF Service Contract for Oracle Database Solution Artifacts](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md) </span></span>  
 <span data-ttu-id="b3d01-128">[创建 Oracle 数据库连接 URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md) </span><span class="sxs-lookup"><span data-stu-id="b3d01-128">[Create the Oracle Database Connection URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md) </span></span>  
 [<span data-ttu-id="b3d01-129">通过使用 WCF 通道模型开发 Oracle 数据库应用程序</span><span class="sxs-lookup"><span data-stu-id="b3d01-129">Develop Oracle Database Applications by Using the WCF Channel Model</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-channel-model.md)