---
title: 数据类型映射，以接收来自 TIBCO 会合 |Microsoft 文档
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
ms.openlocfilehash: dcb17ceac0c323bba7a6f25cff0d07473b6d7fa3
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
ms.locfileid: "24014660"
---
# <a name="data-type-mapping-for-receive-handlers-in-tibco-rendezvous"></a>TIBCO Rendezvous 中用于接收处理程序的数据类型映射
用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器将 TIBCO RV 类型映射到 XML 架构类型，如下表中指定。  
  
## <a name="tibco-rv-to-xml-data-type-mapping"></a>TIBCO RV 到 XML 数据类型映射  
  
|TIBCO RV 类型|XML 架构类型|注释|  
|-------------------|---------------------|--------------|  
|TIBRVMSG_MSG|tibrv:message|从整个消息构造的完全 XML 文档。|  
|TIBRVMSG_XML|tibrv:rawxml|从字节数组构造的 XML 文档（不由适配器解释）。|  
|TIBRVMSG_DATETIME|xsd:dateTime|适配器使用 System.Xml.XmlConvert 类在 XML 架构 `dateTime` 和 `System.DateTime` 实例之间进行转换。|  
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
|TIBRVMSG_IPADDR32|tibrv:IPaddress|`System.Net.IPAddress.ToString( )` 用于生成输出。 内容以网络字节顺序进行排列。 ToString() 对其进行处理。|  
|TIBRVMSG_IPPORT16|tibrv:IPport|内容以网络字节顺序进行排列|  
|TIBRVMSG_I8ARRAY|tibrv:arrayOfByte|“tibrv”架构命名空间随适配器提供。|  
|TIBRVMSG_I16ARRAY|tibrv:arrayOfShort||  
|TIBRVMSG_I32ARRAY|tibrv:arrayOfInt||  
|TIBRVMSG_I64ARRAY|tibrv:arrayOfLong||  
|TIBRVMSG_U8ARRAY|tibrv:arrayOfUnsignedByte||  
|TIBRVMSG_U16ARRAY|tibrv:arrayOfUnsignedShort||  
|TIBRVMSG_U32ARRAY|tibrv:arrayOfUnsignedInt||  
|TIBRVMSG_U64ARRAY|tibrv:arrayOfUnsignedLong||  
|TIBRVMSG_F32ARRAY|tibrv:arrayOfFloat||  
|TIBRVMSG_F64ARRAY|tibrv:arrayOfDouble||  
  
 TIBCO Rendezvous 数组不同于具有相同名称的字段序列。 例如，在 TIBCO Rendezvous 消息中，具有 70,000 元素的数组是有效的，但是具有 70,000 字段则无效。  
  
 上表中数组类型的架构如下所示：  
  
```  
…  
<xsd:complexType name='arrayOfShort'>  
<xsd:sequence>  
<xsd:element name="item" type="xsd:short"/>  
</xsd:sequence>  
</xsd:complexType>  
  
```  
  
 消息中数组元素如下所示：  
  
```  
<someElement xsi:type='tibrv:arrayOfShort'>  
<item>100</item>  
<item>200</item>  
<item>300</item>  
<item>400</item>  
<item>500</item>  
</someElement>  
  
```  
  
 IPaddress 架构如下所示：  
  
```  
<xsd:simpleType name='IPaddress'>  
  
 <xsd:restriction base="xs:string">  
   <xsd:minLength value="7" />  
   <xsd:maxLength value="15" />  
  
 </xsd:restriction>  
       </xsd:simpleType>   
</xsd:simpleType>  
  
```  
  
 IPport 架构如下所示：  
  
```  
<xsd:simpleType name='IPport'>  
  
<xsd:restriction base='xsd:ushort'>  
</xsd:simpleType>  
```  
  
## <a name="see-also"></a>另请参阅  
 [TIBCO 集合中的消息映射](../core/message-mapping-in-tibco-rendezvous.md)   
 [创建 TIBCO Rendezvou 接收处理程序](../core/creating-tibco-rendezvous-receive-handlers.md)