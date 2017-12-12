---
title: "分隔符保留和抑制 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 30985b94-625e-411a-8137-1c129bc197bf
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e0b5a5c60d42892479feacc93aedb3802b11308c
ms.sourcegitcommit: d572ae5c887898adedcb3dfc5f83841beedd3434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/06/2017
---
# <a name="delimiter-preservation-and-suppression"></a><span data-ttu-id="69812-102">分隔符保留和抑制</span><span class="sxs-lookup"><span data-stu-id="69812-102">Delimiter Preservation and Suppression</span></span>

## <a name="overview"></a><span data-ttu-id="69812-103">概述</span><span class="sxs-lookup"><span data-stu-id="69812-103">Overview</span></span>
<span data-ttu-id="69812-104">有两个属性应用于分隔记录：**空数据的保留分隔符**和**禁止显示尾随分隔符**。</span><span class="sxs-lookup"><span data-stu-id="69812-104">There are two properties that apply to delimited records: **Preserve Delimiter For Empty Data** and **Suppress Trailing Delimiters**.</span></span> <span data-ttu-id="69812-105">使用这些属性控制的平面文件汇编如何处理尾随分隔符不存在的数据与关联的分隔符。</span><span class="sxs-lookup"><span data-stu-id="69812-105">Use these properties to control how the flat file assembler handles delimiters associated with nonexistent data and trailing delimiters.</span></span> <span data-ttu-id="69812-106">当你将设置**空数据的保留分隔符**属性**是**（这是默认设置） 中的已翻译的平面文件消息包括分隔符：</span><span class="sxs-lookup"><span data-stu-id="69812-106">When you set the **Preserve Delimiter For Empty Data** property to **Yes** (which is the default setting), delimiters are included in the translated flat file message for:</span></span>  
  
-   <span data-ttu-id="69812-107">没有数据的字段。</span><span class="sxs-lookup"><span data-stu-id="69812-107">Fields without data.</span></span>  
  
-   <span data-ttu-id="69812-108">没有相关联的标记且没有数据的直接从属记录。</span><span class="sxs-lookup"><span data-stu-id="69812-108">Immediately subordinate records without data that do not have a tag associated with them.</span></span>  
  
 <span data-ttu-id="69812-109">当你将设置**空数据的保留分隔符**属性**否**，记录和字段不包含数据的已翻译平面文件中未包含分隔符。</span><span class="sxs-lookup"><span data-stu-id="69812-109">When you set the **Preserve Delimiter For Empty Data** property to **No**, delimiters are not included in the translated flat file for records and fields without data.</span></span> <span data-ttu-id="69812-110">此外，不管如何设置**空数据的保留分隔符**属性，分隔符将不包含在立即从属的记录，而无需为其定义一个标记的数据的已翻译的平面文件消息。</span><span class="sxs-lookup"><span data-stu-id="69812-110">Further, regardless of the setting of the **Preserve Delimiter For Empty Data** property, delimiters will not be included in the translated flat file message for immediately subordinate records without data for which a tag is defined.</span></span>  
  
 <span data-ttu-id="69812-111">当你将设置**禁止显示尾随分隔符**属性**否**（这是默认设置），已转换的平面文件消息中可能包含一个或多个尾随分隔符。</span><span class="sxs-lookup"><span data-stu-id="69812-111">When you set the **Suppress Trailing Delimiters** property to **No** (which is the default setting), one or more trailing delimiters may be included in the translated flat file message.</span></span> <span data-ttu-id="69812-112">当你将设置**禁止显示尾随分隔符**属性**是**、 尾随分隔符不包括在已转换的平面文件消息。</span><span class="sxs-lookup"><span data-stu-id="69812-112">When you set the **Suppress Trailing Delimiters** property to **Yes**, trailing delimiters are not included in the translated flat file message.</span></span>  

