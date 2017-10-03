---
title: "创建接收位置和以编程方式发送端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 47850e66-ce33-4c6a-8190-168071792c0b
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b29e5b275bdf5645717298f82b27aca7db36e034
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="create-the-receive-location-and-send-port-programmatically"></a>创建接收位置和以编程方式发送端口
配置 WCF BasicHttp 接收位置和以编程方式发送端口。 若要使用 BizTalk 管理控制台，请参阅[WCF BasicHttp 适配器](../core/wcf-basichttp-adapter.md)。 
  
## <a name="configure-the-receive-location-programmatically"></a>以编程方式配置接收位置  
  
 使用 BizTalk 浏览器对象模型，您可以通过编程方式创建和配置接收位置。 BizTalk 资源管理器对象模型公开了**IReceiveLocation**接收具有的位置配置接口**TransportTypeData**读/写属性。 此属性以 XML 字符串的名称-值对形式接受 WCF-BasicHttp 接收位置配置属性包。 若要在 BizTalk 资源管理器对象模型中设置此属性，必须设置**InboundTransportLocation**属性**IReceiveLocation**接口。  
  
 **TransportTypeData**属性**IReceiveLocation**接口不需要设置。 如果未设置该属性，则 WCF-BasicHttp 适配器将使用 WCF-BasicHttp 接收位置配置的默认值，如下表所示。  
 
 下面的代码段演示如何创建 WCF BasicHttp 接收位置使用 BizTalk 资源管理器对象模型：  
  
```  
// Use BizTalk Explorer object model to create new WCF-BasicHttp receive location   
string server = System.Environment.MachineName;  
string database = "BizTalkMgmtDb";  
string connectionString = string.Format("Server={0};Database={1};Integrated Security=true", server, database);  
string transportConfigData = @"<CustomProps>  
  \<InboundBodyLocation vt=""8"">UseBodyElement</InboundBodyLocation>  
  \<UseSSO vt=""11"">0</UseSSO>  
  \<Identity vt=""8"">  
    <identity>  
    \<userPrincipalName value=""username@contoso.com"" />  
    </identity>  
  </Identity>  
</CustomProps>";  
//requires project reference to \Program Files\Microsoft BizTalk Server 2009\Developer Tools\Microsoft.BizTalk.ExplorerOM.dll  
BtsCatalogExplorer explorer = new Microsoft.BizTalk.ExplorerOM.BtsCatalogExplorer();  
explorer.ConnectionString = connectionString;  
// Add a new BizTalk application  
Application application = explorer.AddNewApplication();  
application.Name = "SampleBizTalkApplication";  
// Save  
explorer.SaveChanges();  
// Add a new one-way receive port  
IReceivePort receivePort = application.AddNewReceivePort(false);  
receivePort.Name = "SampleReceivePort";  
// Add a new one-way receive location  
IReceiveLocation recieveLocation = receivePort.AddNewReceiveLocation();  
recieveLocation.Name = "SampleReceiveLocation";  
// Find a receive handler for WCF-BasicHttp  
int i = 0;  
for(i=0; i < explorer.ReceiveHandlers.Count; ++i)   
{  
    if("WCF-BasicHttp" == explorer.ReceiveHandlers[i].TransportType.Name)  
        break;  
}  
recieveLocation.ReceiveHandler = explorer.ReceiveHandlers[i];  
recieveLocation.Address = "/samplepath/sampleservice.svc";  
recieveLocation.ReceivePipeline = explorer.Pipelines["Microsoft.BizTalk.DefaultPipelines.PassThruReceive"];  
recieveLocation.TransportType = explorer.ProtocolTypes["WCF-BasicHttp"];  
recieveLocation.TransportTypeData = transportConfigData;  
// Save  
explorer.SaveChanges();  
  
```  

你可以使用以下格式设置中的属性`<CustomProps>`: 
  
