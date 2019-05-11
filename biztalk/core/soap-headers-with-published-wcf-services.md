---
title: 与已发布的 WCF 服务的 SOAP 标头 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- publishing, SOAP headers [WCF services]
- SOAP headers, WCF services
- WCF services, SOAP headers
ms.assetid: 5564a57e-e241-4595-a959-4289c8502410
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d8a133dc15f88d35fe55d82c651738b15af69133
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244331"
---
# <a name="soap-headers-with-published-wcf-services"></a>SOAP 标头与已发布的 WCF 服务
WCF 接收适配器可以将所有 SOAP 标头值都复制到的入站消息中**InboundHeaders**属性，也可以写入或升级到 BizTalk 消息上下文的指定的值。 适配器可以使用自定义 SOAP 标头和标准 SOAP 标头，WCF 基础结构使用，如 Ws-addressing、 Ws-security 和 WS-AtomicTransaction。 **InboundHeaders**上下文属性位于目标命名空间**http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties**，并包含入站消息中的 SOAP 标头值的字符串表示形式。  
  
> [!NOTE]
>  如果要升级指定的 SOAP 标头值，对应于要升级的值在 BizTalk 项目中必须是已部署的属性架构。  
  
> [!NOTE]
>  升级的属性不能超过 256 个字符。  
  
 以下 XML 数据显示为 SOAP 标头的字符串表示形式的示例**InboundHeaders**属性。 这来自客户端和发送到 BizTalk 接收位置。  
  
```  
<headers>  
<a:Action s:mustUnderstand="1" xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing">Operation_1</a:Action>  
<SalesAgent xmlns="Microsoft.Samples.BizTalk.WCF.CustomSoapHeaderPipeline">Contoso</SalesAgent>  
<a:MessageID xmlns:a="http://www.w3.org/2005/08/addressing">urn:uuid:26e6720f-5a82-4ef2-b597-6ef077bab92e</a:MessageID>  
<a:ReplyTo xmlns:a="http://www.w3.org/2005/08/addressing"><a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address></a:ReplyTo>  
<a:To s:mustUnderstand="1" xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing">net.tcp://localhost:9990/NetTcpOrderProcess</a:To>  
</headers>  
```  
  
 若要写入或升级到 BizTalk 消息上下文的 SOAP 标头值，需要将包含属性名称和命名空间为 WCF 消息，使 WCF 适配器能够识别的标头值是以写入或升级的值对的集合。 WCF 适配器需要下面的消息属性中的 WCF 消息的写入或升级到 BizTalk 消息上下文的 SOAP 标头值：  
  
- 若要升级到 BizTalk 消息上下文的 SOAP 标头值，WCF 适配器会寻找的密钥对**http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties/Promote**和值**列表\<KeyValuePair\<XmlQualifiedName，对象\>\>**.  
  
   使用此对 WCF 适配器采用命名空间、 名称和值从**XmlQualifiedName**对象，并将其用于升级标头值。  
  
- 若要编写，而不是升级到 BizTalk 消息上下文的 SOAP 标头值，WCF 适配器会寻找的密钥对**http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties/WriteToContext**和值**列表\<KeyValuePair\<XmlQualifiedName，对象\>\>**。  
  
   WCF 适配器使用此对写入到消息上下文的值。  
  
  下面的代码演示如何写入或升级到 BizTalk 消息上下文的 SOAP 标头值：  
  
```  
const string PropertiesToPromoteKey="http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties/Promote";  
const string PropertiesToWriteKey="http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties/WriteToContext";  
  
XmlQualifiedName PropName1=new XmlQualifiedName("Destination", "http://tempuri.org/2007/sample-properties");  
XmlQualifiedName PropName2=new XmlQualifiedName("Source", "http://tempuri.org/2007/sample-properties");  
  
//Create a List of KeyValuePairs that indicate properties to be promoted to BizTalk message context.   
//A Property Schema must be deployed and string values have a limit of 256 characters  
List<KeyValuePair<XmlQualifiedName, object>> promoteProps=new List<KeyValuePair<XmlQualifiedName, object>>();  
promoteProps.Add(new KeyValuePair<XmlQualifiedName, object>(PropName1, "Property value"));  
wcfMessage.Properties[PropertiesToPromoteKey]=promoteProps;  
  
//Create a List of KeyValuePairs that indicate properties to be written to BizTalk message context  
List<KeyValuePair<XmlQualifiedName, object>> writeProps=new List<KeyValuePair<XmlQualifiedName, object>>();  
writeProps.Add(new KeyValuePair<XmlQualifiedName, object>(PropName2, "Property value"));  
wcfMessage.Properties[PropertiesToWriteKey]=writeProps;  
```  
  
 BizTalk WCF 服务发布向导不包括在生成的元数据中的自定义 SOAP 标头定义。 若要发布的 WCF 服务使用自定义 SOAP 标头的元数据，应手动创建 Web 服务描述语言 (WSDL) 文件。 可以使用**externalMetadataLocation**的属性[ \<serviceMetadata\> ](http://go.microsoft.com/fwlink/?LinkId=89121)元素中的 Web.config 文件，该向导将生成指定的位置WSDL 文件。 WSDL 文件返回到用户以响应 WSDL 和元数据交换 (MEX) 请求，而不是自动生成的 WSDL。  
  
 下面的 XML 数据显示了一部分定义自定义 SOAP 标头的 WSDL 文件的示例：  
  
```  
<wsdl:operation name="Request">  
  <soap12:operation soapAction="http://Microsoft.Samples.BizTalk.NetTcpAdapter/OrderProcess/IOrderProcess/Request" style="document" />   
   <wsdl:input name="Order">  
     <soap12:header message="i0:Order_Headers" part="SalesAgent" use="literal" />   
     <soap12:body use="literal" />   
   </wsdl:input>  
   <wsdl:output name="OrderConfirmation">  
     <soap12:header message="i0:OrderConfirmation_Headers" part="PaymentAgent" use="literal" />   
     <soap12:body use="literal" />   
   </wsdl:output>  
</wsdl:operation>  
```  
  
## <a name="in-this-section"></a>本节内容  
  
-   [使用业务流程访问 WCF 消息中的 SOAP 标头](../core/accessing-soap-headers-in-wcf-messages-with-orchestrations.md)  
  
-   [使用管道组件访问 WCF 消息中的 SOAP 标头](../core/accessing-soap-headers-in-wcf-messages-with-pipeline-components.md)  
  
## <a name="see-also"></a>请参阅  
 [WCF 适配器属性架构和属性](../core/wcf-adapters-property-schema-and-properties.md)   
 [SOAP 标头与使用的 WCF 服务](../core/soap-headers-with-consumed-wcf-services.md)