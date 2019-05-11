---
title: 位置记录中的字段位置规范 |Microsoft Docs
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
ms.openlocfilehash: 7ba66ea6d0efde6eaa4b7103624c092d65c4d8b6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243110"
---
# <a name="specification-of-field-positions-within-positional-records"></a><span data-ttu-id="c6c8c-102">位置记录中的字段位置规范</span><span class="sxs-lookup"><span data-stu-id="c6c8c-102">Specification of Field Positions within Positional Records</span></span>
<span data-ttu-id="c6c8c-103">若要定义位置记录，必须提供有关位置和长度的记录中字段的信息。</span><span class="sxs-lookup"><span data-stu-id="c6c8c-103">To define a positional record, you must provide information about the positions and lengths of the fields within that record.</span></span> <span data-ttu-id="c6c8c-104">如果该记录包含子记录，位置和长度将汇总中的字段将累加起来，以参与到包含记录的有关信息。</span><span class="sxs-lookup"><span data-stu-id="c6c8c-104">If the record contains subrecords, the positions and lengths of the fields in the subrecord are rolled up to contribute to the information about the containing record.</span></span>  
  
 <span data-ttu-id="c6c8c-105">为指定的值的总和**位置偏移量**并**位置长度**为特定**字段元素**或**字段属性**节点确定专用于相应字段的字符数。</span><span class="sxs-lookup"><span data-stu-id="c6c8c-105">The sum of the values you specify for the **Positional Offset** and **Positional Length** properties for a particular **Field Element** or **Field Attribute** node determines the number of characters dedicated to the corresponding field.</span></span> <span data-ttu-id="c6c8c-106">这些涵盖的所有记录中字段和任何其子记录的一系列确定记录中字段的边界。</span><span class="sxs-lookup"><span data-stu-id="c6c8c-106">The series of these sums across all of the fields in the record and any of its subrecords determine the boundaries of the fields in the records.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c6c8c-107">当**数**的属性**架构**节点设置为**是**，则**位置长度**和**位置偏移量**属性指定字节数而不是字符。</span><span class="sxs-lookup"><span data-stu-id="c6c8c-107">When the **Count Positions In Bytes** property of the **Schema** node is set to **Yes**, the **Positional Length** and **Position Offset** properties specify bytes rather than characters.</span></span>  

