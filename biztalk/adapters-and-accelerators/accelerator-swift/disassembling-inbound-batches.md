---
title: 反汇编入站的批处理与 SWIFT |Microsoft Docs
description: 解除批处理入站的消息，并自定义架构进行批处理在 BizTalk Server 中使用 SWIFT 加速器
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 11cb5672-1155-4648-b1fd-c9a3bc30e351
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e378f0e7b887a9b3dab5a4ffc770c61ff5279f8c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378065"
---
# <a name="disassemble-inbound-batches"></a><span data-ttu-id="3fddd-103">反汇编入站的批处理</span><span class="sxs-lookup"><span data-stu-id="3fddd-103">Disassemble Inbound Batches</span></span>

## <a name="debatch-inbound-message"></a><span data-ttu-id="3fddd-104">解除批处理入站的消息</span><span class="sxs-lookup"><span data-stu-id="3fddd-104">Debatch inbound message</span></span>
<span data-ttu-id="3fddd-105">SWIFT 反汇编程序就可以对入站解除批处理它处理或反汇编入站的批处理 （文件或包含多个 SWIFT 消息的消息）。</span><span class="sxs-lookup"><span data-stu-id="3fddd-105">The SWIFT disassembler is able to inbound debatching in which it processes or disassembles inbound batches (files or messages containing multiple SWIFT messages).</span></span> <span data-ttu-id="3fddd-106">允许使用 SWIFT 反汇编程序配置属性具有相同名称的入站解除批处理。</span><span class="sxs-lookup"><span data-stu-id="3fddd-106">You enable inbound debatching using the SWIFT disassembler configuration property of the same name.</span></span> <span data-ttu-id="3fddd-107">启用入站解除批处理后，SWIFT 反汇编程序期望接收要包括多个 SWIFT 消息的批的所有消息。</span><span class="sxs-lookup"><span data-stu-id="3fddd-107">After you enable inbound debatching, the SWIFT disassembler expects all messages that it receives to be batches that include multiple SWIFT messages.</span></span> <span data-ttu-id="3fddd-108">批处理可能或可能不包括批处理信封 （一个批处理标头和批处理尾部），并在一个批处理中每个 SWIFT 消息可能包含或不包含消息信封 （消息标头和消息尾部）。</span><span class="sxs-lookup"><span data-stu-id="3fddd-108">A batch may or may not include a batch envelope (a batch header and a batch trailer), and each individual SWIFT message within a batch may or may not include a message envelope (a message header and a message trailer).</span></span> <span data-ttu-id="3fddd-109">你可以配置这些批次属性 （格式），使用以下 SWIFT 反汇编程序配置属性：</span><span class="sxs-lookup"><span data-stu-id="3fddd-109">You can configure these batch attributes (formats) using the following SWIFT disassembler configuration properties:</span></span>  
  
- <span data-ttu-id="3fddd-110">批处理标头架构</span><span class="sxs-lookup"><span data-stu-id="3fddd-110">Batch Header Schema</span></span>  
  
- <span data-ttu-id="3fddd-111">批处理尾部架构</span><span class="sxs-lookup"><span data-stu-id="3fddd-111">Batch Trailer Schema</span></span>  
  
- <span data-ttu-id="3fddd-112">消息标头架构</span><span class="sxs-lookup"><span data-stu-id="3fddd-112">Message Header Schema</span></span>  
  
