---
title: 验证的已知问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- known issues, validating
- validating, known issues
ms.assetid: 136596f2-ee0f-4ea9-918c-3608f2ee1be3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 73cc1caa3207901780a57e7b1213215217b73326
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010574"
---
# <a name="validation-known-issues"></a><span data-ttu-id="e49b6-102">验证的已知问题</span><span class="sxs-lookup"><span data-stu-id="e49b6-102">Validation Known Issues</span></span>
<span data-ttu-id="e49b6-103">本部分包含可帮助您避免验证错误的有用信息。</span><span class="sxs-lookup"><span data-stu-id="e49b6-103">This section contains useful information that may help you avoid validation errors.</span></span>  
  
## <a name="disabling-xml-validation"></a><span data-ttu-id="e49b6-104">禁用 XML 验证</span><span class="sxs-lookup"><span data-stu-id="e49b6-104">Disabling XML validation</span></span>  
 <span data-ttu-id="e49b6-105">在"验证正文段"标志[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器控制 XML 正文验证并不包括验证意外的分隔符和尾部分隔符。</span><span class="sxs-lookup"><span data-stu-id="e49b6-105">The "Validate Body Segments" flag in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer controls the XML body validation and does not include validation of unexpected delimiters and trailing delimiters.</span></span> <span data-ttu-id="e49b6-106">如果消息不具有适当的分隔符，不能成功分析该消息。</span><span class="sxs-lookup"><span data-stu-id="e49b6-106">If a message does not have the proper delimiters, the message cannot be successfully parsed.</span></span> <span data-ttu-id="e49b6-107">如果不能成功分析一条消息，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]无法生成有效的中间 XML。</span><span class="sxs-lookup"><span data-stu-id="e49b6-107">If a message cannot be successfully parsed, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] cannot generate valid intermediate XML.</span></span> <span data-ttu-id="e49b6-108">禁用"验证正文段"标志将导致以下结果：</span><span class="sxs-lookup"><span data-stu-id="e49b6-108">Disabling the "Validate Body Segments" flag results in the following:</span></span>  
  
1.  <span data-ttu-id="e49b6-109">空的必填的字段。</span><span class="sxs-lookup"><span data-stu-id="e49b6-109">Empty required fields.</span></span>  
  
2.  <span data-ttu-id="e49b6-110">未验证的数据类型。</span><span class="sxs-lookup"><span data-stu-id="e49b6-110">Data types not validated.</span></span>  
  
3.  <span data-ttu-id="e49b6-111">不验证段结构 （不验证段的顺序）。</span><span class="sxs-lookup"><span data-stu-id="e49b6-111">Segment structure is not validated (order of segments is not validated).</span></span>  
  
## <a name="v2xml-acks-with-multiple-errors-will-fail-validation"></a><span data-ttu-id="e49b6-112">V2。带有多个错误的 XML Ack 验证将失败</span><span class="sxs-lookup"><span data-stu-id="e49b6-112">V2.XML ACKs with multiple errors will fail validation</span></span>  
 <span data-ttu-id="e49b6-113">如果传入 V2。XML 消息包含多个错误，Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 分析器可能会生成 V2。在错误字段中的多个错误的 XML 确认 (ACK)。</span><span class="sxs-lookup"><span data-stu-id="e49b6-113">If an incoming V2.XML message contains more than one error, the Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) parser may generate a V2.XML acknowledgment (ACK) with more than one error in the error field.</span></span> <span data-ttu-id="e49b6-114">此类第 2 版。XML 确认将验证失败，因为 HL7 标准指定分析器可以报告 V2 中的只有一个错误。XML 确认错误字段。</span><span class="sxs-lookup"><span data-stu-id="e49b6-114">Such a V2.XML ACK will fail validation, because the HL7 standard specifies that the parser can report only one error in a V2.XML ACK error field.</span></span>  
  
## <a name="two-parsing-errors-are-logged-when-messages-in-the-batch-inbatch-out-scenario-contain-validation-errors"></a><span data-ttu-id="e49b6-115">记录了两个分析错误时批中的消息中批处理出方案包含验证错误</span><span class="sxs-lookup"><span data-stu-id="e49b6-115">Two parsing errors are logged when messages in the Batch In/Batch Out scenario contain validation errors</span></span>  
 <span data-ttu-id="e49b6-116">第一个批处理中的消息时在 / 批处理出方案 （多个消息批处理没有批处理标头） 包含验证错误，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]事件日志中记录两个错误。</span><span class="sxs-lookup"><span data-stu-id="e49b6-116">When the first message in the Batch In/Batch Out scenario (multiple messages batched without batch headers) contains validation errors, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] logs two errors in the Event Log.</span></span> <span data-ttu-id="e49b6-117">第二个错误相关的消息的其余部分和与批处理中的第一个消息相关的第一个错误。</span><span class="sxs-lookup"><span data-stu-id="e49b6-117">The first error pertains to the first message in the batch, and the second error pertains to the remainder of the messages.</span></span>  
  
