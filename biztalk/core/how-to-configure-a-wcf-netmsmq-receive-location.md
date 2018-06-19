---
title: 如何配置 WCF NetMsmq 接收位置 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f82b323b-9870-42fb-9992-c23dca909b4d
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16491259826159f18791e35efb226dd159c12c27
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22250669"
---
# <a name="how-to-configure-a-wcf-netmsmq-receive-location"></a>如何配置 WCF-NetMsmq 接收位置
可以通过编程方式或使用 BizTalk 管理控制台来配置 WCF-NetMsmq 接收位置。  
  
## <a name="configuratin-properties"></a>配置属性
  
 使用 BizTalk 浏览器对象模型，您可以通过编程方式创建和配置接收位置。 BizTalk 资源管理器对象模型公开了**IReceiveLocation**接收具有的位置配置接口**TransportTypeData**读/写属性。 此属性以 XML 字符串的名称-值对形式接受 WCF-NetMsmq 接收位置配置属性包。 若要在 BizTalk 资源管理器对象模型中设置此属性，必须设置**InboundTransportLocation**属性**IReceiveLocation**接口。  
  
 **TransportTypeData**属性**IReceiveLocation**接口不需要设置。 如果未设置该属性，则 WCF-NetMsmq 适配器将使用 WCF-NetMsmq 接收位置配置的默认值，如下表所示。  
  
 下表列出了可在 WCF-NetMsmq 接收位置的 BizTalk 浏览器对象模型中设置的配置属性。  
  
