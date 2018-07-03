---
title: 反汇编阶段 （可恢复的交换处理） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 552b1e90-f75d-4713-8c7b-155a52819308
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ca8b90765b2b00803f5b8eb6a22c59ed6b43776
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966110"
---
# <a name="disassembly-stage-recoverable-interchange-processing"></a><span data-ttu-id="0ed93-102">拆装阶段（可恢复交换处理）</span><span class="sxs-lookup"><span data-stu-id="0ed93-102">Disassembly Stage (Recoverable Interchange Processing)</span></span>
<span data-ttu-id="0ed93-103">在这两种模式中的拆装阶段处理交换：</span><span class="sxs-lookup"><span data-stu-id="0ed93-103">Interchanges are processed at the disassembly stage in two modes:</span></span>  
  
-   <span data-ttu-id="0ed93-104">**标准模式。**</span><span class="sxs-lookup"><span data-stu-id="0ed93-104">**Standard mode.**</span></span> <span data-ttu-id="0ed93-105">如果接收管道的拆装器组件配置为执行标准拆装，交换中包含的消息将被提取、由接收管道处理、映射并发布为工作的事务单元。</span><span class="sxs-lookup"><span data-stu-id="0ed93-105">When the disassembler component of a receive pipeline is configured to perform standard disassembly, the messages contained in an interchange are extracted, processed by the receive pipeline, mapped, and published as a transactional unit of work.</span></span> <span data-ttu-id="0ed93-106">也就是说，整个交换和其包含的消息被完全处理并发布到 MessageBox 数据库中，或者交换被放置在挂起队列中。</span><span class="sxs-lookup"><span data-stu-id="0ed93-106">That is, either the entire interchange and its contained messages are fully processed and published into the MessageBox database, or the interchange is placed in the Suspended queue.</span></span>  
  
-   <span data-ttu-id="0ed93-107">**可恢复模式。**</span><span class="sxs-lookup"><span data-stu-id="0ed93-107">**Recoverable mode.**</span></span> <span data-ttu-id="0ed93-108">当接收管道的拆装器组件配置为执行**可恢复交换处理**，互相独立地提取交换中包含的消息。</span><span class="sxs-lookup"><span data-stu-id="0ed93-108">When the disassembler component of a receive pipeline is configured to perform **recoverable interchange processing**, the messages contained in an interchange are extracted independently of each other.</span></span> <span data-ttu-id="0ed93-109">成功提取的消息随后将向下传播到接收管道。</span><span class="sxs-lookup"><span data-stu-id="0ed93-109">Messages that are successfully extracted are propagated further down the receive pipeline.</span></span> <span data-ttu-id="0ed93-110">在交换内找出、但未能成功提取的消息将放置在挂起队列中。</span><span class="sxs-lookup"><span data-stu-id="0ed93-110">Messages that are identified within an interchange but are not successfully extracted are placed in the Suspended queue.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="0ed93-111">示例</span><span class="sxs-lookup"><span data-stu-id="0ed93-111">Examples</span></span>  
 <span data-ttu-id="0ed93-112">以下示例说明了几个交换处理方案：</span><span class="sxs-lookup"><span data-stu-id="0ed93-112">The following examples illustrate interchange processing scenarios.</span></span>  
  
### <a name="example-1"></a><span data-ttu-id="0ed93-113">示例 1</span><span class="sxs-lookup"><span data-stu-id="0ed93-113">Example 1</span></span>  
 <span data-ttu-id="0ed93-114">在此示例中，在标准交换接收位置上提交以下伪交换。</span><span class="sxs-lookup"><span data-stu-id="0ed93-114">In this example, the following pseudo-interchange is submitted on a standard interchange receive location.</span></span> <span data-ttu-id="0ed93-115">即接收管道中的拆装器组件配置用于标准交换处理。</span><span class="sxs-lookup"><span data-stu-id="0ed93-115">That is, the disassembler component in the receive pipeline is configured for standard interchange processing.</span></span>  
  
