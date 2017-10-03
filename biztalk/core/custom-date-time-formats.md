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
# <a name="custom-date-time-formats"></a><span data-ttu-id="33b88-102">自定义日期时间格式</span><span class="sxs-lookup"><span data-stu-id="33b88-102">Custom Date-Time Formats</span></span>

## <a name="overview"></a><span data-ttu-id="33b88-103">概述</span><span class="sxs-lookup"><span data-stu-id="33b88-103">Overview</span></span>
<span data-ttu-id="33b88-104">由于历史原因，对于为其创建平面文件架构的平面文件格式，其绑定使用的日期和时间格式不符合 ISO 8601 格式。</span><span class="sxs-lookup"><span data-stu-id="33b88-104">Due to their legacy origins, the flat file formats for which you create flat file schemas are bound to use date and time formats that do not conform to ISO 8601 formats.</span></span> <span data-ttu-id="33b88-105">因此，当你要创建平面文件架构，并且你设置**数据类型**属性**Field 元素**或**字段特性**节点为 XML 架构定义 （之一XSD) 语言基元数据类型， **xs: datetime**， **xs: time**，或**xs: date**，你可以使用**自定义日期/时间格式**属性来指定备用格式的日期或时间值。</span><span class="sxs-lookup"><span data-stu-id="33b88-105">Therefore, when you are creating a flat file schema and you set the **Data Type** property of a **Field Element** or **Field Attribute** node to one of the XML Schema definition (XSD) language primitive data types, **xs:dateTime**, **xs:time**, or **xs:date**, you can use the **Custom Date/Time Format** property to specify an alternative format for date or time values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="33b88-106">存储在消息框中将截断中的时间值**xs: datetime**和**xs: time**毫秒级别的元素。</span><span class="sxs-lookup"><span data-stu-id="33b88-106">Storage in the message box truncates time values in **xs:dateTime** and **xs:time** elements below the millisecond level.</span></span> <span data-ttu-id="33b88-107">在转换到 .NET 日期/时间数据类型时，会出现类似的精度损失。</span><span class="sxs-lookup"><span data-stu-id="33b88-107">A similar loss of precision may occur when converting to .NET date/time data types.</span></span>  
  
 <span data-ttu-id="33b88-108">当平面文件反汇编程序转换为其等效的 XML 的此类字段时，设置值的格式的**自定义日期/时间格式**属性将用于允许要转换为符合其 ISO 8601 的平面文件日期/时间格式等效。</span><span class="sxs-lookup"><span data-stu-id="33b88-108">When the flat file disassembler translates such a field to its equivalent XML format, the value of the **Custom Date/Time Format** property will be used to allow the flat file date/time format to be converted to its ISO 8601 compliant equivalent.</span></span> <span data-ttu-id="33b88-109">同样，当平面文件汇编器转换为其等效的平面文件的 ISO 8601 符合日期/时间值的格式字符串中指定的**自定义日期/时间格式**将使用属性构造相应的日期 /平面文件中的预期的时间格式。</span><span class="sxs-lookup"><span data-stu-id="33b88-109">Likewise, when the flat file assembler translates an ISO 8601 compliant date/time value to its flat file equivalent, the format string specified in the **Custom Date/Time Format** property will be used construct the appropriate date/time format expected in the flat file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="33b88-110">默认情况下,对应于 XSD 日期和时间数据类型（其中有多个值）的值必须符合 ISO 8601 格式。</span><span class="sxs-lookup"><span data-stu-id="33b88-110">By default, values that correspond to XSD date and time data types, of which there are several, must conform to ISO 8601 formats.</span></span> <span data-ttu-id="33b88-111">简单地说，将日期表示为**YYYY-月-日**和小时表示为**hh: mm:**使用 24 小时表示法。</span><span class="sxs-lookup"><span data-stu-id="33b88-111">In brief, dates are expressed as **YYYY-MM-DD** and hours are expressed as **hh:mm:ss** using 24-hour notation.</span></span> <span data-ttu-id="33b88-112">当它们发生在一起时，由"T"字符分隔日期和时间值： **YYYY:MM:DDThh:mm:ss**。</span><span class="sxs-lookup"><span data-stu-id="33b88-112">When they occur together, date and time values are separated by the "T" character: **YYYY:MM:DDThh:mm:ss**.</span></span>  
  
 <span data-ttu-id="33b88-113">你可以配置**自定义日期/时间格式**具有几乎任何时间和日期的格式，除了儒略历日期属性。</span><span class="sxs-lookup"><span data-stu-id="33b88-113">You can configure the **Custom Date/Time Format** property with almost any time and date format, except for Julian dates.</span></span> <span data-ttu-id="33b88-114">下拉列表提供了各种选项，但您也可以键入所选择的其他格式。</span><span class="sxs-lookup"><span data-stu-id="33b88-114">The drop-down list provides various choices, but you can also type a different format of your choosing.</span></span> <span data-ttu-id="33b88-115">日期和时间格式使用公共语言运行时 (CLR) **DateTime**设施。</span><span class="sxs-lookup"><span data-stu-id="33b88-115">The date and time formats use the Common Language Runtime (CLR) **DateTime** facilities.</span></span> <span data-ttu-id="33b88-116">但会自动在单字符 d、m、或 M 前面预置百分号 (%)，以生成相应的 DateTime 值的单个元素。</span><span class="sxs-lookup"><span data-stu-id="33b88-116">The exception is that a single character d, m, or M is automatically prepended with a percent sign (%) to yield the corresponding single element of the DateTime value.</span></span> <span data-ttu-id="33b88-117">自定义日期/时间格式允许使用的分隔符包括短划线 (-)、斜杠 (/) 和句点 (.)。</span><span class="sxs-lookup"><span data-stu-id="33b88-117">The allowable separators for custom date/time formats are dash (-), slash (/), and period (.).</span></span> <span data-ttu-id="33b88-118">有关详细信息**DateTime**格式，Visual Studio 文档集合中搜索"DateTimeFormatInfo"。</span><span class="sxs-lookup"><span data-stu-id="33b88-118">For more information about **DateTime** formats, search on "DateTimeFormatInfo" in the Visual Studio document collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33b88-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="33b88-119">See Also</span></span>  
-  [<span data-ttu-id="33b88-120">字段注意事项</span><span class="sxs-lookup"><span data-stu-id="33b88-120">Field Considerations</span></span>](../core/field-considerations.md)   
-  <span data-ttu-id="33b88-121">**数据类型 （节点属性的所有架构的）**和**自定义日期-时间格式 （平面文件架构的节点属性）**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="33b88-121">**Data Type (Node Property of All Schemas)** and **Custom Date-Time Format (Node Property of Flat File Schemas)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>