## <a name="restrictions-in-validating-field-length"></a><span data-ttu-id="e49b6-118">验证字段长度的限制</span><span class="sxs-lookup"><span data-stu-id="e49b6-118">Restrictions in validating field length</span></span>  
 <span data-ttu-id="e49b6-119">HL7 复杂数据类型组成的组件和子组件与关联的字段。</span><span class="sxs-lookup"><span data-stu-id="e49b6-119">Fields associated with HL7 complex data types are comprised of components and subcomponents.</span></span> <span data-ttu-id="e49b6-120">HL7 规则指定的长度和字段级别而不是在组件/子组件级别的可选性。</span><span class="sxs-lookup"><span data-stu-id="e49b6-120">HL7 rules specify the length and optionality at the field level and not at the component/subcomponent level.</span></span> <span data-ttu-id="e49b6-121">例如在于 V2.4，HL7 控制 MSH3 的 HD 数据类型和 180 个字符最大长度。</span><span class="sxs-lookup"><span data-stu-id="e49b6-121">For example in V2.4, HL7 governs MSH3 to be of HD data type and 180 characters maximum length.</span></span> <span data-ttu-id="e49b6-122">HD 是复合数据类型使用 HD1 集按原样、 HD2 设为 ST 和 HD3 设为 id。</span><span class="sxs-lookup"><span data-stu-id="e49b6-122">HD is a composite data type with HD1 set as IS, HD2 set as ST, and HD3 set as ID.</span></span> <span data-ttu-id="e49b6-123">字段长度限制表示三个组件 （包括两个组件分隔符） 中的数据应小于或等于 180。</span><span class="sxs-lookup"><span data-stu-id="e49b6-123">The field length restriction implies that the data in the three components (including the two component separators) should be less than or equal to 180.</span></span> <span data-ttu-id="e49b6-124">但是，未指定三个数据类型的可选性;这意味着所有或某些组件可能存在。</span><span class="sxs-lookup"><span data-stu-id="e49b6-124">However, the optionality of the three data types is not specified; which means that all or some components may exist.</span></span> <span data-ttu-id="e49b6-125">此外，ST 和 IS 的数据类型是用户定义的因此[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]不能为长度分布在三个组件之间的注意，因为这些通常是站点定义。</span><span class="sxs-lookup"><span data-stu-id="e49b6-125">Additionally, data types ST and IS are user defined and therefore [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] cannot be aware of the length distribution across the three components, since these are normally site defined.</span></span>  
  
 <span data-ttu-id="e49b6-126">由于这些和其他复杂问题，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]不会验证字段长度。</span><span class="sxs-lookup"><span data-stu-id="e49b6-126">Due to these and other complications, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] does not validate the field length.</span></span> <span data-ttu-id="e49b6-127">不过，您可以应用长度限制在每个单个组件/子组件 （的数据类型简单） 使用 BizTalk 编辑器中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e49b6-127">However, you can apply length restrictions at each individual component/subcomponent (of data type simple) using BizTalk Editor in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="e49b6-128"> 将验证在处理过程。</span><span class="sxs-lookup"><span data-stu-id="e49b6-128"> will validate these during processing.</span></span>  
  
## <a name="validation-of-batch-and-file-headerstrailers-are-affected-by-enabling-fragmentation"></a><span data-ttu-id="e49b6-129">启用碎片会影响批处理和文件的标头/尾部的验证</span><span class="sxs-lookup"><span data-stu-id="e49b6-129">Validation of batch and file headers/trailers are affected by enabling fragmentation</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="e49b6-130"> 当 FHS3 字段包含具有启用的碎片的参与方时，不会验证 batch 和文件的标头/尾部。</span><span class="sxs-lookup"><span data-stu-id="e49b6-130"> does not validate batch and file headers/trailers when the FHS3 field contains a party that has fragmentation enabled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e49b6-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="e49b6-131">See Also</span></span>  
 [<span data-ttu-id="e49b6-132">已知问题</span><span class="sxs-lookup"><span data-stu-id="e49b6-132">Known Issues</span></span>](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)