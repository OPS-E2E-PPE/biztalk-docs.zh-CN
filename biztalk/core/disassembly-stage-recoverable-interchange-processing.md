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
ms.openlocfilehash: 81be8a4ca330c1ef48bbbb67a2de1b1c9d049f33
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530863"
---
# <a name="disassembly-stage-recoverable-interchange-processing"></a><span data-ttu-id="467d7-102">反汇编阶段 （可恢复的交换处理）</span><span class="sxs-lookup"><span data-stu-id="467d7-102">Disassembly Stage (Recoverable Interchange Processing)</span></span>
<span data-ttu-id="467d7-103">在这两种模式中的拆装阶段处理交换：</span><span class="sxs-lookup"><span data-stu-id="467d7-103">Interchanges are processed at the disassembly stage in two modes:</span></span>  
  
-   <span data-ttu-id="467d7-104">**标准模式。**</span><span class="sxs-lookup"><span data-stu-id="467d7-104">**Standard mode.**</span></span> <span data-ttu-id="467d7-105">当接收管道的拆装器组件配置为执行标准拆装时，交换中包含的消息是提取、 由接收管道处理、 映射，并发布为事务性工作单元。</span><span class="sxs-lookup"><span data-stu-id="467d7-105">When the disassembler component of a receive pipeline is configured to perform standard disassembly, the messages contained in an interchange are extracted, processed by the receive pipeline, mapped, and published as a transactional unit of work.</span></span> <span data-ttu-id="467d7-106">也就是说，整个交换和其包含的消息完全处理并发布到 MessageBox 数据库，或者交换被放置在挂起队列中。</span><span class="sxs-lookup"><span data-stu-id="467d7-106">That is, either the entire interchange and its contained messages are fully processed and published into the MessageBox database, or the interchange is placed in the Suspended queue.</span></span>  
  
-   <span data-ttu-id="467d7-107">**可恢复模式。**</span><span class="sxs-lookup"><span data-stu-id="467d7-107">**Recoverable mode.**</span></span> <span data-ttu-id="467d7-108">当接收管道的拆装器组件配置为执行**可恢复交换处理**，互相独立地提取交换中包含的消息。</span><span class="sxs-lookup"><span data-stu-id="467d7-108">When the disassembler component of a receive pipeline is configured to perform **recoverable interchange processing**, the messages contained in an interchange are extracted independently of each other.</span></span> <span data-ttu-id="467d7-109">已成功提取的消息传播进一步沿接收管道。</span><span class="sxs-lookup"><span data-stu-id="467d7-109">Messages that are successfully extracted are propagated further down the receive pipeline.</span></span> <span data-ttu-id="467d7-110">交换中标识，但未能成功提取的消息将放置在挂起队列中。</span><span class="sxs-lookup"><span data-stu-id="467d7-110">Messages that are identified within an interchange but are not successfully extracted are placed in the Suspended queue.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="467d7-111">示例</span><span class="sxs-lookup"><span data-stu-id="467d7-111">Examples</span></span>  
 <span data-ttu-id="467d7-112">以下示例说明了交换处理方案。</span><span class="sxs-lookup"><span data-stu-id="467d7-112">The following examples illustrate interchange processing scenarios.</span></span>  
  
### <a name="example-1"></a><span data-ttu-id="467d7-113">示例 1</span><span class="sxs-lookup"><span data-stu-id="467d7-113">Example 1</span></span>  
 <span data-ttu-id="467d7-114">在此示例中，将标准提交以下伪交换的交换接收位置。</span><span class="sxs-lookup"><span data-stu-id="467d7-114">In this example, the following pseudo-interchange is submitted on a standard interchange receive location.</span></span> <span data-ttu-id="467d7-115">也就是说，在接收管道的拆装器组件配置为标准交换处理。</span><span class="sxs-lookup"><span data-stu-id="467d7-115">That is, the disassembler component in the receive pipeline is configured for standard interchange processing.</span></span>  
  
