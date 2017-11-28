---
title: "包含的位置记录的平面文件消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 72c17c25-3847-458e-a43e-0dbdc42db749
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26c9e4551abcbd0fba32b21fb8e4205bece6e82f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="flat-file-messages-with-positional-records"></a><span data-ttu-id="a4161-102">带有位置记录的平面文件消息</span><span class="sxs-lookup"><span data-stu-id="a4161-102">Flat File Messages with Positional Records</span></span>
<span data-ttu-id="a4161-103">平面文件实例消息中的位置记录包含的各个字段（数据项）都具有预定义长度。</span><span class="sxs-lookup"><span data-stu-id="a4161-103">Positional records within a flat file instance message contain individual fields (items of data) that are each of a predefined length.</span></span> <span data-ttu-id="a4161-104">根据这些长度对字段进行解析。</span><span class="sxs-lookup"><span data-stu-id="a4161-104">The fields are parsed according to these lengths.</span></span> <span data-ttu-id="a4161-105">例如，考虑平面文件实例消息中的以下位置记录，该记录包含发货地址（第一行显示了为每个字段保留的字符数）。</span><span class="sxs-lookup"><span data-stu-id="a4161-105">For example, consider the following positional record from a flat file instance message, which contains a ship to address (the first line shows the number of characters reserved for each field).</span></span>  
  
```  
123456789012345678901234567890123456789012345678901234567890123456789012345  
US        Alice Smith         123 Maple Street    Mill Valley    CA 90952  
```  
  
 <span data-ttu-id="a4161-106">此记录在平面文件架构中的合理定义可描述为名为“shipTo”的位置记录，其中包含以下字段：</span><span class="sxs-lookup"><span data-stu-id="a4161-106">A reasonable definition for this record in a flat file schema can be described as a positional record named shipTo that contains the following fields:</span></span>  
  
-   <span data-ttu-id="a4161-107">名为“country/region”的属性，它的对齐方式是左对齐，长度为 10 个字符，字符偏移量为零。</span><span class="sxs-lookup"><span data-stu-id="a4161-107">An attribute named country/region that is left-aligned, 10 characters in length, with a zero character offset.</span></span>  
  
-   <span data-ttu-id="a4161-108">名为“name”的元素，它的对齐方式是左对齐，长度为 20 个字符，字符偏移量为零。</span><span class="sxs-lookup"><span data-stu-id="a4161-108">An element named name that is left-aligned, 20 characters in length, with a zero character offset.</span></span>  
  
-   <span data-ttu-id="a4161-109">名为“street”的元素，它的对齐方式是左对齐，长度为 20 个字符，字符偏移量为零。</span><span class="sxs-lookup"><span data-stu-id="a4161-109">An element named street that is left-aligned, 20 characters in length, with a zero character offset.</span></span>  
  
-   <span data-ttu-id="a4161-110">名为“city”的元素，它的对齐方式是左对齐，长度为 15 个字符，字符偏移量为零。</span><span class="sxs-lookup"><span data-stu-id="a4161-110">An element named city that is left-aligned, 15 characters in length, with a zero character offset.</span></span>  
  
-   <span data-ttu-id="a4161-111">名为“state”的元素，它的对齐方式是左对齐，长度为 2 个字符，字符偏移量为零。</span><span class="sxs-lookup"><span data-stu-id="a4161-111">An element named state that is left-aligned, 2 characters in length, with a zero character offset.</span></span>  
  
-   <span data-ttu-id="a4161-112">名为“zip”的元素，它的对齐方式是左对齐，长度为 5 个字符，字符偏移量为一。</span><span class="sxs-lookup"><span data-stu-id="a4161-112">An element named zip that is left-aligned, 5 characters in length, with a one character offset.</span></span>  
  
 <span data-ttu-id="a4161-113">给定这些记录和字段定义后，平面文件拆分器将生成此记录的 XML 等效项，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a4161-113">Given these record and field definitions, the flat file disassembler will produce the following XML equivalent of this record.</span></span>  
  
```  
<shipTo country/region="US">  
    <name>Alice Smith</name>  
    <street>123 Maple Street</street>  
    <city>Mill Valley</city>  
    <state>CA</state>  
    <zip>90952</zip>  
</shipTo>  
  
```  
  
 <span data-ttu-id="a4161-114">有一些与位置记录有关的注意事项将会影响记录的分析（接收时）和构造（发送时）方式，包括：</span><span class="sxs-lookup"><span data-stu-id="a4161-114">There are a number of considerations related to positional records that will affect how the record is parsed when received and constructed when sent, including:</span></span>  
  
-   <span data-ttu-id="a4161-115">用于填充每一字段的未使用部分的字符称为填充字符。</span><span class="sxs-lookup"><span data-stu-id="a4161-115">The character used to fill the unused portion of each field, known as the pad character.</span></span> <span data-ttu-id="a4161-116">有关详细信息，请参阅[字段填充](../core/field-padding.md)。</span><span class="sxs-lookup"><span data-stu-id="a4161-116">For more information, see [Field Padding](../core/field-padding.md).</span></span>  
  
