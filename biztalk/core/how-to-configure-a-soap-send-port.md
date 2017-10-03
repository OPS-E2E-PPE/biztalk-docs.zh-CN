---
title: "如何配置 SOAP 发送端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SOAP adapters, send ports
- SOAP adapters, code samples
- code samples, SOAP adapters
- configuring [SOAP adapters], code samples
- configuring [SOAP adapters], send ports
- send ports, SOAP adapters
ms.assetid: 3a0622f4-d25d-4449-a063-d8ba217e9729
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3cb290feb7b61cf3d2ccdeffb6c795d88c537b4e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-a-soap-send-port"></a>如何配置 SOAP 发送端口
可以通过编程方式或使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台来配置 SOAP 发送端口。  
  
 **如何以编程方式配置 SOAP 发送端口**  
  
 BizTalk 资源管理器对象模型公开了用于发送端口名为的特定于适配器的接口**ITransportInfo**具有**TransportTypeData**读/写属性。 此属性以 XML 字符串的名称-值对形式接受 SOAP 发送端口配置属性包。 请注意，设置此属性中的 BizTalk 资源管理器对象模型必须设置**OutboundTransportLocation**属性**ITransportInfo**接口第一次。  
  
 **TransportTypeData**属性**ITransportInfo**界面不是必需。 如果未设置该属性，则适配器将使用 SOAP 发送端口配置的默认值，如下表所示。  
  
 下表列出了可在 BizTalk 浏览器对象模型中为 SOAP 发送端口设置的配置属性：  
  
|属性名称|类型|Description|  
|-------------------|----------|-----------------|  
|**URI**|字符串|在部署服务器上包含 Web Services 的虚拟目录。|  
|**用户名**|字符串|为访问目标 Web Services 而指定的用户名。<br /><br /> 默认值： 空白|  
|**密码**|字符串|要用于服务器的身份验证的用户密码。<br /><br /> 默认值： 空白|  
|**ClientCertificate**|字符串|客户端 SSL 证书的指纹。<br /><br /> 默认值： 空白|  
|**AffiliateApplicationName**|字符串|用于兑换客户端凭据票证的 SSO 应用程序的名称。<br /><br /> **AffiliateApplicationName**互斥到**用户名**和**密码**对。<br /><br /> 默认值： 空白|  
|**UseProxy**|Boolean|指示 SOAP 发送端口是否使用代理服务器访问目标 Web Services。 代理服务器可由所有的 SOAP 发送端口共享。<br /><br /> 默认值：False|  
|**ProxyAddress**|字符串|用于 Web Services 调用的 HTTP 代理的地址。<br /><br /> 默认值： 空白|  
|**友好**|Integer|用于 Web Services 调用的 HTTP 代理的端口。<br /><br /> 默认值： 空白|  
|**ProxyUsername**|字符串|为代理使用的用户名。<br /><br /> 默认值： 空白|  
|**代理**|字符串|为代理使用的密码。<br /><br /> 默认值： 空白|  
  
 下面的代码显示了用于设置这些属性的格式：  
  
```  
<CustomProps>  
   <URI vt="8"/>  
   <ClientCertificate vt="8"/>  
   <Password vt="8">Encrypted</Password>  
   <ProxyAddress vt="8"/>  
   <ProxyPassword vt="8">Encrypted</ProxyPassword>  
   <ProxyPort vt="3"/>  
   <ProxyUsername vt="8"/>  
   <UseProxy vt="11"/>  
   <Username vt="8"/>  
   <AffiliateApplicationName vt="8"/>  
</CustomProps>  
```  
  
 **如何使用 BizTalk Server 管理控制台配置 SOAP 发送端口**  
  
 可以在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中设置 SOAP 发送端口适配器变量。 如果未设置发送端口的属性，则使用在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中设置的默认发送处理程序值。  
  
### <a name="to-configure-variables-for-a-soap-send-port"></a>配置 SOAP 发送端口的变量  
  
1.  在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中，创建一个新的发送端口或双击某个现有发送端口以对其进行修改。 有关详细信息，请参阅[如何创建发送端口](../core/how-to-create-a-send-port2.md)。 配置所有发送端口选项并指定**SOAP**为**类型**选项**传输**部分**常规**选项卡。  
  
2.  上**常规**选项卡上，在**传输**旁边部分**类型**，单击**配置**。  
  