```  
<Interchange>  
<Document1>...</Document1>  
<Document2 failure=”routing”>...</Document2>  
<Document3>...</Document3>  
<Document4 failure=”pipeline” recoverableError=”true”>...</Document4>  
<Document5>...</Document5>  
</Interchange>  
```  
  
 <span data-ttu-id="467d7-116">此交换包含五个消息时，所有这些拆装器已成功从提取交换。</span><span class="sxs-lookup"><span data-stu-id="467d7-116">This interchange contains five messages, all of which the disassembler successfully extracts from the interchange.</span></span> <span data-ttu-id="467d7-117">它们进行处理，如下所示：</span><span class="sxs-lookup"><span data-stu-id="467d7-117">They are processed as follows:</span></span>  
  
- <span data-ttu-id="467d7-118">第一，第二和第三个消息通过管道进行传播并准备好发布。</span><span class="sxs-lookup"><span data-stu-id="467d7-118">The first, second, and third messages propagate through the pipeline and are ready to be published.</span></span>  
  
- <span data-ttu-id="467d7-119">第四个消息处理管道的拆装阶段失败。</span><span class="sxs-lookup"><span data-stu-id="467d7-119">The fourth message fails processing at the disassembling stage in the pipeline.</span></span> <span data-ttu-id="467d7-120">这将导致已得到处理要回滚的所有消息和要作为可恢复挂起的原始交换消息。</span><span class="sxs-lookup"><span data-stu-id="467d7-120">This causes all the messages that have already been processed to roll back and the original interchange message to be suspended as resumable.</span></span>  
  
  <span data-ttu-id="467d7-121">提交的结果是：</span><span class="sxs-lookup"><span data-stu-id="467d7-121">The result of submission is:</span></span>  
  
- <span data-ttu-id="467d7-122">不发布任何内容。</span><span class="sxs-lookup"><span data-stu-id="467d7-122">Nothing is published.</span></span> <span data-ttu-id="467d7-123">原始交换被挂起，因为在标准交换处理的交换处理期间或之后在任何时刻失败的任何提取的消息会导致所有提取的消息被放弃和原始交换被放置在作为可恢复已挂起队列。</span><span class="sxs-lookup"><span data-stu-id="467d7-123">The original interchange is suspended because in standard interchange processing, any extracted message that fails at any point during or after interchange processing results in all extracted messages being discarded and the original interchange being placed on the Suspended queue as resumable.</span></span>  
  
### <a name="example-2"></a><span data-ttu-id="467d7-124">示例 2</span><span class="sxs-lookup"><span data-stu-id="467d7-124">Example 2</span></span>  
 <span data-ttu-id="467d7-125">该示例与上面的示例中，使用相同的交换处理和传播方案，只不过拆装阶段配置为执行可恢复交换处理。</span><span class="sxs-lookup"><span data-stu-id="467d7-125">The example uses the same interchange processing and propagation scenario as the previous example, except that the disassembly stage is configured to do recoverable interchange processing.</span></span>  
  
 <span data-ttu-id="467d7-126">提交的结果是所有处理单个提取的消息，原始交换被放弃。</span><span class="sxs-lookup"><span data-stu-id="467d7-126">The result of submission is that individual extracted messages are all processed and the original interchange is discarded.</span></span> <span data-ttu-id="467d7-127">按如下所示处理各个消息：</span><span class="sxs-lookup"><span data-stu-id="467d7-127">The individual messages are processed as follows:</span></span>  
  
-   <span data-ttu-id="467d7-128">第一，第二和第三个消息通过管道进行传播并准备好发布。</span><span class="sxs-lookup"><span data-stu-id="467d7-128">The first, second, and third messages propagate through the pipeline and are ready to be published.</span></span>  
  
-   <span data-ttu-id="467d7-129">第四个消息拆装处理失败 （即后出现问题则将提取） 并已准备好将挂起。</span><span class="sxs-lookup"><span data-stu-id="467d7-129">The fourth message fails disassembly processing (that is, something goes wrong after it is extracted) and is ready to be suspended.</span></span>  
  