## <a name="special-scenarios"></a><span data-ttu-id="69812-113">特殊的方案</span><span class="sxs-lookup"><span data-stu-id="69812-113">Special scenarios</span></span>  
 <span data-ttu-id="69812-114">在某些特殊的情况下，其中行为引起的设置**空数据的保留分隔符**和**禁止显示尾随分隔符**属性可能会发生冲突。</span><span class="sxs-lookup"><span data-stu-id="69812-114">There are some special cases where the behaviors caused by the settings of the **Preserve Delimiter For Empty Data** and **Suppress Trailing Delimiters** properties can conflict.</span></span> <span data-ttu-id="69812-115">在这种情况下后, 一个属性，与关联的行为**禁止显示尾随分隔符**，将优先。</span><span class="sxs-lookup"><span data-stu-id="69812-115">In such cases, the behaviors associated with the latter property, **Suppress Trailing Delimiters**, will take precedence.</span></span> <span data-ttu-id="69812-116">此外，在某些特殊情况，系统将警告您为这两个属性选择的设置存在潜在冲突。</span><span class="sxs-lookup"><span data-stu-id="69812-116">Further, there are some special cases where you will be warned about potential conflicts between the settings you have chosen for these two properties.</span></span>  
  
 <span data-ttu-id="69812-117">例如，考虑**记录**定义具有以下属性值的节点：</span><span class="sxs-lookup"><span data-stu-id="69812-117">For example, consider a **Record** node defined with the following property values:</span></span>  
  
-   <span data-ttu-id="69812-118">节点名称为 MyRec</span><span class="sxs-lookup"><span data-stu-id="69812-118">Node Name is MyRec</span></span>  
  
-   <span data-ttu-id="69812-119">标记标识符为 Rec</span><span class="sxs-lookup"><span data-stu-id="69812-119">Tag Identifier is Rec</span></span>  
  
-   <span data-ttu-id="69812-120">子分隔符为 ,</span><span class="sxs-lookup"><span data-stu-id="69812-120">Child Delimiter is ,</span></span>  
  
-   <span data-ttu-id="69812-121">子顺序为中缀</span><span class="sxs-lookup"><span data-stu-id="69812-121">Child Order is Infix</span></span>  
  
 <span data-ttu-id="69812-122">和定义包含五个**Field 元素**具有以下名称的节点 (它们可能是**字段特性**节点或从属**记录**节点):</span><span class="sxs-lookup"><span data-stu-id="69812-122">And defined to contain five **Field Element** nodes with the following names (they could also be **Field Attribute** nodes or subordinate **Record** nodes):</span></span>  
  
-   <span data-ttu-id="69812-123">FieldElem1</span><span class="sxs-lookup"><span data-stu-id="69812-123">FieldElem1</span></span>  
  
-   <span data-ttu-id="69812-124">FieldElem2</span><span class="sxs-lookup"><span data-stu-id="69812-124">FieldElem2</span></span>  
  
-   <span data-ttu-id="69812-125">FieldElem3</span><span class="sxs-lookup"><span data-stu-id="69812-125">FieldElem3</span></span>  
  
-   <span data-ttu-id="69812-126">FieldElem4</span><span class="sxs-lookup"><span data-stu-id="69812-126">FieldElem4</span></span>  
  
-   <span data-ttu-id="69812-127">FieldElem5</span><span class="sxs-lookup"><span data-stu-id="69812-127">FieldElem5</span></span>  
  
 <span data-ttu-id="69812-128">接下来，假定，以下主要空 XML 片段，表示此**记录**节点，传递到的平面文件汇编。</span><span class="sxs-lookup"><span data-stu-id="69812-128">Next, assume that the following mainly empty XML fragment, representing this **Record** node, is passed to the flat file assembler.</span></span>  
  
```  
<MyRec>  
    <FieldElem1 />  
    <FieldElem2 />  
    <FieldElem3>Val</FieldElem3>  
    <FieldElem4 />  
    <FieldElem5 />  
</MyRec>  
  
```  
  
 <span data-ttu-id="69812-129">下表显示生成的输出和关联的其他属性设置为根据不同的设置相关的架构节点的要求**空数据的保留分隔符**(PDFED) 和**禁止显示尾随分隔符**(STD) 属性。</span><span class="sxs-lookup"><span data-stu-id="69812-129">The following table shows the output produced, and the associated additional property setting requirements for the relevant schema nodes, based on different settings for the **Preserve Delimiter For Empty Data** (PDFED) and **Suppress Trailing Delimiters** (STD) properties.</span></span>  
  