<span data-ttu-id="c6c8c-108">查看更多详细信息，这些属性[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。</span><span class="sxs-lookup"><span data-stu-id="c6c8c-108">See more details on these properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="positional-offset-property"></a><span data-ttu-id="c6c8c-109">位置偏移量属性</span><span class="sxs-lookup"><span data-stu-id="c6c8c-109">Positional Offset property</span></span>  
 <span data-ttu-id="c6c8c-110">当平面文件拆装器将转换为等效的 XML 实例消息转换为平面文件实例消息时，指定的值为**位置偏移量**属性定义了许多字符 （或字节数），将被忽略并通过在该位置在实例消息中已跳过。</span><span class="sxs-lookup"><span data-stu-id="c6c8c-110">When the flat file disassembler is converting a flat file instance message into an equivalent XML instance message, the value you specify for the **Positional Offset** property defines a number of characters (or bytes) that are ignored and skipped over at that position in the instance message.</span></span> <span data-ttu-id="c6c8c-111">换而言之，在该起始位置和长度上出现的所有信息 (由指定后者**位置偏移量**属性) 中的平面文件实例消息不会复制到消息的 XML 版本。</span><span class="sxs-lookup"><span data-stu-id="c6c8c-111">In other words, any information occurring at that starting position and length (the latter as specified by the **Positional Offset** property) in the flat file instance message will not be copied into the XML version of the message.</span></span>  
  
 <span data-ttu-id="c6c8c-112">当平面文件组装器将 XML 实例消息转换成等效的平面文件实例消息时，指定的值为**位置偏移量**属性定义了许多字符 （或字节数） 填充的正在创建平面文件实例消息中的起始位置的空格字符。</span><span class="sxs-lookup"><span data-stu-id="c6c8c-112">When the flat file assembler is converting an XML instance message into an equivalent flat file instance message, the value you specify for the **Positional Offset** property defines a number of characters (or bytes) that are filled with space characters at that starting position within the flat file instance message being created.</span></span> <span data-ttu-id="c6c8c-113">始终使用空格字符来填充偏移的位置;使用的字符不是可配置的。</span><span class="sxs-lookup"><span data-stu-id="c6c8c-113">The space character is always used to fill offset positions; the character used is not configurable.</span></span>  
  
 <span data-ttu-id="c6c8c-114">**位置偏移量**属性提供了用于解释位置记录的内容的灵活性。</span><span class="sxs-lookup"><span data-stu-id="c6c8c-114">The **Positional Offset** property provides flexibility for interpreting the contents of positional records.</span></span> <span data-ttu-id="c6c8c-115">从根本上来说，此属性可以忽略任何为其它设置为非零值的字段前面的固定的长度数据。</span><span class="sxs-lookup"><span data-stu-id="c6c8c-115">Essentially, this property allows you to ignore any fixed length data that precedes the field for which it is set to a nonzero value.</span></span> <span data-ttu-id="c6c8c-116">固定的长度数据可能是一个或多个的整个数据字段或某种类型的常数数据，例如使用的字段，不需要的平面文件实例消息的 XML 等效项包括相关联的标记。</span><span class="sxs-lookup"><span data-stu-id="c6c8c-116">That fixed length data might be one or more entire fields of data or some type of constant data, such as a tag associated with the field, that does not need to be included in the XML equivalent of the flat file instance message.</span></span> <span data-ttu-id="c6c8c-117">有关详细信息，请参阅下面的示例。</span><span class="sxs-lookup"><span data-stu-id="c6c8c-117">For more information, see the example that follows.</span></span>  
  
## <a name="positional-length-property"></a><span data-ttu-id="c6c8c-118">位置长度属性</span><span class="sxs-lookup"><span data-stu-id="c6c8c-118">Positional Length property</span></span>  
 <span data-ttu-id="c6c8c-119">当平面文件拆装器将转换为等效的 XML 实例消息转换为平面文件实例消息时，指定的值为**位置长度**属性定义数目的字符 （或字节数）与实例消息中的位置处的字段相关联。</span><span class="sxs-lookup"><span data-stu-id="c6c8c-119">When the flat file disassembler is converting a flat file instance message into an equivalent XML instance message, the value you specify for the **Positional Length** property defines the number of characters (or bytes) that are associated with the field at that position in the instance message.</span></span> <span data-ttu-id="c6c8c-120">发生在平面文件实例消息中起始位置和长度构成了受提供由关联的附加信息的字段中的数据的信息**理由**和**填充字符**属性。</span><span class="sxs-lookup"><span data-stu-id="c6c8c-120">The information occurring at that starting position and length in the flat file instance message constitutes the data in the field, subject to the additional information provided by the associated **Justification** and **Pad Character** properties.</span></span> <span data-ttu-id="c6c8c-121">有关对齐和字段填充的更多概念信息，请参阅[字段对齐](../core/field-justification.md)并[字段填充](../core/field-padding.md)。</span><span class="sxs-lookup"><span data-stu-id="c6c8c-121">For more conceptual information about justification and field padding, see [Field Justification](../core/field-justification.md) and [Field Padding](../core/field-padding.md).</span></span>  
  
 <span data-ttu-id="c6c8c-122">当平面文件组装器将 XML 实例消息转换成等效的平面文件实例消息时，指定的值为**位置长度**属性定义数个字符 （或字节数） 可用于编写与该字段关联的数据。</span><span class="sxs-lookup"><span data-stu-id="c6c8c-122">When the flat file assembler is converting an XML instance message into an equivalent flat file instance message, the value you specify for the **Positional Length** property defines a number of characters (or bytes) available for writing the data associated with that field.</span></span> <span data-ttu-id="c6c8c-123">如果有较少的数据字符数比指定字段长度，相关的填充字符用于填充差额。</span><span class="sxs-lookup"><span data-stu-id="c6c8c-123">If there are fewer data characters than the specified length of the field, the relevant pad character is used to fill up the difference.</span></span> <span data-ttu-id="c6c8c-124">如果有多个数据字符数比指定字段长度的开头或结尾的数据将被截断的设置的基础**理由**属性，不包含在平面文件实例消息正在构造。</span><span class="sxs-lookup"><span data-stu-id="c6c8c-124">If there are more data characters than the specified length of the field, the beginning or end of the data is truncated based on the setting of the **Justification** property and not included in the flat file instance message being constructed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c6c8c-125">左对齐数据的尾部将被截断并丢弃。</span><span class="sxs-lookup"><span data-stu-id="c6c8c-125">The trailing portion of left-aligned data is truncated and discarded.</span></span> <span data-ttu-id="c6c8c-126">右对齐数据的前导部分是被截断并丢弃。</span><span class="sxs-lookup"><span data-stu-id="c6c8c-126">The leading portion of right-aligned data is truncated and discarded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c6c8c-127">示例</span><span class="sxs-lookup"><span data-stu-id="c6c8c-127">Example</span></span>  
 <span data-ttu-id="c6c8c-128">请考虑以下字段定义为一条记录。</span><span class="sxs-lookup"><span data-stu-id="c6c8c-128">Consider the following field definitions for a record.</span></span>  
  
|<span data-ttu-id="c6c8c-129">字段节点名称</span><span class="sxs-lookup"><span data-stu-id="c6c8c-129">Field node name</span></span>|<span data-ttu-id="c6c8c-130">Offset</span><span class="sxs-lookup"><span data-stu-id="c6c8c-130">Offset</span></span>|<span data-ttu-id="c6c8c-131">长度</span><span class="sxs-lookup"><span data-stu-id="c6c8c-131">Length</span></span>|<span data-ttu-id="c6c8c-132">填充字符</span><span class="sxs-lookup"><span data-stu-id="c6c8c-132">Pad Character</span></span>|<span data-ttu-id="c6c8c-133">对齐</span><span class="sxs-lookup"><span data-stu-id="c6c8c-133">Justification</span></span>|  
|---------------------|------------|------------|-------------------|-------------------|  
|<span data-ttu-id="c6c8c-134">Field1</span><span class="sxs-lookup"><span data-stu-id="c6c8c-134">Field1</span></span>|<span data-ttu-id="c6c8c-135">0</span><span class="sxs-lookup"><span data-stu-id="c6c8c-135">0</span></span>|<span data-ttu-id="c6c8c-136">6</span><span class="sxs-lookup"><span data-stu-id="c6c8c-136">6</span></span>|<span data-ttu-id="c6c8c-137">默认值 （空格）</span><span class="sxs-lookup"><span data-stu-id="c6c8c-137">Default (space)</span></span>|<span data-ttu-id="c6c8c-138">Left</span><span class="sxs-lookup"><span data-stu-id="c6c8c-138">Left</span></span>|  
|<span data-ttu-id="c6c8c-139">字段 2</span><span class="sxs-lookup"><span data-stu-id="c6c8c-139">Field2</span></span>|<span data-ttu-id="c6c8c-140">0</span><span class="sxs-lookup"><span data-stu-id="c6c8c-140">0</span></span>|<span data-ttu-id="c6c8c-141">4</span><span class="sxs-lookup"><span data-stu-id="c6c8c-141">4</span></span>|*|<span data-ttu-id="c6c8c-142">Right</span><span class="sxs-lookup"><span data-stu-id="c6c8c-142">Right</span></span>|  
|<span data-ttu-id="c6c8c-143">Field3</span><span class="sxs-lookup"><span data-stu-id="c6c8c-143">Field3</span></span>|<span data-ttu-id="c6c8c-144">2</span><span class="sxs-lookup"><span data-stu-id="c6c8c-144">2</span></span>|<span data-ttu-id="c6c8c-145">6</span><span class="sxs-lookup"><span data-stu-id="c6c8c-145">6</span></span>|*|<span data-ttu-id="c6c8c-146">Left</span><span class="sxs-lookup"><span data-stu-id="c6c8c-146">Left</span></span>|  
|<span data-ttu-id="c6c8c-147">Field4</span><span class="sxs-lookup"><span data-stu-id="c6c8c-147">Field4</span></span>|<span data-ttu-id="c6c8c-148">4</span><span class="sxs-lookup"><span data-stu-id="c6c8c-148">4</span></span>|<span data-ttu-id="c6c8c-149">6</span><span class="sxs-lookup"><span data-stu-id="c6c8c-149">6</span></span>|<span data-ttu-id="c6c8c-150">默认值 （空格）</span><span class="sxs-lookup"><span data-stu-id="c6c8c-150">Default (space)</span></span>|<span data-ttu-id="c6c8c-151">Right</span><span class="sxs-lookup"><span data-stu-id="c6c8c-151">Right</span></span>|  
  
 <span data-ttu-id="c6c8c-152">并在这些字段定义 （第一行是适用于计数字符位置） 的记录的起点遇到以下字符流。</span><span class="sxs-lookup"><span data-stu-id="c6c8c-152">And the following stream of characters is encountered at the starting point of a record with these field definitions (the first line is for counting character positions).</span></span>  
  
```  
123456789012345678901234567890123456789012345678901234567890  
abc   **12345678**skip  here  
```  
  
 <span data-ttu-id="c6c8c-153">这些字段定义应用于此示例记录数据时，平面文件拆装器将生成以下 XML 等效 （具有以粗体显示的数据）。</span><span class="sxs-lookup"><span data-stu-id="c6c8c-153">When these field definitions are applied to this sample record data, the flat file disassembler produces the following XML equivalent (with the data shown in bold type).</span></span>  
  
```  
<Field1>abc</Field1>  
<Field2>12</Field2>  
<Field3>5678</Field3>  
<Field4>here</Field4>  
```  
  
 <span data-ttu-id="c6c8c-154">以下观察值是与此数据的分析方式：</span><span class="sxs-lookup"><span data-stu-id="c6c8c-154">The following observations are relevant to how this data is parsed:</span></span>  
  
- <span data-ttu-id="c6c8c-155">与 Field1 关联的字符 （长度为 6，没有偏移量） 是"`abc` "，但因为空格字符是 Field1 的 （默认值） 填充字符，并且 Field1 被定义为左对齐，在 XML 中不包括空格。</span><span class="sxs-lookup"><span data-stu-id="c6c8c-155">The characters associated with Field1 (length 6 with no offset) are "`abc` ", but the spaces are not included in the XML because the space character is the (default) pad character for Field1 and Field1 is defined as left-aligned.</span></span>  
  
- <span data-ttu-id="c6c8c-156">与 Field2 关联的字符 （长度为 4，没有偏移量） 是"`**12`"，但因为星号字符是为 Field2 定义的填充字符，并且 Field2 被定义为右对齐，在 XML 中不包括星号。</span><span class="sxs-lookup"><span data-stu-id="c6c8c-156">The characters associated with Field2 (length 4 with no offset) are "`**12`", but the asterisks are not included in the XML because the asterisk character is the pad character defined for Field2 and Field2 is defined as right-aligned.</span></span>  
  
- <span data-ttu-id="c6c8c-157">与 Field3 关联的字符 （长度为 6 再加上偏移量为 2） 将"`345678**`"，但 3 和 4 是 XML 中不包括由于偏移量。</span><span class="sxs-lookup"><span data-stu-id="c6c8c-157">The characters associated with Field3 (length 6 plus an offset of 2) are "`345678**`", but the 3 and 4 are not included in the XML because of the offset.</span></span> <span data-ttu-id="c6c8c-158">包括星号，也不在 XML 中因为星号字符是为 Field2 定义的填充字符，并且 Field2 被定义为左对齐。</span><span class="sxs-lookup"><span data-stu-id="c6c8c-158">The asterisks are also not included in the XML because the asterisk character is the pad character defined for Field2 and Field2 is defined as left-aligned.</span></span>  
  
- <span data-ttu-id="c6c8c-159">与 Field4 关联的字符 （长度为 6 再加上偏移量为 4） 将"`skip  here`"，但字符序列"`skip`"由于偏移量不包含在 XML 中。</span><span class="sxs-lookup"><span data-stu-id="c6c8c-159">The characters associated with Field4 (length 6 plus an offset of 4) are "`skip  here`", but the character sequence "`skip`" is not included in the XML because of the offset.</span></span> <span data-ttu-id="c6c8c-160">两个空格字符也不包括在 XML 中因为空格字符是 Field4 的 （默认值） 填充字符，并且 Field4 被定义为右对齐。</span><span class="sxs-lookup"><span data-stu-id="c6c8c-160">The two space characters are also not included in the XML because the space character is the (default) pad character for Field4 and Field4 is defined as right-aligned.</span></span>  
  
  <span data-ttu-id="c6c8c-161">如果在此示例中的平面文件拆装器生成的 XML 传递给使用相同的字段定义的平面文件组装器，生成相同的平面文件数据，但以下两点除外： 被丢弃的偏移序列 34 和跳过用空格字符填充(用`^`字符后面的数据行中)。</span><span class="sxs-lookup"><span data-stu-id="c6c8c-161">If the XML produced by the flat file disassembler in this example is passed to the flat file assembler using the same field definitions, the same flat file data is produced, with two exceptions: the discarded offset sequences 34 and skip are filled with space characters (indicated with the `^` character in the line following the data).</span></span>  
  
```  
123456789012345678901234567890123456789012345678901234567890  
abc   **12  5678**      here  
          ^^      ^^^^  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="c6c8c-162">请参阅</span><span class="sxs-lookup"><span data-stu-id="c6c8c-162">See Also</span></span>  
- [<span data-ttu-id="c6c8c-163">字段注意事项</span><span class="sxs-lookup"><span data-stu-id="c6c8c-163">Field Considerations</span></span>](../core/field-considerations.md)    
- [<span data-ttu-id="c6c8c-164">字段对齐</span><span class="sxs-lookup"><span data-stu-id="c6c8c-164">Field Justification</span></span>](../core/field-justification.md)   
- [<span data-ttu-id="c6c8c-165">字段填充</span><span class="sxs-lookup"><span data-stu-id="c6c8c-165">Field Padding</span></span>](../core/field-padding.md)   
- <span data-ttu-id="c6c8c-166">以下属性的详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:</span><span class="sxs-lookup"><span data-stu-id="c6c8c-166">More info on the following properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]:</span></span>  
    - <span data-ttu-id="c6c8c-167">以字节为单位 （平面文件架构的节点属性） 为单位计算位置</span><span class="sxs-lookup"><span data-stu-id="c6c8c-167">Count Positions In Bytes (Node Property of Flat File Schemas)</span></span>  
    - <span data-ttu-id="c6c8c-168">对齐 （平面文件架构的节点属性）</span><span class="sxs-lookup"><span data-stu-id="c6c8c-168">Justification (Node Property of Flat File Schemas)</span></span>  
    - <span data-ttu-id="c6c8c-169">填充字符 （平面文件架构的节点属性）</span><span class="sxs-lookup"><span data-stu-id="c6c8c-169">Pad Character (Node Property of Flat File Schemas)</span></span> 
    - <span data-ttu-id="c6c8c-170">位置偏移量 （平面文件架构的节点属性）</span><span class="sxs-lookup"><span data-stu-id="c6c8c-170">Positional Offset (Node Property of Flat File Schemas)</span></span>
    - <span data-ttu-id="c6c8c-171">位置长度 （平面文件架构的节点属性）</span><span class="sxs-lookup"><span data-stu-id="c6c8c-171">Positional Length (Node Property of Flat File Schemas)</span></span>