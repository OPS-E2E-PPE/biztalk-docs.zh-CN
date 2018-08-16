---
title: WCF 适配器属性架构和属性 |Microsoft 文档
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
ms.openlocfilehash: 04bb48f54347eabeb886d91fa245bae18c34de55
ms.sourcegitcommit: 50798e04fdcaf5dce5288aa18608e2a981b162fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2018
ms.locfileid: "29139293"
---
# <a name="wcf-adapters-property-schema-and-properties"></a>WCF 适配器属性架构和属性
阅读有关 WCF 适配器属性架构中提升的属性。 WCF 适配器对应用程序中可使用的属性进行赋值。 WCF 适配器还提供了一种用于将自定义属性写入 BizTalk 消息上下文但不进行升级的机制，以及一种用于将自定义属性升级到 BizTalk 消息上下文的机制。 有关更多详细信息，请参阅[发布 WCF 服务使用的 SOAP 标头](../core/soap-headers-with-published-wcf-services.md)。  

## <a name="promoted-properties"></a>提升的属性  
**Namespace:** http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties  

#### <a name="action"></a>操作
指定 **SOAPAction** 传出消息的标头字段。 你可以通过两种方式指定此值︰ 单个操作格式和操作映射格式。 如果将此属性设置中的单个操作格式-例如，http://contoso.com/Svc/Op1- **SOAPAction**标头为传出消息始终设置为此属性中指定的值。

如果在操作映射格式，传出中设置此属性 **SOAPAction** 标头由 **BTS。操作** 上下文属性。 例如，如果此属性设置为以下 XML 格式和 **BTS。操作** 属性设置为 Op1，WCF 发送适配器使用 `http://contoso.com/Svc/Op1` 为传出 **SOAPAction** 标头。

```
<BtsActionMapping>
<Operation Name="Op1" Action="http://contoso.com/Svc/Op1">
<Operation Name="Op2" Action="http://contoso.com/Svc/Op2">
</BtsActionMapping>
```

如果传出消息来自的业务流程端口时，动态设置业务流程实例 **BTS。操作** 与操作名称的端口的属性。 如果使用基于内容的路由路由传出消息，则可以设置 **BTS。操作** 管道组件中的属性。
此属性将自动从传入消息以单一操作格式进行升级。

類型：字串  
默认值： 空字符串  
适用于： 所有 WCF 都发送适配器

#### <a name="affiliateapplicationname"></a>AffiliateApplicationName
指定用于企业单一登录 (SSO) 的关联应用程序。 此属性是必需的如果 **UseSSO** 属性设置为 **True**。 

類型：字串  
默认值： 空字符串  
适用于： 所有 WCF 都发送适配器*除*WCF NetNamedPipe 适配器

#### <a name="algorithmsuite"></a>AlgorithmSuite
指定訊息加密和 Key Wrap 演算法。 這些演算法會對應到安全性原則語言 (WS-SecurityPolicy) 規格中所指定的演算法。

有关详细信息有关的适用值**AlgorithmSuite**属性，请参阅**算法套件**中的属性**Wcf-nettcp 传输属性对话框中，发送，安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。

類型：字串  
默认值︰ **Basic256**  
适用范围： 

- WCF BasicHttp 适配器
- WCF-NetMsmq 适配器
- WCF-NetTcp 适配器
- WCF-WSHttp 适配器

#### <a name="bindingconfiguration"></a>BindingConfiguration
指定使用的 XML 字符串**\<绑定\>** 元素来配置不同类型的预定义的绑定所提供的 Windows Communication Foundation (WCF)。 有关系统提供的绑定和自定义绑定的详细信息，请参阅“另请参见”部分中的相应主题。

例如：

```
<binding name="wsHttpBinding" transactionFlow="true">
<security><message clientCredentialType="UserName"></security>
</binding>
```

類型：字串  
默认值： 空字符串  
适用于： WCF 自定义适配器，WCF CustomIsolated 适配器

#### <a name="bindingtype"></a>BindingType
指定要用于终结点的绑定类型。 有关详细信息有关的适用值**BindingType**属性，请参阅**绑定类型**中的属性**WCF 自定义传输属性对话框中，发送，绑定**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。

類型：字串  
默认值： 空字符串  
适用于： WCF 自定义适配器，WCF CustomIsolated 适配器

