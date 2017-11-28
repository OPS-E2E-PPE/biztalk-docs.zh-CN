---
title: "提升属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- properties, promoting
- promoting properties
- promoting properties, about promoting properties
ms.assetid: e1825028-7dd9-4eae-a383-4db12a83a402
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc1c5ac3e6e9aeadccc4eaefcb1457821ef36a93
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="promoting-properties"></a><span data-ttu-id="47c86-102">提升属性</span><span class="sxs-lookup"><span data-stu-id="47c86-102">Promoting Properties</span></span>
<span data-ttu-id="47c86-103">属性的升级涉及任一提升**Field 元素**或**字段特性**架构是中的节点**可分辨字段**或**属性字段**。</span><span class="sxs-lookup"><span data-stu-id="47c86-103">Promotion of properties involves either promoting **Field Element** or **Field Attribute** nodes in a schema to be **Distinguished Fields** or **Property Fields**.</span></span> <span data-ttu-id="47c86-104">你还可以升级**记录**节点**属性字段**如果它们具有简单内容 (**内容类型**属性**记录**节点设置为**SimpleContent**)。</span><span class="sxs-lookup"><span data-stu-id="47c86-104">You can also promote **Record** nodes as **Property Fields** if they have simple content (**Content Type** property of the **Record** node set to **SimpleContent**).</span></span> <span data-ttu-id="47c86-105">本部分提供有关将提升为节点的分步说明**可分辨字段**或**属性字段**。</span><span class="sxs-lookup"><span data-stu-id="47c86-105">This section provides step-by-step instructions for promoting nodes as either **Distinguished Fields** or as **Property Fields**.</span></span>  
  
 <span data-ttu-id="47c86-106">若要将提升**记录**（具有简单内容）， **Field 元素**，或**字段特性**节点作为**属性字段**，你可能会首先定义调用属性架构的架构的特殊类型。</span><span class="sxs-lookup"><span data-stu-id="47c86-106">To promote a **Record** (with simple content), **Field Element**, or **Field Attribute** node as a **Property Field**, you may first define a special type of schema called a property schema.</span></span> <span data-ttu-id="47c86-107">属性架构定义一组非结构化的**Field 元素**你升级到其中的节点**记录**（具有简单内容）， **Field 元素**，或**字段特性**节点。</span><span class="sxs-lookup"><span data-stu-id="47c86-107">Property schemas define an unstructured set of **Field Element** nodes into which you promote **Record** (with simple content), **Field Element**, or **Field Attribute** nodes.</span></span> <span data-ttu-id="47c86-108">用于创建属性架构的分步说明，请参阅[如何创建属性架构](../core/how-to-create-property-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="47c86-108">For step-by-step instructions for creating a property schema, see [How to Create Property Schemas](../core/how-to-create-property-schemas.md).</span></span>  
  
 <span data-ttu-id="47c86-109">或者，可以使用**快速升级**功能，因此将自动创建并更新单个属性架构，每当你升级新**Field 元素**，**字段特性**，或**记录**（具有简单内容） 节点。</span><span class="sxs-lookup"><span data-stu-id="47c86-109">Alternatively, you can use the **Quick Promotion** feature, which will automatically create and update a single property schema whenever you promote a new **Field Element**, **Field Attribute**, or **Record** (with simple content) node.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="47c86-110">你可以将提升为这两者的字段**可分辨字段**和**属性字段**。</span><span class="sxs-lookup"><span data-stu-id="47c86-110">You can promote a field as both a **Distinguished Field** and a **Property Field**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="47c86-111">**快速升级**功能属性架构修改的方法是插入具有提升的节点的名称的新属性。</span><span class="sxs-lookup"><span data-stu-id="47c86-111">The **Quick Promotion** feature modifies the property schema by inserting a new property with the name of the promoted node.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="47c86-112">升级字段之后，请不要在架构中移动或重命名该字段。</span><span class="sxs-lookup"><span data-stu-id="47c86-112">Do not move or rename a field in the schema once you have promoted it.</span></span> <span data-ttu-id="47c86-113">如果您移动或重命名某一架构字段，BizTalk 编辑器并不会更新定义升级字段的位置的 XPath。</span><span class="sxs-lookup"><span data-stu-id="47c86-113">When you move or rename a schema field, BizTalk Editor does not update the XPath defining the location of the promoted field.</span></span>  
  
## <a name="xsd-and-clr-data-types"></a><span data-ttu-id="47c86-114">XSD 和 CLR 数据类型</span><span class="sxs-lookup"><span data-stu-id="47c86-114">XSD and CLR Data Types</span></span>  
 <span data-ttu-id="47c86-115">在某些情况下（例如在属性升级中），XSD 数据类型将升级到公共语言运行时 (CLR) 数据类型。</span><span class="sxs-lookup"><span data-stu-id="47c86-115">In some places, such as in property promotion, XSD data types are promoted to Common Language Runtime (CLR) data types.</span></span> <span data-ttu-id="47c86-116">下表显示了可升级的 XSD 数据类型以及相应的 CLR 数据类型。</span><span class="sxs-lookup"><span data-stu-id="47c86-116">The following table shows the XSD data types that can be promoted and the corresponding CLR data types.</span></span>  
  
|<span data-ttu-id="47c86-117">XSD 数据类型</span><span class="sxs-lookup"><span data-stu-id="47c86-117">XSD Data Type</span></span>|<span data-ttu-id="47c86-118">CLR 数据类型</span><span class="sxs-lookup"><span data-stu-id="47c86-118">CLR Data Type</span></span>|  
|-------------------|-------------------|  
|<span data-ttu-id="47c86-119">anyURI</span><span class="sxs-lookup"><span data-stu-id="47c86-119">anyURI</span></span>|<span data-ttu-id="47c86-120">字符串</span><span class="sxs-lookup"><span data-stu-id="47c86-120">String</span></span>|  
|<span data-ttu-id="47c86-121">Boolean</span><span class="sxs-lookup"><span data-stu-id="47c86-121">Boolean</span></span>|<span data-ttu-id="47c86-122">Boolean</span><span class="sxs-lookup"><span data-stu-id="47c86-122">Boolean</span></span>|  
|<span data-ttu-id="47c86-123">Byte</span><span class="sxs-lookup"><span data-stu-id="47c86-123">Byte</span></span>|<span data-ttu-id="47c86-124">sbyte</span><span class="sxs-lookup"><span data-stu-id="47c86-124">sbyte</span></span>|  
|<span data-ttu-id="47c86-125">日期</span><span class="sxs-lookup"><span data-stu-id="47c86-125">Date</span></span>|<span data-ttu-id="47c86-126">DateTime</span><span class="sxs-lookup"><span data-stu-id="47c86-126">DateTime</span></span>|  
|<span data-ttu-id="47c86-127">dateTime</span><span class="sxs-lookup"><span data-stu-id="47c86-127">dateTime</span></span>|<span data-ttu-id="47c86-128">DateTime</span><span class="sxs-lookup"><span data-stu-id="47c86-128">DateTime</span></span>|  
|<span data-ttu-id="47c86-129">Decimal</span><span class="sxs-lookup"><span data-stu-id="47c86-129">Decimal</span></span>|<span data-ttu-id="47c86-130">Decimal</span><span class="sxs-lookup"><span data-stu-id="47c86-130">Decimal</span></span>|  
|<span data-ttu-id="47c86-131">双精度</span><span class="sxs-lookup"><span data-stu-id="47c86-131">Double</span></span>|<span data-ttu-id="47c86-132">双精度</span><span class="sxs-lookup"><span data-stu-id="47c86-132">Double</span></span>|  
|<span data-ttu-id="47c86-133">ENTITY</span><span class="sxs-lookup"><span data-stu-id="47c86-133">ENTITY</span></span>|<span data-ttu-id="47c86-134">字符串</span><span class="sxs-lookup"><span data-stu-id="47c86-134">String</span></span>|  
|<span data-ttu-id="47c86-135">Float</span><span class="sxs-lookup"><span data-stu-id="47c86-135">Float</span></span>|<span data-ttu-id="47c86-136">Single</span><span class="sxs-lookup"><span data-stu-id="47c86-136">Single</span></span>|  
|<span data-ttu-id="47c86-137">gDay</span><span class="sxs-lookup"><span data-stu-id="47c86-137">gDay</span></span>|<span data-ttu-id="47c86-138">DateTime</span><span class="sxs-lookup"><span data-stu-id="47c86-138">DateTime</span></span>|  
|<span data-ttu-id="47c86-139">gMonth</span><span class="sxs-lookup"><span data-stu-id="47c86-139">gMonth</span></span>|<span data-ttu-id="47c86-140">DateTime</span><span class="sxs-lookup"><span data-stu-id="47c86-140">DateTime</span></span>|  
|<span data-ttu-id="47c86-141">gMonthDay</span><span class="sxs-lookup"><span data-stu-id="47c86-141">gMonthDay</span></span>|<span data-ttu-id="47c86-142">DateTime</span><span class="sxs-lookup"><span data-stu-id="47c86-142">DateTime</span></span>|  
|<span data-ttu-id="47c86-143">gYear</span><span class="sxs-lookup"><span data-stu-id="47c86-143">gYear</span></span>|<span data-ttu-id="47c86-144">DateTime</span><span class="sxs-lookup"><span data-stu-id="47c86-144">DateTime</span></span>|  
|<span data-ttu-id="47c86-145">gYearMonth</span><span class="sxs-lookup"><span data-stu-id="47c86-145">gYearMonth</span></span>|<span data-ttu-id="47c86-146">DateTime</span><span class="sxs-lookup"><span data-stu-id="47c86-146">DateTime</span></span>|  
|<span data-ttu-id="47c86-147">ID</span><span class="sxs-lookup"><span data-stu-id="47c86-147">ID</span></span>|<span data-ttu-id="47c86-148">字符串</span><span class="sxs-lookup"><span data-stu-id="47c86-148">String</span></span>|  
|<span data-ttu-id="47c86-149">IDREF</span><span class="sxs-lookup"><span data-stu-id="47c86-149">IDREF</span></span>|<span data-ttu-id="47c86-150">字符串</span><span class="sxs-lookup"><span data-stu-id="47c86-150">String</span></span>|  
|<span data-ttu-id="47c86-151">int</span><span class="sxs-lookup"><span data-stu-id="47c86-151">Int</span></span>|<span data-ttu-id="47c86-152">Int32</span><span class="sxs-lookup"><span data-stu-id="47c86-152">Int32</span></span>|  
|<span data-ttu-id="47c86-153">Integer</span><span class="sxs-lookup"><span data-stu-id="47c86-153">Integer</span></span>|<span data-ttu-id="47c86-154">Decimal</span><span class="sxs-lookup"><span data-stu-id="47c86-154">Decimal</span></span>|  
|<span data-ttu-id="47c86-155">语言</span><span class="sxs-lookup"><span data-stu-id="47c86-155">Language</span></span>|<span data-ttu-id="47c86-156">字符串</span><span class="sxs-lookup"><span data-stu-id="47c86-156">String</span></span>|  
|<span data-ttu-id="47c86-157">Name</span><span class="sxs-lookup"><span data-stu-id="47c86-157">Name</span></span>|<span data-ttu-id="47c86-158">字符串</span><span class="sxs-lookup"><span data-stu-id="47c86-158">String</span></span>|  
|<span data-ttu-id="47c86-159">NCName</span><span class="sxs-lookup"><span data-stu-id="47c86-159">NCName</span></span>|<span data-ttu-id="47c86-160">字符串</span><span class="sxs-lookup"><span data-stu-id="47c86-160">String</span></span>|  
|<span data-ttu-id="47c86-161">negativeInteger</span><span class="sxs-lookup"><span data-stu-id="47c86-161">negativeInteger</span></span>|<span data-ttu-id="47c86-162">Decimal</span><span class="sxs-lookup"><span data-stu-id="47c86-162">Decimal</span></span>|  
|<span data-ttu-id="47c86-163">NMTOKEN</span><span class="sxs-lookup"><span data-stu-id="47c86-163">NMTOKEN</span></span>|<span data-ttu-id="47c86-164">字符串</span><span class="sxs-lookup"><span data-stu-id="47c86-164">String</span></span>|  
|<span data-ttu-id="47c86-165">nonNegativeInteger</span><span class="sxs-lookup"><span data-stu-id="47c86-165">nonNegativeInteger</span></span>|<span data-ttu-id="47c86-166">Decimal</span><span class="sxs-lookup"><span data-stu-id="47c86-166">Decimal</span></span>|  
|<span data-ttu-id="47c86-167">nonPositiveInteger</span><span class="sxs-lookup"><span data-stu-id="47c86-167">nonPositiveInteger</span></span>|<span data-ttu-id="47c86-168">Decimal</span><span class="sxs-lookup"><span data-stu-id="47c86-168">Decimal</span></span>|  
|<span data-ttu-id="47c86-169">normalizedString</span><span class="sxs-lookup"><span data-stu-id="47c86-169">normalizedString</span></span>|<span data-ttu-id="47c86-170">字符串</span><span class="sxs-lookup"><span data-stu-id="47c86-170">String</span></span>|  
|<span data-ttu-id="47c86-171">NOTATION</span><span class="sxs-lookup"><span data-stu-id="47c86-171">NOTATION</span></span>|<span data-ttu-id="47c86-172">字符串</span><span class="sxs-lookup"><span data-stu-id="47c86-172">String</span></span>|  
|<span data-ttu-id="47c86-173">positiveInteger</span><span class="sxs-lookup"><span data-stu-id="47c86-173">positiveInteger</span></span>|<span data-ttu-id="47c86-174">Decimal</span><span class="sxs-lookup"><span data-stu-id="47c86-174">Decimal</span></span>|  
|<span data-ttu-id="47c86-175">QName</span><span class="sxs-lookup"><span data-stu-id="47c86-175">QName</span></span>|<span data-ttu-id="47c86-176">字符串</span><span class="sxs-lookup"><span data-stu-id="47c86-176">String</span></span>|  
|<span data-ttu-id="47c86-177">Short</span><span class="sxs-lookup"><span data-stu-id="47c86-177">Short</span></span>|<span data-ttu-id="47c86-178">Int16</span><span class="sxs-lookup"><span data-stu-id="47c86-178">Int16</span></span>|  
|<span data-ttu-id="47c86-179">字符串</span><span class="sxs-lookup"><span data-stu-id="47c86-179">String</span></span>|<span data-ttu-id="47c86-180">字符串</span><span class="sxs-lookup"><span data-stu-id="47c86-180">String</span></span>|  
|<span data-ttu-id="47c86-181">Time</span><span class="sxs-lookup"><span data-stu-id="47c86-181">Time</span></span>|<span data-ttu-id="47c86-182">DateTime</span><span class="sxs-lookup"><span data-stu-id="47c86-182">DateTime</span></span>|  
|<span data-ttu-id="47c86-183">标记</span><span class="sxs-lookup"><span data-stu-id="47c86-183">Token</span></span>|<span data-ttu-id="47c86-184">字符串</span><span class="sxs-lookup"><span data-stu-id="47c86-184">String</span></span>|  
|<span data-ttu-id="47c86-185">unsignedByte</span><span class="sxs-lookup"><span data-stu-id="47c86-185">unsignedByte</span></span>|<span data-ttu-id="47c86-186">Byte</span><span class="sxs-lookup"><span data-stu-id="47c86-186">Byte</span></span>|  
|<span data-ttu-id="47c86-187">unsignedInt</span><span class="sxs-lookup"><span data-stu-id="47c86-187">unsignedInt</span></span>|<span data-ttu-id="47c86-188">UInt32</span><span class="sxs-lookup"><span data-stu-id="47c86-188">UInt32</span></span>|  
|<span data-ttu-id="47c86-189">unsignedShort</span><span class="sxs-lookup"><span data-stu-id="47c86-189">unsignedShort</span></span>|<span data-ttu-id="47c86-190">UInt16</span><span class="sxs-lookup"><span data-stu-id="47c86-190">UInt16</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="47c86-191">base64Binary、duration、ENTITES、hexBinary、IDREFS、long、NMTOKENS 和 unsignedLong 的 XSD 数据类型不支持升级。</span><span class="sxs-lookup"><span data-stu-id="47c86-191">XSD Data Type of base64Binary, duration, ENTITES, hexBinary, IDREFS, long, NMTOKENS, and unsignedLong are not supported for promotion.</span></span>  
  
## <a name="limitations-for-promoting-properties"></a><span data-ttu-id="47c86-192">对升级属性的限制</span><span class="sxs-lookup"><span data-stu-id="47c86-192">Limitations for Promoting Properties</span></span>  
 <span data-ttu-id="47c86-193">升级属性时，请考虑以下事项：</span><span class="sxs-lookup"><span data-stu-id="47c86-193">When promoting properties, consider the following:</span></span>  
  
-   <span data-ttu-id="47c86-194">升级属性的长度限制在 256 个字符之内，而写入属性则没有长度上的限制。</span><span class="sxs-lookup"><span data-stu-id="47c86-194">Promoted properties are limited to 256 characters in length while written properties have no length limitation.</span></span>  
  
-   <span data-ttu-id="47c86-195">升级属性用于消息路由，并由于有关比较和存储效率的原因，对升级属性的大小有所限制。</span><span class="sxs-lookup"><span data-stu-id="47c86-195">Promoted properties are used in message routing and are limited in size for reasons of efficiency in comparison and storage.</span></span> <span data-ttu-id="47c86-196">尽管对写入属性的大小没有硬性限制，但如果在上下文中使用过大的值，也会对性能造成影响，因为这些值仍必须与消息一起进行处理和传递。</span><span class="sxs-lookup"><span data-stu-id="47c86-196">While written properties have no hard limits on size, using excessively large values in the context will have an impact on performance, because those values must still be processed and passed with the message.</span></span> <span data-ttu-id="47c86-197">可分辨字段便是写入属性的例子。</span><span class="sxs-lookup"><span data-stu-id="47c86-197">Distinguished Fields are the examples of written properties.</span></span>  
  
-   <span data-ttu-id="47c86-198">记录节点永远不会被提升为**可分辨字段**。</span><span class="sxs-lookup"><span data-stu-id="47c86-198">Record nodes can never be promoted as **Distinguished Fields**.</span></span>  
  
-   <span data-ttu-id="47c86-199">升级属性仅限于非重复元素/特性。</span><span class="sxs-lookup"><span data-stu-id="47c86-199">Promoted properties are restricted to non-repeating elements/attributes.</span></span>  
  
-   <span data-ttu-id="47c86-200">不要将属于同一根节点的字段升级到相同属性。</span><span class="sxs-lookup"><span data-stu-id="47c86-200">Do not promote fields belonging to the same root node to the same property.</span></span> <span data-ttu-id="47c86-201">此类升级会导致编译或部署错误。</span><span class="sxs-lookup"><span data-stu-id="47c86-201">Such promotions produce compilation or deployment errors.</span></span>  
  
-   <span data-ttu-id="47c86-202">在消息上下文内，某些属性因为没有升级而不可用。</span><span class="sxs-lookup"><span data-stu-id="47c86-202">Within a message context, there are some properties that are not available since they are not promoted.</span></span>  <span data-ttu-id="47c86-203">BTS.ReceiveLocationName 属性就是此类属性之一。</span><span class="sxs-lookup"><span data-stu-id="47c86-203">The BTS.ReceiveLocationName property is one such property.</span></span> <span data-ttu-id="47c86-204">如果您可以将新属性架构或新 BizTalk Server 对象添加到您的开发中，则有可能从业务流程内部访问该属性。</span><span class="sxs-lookup"><span data-stu-id="47c86-204">If you can add a new property schema or a new BizTalk Server project to your development it is possible to access this property from within an orchestration.</span></span>  
  
     <span data-ttu-id="47c86-205">属性值由属性目标命名空间和属性名称标识。</span><span class="sxs-lookup"><span data-stu-id="47c86-205">Property values are identified by the property target namespace and property name.</span></span>  <span data-ttu-id="47c86-206">下面的示例演示如何访问代码格式的接收位置。</span><span class="sxs-lookup"><span data-stu-id="47c86-206">The following example shows how to access the receive location in code.</span></span>  
  
     `string receiveLocationName =       pInMsg.Context.Read("ReceiveLocationName", sysNamespace);`  
  
## <a name="in-this-section"></a><span data-ttu-id="47c86-207">本节内容</span><span class="sxs-lookup"><span data-stu-id="47c86-207">In This Section</span></span>  
  
-   [<span data-ttu-id="47c86-208">如何打开提升属性对话框中</span><span class="sxs-lookup"><span data-stu-id="47c86-208">How to Open the Promote Properties Dialog Box</span></span>](../core/how-to-open-the-promote-properties-dialog-box.md)  
  
-   [<span data-ttu-id="47c86-209">如何将数据复制到可分辨的字段的消息上下文</span><span class="sxs-lookup"><span data-stu-id="47c86-209">How to Copy Data to the Message Context as Distinguished Fields</span></span>](../core/how-to-copy-data-to-the-message-context-as-distinguished-fields.md)  
  
-   [<span data-ttu-id="47c86-210">如何将数据复制到作为属性字段的消息上下文</span><span class="sxs-lookup"><span data-stu-id="47c86-210">How to Copy Data to the Message Context as Property Fields</span></span>](../core/how-to-copy-data-to-the-message-context-as-property-fields.md)