3.  在**SOAP 传输属性**对话框中，在**常规**选项卡上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**Web 服务 URL**|指定要调用的 Web Services 的地址。 **注意：**对要发送的 URI 端口或接收位置不能超过 256 个字符。|  
    |**身份验证**|指示要调用的 Web Services 所采用的验证方法。<br /><br /> 选项：<br /><br /> -   **匿名。** 默认设置。<br />-   **基本。** SOAP 连接以纯文本格式发送用户名和密码。<br />-   **Digest。** SOAP 连接以加密格式发送密码。<br />-   **NTLM。** 用户名和密码都不通过 SOAP 连接发送。 SOAP 适配器始终为此验证类型使用运行 SOAP 发送适配器的进程的凭据。|  
    |**凭据**|指定要使用的凭据类型。<br /><br /> 仅可用**身份验证类型**是**基本**或**摘要式**。<br /><br /> 选项：<br /><br /> -   **不使用单一登录**<br />     **用户名**<br />     对目标服务器进行验证所使用的用户名。 如果**身份验证类型**属性是**匿名**或**NTLM**，将禁用此选项。 此属性需要一个值，如果**基本**或**摘要式**选择，而不用于企业单一登录。<br />     最小长度：0<br />     最大长度：256<br />     **密码**<br />     对目标服务器进行验证所使用的密码。 如果**身份验证类型**属性是**匿名**或**NTLM**，将禁用此选项。 此属性需要一个值，如果**基本**或**摘要式**选择，并且未使用单一登录。<br />     最小长度：0<br />     最大长度：256<br />-   **使用单一登录**<br />     指定是否使用单一登录检索客户端凭据，以便在目标服务器上进行验证。<br />     **关联应用程序**<br />     指定用于单一登录的关联应用程序。 有关填充此列表的信息，请参阅[SSO Affiliate 应用程序](../core/sso-affiliate-applications.md)。<br />     最小长度：0<br />     最大长度：256|  
    |**客户端证书指纹**|指定用于建立连接的客户端证书的指纹。<br /><br /> 示例： 01 23 45 67 89 AB CD EF 01 23 45 67 89 AB CD EF 01 23 45 67<br /><br /> 最小长度：0<br /><br /> 最大长度： 59|  
  
4.  在**SOAP 传输属性**对话框中，在**代理**选项卡上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**使用处理程序的默认代理配置**|指定发送端口代理处理程序配置。 如果为 true，则该端口将使用在处理程序级别指定的代理设置。 为 false 时，发送适配器将使用指定在发送端口上的代理信息。<br /><br /> 默认设置为 true。|  
    |**不使用代理服务器**|表示 SOAP 发送处理程序是否使用代理服务器。|  
    |**使用代理**|表示 SOAP 发送处理程序是否使用代理服务器。 代理服务器可由所有的 SOAP 发送端口共享。|  
    |**Server**|指定代理服务器的名称。<br /><br /> 此属性仅需要一个值，如果**使用代理**选择。<br /><br /> 类型：字符串<br /><br /> 最小长度：0<br /><br /> 最大长度：256|  
    |**端口**|指定 SOAP 发送处理程序使用的端口。<br /><br /> 此属性仅需要一个值，如果**使用代理**选择。<br /><br /> 默认值：80<br /><br /> 类型： 长<br /><br /> 最小值： 0<br /><br /> 最大值： 65535**注意：**指定值为 0，则指示要使用默认值，该值是端口 80。|  
    |**用户名**|指定用于身份验证的用户名。 如果你使用 Windows 集成身份验证，用户名将包括域，**域 \ 用户名**。 如果使用基本或摘要式身份验证的用户名不包括**域\\**。<br /><br /> 此属性仅需要一个值，如果**使用代理**选择。<br /><br /> 类型：字符串<br /><br /> 最小长度：0<br /><br /> 最大长度：256|  
    |**密码**|指定用于身份验证的密码。<br /><br /> 此属性仅需要一个值，如果**使用代理**选择。<br /><br /> 类型：字符串<br /><br /> 最小长度：0<br /><br /> 最大长度：256|  
  
5.  在**SOAP 传输属性**对话框中，在**Web 服务**选项卡上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**业务流程 Web 端口**|指定要在中列出的 Web 服务 URL 中使用 Web 服务公开**常规**选项卡。<br /><br /> 这是默认设置。|  
    |**程序集名称**|指定包含 Web Services 代理的程序集的名称。 您可以通过单击“浏览”按钮找到程序集来填充此字段。 选择程序集之后，此框将填充程序集的完全限定名称。 **注意：**指定程序集必须存在于所有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在运行时的 s。|  
    |**类型名称**|指定包含要调用的 Web 方法的类的名称。 可以从程序集内包含的类型列表选择此项。|  
    |**方法名称**|在列表框中指定的方法之一或选择"指定"的选项更高版本。 如果选择选项“以后指定”，则必须以其他方式（如管道组件）设置 Web 方法。 在此方案中，必须将 web 方法写入到 Soap 适配器**MethodName**上下文属性。|  
    |**SOAP 1.2**|指定此项可生成将支持 SOAP 1.2 协议的代理代码。 如果不选择此选项，则会生成符合 SOAP 1.1 的代理代码。<br /><br /> 默认值： 清除|  
  
6.  单击**确定**和**确定**再次以保存设置。  
  
## <a name="see-also"></a>另请参阅  
 [发布 Web 服务](../core/publishing-web-services.md)