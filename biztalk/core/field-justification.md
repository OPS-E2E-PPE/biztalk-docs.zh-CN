---
title: 字段对齐 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 04380208-9bfd-43cf-a279-104daea2b978
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f6ddea01774cdae6fb17c27212f2d53351fa072
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345566"
---
# <a name="field-justification"></a><span data-ttu-id="70b24-102">字段对齐</span><span class="sxs-lookup"><span data-stu-id="70b24-102">Field Justification</span></span>

## <a name="overview"></a><span data-ttu-id="70b24-103">概述</span><span class="sxs-lookup"><span data-stu-id="70b24-103">Overview</span></span>
<span data-ttu-id="70b24-104">字段对齐问题是否之前出现的字段中的数据字符 （左对齐） 还是之后 （右对齐） 任何伴随的填充字符。</span><span class="sxs-lookup"><span data-stu-id="70b24-104">Field justification concerns whether the data characters in a field occur before (left-aligned) or after (right-aligned) any accompanying pad characters.</span></span>  
  
 <span data-ttu-id="70b24-105">有时字段中包含的数据字符不需要的所有空间专用于该字段。</span><span class="sxs-lookup"><span data-stu-id="70b24-105">Sometimes the data characters contained within a field do not require all of the space dedicated to that field.</span></span> <span data-ttu-id="70b24-106">这是最常在位置记录，其中的字节数或专用于字段的字符数固定的则返回 true，由**位置长度**并**位置偏移量**属性。</span><span class="sxs-lookup"><span data-stu-id="70b24-106">This is true most frequently in positional records, where the number of bytes or characters dedicated to a field is fixed, as determined by the **Positional Length** and **Positional Offset** properties.</span></span> <span data-ttu-id="70b24-107">很常见的项的数据小于字段长度，以填充字符来填充字段的未使用部分此类方案中。</span><span class="sxs-lookup"><span data-stu-id="70b24-107">It is common in such scenarios that the item of data is smaller than the field length, with the unused portion of the field being filled with pad characters.</span></span>  
  
 <span data-ttu-id="70b24-108">此类填充也可能发生在分隔记录时的值**填充字符的最小长度**属性超过存储相关数据项所需的空间。</span><span class="sxs-lookup"><span data-stu-id="70b24-108">Such padding can also occur in delimited records when the value of the **Minimum Length with Pad Character** property exceeds the space required to store the relevant item of data.</span></span>  
  
 <span data-ttu-id="70b24-109">在这两个此类情况下，值**理由**属性 (**左侧**或**右**) 的相关**字段元素**或**字段属性**节点确定是否填充字符将后面 （左对齐） 的数据字符或是否填充字符将前面 （右对齐） 的数据字符。</span><span class="sxs-lookup"><span data-stu-id="70b24-109">In both such cases, the value of the **Justification** property (**Left** or **Right**) of the relevant **Field Element** or **Field Attribute** node determines whether the pad characters will follow the data characters (left-aligned) or whether the pad characters will precede the data characters (right-aligned).</span></span>  
  
 <span data-ttu-id="70b24-110">当平面文件拆装器将平面文件实例消息转换成等效的 XML 实例消息，**理由**属性解析相应的字段时使用。</span><span class="sxs-lookup"><span data-stu-id="70b24-110">When the flat file disassembler is converting a flat file instance message into an equivalent XML instance message, the **Justification** property is used when parsing the corresponding field.</span></span> <span data-ttu-id="70b24-111">当平面文件组装器将 XML 实例消息转换成等效的平面文件实例消息，**理由**属性用于确定当关联的填充字符与特定字段中，如果有的话，应添加到数据流： 之前或之后的相应数据字符。</span><span class="sxs-lookup"><span data-stu-id="70b24-111">When the flat file assembler is converting an XML instance message into an equivalent flat file instance message, the **Justification** property is used to determine when the pad characters associated with a particular field, if any, should be added to the data stream: either before or after the corresponding data characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70b24-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="70b24-112">See Also</span></span>  
- [<span data-ttu-id="70b24-113">字段注意事项</span><span class="sxs-lookup"><span data-stu-id="70b24-113">Field Considerations</span></span>](../core/field-considerations.md)   
- <span data-ttu-id="70b24-114">以下属性的详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:</span><span class="sxs-lookup"><span data-stu-id="70b24-114">More info on the following properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:</span></span>  
    - <span data-ttu-id="70b24-115">对齐 （平面文件架构的节点属性）</span><span class="sxs-lookup"><span data-stu-id="70b24-115">Justification (Node Property of Flat File Schemas)</span></span>  
    - <span data-ttu-id="70b24-116">位置偏移量 （平面文件架构的节点属性）</span><span class="sxs-lookup"><span data-stu-id="70b24-116">Positional Offset (Node Property of Flat File Schemas)</span></span>  
    - <span data-ttu-id="70b24-117">位置长度 （平面文件架构的节点属性）</span><span class="sxs-lookup"><span data-stu-id="70b24-117">Positional Length (Node Property of Flat File Schemas)</span></span>