---
title: 动态消息类型发现和架构解析 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- dynamic schema resolution
- disassembler, code sample
- schemas, dynamic resolution
- assembler, message types
- disassembler, message types
- code samples, disassembler
ms.assetid: 5f71d3df-a37e-4ef2-9055-b614656203e9
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0bb060a903eae06b4014100cac4e8c7bdc4a1ef
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377941"
---
# <a name="dynamic-message-type-discovery-and-schema-resolution"></a><span data-ttu-id="702af-102">动态消息类型发现和架构解析</span><span class="sxs-lookup"><span data-stu-id="702af-102">Dynamic Message Type Discovery and Schema Resolution</span></span>
<span data-ttu-id="702af-103">Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]可实现动态消息类型发现和架构解析 SWIFT 反汇编程序和组装器中的。</span><span class="sxs-lookup"><span data-stu-id="702af-103">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] enables dynamic message type discovery and schema resolution in both the SWIFT disassembler and assembler.</span></span>  
  
## <a name="swift-disassembler"></a><span data-ttu-id="702af-104">SWIFT 反汇编程序</span><span class="sxs-lookup"><span data-stu-id="702af-104">SWIFT Disassembler</span></span>  
 <span data-ttu-id="702af-105">SWIFT 反汇编程序 (DASM) 能够动态地发现收到的消息的消息类型和加载分析消息所需的相应架构。</span><span class="sxs-lookup"><span data-stu-id="702af-105">The SWIFT disassembler (DASM) has the ability to dynamically discover the message type of a received message and load the appropriate schema needed to parse the message.</span></span> <span data-ttu-id="702af-106">此功能的最大的好处是，您可以配置单个管道使用 SWIFT 反汇编程序来处理任何 SWIFT 消息类型的 SWIFT 消息。</span><span class="sxs-lookup"><span data-stu-id="702af-106">The greatest benefit of this feature is that you can configure a single pipeline using the SWIFT disassembler to process SWIFT messages of any SWIFT message type.</span></span> <span data-ttu-id="702af-107">与本机 BizTalk 平面文件拆装器，不同 SWIFT 反汇编程序不需要生成单独的接收管道的 A4SWIFT 可能会遇到的每种消息类型。</span><span class="sxs-lookup"><span data-stu-id="702af-107">Unlike the native BizTalk flat-file disassembler, the SWIFT disassembler does not require that you build a separate receive pipeline for each message type that A4SWIFT might encounter.</span></span>  
  
 <span data-ttu-id="702af-108">如果您假设，在大多数情况下，系统收到的所有消息都将开头结构上同构的标头数据，可以使用动态消息类型发现。</span><span class="sxs-lookup"><span data-stu-id="702af-108">You can use dynamic message type discovery if you assume that, in most cases, all messages that a system receives will begin with structurally homogeneous header data.</span></span> <span data-ttu-id="702af-109">标头内的数据是显示消息的消息类型的字段。</span><span class="sxs-lookup"><span data-stu-id="702af-109">Within the header data are fields that reveal the message type of the message.</span></span> <span data-ttu-id="702af-110">SWIFT 消息标头数据包含 SWIFT 消息块 1、 2 和 3，使用消息块 （称为应用程序标头） 的 2 中包含的类型信息。</span><span class="sxs-lookup"><span data-stu-id="702af-110">For SWIFT messages, header data consists of SWIFT message blocks 1, 2, and 3, with message type information contained in block 2 (known as the Application Header).</span></span>  
  
 <span data-ttu-id="702af-111">SWIFT DASM 组件可以处理所有"单个"（非批处理） SWIFT 消息在初始状态而无需任何要设置的属性。</span><span class="sxs-lookup"><span data-stu-id="702af-111">The SWIFT DASM component can process all "single" (non-batched) SWIFT Messages out of the box without requiring any of the properties to be set.</span></span> <span data-ttu-id="702af-112">默认情况下，不设置 SWIFT 交换架构和 SWIFT 标头架构;但是，SWIFT DASM 组件将使用位于 Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll SWIFT 标头架构来动态检测 SWIFT 消息类型和处理消息。</span><span class="sxs-lookup"><span data-stu-id="702af-112">By default, the SWIFT Interchange Schema and SWIFT Header schema are not set; however, the SWIFT DASM component will use the SWIFT Header schema present in Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.dll to detect the SWIFT Message Type dynamically and process the messages.</span></span> <span data-ttu-id="702af-113">此外，BRE 和 XML 验证是默认情况下启用以便将完全验证处理任何消息。</span><span class="sxs-lookup"><span data-stu-id="702af-113">Also, BRE and XML Validation are enabled by default so any message that is processed will be completely validated.</span></span> <span data-ttu-id="702af-114">SWIFT 标头架构属性设置为指向 RuntimeSchemas.dll 中的 SWIFT 标头还将导致与上面相同的行为。</span><span class="sxs-lookup"><span data-stu-id="702af-114">Setting the SWIFT Header schema property to point to the SWIFT Header in RuntimeSchemas.dll will also result in the same behavior as above.</span></span>  
  
 <span data-ttu-id="702af-115">当 SWIFT 反汇编程序 SWIFT 标头架构配置属性设置为"None"（默认值） 时，拆装器将动态解析和加载相应的架构，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="702af-115">When the SWIFT Header Schema configuration property for the SWIFT disassembler is set to "None" (the default), the disassembler dynamically resolves and loads the appropriate schema by performing the following steps:</span></span>  
  
