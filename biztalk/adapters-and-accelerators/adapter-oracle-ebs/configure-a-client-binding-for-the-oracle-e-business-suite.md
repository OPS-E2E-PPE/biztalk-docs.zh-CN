---
title: "配置客户端绑定 Oracle E-business Suite |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1347cbca-5567-43f8-a75e-a23b108692bc
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dadf91973bdee181050f420ed611eb0c502fc988
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configure-a-client-binding-for-the-oracle-e-business-suite"></a><span data-ttu-id="8552b-102">配置客户端绑定 Oracle E-business Suite</span><span class="sxs-lookup"><span data-stu-id="8552b-102">Configure a client binding for the Oracle E-Business Suite</span></span>
<span data-ttu-id="8552b-103">在你生成 WCF 客户端类后，可以创建一个 WCF 客户端 （实例） 并调用其方法来使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8552b-103">After you have generated the WCF client class, you can create a WCF client (instance) and invoke its methods to consume the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
 <span data-ttu-id="8552b-104">若要创建 WCF 客户端，必须指定终结点地址和绑定。</span><span class="sxs-lookup"><span data-stu-id="8552b-104">To create the WCF client, you must specify an endpoint address and a binding.</span></span> <span data-ttu-id="8552b-105">终结点地址必须包含有效的 Oracle E-business Suite 连接 URI，并且绑定必须 Oracle E-business Suite 绑定的一个实例 (**OracleEBSBinding**)。</span><span class="sxs-lookup"><span data-stu-id="8552b-105">The endpoint address must contain a valid Oracle E-Business Suite connection URI, and the binding must be an instance of an Oracle E-Business Suite binding (**OracleEBSBinding**).</span></span> <span data-ttu-id="8552b-106">有关 Oracle E-business Suite 连接 URI 的详细信息，请参阅[创建与 Oracle E-business Suite 的连接](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-connection-to-oracle-e-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="8552b-106">For more information about the Oracle E-Business Suite connection URI, see [Create a Connection to the Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/create-a-connection-to-oracle-e-business-suite.md).</span></span> <span data-ttu-id="8552b-107">我们建议你不要连接 URI 的一部分指定的用户凭据。</span><span class="sxs-lookup"><span data-stu-id="8552b-107">We recommend that you do not specify the user credentials as part of the connection URI.</span></span> <span data-ttu-id="8552b-108">而改用**ClientCredentials**的 WCF 客户端，如本主题中所述的属性。</span><span class="sxs-lookup"><span data-stu-id="8552b-108">You may instead use the **ClientCredentials** property of the WCF client, as explained in this topic.</span></span>  
  
 <span data-ttu-id="8552b-109">在你的代码或配置文件中，可以指定 Oracle E-business Suite 绑定和终结点地址。</span><span class="sxs-lookup"><span data-stu-id="8552b-109">You can specify the Oracle E-Business Suite binding and the endpoint address in your code or in a configuration file.</span></span> <span data-ttu-id="8552b-110">当你使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]若要生成 WCF 客户端类，创建配置文件 (app.config) 还为你的项目。</span><span class="sxs-lookup"><span data-stu-id="8552b-110">When you use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] to generate the WCF client class, a configuration file (app.config) is also created for your project.</span></span> <span data-ttu-id="8552b-111">此文件包含反映的绑定属性和连接信息 （除凭据） 时连接到 Oracle E-business Suite 与指定的配置设置[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8552b-111">This file contains configuration settings that reflect the binding properties and connection information (except credentials) that you specified when you connected to the Oracle E-Business Suite with the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
## <a name="specifying-the-binding-and-endpoint-address-in-code"></a><span data-ttu-id="8552b-112">在代码中指定的绑定和终结点地址</span><span class="sxs-lookup"><span data-stu-id="8552b-112">Specifying the Binding and Endpoint Address in Code</span></span>  
 <span data-ttu-id="8552b-113">下面的代码演示如何通过在代码中使用指定的绑定和终结点地址创建 WCF 客户端**ClientCredentials**的 WCF 客户端的属性。</span><span class="sxs-lookup"><span data-stu-id="8552b-113">The following code shows how to create a WCF client by specifying the binding and endpoint address in code using the **ClientCredentials** property of the WCF client.</span></span>  
  
```  
//Create an Oracle EBS binding and set the binding properties  
OracleEBSBinding binding = new OracleEBSBinding();  
binding.OracleUserName = "myOracleEBSUser";  
binding.OraclePassword = "myOracleEBSPassword";  
binding.OracleEBSResponsibilityName = "Responsibility";  
binding.OracleEBSOrganizationId = "204";  
  
//Create the client endpoint   
EndpointAddress address = new EndpointAddress("oracleebs://<oracleebs_instance_name>/");  
  
//Create the client and specify the credentials  
ConcurrentPrograms_ARClient client = new ConcurrentPrograms_ARClient(binding,address);  
client.ClientCredentials.UserName.UserName = "myuser";  
client.ClientCredentials.UserName.Password = "mypassword";  
  
//Open the client  
client.Open();  
```  
  
## <a name="specifying-the-binding-and-endpoint-address-in-a-configuration-file"></a><span data-ttu-id="8552b-114">在配置文件中指定的绑定和终结点地址</span><span class="sxs-lookup"><span data-stu-id="8552b-114">Specifying the Binding and Endpoint Address in a Configuration File</span></span>  
 <span data-ttu-id="8552b-115">下面的代码演示如何通过 app.config 文件中指定的绑定和终结点地址创建 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="8552b-115">The following code shows how to create a WCF client by specifying the binding and endpoint address in an app.config file.</span></span>  
  
```  
//Create the client by specifying the endpoint name in the app.config. In this case, the binding properties  
//must also be specified in the app.config.  
ConcurrentPrograms_ARClient client = new ConcurrentPrograms_ARClient("OracleEBSBinding_ConcurrentPrograms_AR");  
  
//Specify the credentials   
client.ClientCredentials.UserName.UserName = "myuser";  
client.ClientCredentials.UserName.Password = "mypassword";  
  
client.Open();  
```  
  
 <span data-ttu-id="8552b-116">下面的 XML 显示了为创建的配置文件**客户接口**通过并发程序[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8552b-116">The following XML shows the configuration file created for the **Customer Interface** concurrent program by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="8552b-117">此文件包含在前面的示例中引用的客户端终结点配置。</span><span class="sxs-lookup"><span data-stu-id="8552b-117">This file contains the client endpoint configuration referenced in the preceding example.</span></span>  
  
```  
\<?xml version="1.0" encoding="utf-8"?>  
<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">  
    \<system.serviceModel>  
        <bindings>  
            <oracleEBSBinding>  
                <binding openTimeout="00:05:00" name="OracleEBSBinding" closeTimeout="00:01:00"  
                    receiveTimeout="00:10:00" sendTimeout="00:01:00" clientCredentialType="Database"  
                    inboundOperationType="Polling" metadataPooling="true" statementCachePurge="false"  
                    statementCacheSize="10" pollWhileDataFound="false" pollingInterval="30"  
                    useOracleConnectionPool="true" minPoolSize="1" maxPoolSize="100"  
                    incrPoolSize="5" decrPoolSize="1" connectionLifetime="0" acceptCredentialsInUri="false"  
                    useAmbientTransaction="true" notifyOnListenerStart="true"  
                    notificationPort="-1" dataFetchSize="65536" longDatatypeColumnSize="32512"  
                    skipNilNodes="true" maxOutputAssociativeArrayElements="32"  
                    enableSafeTyping="false" insertBatchSize="20" useSchemaInNameSpace="true"  
                    enableBizTalkCompatibilityMode="true">  
                    <mlsSettings language="" dateFormat="" dateLanguage="" numericCharacters=""  
                        sort="" territory="" comparison="" currency="" dualCurrency=""  
                        iSOCurrency="" calendar="" lengthSemantics="" nCharConversionException="true"  
                        timeStampFormat="" timeStampTZFormat="" timeZone="" />  
                </binding>  
            </oracleEBSBinding>  
        </bindings>  
        <client>  
            <endpoint address="oracleebs://ebs-70-12/" binding="oracleEBSBinding"  
                bindingConfiguration="OracleEBSBinding" contract="ConcurrentPrograms_AR"  
                name="OracleEBSBinding_ConcurrentPrograms_AR" />  
        </client>  
    \</system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="8552b-118">如果一个项目具有多个 WCF 客户端，将有多个客户端配置文件中定义的终结点条目。</span><span class="sxs-lookup"><span data-stu-id="8552b-118">If a project has more than one WCF client, there will be multiple client endpoint entries defined in the configuration file.</span></span> <span data-ttu-id="8552b-119">每个 WCF 客户端条目将具有基于其绑定配置和目标 Oracle E-business Suite 项目的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="8552b-119">Each WCF client entry will have a unique name based on its binding configuration and target Oracle E-Business Suite artifact.</span></span> <span data-ttu-id="8552b-120">如果你连接多个项目中创建 WCF 客户端的时机，多个绑定配置条目将创建，一个用于每个连接。</span><span class="sxs-lookup"><span data-stu-id="8552b-120">If you connect multiple times to create the WCF clients in your project, multiple binding configuration entries will be created, one for each connection.</span></span> <span data-ttu-id="8552b-121">这些绑定配置条目将被命名为按以下方式： OracleEBSBinding、 OracleEBSBinding1，依次类推。</span><span class="sxs-lookup"><span data-stu-id="8552b-121">These binding configuration entries will be named in the following manner: OracleEBSBinding, OracleEBSBinding1, and so on.</span></span> <span data-ttu-id="8552b-122">在特定的连接过程中创建的每个客户端终结点条目将引用在该连接过程中创建的绑定项。</span><span class="sxs-lookup"><span data-stu-id="8552b-122">Each client endpoint entry created during a specific connection will reference the binding entry created during that connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8552b-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8552b-123">See Also</span></span>  
 [<span data-ttu-id="8552b-124">开发 Oracle E-business Suite 应用程序使用 WCF 服务模型</span><span class="sxs-lookup"><span data-stu-id="8552b-124">Develop Oracle E-Business Suite Applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-oracle-e-business-suite-applications-using-the-wcf-service-model.md)