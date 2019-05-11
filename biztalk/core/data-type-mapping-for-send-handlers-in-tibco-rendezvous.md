---
title: TIBCO Rendezvous 中的数据类型用于发送处理程序映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fa1a9233-8781-45a8-9c55-a18ecaa0f456
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57987751e57353820f243d914da08f2fc57a73c3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352666"
---
# <a name="data-type-mapping-for-send-handlers-in-tibco-rendezvous"></a>用于 TIBCO Rendezvous 中的发送处理程序的数据类型映射
从 XML 架构类型到 TIBCO 集合类型的映射是仅当 TIBCO 集合提供类型信息 (xsi: type =)。 如果可能，任何不受支持的类型将映射到字符串。 如果映射不可能实现，或在端口配置中禁用该选项，则生成错误。  
  
## <a name="xml-schema-to-tibco-rendezvous-data-type-mapping"></a>XML 架构到 TIBCO 集合数据类型映射  
 下表显示可能的映射从 XML 架构类型到 TIBCO 集合类型。  
  
|XML 类型|TIBCO RV Type|  
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
|其他任何内容-具有调试消息|TIBRVMSG_STRING 日志。|  
  
 因为用于 TIBCO Rendezvous 的 BizTalk 适配器不具有访问架构，在从 BizTalk Server 传输到 TIBCO 集合时，必须提供 XML`xsi:type`任何非字符串字段的特性。 适配器使用该信息生成 TIBCO Rendezvous 消息中的相应消息字段类型。  
  
## <a name="message-mapping-example"></a>消息映射示例  
 下面的示例演示如何映射到 TIBCO Rendezvous 从 BizTalk Server 消息。 请参阅有关如何映射类型信息的数据类型映射表。  
  
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
  
 在前面的消息生成为结构化 TIBCO Rendezvous 消息后，它会具有六个字段的顶级 TibcoMsg 实例。 最后一个字段是子消息，两个字段组成的数组类型 (item 元素不映射到 TIBCO 集合消息字段，但一个类型的消息字段中的元素`array`)。 无类型的 MarketCap 字段将作为字符串消息字段发送。  
  
## <a name="see-also"></a>请参阅  
 [创建 TIBCO Rendezvous 发送处理程序](../core/creating-tibco-rendezvous-send-handlers.md)