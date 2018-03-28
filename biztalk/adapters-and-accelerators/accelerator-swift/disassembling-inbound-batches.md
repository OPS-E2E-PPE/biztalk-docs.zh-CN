---
title: 反汇编入站的批处理 SWIFT |Microsoft 文档
description: Debatch 入站的消息和自定义批处理 BizTalk Server 中使用 SWIFT 快捷键的架构
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 11cb5672-1155-4648-b1fd-c9a3bc30e351
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f14a199e3422a45235727d2d16fc1464e2e4927
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="disassemble-inbound-batches"></a><span data-ttu-id="4db77-103">反汇编入站的批处理</span><span class="sxs-lookup"><span data-stu-id="4db77-103">Disassemble Inbound Batches</span></span>

## <a name="debatch-inbound-message"></a><span data-ttu-id="4db77-104">Debatch 入站的消息</span><span class="sxs-lookup"><span data-stu-id="4db77-104">Debatch inbound message</span></span>
<span data-ttu-id="4db77-105">SWIFT 反汇编程序可以为入站 debatching 它处理或进行反汇编，入站的批处理 （文件或包含多个 SWIFT 消息的消息）。</span><span class="sxs-lookup"><span data-stu-id="4db77-105">The SWIFT disassembler is able to inbound debatching in which it processes or disassembles inbound batches (files or messages containing multiple SWIFT messages).</span></span> <span data-ttu-id="4db77-106">你启用入站 debatching 使用相同的名称的 SWIFT 反汇编程序配置属性。</span><span class="sxs-lookup"><span data-stu-id="4db77-106">You enable inbound debatching using the SWIFT disassembler configuration property of the same name.</span></span> <span data-ttu-id="4db77-107">启用入站 debatching 后，SWIFT 反汇编程序期望接收要包括多个 SWIFT 消息的批处理的所有消息。</span><span class="sxs-lookup"><span data-stu-id="4db77-107">After you enable inbound debatching, the SWIFT disassembler expects all messages that it receives to be batches that include multiple SWIFT messages.</span></span> <span data-ttu-id="4db77-108">批处理可能包含或不包含批处理信封 （批处理标头和批处理尾部），并在一个批处理中每个单个 SWIFT 消息可能包含或不包含消息信封 （消息标头和消息尾部）。</span><span class="sxs-lookup"><span data-stu-id="4db77-108">A batch may or may not include a batch envelope (a batch header and a batch trailer), and each individual SWIFT message within a batch may or may not include a message envelope (a message header and a message trailer).</span></span> <span data-ttu-id="4db77-109">你可以配置这些批处理属性 （格式），使用以下 SWIFT 反汇编程序配置属性：</span><span class="sxs-lookup"><span data-stu-id="4db77-109">You can configure these batch attributes (formats) using the following SWIFT disassembler configuration properties:</span></span>  
  
-   <span data-ttu-id="4db77-110">批处理标头架构</span><span class="sxs-lookup"><span data-stu-id="4db77-110">Batch Header Schema</span></span>  
  
-   <span data-ttu-id="4db77-111">批处理尾部架构</span><span class="sxs-lookup"><span data-stu-id="4db77-111">Batch Trailer Schema</span></span>  
  
-   <span data-ttu-id="4db77-112">消息标头架构</span><span class="sxs-lookup"><span data-stu-id="4db77-112">Message Header Schema</span></span>  
  