1. <span data-ttu-id="702af-116">使用用户指定的标头架构 （由 SWIFT 标头架构配置属性指定） 来分析接收消息 （标头） 开头。</span><span class="sxs-lookup"><span data-stu-id="702af-116">Uses the user-specified header schema (specified by the SWIFT Header Schema configuration property) to parse the beginning (header) of the receive message.</span></span>  
  
2. <span data-ttu-id="702af-117">A4SWIFT_MessageType 升级的属性字段中检查结果"标头 XML"。</span><span class="sxs-lookup"><span data-stu-id="702af-117">Inspects the resulting "header XML" for the A4SWIFT_MessageType promoted property field.</span></span> <span data-ttu-id="702af-118">如果不存在此字段，它使用字段的值作为"消息类型"，并继续执行步骤 4。</span><span class="sxs-lookup"><span data-stu-id="702af-118">If this field exists, it uses the field value as the "message type" and proceeds to Step 4.</span></span> <span data-ttu-id="702af-119">如果该字段不存在，则继续步骤 3。</span><span class="sxs-lookup"><span data-stu-id="702af-119">If the field does not exist, it proceeds to Step 3.</span></span>  
  
3. <span data-ttu-id="702af-120">检查 A4SWIFT_MessageType2 升级的属性字段的标头 XML （预计如果拆装器找不到 A4SWIFT_MessageType 字段）。</span><span class="sxs-lookup"><span data-stu-id="702af-120">Inspects the header XML for the A4SWIFT_MessageType2 promoted property field (expected if the disassembler does not find the A4SWIFT_MessageType field).</span></span> <span data-ttu-id="702af-121">使用 A4SWIFT_MessageType2 字段值为"消息类型"。</span><span class="sxs-lookup"><span data-stu-id="702af-121">Uses the A4SWIFT_MessageType2 field value as the "message type".</span></span>  
  
4. <span data-ttu-id="702af-122">如果在步骤 2 或 3 中标识的"消息类型"，"574"SWIFT 反汇编程序检查该消息类型"574"进行中 （这是拆装器的属性） 在双类型消息列表配置属性中指定的消息类型的列表。</span><span class="sxs-lookup"><span data-stu-id="702af-122">If the "message type" identified in Step 2 or 3 is "574", the SWIFT disassembler checks if the message type "574" is in the list of message types specified in the Dual Type Message List configuration property (which is a property of the disassembler).</span></span> <span data-ttu-id="702af-123">如果是，它将继续到步骤 5。</span><span class="sxs-lookup"><span data-stu-id="702af-123">If yes, it proceeds to Step 5.</span></span> <span data-ttu-id="702af-124">如果不是，继续到步骤 6。</span><span class="sxs-lookup"><span data-stu-id="702af-124">If no, proceeds to Step 6.</span></span>  
  