```  
<Interchange>  
<Document1>...</Document1>  
<Document2 failure=”routing”>...</Document2>  
<Document3>...</Document3>  
<Document4 failure=”pipeline” recoverableError=”true”>...</Document4>  
<Document5>...</Document5>  
</Interchange>  
```  
  
 <span data-ttu-id="0ed93-116">此交换包含五个消息，全都是拆装器从交换成功提取的消息。</span><span class="sxs-lookup"><span data-stu-id="0ed93-116">This interchange contains five messages, all of which the disassembler successfully extracts from the interchange.</span></span> <span data-ttu-id="0ed93-117">按如下方式处理这些消息：</span><span class="sxs-lookup"><span data-stu-id="0ed93-117">They are processed as follows:</span></span>  
  
- <span data-ttu-id="0ed93-118">第一个、第二个和第三个消息通过管道进行传播，并且可发布。</span><span class="sxs-lookup"><span data-stu-id="0ed93-118">The first, second, and third messages propagate through the pipeline and are ready to be published.</span></span>  
  
- <span data-ttu-id="0ed93-119">第四个消息在管道的拆装阶段处理失败。</span><span class="sxs-lookup"><span data-stu-id="0ed93-119">The fourth message fails processing at the disassembling stage in the pipeline.</span></span> <span data-ttu-id="0ed93-120">这将导致已处理的所有消息回滚，原始交换消息作为可恢复的消息挂起。</span><span class="sxs-lookup"><span data-stu-id="0ed93-120">This causes all the messages that have already been processed to roll back and the original interchange message to be suspended as resumable.</span></span>  
  
  <span data-ttu-id="0ed93-121">提交的结果为：</span><span class="sxs-lookup"><span data-stu-id="0ed93-121">The result of submission is:</span></span>  
  
- <span data-ttu-id="0ed93-122">不发布任何内容。</span><span class="sxs-lookup"><span data-stu-id="0ed93-122">Nothing is published.</span></span> <span data-ttu-id="0ed93-123">原始交换被挂起，因为在标准交换处理中，在交换处理期间或之后的任何时刻失败的任何提取消息都将导致所有提取的消息被放弃，并且原始交换作为可恢复的交换放置在挂起队列中。</span><span class="sxs-lookup"><span data-stu-id="0ed93-123">The original interchange is suspended because in standard interchange processing, any extracted message that fails at any point during or after interchange processing results in all extracted messages being discarded and the original interchange being placed on the Suspended queue as resumable.</span></span>  
  
### <a name="example-2"></a><span data-ttu-id="0ed93-124">示例 2</span><span class="sxs-lookup"><span data-stu-id="0ed93-124">Example 2</span></span>  
 <span data-ttu-id="0ed93-125">该示例使用与上例相同的交换处理和传播方案，除了拆装阶段配置为执行可恢复交换处理。</span><span class="sxs-lookup"><span data-stu-id="0ed93-125">The example uses the same interchange processing and propagation scenario as the previous example, except that the disassembly stage is configured to do recoverable interchange processing.</span></span>  
  
 <span data-ttu-id="0ed93-126">提交的结果为：单个提取的消息都被处理，原始交换被放弃。</span><span class="sxs-lookup"><span data-stu-id="0ed93-126">The result of submission is that individual extracted messages are all processed and the original interchange is discarded.</span></span> <span data-ttu-id="0ed93-127">按如下所示处理各个消息：</span><span class="sxs-lookup"><span data-stu-id="0ed93-127">The individual messages are processed as follows:</span></span>  
  
-   <span data-ttu-id="0ed93-128">第一个、第二个和第三个消息通过管道进行传播，并且可发布。</span><span class="sxs-lookup"><span data-stu-id="0ed93-128">The first, second, and third messages propagate through the pipeline and are ready to be published.</span></span>  
  
-   <span data-ttu-id="0ed93-129">第四个消息拆装处理失败（即提取该消息后出错），并且可挂起。</span><span class="sxs-lookup"><span data-stu-id="0ed93-129">The fourth message fails disassembly processing (that is, something goes wrong after it is extracted) and is ready to be suspended.</span></span>  
  
