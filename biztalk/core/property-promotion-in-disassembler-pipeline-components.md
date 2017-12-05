---
title: "在反汇编程序管道组件中的属性提升 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components, promoting properties
- XML Disassembler [pipeline component], properties
- pipeline components, properties
- promoting properties, disassembler pipeline components
- BizTalk Framework Assembler [pipeline component], properties
- Flat File Disassembler [pipeline component], properties
ms.assetid: aa37b308-8aa2-45f4-9383-aca4f2c925ce
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6c95c58dafe1f7f875232c5b65962e731334f16
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="property-promotion-in-disassembler-pipeline-components"></a>在反汇编程序管道组件中的属性提升
属性升级是使用 XPath 表达式从 XML 文档中提取属性值，再将其放置到消息上下文中以便用于消息路由的过程。  
  
 如果已提升的属性没有默认值或固定值，该属性的 XML 字段是缺失，并且验证文档结构属性是**False**，该属性不提升。  
  
 自定义管道组件可以升级多值（即数组）属性。 只有在基于内容的路由 (CBR) 方案中，才支持包含多值属性的消息；此类消息无法路由到业务流程或用于跟踪用途。  
  
 如果空元素带有结束标记，则 XML 拆装器不会升级其默认值或固定值。 例如， \<field1\>在下面的 XML 中不会对其进行提升。  
  
```  
<document>  
   <field1></field1>  
</document>  
```  
  
 但是，没有结束标记的空元素将升级，如下例所示：  
  
```  
<document>  
   <field1/>  
</document>  
```  
  
 从文档中读取日期时间数据并将其放在上下文属性中时，如果数据采用 UTC 格式，则保留该格式。 如果日期时间数据采用“本地时间+偏移量”格式，则 BizTalk Server 将日期时间格式转换为偏移量加本地时间所得到的 UTC 格式。 如果日期时间格式没有指定时区或 UTC 格式，则时间假定为本地时间，并基于当前时区转换为 UTC 格式。  
  
## <a name="see-also"></a>另请参阅  
 [XML 反汇编程序管道组件](../core/xml-disassembler-pipeline-component.md)   
 [如何将 XML 反汇编程序管道组件配置](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)