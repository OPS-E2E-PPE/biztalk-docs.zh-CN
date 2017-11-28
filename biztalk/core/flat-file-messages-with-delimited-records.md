---
title: "分隔记录的平面文件消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7ad7119b-4e39-43df-9dba-a04382eb6db2
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a5dc9eb0253e2bfe8824f6395e1c619c23f0e551
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="flat-file-messages-with-delimited-records"></a><span data-ttu-id="67459-102">带有分隔记录的平面文件消息</span><span class="sxs-lookup"><span data-stu-id="67459-102">Flat File Messages with Delimited Records</span></span>
<span data-ttu-id="67459-103">平面文件实例消息中的分隔记录包含嵌套记录和/或使用预定义的字符或一组字符分隔的各个字段（数据项）。</span><span class="sxs-lookup"><span data-stu-id="67459-103">Delimited records within a flat file instance message contain nested records and/or individual fields (items of data) that are separated by a predefined character or set of characters.</span></span> <span data-ttu-id="67459-104">根据这些分隔符对字段进行解析。</span><span class="sxs-lookup"><span data-stu-id="67459-104">The fields are parsed according to these separating delimiters.</span></span> <span data-ttu-id="67459-105">例如，下面是某个平面文件实例消息中的分隔记录，其中包含假设的采购订单中的两个行项目：</span><span class="sxs-lookup"><span data-stu-id="67459-105">For example, consider the following delimited records from a flat file instance message, which contain two line items from a hypothetical purchase order:</span></span>  
  
```  
  
ITEMS,ITEM872-AA|Lawnmower|1|148.95|Electric-120vac,ITEM926-AA|Baby Monitor|1|39.98|Electric-4AA|2004-01-21  
  
```  
  
 <span data-ttu-id="67459-106">此记录在平面文件架构中的合理定义可描述如下：</span><span class="sxs-lookup"><span data-stu-id="67459-106">A reasonable definition for this record in a flat file schema can be described as follows:</span></span>  
  
-   <span data-ttu-id="67459-107">名为“items”的分隔记录带有子分隔符 (,)、子订单前缀和 ITEMS 标记。</span><span class="sxs-lookup"><span data-stu-id="67459-107">A delimited record named items with child delimiter (,), child order prefix, and the tag ITEMS.</span></span>  
  
    -   <span data-ttu-id="67459-108">分隔，一个名为具有子分隔符 & #124 项的重复记录;，子顺序中缀，并标记项。</span><span class="sxs-lookup"><span data-stu-id="67459-108">A delimited, repeating record named item with child delimiter &#124;, child order infix, and the tag ITEM.</span></span>  
  
    -   <span data-ttu-id="67459-109">名为“partNum”的属性。</span><span class="sxs-lookup"><span data-stu-id="67459-109">An attribute named "partNum".</span></span>  
  
    -   <span data-ttu-id="67459-110">名为“productName”的元素。</span><span class="sxs-lookup"><span data-stu-id="67459-110">An element named "productName".</span></span>  
  
    -   <span data-ttu-id="67459-111">名为“quantity”的元素。</span><span class="sxs-lookup"><span data-stu-id="67459-111">An element named "quantity".</span></span>  
  
    -   <span data-ttu-id="67459-112">名为“USPrice”的元素。</span><span class="sxs-lookup"><span data-stu-id="67459-112">An element named "USPrice".</span></span>  
  
    -   <span data-ttu-id="67459-113">名为“powerSource”的元素。</span><span class="sxs-lookup"><span data-stu-id="67459-113">An element named "powerSource".</span></span>  
  
-   <span data-ttu-id="67459-114">名为“shipDate”的可选元素。</span><span class="sxs-lookup"><span data-stu-id="67459-114">An optional element named "shipDate".</span></span>  
  
 <span data-ttu-id="67459-115">给定这些记录和字段定义后，平面文件拆分器将生成这些记录的 XML 等效项，如下所示：</span><span class="sxs-lookup"><span data-stu-id="67459-115">Given these record and field definitions, the flat file disassembler produces the following XML equivalent of these records.</span></span>  
  
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
  
 <span data-ttu-id="67459-116">有一些与分隔记录有关的注意事项将会影响记录的分析（接收时）和构造（发送时）方式，包括：</span><span class="sxs-lookup"><span data-stu-id="67459-116">There are a number of considerations related to delimited records that will affect how the record is parsed when received and constructed when sent, including:</span></span>  
  
-   <span data-ttu-id="67459-117">用于替代分隔符的解释以将其作为数据的一部分进行处理的字符。</span><span class="sxs-lookup"><span data-stu-id="67459-117">The character or characters used to override the interpretation of delimiters so that they are treated as part of the data.</span></span> <span data-ttu-id="67459-118">有关详细信息，请参阅[如何解释的特殊字符作为字段值的一部分](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md)。</span><span class="sxs-lookup"><span data-stu-id="67459-118">For more information, see [Ways to Interpret Special Characters as Part of a Field Value](../core/ways-to-interpret-special-characters-as-part-of-a-field-value.md).</span></span>  
  