-   <span data-ttu-id="0ed93-130">第五个消息通过管道进行传播，并且可发布。</span><span class="sxs-lookup"><span data-stu-id="0ed93-130">The fifth message propagates through the pipeline and is ready to be published.</span></span>  
  
-   <span data-ttu-id="0ed93-131">在从交换中提取了所有消息后，消息 1、2、3 和 5 将发布到 MessageBox 数据库中，消息 4 将放置在挂起队列。</span><span class="sxs-lookup"><span data-stu-id="0ed93-131">After all messages are extracted from the interchange, messages 1, 2, 3, and 5 are published into the MessageBox database, and message 4 is placed on the Suspended queue.</span></span> <span data-ttu-id="0ed93-132">消息 2 也将重定向到挂起队列，因为路由由于没有匹配的订户而失败。</span><span class="sxs-lookup"><span data-stu-id="0ed93-132">Message 2 is also redirected to the Suspended queue because of a routing failure due to no matching subscriber.</span></span>  
  
## <a name="configuring-recoverable-interchange-processing"></a><span data-ttu-id="0ed93-133">配置可恢复的交换处理</span><span class="sxs-lookup"><span data-stu-id="0ed93-133">Configuring Recoverable Interchange Processing</span></span>  
 <span data-ttu-id="0ed93-134">可恢复的交换处理是接收管道的拆装器组件的一个属性。</span><span class="sxs-lookup"><span data-stu-id="0ed93-134">Recoverable interchange processing is a property of the disassembler component of a receive pipeline.</span></span> <span data-ttu-id="0ed93-135">并非所有的拆装器组件都允许您指定可恢复的交换处理；例如，本地 BizTalk 框架拆装器就不允许。</span><span class="sxs-lookup"><span data-stu-id="0ed93-135">Not all disassembler components allow you to specify recoverable interchange processing; for example, the native BizTalk Framework disassembler does not.</span></span> <span data-ttu-id="0ed93-136">如果某一拆装器支持可恢复交换处理，则在管道设计器中指定此行为[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]到所设计的管道的拆装阶段添加拆装器组件时。</span><span class="sxs-lookup"><span data-stu-id="0ed93-136">If a disassembler supports recoverable interchange processing, then you specify this behavior in Pipeline Designer within [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] when you add the disassembler component to the Disassemble stage of the pipeline being designed.</span></span> <span data-ttu-id="0ed93-137">所选拆装器拖到管道的拆装阶段之后，设置可恢复交换处理属性为该拆装器组件的`true`。</span><span class="sxs-lookup"><span data-stu-id="0ed93-137">After you drag the selected disassembler onto the Disassemble stage of the pipeline, you set the recoverable interchange processing property of that disassembler component to `true`.</span></span>  
  
### <a name="party-resolution"></a><span data-ttu-id="0ed93-138">参与方解析</span><span class="sxs-lookup"><span data-stu-id="0ed93-138">Party Resolution</span></span>  
 <span data-ttu-id="0ed93-139">在可恢复的交换处理中成功提取的消息将根据为相应父交换到达的接收端口配置的参与方来标识其发送方。</span><span class="sxs-lookup"><span data-stu-id="0ed93-139">Messages that are successfully extracted in recoverable interchange processing have their sending party identified according to the party configured for the receive port on which the parent interchange arrived.</span></span> <span data-ttu-id="0ed93-140">如果参与方解析对于从给定交换提取的任何消息失败，则认为参与方解析对于整个交换失败。</span><span class="sxs-lookup"><span data-stu-id="0ed93-140">If party resolution fails for any message extracted from a given interchange, then party resolution is considered to have failed for the entire interchange.</span></span>  
  
### <a name="restrictions"></a><span data-ttu-id="0ed93-141">限制</span><span class="sxs-lookup"><span data-stu-id="0ed93-141">Restrictions</span></span>  
  
