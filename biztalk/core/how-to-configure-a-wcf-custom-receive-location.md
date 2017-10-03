---
title: "如何配置 WCF 自定义接收位置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e2092cd4-6612-4ac3-81f3-dd25438837ae
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4fd1d872f0e90b57f760f6ca3028fca8992255ea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-a-wcf-custom-receive-location"></a>如何配置 WCF-Custom 接收位置
可以通过编程方式或使用 BizTalk 管理控制台来配置 WCF-Custom 接收位置。  
  
## <a name="configuration-properties"></a>配置属性
  
 使用 BizTalk 浏览器对象模型，您可以通过编程方式创建和配置接收位置。 BizTalk 资源管理器对象模型公开了**IReceiveLocation**接收具有的位置配置接口**TransportTypeData**读/写属性。 此属性以 XML 字符串的名称-值对形式接受 WCF-Custom 接收位置配置属性包。 若要在 BizTalk 资源管理器对象模型中设置此属性，必须设置**InboundTransportLocation**属性**IReceiveLocation**接口。  
  
 **TransportTypeData**属性**IReceiveLocation**接口不需要设置。 如果未设置该属性，则 WCF-Custom 适配器将使用 WCF-Custom 接收位置配置的默认值，如下表所示。  
  
 下表列出了可在 BizTalk 浏览器对象模型中为 WCF-Custom 接收位置设置的配置属性：  
  
