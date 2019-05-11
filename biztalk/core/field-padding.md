---
title: 字段填充 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 47017036-7d64-4222-b574-d2913bf69358
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4eac7354d7e867ceca759caa40098ef09ed2a2d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388151"
---
# <a name="field-padding"></a><span data-ttu-id="07e36-102">字段填充</span><span class="sxs-lookup"><span data-stu-id="07e36-102">Field Padding</span></span>

## <a name="overview"></a><span data-ttu-id="07e36-103">概述</span><span class="sxs-lookup"><span data-stu-id="07e36-103">Overview</span></span>

<span data-ttu-id="07e36-104">填充字符分隔和位置记录中的字段中使用的字符或该字段为保留的字节数小于字段中包含的数据。</span><span class="sxs-lookup"><span data-stu-id="07e36-104">Pad characters are used in fields within both delimited and positional records when the data contained within the field smaller than the number of characters or bytes reserved for the field.</span></span> <span data-ttu-id="07e36-105">如果有，这些字符将占用的数据，不需要的字段的部分。</span><span class="sxs-lookup"><span data-stu-id="07e36-105">These characters occupy the portion of the field not required by the data, if any.</span></span> <span data-ttu-id="07e36-106">填充字符指定字段的字段使用**填充字符**并**填充字符类型**属性的相应**字段元素**和**字段属性**节点。</span><span class="sxs-lookup"><span data-stu-id="07e36-106">Pad characters are specified on a field-by-field basis using the  **Pad Character** and **Pad Character Type** properties of the corresponding **Field Element** and **Field Attribute** nodes.</span></span> <span data-ttu-id="07e36-107">如果没有填充字符指定为特定字段，默认填充字符： 空格 ("")，用于表示该字段。</span><span class="sxs-lookup"><span data-stu-id="07e36-107">If no pad character is specified for a particular field, the default pad character, space (" "), is used for that field.</span></span>  
  
## <a name="inbound-instances"></a><span data-ttu-id="07e36-108">入站的实例</span><span class="sxs-lookup"><span data-stu-id="07e36-108">Inbound instances</span></span>
 <span data-ttu-id="07e36-109">对于入站的实例消息，而不管特定记录是位置或分隔，平面文件拆装器将放弃前导空格或尾随为指定的实例或默认填充字符的特定字段，因为在实例消息转换为其等效 XML 形式。</span><span class="sxs-lookup"><span data-stu-id="07e36-109">For inbound instance messages, regardless of whether a particular record is positional or delimited, the flat file disassembler discards leading or trailing instances for the specified or default pad character for a particular field as the instance message is translated into its equivalent XML form.</span></span> <span data-ttu-id="07e36-110">无论它是前导空格或尾随的相关的填充字符将被丢弃的实例取决于是否**理由**属性的相应**Field 元素**和**字段特性**节点设置为**右**或**左侧**分别。</span><span class="sxs-lookup"><span data-stu-id="07e36-110">Whether it is leading or trailing instances of the relevant pad character that are discarded depends on whether the **Justification** property of corresponding **Field Element** and **Field Attribute** node is set to **Right** or **Left**, respectively.</span></span>  

## <a name="outbound-instances"></a><span data-ttu-id="07e36-111">出站实例</span><span class="sxs-lookup"><span data-stu-id="07e36-111">Outbound instances</span></span>  
 <span data-ttu-id="07e36-112">对于出站实例消息，平面文件组装器会插入适当数量的指定或默认填充字符字段，以便该字段的长度正确。</span><span class="sxs-lookup"><span data-stu-id="07e36-112">For outbound instance messages, the flat file assembler will insert the appropriate number of the specified or default pad character into fields so that the length of the field is correct.</span></span> <span data-ttu-id="07e36-113">将插入填充字符之前或之后的数据字符基于是否**理由**属性的相应**Field 元素**和**字段属性**节点设置为**右**或**左侧**分别。</span><span class="sxs-lookup"><span data-stu-id="07e36-113">The pad characters will be inserted before or after the data characters based on whether the **Justification** property of the corresponding **Field Element** and **Field Attribute** node is set to **Right** or **Left**, respectively.</span></span>  
  
 <span data-ttu-id="07e36-114">当要填充的出站实例消息中的字段包含在位置记录**位置偏移量**并**位置长度**的相应属性**字段元素**或**字段属性**节点，结合的数据字段必须包含的字符数确定是否所有填充字符都是必需的以及如果是这样，多少。</span><span class="sxs-lookup"><span data-stu-id="07e36-114">When the field to be padded in an outbound instance message is contained within a positional record, the **Positional Offset** and **Positional Length** properties of the corresponding **Field Element** or **Field Attribute** node, combined with the number of data characters that the field must contain, determine whether any pad characters are required, and if so, how many.</span></span> <span data-ttu-id="07e36-115">要填充的出站实例消息中的字段包含在分隔记录中，填充字符时，仅插入时的值**填充字符的最小长度**的相应属性**字段元素**或**字段属性**节点超过数据字符数。</span><span class="sxs-lookup"><span data-stu-id="07e36-115">When the field to be padded in an outbound instance message is contained within a delimited record, pad characters are only inserted when the value of the **Minimum Length with Pad Character** property of the corresponding **Field Element** or **Field Attribute** node exceeds the number of data characters.</span></span>  

## 
<span data-ttu-id="07e36-116">这些属性的更多详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="07e36-116">More details on these properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>

## <a name="see-also"></a><span data-ttu-id="07e36-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="07e36-117">See Also</span></span>  
 <span data-ttu-id="07e36-118">[字段注意事项](../core/field-considerations.md) </span><span class="sxs-lookup"><span data-stu-id="07e36-118">[Field Considerations](../core/field-considerations.md) </span></span>  
 <span data-ttu-id="07e36-119">[字段对齐](../core/field-justification.md) </span><span class="sxs-lookup"><span data-stu-id="07e36-119">[Field Justification](../core/field-justification.md) </span></span>  
 [<span data-ttu-id="07e36-120">位置记录中的字段位置规范</span><span class="sxs-lookup"><span data-stu-id="07e36-120">Specification of Field Positions within Positional Records</span></span>](../core/specification-of-field-positions-within-positional-records.md)  