-   <span data-ttu-id="4db77-113">消息尾部架构</span><span class="sxs-lookup"><span data-stu-id="4db77-113">Message Trailer Schema</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4db77-114">设置这些属性设置为"None"的任何指示的入站的批处理不包含该特定部分。</span><span class="sxs-lookup"><span data-stu-id="4db77-114">Setting any of these properties to "None" indicates that the inbound batch does not include that particular part.</span></span>  
  
 <span data-ttu-id="4db77-115">SWIFT 反汇编程序需要具有以下结构的所有入站的批：</span><span class="sxs-lookup"><span data-stu-id="4db77-115">The SWIFT disassembler expects all inbound batches to have the following structure:</span></span>  
  
 <span data-ttu-id="4db77-116">**批处理标头**</span><span class="sxs-lookup"><span data-stu-id="4db77-116">**Batch Header**</span></span>  
  
 <span data-ttu-id="4db77-117">**消息标头**</span><span class="sxs-lookup"><span data-stu-id="4db77-117">**Message Header**</span></span>  
  
 <span data-ttu-id="4db77-118">**SWIFT 交换/消息 （SWIFT 块 1 到 5）**</span><span class="sxs-lookup"><span data-stu-id="4db77-118">**SWIFT Interchange/Message (SWIFT Blocks 1 to 5)**</span></span>  
  
 <span data-ttu-id="4db77-119">**消息预告片**</span><span class="sxs-lookup"><span data-stu-id="4db77-119">**Message Trailer**</span></span>  
  
 <span data-ttu-id="4db77-120">**批处理尾**</span><span class="sxs-lookup"><span data-stu-id="4db77-120">**Batch Trailer**</span></span>  
  
 <span data-ttu-id="4db77-121">在此结构中，你可以考虑"消息块"是**– SWIFT 交换 – 的消息标头消息预告片**部分。</span><span class="sxs-lookup"><span data-stu-id="4db77-121">Within this structure, you can consider a "message block" to be the **Message Header – SWIFT Interchange – Message Trailer** parts.</span></span> <span data-ttu-id="4db77-122">多个"消息块"的一系列组成批处理中的多个 SWIFT 消息。</span><span class="sxs-lookup"><span data-stu-id="4db77-122">A series of multiple "message blocks" makes up the multiple SWIFT messages in a batch.</span></span> <span data-ttu-id="4db77-123">批处理标头、 消息标头、 消息尾部和批处理尾是可选的但必须一致重复。</span><span class="sxs-lookup"><span data-stu-id="4db77-123">The Batch Header, Message Header, Message Trailer, and Batch Trailer are optional, but must be consistent across repetitions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4db77-124">不要用 SWIFT 的标头和尾块混淆消息信封 （消息头和消息预告片）。</span><span class="sxs-lookup"><span data-stu-id="4db77-124">Do not confuse the message envelope (Message Header and Message Trailer) with the SWIFT header and trailer blocks.</span></span> <span data-ttu-id="4db77-125">在上下文中的批处理，应查看作为整体 （原子） 单元包括 SWIFT 标头和尾块 SWIFT 消息 （交换）。</span><span class="sxs-lookup"><span data-stu-id="4db77-125">In the context of batches, you should view the SWIFT message (interchange), including the SWIFT header and trailer blocks, as a holistic (atomic) unit.</span></span> <span data-ttu-id="4db77-126">在此上下文中，消息标头和消息尾端引用到批处理中包装每个 SWIFT 消息信封。</span><span class="sxs-lookup"><span data-stu-id="4db77-126">In this context, the Message Header and Message Trailer refer to the envelope that wraps each SWIFT message in a batch.</span></span>  
  
 <span data-ttu-id="4db77-127">若要更准确地讲 express 此结构，其选项，其可重复性，请考虑如何[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]定义一批：</span><span class="sxs-lookup"><span data-stu-id="4db77-127">To express this structure, its options, and its repeatability more formally, consider how [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] defines a batch:</span></span>  
  
-   <span data-ttu-id="4db77-128">**批处理标头**由**BH**</span><span class="sxs-lookup"><span data-stu-id="4db77-128">**Batch Header** is represented by **BH**</span></span>  
  
-   <span data-ttu-id="4db77-129">**消息标头**由**MH**</span><span class="sxs-lookup"><span data-stu-id="4db77-129">**Message Header** is represented by **MH**</span></span>  
  
-   <span data-ttu-id="4db77-130">**SWIFT 交换**由**SI**</span><span class="sxs-lookup"><span data-stu-id="4db77-130">**SWIFT Interchange** is represented by **SI**</span></span>  
  
-   <span data-ttu-id="4db77-131">**消息预告片**由**MT**</span><span class="sxs-lookup"><span data-stu-id="4db77-131">**Message Trailer** is represented by **MT**</span></span>  
  
