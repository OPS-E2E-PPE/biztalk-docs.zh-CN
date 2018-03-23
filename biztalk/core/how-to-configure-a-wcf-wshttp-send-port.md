---
title: 如何配置 WCF WSHttp 发送端口 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 035d9a62-b8a3-4705-a7bc-b62676437206
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f5fc7b26877f840de491176beab70e7191ad57e
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
---
# <a name="how-to-configure-a-wcf-wshttp-send-port"></a>如何配置 WCF-WSHttp 发送端口
可以通过编程方式或使用 BizTalk Server 管理控制台来配置 WCF-WSHttp 发送端口。  
  
## <a name="configuration-properties"></a>配置属性
  
 BizTalk 资源管理器对象模型公开了用于发送端口名为的特定于适配器的接口 **ITransportInfo** 具有 **TransportTypeData** 读/写属性。 此属性接受 XML 字符串的名称-值对形式的 WCF-WSHttp 发送端口配置属性包。  
  
 **TransportTypeData** 属性 **ITransportInfo** 界面不是必需。 如果未设置该属性，则适配器将使用 WCF-WSHttp 发送端口配置的默认值，如下表所示。  
  
 下表列出了可在 BizTalk 浏览器对象模型中为 WCF-WSHttp 发送端口设置的配置属性。  
  
