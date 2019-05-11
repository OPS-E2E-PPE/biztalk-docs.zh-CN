---
title: 带有分隔记录的平面文件消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7ad7119b-4e39-43df-9dba-a04382eb6db2
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54b700c0239bed2f1c324085195ca37d2ceaa0c3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387896"
---
# <a name="flat-file-messages-with-delimited-records"></a><span data-ttu-id="6f314-102">带有分隔记录的平面文件消息</span><span class="sxs-lookup"><span data-stu-id="6f314-102">Flat File Messages with Delimited Records</span></span>
<span data-ttu-id="6f314-103">在平面文件实例消息中的分隔的记录包含嵌套的记录和/或通过预定义的字符或一组字符分隔的各个字段 （数据项）。</span><span class="sxs-lookup"><span data-stu-id="6f314-103">Delimited records within a flat file instance message contain nested records and/or individual fields (items of data) that are separated by a predefined character or set of characters.</span></span> <span data-ttu-id="6f314-104">对字段进行解析根据这些分隔符。</span><span class="sxs-lookup"><span data-stu-id="6f314-104">The fields are parsed according to these separating delimiters.</span></span> <span data-ttu-id="6f314-105">例如，考虑以下分隔的记录从平面文件实例消息，其中包含假设的采购订单中的两个行项目：</span><span class="sxs-lookup"><span data-stu-id="6f314-105">For example, consider the following delimited records from a flat file instance message, which contain two line items from a hypothetical purchase order:</span></span>  
  
```  
  
ITEMS,ITEM872-AA|Lawnmower|1|148.95|Electric-120vac,ITEM926-AA|Baby Monitor|1|39.98|Electric-4AA|2004-01-21  
  
```  
  
 <span data-ttu-id="6f314-106">此记录在平面文件架构中的合理定义可描述如下：</span><span class="sxs-lookup"><span data-stu-id="6f314-106">A reasonable definition for this record in a flat file schema can be described as follows:</span></span>  
  
- <span data-ttu-id="6f314-107">名为具有子分隔符 （，）、 子订单前缀和标记项的项的分隔的记录。</span><span class="sxs-lookup"><span data-stu-id="6f314-107">A delimited record named items with child delimiter (,), child order prefix, and the tag ITEMS.</span></span>  
  
  -   <span data-ttu-id="6f314-108">分隔重复记录名为带有子分隔符的项&#124;，子订单中缀和 ITEM 标记。</span><span class="sxs-lookup"><span data-stu-id="6f314-108">A delimited, repeating record named item with child delimiter &#124;, child order infix, and the tag ITEM.</span></span>  
  
  -   <span data-ttu-id="6f314-109">名为"partNum"的属性。</span><span class="sxs-lookup"><span data-stu-id="6f314-109">An attribute named "partNum".</span></span>  
  
  -   <span data-ttu-id="6f314-110">名为"productName"的元素。</span><span class="sxs-lookup"><span data-stu-id="6f314-110">An element named "productName".</span></span>  
  
  -   <span data-ttu-id="6f314-111">名为"数量"的元素。</span><span class="sxs-lookup"><span data-stu-id="6f314-111">An element named "quantity".</span></span>  
  
  -   <span data-ttu-id="6f314-112">名为"USPrice"的元素。</span><span class="sxs-lookup"><span data-stu-id="6f314-112">An element named "USPrice".</span></span>  
  
  -   <span data-ttu-id="6f314-113">名为"powerSource"的元素。</span><span class="sxs-lookup"><span data-stu-id="6f314-113">An element named "powerSource".</span></span>  
  
- <span data-ttu-id="6f314-114">名为"shipDate"的可选元素。</span><span class="sxs-lookup"><span data-stu-id="6f314-114">An optional element named "shipDate".</span></span>  
  
  <span data-ttu-id="6f314-115">给定这些记录和字段定义后，平面文件拆装器会生成这些记录的以下 XML 等效项。</span><span class="sxs-lookup"><span data-stu-id="6f314-115">Given these record and field definitions, the flat file disassembler produces the following XML equivalent of these records.</span></span>  
  
```  
  
<items>  
    <item partNum="872-AA">  
        <productName>Lawnmower</productName>  
        <quantity>1</quantity>  
        <USPrice>148.95</USPrice>  
        <powerSource>Electric-120vac</powerSource>  
    </item>  
    <item partNum="926-AA">  
        <productName>Baby Monitor</productName>  
        <quantity>1</quantity>  
        <USPrice>39.98</USPrice>  
        <powerSource>Electric-4AA</powerSource>  
        <shipDate>2004-01-21</shipDate>  
    </item>  
</items>  
  
```  
  
 <span data-ttu-id="6f314-116">有多种会影响接收和发送时，构造时记录的分析方式的分隔记录与相关的注意事项包括：</span><span class="sxs-lookup"><span data-stu-id="6f314-116">There are a number of considerations related to delimited records that will affect how the record is parsed when received and constructed when sent, including:</span></span>  
  
- <span data-ttu-id="6f314-117">用于替代分隔符的解释，以便它们将被视为数据的一部分的字符。</span><span class="sxs-lookup"><span data-stu-id="6f314-117">The character or characters used to override the interpretation of delimiters so that they are treated as part of the data.</span></span> <span data-ttu-id="6f314-118">有关详细信息，请参阅[方式解释的特殊字符作为字段值的一部分](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md)。</span><span class="sxs-lookup"><span data-stu-id="6f314-118">For more information, see [Ways to Interpret Special Characters as Part of a Field Value](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md).</span></span>  
  
