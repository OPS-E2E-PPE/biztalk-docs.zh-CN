---
title: 带有位置记录的平面文件消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 72c17c25-3847-458e-a43e-0dbdc42db749
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3b780953c9a1f2c538b63f47942eae5f4ce60df
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345320"
---
# <a name="flat-file-messages-with-positional-records"></a><span data-ttu-id="c316c-102">带有位置记录的平面文件消息</span><span class="sxs-lookup"><span data-stu-id="c316c-102">Flat File Messages with Positional Records</span></span>
<span data-ttu-id="c316c-103">位置记录在平面文件实例消息中的包含的各个字段 （数据项），每个预定义长度。</span><span class="sxs-lookup"><span data-stu-id="c316c-103">Positional records within a flat file instance message contain individual fields (items of data) that are each of a predefined length.</span></span> <span data-ttu-id="c316c-104">根据这些长度，对字段进行解析。</span><span class="sxs-lookup"><span data-stu-id="c316c-104">The fields are parsed according to these lengths.</span></span> <span data-ttu-id="c316c-105">例如，考虑平面文件实例消息，其中包含发货地址 （第一行显示为每个字段保留的字符数） 中的以下位置记录。</span><span class="sxs-lookup"><span data-stu-id="c316c-105">For example, consider the following positional record from a flat file instance message, which contains a ship to address (the first line shows the number of characters reserved for each field).</span></span>  
  
```  
123456789012345678901234567890123456789012345678901234567890123456789012345  
US        Alice Smith         123 Maple Street    Mill Valley    CA 90952  
```  
  
 <span data-ttu-id="c316c-106">此记录在平面文件架构中的合理定义可描述为位置记录名为 shipTo 包含以下字段：</span><span class="sxs-lookup"><span data-stu-id="c316c-106">A reasonable definition for this record in a flat file schema can be described as a positional record named shipTo that contains the following fields:</span></span>  
  
- <span data-ttu-id="c316c-107">名为的属性，它是左对齐，国家/地区的长度，具有零个字符的偏移量的 10 个字符。</span><span class="sxs-lookup"><span data-stu-id="c316c-107">An attribute named country/region that is left-aligned, 10 characters in length, with a zero character offset.</span></span>  
  
- <span data-ttu-id="c316c-108">名为名称为左对齐的元素，长度为 20 个字符的零个字符的偏移量。</span><span class="sxs-lookup"><span data-stu-id="c316c-108">An element named name that is left-aligned, 20 characters in length, with a zero character offset.</span></span>  
  
- <span data-ttu-id="c316c-109">名为街道是左对齐的元素，长度为 20 个字符的零个字符的偏移量。</span><span class="sxs-lookup"><span data-stu-id="c316c-109">An element named street that is left-aligned, 20 characters in length, with a zero character offset.</span></span>  
  
- <span data-ttu-id="c316c-110">名为 city，它是左对齐的元素，偏移量为 15 个字符长度，以零个字符。</span><span class="sxs-lookup"><span data-stu-id="c316c-110">An element named city that is left-aligned, 15 characters in length, with a zero character offset.</span></span>  
  
- <span data-ttu-id="c316c-111">名为状态，它是左对齐的元素，2 个字符的长度，零字符偏移量。</span><span class="sxs-lookup"><span data-stu-id="c316c-111">An element named state that is left-aligned, 2 characters in length, with a zero character offset.</span></span>  
  
- <span data-ttu-id="c316c-112">名为 zip，它是左对齐的元素，5 个字符的长度，一个字符偏移量。</span><span class="sxs-lookup"><span data-stu-id="c316c-112">An element named zip that is left-aligned, 5 characters in length, with a one character offset.</span></span>  
  
  <span data-ttu-id="c316c-113">给定这些记录和字段定义后，平面文件拆装器将生成此记录的以下 XML 等效项。</span><span class="sxs-lookup"><span data-stu-id="c316c-113">Given these record and field definitions, the flat file disassembler will produce the following XML equivalent of this record.</span></span>  
  
```  
<shipTo country/region="US">  
    <name>Alice Smith</name>  
    <street>123 Maple Street</street>  
    <city>Mill Valley</city>  
    <state>CA</state>  
    <zip>90952</zip>  
</shipTo>  
  
```  
  
 <span data-ttu-id="c316c-114">有数个会影响接收和发送时，构造时记录的分析方式的位置记录相关的注意事项包括：</span><span class="sxs-lookup"><span data-stu-id="c316c-114">There are a number of considerations related to positional records that will affect how the record is parsed when received and constructed when sent, including:</span></span>  
  
- <span data-ttu-id="c316c-115">用来填充名为的填充字符的每个字段的未使用的部分的字符。</span><span class="sxs-lookup"><span data-stu-id="c316c-115">The character used to fill the unused portion of each field, known as the pad character.</span></span> <span data-ttu-id="c316c-116">有关详细信息，请参阅[字段填充](../core/field-padding.md)。</span><span class="sxs-lookup"><span data-stu-id="c316c-116">For more information, see [Field Padding](../core/field-padding.md).</span></span>  
  