#### <a name="clientcertificate"></a>ClientCertificate
指定用于向服务验证此发送端口的 X.509 证书的指纹。 此属性是必需的如果 **ClientCredentialsType** 属性设置为 **证书**。 此属性使用的证书必须安装到 **我** 将存储在 **当前用户** 位置。

類型：字串  
默认值： 空字符串  
适用范围： 

- WCF-BasicHttp 发送适配器
- WCF-WSHttp 发送适配器
- WCF NetTcp 发送适配器
- WCF NetMsmq 发送适配器

#### <a name="closetimeout"></a>CloseTimeout
指定時間值，表示可供完成通道關閉作業的時間間隔。

類型：字串  
預設值：00:01:00  
适用于： 所有 WCF 适配器*除*WCF 自定义和 WCF CustomIsolated

#### <a name="customdeadletterqueue"></a>CustomDeadLetterQueue
指定完全限定的 URI 与 **net.msmq** 方案的每个应用程序死信队列，消息已过期或者传输或传递失败的存放位置。 例如 net.msmq://localhost/deadLetterQueueName。 死信队列是发送应用程序的队列管理器上的一种队列，用于未能送达的到期的消息。 此属性是必需的如果 **DeadLetterQueue** 属性设置为 **自定义**。

類型：字串  
默认值： 空字符串  
适用于： WCF NetMsmq 发送适配器

#### <a name="deadletterqueue"></a>DeadLetterQueue
指定死信队列，未能传输到应用程序的消息将传输到死信队列中。 有关传递到死信队列的消息的详细信息，请参阅**WCF NetMsmq 传输属性对话框中，发送，绑定**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。

類型：字串  
默认值︰ **系统**  
适用于： WCF NetMsmq 发送适配器

#### <a name="disablelocationonfailure"></a>DisableLocationOnFailure
指定是否禁用由于接收管道故障或路由故障而导致入站处理失败的接收位置。 你可能想要将此属性设置为 **True** 时接收位置可以被禁用，而且拒绝服务 (DoS) 并不是问题。

例如：  
- WCF 自定义适配器： 时**BindingType**属性设置为**netMsmqBinding**。
- WCF 自定义适配器： 时**BindingType**属性设置为**customBinding**，和**BindingConfiguration**属性配置为使用自定义通道依赖如 MSMQ 排队传输。
- WCF CustomIsolated 适配器： 时**BindingType**属性设置为**customBinding**，和**BindingConfiguration**属性配置为使用自定义通道利用如 MSMQ 排队传输
- WCF-NetMsmq 适配器

类型︰ Boolean  
默认值︰ **False**  
适用范围：  
- WCF NetMsmq 接收适配器
- WCF 自定义接收适配器
- WCF-CustomIsolated 接收适配器

#### <a name="enabletransaction"></a>EnableTransaction
此属性的效果依 WCF 适配器的不同而变化。 有关此属性的详细信息，请参阅操作指南主题中的每个 WCF 适配器[WCF 适配器](../core/wcf-adapters.md)。

类型︰ Boolean  
适用范围： 

- WCF-WSHttp 适配器
- WCF-NetTcp 适配器
- WCF NetNamedPipe 适配器
- WCF-NetMsmq 适配器

#### <a name="endpointbehaviorconfiguration"></a>EndpointBehaviorConfiguration
指定使用的 XML 字符串**\<行为\>** 元素**\<endpointBehaviors\>** 元素来配置的行为设置WCF 终结点。 有关详细信息**\<endpointBehaviors\>** 元素，请参阅另请参阅中的相应主题。

例如： 
```
<behavior name="sampleBehavior"><callbackTimeouts/></behavior>
```

類型：字串  
默认值： 空字符串  
适用于： WCF 自定义发送适配器

#### <a name="establishsecuritycontext"></a>EstablishSecurityContext
指定安全通道是否建立安全会话。 安全会话在交换应用程序消息之前建立安全上下文标记 (SCT)。

类型︰ Boolean  
默认值：True  
应用于： WCF WSHttp 适配器

#### <a name="fromaddress"></a>FromAddress
指示发送传入 WCF 消息的源终结点地址。 该属性将自动提升从传入消息。

