---
title: 创建 Siebel 系统连接 URI |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- connection URI
- connecting to Siebel, using the connection URI
- how to, connect using connection URI
- connecting using connection URI
ms.assetid: 8cc78149-1c20-40db-aece-aab520ee04e7
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3360433e97b9b7d21a06d3ad5c304f37a924589f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000614"
---
# <a name="create-the-siebel-system-connection-uri"></a>创建 Siebel 系统连接 URI
[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]连接 URI 包含适配器用来建立与 Siebel 系统的连接属性。  

 本主题提供有关 Siebel 连接 URI 的信息，并还提供了指向其他主题的解释如何在不同的编程方案中指定连接 URI。  

## <a name="connection-uri-for-the-siebel-adapter"></a>Siebel 适配器的连接 URI  
 典型[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]终结点地址 URI 表示，如下所示：  

```  
scheme://userinfoparams@hostinfoparams?query_string  
```  

 终结点地址 URI 包含以下组件：  

- 方案为方案名称。  

- userinfoparams 是终结点进行用户身份验证所需的参数名称值集合。  

- hostinfoparams 是建立与主机; 的连接所需的信息例如，路径。  

- query_string 是由问号 （？） 分隔的参数的可选名称值集合。  

  Siebel 连接 URI 遵循以下常规格式，并实现，如下所示：  

```  
siebel://Username=[USER_NAME];Password=[PASSWORD]@[SERVER]:[PORT]?SiebelObjectManager=[SIEBEL_OBJECT_MANAGER_NAME]&SiebelEnterpriseServer=[SERVER_NAME]&Language=[LANGUAGE]&Transport=[TRANSPORT]&Encryption=[ENCRYPTION]&Compression=[COMPRESSION]&SiebelServer=[SIEBEL_SERVER_NAME]&SiebelRepository=[SIEBEL_REPOSITORY_NAME]  
```  

 以下各节介绍 Siebel 连接 URI 的每个组件实现的属性。  

### <a name="the-scheme-for-the-siebel-connection-uri"></a>Siebel 连接 URI 的方案  
 Siebel 连接 URI 的方案是"siebel"。  

### <a name="user-information-in-the-siebel-connection-uri"></a>Siebel 连接 URI 中的用户信息  
 默认情况下， [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] Siebel 系统凭据指定连接 URI 中时将引发异常。 这是因为这些凭据表示为纯文本，这会带来固有的安全风险。 可以设置**AcceptCredentialsInUri**属性绑定到控件是否连接 URI 可以包含的凭据。 如果**AcceptCredentialsInUri**属性是**false**，则[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]时引发异常的连接 URI 包含凭据; 如果该属性为**true**，不会引发异常。  

> [!IMPORTANT]
>  通过在字符串中以明文形式传递凭据带来的固有安全风险，由于是最好不要在连接 URI 中指定 Siebel 系统凭据。  

 有几种方法来提供不包含在连接 URI 中指定的 Siebel 系统凭据。  

- 在代码中，可以设置**ClientCredentials**相应对象上的属性。  

- 当你使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，可以通过选择输入凭据**安全**选项卡**配置适配器**对话框。  

- 当指定的发送端口或接收位置中的绑定[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]解决方案，可以通过选择输入凭据**安全**相应对话框中的选项卡。  

  Siebel 连接 URI 表示为的用户身份验证所需的参数的名称 / 值集合中的用户信息 (userinfoparams)。 下表介绍了这些参数。  

| “属性” |                                                                                                                                                                                                          Description                                                                                                                                                                                                          |
|----------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 用户名 |      Siebel 系统用户名此值是区分大小写。 必须设置**AcceptCredentialsInUri**属性绑定到**true**连接 URI 中指定的用户名和密码。 **注意：** [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]将保留在打开 Siebel 系统上的连接时输入的用户名的值的大小写。       |
| Password | Siebel 系统用户的密码此值是区分大小写。 必须设置**AcceptCredentialsInUri**属性绑定到**true**连接 URI 中指定的用户名和密码。 **注意：** [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]将保留在打开 Siebel 系统上的连接时输入的密码值的大小写。 |

### <a name="host-information-in-the-siebel-connection-uri"></a>Siebel 连接 URI 中的主机信息  
 Siebel 主机信息 (hostinfoparams) 指定的 Siebel 系统的地址采用以下格式: [服务器]: [PORT]。 具体取决于 Siebel 服务器版本，Siebel 主机信息采用不同的值：  

- **用于 Siebel 版本 7.5 和更早版本**，主机信息参数采用哪些 Siebel 网关服务器安装和 Siebel 网关端口号上的计算机的名称。  

- **用于 Siebel 7.7 和更高版本**，主机信息参数采用在其安装服务器 Siebel 和 Siebel 连接 broker 端口号的计算机的名称。  

  > [!IMPORTANT]
  >  当你使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]或[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]要连接到 Siebel 系统，主机信息必须提供"SiebelGateway"连接属性。  