-   <span data-ttu-id="4db77-132">**批处理预告片**由**BT**。</span><span class="sxs-lookup"><span data-stu-id="4db77-132">**Batch Trailer** is represented by **BT**.</span></span>  
  
 <span data-ttu-id="4db77-133">表示预期的批处理结构表达式，如下所示为：</span><span class="sxs-lookup"><span data-stu-id="4db77-133">The expression that represents the expected batch structure is as follows:</span></span>  
  
 `[BH] ([MH] SI [MT])* [BT]  `
  
 <span data-ttu-id="4db77-134">方括号 ( `[ ] ` ) 指示的部分是可选。</span><span class="sxs-lookup"><span data-stu-id="4db77-134">The brackets ( `[ ] ` ) indicate that the part is optional.</span></span> <span data-ttu-id="4db77-135">星号 (**\***) 指示是可重复的块。</span><span class="sxs-lookup"><span data-stu-id="4db77-135">The asterisk (**\***)indicates that the block is repeatable.</span></span> <span data-ttu-id="4db77-136">任何人员都生成消息批必须使用消息标头 (**MH**) 和尾部 (**MT**) 内的每个重复即可一致 (`[MH] SI [MT]`)。</span><span class="sxs-lookup"><span data-stu-id="4db77-136">Whoever builds the message batch must use the message header (**MH**) and trailer (**MT**) consistently in each repetition of (`[MH] SI [MT]`).</span></span>  
  
 <span data-ttu-id="4db77-137">SWIFT 反汇编程序就能够处理遵循上述结构中，任何入站批次，因为结构中的每个部分符合平面文件架构。</span><span class="sxs-lookup"><span data-stu-id="4db77-137">The SWIFT disassembler is able to process any inbound batch that obeys the above structure, because each part in the structure conforms to a flat-file schema.</span></span> <span data-ttu-id="4db77-138">但是，如果不使用可选的批处理标头/尾和消息标头/尾，则消息将符合这些架构。</span><span class="sxs-lookup"><span data-stu-id="4db77-138">However, if you do not use the optional batch header/trailer and message header/trailer, the message will not conform to those schemas.</span></span> <span data-ttu-id="4db77-139">因此，包含仅连续 SWIFT 消息的批处理将具有批处理标头架构、 批处理尾部架构、 消息标头架构和消息尾部架构属性设置为"None"。</span><span class="sxs-lookup"><span data-stu-id="4db77-139">As a result, a batch containing only consecutive SWIFT messages will have the Batch Header Schema, Batch Trailer Schema, Message Header Schema, and Message Trailer Schema properties set to "None".</span></span>  

## <a name="customize-schemas-for-batching"></a><span data-ttu-id="4db77-140">自定义批处理的架构</span><span class="sxs-lookup"><span data-stu-id="4db77-140">Customize schemas for batching</span></span>  
 <span data-ttu-id="4db77-141">你可以自定义批处理标头/尾和消息标头/尾的架构。</span><span class="sxs-lookup"><span data-stu-id="4db77-141">You can customize the schemas for the batch header/trailer and message header/trailer.</span></span> <span data-ttu-id="4db77-142">下面的批处理是一个示例：</span><span class="sxs-lookup"><span data-stu-id="4db77-142">An example is the following batch:</span></span>  
  
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
  
 <span data-ttu-id="4db77-143">若要处理这种类型的批处理，将按以下方式设置批的架构属性：</span><span class="sxs-lookup"><span data-stu-id="4db77-143">To handle this type of batch, you would set the schema properties for the batch as follows:</span></span>  
  
-   <span data-ttu-id="4db77-144">分析由回车符分隔是一个数字 （消息计数） 的平面文件架构设置批处理标头架构属性。</span><span class="sxs-lookup"><span data-stu-id="4db77-144">You set the Batch Header Schema property to a flat-file schema that parses a single number (message count) delimited by carriage-return.</span></span>  
  
-   <span data-ttu-id="4db77-145">将消息尾部架构设置为将对单个 $ 符号和回车分析的平面文件架构。</span><span class="sxs-lookup"><span data-stu-id="4db77-145">You set the Message Trailer Schema to a flat-file schema that parses a single $ symbol and carriage-return.</span></span>  
  
