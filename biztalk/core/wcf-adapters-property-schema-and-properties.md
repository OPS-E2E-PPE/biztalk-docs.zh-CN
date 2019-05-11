---
title: WCF 适配器属性架构和属性 |Microsoft Docs
ms.custom: ''
ms.date: 02/09/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2093745e-86c0-4276-a7cc-a0187391ca4a
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10781e8743eeea68ff0be8993b3588d5ecd204d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399145"
---
# <a name="wcf-adapters-property-schema-and-properties"></a>WCF 适配器属性架构和属性
阅读有关 WCF 适配器属性架构中升级的属性。 WCF 适配器将值分配给可以在应用程序中使用的属性。 WCF 适配器还提供了一种机制来编写，而不是升级到 BizTalk 消息上下文中，自定义属性和升级到 BizTalk 消息上下文的自定义属性的机制。 有关更多详细信息，请参阅[SOAP 标头发布 WCF 服务与](../core/soap-headers-with-published-wcf-services.md)。  

## <a name="promoted-properties"></a>升级的属性  
**Namespace**： http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties  

#### <a name="action"></a>操作
指定**SOAPAction**为传出消息的标头字段。 可以通过两种方式指定此值： 单一操作格式和操作映射格式。 如果将此属性设置在单一操作格式 — 例如， http://contoso.com/Svc/Op1 — **SOAPAction**标头传出消息将始终设置为此属性中指定的值。

如果将此属性设置采用操作映射格式，传出**SOAPAction**标头由**BTS。操作**上下文属性。 例如，如果此属性设置为以下 XML 格式和**BTS。操作**属性设置为 Op1，WCF 发送适配器使用 `http://contoso.com/Svc/Op1` 为传出**SOAPAction**标头。

```
<BtsActionMapping>
<Operation Name="Op1" Action="http://contoso.com/Svc/Op1">
<Operation Name="Op2" Action="http://contoso.com/Svc/Op2">
</BtsActionMapping>
```

如果传出消息来自某个业务流程端口，业务流程实例动态设置**BTS。操作**使用的端口的操作名称的属性。 如果使用基于内容的路由来路由传出消息，则可以设置**BTS。操作**管道组件中的属性。
从传入消息以单一操作格式自动升级此属性。

键入：String  
默认值：空字符串  
适用范围：所有 WCF 发送适配器

#### <a name="affiliateapplicationname"></a>AffiliateApplicationName
指定要使用的企业单一登录 (SSO) 关联应用程序。 此属性是必需的如果**UseSSO**属性设置为**True**。 

键入：String  
默认值：空字符串  
适用范围：所有 WCF 都发送适配器*除*Wcf-netnamedpipe 适配器

#### <a name="algorithmsuite"></a>AlgorithmSuite
指定消息加密和密钥包装算法。 这些算法与“安全策略语言”(WS-SecurityPolicy) 规范中指定的算法一致。

有关适合的值的详细信息**AlgorithmSuite**属性，请参阅**算法套件**中的属性**Wcf-nettcp 传输属性对话框，发送，安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。

键入：String  
默认值：**Basic256**  
适用范围： 

- Wcf-basichttp 适配器
- Wcf-netmsmq 适配器
- Wcf-nettcp 适配器
- Wcf-wshttp 适配器

#### <a name="bindingconfiguration"></a>BindingConfiguration
指定 XML 字符串与 **\<绑定\>** 元素来配置不同类型的预定义的 Windows Communication Foundation (WCF) 提供的绑定。 有关系统提供的绑定和自定义绑定的详细信息，请参阅另请参阅中的相应主题。

例如：

```
<binding name="wsHttpBinding" transactionFlow="true">
<security><message clientCredentialType="UserName"></security>
</binding>
```

键入：String  
默认值：空字符串  
适用范围：Wcf-custom 适配器，Wcf-customisolated 适配器

#### <a name="bindingtype"></a>BindingType
指定要用于终结点的绑定的类型。 有关适合的值的详细信息**BindingType**属性，请参阅**绑定类型**中的属性**Wcf-custom 传输属性对话框，发送，绑定**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。

键入：String  
默认值：空字符串  
适用范围：Wcf-custom 适配器，Wcf-customisolated 适配器

#### <a name="clientcertificate"></a>ClientCertificate
指定此发送端口对服务进行身份验证的 X.509 证书的指纹。 此属性是必需的如果**ClientCredentialsType**属性设置为**证书**。 要用于此属性的证书必须安装到**我**将存储在**当前用户**位置。