-   <span data-ttu-id="a4161-117">记录内的可选标记，用于将某记录区别于其他相似的记录。</span><span class="sxs-lookup"><span data-stu-id="a4161-117">An optional tag within the record, used to distinguish the record from other similar records.</span></span> <span data-ttu-id="a4161-118">标记通常出现在记录开头，但也允许在记录的其他地方出现。</span><span class="sxs-lookup"><span data-stu-id="a4161-118">Tags usually occur at the beginning of the record but allowable anywhere within it.</span></span> <span data-ttu-id="a4161-119">有关详细信息，请参阅[位置记录中的标记处理](../core/tag-handling-in-positional-records.md)。</span><span class="sxs-lookup"><span data-stu-id="a4161-119">For more information, see [Tag Handling in Positional Records](../core/tag-handling-in-positional-records.md).</span></span> <span data-ttu-id="a4161-120">位置记录可定义为具有或不具有标记，但是一旦定义后，就必须根据该定义决定标记的存在与否。</span><span class="sxs-lookup"><span data-stu-id="a4161-120">Positional records can be defined to have a tag or not have a tag, but once defined, the tag must be present or not, based on the definition.</span></span>  
  
-   <span data-ttu-id="a4161-121">固定的长度字段，相对于随附的填充字符中的数据的对齐方式。</span><span class="sxs-lookup"><span data-stu-id="a4161-121">How data is justified within a fixed length field, relative to the accompanying pad characters.</span></span> <span data-ttu-id="a4161-122">有关详细信息，请参阅[字段理由](../core/field-justification.md)。</span><span class="sxs-lookup"><span data-stu-id="a4161-122">For more information, see [Field Justification](../core/field-justification.md).</span></span>  
  
-   <span data-ttu-id="a4161-123">其他位置记录或分隔记录中嵌套的位置记录。</span><span class="sxs-lookup"><span data-stu-id="a4161-123">Positional records nested within other positional or delimited records.</span></span> <span data-ttu-id="a4161-124">有关详细信息，请参阅[嵌套位置记录](../core/nested-positional-records.md)。</span><span class="sxs-lookup"><span data-stu-id="a4161-124">For more information, see [Nested Positional Records](../core/nested-positional-records.md).</span></span>  
  
-   <span data-ttu-id="a4161-125">其字段长度指定为特定的字节数而非特定的字符数的位置记录。</span><span class="sxs-lookup"><span data-stu-id="a4161-125">Positional records with field lengths specified as a specific number of bytes rather than a specific number of characters.</span></span> <span data-ttu-id="a4161-126">有关详细信息，请参阅[位置以字节为单位计数](../core/position-counting-in-bytes.md)。</span><span class="sxs-lookup"><span data-stu-id="a4161-126">For more information, see [Position Counting in Bytes](../core/position-counting-in-bytes.md).</span></span>  
  
 <span data-ttu-id="a4161-127">若要帮助你更好地了解如何使用位置的平面文件，请参阅位于 files\microsoft 的 FlatFileReceive 和 FlatFileSend 文件夹中的示例[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]\SDK\Samples\Pipelines\AssemblerDisassembler\\。</span><span class="sxs-lookup"><span data-stu-id="a4161-127">To help you better understand how to work with positional flat files, see the samples in the FlatFileReceive and FlatFileSend folders located at \Program Files\Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]\SDK\Samples\Pipelines\AssemblerDisassembler\\.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a4161-128">如果你平面文件包含分隔和定位记录，则必须设置**结构**的根节点的属性**带分隔符**和**结构**属性从属记录节点为**带分隔符**或**位置**根据。</span><span class="sxs-lookup"><span data-stu-id="a4161-128">If your flat file contains both delimited and positional records, you must set the **Structure** property of the root node to **Delimited** and the **Structure** property of subordinate record nodes to either **Delimited** or **Positional** as appropriate.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a4161-129">位置记录中的字段最多包含 50000000 个字符。</span><span class="sxs-lookup"><span data-stu-id="a4161-129">Fields in positional records have a limit of 50000000 characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4161-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a4161-130">See Also</span></span>  
 <span data-ttu-id="a4161-131">[平面文件消息的结构](../core/structure-of-a-flat-file-message.md) </span><span class="sxs-lookup"><span data-stu-id="a4161-131">[Structure of a Flat File Message](../core/structure-of-a-flat-file-message.md) </span></span>  
 [<span data-ttu-id="a4161-132">如何创建平面文件消息架构</span><span class="sxs-lookup"><span data-stu-id="a4161-132">How to Create Schemas for Flat File Messages</span></span>](../core/how-to-create-schemas-for-flat-file-messages.md)