|属性名称|类型|Description|  
|-------------------|----------|-----------------|  
|**标识**|XML Blob<br /><br /> 例如：<br /><br /> &lt;标识&gt;<br /><br /> &lt;userPrincipalName 值 ="username@contoso.com"/&gt;<br /><br /> &lt;/identity&gt;|指定此接收位置提供的服务的标识。 可以为指定的值**标识**属性而异的安全配置。 通过这些设置，客户端可对此接收位置进行验证。 在客户端与服务进行握手的过程中，Windows Communication Foundation (WCF) 基础结构将确保预期服务的标识与此元素的值保持一致。<br /><br /> 默认值为空字符串。|  
|**BindingType**|Enum<br /><br /> -   **basicHttpBinding**<br />-   **customBinding**<br />-   **mexHttpBinding**<br />-   **mexHttpsBinding**<br />-   **mexNamedPipeBinding**<br />-   **mexTcpBinding**<br />-   **netMsmqBinding**<br />-   **netNamedPipeBinding**<br />-   **netPeerTcpBinding**<br />-   **netTcpBinding**<br />-   **wsDualHttpBinding**<br />-   **wsFederationHttpBinding**<br />-   **wsHttpBinding**|指定此接收位置使用的终结点所采用的绑定类型。 **注意：**如果你使用的自定义绑定， **BindingType**属性可以配置使用自定义绑定。 有关如何使用自定义绑定的详细信息，请参阅[如何启用与 WCF 适配器 WCF 扩展点](../core/how-to-enable-the-wcf-extensibility-points-with-the-wcf-adapters.md)。 <br /><br /> 默认值为空字符串。|  
|**BindingConfiguration**|XML Blob<br /><br /> 例如：<br /><br /> &lt;绑定名称 ="netNamedPipeBinding"&gt;&lt;安全模式 ="None"/&gt;&lt;绑定&gt;|指定使用的 XML 字符串**\<绑定 >**元素来配置不同类型的预定义的绑定所提供的 Windows Communication Foundation (WCF)。 有关系统提供的绑定和自定义绑定的详细信息，请参阅“另请参见”部分中的相应主题。 **注意：** BizTalk Server 不支持你可以使用配置的绑定扩展元素的所有类型**BindingConfiguration**属性。 <br /><br /> 默认值为空字符串。|  
|**ServiceBehaviorConfiguration**|XML Blob<br /><br /> 例如：<br /><br /> &lt;行为名称 ="SampleServiceBehavior"&gt;&lt;serviceMetadata httpGetEnabled ="true"httpGetUrl ="http://mycomputer:9995/SampleMex"/&gt;&lt;serviceCredentials /&gt; &lt;/behavior&gt;|指定使用的 XML 字符串**\<行为 >**元素 **\<serviceBehaviors >**元素来配置 WCF 服务的行为设置。 有关详细信息 **\<serviceBehaviors >**元素，请参阅另请参阅中的相应主题。<br /><br /> 默认值为空字符串。|  
|**EndpointBehaviorConfiguration**|XML Blob<br /><br /> 例如：<br /><br /> &lt;行为名称 ="sampleBehavior"&gt;&lt;callbackTimeouts /&gt;&lt;/behavior&gt;|指定使用的 XML 字符串**\<行为 >**元素 **\<endpointBehaviors >**元素来配置 WCF 终结点的行为设置。 有关详细信息 **\<endpointBehaviors >**元素，请参阅另请参阅中的相应主题。 **注意：** BizTalk Server 不支持你可以使用配置的行为扩展元素的所有类型**EndpointBehaviorConfiguration**属性。 <br /><br /> 默认值为空字符串。|  
|**CredentialType**|Enum<br /><br /> -   **无**： 不要的使用任何凭据时此接收位置发送请求消息来轮询外部服务，或此接收位置不需要轮询任何外部服务。<br />-   **IssueTicket**： 使用企业单一登录 (SSO) 来检索要颁发的 SSO 票证的客户端凭据。 该选项要求所使用的安全模式允许接收位置模拟用户帐户来颁发 SSO 票证。<br />-   **UserAccount**： 使用中指定的凭据**用户名**和**密码**属性时此接收位置发送请求消息来轮询外部服务。<br />-   **执行的 getcredentials 操作**： 使用 SSO 关联应用程序中指定**AffiliateApplicationName**属性时此接收位置发送请求消息来轮询外部服务。|指定在轮询外部服务时此接收位置使用的凭据类型<br /><br /> 默认值：**无**|  
|**UserName**|字符串|指定在轮询外部服务以检索响应消息时此接收位置使用的用户名。 当此属性是必需**CredentialType**属性设置为**UserAccount**。<br /><br /> 默认值为空字符串。|  
|**密码**|字符串|指定在轮询外部服务以检索响应消息时此接收位置使用的密码。 当此属性是必需**CredentialType**属性设置为**UserAccount**。<br /><br /> 默认值为空字符串。|  
|**AffiliateApplicationName**|字符串|指定此接收位置发送要求消息以轮询外部服务时返回要使用的外部凭据的 SSO 关联应用程序。 在运行接收位置所使用的 Windows 帐户和用于外部服务的帐户之间，指定的 SSO 关联应用程序必须具有一个映射。 当此属性是必需**CredentialType**属性设置为**执行的 getcredentials 操作**。<br /><br /> 默认值为空字符串。|  
|**OrderedProcessing**|Boolean|指定在处理消息时是否保留消息顺序（以便与 NetMsmq 绑定一起使用）。<br /><br /> 默认值： **False**|  
|**InboundBodyLocation**|Enum<br /><br /> -   **UseBodyElement** -使用 SOAP 的内容**正文**传入消息创建 BizTalk 消息正文部分的元素。 如果 **Body** 元素具有多个子元素，则只有第一个元素将成为 BizTalk 消息正文部分。<br />-   **UseEnvelope** -从整个 SOAP 创建 BizTalk 消息正文部分**信封**传入消息。<br />-   **UseBodyPath** -使用中的正文路径表达式**InboundBodyPathExpression**属性创建 BizTalk 消息正文部分。 针对传入消息的 SOAP **Body** 元素的直接子元素计算正文路径表达式。 此属性仅对要求-响应端口有效。<br /><br /> 有关如何使用**InboundBodyLocation**属性，请参阅[为 WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。|指定 SOAP 数据选择**正文**传入 WCF 消息的元素。<br /><br /> 默认值： **UseBodyElement**|  
|**InboundBodyPathExpression**|字符串<br /><br /> 有关如何使用**InboundBodyPathExpression**属性，请参阅[WCF 适配器属性架构和属性](../core/wcf-adapters-property-schema-and-properties.md)。|指定正文路径表达式以标识传入消息中用于创建 BizTalk 消息正文部分的特定部分。 此正文路径表达式针对 SOAP 的即时子元素进行评估**正文**传入消息的节点。 如果此正文路径表达式返回多个节点，则只选择第一个节点作为 BizTalk 消息正文部分。 此属性是必需的如果**InboundBodyLocation**属性设置为**UseBodyPath**。<br /><br /> 默认值为空字符串。|  
|**InboundNodeEncoding**|Enum<br /><br /> -   **Base64** -Base64 编码。<br />-   **十六进制**-十六进制编码。<br />-   **字符串**编码文本的 utf-8。<br />-   **XML** -WCF 适配器使用由正文路径表达式中所选节点的外部 XML 创建 BizTalk 消息正文**InboundBodyPathExpression**。|指定的编码，WCF 自定义接收适配器使用要解码识别由正文路径表达式中指定的节点类型**InboundBodyPathExpression**。 此属性是必需的如果**InboundBodyLocation**属性设置为**UseBodyPath**。<br /><br /> 默认值： **XML**|  
|**OutboundBodyLocation**|Enum<br /><br /> -   **UseBodyElement** -BizTalk 消息正文部分用于创建的 SOAP 内容**正文**的传出的响应消息的元素。<br />-   **UseTemplate** -使用中提供的模板**OutboundXMLTemplate**属性来创建的内容 SOAP**正文**的传出的响应消息的元素。<br /><br /> 有关如何使用**OutboundBodyLocation**属性，请参阅[为 WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。|指定 SOAP 数据选择**正文**传出的 WCF 消息的元素。 此属性仅对请求响应接收位置有效。<br /><br /> 默认值： **UseBodyElement**|  
|**OutboundXMLTemplate**|字符串<br /><br /> 有关如何使用**OutboundXMLTemplate**属性，请参阅[为 WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。|指定的 SOAP 内容的 XML 格式模板**正文**的传出响应消息的元素。 此属性是必需的如果**OutboundBodyLocation**属性设置为**UseTemplate**。 此属性仅对请求响应接收位置有效。<br /><br /> 默认值为空字符串。|  
|**DisableLocationOnFailure**|Boolean|指定是否禁用由于接收管道故障或路由故障而导致入站处理失败的接收位置。<br /><br /> 默认值： **False**|  
|**SuspendMessageOnFailure**|Boolean|指定是否将由于接收管道故障或路由故障而导致入站处理失败的请求消息挂起。<br /><br /> 默认值： **True**|  
|**IncludeExceptionDetailInFaults**|Boolean|指定是否将托管异常信息包括在返回给客户端以便进行调试的 SOAP 错误的详细信息中。<br /><br /> 默认值： **False**|  
|**ReferencedBindings**|XML Blob<br /><br /> 例如：<br /><br /> \<**BindingConfiguration** vt ="8"><br /><br /> &lt;wsFederationHttpBinding&gt;<br /><br /> &lt;绑定名称 ="sampleBinding"&gt;<br /><br /> &lt;安全模式 ="Message"&gt;<br /><br /> &lt;消息 issuedKeyType ="AsymmetricKey"&gt;<br /><br /> &lt;颁发者地址 ="http://www.contoso.com/samplests"绑定 ="wsFederationHttpBinding"bindingConfiguration ="**contosoSTSBinding**"/&gt;<br /><br /> &lt;/message&gt;<br /><br /> &lt;/ 安全&gt;<br /><br /> &lt;/ 绑定&gt;<br /><br /> &lt;/wsFederationHttpBinding&gt;<br /><br /> \</**BindingConfiguration**><br /><br /> \<**ReferencedBindings** vt ="8"><br /><br /> &lt;绑定&gt;<br /><br /> &lt;wsFederationHttpBinding&gt;<br /><br /> &lt;绑定名称 ="**contosoSTSBinding**"&gt;<br /><br /> &lt;安全模式 ="Message"&gt;<br /><br /> &lt;消息 negotiateServiceCredential ="false"&gt;<br /><br /> &lt;颁发者地址 ="http://northwind.com/samplests"bindingConfiguration ="**northwindBinding**"绑定 ="wsHttpBinding"&gt;<br /><br /> &lt;/issuer&gt;<br /><br /> &lt;/message&gt;<br /><br /> &lt;/ 安全&gt;<br /><br /> &lt;/ 绑定&gt;<br /><br /> &lt;/wsFederationHttpBinding&gt;<br /><br /> &lt;wsHttpBinding&gt;<br /><br /> &lt;绑定名称 ="**northwindBinding**"&gt;<br /><br /> &lt;安全模式 ="Message"&gt;<br /><br /> &lt;消息 clientCredentialType ="证书"/&gt;<br /><br /> &lt;/ 安全&gt;<br /><br /> &lt;/ 绑定&gt;<br /><br /> &lt;/wsHttpBinding&gt;<br /><br /> &lt;/bindings&gt;<br /><br /> \</**ReferencedBindings**> **注意：** **ReferencedBinding**属性不能包含中使用的绑定配置**BindingConfiguration**属性。|指定引用的绑定配置**bindingConfiguration**属性**\<颁发者 >**元素**wsFederationHttpBinding**和**customBinding**，表示安全令牌服务 (STS) 颁发安全令牌。 有关详细信息**\<颁发者 >**元素，请参阅主题中，"\<颁发者 >"在[http://go.microsoft.com/fwlink/?LinkId=83476](http://go.microsoft.com/fwlink/?LinkId=83476)。<br /><br /> 绑定信息包括**\<颁发者 >**元素**wsFederationHttpBinding**和**customBinding**可通过配置**BindingConfiguration** WCF 自定义和 WCF CustomIsolated 适配器的属性。 此属性的引用的绑定配置的所有必须置于窗体的[\<绑定 >](http://go.microsoft.com/fwlink/?LinkID=80878)元素。 **注意：**无法在上配置此属性**绑定**传输的属性对话框中选项卡。 你可以导入和导出通过此属性**导入/导出**的 WCF 自定义和 WCF CustomIsolated 适配器的传输属性对话框中选项卡。 **注意：** **bindingConfiguration**属性**\<颁发者 >**元素必须引用此属性中的一个有效的绑定名称。 **注意：** **\<颁发者 >**引用的绑定配置中的元素也可以指 t 中的不同绑定配置其属性如果此引用链不会进行一个循环依赖关系. <br /><br /> 默认值为空字符串。|  
  
## <a name="configure-a-wcf-custom-receive-location-with-the-biztalk-administration-console"></a>配置 WCF 自定义接收位置使用 BizTalk 管理控制台
  
 您可以在 BizTalk 管理控制台中设置 WCF-Custom 接收位置适配器变量。 如果未设置接收位置的属性，则使用 BizTalk 管理控制台中设置的默认接收处理程序值。  
  
> [!NOTE]
>  在执行以下过程之前，您必须已添加接收端口。 有关详细信息，请参阅[如何创建接收端口](../core/how-to-create-a-receive-port.md)。  
  
## <a name="configure-variables-for-a-wcf-custom-receive-location"></a>WCF 自定义接收位置的配置变量  
  
1.  如果打算在配置 WCF-Custom 适配器时使用 WCF 扩展点（如自定义绑定元素、自定义行为元素和自定义通道组件），则必须同时在 BizTalk 处理计算机（运行时计算机）和管理计算机上向全局程序集缓存添加实现扩展点的程序集及所有依存程序集。 此外，您必须向 machine.config 文件注册扩展组件。 有关如何使用 WCF 自定义适配器 WCF 扩展点的详细信息，请参阅[如何启用与 WCF 适配器 WCF 扩展点](../core/how-to-enable-the-wcf-extensibility-points-with-the-wcf-adapters.md)。  
  
2.  在 BizTalk 管理控制台中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，展开**应用程序**，然后展开你要在其中创建接收位置的应用程序。  
  
3.  在 BizTalk 管理控制台的左窗格中，单击“接收端口”  节点。 随后，在右窗格中右键单击与现有接收位置关联的接收端口或要与新接收位置关联的接收端口，然后单击“属性” 。  
  
4.  在**接收端口属性**对话框中，在左侧的窗格中，选择**接收位置**，然后在右窗格中，双击现有接收位置或单击**新建**创建一个新接收位置。  
  
5.  在**接收位置属性**对话框中，在**传输**旁边部分**类型**，选择**WCF 自定义**从下拉列表列表，，然后单击**配置**。  
  
6.  在**WCF 自定义传输属性**对话框中，在**常规**选项卡上，配置终结点地址和 WCF 自定义的服务标识接收位置。 有关详细信息**常规**选项卡中**WCF 自定义传输属性**对话框中，请参阅**WCF 自定义传输属性对话框中，接收、 常规**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  
  
7.  在**WCF 自定义传输属性**对话框中，在**绑定**选项卡上，配置不同类型的 WCF 的预定义或自定义绑定。 有关详细信息**绑定**选项卡中**WCF 自定义传输属性**对话框中，请参阅**WCF 自定义传输属性对话框中，接收，绑定**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  
  
8.  在**WCF 自定义传输属性**对话框中，在**行为**选项卡，配置终结点，此服务行为接收位置。 终结点行为是一组行为扩展元素，这些元素修改或扩展服务或客户端功能。 有关详细信息**行为**选项卡中**WCF 自定义传输属性**对话框中，请参阅**WCF 自定义传输属性对话框中，接收，行为**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  
  
9. 在**WCF 自定义传输属性**对话框中，在**其他**选项卡上，配置此哪些凭据接收轮询的外部服务时要使用的位置和这是否接收位置在处理消息时，会保留消息顺序。 有关详细信息**其他**选项卡中**WCF 自定义传输属性**对话框中，请参阅**WCF 自定义传输属性对话框中，接收、 其他**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  
  
10. 在**WCF 自定义传输属性**对话框中，在**消息**选项卡上，指定 SOAP 数据选择**正文**元素。 有关详细信息**消息**选项卡中**WCF 自定义传输属性**对话框中，请参阅**WCF 自定义传输属性对话框中，接收、 消息**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  
  
11. 在**WCF 自定义传输属性**对话框中，在**导入/导出**选项卡上，导入和导出**地址 (URI)**和**终结点标识**属性**常规**选项卡上，在上绑定信息**绑定**选项卡上，和终结点行为**行为**此接收的选项卡位置。 有关详细信息**导入/导出**选项卡中**WCF 自定义传输属性**对话框中，请参阅**WCF 自定义传输属性对话框中，接收、 导入-导出**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  

## <a name="configure-a-wcf-custom-receive-location-programmatically"></a>以编程方式配置 WCF 自定义接收位置
  
 可使用以下格式设置属性：  
  
```  
<CustomProps>  
  <InboundBodyPathExpression vt="8" />  
  <InboundBodyLocation vt="8">UseBodyElement</InboundBodyLocation>  
  <BindingConfiguration vt="8"><binding name="netNamedPipeBinding"><security mode="None" /></binding></BindingConfiguration>  
  <OutboundXmlTemplate vt="8"><bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="xml"/></OutboundXmlTemplate>  
  <CredentialType vt="8">GetCredentials</CredentialType>  
  <Identity vt="8" />  
  <ServiceBehaviorConfiguration vt="8"><behavior name="SampleServiceBehavior"><serviceMetadata httpGetEnabled="true" httpGetUrl="http://mycomputer:9995/SampleService/Mex" /><serviceCredentials /></behavior></ServiceBehaviorConfiguration>  
  <Password vt="1" />  
  <OrderedProcessing vt="11">-1</OrderedProcessing>  
  <IncludeExceptionDetailInFaults vt="11">0</IncludeExceptionDetailInFaults>  
  <AffiliateApplicationName vt="8">SampleAffiliateApplication</AffiliateApplicationName>  
  <DisableLocationOnFailure vt="11">0</DisableLocationOnFailure>  
  <SuspendMessageOnFailure vt="11">0</SuspendMessageOnFailure>  
  <BindingType vt="8">netNamedPipeBinding</BindingType>  
  <UserName vt="8">Hello</UserName>  
  <InboundNodeEncoding vt="8">Xml</InboundNodeEncoding>  
  <EndpointBehaviorConfiguration vt="8"><behavior name="EndpointBehavior" /></EndpointBehaviorConfiguration>  
  <OutboundBodyLocation vt="8">UseBodyElement</OutboundBodyLocation>  
</CustomProps>  
  
```  
  
 以下代码段显示了如何创建 WCF-Custom 接收位置：  
  
```  
// Use BizTalk Explorer object model to create new WCF-Custom receive location   
string server = System.Environment.MachineName;  
string database = "BizTalkMgmtDb";  
string connectionString = string.Format("Server={0};Database={1};Integrated Security=true", server, database);  
string transportConfigData = @"<CustomProps>  
  <BindingConfiguration vt=""8""><binding name=""netNamedPipeBinding""><security mode=""None"" /></binding></BindingConfiguration>  
  <BindingType vt=""8"">netNamedPipeBinding</BindingType>  
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
// Find a receive handler for WCF-Custom   
int i = 0;  
for(i=0; i < explorer.ReceiveHandlers.Count; ++i)   
{  
    if("WCF-Custom" == explorer.ReceiveHandlers[i].TransportType.Name)  
        break;  
}  
recieveLocation.ReceiveHandler = explorer.ReceiveHandlers[i];  
recieveLocation.Address = "net.pipe://mycomputer/samplePipeName";  
recieveLocation.ReceivePipeline = explorer.Pipelines["Microsoft.BizTalk.DefaultPipelines.PassThruReceive"];  
recieveLocation.TransportType = explorer.ProtocolTypes["WCF-Custom"];  
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
 [配置 WCF 自定义适配器](../core/configuring-the-wcf-custom-adapter.md)   
 [如何创建关联应用程序](../core/how-to-create-an-affiliate-application.md)   
 [\<行为 > 的\<endpointBehaviors >](http://go.microsoft.com/fwlink/?LinkId=80879)   
 [\<绑定 >](http://go.microsoft.com/fwlink/?LinkId=80878)   
 [\<行为 > 的\<serviceBehaviors >](http://go.microsoft.com/fwlink/?LinkId=81095)