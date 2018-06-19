---
title: 与已发布的 WCF 服务的 SOAP 标头 |Microsoft 文档
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
ms.openlocfilehash: 78f36e778930a781ac797e18308240ecb4bef667
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25975683"
---
# <a name="soap-headers-with-published-wcf-services"></a>SOAP 标头与发布的 WCF 服务
WCF 接收适配器可以将所有 SOAP 标头值都复制到入站消息中**InboundHeaders**属性，也可以编写或提升为 BizTalk 消息上下文的指定的值。 这些适配器可以处理 WCF 基础结构使用的自定义 SOAP 标头和标准 SOAP 标头，如 WS-Addressing、WS-Security 和 WS-AtomicTransaction。 **InboundHeaders**上下文属性是目标命名空间中**http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties**，并包含在 soap 的字符串表示形式入站消息中的标头值。  
  
> [!NOTE]
>  如果要升级您指定的 SOAP 标头值，BizTalk 项目中必须有与您要升级的值对应的已部署属性架构。  
  
> [!NOTE]
>  升级后的属性不得超过 256 个字符。  
  
 下面的 XML 数据显示的字符串表示形式的 SOAP 标头的示例**InboundHeaders**属性。 这来自客户端，并将发送到 BizTalk 接收位置。  
  
```  
<headers>  
<a:Action s:mustUnderstand="1" xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing">Operation_1</a:Action>  
<SalesAgent xmlns="Microsoft.Samples.BizTalk.WCF.CustomSoapHeaderPipeline">Contoso</SalesAgent>  
<a:MessageID xmlns:a="http://www.w3.org/2005/08/addressing">urn:uuid:26e6720f-5a82-4ef2-b597-6ef077bab92e</a:MessageID>  
<a:ReplyTo xmlns:a="http://www.w3.org/2005/08/addressing"><a:Address>http://www.w3.org/2005/08/addressing/anonymous</a:Address></a:ReplyTo>  
<a:To s:mustUnderstand="1" xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing">net.tcp://localhost:9990/NetTcpOrderProcess</a:To>  
</headers>  
```  
  
 若要将 SOAP 标头值写入或升级到 BizTalk 消息上下文，需要将由属性名称和命名空间组成的值对的集合放入 WCF 消息中，这样 WCF 适配器就可以知道将写入或升级这些标头值。 在将 SOAP 标头值写入或升级到 BizTalk 消息上下文时，WCF 适配器需要获取 WCF 消息中的以下消息属性：  
  
-   若要升级到 BizTalk 消息上下文的 SOAP 标头值，WCF 适配器要查找的键对**http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties/Promote**和值**列表\<KeyValuePair\<XmlQualifiedName，对象\>\>**。  
  
     使用此对，WCF 适配器采取命名空间、 名称和值从**XmlQualifiedName**对象，并将其用于升级的标头值。  
  
-   若要编写，但不是将提升为 BizTalk 消息上下文的 SOAP 标头值，WCF 适配器要查找的键对**http://schemas.microsoft.com/BizTalk/2006/01/Adapters/WCF-properties/WriteToContext**和值**列表\<KeyValuePair\<XmlQualifiedName，对象\>\>**。  
  
     WCF 适配器使用此对将这些值写入消息上下文。  
  
 以下代码显示的是如何将 SOAP 标头值写入或升级到 BizTalk 消息上下文：  
  
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
  
 BizTalk WCF 服务发布向导未将自定义 SOAP 标头定义包含在生成的元数据中。 若要使用自定义 SOAP 标头发布 WCF 服务的元数据，应手动创建 Web Services 描述语言 (WSDL) 文件。 你可以使用**externalMetadataLocation**属性[ \<serviceMetadata\> ](http://go.microsoft.com/fwlink/?LinkId=89121)向导生成指定的位置的 Web.config 文件中的元素WSDL 文件。 会向用户返回该 WSDL 文件以响应 WSDL 和元数据交换 (MEX) 请求，而不是返回自动生成的 WSDL。  
  
 以下 XML 数据显示的示例是定义自定义 SOAP 标头的 WSDL 文件的一部分：  
  
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
  
## <a name="see-also"></a>另请参阅  
 [WCF 适配器属性架构和属性](../core/wcf-adapters-property-schema-and-properties.md)   
 [SOAP 标头与使用的 WCF 服务](../core/soap-headers-with-consumed-wcf-services.md)