- <span data-ttu-id="3fddd-113">消息尾部架构</span><span class="sxs-lookup"><span data-stu-id="3fddd-113">Message Trailer Schema</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="3fddd-114">设置这些属性为"None"的任何指示的入站的批处理不包含该特定部分。</span><span class="sxs-lookup"><span data-stu-id="3fddd-114">Setting any of these properties to "None" indicates that the inbound batch does not include that particular part.</span></span>  
  
  <span data-ttu-id="3fddd-115">SWIFT 反汇编程序需要具有以下结构的所有入站的批：</span><span class="sxs-lookup"><span data-stu-id="3fddd-115">The SWIFT disassembler expects all inbound batches to have the following structure:</span></span>  
  
  <span data-ttu-id="3fddd-116">**批处理标头**</span><span class="sxs-lookup"><span data-stu-id="3fddd-116">**Batch Header**</span></span>  
  
  <span data-ttu-id="3fddd-117">**消息标头**</span><span class="sxs-lookup"><span data-stu-id="3fddd-117">**Message Header**</span></span>  
  
  <span data-ttu-id="3fddd-118">**SWIFT 的交换消息 （SWIFT 块 1 到 5）**</span><span class="sxs-lookup"><span data-stu-id="3fddd-118">**SWIFT Interchange/Message (SWIFT Blocks 1 to 5)**</span></span>  
  
  <span data-ttu-id="3fddd-119">**消息尾部**</span><span class="sxs-lookup"><span data-stu-id="3fddd-119">**Message Trailer**</span></span>  
  
  <span data-ttu-id="3fddd-120">**批处理尾部**</span><span class="sxs-lookup"><span data-stu-id="3fddd-120">**Batch Trailer**</span></span>  
  
  <span data-ttu-id="3fddd-121">在此结构中，可以考虑"消息块"是**消息标头 – SWIFT 交换 – 消息尾部**部件。</span><span class="sxs-lookup"><span data-stu-id="3fddd-121">Within this structure, you can consider a "message block" to be the **Message Header – SWIFT Interchange – Message Trailer** parts.</span></span> <span data-ttu-id="3fddd-122">多个"消息块"的一系列组成一批中的多个 SWIFT 消息。</span><span class="sxs-lookup"><span data-stu-id="3fddd-122">A series of multiple "message blocks" makes up the multiple SWIFT messages in a batch.</span></span> <span data-ttu-id="3fddd-123">批处理标头、 消息标头、 消息尾部和批处理尾部是可选的但在重复必须保持一致。</span><span class="sxs-lookup"><span data-stu-id="3fddd-123">The Batch Header, Message Header, Message Trailer, and Batch Trailer are optional, but must be consistent across repetitions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3fddd-124">不要用 SWIFT 标头和尾部块混淆消息信封 （消息标头和消息尾部）。</span><span class="sxs-lookup"><span data-stu-id="3fddd-124">Do not confuse the message envelope (Message Header and Message Trailer) with the SWIFT header and trailer blocks.</span></span> <span data-ttu-id="3fddd-125">在批处理的上下文中，应查看包含 SWIFT 标头和尾部块作为一个整体 (atomic) 单元的 SWIFT 消息 （交换）。</span><span class="sxs-lookup"><span data-stu-id="3fddd-125">In the context of batches, you should view the SWIFT message (interchange), including the SWIFT header and trailer blocks, as a holistic (atomic) unit.</span></span> <span data-ttu-id="3fddd-126">在此上下文中，消息标头和消息尾部指封装在批处理中的每个 SWIFT 消息的信封。</span><span class="sxs-lookup"><span data-stu-id="3fddd-126">In this context, the Message Header and Message Trailer refer to the envelope that wraps each SWIFT message in a batch.</span></span>  
  
 <span data-ttu-id="3fddd-127">若要更准确地讲 express 此结构，其选项，其可重复性，请考虑如何[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]定义批处理：</span><span class="sxs-lookup"><span data-stu-id="3fddd-127">To express this structure, its options, and its repeatability more formally, consider how [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] defines a batch:</span></span>  
  
- <span data-ttu-id="3fddd-128">**批处理标头**为由**BH**</span><span class="sxs-lookup"><span data-stu-id="3fddd-128">**Batch Header** is represented by **BH**</span></span>  
  
- <span data-ttu-id="3fddd-129">**消息标头**为由**MH**</span><span class="sxs-lookup"><span data-stu-id="3fddd-129">**Message Header** is represented by **MH**</span></span>  
  
- <span data-ttu-id="3fddd-130">**SWIFT 交换**为由**SI**</span><span class="sxs-lookup"><span data-stu-id="3fddd-130">**SWIFT Interchange** is represented by **SI**</span></span>  
  
- <span data-ttu-id="3fddd-131">**消息尾部**为由**MT**</span><span class="sxs-lookup"><span data-stu-id="3fddd-131">**Message Trailer** is represented by **MT**</span></span>  
  
