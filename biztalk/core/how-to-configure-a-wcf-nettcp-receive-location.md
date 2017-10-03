---
title: "如何配置 WCF NetTcp 接收位置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 937862ca-14cb-4eda-8176-38c15423679e
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37ad7fc1ac3ede003c273e789ab465136b8d6abe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-a-wcf-nettcp-receive-location"></a>如何配置 WCF-NetTcp 接收位置
可以通过编程方式或使用 BizTalk 管理控制台来配置 WCF-NetTcp 接收位置。  
  
## <a name="configuration-properties"></a>配置属性
  
 使用 BizTalk 浏览器对象模型，您可以通过编程方式创建和配置接收位置。 BizTalk 资源管理器对象模型公开了**IReceiveLocation**接收具有的位置配置接口**TransportTypeData**读/写属性。 此属性接受名称-值对 XML 字符串形式的 WCF-NetTcp 接收位置配置属性包。 若要在 BizTalk 资源管理器对象模型中设置此属性，必须设置**InboundTransportLocation**属性**IReceiveLocation**接口。  
  
 **TransportTypeData**属性**IReceiveLocation**接口不需要设置。 如果未设置该属性，则 WCF-NetTcp 适配器将使用 WCF-NetTcp 接收位置配置的默认值，如下表所示。  
  
 下表列出了可在 BizTalk 浏览器对象模型中为 WCF-NetTcp 接收位置设置的配置属性：  
  