-   <span data-ttu-id="4db77-146">将剩余的信封架构 （批处理尾部架构和消息标头架构） 设置为无。</span><span class="sxs-lookup"><span data-stu-id="4db77-146">You set the remaining envelope schemas (Batch Trailer Schema and Message Header Schema) to None.</span></span>  
  
 <span data-ttu-id="4db77-147">你可以配置 SWIFT 反汇编程序，以便它可以通过创建并指定合适的平面文件信封架构组合处理几乎任何 SWIFT 消息批次。</span><span class="sxs-lookup"><span data-stu-id="4db77-147">You can configure the SWIFT disassembler such that it processes just about any SWIFT message batch by creating and specifying the appropriate combination of flat-file envelope schemas.</span></span> <span data-ttu-id="4db77-148">此功能是非常灵活。</span><span class="sxs-lookup"><span data-stu-id="4db77-148">This functionality is very flexible.</span></span>  
  
 <span data-ttu-id="4db77-149">SWIFT 拆装器始终尝试完成的整个批处理，处理，即使它遇到此过程中的错误。</span><span class="sxs-lookup"><span data-stu-id="4db77-149">The SWIFT disassembler always attempts to complete processing of an entire batch, even when it encounters errors along the way.</span></span> <span data-ttu-id="4db77-150">这使它能够收集并尽可能在一次报告尽可能多的错误。</span><span class="sxs-lookup"><span data-stu-id="4db77-150">This enables it to collect and report as many errors as possible all at once.</span></span> <span data-ttu-id="4db77-151">若要执行此"最佳效果"启发式，SWIFT 反汇编程序必须进行某些决策和假设选择要在遇到新部件时使用的架构时或发生分析错误。</span><span class="sxs-lookup"><span data-stu-id="4db77-151">To perform this "best effort" heuristic, the SWIFT disassembler must make certain decisions and assumptions when selecting the schema to use upon encountering a new part, or if a parsing error occurs.</span></span> <span data-ttu-id="4db77-152">选择正确的架构并不总是可能具体取决于性质和位置分析错误和信封架构和 SWIFT 交换架构之间的多义性/相似性。</span><span class="sxs-lookup"><span data-stu-id="4db77-152">Selecting the correct schema is not always possible depending upon the nature and location of a parse error and the ambiguity/similarity between envelope schemas and the SWIFT interchange schemas.</span></span> <span data-ttu-id="4db77-153">在某些情况下，可以通过使用设计良好的信封架构中定义的错误的架构的可能性降至。</span><span class="sxs-lookup"><span data-stu-id="4db77-153">In some cases, you can minimize the possibility of selecting the wrong schema by using well-designed envelope schemas.</span></span> <span data-ttu-id="4db77-154">如果拆装器遇到致命的分析错误或反汇编程序无法确定正确的架构，拆装器则该批处理失败而不会处理剩余的数据。</span><span class="sxs-lookup"><span data-stu-id="4db77-154">If the disassembler encounters a fatal parse error or the disassembler cannot determine the correct schema, the disassembler will fail the batch without processing the remaining data.</span></span>  
  
 <span data-ttu-id="4db77-155">当**入站 Debatching**是**启用**(设置为**True**)，SWIFT 反汇编程序分析批处理使用指定的批处理信封 （批处理标头架构的架构和批处理尾部架构） 和消息信封 （消息标头架构和消息尾部架构），以及用于分析批处理中的 SWIFT 消息 （交换） 中指定的架构。</span><span class="sxs-lookup"><span data-stu-id="4db77-155">When **Inbound Debatching** is **enabled** (set to **True**), the SWIFT disassembler parses the batch using the schemas specified for the batch envelope (Batch Header Schema and Batch Trailer Schema) and message envelope (Message Header Schema and Message Trailer Schema), as well as the schema specified for parsing the SWIFT messages (interchanges) in the batch.</span></span> <span data-ttu-id="4db77-156">批处理中的 SWIFT 消息，消息类型和架构可以动态发现和加载作为单个非批处理消息相同的方式 （通过指定 SWIFT 标头架构）。</span><span class="sxs-lookup"><span data-stu-id="4db77-156">For the SWIFT messages in the batch, the message type and schema can be dynamically discovered and loaded in the same way as single non-batch messages (by specifying a SWIFT Header Schema).</span></span> <span data-ttu-id="4db77-157">有关如何 SWIFT 反汇编程序执行架构解析的详细信息，请参阅[动态消息类型发现和架构解决](../../adapters-and-accelerators/accelerator-swift/dynamic-message-type-discovery-and-schema-resolution.md)。</span><span class="sxs-lookup"><span data-stu-id="4db77-157">For more information about how the SWIFT disassembler performs schema resolution, see [Dynamic Message Type Discovery and Schema Resolution](../../adapters-and-accelerators/accelerator-swift/dynamic-message-type-discovery-and-schema-resolution.md).</span></span>  
  
 <span data-ttu-id="4db77-158">SWIFT 反汇编程序分析，并单独验证入站批处理中的每个 SWIFT 消息。</span><span class="sxs-lookup"><span data-stu-id="4db77-158">The SWIFT disassembler parses and validates each SWIFT message in an inbound batch individually.</span></span> <span data-ttu-id="4db77-159">它执行以下的批处理操作序列：</span><span class="sxs-lookup"><span data-stu-id="4db77-159">It performs the following batch processing sequence:</span></span>  
  
