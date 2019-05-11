---
title: SOAP 标头与已使用的 Web 服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP headers, code samples
- Web services, consuming
- Web services, SOAP headers
- SOAP headers, Web services
- Web services, code samples
ms.assetid: 7be2eee1-ce1c-4611-985c-91dbc8492d6e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9cd18a60feae0d3726b56892d1bcea2864a25d97
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244346"
---
# <a name="soap-headers-with-consumed-web-services"></a>SOAP 标头与已使用的 Web 服务
将 Web 服务添加到你的业务流程使用后**添加 Web 引用**对话框中，可以使用 Web 服务描述语言 (WSDL) 定义 Web 服务中的 SOAP 标头。  
  
> [!NOTE]
>  已使用的 Web services 不支持未知的 SOAP 标头。  
  
 已使用的 Web 服务的 WSDL 列出绑定元素中定义的 SOAP 标头。 下面的示例演示已使用的 Web 服务的 WSDL 文件中的绑定元素：  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<definitions xmlns:http="http://schemas.xmlsoap.org/wsdl/http/" xmlns:soap="http://schemas.xmlsoap.org/wsdl/soap/" xmlns:s="http://www.w3.org/2001/XMLSchema" xmlns:s0="http://SOAPHeaderWS.ItemAvailability" xmlns:soapenc="http://schemas.xmlsoap.org/soap/encoding/" xmlns:tm="http://microsoft.com/wsdl/mime/textMatching/" xmlns:mime="http://schemas.xmlsoap.org/wsdl/mime/" targetNamespace="http://SOAPHeaderWS.ItemAvailability" xmlns="http://schemas.xmlsoap.org/wsdl/">  
       <types>  
             <s:schema elementFormDefault="qualified" targetNamespace="http://SOAPHeaderWS.ItemAvailability">  
  
                    <s:element name="OrigDest" type="s0:OrigDest"/>  
                    <s:complexType name="OrigDest">  
                           <s:sequence>  
                                 <s:element minOccurs="0" maxOccurs="1" name="Origination" type="s:string"/>  
                                 <s:element minOccurs="0" maxOccurs="1" name="Destination" type="s:string"/>  
                           </s:sequence>  
                    </s:complexType>  
             </s:schema>  
       </types>  
  
       <binding name="ItemAvailabilityServiceSoap" type="s0:ItemAvailabilityServiceSoap">  
             <soap:binding transport="http://schemas.xmlsoap.org/soap/http" style="document"/>  
             <operation name="ItemAvailability">  
                    <soap:operation soapAction="http://SOAPHeaderWS.ItemAvailability/ItemAvailability" style="document"/>  
                    <input>  
                           <soap:body use="literal"/>  
                           <soap:header message="s0:ItemAvailabilityOrigDest" part="OrigDest" use="literal"/>  
                    </input>  
                    <output>  
                           <soap:body use="literal"/>  
                           <soap:header message="s0:ItemAvailabilityOrigDest" part="OrigDest" use="literal"/>  
                    </output>  
             </operation>  
       </binding>  
       <service name="ItemAvailabilityService">  
             <port name="ItemAvailabilityServiceSoap" binding="s0:ItemAvailabilityServiceSoap">  
                    <soap:address location="http://localhost/SOAPHeaderWS/ItemAvailability.asmx"/>  
             </port>  
       </service>  
</definitions>  
```  
  
 有关使用 SOAP 标头的详细信息，请参阅"使用 SOAP 标头"在.NET Framework 文档中[ http://go.microsoft.com/fwlink/?LinkId=62266 ](http://go.microsoft.com/fwlink/?LinkId=62266)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [使用具有 SOAP 标头的 Web 服务](../core/consuming-web-services-with-soap-headers.md)  
  
-   [在业务流程中使用 SOAP 标头](../core/using-soap-headers-in-orchestrations.md)  
  
-   [在管道组件中使用 SOAP 标头](../core/using-soap-headers-in-pipeline-components.md)