|属性名称|类型|Description|  
|-------------------|----------|-----------------|  
|**标识**|XML Blob<br /><br /> 例如：<br /><br /> &lt;标识&gt;<br /><br /> &lt;userPrincipalName 值 ="username@contoso.com"/&gt;<br /><br /> &lt;/identity&gt;|指定此接收位置提供的服务的标识。 可以为指定的值**标识**属性而异的安全配置。 通过这些设置，客户端可对此接收位置进行验证。 在客户端与服务进行握手的过程中，Windows Communication Foundation (WCF) 基础结构将确保预期服务的标识与此元素的值保持一致。<br /><br /> 默认值为空字符串。|  
|**OpenTimeout**|**System.TimeSpan**|指定一个时间跨度值来表示为完成信道打开操作提供的时间间隔。<br /><br /> 默认值：00:01:00|  
|**SendTimeout**|**System.TimeSpan**|指定一个时间跨度值来表示为完成发送操作提供的时间间隔。<br /><br /> 默认值：00:01:00|  
|**CloseTimeout**|**System.TimeSpan**|指定一个时间跨度值来表示为完成信道关闭操作提供的时间间隔。<br /><br /> 默认值：00:01:00|  
|**MaxReceivedMessageSize**|Integer|指定网络上可接收的消息的最大大小（包括标头），以字节为单位。 消息的大小受为每条消息分配的内存量的限制。 你可以使用此属性来降低受拒绝服务 (DoS) 攻击的可能性。<br /><br /> 默认值：65536|  
|**EnableTransaction**|Boolean|指定消息队列类型：事务性或非事务性。 如果选择此属性，则每条消息仅发送一次，并且在发送失败时会通知发件人。 要将通过事务发送的消息发送端口，同时**持久**和**exactlyOnce**绑定元素的客户端必须设置为**True**。 如果清除此属性，则发送的消息不保证送达。 **注意：** 如果使用这一个事务性队列接收位置，必须选择此属性。 <br /><br /> 默认值： **False**|  
|**OrderedProcessing**|Boolean|指定是否按顺序处理消息。 当选中此属性时，此接收位置与拥有的 BizTalk 消息传递或业务流程发送端口结合使用时的有序的消息传递**按序送达**选项设置为`True`。 你可以选择此仅当**EnableTransaction**属性设置为**True**。<br /><br /> 有关详细信息**按序送达**选项，请参阅另请参阅中的相应主题。<br /><br /> 当此属性设置为**True**，WCF NetMsmq 接收位置通过进行单线程的适配器处理大消息时优化资源使用情况。<br /><br /> 默认值： **False**|  
|**MaxConcurrentCalls**|Integer|指定针对单个服务实例的并发调用的数目。 超出此限制的调用将在队列中排队。 此属性的范围是从 0 到**Int32.MaxValue**。<br /><br /> 默认值：200|  
|**SecurityMode**|Enum<br /><br /> -   **无**<br />-   **消息**<br />-   **传输**<br />-   **同时**<br /><br /> 有关成员名称的详细信息**SecurityMode**属性，请参阅**安全模式**中的属性**WCF NetMsmq 传输属性对话框中，接收，安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。|指定使用的安全类型。<br /><br /> 默认值：**传输**|  
|**MsmqAuthenticationMode**|Enum<br /><br /> -   **无**<br />-   **WindowsDomain**<br />-   **证书**<br /><br /> 有关成员名称的详细信息**MsmqAuthenticationMode**属性，请参阅**MSMQ 身份验证模式**中的属性**WCF NetMsmq 传输属性对话框中，接收安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。|指定如何通过 MSMQ 传输对消息进行验证。<br /><br /> 默认值： **WindowsDomain**|  
|**而 MsmqProtectionLevel**|Enum<br /><br /> -   **无**： 无保护。<br />-   **登录**： 对消息进行签名。<br />-   **EncryptAndSign**： 消息进行加密和签名。 若要使用此保护级别，必须启用**Active Directory 集成**为**MSMQ**。|指定消息在 MSMQ 传输一级的保护方式。 加密可以确保消息的完整性，而签名且加密既可确保消息的完整性又可确保不可否认性。<br /><br /> 默认值：**登录**|  
|**MsmqSecureHashAlgorithm**|Enum<br /><br /> -   **MD5**<br />-   **SHA1**<br />-   **SHA25**<br />-   **SHA512**|指定使用哈希算法计算消息摘要。 此属性不可用如果**而 MsmqProtectionLevel**属性设置为**无**。<br /><br /> 默认值： **SHA1**|  
|**MsmqEncryptionAlgorithm**|Enum<br /><br /> -   **RC4Stream**<br />-   **AES**|指定在消息队列管理器之间传输消息时，将在网络上使用的消息加密算法。 此属性才可用才**而 MsmqProtectionLevel**属性设置为**EncryptAndSign**。<br /><br /> 默认值： **RC4Stream**|  
|**MessageClientCredentialType**|Enum<br /><br /> -   **无**<br />-   **Windows**<br />-   **用户名**<br />-   **证书**<br /><br /> 有关成员名称的详细信息**MessageClientCredentialType**属性，请参阅**消息客户端凭据类型**中的属性**WCF NetMsmq 传输属性对话框框中，接收、 安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。|指定使用基于消息的安全性对客户端执行验证时所用的凭据类型。<br /><br /> 默认值： **Windows**|  
|**AlgorithmSuite**|Enum<br /><br /> 有关成员名称的详细信息**AlgorithmSuite**属性，请参阅**算法套件**中的属性**WCF NetMsmq 传输属性对话框中，接收，安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。|指定消息加密和密钥包装算法。 这些算法与“安全策略语言”(WS-SecurityPolicy) 规范中指定的算法一致。<br /><br /> 默认值： **Basic256**|  
|**ServiceCertificate**|字符串|为此接收位置指定 X.509 证书的指纹，客户端利用该指纹验证服务。 此属性使用的证书必须安装到**我**将存储在**当前用户**位置。 **注意：** 必须安装到的服务证书**当前用户**承载此接收位置接收处理程序的用户帐户的位置。 <br /><br /> 默认值为空字符串。|  
|**InboundBodyLocation**|Enum<br /><br /> -   **UseBodyElement** -使用 SOAP 的内容**正文**传入消息创建 BizTalk 消息正文部分的元素。 如果 **Body** 元素具有多个子元素，则只有第一个元素将成为 BizTalk 消息正文部分。<br />-   **UseEnvelope** -从整个 SOAP 创建 BizTalk 消息正文部分**信封**传入消息。<br />-   **UseBodyPath** -使用中的正文路径表达式**InboundBodyPathExpression**属性创建 BizTalk 消息正文部分。 针对传入消息的 SOAP **Body** 元素的直接子元素计算正文路径表达式。 此属性仅对要求-响应端口有效。<br /><br /> 有关如何使用**InboundBodyLocation**属性，请参阅[为 WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。|指定 SOAP 数据选择**正文**传入 WCF 消息的元素。<br /><br /> 默认值： **UseBodyElement**|  
|**InboundBodyPathExpression**|字符串<br /><br /> 有关如何使用**InboundBodyPathExpression**属性，请参阅[WCF 适配器属性架构和属性](../core/wcf-adapters-property-schema-and-properties.md)。|指定正文路径表达式以标识传入消息中用于创建 BizTalk 消息正文部分的特定部分。 此正文路径表达式针对 SOAP 的即时子元素进行评估**正文**传入消息的节点。 如果此正文路径表达式返回多个节点，则只选择第一个节点作为 BizTalk 消息正文部分。 此属性是必需的如果**InboundBodyLocation**属性设置为**UseBodyPath**。<br /><br /> 默认值为空字符串。|  
|**InboundNodeEncoding**|Enum<br /><br /> -   **Base64** -Base64 编码。<br />-   **十六进制**-十六进制编码。<br />-   **字符串**编码文本的 utf-8。<br />-   **XML** -WCF 适配器使用由正文路径表达式中所选节点的外部 XML 创建 BizTalk 消息正文**InboundBodyPathExpression**。|指定的编码，WCF NetMsmq 接收适配器使用要解码识别由正文路径表达式中指定的节点类型**InboundBodyPathExpression**。 此属性是必需的如果**InboundBodyLocation**属性设置为**UseBodyPath**。<br /><br /> 默认值： **XML**|  
|**DisableLocationOnFailure**|Boolean|指定是否禁用由于接收管道故障或路由故障而导致入站处理失败的接收位置。<br /><br /> 默认值： **False**|  
|**SuspendMessageOnFailure**|Boolean|指定是否将由于接收管道故障或路由故障而导致入站处理失败的请求消息挂起。<br /><br /> 默认值： **True**|  
|**IncludeExceptionDetailInFaults**|Boolean|指定是否将托管异常信息包括在返回给客户端以便进行调试的 SOAP 错误的详细信息中。<br /><br /> 默认值： **False**|  
  
## <a name="configure-a-wcf-netmsmq-receive-location-with-the-biztalk-administration-console"></a>配置 WCF NetMsmq 接收位置使用 BizTalk 管理控制台
  
 您可以在 BizTalk 管理控制台中设置 WCF-NetMsmq 接收位置适配器变量。 如果未设置接收位置的属性，则使用 BizTalk 管理控制台中设置的默认接收处理程序值。  
  
> [!NOTE]
>  在执行以下过程之前，您必须已添加接收端口。 有关详细信息，请参阅[如何创建接收端口](../core/how-to-create-a-receive-port.md)。  
  
> [!NOTE]
>  WCF 客户端和 WCF-NetMsmq 接收位置的绑定配置必须相符。 如果不相符，WCF-NetMsmq 接收位置会丢失传入的消息。  
  
## <a name="configure-variables-for-a-wcf-netmsmq-receive-location"></a>WCF NetMsmq 接收位置的配置变量  
  
1.  在 BizTalk 管理控制台中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，展开**BizTalk 组**，展开**应用程序**，然后展开应用程序你想要创建中的接收位置。  
  
2.  在 BizTalk 管理控制台的左窗格中，单击“接收端口”  节点。 随后，在右窗格中右键单击与现有接收位置关联的接收端口或要与新接收位置关联的接收端口，然后单击“属性” 。  
  
3.  在**接收端口属性**对话框中，在左侧的窗格中，选择**接收位置**，然后在右窗格中，双击现有接收位置或单击**新建**创建一个新接收位置。  
  
4.  在**接收位置属性**对话框中，在**传输**旁边部分**类型**，选择**WCF NetMsmq**从下拉列表，然后单击**配置**。  
  
5.  在**WCF NetMsmq 传输属性**对话框中，在**常规**选项卡上，配置终结点地址和 WCF NetMsmq 的服务标识接收位置。 有关详细信息**常规**选项卡中**WCF NetMsmq 传输属性**对话框中，请参阅**WCF NetMsmq 传输属性对话框中，接收、 常规**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  
  
6.  在**WCF NetMsmq 传输属性**对话框中，在**绑定**选项卡上配置的超时和事务的属性。 有关详细信息**绑定**选项卡中**WCF NetMsmq 传输属性**对话框中，请参阅**WCF NetMsmq 传输属性对话框中，接收，绑定**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  
  
7.  在**WCF NetMsmq 传输属性**对话框中，在**安全**选项卡上，定义安全性功能 WCF NetMsmq 接收位置。 有关详细信息**安全**选项卡中**WCF NetMsmq 传输属性**对话框中，请参阅**WCF NetMsmq 传输属性对话框中，接收、 安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  
  
8.  在**WCF NetMsmq 传输属性**对话框中，在**消息**选项卡上，指定 SOAP 数据选择**正文**元素。 有关详细信息**消息**选项卡中**WCF NetMsmq 传输属性**对话框中，请参阅**WCF NetMsmq 传输属性对话框中，接收、 消息**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。 
  
## <a name="configure-a-wcf-netmsmq-receive-location-programmatically"></a>配置 WCF NetMsmq 以编程方式接收位置
  
 可使用以下格式设置属性：  
  
```  
<CustomProps>  
  <ServiceCertificate vt="8" />  
  <InboundBodyLocation vt="8">UseBodyElement</InboundBodyLocation>  
  <InboundBodyPathExpression vt="8" />  
  <MessageClientCredentialType vt="8">Windows</MessageClientCredentialType>  
  <SendTimeout vt="8">00:01:00</SendTimeout>  
  <IncludeExceptionDetailInFaults vt="11">0</IncludeExceptionDetailInFaults>  
  <OpenTimeout vt="8">00:01:00</OpenTimeout>  
  <AlgorithmSuite vt="8">Basic256</AlgorithmSuite>  
  <MaxConcurrentCalls vt="3">16</MaxConcurrentCalls>  
  <SecurityMode vt="8">Transport</SecurityMode>  
  <OrderedProcessing vt="11">0</OrderedProcessing>  
  <CloseTimeout vt="8">00:01:00</CloseTimeout>  
  <MsmqEncryptionAlgorithm vt="8">RC4Stream</MsmqEncryptionAlgorithm>  
  <MaxReceivedMessageSize vt="3">2097152</MaxReceivedMessageSize>  
  <MsmqProtectionLevel vt="8">Sign</MsmqProtectionLevel>  
  <DisableLocationOnFailure vt="11">0</DisableLocationOnFailure>  
  <MsmqSecureHashAlgorithm vt="8">Sha1</MsmqSecureHashAlgorithm>  
  <SuspendMessageOnFailure vt="11">-1</SuspendMessageOnFailure>  
  <EnableTransaction vt="11">-1</EnableTransaction>  
  <InboundNodeEncoding vt="8">Xml</InboundNodeEncoding>  
  <MsmqAuthenticationMode vt="8">WindowsDomain</MsmqAuthenticationMode>  
</CustomProps>  
  
```  
  
 以下代码段显示了如何创建 WCF-NetMsmq 接收位置：  
  
```  
// Use BizTalk Explorer object model to create new WCF-NetMsmq receive location   
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
// Find a receive handler for WCF-NetMsmq   
int i = 0;  
for(i=0; i < explorer.ReceiveHandlers.Count; ++i)   
{  
    if("WCF-NetMsmq" == explorer.ReceiveHandlers[i].TransportType.Name)  
        break;  
}  
recieveLocation.ReceiveHandler = explorer.ReceiveHandlers[i];  
recieveLocation.Address = "net.msmq://mycomputer/private/sampleQueue";  
recieveLocation.ReceivePipeline = explorer.Pipelines["Microsoft.BizTalk.DefaultPipelines.PassThruReceive"];  
recieveLocation.TransportType = explorer.ProtocolTypes["WCF-NetMsmq"];  
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
 [配置 WCF NetMsmq 适配器](../core/configuring-the-wcf-netmsmq-adapter.md)   
 [有序的消息传送](../core/ordered-delivery-of-messages.md)   
 [发送和检索在事务中的消息](http://go.microsoft.com/fwlink/?LinkID=75752)   
 [消息队列和 Active Directory](http://go.microsoft.com/fwlink/?LinkID=75769)   
 [公用和专用队列](http://go.microsoft.com/fwlink/?LinkId=196673)