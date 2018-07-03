---
title: 分隔符保留和取消 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30985b94-625e-411a-8137-1c129bc197bf
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9bb92d9784fb9e12494757407898388d6f52725e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975470"
---
# <a name="delimiter-preservation-and-suppression"></a><span data-ttu-id="3a0f2-102">分隔符保留和取消</span><span class="sxs-lookup"><span data-stu-id="3a0f2-102">Delimiter Preservation and Suppression</span></span>

## <a name="overview"></a><span data-ttu-id="3a0f2-103">概述</span><span class="sxs-lookup"><span data-stu-id="3a0f2-103">Overview</span></span>
<span data-ttu-id="3a0f2-104">有两个属性可应用于分隔记录：**为空数据保留分隔符**并**取消尾部分隔符**。</span><span class="sxs-lookup"><span data-stu-id="3a0f2-104">There are two properties that apply to delimited records: **Preserve Delimiter For Empty Data** and **Suppress Trailing Delimiters**.</span></span> <span data-ttu-id="3a0f2-105">使用这些属性来控制平面文件组装器如何处理与不存在的数据和尾部分隔符的分隔符。</span><span class="sxs-lookup"><span data-stu-id="3a0f2-105">Use these properties to control how the flat file assembler handles delimiters associated with nonexistent data and trailing delimiters.</span></span> <span data-ttu-id="3a0f2-106">当您将设置**为空数据保留分隔符**属性设置为**是**（这是默认设置），在翻译后的平面文件消息中包括分隔符：</span><span class="sxs-lookup"><span data-stu-id="3a0f2-106">When you set the **Preserve Delimiter For Empty Data** property to **Yes** (which is the default setting), delimiters are included in the translated flat file message for:</span></span>  
  
- <span data-ttu-id="3a0f2-107">没有数据的字段。</span><span class="sxs-lookup"><span data-stu-id="3a0f2-107">Fields without data.</span></span>  
  
- <span data-ttu-id="3a0f2-108">没有相关联的标记且没有数据的直接从属记录。</span><span class="sxs-lookup"><span data-stu-id="3a0f2-108">Immediately subordinate records without data that do not have a tag associated with them.</span></span>  
  
  <span data-ttu-id="3a0f2-109">当您将设置**为空数据保留分隔符**属性设置为**否**，记录和字段不包含数据的已翻译平面文件中不包括分隔符。</span><span class="sxs-lookup"><span data-stu-id="3a0f2-109">When you set the **Preserve Delimiter For Empty Data** property to **No**, delimiters are not included in the translated flat file for records and fields without data.</span></span> <span data-ttu-id="3a0f2-110">此外，而不考虑的设置**为空数据保留分隔符**属性，而无需为其定义标记的数据的直接从属记录在翻译后的平面文件消息中不会包含分隔符。</span><span class="sxs-lookup"><span data-stu-id="3a0f2-110">Further, regardless of the setting of the **Preserve Delimiter For Empty Data** property, delimiters will not be included in the translated flat file message for immediately subordinate records without data for which a tag is defined.</span></span>  
  
  <span data-ttu-id="3a0f2-111">当您将设置**取消尾部分隔符**属性设置为**否**（这是默认设置），可能会在翻译后的平面文件消息中包含一个或多个尾部分隔符。</span><span class="sxs-lookup"><span data-stu-id="3a0f2-111">When you set the **Suppress Trailing Delimiters** property to **No** (which is the default setting), one or more trailing delimiters may be included in the translated flat file message.</span></span> <span data-ttu-id="3a0f2-112">当您将设置**取消尾部分隔符**属性设置为**是**、 尾随翻译后的平面文件消息中不包含分隔符。</span><span class="sxs-lookup"><span data-stu-id="3a0f2-112">When you set the **Suppress Trailing Delimiters** property to **Yes**, trailing delimiters are not included in the translated flat file message.</span></span>  

