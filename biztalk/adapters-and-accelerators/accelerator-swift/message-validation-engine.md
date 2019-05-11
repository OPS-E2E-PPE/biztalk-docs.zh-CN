---
title: 消息验证引擎 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message validation engine
- errors, validating
- XML validation
- parsing validation
- BRE policies, validating
- errors, messages
- messages, errors
- validating, messages
- validating, BRE policies
- validating, XML
- messages, validating
- validating, errors
- validating, parsing
ms.assetid: 4ba0b75e-665b-4771-b04f-5bc3e90d83f0
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd286de8a1f2b0d9947a87cedaafd2a0efbce976
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377198"
---
# <a name="message-validation-engine"></a><span data-ttu-id="e5464-102">消息验证引擎</span><span class="sxs-lookup"><span data-stu-id="e5464-102">Message Validation Engine</span></span>
<span data-ttu-id="e5464-103">提供的最重要功能之一[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]是能够完全验证从后端系统的 SWIFT 网络发往或来自 （由贸易合作伙伴发送） 的 SWIFT 网络接收的 SWIFT 消息。</span><span class="sxs-lookup"><span data-stu-id="e5464-103">One of the most important features provided by [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] is the ability to fully validate SWIFT messages received from back-end systems destined for the SWIFT network, or received from the SWIFT network (sent by trading partners).</span></span> <span data-ttu-id="e5464-104">验证出站 SWIFT 消息可以保证消息符合 SWIFT 标准和 SWIFT 网络将不会拒绝消息。</span><span class="sxs-lookup"><span data-stu-id="e5464-104">Validating outbound SWIFT messages guarantees that the messages conform to SWIFT standards and that the SWIFT network will not reject the messages.</span></span>  
  
 <span data-ttu-id="e5464-105">验证入站 SWIFT 消息可确保从其他金融机构收到的消息遵循特定协议 （业务规则） 特定于此关系。</span><span class="sxs-lookup"><span data-stu-id="e5464-105">Validating inbound SWIFT messages ensures that messages received from other financial institutions obey particular agreements (business rules) specific to the relationship.</span></span> <span data-ttu-id="e5464-106">在这两种情况下，验证和提交一条消息之前捕获的错误的功能可帮助降低事务成本和总拥有成本 (TCO)。</span><span class="sxs-lookup"><span data-stu-id="e5464-106">In both scenarios, the ability to validate and trap errors before committing a message helps to reduce transaction costs and total cost of ownership (TCO).</span></span>  
  
 <span data-ttu-id="e5464-107">以下列表描述了组成 A4SWIFT 验证引擎的四个部分：</span><span class="sxs-lookup"><span data-stu-id="e5464-107">The following list describes the four parts that make up the A4SWIFT validation engine:</span></span>  
  
-   <span data-ttu-id="e5464-108">执行的平面文件分析器的结构验证</span><span class="sxs-lookup"><span data-stu-id="e5464-108">Structural validation performed by the flat file parser</span></span>  
  
-   <span data-ttu-id="e5464-109">执行的验证读取器的 XML 的数据验证</span><span class="sxs-lookup"><span data-stu-id="e5464-109">Data validation performed by the XML validating reader</span></span>  
  
-   <span data-ttu-id="e5464-110">执行由业务规则引擎 (BRE) 的 SWIFT 网络和使用情况的规则验证</span><span class="sxs-lookup"><span data-stu-id="e5464-110">SWIFT network and usage rule validation performed by the Business Rule Engine (BRE)</span></span>  
  
-   <span data-ttu-id="e5464-111">消息标记和收集的"最大程度的"错误</span><span class="sxs-lookup"><span data-stu-id="e5464-111">Message marking and "best effort" error collecting</span></span>  
  
