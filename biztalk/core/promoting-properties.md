---
title: "提升属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- properties, promoting
- promoting properties
- promoting properties, about promoting properties
ms.assetid: e1825028-7dd9-4eae-a383-4db12a83a402
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc1c5ac3e6e9aeadccc4eaefcb1457821ef36a93
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="promoting-properties"></a>提升属性
属性的升级涉及任一提升**Field 元素**或**字段特性**架构是中的节点**可分辨字段**或**属性字段**。 你还可以升级**记录**节点**属性字段**如果它们具有简单内容 (**内容类型**属性**记录**节点设置为**SimpleContent**)。 本部分提供有关将提升为节点的分步说明**可分辨字段**或**属性字段**。  
  
 若要将提升**记录**（具有简单内容）， **Field 元素**，或**字段特性**节点作为**属性字段**，你可能会首先定义调用属性架构的架构的特殊类型。 属性架构定义一组非结构化的**Field 元素**你升级到其中的节点**记录**（具有简单内容）， **Field 元素**，或**字段特性**节点。 用于创建属性架构的分步说明，请参阅[如何创建属性架构](../core/how-to-create-property-schemas.md)。  
  
 或者，可以使用**快速升级**功能，因此将自动创建并更新单个属性架构，每当你升级新**Field 元素**，**字段特性**，或**记录**（具有简单内容） 节点。  
  
> [!NOTE]
>  你可以将提升为这两者的字段**可分辨字段**和**属性字段**。  
  
> [!NOTE]
>  **快速升级**功能属性架构修改的方法是插入具有提升的节点的名称的新属性。  
  
> [!IMPORTANT]
>  升级字段之后，请不要在架构中移动或重命名该字段。 如果您移动或重命名某一架构字段，BizTalk 编辑器并不会更新定义升级字段的位置的 XPath。  
  
## <a name="xsd-and-clr-data-types"></a>XSD 和 CLR 数据类型  
 在某些情况下（例如在属性升级中），XSD 数据类型将升级到公共语言运行时 (CLR) 数据类型。 下表显示了可升级的 XSD 数据类型以及相应的 CLR 数据类型。  
  
|XSD 数据类型|CLR 数据类型|  
|-------------------|-------------------|  
|anyURI|字符串|  
|Boolean|Boolean|  
|Byte|sbyte|  
|日期|DateTime|  
|dateTime|DateTime|  
|Decimal|Decimal|  
|双精度|双精度|  
|ENTITY|字符串|  
|Float|Single|  
|gDay|DateTime|  
|gMonth|DateTime|  
|gMonthDay|DateTime|  
|gYear|DateTime|  
|gYearMonth|DateTime|  
|ID|字符串|  
|IDREF|字符串|  
|int|Int32|  
|Integer|Decimal|  
|语言|字符串|  
|Name|字符串|  
|NCName|字符串|  
|negativeInteger|Decimal|  
|NMTOKEN|字符串|  
|nonNegativeInteger|Decimal|  
|nonPositiveInteger|Decimal|  
|normalizedString|字符串|  
|NOTATION|字符串|  
|positiveInteger|Decimal|  
|QName|字符串|  
|Short|Int16|  
|字符串|字符串|  
|Time|DateTime|  
|标记|字符串|  
|unsignedByte|Byte|  
|unsignedInt|UInt32|  
|unsignedShort|UInt16|  
  
> [!NOTE]
>  base64Binary、duration、ENTITES、hexBinary、IDREFS、long、NMTOKENS 和 unsignedLong 的 XSD 数据类型不支持升级。  
  
## <a name="limitations-for-promoting-properties"></a>对升级属性的限制  
 升级属性时，请考虑以下事项：  
  
-   升级属性的长度限制在 256 个字符之内，而写入属性则没有长度上的限制。  
  
-   升级属性用于消息路由，并由于有关比较和存储效率的原因，对升级属性的大小有所限制。 尽管对写入属性的大小没有硬性限制，但如果在上下文中使用过大的值，也会对性能造成影响，因为这些值仍必须与消息一起进行处理和传递。 可分辨字段便是写入属性的例子。  
  
-   记录节点永远不会被提升为**可分辨字段**。  
  
-   升级属性仅限于非重复元素/特性。  
  
-   不要将属于同一根节点的字段升级到相同属性。 此类升级会导致编译或部署错误。  
  
-   在消息上下文内，某些属性因为没有升级而不可用。  BTS.ReceiveLocationName 属性就是此类属性之一。 如果您可以将新属性架构或新 BizTalk Server 对象添加到您的开发中，则有可能从业务流程内部访问该属性。  
  
     属性值由属性目标命名空间和属性名称标识。  下面的示例演示如何访问代码格式的接收位置。  
  
     `string receiveLocationName =       pInMsg.Context.Read("ReceiveLocationName", sysNamespace);`  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何打开提升属性对话框中](../core/how-to-open-the-promote-properties-dialog-box.md)  
  
-   [如何将数据复制到可分辨的字段的消息上下文](../core/how-to-copy-data-to-the-message-context-as-distinguished-fields.md)  
  
-   [如何将数据复制到作为属性字段的消息上下文](../core/how-to-copy-data-to-the-message-context-as-property-fields.md)