-   <span data-ttu-id="0ed93-142">当某个交换在拆装器中失败时，该交换将作为可恢复交换被挂起。</span><span class="sxs-lookup"><span data-stu-id="0ed93-142">When an interchange fails in the disassembler, the interchange is suspended as resumable.</span></span> <span data-ttu-id="0ed93-143">但是，如果管理性地恢复该交换，它将再次失败，因为导致拆装失败的这些类型的错误只是交换内容的结果，其在恢复交换时将保持相同。</span><span class="sxs-lookup"><span data-stu-id="0ed93-143">However, if the interchange is administratively resumed, it will fail again because the kinds of errors that cause disassembly failure are solely a result of the interchange content, which stays the same when the interchange is resumed.</span></span> <span data-ttu-id="0ed93-144">必须修改此类失败的交换，并通过接收位置重新提交相应交换。</span><span class="sxs-lookup"><span data-stu-id="0ed93-144">Such a failed interchange must be modified and resubmitted through a receive location.</span></span>  
  
-   <span data-ttu-id="0ed93-145">如果从交换成功提取的消息随后由于不匹配的订户无法通过消息传送传播，则该将消息作为可恢复消息挂起。</span><span class="sxs-lookup"><span data-stu-id="0ed93-145">If a message that was successfully extracted from an interchange subsequently fails to propagate through messaging due to an unmatched subscriber, the message is suspended as resumable.</span></span> <span data-ttu-id="0ed93-146">如果解决了导致路由失败的问题，则可以管理性地恢复此消息。</span><span class="sxs-lookup"><span data-stu-id="0ed93-146">This message can be administratively resumed if the cause of the routing failure is fixed.</span></span>  
  
-   <span data-ttu-id="0ed93-147">即使拆装器组件中出现以下错误，拆装器组件也将继续从交换中提取消息：</span><span class="sxs-lookup"><span data-stu-id="0ed93-147">The disassembler component continues to extract messages from an interchange despite the following errors in disassembler components:</span></span>  
  
    -   <span data-ttu-id="0ed93-148">找不到架构</span><span class="sxs-lookup"><span data-stu-id="0ed93-148">Schema not found</span></span>  
  
    -   <span data-ttu-id="0ed93-149">未解决架构不明确问题（即，对于同一消息类型存在多个架构）</span><span class="sxs-lookup"><span data-stu-id="0ed93-149">Schema ambiguity not resolved (that is, more than one schema exists for the same message type)</span></span>  
  
    -   <span data-ttu-id="0ed93-150">XML 验证失败</span><span class="sxs-lookup"><span data-stu-id="0ed93-150">XML validation failed</span></span>  
  
    -   <span data-ttu-id="0ed93-151">平面文件解析失败</span><span class="sxs-lookup"><span data-stu-id="0ed93-151">Flat-file parsing failed</span></span>  
  
-   <span data-ttu-id="0ed93-152">拆装器组件实现**不**继续从交换中提取消息，如果拆装器组件中出现以下错误：</span><span class="sxs-lookup"><span data-stu-id="0ed93-152">The disassembler component does **not** continue to extract messages from an interchange if the following error occurs in disassembler components:</span></span>  
  
    -   <span data-ttu-id="0ed93-153">文档数据不是格式正确的 XML—将导致 System.Xml.XmlReader 失败的任何文档属性</span><span class="sxs-lookup"><span data-stu-id="0ed93-153">Document data is not well-formed XML—any document properties that would cause System.Xml.XmlReader to fail</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ed93-154">请参阅</span><span class="sxs-lookup"><span data-stu-id="0ed93-154">See Also</span></span>  
 <span data-ttu-id="0ed93-155">[如何配置 XML 拆装器管道组件](../core/how-to-configure-the-xml-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="0ed93-155">[How to Configure the XML Disassembler Pipeline Component](../core/how-to-configure-the-xml-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="0ed93-156">如何配置平面文件拆装器管道组件</span><span class="sxs-lookup"><span data-stu-id="0ed93-156">How to Configure the Flat File Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)