|<span data-ttu-id="69812-130">PDFED 设置</span><span class="sxs-lookup"><span data-stu-id="69812-130">PDFED setting</span></span>|<span data-ttu-id="69812-131">STD 设置</span><span class="sxs-lookup"><span data-stu-id="69812-131">STD setting</span></span>|<span data-ttu-id="69812-132">“输出”</span><span class="sxs-lookup"><span data-stu-id="69812-132">Output</span></span>|<span data-ttu-id="69812-133">其他节点要求</span><span class="sxs-lookup"><span data-stu-id="69812-133">Additional node requirements</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="69812-134">是</span><span class="sxs-lookup"><span data-stu-id="69812-134">Yes</span></span>|<span data-ttu-id="69812-135">是</span><span class="sxs-lookup"><span data-stu-id="69812-135">No</span></span>|<span data-ttu-id="69812-136">Rec,,,Val,,</span><span class="sxs-lookup"><span data-stu-id="69812-136">Rec,,,Val,,</span></span>|<span data-ttu-id="69812-137">无。</span><span class="sxs-lookup"><span data-stu-id="69812-137">None.</span></span>|  
|<span data-ttu-id="69812-138">是</span><span class="sxs-lookup"><span data-stu-id="69812-138">No</span></span>|<span data-ttu-id="69812-139">是</span><span class="sxs-lookup"><span data-stu-id="69812-139">Yes</span></span>|<span data-ttu-id="69812-140">Rec,Val</span><span class="sxs-lookup"><span data-stu-id="69812-140">Rec,Val</span></span>|<span data-ttu-id="69812-141">所有**Field 元素**节点必须配置为可选。</span><span class="sxs-lookup"><span data-stu-id="69812-141">All **Field Element** nodes must be configured as optional.</span></span>|  
|<span data-ttu-id="69812-142">是</span><span class="sxs-lookup"><span data-stu-id="69812-142">Yes</span></span>|<span data-ttu-id="69812-143">是</span><span class="sxs-lookup"><span data-stu-id="69812-143">Yes</span></span>|<span data-ttu-id="69812-144">Rec,,,Val</span><span class="sxs-lookup"><span data-stu-id="69812-144">Rec,,,Val</span></span>|<span data-ttu-id="69812-145">节点名为**FieldElem4**和**FieldElem5**必须配置为可选。</span><span class="sxs-lookup"><span data-stu-id="69812-145">Nodes named **FieldElem4** and **FieldElem5** must be configured as optional.</span></span>|  
|<span data-ttu-id="69812-146">是</span><span class="sxs-lookup"><span data-stu-id="69812-146">No</span></span>|<span data-ttu-id="69812-147">是</span><span class="sxs-lookup"><span data-stu-id="69812-147">No</span></span>|<span data-ttu-id="69812-148">Rec,Val,,</span><span class="sxs-lookup"><span data-stu-id="69812-148">Rec,Val,,</span></span>|<span data-ttu-id="69812-149">所有**Field 元素**节点必须配置为可选。</span><span class="sxs-lookup"><span data-stu-id="69812-149">All **Field Element** nodes must be configured as optional.</span></span>|  
  
 <span data-ttu-id="69812-150">当这些属性设置指定应不保留分隔符或应取消分隔符时，在以下两种情况下将发出一条消息，警告您可能无法使用同一架构解析序列化平面文件数据：</span><span class="sxs-lookup"><span data-stu-id="69812-150">When these property settings specify that delimiters should either not be preserved or should be suppressed, a message warning that it might not be possible to parse the serialized flat file data using the same schema will be issued in the following two cases:</span></span>  
  
-   <span data-ttu-id="69812-151">当**记录**为其节点**空数据的保留分隔符**属性设置为**否**和/或**禁止显示尾随分隔符**属性设置为**是**分别包含从属**Field 元素**节点，**字段特性**节点，或**记录**为其指定没有标记的节点。</span><span class="sxs-lookup"><span data-stu-id="69812-151">When the **Record** node for which the **Preserve Delimiter For Empty Data** property is set to **No** and/or the **Suppress Trailing Delimiters** property is set to **Yes**, respectively, contains subordinate **Field Element** nodes, **Field Attribute** nodes, or **Record** nodes for which no tag is specified.</span></span>  
  
