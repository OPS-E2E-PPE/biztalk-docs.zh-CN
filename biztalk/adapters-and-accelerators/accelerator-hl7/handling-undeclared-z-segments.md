---
title: "处理未声明的 Z 段 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Z segments, 2.X schemas
- 2.X schemas, undeclared Z segments
- segments, undeclared [Z objects]
- Z objects, undeclared segments
ms.assetid: 8878bc93-1833-4bfc-b80e-305e4144739e
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ff982aedee39ed60820a9f03db11d7e4d051a34
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="handling-undeclared-z-segments"></a><span data-ttu-id="bcc6d-102">处理未声明的 Z 段</span><span class="sxs-lookup"><span data-stu-id="bcc6d-102">Handling Undeclared Z Segments</span></span>
<span data-ttu-id="bcc6d-103">有两种类型的 Z 段： 声明 Z 段和未声明的 Z 段。</span><span class="sxs-lookup"><span data-stu-id="bcc6d-103">There are two types of Z segments: declared Z segments and undeclared Z segments.</span></span> <span data-ttu-id="bcc6d-104">尽管它们是类似方法，在用于本地目的，它们是非常不同中如何使用它们。</span><span class="sxs-lookup"><span data-stu-id="bcc6d-104">While they are similar in that you use them for local purposes, they are very different in how you use them.</span></span>  
  
 <span data-ttu-id="bcc6d-105">在消息架构中，包括声明的 Z 段的定义和[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 使用它来处理一条消息，就像由 HL7 标准定义的架构一样。</span><span class="sxs-lookup"><span data-stu-id="bcc6d-105">You include the definition of a declared Z segment in a message schema, and [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) uses it to process a message, just like a schema defined by the HL7 standard.</span></span> <span data-ttu-id="bcc6d-106">任何架构都没有定义一个未声明的 Z 段。</span><span class="sxs-lookup"><span data-stu-id="bcc6d-106">No schema defines an undeclared Z segment.</span></span> <span data-ttu-id="bcc6d-107">包含一条消息，末尾未声明的 Z 段和[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]传递而不会处理针对的架构。</span><span class="sxs-lookup"><span data-stu-id="bcc6d-107">You include an undeclared Z segment at the end of a message, and [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] passes through without processing it against a schema.</span></span> <span data-ttu-id="bcc6d-108">分析器和序列化程序不会验证它。</span><span class="sxs-lookup"><span data-stu-id="bcc6d-108">The parser and serializer do not validate it.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="bcc6d-109">会将其视为二进制大型对象 (BLOB)。</span><span class="sxs-lookup"><span data-stu-id="bcc6d-109"> treats it as a binary large object (BLOB).</span></span> <span data-ttu-id="bcc6d-110">唯一检查[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]未上未声明 Z 段验证 BLOB 不包括任何现有的三个字符架构标记。</span><span class="sxs-lookup"><span data-stu-id="bcc6d-110">The only check that [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] does on an undeclared Z segment is verifying that the BLOB does not include any existing three-character schema tag.</span></span>  
  
 <span data-ttu-id="bcc6d-111">包括作为第三部分或 Z 部分，多个部分的消息的未声明的 Z 段。</span><span class="sxs-lookup"><span data-stu-id="bcc6d-111">You include the undeclared Z segment as the third part, or Z part, of a multi-part message.</span></span> <span data-ttu-id="bcc6d-112">该消息包含标头、 正文和的 Z 部分。</span><span class="sxs-lookup"><span data-stu-id="bcc6d-112">The message includes the header, the body, and the Z part.</span></span> <span data-ttu-id="bcc6d-113">Z 部件具有以字母"Z"开头的分段 ID。</span><span class="sxs-lookup"><span data-stu-id="bcc6d-113">The Z part has a segment ID starting with the letter "Z".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bcc6d-114">Zpart 必须始终包含数据。</span><span class="sxs-lookup"><span data-stu-id="bcc6d-114">The Zpart must always contain data.</span></span> <span data-ttu-id="bcc6d-115">指定的错误条件中的流结果为 null。</span><span class="sxs-lookup"><span data-stu-id="bcc6d-115">Specifying null for the stream results in an error condition.</span></span> <span data-ttu-id="bcc6d-116">如果没有数据包含在 Zpart，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]在 Zpart 中插入 word"空"。</span><span class="sxs-lookup"><span data-stu-id="bcc6d-116">If no data is included in the Zpart, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] inserts the word "Empty" in the Zpart.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="bcc6d-117">使用上下文属性**ZPartPresent**以确定是否序列化的 Z 部分。</span><span class="sxs-lookup"><span data-stu-id="bcc6d-117"> uses the context property **ZPartPresent** to determine whether to serialize the Z part.</span></span>  
  
> [!CAUTION]
>  [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="bcc6d-118">ANSI 字符集，与 ANSI 字符的 Zsegment 行为是可预测的结果进行了测试 Zsegments。</span><span class="sxs-lookup"><span data-stu-id="bcc6d-118"> has tested Zsegments with ANSI character sets, with the result that Zsegment behavior with ANSI characters is predictable.</span></span> <span data-ttu-id="bcc6d-119">但是，在 Zsegments 中使用其他字符集可能会导致不可预知的行为。</span><span class="sxs-lookup"><span data-stu-id="bcc6d-119">However, using other character sets in Zsegments may result in unpredictable behavior.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcc6d-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bcc6d-120">See Also</span></span>  
 <span data-ttu-id="bcc6d-121">[扩展 HL7 2.X 架构具有 Z 对象](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span><span class="sxs-lookup"><span data-stu-id="bcc6d-121">[Extending HL7 2.X Schemas with Z Objects](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span></span>  
 <span data-ttu-id="bcc6d-122">[创建声明的 Z 段](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md) </span><span class="sxs-lookup"><span data-stu-id="bcc6d-122">[Creating Declared Z Segments](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md) </span></span>  
 <span data-ttu-id="bcc6d-123">[在架构中创建自定义数据类型](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="bcc6d-123">[Creating Custom Data Types in Schemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md) </span></span>  
 [<span data-ttu-id="bcc6d-124">在架构中创建自定义的表</span><span class="sxs-lookup"><span data-stu-id="bcc6d-124">Creating Custom Tables in Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md)