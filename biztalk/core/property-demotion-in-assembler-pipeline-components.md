---
title: "汇编程序管道组件中的属性降级 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML Assembler [pipeline component], properties
- pipeline components, properties
- BizTalk Framework Assembler [pipeline component], properties
- XML Assembler [pipeline component], about XML Assembler
- Flat File Assembler [pipeline component], properties
ms.assetid: c5275638-d594-4b0d-a818-b7a9460b41a6
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af634d302f01b18c91ebdbb7533673e8b9c545c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="property-demotion-in-assembler-pipeline-components"></a>汇编程序管道组件中的属性降级
您可以使用属性降级将属性值从消息上下文复制到消息内容中，或复制到该消息的头部或尾部。 通过使用文档中指定的 XPath 表达式，或头部和尾部架构中指定的 XPath 表达式可以完成属性降级。  
  
 在将日期时间数据从上下文属性写入最终文档时，BizTalk Server 假定所有日期时间数据均采用 UTC 格式。  
  
 用于将属性写入数据的格式由下表中显示的 XSD 数据类型确定：  
  
|数据类型|格式|  
|---------------|------------|  
|xs:datetime|yyyy-MM-ddTHH:mm:ss.fffffffZ|  
|xs:date|yyyy-MM-ddZ|  
|xs:gDay|---ddZ|  
|xs:gMonth|--MM—Z|  
|xs:gMonthDay|--MM-ddZ|  
|xs:gYear|yyyyZ|  
|xs:gYearMonth|yyyy-MMZ|  
|xs:time|HH:mm:ss.fffffffZ|  
  
## <a name="property-demotion-and-envelopes"></a>属性降级和信封  
 在信封中组装文件时，经常需要从一个或多个系统命名空间中，或自己的一个命名空间中降级值。 一些常见情形包括：  
  
-   希望在出站消息中包含提交给系统的原始文件名称，以便后端系统可以跟踪数据的起源。  
  
-   希望将数据从正文消息写入到标题中。 例如，对于采购订单，可能需要将“发送到”的名称写到下游系统的信封中。  
  
-   希望将许多不同的字段合并到标题中，而无需编写自定义代码。 Xml 组装器或平面文件组装器中的属性降级就可以实现这一点。  
  
 需要特别记住的是，XML 组装器组件和 平面文件组装器组件都可以指定用于信封和文档正文的架构。 您可以选择在拆卸中使用相同的架构，也可以创建带有不同的字段的新信封架构。  
  
 有关这些概念的示例，请参阅[EnvelopeProcessing （BizTalk Server 示例）](../core/envelopeprocessing-biztalk-server-sample.md)。  
  
## <a name="see-also"></a>另请参阅  
 [平面文件汇编管道组件](../core/flat-file-assembler-pipeline-component.md)   
 [如何配置平面文件汇编管道组件](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md)