-   <span data-ttu-id="467d7-130">第五个消息通过管道进行传播，并已准备好发布。</span><span class="sxs-lookup"><span data-stu-id="467d7-130">The fifth message propagates through the pipeline and is ready to be published.</span></span>  
  
-   <span data-ttu-id="467d7-131">从交换中提取所有消息后，消息 1、 2、 3 和 5 将发布到 MessageBox 数据库中，并且消息 4 将放置在挂起队列。</span><span class="sxs-lookup"><span data-stu-id="467d7-131">After all messages are extracted from the interchange, messages 1, 2, 3, and 5 are published into the MessageBox database, and message 4 is placed on the Suspended queue.</span></span> <span data-ttu-id="467d7-132">消息 2 也将重定向到挂起队列由于路由失败的原因是没有匹配的订户。</span><span class="sxs-lookup"><span data-stu-id="467d7-132">Message 2 is also redirected to the Suspended queue because of a routing failure due to no matching subscriber.</span></span>  
  
## <a name="configuring-recoverable-interchange-processing"></a><span data-ttu-id="467d7-133">配置可恢复交换处理</span><span class="sxs-lookup"><span data-stu-id="467d7-133">Configuring Recoverable Interchange Processing</span></span>  
 <span data-ttu-id="467d7-134">可恢复交换处理是接收管道的拆装器组件的属性。</span><span class="sxs-lookup"><span data-stu-id="467d7-134">Recoverable interchange processing is a property of the disassembler component of a receive pipeline.</span></span> <span data-ttu-id="467d7-135">并非所有的拆装器组件允许您指定可恢复交换处理;例如，本机 BizTalk 框架拆装器不。</span><span class="sxs-lookup"><span data-stu-id="467d7-135">Not all disassembler components allow you to specify recoverable interchange processing; for example, the native BizTalk Framework disassembler does not.</span></span> <span data-ttu-id="467d7-136">如果某一拆装器支持可恢复交换处理，则在管道设计器中指定此行为[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]到所设计的管道的拆装阶段添加拆装器组件时。</span><span class="sxs-lookup"><span data-stu-id="467d7-136">If a disassembler supports recoverable interchange processing, then you specify this behavior in Pipeline Designer within [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] when you add the disassembler component to the Disassemble stage of the pipeline being designed.</span></span> <span data-ttu-id="467d7-137">所选拆装器拖到管道的拆装阶段之后，设置可恢复交换处理属性为该拆装器组件的`true`。</span><span class="sxs-lookup"><span data-stu-id="467d7-137">After you drag the selected disassembler onto the Disassemble stage of the pipeline, you set the recoverable interchange processing property of that disassembler component to `true`.</span></span>  
  
### <a name="party-resolution"></a><span data-ttu-id="467d7-138">参与方解析</span><span class="sxs-lookup"><span data-stu-id="467d7-138">Party Resolution</span></span>  
 <span data-ttu-id="467d7-139">可恢复交换处理中成功提取的消息具有为相应父交换到达的接收端口配置的参与方根据标识其发送方。</span><span class="sxs-lookup"><span data-stu-id="467d7-139">Messages that are successfully extracted in recoverable interchange processing have their sending party identified according to the party configured for the receive port on which the parent interchange arrived.</span></span> <span data-ttu-id="467d7-140">如果从给定交换提取的任何消息的参与方解析失败，则认为参与方解析对于整个交换失败。</span><span class="sxs-lookup"><span data-stu-id="467d7-140">If party resolution fails for any message extracted from a given interchange, then party resolution is considered to have failed for the entire interchange.</span></span>  
  
### <a name="restrictions"></a><span data-ttu-id="467d7-141">限制</span><span class="sxs-lookup"><span data-stu-id="467d7-141">Restrictions</span></span>  
  
