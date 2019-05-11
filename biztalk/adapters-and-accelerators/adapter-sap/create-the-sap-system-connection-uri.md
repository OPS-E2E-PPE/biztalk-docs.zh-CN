---
title: 创建 SAP 系统连接 URI |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- connection URI
- how to, connect using connection URI
- connecting using connection URI
- connecting to SAP, using the connection URI
ms.assetid: e41ed488-07a7-4fb7-97c0-6d626e041e95
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f0cf3f1f830540469fb9e87af6ef3cdcb7f87068
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373539"
---
# <a name="create-the-sap-system-connection-uri"></a>创建 SAP 系统连接 URI
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]连接 URI 包含适配器用于建立到 SAP 系统的连接的属性。  

> [!IMPORTANT]
>  默认情况下，SAP 客户端库 (librfc32u.dll) 支持最多 100 个连接到 SAP 系统。 如果超过此数量的连接，将引发异常。 出于此原因，应设置**MaxConnectionsPerSystem**绑定属性可限制连接数的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]将尝试打开 SAP 系统或 CPIC_MAX_CONV 环境变量设置为增加受支持的 SAP 客户端库的连接数。 如果更改 CPIC_MAX_CONV，必须重新启动计算机中的更改才能生效。 有关详细信息[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]绑定属性，请参阅[了解关于 BizTalk Adapter for mySAP Business Suite 绑定属性](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。  

 本主题提供有关 SAP 连接 URI 的信息，并还提供了指向其他主题的解释如何在不同的编程方案中指定连接 URI。  

## <a name="connection-uri-for-the-sap-adapter"></a>SAP 适配器的连接 URI  
 典型[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]终结点地址 URI 表示，如下所示：  

```  
scheme://userinfoparams@hostinfoparams?query_string  
```  

 终结点地址 URI 包含以下组件：  

- 方案为方案名称。  

- userinfoparams 是终结点进行用户身份验证所需的参数名称值集合。  

- hostinfoparams 是建立与主机; 的连接所需的信息例如，路径。  

- query_string 是由问号 （？） 分隔的参数的可选名称值集合。  

  终结点地址 URI 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]SAP 系统的用途通过使用 SAP 连接 URI 中指定。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]实现此连接 URI，如下所示：  

```  
sap://user=[USER_NAME];passwd=[PASSWORD];Client=[CLIENT];lang=[LANGUAGE];[UseSnc]=[True|False]@connectiontype/conndetail1/conndetail2?GwHost=[GWHOST]?GwServ=[GWSERV]?MsServ=[MSSERV]?Group=[GROUP]?ListenerDest=[LISTENERDEST]?ListenerGwHost=[LISTENERGWHOST]?ListenerGwServ=[LISTENERGWSERV]?ListenerProgramId=[LISTENERPROGRAMID]?RfcSdkTrace=[true/false]?AbapDebug=[true/false]  
```  

 以下各节中介绍了连接 URI 的组件。  

### <a name="the-sap-connection-uri-scheme"></a>SAP 连接 URI 方案  
 SAP 连接 URI 的方案是"sap"。  

### <a name="user-information-in-the-sap-connection-uri"></a>在 SAP 连接 URI 用户信息  
 SAP 连接 URI 表示为所需的用户身份验证、 客户端标识和语言规范参数的名称值集合中的用户信息 (userinfoparams)。 下表介绍了这些参数。  


| 属性 |                                                                                                                                                                                                                                                                                                                                                                                                          Description                                                                                                                                                                                                                                                                                                                                                                                                          |
|----------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|   “用户”   |                                                                                                                                                                                                            SAP 系统的用户名此值是区分大小写。 必须设置**AcceptCredentialsInUri**属性绑定到**true**连接 URI 中指定的用户名和密码。 **注意：** [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]将保留在打开 SAP 系统上的连接时输入的用户名的值的大小写。                                                                                                                                                                                                             |
|  Passwd  |                                                                                                                                                                                                       在 SAP 系统，则为用户的密码此值是区分大小写。 必须设置**AcceptCredentialsInUri**属性绑定到**true**连接 URI 中指定的用户名和密码。 **注意：** [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]将保留在打开 SAP 系统上的连接时输入的密码值的大小写。                                                                                                                                                                                                       |
|  客户端  |                                                                                                                                                                                                                                                                                                                                                                                                   SAP 系统客户端 id。                                                                                                                                                                                                                                                                                                                                                                                                   |
| 语言 |                                                                                                                                                                                                                                                                                                                                                                                                           语言。                                                                                                                                                                                                                                                                                                                                                                                                           |
|  UseSnc  | 可选参数，用于指定是否已启用 SAP 安全网络通信 (SNC)。 值可以是 True 或 False;如果为 True，则启用 SNC。 默认值为 False<br /><br /> 如果启用 SNC，还必须设置**SncPartnerName**并**SncLibrary**绑定属性。 有关详细信息，请参阅[了解关于 BizTalk Adapter for mySAP Business Suite 绑定属性](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md)。<br /><br /> 如果启用 SNC 连接 URI 包含凭据，则适配器将引发异常。 **注意：** UseSnc 连接参数是仅适用于连接类型 A 和 b。本主题稍后将详细介绍不同的连接类型和其重要性。 |

