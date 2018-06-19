---
title: 配置客户端绑定 SAP 系统 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- proxy programming, creating a proxy
- creating a proxy
- how to, create a proxy
ms.assetid: bceef132-29ff-4207-a37d-bf94fab484dd
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1e9a4f84dbf98a17b2c1a918e30ab85b8e86c13
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963851"
---
# <a name="configure-a-client-binding-for-the-sap-system"></a><span data-ttu-id="0684c-102">配置客户端绑定 SAP 系统</span><span class="sxs-lookup"><span data-stu-id="0684c-102">Configure a client binding for the SAP system</span></span>
<span data-ttu-id="0684c-103">在你生成 WCF 客户端类后，可以创建一个 WCF 客户端 （实例） 并调用其方法来使用[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0684c-103">After you have generated the WCF client class, you can create a WCF client (instance) and invoke its methods to consume the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)].</span></span> <span data-ttu-id="0684c-104">有关如何生成操作的 WCF 客户端类和帮助程序代码，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]公开，请参阅[生成 WCF 客户端或 SAP 解决方案项目关联的 WCF 服务协定](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="0684c-104">For information about how to generate the WCF client class and helper code for operations that the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] exposes, see [Generate a WCF client or a WCF service contract for SAP solution artifacts](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md).</span></span>  
  
 <span data-ttu-id="0684c-105">若要创建 WCF 客户端，必须指定终结点地址和绑定。</span><span class="sxs-lookup"><span data-stu-id="0684c-105">To create the WCF client, you must specify an endpoint address and a binding.</span></span> <span data-ttu-id="0684c-106">终结点地址必须包含有效的 SAP 连接 URI，并且绑定必须 SAP 绑定的一个实例 (**SAPBinding**)。</span><span class="sxs-lookup"><span data-stu-id="0684c-106">The endpoint address must contain a valid SAP connection URI, and the binding must be an instance of an SAP Binding (**SAPBinding**).</span></span> <span data-ttu-id="0684c-107">有关 SAP 连接 URI 的详细信息，请参阅[创建 SAP 系统连接 URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="0684c-107">For more information about the SAP connection URI, see [Create the SAP system connection URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md).</span></span>  
  
 <span data-ttu-id="0684c-108">在你的代码或配置文件中，可以指定 SAP 绑定和终结点地址。</span><span class="sxs-lookup"><span data-stu-id="0684c-108">You can specify the SAP Binding and the endpoint address in your code or in a configuration file.</span></span> <span data-ttu-id="0684c-109">当你使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]若要生成 WCF 客户端类，创建配置文件 (app.config) 还为你的项目。</span><span class="sxs-lookup"><span data-stu-id="0684c-109">When you use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] to generate the WCF client class, a configuration file (app.config) is also created for your project.</span></span> <span data-ttu-id="0684c-110">此文件包含反映的绑定属性和连接信息 （除凭据） 时连接到 SAP 系统，以及使用指定的配置设置[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0684c-110">This file contains configuration settings that reflect the binding properties and connection information (except credentials) that you specified when you connected to the SAP system with the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
## <a name="specifying-the-binding-and-endpoint-address-in-code"></a><span data-ttu-id="0684c-111">在代码中指定的绑定和终结点地址</span><span class="sxs-lookup"><span data-stu-id="0684c-111">Specifying the Binding and Endpoint Address in Code</span></span>  
 <span data-ttu-id="0684c-112">下面的代码演示如何通过在代码中指定的绑定和终结点地址创建 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="0684c-112">The following code shows how to create a WCF client by specifying the binding and endpoint address in code.</span></span> <span data-ttu-id="0684c-113">很好的做法，使用指定的 SAP 系统凭据**ClientCredentials**的 WCF 客户端而不是连接的终结点地址为提供的 URI 中的属性。</span><span class="sxs-lookup"><span data-stu-id="0684c-113">It is good practice to specify the SAP system credentials by using the **ClientCredentials** property of the WCF client rather than in the connection URI supplied for the endpoint address.</span></span>  
  
```  
// A WCF client that targets an RFC is created  
// by using a binding object and endpoint address  
SAPBinding sapBinding = new SAPBinding();  
EndpointAddress sapAddress = new EndpointAddress("sap://CLIENT=800;LANG=EN;@a/YourSAPHost/00");  
  
RfcClient rfcClient = new RfcClient(sapBinding, sapAddress);  
  
rfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
rfcClient.ClientCredentials.UserName.Password = "YourPassword";  
  
rfcClient.Open();  
```  
  
## <a name="specifying-the-binding-and-endpoint-address-in-a-configuration-file"></a><span data-ttu-id="0684c-114">在配置文件中指定的绑定和终结点地址</span><span class="sxs-lookup"><span data-stu-id="0684c-114">Specifying the Binding and Endpoint Address in a Configuration File</span></span>  
 <span data-ttu-id="0684c-115">下面的代码演示如何通过 app.config 文件中指定的绑定和终结点地址创建 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="0684c-115">The following code shows how to create a WCF client by specifying the binding and endpoint address in an app.config file.</span></span>  
  
```  
// A WCF client that targets an RFC is created  
// by specifying the client endpoint information in app.config  
RfcClient rfcClient = new RfcClient("SAPBinding_Rfc");  
  
rfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
rfcClient.ClientCredentials.UserName.Password = "YourPassword";  
  
rfcClient.Open();  
```  
  
 <span data-ttu-id="0684c-116">下面的 XML 演示通过 EMP 表所创建的配置文件[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0684c-116">The following XML shows the configuration file created for the EMP table by the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span> <span data-ttu-id="0684c-117">此文件包含在前面的示例中引用的客户端终结点配置。</span><span class="sxs-lookup"><span data-stu-id="0684c-117">This file contains the client endpoint configuration referenced in the preceding example.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<configuration xmlns="http://schemas.microsoft.com/.NetConfiguration/v2.0">  
    <system.serviceModel>  
        <bindings>  
            <sapBinding>  
                <binding name="SAPBinding" closeTimeout="00:01:00" openTimeout="00:01:00"  
                    receiveTimeout="00:10:00" sendTimeout="00:01:00" receiveIdocFormat="Typed"  
                    generateFlatFileCompatibleIdocSchema="true" maxConnectionsPerSystem="50"  
                    enableConnectionPooling="true" idleConnectionTimeout="00:15:00"  
                    flatFileSegmentIndicator="SegmentDefinition" enablePerformanceCounters="false"  
                    autoConfirmSentIdocs="false"  
                    acceptCredentialsInUri="false" padReceivedIdocWithSpaces="false"  
                    enableBizTalkCompatibilityMode="false" />  
            </sapBinding>  
        </bindings>  
        <client>  
            <endpoint address="sap://CLIENT=800;LANG=EN;@a/YourSAPHost/00?RfcSdkTrace=False&AbapDebug=False&UseSapGui=Without"  
                binding="sapBinding" bindingConfiguration="SAPBinding" contract="Rfc"  
                name="SAPBinding_Rfc" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="0684c-118">如果一个项目具有多个 WCF 客户端，将有多个客户端配置文件中定义的终结点条目。</span><span class="sxs-lookup"><span data-stu-id="0684c-118">If a project has more than one WCF client, there will be multiple client endpoint entries defined in the configuration file.</span></span> <span data-ttu-id="0684c-119">WCF 客户端的每个条目将具有唯一的名称基于它的绑定配置和目标 SAP 系统项目 （如 Rfc 和 Trfc）;例如，"SAPBinding_Rfc"。</span><span class="sxs-lookup"><span data-stu-id="0684c-119">Each WCF client entry will have a unique name based on its binding configuration and target SAP system artifacts (such as Rfc and Trfc); for example, "SAPBinding_Rfc".</span></span> <span data-ttu-id="0684c-120">如果你连接多个项目中创建 WCF 客户端的时机，多个绑定配置条目将创建，一个用于每个连接。</span><span class="sxs-lookup"><span data-stu-id="0684c-120">If you connect multiple times to create the WCF clients in your project, multiple binding configuration entries will be created, one for each connection.</span></span> <span data-ttu-id="0684c-121">这些绑定配置条目将被命名为按以下方式： SAPBinding1、 SAPBinding2，依次类推。</span><span class="sxs-lookup"><span data-stu-id="0684c-121">These binding configuration entries will be named in the following manner: SAPBinding1, SAPBinding2, and so on.</span></span> <span data-ttu-id="0684c-122">在特定的连接过程中创建的每个客户端终结点条目将引用在该连接过程中创建的绑定项。</span><span class="sxs-lookup"><span data-stu-id="0684c-122">Each client endpoint entry created during a specific connection will reference the binding entry created during that connection.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0684c-123">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]显示不同的 SAP 项目的相同的类型 （例如 RFC、 TRFC 和 IDOC） 为相同的服务协定的不同操作。</span><span class="sxs-lookup"><span data-stu-id="0684c-123">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces different SAP artifacts of the same type (such as RFC, TRFC, and IDOC) as different operations of the same service contract.</span></span> <span data-ttu-id="0684c-124">例如，两个不同的 Rfc、 RFC_EXAMPLE_A 和 RFC_EXAMPLE_B，同时不会出现在相同的服务协定 ("Rfc")。</span><span class="sxs-lookup"><span data-stu-id="0684c-124">For example, two different RFCs, RFC_EXAMPLE_A and RFC_EXAMPLE_B, will both be surfaced under the same service contract ("Rfc").</span></span> <span data-ttu-id="0684c-125">这意味着同一 WCF 客户端类，将调用两个 Rfc **RfcClient**，并且将在相同的命名空间中声明两个 Rfc 的参数。</span><span class="sxs-lookup"><span data-stu-id="0684c-125">This means that both RFCs will be invoked by the same WCF client class, **RfcClient**, and that the parameters for both RFCs will be declared in the same namespace.</span></span> <span data-ttu-id="0684c-126">因此，你必须在相同期间生成 WCF 客户端中的两个 Rfc[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]会话 （连接），以避免在生成解决方案时遇到命名空间冲突。</span><span class="sxs-lookup"><span data-stu-id="0684c-126">Therefore, you must generate the WCF client for both RFCs during the same [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] session (connection) to avoid experiencing a namespace collision when you build your solution.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0684c-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0684c-127">See Also</span></span>  
<span data-ttu-id="0684c-128">[开发使用 WCF 服务模型的 SAP 应用程序](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md) </span><span class="sxs-lookup"><span data-stu-id="0684c-128">[Develop SAP applications using the WCF Service Model](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md) </span></span>  
 <span data-ttu-id="0684c-129">[生成 WCF 客户端或 SAP 解决方案项目关联的 WCF 服务协定](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md) </span><span class="sxs-lookup"><span data-stu-id="0684c-129">[Generate a WCF client or a WCF service contract for SAP solution artifacts](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md) </span></span>  
 [<span data-ttu-id="0684c-130">创建 SAP 系统连接 URI</span><span class="sxs-lookup"><span data-stu-id="0684c-130">Create the SAP system connection URI</span></span>](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)