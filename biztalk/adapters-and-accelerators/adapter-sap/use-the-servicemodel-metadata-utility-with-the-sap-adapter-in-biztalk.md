---
title: "使用 ServiceModel 元数据实用工具 BizTalk 适配器为 mySAP Business Suite |Microsoft 文档"
description: "使用 svcutil.exe，对于非默认绑定，或使用 SAP 适配器-BizTalk 适配器包 (BAP) 中创建的 WCF 客户端类或 WCF 服务协定"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ServiceModel Metadata Utility Tool, creating a WCF Client Class or a WCF service contract with the tool
- ServiceModel Metadata Utility Tool, configuring the tool for the adapter
ms.assetid: 7ac08012-bb12-4983-9402-be84fe3997d8
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15c4612db6e3cde4e46385b1c5d1810fbb00eb70
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="using-the-servicemodel-metadata-utility-tool-with-the-biztalk-adapter-for-mysap-business-suite"></a>为 mySAP Business Suite 中使用 BizTalk 适配器使用 ServiceModel 元数据实用工具
你可以使用 ServiceModel 元数据实用工具 (svcutil.exe) 生成 WCF 客户端类或操作的 WCF 服务协定 （接口），[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]公开。 运行 svcutil.exe 以生成 WCF 客户端类或 WCF 服务协定后，您可以在你的代码中包含生成的文件和创建生成的类的实例或实现 WCF 服务生成的接口在 SAP 上执行操作系统。  
  
 使用 svcutil.exe 需要你提供一个连接 URI，其中包含凭据。 因为，默认情况下，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]禁用凭据在连接 URI，你必须配置要使用的非默认绑定的 svcutil.exe [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 你还可以在非默认绑定; 中配置其他绑定属性例如，若要创建 WCF 客户端 BAPI 操作，你必须设置**EnableSafeTyping**属性绑定到**true**。  
  
 以下部分说明如何配置 svcutil.exe 以及如何使用 svcutil.exe 生成 WCF 客户端代码或 WCF 服务协定与[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
##  <a name="BKMK_ConfigureSvcutil"></a>为 SAP 适配器配置 svcutil.exe  
 若要配置为使用非默认绑定的 svcutil.exe，你必须创建 svcutil.exe 的本地副本，然后创建或修改 svcutil.exe.config 配置文件的本地副本。  
  
1.  创建一个文件夹，并将 svcutil.exe 复制到新文件夹。 你通常可以找到 svcutil.exe 在 Windows SDK 安装位置，具体而言，C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin。  
  
2.  创建名为的新文件夹中的 svcutil.exe.config 的文件。  
  
3.  将一个绑定和客户端终结点添加到 svcutil.exe.config 文件中。 你必须从新的文件夹，以确保使用正确的配置运行 svcutil.exe。  
  
    > [!IMPORTANT]
    >  客户端终结点的名称属性必须指定连接 URI 中所使用的方案。 此值区分大小写。  
  
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
  
 你可以设置的绑定属性的任何[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]在绑定配置。 例如，你可以指定以下的非默认绑定，以使用 svcutil.exe 生成 WCF 客户端 BAPI 操作。  
  
```  
<bindings>  
  <sapBinding>  
    <binding name="SAPBinding" acceptCredentialsInUri="true"/>  
  </sapBinding>  
</bindings>  
```  
  
 有关配置 svcutil.exe 的非默认绑定的详细信息，请参阅[自定义安全元数据终结点](https://msdn.microsoft.com/library/aa395212.aspx)。
  
## <a name="creating-a-wcf-client-class-or-a-wcf-service-contract-with-svcutilexe"></a>使用 svcutil.exe 创建 WCF 客户端类或 WCF 服务协定  
 以使用 svcutil.exe 来生成 WCF 客户端代码或 WCF 服务协定 （接口） [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，你必须提供连接 URI，指定 WS 元数据交换 (MEX) 终结点的操作或你想到 svcutil.exe 的操作生成代码。 此外必须在连接 URI 中指定的 SAP 系统的连接凭据。  
  
> [!NOTE]
>  你可以使用 svcutil.exe 与之前[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，你必须将其配置为使用非默认绑定; 有关如何执行此操作，请参阅[为 SAP 适配器配置 svcutil.exe](#BKMK_ConfigureSvcutil)。  
  
 指定在 MEX 终结点和目标操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]连接 URI 按以下方式：  
  
-   你必须查询字符串中包含"wsdl"参数。 如果是查询字符串中的第一个参数，其指定为问号 （？） 之后。 如果它不是第一个参数，它应在它前面加一个与号 (&)。  
  
-   你必须执行一个或多个"op"参数"wsdl"的参数。 每个"op"参数前面是一个与号 (&)，并指定目标操作的节点 ID。  
  
 以下三个示例演示如何通过使用 svcutil.exe 来面向各种操作。  
  
 此示例为 RFC_CALCULATE_TAXES 创建 WCF 客户端类。  
  
 **。 \svcutil"sap://User=YourUserName;密码 = 你的密码;客户端 = 800;Lang = EN;@a/YourSAPHost/00？ wsdl （& a) 操作 = http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CALCULATE_TAXES"**  
  
 此示例创建一个 WCF 客户端类 SALESORDER_CREATEFROMDAT201 和 SALESORDER_CREATEFROMDAT202 IDOC。  
  
 **。 \svcutil"sap://User=YourUserName;密码 = 你的密码;客户端 = 800;Lang = EN;@a/YourSAPHost/00？ wsdl （& a) 操作 = http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT201//620/Send 操作 = http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT202//620/Send"**  
  
 此示例将创建 WCF 服务约定以 SALESORDER_CREATEFROMDAT201 IDOC 接收 SAP 系统。 节点 ID 指定接收操作。 此示例处理检索元数据，因为没有无需连接 URI query_string 中指定的侦听器参数。  
  
 **。 \svcutil"sap://User=YourUserName;密码 = 你的密码;客户端 = 800;Lang = EN;@a/YourSAPHost/00？ wsdl （& a) 操作 = http://Microsoft.LobServices.Sap/2007/03/Idoc/3/SALESORDER_CREATEFROMDAT201//620/Receive"**  
  
> [!IMPORTANT]
>  必须用引号引起来，在命令行上放置连接 URI。 否则，svcutil.exe 会尝试检索操作的元数据，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]不支持。 这类尝试的结果不确定。  
  
 默认情况下，svcutil.exe 将生成的代码文件中的 output.cs;但是，你可以更改输出文件的名称和许多其他选项，svcutil.exe 使用通过设置命令行开关。 该 svcutil.exe 支持的选项的详细信息，请参阅[ServiceModel 元数据实用工具 (Svcutil.exe)](https://msdn.microsoft.com/library/aa347733.aspx)。
  
 Svcutil.exe 不提供的功能 （例如，通过使用通配符） 搜索操作。 你必须显式指定要设定为目标的特定操作的节点 Id。 等效于其消息的操作字符串运算的节点 ID。 不能指定节点仅引用中的类别的 Id。 有关节点 Id 的详细信息，[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]图面，请参阅[元数据的节点 Id](../../adapters-and-accelerators/adapter-sap/metadata-node-ids4.md)。  
  
 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]提供了高级的浏览和搜索功能可以极大地简化生成的 WCF 客户端类和 WCF 服务协定。 有关详细信息[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，请参阅[生成 WCF 客户端或 SAP 解决方案项目关联的 WCF 服务协定](../../adapters-and-accelerators/adapter-sap/generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts.md)。  
  
