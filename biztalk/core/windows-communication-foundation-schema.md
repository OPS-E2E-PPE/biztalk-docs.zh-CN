---
title: Windows Communication Foundation 架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e95e0e8d-82cf-4608-b54f-188cb8cdaaee
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c40ede53410a2b75b1d63b86c7ed4eacc0f085be
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242836"
---
# <a name="windows-communication-foundation-schema"></a><span data-ttu-id="02769-102">Windows Communication Foundation 架构</span><span class="sxs-lookup"><span data-stu-id="02769-102">Windows Communication Foundation Schema</span></span>
<span data-ttu-id="02769-103">本部分包含 Windows Communication Framework 侦听器的架构。</span><span class="sxs-lookup"><span data-stu-id="02769-103">This section contains the schema for the Windows Communication Framework interceptor.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema targetNamespace="http://schemas.microsoft.com/BizTalkServer/2004/10/BAM/WcfInterceptorConfiguration"   
           xmlns="http://schemas.microsoft.com/BizTalkServer/2004/10/BAM/WcfInterceptorConfiguration"   
           xmlns:xs="http://www.w3.org/2001/XMLSchema"  
           elementFormDefault="qualified" >  
  
  <xs:element name="Operation">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="Argument" type="xs:string" minOccurs="0" maxOccurs="unbounded" />  
      </xs:sequence>  
      <xs:attribute name="Name" type="WcfOperationType" use="required" />  
    </xs:complexType>  
  </xs:element>  
  
  <xs:simpleType name="WcfOperationType">  
    <xs:restriction base="xs:string">  
      <xs:enumeration value="GetContextProperty" />  
      <xs:enumeration value="GetEndpointName" />  
      <xs:enumeration value="GetOperationName" />  
      <xs:enumeration value="GetServiceContractCallPoint" />  
      <xs:enumeration value="XPath" />  
      <xs:enumeration value="AutoGenerateCorrelationToken" />  
    </xs:restriction>  
  </xs:simpleType>  
  
  <xs:element name="NamespaceMappings">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="Namespace" type="WcfNamespaceMapping" minOccurs="1" maxOccurs="unbounded" />  
      </xs:sequence>  
    </xs:complexType>  
  </xs:element>  
  
  <xs:complexType name="WcfNamespaceMapping">  
    <xs:sequence>  
    </xs:sequence>  
    <xs:attribute name="Prefix" type="xs:string" use="required" />  
    <xs:attribute name="Uri" type="xs:string" use="required" />  
  </xs:complexType>  
  
</xs:schema>  
```  
  
## <a name="see-also"></a><span data-ttu-id="02769-104">请参阅</span><span class="sxs-lookup"><span data-stu-id="02769-104">See Also</span></span>  
 <span data-ttu-id="02769-105">[Windows Workflow Foundation 架构](../core/windows-workflow-foundation-schema.md) </span><span class="sxs-lookup"><span data-stu-id="02769-105">[Windows Workflow Foundation Schema](../core/windows-workflow-foundation-schema.md) </span></span>  
 [<span data-ttu-id="02769-106">侦听器配置架构</span><span class="sxs-lookup"><span data-stu-id="02769-106">Interceptor Configuration Schema</span></span>](../core/interceptor-configuration-schema.md)