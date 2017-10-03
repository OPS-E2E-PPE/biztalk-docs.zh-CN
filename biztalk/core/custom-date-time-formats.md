---
title: "自定义日期时间格式 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b5efbec4-3138-44d7-bc76-f9c21547e1d5
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1496f1f506df06a4d5569c065cba3bf4f8cbdad
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="custom-date-time-formats"></a>自定义日期时间格式

## <a name="overview"></a>概述
由于历史原因，对于为其创建平面文件架构的平面文件格式，其绑定使用的日期和时间格式不符合 ISO 8601 格式。 因此，当你要创建平面文件架构，并且你设置**数据类型**属性**Field 元素**或**字段特性**节点为 XML 架构定义 （之一XSD) 语言基元数据类型， **xs: datetime**， **xs: time**，或**xs: date**，你可以使用**自定义日期/时间格式**属性来指定备用格式的日期或时间值。  
  
> [!NOTE]
>  存储在消息框中将截断中的时间值**xs: datetime**和**xs: time**毫秒级别的元素。 在转换到 .NET 日期/时间数据类型时，会出现类似的精度损失。  
  
 当平面文件反汇编程序转换为其等效的 XML 的此类字段时，设置值的格式的**自定义日期/时间格式**属性将用于允许要转换为符合其 ISO 8601 的平面文件日期/时间格式等效。 同样，当平面文件汇编器转换为其等效的平面文件的 ISO 8601 符合日期/时间值的格式字符串中指定的**自定义日期/时间格式**将使用属性构造相应的日期 /平面文件中的预期的时间格式。  
  
> [!NOTE]
>  默认情况下,对应于 XSD 日期和时间数据类型（其中有多个值）的值必须符合 ISO 8601 格式。 简单地说，将日期表示为**YYYY-月-日**和小时表示为**hh: mm:**使用 24 小时表示法。 当它们发生在一起时，由"T"字符分隔日期和时间值： **YYYY:MM:DDThh:mm:ss**。  
  
 你可以配置**自定义日期/时间格式**具有几乎任何时间和日期的格式，除了儒略历日期属性。 下拉列表提供了各种选项，但您也可以键入所选择的其他格式。 日期和时间格式使用公共语言运行时 (CLR) **DateTime**设施。 但会自动在单字符 d、m、或 M 前面预置百分号 (%)，以生成相应的 DateTime 值的单个元素。 自定义日期/时间格式允许使用的分隔符包括短划线 (-)、斜杠 (/) 和句点 (.)。 有关详细信息**DateTime**格式，Visual Studio 文档集合中搜索"DateTimeFormatInfo"。  
  
## <a name="see-also"></a>另请参阅  
-  [字段注意事项](../core/field-considerations.md)   
-  **数据类型 （节点属性的所有架构的）**和**自定义日期-时间格式 （平面文件架构的节点属性）**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]