---
title: 用于 Siebel eBusiness 应用程序的 BizTalk 适配器使用 ServiceModel Metadata Utility Tool |Microsoft Docs
description: 使用 svcutil.exe 为非默认绑定，或使用 Siebel 适配器的 BizTalk 适配器包 (BAP) 中创建 WCF 客户端类或 WCF 服务协定
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 03d16481-cc8b-4e28-a33c-92e48a9a7e8f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9741b970873b97401968f7b87ee76ac853c60ae4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987382"
---
# <a name="using-the-servicemodel-metadata-utility-tool-with-the-biztalk-adapter-for-siebel-ebusiness-applications"></a>用于 Siebel eBusiness 应用程序的 BizTalk 适配器使用 ServiceModel Metadata Utility Tool
可以使用 ServiceModel Metadata Utility Tool (svcutil.exe) 生成操作的 WCF 客户端类的[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]公开。 运行 svcutil.exe 来生成 WCF 客户端类后，可以在代码中包含生成的文件并创建要在 Siebel 系统上执行操作的 WCF 客户端类的实例。  
  
 使用 svcutil.exe 要求您提供一个连接 URI，其中包含凭据。 因为，默认情况下[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]禁用凭据中的连接 URI，必须配置要使用的非默认绑定的 svcutil.exe [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。 此外可以在非默认绑定中配置其他绑定属性。  
  
 以下部分介绍如何配置 svcutil.exe 以及如何使用 svcutil.exe 来生成 WCF 客户端代码与[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  
##  <a name="BKMK_ConfigureSvcutil"></a>配置非默认绑定的 svcutil.exe   
 若要配置 svcutil.exe 使用非默认绑定，您必须创建 svcutil.exe 的本地副本，然后创建或修改 svcutil.exe.config 配置文件的本地副本。  
  
 
1.  创建一个文件夹，并将 svcutil.exe 复制到新文件夹。 通常可以找到 svcutil.exe 在 Windows SDK 安装位置，具体而言，C:\Program Files\Microsoft SDKs\Windows\v6.0\Bin。  
  
2.  创建名为的新文件夹中的 svcutil.exe.config 的文件。  
  
3.  将一个绑定和客户端终结点添加到 svcutil.exe.config 文件。 您必须从新的文件夹，以确保使用正确的配置运行 svcutil.exe。  
  
    > [!IMPORTANT]
    >  客户端终结点的 name 属性必须指定连接 URI 中使用的方案。 此值区分大小写。  
  
    ```  
    <configuration>  
      <system.serviceModel>  
        <client>  
          <!-- the name should match the required scheme of the Metadata Exchange endpoint   
          and the contract should be "IMetadataExchange" -->  
          <endpoint name="siebel"  
            binding="siebelBinding"  
            bindingConfiguration="SiebelBinding"  
            contract="IMetadataExchange" />  
        </client>  
        <bindings>  
          <siebelBinding>  
            <binding name="SiebelBinding" acceptCredentialsInUri="true" />  
          </siebelBinding>  
        </bindings>  
  
      </system.serviceModel>  
  
    </configuration>  
  
    ```  
  
> [!NOTE]
>  您可以设置的绑定属性的任何[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]绑定配置中。  
  
 有关配置 svcutil.exe 的非默认绑定的详细信息，请参阅 WCF 文档中的"自定义安全元数据终结点"主题[ http://go.microsoft.com/fwlink/?LinkId=96077 ](http://go.microsoft.com/fwlink/?LinkId=96077)。  
  
## <a name="creating-a-wcf-client-class-with-svcutilexe"></a>使用 svcutil.exe 创建 WCF 客户端类  
 若要使用 svcutil.exe 生成的 WCF 客户端代码[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，必须提供的连接 URI，指定**IMetadataExchange** (mex) 终结点的操作或操作为想 svcutil.exe 生成代码。 此外必须在连接 URI 中指定用于 Siebel 系统的连接凭据。  
  
> [!NOTE]
>  您可以使用 svcutil.exe 与之前[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，你必须将其配置为使用非默认绑定; 了解有关如何执行此操作，请参阅[Siebel 适配器的配置 svcutil.exe](#BKMK_ConfigureSvcutil)。  
  
 指定在 mex 终结点和目标操作[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]连接 URI 按以下方式：  
  
- 你必须在 query_string 中包括"wsdl"参数。 如果它是 query_string 中的第一个参数，则将其指定之后问号 （？）。 如果它不是第一个参数，它应在前面加上 & 号 (&)。  
  
- 必须遵循一个或多个"op"参数"wsdl"的参数。 每个"op"参数的前面有与号 (&)，并指定目标操作的节点 ID。  
  
  以下两个示例演示如何通过使用 svcutil.exe 来面向各种操作。  
  
  此示例创建 ACCOUNT\ACCOUNT 业务对象的插入操作的 WCF 客户端类。  
  
  **.\svcutil "siebel://Username=YourUserName;Password=YourPassword@Siebel_server:1234?SiebelEnterpriseServer=ent_server&SiebelObjectManager=obj_mgr&Language=enu&wsdl&op=http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert"**  
  
  此示例创建用于插入操作和删除操作在 ACCOUNT\ACCOUNT 业务对象上的 WCF 客户端类。  
  
  **.\svcutil " siebel://Username=YourUserName;Password=YourPassword@Siebel_server:1234?SiebelEnterpriseServer=ent_server&SiebelObjectManager=obj_mgr&Language=enu&wsdl&op=http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert&op=http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Delete"**  
  
> [!IMPORTANT]
>  必须将连接 URI 放在命令行上的引号。 否则，svcutil.exe 会尝试检索操作的元数据的[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]不支持。 这类尝试的结果不确定。  
  
 默认情况下，svcutil.exe 将生成的代码 output.cs 文件;但是，可以更改输出文件的名称和许多其他选项，svcutil.exe 使用通过设置命令行开关。  
  
 Svcutil.exe 不提供搜索操作 （例如，通过使用通配符） 的功能。 必须显式指定你想要针对的特定操作的节点 Id。 不能指定节点只能引用类别的 Id。 详细了解节点 Id 的[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]图面，请参阅[元数据节点 Id](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md)。  
  
 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]提供高级的浏览和搜索功能，可以极大地简化生成 WCF 客户端类。 有关详细信息[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，请参阅[生成 WCF 客户端或 WCF 服务协定为 Siebel 解决方案项目](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md)。  
  
