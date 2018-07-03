---
title: 如何配置 HTTP 发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send ports, HTTP adapters
- HTTP adapters, send ports
- configuring [HTTP adapters], send ports
ms.assetid: 29c6868c-4570-4375-9494-08c07220eeb3
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c5195f4cae1e7968f1a691ea177ffa5d65f9653
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011062"
---
# <a name="how-to-configure-an-http-send-port"></a>如何配置 HTTP 发送端口
可以以编程方式或使用 BizTalk Server 管理控制台配置 HTTP 发送端口。  
  
## <a name="configure-an-http-send-port-programmatically"></a>以编程方式配置 HTTP 发送端口
  
 HTTP 适配器将其配置信息存储在 BizTalk 管理数据库 （也称为配置数据库）。 自定义的 XML 属性包中存储配置信息。 HTTP 适配器的初始化过程并在其运行时，服务器传递配置到适配器，如下所示：  
  
- 对于 HTTP 发送处理程序，配置信息传递到适配器通过调用**负载**方法**IPersistPropertyBag**接口。  
  
- 对于 HTTP 发送端口，配置信息传递到适配器为一组属性的消息上下文。 对 HTTP 命名空间将这些属性组合在一起。  
  
  BizTalk 浏览器对象模型可公开发送端口的 `ItransportInfo` 适配器配置接口，该接口包含 `TransportTypeData` 读/写属性。 此属性接受 HTTP 发送端口配置属性包以名称/值对 XML 字符串。 请注意，若要在 BizTalk 浏览器对象模型中设置此属性，则必须先设置上`Address`的属性**ITransportInfo**接口。  
  
  设置**TransportTypeData**的属性**ITransportInfo**接口不需要。 如果未设置，HTTP 适配器将为 HTTP 发送处理程序使用的默认值。  
  
  如果未定义重复的处理程序配置的发送端口配置属性，则使用处理程序的配置属性。 HTTP 发送处理程序不具有配置值，如果 HTTP 发送适配器将事件日志中记录错误，并会将消息移到备份适配器。  
  
  消息上下文，可以以编程方式设置配置属性。 在 BizTalk Server 业务流程调度或自定义管道组件中，可以设置这些属性。 使用这些属性时，以下规则适用：  
  
- 如果设置配置属性在业务流程或自定义管道组件在接收管道中，然后：  
  
  -   如果一条消息发送到静态发送端口，属性值将覆盖与该发送端口配置的值。  
  
  -   如果一条消息发送到动态发送端口，则不会覆盖属性值。  
  
- 如果然后在发送管道中，自定义管道组件中设置配置属性：  
  
  -   无论将消息发送到静态发送端口还是动态发送端口，都不会覆盖属性值。  
  
  下表列出了可在 HTTP 在 BizTalk 浏览器对象模型中设置的配置属性发送位置。  
  