- <span data-ttu-id="3fddd-132">**批处理尾部**为由**BT**。</span><span class="sxs-lookup"><span data-stu-id="3fddd-132">**Batch Trailer** is represented by **BT**.</span></span>  
  
  <span data-ttu-id="3fddd-133">表示预期的批处理结构的表达式如下所示：</span><span class="sxs-lookup"><span data-stu-id="3fddd-133">The expression that represents the expected batch structure is as follows:</span></span>  
  
  `[BH] ([MH] SI [MT])* [BT]  `
  
  <span data-ttu-id="3fddd-134">方括号 ( `[ ] ` ) 指示的部分是可选。</span><span class="sxs-lookup"><span data-stu-id="3fddd-134">The brackets ( `[ ] ` ) indicate that the part is optional.</span></span> <span data-ttu-id="3fddd-135">星号 (**\\* \* *) 指示的块是可重复。无论谁生成消息批，则必须使用消息标头 (*<em>MH</em>*) 和尾部 (*<em>MT</em>*) 中的每次重复的一致地 (`[MH] SI [MT]`)。</span><span class="sxs-lookup"><span data-stu-id="3fddd-135">The asterisk (\**\\*\*\*)indicates that the block is repeatable. Whoever builds the message batch must use the message header (*<em>MH</em>*) and trailer (*<em>MT</em>\*) consistently in each repetition of (`[MH] SI [MT]`).</span></span>  
  
  <span data-ttu-id="3fddd-136">SWIFT 反汇编程序是能够处理遵循上面的结构，任何入站的批处理，因为结构中的每个部件符合平面文件架构。</span><span class="sxs-lookup"><span data-stu-id="3fddd-136">The SWIFT disassembler is able to process any inbound batch that obeys the above structure, because each part in the structure conforms to a flat-file schema.</span></span> <span data-ttu-id="3fddd-137">但是，如果不使用的可选批处理标头/尾部和消息标头/尾部，则消息将符合这些架构。</span><span class="sxs-lookup"><span data-stu-id="3fddd-137">However, if you do not use the optional batch header/trailer and message header/trailer, the message will not conform to those schemas.</span></span> <span data-ttu-id="3fddd-138">因此，包含仅连续 SWIFT 消息的批处理将具有批头部架构、 批处理尾部架构、 消息标头架构和消息尾部架构属性设置为"None"。</span><span class="sxs-lookup"><span data-stu-id="3fddd-138">As a result, a batch containing only consecutive SWIFT messages will have the Batch Header Schema, Batch Trailer Schema, Message Header Schema, and Message Trailer Schema properties set to "None".</span></span>  

## <a name="customize-schemas-for-batching"></a><span data-ttu-id="3fddd-139">自定义批处理的架构</span><span class="sxs-lookup"><span data-stu-id="3fddd-139">Customize schemas for batching</span></span>  
 <span data-ttu-id="3fddd-140">您可以自定义批处理标头/尾部和消息标头/尾部的架构。</span><span class="sxs-lookup"><span data-stu-id="3fddd-140">You can customize the schemas for the batch header/trailer and message header/trailer.</span></span> <span data-ttu-id="3fddd-141">下面的批处理是一个示例：</span><span class="sxs-lookup"><span data-stu-id="3fddd-141">An example is the following batch:</span></span>  
  
```  
4  
SWIFT Message # 1  
$  
SWIFT Message # 2  
$  
SWIFT Message # 3  
$  
SWIFT Message # 4  
$  
```  
  
 <span data-ttu-id="3fddd-142">若要处理这种类型的批处理，可以设置批处理的架构属性，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3fddd-142">To handle this type of batch, you would set the schema properties for the batch as follows:</span></span>  
  
- <span data-ttu-id="3fddd-143">分析由回车符-分隔的单个数字 （消息计数） 的平面文件架构设置批处理标头架构属性。</span><span class="sxs-lookup"><span data-stu-id="3fddd-143">You set the Batch Header Schema property to a flat-file schema that parses a single number (message count) delimited by carriage-return.</span></span>  
  
- <span data-ttu-id="3fddd-144">将对单个 $ 符号和回车符-分析的平面文件架构设置消息尾部架构。</span><span class="sxs-lookup"><span data-stu-id="3fddd-144">You set the Message Trailer Schema to a flat-file schema that parses a single $ symbol and carriage-return.</span></span>  
  
