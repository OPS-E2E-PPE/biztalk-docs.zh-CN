---
title: "与批处理相关提升属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- promoted properties, batch related properties
- batching, promoted properties
ms.assetid: 00df1d8f-2f3f-4e3f-9983-37dcf3514fd8
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20fa421c6536d1d5182a11872206783392c65f69
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="batch-related-promoted-properties"></a><span data-ttu-id="e67b7-102">与批处理相关提升的属性</span><span class="sxs-lookup"><span data-stu-id="e67b7-102">Batch-Related Promoted Properties</span></span>
<span data-ttu-id="e67b7-103">当 SWIFT 反汇编程序发布到 MessageBox 数据库从入站批处理发出的消息时，拆装器会将标记的消息的特殊[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]升级的特定于消息进行批处理的属性。</span><span class="sxs-lookup"><span data-stu-id="e67b7-103">When the SWIFT disassembler publishes a message that originated from an inbound batch to the MessageBox database, the disassembler marks the message with special [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] promoted properties that are specific to batch messages.</span></span> <span data-ttu-id="e67b7-104">这些属性提供上下文信息，如从哪些序号位置发出的消息的批它已在中的批处理，保留已部分 A4SWIFT，依此类推。</span><span class="sxs-lookup"><span data-stu-id="e67b7-104">These properties provide context information, such as which batch a message originated from, what ordinal position it was in within the batch, which parts A4SWIFT has preserved, and so forth.</span></span>  
  
 <span data-ttu-id="e67b7-105">A4SWIFT 设置消息进行批处理的以下提升的属性：</span><span class="sxs-lookup"><span data-stu-id="e67b7-105">A4SWIFT sets the following promoted properties for batch messages:</span></span>  
  
-   <span data-ttu-id="e67b7-106">**A4SWIFT_BatchId**</span><span class="sxs-lookup"><span data-stu-id="e67b7-106">**A4SWIFT_BatchId**</span></span>  
  
-   <span data-ttu-id="e67b7-107">**A4SWIFT_IsMessageHeaderValued**</span><span class="sxs-lookup"><span data-stu-id="e67b7-107">**A4SWIFT_IsMessageHeaderValued**</span></span>  
  
-   <span data-ttu-id="e67b7-108">**A4SWIFT_IsMessageTrailerValued**</span><span class="sxs-lookup"><span data-stu-id="e67b7-108">**A4SWIFT_IsMessageTrailerValued**</span></span>  
  
-   <span data-ttu-id="e67b7-109">**A4SWIFT_NumberOfParts**</span><span class="sxs-lookup"><span data-stu-id="e67b7-109">**A4SWIFT_NumberOfParts**</span></span>  
  
