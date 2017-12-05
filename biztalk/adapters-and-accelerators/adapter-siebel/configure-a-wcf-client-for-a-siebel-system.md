---
title: "配置 Siebel 系统的 WCF 客户端 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- how to, create a WCF client by specifying binding and endpoint address in a configuration file
- how to, create a WCF client by specifying binding and endpoint address in code
- WCF service model, configuring a WCF client for a Siebel system
ms.assetid: 6b4c5b06-d5ff-4dbf-8dc2-89c547a59864
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04d122c3300f3c1e52194a10332fbb7fb6c45d81
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="configure-a-wcf-client-for-a-siebel-system"></a><span data-ttu-id="697b9-102">配置 Siebel 系统的 WCF 客户端</span><span class="sxs-lookup"><span data-stu-id="697b9-102">Configure a WCF Client for a Siebel System</span></span>
<span data-ttu-id="697b9-103">在你生成 WCF 客户端类后，可以创建一个 WCF 客户端 （实例） 并调用其方法来使用[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="697b9-103">After you have generated the WCF client class, you can create a WCF client (instance) and invoke its methods to consume the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="697b9-104">有关如何生成操作的 WCF 客户端类和帮助程序代码，[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]公开，请参阅[生成 WCF 客户端或 WCF 服务协定 Siebel 解决方案项目](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="697b9-104">For information about how to generate the WCF client class and helper code for operations that the [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] exposes, see [Generate a WCF Client or a WCF service contract for Siebel solution Artifacts](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md).</span></span>  
  
 <span data-ttu-id="697b9-105">若要创建 WCF 客户端，必须指定终结点地址和绑定。</span><span class="sxs-lookup"><span data-stu-id="697b9-105">To create the WCF client, you must specify an endpoint address and a binding.</span></span> <span data-ttu-id="697b9-106">终结点地址必须包含有效的 Siebel 连接 URI，并且绑定必须 Siebel 绑定的一个实例 (**SiebelBinding**)。</span><span class="sxs-lookup"><span data-stu-id="697b9-106">The endpoint address must contain a valid Siebel connection URI, and the binding must be an instance of a Siebel Binding (**SiebelBinding**).</span></span> <span data-ttu-id="697b9-107">有关 Siebel 连接 URI 的详细信息，请参阅[连接到 Visual Studio 中的 Siebel 系统](../../adapters-and-accelerators/adapter-siebel/connect-to-the-siebel-system-in-visual-studio.md)。</span><span class="sxs-lookup"><span data-stu-id="697b9-107">For more information about the Siebel connection URI, see [Connect to the Siebel System in Visual Studio](../../adapters-and-accelerators/adapter-siebel/connect-to-the-siebel-system-in-visual-studio.md).</span></span>  
  
 <span data-ttu-id="697b9-108">在你的代码或配置文件中，可以指定 Siebel 绑定和终结点地址。</span><span class="sxs-lookup"><span data-stu-id="697b9-108">You can specify the Siebel Binding and the endpoint address in your code or in a configuration file.</span></span> <span data-ttu-id="697b9-109">当你使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]若要生成 WCF 客户端类，创建配置文件 (app.config) 还为你的项目。</span><span class="sxs-lookup"><span data-stu-id="697b9-109">When you use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] to generate the WCF client class, a configuration file (app.config) is also created for your project.</span></span> <span data-ttu-id="697b9-110">此文件包含反映的绑定属性和连接信息 （除凭据） 时连接到 Siebel 系统与指定的配置设置[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="697b9-110">This file contains configuration settings that reflect the binding properties and connection information (except credentials) that you specified when you connected to the Siebel system with the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
## <a name="specifying-the-binding-and-endpoint-address-in-code"></a><span data-ttu-id="697b9-111">在代码中指定的绑定和终结点地址</span><span class="sxs-lookup"><span data-stu-id="697b9-111">Specifying the Binding and Endpoint Address in Code</span></span>  
 <span data-ttu-id="697b9-112">下面的代码演示如何通过在代码中指定的绑定和终结点地址创建 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="697b9-112">The following code shows how to create a WCF client by specifying the binding and endpoint address in code.</span></span> <span data-ttu-id="697b9-113">很好的做法，可通过使用指定的 Siebel 凭据**ClientCredentials**的 WCF 客户端而不是连接的终结点地址为提供的 URI 中的属性。</span><span class="sxs-lookup"><span data-stu-id="697b9-113">It is good practice to specify the Siebel credentials by using the **ClientCredentials** property of the WCF client rather than in the connection URI supplied for the endpoint address.</span></span>  
  
```  
// A WCF client that targets the TimeStamp business service is created  
// by using a binding object and endpoint address  
SiebelBinding sblBinding = new SiebelBinding();  
EndpointAddress sblAddress = new EndpointAddress("siebel://Siebel_server:1234?SiebelObjectManager=obj_mgr&SiebelEnterpriseServer=ent_server&Language=enu");  
  
BusinessServices_TimeStamp_OperationClient client =   
    new BusinessServices_TimeStamp_OperationClient(sblBinding, sblAddress);  
  
    client.ClientCredentials.UserName.UserName = "SADMIN";  
    client.ClientCredentials.UserName.Password = "SADMIN";  
  
    client.Open();  
```  
  
## <a name="specifying-the-binding-and-endpoint-address-in-a-configuration-file"></a><span data-ttu-id="697b9-114">在配置文件中指定的绑定和终结点地址</span><span class="sxs-lookup"><span data-stu-id="697b9-114">Specifying the Binding and Endpoint Address in a Configuration File</span></span>  
 <span data-ttu-id="697b9-115">下面的代码演示如何通过 app.config 文件中指定的绑定和终结点地址创建 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="697b9-115">The following code shows how to create a WCF client by specifying the binding and endpoint address in an app.config file.</span></span>  
  
```  
// A WCF client that targets the TimeStamp business service is created  
// by specifying the client endpoint information in app.config  
BusinessServices_TimeStamp_OperationClient client =   
    new BusinessServices_TimeStamp_OperationClient("SiebelBinding_BusinessServices_TimeStamp_Operation");  
  
client.ClientCredentials.UserName.UserName = "SADMIN";  
client.ClientCredentials.UserName.Password = "SADMIN";  
  
client.Open();  
```  
  
### <a name="the-appconfig-file"></a><span data-ttu-id="697b9-116">App.config 文件</span><span class="sxs-lookup"><span data-stu-id="697b9-116">The App.config File</span></span>  
 <span data-ttu-id="697b9-117">下面的 XML 演示创建由时间戳业务服务的配置文件[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="697b9-117">The following XML shows the configuration file created for the TimeStamp business service by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="697b9-118">此文件包含在前面的示例中引用的客户端终结点配置。</span><span class="sxs-lookup"><span data-stu-id="697b9-118">This file contains the client endpoint configuration referenced in the preceding example.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">  
    <system.serviceModel>  
        <bindings>  
            <siebelBinding>  
                <binding name="SiebelBinding" closeTimeout="00:01:00" openTimeout="00:01:00"  
                    receiveTimeout="00:10:00" sendTimeout="00:01:00" enableBizTalkCompatibilityMode="false"  
                    enablePerformanceCounters="false" enableConnectionPooling="true"  
                    maxConnectionsPerSystem="5" idleConnectionTimeout="00:01:00"  
                    acceptCredentialsInUri="false" />  
            </siebelBinding>  
        </bindings>  
        <client>  
            <endpoint address="siebel://Siebel_server:1234?SiebelObjectManager=obj_mgr&SiebelEnterpriseServer=ent_server&Language=enu"  
                binding="siebelBinding" bindingConfiguration="SiebelBinding"  
                contract="BusinessServices_TimeStamp_Operation" name="SiebelBinding_BusinessServices_TimeStamp_Operation" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="697b9-119">如果一个项目具有多个 WCF 客户端，将有多个客户端配置文件中定义的终结点条目。</span><span class="sxs-lookup"><span data-stu-id="697b9-119">If a project has more than one WCF client, there will be multiple client endpoint entries defined in the configuration file.</span></span> <span data-ttu-id="697b9-120">WCF 客户端的每个条目将具有唯一的名称基于它的绑定配置和目标 Siebel 项目;例如，"SiebelBinding_BusinessServices_TimeStamp_Operation"。</span><span class="sxs-lookup"><span data-stu-id="697b9-120">Each WCF client entry will have a unique name based on its binding configuration and target Siebel artifact; for example, " SiebelBinding_BusinessServices_TimeStamp_Operation ".</span></span> <span data-ttu-id="697b9-121">如果你连接多个项目中创建 WCF 客户端的时机，多个绑定配置条目将创建，一个用于每个连接。</span><span class="sxs-lookup"><span data-stu-id="697b9-121">If you connect multiple times to create the WCF clients in your project, multiple binding configuration entries will be created, one for each connection.</span></span> <span data-ttu-id="697b9-122">这些绑定配置条目将被命名为按以下方式： SiebelBinding、 SiebelBinding1、 SiebelBinding2，依次类推。</span><span class="sxs-lookup"><span data-stu-id="697b9-122">These binding configuration entries will be named in the following manner: SiebelBinding, SiebelBinding1, SiebelBinding2, and so on.</span></span> <span data-ttu-id="697b9-123">在特定的连接过程中创建的每个客户端终结点条目将引用在该连接过程中创建的绑定项。</span><span class="sxs-lookup"><span data-stu-id="697b9-123">Each client endpoint entry created during a specific connection will reference the binding entry created during that connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="697b9-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="697b9-124">See Also</span></span>  
 [<span data-ttu-id="697b9-125">开发 Siebel 应用程序使用 WCF 服务模型</span><span class="sxs-lookup"><span data-stu-id="697b9-125">Develop Siebel Applications using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md)