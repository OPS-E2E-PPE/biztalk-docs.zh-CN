---
title: 与批处理相关的已提升属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- promoted properties, batch related properties
- batching, promoted properties
ms.assetid: 00df1d8f-2f3f-4e3f-9983-37dcf3514fd8
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea49f40097df45bac158150cd22d124b43831bcb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378950"
---
# <a name="batch-related-promoted-properties"></a><span data-ttu-id="31331-102">与批处理相关的已提升的属性</span><span class="sxs-lookup"><span data-stu-id="31331-102">Batch-Related Promoted Properties</span></span>
<span data-ttu-id="31331-103">当 SWIFT 反汇编程序发布到 MessageBox 数据库源自的入站批处理的消息时，拆装器会将消息标记与特殊 Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]提升特定对消息进行批处理的属性。</span><span class="sxs-lookup"><span data-stu-id="31331-103">When the SWIFT disassembler publishes a message that originated from an inbound batch to the MessageBox database, the disassembler marks the message with special Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] promoted properties that are specific to batch messages.</span></span> <span data-ttu-id="31331-104">这些属性提供上下文信息，如从哪些序号位置发出一条消息的批时中的批处理，部件 A4SWIFT 已预留，等等。</span><span class="sxs-lookup"><span data-stu-id="31331-104">These properties provide context information, such as which batch a message originated from, what ordinal position it was in within the batch, which parts A4SWIFT has preserved, and so forth.</span></span>  
  
 <span data-ttu-id="31331-105">A4SWIFT 设置批处理消息，升级以下的属性：</span><span class="sxs-lookup"><span data-stu-id="31331-105">A4SWIFT sets the following promoted properties for batch messages:</span></span>  
  
- <span data-ttu-id="31331-106">**A4SWIFT_BatchId**</span><span class="sxs-lookup"><span data-stu-id="31331-106">**A4SWIFT_BatchId**</span></span>  
  
- <span data-ttu-id="31331-107">**A4SWIFT_IsMessageHeaderValued**</span><span class="sxs-lookup"><span data-stu-id="31331-107">**A4SWIFT_IsMessageHeaderValued**</span></span>  
  
- <span data-ttu-id="31331-108">**A4SWIFT_IsMessageTrailerValued**</span><span class="sxs-lookup"><span data-stu-id="31331-108">**A4SWIFT_IsMessageTrailerValued**</span></span>  
  
- <span data-ttu-id="31331-109">**A4SWIFT_NumberOfParts**</span><span class="sxs-lookup"><span data-stu-id="31331-109">**A4SWIFT_NumberOfParts**</span></span>  
  
