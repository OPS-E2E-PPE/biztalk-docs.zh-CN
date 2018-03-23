---
title: 使用 ServiceModel 元数据实用工具 BizTalk 适配器为 Siebel eBusiness Applications |Microsoft 文档
description: 使用 svcutil.exe，对于非默认绑定，或使用 Siebel 适配器-BizTalk 适配器包 (BAP) 中创建的 WCF 客户端类或 WCF 服务协定
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 03d16481-cc8b-4e28-a33c-92e48a9a7e8f
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0bcf80d4a1ea9fc6b54403faa14084816e413be
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
---
# <a name="using-the-servicemodel-metadata-utility-tool-with-the-biztalk-adapter-for-siebel-ebusiness-applications"></a>使用 ServiceModel 元数据实用工具 BizTalk 适配器为 Siebel eBusiness Applications
你可以使用 ServiceModel 元数据实用工具 (svcutil.exe) 生成操作的 WCF 客户端类，[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]公开。 运行 svcutil.exe 以生成 WCF 客户端类后，你可以在你的代码中包含生成的文件和创建要在 Siebel 系统上执行操作的 WCF 客户端类的实例。  
  
 使用 svcutil.exe 需要你提供一个连接 URI，其中包含凭据。 因为，默认情况下，[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]禁用凭据在连接 URI，你必须配置要使用的非默认绑定的 svcutil.exe [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。 你还可以在非默认绑定中配置其他绑定属性。  
  
 以下部分说明如何配置 svcutil.exe 以及如何使用 svcutil.exe 生成 WCF 客户端代码[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  
##  <a name="BKMK_ConfigureSvcutil"></a>配置非默认绑定的 svcutil.exe   
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
>  你可以设置的绑定属性的任何[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]在绑定配置。  
  
 有关配置 svcutil.exe 的非默认绑定的详细信息，请参阅 WCF 文档中的"自定义安全元数据终结点"主题[ http://go.microsoft.com/fwlink/?LinkId=96077 ](http://go.microsoft.com/fwlink/?LinkId=96077)。  
  
## <a name="creating-a-wcf-client-class-with-svcutilexe"></a>使用 svcutil.exe 创建 WCF 客户端类  
 若要使用 svcutil.exe 生成的 WCF 客户端代码[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，你必须提供连接 URI，指定**IMetadataExchange** (mex) 终结点的操作或操作所需 svcutil.exe 生成代码。 你还必须在连接 URI 中指定 Siebel 系统的连接凭据。  
  
> [!NOTE]
>  你可以使用 svcutil.exe 与之前[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，你必须将其配置为使用非默认绑定; 有关如何执行此操作，请参阅[为 Siebel 适配器配置 svcutil.exe](#BKMK_ConfigureSvcutil)。  
  
 指定在 mex 终结点和目标操作[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]连接 URI 按以下方式：  
  
-   你必须在 query_string 中包含"wsdl"参数。 如果它是 query_string 中的第一个参数，其指定为问号 （？） 之后。 如果它不是第一个参数，它应在它前面加一个与号 (&)。  
  
-   你必须执行一个或多个"op"参数"wsdl"的参数。 每个"op"参数前面是一个与号 (&)，并指定目标操作的节点 ID。  
  
 下面的两个示例演示如何通过使用 svcutil.exe 来面向各种操作。  
  
 此示例创建插入操作在 ACCOUNT\ACCOUNT 业务对象上的 WCF 客户端类。  
  
 **.\svcutil "siebel://Username=YourUserName;Password=YourPassword@Siebel_server:1234?SiebelEnterpriseServer=ent_server&SiebelObjectManager=obj_mgr&Language=enu&wsdl&op=http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert"**  
  
 此示例创建插入操作和删除操作在 ACCOUNT\ACCOUNT 业务对象上的 WCF 客户端类。  
  
 **.\svcutil " siebel://Username=YourUserName;Password=YourPassword@Siebel_server:1234?SiebelEnterpriseServer=ent_server&SiebelObjectManager=obj_mgr&Language=enu&wsdl&op=http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert&op=http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Delete"**  
  
> [!IMPORTANT]
>  必须用引号引起来，在命令行上放置连接 URI。 否则，svcutil.exe 会尝试检索操作的元数据，[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]不支持。 这类尝试的结果不确定。  
  
 默认情况下，svcutil.exe 将生成的代码文件中的 output.cs;但是，你可以更改输出文件的名称和许多其他选项，svcutil.exe 使用通过设置命令行开关。  
  
 Svcutil.exe 不提供的功能 （例如，通过使用通配符） 搜索操作。 你必须显式指定要设定为目标的特定操作的节点 Id。 不能指定节点仅引用中的类别的 Id。 有关节点 Id 的详细信息，[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]图面，请参阅[元数据的节点 Id](../../adapters-and-accelerators/adapter-siebel/metadata-node-ids1.md)。  
  
 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]提供了高级的浏览和搜索功能可以极大地简化生成 WCF 客户端类。 有关详细信息[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，请参阅[生成 WCF 客户端或 Siebel 解决方案项目关联的 WCF 服务协定](../../adapters-and-accelerators/adapter-siebel/generate-a-wcf-client-or-a-wcf-service-contract-for-siebel-solution-artifacts.md)。  
  
