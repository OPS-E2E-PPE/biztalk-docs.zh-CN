---
title: 在 BizTalk Server 中的 Oracle 数据库的 BizTalk 适配器使用 ServiceModel Metadata Utility Tool |Microsoft Docs
description: 使用 svcutil.exe 为非默认绑定，或使用 Oracle DB 适配器的 BizTalk 适配器包 (BAP) 中创建 WCF 客户端类或 WCF 服务协定
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f8660014-da04-4692-89e8-f14fcb419496
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fe432c9cf7e586269f85beb5f584bbe2aa37210
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999358"
---
# <a name="using-the-servicemodel-metadata-utility-tool-with-the-biztalk-adapter-for-oracle-database"></a>ServiceModel Metadata Utility Tool 的 BizTalk 适配器将用于 Oracle 数据库
可以使用 ServiceModel Metadata Utility Tool (svcutil.exe) 生成 WCF 客户端类或操作的 WCF 服务协定 （接口） 的[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]公开。 运行 svcutil.exe 来生成 WCF 客户端类或 WCF 服务协定后，可以在代码中包含生成的文件并创建生成的类的实例也可以实现对 Oracle 执行操作的协定中的 WCF 服务数据库。  
  
 使用 svcutil.exe 要求您提供一个连接 URI，其中包含凭据。 因为，默认情况下[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]禁用凭据中的连接 URI，必须配置要使用的非默认绑定的 svcutil.exe [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
 以下部分介绍如何配置 svcutil.exe 以及如何使用 svcutil.exe 来生成 WCF 客户端代码或具有的 WCF 服务协定[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
##  <a name="BKMK_ConfigureSvcutil"></a> 配置非默认绑定的 svcutil.exe   
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
          <!-- the name should match the required scheme of the WS-Metadata Exchange endpoint   
          and the contract should be "IMetadataExchange" -->  
          <endpoint name="oracledb"  
                    binding="oracleDBBinding"  
                    bindingConfiguration="OracleDBBinding"  
                    contract="IMetadataExchange" />  
        </client>  
        <bindings>  
            <oracleDBBinding>  
                <binding name="OracleDBBinding" acceptCredentialsInUri="true" />  
            </oracleDBBinding>  
        </bindings>  
  
      </system.serviceModel>  
  
    </configuration>  
    ```  
  
> [!NOTE]
>  您可以设置的绑定属性的任何[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]绑定配置中。  
  
 有关配置 svcutil.exe 的非默认绑定的详细信息，请参阅 WCF 文档中的"自定义安全元数据终结点"主题[ http://go.microsoft.com/fwlink/?LinkId=96077 ](http://go.microsoft.com/fwlink/?LinkId=96077)。  
  
### <a name="configure-a-non-default-binding-for-the-pollingstmt-operation"></a>配置非默认绑定 POLLINGSTMT 操作  
 若要使用 svcutil.exe 创建 POLLINGSTMT 操作的 WCF 服务协定，必须配置要包括的非默认绑定**pollingStatement**属性，除了**acceptCredentialsInUri**. **PollingStatement**必须包含目标表的 SELECT 语句。 [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]使用此属性以生成类，它表示强类型化结果设置 POLLINGSTMT 操作返回。 下面的示例演示用于生成面向的 POLLINGSTMT 操作的 WCF 服务协定的绑定配置 /SCOTT/EMP 表。  
  
```  
<bindings>  
    <oracleDBBinding>  
        <binding name="OracleDBBinding" acceptCredentialsInUri="true"   
                                   pollingStatement="SELECT * FROM EMP FOR UPDATE" />  
    </oracleDBBinding>  
</bindings>  
```  
  
## <a name="create-a-wcf-client-class-or-wcf-service-contract-with-svcutilexe"></a>使用 svcutil.exe 创建 WCF 客户端类或 WCF 服务约定  
 若要使用 svcutil.exe 为生成 WCF 客户端代码或 WCF 服务协定 （接口） [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，必须提供 URI，指定的 WS-元数据交换 (MEX) 终结点的操作或操作要到 svcutil.exe 的连接生成代码。 此外必须在连接 URI 中指定 Oracle 数据库的连接凭据。  
  
> [!NOTE]
>  您可以使用 svcutil.exe 与之前[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，你必须将其配置为使用非默认绑定; 了解有关如何执行此操作，请参阅[Oracle 数据库适配器的配置 svcutil.exe](#BKMK_ConfigureSvcutil)。  
  
 指定在 MEX 终结点和目标操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]连接 URI 按以下方式：  
  
- 你必须在 query_string 中包括"wsdl"参数。 如果它是 query_string 中的第一个参数，则将其指定之后问号 （？）。 如果它不是第一个参数，它应在前面加上 & 号 (&)。  
  
- 必须遵循一个或多个"op"参数"wsdl"的参数。 每个"op"参数的前面有与号 (&)，并指定目标操作的节点 ID。  
  
  以下三个示例演示如何通过使用 svcutil.exe 来面向各种操作。  
  
  此示例创建 /SCOTT/EMP 表上插入操作的 WCF 客户端类。  
  
  **。 \svcutil"oracledb://User=SCOTT;密码 =TIGER@ADAPTER？ wsdl & op =http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert"**  
  
  此示例创建一个 WCF 客户端类对于插入和 /SCOTT/EMP 表上的删除操作。  
  
  **。 \svcutil"oracledb://User=SCOTT;密码 =TIGER@ADAPTER？ wsdl & op =http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert&op=http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Delete"**  
  
  此示例创建 POLLLINGSTMT 操作的 WCF 服务约定。 （若要使用 svcutil.exe 生成 POLLINGSTMT 操作的 WCF 服务约定，您必须配置包含一个轮询语句的 svcutil.exe 的非默认绑定。）  
  
  **。 \svcutil"oracledb://User=SCOTT;密码 =TIGER@ADAPTER？ wsdl & op =http://Microsoft.LobServices.OracleDB/2007/03/POLLINGSTMT"**  
  
> [!IMPORTANT]
>  必须将连接 URI 放在命令行上的引号。 否则，svcutil.exe 会尝试检索操作的元数据的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]不支持。 这类尝试的结果不确定。  
  
 默认情况下，svcutil.exe 将生成的代码 output.cs 文件;但是，可以更改输出文件的名称和许多其他选项，svcutil.exe 使用通过设置命令行开关。 该 svcutil.exe 支持的选项的详细信息，请参阅 WCF 文档中的"ServiceModel 元数据实用工具工具 (Svcutil.exe)"主题[ http://go.microsoft.com/fwlink/?LinkId=72777 ](http://go.microsoft.com/fwlink/?LinkId=72777)。  
  
 Svcutil.exe 不提供搜索操作 （例如，通过使用通配符） 的功能。 必须显式指定你想要针对的特定操作的节点 Id。 不能指定节点只能引用类别的 Id。 详细了解节点 Id 的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]图面，请参阅[元数据节点 Id](../../adapters-and-accelerators/adapter-oracle-database/metadata-node-ids3.md)。  
  
 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]提供高级的浏览和搜索功能，可以极大地简化生成 WCF 客户端类和 WCF 服务约定。 有关详细信息[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]，请参阅[为 Oracle 数据库解决方案项目生成 WCF 客户端或 WCF 服务约定](../../adapters-and-accelerators/adapter-oracle-database/create-a-wcf-client-or-wcf-service-contract-for-oracle-db-solution-artifacts.md)。  
  
## <a name="see-also"></a>请参阅  
 [Oracle 数据库的 BizTalk 适配器的消息和消息架构](../../adapters-and-accelerators/adapter-oracle-database/messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)