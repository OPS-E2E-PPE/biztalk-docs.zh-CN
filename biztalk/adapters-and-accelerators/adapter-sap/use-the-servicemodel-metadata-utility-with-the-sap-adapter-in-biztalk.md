---
title: 用于 mySAP Business Suite 的 BizTalk 适配器使用 ServiceModel Metadata Utility Tool |Microsoft Docs
description: 使用 svcutil.exe 为非默认绑定，或若要使用 SAP 适配器的 BizTalk 适配器包 (BAP) 中创建 WCF 客户端类或 WCF 服务协定
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ServiceModel Metadata Utility Tool, creating a WCF Client Class or a WCF service contract with the tool
- ServiceModel Metadata Utility Tool, configuring the tool for the adapter
ms.assetid: 7ac08012-bb12-4983-9402-be84fe3997d8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a8bdbf2a3b3a3c359a4c3e4912e2b6e18928023
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003174"
---
# <a name="using-the-servicemodel-metadata-utility-tool-with-the-biztalk-adapter-for-mysap-business-suite"></a>用于 mySAP Business Suite 的 BizTalk 适配器使用 ServiceModel Metadata Utility Tool
可以使用 ServiceModel Metadata Utility Tool (svcutil.exe) 生成 WCF 客户端类或操作的 WCF 服务协定 （接口） 的[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]公开。 运行 svcutil.exe 来生成 WCF 客户端类或 WCF 服务协定后，您可以在代码中包含生成的文件和创建生成的类的实例或实现中生成的接口对 SAP 执行操作的 WCF 服务系统。  
  
 使用 svcutil.exe 要求您提供一个连接 URI，其中包含凭据。 因为，默认情况下[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]禁用凭据中的连接 URI，必须配置要使用的非默认绑定的 svcutil.exe [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 此外可以在非默认绑定; 中配置其他绑定属性例如，若要创建 BAPI 操作的 WCF 客户端，必须设置**EnableSafeTyping**属性绑定到**true**。  
  
 以下部分介绍如何配置 svcutil.exe 以及如何使用 svcutil.exe 来生成 WCF 客户端代码或具有的 WCF 服务协定[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
##  <a name="BKMK_ConfigureSvcutil"></a> SAP 适配器的配置 svcutil.exe  
 若要配置 svcutil.exe 使用非默认绑定，您必须创建 svcutil.exe 的本地副本，然后创建或修改 svcutil.exe.config 配置文件的本地副本。  
  
1. 创建一个文件夹，并将 svcutil.exe 复制到新文件夹。 通常可以找到 svcutil.exe 在 Windows SDK 安装位置，具体而言，C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin。  
  
2. 创建名为的新文件夹中的 svcutil.exe.config 的文件。  
  
3. 将一个绑定和客户端终结点添加到 svcutil.exe.config 文件。 您必须从新的文件夹，以确保使用正确的配置运行 svcutil.exe。  
  
   > [!IMPORTANT]
   >  客户端终结点的 name 属性必须指定连接 URI 中使用的方案。 此值区分大小写。  
  
   ```  
   <configuration>  
     <system.serviceModel>  
       <client>  
         <!-- the name should match the required scheme of the WS-Metadata Exchange endpoint   
         and the contract should be "IMetadataExchange" -->  
         <endpoint name="sap"  
                   binding="sapBinding"  
                   bindingConfiguration="SAPBinding"  
                   contract="IMetadataExchange" />  
       </client>  
       <bindings>  
         <sapBinding>  
           <binding name="SAPBinding" acceptCredentialsInUri="true"/>  
         </sapBinding>  
       </bindings>  
  
     </system.serviceModel>  
  
   </configuration>  
   ```  
  
   您可以设置的绑定属性的任何[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]绑定配置中。 例如，可以指定要使用 svcutil.exe 生成 BAPI 操作的 WCF 客户端的以下非默认绑定。  
  
```  
<bindings>  
  <sapBinding>  
    <binding name="SAPBinding" acceptCredentialsInUri="true"/>  
  </sapBinding>  
</bindings>  
```  
  
 有关配置 svcutil.exe 的非默认绑定的详细信息，请参阅[自定义安全元数据终结点](https://msdn.microsoft.com/library/aa395212.aspx)。
  
## <a name="creating-a-wcf-client-class-or-a-wcf-service-contract-with-svcutilexe"></a>使用 svcutil.exe 创建 WCF 客户端类或 WCF 服务约定  
 若要使用 svcutil.exe 为生成 WCF 客户端代码或 WCF 服务协定 （接口） [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，必须提供 URI，指定的 WS-元数据交换 (MEX) 终结点的操作或操作要到 svcutil.exe 的连接生成代码。 此外必须在连接 URI 中指定为 SAP 系统的连接凭据。  
  
> [!NOTE]
>  您可以使用 svcutil.exe 与之前[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，你必须将其配置为使用非默认绑定; 了解有关如何执行此操作，请参阅[SAP 适配器的配置 svcutil.exe](#BKMK_ConfigureSvcutil)。  
  
 指定在 MEX 终结点和目标操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]连接 URI 按以下方式：  
  
- 您必须在查询字符串中包含"wsdl"参数。 如果它是查询字符串中的第一个参数，则将其指定之后问号 （？）。 如果它不是第一个参数，它应在前面加上 & 号 (&)。  
  
- 必须遵循一个或多个"op"参数"wsdl"的参数。 每个"op"参数的前面有与号 (&)，并指定目标操作的节点 ID。  
  
  以下三个示例演示如何通过使用 svcutil.exe 来面向各种操作。  
  
  此示例中为 RFC_CALCULATE_TAXES 创建 WCF 客户端类。  
  
  **.\svcutil "sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?wsdl&op=http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CALCULATE_TAXES"**  
  
  此示例中为 SALESORDER_CREATEFROMDAT201 和 SALESORDER_CREATEFROMDAT202 IDOC 创建 WCF 客户端类。  
  
  **.\svcutil "sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?wsdl&op=http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT201//620/Send&op=http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT202//620/Send"**  
  
  此示例创建 WCF 服务协定以接收来自 SAP 系统的 SALESORDER_CREATEFROMDAT201 IDOC。 节点 ID 指定接收操作。 此示例中处理检索元数据，因为没有需要的连接 URI query_string 中指定的侦听参数。  
  
  **.\svcutil "sap://User=YourUserName;Passwd=YourPassword;Client=800;Lang=EN;@a/YourSAPHost/00?wsdl&op=http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT201//620/Receive"**  
  
> [!IMPORTANT]
>  必须将连接 URI 放在命令行上的引号。 否则，svcutil.exe 会尝试检索操作的元数据的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]不支持。 这类尝试的结果不确定。  
  
 默认情况下，svcutil.exe 将生成的代码 output.cs 文件;但是，可以更改输出文件的名称和许多其他选项，svcutil.exe 使用通过设置命令行开关。 该 svcutil.exe 支持的选项的详细信息，请参阅[ServiceModel Metadata Utility Tool (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx)。
  
 Svcutil.exe 不提供搜索操作 （例如，通过使用通配符） 的功能。 必须显式指定你想要针对的特定操作的节点 Id。 操作的节点 ID 等于其消息的操作字符串。 不能指定节点只能引用类别的 Id。 详细了解节点 Id 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]图面，请参阅[元数据节点 Id](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md)。  
  
 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]提供高级的浏览和搜索功能，可以极大地简化生成 WCF 客户端类和 WCF 服务约定。 有关详细信息[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，请参阅[生成 WCF 客户端或 SAP 解决方案项目的 WCF 服务约定](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)。  
  
