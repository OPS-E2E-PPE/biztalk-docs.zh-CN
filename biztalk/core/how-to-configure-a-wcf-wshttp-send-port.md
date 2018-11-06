---
title: 配置 Wcf-wshttp 发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 035d9a62-b8a3-4705-a7bc-b62676437206
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4b27136c01db4414d43d30790474a0deb339aee
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "50752347"
---
# <a name="how-to-configure-a-wcf-wshttp-send-port"></a>如何配置 WCF-WSHttp 发送端口
可以通过编程方式或使用 BizTalk Server 管理控制台来配置 WCF-WSHttp 发送端口。  

## <a name="configuration-properties"></a>配置属性

 BizTalk 资源管理器对象模型公开了名为发送端口的特定于适配器的接口**ITransportInfo**具有**TransportTypeData**读/写属性。 此属性接受 XML 字符串的名称-值对形式的 WCF-WSHttp 发送端口配置属性包。  

 **TransportTypeData**的属性**ITransportInfo**接口不需要。 如果未设置该属性，则适配器将使用 WCF-WSHttp 发送端口配置的默认值，如下表所示。  

 下表列出了可在 BizTalk 浏览器对象模型中为 WCF-WSHttp 发送端口设置的配置属性。  


| 属性名称 | 类型 |  Description |
|---|---|---|
| **标识**            |  XML Blob<br /><br /> 示例：<br /><br /> &lt;标识&gt;<br /><br /> &lt;userPrincipalName value="username@contoso.com" /&gt;<br /><br /> &lt;/identity&gt; |  指定此发送端口预期的服务标识。 这些设置支持此发送端口对服务进行验证。 在客户端与服务进行握手的过程中，Windows Communication Foundation (WCF) 基础结构将确保预期服务的标识与此元素的值保持一致。<br /><br /> 默认值为空字符串。  |
|  **StaticAction**          |  -字符串  | 指定**SOAPAction**为传出消息的 HTTP 标头字段。 此外可以通过消息上下文属性设置此属性**WCF。操作**管道或业务流程中。 可以通过两种方式指定此值： 单一操作格式和操作映射格式。 如果您将此属性设置中的单一操作格式-例如，<`http://contoso.com/Svc/Op1-`> **SOAPAction**标头传出消息将始终设置为此属性中指定的值。<br /><br /> 如果将此属性设置采用操作映射格式，传出**SOAPAction**标头由**BTS。操作**上下文属性。 例如，如果此属性设置为以下 XML 格式和**BTS。操作**属性设置为 Op1，WCF 发送适配器使用 <http://contoso.com/Svc/Op1> 为传出**SOAPAction**标头。<br /><br /> \<BtsActionMapping\><br /><br /> \<操作名称 ="Op1"操作 ="<http://contoso.com/Svc/Op1>"/\><br /><br /> \<操作名称 ="Op2"操作 ="<http://contoso.com/Svc/Op2>"/\><br /><br /> \</BtsActionMapping\><br /><br /> 如果传出消息来自某个业务流程端口，业务流程实例动态设置**BTS。操作**使用的端口的操作名称的属性。 如果使用基于内容的路由来路由传出消息，则可以设置**BTS。操作**管道组件中的属性。<br /><br /> 默认值为空字符串。 |
|          **OpenTimeout**          | **System.TimeSpan** |  指定一个时间跨度值来表示为完成信道打开操作提供的时间间隔。<br /><br /> 默认值：00:01:00  |
|          **SendTimeout**          | **System.TimeSpan**  |  指定一个时间跨度值来表示为完成发送操作提供的时间间隔。 如果使用要求-响应发送端口，则此值指定完成整个交互的时间跨度（即使服务返回一条大消息）。<br /><br /> 默认值：00:01:00  |
|         **CloseTimeout**          |  **System.TimeSpan**  |  指定一个时间跨度值来表示为完成信道关闭操作提供的时间间隔。<br /><br /> 默认值：00:01:00  |
|    **MaxReceivedMessageSize**     | Integer  | 指定网络上可接收的消息的最大大小（包括标头），以字节为单位。 消息的大小受为每条消息分配的内存量的限制。 你可以使用此属性来降低受拒绝服务 (DoS) 攻击的可能性。<br /><br /> 默认值：65536  |
|        **MessageEncoding**        |  Enum<br /><br /> -   **文本**-使用文本消息编码器。<br />-   **Mtom** -使用消息传输组织机制 1.0 (MTOM) 编码器。  |  指定用于对 SOAP 消息进行编码的编码器。<br /><br /> 默认值：**文本**  |
|         **TextEncoding**          | Enum<br /><br /> -   **unicodeFFF** -Unicode BigEndian 编码。<br />-   **utf-16** -16 位编码。<br />-   **utf-8** -8 位编码。  | 指定要使用该绑定上发出消息编码的字符集时**MessageEncoding**属性设置为**文本**。<br /><br /> 默认值： **utf-8**  |
|       **EnableTransaction**       |  Boolean  |  指定是否一条消息传输到目标服务，并从在事务性上下文中使用的 MessageBox 数据库中删除**WS-AtomicTransaction**协议。<br /><br /> 默认值： **False**  |
|         **SecurityMode**          |  Enum<br /><br /> -   **无**<br />-   **消息**<br />-   **传输**<br />-   **TransportWithMessageCredential**<br /><br /> 有关成员名称的详细信息**SecurityMode**属性，请参阅**安全模式**中的属性**Wcf-wshttp 传输属性对话框，发送，安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。   | 指定使用的安全类型。<br /><br /> 默认值： **None**  |
| **TransportClientCredentialType** |  Enum<br /><br /> -   **无**<br />-   **基本**<br />-   **Windows**<br />-   **证书**<br />-   **摘要**<br />-   **ntlm**<br /><br /> 有关成员名称的详细信息**TransportClientCredentialType**属性，请参阅**传输客户端凭据类型**中的属性**Wcf-wshttp 传输属性对话框中，发送，安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  |  指定执行发送端口验证时使用的凭据类型。<br /><br /> 默认值： **None**  |
|  **MessageClientCredentialType**  | Enum<br /><br /> -   **无**<br />-   **Windows**<br />-   **用户名**<br />-   **证书**<br /><br /> 有关成员名称的详细信息**MessageClientCredentialType**属性，请参阅**消息客户端凭据类型**中的属性**Wcf-wshttp 传输属性对话框框中，发送，安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  | 指定使用基于消息的安全性对客户端执行验证时所用的凭据类型。<br /><br /> 默认值：**用户名**  |
|        **AlgorithmSuite**         | Enum<br /><br /> 有关成员名称的详细信息**AlgorithmSuite**属性，请参阅**算法套件**中的属性**Wcf-wshttp 传输属性对话框，发送，安全性**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  |  指定消息加密和密钥包装算法。 这些算法与“安全策略语言”(WS-SecurityPolicy) 规范中指定的算法一致。<br /><br /> 默认值： **Basic256**  |
|  **NegotiateServiceCredential**   |  Boolean<br /><br /> 有关成员名称的详细信息**NegotiateServiceCredential**属性，请参阅**协商服务凭据**中的属性**Wcf-wshttp 传输属性对话框框中，发送，安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。 |  指定是在此带外发送端口提供服务凭据，还是通过协商从服务获取服务凭据并发送到此发送端口。 这种协商是正常消息交换开始前的准备过程。<br /><br /> 默认值： **False**|
|     **EnableSecurityContext**     | Boolean  |  指定是否通过建立安全上下文令牌**Ws-secureconversation**此发送端口和服务之间交换。 如果此属性设置为 **，则返回 True**则目标服务必须支持**Ws-secureconversation**。<br /><br /> 默认值： **，则返回 True**  |
|       **ClientCertificate**       | String  |  指定用于向服务验证此发送端口的 X.509 证书的指纹。 此属性是必需的如果**ClientCredentialsType**属性设置为**证书**。 要用于此属性的证书必须安装到**我**将存储在**当前用户**位置。<br /><br /> 默认值为空字符串。 |
|      **ServiceCertificate**       |  String  |  指定用于验证服务（此发送端口要将消息发送到的服务）的 X.509 证书的指纹。 要用于此属性的证书必须安装到**其他人**将存储在**本地计算机**位置。<br /><br /> 默认值为空字符串。  |
|   **AffiliateApplicationName**    |  String  | 指定用于企业单一登录 (SSO) 的关联应用程序。<br /><br /> 默认值为空字符串。 |
|            **UseSSO**             |   Boolean  |  指定是否使用单一登录检索客户端凭据，以便在目标服务器上进行验证。<br /><br /> 默认值： **False** |
|           **UserName**            |  String  |  指定要用于目标服务器的身份验证的用户名时**UseSSO**属性设置为**False**。 不必采用“域\用户”格式设置此属性。<br /><br /> 默认值为空字符串。 |
|           **密码**            |  String  | 指定要用于目标服务器的身份验证的密码时**UseSSO**属性设置为**False**。<br /><br /> 默认值为空字符串。 |
|          **ProxyToUse**           | Enum<br /><br /> -   **无**-不为此发送端口使用代理服务器。<br />-   **默认**-使用承载此发送端口的发送处理程序中的代理设置。<br />-   **UserSpecified** -使用中指定的代理服务器**ProxyAddress**属性。  | 指定要用于传出 HTTP 通信的代理服务器。<br /><br /> 默认值： **None**  |
|         **ProxyAddress**          | String |  指定代理服务器的地址。 使用**https**或**http**具体取决于安全配置的方案。 此地址后面可跟冒号和端口号。 例如 `http://127.0.0.1:8080` 。<br /><br /> 默认值为空字符串。 |
|         **ProxyUserName**         |  String  | 指定用于代理的用户名。 Wcf-wshttp 适配器利用[WSHttpBinding](http://go.microsoft.com/fwlink/?LinkId=81206)在缓冲的传输模式下，与终结点进行通信。 代理凭据**WSHttpBinding**是适用的安全模式时才**传输**，或**None**。 如果您设置**SecurityMode**属性设置为**消息**或**TransportWithMessageCredential**，Wcf-wshttp 适配器不使用中指定的凭据**ProxyUserName**并**ProxyPassword**针对代理进行身份验证的属性。 **注意：** Wcf-wshttp 发送适配器将使用基本身份验证代理。 <br /><br /> 默认值为空字符串。  |
|         **ProxyPassword**         |  String  |  指定用于代理的密码。<br /><br /> 默认值为空字符串。|
|     **OutboundBodyLocation**      |  Enum<br /><br /> -   **UseBodyElement** -使用 BizTalk 消息正文部分创建的 soap 内容**正文**为传出消息的元素。<br />-   **UseTemplate** -使用中提供的模板**OutboundXMLTemplate**属性创建的 soap 内容**正文**为传出消息的元素。<br /><br /> 有关如何使用详细信息**OutboundBodyLocation**属性，请参阅[WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。  |  指定数据选择 soap**正文**的传出 WCF 消息的元素。<br /><br /> 默认值： **UseBodyElement**  |
|      **OutboundXMLTemplate**      |  String<br /><br /> 有关如何使用详细信息**OutboundXMLTemplate**属性，请参阅[WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。  |  指定内容的 SOAP XML 格式的模板**正文**传出的消息的元素。 此属性是必需的如果**OutboundBodyLocation**属性设置为**UseTemplate**。<br /><br /> 默认值为空字符串。  |
|      **InboundBodyLocation**      | Enum<br /><br /> -   **UseBodyElement** -使用的 soap 内容**正文**传入消息创建 BizTalk 消息正文部分的元素。 如果 **Body** 元素具有多个子元素，则只有第一个元素将成为 BizTalk 消息正文部分。 此属性仅对要求-响应端口有效。<br />-   **UseEnvelope** -创建 BizTalk 消息正文部分的整个 soap**信封**传入消息。<br />-   **UseBodyPath** -使用中的正文路径表达式**InboundBodyPathExpression**属性以创建 BizTalk 消息正文部分。 针对传入消息的 SOAP **Body** 元素的直接子元素计算正文路径表达式。 此属性仅对要求-响应端口有效。<br /><br /> 有关如何使用详细信息**InboundBodyLocation**属性，请参阅[WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。 |  指定数据选择 soap**正文**传入 WCF 消息的元素。<br /><br /> 默认值： **UseBodyElement**  |
|   **InboundBodyPathExpression**   |  String<br /><br /> 有关如何使用详细信息**InboundBodyPathExpression**属性，请参阅[WCF 适配器属性架构和属性](../core/wcf-adapters-property-schema-and-properties.md)。  |  指定正文路径表达式以标识传入消息中用于创建 BizTalk 消息正文部分的特定部分。 针对 SOAP 的直接子元素计算此正文路径表达式**正文**传入消息的节点。 如果此正文路径表达式返回多个节点，则只选择第一个节点作为 BizTalk 消息正文部分。 此属性是必需的如果**InboundBodyLocation**属性设置为**UseBodyPath**。 此属性仅对要求-响应端口有效。<br /><br /> 默认值为空字符串。  |
|      **InboundNodeEncoding**      |  Enum<br /><br /> -   **Base64** -Base64 编码。<br />-   **十六进制**-十六进制编码。<br />-   **字符串**-文本编码-utf-8。<br />-   **XML** -WCF 适配器中的正文路径表达式所选择的节点的外部 xml 创建 BizTalk 消息正文**InboundBodyPathExpression**。  |  指定 Wcf-wshttp 发送适配器将使用进行解码中指定的正文路径所标识的节点的编码类型**InboundBodyPathExpression**。 此属性是必需的如果**InboundBodyLocation**属性设置为**UseBodyPath**。 此属性仅对要求-响应端口有效。<br /><br /> 默认值： **XML**  |
|     **PropagateFaultMessage**     | Boolean<br /><br /> -   **True** -将路由到某个订阅应用程序的出站处理失败的消息 （例如其他接收端口或业务流程计划）。<br />-   **False** -挂起失败的消息并生成一个否定确认 (NACK)。 |  指定是路由还是挂起在出站处理中失败的消息。<br /><br /> 此属性仅对要求-响应端口有效。<br /><br /> 默认值： **，则返回 True**  |

## <a name="configure-a-wcf-wshttp-send-port-with-the-biztalk-administration-console"></a>使用 BizTalk 管理控制台配置 Wcf-wshttp 发送端口

 您可以在 BizTalk 管理控制台中设置 WCF-WSHttp 发送端口适配器变量。 如果没有为发送端口设置属性，将使用 WCF-WSHttp 发送端口配置的默认值，如前表所示。  

## <a name="configure-variables-for-a-wcf-wshttp-send-port"></a>配置 Wcf-wshttp 发送端口的变量  

1. 在 BizTalk 管理控制台中，创建一个新的发送端口或双击某个现有发送端口以对其进行修改。 有关详细信息，请参阅[如何创建发送端口](../core/how-to-create-a-send-port2.md)。 配置所有发送端口选项，并指定**Wcf-wshttp**有关**类型**选项**传输**一部分**常规**选项卡。  

2. 上**常规**选项卡上，在**传输**部分中，单击**配置**旁边**类型**。  

3. 在**Wcf-wshttp 传输属性**对话框中，在**常规**选项卡上，配置终结点地址、 服务标识，并且**SOAPAction** HTTP 标头Wcf-wshttp 发送端口。 有关详细信息**常规**选项卡**Wcf-wshttp 传输属性**对话框中，请参阅**Wcf-wshttp 传输属性对话框，发送，常规**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  

4. 在中**Wcf-wshttp 传输属性**对话框中，在**绑定**选项卡上，配置超时、 编码和事务属性。 有关详细信息**绑定**选项卡**Wcf-wshttp 传输属性**对话框中，请参阅**Wcf-wshttp 传输属性对话框，发送，绑定**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  

5. 在中**Wcf-wshttp 传输属性**对话框中，在**安全**选项卡上，定义 Wcf-wshttp 发送端口的安全功能。 有关详细信息**安全**选项卡**Wcf-wshttp 传输属性**对话框中，请参阅**Wcf-wshttp 传输属性对话框，发送，安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。

6. 在中**Wcf-wshttp 传输属性**对话框中，在**代理**选项卡上，配置代理设置 Wcf-wshttp 发送端口。 有关详细信息**代理**选项卡**Wcf-wshttp 传输属性**对话框中，请参阅**Wcf-wshttp 传输属性对话框，发送，代理**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].

7. 在中**Wcf-wshttp 传输属性**对话框中，在**消息**选项卡上，指定数据选择 soap**正文**元素。 有关详细信息**消息**选项卡**Wcf-wshttp 传输属性**对话框中，请参阅**Wcf-wshttp 传输属性对话框，发送，消息**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。

## <a name="configure-a-wcf-wshttp-send-port-programmatically"></a>以编程方式配置 Wcf-wshttp 发送端口

 可使用以下格式设置属性：  

```  
 <CustomProps>    
  <ServiceCertificate vt="8" />  
  <UseSSO vt="11">0</UseSSO>  
  <InboundBodyPathExpression vt="8" />  
  <MessageClientCredentialType vt="8">Windows</MessageClientCredentialType>  
  <SendTimeout vt="8">00:01:00</SendTimeout>  
  <OutboundXmlTemplate vt="8"><bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="xml"/></OutboundXmlTemplate>  
  <OpenTimeout vt="8">00:01:00</OpenTimeout>  
  <Identity vt="8" />  
  <AlgorithmSuite vt="8">Basic256</AlgorithmSuite>  
  <SecurityMode vt="8">Message</SecurityMode>  
  <TransportClientCredentialType vt="8">Windows</TransportClientCredentialType>  
  <TextEncoding vt="8">utf-8</TextEncoding>  
  <NegotiateServiceCredential vt="11">-1</NegotiateServiceCredential>  
  <MaxReceivedMessageSize vt="3">2097152</MaxReceivedMessageSize>  
  <ClientCertificate vt="8" />  
  <ProxyUserName vt="8" />  
  <CloseTimeout vt="8">00:01:00</CloseTimeout>  
  <ProxyToUse vt="8">Default</ProxyToUse>  
  <EnableTransaction vt="11">0</EnableTransaction>  
  <InboundBodyLocation vt="8">UseBodyElement</InboundBodyLocation>  
  <InboundNodeEncoding vt="8">Xml</InboundNodeEncoding>  
  <EstablishSecurityContext vt="11">-1</EstablishSecurityContext>  
  <StaticAction vt="8">http://www.northwindtraders.com/Service/Operation</StaticAction>  
  <PropagateFaultMessage vt="11">-1</PropagateFaultMessage>  
  <ProxyAddress vt="8" />  
  <MessageEncoding vt="8">Text</MessageEncoding>  
  <OutboundBodyLocation vt="8">UseBodyElement</OutboundBodyLocation>  
</CustomProps>  

```  

 下面的代码段说明了如何创建 WCF-WSHttp 发送端口：  

```  
// Use BizTalk Explorer object model to create new WCF-WSHttp send port.  
string server = System.Environment.MachineName;  
string database = "BizTalkMgmtDb";  
string connectionString = string.Format("Server={0};Database={1};Integrated Security=true", server, database);  
string transportConfigData = @"<CustomProps>  
                                 <StaticAction vt=""8"">http://www.northwindtraders.com/Service/Operation</StaticAction>  
                                 <MessageEncoding vt=""8"">Text</MessageEncoding>  
                                 <TextEncoding vt=""8"">utf-8</TextEncoding>  
                                 <OpenTimeout vt=""8"">00:01:00</OpenTimeout>  
                               </CustomProps>";  
//requires project reference to \Program Files\Microsoft BizTalk Server 2009\Developer Tools\Microsoft.BizTalk.ExplorerOM.dll  
BtsCatalogExplorer explorer = new Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer();  
explorer.ConnectionString = connectionString;  
// Add a new BizTalk application  
Application application = explorer.AddNewApplication();  
application.Name = "SampleBizTalkApplication";  
// Save  
explorer.SaveChanges();  

// Add a new static one-way send port  
SendPort sendPort = application.AddNewSendPort(false, false);   
sendPort.Name = "SampleSendPort";  
sendPort.PrimaryTransport.TransportType = explorer.ProtocolTypes["WCF-WSHttp"];  
sendPort.PrimaryTransport.Address = "http://mycomputer/samplepath";  
sendPort.PrimaryTransport.TransportTypeData = transportConfigData; // propertyData; // need to change  
sendPort.SendPipeline = explorer.Pipelines["Microsoft.BizTalk.DefaultPipelines.PassThruTransmit"];  
// Save  
explorer.SaveChanges();  
```  

## <a name="see-also"></a>请参阅  
 [WCF 适配器属性架构和属性](../core/wcf-adapters-property-schema-and-properties.md)   
 [配置 Wcf-wshttp 适配器](../core/configuring-the-wcf-wshttp-adapter.md)   
 [指定 WCF 适配器的消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)   
 [用于 WCF 适配器安装证书](../core/installing-certificates-for-the-wcf-adapters.md)   
 [使用 WCF 适配器上下文属性配置动态发送端口](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)
