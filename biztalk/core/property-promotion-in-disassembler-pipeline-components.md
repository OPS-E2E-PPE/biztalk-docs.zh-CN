---
title: 拆装器管道组件中的属性升级 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, promoting properties
- XML Disassembler [pipeline component], properties
- pipeline components, properties
- promoting properties, disassembler pipeline components
- BizTalk Framework Assembler [pipeline component], properties
- Flat File Disassembler [pipeline component], properties
ms.assetid: aa37b308-8aa2-45f4-9383-aca4f2c925ce
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26e8b358b70c12ecf5567c19377fa8419f5bea83
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398466"
---
# <a name="property-promotion-in-disassembler-pipeline-components"></a>拆装器管道组件中的属性升级
属性升级是使用 XPath 表达式从 XML 文档中提取属性值并将它放置在消息上下文，以便它可用于消息路由所依据的进程。  
  
 如果升级的属性不具有默认值或固定值，该属性的 XML 字段是缺失，并且验证文档结构属性是**False**，则不升级该属性。  
  
 自定义管道组件可以升级多值 （即数组） 属性。 基于内容的路由 (CBR) 方案; 仅支持包含多值的属性的消息它们不能路由到业务流程或用于进行跟踪。  
  
 XML 拆装器不会升级其默认值或固定值的空元素，如果它具有结束标记。 例如， \<field1\>以下 XML 不会升级。  
  
```  
<document>  
   <field1></field1>  
</document>  
```  
  
 但是，升级空元素没有结束标记 （如下面的示例中所示）。  
  
```  
<document>  
   <field1/>  
</document>  
```  
  
 当从一个文档并将其放置到上下文属性，如果数据采用 UTC 格式读取日期时间数据，则保留该格式。 如果日期时间数据的格式本地 + 偏移量，BizTalk Server 将日期时间格式转换为偏移量加本地时间而得出的 UTC 格式。 如果日期时间格式没有指定时区或 UTC 格式，时间被假定为本地和转换为 UTC 基于当前时区。  
  
## <a name="see-also"></a>请参阅  
 [XML 拆装器管道组件](../core/xml-disassembler-pipeline-component.md)   
 [如何配置 XML 拆装器管道组件](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)