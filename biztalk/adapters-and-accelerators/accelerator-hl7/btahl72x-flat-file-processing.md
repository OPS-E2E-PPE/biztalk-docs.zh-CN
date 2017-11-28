---
title: "BTAHL72X 平面文件处理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ACKs
- 2.X messages, disassembler
- property promotion, MSH-header schemas
- disassembler, validating messages
- HL7, errors
- 2.X messages, validating headers
- acknowledgements, generating
- assembler, validating messages
- messages, multi-part messages
- property promotion, property schemas
- generating aknowledgements
- messages, 2.X messages
- schemas, MSH-header schemas
- 2.X messages, validating message bodies
- 2.X messages
- schemas, property schemas
- message modes, 2.X messages
- errors, HL7 error format
- flat files
- validating, messages
- schemas, property promotion
- headers, validating
- 2.X messages, message modes
- 2.X messages, header validation
- 2.X messages, parsing flat files
ms.assetid: c92e2f70-0bfa-4bc8-8044-4a6e62cabee3
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b15d21653b9f0d6109487677484506c7a5d6bcc2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="btahl72x-flat-file-processing"></a><span data-ttu-id="556f1-102">BTAHL72X 平面文件处理</span><span class="sxs-lookup"><span data-stu-id="556f1-102">BTAHL72X Flat File Processing</span></span>
<span data-ttu-id="556f1-103">中的以下组件[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 处理 HL7 2.X （HL7 编码） 消息：</span><span class="sxs-lookup"><span data-stu-id="556f1-103">The following components in [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) process HL7 2.X (HL7-encoded) messages:</span></span>  
  
-   <span data-ttu-id="556f1-104">管道和核心库： [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]。PipelineCommon.dll 和[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]。PipelineMessageCore.dll</span><span class="sxs-lookup"><span data-stu-id="556f1-104">Pipelines and core libraries: [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].PipelineCommon.dll and [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].PipelineMessageCore.dll</span></span>  
  
-   <span data-ttu-id="556f1-105">汇编程序和反汇编程序库： [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]。HL72fAsm.dll 和[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]。HL72fDAsm.dll</span><span class="sxs-lookup"><span data-stu-id="556f1-105">Assembler and disassembler libraries: [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].HL72fAsm.dll and [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].HL72fDAsm.dll</span></span>  
  
-   <span data-ttu-id="556f1-106">用于双向 MLLP 确认 (ACK) 验证库发送适配器： [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]。HL7ACKHelper.dll</span><span class="sxs-lookup"><span data-stu-id="556f1-106">The acknowledgment (ACK) validation library used for the two-way MLLP send adapter: [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].HL7ACKHelper.dll</span></span>  
  
## <a name="hl7-message-modes"></a><span data-ttu-id="556f1-107">HL7 消息模式</span><span class="sxs-lookup"><span data-stu-id="556f1-107">HL7 Message Modes</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="556f1-108">支持以下的消息模式的 2.X 消息：</span><span class="sxs-lookup"><span data-stu-id="556f1-108"> supports the following message modes for 2.X messages:</span></span>  
  
-   <span data-ttu-id="556f1-109">发布服务器订阅服务器 （发布-订阅） 模式</span><span class="sxs-lookup"><span data-stu-id="556f1-109">Publisher-subscriber (pub-sub) mode</span></span>  
  
     <span data-ttu-id="556f1-110">为订阅服务器，为声明性或一个未经请求方广播发布服务器更新。</span><span class="sxs-lookup"><span data-stu-id="556f1-110">The publisher broadcasts to a party of subscribers, either as declarative or an unsolicited update.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="556f1-111">和[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]提供灵活地此模式下，因为你可以在设计时后管理订阅和方。</span><span class="sxs-lookup"><span data-stu-id="556f1-111"> and [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] provide flexibility to this mode, since you can manage subscriptions and parties after design time.</span></span>  
  
-   <span data-ttu-id="556f1-112">请求-响应模式</span><span class="sxs-lookup"><span data-stu-id="556f1-112">Request-response mode</span></span>  
  
     <span data-ttu-id="556f1-113">来自特定实体的特定请求导致响应消息 interrogative 或查询消息交换。</span><span class="sxs-lookup"><span data-stu-id="556f1-113">An interrogative or query message exchange in which a specific request from a specific entity results in a responding message.</span></span>  
  
## <a name="flat-file-parsing"></a><span data-ttu-id="556f1-114">分析的平面文件</span><span class="sxs-lookup"><span data-stu-id="556f1-114">Flat File Parsing</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="556f1-115">分析 HL7 2.X 多个部分的消息数分为三个部分：</span><span class="sxs-lookup"><span data-stu-id="556f1-115"> parses HL7 2.X multi-part messages into three parts:</span></span>  
  
-   <span data-ttu-id="556f1-116">标头 MSH 一部分</span><span class="sxs-lookup"><span data-stu-id="556f1-116">Header-MSH part</span></span>  
  
-   <span data-ttu-id="556f1-117">正文部分</span><span class="sxs-lookup"><span data-stu-id="556f1-117">Body part</span></span>  
  
-   <span data-ttu-id="556f1-118">Z 一部分</span><span class="sxs-lookup"><span data-stu-id="556f1-118">Z part</span></span>  
  
## <a name="hl7-header-validation"></a><span data-ttu-id="556f1-119">HL7 标头验证</span><span class="sxs-lookup"><span data-stu-id="556f1-119">HL7 Header Validation</span></span>  
 <span data-ttu-id="556f1-120">HL7 反汇编程序和汇编程序执行 2.X 消息，以验证它可以处理该消息的标头的结构化和示意图验证。</span><span class="sxs-lookup"><span data-stu-id="556f1-120">The HL7 disassembler and assembler perform structural and schematic validation of the header of a 2.X message, in order to verify that it can process the message.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="556f1-121">窗体的常见标头架构 MSH_25_GLO_DEF 的示意图验证。</span><span class="sxs-lookup"><span data-stu-id="556f1-121"> bases the schematic validation on the common header schema, MSH_25_GLO_DEF.</span></span>  
  
 <span data-ttu-id="556f1-122">例如，该分析器会认为 MSH1 和 MSH2 字段的格式正确。</span><span class="sxs-lookup"><span data-stu-id="556f1-122">For instance, the parser determines that the MSH1 and MSH2 fields are well formed.</span></span> <span data-ttu-id="556f1-123">MSH1 必须只有一个字符。</span><span class="sxs-lookup"><span data-stu-id="556f1-123">MSH1 must have only one character.</span></span> <span data-ttu-id="556f1-124">MSH2 必须介于两个和第四个字符之间，并且没有的字符可以重复。</span><span class="sxs-lookup"><span data-stu-id="556f1-124">MSH2 must be between two and four characters, and no characters can repeat.</span></span>  
  
## <a name="hl7-body-validation"></a><span data-ttu-id="556f1-125">HL7 正文验证</span><span class="sxs-lookup"><span data-stu-id="556f1-125">HL7 Body Validation</span></span>  
 <span data-ttu-id="556f1-126">HL7 反汇编程序和汇编程序执行 2.X 消息正文的基本结构验证和示意图验证，如果你启用它。</span><span class="sxs-lookup"><span data-stu-id="556f1-126">The HL7 disassembler and assembler perform basic structural validation of the body of a 2.X message, and schematic validation, if you enable it.</span></span>  
  
 <span data-ttu-id="556f1-127">正文的基本结构验证其[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]始终执行，包括验证以下：</span><span class="sxs-lookup"><span data-stu-id="556f1-127">The basic structural validation of the body, which [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] always performs, includes verifying the following:</span></span>  
  
-   <span data-ttu-id="556f1-128">段中有三个字符</span><span class="sxs-lookup"><span data-stu-id="556f1-128">That there are three characters in segments</span></span>  
  
-   <span data-ttu-id="556f1-129">段分隔符是\<CR > 或\<CR >\<LF > （可选择的最后一段）</span><span class="sxs-lookup"><span data-stu-id="556f1-129">That the segment delimiter is \<CR> or \<CR>\<LF> (optional for the last segment)</span></span>  
  
-   <span data-ttu-id="556f1-130">字段分隔符是适当</span><span class="sxs-lookup"><span data-stu-id="556f1-130">That field delimiters are appropriate</span></span>  
  
-   <span data-ttu-id="556f1-131">未声明的 Z 段中有任何声明的段 （与定义的三个字符段标记）</span><span class="sxs-lookup"><span data-stu-id="556f1-131">That there are no declared segments (with a defined three-character segment tag) in an undeclared Z segment</span></span>  
  
 <span data-ttu-id="556f1-132">正文的更广泛的架构验证过程包括以下：</span><span class="sxs-lookup"><span data-stu-id="556f1-132">More extensive schema validation of the body includes the following:</span></span>  
  
-   <span data-ttu-id="556f1-133">尾随字段分隔符</span><span class="sxs-lookup"><span data-stu-id="556f1-133">Trailing-field delimiters</span></span>  
  
     <span data-ttu-id="556f1-134">标头 MSH 段和正文段中</span><span class="sxs-lookup"><span data-stu-id="556f1-134">In Header-MSH segment and body segments</span></span>  
  
-   <span data-ttu-id="556f1-135">Z 段</span><span class="sxs-lookup"><span data-stu-id="556f1-135">Z segment</span></span>  
  
-   <span data-ttu-id="556f1-136">XSD 支持和自定义数据类型</span><span class="sxs-lookup"><span data-stu-id="556f1-136">XSD-supported and custom data type</span></span>  
  
     <span data-ttu-id="556f1-137">支持的 XSD 和非 XSD 类型 （TS （时间戳）、 DT （日期）、 TM （时间） 和 TN （电话号码）</span><span class="sxs-lookup"><span data-stu-id="556f1-137">XSD supported and non-XSD types (TS (Time Stamp), DT (date), TM (time), and TN (telephone number)</span></span>  
  
-   <span data-ttu-id="556f1-138">枚举</span><span class="sxs-lookup"><span data-stu-id="556f1-138">Enumerations</span></span>  
  
     <span data-ttu-id="556f1-139">ID （HL7 定义表） 和 IS （用户定义表）</span><span class="sxs-lookup"><span data-stu-id="556f1-139">ID (HL7-defined tables) and IS (user-defined tables)</span></span>  
  
-   <span data-ttu-id="556f1-140">Optionality</span><span class="sxs-lookup"><span data-stu-id="556f1-140">Optionality</span></span>  
  
     <span data-ttu-id="556f1-141">必选和可选</span><span class="sxs-lookup"><span data-stu-id="556f1-141">Required and optional</span></span>  
  
-   <span data-ttu-id="556f1-142">重复</span><span class="sxs-lookup"><span data-stu-id="556f1-142">Repetition</span></span>  
  
     <span data-ttu-id="556f1-143">段和字段</span><span class="sxs-lookup"><span data-stu-id="556f1-143">Segment and field</span></span>  
  
-   <span data-ttu-id="556f1-144">转义序列</span><span class="sxs-lookup"><span data-stu-id="556f1-144">Escape sequences</span></span>  
  
     <span data-ttu-id="556f1-145">字符进行编码、 格式和字符集</span><span class="sxs-lookup"><span data-stu-id="556f1-145">Encoding characters, formatting, and character sets</span></span>  
  
 <span data-ttu-id="556f1-146">启用或禁用的所有消息从接收或发送到特定方 （源方反汇编程序、 目标为汇编程序的参与方） 的示意图验证。</span><span class="sxs-lookup"><span data-stu-id="556f1-146">You enable or disable schematic validation for all messages received from or sent to a specific party (source party for the disassembler, destination party for the assembler).</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="556f1-147">直接对此处理，根据 MSH9.3 消息结构标头字段、 MSH12 版本 ID 字段 （2.3.1、 2.4 或 2.5） 和命名空间设置的使用 HL7 2.X 架构[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。</span><span class="sxs-lookup"><span data-stu-id="556f1-147"> uses the HL7 2.X schemas directly for this processing, as determined by the MSH9.3 message-structure header field, the MSH12 Version ID field (2.3.1, 2.4, or 2.5), and the namespace setting in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer.</span></span>  
  
## <a name="hl7-disassembler-processing"></a><span data-ttu-id="556f1-148">HL7 反汇编程序处理</span><span class="sxs-lookup"><span data-stu-id="556f1-148">HL7 Disassembler Processing</span></span>  
 <span data-ttu-id="556f1-149">HL7 反汇编程序分析到 XML 段，用来处理传入的 HL7 消息。</span><span class="sxs-lookup"><span data-stu-id="556f1-149">The HL7 disassembler parses incoming HL7 messages into XML segments for processing.</span></span> <span data-ttu-id="556f1-150">它会分析消息，拆装器执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="556f1-150">As it parses the messages, the disassembler performs the following tasks:</span></span>  
  
-   <span data-ttu-id="556f1-151">句柄转义序列</span><span class="sxs-lookup"><span data-stu-id="556f1-151">Handles escape sequences</span></span>  
  
-   <span data-ttu-id="556f1-152">处理检查必需/可选属性</span><span class="sxs-lookup"><span data-stu-id="556f1-152">Handles checks of the required/optional properties</span></span>  
  
-   <span data-ttu-id="556f1-153">句柄定义线段而未定义或意外 Z 线段 (Z 段的说明，请参阅[Z 对象通过自定义消息](../../adapters-and-accelerators/accelerator-hl7/customizing-messages-through-z-objects.md))。</span><span class="sxs-lookup"><span data-stu-id="556f1-153">Handles defined segments and undefined or unexpected Z segments (for a description of Z segments, see [Customizing Messages through Z Objects](../../adapters-and-accelerators/accelerator-hl7/customizing-messages-through-z-objects.md)).</span></span>  
  
-   <span data-ttu-id="556f1-154">将忽略意外的段数实例的末尾 （变得未声明的 Z 段）</span><span class="sxs-lookup"><span data-stu-id="556f1-154">Ignores unexpected segments at the end of an instance (which become undeclared Z segments)</span></span>  
  
## <a name="error-reporting"></a><span data-ttu-id="556f1-155">错误报告</span><span class="sxs-lookup"><span data-stu-id="556f1-155">Error Reporting</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="556f1-156">报告标准 HL7 错误格式，其中包括段、 序列、 字段和错误代码的大多数错误。</span><span class="sxs-lookup"><span data-stu-id="556f1-156"> reports most errors in standard HL7 error format, which include the segment, sequence, field, and error code.</span></span> <span data-ttu-id="556f1-157">但是，错误条件中的可能是这样的： 不是所有这些都可用，例如，如果没有架构，则存在。</span><span class="sxs-lookup"><span data-stu-id="556f1-157">However, the error condition may be such that not all of these are available, for instance, if no schema is present.</span></span> <span data-ttu-id="556f1-158">若要处理这种情况下，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]可以报告中备用的错误[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]错误格式。</span><span class="sxs-lookup"><span data-stu-id="556f1-158">To handle such cases, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] can report errors in an alternate [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] error format.</span></span> <span data-ttu-id="556f1-159">在消息中的错误段包括两个部分： 一个用于 HL7 错误，一个可选[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]错误。</span><span class="sxs-lookup"><span data-stu-id="556f1-159">The error segment in a message includes two parts: one for the HL7 error and one for the alternative [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] error.</span></span>  
  
## <a name="ack-generation"></a><span data-ttu-id="556f1-160">ACK 生成</span><span class="sxs-lookup"><span data-stu-id="556f1-160">ACK Generation</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="556f1-161">2.X 消息支持以下类型的确认 (Ack)。</span><span class="sxs-lookup"><span data-stu-id="556f1-161"> supports the following types of acknowledgments (ACKs) for 2.X messages.</span></span> <span data-ttu-id="556f1-162">HL7 错误类型和[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]使用 （备用） 错误类型：</span><span class="sxs-lookup"><span data-stu-id="556f1-162">Both the HL7 error type and the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] (alternate) error type are used:</span></span>  
  
-   <span data-ttu-id="556f1-163">将原始消息和 ACK 映射</span><span class="sxs-lookup"><span data-stu-id="556f1-163">Mapping original message and ACK</span></span>  
  
-   <span data-ttu-id="556f1-164">HL7 原始确认</span><span class="sxs-lookup"><span data-stu-id="556f1-164">HL7 original ACKs</span></span>  
  
-   <span data-ttu-id="556f1-165">HL7 增强确认</span><span class="sxs-lookup"><span data-stu-id="556f1-165">HL7 enhanced ACKs</span></span>  
  
     <span data-ttu-id="556f1-166">提交接受和应用程序接受</span><span class="sxs-lookup"><span data-stu-id="556f1-166">Commit Accept and Application Accept</span></span>  
  
-   <span data-ttu-id="556f1-167">静态/代理 ACK</span><span class="sxs-lookup"><span data-stu-id="556f1-167">Static/proxy ACK</span></span>  
  
     <span data-ttu-id="556f1-168">ACK 或否认</span><span class="sxs-lookup"><span data-stu-id="556f1-168">ACK or NAK</span></span>  
  
## <a name="property-promotion"></a><span data-ttu-id="556f1-169">属性提升</span><span class="sxs-lookup"><span data-stu-id="556f1-169">Property Promotion</span></span>  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="556f1-170">升级以下 2.X 属性的支持：</span><span class="sxs-lookup"><span data-stu-id="556f1-170"> supports promoting the following 2.X properties:</span></span>  
  
-   <span data-ttu-id="556f1-171">属性架构</span><span class="sxs-lookup"><span data-stu-id="556f1-171">Property schema</span></span>  
  
-   <span data-ttu-id="556f1-172">MSH 标头架构</span><span class="sxs-lookup"><span data-stu-id="556f1-172">MSH-header schema</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="556f1-173">本节内容</span><span class="sxs-lookup"><span data-stu-id="556f1-173">In This Section</span></span>  
  
-   [<span data-ttu-id="556f1-174">HL7 2.X 反汇编程序中的架构确定</span><span class="sxs-lookup"><span data-stu-id="556f1-174">Schema Determination in the HL7 2.X Disassembler</span></span>](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-disassembler.md)  
  
-   [<span data-ttu-id="556f1-175">架构确定在 HL7 2.X 汇编程序</span><span class="sxs-lookup"><span data-stu-id="556f1-175">Schema Determination in the HL7 2.X Assembler</span></span>](../../adapters-and-accelerators/accelerator-hl7/schema-determination-in-the-hl7-2-x-assembler.md)  
  
## <a name="see-also"></a><span data-ttu-id="556f1-176">另请参阅</span><span class="sxs-lookup"><span data-stu-id="556f1-176">See Also</span></span>  
 <span data-ttu-id="556f1-177">[消息处理](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="556f1-177">[Message Processing](../../adapters-and-accelerators/accelerator-hl7/message-processing.md) </span></span>  
 <span data-ttu-id="556f1-178">[处理 HL7 消息](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span><span class="sxs-lookup"><span data-stu-id="556f1-178">[Processing HL7 Messages](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md) </span></span>  
 [<span data-ttu-id="556f1-179">使用 HL7 2.X 架构</span><span class="sxs-lookup"><span data-stu-id="556f1-179">Using HL7 2.X Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)