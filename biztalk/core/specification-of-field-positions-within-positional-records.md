---
title: 规范的位置记录中的字段位置 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 33c2eee3-ec30-46c5-a143-a3d2e2f265a6
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91a253c76e8f3394897514716978e1902cf2e3d8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279341"
---
# <a name="specification-of-field-positions-within-positional-records"></a><span data-ttu-id="43c49-102">位置记录中的字段位置的规范</span><span class="sxs-lookup"><span data-stu-id="43c49-102">Specification of Field Positions within Positional Records</span></span>
<span data-ttu-id="43c49-103">若要定义位置记录，必须提供有关记录中字段的位置和长度的信息。</span><span class="sxs-lookup"><span data-stu-id="43c49-103">To define a positional record, you must provide information about the positions and lengths of the fields within that record.</span></span> <span data-ttu-id="43c49-104">如果记录包含子记录，则子记录中的字段的位置和长度将汇总到包含记录的有关信息中。</span><span class="sxs-lookup"><span data-stu-id="43c49-104">If the record contains subrecords, the positions and lengths of the fields in the subrecord are rolled up to contribute to the information about the containing record.</span></span>  
  
 <span data-ttu-id="43c49-105">为指定的值的总和**位置偏移量**和**位置长度**为特定的属性**Field 元素**或**字段特性**节点确定专用于相应字段的字符数。</span><span class="sxs-lookup"><span data-stu-id="43c49-105">The sum of the values you specify for the **Positional Offset** and **Positional Length** properties for a particular **Field Element** or **Field Attribute** node determines the number of characters dedicated to the corresponding field.</span></span> <span data-ttu-id="43c49-106">涵盖记录及其所有子记录中的所有字段的一系列这样的和决定了记录中字段的边界。</span><span class="sxs-lookup"><span data-stu-id="43c49-106">The series of these sums across all of the fields in the record and any of its subrecords determine the boundaries of the fields in the records.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43c49-107">当**计数位置中字节**属性**架构**节点设置为**是**、**位置长度**和**位置偏移量**属性指定字节，而不是字符。</span><span class="sxs-lookup"><span data-stu-id="43c49-107">When the **Count Positions In Bytes** property of the **Schema** node is set to **Yes**, the **Positional Length** and **Position Offset** properties specify bytes rather than characters.</span></span>  