5. <span data-ttu-id="702af-125">检查标头 XML A4SWIFT_SecondaryMessageType 升级的属性字段。</span><span class="sxs-lookup"><span data-stu-id="702af-125">Inspects header XML for the A4SWIFT_SecondaryMessageType promoted property field.</span></span> <span data-ttu-id="702af-126">如果不存在此字段，拆装器使用字段的值 (例如，"IRSLST") 作为"消息的子类型"，并将其追加到的"消息类型"，例如，"574_IRSLST"。</span><span class="sxs-lookup"><span data-stu-id="702af-126">If this field exists, the disassembler uses the field value (for example, "IRSLST") as the "message sub-type" and appends it to the "message type", for example, "574_IRSLST".</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="702af-127">为步骤 5 的解释是简化的 SWIFT 反汇编程序实际作用以计算消息子类型。</span><span class="sxs-lookup"><span data-stu-id="702af-127">The explanation given for Step 5 is a simplification of what the SWIFT disassembler actually does to evaluate message sub-type.</span></span> <span data-ttu-id="702af-128">实际上，SWIFT 反汇编程序将使用以下算法对以确定消息类型都有子类型，以及如果是这样，哪些的子类型，如下所示。</span><span class="sxs-lookup"><span data-stu-id="702af-128">In actuality, the SWIFT disassembler uses the following algorithm to determine if a message type has sub-types, and if so, what that sub-type is as follows.</span></span>  
  
   ```  
   Given MT type number nxx ...  
   if nxx is in the Dual-Type list {  
     if field 119 exists AND field 119 is NOT null/empty {  
       if n == 1 {  
         if field 119 == "STP" {  
           Use MTnxxPLUS schema  
         } else if field 119 == "REMIT" {  
           Use MTnxx schema  
         } else {  
           Use MTnxx_<field 119> schema  
         }   
       } else {  
         // n != 1  
         Use MTnxx_<field 119> schema  
       }  
     } else {  
       // field 119 does not exist or 119 does exist but is null/empty  
       Use MTnxx schema  
     }  
   } else {  
     // nxx is not a dual-type message  
     Use MTnxx schema  
   }  
   ```  
  
6. <span data-ttu-id="702af-129">拆装器现在知道消息类型，并且它可以通过连接命名前缀和后缀 （例如"MT"的前缀中以使"MT574_IRSLST") 一些固定的架构来形成交换架构名称。</span><span class="sxs-lookup"><span data-stu-id="702af-129">The disassembler now knows the message type, and it can form the interchange schema name by concatenating some fixed schema naming prefixes and suffixes (such as "MT" in the prefix to make "MT574_IRSLST").</span></span>  
  
