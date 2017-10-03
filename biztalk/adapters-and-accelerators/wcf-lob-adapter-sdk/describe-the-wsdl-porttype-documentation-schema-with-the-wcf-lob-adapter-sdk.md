---
title: "描述与 WCF LOB 适配器 SDK 的 WSDL PortType 文档架构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9dd96eaf-b3b3-49b4-aea9-0ae1e8999d62
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 038b8ca075e756a0857e70a420c0fc7913113c92
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="describe-the-wsdl-porttype-documentation-schema-with-the-wcf-lob-adapter-sdk"></a>描述与 WCF LOB 适配器 SDK 的 WSDL PortType 文档架构
WSDL 的[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]生成包含的每个 portType 其他描述性信息。 此附加信息的架构是本主题中所述。  
  
## <a name="documentation-xml-schema"></a>文档 XML 架构  
 使用批注 portType 添加表示该操作的适配器文档的节点实现的操作文档。 此节点包含若干子节点，进一步描述的操作和参数。 此架构定义，如下所示。  
  
```  
\<?xml version="1.0" encoding="utf-8"?>  
\<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  \<xs:element name="adapterOperationDocumentation">  
    \<xs:complexType>  
      \<xs:sequence>  
        \<xs:element name="summary" type="xs:string" />  
        \<xs:element maxOccurs="unbounded" name="param">  
          \<xs:complexType>  
            \<xs:simpleContent>  
              \<xs:extension base="xs:string">  
                \<xs:attribute name="name" type="xs:string" use="required" />  
              \</xs:extension>  
            \</xs:simpleContent>  
          \</xs:complexType>  
        \</xs:element>  
        \<xs:element name="returns" type="xs:string" />  
      \</xs:sequence>  
    \</xs:complexType>  
  \</xs:element>  
\</xs:schema>  
```  
  
 当指定的操作生成 WSDL 时，前面的架构用于提供人类可读格式中的其他说明性信息。 例如，以下 portType 信息 Echo 适配器 EchoString 操作返回。  
  
```  
\<wsdl:portType name="EchoService">  
  \<wsdl:operation name="EchoString">  
    \<wsdl:documentation>  
      \<doc:adapterOperationDocumentation>  
        \<doc:summary>String EchoString( string aName)\</doc:summary>  
        \<doc:param name="aName">This string will be echoed back to the user.\</doc:param>  
        \<doc:returns>String value containing the value of aName \</doc:returns>  
      \</doc:adapterOperationDocumentation>  
    \</wsdl:documentation>  
    \<wsdl:input wsaw:Action="Echo/EchoString" message="ns2:EchoService_EchoString_InputMessage" />  
    \<wsdl:output wsaw:Action="Echo/EchoString/response" message="ns2:EchoService_EchoString_OutputMessage" />  
  \</wsdl:operation>  
\</wsdl:portType>  
```  
  
 文档元素的值从获得`Microsoft.ServiceModel.Channels.Common.ParameterizedOperationMetadata`操作。 前面的示例后生成下面的示例。  
  
```csharp  
ParameterizedOperationMetadata om = new ParameterizedOperationMetadata(operationId, operationId);  
// set this if you want this operation to belong to this interface name  
// in the generated proxy, the interface name will be EchoService  
// and the client implementation name will be EchoServiceClient.  
om.OperationGroup = "EchoService";  
// set the operation namespace to be same as service namespace  
om.OperationNamespace = EchoAdapter.SERVICENAMESPACE;              
switch (operationId)  
{  
   case "Echo/EchoString":  
       om.DisplayName = "EchoString";  
       om.OriginalName = "targetSystemEchoString";  
       om.Description = "String EchoString( string aName)";  
       OperationParameter parm1 = new OperationParameter("aName", OperationParameterDirection.In, QualifiedType.StringType, false);  
       parm1.Description = "This string will be echoed back to the user.";  
       OperationResult result = new OperationResult(new SimpleQualifiedType(XmlTypeCode.String), false);  
       result.Description = "String value containing the value of aName";  
       om.Parameters.Add(parm1);  
       om.OperationResult = result;  
       return om;   
```  
  
## <a name="see-also"></a>另请参阅  
 [使用 WCF LOB 适配器 SDK 开发最佳做法](../../adapters-and-accelerators/wcf-lob-adapter-sdk/development-best-practices-using-the-wcf-lob-adapter-sdk.md)