1.  <span data-ttu-id="4db77-160">如果已指定批处理标头架构，分析批处理标头。</span><span class="sxs-lookup"><span data-stu-id="4db77-160">Parses the batch header if you have specified the Batch Header Schema.</span></span>  
  
2.  <span data-ttu-id="4db77-161">如果已指定消息标头架构，请分析消息信封标头。</span><span class="sxs-lookup"><span data-stu-id="4db77-161">Parses the message envelope header if you have specified the Message Header Schema.</span></span>  
  
3.  <span data-ttu-id="4db77-162">分析 SWIFT 交换 （消息）。</span><span class="sxs-lookup"><span data-stu-id="4db77-162">Parses the SWIFT interchange (message).</span></span>  
  
4.  <span data-ttu-id="4db77-163">如果已启用 XML 验证来验证 SWIFT 消息根据 XML 的约束。</span><span class="sxs-lookup"><span data-stu-id="4db77-163">Validates the SWIFT message against XML constraints if you have enabled XML validation.</span></span>  
  
5.  <span data-ttu-id="4db77-164">如果已启用 BRE 验证来验证 SWIFT 消息根据 BRE 策略 （SWIFT 网络和使用情况规则）。</span><span class="sxs-lookup"><span data-stu-id="4db77-164">Validates the SWIFT message against BRE policies (SWIFT network and usage rules) if you have enabled BRE validation.</span></span>  
  
6.  <span data-ttu-id="4db77-165">如果指定消息尾部架构，请分析消息信封预告片。</span><span class="sxs-lookup"><span data-stu-id="4db77-165">Parses the message envelope trailer if the Message Trailer Schema is specified.</span></span>  
  
7.  <span data-ttu-id="4db77-166">重复步骤 2 到 6，直到拆装器找不到更多消息批处理中。</span><span class="sxs-lookup"><span data-stu-id="4db77-166">Repeats Steps 2 to 6 until the disassembler does not find any more messages in the batch.</span></span>  
  
8.  <span data-ttu-id="4db77-167">如果已指定批处理尾部架构，分析批处理尾。</span><span class="sxs-lookup"><span data-stu-id="4db77-167">Parses the batch trailer if you have specified the Batch Trailer Schema.</span></span>  
  
 <span data-ttu-id="4db77-168">你可以配置 SWIFT 反汇编程序中，若要执行不同的操作与批处理数据分析和验证使用 SWIFT 拆装器配置的以下属性：</span><span class="sxs-lookup"><span data-stu-id="4db77-168">You can configure the SWIFT disassembler to do different things with the batch data that it parses and validates using the following SWIFT disassembler configuration properties:</span></span>  
  
