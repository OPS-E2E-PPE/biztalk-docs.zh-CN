---
title: "验证已知问题 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- known issues, validating
- validating, known issues
ms.assetid: 136596f2-ee0f-4ea9-918c-3608f2ee1be3
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69400c5196b31a53d49055e500356c7ce3430e58
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="validation-known-issues"></a><span data-ttu-id="0f109-102">验证已知问题</span><span class="sxs-lookup"><span data-stu-id="0f109-102">Validation Known Issues</span></span>
<span data-ttu-id="0f109-103">本节包含可以帮助您避免验证错误的有用信息。</span><span class="sxs-lookup"><span data-stu-id="0f109-103">This section contains useful information that may help you avoid validation errors.</span></span>  
  
## <a name="disabling-xml-validation"></a><span data-ttu-id="0f109-104">禁用 XML 验证</span><span class="sxs-lookup"><span data-stu-id="0f109-104">Disabling XML validation</span></span>  
 <span data-ttu-id="0f109-105">"验证正文段"标志中[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器控制 XML 正文验证，并且不包括验证意外的分隔符和尾随分隔符。</span><span class="sxs-lookup"><span data-stu-id="0f109-105">The "Validate Body Segments" flag in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer controls the XML body validation and does not include validation of unexpected delimiters and trailing delimiters.</span></span> <span data-ttu-id="0f109-106">如果消息不具有适当的分隔符，则无法成功分析消息。</span><span class="sxs-lookup"><span data-stu-id="0f109-106">If a message does not have the proper delimiters, the message cannot be successfully parsed.</span></span> <span data-ttu-id="0f109-107">如果无法成功分析一条消息，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]无法生成有效的中间 XML。</span><span class="sxs-lookup"><span data-stu-id="0f109-107">If a message cannot be successfully parsed, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] cannot generate valid intermediate XML.</span></span> <span data-ttu-id="0f109-108">禁用"验证正文段"标志将产生以下结果：</span><span class="sxs-lookup"><span data-stu-id="0f109-108">Disabling the "Validate Body Segments" flag results in the following:</span></span>  
  
1.  <span data-ttu-id="0f109-109">空的必填的字段。</span><span class="sxs-lookup"><span data-stu-id="0f109-109">Empty required fields.</span></span>  
  
2.  <span data-ttu-id="0f109-110">未验证的数据类型。</span><span class="sxs-lookup"><span data-stu-id="0f109-110">Data types not validated.</span></span>  
  
3.  <span data-ttu-id="0f109-111">不验证段结构 （不验证的段的顺序）。</span><span class="sxs-lookup"><span data-stu-id="0f109-111">Segment structure is not validated (order of segments is not validated).</span></span>  
  
## <a name="v2xml-acks-with-multiple-errors-will-fail-validation"></a><span data-ttu-id="0f109-112">V2。使用多个错误的 XML 确认将未通过验证</span><span class="sxs-lookup"><span data-stu-id="0f109-112">V2.XML ACKs with multiple errors will fail validation</span></span>  
 <span data-ttu-id="0f109-113">如果传入 V2。XML 消息包含多个错误， [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 分析器可能会生成 V2。与错误字段中的多个错误的 XML 确认 (ACK)。</span><span class="sxs-lookup"><span data-stu-id="0f109-113">If an incoming V2.XML message contains more than one error, the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) parser may generate a V2.XML acknowledgment (ACK) with more than one error in the error field.</span></span> <span data-ttu-id="0f109-114">此类 V2。XML ACK 将未通过验证，因为 HL7 标准指定分析器可以报告 V2 中的只有一个错误。XML ACK 错误字段。</span><span class="sxs-lookup"><span data-stu-id="0f109-114">Such a V2.XML ACK will fail validation, because the HL7 standard specifies that the parser can report only one error in a V2.XML ACK error field.</span></span>  
  
## <a name="two-parsing-errors-are-logged-when-messages-in-the-batch-inbatch-out-scenario-contain-validation-errors"></a><span data-ttu-id="0f109-115">记录两个分析错误时批处理中的消息中批处理出方案包含验证错误</span><span class="sxs-lookup"><span data-stu-id="0f109-115">Two parsing errors are logged when messages in the Batch In/Batch Out scenario contain validation errors</span></span>  
 <span data-ttu-id="0f109-116">第一个批处理中的消息时在 / 批处理出方案 （多个消息批处理不带批处理标头） 包含验证错误[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]记录事件日志中的两个错误。</span><span class="sxs-lookup"><span data-stu-id="0f109-116">When the first message in the Batch In/Batch Out scenario (multiple messages batched without batch headers) contains validation errors, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] logs two errors in the Event Log.</span></span> <span data-ttu-id="0f109-117">第一个错误与批处理中的第一条和第二个错误与消息的其余部分。</span><span class="sxs-lookup"><span data-stu-id="0f109-117">The first error pertains to the first message in the batch, and the second error pertains to the remainder of the messages.</span></span>  
  