### <a name="query-information-in-the-siebel-connection-uri"></a>Siebel 连接 URI 中的查询信息  
 Siebel 连接 URI 中的查询信息 (query_string) 用于指定附加的连接属性。  


|        “属性”        |                                                                                                                                          Description                                                                                                                                           |
|------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  SiebelObjectManager   |                                                                                                  企业服务器上的 Siebel 对象管理器的名称。 此参数是必需的。                                                                                                   |
| SiebelEnterpriseServer |                                                                                                             Siebel 企业服务器的名称。 此参数是必需的。                                                                                                              |
|        “报表”        |                                             对象管理器的语言。 此参数可选。 如果未指定，[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]提供默认值 (enu)。                                              |
|       Transport        |                                                                        传输;仅支持 tcpip。 此参数可选。 如果未指定，Siebel 系统提供默认值 (tcpip)。                                                                         |
|       加密       | 要使用之间的加密类型[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]和 Siebel 系统。 支持的值为 none、 mscrypto，或 rsa。 此参数可选。 如果未指定，Siebel 系统提供的默认值 （无）。 |
|      压缩      |    要使用之间的压缩算法[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]和 Siebel 系统。 支持的值为 none 或使用 zlib。 此参数可选。 如果未指定，Siebel 系统提供默认值 (使用 zlib)。     |
|      SiebelServer      |                                                                                 Siebel 服务器。 所需的所有 Siebel 7.5 服务器连接 (7.5.2、 7.5.3，等等。);否则，未设置此参数。                                                                                  |
|    SiebelRepository    |                          Siebel 存储库。 所需的服务器; 上是否存在多个存储库否则为可选。 **注意：** 如果在服务器上存在多个存储库，则必须 SiebelRepository 参数中指定目标存储库。                           |

 有关在查询信息中设置的 Siebel 参数的详细信息，请参阅 Siebel 文档。  

## <a name="using-reserved-characters-in-the-connection-uri"></a>在连接 URI 中使用保留的字符  
 [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]不支持指定连接 URI，其中含有特殊字符的任何参数值。 如果连接参数值包含特殊字符，请确保执行下列任一操作：  

- 如果在指定的 URI 中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，则必须指定其作为-处于**URI 属性**选项卡上，即，而无需使用任何转义符。 如果指定的 URI 中直接**配置 URI**字段和连接参数包含保留的字符，则必须指定连接参数使用正确的转义字符。  

- 如果创建一个发送时指定的 URI 或接收端口中的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中和连接参数包含保留的字符，则必须指定连接参数使用正确的转义字符。  

## <a name="using-the-connection-uri-to-connect-to-the-siebel-system"></a>用于连接到 Siebel 系统连接 URI  
 下面是示例 Siebel 连接 URI。  

```  
siebel://Username=YourUserName;Password=YourPassword@Siebel_server:1234?SiebelObjectManager=obj_mgr&SiebelEnterpriseServer=entserver&Language=enu  
```  

> [!NOTE]
>  此示例 URI 包含 Siebel 系统凭据;必须设置**AcceptCredentialsInUri**属性绑定到**true**若要使用的连接 URI，其中包含凭据。  

 有关如何建立与 Siebel 系统 （包括设置连接属性） 的连接时你：  

- 使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]或[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]，请参阅[获取 Siebel 操作在 Visual Studio 中的元数据](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)。  

- 配置发送端口或接收端口 （位置） 中[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]解决方案，请参阅[手动配置到 Siebel 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-siebel/manually-configure-a-physical-port-binding-to-the-siebel-adapter.md)。

- 编程解决方案中使用 WCF 通道模型，请参阅[创建一个通道，使用 Siebel](../../adapters-and-accelerators/adapter-siebel/create-a-channel-using-siebel.md)。  

- 编程解决方案中使用 WCF 服务模型，请参阅[为 Siebel 系统配置 WCF 客户端](../../adapters-and-accelerators/adapter-siebel/configure-a-wcf-client-for-a-siebel-system.md)。  

- 使用 WCF ServiceModel Metadata Utility Tool (svcutil.exe)，请参阅[用于 Siebel eBusiness 应用程序的 BizTalk 适配器使用 ServiceModel Metadata Utility Tool](../../adapters-and-accelerators/adapter-siebel/use-the-servicemodel-metadata-utility-with-the-siebel-adapter.md)。  

## <a name="see-also"></a>请参阅  
 [创建与 Siebel 系统的连接](../../adapters-and-accelerators/adapter-siebel/create-a-connection-to-the-siebel-system.md)   
[开发 Siebel 应用程序](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)   
 [开发 Siebel 应用程序使用 WCF 通道 Model3](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-channel-model3.md)   
 [开发 SQL 应用程序使用 WCF 服务模型](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)