|属性名称|类型|Description|限制|注释|  
|-------------------|----------|-----------------|------------------|--------------|  
|**RequestTimeout**|xs:int|超时期限的等待来自服务器的响应。 如果设置为零 (0)，在系统计算超时值根据请求消息的大小。|**最小值：** 0<br /><br /> **最大值：** MAX_LONG|**默认值：** 0|  
|**ContentType**|xs:string|请求消息的内容类型|**最小长度：** 0<br /><br /> **最大长度：** 256|**默认值：** Text/XML|  
|**MaxRedirects**|xs:int|最多的 HTTP 适配器可以将请求重定向的次数。|**最小值：** 0<br /><br /> **最大值：** 10|**默认值：** 5|  
|**UseHandlerProxySettings**|xs:boolean|指定 HTTP 发送端口是否将使用进行发送处理程序的代理配置。|InclusionThresholdSetting|**默认值：** ，则返回 True<br /><br /> 为 true 时，发送端口将使用在处理程序级别指定的代理设置。 为 false 时，发送适配器将使用发送端口上指定的代理信息。|  
|**UseProxy**|xs:boolean|指定 HTTP 适配器是否将使用代理服务器。 代理服务器可以由所有 HTTP 发送端口共享。|InclusionThresholdSetting|**默认值：** False<br /><br /> 如果忽略此属性**UseHandlerProxySettings**是**True**。|  
|**代理名称**|xs:string|指定代理服务器名称。|**最小长度：** 0<br /><br /> **最大长度：** 256|**默认值：** 空<br /><br /> HTTP 发送适配器将忽略此属性，如果**UseHandlerProxySettings**属性设置为**True**。 否则，HTTP 发送适配器将使用此属性仅当**UseProxy**是**True**。 此属性是必需的如果**UseProxy**是**True**。|  
|**ProxyPort**|xs:int|指定代理服务器端口。|**最小值：** 0<br /><br /> **最大值：** 65535|**默认值：** 80<br /><br /> HTTP 发送适配器将忽略此属性，如果**UseHandlerProxySettings**是**True**。 否则，HTTP 发送适配器将使用此属性仅当**UseProxy**是**True**。 此属性是必需的如果**UseProxy**是**True**。|  
|**ProxyUsername**|xs:string|指定与代理服务器进行身份验证的用户名。|**最小长度：** 0<br /><br /> **最大长度：** 256|**默认值：** 空<br /><br /> HTTP 发送适配器将忽略此属性，如果**UseHandlerProxySettings**是**True**。 否则，HTTP 发送适配器将使用此属性仅当**UseProxy**是**True**。|  
|**ProxyPassword**|xs:string|指定与代理服务器进行身份验证的用户密码。|**最小长度：** 0<br /><br /> **最大长度：** 256|**默认值：** 空<br /><br /> HTTP 发送适配器将忽略此属性，如果**UseHandlerProxySettings**是**True**。 否则，HTTP 发送适配器将使用此属性仅当**UseProxy**是**True**。|  
|**AuthenticationScheme**|xs:string|要对目标服务器使用的身份验证类型。|InclusionThresholdSetting|**有效的值：**<br /><br /> -   **匿名 （默认值）**<br />-   **基本**<br />-   **摘要**<br />-   **Kerberos**|  
|**用户名**|xs:string|要用于服务器的身份验证的用户名称。|**最小长度：** 0<br /><br /> **最大长度：** 256|**默认值：** 空<br /><br /> 如果选择此值是必需**基本**或**摘要**身份验证。 HTTP 适配器将忽略此属性的值，如果**UseSSO**是**True**。|  
|**密码**|xs:string|要用于服务器的身份验证的用户密码。|**最小长度：** 0<br /><br /> **最大长度：** 256|**默认值：** 空<br /><br /> 如果选择此值是必需**基本**或**摘要**身份验证。 如果忽略此属性的值**UseSSO**是**True**。|  
|**EnableChunkedEncoding**|xs:boolean|指定 chunked 编码由 HTTP 适配器|InclusionThresholdSetting|**默认值：**<br /><br /> True|  
|**证书**|xs:string|客户端 SSL 证书的指纹。|**最小长度：** 0<br /><br /> **最大长度：** 59|**默认值：** 空|  
|**UseSSO**|xs:boolean|指定是否将为发送端口使用 SSO。|InclusionThresholdSetting|**默认值：** False|  
|**AffiliateApplicationName**|xs:string|若要使用的 SSO 关联应用程序的名称。|**最小长度：** 0<br /><br /> **最大长度：** 256|**默认值：** 空<br /><br /> 需要**UseSSO**是**True**。|  
  
 下面的代码显示了要用于设置这些属性的 XML 字符串：  
  
```  
<CustomProps>  
   <ContentType vt="8">text/xml</ContentType>  
   <RequestTimeout vt="3">0</RequestTimeout>  
   <MaxRedirects vt="3">5</MaxRedirects>  
   <UseHandlerProxySettings vt="8">-1</UseHandlerProxySettings>  
   <UseProxy vt="8">-1</UseProxy>  
   <ProxyName vt="8">sdfsd</ProxyName>  
   <ProxyPort vt="3">80</ProxyPort>  
   <ProxyUsername vt="8">Somename</ProxyUsername>  
   <ProxyPassword vt="8">Somepassword</ProxyPassword>  
   <AuthenticationScheme vt="8">Basic</AuthenticationScheme>  
   <Username vt="8">Somename</Username>  
   <Password vt="8">Somepassword</Password>  
   <EnableChunkedEncoding vt="11">1</EnableChunkedEncoding>  
   <Certificate vt="8">AAAA BBBB CCCC DDDD</Certificate>  
   <UseSSO vt="11">0</UseSSO>  
   <AffiliateApplicationName vt="8">Name</AffiliateApplicationName>  
</CustomProps>  
```  
  
## <a name="configure-an-http-send-port-with-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台配置 HTTP 发送端口
  
 在 BizTalk Server 管理控制台中，可以设置 HTTP 发送端口适配器变量。 如果没有为发送端口设置属性的默认发送处理程序将使用 BizTalk Server 管理控制台中设置的值。  
  
> [!NOTE]
>  本主题中所述的配置属性共有的单向和请求-响应 HTTP 发送端口。  
  
1.  在 BizTalk Server 管理控制台中，创建新的发送端口或双击某个现有发送端口以对其进行修改。 请参阅[如何创建发送端口](../core/how-to-create-a-send-port2.md)有关详细信息。 配置所有发送端口选项，并指定**HTTP**有关**类型**选项**传输**部分上**常规**选项卡。  
  
2.  上**常规**选项卡上，在**传输**部分中，单击**配置**旁边**类型**。  
  