```  
<CustomProps>  
  <ServiceCertificate vt="8" />  
  <InboundBodyLocation vt="8">UseBodyElement</InboundBodyLocation>  
  <UseSSO vt="11">0</UseSSO>  
  <MessageClientCredentialType vt="8">UserName</MessageClientCredentialType>  
  <InboundBodyPathExpression vt="8" />  
  <SendTimeout vt="8">00:01:00</SendTimeout>  
  <OutboundXmlTemplate vt="8">\<bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="xml"/></OutboundXmlTemplate>  
  <OpenTimeout vt="8">00:01:00</OpenTimeout>  
  <Identity vt="8">  
    <identity>  
    <userPrincipalName value="username@contoso.com" />  
    </identity>  
  </Identity>  
  <AlgorithmSuite vt="8">Basic256</AlgorithmSuite>  
  <SecurityMode vt="8">None</SecurityMode>  
  <TransportClientCredentialType vt="8">None</TransportClientCredentialType>  
  <MaxReceivedMessageSize vt="3">2097152</MaxReceivedMessageSize>  
  <TextEncoding vt="8">utf-8</TextEncoding>  
  <CloseTimeout vt="8">00:01:00</CloseTimeout>  
  <SuspendMessageOnFailure vt="11">0</SuspendMessageOnFailure>  
  <InboundNodeEncoding vt="8">Xml</InboundNodeEncoding>  
  <IncludeExceptionDetailInFaults vt="11">0</IncludeExceptionDetailInFaults>  
  <MaxConcurrentCalls vt="3">16</MaxConcurrentCalls>  
  <MessageEncoding vt="8">Text</MessageEncoding>  
  <OutboundBodyLocation vt="8">UseBodyElement</OutboundBodyLocation>  
</CustomProps>  
  
```   
  
下表列出了可以设置为接收位置的配置属性：  
  