<span data-ttu-id="43c49-108">这些属性中查看更多细节[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="43c49-108">See more details on these properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="positional-offset-property"></a><span data-ttu-id="43c49-109">“位置偏移量”属性</span><span class="sxs-lookup"><span data-stu-id="43c49-109">Positional Offset property</span></span>  
 <span data-ttu-id="43c49-110">平面文件反汇编程序是将平面文件实例消息转换为等效的 XML 实例消息中，指定的值为**位置偏移量**属性定义将被忽略了多个字符 （或字节数）并通过在实例消息中的此位置被跳过。</span><span class="sxs-lookup"><span data-stu-id="43c49-110">When the flat file disassembler is converting a flat file instance message into an equivalent XML instance message, the value you specify for the **Positional Offset** property defines a number of characters (or bytes) that are ignored and skipped over at that position in the instance message.</span></span> <span data-ttu-id="43c49-111">换而言之，在该开始位置和长度发生的任何信息 (后者为指定的**位置偏移量**属性) 中的平面文件实例消息将不复制到的 XML 版本的消息。</span><span class="sxs-lookup"><span data-stu-id="43c49-111">In other words, any information occurring at that starting position and length (the latter as specified by the **Positional Offset** property) in the flat file instance message will not be copied into the XML version of the message.</span></span>  
  
 <span data-ttu-id="43c49-112">平面文件汇编器是将 XML 实例消息转换为等效的平面文件实例消息中，指定的值为**位置偏移量**属性定义将填入了多个字符 （或字节数）正在创建的平面文件实例消息中该起始位置处的空格字符。</span><span class="sxs-lookup"><span data-stu-id="43c49-112">When the flat file assembler is converting an XML instance message into an equivalent flat file instance message, the value you specify for the **Positional Offset** property defines a number of characters (or bytes) that are filled with space characters at that starting position within the flat file instance message being created.</span></span> <span data-ttu-id="43c49-113">始终使用空格字符来填充偏移位置；所使用的字符不可配置。</span><span class="sxs-lookup"><span data-stu-id="43c49-113">The space character is always used to fill offset positions; the character used is not configurable.</span></span>  
  
 <span data-ttu-id="43c49-114">**位置偏移量**属性提供了灵活性解释的位置记录的内容。</span><span class="sxs-lookup"><span data-stu-id="43c49-114">The **Positional Offset** property provides flexibility for interpreting the contents of positional records.</span></span> <span data-ttu-id="43c49-115">实际上，此属性允许您忽略位于将此属性设置为非零值的字段前面的任何固定长度数据。</span><span class="sxs-lookup"><span data-stu-id="43c49-115">Essentially, this property allows you to ignore any fixed length data that precedes the field for which it is set to a nonzero value.</span></span> <span data-ttu-id="43c49-116">该固定长度数据可能是一个或多个不需要包括在平面文件实例消息的 XML 等效消息中的整个数据字段或某些类型的常数数据，例如，与字段关联的标记。</span><span class="sxs-lookup"><span data-stu-id="43c49-116">That fixed length data might be one or more entire fields of data or some type of constant data, such as a tag associated with the field, that does not need to be included in the XML equivalent of the flat file instance message.</span></span> <span data-ttu-id="43c49-117">有关详细信息，请参阅后面的示例。</span><span class="sxs-lookup"><span data-stu-id="43c49-117">For more information, see the example that follows.</span></span>  
  
## <a name="positional-length-property"></a><span data-ttu-id="43c49-118">“位置长度”属性</span><span class="sxs-lookup"><span data-stu-id="43c49-118">Positional Length property</span></span>  
 <span data-ttu-id="43c49-119">平面文件反汇编程序是将平面文件实例消息转换为等效的 XML 实例消息中，指定的值为**位置长度**属性定义是字符 （或字节数） 数与实例消息中的此位置处的字段相关联。</span><span class="sxs-lookup"><span data-stu-id="43c49-119">When the flat file disassembler is converting a flat file instance message into an equivalent XML instance message, the value you specify for the **Positional Length** property defines the number of characters (or bytes) that are associated with the field at that position in the instance message.</span></span> <span data-ttu-id="43c49-120">上发生，平面文件实例消息中起始位置和长度构成的字段中，根据提供由关联的附加信息的数据的信息**理由**和**填充字符**属性。</span><span class="sxs-lookup"><span data-stu-id="43c49-120">The information occurring at that starting position and length in the flat file instance message constitutes the data in the field, subject to the additional information provided by the associated **Justification** and **Pad Character** properties.</span></span> <span data-ttu-id="43c49-121">有关对齐方式和字段填充的更多概念信息，请参阅[字段理由](../core/field-justification.md)和[字段填充](../core/field-padding.md)。</span><span class="sxs-lookup"><span data-stu-id="43c49-121">For more conceptual information about justification and field padding, see [Field Justification](../core/field-justification.md) and [Field Padding](../core/field-padding.md).</span></span>  
  
 <span data-ttu-id="43c49-122">平面文件汇编器是将 XML 实例消息转换为等效的平面文件实例消息中，指定的值为**位置长度**属性定义了多个字符 （或字节） 可用于编写含该字段关联的数据。</span><span class="sxs-lookup"><span data-stu-id="43c49-122">When the flat file assembler is converting an XML instance message into an equivalent flat file instance message, the value you specify for the **Positional Length** property defines a number of characters (or bytes) available for writing the data associated with that field.</span></span> <span data-ttu-id="43c49-123">如果数据字符数比指定的字段长度要少，则将使用相关的填充字符来填充差额。</span><span class="sxs-lookup"><span data-stu-id="43c49-123">If there are fewer data characters than the specified length of the field, the relevant pad character is used to fill up the difference.</span></span> <span data-ttu-id="43c49-124">如果有多个数据字符数应少于指定的字段长度的开头或末尾的数据将被截断基于的设置**理由**属性并且不包含在平面文件实例消息正在构造。</span><span class="sxs-lookup"><span data-stu-id="43c49-124">If there are more data characters than the specified length of the field, the beginning or end of the data is truncated based on the setting of the **Justification** property and not included in the flat file instance message being constructed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43c49-125">左对齐数据的尾部将被截断并丢弃。</span><span class="sxs-lookup"><span data-stu-id="43c49-125">The trailing portion of left-aligned data is truncated and discarded.</span></span> <span data-ttu-id="43c49-126">右对齐数据的头部将被截断并丢弃。</span><span class="sxs-lookup"><span data-stu-id="43c49-126">The leading portion of right-aligned data is truncated and discarded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="43c49-127">示例</span><span class="sxs-lookup"><span data-stu-id="43c49-127">Example</span></span>  
 <span data-ttu-id="43c49-128">假设记录的字段定义如下：</span><span class="sxs-lookup"><span data-stu-id="43c49-128">Consider the following field definitions for a record.</span></span>  
  
|<span data-ttu-id="43c49-129">字段节点名称</span><span class="sxs-lookup"><span data-stu-id="43c49-129">Field node name</span></span>|<span data-ttu-id="43c49-130">Offset</span><span class="sxs-lookup"><span data-stu-id="43c49-130">Offset</span></span>|<span data-ttu-id="43c49-131">长度</span><span class="sxs-lookup"><span data-stu-id="43c49-131">Length</span></span>|<span data-ttu-id="43c49-132">填充字符</span><span class="sxs-lookup"><span data-stu-id="43c49-132">Pad Character</span></span>|<span data-ttu-id="43c49-133">对齐</span><span class="sxs-lookup"><span data-stu-id="43c49-133">Justification</span></span>|  
|---------------------|------------|------------|-------------------|-------------------|  
|<span data-ttu-id="43c49-134">Field1</span><span class="sxs-lookup"><span data-stu-id="43c49-134">Field1</span></span>|<span data-ttu-id="43c49-135">0</span><span class="sxs-lookup"><span data-stu-id="43c49-135">0</span></span>|<span data-ttu-id="43c49-136">6</span><span class="sxs-lookup"><span data-stu-id="43c49-136">6</span></span>|<span data-ttu-id="43c49-137">默认值（空格）</span><span class="sxs-lookup"><span data-stu-id="43c49-137">Default (space)</span></span>|<span data-ttu-id="43c49-138">Left</span><span class="sxs-lookup"><span data-stu-id="43c49-138">Left</span></span>|  
|<span data-ttu-id="43c49-139">Field2</span><span class="sxs-lookup"><span data-stu-id="43c49-139">Field2</span></span>|<span data-ttu-id="43c49-140">0</span><span class="sxs-lookup"><span data-stu-id="43c49-140">0</span></span>|<span data-ttu-id="43c49-141">4</span><span class="sxs-lookup"><span data-stu-id="43c49-141">4</span></span>|*|<span data-ttu-id="43c49-142">Right</span><span class="sxs-lookup"><span data-stu-id="43c49-142">Right</span></span>|  
|<span data-ttu-id="43c49-143">Field3</span><span class="sxs-lookup"><span data-stu-id="43c49-143">Field3</span></span>|<span data-ttu-id="43c49-144">2</span><span class="sxs-lookup"><span data-stu-id="43c49-144">2</span></span>|<span data-ttu-id="43c49-145">6</span><span class="sxs-lookup"><span data-stu-id="43c49-145">6</span></span>|*|<span data-ttu-id="43c49-146">Left</span><span class="sxs-lookup"><span data-stu-id="43c49-146">Left</span></span>|  
|<span data-ttu-id="43c49-147">Field4</span><span class="sxs-lookup"><span data-stu-id="43c49-147">Field4</span></span>|<span data-ttu-id="43c49-148">4</span><span class="sxs-lookup"><span data-stu-id="43c49-148">4</span></span>|<span data-ttu-id="43c49-149">6</span><span class="sxs-lookup"><span data-stu-id="43c49-149">6</span></span>|<span data-ttu-id="43c49-150">默认值（空格）</span><span class="sxs-lookup"><span data-stu-id="43c49-150">Default (space)</span></span>|<span data-ttu-id="43c49-151">Right</span><span class="sxs-lookup"><span data-stu-id="43c49-151">Right</span></span>|  
  
 <span data-ttu-id="43c49-152">并且，在具有这些字段定义的记录的起点遇到以下字符流（第一行用于对字符位置计数）：</span><span class="sxs-lookup"><span data-stu-id="43c49-152">And the following stream of characters is encountered at the starting point of a record with these field definitions (the first line is for counting character positions).</span></span>  
  
```  
123456789012345678901234567890123456789012345678901234567890  
abc   **12345678**skip  here  
```  
  
 <span data-ttu-id="43c49-153">将这些字段定义应用于此示例记录数据时，平面文件拆装器将生成以下 XML 等效消息（数据以粗体显示）：</span><span class="sxs-lookup"><span data-stu-id="43c49-153">When these field definitions are applied to this sample record data, the flat file disassembler produces the following XML equivalent (with the data shown in bold type).</span></span>  
  
```  
<Field1>abc</Field1>  
<Field2>12</Field2>  
<Field3>5678</Field3>  
<Field4>here</Field4>  
```  
  
 <span data-ttu-id="43c49-154">以下所观察到的现象展示了是如何对此数据进行解析的：</span><span class="sxs-lookup"><span data-stu-id="43c49-154">The following observations are relevant to how this data is parsed:</span></span>  
  
-   <span data-ttu-id="43c49-155">与 Field1 关联的字符 （长度与未偏移量 6） 是"`abc` "，但空间不包含在 XML 中，因为空间字符是 Field1 （默认值） 填充字符并且 Field1 定义为左对齐。</span><span class="sxs-lookup"><span data-stu-id="43c49-155">The characters associated with Field1 (length 6 with no offset) are "`abc` ", but the spaces are not included in the XML because the space character is the (default) pad character for Field1 and Field1 is defined as left-aligned.</span></span>  
  
-   <span data-ttu-id="43c49-156">与 Field2（长度为 4，没有偏移量）关联的字符为“`**12`”，但在 XML 中不包括星号，因为星号字符是为 Field2 定义的填充字符，并且 Field2 被定义为右对齐。</span><span class="sxs-lookup"><span data-stu-id="43c49-156">The characters associated with Field2 (length 4 with no offset) are "`**12`", but the asterisks are not included in the XML because the asterisk character is the pad character defined for Field2 and Field2 is defined as right-aligned.</span></span>  
  
-   <span data-ttu-id="43c49-157">与 Field3（长度为 6，偏移量为 2）关联的字符为“`345678**`”，但因为存在偏移量，所以在 XML 中不包括 3 和 4。</span><span class="sxs-lookup"><span data-stu-id="43c49-157">The characters associated with Field3 (length 6 plus an offset of 2) are "`345678**`", but the 3 and 4 are not included in the XML because of the offset.</span></span> <span data-ttu-id="43c49-158">在 XML 中也不包括星号，因为星号字符是为 Field2 定义的填充字符，并且 Field2 被定义为左对齐。</span><span class="sxs-lookup"><span data-stu-id="43c49-158">The asterisks are also not included in the XML because the asterisk character is the pad character defined for Field2 and Field2 is defined as left-aligned.</span></span>  
  
-   <span data-ttu-id="43c49-159">与 Field4（长度为 6，偏移量为 4）关联的字符为“`skip  here`”，但因为存在偏移量，所以在 XML 中不包括字符序列“`skip`”。</span><span class="sxs-lookup"><span data-stu-id="43c49-159">The characters associated with Field4 (length 6 plus an offset of 4) are "`skip  here`", but the character sequence "`skip`" is not included in the XML because of the offset.</span></span> <span data-ttu-id="43c49-160">在 XML 中也不包括两个空格字符，因为空格字符是 Field4 的（默认）填充字符，并且 Field4 被定义为右对齐。</span><span class="sxs-lookup"><span data-stu-id="43c49-160">The two space characters are also not included in the XML because the space character is the (default) pad character for Field4 and Field4 is defined as right-aligned.</span></span>  
  
 <span data-ttu-id="43c49-161">如果在此示例中的平面文件反汇编程序所生成的 XML 传递给使用相同的字段定义的平面文件汇编，生成相同的平面文件数据，有两个例外： 丢弃的偏移量序列 34 和跳过将填入空格字符(用指示`^`以下数据行中的字符)。</span><span class="sxs-lookup"><span data-stu-id="43c49-161">If the XML produced by the flat file disassembler in this example is passed to the flat file assembler using the same field definitions, the same flat file data is produced, with two exceptions: the discarded offset sequences 34 and skip are filled with space characters (indicated with the `^` character in the line following the data).</span></span>  
  
```  
123456789012345678901234567890123456789012345678901234567890  
abc   **12  5678**      here  
          ^^      ^^^^  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="43c49-162">另请参阅</span><span class="sxs-lookup"><span data-stu-id="43c49-162">See Also</span></span>  
-  [<span data-ttu-id="43c49-163">字段注意事项</span><span class="sxs-lookup"><span data-stu-id="43c49-163">Field Considerations</span></span>](../core/field-considerations.md)    
-  [<span data-ttu-id="43c49-164">字段理由</span><span class="sxs-lookup"><span data-stu-id="43c49-164">Field Justification</span></span>](../core/field-justification.md)   
-  [<span data-ttu-id="43c49-165">字段填充</span><span class="sxs-lookup"><span data-stu-id="43c49-165">Field Padding</span></span>](../core/field-padding.md)   
- <span data-ttu-id="43c49-166">以下属性的详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:</span><span class="sxs-lookup"><span data-stu-id="43c49-166">More info on the following properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:</span></span>  
    - <span data-ttu-id="43c49-167">以字节为单位 （节点属性的平面文件架构） 的计数位置</span><span class="sxs-lookup"><span data-stu-id="43c49-167">Count Positions In Bytes (Node Property of Flat File Schemas)</span></span>  
    - <span data-ttu-id="43c49-168">两端对齐 （的平面文件架构的节点属性）</span><span class="sxs-lookup"><span data-stu-id="43c49-168">Justification (Node Property of Flat File Schemas)</span></span>  
    - <span data-ttu-id="43c49-169">填充字符 （的平面文件架构的节点属性）</span><span class="sxs-lookup"><span data-stu-id="43c49-169">Pad Character (Node Property of Flat File Schemas)</span></span> 
    - <span data-ttu-id="43c49-170">位置偏移量 （的平面文件架构的节点属性）</span><span class="sxs-lookup"><span data-stu-id="43c49-170">Positional Offset (Node Property of Flat File Schemas)</span></span>
    - <span data-ttu-id="43c49-171">位置的长度 （的平面文件架构的节点属性）</span><span class="sxs-lookup"><span data-stu-id="43c49-171">Positional Length (Node Property of Flat File Schemas)</span></span>