類型：字串  
适用于： 所有 WCF 适配器*除*WCF NetMsmq 发送适配器
  
#### <a name="headers"></a>标头
指定用于提供除 URI 外的其他寻址信息的终结点引用。 当使用此属性时，此属性必须具有\<**标头**\>作为根元素的元素。 所有地址标头必须放置在\<**标头**\>元素。 该属性自动从传入消息进行升级。

例如：
```
<headers>
<Region xmlns="Uri">"String"</Region>
<Member xmlns="Uri">"String"</Member> 
</headers>
```

類型：字串  
适用于： 所有 WCF 适配器
  
#### <a name="identity"></a>标识
指定接收位置提供或发送端口预期的服务的标识。 可以为指定的值 **标识** 属性而异的安全配置。 这些设置使客户端能够对服务进行身份验证。 在客户端与服务进行握手的过程中，Windows Communication Foundation (WCF) 基础结构将确保服务的标识与客户端的值保持一致。

例如：
```
<identity>
<userPrincipalName value="username@contoso.com"/>
</identity>
```

類型：字串  
默认值： 空字符串  
适用于： 所有 WCF 适配器

#### <a name="inboundbodylocation"></a>InboundBodyLocation
指定 SOAP 数据选择 **正文** 传入 WCF 消息的元素。 有关如何使用**InboundBodyLocation**属性，请参阅[为 WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。

類型：字串  
默认值： UseBodyElement  

    Applicable values are:  
        - UseBodyElement: Use the content of the SOAP **Body** element of an incoming message to create the BizTalk message body part. If the **Body** element has more than one child element, only the first element becomes the BizTalk message body part.
        - UseEnvelope: Create the BizTalk message body part from the entire SOAP **Envelope** of an incoming message.
        - UseBodyPath: Use the body path expression in the **InboundBodyPathExpression** property to create the BizTalk message body part. The body path expression is evaluated against the immediate child element of the SOAP **Body** element of an incoming message. This property is valid only for solicit-response ports.  

适用于： 所有 WCF 适配器*除*WCF NetMsmq 发送  

#### <a name="inboundbodypathexpression"></a>InboundBodyPathExpression
指定正文路径表达式以标识传入消息中用于创建 BizTalk 消息正文部分的特定部分。 此正文路径表达式针对 SOAP 的即时子元素进行评估 **正文** 传入消息的节点。 如果此正文路径表达式返回多个节点，则只选择第一个节点作为 BizTalk 消息正文部分。 此属性是必需的如果 **InboundBodyLocation** 属性设置为 **UseBodyPath**。 有关如何使用**InboundBodyPathExpression**属性，请参阅[WCF 适配器属性架构和属性](../core/wcf-adapters-property-schema-and-properties.md)。

類型：字串  
默认值： 空字符串  
适用于： 所有 WCF 适配器*除*WCF NetMsmq 发送适配器

#### <a name="inboundheaders"></a>InboundHeaders
使用 **InboundHeaders** 属性访问传入的 WCF 消息的 SOAP 标头。 WCF 适配器将入站消息中的所有 SOAP 标头值复制到此属性，其中包括 WCF 基础结构用于诸如 WS-Addressing、WS-Security 和 WS-AtomicTransaction 的自定义 SOAP 标头和标准 SOAP 标头。 上下文属性中包含的值是一个包含与 XML 数据字符串\<**标头**\>根元素和传入的 SOAP 标头将复制作为子元素的\< **标头**\>元素。 有关如何对访问 SOAP 标头与 WCF 适配器的详细信息，请参阅 SDK 示例中，使用自定义 SOAP 标头与 WCF 适配器中，从 [http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960)。

類型：字串  
适用于： 所有 WCF 适配器*除*WCF NetMsmq 发送适配器

#### <a name="inboundnodeencoding"></a>InboundNodeEncoding
指定的编码 WCF 接收适配器使用要解码识别由正文路径表达式中指定的节点类型 **InboundBodyPathExpression**。 此属性是必需的如果 **InboundBodyLocation** 属性设置为 **UseBodyPath**。

類型：字串  
默认值： XML  

    Applicable values are:  
        - Base64: Base64 encoding
        - Hex: Hexadecimal encoding
        - String: Text encoding - UTF-8
        - XML: The WCF adapters create the BizTalk message body with the outer XML of the node selected by the body path expression in **InboundBodyPathExpression**.  

适用于： 所有 WCF 适配器*除*WCF NetMsmq 发送适配器

#### <a name="isfault"></a>IsFault
指示是否接收 SOAP 错误消息。 该属性将自动提升从传入消息。 

**请注意**  
**IsFault**属性不能用于检查收到的消息，例如 HTTP 404 （文件或找不到目录） 错误的传输错误。

类型︰ Boolean  
适用于： 所有 WCF 适配器*除*WCF NetMsmq 发送适配器

#### <a name="leasetimeout"></a>LeaseTimeout
指定活动的池连接的最大生存期。 指定的时间过后，则连接将关闭后当前的请求已得到处理。

WCF NetTcp 适配器利用 [NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087) 类与终结点进行通信。 使用时 [NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087) 在负载平衡方案中，请考虑减少的默认租约超时值。有关负载平衡时使用的详细信息[NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087)，请参阅另请参阅中的相应主题。

類型：字串  
默认值：00:05:00  
适用于： WCF NetTcp 接收适配器  

#### <a name="maxconcurrentcalls"></a>MaxConcurrentCalls
指定對單一服務執行個體的並行呼叫數目。 超出上限的呼叫將排入佇列。 將這個值設定為 0 的效果與設定為 **Int32.MaxValue**相同。 

**请注意**  
在 BAM 主导入数据库中无法使用跟踪配置文件跟踪此属性。 

类型： 整数  
默认值：200  
适用于： 所有 WCF 都接收适配器*除*的 WCF 自定义和 WCF CustomIsolated 适配器

#### <a name="maxconnections"></a>MaxConnections
指定监听程序可以拥有的等待应用程序接受的最大连接数。 在超过此配额值时，将删除新的传入连接，而不是等待接受这些连接。 

**请注意**  
由于这是一个适配器处理程序属性，因此该属性无法在管道组件和业务流程中进行配置。 

**请注意**  
在 BAM 主导入数据库中无法使用跟踪配置文件跟踪此属性。 

类型： 整数  
默认值： 10  
适用于： WCF NetNamedPipe 适配器，WCF NetTcp 适配器  

#### <a name="maxreceivedmessagesize"></a>MaxReceivedMessageSize
指定网络上可接收的消息的最大大小（包括标头），以字节为单位。 消息的大小受为每条消息分配的内存量的限制。 您可以使用這個屬性來限制遭受拒絕服務 (DoS) 攻擊的風險程度。

类型： 整数  
預設值：65536  
适用范围： 
- WCF BasicHttp 适配器
- WCF-WSHttp 适配器
- WCF-NetTcp 适配器
- WCF NetNamedPipe 适配器
- WCF NetMsmq 接收适配器

#### <a name="messageclientcredentialtype"></a>MessageClientCredentialType
指定使用基于消息的安全性对客户端执行验证时所用的凭据类型。

适用值因每个 WCF 适配器的不同而异。 有关详细信息**MessageClientCredentialType**属性，请参阅操作指南主题中的每个 WCF 适配器[WCF 适配器](../core/wcf-adapters.md)。

類型：字串  
适用范围： 
- WCF BasicHttp 适配器
- WCF-WSHttp 适配器
- WCF-NetTcp 适配器
- WCF NetNamedPipe 适配器

#### <a name="messageencoding"></a>MessageEncoding
指定用來為 SOAP 訊息編碼的編碼器。

類型：字串  
默认值︰ 文本  

    Applicable values: 
        - Text: Use a text message encoder
        - Mtom: Use a Message Transmission Organization Mechanism 1.0 (MTOM) encoder  

适用于： WCF BasicHttp 适配器，WCF WSHttp 适配器


#### <a name="msmqauthenticationmode"></a>MsmqAuthenticationMode
指定如何通过 MSMQ 传输对消息进行验证。

類型：字串  
默认值︰ **WindowsDomain**  
    有关详细信息有关的适用值**MsmqAuthenticationMode**属性，请参阅**MSMQ 身份验证模式**中的属性**WCF NetMsmq 传输属性对话框框中，发送，安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
适用于： WCF NetMsmq 适配器  

#### <a name="msmqencryptionalgorithm"></a>MsmqEncryptionAlgorithm
指定在消息队列管理器之间传输消息时，将在网络上使用的消息加密算法。 此属性才可用才 **而 MsmqProtectionLevel** 属性设置为 **EncryptAndSign**。

類型：字串  
默认值︰ **RC4Stream**  

    Applicable values are: RC4Stream, AES

适用于： WCF NetMsmq 适配器  

#### <a name="msmqprotectionlevel"></a>MsmqProtectionLevel
指定消息在 MSMQ 传输一级的保护方式。

類型：字串  
默认值︰ **登录**  

    Applicable values are:
        - None: No protection
        - Sign: Messages are signed
        - EncryptAndSign: Messages are encrypted and signed. To use this protection level, you must enable **Active Directory Integration** for **MSMQ**  

适用于： WCF NetMsmq 适配器  

#### <a name="msmqsecurehashalgorithm"></a>MsmqSecureHashAlgorithm
指定使用哈希算法计算消息摘要。 此属性不可用如果 **而 MsmqProtectionLevel** 属性设置为 **无**。

類型：字串  
默认值︰ **SHA1**  

    Applicable values are: MD5, SHA1, SHA25, SHA512  

适用于： WCF NetMsmq 适配器  

#### <a name="negotiateservicecredential"></a>NegotiateServiceCredential
指定是在带外客户端提供服务凭据，还是通过协商过程从服务将服务凭据提供给客户端。 这种协商是正常消息交换开始前的准备过程。

如果 **MessageClientCredentialType** 属性等于 **无**, ，**用户名**, ，或 **证书**, ，此属性设置为 **False** 意味着服务证书位于带外客户端和客户端需要指定服务证书。 此模式可与实现 WS-Trust 和 WS-SecureConversation 的 SOAP 堆栈交互操作。

如果 **MessageClientCredentialType** 属性设置为 **Windows**, ，此属性设置为 **False** 指定基于 Kerberos 的身份验证。 这意味着客户端和服务必须属于同一个 Kerberos 域。 此模式可与实现 Kerberos 标记配置文件（在 OASIS WSS TC 中定义）以及 WS-Trust 和 WS-SecureConversation 的 SOAP 堆栈交互操作。

当此属性是 **True**, ，会引起通过 SOAP 消息隧道 SPNego 交换的.NET SOAP 协商。

类型︰ Boolean  
默认值：True  
适用于： WCF WSHttp 适配器  

#### <a name="opentimeout"></a>OpenTimeout
指定時間值，表示可供完成通道開啟作業的時間間隔。 

**请注意**  
在 BAM 主导入数据库中无法使用跟踪配置文件跟踪此属性。 

類型：字串  
預設值：00:01:00  
适用于： 所有 WCF 适配器*除*的 WCF 自定义和 WCF CustomIsolated 适配器

#### <a name="orderedprocessing"></a>OrderedProcessing
指定是否按顺序处理消息。 当选中此属性时，此接收位置与拥有的 BizTalk 消息传递或业务流程发送端口结合使用时的有序的消息传递 **按序送达** 选项设置为 `True`。 有关详细信息 **按序送达** 选项，请参阅另请参阅中的相应主题。

此属性适用于以下情况：
- WCF 自定义适配器： 时**BindingType**属性设置为**netMsmqBinding**
- WCF 自定义适配器： 时**BindingType**属性设置为**customBinding**，和**BindingConfiguration**属性配置为使用自定义通道依赖支持有序的传递，如 MSMQ 传输。
- WCF CustomIsolated 适配器： 时**BindingType**属性设置为**customBinding**，和**BindingConfiguration**属性配置为使用自定义通道利用支持有序的传递的传输。
- WCF-NetMsmq 适配器

類型：字串  
默认值︰ **False**  
适用范围： 
- WCF NetMsmq 接收适配器
- WCF 自定义接收适配器
- WCF-CustomIsolated 接收适配器

#### <a name="outboundbodylocation"></a>OutboundBodyLocation
指定 SOAP 数据选择 **正文** 传出的 WCF 消息的元素。 有关如何使用**OutboundBodyLocation**属性，请参阅[为 WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。

類型：字串  
默认值： UseBodyElement  

    Applicable values are:
        - UseBodyElement: Use the BizTalk message body part to create the content of the SOAP **Body** element for an outgoing message
        - **UseTem****plate**: Use the template supplied in the OutboundXMLTemplate property to create the content of the SOAP **Body** element for an outgoing message

适用于： 所有 WCF 适配器*除*WCF NetMsmq 接收适配器

#### <a name="outboundcustomheaders"></a>OutboundCustomHeaders
指定传出消息的自定义 SOAP 标头。 当使用此属性时，该属性必须具有\<**标头**\>作为根元素的元素。 所有自定义 SOAP 标头必须放置在\<**标头**\>元素。 如果自定义 SOAP 标头的值为空字符串，则必须分配\<**标头**\>\</**标头**\>或\<**标头**\>到此属性。 有关如何使用 WCF 适配器使用 SOAP 标头的详细信息，请参阅 SDK 示例中，使用自定义 SOAP 标头与 WCF 适配器中，从 [http://go.microsoft.com/fwlink/?LinkId=79960](http://go.microsoft.com/fwlink/?LinkId=79960)。

類型：字串  
适用于： 所有 WCF 适配器*除*WCF NetMsmq 接收适配器

#### <a name="outboundxmltemplate"></a>OutboundXmlTemplate
指定的 SOAP 内容的 XML 格式模板 **正文** 的传出消息的元素。 此属性是必需的如果 **OutboundBodyLocation** 属性设置为 **UseTemplate**。 有关如何使用**OutboundXMLTemplate**属性，请参阅[为 WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。

類型：字串  
默认值： 空字符串  
适用于： 所有 WCF 适配器*除*WCF NetMsmq 接收适配器

#### <a name="password"></a>密码
指定要用于目标服务器的身份验证的密码时 **UseSSO** 属性设置为 **False**。

類型：字串  
默认值： 空字符串  
适用于： 所有 WCF 都发送适配器*除*WCF NetNamedPipe 适配器  

#### <a name="propagatefaultmessage"></a>PropagateFaultMessage
指定是否路由或挂起出站处理中失败的消息。 此屬性只對請求-回應連接埠有效。 

**请注意**  
在 BAM 主导入数据库中无法使用跟踪配置文件跟踪此属性。

类型︰ Boolean  
默认值︰ **True**  

    Applicable values are:  
        - True: Route the message that fails outbound processing to a subscribing application (such as another receive port or orchestration schedule)
        - False: Suspend failed messages and generate a negative acknowledgment (NACK)

适用于： 所有 WCF 都发送适配器*除*WCF NetMsmq 适配器
  
#### <a name="proxyaddress"></a>ProxyAddress
指定 Proxy 伺服器的位址。 使用 **https** 或 **http** 根据安全配置的方案。 這個位址後面可以加上冒號和連接埠編號， 该属性是必需的如果**ProxyToUse**属性设置为**UserSpecified** (例如，http://127.0.0.1:8080)

類型：字串  
默认值： 空字符串  
适用于： WCF BasicHttp 发送适配器，WCF WSHttp 发送适配器  

#### <a name="proxypassword"></a>ProxyPassword
指定要用于中指定的代理服务器密码 **ProxyAddress** 属性。

類型：字串  
默认值： 空字符串  
适用于： WCF BasicHttp 发送适配器，WCF WSHttp 发送适配器

#### <a name="proxytouse"></a>ProxyToUse
指定要用于传出 HTTP 通信的代理服务器。

類型：字串  
默认值︰ **无**  

    Applicable values are:  
        - None: Do not use a proxy server for this send port
        - Default: Use the proxy settings in the send handler hosting this send port
        - UserSpecified: Use the proxy server specified in the **ProxyAddress** property

适用于： WCF BasicHttp 发送适配器，WCF WSHttp 发送适配器  

#### <a name="proxyusername"></a>ProxyUserName
指定要用于代理服务器中指定的用户名称 **ProxyAddress** 属性。 该属性是必需的如果 **ProxyToUse** 属性设置为 **UserSpecified**。

有关此属性的详细信息，请参阅[如何配置 WCF WSHttp 发送端口](../core/how-to-configure-a-wcf-wshttp-send-port.md)和[如何配置 WCF BasicHttp 发送端口](http://msdn.microsoft.com/library/acdb50fa-57fe-4657-9561-b6b2f4919c7f)。

類型：字串  
适用于： WCF BasicHttp 发送适配器，WCF WSHttp 发送适配器

#### <a name="replytoaddress"></a>ReplyToAddress
指示与通过请求响应接收位置接收的传入消息相对应的传出 WCF 消息的回复终结点地址。 该属性将自动提升从传入消息。

類型：字串  
默认值： 空字符串  
适用于： 所有 WCF 适配器*除*WCF NetMsmq 适配器

#### <a name="securitymode"></a>SecurityMode
指定使用的安全性類型。 适用值因每个 WCF 适配器的不同而异。 有关详细信息**SecurityMode**属性，请参阅操作指南主题中的每个 WCF 适配器[WCF 适配器](../core/wcf-adapters.md)。 

**请注意**  
在 BAM 主导入数据库中无法使用跟踪配置文件跟踪此属性。

類型：字串  
适用于： 所有 WCF 适配器*除*的 WCF 自定义和 WCF CustomIsolated 适配器

#### <a name="sendtimeout"></a>SendTimeout
指定時間值，表示可供完成傳送作業的時間間隔。 此值指定完成整个交互的时间跨度（即使响应方返回一条大消息）。

類型：字串  
預設值：00:01:00  
适用于： 所有 WCF 适配器*除*的 WCF 自定义和 WCF CustomIsolated 适配器

#### <a name="servicebehaviorconfiguration"></a>ServiceBehaviorConfiguration
指定使用的 XML 字符串**\<行为\>** 元素**\<serviceBehaviors\>** 元素来配置 WCF 行为设置服务。 有关详细信息**\<serviceBehaviors\>** 元素，请参阅另请参阅中的相应主题。

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

類型：字串  
默认值： 空字符串  
适用于： WCF 自定义接收适配器，WCF CustomIsolated 适配器

#### <a name="servicecertificate"></a>ServiceCertificate
如果此属性用于接收位置，则为接收位置指定 X.509 证书的指纹，客户端利用该指纹验证服务。 此属性使用的证书必须安装到 **我** 将存储在 **当前用户** 位置。

如果此属性用于发送端口，请指定 X.509 证书的指纹，用于验证此发送端口将消息发送到的服务。 此属性使用的证书必须安装到 **其他人** 将存储在 **本地计算机** 位置。

類型：字串  
默认值： 空字符串  
适用范围： 
- WCF BasicHttp 适配器
- WCF-NetMsmq 适配器
- WCF-WSHttp 适配器
- WCF-NetTcp 接收适配器

#### <a name="suspendmessageonfailure"></a>SuspendMessageOnFailure
指定是否擱置因接收管線失敗或路由失敗而造成輸入處理失敗的要求訊息。

类型︰ Boolean  
默认值：True  
适用于： 所有 WCF 都接收适配器  

#### <a name="textencoding"></a>TextEncoding
指定的字符集编码要用于在绑定上发出消息时 **MessageEncoding** 属性设置为 **文本**。 

**请注意**  
在 BAM 主导入数据库中无法使用跟踪配置文件跟踪此属性。 

類型：字串  
默认值： utf-8  

    Applicable values are:  
        - unicodeFFF: Unicode BigEndian encoding
        - utf-16: 16-bit encoding
        - utf-8: 8-bit encoding

适用于： WCF BasicHttp 适配器，WCF WSHttp 适配器
  
#### <a name="timetolive"></a>TimeToLive
指定一个时间范围，在此范围内消息有效，一旦超出此范围，消息将到期并被置于死信队列。 设置此属性是为了确保时间敏感消息在被发送端口处理前不会变得陈旧。 队列中在指定的时间间隔内未由此发送端口使用的消息将被认为到期。 到期的消息将发送到称为死信队列的特殊队列。 死信队列的位置设置 **DeadLetterQueue** 属性。

類型：字串  
默认值︰ 1.00:00:00  
适用于： WCF NetMsmq 发送适配器

#### <a name="to"></a>若要
为 WCF 发送端口发送的传出 WCF 消息指定目标终结点地址。

類型：字串  
默认值： 空字符串  
适用于： 所有 WCF 都发送适配器  

#### <a name="transactionprotocol"></a>TransactionProtocol
指定要与此绑定一起使用的事务协议。 此属性是必需的如果 **EnableTransaction** 属性设置为 **True**。

類型：字串  
默认值： OleTransaction  

    Applicable values are: OleTransaction, WS-AtomicTransaction

适用于： WCF NetNamedPipe 适配器，WCF NetTcp 适配器  

#### <a name="transportclientcredentialtype"></a>TransportClientCredentialType
指定执行发送端口验证时使用的凭据类型。 适用值因每个 WCF 适配器的不同而异。 有关详细信息**TransportClientCredentialType**属性，请参阅操作指南主题中的每个 WCF 适配器[WCF 适配器](../core/wcf-adapters.md)。

類型：字串  
适用于： WCF Basic 适配器，WCF NetTcp 适配器，WCF WSHttp 适配器  

#### <a name="transportprotectionlevel"></a>TransportProtectionLevel
指定 TCP 传输级别的安全性。 消息签名降低了在消息传输过程中第三方对消息进行篡改的风险。 加密为传输过程提供了数据级保密功能。

類型：字串  
默认值︰ **EncryptAndSign**  

    Applicable values are:  
        - None: No protection
        - Sign: Messages are signed
        - EncryptAndSign: Messages are encrypted and signed

适用于： WCF NetTcp 适配器，WCF NetNamedPipe 适配器  

#### <a name="username"></a>UserName
指定要用于目标服务器的身份验证的用户名称时 **UseSSO** 属性设置为 **False**。 不必采用“域\用户”格式设置此属性。

類型：字串  
默认值： 空字符串  
适用于： 所有 WCF 都发送适配器*除*WCF NetNamedPipe 适配器

#### <a name="usesourcejournal"></a>UseSourceJournal
指定是否应将此发送端口所处理的消息副本存储到源日记队列中。

类型︰ Boolean  
默认值：False  
适用于： WCF NetMsmq 发送适配器  

#### <a name="usesso"></a>UseSSO
指定是否使用单一登录检索客户端凭据，以便在目标服务器上进行验证。 

**请注意**  
在 BAM 主导入数据库中无法使用跟踪配置文件跟踪此属性。 

类型︰ Boolean  
默认值：False  
适用于： 所有 WCF 都发送适配器*除*WCF NetNamedPipe 适配器

#### <a name="referencedbindings"></a>ReferencedBindings
指定引用的绑定配置**bindingConfiguration**属性**\<颁发者\>** 元素**wsFederationHttpBinding**和**customBinding**，表示安全令牌服务 (STS) 颁发安全令牌。 有关详细信息**\<颁发者\>** 元素，请参阅主题中，"\<颁发者\>"在[http://go.microsoft.com/fwlink/?LinkId=83476](http://go.microsoft.com/fwlink/?LinkId=83476)。

绑定信息包括**\<颁发者\>** 元素**wsFederationHttpBinding**和**customBinding**可以是通过配置**BindingConfiguration**的 WCF 自定义和 WCF CustomIsolated 适配器的属性。 此属性的引用的绑定配置的所有必须置于窗体的[\<绑定\>](http://go.microsoft.com/fwlink/?LinkID=80878)元素。 

**请注意**  
**BindingConfiguration**属性**\<颁发者\>** 元素必须引用此属性中的一个有效的绑定名称。 

**请注意**  
**\<颁发者\>** 如果此引用链不会进行一个循环依赖关系中的引用的绑定配置元素还可以引用到此属性中的不同绑定配置。 

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

**请注意**  
**ReferencedBinding**属性不能包含中使用的绑定配置**BindingConfiguration**属性。

類型：字串  
默认值： 空字符串  
适用于： WCF 自定义适配器，WCF CustomIsolated 适配器
  
## <a name="see-also"></a>另请参阅  
 [WCF 适配器](../core/wcf-adapters.md)   
 [\<行为\>的\<endpointBehaviors\>](http://go.microsoft.com/fwlink/?LinkId=80879)   
 [\<bindings\>](http://go.microsoft.com/fwlink/?LinkId=80878)   
 [\<behavior\> of \<serviceBehaviors\>](http://go.microsoft.com/fwlink/?LinkId=81095)   
 [有序的消息传送](../core/ordered-delivery-of-messages.md)   
 [负载平衡](http://go.microsoft.com/fwlink/?LinkId=81089)
