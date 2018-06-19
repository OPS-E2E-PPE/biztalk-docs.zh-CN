---
title: 描述与 WCF LOB 适配器 SDK 的 WSDL PortType 文档架构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9dd96eaf-b3b3-49b4-aea9-0ae1e8999d62
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81e4977403da18229aea19beef21f361dfdd9391
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965147"
---
# <a name="describe-the-wsdl-porttype-documentation-schema-with-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="ddf1d-102">描述与 WCF LOB 适配器 SDK 的 WSDL PortType 文档架构</span><span class="sxs-lookup"><span data-stu-id="ddf1d-102">Describe the WSDL PortType Documentation Schema with the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="ddf1d-103">WSDL 的[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]生成包含的每个 portType 其他描述性信息。</span><span class="sxs-lookup"><span data-stu-id="ddf1d-103">The WSDL that the  [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] generates contains additional descriptive information for each portType.</span></span> <span data-ttu-id="ddf1d-104">此附加信息的架构是本主题中所述。</span><span class="sxs-lookup"><span data-stu-id="ddf1d-104">The schema for this additional information is described in this topic.</span></span>  
  
## <a name="documentation-xml-schema"></a><span data-ttu-id="ddf1d-105">文档 XML 架构</span><span class="sxs-lookup"><span data-stu-id="ddf1d-105">Documentation XML Schema</span></span>  
 <span data-ttu-id="ddf1d-106">使用批注 portType 添加表示该操作的适配器文档的节点实现的操作文档。</span><span class="sxs-lookup"><span data-stu-id="ddf1d-106">The operation documentation is implemented using annotation of the portType to add a node that represents the adapter documentation for the operation.</span></span> <span data-ttu-id="ddf1d-107">此节点包含若干子节点，进一步描述的操作和参数。</span><span class="sxs-lookup"><span data-stu-id="ddf1d-107">This node contains subnodes that further describe the operation and parameters.</span></span> <span data-ttu-id="ddf1d-108">此架构定义，如下所示。</span><span class="sxs-lookup"><span data-stu-id="ddf1d-108">This schema is defined as follows.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema attributeFormDefault="unqualified" elementFormDefault="qualified" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
  <xs:element name="adapterOperationDocumentation">  
    <xs:complexType>  
      <xs:sequence>  
        <xs:element name="summary" type="xs:string" />  
        <xs:element maxOccurs="unbounded" name="param">  
          <xs:complexType>  
            <xs:simpleContent>  
              <xs:extension base="xs:string">  
                <xs:attribute name="name" type="xs:string" use="required" />  
              </xs:extension>  
            </xs:simpleContent>  
          </xs:complexType>  
        </xs:element>  
        <xs:element name="returns" type="xs:string" />  
      </xs:sequence>  
    </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="ddf1d-109">当指定的操作生成 WSDL 时，前面的架构用于提供人类可读格式中的其他说明性信息。</span><span class="sxs-lookup"><span data-stu-id="ddf1d-109">When WSDL is generated for a given operation, the preceding schema is used to provide additional descriptive information in human readable format.</span></span> <span data-ttu-id="ddf1d-110">例如，以下 portType 信息 Echo 适配器 EchoString 操作返回。</span><span class="sxs-lookup"><span data-stu-id="ddf1d-110">For example, the following portType information is returned for the EchoString operation of the Echo Adapter.</span></span>  
  
```  
<wsdl:portType name="EchoService">  
  <wsdl:operation name="EchoString">  
    <wsdl:documentation>  
      <doc:adapterOperationDocumentation>  
        <doc:summary>String EchoString( string aName)\</doc:summary>  
        <doc:param name="aName">This string will be echoed back to the user.\</doc:param>  
        <doc:returns>String value containing the value of aName \</doc:returns>  
      </doc:adapterOperationDocumentation>  
    </wsdl:documentation>  
    <wsdl:input wsaw:Action="Echo/EchoString" message="ns2:EchoService_EchoString_InputMessage" />  
    <wsdl:output wsaw:Action="Echo/EchoString/response" message="ns2:EchoService_EchoString_OutputMessage" />  
  </wsdl:operation>  
</wsdl:portType>  
```  
  
 <span data-ttu-id="ddf1d-111">文档元素的值从获得`Microsoft.ServiceModel.Channels.Common.ParameterizedOperationMetadata`操作。</span><span class="sxs-lookup"><span data-stu-id="ddf1d-111">The values for the documentation elements are obtained from `Microsoft.ServiceModel.Channels.Common.ParameterizedOperationMetadata` for the operation.</span></span> <span data-ttu-id="ddf1d-112">前面的示例后生成下面的示例。</span><span class="sxs-lookup"><span data-stu-id="ddf1d-112">The preceding example was generated as a result of the following example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ddf1d-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ddf1d-113">See Also</span></span>  
 [<span data-ttu-id="ddf1d-114">使用 WCF LOB 适配器 SDK 开发最佳做法</span><span class="sxs-lookup"><span data-stu-id="ddf1d-114">Development best practices using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/development-best-practices-using-the-wcf-lob-adapter-sdk.md)