- <span data-ttu-id="3fddd-145">将剩余的信封架构 （批处理尾部架构和消息标头架构） 设置为无。</span><span class="sxs-lookup"><span data-stu-id="3fddd-145">You set the remaining envelope schemas (Batch Trailer Schema and Message Header Schema) to None.</span></span>  
  
  <span data-ttu-id="3fddd-146">可以配置 SWIFT 反汇编程序，使它通过创建并指定适当的平面文件信封架构组合处理几乎任何 SWIFT 消息批。</span><span class="sxs-lookup"><span data-stu-id="3fddd-146">You can configure the SWIFT disassembler such that it processes just about any SWIFT message batch by creating and specifying the appropriate combination of flat-file envelope schemas.</span></span> <span data-ttu-id="3fddd-147">此功能是非常灵活。</span><span class="sxs-lookup"><span data-stu-id="3fddd-147">This functionality is very flexible.</span></span>  
  
  <span data-ttu-id="3fddd-148">SWIFT 反汇编程序始终会尝试完成的整个批次处理，即使在遇到错误，在此过程。</span><span class="sxs-lookup"><span data-stu-id="3fddd-148">The SWIFT disassembler always attempts to complete processing of an entire batch, even when it encounters errors along the way.</span></span> <span data-ttu-id="3fddd-149">这使它能够收集并一次性地报告任意多个错误。</span><span class="sxs-lookup"><span data-stu-id="3fddd-149">This enables it to collect and report as many errors as possible all at once.</span></span> <span data-ttu-id="3fddd-150">若要执行此"最大努力"启发式，SWIFT 反汇编程序必须进行某些决策和假设选择要在遇到新部件时使用的架构时或发生分析错误。</span><span class="sxs-lookup"><span data-stu-id="3fddd-150">To perform this "best effort" heuristic, the SWIFT disassembler must make certain decisions and assumptions when selecting the schema to use upon encountering a new part, or if a parsing error occurs.</span></span> <span data-ttu-id="3fddd-151">选择正确的架构并不总是可能根据的性质和分析错误和信封架构和 SWIFT 交换架构之间的多义性/相似性的位置。</span><span class="sxs-lookup"><span data-stu-id="3fddd-151">Selecting the correct schema is not always possible depending upon the nature and location of a parse error and the ambiguity/similarity between envelope schemas and the SWIFT interchange schemas.</span></span> <span data-ttu-id="3fddd-152">在某些情况下，可以通过使用精心设计的信封架构中选择错误的架构的可能性降至。</span><span class="sxs-lookup"><span data-stu-id="3fddd-152">In some cases, you can minimize the possibility of selecting the wrong schema by using well-designed envelope schemas.</span></span> <span data-ttu-id="3fddd-153">如果拆装器遇到致命的分析错误或拆装器无法确定正确的架构，拆装器将批处理失败而不会处理剩余的数据。</span><span class="sxs-lookup"><span data-stu-id="3fddd-153">If the disassembler encounters a fatal parse error or the disassembler cannot determine the correct schema, the disassembler will fail the batch without processing the remaining data.</span></span>  
  
  <span data-ttu-id="3fddd-154">当**入站解除批处理**是**启用**(设置为**True**)，SWIFT 反汇编程序将使用指定的批处理信封 （批处理标头架构的架构的批处理分析和批处理尾部架构） 和消息信封 （消息标头架构和消息尾部架构），以及指定用于分析的批处理中的 SWIFT 消息 （交换） 的架构。</span><span class="sxs-lookup"><span data-stu-id="3fddd-154">When **Inbound Debatching** is **enabled** (set to **True**), the SWIFT disassembler parses the batch using the schemas specified for the batch envelope (Batch Header Schema and Batch Trailer Schema) and message envelope (Message Header Schema and Message Trailer Schema), as well as the schema specified for parsing the SWIFT messages (interchanges) in the batch.</span></span> <span data-ttu-id="3fddd-155">为批处理中的 SWIFT 消息，消息类型和架构可以被动态地发现和加载单个非批处理消息的方式相同 （通过指定 SWIFT 标头架构）。</span><span class="sxs-lookup"><span data-stu-id="3fddd-155">For the SWIFT messages in the batch, the message type and schema can be dynamically discovered and loaded in the same way as single non-batch messages (by specifying a SWIFT Header Schema).</span></span> <span data-ttu-id="3fddd-156">SWIFT 反汇编程序如何执行架构解析的详细信息，请参阅[动态消息类型发现和架构解析](../../adapters-and-accelerators/accelerator-swift/dynamic-message-type-discovery-and-schema-resolution.md)。</span><span class="sxs-lookup"><span data-stu-id="3fddd-156">For more information about how the SWIFT disassembler performs schema resolution, see [Dynamic Message Type Discovery and Schema Resolution](../../adapters-and-accelerators/accelerator-swift/dynamic-message-type-discovery-and-schema-resolution.md).</span></span>  
  
  <span data-ttu-id="3fddd-157">SWIFT 反汇编程序分析，并单独验证入站批处理中的每个 SWIFT 消息。</span><span class="sxs-lookup"><span data-stu-id="3fddd-157">The SWIFT disassembler parses and validates each SWIFT message in an inbound batch individually.</span></span> <span data-ttu-id="3fddd-158">它将执行下面的批处理处理序列：</span><span class="sxs-lookup"><span data-stu-id="3fddd-158">It performs the following batch processing sequence:</span></span>  
  
