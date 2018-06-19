---
title: 如何配置 WCF NetTcp 发送端口 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a8fff07e-b08e-4f95-8ce2-27b508674a5c
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f46c4b521c754bd2096916a03e356262dfa4d46
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
ms.locfileid: "25974115"
---
# <a name="how-to-configure-a-wcf-nettcp-send-port"></a>如何配置 WCF-NetTcp 发送端口
可以通过编程方式或使用 BizTalk 管理控制台来配置 WCF-NetTcp 发送端口。  
  
## <a name="configuration-properties"></a>配置属性
  
 BizTalk 资源管理器对象模型公开了用于发送端口名为的特定于适配器的接口 **ITransportInfo** 具有 **TransportTypeData** 读/写属性。 此属性接受 XML 字符串的名称-值对形式的 WCF-NetTcp 发送端口配置属性包。  
  
 **TransportTypeData** 属性 **ITransportInfo** 界面不是必需。 如果未设置该属性，则适配器将使用 WCF-NetTcp 发送端口配置的默认值，如下表所示。  
  
 下表列出了可在 BizTalk 浏览器对象模型中为 WCF-NetTcp 发送端口设置的配置属性。  
  
|属性名称|型別|Description|  
|-------------------|----------|-----------------|  
|**标识**|XML Blob<br /><br /> 示例︰<br /><br /> &lt;标识&gt;<br /><br /> &lt;userPrincipalName value="username@contoso.com" /&gt;<br /><br /> &lt;/identity&gt;|指定此发送端口预期的服务标识。 这些设置支持此发送端口对服务进行验证。 在客户端与服务进行握手的过程中，Windows Communication Foundation (WCF) 基础结构将确保预期服务的标识与此元素的值保持一致。<br /><br /> 默认值为空字符串。|  
|**StaticAction**|字符串|指定 **SOAPAction** 传出消息的标头字段。 此外可以通过消息上下文属性设置此属性 **WCF。操作** 在管道或业务流程。 你可以通过两种方式指定此值︰ 单个操作格式和操作映射格式。 如果将此属性设置中的单个操作格式-例如， http://contoso.com/Svc/Op1- **SOAPAction**标头为传出消息始终设置为此属性中指定的值。<br /><br /> 如果在操作映射格式，传出中设置此属性 **SOAPAction** 标头由 **BTS。操作** 上下文属性。 例如，如果此属性设置为以下 XML 格式和**BTS。操作**属性设置为 Op1，WCF 发送适配器使用http://contoso.com/Svc/Op1为传出**SOAPAction**标头。<br /><br /> \<BtsActionMapping\><br /><br /> \<Operation Name="Op1" Action="http://contoso.com/Svc/Op1" /\><br /><br /> \<Operation Name="Op2" Action="http://contoso.com/Svc/Op2" /\><br /><br /> \</BtsActionMapping\><br /><br /> 如果传出消息来自的业务流程端口时，动态设置业务流程实例 **BTS。操作** 与操作名称的端口的属性。 如果使用基于内容的路由路由传出消息，则可以设置 **BTS。操作** 管道组件中的属性。<br /><br /> 默认值为空字符串。|  
|**OpenTimeout**|**System.TimeSpan**|指定一个时间跨度值来表示为完成信道打开操作提供的时间间隔。<br /><br /> 默认值：00:01:00|  
|**SendTimeout**|**System.TimeSpan**|指定一个时间跨度值来表示为完成发送操作提供的时间间隔。 如果使用要求-响应发送端口，则此值指定完成整个交互的时间跨度（即使服务返回一条大消息）。<br /><br /> 默认值：00:01:00|  
|**CloseTimeout**|**System.TimeSpan**|指定一个时间跨度值来表示为完成信道关闭操作提供的时间间隔。<br /><br /> 默认值：00:01:00|  
|**MaxReceivedMessageSize**|Integer|指定网络上可接收的消息的最大大小（包括标头），以字节为单位。 消息的大小受为每条消息分配的内存量的限制。 你可以使用此属性来降低受拒绝服务 (DoS) 攻击的可能性。<br /><br /> WCF NetTcp 适配器利用 [NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087) 在缓冲的传输模式中与终结点进行通信的类。 对于缓冲的传输模式中， [NetTcpBinding.MaxBufferSize](http://go.microsoft.com/fwlink/?LinkId=81088) 属性也始终等于此属性的值。<br /><br /> 默认值：65536|  
|**EnableTransaction**|Boolean|指定是否为传输到目标服务并从 MessageBox 数据库中使用的事务处理协议中指定的事务上下文中删除一条消息 **TransactionProtocol** 属性。<br /><br /> 默认值︰ **False**|  
|**TransactionProtocol**|Enum<br /><br /> -   **OleTransaction**<br />-   **Ws-atomictransaction**|指定要与此绑定一起使用的事务协议。<br /><br /> 默认值︰ **OleTransaction**|  
|**SecurityMode**|Enum<br /><br /> -   **无**<br />-   **消息**<br />-   **传输**<br />-   **TransportWithMessageCredential**<br /><br /> 有关成员名称的详细信息**SecurityMode**属性，请参阅**安全模式**中的属性**Wcf-nettcp 传输属性对话框中，发送，安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。|指定使用的安全性類型。<br /><br /> 默认值︰ **传输**|  
|**TransportClientCredentialType**|Enum<br /><br /> -   **无**<br />-   **Windows**<br />-   **证书**<br /><br /> 有关成员名称的详细信息**TransportClientCredentialType**属性，请参阅**传输客户端凭据类型**中的属性**Wcf-nettcp 传输属性对话框中，发送，安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。|指定执行发送端口验证时使用的凭据类型。<br /><br /> 默认值︰ **Windows**|  
|**TransportProtectionLevel**|Enum<br /><br /> -   **无**-无保护。<br />-   **登录** -消息进行签名。<br />-   **EncryptAndSign** -消息进行加密和签名。|指定 TCP 传输级别的安全性。 消息签名降低了在消息传输过程中第三方对消息进行篡改的风险。 加密为传输过程提供了数据级保密功能。<br /><br /> 默认值︰ **EncryptAndSign**|  
|**MessageClientCredentialType**|Enum<br /><br /> -   **无**<br />-   **Windows**<br />-   **用户名**<br />-   **证书**<br /><br /> 有关成员名称的详细信息**MessageClientCredentialType**属性，请参阅**消息客户端凭据类型**中的属性**Wcf-nettcp 传输属性对话框框中，发送，安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。|指定使用基于消息的安全性对客户端执行验证时所用的凭据类型。<br /><br /> 默认值︰ **Windows**|  
|**AlgorithmSuite**|Enum<br /><br /> 有关成员名称的详细信息**AlgorithmSuite**属性，请参阅**算法套件**中的属性**Wcf-nettcp 传输属性对话框中，发送，安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。|指定訊息加密和 Key Wrap 演算法。 这些算法与“安全策略语言”(WS-SecurityPolicy) 规范中指定的算法一致。<br /><br /> 默认值︰ **Basic256**|  
|**ClientCertificate**|字符串|指定用于向服务验证此发送端口的 X.509 证书的指纹。 此属性是必需的如果 **ClientCredentialsType** 属性设置为 **证书**。 此属性使用的证书必须安装到 **我** 将存储在 **当前用户** 位置。<br /><br /> 默认值为空字符串。|  
|**AffiliateApplicationName**|字符串|指定用于企业单一登录 (SSO) 的关联应用程序。<br /><br /> 默认值为空字符串。|  
|**UseSSO**|Boolean|指定是否使用单一登录检索客户端凭据，以便在目标服务器上进行验证。<br /><br /> 默认值︰ **False**|  
|**用户名**|字符串|指定要用于目标服务器的身份验证的用户名称时 **UseSSO** 属性设置为 **False**。 不必采用“域\用户”格式设置此属性。<br /><br /> 默认值为空字符串。|  
|**密码**|字符串|指定要用于目标服务器的身份验证的密码时 **UseSSO** 属性设置为 **False**。<br /><br /> 默认值为空字符串。|  
|**OutboundBodyLocation**|Enum<br /><br /> -   **UseBodyElement** -BizTalk 消息正文部分用于创建的 SOAP 内容**正文**传出消息的元素。<br />-   **UseTemplate** -使用中提供的模板 **OutboundXMLTemplate** 属性来创建的内容 SOAP **正文** 传出消息的元素。<br /><br /> 有关如何使用**OutboundBodyLocation**属性，请参阅[为 WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。|指定 SOAP 数据选择 **正文** 传出的 WCF 消息的元素。<br /><br /> 默认值︰ **UseBodyElement**|  
|**OutboundXMLTemplate**|字符串<br /><br /> 有关如何使用**OutboundXMLTemplate**属性，请参阅[为 WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。|指定的 SOAP 内容的 XML 格式模板 **正文** 的传出消息的元素。 此属性是必需的如果 **OutboundBodyLocation** 属性设置为 **UseTemplate**。<br /><br /> 默认值为空字符串。|  
|**InboundBodyLocation**|Enum<br /><br /> -   **UseBodyElement** -使用 SOAP 的内容**正文**传入消息创建 BizTalk 消息正文部分的元素。 如果 **Body** 元素具有多个子元素，则只有第一个元素将成为 BizTalk 消息正文部分。 此属性仅对要求-响应端口有效。<br />-   **UseEnvelope** -从整个 SOAP 创建 BizTalk 消息正文部分 **信封** 传入消息。<br />-   **UseBodyPath** -使用中的正文路径表达式 **InboundBodyPathExpression** 属性创建 BizTalk 消息正文部分。 针对传入消息的 SOAP **Body** 元素的直接子元素计算正文路径表达式。 此属性仅对要求-响应端口有效。<br /><br /> 有关如何使用**InboundBodyLocation**属性，请参阅[为 WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。|指定 SOAP 数据选择 **正文** 传入 WCF 消息的元素。<br /><br /> 默认值︰ **UseBodyElement**|  
|**InboundBodyPathExpression**|字符串<br /><br /> 有关如何使用**InboundBodyPathExpression**属性，请参阅[WCF 适配器属性架构和属性](../core/wcf-adapters-property-schema-and-properties.md)。|指定正文路径表达式以标识传入消息中用于创建 BizTalk 消息正文部分的特定部分。 此正文路径表达式针对 SOAP 的即时子元素进行评估 **正文** 传入消息的节点。 如果此正文路径表达式返回多个节点，则只选择第一个节点作为 BizTalk 消息正文部分。 此属性是必需的如果 **InboundBodyLocation** 属性设置为 **UseBodyPath**。 此属性仅对要求-响应端口有效。<br /><br /> 默认值为空字符串。|  
|**InboundNodeEncoding**|Enum<br /><br /> -   **XML**<br />-   **Base64** -Base64 编码。<br />-   **十六进制** -十六进制编码。<br />-   **字符串** 编码文本的 utf-8。<br />-   **XML** -WCF 适配器使用由正文路径表达式中所选节点的外部 XML 创建 BizTalk 消息正文 **InboundBodyPathExpression**。|指定的编码 WCF NetTcp 发送适配器使用的类型进行解码为标识中指定的 XPath 节点 **InboundBodyPathExpression**。 此属性是必需的如果 **InboundBodyLocation** 属性设置为 **UseBodyPath**。 此属性仅对要求-响应端口有效。<br /><br /> 默认值︰ **XML**|  
|**PropagateFaultMessage**|Boolean<br /><br /> -   **True** -失败对订阅应用程序的出站处理将消息路由 （如另一个接收端口或业务流程计划）。<br />-   **False** -挂起失败的消息并生成否定确认 (NACK)。|指定是路由还是挂起在出站处理中失败的消息。<br /><br /> 此属性仅对要求-响应端口有效。<br /><br /> 默认值︰ **True**|  
  
 **如何使用 BizTalk 管理控制台中配置 WCF NetTcp 发送端口**  
  
 您可以在 BizTalk 管理控制台中设置 WCF-NetTcp 发送端口适配器变量。 如果没有为发送端口设置属性，将使用 WCF-NetTcp 发送端口配置的默认值，如前表所示。  
  
## <a name="configure-variables-for-a-wcf-nettcp-send-port"></a>配置变量 WCF NetTcp 发送端口  
  
1.  在 [BizTalk 管理主控台] 中建立新的傳送埠，或按兩下現有的傳送埠進行修改。 有关详细信息，请参阅[如何创建发送端口](../core/how-to-create-a-send-port2.md)。 配置所有发送端口选项并指定 **WCF NetTcp** 为 **类型** 选项 **传输** 部分 **常规** 选项卡。  
  
2.  上 **常规** 选项卡上，在 **传输** 部分中，单击 **配置** 按钮旁边 **类型**。  
  
3.  在 **Wcf-nettcp 传输属性** 对话框中，在 **常规** 选项卡上配置的终结点地址，服务标识，与 **SOAPAction** WCF NetTcp 的标头发送端口。 有关详细信息**常规**选项卡中**Wcf-nettcp 传输属性**对话框中，请参阅**Wcf-nettcp 传输属性对话框中，发送，常规**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  
  
4.  在 **Wcf-nettcp 传输属性** 对话框中，在 **绑定** 选项卡上配置的超时和事务的属性。 有关详细信息**绑定**选项卡中**Wcf-nettcp 传输属性**对话框中，请参阅**Wcf-nettcp 传输属性对话框中，发送，绑定**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  
  
5.  在 **Wcf-nettcp 传输属性** 对话框中，在 **安全** 选项卡上，定义 WCF NetTcp 发送端口的安全功能。 有关详细信息**安全**选项卡中**Wcf-nettcp 传输属性**对话框中，请参阅**Wcf-nettcp 传输属性对话框中，发送，安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  
  
6.  在 **Wcf-nettcp 传输属性** 对话框中，在 **消息** 选项卡上，指定 SOAP 数据选择 **正文** 元素。 有关详细信息**消息**选项卡中**Wcf-nettcp 传输属性**对话框中，请参阅**Wcf-nettcp 传输属性对话框中，发送消息**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="configure-a-wcf-nettcp-send-port-programmatically"></a>以编程方式配置 WCF NetTcp 发送端口
  
 可使用以下格式设置属性：  
  
 \<CustomProps\>  
  
```  
  <UseSSO vt="11">0</UseSSO>  
  <InboundBodyLocation vt="8">UseBodyElement</InboundBodyLocation>  
  <InboundBodyPathExpression vt="8" />  
  <MessageClientCredentialType vt="8">Windows</MessageClientCredentialType>  
  <SendTimeout vt="8">00:01:00</SendTimeout>  
  <OutboundXmlTemplate vt="8"><bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="xml"/></OutboundXmlTemplate>  
  <OpenTimeout vt="8">00:01:00</OpenTimeout>  
  <AlgorithmSuite vt="8">Basic256</AlgorithmSuite>  
  <SecurityMode vt="8">Transport</SecurityMode>  
  <TransportClientCredentialType vt="8">Windows</TransportClientCredentialType>  
  <ClientCertificate vt="8" />  
  <TransactionProtocol vt="8">OleTransactions</TransactionProtocol>  
  <MaxReceivedMessageSize vt="3">2097152</MaxReceivedMessageSize>  
  <StaticAction vt="8">http://www.northwindtraders.com/Service/Operation</StaticAction>  
  <TransportProtectionLevel vt="8">EncryptAndSign</TransportProtectionLevel>  
  <CloseTimeout vt="8">00:01:00</CloseTimeout>  
  <EnableTransaction vt="11">0</EnableTransaction>  
  <InboundNodeEncoding vt="8">Xml</InboundNodeEncoding>  
  <PropagateFaultMessage vt="11">-1</PropagateFaultMessage>  
  <OutboundBodyLocation vt="8">UseBodyElement</OutboundBodyLocation>  
</CustomProps>  
  
```  
  
 下面的代码段说明了如何创建 WCF-NetTcp 发送端口：  
  
```  
// Use BizTalk Explorer object model to create new WCF-NetTcp send port.  
string server = System.Environment.MachineName;  
string database = "BizTalkMgmtDb";  
string connectionString = string.Format("Server={0};Database={1};Integrated Security=true", server, database);  
string transportConfigData = @"<CustomProps>  
                                 <StaticAction vt=""8"">http://www.northwindtraders.com/Service/Operation</StaticAction>  
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
sendPort.PrimaryTransport.TransportType = explorer.ProtocolTypes["WCF-NetTcp"];  
sendPort.PrimaryTransport.Address = "net.tcp://mycomputer/private/samplequeue";  
sendPort.PrimaryTransport.TransportTypeData = transportConfigData; // propertyData; // need to change  
sendPort.SendPipeline = explorer.Pipelines["Microsoft.BizTalk.DefaultPipelines.PassThruTransmit"];  
// Save  
explorer.SaveChanges();  
```  
  
## <a name="see-also"></a>另请参阅  
 [WCF 适配器属性架构和属性](../core/wcf-adapters-property-schema-and-properties.md)   
 [为 WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)   
 [将证书安装适用于这些 WCF 适配器](../core/installing-certificates-for-the-wcf-adapters.md)   
 [配置 WCF NetTcp 适配器](../core/configuring-the-wcf-nettcp-adapter.md)   
 [使用 WCF 适配器上下文属性配置动态发送端口](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)