- <span data-ttu-id="6f314-119">用于将某记录区别与其他类似记录的记录的开始处的可选标记。</span><span class="sxs-lookup"><span data-stu-id="6f314-119">An optional tag at the beginning of the record, used to distinguish the record from other similar records.</span></span> <span data-ttu-id="6f314-120">有关详细信息，请参阅[分隔记录中的标记处理](../core/tag-handling-in-delimited-records.md)。</span><span class="sxs-lookup"><span data-stu-id="6f314-120">For more information, see [Tag Handling in Delimited Records](../core/tag-handling-in-delimited-records.md).</span></span>  
  
- <span data-ttu-id="6f314-121">在相对于伴随填充字符的最小长度字段内的数据的对齐方式。</span><span class="sxs-lookup"><span data-stu-id="6f314-121">How data is justified within fields with minimum lengths, relative to the accompanying pad characters.</span></span> <span data-ttu-id="6f314-122">有关详细信息，请参阅[字段填充](../core/field-padding.md)，[字段对齐](../core/field-justification.md)，并[最小字段长度分隔记录中的](../core/minimum-field-lengths-within-delimited-records.md)。</span><span class="sxs-lookup"><span data-stu-id="6f314-122">For more information, see [Field Padding](../core/field-padding.md), [Field Justification](../core/field-justification.md), and [Minimum Field Lengths Within Delimited Records](../core/minimum-field-lengths-within-delimited-records.md).</span></span>  
  
- <span data-ttu-id="6f314-123">位置记录嵌套在其他分隔记录中。</span><span class="sxs-lookup"><span data-stu-id="6f314-123">Positional records nested within other delimited records.</span></span> <span data-ttu-id="6f314-124">有关详细信息，请参阅[嵌套位置和分隔记录](../core/nested-positional-and-delimited-records.md)。</span><span class="sxs-lookup"><span data-stu-id="6f314-124">For more information, see [Nested Positional and Delimited Records](../core/nested-positional-and-delimited-records.md).</span></span>  
  
- <span data-ttu-id="6f314-125">在固定的长度字段，相对于其伴随填充字符中的数据的对齐方式。</span><span class="sxs-lookup"><span data-stu-id="6f314-125">How data is justified within a fixed length field, relative to its accompanying pad characters.</span></span> <span data-ttu-id="6f314-126">有关详细信息，请参阅[字段对齐](../core/field-justification.md)。</span><span class="sxs-lookup"><span data-stu-id="6f314-126">For more information, see [Field Justification](../core/field-justification.md).</span></span>  
  
- <span data-ttu-id="6f314-127">有关分隔符的位置的注意事项均与所分隔的数据。</span><span class="sxs-lookup"><span data-stu-id="6f314-127">Considerations concerning the positioning of delimiters relate to the data that they delimit.</span></span> <span data-ttu-id="6f314-128">有关详细信息，请参阅[子顺序的注意事项](../core/child-order-considerations.md)。</span><span class="sxs-lookup"><span data-stu-id="6f314-128">For more information, see [Child Order Considerations](../core/child-order-considerations.md).</span></span>  
  
- <span data-ttu-id="6f314-129">保留和取消分隔符时接收和发送平面文件消息。</span><span class="sxs-lookup"><span data-stu-id="6f314-129">Preservation and suppression of delimiters when flat file messages are received and sent.</span></span> <span data-ttu-id="6f314-130">有关详细信息，请参阅[分隔符保留和取消](../core/delimiter-preservation-and-suppression.md)。</span><span class="sxs-lookup"><span data-stu-id="6f314-130">For more information, see [Delimiter Preservation and Suppression](../core/delimiter-preservation-and-suppression.md).</span></span>  
  
  <span data-ttu-id="6f314-131">若要帮助您更好地理解如何处理分隔平面文件，请参阅位于的 FlatFileReceive 和 FlatFileSend 文件夹中的示例[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Pipelines\AssemblerDisassembler\\。</span><span class="sxs-lookup"><span data-stu-id="6f314-131">To help you better understand how to work with delimited flat files, see the samples in the FlatFileReceive and FlatFileSend folders located at [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Pipelines\AssemblerDisassembler\\.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6f314-132">如果平面文件中包含分隔和位置记录，则必须设置**结构**属性的根节点**带分隔符**并**结构**属性从属记录节点**带分隔符**或**位置**根据需要。</span><span class="sxs-lookup"><span data-stu-id="6f314-132">If your flat file contains both delimited and positional records, you must set the **Structure** property of the root node to **Delimited** and the **Structure** property of subordinate record nodes to either **Delimited** or **Positional** as appropriate.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6f314-133">平面文件中的分隔的字段的最多包含 50000000 个字符的限制。</span><span class="sxs-lookup"><span data-stu-id="6f314-133">Delimited fields in flat files have a limit of 50000000 characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f314-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="6f314-134">See Also</span></span>  
 <span data-ttu-id="6f314-135">[平面文件消息的结构](../core/structure-of-a-flat-file-message.md) </span><span class="sxs-lookup"><span data-stu-id="6f314-135">[Structure of a Flat File Message](../core/structure-of-a-flat-file-message.md) </span></span>  
 <span data-ttu-id="6f314-136">[如何为平面文件消息创建架构](../core/how-to-create-schemas-for-flat-file-messages.md) </span><span class="sxs-lookup"><span data-stu-id="6f314-136">[How to Create Schemas for Flat File Messages](../core/how-to-create-schemas-for-flat-file-messages.md) </span></span>  
 [<span data-ttu-id="6f314-137">迁移平面文件记录</span><span class="sxs-lookup"><span data-stu-id="6f314-137">Migrating Flat File Records</span></span>](../core/migrating-flat-file-records.md)