- <span data-ttu-id="c316c-117">记录中的可选标记用于将记录与其他相似的记录区分开来。</span><span class="sxs-lookup"><span data-stu-id="c316c-117">An optional tag within the record, used to distinguish the record from other similar records.</span></span> <span data-ttu-id="c316c-118">标记通常出现在的记录，但是允许任意位置的开头。</span><span class="sxs-lookup"><span data-stu-id="c316c-118">Tags usually occur at the beginning of the record but allowable anywhere within it.</span></span> <span data-ttu-id="c316c-119">有关详细信息，请参阅[位置记录中的标记处理](../core/tag-handling-in-positional-records.md)。</span><span class="sxs-lookup"><span data-stu-id="c316c-119">For more information, see [Tag Handling in Positional Records](../core/tag-handling-in-positional-records.md).</span></span> <span data-ttu-id="c316c-120">位置记录可以定义为具有或不具有标记，但定义后，该标记必须存在与否，基于所定义。</span><span class="sxs-lookup"><span data-stu-id="c316c-120">Positional records can be defined to have a tag or not have a tag, but once defined, the tag must be present or not, based on the definition.</span></span>  
  
- <span data-ttu-id="c316c-121">在固定的长度字段，相对于伴随填充字符中的数据的对齐方式。</span><span class="sxs-lookup"><span data-stu-id="c316c-121">How data is justified within a fixed length field, relative to the accompanying pad characters.</span></span> <span data-ttu-id="c316c-122">有关详细信息，请参阅[字段对齐](../core/field-justification.md)。</span><span class="sxs-lookup"><span data-stu-id="c316c-122">For more information, see [Field Justification](../core/field-justification.md).</span></span>  
  
- <span data-ttu-id="c316c-123">位置记录嵌套在其他位置或分隔记录。</span><span class="sxs-lookup"><span data-stu-id="c316c-123">Positional records nested within other positional or delimited records.</span></span> <span data-ttu-id="c316c-124">有关详细信息，请参阅[嵌套位置记录](../core/nested-positional-records.md)。</span><span class="sxs-lookup"><span data-stu-id="c316c-124">For more information, see [Nested Positional Records](../core/nested-positional-records.md).</span></span>  
  
- <span data-ttu-id="c316c-125">字段长度指定为特定的字节数，而不是特定数目的字符的位置记录。</span><span class="sxs-lookup"><span data-stu-id="c316c-125">Positional records with field lengths specified as a specific number of bytes rather than a specific number of characters.</span></span> <span data-ttu-id="c316c-126">有关详细信息，请参阅[以字节为单位为单位计算位置](../core/position-counting-in-bytes.md)。</span><span class="sxs-lookup"><span data-stu-id="c316c-126">For more information, see [Position Counting in Bytes](../core/position-counting-in-bytes.md).</span></span>  
  
  <span data-ttu-id="c316c-127">若要帮助您更好地理解如何处理位置平面文件，请参阅位于 \Program Files\Microsoft BizTalk Server\SDK\Samples\Pipelines\AssemblerDisassembler 的 FlatFileReceive 和 FlatFileSend 文件夹中的示例\\。</span><span class="sxs-lookup"><span data-stu-id="c316c-127">To help you better understand how to work with positional flat files, see the samples in the FlatFileReceive and FlatFileSend folders located at \Program Files\Microsoft BizTalk Server\SDK\Samples\Pipelines\AssemblerDisassembler\\.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c316c-128">如果平面文件中包含分隔和位置记录，则必须设置**结构**属性的根节点**带分隔符**并**结构**属性从属记录节点**带分隔符**或**位置**根据需要。</span><span class="sxs-lookup"><span data-stu-id="c316c-128">If your flat file contains both delimited and positional records, you must set the **Structure** property of the root node to **Delimited** and the **Structure** property of subordinate record nodes to either **Delimited** or **Positional** as appropriate.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c316c-129">位置记录中的字段具有最多包含 50000000 个字符的限制。</span><span class="sxs-lookup"><span data-stu-id="c316c-129">Fields in positional records have a limit of 50000000 characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c316c-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="c316c-130">See Also</span></span>  
 <span data-ttu-id="c316c-131">[平面文件消息的结构](../core/structure-of-a-flat-file-message.md) </span><span class="sxs-lookup"><span data-stu-id="c316c-131">[Structure of a Flat File Message](../core/structure-of-a-flat-file-message.md) </span></span>  
 [<span data-ttu-id="c316c-132">如何为平面文件消息创建架构</span><span class="sxs-lookup"><span data-stu-id="c316c-132">How to Create Schemas for Flat File Messages</span></span>](../core/how-to-create-schemas-for-flat-file-messages.md)