-   <span data-ttu-id="67459-119">位于记录开始位置、用于将该记录与其他类似记录区分开的可选标记。</span><span class="sxs-lookup"><span data-stu-id="67459-119">An optional tag at the beginning of the record, used to distinguish the record from other similar records.</span></span> <span data-ttu-id="67459-120">有关详细信息，请参阅[中分隔记录的标记处理](../core/tag-handling-in-delimited-records.md)。</span><span class="sxs-lookup"><span data-stu-id="67459-120">For more information, see [Tag Handling in Delimited Records](../core/tag-handling-in-delimited-records.md).</span></span>  
  
-   <span data-ttu-id="67459-121">数据在最小长度字段中相对于伴随填充字符的对齐方式。</span><span class="sxs-lookup"><span data-stu-id="67459-121">How data is justified within fields with minimum lengths, relative to the accompanying pad characters.</span></span> <span data-ttu-id="67459-122">有关详细信息，请参阅[字段填充](../core/field-padding.md)，[字段理由](../core/field-justification.md)，和[最小值字段长度内分隔记录](../core/minimum-field-lengths-within-delimited-records.md)。</span><span class="sxs-lookup"><span data-stu-id="67459-122">For more information, see [Field Padding](../core/field-padding.md), [Field Justification](../core/field-justification.md), and [Minimum Field Lengths Within Delimited Records](../core/minimum-field-lengths-within-delimited-records.md).</span></span>  
  
-   <span data-ttu-id="67459-123">其他分隔记录中嵌套的位置记录。</span><span class="sxs-lookup"><span data-stu-id="67459-123">Positional records nested within other delimited records.</span></span> <span data-ttu-id="67459-124">有关详细信息，请参阅[嵌套位置和分隔记录](../core/nested-positional-and-delimited-records.md)。</span><span class="sxs-lookup"><span data-stu-id="67459-124">For more information, see [Nested Positional and Delimited Records](../core/nested-positional-and-delimited-records.md).</span></span>  
  
-   <span data-ttu-id="67459-125">数据在固定长度字段中相对于其伴随填充字符的对齐方式。</span><span class="sxs-lookup"><span data-stu-id="67459-125">How data is justified within a fixed length field, relative to its accompanying pad characters.</span></span> <span data-ttu-id="67459-126">有关详细信息，请参阅[字段理由](../core/field-justification.md)。</span><span class="sxs-lookup"><span data-stu-id="67459-126">For more information, see [Field Justification](../core/field-justification.md).</span></span>  
  
-   <span data-ttu-id="67459-127">有关分隔符相对于所分隔数据的位置的注意事项。</span><span class="sxs-lookup"><span data-stu-id="67459-127">Considerations concerning the positioning of delimiters relate to the data that they delimit.</span></span> <span data-ttu-id="67459-128">有关详细信息，请参阅[子顺序注意事项](../core/child-order-considerations.md)。</span><span class="sxs-lookup"><span data-stu-id="67459-128">For more information, see [Child Order Considerations](../core/child-order-considerations.md).</span></span>  
  
-   <span data-ttu-id="67459-129">在接收和发送平面文件消息时分隔符的保留和取消。</span><span class="sxs-lookup"><span data-stu-id="67459-129">Preservation and suppression of delimiters when flat file messages are received and sent.</span></span> <span data-ttu-id="67459-130">有关详细信息，请参阅[分隔符保留和抑制](../core/delimiter-preservation-and-suppression.md)。</span><span class="sxs-lookup"><span data-stu-id="67459-130">For more information, see [Delimiter Preservation and Suppression](../core/delimiter-preservation-and-suppression.md).</span></span>  
  
 <span data-ttu-id="67459-131">若要帮助你更好地了解如何使用带分隔符的平面文件，请参阅位于的 FlatFileReceive 和 FlatFileSend 文件夹中的示例[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Pipelines\AssemblerDisassembler\\。</span><span class="sxs-lookup"><span data-stu-id="67459-131">To help you better understand how to work with delimited flat files, see the samples in the FlatFileReceive and FlatFileSend folders located at [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\Pipelines\AssemblerDisassembler\\.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="67459-132">如果你平面文件包含分隔和定位记录，则必须设置**结构**的根节点的属性**带分隔符**和**结构**属性从属记录节点为**带分隔符**或**位置**根据。</span><span class="sxs-lookup"><span data-stu-id="67459-132">If your flat file contains both delimited and positional records, you must set the **Structure** property of the root node to **Delimited** and the **Structure** property of subordinate record nodes to either **Delimited** or **Positional** as appropriate.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="67459-133">平面文件中的分隔字段最多包含 50000000 个字符。</span><span class="sxs-lookup"><span data-stu-id="67459-133">Delimited fields in flat files have a limit of 50000000 characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67459-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="67459-134">See Also</span></span>  
 <span data-ttu-id="67459-135">[平面文件消息的结构](../core/structure-of-a-flat-file-message.md) </span><span class="sxs-lookup"><span data-stu-id="67459-135">[Structure of a Flat File Message](../core/structure-of-a-flat-file-message.md) </span></span>  
 <span data-ttu-id="67459-136">[如何创建平面文件消息架构](../core/how-to-create-schemas-for-flat-file-messages.md) </span><span class="sxs-lookup"><span data-stu-id="67459-136">[How to Create Schemas for Flat File Messages](../core/how-to-create-schemas-for-flat-file-messages.md) </span></span>  
 [<span data-ttu-id="67459-137">迁移的平面文件记录</span><span class="sxs-lookup"><span data-stu-id="67459-137">Migrating Flat File Records</span></span>](../core/migrating-flat-file-records.md)