## <a name="special-scenarios"></a><span data-ttu-id="3a0f2-113">特殊的方案</span><span class="sxs-lookup"><span data-stu-id="3a0f2-113">Special scenarios</span></span>  
 <span data-ttu-id="3a0f2-114">行为引起的设置的其中某些特殊情况下**为空数据保留分隔符**并**取消尾部分隔符**属性可能会发生冲突。</span><span class="sxs-lookup"><span data-stu-id="3a0f2-114">There are some special cases where the behaviors caused by the settings of the **Preserve Delimiter For Empty Data** and **Suppress Trailing Delimiters** properties can conflict.</span></span> <span data-ttu-id="3a0f2-115">在这种情况下后, 一种属性，与关联的行为**取消尾部分隔符**，将优先。</span><span class="sxs-lookup"><span data-stu-id="3a0f2-115">In such cases, the behaviors associated with the latter property, **Suppress Trailing Delimiters**, will take precedence.</span></span> <span data-ttu-id="3a0f2-116">此外，在某些特殊情况，系统将警告您为这两个属性选择的设置存在潜在冲突。</span><span class="sxs-lookup"><span data-stu-id="3a0f2-116">Further, there are some special cases where you will be warned about potential conflicts between the settings you have chosen for these two properties.</span></span>  
  
 <span data-ttu-id="3a0f2-117">例如，考虑**记录**定义具有以下属性值的节点：</span><span class="sxs-lookup"><span data-stu-id="3a0f2-117">For example, consider a **Record** node defined with the following property values:</span></span>  
  
- <span data-ttu-id="3a0f2-118">节点名称为 MyRec</span><span class="sxs-lookup"><span data-stu-id="3a0f2-118">Node Name is MyRec</span></span>  
  
- <span data-ttu-id="3a0f2-119">标记标识符为 Rec</span><span class="sxs-lookup"><span data-stu-id="3a0f2-119">Tag Identifier is Rec</span></span>  
  
- <span data-ttu-id="3a0f2-120">子分隔符为 ,</span><span class="sxs-lookup"><span data-stu-id="3a0f2-120">Child Delimiter is ,</span></span>  
  
- <span data-ttu-id="3a0f2-121">子顺序为中缀</span><span class="sxs-lookup"><span data-stu-id="3a0f2-121">Child Order is Infix</span></span>  
  
  <span data-ttu-id="3a0f2-122">并定义包含五个**字段元素**具有以下名称的节点 (它们也可能是**Field 特性**节点或从属**记录**节点):</span><span class="sxs-lookup"><span data-stu-id="3a0f2-122">And defined to contain five **Field Element** nodes with the following names (they could also be **Field Attribute** nodes or subordinate **Record** nodes):</span></span>  
  
- <span data-ttu-id="3a0f2-123">FieldElem1</span><span class="sxs-lookup"><span data-stu-id="3a0f2-123">FieldElem1</span></span>  
  
- <span data-ttu-id="3a0f2-124">FieldElem2</span><span class="sxs-lookup"><span data-stu-id="3a0f2-124">FieldElem2</span></span>  
  
- <span data-ttu-id="3a0f2-125">FieldElem3</span><span class="sxs-lookup"><span data-stu-id="3a0f2-125">FieldElem3</span></span>  
  
- <span data-ttu-id="3a0f2-126">FieldElem4</span><span class="sxs-lookup"><span data-stu-id="3a0f2-126">FieldElem4</span></span>  
  
- <span data-ttu-id="3a0f2-127">FieldElem5</span><span class="sxs-lookup"><span data-stu-id="3a0f2-127">FieldElem5</span></span>  
  
  <span data-ttu-id="3a0f2-128">接下来，假定，以下主要空 XML 片段，表示此**记录**节点中，传递给平面文件组装器。</span><span class="sxs-lookup"><span data-stu-id="3a0f2-128">Next, assume that the following mainly empty XML fragment, representing this **Record** node, is passed to the flat file assembler.</span></span>  
  
```  
<MyRec>  
    <FieldElem1 />  
    <FieldElem2 />  
    <FieldElem3>Val</FieldElem3>  
    <FieldElem4 />  
    <FieldElem5 />  
</MyRec>  
  
```  
  
 <span data-ttu-id="3a0f2-129">下表显示产生的输出和关联的其他属性设置的相关架构节点，根据不同的设置要求**为空数据保留分隔符**(PDFED) 和**取消尾部分隔符**(STD) 属性。</span><span class="sxs-lookup"><span data-stu-id="3a0f2-129">The following table shows the output produced, and the associated additional property setting requirements for the relevant schema nodes, based on different settings for the **Preserve Delimiter For Empty Data** (PDFED) and **Suppress Trailing Delimiters** (STD) properties.</span></span>  
  