> [!NOTE]
>  必须在 SAP 连接 URI 中指定的客户端和语言。  

 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]图面**AcceptCredentialsinUri**绑定属性，以便您可以控制是否可以连接 URI 中指定 SAP 系统凭据。 这是因为凭据表示为纯文本形式的连接 URI，而这会带来固有的安全风险。 默认情况下**AcceptCredentialsInUri**绑定属性为 false，并且该适配器将引发异常，如果在连接 URI 中指定凭据。  

 某些情况下，它是需要在连接 URI; 中指定凭据例如，若要从 SAP 接收入站的操作系统时使用 WCF 服务模型或 WCF 通道模型。 可以设置**AcceptCredentialsInUri**属性设为 true，对于这种情况。 它是最佳做法，但是，若要避免提供直接在连接 URI 中的凭据。 有关如何更安全地提供 SAP 连接的凭据的详细信息，请参阅[保护 SAP 应用程序](../../adapters-and-accelerators/adapter-sap/secure-your-sap-applications.md)。  

> [!IMPORTANT]
>  如果通过 UseSnc 参数设置为 true，来启用安全网络通信 (SNC)，适配器将引发异常。  

### <a name="host-information-in-the-sap-connection-uri"></a>在 SAP 连接 URI 的主机信息  
 SAP 主机信息 (hostinfoparams) 由 SAP 连接 URI 中的下列元素： `connectiontype/conndetail1/conndetail2`。 这些参数指定有关客户端连接到 SAP 系统的详细信息。 有关 SAP 客户端连接以及到 SAP RFC 目标侦听器可以被指定 query_string 中建立的连接的详细信息的其他详细信息。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP 连接 URI 中支持以下客户端连接类型：  

- 答：应用程序主机基于在其中连接 URI 指定通过该应用程序服务器的连接[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]连接到 SAP。  

- B:负载平衡的连接 URI 中指定了消息和服务器之间的连接[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]连接到 SAP。  

- D:一种基于目标的连接，在其中连接 URI 指定连接参数包含适用于 SAP 的 saprfc.ini 文件中的目标。  

  > [!NOTE]
  > 连接类型 B 仅适用于发送端口。  在配置接收位置时，选择连接类型 A 或 d。

  下表介绍了如何在 SAP 连接 URI 中指定这些连接。  

|连接类型|Conndetail1|Conndetail2|Description|  
|---------------------|-----------------|-----------------|-----------------|  
|A|ASHOST （应用程序服务器主机）|SYSNR （SAP 系统编号）|指定应用程序基于主机的连接。 对于应用程序基于主机的连接，可以 query_string 中指定一个可选网关主机和网关服务。|  
|B|MSHOST （消息服务器主机）|R3NAME （SAP R3 名称）|指定负载均衡通过消息服务器的连接。 对于负载平衡连接，可以 query_string 中指定可选的服务器组和消息服务。|  
|D|DEST （包含 saprfc.ini 文件中的连接参数的目标）|--|指定基于目标的连接。 SAP 连接参数包含在 saprfc.ini 文件中指定的目标。 在目标中，可以指定只有一个类型和 B 类型的连接。|  

> [!NOTE]
>  如果 saprfc.ini 文件中指定的连接值，请确保该文件位于同一文件夹作为.exe 访问文件或在所需的 SAP 系统的标准位置。 有关详细信息，请参阅 SAP 文档。  

### <a name="query-information-in-the-sap-connection-uri"></a>在 SAP 连接 URI 的查询信息  
 在 SAP 连接 URI 的查询信息 (query_string) 包含可以是包括在内，以指定下列各项的可选参数：  

- 其他连接的应用程序基于主机的连接 (A) 的详细信息。  

- 附加的连接详细信息的负载平衡连接 (B)。  