## <a name="restrictions-in-validating-field-length"></a><span data-ttu-id="0f109-118">验证字段长度的限制</span><span class="sxs-lookup"><span data-stu-id="0f109-118">Restrictions in validating field length</span></span>  
 <span data-ttu-id="0f109-119">复杂数据类型组成组件和子组件的 HL7 与关联的字段。</span><span class="sxs-lookup"><span data-stu-id="0f109-119">Fields associated with HL7 complex data types are comprised of components and subcomponents.</span></span> <span data-ttu-id="0f109-120">HL7 规则指定的长度和 optionality 在字段级别而不是在组件/子组件级别。</span><span class="sxs-lookup"><span data-stu-id="0f109-120">HL7 rules specify the length and optionality at the field level and not at the component/subcomponent level.</span></span> <span data-ttu-id="0f109-121">例如在 V2.4，HL7 控制 MSH3 为 HD 数据类型和 180 个字符最大长度。</span><span class="sxs-lookup"><span data-stu-id="0f109-121">For example in V2.4, HL7 governs MSH3 to be of HD data type and 180 characters maximum length.</span></span> <span data-ttu-id="0f109-122">HD 是复合数据类型并带有 HD1 设为 IS、 HD2 设为表 ST 和 HD3 设为 id。</span><span class="sxs-lookup"><span data-stu-id="0f109-122">HD is a composite data type with HD1 set as IS, HD2 set as ST, and HD3 set as ID.</span></span> <span data-ttu-id="0f109-123">字段长度限制意味着 （包括这两个组件分隔符） 的三个组件中的数据应小于或等于 180。</span><span class="sxs-lookup"><span data-stu-id="0f109-123">The field length restriction implies that the data in the three components (including the two component separators) should be less than or equal to 180.</span></span> <span data-ttu-id="0f109-124">但是，未指定三种数据类型的 optionality;这意味着所有或某些组件可能存在。</span><span class="sxs-lookup"><span data-stu-id="0f109-124">However, the optionality of the three data types is not specified; which means that all or some components may exist.</span></span> <span data-ttu-id="0f109-125">此外，数据类型为 ST 和 IS 是用户定义的因此[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]不能为感知的长度分布的三个组件，因为这些通常是定义的站点。</span><span class="sxs-lookup"><span data-stu-id="0f109-125">Additionally, data types ST and IS are user defined and therefore [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] cannot be aware of the length distribution across the three components, since these are normally site defined.</span></span>  
  
 <span data-ttu-id="0f109-126">由于这些和其他的复杂性，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]不会验证字段长度。</span><span class="sxs-lookup"><span data-stu-id="0f109-126">Due to these and other complications, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] does not validate the field length.</span></span> <span data-ttu-id="0f109-127">但是，你可以应用长度限制在每个单个组件/子组件 （的数据类型简单） 使用 BizTalk 编辑器中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0f109-127">However, you can apply length restrictions at each individual component/subcomponent (of data type simple) using BizTalk Editor in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="0f109-128">将验证在处理过程。</span><span class="sxs-lookup"><span data-stu-id="0f109-128"> will validate these during processing.</span></span>  
  
## <a name="validation-of-batch-and-file-headerstrailers-are-affected-by-enabling-fragmentation"></a><span data-ttu-id="0f109-129">启用碎片会影响的批处理和文件的标头/拖车的验证</span><span class="sxs-lookup"><span data-stu-id="0f109-129">Validation of batch and file headers/trailers are affected by enabling fragmentation</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="0f109-130">当 FHS3 字段包含已启用的碎片的当事方，则不会验证批处理和文件标头/拖车安排。</span><span class="sxs-lookup"><span data-stu-id="0f109-130"> does not validate batch and file headers/trailers when the FHS3 field contains a party that has fragmentation enabled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f109-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0f109-131">See Also</span></span>  
 [<span data-ttu-id="0f109-132">已知问题</span><span class="sxs-lookup"><span data-stu-id="0f109-132">Known Issues</span></span>](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)