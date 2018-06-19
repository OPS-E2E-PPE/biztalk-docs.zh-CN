---
title: HL7 2.X 反汇编程序中的架构确定 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- header segments [2.X]
- 2.X messages, header segments
- messages, parsing messages
- MSH
- disassembler, parsing messages
- 2.X messages, MSH
ms.assetid: afd45c4c-2feb-44eb-b3bd-49fe114eb893
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6314f9651d09dbb041d2e8851565e904366c9efe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206085"
---
# <a name="schema-determination-in-the-hl7-2x-disassembler"></a><span data-ttu-id="1d3b4-102">HL7 2.X 反汇编程序中的架构确定</span><span class="sxs-lookup"><span data-stu-id="1d3b4-102">Schema Determination in the HL7 2.X Disassembler</span></span>
<span data-ttu-id="1d3b4-103">HL7 2.X 消息包含跟正文段的编号和可选的 Z 段的标头段 (MSH)。</span><span class="sxs-lookup"><span data-stu-id="1d3b4-103">HL7 2.X messages contain a header segment (MSH), followed by a number of body segments and an optional number of Z segments.</span></span> <span data-ttu-id="1d3b4-104">MSH 包含 21 字段。</span><span class="sxs-lookup"><span data-stu-id="1d3b4-104">MSH contains 21 fields.</span></span>  
  
 <span data-ttu-id="1d3b4-105">当消息到达时，2.X 引擎读取标头以确定要用于分析消息正文的架构。</span><span class="sxs-lookup"><span data-stu-id="1d3b4-105">When a message arrives, the 2.X engine reads the header to determine the schema to use to parse the message body.</span></span> <span data-ttu-id="1d3b4-106">事件按下列顺序发生：</span><span class="sxs-lookup"><span data-stu-id="1d3b4-106">The following sequence of events occurs:</span></span>  
  
1.  <span data-ttu-id="1d3b4-107">反汇编程序读取 MSH3 值 （源方） 以确定以下的验证选项：</span><span class="sxs-lookup"><span data-stu-id="1d3b4-107">The disassembler reads the value of MSH3 (source party) to determine the following validation options:</span></span>  
  
    1.  <span data-ttu-id="1d3b4-108">是否正文执行 XML 验证</span><span class="sxs-lookup"><span data-stu-id="1d3b4-108">Whether to perform XML validation for the body</span></span>  
  
    2.  <span data-ttu-id="1d3b4-109">是否要验证自定义数据类型字段中的正文数据</span><span class="sxs-lookup"><span data-stu-id="1d3b4-109">Whether to validate custom data type fields in the body data</span></span>  
  
    3.  <span data-ttu-id="1d3b4-110">是否允许尾随分隔符在正文中</span><span class="sxs-lookup"><span data-stu-id="1d3b4-110">Whether to allow trailing delimiters in the body</span></span>  
  
    4.  <span data-ttu-id="1d3b4-111">什么是正文架构的目标命名空间 (**TargetNS**)</span><span class="sxs-lookup"><span data-stu-id="1d3b4-111">What the target namespace of the body schema is (**TargetNS**)</span></span>  
  
2.  <span data-ttu-id="1d3b4-112">然后，拆装器读取 MSH9 并 MSH12 确定正文的根节点名称。</span><span class="sxs-lookup"><span data-stu-id="1d3b4-112">The disassembler then reads MSH9 and MSH12 to determine the root node name of the body.</span></span> <span data-ttu-id="1d3b4-113">算法是，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1d3b4-113">The algorithm is as follows:</span></span>  
  
    ```  
    Body schema type = TargetNS + "#" + MSH9.1 + MSH9.2 + MSH12.1 (with dots removed) + MSH12.2 (or GLO if the value is blank) + MSH12.3 (or DEF if the value is blank)  
    ```  
  
     [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="1d3b4-114">BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 始终允许尾随分隔符消息标头中的。</span><span class="sxs-lookup"><span data-stu-id="1d3b4-114"> BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) always allows trailing delimiters in a message header.</span></span> <span data-ttu-id="1d3b4-115">引擎将检查每个行的前三个字符的段标识符。</span><span class="sxs-lookup"><span data-stu-id="1d3b4-115">The engine examines the segment identifier that is the first three characters of each line.</span></span> <span data-ttu-id="1d3b4-116">它保留对于正文架构定义的所有部门生成 XML。</span><span class="sxs-lookup"><span data-stu-id="1d3b4-116">It keeps on generating XML for all segments that the body schema defines.</span></span> <span data-ttu-id="1d3b4-117">当它遇到一个未定义的段时，它将该段视为 Z 段。</span><span class="sxs-lookup"><span data-stu-id="1d3b4-117">When it encounters an undefined segment, it treats that segment as a Z segment.</span></span> <span data-ttu-id="1d3b4-118">从那一刻开始，所有未定义的段构成消息的 Z 部分。</span><span class="sxs-lookup"><span data-stu-id="1d3b4-118">From that point on, all undefined segments constitute the Z part of the message.</span></span> <span data-ttu-id="1d3b4-119">下一步 MSH 将标记此消息的末尾。</span><span class="sxs-lookup"><span data-stu-id="1d3b4-119">The next MSH marks the end of this message.</span></span> <span data-ttu-id="1d3b4-120">对于批处理消息下, 一步 MSH 或 BTS （批处理预告片段标记） 将标记消息的末尾。</span><span class="sxs-lookup"><span data-stu-id="1d3b4-120">For batch messages, the next MSH or BTS (the batch trailer segment tag) marks the end of a message.</span></span> <span data-ttu-id="1d3b4-121">Z 段只能包含在架构中未声明的段。</span><span class="sxs-lookup"><span data-stu-id="1d3b4-121">A Z segment can only contain segments that are undeclared in a schema.</span></span> <span data-ttu-id="1d3b4-122">它是错误遇到声明的段。</span><span class="sxs-lookup"><span data-stu-id="1d3b4-122">It is an error to encounter a declared segment.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d3b4-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1d3b4-123">See Also</span></span>  
 <span data-ttu-id="1d3b4-124">[消息处理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="1d3b4-124">[Message Processing](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span></span>  
 [<span data-ttu-id="1d3b4-125">BTAHL72X 平面文件处理</span><span class="sxs-lookup"><span data-stu-id="1d3b4-125">BTAHL72X Flat File Processing</span></span>](../../adapters-and-accelerators/accelerator-hl7/btahl72x-flat-file-processing.md)