1. <span data-ttu-id="3fddd-159">如果已指定批处理标头架构，分析批处理标头。</span><span class="sxs-lookup"><span data-stu-id="3fddd-159">Parses the batch header if you have specified the Batch Header Schema.</span></span>  
  
2. <span data-ttu-id="3fddd-160">如果已指定消息标头架构，分析消息信封标头。</span><span class="sxs-lookup"><span data-stu-id="3fddd-160">Parses the message envelope header if you have specified the Message Header Schema.</span></span>  
  
3. <span data-ttu-id="3fddd-161">分析 SWIFT 交换 （消息）。</span><span class="sxs-lookup"><span data-stu-id="3fddd-161">Parses the SWIFT interchange (message).</span></span>  
  
4. <span data-ttu-id="3fddd-162">如果已启用了 XML 验证，请验证 XML 约束针对的 SWIFT 消息。</span><span class="sxs-lookup"><span data-stu-id="3fddd-162">Validates the SWIFT message against XML constraints if you have enabled XML validation.</span></span>  
  
5. <span data-ttu-id="3fddd-163">如果已启用了 BRE 验证，请验证对 BRE 策略 （SWIFT 网络和使用情况规则） SWIFT 消息。</span><span class="sxs-lookup"><span data-stu-id="3fddd-163">Validates the SWIFT message against BRE policies (SWIFT network and usage rules) if you have enabled BRE validation.</span></span>  
  
6. <span data-ttu-id="3fddd-164">如果指定消息尾部架构，分析消息信封尾部。</span><span class="sxs-lookup"><span data-stu-id="3fddd-164">Parses the message envelope trailer if the Message Trailer Schema is specified.</span></span>  
  
7. <span data-ttu-id="3fddd-165">重复步骤 2 到 6，直到拆装器找不到更多消息批次中。</span><span class="sxs-lookup"><span data-stu-id="3fddd-165">Repeats Steps 2 to 6 until the disassembler does not find any more messages in the batch.</span></span>  
  
8. <span data-ttu-id="3fddd-166">如果已指定批处理尾部架构，分析批处理尾部。</span><span class="sxs-lookup"><span data-stu-id="3fddd-166">Parses the batch trailer if you have specified the Batch Trailer Schema.</span></span>  
  
   <span data-ttu-id="3fddd-167">你可以配置 SWIFT 反汇编程序不同的执行操作的批处理数据，它将分析和验证使用以下 SWIFT 反汇编程序配置属性：</span><span class="sxs-lookup"><span data-stu-id="3fddd-167">You can configure the SWIFT disassembler to do different things with the batch data that it parses and validates using the following SWIFT disassembler configuration properties:</span></span>  
  
