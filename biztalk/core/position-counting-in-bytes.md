---
title: 以字节为单位计算位置 |Microsoft Docs
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
ms.openlocfilehash: 5801987517d66147a9c8110c945b8fdff84bc88b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396219"
---
# <a name="position-counting-in-bytes"></a><span data-ttu-id="2dc26-102">以字节为单位计算位置</span><span class="sxs-lookup"><span data-stu-id="2dc26-102">Position Counting in Bytes</span></span>

## <a name="overview"></a><span data-ttu-id="2dc26-103">概述</span><span class="sxs-lookup"><span data-stu-id="2dc26-103">Overview</span></span>

<span data-ttu-id="2dc26-104">可以使用**数**的属性**架构**节点：</span><span class="sxs-lookup"><span data-stu-id="2dc26-104">You can use the **Count Positions In Bytes** property of the **Schema** node to:</span></span> 

* <span data-ttu-id="2dc26-105">指定如何值为输入**位置长度**并**位置偏移量**解释位置记录内的各字段的属性</span><span class="sxs-lookup"><span data-stu-id="2dc26-105">Specify how the values you enter for the **Positional Length** and **Positional Offset** properties of the various fields within positional records are interpreted</span></span>
* <span data-ttu-id="2dc26-106">指定如何值为输入**标记偏移量**解释为位置记录本身的属性</span><span class="sxs-lookup"><span data-stu-id="2dc26-106">Specify how the values you enter for the **Tag Offset** property of the positional records themselves are interpreted</span></span>

<span data-ttu-id="2dc26-107">默认情况下，这些值被解释为字符数。</span><span class="sxs-lookup"><span data-stu-id="2dc26-107">By default, these values are interpreted as a number of characters.</span></span> <span data-ttu-id="2dc26-108">但当**数**属性设置为**True**，这些值被解释为字节数。</span><span class="sxs-lookup"><span data-stu-id="2dc26-108">But when the **Count Positions In Bytes** property is set to **True**, these values are interpreted as a number of bytes.</span></span>  
  
 <span data-ttu-id="2dc26-109">设置**数**属性设置为**True**可能需要处理多字节字符时设置 （MBCS 或 DBCS） 数据，或当平面文件消息源自 SAP、 大型机或其他系统，可能数以字节为单位的位置。</span><span class="sxs-lookup"><span data-stu-id="2dc26-109">Setting the **Count Positions In Bytes** property to **True** might be necessary when dealing with multibyte character set (MBCS or DBCS) data, or when your flat file messages originate in SAP, mainframes, or other systems that may count positions in bytes.</span></span>  
  
 <span data-ttu-id="2dc26-110">使用字符进行编码的字节数是变量，并可能会导致一些问题有关确定字段边界时，计算字段长度以字节为单位可能很复杂。</span><span class="sxs-lookup"><span data-stu-id="2dc26-110">Counting field lengths in bytes can be complicated when the number of bytes used to encode characters is variable, and can result in some issues with respect to determining field boundaries.</span></span> <span data-ttu-id="2dc26-111">当平面文件拆装器对平面文件中这种情况下时，它会尝试以使相应的解析决策基于自身使用的字符编码的了解。</span><span class="sxs-lookup"><span data-stu-id="2dc26-111">When the flat file disassembler parses a flat file in such situations, it attempts to make appropriate parsing decisions based on its knowledge of the character encoding in use.</span></span>  
  
 <span data-ttu-id="2dc26-112">此类型的解析决策示例涉及 MBCS 字符编码中的前导字节。</span><span class="sxs-lookup"><span data-stu-id="2dc26-112">An example of this type of parsing decision concerns lead bytes in MBCS character encodings.</span></span> <span data-ttu-id="2dc26-113">前导字节是已知字节值，用于开始的多字节字符编码和其应永远不会出现在其自己。</span><span class="sxs-lookup"><span data-stu-id="2dc26-113">Lead bytes are well-known byte values that are used to begin multibyte character encodings, and which should never occur on their own.</span></span> <span data-ttu-id="2dc26-114">指定使用字节而不是字符字段的长度时, 的情况下可能会出现在其中找到的字段中的最后一个字节是前导字节，不能构成完整字符本身。</span><span class="sxs-lookup"><span data-stu-id="2dc26-114">When specifying the length of the fields using bytes rather than character, situations may arise in which the last byte in a field is found to be a lead byte, which cannot constitute an entire character on its own.</span></span> <span data-ttu-id="2dc26-115">在这种情况下，平面文件拆装器将字符视为就在前导字节之前为前一个字段中的最后一个字符并开始分析下一个字段开头的前导字节。</span><span class="sxs-lookup"><span data-stu-id="2dc26-115">In such cases, the flat file disassembler will treat the character occurring just prior to the lead byte as the last character in the previous field, and begin parsing the next field starting with the lead byte.</span></span>  

<span data-ttu-id="2dc26-116">这些属性的更多详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="2dc26-116">More details on these properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2dc26-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="2dc26-117">See Also</span></span>  
 [<span data-ttu-id="2dc26-118">位置记录注意事项</span><span class="sxs-lookup"><span data-stu-id="2dc26-118">Positional Record Considerations</span></span>](../core/positional-record-considerations.md)   
