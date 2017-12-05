---
title: "如何配置 WCF 自定义发送端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a195c047-5d5c-478b-accd-252e9dc5cfe8
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c615e2f54e1d7db9115a2607162f6eae1dffc01a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-configure-a-wcf-custom-send-port"></a>如何配置 WCF-Custom 发送端口
可以通过编程方式或使用 BizTalk 管理控制台来配置 WCF-Custom 发送端口。  
  
## <a name="configuration-properties"></a>配置属性
  
 BizTalk 资源管理器对象模型公开了用于发送端口名为的特定于适配器的接口**ITransportInfo**具有**TransportTypeData**读/写属性。 此属性接受 XML 字符串的名称-值对形式的 WCF-Custom 发送端口配置属性包。  
  
 **TransportTypeData**属性**ITransportInfo**界面不是必需。 如果未设置该属性，则适配器将使用 WCF-Custom 发送端口配置的默认值，如下表所示。  
  
 下表列出了可在 BizTalk 浏览器对象模型中为 WCF-Custom 发送端口设置的配置属性。  
  
|属性名称|类型|Description|  
|-------------------|----------|-----------------|  
|**标识**|XML Blob<br /><br /> 例如：<br /><br /> &lt;标识&gt;<br /><br /> &lt;userPrincipalName 值 ="username@contoso.com"/&gt;<br /><br /> &lt;/identity&gt;|指定此发送端口预期的服务标识。 这些设置支持此发送端口对服务进行验证。 在客户端与服务进行握手的过程中，WCF 基础结构将确保预期服务的标识与此元素的值匹配。 可以为指定的值**标识**属性而异的安全配置。<br /><br /> 默认值为空字符串。|  
|**StaticAction**|字符串|指定**SOAPAction**传出消息的标头字段。 此外可以通过消息上下文属性设置此属性**WCF。操作**在管道或业务流程。 你可以通过两种方式指定此值： 单个操作格式和操作映射格式。 如果将此属性设置中的单个操作格式-例如，http://contoso.com/Svc/Op1- **SOAPAction**标头为传出消息始终设置为此属性中指定的值。<br /><br /> 如果在操作映射格式，传出中设置此属性**SOAPAction**标头由**BTS。操作**上下文属性。 例如，如果此属性设置为以下 XML 格式和**BTS。操作**属性设置为 Op1，为传出的 WCF 发送适配器使用 http://contoso.com/Svc/Op1 **SOAPAction**标头。<br /><br /> \<BtsActionMapping\><br /><br /> \<操作名称 ="Op1"操作 ="http://contoso.com/Svc/Op1"/\><br /><br /> \<操作名称 ="Op2"操作 ="http://contoso.com/Svc/Op2"/\><br /><br /> \</ BtsActionMapping\><br /><br /> 如果传出消息来自的业务流程端口时，动态设置业务流程实例**BTS。操作**与操作名称的端口的属性。 如果使用基于内容的路由路由传出消息，则可以设置**BTS。操作**管道组件中的属性。<br /><br /> 默认值为空字符串。|  
|**BindingType**|Enum<br /><br /> 有关成员名称的详细信息**BindingType**属性，请参阅**绑定类型**中的属性**WCF 自定义传输属性对话框中，发送，绑定**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。|指定此发送端口使用的终结点所采用的绑定类型。 **注意：**如果你使用的自定义绑定， **BindingType**属性可以配置使用自定义绑定。 有关如何使用自定义绑定的详细信息，请参阅[如何启用与 WCF 适配器 WCF 扩展点](../core/how-to-enable-the-wcf-extensibility-points-with-the-wcf-adapters.md)。|  
|**BindingConfiguration**|XML Blob<br /><br /> 例如：<br /><br /> &lt;绑定名称 ="netNamedPipeBinding"&gt;&lt;readerQuotas maxDepth ="32"maxStringContentLength ="8192"maxArrayLength ="16384"maxBytesPerRead ="4096"maxNameTableCharCount ="16384"/&gt;&lt;安全模式 ="None"/&gt;&lt;绑定&gt;|指定使用的 XML 字符串**\<绑定\>**元素来配置不同类型的预定义的绑定所提供的 Windows Communication Foundation (WCF)。 有关系统提供的绑定和自定义绑定的详细信息，请参阅“另请参见”部分中所列的相应主题。 **注意：** BizTalk Server 不支持你可以使用配置的绑定扩展元素的所有类型**BindingConfiguration**属性。 <br /><br /> 默认值为空字符串。|  
|**EndpointBehaviorConfiguration**|XML Blob<br /><br /> 例如：<br /><br /> &lt;行为名称 ="sampleBehavior"&gt;&lt;callbackTimeouts /&gt;&lt;/behavior&gt;|指定使用的 XML 字符串**\<行为\>**元素 **\<endpointBehaviors\>** 元素来配置的行为设置WCF 终结点。 有关详细信息 **\<endpointBehaviors\>** 元素，请参阅另请参阅中的相应主题。 **注意：** BizTalk Server 不支持你可以使用配置的行为扩展元素的所有类型**EndpointBehaviorConfiguration**属性。 <br /><br /> 默认值为空字符串。|  
|**AffiliateApplicationName**|字符串|指定用于企业单一登录 (SSO) 的关联应用程序。<br /><br /> 默认值为空字符串。|  
|**UseSSO**|Boolean|指定是否使用单一登录检索客户端凭据，以便在目标服务器上进行验证。<br /><br /> 默认值： **False**|  
|**UserName**|字符串|指定要用于目标服务器的身份验证的用户名称时**UseSSO**属性设置为**False**。 不必采用“域\用户”格式设置此属性。<br /><br /> 默认值为空字符串。|  
|**密码**|字符串|指定要用于目标服务器的身份验证的密码时**UseSSO**属性设置为**False**。<br /><br /> 默认值为空字符串。|  
|**OutboundBodyLocation**|Enum<br /><br /> -   **UseBodyElement** -BizTalk 消息正文部分用于创建的 SOAP 内容**正文**传出消息的元素。<br />-   **UseTemplate** -使用中提供的模板**OutboundXMLTemplate**属性来创建的内容 SOAP**正文**传出消息的元素。<br /><br /> 有关如何使用**OutboundBodyLocation**属性，请参阅[为 WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。|指定 SOAP 数据选择**正文**传出的 WCF 消息的元素。<br /><br /> 默认值： **UseBodyElement**|  
|**OutboundXMLTemplate**|字符串<br /><br /> 有关如何使用**OutboundXMLTemplate**属性，请参阅[为 WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。|指定的 SOAP 内容的 XML 格式模板**正文**的传出消息的元素。 此属性是必需的如果**OutboundBodyLocation**属性设置为**UseTemplate**。<br /><br /> 默认值为空字符串。|  
|**InboundBodyLocation**|Enum<br /><br /> -   **UseBodyElement** -使用 SOAP 的内容**正文**传入消息创建 BizTalk 消息正文部分的元素。 如果 **Body** 元素具有多个子元素，则只有第一个元素将成为 BizTalk 消息正文部分。 此属性仅对要求-响应端口有效。<br />-   **UseEnvelope** -从整个 SOAP 创建 BizTalk 消息正文部分**信封**传入消息。<br />-   **UseBodyPath** -使用中的正文路径表达式**InboundBodyPathExpression**属性创建 BizTalk 消息正文部分。 针对传入消息的 SOAP **Body** 元素的直接子元素计算正文路径表达式。 此属性仅对要求-响应端口有效。<br /><br /> 有关如何使用**InboundBodyLocation**属性，请参阅[为 WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)。|指定 SOAP 数据选择**正文**传入 WCF 消息的元素。<br /><br /> 默认值： **UseBodyElement**|  
|**InboundBodyPathExpression**|字符串<br /><br /> 有关如何使用**InboundBodyPathExpression**属性，请参阅[WCF 适配器属性架构和属性](../core/wcf-adapters-property-schema-and-properties.md)。|指定正文路径表达式以标识传入消息中用于创建 BizTalk 消息正文部分的特定部分。 此正文路径表达式针对 SOAP 的即时子元素进行评估**正文**传入消息的节点。 如果此正文路径表达式返回多个节点，则只选择第一个节点作为 BizTalk 消息正文部分。 此属性是必需的如果**InboundBodyLocation**属性设置为**UseBodyPath**。 此属性仅对要求-响应端口有效。<br /><br /> 默认值为空字符串。|  
|**InboundNodeEncoding**|Enum<br /><br /> -   **XML**<br />-   **Base64** -Base64 编码。<br />-   **十六进制**-十六进制编码。<br />-   **字符串**编码文本的 utf-8。<br />-   **XML** -WCF 适配器使用由正文路径表达式中所选节点的外部 XML 创建 BizTalk 消息正文**InboundBodyPathExpression**。|指定的 WCF 自定义发送适配器用于解码由中指定的正文路径标识的节点的编码类型**InboundBodyPathExpression**。 此属性是必需的如果**InboundBodyLocation**属性设置为**UseBodyPath**。 此属性仅对要求-响应端口有效。<br /><br /> 默认值： **XML**|  
|**PropagateFaultMessage**|Boolean<br /><br /> -   **True** -失败对订阅应用程序的出站处理将消息路由 （如另一个接收端口或业务流程计划）。<br />-   **False** -挂起失败的消息并生成否定确认 (NACK)。|指定是路由还是挂起在出站处理中失败的消息。<br /><br /> 此属性仅对要求-响应端口有效。<br /><br /> 默认值： **True**|  
|**ReferencedBindings**|XML Blob<br /><br /> 例如：<br /><br /> \<**BindingConfiguration** vt ="8"\><br /><br /> &lt;wsFederationHttpBinding&gt;<br /><br /> &lt;绑定名称 ="sampleBinding"&gt;<br /><br /> &lt;安全模式 ="Message"&gt;<br /><br /> &lt;消息 issuedKeyType ="AsymmetricKey"&gt;<br /><br /> &lt;颁发者地址 ="http://www.contoso.com/samplests"绑定 ="wsFederationHttpBinding"bindingConfiguration ="**contosoSTSBinding**"/&gt;<br /><br /> &lt;/message&gt;<br /><br /> &lt;/ 安全&gt;<br /><br /> &lt;/ 绑定&gt;<br /><br /> &lt;/wsFederationHttpBinding&gt;<br /><br /> \</**BindingConfiguration**\><br /><br /> \<**ReferencedBindings** vt ="8"\><br /><br /> &lt;绑定&gt;<br /><br /> &lt;wsFederationHttpBinding&gt;<br /><br /> &lt;绑定名称 ="**contosoSTSBinding**"&gt;<br /><br /> &lt;安全模式 ="Message"&gt;<br /><br /> &lt;消息 negotiateServiceCredential ="false"&gt;<br /><br /> &lt;颁发者地址 ="http://northwind.com/samplests"bindingConfiguration ="**northwindBinding**"绑定 ="wsHttpBinding"&gt;<br /><br /> &lt;/issuer&gt;<br /><br /> &lt;/message&gt;<br /><br /> &lt;/ 安全&gt;<br /><br /> &lt;/ 绑定&gt;<br /><br /> &lt;/wsFederationHttpBinding&gt;<br /><br /> &lt;wsHttpBinding&gt;<br /><br /> &lt;绑定名称 ="**northwindBinding**"&gt;<br /><br /> &lt;安全模式 ="Message"&gt;<br /><br /> &lt;消息 clientCredentialType ="证书"/&gt;<br /><br /> &lt;/ 安全&gt;<br /><br /> &lt;/ 绑定&gt;<br /><br /> &lt;/wsHttpBinding&gt;<br /><br /> &lt;/bindings&gt;<br /><br /> \</**ReferencedBindings** \> **注意：** **ReferencedBinding**属性不能包含中使用的绑定配置**BindingConfiguration**属性。|指定引用的绑定配置**bindingConfiguration**属性**\<颁发者\>**元素**wsFederationHttpBinding**和**customBinding**，表示安全令牌服务 (STS) 颁发安全令牌。 有关详细信息**\<颁发者\>**元素，请参阅主题中，"\<颁发者\>"在[http://go.microsoft.com/fwlink/?LinkId=83476](http://go.microsoft.com/fwlink/?LinkId=83476)。<br /><br /> 绑定信息包括**\<颁发者\>**元素**wsFederationHttpBinding**和**customBinding**可以是通过配置**BindingConfiguration** WCF 自定义和 WCF CustomIsolated 适配器的属性。 此属性的引用的绑定配置的所有必须置于窗体的[\<绑定\>](http://go.microsoft.com/fwlink/?LinkID=80878)元素。 **注意：**无法在上配置此属性**绑定**传输的属性对话框中选项卡。 你可以导入和导出通过此属性**导入/导出**的 WCF 自定义和 WCF CustomIsolated 适配器的传输属性对话框中选项卡。 **注意：** **bindingConfiguration**属性**\<颁发者\>**元素必须引用此属性中的一个有效的绑定名称。 **注意：** **\<颁发者\>**引用的绑定配置中的元素也可以指 t 中的不同绑定配置其属性如果此引用链不会进行循环依赖关系。 <br /><br /> 默认值为空字符串。|  
  
## <a name="configure-a-wcf-custom-send-port-with-the-biztalk-administration-console"></a>使用 BizTalk 管理控制台中配置 WCF 自定义发送端口
  
 您可以在 BizTalk 管理控制台中设置 WCF-Custom 发送端口适配器变量。 如果没有为发送端口设置属性，将使用 WCF-Custom 发送端口配置的默认值，如前表所示。  
  
## <a name="configure-variables-for-a-wcf-custom-send-port"></a>配置变量 WCF 自定义发送端口  
  
1.  如果打算在配置 WCF-Custom 适配器时使用 WCF 扩展点（如自定义绑定元素、自定义行为元素和自定义通道组件），则必须同时在 BizTalk 处理计算机（运行时计算机）和管理计算机上向全局程序集缓存添加实现扩展点的程序集及所有依存程序集。 此外，您必须向 machine.config 文件注册扩展组件。 有关如何使用 WCF 自定义适配器 WCF 扩展点的详细信息，请参阅[如何启用与 WCF 适配器 WCF 扩展点](../core/how-to-enable-the-wcf-extensibility-points-with-the-wcf-adapters.md)。  
  
2.  在 BizTalk 管理控制台中，创建一个新的发送端口或双击某个现有发送端口以对其进行修改。 有关详细信息，请参阅[如何创建发送端口](../core/how-to-create-a-send-port2.md)。 配置所有发送端口选项并指定**WCF 自定义**为**类型**选项**传输**部分**常规**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].  
  
3.  上**常规**选项卡上，在**传输**部分中，单击**配置**按钮旁边**类型**。  
  
4.  在**WCF 自定义传输属性**对话框中，在**常规**选项卡上配置的终结点地址，服务标识，与**SOAPAction**标头WCF 自定义发送端口。 有关详细信息**常规**选项卡中**WCF 自定义传输属性**对话框中，请参阅**WCF 自定义传输属性对话框中，发送，常规**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  
  
5.  在**WCF 自定义传输属性**对话框中，在**绑定**选项卡上，配置不同类型的 WCF 的预定义或自定义绑定。 有关详细信息**绑定**选项卡中**WCF 自定义传输属性**对话框中，请参阅**WCF 自定义传输属性对话框中，发送，绑定**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  
  
6.  在**WCF 自定义传输属性**对话框中，在**行为**选项卡上，配置此发送端口的终结点行为。 终结点行为是修改或扩展服务或客户端功能的行为扩展元素的一组。 有关详细信息**行为**选项卡中**WCF 自定义传输属性**对话框中，请参阅**WCF 自定义传输属性对话框中，发送，行为**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  
  
7.  在**WCF 自定义传输属性**对话框中，在**凭据**选项卡上，指定要发送消息时使用的凭据。 有关详细信息**凭据**选项卡中**WCF 自定义传输属性**对话框框中，请参阅**WCF 自定义传输属性对话框中，发送凭据**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  
  
8.  在**WCF 自定义传输属性**对话框中，在**消息**选项卡上，指定 SOAP 数据选择**正文**元素。 有关详细信息**消息**选项卡中**WCF 自定义传输属性**对话框中，请参阅**WCF 自定义传输属性对话框中，发送消息**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  
  
9. 在**WCF 自定义传输属性**对话框中，在**导入/导出**选项卡上，导入和导出**地址 (URI)**和**终结点标识**属性**常规**选项卡上，在上绑定信息**绑定**选项卡上，和终结点行为**行为**此发送端口的选项卡。 有关详细信息**导入/导出**选项卡中**WCF 自定义传输属性**对话框中，请参阅**WCF 自定义传输属性对话框中，发送，导入-导出**选项卡[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。  
  
## <a name="configure-a-wcf-custom-send-port-programmatically"></a>以编程方式配置 WCF 自定义发送端口  
  
 可使用以下格式设置属性：  
  
```  
<CustomProps>  
  <OutboundXmlTemplate vt="8"><bts-msg-body xmlns="http://www.microsoft.com/schemas/bts2007" encoding="xml"/></OutboundXmlTemplate>  
  <InboundBodyPathExpression vt="8" />  
  <EndpointBehaviorConfiguration vt="8"><behavior name="sampleBehavior"><callbackTimeouts /></behavior></EndpointBehaviorConfiguration>  
  <OutboundBodyLocation vt="8">UseBodyElement</OutboundBodyLocation>  
  <StaticAction vt="8">http://www.northwindtraders.com/Service/Operation</StaticAction>  
  <BindingConfiguration vt="8"><binding name="NetNamedPipeOrderProcessService.OrderProcessServieEndpoint"><readerQuotas maxDepth="32" maxStringContentLength="8192" maxArrayLength="16384" maxBytesPerRead="4096" maxNameTableCharCount="16384" /><security mode="None" /></binding></BindingConfiguration>  
  <InboundNodeEncoding vt="8">Xml</InboundNodeEncoding>  
  <UseSSO vt="11">0</UseSSO>  
  <AffiliateApplicationName vt="8" />  
  <BindingType vt="8">netNamedPipeBinding</BindingType>  
  <InboundBodyLocation vt="8">UseBodyElement</InboundBodyLocation>  
  <UserName vt="8" />  
  <PropagateFaultMessage vt="11">-1</PropagateFaultMessage>  
</CustomProps>  
  
```  
  
 下面的代码段说明了如何创建 WCF-Custom 发送端口：  
  
```  
// Use BizTalk Explorer object model to create new WCF-Custom send port.  
string server = System.Environment.MachineName;  
string database = "BizTalkMgmtDb";  
string connectionString = string.Format("Server={0};Database={1};Integrated Security=true", server, database);  
string transportConfigData = @"<CustomProps>  
                                 <StaticAction vt=""8"">http://www.northwindtraders.com/Service/Operation</StaticAction>  
                                 <EndpointBehaviorConfiguration vt=""8""><behavior name=""sampleBehavior""><callbackTimeouts /></behavior></EndpointBehaviorConfiguration>  
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
  
// Add a new static one-way send port  
SendPort sendPort = application.AddNewSendPort(false, false);   
sendPort.Name = "SampleSendPort";  
sendPort.PrimaryTransport.TransportType = explorer.ProtocolTypes["WCF-Custom"];  
sendPort.PrimaryTransport.Address = "net.pipe://mycomputer/private/samplequeue";  
sendPort.PrimaryTransport.TransportTypeData = transportConfigData; // propertyData; // need to change  
sendPort.SendPipeline = explorer.Pipelines["Microsoft.BizTalk.DefaultPipelines.PassThruTransmit"];  
// Save  
explorer.SaveChanges();  
```  
  
## <a name="see-also"></a>另请参阅  
 [WCF 适配器属性架构和属性](../core/wcf-adapters-property-schema-and-properties.md)   
 [为 WCF 适配器指定消息正文](../core/specifying-the-message-body-for-the-wcf-adapters.md)   
 [将证书安装适用于这些 WCF 适配器](../core/installing-certificates-for-the-wcf-adapters.md)   
 [配置 WCF 自定义适配器](../core/configuring-the-wcf-custom-adapter.md)   
 [配置动态发送端口使用 WCF 适配器上下文属性](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)   
 [\<绑定\>](http://go.microsoft.com/fwlink/?LinkId=80878)   
 [\<行为\>的\<endpointBehaviors\>](http://go.microsoft.com/fwlink/?LinkId=80879)