7. <span data-ttu-id="702af-130">将交换架构加载 （按名称），并将其整个消息**从头开始启动**，使用加载的架构 (这意味着，拆装器对标头数据两次： 一次使用的标头架构，并再次使用交换架构的开头）。</span><span class="sxs-lookup"><span data-stu-id="702af-130">Loads the interchange schema (by name) and parses the entire message, **starting from the beginning**, using the loaded schema (this means that the disassembler parses the header data twice: once using the header schema, and again using the beginning of the interchange schema).</span></span> <span data-ttu-id="702af-131">交换架构必须是可以解析出整个消息，包括标头。</span><span class="sxs-lookup"><span data-stu-id="702af-131">The interchange schema must be able to parse the entire message, including the header.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="702af-132">拆装器可以使用所有 A4SWIFT SWIFT 消息架构来分析整个 SWIFT 交换 （SWIFT 块 1、 2、 3、 4 和 5）。</span><span class="sxs-lookup"><span data-stu-id="702af-132">The disassembler can use all A4SWIFT SWIFT message schemas to parse the entire SWIFT interchange (SWIFT blocks 1, 2, 3, 4, and 5).</span></span> <span data-ttu-id="702af-133">拆装器使用默认 SWIFT 标头架构分析块 1、 2 和 3 只。</span><span class="sxs-lookup"><span data-stu-id="702af-133">The disassembler uses the default SWIFT header schema to parse blocks 1, 2, and 3 only.</span></span> <span data-ttu-id="702af-134">有关详细信息，请参阅下面的内容。</span><span class="sxs-lookup"><span data-stu-id="702af-134">See below for details.</span></span>  
  
   <span data-ttu-id="702af-135">上面所述的架构解析算法意味着，为了使动态消息类型发现正常工作，SWIFT 标头架构必须包含拆装器已提升使用以下升级的属性 （在 A4SWIFT 中定义的字段属性架构，Microsoft.Solutions.A4SWIFT.Property.PropertySchema）：</span><span class="sxs-lookup"><span data-stu-id="702af-135">The schema resolution algorithm described above implies that in order for dynamic message type discovery to work, the SWIFT Header Schema must contain fields that the disassembler has promoted using the following promoted properties (defined in the A4SWIFT Property Schema, Microsoft.Solutions.A4SWIFT.Property.PropertySchema):</span></span>  
  
- <span data-ttu-id="702af-136">**A4SWIFT_MessageType**</span><span class="sxs-lookup"><span data-stu-id="702af-136">**A4SWIFT_MessageType**</span></span>  
  
- <span data-ttu-id="702af-137">**A4SWIFT_MessageType2** (可选如果**A4SWIFT_MessageTypes**使用)</span><span class="sxs-lookup"><span data-stu-id="702af-137">**A4SWIFT_MessageType2** (optional if **A4SWIFT_MessageTypes** is used)</span></span>  
  
- <span data-ttu-id="702af-138">**A4SWIFT_SecondaryMessageType** （可选）</span><span class="sxs-lookup"><span data-stu-id="702af-138">**A4SWIFT_SecondaryMessageType** (optional)</span></span>  
  
  <span data-ttu-id="702af-139">有关这些及其他升级的属性的详细信息，请参阅[A4SWIFT_ \* 升级的属性](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="702af-139">For more information about these and other promoted properties, see [A4SWIFT_\* Promoted Properties](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="702af-140">如果 SWIFT 标头架构设置为**无**，则应指定完整的交换架构**SWIFT 交换架构**属性。</span><span class="sxs-lookup"><span data-stu-id="702af-140">If you set the SWIFT Header Schema to **None**, you should specify a complete interchange schema for the **SWIFT Interchange Schema** property.</span></span> <span data-ttu-id="702af-141">在这种情况下，拆装器使用指定的交换架构分析 A4SWIFT 接收的所有消息。</span><span class="sxs-lookup"><span data-stu-id="702af-141">In this case, the disassembler uses the specified interchange schema to parse all messages that A4SWIFT receives.</span></span> <span data-ttu-id="702af-142">也就是说，可以禁用动态架构解析和配置管道以接收其类型与指定的交换架构匹配的消息。</span><span class="sxs-lookup"><span data-stu-id="702af-142">That is, you disable dynamic schema resolution and configure the pipeline to receive only messages whose type matches the specified interchange schema.</span></span>  
  
 <span data-ttu-id="702af-143">A4SWIFT 安装 SWIFT 标头默认架构 (Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema) 可以分析 SWIFT 标准标头数据并具有必要的升级的属性，以便动态架构解析。</span><span class="sxs-lookup"><span data-stu-id="702af-143">A4SWIFT installs a default SWIFT header schema (Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema) that can parse SWIFT standard header data and has the necessary promoted properties to facilitate dynamic schema resolution.</span></span>  
  
 <span data-ttu-id="702af-144">默认 SWIFT 标头架构有以下升级的字段：</span><span class="sxs-lookup"><span data-stu-id="702af-144">The default SWIFT header schema has the following promoted fields:</span></span>  
  
- <span data-ttu-id="702af-145">**可以忽略 SWIFTHeader/ApplicationHeaderBlock_Input MessageType**。</span><span class="sxs-lookup"><span data-stu-id="702af-145">**SWIFTHeader/ApplicationHeaderBlock_Input/MessageType**.</span></span> <span data-ttu-id="702af-146">拆装器将其升级使用**A4SWIFT_MessageType**属性。</span><span class="sxs-lookup"><span data-stu-id="702af-146">The disassembler promotes this using the **A4SWIFT_MessageType** property.</span></span>  
  
- <span data-ttu-id="702af-147">**SWIFTHeader/ApplicationHeaderBlock_Output/MessageType**.</span><span class="sxs-lookup"><span data-stu-id="702af-147">**SWIFTHeader/ApplicationHeaderBlock_Output/MessageType**.</span></span> <span data-ttu-id="702af-148">拆装器将其升级使用**A4SWIFT_MessageType2**属性。</span><span class="sxs-lookup"><span data-stu-id="702af-148">The disassembler promotes this using the **A4SWIFT_MessageType2** property.</span></span>  
  
- <span data-ttu-id="702af-149">**SWIFTHeader/UserHeaderBlock/ValidationFlag_119**。</span><span class="sxs-lookup"><span data-stu-id="702af-149">**SWIFTHeader/UserHeaderBlock/ValidationFlag_119**.</span></span> <span data-ttu-id="702af-150">拆装器将其升级使用**A4SWIFT_MessageType**属性。</span><span class="sxs-lookup"><span data-stu-id="702af-150">The disassembler promotes this using the **A4SWIFT_MessageType** property.</span></span>  
  
  <span data-ttu-id="702af-151">拆装器使用**Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema**作为标头架构如果 SWIFT 标头架构和 SWIFT 交换架构配置属性设置为默认情况下"None"。</span><span class="sxs-lookup"><span data-stu-id="702af-151">The disassembler uses **Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema** by default as the header schema if you set both SWIFT Header Schema and SWIFT Interchange Schema configuration properties to "None".</span></span>  
  
## <a name="swift-assembler"></a><span data-ttu-id="702af-152">SWIFT 汇编程序</span><span class="sxs-lookup"><span data-stu-id="702af-152">SWIFT Assembler</span></span>  
 <span data-ttu-id="702af-153">SWIFT 反汇编程序，如 SWIFT 汇编程序具有动态发现出站消息的消息类型和加载相应的架构序列化消息所需的功能。</span><span class="sxs-lookup"><span data-stu-id="702af-153">Like the SWIFT disassembler, the SWIFT assembler has the ability to dynamically discover the message type of an outbound message and load the appropriate schema needed to serialize the message.</span></span> <span data-ttu-id="702af-154">此功能，可配置 SWIFT 汇编程序用于处理任何 SWIFT 消息类型的 SWIFT 消息的单个管道。</span><span class="sxs-lookup"><span data-stu-id="702af-154">This feature enables you to configure a single pipeline using the SWIFT assembler to process SWIFT messages of any SWIFT message type.</span></span> <span data-ttu-id="702af-155">与本机 BizTalk 平面文件组装器，不同 SWIFT 汇编程序不需要可构建 A4SWIFT 可能会遇到的每种消息类型的单独的发送管道。</span><span class="sxs-lookup"><span data-stu-id="702af-155">Unlike the native BizTalk flat-file assembler, the SWIFT assembler does not require you to build a separate send pipeline for each message type that A4SWIFT might encounter.</span></span>  
  
 <span data-ttu-id="702af-156">SWIFT 汇编程序中的动态架构解析是比要简单得 SWIFT 反汇编程序中，因为组装器会恢复到 SWIFT 的平面文件格式序列化 XML 的作业。</span><span class="sxs-lookup"><span data-stu-id="702af-156">Dynamic schema resolution in the SWIFT assembler is much simpler than in the SWIFT disassembler because the assembler does the job of serializing XML back into SWIFT flat-file format.</span></span> <span data-ttu-id="702af-157">XML 的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]给予 SWIFT 汇编程序，序列化包含 SWIFT 汇编程序可以使用直接加载适当架构，以进行序列化的消息类型和架构信息。</span><span class="sxs-lookup"><span data-stu-id="702af-157">The XML that [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] gives to the SWIFT assembler for serialization contains the message type and schema information, which the SWIFT assembler can use directly to load the appropriate schema for serialization.</span></span> <span data-ttu-id="702af-158">在这种情况下，SWIFT 汇编程序不具有任何可配置性对于标头和交换架构： 它始终使用指定的架构将进行序列化的 XML 中。</span><span class="sxs-lookup"><span data-stu-id="702af-158">As such, the SWIFT assembler does not have any configurability for header and interchange schemas: it always uses the schema specified in the XML that it will serialize.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="702af-159">请参阅</span><span class="sxs-lookup"><span data-stu-id="702af-159">See Also</span></span>  
 [<span data-ttu-id="702af-160">使用 SWIFT 反汇编程序和汇编程序</span><span class="sxs-lookup"><span data-stu-id="702af-160">Working with the SWIFT Disassembler and Assembler</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)