- 指定通过该 SAP 系统可以发送 Rfc、 Trfc 和 Idoc 到 SAP 系统的 RFC 目标的侦听程序详细信息[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  

- 是否启用 SAP 安全网络通信 (SNC)。  

- 指定调试配置的详细信息。  

  查询参数是可选的;但是，必须为指定侦听器的详细信息[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]为 RFC 服务器。  

  下表描述了查询参数，并指示它们是有效的 SAP 连接类型。  

|       ReplTest1       | 有效的连接类型 |                                                                                                                                                                                                                                    Description                                                                                                                                                                                                                                     |
|-------------------|-----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|      GwHost       |           A           |                                                                                                                                                                                              在应用程序基于主机的连接中指定可选网关主机的名称。                                                                                                                                                                                               |
|      GwServ       |           A           |                                                                                                                                                                                             在应用程序基于主机的连接中指定可选网关服务的名称。                                                                                                                                                                                             |
|      MsServ       |           B           |                                                                                                                                                                                                 在负载平衡连接中指定可选的消息服务的名称。                                                                                                                                                                                                  |
|       Group       |           B           |                                                                                                                                                                                                 指定在负载平衡连接的应用程序服务器的可选组。                                                                                                                                                                                                 |
|   ListenerDest    |          (R)          |                                                                                                                                                                      Rfc 服务器连接中 saprfc.ini 文件中指定的可选目标。 目标必须指定 R 类型连接。                                                                                                                                                                      |
|  ListenerGwHost   |          (R)          |                                                                                      指定 rfc 服务器连接的网关主机。 此参数是可选的;但是，如果所需的 rfc 服务器连接和 LISTENERDEST 未指定或没有网关主机由 saprfc.ini 文件中的目标指定，LISTENERGWHOST 必须包含有效的网关主机。                                                                                      |
|  ListenerGwServ   |          (R)          |                                                                                 指定 rfc 服务器连接的网关服务。 此参数是可选的;但是，如果所需的 rfc 服务器连接和 LISTENERDEST 未指定或由 saprfc.ini 文件中的目标指定没有任何网关服务，然后 LISTENERGWSERV 必须包含有效的网关服务。                                                                                  |
| ListenerProgramId |          (R)          |                                                                                  指定 rfc 服务器连接的程序 id。 此参数是可选的;但是，如果所需的 rfc 服务器连接和 LISTENERDEST 未指定或由 saprfc.ini 文件中的目标指定没有任何网关服务，然后 LISTENERPROGRAMID 必须包含有效的网关服务。                                                                                   |
|    RfcSdkTrace    |          All          | 可选参数，用于指定是否启用了 RFC 库跟踪。 值可以是 True 或 False;如果为 True，则启用 RFC 库跟踪。 默认值为 False。<br /><br /> 情况下 RfcSdkTrace 参数启用的跟踪级别取决于 RFC_TRACE 环境变量。<br /><br /> -如果 RFC_TRACE 不存在，或者设置为 0，则启用最小的跟踪级别。<br />-你可以将 RFC_TRACE 设置为 1 或 2，以增加的跟踪级别。 |
|     AbapDebug     |          All          |                                                                                             可选参数，用于指定是否从调试 ABAP[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]已启用。 值可以是 True 或 False;如果为 True，则启用 ABAP 调试。 默认值为 False。 如果 AbapDebug 为 True，则打开 SAP GUI。                                                                                             |

 在查询字符串参数是 SAP 参数，并由 SAP 定义它们的值。 有关这些参数的详细信息，请参阅 SAP 文档。  

 下面显示了应用程序基于主机的连接的示例连接 URI:  

```  
sap://Client=800;lang=EN@A/YourSAPHOST/00  
```  

## <a name="connection-uri-properties-in-the-configure-adapter-dialog-box"></a>中的连接 URI 属性配置适配器对话框  
 当您连接到 SAP 系统[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]或[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]所设置的连接 URI 参数从**URI 属性**选项卡中**配置适配器**对话框。 下表显示了 URI 属性中的显示方式**URI 属性**工作表。 （URI 属性按列出它们在 URI 属性表中显示的顺序组。）  

|Category|URI 属性|URI 部分|  
|--------------|------------------|--------------|  
|应用程序服务器|应用程序服务器主机|Conndetail1 （主机信息连接类型 A）|  
|应用程序服务器|网关主机|GwHost （查询字符串）|  
|应用程序服务器|网关服务|GwServ （查询字符串）|  
|应用程序服务器|系统编号|Conndetail2 （主机信息连接类型 A）|  
|目标|目标名称|Conndetail1 （主机信息连接类型为 D）|  
|诊断|RFC 跟踪|RfcSdkTrace （查询字符串）|  
|诊断|ABAP 调试|AbapDebug （查询字符串）|  
|登录信息|客户端|客户端 (userinfoparams)|  
|登录信息|语言|语言 (userinfoparams)|  
|消息服务器|应用程序服务器组名称|组 （查询字符串）|  
|消息服务器|消息服务器主机|Conndetail1 （主机信息连接类型 B）|  
|消息服务器|消息服务器服务|MsServ （查询字符串）|  
|消息服务器|R/3 系统名称|Conndetail2 （主机信息连接类型 B）|  
|杂项|连接类型|连接类型 (主机信息：A、 B 或 D）|  
|RFC 服务器|目标名称|ListenerDest （查询字符串）|  
|RFC 服务器|网关主机|ListenerGwHost （查询字符串）|  
|RFC 服务器|网关服务|ListenerGwServ （查询字符串）|  
|RFC 服务器|程序 Id|ListenerProgramId （查询字符串）|  
|SNC|UseSnc|UseSnc （用户信息）|  

## <a name="how-to-specify-a-connection-uri-for-rfc-server-connections"></a>如何为 RFC 服务器连接中指定连接 URI。  
 若要创建通过该终结点地址[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]可以作为 RFC 服务器，则必须指定 SAP 程序 id、 SAP 网关主机，并与 SAP 系统上的 RFC 目标相对应的 SAP 网关服务。 有关如何设置上 SAP 的 RFC 目标的信息，请参阅[创建 RFC 和 RFC 目标发送来自 SAP RFC](creating-an-rfc-in-an-sap-system.md)。  

 可以在连接中两种方式之一的 URI 中指定的程序 id、 网关主机和网关服务：  

-   通过设置 ListenerGwHost、 ListenerGwServ 和 ListenerProgramId 查询参数  

-   通过 ListenerDest 查询参数设置为 saprfc.ini 文件中的目标的指定 R 类型连接。  

> [!NOTE]
>  如果 saprfc.ini 文件中指定的连接值，请确保该文件驻留在与访问该文件的.exe 相同的位置或所需的 SAP 系统的标准位置。 有关详细信息，请参阅 SAP 文档。  

 若要指定是 RFC 服务器连接的连接 URI，请使用查询字符串，如以下示例所示中指定的 RFC 目标指定常规客户端连接：  

```  
sap://Client=800;lang=EN@A/YourSAPHOST/00?ListenerGwHost=YourSAPHOST&ListenerGwServ=SAPGW00&ListenerProgramId=MyProgramId  
```  

 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用中的连接 URI 的 userinfoparams 和 hostinfoparams 一部分包含的信息来检索元数据从 SAP 系统并使用查询字符串中的侦听器参数提供的信息将自己注册为在 SAP RFC 目标的侦听器。  

## <a name="using-reserved-characters-in-the-connection-uri"></a>在连接 URI 中使用保留的字符  
 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]不支持指定连接 URI，其中含有特殊字符的任何参数值。 如果连接参数值包含特殊字符，请确保执行下列任一操作：  

- 如果在指定的 URI 中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，则必须指定其作为-处于**URI 属性**选项卡上，即，而无需使用任何转义符。 如果指定的 URI 中直接**配置 URI**字段和连接参数包含保留的字符，则必须指定连接参数使用正确的转义字符。  

- 如果创建一个发送时指定的 URI 或接收端口中的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中和连接参数包含保留的字符，则必须指定连接参数使用正确的转义字符。  

## <a name="using-the-connection-uri-to-connect-to-the-sap-system"></a>用于连接到 SAP 系统连接 URI  
 有关如何建立到 SAP 系统的连接信息时您：  

- 使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]或[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]，请参阅[连接到 Visual Studio 中的 SAP 系统](../../adapters-and-accelerators/adapter-sap/connect-to-the-sap-system-in-visual-studio.md)。  

- 配置发送端口或接收端口 （位置） 中[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]解决方案，请参阅[手动配置到 SAP 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md)。  

- 编程解决方案中使用 WCF 通道模型，请参阅[创建一个通道，使用 SAP](../../adapters-and-accelerators/adapter-sap/create-a-channel-using-sap.md)。  

- 编程解决方案中使用 WCF 服务模型，请参阅[配置客户端 SAP 系统的绑定](../../adapters-and-accelerators/adapter-sap/configure-a-client-binding-for-the-sap-system.md)。  

- 使用 WCF ServiceModel Metadata Utility Tool (svcutil.exe)，请参阅[用于 mySAP Business Suite 的 BizTalk 适配器使用 ServiceModel Metadata Utility Tool](../../adapters-and-accelerators/adapter-sap/use-the-servicemodel-metadata-utility-with-the-sap-adapter-in-biztalk.md)。  

## <a name="see-also"></a>请参阅  
 [创建指向 SAP 系统的连接](../../adapters-and-accelerators/adapter-sap/create-a-connection-to-the-sap-system.md)