键入：String  
默认值：空字符串  
适用范围： 

- Wcf-basichttp 发送适配器
- Wcf-wshttp 发送适配器
- Wcf-nettcp 发送适配器
- Wcf-netmsmq 发送适配器

#### <a name="closetimeout"></a>CloseTimeout
指定一个时间跨度值来表示为完成信道关闭操作提供的时间间隔。

键入：String  
默认值：00:01:00  
适用范围：所有 WCF 适配器*除*Wcf-custom 和 Wcf-customisolated

#### <a name="customdeadletterqueue"></a>CustomDeadLetterQueue
指定使用的完全限定的 URI **net.msmq**方案的每个应用程序的死信队列，消息已过期或失败传输或传递的放置位置的位置。 例如，net.msmq: //localhost/deadletterqueuename。 死信队列是发送应用程序的已用于放置传递失败的过期消息的队列管理器上的队列。 此属性是必需的如果**DeadLetterQueue**属性设置为**自定义**。

键入：String  
默认值：空字符串  
适用范围：Wcf-netmsmq 发送适配器

#### <a name="deadletterqueue"></a>DeadLetterQueue
指定要从中传输失败传递到应用程序的消息的死信队列。 有关传递到死信队列的消息的详细信息，请参阅**Wcf-netmsmq 传输属性对话框，发送，绑定**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。

键入：String  
默认值：**系统**  
适用范围：Wcf-netmsmq 发送适配器

#### <a name="disablelocationonfailure"></a>DisableLocationOnFailure
指定是否禁用由于接收管道故障或路由故障而导致入站处理失败的接收位置。 你可能想要将此属性设置为 **，则返回 True**时接收位置可以禁用和拒绝服务 (DoS) 并不是问题。

例如：  
- Wcf-custom 适配器：当**BindingType**属性设置为**netMsmqBinding**。
- Wcf-custom 适配器：当**BindingType**属性设置为**customBinding**，并**BindingConfiguration**属性配置为使用依赖于队列传输的自定义通道如 MSMQ。
- Wcf-customisolated 适配器：当**BindingType**属性设置为**customBinding**，并**BindingConfiguration**属性配置为使用依赖于队列传输的自定义通道如 MSMQ
- Wcf-netmsmq 适配器

键入：Boolean  
默认值：**False**  
适用范围：  
- Wcf-netmsmq 接收适配器
- WCF 自定义接收适配器
- Wcf-customisolated 接收适配器

#### <a name="enabletransaction"></a>EnableTransaction
此属性的效果各不相同，具体取决于 WCF 适配器。 有关此属性的详细信息，请参阅中每个 WCF 适配器的操作指南主题[WCF 适配器](../core/wcf-adapters.md)。

键入：Boolean  
适用范围： 

- Wcf-wshttp 适配器
- Wcf-nettcp 适配器
- Wcf-netnamedpipe 适配器
- Wcf-netmsmq 适配器

#### <a name="endpointbehaviorconfiguration"></a>EndpointBehaviorConfiguration
指定 XML 字符串与 **\<行为\>** 元素 **\<endpointBehaviors\>** 元素来配置的行为设置WCF 终结点。 有关详细信息 **\<endpointBehaviors\>** 元素，请参阅另请参阅中的相应主题。

例如： 
```
<behavior name="sampleBehavior"><callbackTimeouts/></behavior>
```

键入：String  
默认值：空字符串  
适用范围：WCF 自定义发送适配器

#### <a name="establishsecuritycontext"></a>EstablishSecurityContext
指定安全通道是否建立安全会话。 安全会话在交换应用程序消息之前建立安全上下文令牌 (SCT)。

键入：Boolean  
默认值：True  
应用于：Wcf-wshttp 适配器

#### <a name="fromaddress"></a>FromAddress
指示通过其发送传入 WCF 消息的源终结点地址。 从传入消息，则会自动升级该属性。

键入：String  
适用范围：所有 WCF 适配器*除*Wcf-netmsmq 发送适配器
  
#### <a name="headers"></a>标头
指定用于提供除 URI 外的其他寻址信息的终结点引用。 使用此属性时，此属性必须具有\<**标头**\>元素作为根元素。 所有地址标头必须位于内部\<**标头**\>元素。 此属性将自动提升为传入消息。