-   <span data-ttu-id="467d7-142">当交换在拆装器失败时，将挂起交换作为可恢复。</span><span class="sxs-lookup"><span data-stu-id="467d7-142">When an interchange fails in the disassembler, the interchange is suspended as resumable.</span></span> <span data-ttu-id="467d7-143">但是，如果管理性地恢复该交换，它将无法再次因为导致拆装失败的错误的类型是完全保持不变时恢复该交换的交换内容的结果。</span><span class="sxs-lookup"><span data-stu-id="467d7-143">However, if the interchange is administratively resumed, it will fail again because the kinds of errors that cause disassembly failure are solely a result of the interchange content, which stays the same when the interchange is resumed.</span></span> <span data-ttu-id="467d7-144">此类失败的交换必须修改并重新提交通过接收位置。</span><span class="sxs-lookup"><span data-stu-id="467d7-144">Such a failed interchange must be modified and resubmitted through a receive location.</span></span>  
  
-   <span data-ttu-id="467d7-145">如果已成功提取来自交换随后的消息无法通过不匹配的订户由于消息传送传播，作为可恢复挂起消息。</span><span class="sxs-lookup"><span data-stu-id="467d7-145">If a message that was successfully extracted from an interchange subsequently fails to propagate through messaging due to an unmatched subscriber, the message is suspended as resumable.</span></span> <span data-ttu-id="467d7-146">如果路由失败的原因固定，可管理性地恢复此消息。</span><span class="sxs-lookup"><span data-stu-id="467d7-146">This message can be administratively resumed if the cause of the routing failure is fixed.</span></span>  
  
-   <span data-ttu-id="467d7-147">拆装器组件将继续从交换拆装器组件中显示以下错误尽管中提取消息：</span><span class="sxs-lookup"><span data-stu-id="467d7-147">The disassembler component continues to extract messages from an interchange despite the following errors in disassembler components:</span></span>  
  
    -   <span data-ttu-id="467d7-148">找不到架构</span><span class="sxs-lookup"><span data-stu-id="467d7-148">Schema not found</span></span>  
  
    -   <span data-ttu-id="467d7-149">未解析的架构不明确问题 （即，多个架构相同的消息类型存在）</span><span class="sxs-lookup"><span data-stu-id="467d7-149">Schema ambiguity not resolved (that is, more than one schema exists for the same message type)</span></span>  
  
    -   <span data-ttu-id="467d7-150">XML 验证失败</span><span class="sxs-lookup"><span data-stu-id="467d7-150">XML validation failed</span></span>  
  
    -   <span data-ttu-id="467d7-151">平面文件解析失败</span><span class="sxs-lookup"><span data-stu-id="467d7-151">Flat-file parsing failed</span></span>  
  
-   <span data-ttu-id="467d7-152">拆装器组件实现**不**继续从交换中提取消息，如果拆装器组件中出现以下错误：</span><span class="sxs-lookup"><span data-stu-id="467d7-152">The disassembler component does **not** continue to extract messages from an interchange if the following error occurs in disassembler components:</span></span>  
  
    -   <span data-ttu-id="467d7-153">文档数据不是格式正确 XML — 将导致 System.Xml.XmlReader 失败的任何文档属性</span><span class="sxs-lookup"><span data-stu-id="467d7-153">Document data is not well-formed XML—any document properties that would cause System.Xml.XmlReader to fail</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="467d7-154">请参阅</span><span class="sxs-lookup"><span data-stu-id="467d7-154">See Also</span></span>  
 <span data-ttu-id="467d7-155">[如何配置 XML 拆装器管道组件](../core/how-to-configure-the-xml-disassembler-pipeline-component.md) </span><span class="sxs-lookup"><span data-stu-id="467d7-155">[How to Configure the XML Disassembler Pipeline Component](../core/how-to-configure-the-xml-disassembler-pipeline-component.md) </span></span>  
 [<span data-ttu-id="467d7-156">如何配置平面文件拆装器管道组件</span><span class="sxs-lookup"><span data-stu-id="467d7-156">How to Configure the Flat File Disassembler Pipeline Component</span></span>](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)