|<span data-ttu-id="3a0f2-130">PDFED 设置</span><span class="sxs-lookup"><span data-stu-id="3a0f2-130">PDFED setting</span></span>|<span data-ttu-id="3a0f2-131">STD 设置</span><span class="sxs-lookup"><span data-stu-id="3a0f2-131">STD setting</span></span>|<span data-ttu-id="3a0f2-132">“输出”</span><span class="sxs-lookup"><span data-stu-id="3a0f2-132">Output</span></span>|<span data-ttu-id="3a0f2-133">其他节点要求</span><span class="sxs-lookup"><span data-stu-id="3a0f2-133">Additional node requirements</span></span>|  
|---|---|---|---|  
|<span data-ttu-id="3a0f2-134">是</span><span class="sxs-lookup"><span data-stu-id="3a0f2-134">Yes</span></span>|<span data-ttu-id="3a0f2-135">“否”</span><span class="sxs-lookup"><span data-stu-id="3a0f2-135">No</span></span>|<span data-ttu-id="3a0f2-136">Rec,,,Val,,</span><span class="sxs-lookup"><span data-stu-id="3a0f2-136">Rec,,,Val,,</span></span>|<span data-ttu-id="3a0f2-137">无。</span><span class="sxs-lookup"><span data-stu-id="3a0f2-137">None.</span></span>|  
|<span data-ttu-id="3a0f2-138">“否”</span><span class="sxs-lookup"><span data-stu-id="3a0f2-138">No</span></span>|<span data-ttu-id="3a0f2-139">是</span><span class="sxs-lookup"><span data-stu-id="3a0f2-139">Yes</span></span>|<span data-ttu-id="3a0f2-140">Rec,Val</span><span class="sxs-lookup"><span data-stu-id="3a0f2-140">Rec,Val</span></span>|<span data-ttu-id="3a0f2-141">所有**Field 元素**节点必须配置为可选。</span><span class="sxs-lookup"><span data-stu-id="3a0f2-141">All **Field Element** nodes must be configured as optional.</span></span>|  
|<span data-ttu-id="3a0f2-142">是</span><span class="sxs-lookup"><span data-stu-id="3a0f2-142">Yes</span></span>|<span data-ttu-id="3a0f2-143">是</span><span class="sxs-lookup"><span data-stu-id="3a0f2-143">Yes</span></span>|<span data-ttu-id="3a0f2-144">Rec,,,Val</span><span class="sxs-lookup"><span data-stu-id="3a0f2-144">Rec,,,Val</span></span>|<span data-ttu-id="3a0f2-145">节点名分别为**fieldelem4**并**FieldElem5**必须配置为可选。</span><span class="sxs-lookup"><span data-stu-id="3a0f2-145">Nodes named **FieldElem4** and **FieldElem5** must be configured as optional.</span></span>|  
|<span data-ttu-id="3a0f2-146">“否”</span><span class="sxs-lookup"><span data-stu-id="3a0f2-146">No</span></span>|<span data-ttu-id="3a0f2-147">“否”</span><span class="sxs-lookup"><span data-stu-id="3a0f2-147">No</span></span>|<span data-ttu-id="3a0f2-148">Rec,Val,,</span><span class="sxs-lookup"><span data-stu-id="3a0f2-148">Rec,Val,,</span></span>|<span data-ttu-id="3a0f2-149">所有**Field 元素**节点必须配置为可选。</span><span class="sxs-lookup"><span data-stu-id="3a0f2-149">All **Field Element** nodes must be configured as optional.</span></span>|  
  
 <span data-ttu-id="3a0f2-150">当这些属性设置指定应不保留分隔符或应取消分隔符时，在以下两种情况下将发出一条消息，警告您可能无法使用同一架构解析序列化平面文件数据：</span><span class="sxs-lookup"><span data-stu-id="3a0f2-150">When these property settings specify that delimiters should either not be preserved or should be suppressed, a message warning that it might not be possible to parse the serialized flat file data using the same schema will be issued in the following two cases:</span></span>  
  
-   <span data-ttu-id="3a0f2-151">当**记录**为其节点**为空数据保留分隔符**属性设置为**否**和/或**取消尾部分隔符**属性设置为**是**分别包含从属**字段元素**节点，**字段属性**节点，或**记录**节点未指定任何标记。</span><span class="sxs-lookup"><span data-stu-id="3a0f2-151">When the **Record** node for which the **Preserve Delimiter For Empty Data** property is set to **No** and/or the **Suppress Trailing Delimiters** property is set to **Yes**, respectively, contains subordinate **Field Element** nodes, **Field Attribute** nodes, or **Record** nodes for which no tag is specified.</span></span>  
  
