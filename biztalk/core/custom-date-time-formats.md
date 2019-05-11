---
title: 自定义日期时间格式 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b5efbec4-3138-44d7-bc76-f9c21547e1d5
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e1c456170170859ffd81d0963b85fb6db60f955
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353369"
---
# <a name="custom-date-time-formats"></a>自定义日期时间格式

## <a name="overview"></a>概述
由于它们旧的源，而绑定为其创建平面文件架构的平面文件格式使用的不符合 ISO 8601 格式的日期和时间格式。 因此，如果要创建的平面文件架构，而您设置**数据类型**的属性**Field 元素**或**字段属性**到一个 XML 架构定义 （节点XSD) 语言基元数据类型， **xs: datetime**， **xs: time**，或**xs: date**，可以使用**自定义日期/时间格式**属性来指定日期或时间值的替代格式。  

> [!NOTE]
>  消息框中的存储将截断时间值中的**xs: datetime**并**xs: time**到毫秒级以下元素。 将转换为.NET 日期/时间数据类型时，可能会发生类似的精度损失。  

 当平面文件拆装器转换为其等效 XML 的此类字段时，值的格式设置**自定义日期/时间格式**属性将用于允许要转换为符合其 ISO 8601 的平面文件日期/时间格式等效。 同样，当平面文件组装器将转换为其等效的平面文件的 ISO 8601 符合日期/时间值，格式字符串中指定**自定义日期/时间格式**属性将用于构造相应的日期 /平面文件中所需的时间格式。  

> [!NOTE]
>  默认情况下，对应于 XSD 日期和时间数据类型，其中有多个的值必须符合 ISO 8601 格式。 简单地说，日期表示为**年-月-日**，小时表示为**hh: mm:** 使用 24 小时表示法。 当它们一起出现时，日期和时间值以分隔字符"T":**YYYY:MM:DDThh:mm:ss**。  

 你可以配置**自定义日期/时间格式**使用几乎任何时间和日期的格式，除了 Julian 日期属性。 下拉列表提供了各种选项，但您还可以键入所选的不同的格式。 日期和时间格式使用公共语言运行时 (CLR) **DateTime**设施。 例外情况是，单字符 d、 m 自动前面带有百分号 （%）若要生成的日期时间值相应的单一元素。 自定义日期/时间格式允许使用的分隔符是短划线 （-）、 斜杠 （/） 和句点 （.）。 有关详细信息**DateTime**格式，在 Visual Studio 文档集合中搜索的"DateTimeFormatInfo"。  

## <a name="see-also"></a>请参阅  
- [字段注意事项](../core/field-considerations.md)   
- **数据类型 （所有架构的节点属性）** 和**自定义日期时间格式 （平面文件架构的节点属性）** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