|属性名称|类型|Description|  
|-------------------|----------|-----------------|  
|**标识**|XML Blob<br /><br /> 例如：<br /><br /> &lt;标识&gt;<br /><br /> &lt;userPrincipalName 值 ="username@contoso.com"/&gt;<br /><br /> &lt;/identity&gt;|指定此接收位置提供的服务的标识。 可以为指定的值**标识**属性而异的安全配置。 通过这些设置，客户端可对此接收位置进行验证。 在客户端与服务进行握手的过程中，Windows Communication Foundation (WCF) 基础结构将确保预期服务的标识与此元素的值保持一致。<br /><br /> 默认值为空字符串。|  
|**OpenTimeout**|**System.TimeSpan**|指定一个时间跨度值来表示为完成信道打开操作提供的时间间隔。<br /><br /> 默认值：00:01:00|  
|**SendTimeout**|**System.TimeSpan**|指定一个时间跨度值来表示为完成发送操作提供的时间间隔。 如果使用请求-响应接收端口，则此值指定完成整个交互的时间跨度（即使客户端返回一条大消息）。<br /><br /> 默认值：00:01:00|  
|**CloseTimeout**|**System.TimeSpan**|指定一个时间跨度值来表示为完成信道关闭操作提供的时间间隔。<br /><br /> 默认值：00:01:00|  
|**MaxReceivedMessageSize**|Integer|指定网络上可接收的消息的最大大小（包括标头），以字节为单位。 消息的大小受为每条消息分配的内存量的限制。 你可以使用此属性来降低受拒绝服务 (DoS) 攻击的可能性。<br /><br /> WCF BasicHttp 适配器利用[BasicHttpBinding](http://go.microsoft.com/fwlink/?LinkId=81086)在缓冲的传输模式中与终结点进行通信的类。 对于缓冲的传输模式中， [BasicHttpBinding.MaxBufferSize](http://go.microsoft.com/fwlink/?LinkId=80659)属性也始终等于此属性的值。<br /><br /> 默认值：65536|  
|**MessageEncoding**|Enum<br /><br /> -   **文本**-使用文本消息编码器。<br />-   **Mtom** -使用消息传输优化机制 1.0 (MTOM) 编码器。|指定用于对 SOAP 消息进行编码的编码器。<br /><br /> 默认值：**文本**|  
|**TextEncoding**|Enum<br /><br /> -   **unicodeFFF** -Unicode BigEndian 编码。<br />-   **utf-16** -16 位编码。<br />-   **utf-8** -8 位编码|指定的字符集编码要用于在绑定上发出消息时**MessageEncoding**属性设置为**文本**。<br /><br /> 默认值： **utf-8**|  
|**MaxConcurrentCalls**|Integer|指定针对单个服务实例的并发调用的数目。 超出此限制的调用将在队列中排队。 此属性的范围是从 1 到**Int32.MaxValue**。<br /><br /> 默认值：200|  
|**SecurityMode**|Enum<br /><br /> -   **无**<br />-   **消息**<br />-   **传输**<br />-   **TransportWithMessageCredential**<br />-   **TransportCredentialOnly**<br /><br /> 有关成员名称的详细信息**SecurityMode**属性，请参阅**安全模式**中的属性**WCF BasicHttp 传输属性对话框中，接收，安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。|指定使用的安全类型。<br /><br /> 默认值：**无**|  
|**TransportClientCredentialType**|有关成员名称的详细信息**TransportClientCredentialType**属性，请参阅**传输客户端凭据类型**中的属性**WCF BasicHttp 传输属性对话框中，接收、 安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。|指定执行客户端验证时要使用的凭据类型。<br /><br /> 默认值：**无**|  
|**MessageClientCredentialType**|Enum<br /><br /> -   **用户名**<br />-   **证书**<br /><br /> 有关成员名称的详细信息**MessageClientCredentialType**属性，请参阅**消息客户端凭据类型**中的属性**WCF BasicHttp 传输属性对话框框中，接收、 安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。|指定使用基于消息的安全性对客户端执行验证时所用的凭据类型。<br /><br /> 默认值：**用户名**|  
|**AlgorithmSuite**|Enum<br /><br /> 有关成员名称的详细信息**AlgorithmSuite**属性，请参阅**算法套件**中的属性**WCF BasicHttp 传输属性对话框中，接收，安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。|指定消息加密和密钥包装算法。 这些算法与“安全策略语言”(WS-SecurityPolicy) 规范中指定的算法一致。<br /><br /> 默认值： **Basic256**|  
|**ServiceCertificate**|字符串|为此接收位置指定 X.509 证书的指纹，客户端利用该指纹验证服务。 此属性使用的证书必须安装到**我**将存储在**当前用户**位置。 **注意：**必须安装到的服务证书**当前用户**承载此接收位置接收处理程序的用户帐户的位置。 <br /><br /> 默认值为空字符串。|  
|**UseSSO**|Boolean|指定是否使用企业单一登录 (SSO) 检索客户端凭据以颁发 SSO 票证。 有关安全配置的详细信息支持 SSO，请参阅"企业单一登录可支持性的 WCF BasicHttp 接收适配器"一节中**WCF BasicHttp 传输属性对话框中，接收，安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。<br /><br /> 默认值： **False**|  
|**InboundBodyLocation**|Enum<br /><br /> -   **UseBodyElement** -使用 SOAP 的内容**正文**传入消息创建 BizTalk 消息正文部分的元素。 如果 **Body** 元素具有多个子元素，则只有第一个元素将成为 BizTalk 消息正文部分。<br />-   **UseEnvelope** -从整个 SOAP 创建 BizTalk 消息正文部分**信封**传入消息。<br />-   **UseBodyPath** -使用中的正文路径表达式**InboundBodyPathExpression**属性创建 BizTalk 消息正文部分。 针对传入消息的 SOAP **Body** 元素的直接子元素计算正文路径表达式。 此属性仅对要求-响应端口有效。<br /><br /> 有关如何使用**InboundBodyLocation**属性，请参阅[为 WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。|指定 SOAP 数据选择**正文**传入 WCF 消息的元素。<br /><br /> 默认值： **UseBodyElement**|  
|**InboundBodyPathExpression**|字符串<br /><br /> 有关如何使用**InboundBodyPathExpression**属性，请参阅[WCF 适配器属性架构和属性](../core/wcf-adapters-property-schema-and-properties.md)。|指定正文路径表达式以标识传入消息中用于创建 BizTalk 消息正文部分的特定部分。 此正文路径表达式针对 SOAP 的即时子元素进行评估**正文**传入消息的节点。 如果此正文路径表达式返回多个节点，则只选择第一个节点作为 BizTalk 消息正文部分。 此属性是必需的如果**InboundBodyLocation**属性设置为**UseBodyPath**。<br /><br /> 默认值为空字符串。|  
|**InboundNodeEncoding**|Enum<br /><br /> -   **Base64** -Base64 编码。<br />-   **十六进制**-十六进制编码。<br />-   **字符串**编码文本的 utf-8<br />-   **XML** -WCF 适配器使用由正文路径表达式中所选节点的外部 XML 创建 BizTalk 消息正文**InboundBodyPathExpression**。|指定的编码，WCF BasicHttp 接收适配器使用要解码识别由正文路径表达式中指定的节点类型**InboundBodyPathExpression**。 此属性是必需的如果**InboundBodyLocation**属性设置为**UseBodyPath**。<br /><br /> 默认值： **XML**|  
|**OutboundBodyLocation**|Enum<br /><br /> -   **UseBodyElement** -BizTalk 消息正文部分用于创建的 SOAP 内容**正文**的传出的响应消息的元素。<br />-   **UseTemplate** -使用中提供的模板**OutboundXMLTemplate**属性来创建的内容 SOAP**正文**的传出的响应消息的元素。<br /><br /> 有关如何使用**OutboundBodyLocation**属性，请参阅[为 WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。|指定 SOAP 数据选择**正文**传出的 WCF 消息的元素。 此属性仅对请求响应接收位置有效。<br /><br /> 默认值： **UseBodyElement**|  
|**OutboundXMLTemplate**|字符串<br /><br /> 有关如何使用**OutboundXMLTemplate**属性，请参阅[为 WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。|指定的 SOAP 内容的 XML 格式模板**正文**的传出响应消息的元素。 此属性是必需的如果**OutboundBodyLocation**属性设置为**UseTemplate**。 此属性仅对请求响应接收位置有效。<br /><br /> 默认值为空字符串。|  
|**SuspendMessageOnFailure**|Boolean|指定是否将由于接收管道故障或路由故障而导致入站处理失败的请求消息挂起。<br /><br /> 默认值： **False**|  
|**IncludeExceptionDetailInFaults**|Boolean|指定是否将托管异常信息包括在返回给客户端以便进行调试的 SOAP 错误的详细信息中。<br /><br /> 默认值： **False**|  
  
## <a name="configure-the-send-port-programmatically"></a>以编程方式配置发送端口   

 下面的代码段演示如何创建使用 BizTalk 资源管理器对象模型的 WCF BasicHttp 发送端口：    
  
```  
// Use BizTalk Explorer object model to create new WCF-BasicHttp send port.  
string server = System.Environment.MachineName;  
string database = "BizTalkMgmtDb";  
string connectionString = string.Format("Server={0};Database={1};Integrated Security=true", server, database);  
string transportConfigData = @"<CustomProps>  
                                 \<StaticAction vt=""8"">http://www.northwindtraders.com/Service/Operation</StaticAction>  
                                 \<MessageEncoding vt=""8"">Text</MessageEncoding>  
                                 \<TextEncoding vt=""8"">utf-8</TextEncoding>  
                                 \<OpenTimeout vt=""8"">00:01:00</OpenTimeout>  
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
sendPort.PrimaryTransport.TransportType = explorer.ProtocolTypes["WCF-BasicHttp"];  
sendPort.PrimaryTransport.Address = "http://mycomputer/samplepath";  
sendPort.PrimaryTransport.TransportTypeData = transportConfigData; // propertyData; // need to change  
sendPort.SendPipeline = explorer.Pipelines["Microsoft.BizTalk.DefaultPipelines.PassThruTransmit"];  
// Save  
explorer.SaveChanges();  
```    

你可以使用以下格式设置中的属性`<CustomProps>`: 
  
```  
<CustomProps>  
  <ServiceCertificate vt="8" />  
  <InboundBodyLocation vt="8">UseBodyElement</InboundBodyLocation>  
  <UseSSO vt="11">0</UseSSO>  
  <MessageClientCredentialType vt="8">UserName</MessageClientCredentialType>  
  <InboundBodyPathExpression vt="8" />  
  <SendTimeout vt="8">00:01:00</SendTimeout>  
  <OutboundXmlTemplate vt="8">\<bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="xml"/></OutboundXmlTemplate>  
  <OpenTimeout vt="8">00:01:00</OpenTimeout>  
  <AlgorithmSuite vt="8">Basic256</AlgorithmSuite>  
  <SecurityMode vt="8">None</SecurityMode>  
  <TransportClientCredentialType vt="8">None</TransportClientCredentialType>  
  <ClientCertificate vt="8" />  
  <ProxyUserName vt="8" />  
  <MaxReceivedMessageSize vt="3">2097152</MaxReceivedMessageSize>  
  <TextEncoding vt="8">utf-8</TextEncoding>  
  <StaticAction vt="8">http://www.northwindtraders.com/Service/Operation</StaticAction>  
  <CloseTimeout vt="8">00:01:00</CloseTimeout>  
  <ProxyToUse vt="8">Default</ProxyToUse>  
  <InboundNodeEncoding vt="8">Xml</InboundNodeEncoding>  
  <PropagateFaultMessage vt="11">-1</PropagateFaultMessage>  
  <ProxyAddress vt="8" />  
  <MessageEncoding vt="8">Text</MessageEncoding>  
  <OutboundBodyLocation vt="8">UseBodyElement</OutboundBodyLocation>  
</CustomProps>  
  
```  

下表列出可以为发送端口设置的配置属性：  
  
|属性名称|类型|Description|  
|-------------------|----------|-----------------|  
|**SecurityMode**|Enum<br /><br /> -   **无**<br />-   **消息**<br />-   **传输**<br />-   **TransportWithMessageCredential**<br />-   **TransportCredentialOnly**<br /><br /> 有关成员名称的详细信息**SecurityMode**属性，请参阅**安全模式**中的属性**WCF BasicHttp 传输属性对话框中，发送，安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。|指定使用的安全类型。<br /><br /> 默认值：**无**|  
|**MessageClientCredentialType**|Enum<br /><br /> -   **用户名**<br />-   **证书**<br /><br /> 有关成员名称的详细信息**MessageClientCredentialType**属性，请参阅**消息客户端凭据类型**中的属性**WCF BasicHttp 传输属性对话框框中，发送，安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。|指定使用基于消息的安全性对客户端执行验证时所用的凭据类型。<br /><br /> 默认值：**用户名**|  
|**TransportClientCredentialType**|Enum<br /><br /> -   **无**<br />-   **基本**<br />-   **Windows**<br />-   **证书**<br />-   **摘要**<br />-   **Ntlm**<br /><br /> 有关成员名称的详细信息**TransportClientCredentialType**属性，请参阅**传输客户端凭据类型**中的属性**WCF BasicHttp 传输属性对话框中，发送，安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。|指定执行发送端口验证时使用的凭据类型。<br /><br /> 默认值：**无**|  
|**UserName**|字符串|指定要用于目标服务器的身份验证的用户名称时**UseSSO**属性设置为**False**。 不必采用“域\用户”格式设置此属性。<br /><br /> 默认值为空字符串。|  
|**密码**|字符串|指定要用于目标服务器的身份验证的密码时**UseSSO**属性设置为**False**。<br /><br /> 默认值为空字符串。|  
|**AffiliateApplicationName**|字符串|指定用于企业单一登录 (SSO) 的关联应用程序。<br /><br /> 默认值为空字符串。|  
|**UseSSO**|Boolean|指定是否使用单一登录检索客户端凭据，以便在目标服务器上进行验证。<br /><br /> 默认值： **False**|  
|**ClientCertificate**|字符串|指定用于向服务验证此发送端口的 X.509 证书的指纹。 此属性是必需的如果**ClientCredentialsType**属性设置为**证书**。 此属性使用的证书必须安装到**我**将存储在**当前用户**位置。<br /><br /> 默认值为空字符串。|  
|**ServiceCertificate**|字符串|指定用于验证服务（此发送端口要将消息发送到的服务）的 X.509 证书的指纹。 此属性使用的证书必须安装到**其他人**将存储在**本地计算机**位置。<br /><br /> 默认值为空字符串。|  
|**ProxyToUse**|Enum<br /><br /> -   **无**-为此发送端口不使用代理服务器。<br />-   **默认**-承载此发送端口的发送处理程序中使用的代理设置。<br />-   **UserSpecified** -使用中指定的代理服务器**ProxyAddress**属性|指定要用于传出 HTTP 通信的代理服务器。<br /><br /> 默认值：**无**|  
|**ProxyAddress**|字符串|指定代理服务器的地址。 使用**https**或**http**根据安全配置的方案。 此地址后面可跟冒号和端口号。 例如，http://127.0.0.1:8080。<br /><br /> 默认值为空字符串。|  
|**ProxyUserName**|字符串|指定用于代理的用户名。 WCF BasicHttp 适配器利用[BasicHttpBinding](http://go.microsoft.com/fwlink/?LinkId=81086)在缓冲的传输模式中与终结点进行通信。 代理凭据**BasicHttpBinding**是适用的安全模式时才**传输**，**无**，或**TransportCredentialOnly**. 如果你设置**SecurityMode**属性**消息**或**TransportWithMessageCredential**，WCF BasicHttp 适配器不使用中指定的凭据**ProxyUserName**和**代理**针对代理进行身份验证的属性。 **注意：** WCF BasicHttp 发送适配器使用基本身份验证代理... <br /><br /> 默认值为空字符串。|  
|**代理**|字符串|指定用于代理的密码。<br /><br /> 默认值为空字符串。|  
|**InboundBodyLocation**|Enum<br /><br /> -   **UseBodyElement** -使用 SOAP 的内容**正文**传入消息创建 BizTalk 消息正文部分的元素。 如果 **Body** 元素具有多个子元素，则只有第一个元素将成为 BizTalk 消息正文部分。 此属性仅对要求-响应端口有效。<br />-   **UseEnvelope** -从整个 SOAP 创建 BizTalk 消息正文部分**信封**传入消息。<br />-   **UseBodyPath** -使用中的正文路径表达式**InboundBodyPathExpression**属性创建 BizTalk 消息正文部分。 针对传入消息的 SOAP **Body** 元素的直接子元素计算正文路径表达式。 此属性仅对要求-响应端口有效。<br /><br /> 有关如何使用**InboundBodyLocation**属性，请参阅[为 WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。|指定 SOAP 数据选择**正文**传入 WCF 消息的元素。<br /><br /> 默认值： **UseBodyElement**|  
|**OutboundBodyLocation**|Enum<br /><br /> -   **UseBodyElement** -BizTalk 消息正文部分用于创建的 SOAP 内容**正文**传出消息的元素。<br />-   **UseTemplate** -使用中提供的模板**OutboundXMLTemplate**属性来创建的内容 SOAP**正文**传出消息的元素。<br /><br /> 有关如何使用**OutboundBodyLocation**属性，请参阅[为 WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。|指定 SOAP 数据选择**正文**传出的 WCF 消息的元素。<br /><br /> 默认值： **UseBodyElement**|  
|**InboundBodyPathExpression**|字符串<br /><br /> 有关如何使用**InboundBodyPathExpression**属性，请参阅[WCF 适配器属性架构和属性](../core/wcf-adapters-property-schema-and-properties.md)。|指定正文路径表达式以标识传入消息中用于创建 BizTalk 消息正文部分的特定部分。 此正文路径表达式针对 SOAP 的即时子元素进行评估**正文**传入消息的节点。 如果此正文路径表达式返回多个节点，则只选择第一个节点作为 BizTalk 消息正文部分。 此属性是必需的如果**InboundBodyLocation**属性设置为**UseBodyPath**。 此属性仅对要求-响应端口有效。<br /><br /> 默认值为空字符串。|  
|**OutboundXMLTemplate**|字符串<br /><br /> 有关如何使用**OutboundXMLTemplate**属性，请参阅[为 WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。|指定的 SOAP 内容的 XML 格式模板**正文**的传出消息的元素。 此属性是必需的如果**OutboundBodyLocation**属性设置为**UseTemplate**。<br /><br /> 默认值为空字符串。|  
|**InboundNodeEncoding**|Enum<br /><br /> -   **Base64** -Base64 编码。<br />-   **十六进制**-十六进制编码。<br />-   **字符串**编码文本的 utf-8<br />-   **XML** -WCF 适配器使用由正文路径表达式中所选节点的外部 XML 创建 BizTalk 消息正文**InboundBodyPathExpression**。|指定的编码的 WCF BasicHttp 发送适配器使用要解码识别由正文路径表达式中指定的节点类型**InboundBodyPathExpression**。 此属性是必需的如果**InboundBodyLocation**属性设置为**UseBodyPath**。 此属性仅对要求-响应端口有效。<br /><br /> 默认值： **XML**|  
|**StaticAction**|字符串|指定**SOAPAction**传出消息的 HTTP 标头字段。 此外可以通过消息上下文属性设置此属性**WCF。操作**在管道或业务流程。 你可以通过两种方式指定此值： 单个操作格式和操作映射格式。 如果将此属性设置中的单个操作格式-例如，http://contoso.com/Svc/Op1- **SOAPAction**标头为传出消息始终设置为此属性中指定的值。<br /><br /> 如果在操作映射格式，传出中设置此属性**SOAPAction**标头由**BTS。操作**上下文属性。 例如，如果此属性设置为以下 XML 格式和**BTS。操作**属性设置为 Op1，为传出的 WCF 发送适配器使用 http://contoso.com/Svc/Op1 **SOAPAction**标头。<br /><br /> \<BtsActionMapping ><br /><br /> \<操作名称 ="Op1"操作 ="http://contoso.com/Svc/Op1"/ ><br /><br /> \<操作名称 ="Op2"操作 ="http://contoso.com/Svc/Op2"/ ><br /><br /> \</ BtsActionMapping ><br /><br /> 如果传出消息来自的业务流程端口时，动态设置业务流程实例**BTS。操作**与操作名称的端口的属性。 如果使用基于内容的路由路由传出消息，则可以设置**BTS。操作**管道组件中的属性。<br /><br /> 默认值为空字符串。|  
|**MaxReceivedMessageSize**|Integer|指定网络上可接收的消息的最大大小（包括标头），以字节为单位。 消息的大小受为每条消息分配的内存量的限制。 你可以使用此属性来降低受拒绝服务 (DoS) 攻击的可能性。<br /><br /> WCF BasicHttp 适配器利用[BasicHttpBinding](http://go.microsoft.com/fwlink/?LinkId=81086)在缓冲的传输模式中与终结点进行通信的类。 对于缓冲的传输模式中， [BasicHttpBinding.MaxBufferSize](http://go.microsoft.com/fwlink/?LinkId=80659)属性也始终等于此属性的值。<br /><br /> 默认值： 65536|  
|**MessageEncoding**|Enum<br /><br /> -   **文本**-使用文本消息编码器。<br />-   **Mtom** -使用消息传输组织机制 1.0 (MTOM) 编码器。|指定用于对 SOAP 消息进行编码的编码器。<br /><br /> 默认值：**文本**|  
|**TextEncoding**|Enum<br /><br /> -   **unicodeFFF** -Unicode BigEndian 编码。<br />-   **utf-16** -16 位编码。<br />-   **utf-8** -8 位编码|指定的字符集编码要用于在绑定上发出消息时**MessageEncoding**属性设置为**文本**。<br /><br /> 默认值： **utf-8**|  
|**SendTimeout**|**System.TimeSpan**|指定一个时间跨度值来表示为完成发送操作提供的时间间隔。 如果使用要求-响应发送端口，则此值指定完成整个交互的时间跨度（即使服务返回一条大消息）。<br /><br /> 默认值：00:01:00|  
|**OpenTimeout**|**System.TimeSpan**|指定一个时间跨度值来表示为完成信道打开操作提供的时间间隔。<br /><br /> 默认值：00:01:00|  
|**CloseTimeout**|**System.TimeSpan**|指定一个时间跨度值来表示为完成信道关闭操作提供的时间间隔。<br /><br /> 默认值：00:01:00|  
|**AlgorithmSuite**|Enum<br /><br /> 有关成员名称的详细信息**AlgorithmSuite**属性，请参阅**算法套件**中的属性**WCF BasicHttp 传输属性对话框中，发送，安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。|指定消息加密和密钥包装算法。 这些算法与“安全策略语言”(WS-SecurityPolicy) 规范中指定的算法一致。<br /><br /> 默认值： **Basic256**|  
|**标识**|XML Blob<br /><br /> 示例：<br /><br /> &lt;标识&gt;<br /><br /> &lt;userPrincipalName 值 ="username@contoso.com"/&gt;<br /><br /> &lt;/identity&gt;|指定此发送端口预期的服务标识。 这些设置支持此发送端口对服务进行验证。 在客户端与服务进行握手的过程中，Windows Communication Foundation (WCF) 基础结构将确保预期服务的标识与此元素的值保持一致。<br /><br /> 默认值为空字符串。|  
|**PropagateFaultMessage**|Boolean<br /><br /> -   **True** -失败对订阅应用程序的出站处理将消息路由 （如另一个接收端口或业务流程计划）。<br />-   **False** -挂起失败的消息并生成否定确认 (NACK)。|指定是路由还是挂起在出站处理中失败的消息。<br /><br /> 此属性仅对要求-响应端口有效。<br /><br /> 默认值： **True**|  
  
## <a name="see-also"></a>另请参阅  
 [WCF 适配器有哪些？](../core/what-are-the-wcf-adapters.md)  
 [使用独立的 WCF 发布 WCF 服务接收适配器](../core/publishing-wcf-services-with-the-isolated-wcf-receive-adapters.md)   
 [配置 IIS 的独立 WCF 接收适配器](../core/configuring-iis-for-the-isolated-wcf-receive-adapters.md)   
 [管理 BizTalk 主机和主机实例](../core/managing-biztalk-hosts-and-host-instances.md)   
 [如何更改服务帐户和密码](../core/how-to-change-service-accounts-and-passwords.md)   
 [将证书安装适用于这些 WCF 适配器](../core/installing-certificates-for-the-wcf-adapters.md)   
 [为 WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)    
  [WCF 适配器属性架构和属性](../core/wcf-adapters-property-schema-and-properties.md)   
 [配置动态发送端口使用 WCF 适配器上下文属性](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)