---
title: 如何配置 WCF NetMsmq 发送端口 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 13f55e53-12af-473b-b73f-1c98edadfc28
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48ad9e8f7ce806e0570877702fbccb432ca2946a
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
ms.locfileid: "25975243"
---
# <a name="how-to-configure-a-wcf-netmsmq-send-port"></a>如何配置 WCF NetMsmq 发送端口
可以通过编程方式或使用 BizTalk Server 管理控制台来配置 WCF-NetMsmq 发送端口。  
  
## <a name="configuration-properties"></a>配置属性
  
 BizTalk 资源管理器对象模型公开了用于发送端口名为的特定于适配器的接口 **ITransportInfo** 具有 **TransportTypeData** 读/写属性。 此属性接受 XML 字符串的名称-值对形式的 WCF-NetMsmq 发送端口配置属性包。  
  
 **TransportTypeData** 属性 **ITransportInfo** 界面不是必需。 如果未设置该属性，则适配器将使用 WCF-NetMsmq 发送端口配置的默认值，如下表所示。  
  
 下表列出了可在 BizTalk 浏览器对象模型中为 WCF-NetMsmq 发送端口设置的配置属性。  
  
|属性名称|型別|Description|  
|-------------------|----------|-----------------|  
|**标识**|XML Blob<br /><br /> 示例︰<br /><br /> &lt;标识&gt;<br /><br /> &lt;userPrincipalName value="username@contoso.com" /&gt;<br /><br /> &lt;/identity&gt;|指定此发送端口预期的服务标识。 这些设置支持此发送端口对服务进行验证。 在客户端与服务进行握手的过程中，Windows Communication Foundation (WCF) 基础结构将确保预期服务的标识与此元素的值保持一致。<br /><br /> 默认值为空字符串。|  
|**StaticAction**|字符串|指定 **SOAPAction** 传出消息的标头字段。 此外可以通过消息上下文属性设置此属性 **WCF。操作** 在管道或业务流程。 你可以通过两种方式指定此值︰ 单个操作格式和操作映射格式。 如果将此属性设置中的单个操作格式-例如， http://contoso.com/Svc/Op1- **SOAPAction**标头为传出消息始终设置为此属性中指定的值。<br /><br /> 如果在操作映射格式，传出中设置此属性 **SOAPAction** 标头由 **BTS。操作** 上下文属性。 例如，如果此属性设置为以下 XML 格式和**BTS。操作**属性设置为 Op1，WCF 发送适配器使用http://contoso.com/Svc/Op1为传出**SOAPAction**标头。<br /><br /> \<BtsActionMapping\><br /><br /> \<Operation Name="Op1" Action="http://contoso.com/Svc/Op1" /\><br /><br /> \<Operation Name="Op2" Action="http://contoso.com/Svc/Op2" /\><br /><br /> \</BtsActionMapping\><br /><br /> 如果传出消息来自的业务流程端口时，动态设置业务流程实例 **BTS。操作** 与操作名称的端口的属性。 如果使用基于内容的路由路由传出消息，则可以设置 **BTS。操作** 管道组件中的属性。<br /><br /> 默认值为空字符串。|  
|**OpenTimeout**|**System.TimeSpan**|指定一个时间跨度值来表示为完成信道打开操作提供的时间间隔。<br /><br /> 默认值：00:01:00|  
|**SendTimeout**|**System.TimeSpan**|指定一个时间跨度值来表示为完成发送操作提供的时间间隔。 如果使用要求-响应发送端口，则此值指定完成整个交互的时间跨度（即使服务返回一条大消息）。<br /><br /> 默认值：00:01:00|  
|**CloseTimeout**|**System.TimeSpan**|指定一个时间跨度值来表示为完成信道关闭操作提供的时间间隔。<br /><br /> 默认值：00:01:00|  
|**EnableTransactional**|Boolean|指定的一种目标服务的消息队列︰ 事务性或非事务性。 如果此属性设置为 **True**, 、 处理此发送端口的每个消息只传递一次，并且发件人会传递失败的通知。 要将通过事务发送的消息发送端口，同时 **持久** 和 **exactlyOnce** 绑定的服务元素必须设置为 **True**。 如果此属性设置为 **False**, ，而无需传递保证传输消息。<br /><br /> 默认值︰ **True**|  
|**DeadLetterQueue**|Enum<br /><br /> -   **无**-没有死信队列是使用。<br />-   **系统** -使用系统级死信队列。<br />-   **自定义** -使用自定义死信队列。|指定死信队列，未能传输到应用程序的消息将传输到死信队列中。 有关传递到死信队列的消息的详细信息，请参阅**WCF NetMsmq 传输属性对话框中，发送，绑定**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。<br/><br/> **请注意**： 自定义死信队列支持仅在消息队列 (MSMQ) 4.0 中，与 Windows Vista 一起发布。 <br /><br /> 默认值︰ **系统**|  
|**CustomDeadLetterQueue**|字符串|指定完全限定的 URI 与 **net.msmq** 方案的每个应用程序死信队列，消息已过期或者传输或传递失败的存放位置。 例如 net.msmq://localhost/deadLetterQueueName。 死信队列是发送应用程序的队列管理器上的一种队列，用于未能送达的到期的消息。 此属性是必需的如果 **DeadLetterQueue** 属性设置为 **自定义**。<br /><br /> 默认值为空字符串。|  
|**TimeToLive**|**System.TimeSpan**|指定一个时间范围，在此范围内消息有效，一旦超出此范围，消息将到期并被置于死信队列。 设置此属性是为了确保时间敏感消息在被此发送端口处理前不会过时。 队列中在指定的时间间隔内未由此发送端口使用的消息将被认为到期。 到期的消息将发送到称为死信队列的特殊队列。 死信队列的位置设置 **DeadLetterQueue** 属性。<br /><br /> 默认值︰ 1.00:00:00|  
|**UseSourceJournal**|Boolean|指定是否应将此发送端口所处理的消息副本存储到源日记队列中。<br /><br /> 默认值︰ **False**|  
|**SecurityMode**|Enum<br /><br /> -   **无**<br />-   **消息**<br />-   **传输**<br />-   **同时**<br /><br /> 有关成员名称的详细信息**SecurityMode**属性，请参阅**安全模式**中的属性**WCF NetMsmq 传输属性对话框中，发送，安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。|指定使用的安全性類型。<br /><br /> 默认值︰ **传输**|  
|**MsmqAuthenticationMode**|Enum<br /><br /> -   **无**<br />-   **WindowsDomain**<br />-   **证书**<br /><br /> 有关成员名称的详细信息**MsmqAuthenticationMode**属性，请参阅**MSMQ 身份验证模式**中的属性**WCF NetMsmq 传输属性对话框中，发送，安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。|指定如何通过 MSMQ 传输对消息进行验证。<br /><br /> 默认值︰ **WindowsDomain**|  
|**而 MsmqProtectionLevel**|Enum<br /><br /> -   **无**： 无保护。<br />-   **登录**︰ 对消息进行签名。<br />-   **EncryptAndSign**︰ 消息进行加密和签名。 若要使用此保护级别，必须启用 **Active Directory 集成** 为 **MSMQ**。|指定消息在 MSMQ 传输一级的保护方式。<br /><br /> 默认值︰ **登录**|  
|**MsmqSecureHashAlgorithm**|Enum<br /><br /> -   **MD5**<br />-   **SHA1**<br />-   **SHA25**<br />-   **SHA512**|指定使用哈希算法计算消息摘要。 此属性不可用如果 **而 MsmqProtectionLevel** 属性设置为 **无**。<br /><br /> 默认值︰ **SHA1**|  
|**MsmqEncryptionAlgorithm**|Enum<br /><br /> -   **RC4Stream**<br />-   **AES**|指定在消息队列管理器之间传输消息时，将在网络上使用的消息加密算法。 此属性才可用才 **而 MsmqProtectionLevel** 属性设置为 **EncryptAndSign**。<br /><br /> 默认值︰ **RC4Stream**|  
|**MessageClientCredentialType**|Enum<br /><br /> -   **无**<br />-   **Windows**<br />-   **用户名**<br />-   **证书**<br /><br /> 有关成员名称的详细信息**MessageClientCredentialType**属性，请参阅**消息客户端凭据类型**中的属性**WCF NetMsmq 传输属性对话框框中，发送，安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。|指定使用基于消息的安全性对客户端执行验证时所用的凭据类型。<br /><br /> 默认值︰ **Windows**|  
|**AlgorithmSuite**|Enum<br /><br /> 有关成员名称的详细信息**AlgorithmSuite**属性，请参阅**算法套件**中的属性**WCF NetMsmq 传输属性对话框中，发送，安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。|指定訊息加密和 Key Wrap 演算法。 这些算法与“安全策略语言”(WS-SecurityPolicy) 规范中指定的算法一致。<br /><br /> 默认值︰ **Basic256**|  
|**ClientCertificate**|字符串|指定用于向服务验证此发送端口的 X.509 证书的指纹。 此属性是必需的如果 **ClientCredentialsType** 属性设置为 **证书**。 此属性使用的证书必须安装到 **我** 将存储在 **当前用户** 位置。<br /><br /> 默认值为空字符串。|  
|**ServiceCertificate**|字符串|指定用于验证服务（此发送端口要将消息发送到的服务）的 X.509 证书的指纹。 此属性使用的证书必须安装到 **其他人** 将存储在 **本地计算机** 位置。<br /><br /> 默认值为空字符串。|  
|**AffiliateApplicationName**|字符串|指定用于企业单一登录 (SSO) 的关联应用程序。<br /><br /> 默认值为空字符串。|  
|**UseSSO**|Boolean|指定是否使用单一登录检索客户端凭据，以便在目标服务器上进行验证。<br /><br /> 默认值︰ **False**|  
|**用户名**|字符串|指定要用于目标服务器的身份验证的用户名称时 **UseSSO** 属性设置为 **False**。 不必采用“域\用户”格式设置此属性。<br /><br /> 默认值为空字符串。|  
|**密码**|字符串|指定要用于目标服务器的身份验证的密码时 **UseSSO** 属性设置为 **False**。<br /><br /> 默认值为空字符串。|  
|**OutboundBodyLocation**|Enum<br /><br /> -   **UseBodyElement** -BizTalk 消息正文部分用于创建的 SOAP 内容**正文**传出消息的元素。<br />-   **UseTemplate** -使用中提供的模板 **OutboundXMLTemplate** 属性来创建的内容 SOAP **正文** 传出消息的元素。<br /><br /> 有关如何使用**OutboundBodyLocation**属性，请参阅[为 WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。|指定 SOAP 数据选择 **正文** 传出的 WCF 消息的元素。<br /><br /> 默认值︰ **UseBodyElement**|  
|**OutboundXMLTemplate**|字符串<br /><br /> 有关如何使用**OutboundXMLTemplate**属性，请参阅[为 WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。|指定的 SOAP 内容的 XML 格式模板 **正文** 的传出消息的元素。 此属性是必需的如果 **OutboundBodyLocation** 属性设置为 **UseTemplate**。<br /><br /> 預設為空字串。|  
  
## <a name="configure-a-wcf-netmsmq-send-port-with-the-biztalk-administration-console"></a>使用 BizTalk 管理控制台中配置 WCF NetMsmq 发送端口
  
 您可以在 BizTalk 管理控制台中设置 WCF-NetMsmq 发送端口适配器变量。 如果没有为发送端口设置属性，将使用 WCF-NetMsmq 发送端口配置的默认值，如前表所示。  
  
## <a name="configure-variables-for-a-wcf-netmsmq-send-port"></a>配置变量 WCF NetMsmq 发送端口  
  
1.  在 [BizTalk 管理主控台] 中建立新的傳送埠，或按兩下現有的傳送埠進行修改。 有关详细信息，请参阅[如何创建发送端口](../core/how-to-create-a-send-port2.md)。 配置所有发送端口选项并指定**WCF NetMsmq**为**类型**选项**传输**部分**常规**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  
  
2.  上 **常规** 选项卡上，在 **传输** 部分中，单击 **配置** 按钮旁边 **类型**。  
  
3.  在 **WCF NetMsmq 传输属性** 对话框中，在 **常规** 选项卡上配置的终结点地址，服务标识，与 **SOAPAction** WCF NetMsmq 的标头发送端口。 有关详细信息**常规**选项卡中**WCF NetMsmq 传输属性**对话框中，请参阅**WCF NetMsmq 传输属性对话框中，发送，常规**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  
  
4.  在 **WCF NetMsmq 传输属性** 对话框中，在 **绑定** 选项卡上，配置的超时和事务的属性和队列设置。 有关详细信息**绑定**选项卡中**WCF NetMsmq 传输属性**对话框中，请参阅**WCF NetMsmq 传输属性对话框中，发送，绑定**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  
  
5.  在 **WCF NetMsmq 传输属性** 对话框中，在 **安全** 选项卡上，定义 WCF NetMsmq 发送端口的安全功能。 有关详细信息**安全**选项卡中**WCF NetMsmq 传输属性**对话框中，请参阅**WCF NetMsmq 传输属性对话框中，发送，安全**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  
  
6.  在 **WCF NetMsmq 传输属性** 对话框中，在 **消息** 选项卡上，指定 SOAP 数据选择 **正文** 元素。 有关详细信息**消息**选项卡中**WCF NetMsmq 传输属性**对话框中，请参阅**WCF NetMsmq 传输属性对话框中，发送消息**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  
  
## <a name="configure-a-wcf-netmsmq-send-port-programmatically"></a>以编程方式配置 WCF NetMsmq 发送端口
  
 可使用以下格式设置属性：  
  
```  
<CustomProps>  
  <ServiceCertificate vt="8" />  
  <UseSSO vt="11">0</UseSSO>  
  <CloseTimeout vt="8">00:01:00</CloseTimeout>  
  <MessageClientCredentialType vt="8">Windows</MessageClientCredentialType>  
  <SendTimeout vt="8">00:01:00</SendTimeout>  
  <OutboundXmlTemplate vt="8"><bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="xml"/></OutboundXmlTemplate>  
  <MsmqProtectionLevel vt="8">Sign</MsmqProtectionLevel>  
  <OpenTimeout vt="8">00:01:00</OpenTimeout>  
  <UseSourceJournal vt="11">0</UseSourceJournal>  
  <AlgorithmSuite vt="8">Basic256</AlgorithmSuite>  
  <SecurityMode vt="8">Transport</SecurityMode>  
  <CustomDeadLetterQueue vt="8" />  
  <ClientCertificate vt="8" />  
  <MsmqEncryptionAlgorithm vt="8">RC4Stream</MsmqEncryptionAlgorithm>  
  <StaticAction vt="8">http://www.northwindtraders.com/Service/Operation</StaticAction>  
  <MsmqSecureHashAlgorithm vt="8">Sha1</MsmqSecureHashAlgorithm>  
  <EnableTransaction vt="11">-1</EnableTransaction>  
  <TimeToLive vt="8">1.00:00:00</TimeToLive>  
  <MsmqAuthenticationMode vt="8">WindowsDomain</MsmqAuthenticationMode>  
  <DeadLetterQueue vt="8">System</DeadLetterQueue>  
  <OutboundBodyLocation vt="8">UseBodyElement</OutboundBodyLocation>  
</CustomProps>  
  
```  
  
 下面的代码段说明了如何创建 WCF-NetMsmq 发送端口：  
  
```  
// Use BizTalk Explorer object model to create new WCF-NetMsmq send port.  
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
sendPort.PrimaryTransport.TransportType = explorer.ProtocolTypes["WCF-NetMsmq"];  
sendPort.PrimaryTransport.Address = "net.msmq://mycomputer/private/samplequeue";  
sendPort.PrimaryTransport.TransportTypeData = transportConfigData; // propertyData; // need to change  
sendPort.SendPipeline = explorer.Pipelines["Microsoft.BizTalk.DefaultPipelines.PassThruTransmit"];  
// Save  
explorer.SaveChanges();  
```  
  
## <a name="see-also"></a>另请参阅  
 [WCF 适配器属性架构和属性](../core/wcf-adapters-property-schema-and-properties.md)   
 [将证书安装适用于这些 WCF 适配器](../core/installing-certificates-for-the-wcf-adapters.md)   
 [为 WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)   
 [配置 WCF NetMsmq 适配器](../core/configuring-the-wcf-netmsmq-adapter.md)   
 [使用 WCF 适配器上下文属性配置动态发送端口](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)