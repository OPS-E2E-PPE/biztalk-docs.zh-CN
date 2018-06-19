---
title: 以字节为单位计数的位置 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5cf666ec-d15e-4d2d-9df9-49189f352c65
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3cdb7bbf1f0d6af04f0cc28ed1bdb7477b259de
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264029"
---
# <a name="position-counting-in-bytes"></a><span data-ttu-id="33053-102">以字节为单位计数的位置</span><span class="sxs-lookup"><span data-stu-id="33053-102">Position Counting in Bytes</span></span>

## <a name="overview"></a><span data-ttu-id="33053-103">概述</span><span class="sxs-lookup"><span data-stu-id="33053-103">Overview</span></span>

<span data-ttu-id="33053-104">你可以使用**计数位置中字节**属性**架构**节点：</span><span class="sxs-lookup"><span data-stu-id="33053-104">You can use the **Count Positions In Bytes** property of the **Schema** node to:</span></span> 

* <span data-ttu-id="33053-105">指定如何值你输入**位置长度**和**位置偏移量**解释的位置记录中的各个字段的属性</span><span class="sxs-lookup"><span data-stu-id="33053-105">Specify how the values you enter for the **Positional Length** and **Positional Offset** properties of the various fields within positional records are interpreted</span></span>
* <span data-ttu-id="33053-106">指定如何值你输入**标记偏移量**解释的位置记录本身的属性</span><span class="sxs-lookup"><span data-stu-id="33053-106">Specify how the values you enter for the **Tag Offset** property of the positional records themselves are interpreted</span></span>

<span data-ttu-id="33053-107">默认情况下，这些值被解释为字符数。</span><span class="sxs-lookup"><span data-stu-id="33053-107">By default, these values are interpreted as a number of characters.</span></span> <span data-ttu-id="33053-108">但当**计数位置中字节**属性设置为**True**，这些值都会被解释为字节数。</span><span class="sxs-lookup"><span data-stu-id="33053-108">But when the **Count Positions In Bytes** property is set to **True**, these values are interpreted as a number of bytes.</span></span>  
  
 <span data-ttu-id="33053-109">设置**计数位置中字节**属性**True**可能需要处理多字节字符时设置 （MBCS 或 DBCS） 的数据，或当平面文件消息源自 SAP，大型机，或其他可能计数以字节为单位的位置的系统。</span><span class="sxs-lookup"><span data-stu-id="33053-109">Setting the **Count Positions In Bytes** property to **True** might be necessary when dealing with multibyte character set (MBCS or DBCS) data, or when your flat file messages originate in SAP, mainframes, or other systems that may count positions in bytes.</span></span>  
  
 <span data-ttu-id="33053-110">当用于对字符进行编码的字节数是变量时，以字节为单位计算字段长度可能十分复杂，并可能引发有关确定字段边界的一些问题。</span><span class="sxs-lookup"><span data-stu-id="33053-110">Counting field lengths in bytes can be complicated when the number of bytes used to encode characters is variable, and can result in some issues with respect to determining field boundaries.</span></span> <span data-ttu-id="33053-111">在这种情况下,如果平面文件拆装器对平面文件进行解析，则它将尝试根据所使用的字符编码的相关知识，进行相应的解析决策。</span><span class="sxs-lookup"><span data-stu-id="33053-111">When the flat file disassembler parses a flat file in such situations, it attempts to make appropriate parsing decisions based on its knowledge of the character encoding in use.</span></span>  
  
 <span data-ttu-id="33053-112">此类型的解析决策示例涉及 MBCS 字符编码中的前导字节。</span><span class="sxs-lookup"><span data-stu-id="33053-112">An example of this type of parsing decision concerns lead bytes in MBCS character encodings.</span></span> <span data-ttu-id="33053-113">前导字节是已知字节值，用于开始对多字节字符编码并永远不会单独出现。</span><span class="sxs-lookup"><span data-stu-id="33053-113">Lead bytes are well-known byte values that are used to begin multibyte character encodings, and which should never occur on their own.</span></span> <span data-ttu-id="33053-114">在使用字节而非字符指定字段长度时，可能会出现以下情况：字段中最后的字节是前导字节，而前导字节本身不能构成完整字符。</span><span class="sxs-lookup"><span data-stu-id="33053-114">When specifying the length of the fields using bytes rather than character, situations may arise in which the last byte in a field is found to be a lead byte, which cannot constitute an entire character on its own.</span></span> <span data-ttu-id="33053-115">在这种情况下，平面文件拆装器将该前导字节的上一字符视为前一字段中的最后的字符，并从该前导字节开始解析下一字段。</span><span class="sxs-lookup"><span data-stu-id="33053-115">In such cases, the flat file disassembler will treat the character occurring just prior to the lead byte as the last character in the previous field, and begin parsing the next field starting with the lead byte.</span></span>  

<span data-ttu-id="33053-116">这些属性的更多详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="33053-116">More details on these properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="33053-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="33053-117">See Also</span></span>  
 [<span data-ttu-id="33053-118">位置记录注意事项</span><span class="sxs-lookup"><span data-stu-id="33053-118">Positional Record Considerations</span></span>](../core/positional-record-considerations.md)   