|属性名称|类型|Description|  
|-------------------|----------|-----------------|  
|**标识**|XML Blob<br /><br /> 例如：<br /><br /> &lt;标识&gt;<br /><br /> &lt;userPrincipalName 值 ="username@contoso.com"/&gt;<br /><br /> &lt;/identity&gt;|指定此接收位置提供的服务的标识。 可以为指定的值**标识**属性而异的安全配置。 通过这些设置，客户端可对此接收位置进行验证。 在客户端与服务进行握手的过程中，Windows Communication Foundation (WCF) 基础结构将确保预期服务的标识与此元素的值保持一致。<br /><br /> 默认值为空字符串。|  
|**OpenTimeout**|**System.TimeSpan**|指定一个时间跨度值来表示为完成信道打开操作提供的时间间隔。<br /><br /> 默认值：00:01:00|  
|**SendTimeout**|**System.TimeSpan**|指定一个时间跨度值来表示为完成发送操作提供的时间间隔。 如果使用请求-响应接收端口，则此值指定完成整个交互的时间跨度（即使客户端返回一条大消息）。<br /><br /> 默认值：00:01:00|  
|**CloseTimeout**|**System.TimeSpan**|指定一个时间跨度值来表示为完成信道关闭操作提供的时间间隔。<br /><br /> 默认值：00:01:00|  
|**MaxReceivedMessageSize**|Integer|指定网络上可接收的消息的最大大小（包括标头），以字节为单位。 消息的大小受为每条消息分配的内存量的限制。 你可以使用此属性来降低受拒绝服务 (DoS) 攻击的可能性。<br /><br /> WCF NetTcp 适配器利用[NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087)在缓冲的传输模式中与终结点进行通信的类。 对于缓冲的传输模式中， [NetTcpBinding.MaxBufferSize](http://go.microsoft.com/fwlink/?LinkId=81088)属性也始终等于此属性的值。<br /><br /> 默认值：65536|  
|**EnableTransaction**|Boolean|指定是否使用从客户端流入的事务将消息提交给 MessageBox 数据库。 如果此属性设置为**True**，要求客户端提交使用事务协议中指定的消息**TransactionProtocol**属性。 如果客户端提交事务作用域之外的消息，则此接收位置将向客户端返回一个异常，并且不会挂起任何消息。<br /><br /> 该选项只可用于单向接收位置。 如果客户端为请求-响应接收位置提交事务上下文中的消息，则会向客户端返回一个异常，并且不会挂起任何消息。<br /><br /> 默认值：30`False`|  
|**TransactionProtocol**|Enum<br /><br /> -   **OleTransaction**<br />-   **Ws-atomictransaction**|指定要与此接收位置一起使用的事务协议。<br /><br /> 默认值： **OleTransaction**|  
|**LeaseTimeout**|**System.TimeSpan**|指定活动的池连接的最大生存期。 指定的时间过后，则连接将关闭后当前的请求已得到处理。<br /><br /> WCF NetTcp 适配器利用[NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087)类与终结点进行通信。 使用时[NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087)在负载平衡方案中，请考虑减少的默认租约超时值。有关负载平衡时使用的详细信息[NetTcpBinding](http://go.microsoft.com/fwlink/?LinkId=81087)，请参阅另请参阅中的相应主题。<br /><br /> 默认值：00:05:00|  
|**MaxConcurrentCalls**|Integer|指定针对单个服务实例的并发调用的数目。 超出此限制的调用将在队列中排队。 此属性的范围是从 1 到 Int32.MaxValue。<br /><br /> 默认值：200|  
|**SecurityMode**|Enum<br /><br /> -   **无**<br />-   **消息**<br />-   **传输**<br />-   **TransportWithMessageCredential**<br /><br /> 有关成员名称的详细信息**SecurityMode**属性，请参阅**安全模式**中的属性**Wcf-nettcp 传输属性对话框中，接收、 安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。|指定使用的安全类型。<br /><br /> 默认值：**传输**|  
|**TransportClientCredentialType**|Enum<br /><br /> -   **无**<br />-   **Windows**<br />-   **证书**<br /><br /> 有关成员名称的详细信息**TransportClientCredentialType**属性，请参阅**传输客户端凭据类型**中的属性**Wcf-nettcp 传输属性对话框中，接收、 安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。|指定执行客户端验证时要使用的凭据类型。<br /><br /> 默认值： **Windows**|  
|**TransportProtectionLevel**|Enum<br /><br /> -   **无**： 无保护。<br />-   **登录**： 对消息进行签名。<br />-   **EncryptAndSign**： 消息进行加密和签名。|定义 TCP 传输一级的安全性。 消息签名降低了在消息传输过程中第三方对消息进行篡改的风险。 加密为传输过程提供了数据级保密功能。<br /><br /> 默认值： **EncryptAndSign**|  
|**MessageClientCredentialType**|Enum<br /><br /> -   **无**<br />-   **Windows**<br />-   **用户名**<br />-   **证书**<br /><br /> 有关成员名称的详细信息**MessageClientCredentialType**属性，请参阅**消息客户端凭据类型**中的属性**Wcf-nettcp 传输属性对话框框中，接收、 安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。|指定使用基于消息的安全性对客户端执行验证时所用的凭据类型。<br /><br /> 默认值： **Windows**|  
|**AlgorithmSuite**|Enum<br /><br /> 有关成员名称的详细信息**AlgorithmSuite**属性，请参阅**算法套件**中的属性**Wcf-nettcp 传输属性对话框中，接收，安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。|指定消息加密和密钥包装算法。 这些算法与“安全策略语言”(WS-SecurityPolicy) 规范中指定的算法一致。<br /><br /> 默认值： **Basic256**|  
|**ServiceCertificate**|字符串|为此接收位置指定 X.509 证书的指纹，客户端利用该指纹验证服务。 此属性使用的证书必须安装到**我**将存储在**当前用户**位置。 **注意：**必须安装到的服务证书**当前用户**承载此接收位置接收处理程序的用户帐户的位置。 <br /><br /> 默认值为空字符串。|  
|**UseSSO**|Boolean|指定是否使用企业单一登录 (SSO) 检索客户端凭据以颁发 SSO 票证。 有关安全配置的详细信息支持 SSO，请参阅"企业单一登录可支持性的 WCF NetTcp 接收适配器"一节中**Wcf-nettcp 传输属性对话框中，接收、 安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。|  
|**InboundBodyLocation**|Enum<br /><br /> -   **UseBodyElement** -使用 SOAP 的内容**正文**传入消息创建 BizTalk 消息正文部分的元素。 如果 **Body** 元素具有多个子元素，则只有第一个元素将成为 BizTalk 消息正文部分。<br />-   **UseEnvelope** -从整个 SOAP 创建 BizTalk 消息正文部分**信封**传入消息。<br />-   **UseBodyPath** -使用中的正文路径表达式**InboundBodyPathExpression**属性创建 BizTalk 消息正文部分。 针对传入消息的 SOAP **Body** 元素的直接子元素计算正文路径表达式。 此属性仅对要求-响应端口有效。<br /><br /> 有关如何使用**InboundBodyLocation**属性，请参阅[为 WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。|指定 SOAP 数据选择**正文**传入 WCF 消息的元素。<br /><br /> 默认值： **UseBodyElement**|  
|**InboundBodyPathExpression**|字符串<br /><br /> 有关如何使用**InboundBodyPathExpression**属性，请参阅[WCF 适配器属性架构和属性](../core/wcf-adapters-property-schema-and-properties.md)。|指定正文路径表达式以标识传入消息中用于创建 BizTalk 消息正文部分的特定部分。 此正文路径表达式针对 SOAP 的即时子元素进行评估**正文**传入消息的节点。 如果此正文路径表达式返回多个节点，则只选择第一个节点作为 BizTalk 消息正文部分。 此属性是必需的如果**InboundBodyLocation**属性设置为**UseBodyPath**。<br /><br /> 默认值为空字符串。|  
|**InboundNodeEncoding**|Enum<br /><br /> -   **Base64** -Base64 编码。<br />-   **十六进制**-十六进制编码。<br />-   **字符串**编码文本的 utf-8。<br />-   **XML** -WCF 适配器使用由正文路径表达式中所选节点的外部 XML 创建 BizTalk 消息正文**InboundBodyPathExpression**。|指定的编码，WCF NetTcp 接收适配器使用要解码识别由正文路径表达式中指定的节点类型**InboundBodyPathExpression**。 此属性是必需的如果**InboundBodyLocation**属性设置为**UseBodyPath**。<br /><br /> 默认值： **XML**|  
|**OutboundBodyLocation**|Enum<br /><br /> -   **UseBodyElement** -BizTalk 消息正文部分用于创建的 SOAP 内容**正文**的传出的响应消息的元素。<br />-   **UseTemplate** -使用中提供的模板**OutboundXMLTemplate**属性来创建的内容 SOAP**正文**的传出的响应消息的元素。<br /><br /> 有关如何使用**OutboundBodyLocation**属性，请参阅[为 WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。|指定 SOAP 数据选择**正文**传出的 WCF 消息的元素。 此属性仅对请求响应接收位置有效。<br /><br /> 默认值： **UseBodyElement**|  
|**OutboundXMLTemplate**|字符串<br /><br /> 有关如何使用**OutboundXMLTemplate**属性，请参阅[为 WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。|指定的 SOAP 内容的 XML 格式模板**正文**的传出响应消息的元素。 此属性是必需的如果**OutboundBodyLocation**属性设置为**UseTemplate**。 此属性仅对请求响应接收位置有效。<br /><br /> 默认值为空字符串。|  
|**SuspendMessageOnFailure**|Boolean|指定是否将由于接收管道故障或路由故障而导致入站处理失败的请求消息挂起。<br /><br /> 默认值： **True**|  
|**IncludeExceptionDetailInFaults**|Boolean|指定是否将托管异常信息包括在返回给客户端以便进行调试的 SOAP 错误的详细信息中。<br /><br /> 默认值： **False**|  
  
## <a name="configure-a-wcf-nettcp-receive-location-with-the-biztalk-administration-console"></a>配置 WCF NetTcp 接收位置使用 BizTalk 管理控制台
  
 您可以在 BizTalk 管理控制台中设置 WCF-NetTcp 接收位置适配器变量。 如果未设置接收位置的属性，则使用 BizTalk 管理控制台中设置的默认接收处理程序值。  
  
> [!NOTE]
>  在执行以下过程之前，您必须已添加接收端口。 有关详细信息，请参阅[如何创建接收端口](../core/how-to-create-a-receive-port.md)。  
  
## <a name="configure-variables-for-a-wcf-nettcp-receive-location"></a>WCF NetTcp 接收位置的配置变量  
  
1.  在 BizTalk 管理控制台中，依次展开“BizTalk Server 2009 管理” 、“BizTalk 组” 和“应用程序” ，然后展开要在其中创建接收位置的应用程序。  
  
2.  在 BizTalk 管理控制台的左窗格中，单击“接收端口”  节点。 随后，在右窗格中右键单击与现有接收位置关联的接收端口或要与新接收位置关联的接收端口，然后单击“属性” 。  
  
3.  在**接收端口属性**对话框中，在左侧的窗格中，选择**接收位置**，然后在右窗格中，双击现有接收位置或单击**新建**创建一个新接收位置。  
  
4.  在**接收位置属性**对话框中，在**传输**旁边部分**类型**，选择**WCF NetTcp**从下拉列表列表，，然后单击**配置**。  
  
5.  在**Wcf-nettcp 传输属性**对话框中，在**常规**选项卡上，配置终结点地址和 WCF NetTcp 的服务标识接收位置。 有关详细信息**常规**选项卡中**Wcf-nettcp 传输属性**对话框中，请参阅**Wcf-nettcp 传输属性对话框中，接收、 常规**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  
  
6.  在**Wcf-nettcp 传输属性**对话框中，在**绑定**选项卡上配置的超时和事务的属性。 有关详细信息**绑定**选项卡中**Wcf-nettcp 传输属性**对话框中，请参阅**Wcf-nettcp 传输属性对话框中，接收，绑定**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
7.  在**Wcf-nettcp 传输属性**对话框中，在**安全**选项卡上，定义安全性功能 WCF NetTcp 接收位置。 有关详细信息**安全**选项卡中**Wcf-nettcp 传输属性**对话框中，请参阅**Wcf-nettcp 传输属性对话框中，接收、 安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
8.  在**Wcf-nettcp 传输属性**对话框中，在**消息**选项卡上，指定 SOAP 数据选择**正文**元素。 有关详细信息**消息**选项卡中**Wcf-nettcp 传输属性**对话框中，请参阅**Wcf-nettcp 传输属性对话框中，接收、 消息**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
##<a name="configure-a-wcf-nettcp-receive-location-programmatically"></a>配置 WCF NetTcp 以编程方式接收位置
  
 可使用以下格式设置属性：  
  
```  
<CustomProps>  
  <InboundBodyPathExpression vt="8" />  
  <InboundBodyLocation vt="8">UseBodyElement</InboundBodyLocation>  
  <UseSSO vt="11">0</UseSSO>  
  <MessageClientCredentialType vt="8">Windows</MessageClientCredentialType>  
  <SendTimeout vt="8">00:01:00</SendTimeout>  
  <OutboundXmlTemplate vt="8"><bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="xml"/></OutboundXmlTemplate>  
  <OpenTimeout vt="8">00:01:00</OpenTimeout>  
  <AlgorithmSuite vt="8">Basic256</AlgorithmSuite>  
  <SecurityMode vt="8">Message</SecurityMode>  
  <TransportClientCredentialType vt="8">Windows</TransportClientCredentialType>  
  <MaxReceivedMessageSize vt="3">2097152</MaxReceivedMessageSize>  
  <CloseTimeout vt="8">00:01:00</CloseTimeout>  
  <SuspendMessageOnFailure vt="11">0</SuspendMessageOnFailure>  
  <EnableTransaction vt="11">0</EnableTransaction>  
  <InboundNodeEncoding vt="8">Xml</InboundNodeEncoding>  
  <IncludeExceptionDetailInFaults vt="11">0</IncludeExceptionDetailInFaults>  
  <MaxConcurrentCalls vt="3">16</MaxConcurrentCalls>  
  <ServiceCertificate vt="8" />  
  <OutboundBodyLocation vt="8">UseBodyElement</OutboundBodyLocation>  
</CustomProps>  
  
```  
  
 以下代码段显示了如何创建 WCF-NetTcp 接收位置：  
  
```  
// Use BizTalk Explorer object model to create new WCF-NetTcp receive location   
string server = System.Environment.MachineName;  
string database = "BizTalkMgmtDb";  
string connectionString = string.Format("Server={0};Database={1};Integrated Security=true", server, database);  
string transportConfigData = @"<CustomProps>  
  <InboundBodyLocation vt=""8"">UseBodyElement</InboundBodyLocation>  
  <UseSSO vt=""11"">0</UseSSO>  
  <Identity vt=""8"">  
    <identity>  
    <userPrincipalName value=""username@contoso.com"" />  
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
// Find a receive handler for WCF-NetTcp   
int i = 0;  
for(i=0; i < explorer.ReceiveHandlers.Count; ++i)   
{  
    if("WCF-NetTcp" == explorer.ReceiveHandlers[i].TransportType.Name)  
        break;  
}  
recieveLocation.ReceiveHandler = explorer.ReceiveHandlers[i];  
recieveLocation.Address = "net.tcp://mycomputer/samplepath";  
recieveLocation.ReceivePipeline = explorer.Pipelines["Microsoft.BizTalk.DefaultPipelines.PassThruReceive"];  
recieveLocation.TransportType = explorer.ProtocolTypes["WCF-NetTcp"];  
recieveLocation.TransportTypeData = transportConfigData;  
// Save  
explorer.SaveChanges();   
```  
  
## <a name="see-also"></a>另请参阅  
 [为 WCF 发布服务元数据接收适配器](../core/publishing-service-metadata-for-the-wcf-receive-adapters.md)   
 [管理 BizTalk 主机和主机实例](../core/managing-biztalk-hosts-and-host-instances.md)   
 [如何更改服务帐户和密码](../core/how-to-change-service-accounts-and-passwords.md)   
 [将证书安装适用于这些 WCF 适配器](../core/installing-certificates-for-the-wcf-adapters.md)   
 [为 WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)   
 [负载平衡](http://go.microsoft.com/fwlink/?LinkId=81089)   
 [配置 WCF NetTcp 适配器](../core/configuring-the-wcf-nettcp-adapter.md)