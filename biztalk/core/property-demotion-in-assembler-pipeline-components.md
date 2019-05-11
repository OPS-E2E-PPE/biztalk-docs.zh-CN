---
title: 组装器管道组件中的属性降级 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML Assembler [pipeline component], properties
- pipeline components, properties
- BizTalk Framework Assembler [pipeline component], properties
- XML Assembler [pipeline component], about XML Assembler
- Flat File Assembler [pipeline component], properties
ms.assetid: c5275638-d594-4b0d-a818-b7a9460b41a6
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b114d4a66b4fcb0139403fc22dcacc5c8ec1675
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398483"
---
# <a name="property-demotion-in-assembler-pipeline-components"></a>组装器管道组件中的属性降级
可以使用属性降级将属性值从消息上下文复制，传入消息内容或其标头或尾部。 通过使用在文档或标头和尾部架构中指定的 XPath 表达式完成属性降级。  
  
 当从上下文属性的日期时间数据写入到生成的文档，BizTalk Server 假定所有日期时间数据采用 UTC 格式。  
  
 用于将属性写入到数据格式由下表中所示的 XSD 数据类型决定。  
  
|数据类型|格式|  
|---------------|------------|  
|xs: datetime|yyyy-MM-ddTHH:mm:ss.fffffffZ|  
|xs:date|yyyy-MM-ddZ|  
|xs:gDay|---ddZ|  
|xs:gMonth|--MM—Z|  
|xs:gMonthDay|--MM-ddZ|  
|xs:gYear|yyyyZ|  
|xs:gYearMonth|yyyy-MMZ|  
|xs:time|HH:mm:ss.fffffffZ|  
  
## <a name="property-demotion-and-envelopes"></a>属性降级和信封  
 通常它可用于将值从一个或多个系统命名空间或某个你自己的命名空间-降级组装在信封中的文件时。 一些常见方案包括：  
  
- 你想要包括提交到出站消息中的系统，因此后端系统可以跟踪的数据的来源的原始文件名。  
  
- 你想要将数据从正文消息写入到的标头。 例如，对于采购订单可能有用飞船写入到信封的下游系统的名称。  
  
- 你想要将许多不同的字段合并到标头，而无需编写自定义代码。 Xml 组装器或平面文件组装器中的属性降级可以实现这一点。  
  
  请务必记住 XML 和平面文件组装器组件都允许您指定要用于信封和文档正文的架构。 可以选择在拆卸中使用相同的架构，也可以使用不同的字段创建新的信封架构。  
  
  有关这些概念的示例，请参阅[EnvelopeProcessing （BizTalk Server 示例）](../core/envelopeprocessing-biztalk-server-sample.md)。  
  
## <a name="see-also"></a>请参阅  
 [平面文件组装器管道组件](../core/flat-file-assembler-pipeline-component.md)   
 [如何配置平面文件组装器管道组件](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md)