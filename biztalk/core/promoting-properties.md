---
title: 升级属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- properties, promoting
- promoting properties
- promoting properties, about promoting properties
ms.assetid: e1825028-7dd9-4eae-a383-4db12a83a402
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c8f10ba41a497a8595632947deaac31c5f48426
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398512"
---
# <a name="promoting-properties"></a>升级属性
升级属性涉及到任一提升**字段元素**或**字段属性**节点为架构中的**可分辨字段**或**属性字段**。 你还可以升级**记录**作为节点**属性字段**如果他们具有简单内容 (**内容类型**属性的**记录**节点设置为**SimpleContent**)。 本部分提供分步说明将为节点升级**可分辨字段**或是**属性字段**。  
  
 若要将提升**记录**（具有简单内容），**字段元素**，或**字段属性**节点作为**属性字段**，您可以首先定义特殊类型的架构名为属性架构。 属性架构定义的非结构化一组**Field 元素**升级到这些节点**记录**（具有简单内容），**字段元素**，或**字段属性**节点。 创建属性架构的分步说明，请参阅[如何创建属性架构](../core/how-to-create-property-schemas.md)。  
  
 或者，可以使用**快速升级**功能，它将自动创建和更新单个属性架构，只要您升级新**Field 元素**，**字段属性**，或**记录**（具有简单内容） 节点。  
  
> [!NOTE]
>  您可以将升级的字段为这两者**可分辨字段**和一个**属性字段**。  
  
> [!NOTE]
>  **快速升级**功能通过插入具有升级节点的名称的新属性来修改属性架构。  
  
> [!IMPORTANT]
>  不要移动或升级后重命名架构中的字段。 当您移动或重命名某一架构字段时，BizTalk 编辑器中不会更新定义升级字段的位置的 XPath。  
  
## <a name="xsd-and-clr-data-types"></a>XSD 和 CLR 数据类型  
 在某些位置，例如在属性升级中，XSD 数据类型被提升到公共语言运行时 (CLR) 数据类型。 下表显示了可以升级的 XSD 数据类型和相应的 CLR 数据类型。  
  
|XSD 数据类型|CLR 数据类型|  
|-------------------|-------------------|  
|anyURI|String|  
|Boolean|Boolean|  
|Byte|sbyte|  
|Date|DateTime|  
|dateTime|DateTime|  
|Decimal|Decimal|  
|双精度|双精度|  
|实体|String|  
|float|Single|  
|gDay|DateTime|  
|gMonth|DateTime|  
|gMonthDay|DateTime|  
|gYear|DateTime|  
|gYearMonth|DateTime|  
|ID|String|  
|IDREF|String|  
|smallint|Int32|  
|Integer|Decimal|  
|语言|String|  
|“属性”|String|  
|NCName|String|  
|negativeInteger|Decimal|  
|NMTOKEN|String|  
|nonNegativeInteger|Decimal|  
|nonPositiveInteger|Decimal|  
|normalizedString|String|  
|表示法|String|  
|positiveInteger|Decimal|  
|QName|String|  
|Short|Int16|  
|String|String|  
|Time|DateTime|  
|标记|String|  
|unsignedByte|Byte|  
|unsignedInt|UInt32|  
|unsignedShort|UInt16|  
  
> [!NOTE]
>  XSD 数据类型的 base64Binary，持续时间，实体导出，hexBinary，IDREFS，长时间，NMTOKENS 和 unsignedLong 不支持升级。  
  
## <a name="limitations-for-promoting-properties"></a>升级属性的限制  
 升级属性时，考虑以下方面：  
  
-   升级属性的长度限制在 256 个字符之内，而写入属性则没有长度上的限制。  
  
-   升级属性用于消息路由，并由于有关比较和存储效率的原因，对升级属性的大小有所限制。 尽管对写入属性的大小没有硬性限制，但如果在上下文中使用过大的值，也会对性能造成影响，因为这些值仍必须与消息一起进行处理和传递。 可分辨的字段是写入属性的示例。  
  
-   记录节点永远无法升级为**可分辨字段**。  
  
-   升级的属性仅限于非重复元素/属性。  
  
-   不要升级属于同一根节点的同一属性的字段。 此类升级会导致编译或部署错误。  
  
-   在消息上下文中，有一些属性，因为它们不升级不可用。  BTS。ReceiveLocationName 属性是一个此类属性。 如果可以将新属性架构或新的 BizTalk Server 项目添加到你的开发很有可能访问此属性从业务流程中。  
  
     属性值由属性目标命名空间和属性名称标识。  下面的示例演示如何访问代码中的接收位置。  
  
     `string receiveLocationName =       pInMsg.Context.Read("ReceiveLocationName", sysNamespace);`  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何打开升级属性对话框](../core/how-to-open-the-promote-properties-dialog-box.md)  
  
-   [如何将数据复制到消息上下文作为可分辨字段](../core/how-to-copy-data-to-the-message-context-as-distinguished-fields.md)  
  
-   [如何将数据复制到消息上下文为属性字段](../core/how-to-copy-data-to-the-message-context-as-property-fields.md)