-   <span data-ttu-id="3a0f2-152">当从属**字段元素**节点，**字段属性**节点，并**记录**未指定任何标记的节点未配置为 optional (通过设置**最小出现次数**属性设置为零) 架构中。</span><span class="sxs-lookup"><span data-stu-id="3a0f2-152">When the subordinate **Field Element** nodes, **Field Attribute** nodes, and **Record** nodes for which no tag is specified are not configured to be optional (by setting the **Min Occurs** property set to zero) in the schema.</span></span> <span data-ttu-id="3a0f2-153">当**取消尾部分隔符**属性设置为**是**，只有最后一个这样的从属节点需要配置为可选。</span><span class="sxs-lookup"><span data-stu-id="3a0f2-153">When the **Suppress Trailing Delimiters** property is set to **Yes**, only the last such subordinate nodes need to be configured as optional.</span></span> <span data-ttu-id="3a0f2-154">当**为空数据保留分隔符**属性设置为**否**、 所有尾部从属节点需要配置为可选。</span><span class="sxs-lookup"><span data-stu-id="3a0f2-154">When the **Preserve Delimiter For Empty Data** property is set to **No**, all trailing subordinate nodes need to be configured as optional.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3a0f2-155">当与 （可能可选） 相关联的 XML 元素，则始终保留分隔符**记录**， **Field 元素**，或**字段属性**节点是根本没有从除一条记录时遵循缺失的可选字段的业务文档的 XML 表示形式。</span><span class="sxs-lookup"><span data-stu-id="3a0f2-155">Delimiters are always preserved when the XML element associated with a (presumably optional) **Record**, **Field Element**, or **Field Attribute** node are entirely missing from the XML representation of the business document except when a Record follows a missing optional Field.</span></span> <span data-ttu-id="3a0f2-156">换句话说，如果数据及其前后的 XML 标记都丢失，则在业务文档的平面文件表示形式中将始终包含相应的分隔符。</span><span class="sxs-lookup"><span data-stu-id="3a0f2-156">In other words, when the data and its surrounding XML tags are both missing, the corresponding delimiter is always included in the flat file representation of the business document.</span></span>  
  
 <span data-ttu-id="3a0f2-157">现在将该架构更改为紧随缺少的“字段元素”之后包含一个带有两个“字段元素”的子记录。</span><span class="sxs-lookup"><span data-stu-id="3a0f2-157">Now change the schema to include a child record with two Field Element immediately following a missing Field Element.</span></span> <span data-ttu-id="3a0f2-158">将该子记录元素配置为使用&#124;（管道） 字符作为分隔符。</span><span class="sxs-lookup"><span data-stu-id="3a0f2-158">The child record elements are configured to use the &#124; (pipe) character as a delimiter.</span></span>  
  
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
  
 <span data-ttu-id="3a0f2-159">如果将其传递给平面文件拆装器，则不会保留“FieldElem4”的分隔符，但后面的记录将按预期进行分隔。</span><span class="sxs-lookup"><span data-stu-id="3a0f2-159">If this is passed to the flat file disassembler, the delimiters for FieldElem4 will not be preserved but subsequent records will be delimited as expected.</span></span>  
  
```  
,,Val,,Inner1,Inner2,,  
```  
  
## <a name="see-also"></a><span data-ttu-id="3a0f2-160">请参阅</span><span class="sxs-lookup"><span data-stu-id="3a0f2-160">See Also</span></span>  
- [<span data-ttu-id="3a0f2-161">分隔记录注意事项</span><span class="sxs-lookup"><span data-stu-id="3a0f2-161">Delimited Record Considerations</span></span>](../core/delimited-record-considerations.md)   
- <span data-ttu-id="3a0f2-162">**为空数据 （平面文件架构的节点属性） 保留分隔符**和**取消尾部分隔符 （平面文件架构的节点属性）** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="3a0f2-162">**Preserve Delimiter For Empty Data (Node Property of Flat File Schemas)** and **Suppress Trailing Delimiters (Node Property of Flat File Schemas)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