- <span data-ttu-id="3fddd-168">**碎片**属性确定是否单独 SWIFT 反汇编程序应发布每个消息批处理到 MessageBox 数据库中 (也就是说，对于每个消息，上面的步骤 6 的每个匹配项后)，还是应完成所有步骤 1 到 8，然后将整个批次发布以本机形式 （输入的精确副本），作为单个消息发布到 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="3fddd-168">The **Fragmentation** property determines if the SWIFT disassembler should publish each message in the batch to the MessageBox database individually (that is, for each message, after each occurrence of Step 6 above), or if it should complete all of steps 1 to 8 and then publish the entire batch, in native form (exact copy of input), as a single message to the MessageBox database.</span></span> <span data-ttu-id="3fddd-169">您设置**碎片**到**True**启用碎片和单独发布在批处理中的消息。</span><span class="sxs-lookup"><span data-stu-id="3fddd-169">You set **Fragmentation** to **True** to enable fragmentation and publish messages from a batch individually.</span></span> <span data-ttu-id="3fddd-170">您设置**碎片**到**False**禁用碎片并将整批，以本机形式发布为仅在处理整个批次一条消息。</span><span class="sxs-lookup"><span data-stu-id="3fddd-170">You set **Fragmentation** to **False** to disable fragmentation and publish the entire batch, in native form, as a single message only after processing the entire batch.</span></span> <span data-ttu-id="3fddd-171">通常情况下，设置**碎片**到**禁用**方案时仅需要 BizTalk Accelerator for SWIFT ([!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]) 来分析和验证入站的批处理和失败，或转发，在同一个窗体[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]收到它们。</span><span class="sxs-lookup"><span data-stu-id="3fddd-171">Typically, set **Fragmentation** to **Disabled**for scenarios when you only need the BizTalk Accelerator for SWIFT ([!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]) to parse and validate inbound batches and either failed, or forwarded, in the same form that [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] received them.</span></span> <span data-ttu-id="3fddd-172">通常设置**碎片**到**已启用**想在其中[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]来转换或修改批处理内的消息后分析和验证，或者当你想[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]进行重新排序顺序不同于为批中的消息[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]最初接收到中。</span><span class="sxs-lookup"><span data-stu-id="3fddd-172">You usually set **Fragmentation** to **Enabled** for scenarios in which you want [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] to transform or modify messages within a batch after parsing and validation, or when you want [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] to re-sort messages in a batch to an order different from what [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] originally received them in.</span></span> <span data-ttu-id="3fddd-173">此外设置**碎片**到**已启用**对于入站的批处理中包含有不同的最终目标的消息的方案。</span><span class="sxs-lookup"><span data-stu-id="3fddd-173">You also set **Fragmentation** to **Enabled** for scenarios in which an inbound batch contains messages that have differing final destinations.</span></span>  
  
- <span data-ttu-id="3fddd-174">**保留批处理标头 / 保留批处理尾部**属性确定 SWIFT 反汇编程序是应放弃还是在分析后保留的批处理的信封 （标头和尾部） 数据。</span><span class="sxs-lookup"><span data-stu-id="3fddd-174">The **Preserve Batch Header / Preserve Batch Trailer** property determines if the SWIFT disassembler should discard or preserve the batch envelope (header and trailer) data after parsing it.</span></span> <span data-ttu-id="3fddd-175">如果您设置**保留批处理标头或保留批尾部**到**True**，拆装器将相应的批次部分 (已分析的 XML) 发布到 MessageBox 数据库，是作为单条消息。</span><span class="sxs-lookup"><span data-stu-id="3fddd-175">If you set **Preserve Batch Header or Preserve Batch Trailer** to **True**, the disassembler publishes the corresponding batch part (parsed XML) to the MessageBox database as individual messages.</span></span> <span data-ttu-id="3fddd-176">拆装器将数据发布在多部分消息的正文部分。</span><span class="sxs-lookup"><span data-stu-id="3fddd-176">The disassembler publishes the data in the body part of the multi-part message.</span></span> <span data-ttu-id="3fddd-177">拆装器将特殊的上下文属性升级，以便[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]可将它们是在批处理中将这些消息给它们原来的位置的批处理和的序号位置相关联 （批处理标头的第一个位置，为批处理尾部的最后一个位置）。</span><span class="sxs-lookup"><span data-stu-id="3fddd-177">The disassembler promotes special context properties so that [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] can correlate these messages to the batch that they came from and the ordinal position they were in within the batch (first position for batch header, last position for batch trailer).</span></span> <span data-ttu-id="3fddd-178">如果您设置**保留批处理标头或保留批尾部**到**False**，拆装器在分析后放弃相应的批次部分 （已分析的数据）。</span><span class="sxs-lookup"><span data-stu-id="3fddd-178">If you set **Preserve Batch Header or Preserve Batch Trailer** to **False**, the disassembler discards the corresponding batch part (parsed data) after parsing.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="3fddd-179">仅当启用碎片时，这些配置属性都有效 (**碎片**设置为**True**)。</span><span class="sxs-lookup"><span data-stu-id="3fddd-179">These configuration properties are valid only when fragmentation is enabled (**Fragmentation** set to **True**).</span></span> <span data-ttu-id="3fddd-180">因此保留设置是不相关时碎片处于禁用状态，拆装器会以本机形式，向 MessageBox 数据库中发布整个批次的精确副本 (*一切*保留)。</span><span class="sxs-lookup"><span data-stu-id="3fddd-180">When fragmentation is disabled, the disassembler publishes an exact copy of the entire batch, in native form, to the MessageBox database, so preservation settings are irrelevant (*everything* is preserved).</span></span>  
  
