---
title: "TIBCO 集合中的数据类型的发送处理程序映射 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML schemas, mapping to Redevous types
- message mapping, examples
- XML schemas, schema types
- data type mapping, send handlers
- examples, message mapping
- send handlers, data type mapping
ms.assetid: fa1a9233-8781-45a8-9c55-a18ecaa0f456
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6c54cb7ae684aa2f617ca615ed55703e331de46
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="data-type-mapping-for-send-handlers-in-tibco-rendezvous"></a>TIBCO Rendezvous 中用于发送处理程序的数据类型映射
仅当 TIBCO 集合提供类型信息 (xsi:type=) 时，从 XML 架构类型到 TIBCO 集合类型的映射才有可能。 如果可能，会将任何不受支持的类型映射到字符串。 如果映射不可能，或者该选项已在端口配置中被禁用，则会生成错误。  
  
## <a name="xml-schema-to-tibco-rendezvous-data-type-mapping"></a>XML 架构到 TIBCO 集合数据类型映射  
 下表显示从 XML 架构类型到 TIBCO 集合类型的可能映射。  
  
|XML 类型|TIBCO RV 类型|  
|--------------|-------------------|  
||TIBRVMSG_MSG|  
||TIBRVMSG_XML|  
|xsd:dateTime|TIBRVMSG_DATETIME|  
|xsd:boolean|TIBRVMSG_BOOL|  
|xsd:byte|TIBRVMSG_I8|  
|xsd:short|TIBRVMSG_I16|  
|xsd:int|TIBRVMSG_I32|  
|xsd:long|TIBRVMSG_I64|  
|xsd:unsignedByte|TIBRVMSG_U8|  
|xsd:unsignedShort|TIBRVMSG_U16|  
|xsd:unsignedInt|TIBRVMSG_U32|  
|xsd:unsignedLong|TIBRVMSG_U64|  
|xsd:float|TIBRVMSG_F32|  
|xsd:double|TIBRVMSG_F64|  
|tibrv:IPaddress|TIBRVMSG_IPADDR32|  
|tibrv:IPport|TIBRVMSG_IPPORT16|  
|tibrv:arrayOfByte|TIBRVMSG_I8ARRAY|  
|tibrv:arrayOfShort|TIBRVMSG_I16ARRAY|  
|tibrv:arrayOfInt|TIBRVMSG_I32ARRAY|  
|tibrv:arrayOfLong|TIBRVMSG_I64ARRAY|  
|tibrv:arrayOfUnsignedByte|TIBRVMSG_U8ARRAY|  
|tibrv:arrayOfUnsignedShort|TIBRVMSG_U16ARRAY|  
|tibrv:arrayOfUnsignedInt|TIBRVMSG_U32ARRAY|  
|tibrv:arrayOfUnsignedLong|TIBRVMSG_U64ARRAY|  
|tibrv:arrayOfFloat|TIBRVMSG_F32ARRAY|  
|tibrv:arrayOfDouble|TIBRVMSG_F64ARRAY|  
|其他任何内容 - 具有调试消息|TIBRVMSG_STRING 日志。|  
  
 由于 TIBCO 集合的 BizTalk 适配器没有对架构的访问权限，因此当您从 BizTalk Server 传输到 TIBCO 集合时，必须为任何非字符串字段提供 XML `xsi:type` 属性。 适配器使用该信息生成 TIBCO 集合消息中的相应消息字段类型。  
  
## <a name="message-mapping-example"></a>消息映射示例  
 下面的示例演示从 BizTalk Server 到 TIBCO 集合的消息映射。 有关如何映射类型的信息，请参考数据类型映射表。  
  
```  
<ns:QuoteUpdate xmlns:xsi http://www.w3.org/2001/XMLSchema-instance"  
xmlns:xsd http://www.w3.org/2001/XMLSchema"  
xmlns:tibrv="http://schemas.microsoft.com/TibcoRendezvous/Types"  
xmlns:ns="some namespace for this message [value not important, unless the schema is also used for receive ports]">  
  
<ns:SymbolName id=1 xsi:type="xsd:string">MSFT</ns:SymbolName>  
  
<ns:LastTrade id=2 xsi:type="xsd:double">28.40</ns:LastTrade>   
<ns:DayLow id=3 xsi:type="xsd:double">28.25</ns:DayLow>  
  
```  
  
|||  
|-|-|  
|`<ns:DayHigh`|`id=4 xsi:type="xsd:double">28.40</ns:DayHigh>`|  
|`<ns:MarketCap`|`id=10>262575234981</ns:MarketCap>`|  
|`<ns:Bids`|`id=100 xsi:type="tibrv:message">`|  
  
```  
<ns:TopBids id=1 xsi:type="tibrv:arrayOfDouble">  
<item>28.40</item>  
<item>28.39</item>  
<item>28.39</item>  
<item>28.39</item>  
<item>28.38</item>  
  
</ns:TopBids>  
  
<ns:BidsSize id=2 xsi:type="tibrv:arrayOfLong">  
<item>500</item>  
<item>1000</item>  
<item>100</item>  
<item>100</item>  
<item>2000</item>  
  
</ns:BidsSize>  
</ns:Bids>  
</ns:QuoteUpdate>  
  
```  
  
 将以前的消息生成为结构化的 TIBCO 集合消息之后，该消息将成为具有六个字段的顶级 TibcoMsg 实例。 最后字段是子消息，由两个数组类型的字段组成（“item”元素未映射到 TIBCO 集合消息字段，而是映射到类型为 `array` 的一个消息字段中的元素）。 未指定类型的 MarketCap 字段将作为字符串消息字段发送。  
  
## <a name="see-also"></a>另请参阅  
 [创建 TIBCO 会合发送处理程序](../core/creating-tibco-rendezvous-send-handlers.md)