## <a name="structural-validation-parsing"></a><span data-ttu-id="e5464-112">（分析） 的结构验证</span><span class="sxs-lookup"><span data-stu-id="e5464-112">Structural Validation (Parsing)</span></span>  
 <span data-ttu-id="e5464-113">A4SWIFT 分析针对 XSD 架构为 SWIFT 标准根据每个 SWIFT 消息类型定义的 SWIFT 平面文件消息。</span><span class="sxs-lookup"><span data-stu-id="e5464-113">A4SWIFT parses SWIFT flat file messages against XSD schemas defined for each SWIFT message type in accordance with the SWIFT standard.</span></span> <span data-ttu-id="e5464-114">将平面文件解析为 XML 保证平面文件结构正确。</span><span class="sxs-lookup"><span data-stu-id="e5464-114">Parsing a flat file into XML guarantees that the flat file is structurally correct.</span></span> <span data-ttu-id="e5464-115">分析还会生成更轻松地读取、 处理或转换为其他格式或消息类型的 XML。</span><span class="sxs-lookup"><span data-stu-id="e5464-115">Parsing also produces XML that is easier to read, manipulate, or transform into other formats or message types.</span></span> <span data-ttu-id="e5464-116">此外可以根据数据有效性的架构验证 XML，并用于更复杂的计算业务规则引擎 (BRE)。</span><span class="sxs-lookup"><span data-stu-id="e5464-116">You can also validate the XML against schema for data validity and use the Business Rule Engine (BRE) for more complex evaluations.</span></span>  
  
 <span data-ttu-id="e5464-117">SWIFT 反汇编程序调用 BizTalk 平面文件分析器来分析由 SWIFT 反汇编程序调用的 SWIFT 平面文件消息。</span><span class="sxs-lookup"><span data-stu-id="e5464-117">The SWIFT disassembler invokes the BizTalk flat file parser to parse SWIFT flat file messages invoked by the SWIFT disassembler.</span></span> <span data-ttu-id="e5464-118">SWIFT 反汇编程序记录错误集合中的分析过程中，遇到的任何错误的详细信息，并始终会尝试继续进行数据分析在试图收集尽可能上第一次传递的任意数量的结构错误。</span><span class="sxs-lookup"><span data-stu-id="e5464-118">The SWIFT disassembler records in an error collection the details of any errors encountered during parsing, and always attempts to continue parsing the data in an effort to collect as many structural errors as possible on the first pass.</span></span> <span data-ttu-id="e5464-119">但是，大多数分析错误都是致命并停止在第一个错误的消息处理。</span><span class="sxs-lookup"><span data-stu-id="e5464-119">However, most parse errors are fatal and halt message processing at the first error.</span></span>  
  
 <span data-ttu-id="e5464-120">有关结构验证的详细信息，请参阅[处理架构](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="e5464-120">For more information about structural validation, see [Working with Schemas](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md).</span></span>  
  
## <a name="data-validation-xml-validation"></a><span data-ttu-id="e5464-121">数据验证 （XML 验证）</span><span class="sxs-lookup"><span data-stu-id="e5464-121">Data Validation (XML Validation)</span></span>  
 <span data-ttu-id="e5464-122">可以定义传递结构验证为格式正确的 XML 符合定义的 XSD 架构的 SWIFT 消息。</span><span class="sxs-lookup"><span data-stu-id="e5464-122">You can define SWIFT messages that pass structural validation as well-formed XML conforming to defined XSD schemas.</span></span> <span data-ttu-id="e5464-123">A4SWIFT 在解析阶段生成的具有有效结构的 SWIFT 消息的 XML。</span><span class="sxs-lookup"><span data-stu-id="e5464-123">A4SWIFT produces XML for structurally valid SWIFT messages during the parsing stage.</span></span> <span data-ttu-id="e5464-124">然后，A4SWIFT 可以验证数据正确，根据相应的 XSD 架构中定义的约束对此 XML。</span><span class="sxs-lookup"><span data-stu-id="e5464-124">A4SWIFT can then validate this XML for data correctness against constraints defined in the corresponding XSD schema.</span></span>  
  
 <span data-ttu-id="e5464-125">这些约束包括多个数据类型、 长度和标准 SWIFT 按照定义的值范围。</span><span class="sxs-lookup"><span data-stu-id="e5464-125">These constraints include data typing, length, and value ranges defined in accordance with the SWIFT standard.</span></span> <span data-ttu-id="e5464-126">SWIFT 反汇编程序调用验证读取器来执行数据验证的 XML。</span><span class="sxs-lookup"><span data-stu-id="e5464-126">The SWIFT disassembler invokes the XML validating reader to perform data validation.</span></span>  
  
 <span data-ttu-id="e5464-127">SWIFT 反汇编程序记录的错误集合中的 XML 验证过程中遇到任何错误的详细信息，并继续验证要在第一次传递上尽可能收集尽可能多的 XML 验证错误的其余数据。</span><span class="sxs-lookup"><span data-stu-id="e5464-127">The SWIFT disassembler records in an error collection the details of any errors encountered during XML validation, and continues validating the remaining data to collect as many XML validation errors as possible on the first pass.</span></span> <span data-ttu-id="e5464-128">（与不同的分析过程中，延续的 XML 验证的保证。）</span><span class="sxs-lookup"><span data-stu-id="e5464-128">(Unlike parsing, continuation of XML validation is guaranteed.)</span></span>  
  
 <span data-ttu-id="e5464-129">关于数据验证的详细信息，请参阅[处理架构](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="e5464-129">For more information about data validation, see [Working with Schemas](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md).</span></span>  
  
## <a name="swift-network-and-usage-rule-validation-bre-validation"></a><span data-ttu-id="e5464-130">SWIFT 网络和使用情况规则验证 （BRE 验证）</span><span class="sxs-lookup"><span data-stu-id="e5464-130">SWIFT Network and Usage Rule Validation (BRE Validation)</span></span>  
 <span data-ttu-id="e5464-131">A4SWIFT 验证 XML 的有效结构 SWIFT 消息针对业务规则引擎 (BRE) 策略的业务级别正确。</span><span class="sxs-lookup"><span data-stu-id="e5464-131">A4SWIFT validates XML for structurally valid SWIFT messages for business-level correctness against Business Rule Engine (BRE) policies.</span></span> <span data-ttu-id="e5464-132">这些策略包括强制实施 SWIFT 网络和使用情况的规则和其他复杂的跨域规则按照 SWIFT 标准定义。</span><span class="sxs-lookup"><span data-stu-id="e5464-132">These policies include enforcement of SWIFT network and usage rules and other complex cross-field rules defined in accordance with the SWIFT standard.</span></span> <span data-ttu-id="e5464-133">SWIFT 反汇编程序调用 BRE 执行业务级验证。</span><span class="sxs-lookup"><span data-stu-id="e5464-133">The SWIFT disassembler invokes the BRE to perform business-level validation.</span></span>  
  
 <span data-ttu-id="e5464-134">SWIFT 反汇编程序记录的错误集合中的 BRE 验证过程中遇到任何错误的详细信息，并继续验证要在第一次传递上尽可能收集尽可能多的 BRE 验证错误的其余数据。</span><span class="sxs-lookup"><span data-stu-id="e5464-134">The SWIFT disassembler records in an error collection the details of any errors encountered during BRE validation, and continues validating the remaining data to collect as many BRE validation errors as possible on the first pass.</span></span> <span data-ttu-id="e5464-135">（例如 XML 验证、 延续 BRE 验证的保证。）</span><span class="sxs-lookup"><span data-stu-id="e5464-135">(Like XML validation, continuation of BRE validation is guaranteed.)</span></span>  
  
 <span data-ttu-id="e5464-136">SWIFT 网络和使用情况的规则验证的详细信息，请参阅[使用 BRE 策略](../../adapters-and-accelerators/accelerator-swift/working-with-bre-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="e5464-136">For more information about SWIFT network and usage rule validation, see [Working with BRE Policies](../../adapters-and-accelerators/accelerator-swift/working-with-bre-policies.md).</span></span>  
  
## <a name="validation-failures-and-message-marking"></a><span data-ttu-id="e5464-137">验证失败和消息标记</span><span class="sxs-lookup"><span data-stu-id="e5464-137">Validation Failures and Message Marking</span></span>  
 <span data-ttu-id="e5464-138">A4SWIFT 收集验证错误和消息验证的每个阶段的详细信息： 结构分析、 XML 验证和 BRE 验证。</span><span class="sxs-lookup"><span data-stu-id="e5464-138">A4SWIFT collects validation errors and details through each stage of message validation: structural parsing, XML validation, and BRE validation.</span></span> <span data-ttu-id="e5464-139">A4SWIFT 收集使用"最大程度"启发式方法来收集有关消息太多错误的信息尽可能这些错误。</span><span class="sxs-lookup"><span data-stu-id="e5464-139">A4SWIFT collects these errors using a "best effort" heuristic to gather as much error information about a message as possible.</span></span> <span data-ttu-id="e5464-140">此功能允许具有捕获的所有错误和报告在一次传递，而无需多个迭代的提交，验证、 失败、 修复、 重新提交失败消息。</span><span class="sxs-lookup"><span data-stu-id="e5464-140">This functionality allows a failing message to have all errors caught and reported in one pass rather than having multiple iterations of submit, validate, fail, fix, resubmit.</span></span>  
  
 <span data-ttu-id="e5464-141">具有至少一个错误集合中的任何验证阶段过程中遇到的错误消息将被视为无效并失败。</span><span class="sxs-lookup"><span data-stu-id="e5464-141">Messages that have at least one error encountered during any validation stage in the error collection are considered invalid and are failed.</span></span> <span data-ttu-id="e5464-142">A4SWIFT 将这些消息发布到 MessageBox 数据库中，但它们被标记为与升级的属性以指示消息未通过验证并对每个验证阶段报告错误计数。</span><span class="sxs-lookup"><span data-stu-id="e5464-142">A4SWIFT publishes these messages to the MessageBox database, but they are marked with promoted properties to indicate that the message has failed validation and to report error counts for each validation stage.</span></span>  
  
 <span data-ttu-id="e5464-143">升级属性，除了 A4SWIFT 序列化到 XML 错误集合并将附加"错误"的一部分的多部分消息的集合。</span><span class="sxs-lookup"><span data-stu-id="e5464-143">In addition to the promoted properties, A4SWIFT serializes the error collection into XML and attaches the collection as an "error part" of the multipart message.</span></span> <span data-ttu-id="e5464-144">最后一条消息包含的正文部分中的失败消息和错误集合中的错误部分中，XML 和已增强，A4SWIFT 升级属性用来指示故障状态。</span><span class="sxs-lookup"><span data-stu-id="e5464-144">The final message consists of the failed message in the body part and error-collection XML in the error part, and is enhanced with A4SWIFT promoted properties that indicate a failure state.</span></span> <span data-ttu-id="e5464-145">SWIFT 反汇编程序将此多部分消息发布到 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="e5464-145">The SWIFT disassembler publishes this multipart message to the MessageBox database.</span></span>  
  
 <span data-ttu-id="e5464-146">BizTalk 发送端口或业务流程可以检索失败的消息从 MessageBox 数据库通过订阅到特殊的 A4SWIFT 提升属性。</span><span class="sxs-lookup"><span data-stu-id="e5464-146">BizTalk send ports or orchestrations can retrieve failed messages from the MessageBox database by subscribing to the special A4SWIFT promoted properties.</span></span> <span data-ttu-id="e5464-147">您可以进行订阅以检索特定验证阶段中的所有失败的消息或仅使用特定的多个错误消息。</span><span class="sxs-lookup"><span data-stu-id="e5464-147">You can make subscriptions to retrieve all failed messages or only messages with a particular number of errors from specific validation stages.</span></span>  
  
 <span data-ttu-id="e5464-148">检索失败的消息后，可以将其发送到报告应用程序、 修复应用程序或进程或失败的存储库，或放弃它。</span><span class="sxs-lookup"><span data-stu-id="e5464-148">After a failed message is retrieved, you can send it to a reporting application, a repair application or process, or a failure repository, or you can discard it.</span></span>  
  
 <span data-ttu-id="e5464-149">这一功能订阅要失败的消息 （并区分类型的订阅中的故障），再加丰富信息的错误集合上附加到每个失败的消息的 XML 构成一个功能强大的框架，用于开发简单的错误报告提供应用程序，如通过消息修复和新提交功能，由 A4SWIFT 安装程序安装。</span><span class="sxs-lookup"><span data-stu-id="e5464-149">This ability to subscribe to failed messages (and to differentiate between types of failures in the subscription), coupled with information-rich error collection XML attached to each failed message, forms a powerful framework for developing simple error reporting applications, such as provided by the message repair and new submission feature installed by A4SWIFT setup.</span></span>  
  
 <span data-ttu-id="e5464-150">有关验证失败和消息标记的详细信息，请参阅[使用失败消息订阅](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md)。</span><span class="sxs-lookup"><span data-stu-id="e5464-150">For more information about validation failures and message marking, see [Working with Failed Message Subscriptions](../../adapters-and-accelerators/accelerator-swift/working-with-failed-message-subscriptions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5464-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="e5464-151">See Also</span></span>  
 [<span data-ttu-id="e5464-152">BizTalk Accelerator for SWIFT 运行时</span><span class="sxs-lookup"><span data-stu-id="e5464-152">BizTalk Accelerator for SWIFT Runtime</span></span>](../../adapters-and-accelerators/accelerator-swift/biztalk-accelerator-for-swift-runtime.md)