例如：
```
<headers>
<Region xmlns="Uri">"String"</Region>
<Member xmlns="Uri">"String"</Member> 
</headers>
```

键入：String  
适用范围：所有 WCF 适配器
  
#### <a name="identity"></a>标识
指定接收位置提供或发送端口预期的服务标识。 可以为指定的值**标识**属性不同的安全配置而异。 这些设置使客户端进行身份验证服务。 在客户端和服务之间的握手过程中，Windows Communication Foundation (WCF) 基础结构将确保服务的标识匹配的客户端的值。

例如：
```
<identity>
<userPrincipalName value="username@contoso.com"/>
</identity>
```

键入：String  
默认值：空字符串  
适用范围：所有 WCF 适配器

#### <a name="inboundbodylocation"></a>InboundBodyLocation
指定数据选择 soap**正文**传入 WCF 消息的元素。 有关如何使用详细信息**InboundBodyLocation**属性，请参阅[WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。

键入：String  
默认值：UseBodyElement  

    Applicable values are:  
        - UseBodyElement: Use the content of the SOAP **Body** element of an incoming message to create the BizTalk message body part. If the **Body** element has more than one child element, only the first element becomes the BizTalk message body part.
        - UseEnvelope: Create the BizTalk message body part from the entire SOAP **Envelope** of an incoming message.
        - UseBodyPath: Use the body path expression in the **InboundBodyPathExpression** property to create the BizTalk message body part. The body path expression is evaluated against the immediate child element of the SOAP **Body** element of an incoming message. This property is valid only for solicit-response ports.  

适用范围：所有 WCF 适配器*除*Wcf-netmsmq 发送  

#### <a name="inboundbodypathexpression"></a>InboundBodyPathExpression
指定正文路径表达式以标识用于创建 BizTalk 消息正文部分的传入消息的特定部分。 针对 SOAP 的直接子元素计算此正文路径表达式**正文**传入消息的节点。 如果此正文路径表达式返回多个节点，则只选择第一个节点作为 BizTalk 消息正文部分。 此属性是必需的如果**InboundBodyLocation**属性设置为**UseBodyPath**。 有关如何使用详细信息**InboundBodyPathExpression**属性，请参阅[WCF 适配器属性架构和属性](../core/wcf-adapters-property-schema-and-properties.md)。

键入：String  
默认值：空字符串  
适用范围：所有 WCF 适配器*除*Wcf-netmsmq 发送适配器

#### <a name="inboundheaders"></a>InboundHeaders
使用**InboundHeaders**属性访问传入 WCF 消息的 SOAP 标头。 WCF 适配器将复制所有 SOAP 标头值入站消息中到此属性，包括自定义 SOAP 标头和标准 SOAP 标头，WCF 基础结构用于诸如 Ws-addressing、 Ws-security 和 WS-AtomicTransaction。 上下文属性中包含的值是一个包含 XML 数据字符串\<**标头**\>根元素和传入的 SOAP 标头复制为子元素的\< **标头**\>元素。 有关如何对访问 SOAP 标头用于 WCF 适配器的详细信息，请参阅 SDK 示例中，将自定义 SOAP 标头用于 WCF 适配器中，从[ http://go.microsoft.com/fwlink/?LinkId=79960 ](http://go.microsoft.com/fwlink/?LinkId=79960)。

键入：String  
适用范围：所有 WCF 适配器*除*Wcf-netmsmq 发送适配器

#### <a name="inboundnodeencoding"></a>InboundNodeEncoding
指定 WCF 接收适配器将使用由中指定的正文路径表达式标识的节点进行解码的编码类型**InboundBodyPathExpression**。 此属性是必需的如果**InboundBodyLocation**属性设置为**UseBodyPath**。

键入：String  
默认值：XML  

    Applicable values are:  
        - Base64: Base64 encoding
        - Hex: Hexadecimal encoding
        - String: Text encoding - UTF-8
        - XML: The WCF adapters create the BizTalk message body with the outer XML of the node selected by the body path expression in **InboundBodyPathExpression**.  

适用范围：所有 WCF 适配器*除*Wcf-netmsmq 发送适配器

#### <a name="isfault"></a>IsFault
指示是否接收 SOAP 错误消息。 从传入消息，则会自动升级该属性。 

**注意**  
**IsFault**属性不能用于检查接收的消息传输错误，例如 HTTP 404 （文件或找不到目录） 错误。

键入：Boolean  
适用范围：所有 WCF 适配器*除*Wcf-netmsmq 发送适配器

#### <a name="leasetimeout"></a>LeaseTimeout
指定活动的池连接的最大生存期。 在指定的时间过后，则关闭连接后当前请求提供服务。

Wcf-nettcp 适配器利用[NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087)类与终结点进行通信。 使用时[NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087)在负载平衡方案中，请考虑缩短默认租约超时值。有关负载平衡时使用的详细信息[NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087)，请参阅另请参阅中的相应主题。

键入：String  
默认值：00:05:00  
适用范围：Wcf-nettcp 接收适配器  

#### <a name="maxconcurrentcalls"></a>MaxConcurrentCalls
指定针对单个服务实例的并发调用的数目。 超出此限制的调用将在队列中排队。 将该值设置为 0 等效于将它设置为 **Int32.MaxValue**。 

**注意**  
使用跟踪配置文件，不能在 BAM 主导入数据库中跟踪此属性。 

键入：Integer  
默认值：200  
适用范围：所有 WCF 都接收适配器*除*Wcf-custom 和 Wcf-customisolated 适配器

#### <a name="maxconnections"></a>MaxConnections
指定的最大侦听器可以拥有等待接受的应用程序的连接数。 当超过此配额值时，会删除新的传入连接而不是等待接受。 

**注意**  
由于这是一个适配器处理程序属性，则此属性不能配置管道组件和业务流程中。 

**注意**  
使用跟踪配置文件，不能在 BAM 主导入数据库中跟踪此属性。 

键入：Integer  
默认值：10  
适用范围：Wcf-netnamedpipe 适配器，Wcf-nettcp 适配器  

#### <a name="maxreceivedmessagesize"></a>MaxReceivedMessageSize
指定的最大大小，以字节为单位，可以在网络上接收的消息 （包括标头）。 消息的大小受为每条消息分配的内存量的限制。 你可以使用此属性来降低受拒绝服务 (DoS) 攻击的可能性。

键入：Integer  
默认值：65536  
适用范围： 
- Wcf-basichttp 适配器
- Wcf-wshttp 适配器
- Wcf-nettcp 适配器
- Wcf-netnamedpipe 适配器
- Wcf-netmsmq 接收适配器

#### <a name="messageclientcredentialtype"></a>MessageClientCredentialType
指定使用基于消息的安全性对客户端执行验证时所用的凭据类型。

每个 WCF 适配器不同的值。 有关详细信息**MessageClientCredentialType**属性，每个 WCF 适配器中，请参阅操作指南主题[WCF 适配器](../core/wcf-adapters.md)。

键入：String  
适用范围： 
- Wcf-basichttp 适配器
- Wcf-wshttp 适配器
- Wcf-nettcp 适配器
- Wcf-netnamedpipe 适配器

#### <a name="messageencoding"></a>MessageEncoding
指定用于对 SOAP 消息进行编码的编码器。

键入：String  
默认值：Text  

    Applicable values: 
        - Text: Use a text message encoder
        - Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder  

适用范围：Wcf-basichttp 适配器，Wcf-wshttp 适配器


#### <a name="msmqauthenticationmode"></a>MsmqAuthenticationMode
指定 MSMQ 传输必须如何验证消息。

键入：String  
默认值：**WindowsDomain**  
    有关适合的值的详细信息**MsmqAuthenticationMode**属性，请参阅**MSMQ 身份验证模式**中的属性**Wcf-netmsmq 传输属性对话框框中，发送，安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
适用范围：Wcf-netmsmq 适配器  

#### <a name="msmqencryptionalgorithm"></a>MsmqEncryptionAlgorithm
指定消息队列管理器之间传输消息时要使用在网络上进行消息加密算法。 提供了该属性才**MsmqProtectionLevel**属性设置为**EncryptAndSign**。

键入：String  
默认值：**RC4Stream**  

    Applicable values are: RC4Stream, AES

适用范围：Wcf-netmsmq 适配器  

#### <a name="msmqprotectionlevel"></a>MsmqProtectionLevel
指定在 MSMQ 传输级别保护消息。

键入：String  
默认值：**签名**  

    Applicable values are:
        - None: No protection
        - Sign: Messages are signed
        - EncryptAndSign: Messages are encrypted and signed. To use this protection level, you must enable **Active Directory Integration** for **MSMQ**  

适用范围：Wcf-netmsmq 适配器  

#### <a name="msmqsecurehashalgorithm"></a>MsmqSecureHashAlgorithm
指定要用于计算消息摘要的哈希算法。 此属性不可用如果**MsmqProtectionLevel**属性设置为**None**。

键入：String  
默认值：**SHA1**  

    Applicable values are: MD5, SHA1, SHA25, SHA512  

适用范围：Wcf-netmsmq 适配器  

#### <a name="negotiateservicecredential"></a>NegotiateServiceCredential
指定服务凭据在带外，客户端设置还是通过协商过程由客户端从服务中获取。 这种协商是正常消息交换的前提。

如果**MessageClientCredentialType**属性等于**None**，**用户名**，或者**证书**，设置此属性设置为**False**意味着服务证书可在带外客户端，并且客户端需要指定服务证书。 此模式是可与实现 Ws-trust 和 Ws-secureconversation 的 SOAP 堆栈交互操作。

如果**MessageClientCredentialType**属性设置为**Windows**，此属性设置为**False**指定基于 Kerberos 的身份验证。 这意味着，客户端和服务必须是相同 Kerberos 域的一部分。 此模式是可与实现 Kerberos 令牌配置文件 （如 OASIS WSS tc 中定义） 以及 Ws-trust 和 Ws-secureconversation 的 SOAP 堆栈交互操作。

当此属性是 **，则返回 True**，会引起通过 SOAP 消息传送 SPNego 交换的.NET SOAP 协商。

键入：Boolean  
默认值：True  
适用范围：Wcf-wshttp 适配器  

#### <a name="opentimeout"></a>OpenTimeout
指定一个时间跨度值来表示为完成信道打开操作提供的时间间隔。 

**注意**  
使用跟踪配置文件，不能在 BAM 主导入数据库中跟踪此属性。 

键入：String  
默认值：00:01:00  
适用范围：所有 WCF 适配器*除*Wcf-custom 和 Wcf-customisolated 适配器

#### <a name="orderedprocessing"></a>OrderedProcessing
指定是否按顺序处理消息。 选中此属性后，此接收位置会按序送达的消息传递中具有的 BizTalk 消息传送或业务流程发送端口一起使用时**按序送达**选项设置为`True`。 有关详细信息**按序送达**选项，请参阅另请参阅中的相应主题。

此属性是在以下情况下适用：
- Wcf-custom 适配器：当**BindingType**属性设置为**netMsmqBinding**
- Wcf-custom 适配器：当**BindingType**属性设置为**customBinding**，并**BindingConfiguration**属性配置为使用依赖于传输的自定义通道支持如 MSMQ 的按序的送达。
- Wcf-customisolated 适配器：当**BindingType**属性设置为**customBinding**，并**BindingConfiguration**属性配置为使用依赖于传输的自定义通道支持按序的送达。
- Wcf-netmsmq 适配器

键入：String  
默认值：**False**  
适用范围： 
- Wcf-netmsmq 接收适配器
- WCF 自定义接收适配器
- Wcf-customisolated 接收适配器

#### <a name="outboundbodylocation"></a>OutboundBodyLocation
指定数据选择 soap**正文**的传出 WCF 消息的元素。 有关如何使用详细信息**OutboundBodyLocation**属性，请参阅[WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。

键入：String  
默认值：UseBodyElement  

    Applicable values are:
        - UseBodyElement: Use the BizTalk message body part to create the content of the SOAP **Body** element for an outgoing message
        - **UseTem****plate**: Use the template supplied in the OutboundXMLTemplate property to create the content of the SOAP **Body** element for an outgoing message

适用范围：所有 WCF 适配器*除*Wcf-netmsmq 接收适配器

#### <a name="outboundcustomheaders"></a>OutboundCustomHeaders
指定传出消息的自定义 SOAP 标头。 使用此属性时，该属性必须具有\<**标头**\>元素作为根元素。 所有自定义 SOAP 标头必须位于内部\<**标头**\>元素。 如果自定义 SOAP 标头值为空字符串，则必须分配\<**标头**\>\</**标头**\>或\<**标头**\>给此属性。 有关如何通过 WCF 适配器将 SOAP 标头的详细信息，请参阅 SDK 示例中，将自定义 SOAP 标头用于 WCF 适配器中，从[ http://go.microsoft.com/fwlink/?LinkId=79960 ](http://go.microsoft.com/fwlink/?LinkId=79960)。

键入：String  
适用范围：所有 WCF 适配器*除*Wcf-netmsmq 接收适配器

#### <a name="outboundxmltemplate"></a>OutboundXmlTemplate
指定内容的 SOAP XML 格式的模板**正文**传出的消息的元素。 此属性是必需的如果**OutboundBodyLocation**属性设置为**UseTemplate**。 有关如何使用详细信息**OutboundXMLTemplate**属性，请参阅[WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。

键入：String  
默认值：空字符串  
适用范围：所有 WCF 适配器*除*Wcf-netmsmq 接收适配器

#### <a name="password"></a>Password
指定要用于目标服务器的身份验证的密码时**UseSSO**属性设置为**False**。

键入：String  
默认值：空字符串  
适用范围：所有 WCF 都发送适配器*除*Wcf-netnamedpipe 适配器  

#### <a name="propagatefaultmessage"></a>PropagateFaultMessage
指定是路由还是挂起在出站处理失败的消息。 此属性是仅对要求响应端口有效。 

**注意**  
使用跟踪配置文件，不能在 BAM 主导入数据库中跟踪此属性。

键入：Boolean  
默认值：**True**  

    Applicable values are:  
        - True: Route the message that fails outbound processing to a subscribing application (such as another receive port or orchestration schedule)
        - False: Suspend failed messages and generate a negative acknowledgment (NACK)

适用范围：所有 WCF 都发送适配器*除*Wcf-netmsmq 适配器
  
#### <a name="proxyaddress"></a>ProxyAddress
指定代理服务器的地址。 使用**https**或**http**具体取决于安全配置的方案。 此地址可以跟一个冒号和端口号。 该属性是必需的如果**ProxyToUse**属性设置为**UserSpecified** （例如， http://127.0.0.1:8080)

键入：String  
默认值：空字符串  
适用范围：Wcf-basichttp 发送适配器、 Wcf-wshttp 发送适配器  

#### <a name="proxypassword"></a>ProxyPassword
指定要用于在指定的代理服务器的密码**ProxyAddress**属性。

键入：String  
默认值：空字符串  
适用范围：Wcf-basichttp 发送适配器、 Wcf-wshttp 发送适配器

#### <a name="proxytouse"></a>ProxyToUse
指定要用于传出 HTTP 通信的代理服务器。

键入：String  
默认值：**无**  

    Applicable values are:  
        - None: Do not use a proxy server for this send port
        - Default: Use the proxy settings in the send handler hosting this send port
        - UserSpecified: Use the proxy server specified in the **ProxyAddress** property

适用范围：Wcf-basichttp 发送适配器、 Wcf-wshttp 发送适配器  

#### <a name="proxyusername"></a>ProxyUserName
指定要用于在指定的代理服务器的用户名**ProxyAddress**属性。 该属性是必需的如果**ProxyToUse**属性设置为**UserSpecified**。

有关此属性的详细信息，请参阅[如何配置 Wcf-wshttp 发送端口](../core/how-to-configure-a-wcf-wshttp-send-port.md)并[如何配置 Wcf-basichttp 发送端口](http://msdn.microsoft.com/library/acdb50fa-57fe-4657-9561-b6b2f4919c7f)。

键入：String  
适用范围：Wcf-basichttp 发送适配器、 Wcf-wshttp 发送适配器

#### <a name="replytoaddress"></a>ReplyToAddress
指示答复终结点地址与通过请求-响应接收的传入消息相对应的传出 WCF 消息接收位置。 从传入消息，则会自动升级该属性。

键入：String  
默认值：空字符串  
适用范围：所有 WCF 适配器*除*Wcf-netmsmq 适配器

#### <a name="securitymode"></a>SecurityMode
指定使用的安全类型。 每个 WCF 适配器不同的值。 有关详细信息**SecurityMode**属性，每个 WCF 适配器中，请参阅操作指南主题[WCF 适配器](../core/wcf-adapters.md)。 

**注意**  
使用跟踪配置文件，不能在 BAM 主导入数据库中跟踪此属性。

键入：String  
适用范围：所有 WCF 适配器*除*Wcf-custom 和 Wcf-customisolated 适配器

#### <a name="sendtimeout"></a>SendTimeout
指定一个时间跨度值来表示为完成发送操作提供的时间间隔。 此值指定完成，整个交互的时间跨度，即使响应方返回发送大消息。

键入：String  
默认值：00:01:00  
适用范围：所有 WCF 适配器*除*Wcf-custom 和 Wcf-customisolated 适配器

#### <a name="servicebehaviorconfiguration"></a>ServiceBehaviorConfiguration
指定 XML 字符串与 **\<行为\>** 元素 **\<serviceBehaviors\>** 元素来配置 WCF 行为设置服务。 有关详细信息 **\<serviceBehaviors\>** 元素，请参阅另请参阅中的相应主题。

例如：

```
<behavior name="SampleServiceBehavior">
<serviceAuthorization principalPermissionMode="UseAspNetRoles"/>
<serviceCredentials>
<serviceCertificate findValue="539d9ab3089bb6dc187fa7dbb382cf01f8d78f5f" storeLocation="CurrentUser" x509FindType="FindByThumbprint"/>
</serviceCredentials>
<serviceMetadata httpGetEnabled="true"/>
</behavior>
```

键入：String  
默认值：空字符串  
适用范围：WCF 自定义接收适配器，Wcf-customisolated 适配器

#### <a name="servicecertificate"></a>ServiceCertificate
如果此属性用于接收位置，指定接收位置的客户端使用服务进行身份验证的 X.509 证书的指纹。 要用于此属性的证书必须安装到**我**将存储在**当前用户**位置。

如果此属性用于发送端口，指定用于对此发送端口将消息发送到该服务进行身份验证的 X.509 证书的指纹。 要用于此属性的证书必须安装到**其他人**将存储在**本地计算机**位置。

键入：String  
默认值：空字符串  
适用范围： 
- Wcf-basichttp 适配器
- Wcf-netmsmq 适配器
- Wcf-wshttp 适配器
- Wcf-nettcp 接收适配器

#### <a name="suspendmessageonfailure"></a>SuspendMessageOnFailure
指定是否将由于接收管道故障或路由故障而导致入站处理失败的请求消息挂起。

键入：Boolean  
默认值：True  
适用范围：所有 WCF 都接收适配器  

#### <a name="textencoding"></a>TextEncoding
指定要使用该绑定上发出消息编码的字符集时**MessageEncoding**属性设置为**文本**。 

**注意**  
使用跟踪配置文件，不能在 BAM 主导入数据库中跟踪此属性。 

键入：String  
默认值： utf-8  

    Applicable values are:  
        - unicodeFFF: Unicode BigEndian encoding
        - utf-16: 16-bit encoding
        - utf-8: 8-bit encoding

适用范围：Wcf-basichttp 适配器，Wcf-wshttp 适配器
  
#### <a name="timetolive"></a>TimeToLive
指定在将过期并放入死信队列之前消息多长时间是有效的时间跨度。 若要确保具有时效性的消息执行操作不会过时，通过发送端口进行处理之前，设置此属性。 不使用时此发送端口指定的时间间隔内队列中的消息被认为已过期。 已过期的消息发送到称为死信队列的特殊队列。 死信队列的位置设置与**DeadLetterQueue**属性。

键入：String  
默认值：1.00:00:00  
适用范围：Wcf-netmsmq 发送适配器

#### <a name="to"></a>若要
指定 WCF 发送端口发送的传出 WCF 消息的目标终结点地址。

键入：String  
默认值：空字符串  
适用范围：所有 WCF 发送适配器  

#### <a name="transactionprotocol"></a>TransactionProtocol
指定要与此绑定一起使用的事务协议。 此属性是必需的如果**EnableTransaction**属性设置为**True**。

键入：String  
默认值：OleTransaction  

    Applicable values are: OleTransaction, WS-AtomicTransaction

适用范围：Wcf-netnamedpipe 适配器，Wcf-nettcp 适配器  

#### <a name="transportclientcredentialtype"></a>TransportClientCredentialType
指定要执行发送端口验证时要使用的凭据类型。 每个 WCF 适配器不同的值。 有关详细信息**TransportClientCredentialType**属性，每个 WCF 适配器中，请参阅操作指南主题[WCF 适配器](../core/wcf-adapters.md)。

键入：String  
适用范围：Wcf-basic 适配器、 WCF NetTcp 适配器、 Wcf-wshttp 适配器  

#### <a name="transportprotectionlevel"></a>TransportProtectionLevel
指定 TCP 传输级别的安全性。 消息签名降低了在消息传输过程中第三方对消息进行篡改的风险。 加密为传输过程提供了数据级保密功能。

键入：String  
默认值：**EncryptAndSign**  

    Applicable values are:  
        - None: No protection
        - Sign: Messages are signed
        - EncryptAndSign: Messages are encrypted and signed

适用范围：Wcf-nettcp 适配器，Wcf-netnamedpipe 适配器  

#### <a name="username"></a>UserName
指定要用于目标服务器的身份验证的用户名时**UseSSO**属性设置为**False**。 无需使用此属性的域 \ 用户格式。

键入：String  
默认值：空字符串  
适用范围：所有 WCF 都发送适配器*除*Wcf-netnamedpipe 适配器

#### <a name="usesourcejournal"></a>UseSourceJournal
指定此发送端口处理的消息副本是否应存储在源日记队列。

键入：Boolean  
默认值：False  
适用范围：Wcf-netmsmq 发送适配器  

#### <a name="usesso"></a>UseSSO
指定是否使用单一登录检索客户端凭据的目标服务器的身份验证。 

**注意**  
使用跟踪配置文件，不能在 BAM 主导入数据库中跟踪此属性。 

键入：Boolean  
默认值：False  
适用范围：所有 WCF 都发送适配器*除*Wcf-netnamedpipe 适配器

#### <a name="referencedbindings"></a>ReferencedBindings
指定引用的绑定配置 **bindingConfiguration** 的属性 **\<颁发者\>** 元素 **wsFederationHttpBinding** 并**customBinding**， 表示安全令牌服务 (STS) 颁发安全令牌。 有关详细信息 **\<颁发者\>** 元素中，请参阅本主题中，"\<颁发者\>"在[http://go.microsoft.com/fwlink/?LinkId=83476](http://go.microsoft.com/fwlink/?LinkId=83476)。

绑定信息，包括**\<颁发者\>** 元素**wsFederationHttpBinding**并**customBinding**可以是通过配置**BindingConfiguration** Wcf-custom 和 Wcf-customisolated 适配器的属性。 此属性的引用的绑定配置的所有必须置于的窗体[\<绑定\>](http://go.microsoft.com/fwlink/?LinkID=80878)元素。 

**注意**  
**BindingConfiguration**的属性**\<颁发者\>** 元素必须引用此属性中的有效绑定名称。 

**注意**  
**\<颁发者\>** 中引用的绑定配置元素还可以对此属性中的其他绑定配置引用如果此引用链不会使循环依赖项。 

例如： 

```
WCF.BindingConfiguration = @"<wsFederationHttpBinding>
<binding name=""sampleBinding"">
<security mode=""Message"">
<message issuedKeyType=""AsymmetricKey"">
<issuer address=""http://www.contoso.com/samplests"" binding=""wsFederationHttpBinding"" bindingConfiguration=""**contosoSTSBinding**""/>
</message>
</security>
</binding>
</wsFederationHttpBinding>";
WCF.ReferencedBinding =@"<bindings>
<wsFederationHttpBinding>
<binding name=""**contosoSTSBinding**"">
<security mode=""Message"">
<message negotiateServiceCredential=""false"">
<issuer address=""http://northwind.com/samplests"" bindingConfiguration=""**northwindBinding**"" binding=""wsHttpBinding"">
</issuer>
</message>
</security>
</binding>
</wsFederationHttpBinding>
<wsHttpBinding>
<binding name=""**northwindBinding**"">
<security mode=""Message"">
<message clientCredentialType=""Certificate""/>
</security>
</binding>
</wsHttpBinding>
</bindings>" 
``` 

**注意**  
**ReferencedBinding**属性不能包含中使用的绑定配置**BindingConfiguration**属性。

键入：String  
默认值：空字符串  
适用范围：Wcf-custom 适配器，Wcf-customisolated 适配器
  
## <a name="see-also"></a>请参阅  
 [WCF 适配器](../core/wcf-adapters.md)   
 [\<行为\>的\<endpointBehaviors\>](http://go.microsoft.com/fwlink/?LinkId=80879)   
 [\<bindings\>](http://go.microsoft.com/fwlink/?LinkId=80878)   
 [\<行为\>的\<serviceBehaviors\>](http://go.microsoft.com/fwlink/?LinkId=81095)   
 [按序送达消息](../core/ordered-delivery-of-messages.md)   
 [负载平衡](http://go.microsoft.com/fwlink/?LinkId=81089)