|属性名称|型別|Description|  
|-------------------|----------|-----------------|  
|**标识**|XML Blob<br /><br /> 示例︰<br /><br /> &lt;标识&gt;<br /><br /> &lt;userPrincipalName value="username@contoso.com" /&gt;<br /><br /> &lt;/identity&gt;|指定此发送端口预期的服务标识。 这些设置支持此发送端口对服务进行验证。 在客户端与服务进行握手的过程中，Windows Communication Foundation (WCF) 基础结构将确保预期服务的标识与此元素的值保持一致。<br /><br /> 默认值为空字符串。|  
|**StaticAction**|字符串|指定 **SOAPAction** 传出消息的 HTTP 标头字段。 此外可以通过消息上下文属性设置此属性 **WCF。操作** 在管道或业务流程。 你可以通过两种方式指定此值︰ 单个操作格式和操作映射格式。 如果将此属性设置中的单个操作格式-例如， http://contoso.com/Svc/Op1- **SOAPAction**标头为传出消息始终设置为此属性中指定的值。<br /><br /> 如果在操作映射格式，传出中设置此属性 **SOAPAction** 标头由 **BTS。操作** 上下文属性。 例如，如果此属性设置为以下 XML 格式和**BTS。操作**属性设置为 Op1，WCF 发送适配器使用http://contoso.com/Svc/Op1为传出**SOAPAction**标头。<br /><br /> \<BtsActionMapping\><br /><br /> \<Operation Name="Op1" Action="http://contoso.com/Svc/Op1" /\><br /><br /> \<Operation Name="Op2" Action="http://contoso.com/Svc/Op2" /\><br /><br /> \</BtsActionMapping\><br /><br /> 如果传出消息来自的业务流程端口时，动态设置业务流程实例 **BTS。操作** 与操作名称的端口的属性。 如果使用基于内容的路由路由传出消息，则可以设置 **BTS。操作** 管道组件中的属性。<br /><br /> 默认值为空字符串。|  
|**OpenTimeout**|**System.TimeSpan**|指定一个时间跨度值来表示为完成信道打开操作提供的时间间隔。<br /><br /> 默认值：00:01:00|  
|**SendTimeout**|**System.TimeSpan**|指定一个时间跨度值来表示为完成发送操作提供的时间间隔。 如果使用要求-响应发送端口，则此值指定完成整个交互的时间跨度（即使服务返回一条大消息）。<br /><br /> 默认值：00:01:00|  
|**CloseTimeout**|**System.TimeSpan**|指定一个时间跨度值来表示为完成信道关闭操作提供的时间间隔。<br /><br /> 默认值：00:01:00|  
|**MaxReceivedMessageSize**|Integer|指定网络上可接收的消息的最大大小（包括标头），以字节为单位。 消息的大小受为每条消息分配的内存量的限制。 您可以使用這個屬性來限制遭受拒絕服務 (DoS) 攻擊的風險程度。<br /><br /> 默认值：65536|  
|**MessageEncoding**|Enum<br /><br /> -   **文本**-使用文本消息编码器。<br />-   **Mtom** -使用消息传输组织机制 1.0 (MTOM) 编码器。|指定用于对 SOAP 消息进行编码的编码器。<br /><br /> 默认值︰ **文本**|  
|**TextEncoding**|Enum<br /><br /> -   **unicodeFFF** -Unicode BigEndian 编码。<br />-   **utf-16** -16 位编码。<br />-   **utf-8** -8 位编码。|指定的字符集编码要用于在绑定上发出消息时 **MessageEncoding** 属性设置为 **文本**。<br /><br /> 默认值︰ **utf-8**|  
|**EnableTransaction**|Boolean|指定是否为传输到目标服务并从在事务上下文中使用的 MessageBox 数据库中删除一条消息 **Ws-atomictransaction** 协议。<br /><br /> 默认值︰ **False**|  
|**SecurityMode**|Enum<br /><br /> -   **无**<br />-   **消息**<br />-   **传输**<br />-   **TransportWithMessageCredential**<br /><br /> 有关成员名称的详细信息**SecurityMode**属性，请参阅**安全模式**中的属性**WCF WSHttp 传输属性对话框中，发送，安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。|指定使用的安全性類型。<br /><br /> 默认值︰ **无**|  
|**TransportClientCredentialType**|Enum<br /><br /> -   **无**<br />-   **基本**<br />-   **Windows**<br />-   **证书**<br />-   **摘要**<br />-   **Ntlm**<br /><br /> 有关成员名称的详细信息**TransportClientCredentialType**属性，请参阅**传输客户端凭据类型**中的属性**WCF WSHttp 传输属性对话框中，发送，安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。|指定执行发送端口验证时使用的凭据类型。<br /><br /> 默认值︰ **无**|  
|**MessageClientCredentialType**|Enum<br /><br /> -   **无**<br />-   **Windows**<br />-   **用户名**<br />-   **证书**<br /><br /> 有关成员名称的详细信息**MessageClientCredentialType**属性，请参阅**消息客户端凭据类型**中的属性**WCF WSHttp 传输属性对话框框中，发送，安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。|指定使用基于消息的安全性对客户端执行验证时所用的凭据类型。<br /><br /> 默认值︰ **用户名**|  
|**AlgorithmSuite**|Enum<br /><br /> 有关成员名称的详细信息**AlgorithmSuite**属性，请参阅**算法套件**中的属性**WCF WSHttp 传输属性对话框中，发送，安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。|指定訊息加密和 Key Wrap 演算法。 这些算法与“安全策略语言”(WS-SecurityPolicy) 规范中指定的算法一致。<br /><br /> 默认值︰ **Basic256**|  
|**NegotiateServiceCredential**|Boolean<br /><br /> 有关成员名称的详细信息**NegotiateServiceCredential**属性，请参阅**协商服务凭据**中的属性**WCF WSHttp 传输属性对话框框中，发送，安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。|指定是在此带外发送端口提供服务凭据，还是通过协商从服务获取服务凭据并发送到此发送端口。 这种协商是正常消息交换开始前的准备过程。<br /><br /> 默认值︰ **False**|  
|**EnableSecurityContext**|Boolean|指定是否通过建立安全上下文令牌 **Ws-secureconversation** 此发送端口和服务之间的交换。 如果此属性设置为 **True** 然后目标服务必须支持 **Ws-secureconversation**。<br /><br /> 默认值︰ **True**|  
|**ClientCertificate**|字符串|指定用于向服务验证此发送端口的 X.509 证书的指纹。 此属性是必需的如果 **ClientCredentialsType** 属性设置为 **证书**。 此属性使用的证书必须安装到 **我** 将存储在 **当前用户** 位置。<br /><br /> 默认值为空字符串。|  
|**ServiceCertificate**|字符串|指定用于验证服务（此发送端口要将消息发送到的服务）的 X.509 证书的指纹。 此属性使用的证书必须安装到 **其他人** 将存储在 **本地计算机** 位置。<br /><br /> 默认值为空字符串。|  
|**AffiliateApplicationName**|字符串|指定用于企业单一登录 (SSO) 的关联应用程序。<br /><br /> 默认值为空字符串。|  
|**UseSSO**|Boolean|指定是否使用单一登录检索客户端凭据，以便在目标服务器上进行验证。<br /><br /> 默认值︰ **False**|  
|**用户名**|字符串|指定要用于目标服务器的身份验证的用户名称时 **UseSSO** 属性设置为 **False**。 不必采用“域\用户”格式设置此属性。<br /><br /> 默认值为空字符串。|  
|**密码**|字符串|指定要用于目标服务器的身份验证的密码时 **UseSSO** 属性设置为 **False**。<br /><br /> 默认值为空字符串。|  
|**ProxyToUse**|Enum<br /><br /> -   **无**-为此发送端口不使用代理服务器。<br />-   **默认** -承载此发送端口的发送处理程序中使用的代理设置。<br />-   **UserSpecified** -使用中指定的代理服务器 **ProxyAddress** 属性。|指定要用于传出 HTTP 通信的代理服务器。<br /><br /> 默认值︰ **无**|  
|**ProxyAddress**|字符串|指定代理服务器的地址。 使用 **https** 或 **http** 根据安全配置的方案。 這個位址後面可以加上冒號和連接埠編號， 例如，http://127.0.0.1:8080。<br /><br /> 默认值为空字符串。|  
|**ProxyUserName**|字符串|指定用于代理的用户名。 WCF WSHttp 适配器利用 [WSHttpBinding](http://go.microsoft.com/fwlink/?LinkId=81206) 在缓冲的传输模式中与终结点进行通信。 代理凭据 **WSHttpBinding** 是适用的安全模式时才 **传输**, ，或 **无**。 如果你设置 **SecurityMode** 属性 **消息** 或 **TransportWithMessageCredential**, ，WCF WSHttp 适配器不使用中指定的凭据 **ProxyUserName** 和 **代理** 针对代理进行身份验证的属性。 **注意︰**  WCF WSHttp 发送适配器使用代理的基本身份验证。 <br /><br /> 默认值为空字符串。|  
|**代理**|字符串|指定用于代理的密码。<br /><br /> 默认值为空字符串。|  
|**OutboundBodyLocation**|Enum<br /><br /> -   **UseBodyElement** -BizTalk 消息正文部分用于创建的 SOAP 内容**正文**传出消息的元素。<br />-   **UseTemplate** -使用中提供的模板 **OutboundXMLTemplate** 属性来创建的内容 SOAP **正文** 传出消息的元素。<br /><br /> 有关如何使用**OutboundBodyLocation**属性，请参阅[为 WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。|指定 SOAP 数据选择 **正文** 传出的 WCF 消息的元素。<br /><br /> 默认值︰ **UseBodyElement**|  
|**OutboundXMLTemplate**|字符串<br /><br /> 有关如何使用**OutboundXMLTemplate**属性，请参阅[为 WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。|指定的 SOAP 内容的 XML 格式模板 **正文** 的传出消息的元素。 此属性是必需的如果 **OutboundBodyLocation** 属性设置为 **UseTemplate**。<br /><br /> 默认值为空字符串。|  
|**InboundBodyLocation**|Enum<br /><br /> -   **UseBodyElement** -使用 SOAP 的内容**正文**传入消息创建 BizTalk 消息正文部分的元素。 如果 **Body** 元素具有多个子元素，则只有第一个元素将成为 BizTalk 消息正文部分。 此属性仅对要求-响应端口有效。<br />-   **UseEnvelope** -从整个 SOAP 创建 BizTalk 消息正文部分 **信封** 传入消息。<br />-   **UseBodyPath** -使用中的正文路径表达式 **InboundBodyPathExpression** 属性创建 BizTalk 消息正文部分。 针对传入消息的 SOAP **Body** 元素的直接子元素计算正文路径表达式。 此属性仅对要求-响应端口有效。<br /><br /> 有关如何使用**InboundBodyLocation**属性，请参阅[为 WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。|指定 SOAP 数据选择 **正文** 传入 WCF 消息的元素。<br /><br /> 默认值︰ **UseBodyElement**|  
|**InboundBodyPathExpression**|字符串<br /><br /> 有关如何使用**InboundBodyPathExpression**属性，请参阅[WCF 适配器属性架构和属性](../core/wcf-adapters-property-schema-and-properties.md)。|指定正文路径表达式以标识传入消息中用于创建 BizTalk 消息正文部分的特定部分。 此正文路径表达式针对 SOAP 的即时子元素进行评估 **正文** 传入消息的节点。 如果此正文路径表达式返回多个节点，则只选择第一个节点作为 BizTalk 消息正文部分。 此属性是必需的如果 **InboundBodyLocation** 属性设置为 **UseBodyPath**。 此属性仅对要求-响应端口有效。<br /><br /> 默认值为空字符串。|  
|**InboundNodeEncoding**|Enum<br /><br /> -   **Base64** -Base64 编码。<br />-   **十六进制** -十六进制编码。<br />-   **字符串** 编码文本的 utf-8。<br />-   **XML** -WCF 适配器使用由正文路径表达式中所选节点的外部 XML 创建 BizTalk 消息正文 **InboundBodyPathExpression**。|指定 WCF WSHttp 发送适配器用于解码由中指定的正文路径标识的节点的编码类型 **InboundBodyPathExpression**。 此属性是必需的如果 **InboundBodyLocation** 属性设置为 **UseBodyPath**。 此属性仅对要求-响应端口有效。<br /><br /> 默认值︰ **XML**|  
|**PropagateFaultMessage**|Boolean<br /><br /> -   **True** -失败对订阅应用程序的出站处理将消息路由 （如另一个接收端口或业务流程计划）。<br />-   **False** -挂起失败的消息并生成否定确认 (NACK)。|指定是路由还是挂起在出站处理中失败的消息。<br /><br /> 此属性仅对要求-响应端口有效。<br /><br /> 默认值︰ **True**|  
  
## <a name="configure-a-wcf-wshttp-send-port-with-the-biztalk-administration-console"></a>使用 BizTalk 管理控制台中配置 WCF WSHttp 发送端口
  
 您可以在 BizTalk 管理控制台中设置 WCF-WSHttp 发送端口适配器变量。 如果没有为发送端口设置属性，将使用 WCF-WSHttp 发送端口配置的默认值，如前表所示。  
  
## <a name="configure-variables-for-a-wcf-wshttp-send-port"></a>配置变量 WCF WSHttp 发送端口  
  
1.  在 [BizTalk 管理主控台] 中建立新的傳送埠，或按兩下現有的傳送埠進行修改。 有关详细信息，请参阅[如何创建发送端口](../core/how-to-create-a-send-port2.md)。 配置所有发送端口选项并指定 **WCF WSHttp** 为 **类型** 选项 **传输** 部分 **常规** 选项卡。  
  
2.  上 **常规** 选项卡上，在 **传输** 部分中，单击 **配置** 按钮旁边 **类型**。  
  
3.  在 **WCF WSHttp 传输属性** 对话框中，在 **常规** 选项卡上配置的终结点地址，服务标识，与 **SOAPAction** WCF WSHttp 发送端口的 HTTP 标头。 有关详细信息**常规**选项卡中**WCF WSHttp 传输属性**对话框中，请参阅**WCF WSHttp 传输属性对话框中，发送，常规**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  
  
4.  在 **WCF WSHttp 传输属性** 对话框中，在 **绑定** 选项卡上配置的超时、 编码和事务属性。 有关详细信息**绑定**选项卡中**WCF WSHttp 传输属性**对话框中，请参阅**WCF WSHttp 传输属性对话框中，发送，绑定**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  
  
5.  在 **WCF WSHttp 传输属性** 对话框中，在 **安全** 选项卡上，定义 WCF WSHttp 发送端口的安全功能。 有关详细信息**安全**选项卡中**WCF WSHttp 传输属性**对话框中，请参阅**WCF WSHttp 传输属性对话框中，发送，安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
6.  在 **WCF WSHttp 传输属性** 对话框中，在 **代理** 选项卡上配置的代理设置 WCF WSHttp 发送端口。 有关详细信息**代理**选项卡中**WCF WSHttp 传输属性**对话框中，请参阅**WCF WSHttp 传输属性对话框中，发送，代理**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
7.  在 **WCF WSHttp 传输属性** 对话框中，在 **消息** 选项卡上，指定 SOAP 数据选择 **正文** 元素。 有关详细信息**消息**选项卡中**WCF WSHttp 传输属性**对话框中，请参阅**WCF WSHttp 传输属性对话框中，发送消息**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="configure-a-wcf-wshttp-send-port-programmatically"></a>以编程方式配置 WCF WSHttp 发送端口
  
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
  
## <a name="see-also"></a>另请参阅  
 [WCF 适配器属性架构和属性](../core/wcf-adapters-property-schema-and-properties.md)   
 [配置 WCF WSHttp 适配器](../core/configuring-the-wcf-wshttp-adapter.md)   
 [为 WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)   
 [将证书安装适用于这些 WCF 适配器](../core/installing-certificates-for-the-wcf-adapters.md)   
 [使用 WCF 适配器上下文属性配置动态发送端口](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)