-   <span data-ttu-id="69812-152">当从属**Field 元素**节点，**字段特性**节点，和**记录**未配置为其指定没有标记的节点是可选 (通过设置**最小出现次数**属性设置为零) 架构中。</span><span class="sxs-lookup"><span data-stu-id="69812-152">When the subordinate **Field Element** nodes, **Field Attribute** nodes, and **Record** nodes for which no tag is specified are not configured to be optional (by setting the **Min Occurs** property set to zero) in the schema.</span></span> <span data-ttu-id="69812-153">当**禁止显示尾随分隔符**属性设置为**是**，只有的最后一个这样的从属节点需要将配置为可选。</span><span class="sxs-lookup"><span data-stu-id="69812-153">When the **Suppress Trailing Delimiters** property is set to **Yes**, only the last such subordinate nodes need to be configured as optional.</span></span> <span data-ttu-id="69812-154">当**空数据的保留分隔符**属性设置为**否**、 所有尾随从属节点需要将配置为可选。</span><span class="sxs-lookup"><span data-stu-id="69812-154">When the **Preserve Delimiter For Empty Data** property is set to **No**, all trailing subordinate nodes need to be configured as optional.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="69812-155">与 （大概可选） 关联的 XML 元素时，将始终保留分隔符**记录**， **Field 元素**，或**字段特性**完全节点未显示从 XML 文档的表示形式业务除一条记录时遵循缺失的可选字段。</span><span class="sxs-lookup"><span data-stu-id="69812-155">Delimiters are always preserved when the XML element associated with a (presumably optional) **Record**, **Field Element**, or **Field Attribute** node are entirely missing from the XML representation of the business document except when a Record follows a missing optional Field.</span></span> <span data-ttu-id="69812-156">换句话说，如果数据及其前后的 XML 标记都丢失，则在业务文档的平面文件表示形式中将始终包含相应的分隔符。</span><span class="sxs-lookup"><span data-stu-id="69812-156">In other words, when the data and its surrounding XML tags are both missing, the corresponding delimiter is always included in the flat file representation of the business document.</span></span>  
  
 <span data-ttu-id="69812-157">现在将该架构更改为紧随缺少的“字段元素”之后包含一个带有两个“字段元素”的子记录。</span><span class="sxs-lookup"><span data-stu-id="69812-157">Now change the schema to include a child record with two Field Element immediately following a missing Field Element.</span></span> <span data-ttu-id="69812-158">子记录元素配置为使用 &#124;（竖线） 作为分隔符的字符。</span><span class="sxs-lookup"><span data-stu-id="69812-158">The child record elements are configured to use the &#124; (pipe) character as a delimiter.</span></span>  
  
```  
<MyRec>  
    <FieldElem1 />  
    <FieldElem2 />  
    <FieldElem3>Val</FieldElem3>  
    <!-- <FieldElem4 /> -->  
    <ChildRec>  
        <InnerFieldElement1>Inner1</InnerFieldElement1>   
        <InnerFieldElement2>Inner2</InnerFieldElement1>  
    </ChildRec>  
    <FieldElem5 />  
</MyRec>  
  
```  
  
 <span data-ttu-id="69812-159">如果将其传递给平面文件拆装器，则不会保留“FieldElem4”的分隔符，但后面的记录将按预期进行分隔。</span><span class="sxs-lookup"><span data-stu-id="69812-159">If this is passed to the flat file disassembler, the delimiters for FieldElem4 will not be preserved but subsequent records will be delimited as expected.</span></span>  
  
```  
,,Val,,Inner1,Inner2,,  
```  
  
## <a name="see-also"></a><span data-ttu-id="69812-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="69812-160">See Also</span></span>  
-  [<span data-ttu-id="69812-161">分隔记录注意事项</span><span class="sxs-lookup"><span data-stu-id="69812-161">Delimited Record Considerations</span></span>](../core/delimited-record-considerations.md)   
-  <span data-ttu-id="69812-162">**为空数据 （的平面文件架构的节点属性） 保留分隔符**和**禁止显示尾部分隔符 （节点属性的平面文件架构）**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="69812-162">**Preserve Delimiter For Empty Data (Node Property of Flat File Schemas)** and **Suppress Trailing Delimiters (Node Property of Flat File Schemas)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