-   <span data-ttu-id="4db77-169">**碎片**属性确定是否 SWIFT 反汇编程序应逐个每条消息到 MessageBox 数据库批处理中 (即，对于每个消息，在上面的步骤 6 的每个匹配项后)，或如果它应完成所有步骤 1 到 8，然后将整个批处理，发布以本机形式 （输入的精确副本），为到 MessageBox 数据库一条消息。</span><span class="sxs-lookup"><span data-stu-id="4db77-169">The **Fragmentation** property determines if the SWIFT disassembler should publish each message in the batch to the MessageBox database individually (that is, for each message, after each occurrence of Step 6 above), or if it should complete all of steps 1 to 8 and then publish the entire batch, in native form (exact copy of input), as a single message to the MessageBox database.</span></span> <span data-ttu-id="4db77-170">你设置**碎片**到**True**启用碎片和逐个批处理中的消息。</span><span class="sxs-lookup"><span data-stu-id="4db77-170">You set **Fragmentation** to **True** to enable fragmentation and publish messages from a batch individually.</span></span> <span data-ttu-id="4db77-171">你设置**碎片**到**False**禁用碎片并发布整个批次，以本机形式处理整个批次后，才在一个消息。</span><span class="sxs-lookup"><span data-stu-id="4db77-171">You set **Fragmentation** to **False** to disable fragmentation and publish the entire batch, in native form, as a single message only after processing the entire batch.</span></span> <span data-ttu-id="4db77-172">通常情况下，设置**碎片**到**禁用**方案仅在需要时 BizTalk Accelerator for SWIFT ([!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]) 分析和验证入站的批处理和失败，或转发，在同一个窗体[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]收到它们。</span><span class="sxs-lookup"><span data-stu-id="4db77-172">Typically, set **Fragmentation** to **Disabled**for scenarios when you only need the BizTalk Accelerator for SWIFT ([!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]) to parse and validate inbound batches and either failed, or forwarded, in the same form that [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] received them.</span></span> <span data-ttu-id="4db77-173">通常设置**碎片**到**已启用**适合你希望[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]来转换或修改某一批处理中的消息后分析和验证，或者当你想[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]进行重新排序为不同于什么订单的批处理中的消息[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]最初收到它们中。</span><span class="sxs-lookup"><span data-stu-id="4db77-173">You usually set **Fragmentation** to **Enabled** for scenarios in which you want [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] to transform or modify messages within a batch after parsing and validation, or when you want [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] to re-sort messages in a batch to an order different from what [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] originally received them in.</span></span> <span data-ttu-id="4db77-174">你还设置**碎片**到**已启用**对于其中的入站的批处理包含具有不同的最终目标的消息的方案。</span><span class="sxs-lookup"><span data-stu-id="4db77-174">You also set **Fragmentation** to **Enabled** for scenarios in which an inbound batch contains messages that have differing final destinations.</span></span>  
  
-   <span data-ttu-id="4db77-175">**保留批处理标头 / 保留批处理预告片**属性确定 SWIFT 反汇编程序是应放弃还是在分析后保留批处理信封 （标头和尾） 数据。</span><span class="sxs-lookup"><span data-stu-id="4db77-175">The **Preserve Batch Header / Preserve Batch Trailer** property determines if the SWIFT disassembler should discard or preserve the batch envelope (header and trailer) data after parsing it.</span></span> <span data-ttu-id="4db77-176">如果你设置**保留批处理标头或保留批处理预告片**到**True**，拆装器会将相应的批次部分 (已分析的 XML) 发布到 MessageBox 数据库是作为单条消息。</span><span class="sxs-lookup"><span data-stu-id="4db77-176">If you set **Preserve Batch Header or Preserve Batch Trailer** to **True**, the disassembler publishes the corresponding batch part (parsed XML) to the MessageBox database as individual messages.</span></span> <span data-ttu-id="4db77-177">反汇编程序中的多个部分的消息的正文部分的发布数据。</span><span class="sxs-lookup"><span data-stu-id="4db77-177">The disassembler publishes the data in the body part of the multi-part message.</span></span> <span data-ttu-id="4db77-178">反汇编程序提升特殊的上下文属性，以便[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]可以关联到它原来的批处理和的序号位置在批处理中处于这些消息 （批处理标头的第一个位置，为批处理尾的最后一个位置）。</span><span class="sxs-lookup"><span data-stu-id="4db77-178">The disassembler promotes special context properties so that [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] can correlate these messages to the batch that they came from and the ordinal position they were in within the batch (first position for batch header, last position for batch trailer).</span></span> <span data-ttu-id="4db77-179">如果你设置**保留批处理标头或保留批处理预告片**到**False**，拆装器在分析后放弃相应的批次部分 （已分析的数据）。</span><span class="sxs-lookup"><span data-stu-id="4db77-179">If you set **Preserve Batch Header or Preserve Batch Trailer** to **False**, the disassembler discards the corresponding batch part (parsed data) after parsing.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4db77-180">这些配置属性是有效的仅当启用碎片 (**碎片**设置为**True**)。</span><span class="sxs-lookup"><span data-stu-id="4db77-180">These configuration properties are valid only when fragmentation is enabled (**Fragmentation** set to **True**).</span></span> <span data-ttu-id="4db77-181">当禁用碎片时，反汇编程序发布整个批处理的一个精确副本中的本机窗体中，到 MessageBox 数据库中，以便保留设置是不相关 (*的所有内容*保留)。</span><span class="sxs-lookup"><span data-stu-id="4db77-181">When fragmentation is disabled, the disassembler publishes an exact copy of the entire batch, in native form, to the MessageBox database, so preservation settings are irrelevant (*everything* is preserved).</span></span>  
  