- <span data-ttu-id="31331-110">**A4SWIFT_PosInBatch**</span><span class="sxs-lookup"><span data-stu-id="31331-110">**A4SWIFT_PosInBatch**</span></span>  
  
  <span data-ttu-id="31331-111">有关这些及其他升级的属性的信息，请参阅[A4SWIFT_ \* 升级的属性](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="31331-111">For information about these and other promoted properties, see [A4SWIFT_\* Promoted Properties](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md).</span></span>  
  
## <a name="failures-during-batch-processing"></a><span data-ttu-id="31331-112">批处理的处理期间出现的故障</span><span class="sxs-lookup"><span data-stu-id="31331-112">Failures During Batch Processing</span></span>  
 <span data-ttu-id="31331-113">SWIFT 反汇编程序当批处理过程中遇到消息失败 （分析或验证） (**入站解除批处理**设置为**True**)，其行为取决于批处理的配置中，为如下所示：</span><span class="sxs-lookup"><span data-stu-id="31331-113">When the SWIFT disassembler encounters message failures (parsing or validation) during batch processing (**Inbound Debatching** set to **True**), its behavior depends upon the batching configuration, as follows:</span></span>  
  
- <span data-ttu-id="31331-114">用于批处理 (**入站解除批处理**设置为**True**) 与已启用的碎片 (**碎片**设置为**True**)，则拆装器发布到 MessageBox 数据库的失败的消息分别使用相应的错误信息在升级的属性中附加和序列化**ErrorCollection** XML。</span><span class="sxs-lookup"><span data-stu-id="31331-114">For batch processing (**Inbound Debatching** set to **True**) with fragmentation enabled (**Fragmentation** set to **True**), the disassembler publishes failed messages to the MessageBox database individually, with corresponding error information appended in promoted properties and serialized **ErrorCollection** XML.</span></span> <span data-ttu-id="31331-115">如果拆装器发现意外的数据末尾的批处理 （即，拆装器无法分析使用任何指定的架构的数据），拆装器在批处理中的最后一个消息中包括此意外的数据，并将其标记为已失败分析.</span><span class="sxs-lookup"><span data-stu-id="31331-115">If the disassembler finds unexpected data at the end of the batch (that is, data that the disassembler cannot parse using any of the specified schemas), the disassembler includes this unexpected data in the last message in the batch and marks it as having failed parsing.</span></span> <span data-ttu-id="31331-116">如果拆装器在处理期间遇到致命错误，拆装器将发布导致出现错误，以及到交换作为单个消息末尾的所有数据的消息。</span><span class="sxs-lookup"><span data-stu-id="31331-116">If the disassembler encounters a fatal error during processing, then the disassembler publishes the message that caused the fatal error, plus all data to the end of the interchange, as a single message.</span></span> <span data-ttu-id="31331-117">拆装器不会严重错误后进行分段的消息。</span><span class="sxs-lookup"><span data-stu-id="31331-117">The disassembler does not fragment messages after the fatal error.</span></span>  
  
- <span data-ttu-id="31331-118">用于批处理 (**入站解除批处理**设置为**True**) 与禁用的碎片 (**碎片**设置为**False**)，则拆装器发布到 MessageBox 数据库的失败的消息分别使用相应的错误信息在升级的属性中附加和序列化**ErrorCollection** XML。</span><span class="sxs-lookup"><span data-stu-id="31331-118">For batch processing (**Inbound Debatching** set to **True**) with fragmentation disabled (**Fragmentation** set to **False**), the disassembler publishes failed messages to the MessageBox database individually, with corresponding error information appended in promoted properties and serialized **ErrorCollection** XML.</span></span> <span data-ttu-id="31331-119">此外，拆装器 （包含一个或多个失败的消息） 的整个批处理到 MessageBox 数据库将作为发布一条消息，以本机形式 （输入的精确副本）。</span><span class="sxs-lookup"><span data-stu-id="31331-119">In addition, the disassembler publishes the entire batch (containing one or more failed messages) to the MessageBox database as a single message, in native form (exact copy of input).</span></span> <span data-ttu-id="31331-120">拆装器将其与标记**A4SWIFT_Failed**提升属性集**True**以指示批处理包含一个或多个失败的消息。</span><span class="sxs-lookup"><span data-stu-id="31331-120">The disassembler marks it with the **A4SWIFT_Failed** promoted property set **True** to indicate that the batch contains one or more failed messages.</span></span> <span data-ttu-id="31331-121">拆装器还会将附加序列化**ErrorCollection**的 XML 与非零碎的批处理，表示遇到批处理内的单个消息中的所有错误的串联。</span><span class="sxs-lookup"><span data-stu-id="31331-121">The disassembler also attaches serialized **ErrorCollection** XML to the un-fragmented batch that represents the concatenation of all errors encountered in the individual messages within the batch.</span></span> <span data-ttu-id="31331-122">若要了解失败的消息批次中的每条消息错误详细信息，必须从 MessageBox 数据库中检索单个失败的消息 （通过关联来 A4SWIFT_BatchId 上），并将解压缩**ErrorCollection** XML为每个失败的消息。</span><span class="sxs-lookup"><span data-stu-id="31331-122">To discover the per-message error details from failed messages in the batch, you must retrieve the individual failed messages from the MessageBox database (by correlating on A4SWIFT_BatchId), and extract the **ErrorCollection** XML for each failed message.</span></span> <span data-ttu-id="31331-123">如果拆装器发现意外的数据末尾的批处理 （即，拆装器无法分析使用任何指定的架构的数据），拆装器将包括意外的数据的整个失败的批处理 （因为拆装器发布到MessageBox 数据库中逐字字符串），并将其标记为已失败由于意外的数据分析。</span><span class="sxs-lookup"><span data-stu-id="31331-123">If the disassembler finds unexpected data at the end of the batch (that is, data that the disassembler cannot parse using any of the specified schemas), the disassembler includes the unexpected data with the entire failed batch (since the disassembler publishes it to the MessageBox database verbatim), and marks it as having failed parsing due to unexpected data.</span></span>  
  
- <span data-ttu-id="31331-124">对于非批处理方案 (**入站解除批处理**设置为**False**)，拆装器始终失败将消息发布到 MessageBox 数据库按预期方式分别。</span><span class="sxs-lookup"><span data-stu-id="31331-124">For non-batch scenarios (**Inbound Debatching** set to **False**), the disassembler always publishes failed messages to the MessageBox database individually, as expected.</span></span>  
  
  <span data-ttu-id="31331-125">有关 A4SWIFT 失败/错误详细信息的已提升属性和**ErrorCollection**对象，请参阅[使用失败消息订阅](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md)。</span><span class="sxs-lookup"><span data-stu-id="31331-125">For more information about A4SWIFT failure/error promoted properties and the **ErrorCollection** object, see [Working with Failed Message Subscriptions](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31331-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="31331-126">See Also</span></span>  
 <span data-ttu-id="31331-127">[反汇编入站的批处理](../../adapters-and-accelerators/accelerator-swift/disassembling-inbound-batches.md) </span><span class="sxs-lookup"><span data-stu-id="31331-127">[Disassembling Inbound Batches](../../adapters-and-accelerators/accelerator-swift/disassembling-inbound-batches.md) </span></span>  
 [<span data-ttu-id="31331-128">使用 SWIFT 反汇编程序和汇编程序</span><span class="sxs-lookup"><span data-stu-id="31331-128">Working with the SWIFT Disassembler and Assembler</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)