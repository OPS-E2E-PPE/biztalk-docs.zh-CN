---
title: 配置客户端绑定为 SAP 系统 |Microsoft Docs
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
ms.openlocfilehash: 6788d735a1c2d91937473661365e7da393426b65
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373962"
---
# <a name="configure-a-client-binding-for-the-sap-system"></a>配置客户端 SAP 系统的绑定
生成 WCF 客户端类后，您可以创建 WCF 客户端 （实例） 并调用其方法来使用[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]。 有关如何生成操作的 WCF 客户端类和帮助程序代码的信息的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]公开，请参阅[生成 WCF 客户端或 SAP 解决方案项目的 WCF 服务约定](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)。  
  
 若要创建 WCF 客户端，必须指定一个终结点地址和绑定。 终结点地址必须包含有效的 SAP 连接 URI，并且该绑定必须是 SAP 绑定的一个实例 (**SAPBinding**)。 有关 SAP 连接 URI 的详细信息，请参阅[创建 SAP 系统连接 URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)。  
  
 在代码中或在配置文件中，可以指定 SAP 绑定和终结点地址。 当你使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]生成 WCF 客户端类，创建配置文件 (app.config) 还为你的项目。 此文件包含反映的绑定属性和连接信息 （除了凭据） 时连接到 SAP 系统与指定的配置设置[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。  
  
## <a name="specifying-the-binding-and-endpoint-address-in-code"></a>在代码中指定的绑定和终结点地址  
 下面的代码演示如何通过在代码中指定的绑定和终结点地址创建 WCF 客户端。 它是通过使用指定的 SAP 系统凭据的好办法**ClientCredentials**的 WCF 客户端，而不是连接提供的终结点地址 URI 中的属性。  
  
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
  
## <a name="specifying-the-binding-and-endpoint-address-in-a-configuration-file"></a>在配置文件中指定的绑定和终结点地址  
 下面的代码演示如何通过在 app.config 文件中指定的绑定和终结点地址创建 WCF 客户端。  
  
```  
// A WCF client that targets an RFC is created  
// by specifying the client endpoint information in app.config  
RfcClient rfcClient = new RfcClient("SAPBinding_Rfc");  
  
rfcClient.ClientCredentials.UserName.UserName = "YourUserName";  
rfcClient.ClientCredentials.UserName.Password = "YourPassword";  
  
rfcClient.Open();  
```  
  
 下面的 XML 演示配置文件的 EMP 表创建的[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]。 此文件包含在前面的示例中引用的客户端终结点配置。  
  
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
  
 如果一个项目具有多个 WCF 客户端，将有多个客户端配置文件中定义的终结点条目。 每个 WCF 客户端条目将具有唯一的名称基于其绑定配置和目标 SAP 系统项目 （如 Rfc 和 Trfc）;例如，"SAPBinding_Rfc"。 如果连接多个要在项目中创建 WCF 客户端的时间，多个绑定配置条目将创建，另一个用于每个连接。 将按以下方式命名这些绑定配置条目：SAPBinding1、 SAPBinding2，等等。 在特定的连接过程中创建每个客户端终结点条目将引用在该连接过程中创建的绑定项。  
  
> [!IMPORTANT]
>  [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]显示相同类型 （如 RFC、 TRFC 和 IDOC） 的不同 SAP 项目作为相同的服务协定的不同操作。 例如，两个不同的 Rfc、 RFC_EXAMPLE_A 和 RFC_EXAMPLE_B，不会同时出现在相同的服务合同 ("Rfc")。 这意味着同一 WCF 客户端类，将调用这两个 Rfc **RfcClient**，并将在相同的命名空间中声明这两个 Rfc 的参数。 因此，必须在同一生成 WCF 客户端为这两个 Rfc[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]会话 （连接），以避免生成解决方案时遇到的命名空间冲突。  
  
## <a name="see-also"></a>请参阅  
[开发 SAP 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-service-model.md)   
 [生成 WCF 客户端或 WCF 服务约定的 SAP 解决方案项目](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)   
 [创建 SAP 系统连接 URI](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)