3.  在中**HTTP 传输属性**对话框中，在**常规**选项卡上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**目标 URL**|必需的。 指定用于发送 HTTP 请求的地址。 包含附加在基本 URL 后面的查询字符串。<br /><br /> **类型：** 字符串<br /><br /> **最大长度：** 256<br /><br /> 有关详细信息，请参阅[对目标 URL 属性的限制](../core/restrictions-on-the-destination-url-property.md)。 **注意：** 的 URI 发送端口或接收位置不能超过 256 个字符。|  
    |**启用 chunked 编码**|指定使用 Chunked 编码。 如果启用了此选项，则 HTTP 适配器将使用最大块大小为 8 KB 的 HTTP Chunked 编码。 如果 HTTP 发送处理程序配置为隐式禁用 chunked 编码**使用代理**。<br /><br /> **类型：** 布尔<br /><br /> **默认值：** ，则返回 True|  
    |**请求超时 （秒）**|以秒为单位指定 HTTP/HTTPS 传输的超时时间。 如果 HTTP 适配器在此时间内未收到响应，则服务将记录错误并根据重试基础结构重新提交消息。<br /><br /> 如果此属性设置为零 (0)，则 BizTalk 消息引擎将根据请求消息的大小来计算超时值。 如果未提供任何值，则使用处理程序的值。<br /><br /> **类型：** 长<br /><br /> **最小值：** 0<br /><br /> **最大值：** MAX_LONG|  
    |**最大重定向**|指定对发送的消息所允许的最大重定向次数。<br /><br /> **默认值：** 5<br /><br /> **类型：** Int<br /><br /> **最小值：** 0<br /><br /> **最大值：** 10|  
    |**内容类型**|指定请求消息的内容类型。<br /><br /> 如果未设置此值，则使用处理程序的值。<br /><br /> **类型：** 字符串<br /><br /> **最小长度：** 0<br /><br /> **最大长度：** 256|  
  
4.  在中**HTTP 传输属性**对话框中，在**代理 （处理程序替代）** 选项卡上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**使用处理程序的默认代理配置**|指定发送端口配置必须使用 HTTP 发送处理程序为指定的代理设置。<br /><br /> 这是默认设置。|  
    |**不使用代理**|指定是否 HTTP 发送处理程序使用代理服务器。<br /><br /> 如果选择此项，则此发送端口的 HTTP 发送处理程序不使用代理服务器。|  
    |**使用代理**|指定是否 HTTP 发送处理程序使用代理服务器。<br /><br /> 如果选择此项，则 HTTP 发送处理程序使用代理服务器。|  
    |**Server**|指定此发送端口的代理服务器地址。<br /><br /> 此属性仅需要一个值，如果**使用代理**处于选中状态。<br /><br /> **类型：** 字符串<br /><br /> **最小长度：** 0<br /><br /> **最大长度：** 256|  
    |**端口**|指定此发送端口的代理服务器端口。<br /><br /> 此属性仅需要一个值，如果**使用代理**处于选中状态。<br /><br /> **默认值：** 80<br /><br /> **类型：** 长<br /><br /> **最小值：** 0<br /><br /> **最大值：** 65535|  
    |**用户名**|指定用于对代理服务器进行验证的用户名。<br /><br /> 此属性仅需要一个值，如果**使用代理**处于选中状态。<br /><br /> **类型：** 字符串<br /><br /> **最小长度：** 0<br /><br /> **最大长度：** 256|  
    |**密码**|指定用于对代理服务器进行验证的用户密码。<br /><br /> 此属性仅需要一个值，如果**使用代理**处于选中状态。<br /><br /> **类型：** 字符串<br /><br /> **最小长度：** 0<br /><br /> **最大长度：** 256|  
  
5.  在中**HTTP 传输属性**对话框中，在**身份验证**选项卡上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**身份验证类型**|指定目标服务器使用的验证类型。<br /><br /> 有效选项为：<br /><br /> -   **匿名**<br />-   **基本**<br />-   **摘要**<br />-   **Kerberos**<br /><br /> **默认值：** 匿名|  
    |**凭据**|指定要使用的凭据类型。<br /><br /> 只有**身份验证类型**是**基本**或**摘要**。<br /><br /> 有效选项为：<br /><br /> -   **不使用单一登录**<br />     **用户名：**<br />     对目标服务器进行验证所使用的用户名。 如果**身份验证类型**属性是**Anonymous**或**Kerberos**，将禁用此选项。 此属性需要一个值，如果**基本**或**摘要**选择，并且不使用企业单一登录。<br />     **最小长度：** 0<br />     **最大长度：** 256<br />     **密码：**<br />     对目标服务器进行验证所使用的密码。 如果**身份验证类型**属性是**Anonymous**或**Kerberos**，将禁用此选项。 此属性需要一个值，如果**基本**或**摘要**选择，并且不使用单一登录。<br />     **最小长度：** 0<br />     **最大长度：** 256<br />-   **使用单一登录**<br />     指定是否使用单一登录检索客户端凭据，以便在目标服务器上进行验证。<br />     **关联应用程序**<br />     指定要使用单一登录关联应用程序。<br />     选择要使用单一登录的应用程序。<br />     **最小长度：** 0<br />     **最大长度：** 256|  
    |**SSL 客户端证书指纹**|指定用于建立安全套接字层 (SSL) 连接的客户端证书的指纹。<br /><br /> **最小长度：** 0<br /><br /> **最大长度：** 59|  
  
6.  单击**确定**并**确定**次以保存设置。  
  
## <a name="see-also"></a>请参阅  
 [配置 HTTP 发送端口](../core/configuring-an-http-send-port.md)