-   <span data-ttu-id="4db77-182">**保留消息标头** / **保留消息预告片**属性确定应放弃还是保留消息信封 （消息标头和拖车安排） 应 SWIFT 反汇编程序后分析它们。</span><span class="sxs-lookup"><span data-stu-id="4db77-182">The **Preserve Message Header** / **Preserve Message Trailer** property determines if the SWIFT disassembler should discard or preserve the message envelopes (message headers and trailers) after parsing them.</span></span> <span data-ttu-id="4db77-183">如果你设置**保留消息标头或保留消息预告片**到**True**，拆装器将相应的批次部分 (已分析的 XML) 发布到 MessageBox 数据库*连同它所包装的单个 SWIFT 消息*。</span><span class="sxs-lookup"><span data-stu-id="4db77-183">If you set **Preserve Message Header or Preserve Message Trailer** to **True**, the disassembler publishes the corresponding batch part (parsed XML) to the MessageBox database *along with the individual SWIFT message that it wraps*.</span></span> <span data-ttu-id="4db77-184">反汇编程序发布消息信封标头中的**标头**属于多个部分的消息。</span><span class="sxs-lookup"><span data-stu-id="4db77-184">The disassembler publishes message envelope headers in the **header** part of the multi-part message.</span></span> <span data-ttu-id="4db77-185">反汇编程序发布中的消息信封拖车安排**预告片**属于多个部分的消息。</span><span class="sxs-lookup"><span data-stu-id="4db77-185">The disassembler publishes message envelope trailers in the **trailer** part of the multi-part message.</span></span> <span data-ttu-id="4db77-186">反汇编程序发布消息信封中包含的 SWIFT 消息**正文**相同的多个部分消息的一部分。</span><span class="sxs-lookup"><span data-stu-id="4db77-186">The disassembler publishes the SWIFT message contained in the message envelope in the **body** part of the same multi-part message.</span></span> <span data-ttu-id="4db77-187">反汇编程序提升特殊的上下文属性，以便[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]可以关联到它原来批处理和批处理中它们所处的序号位置这些消息。</span><span class="sxs-lookup"><span data-stu-id="4db77-187">The disassembler promotes special context properties so that [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] can correlate these messages to the batch they came from and the ordinal position that they were in within the batch.</span></span> <span data-ttu-id="4db77-188">如果你设置**保留消息标头或保留消息预告片**到**False**，拆装器在分析后放弃相应的批次部分 （已分析的数据）。</span><span class="sxs-lookup"><span data-stu-id="4db77-188">If you set **Preserve Message Header or Preserve Message Trailer** to **False**, the disassembler discards the corresponding batch part (parsed data) after parsing.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4db77-189">这些配置属性是有效的仅当启用碎片 (**碎片**设置为**True**)。</span><span class="sxs-lookup"><span data-stu-id="4db77-189">These configuration properties are valid only when fragmentation is enabled (**Fragmentation** set to **True**).</span></span> <span data-ttu-id="4db77-190">当禁用碎片时，反汇编程序发布整个批处理的一个精确副本中的本机窗体中，到 MessageBox 数据库中，以便保留设置是不相关 (*的所有内容*保留)。</span><span class="sxs-lookup"><span data-stu-id="4db77-190">When fragmentation is disabled, the disassembler publishes an exact copy of the entire batch, in native form, to the MessageBox database, so preservation settings are irrelevant (*everything* is preserved).</span></span>  
  
 <span data-ttu-id="4db77-191">有关详细信息，有关每个配置属性，以及其他使用情况和配置信息，请参阅[SWIFT 反汇编程序配置属性](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="4db77-191">For more information about each configuration property, as well as other usage and configuration information, see [SWIFT Disassembler Configuration Properties](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md).</span></span> <span data-ttu-id="4db77-192">有关 MessageBox 数据库发布和多个部分的消息的详细信息，请参阅 BizTalk Server 帮助。</span><span class="sxs-lookup"><span data-stu-id="4db77-192">For more information about MessageBox database publishing and multi-part messages, see BizTalk Server Help.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="4db77-193">下一步</span><span class="sxs-lookup"><span data-stu-id="4db77-193">Next step</span></span>
  
[<span data-ttu-id="4db77-194">与批处理相关的已提升属性</span><span class="sxs-lookup"><span data-stu-id="4db77-194">Batch-Related Promoted Properties</span></span>](batch-related-promoted-properties.md)
