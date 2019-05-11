---
title: 数据类型映射，以接收来自 TIBCO Rendezvous |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 36908a94-3c0d-466e-aa49-f674ba4a26af
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37f064021c58e2d870df8e1110a07ce42d0dc9ab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389958"
---
# <a name="data-type-mapping-for-receive-handlers-in-tibco-rendezvous"></a>数据类型映射中 TIBCO Rendezvous 接收处理程序
用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器将 TIBCO RV 类型映射到下表中指定的 XML 架构类型。  
  
## <a name="tibco-rv-to-xml-data-type-mapping"></a>TIBCO RV 到 XML 数据类型映射  
  
|TIBCO RV Type|XML 架构类型|注释|  
|-------------------|---------------------|--------------|  
|TIBRVMSG_MSG|tibrv:message|从整个消息构造完整的 XML 文档。|  
|TIBRVMSG_XML|tibrv:rawxml|构造的 （不由适配器解释） 的字节数组从 XML 文档。|  
|TIBRVMSG_DATETIME|xsd:dateTime|适配器使用 System.Xml.XmlConvert 类 XML 架构之间进行转换`dateTime`和`System.DateTime`实例。|  
|TIBRVMSG_OPAQUE|xsd:base64Binary||  
|TIBRVMSG_STRING|xsd:string||  
|TIBRVMSG_BOOL|xsd:boolean||  
|TIBRVMSG_I8|xsd:byte||  
|TIBRVMSG_I16|xsd:short||  
|TIBRVMSG_I32|xsd:int||  
|TIBRVMSG_I64|xsd:long||  
|TIBRVMSG_U8|xsd:unsignedByte||  
|TIBRVMSG_U16|xsd:unsignedShort||  
|TIBRVMSG_U32|xsd:unsignedInt||  
|TIBRVMSG_U64|xsd:unsignedLong||  
|TIBRVMSG_F32|xsd:float||  
|TIBRVMSG_F64|xsd:double||  
|TIBRVMSG_IPADDR32|tibrv:IPaddress|`System.Net.IPAddress.ToString( )` 用于生成输出。 内容是以网络字节顺序。 Tostring （） 将负责的。|  
|TIBRVMSG_IPPORT16|tibrv:IPport|内容以网络字节顺序|  
|TIBRVMSG_I8ARRAY|tibrv:arrayOfByte|tibrv 架构命名空间随适配器提供。|  
|TIBRVMSG_I16ARRAY|tibrv:arrayOfShort||  
|TIBRVMSG_I32ARRAY|tibrv:arrayOfInt||  
|TIBRVMSG_I64ARRAY|tibrv:arrayOfLong||  
|TIBRVMSG_U8ARRAY|tibrv:arrayOfUnsignedByte||  
|TIBRVMSG_U16ARRAY|tibrv:arrayOfUnsignedShort||  
|TIBRVMSG_U32ARRAY|tibrv:arrayOfUnsignedInt||  
|TIBRVMSG_U64ARRAY|tibrv:arrayOfUnsignedLong||  
|TIBRVMSG_F32ARRAY|tibrv:arrayOfFloat||  
|TIBRVMSG_F64ARRAY|tibrv:arrayOfDouble||  
  
 TIBCO Rendezvous 数组不同于一系列具有相同名称的字段。 例如，在 TIBCO Rendezvous 消息中，它是有效的数组具有 70,000 元素，但并不有效具有 70,000 字段。  
  
 上表中的数组类型的架构如下所示：  
  
```  
…  
<xsd:complexType name='arrayOfShort'>  
<xsd:sequence>  
<xsd:element name="item" type="xsd:short"/>  
</xsd:sequence>  
</xsd:complexType>  
  
```  
  
 在消息中的数组元素如下所示：  
  
```  
<someElement xsi:type='tibrv:arrayOfShort'>  
<item>100</item>  
<item>200</item>  
<item>300</item>  
<item>400</item>  
<item>500</item>  
</someElement>  
  
```  
  
 Ipaddress 架构如下所示：  
  
```  
<xsd:simpleType name='IPaddress'>  
  
 <xsd:restriction base="xs:string">  
   <xsd:minLength value="7" />  
   <xsd:maxLength value="15" />  
  
 </xsd:restriction>  
       </xsd:simpleType>   
</xsd:simpleType>  
  
```  
  
 Ipport 架构如下所示：  
  
```  
<xsd:simpleType name='IPport'>  
  
<xsd:restriction base='xsd:ushort'>  
</xsd:simpleType>  
```  
  
## <a name="see-also"></a>请参阅  
 [TIBCO Rendezvous 中消息映射](../core/message-mapping-in-tibco-rendezvous.md)   
 [创建 TIBCO Rendezvou 接收处理程序](../core/creating-tibco-rendezvous-receive-handlers.md)