-   <span data-ttu-id="e67b7-110">**A4SWIFT_PosInBatch**</span><span class="sxs-lookup"><span data-stu-id="e67b7-110">**A4SWIFT_PosInBatch**</span></span>  
  
 <span data-ttu-id="e67b7-111">有关这些及其他提升的属性的信息，请参阅[A4SWIFT_ * 提升属性](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="e67b7-111">For information about these and other promoted properties, see [A4SWIFT_* Promoted Properties](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md).</span></span>  
  
## <a name="failures-during-batch-processing"></a><span data-ttu-id="e67b7-112">批处理操作期间出现的故障</span><span class="sxs-lookup"><span data-stu-id="e67b7-112">Failures During Batch Processing</span></span>  
 <span data-ttu-id="e67b7-113">当 SWIFT 反汇编程序 （分析或验证） 的消息失败在过程中遇到批处理 (**入站 Debatching**设置为**True**)，其行为取决于批处理的配置中，为如下所示：</span><span class="sxs-lookup"><span data-stu-id="e67b7-113">When the SWIFT disassembler encounters message failures (parsing or validation) during batch processing (**Inbound Debatching** set to **True**), its behavior depends upon the batching configuration, as follows:</span></span>  
  
-   <span data-ttu-id="e67b7-114">批处理 (**入站 Debatching**设置为**True**) 与启用的碎片 (**碎片**设置为**True**)，则反汇编程序发布到 MessageBox 数据库失败的消息单独，与相应的错误信息在提升的属性中附加和序列化**ErrorCollection** XML。</span><span class="sxs-lookup"><span data-stu-id="e67b7-114">For batch processing (**Inbound Debatching** set to **True**) with fragmentation enabled (**Fragmentation** set to **True**), the disassembler publishes failed messages to the MessageBox database individually, with corresponding error information appended in promoted properties and serialized **ErrorCollection** XML.</span></span> <span data-ttu-id="e67b7-115">如果拆装器找到末尾的批处理 （即，拆装器无法分析使用任何指定的架构中的数据） 的意外的数据，拆装器在批处理中的最后一条包含此意外的数据，并将其标记已发生故障分析.</span><span class="sxs-lookup"><span data-stu-id="e67b7-115">If the disassembler finds unexpected data at the end of the batch (that is, data that the disassembler cannot parse using any of the specified schemas), the disassembler includes this unexpected data in the last message in the batch and marks it as having failed parsing.</span></span> <span data-ttu-id="e67b7-116">如果反汇编程序在处理过程中遇到致命错误，拆装器发布导致错误，加上所有数据的末尾将交换，为单个消息的消息。</span><span class="sxs-lookup"><span data-stu-id="e67b7-116">If the disassembler encounters a fatal error during processing, then the disassembler publishes the message that caused the fatal error, plus all data to the end of the interchange, as a single message.</span></span> <span data-ttu-id="e67b7-117">反汇编程序不严重的错误后进行分段消息。</span><span class="sxs-lookup"><span data-stu-id="e67b7-117">The disassembler does not fragment messages after the fatal error.</span></span>  
  
-   <span data-ttu-id="e67b7-118">批处理 (**入站 Debatching**设置为**True**) 具有禁用的碎片 (**碎片**设置为**False**)，则反汇编程序发布到 MessageBox 数据库失败的消息单独，与相应的错误信息在提升的属性中附加和序列化**ErrorCollection** XML。</span><span class="sxs-lookup"><span data-stu-id="e67b7-118">For batch processing (**Inbound Debatching** set to **True**) with fragmentation disabled (**Fragmentation** set to **False**), the disassembler publishes failed messages to the MessageBox database individually, with corresponding error information appended in promoted properties and serialized **ErrorCollection** XML.</span></span> <span data-ttu-id="e67b7-119">此外，反汇编程序 （包含一个或多个失败的消息） 的整个批到 MessageBox 数据库将作为发布单个消息，以本机形式 （输入的准确副本）。</span><span class="sxs-lookup"><span data-stu-id="e67b7-119">In addition, the disassembler publishes the entire batch (containing one or more failed messages) to the MessageBox database as a single message, in native form (exact copy of input).</span></span> <span data-ttu-id="e67b7-120">反汇编程序将其与标记**A4SWIFT_Failed**提升属性集**True**以指示批处理包含一个或多个失败的消息。</span><span class="sxs-lookup"><span data-stu-id="e67b7-120">The disassembler marks it with the **A4SWIFT_Failed** promoted property set **True** to indicate that the batch contains one or more failed messages.</span></span> <span data-ttu-id="e67b7-121">反汇编程序还会将附加序列化**ErrorCollection**到表示单个批处理中消息中遇到的所有错误的串联未分片批次的 XML。</span><span class="sxs-lookup"><span data-stu-id="e67b7-121">The disassembler also attaches serialized **ErrorCollection** XML to the un-fragmented batch that represents the concatenation of all errors encountered in the individual messages within the batch.</span></span> <span data-ttu-id="e67b7-122">若要发现从批处理中的失败消息的每个消息错误详细信息，必须从 MessageBox 数据库中检索单个失败的消息 （通过关联来在 A4SWIFT_BatchId 上），并提取**ErrorCollection** XML为每个失败的消息。</span><span class="sxs-lookup"><span data-stu-id="e67b7-122">To discover the per-message error details from failed messages in the batch, you must retrieve the individual failed messages from the MessageBox database (by correlating on A4SWIFT_BatchId), and extract the **ErrorCollection** XML for each failed message.</span></span> <span data-ttu-id="e67b7-123">（由于反汇编程序发布到反汇编程序如果拆装器找到末尾的批处理 （即，拆装器无法分析使用任何指定的架构中的数据） 的意外的数据，包括与整个失败的批处理的意外的数据MessageBox 数据库逐字），并将它标记为失败后，由于意外的数据分析。</span><span class="sxs-lookup"><span data-stu-id="e67b7-123">If the disassembler finds unexpected data at the end of the batch (that is, data that the disassembler cannot parse using any of the specified schemas), the disassembler includes the unexpected data with the entire failed batch (since the disassembler publishes it to the MessageBox database verbatim), and marks it as having failed parsing due to unexpected data.</span></span>  
  
-   <span data-ttu-id="e67b7-124">对于非批处理方案 (**入站 Debatching**设置为**False**)，拆装器始终将发布失败的消息到 MessageBox 数据库按预期方式单独。</span><span class="sxs-lookup"><span data-stu-id="e67b7-124">For non-batch scenarios (**Inbound Debatching** set to **False**), the disassembler always publishes failed messages to the MessageBox database individually, as expected.</span></span>  
  
 <span data-ttu-id="e67b7-125">有关 A4SWIFT 失败/错误的详细信息升级的属性和**ErrorCollection**对象，请参阅[使用失败消息订阅](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md)。</span><span class="sxs-lookup"><span data-stu-id="e67b7-125">For more information about A4SWIFT failure/error promoted properties and the **ErrorCollection** object, see [Working with Failed Message Subscriptions](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e67b7-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e67b7-126">See Also</span></span>  
 <span data-ttu-id="e67b7-127">[反汇编入站的批处理](../../adapters-and-accelerators/accelerator-swift/disassembling-inbound-batches.md) </span><span class="sxs-lookup"><span data-stu-id="e67b7-127">[Disassembling Inbound Batches](../../adapters-and-accelerators/accelerator-swift/disassembling-inbound-batches.md) </span></span>  
 [<span data-ttu-id="e67b7-128">使用 SWIFT 反汇编程序和汇编程序</span><span class="sxs-lookup"><span data-stu-id="e67b7-128">Working with the SWIFT Disassembler and Assembler</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)