- <span data-ttu-id="3fddd-181">**保留消息标头** / **保留消息尾部**属性确定 SWIFT 反汇编程序是应放弃还是保留消息信封 （消息标头和尾部）在解析它们。</span><span class="sxs-lookup"><span data-stu-id="3fddd-181">The **Preserve Message Header** / **Preserve Message Trailer** property determines if the SWIFT disassembler should discard or preserve the message envelopes (message headers and trailers) after parsing them.</span></span> <span data-ttu-id="3fddd-182">如果您设置**保留消息标头或保留消息尾部**到**True**，拆装器将相应的批次部分 (已分析的 XML) 发布到 MessageBox 数据库*连同它所包装的单个 SWIFT 消息*。</span><span class="sxs-lookup"><span data-stu-id="3fddd-182">If you set **Preserve Message Header or Preserve Message Trailer** to **True**, the disassembler publishes the corresponding batch part (parsed XML) to the MessageBox database *along with the individual SWIFT message that it wraps*.</span></span> <span data-ttu-id="3fddd-183">拆装器将发布消息信封中的标头**标头**多部分消息的一部分。</span><span class="sxs-lookup"><span data-stu-id="3fddd-183">The disassembler publishes message envelope headers in the **header** part of the multi-part message.</span></span> <span data-ttu-id="3fddd-184">拆装器将发布中的消息信封尾部**尾部**多部分消息的一部分。</span><span class="sxs-lookup"><span data-stu-id="3fddd-184">The disassembler publishes message envelope trailers in the **trailer** part of the multi-part message.</span></span> <span data-ttu-id="3fddd-185">拆装器将发布消息信封中包含的 SWIFT 消息**正文**相同的多部分消息的一部分。</span><span class="sxs-lookup"><span data-stu-id="3fddd-185">The disassembler publishes the SWIFT message contained in the message envelope in the **body** part of the same multi-part message.</span></span> <span data-ttu-id="3fddd-186">拆装器将特殊的上下文属性升级，以便[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]可将这些消息给它们原来的批处理和它们所处的批处理中的序号位置相关联。</span><span class="sxs-lookup"><span data-stu-id="3fddd-186">The disassembler promotes special context properties so that [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] can correlate these messages to the batch they came from and the ordinal position that they were in within the batch.</span></span> <span data-ttu-id="3fddd-187">如果您设置**保留消息标头或保留消息尾部**到**False**，拆装器在分析后放弃相应的批次部分 （已分析的数据）。</span><span class="sxs-lookup"><span data-stu-id="3fddd-187">If you set **Preserve Message Header or Preserve Message Trailer** to **False**, the disassembler discards the corresponding batch part (parsed data) after parsing.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="3fddd-188">仅当启用碎片时，这些配置属性都有效 (**碎片**设置为**True**)。</span><span class="sxs-lookup"><span data-stu-id="3fddd-188">These configuration properties are valid only when fragmentation is enabled (**Fragmentation** set to **True**).</span></span> <span data-ttu-id="3fddd-189">因此保留设置是不相关时碎片处于禁用状态，拆装器会以本机形式，向 MessageBox 数据库中发布整个批次的精确副本 (*一切*保留)。</span><span class="sxs-lookup"><span data-stu-id="3fddd-189">When fragmentation is disabled, the disassembler publishes an exact copy of the entire batch, in native form, to the MessageBox database, so preservation settings are irrelevant (*everything* is preserved).</span></span>  
  
  <span data-ttu-id="3fddd-190">有关每个配置属性，有关详细信息，以及其他使用情况和配置信息，请参阅[SWIFT 反汇编程序配置属性](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="3fddd-190">For more information about each configuration property, as well as other usage and configuration information, see [SWIFT Disassembler Configuration Properties](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md).</span></span> <span data-ttu-id="3fddd-191">有关 MessageBox 数据库发布和多部分消息的详细信息，请参阅 BizTalk Server 帮助。</span><span class="sxs-lookup"><span data-stu-id="3fddd-191">For more information about MessageBox database publishing and multi-part messages, see BizTalk Server Help.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="3fddd-192">下一步</span><span class="sxs-lookup"><span data-stu-id="3fddd-192">Next step</span></span>
  
[<span data-ttu-id="3fddd-193">与批处理相关的已提升属性</span><span class="sxs-lookup"><span data-stu-id="3fddd-193">Batch-Related Promoted Properties</span></span>](batch-related-promoted-properties.md)
