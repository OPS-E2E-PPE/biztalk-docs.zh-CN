---
title: EDI 批处理的已知问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 510ac82b-8a02-4135-87b7-0a5f288f5317
caps.latest.revision: 38
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c33be4da2db28fb38c3f81d3d1aaa5316a0a16a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997166"
---
# <a name="known-issues-with-edi-batching"></a><span data-ttu-id="58828-102">EDI 批处理的已知问题</span><span class="sxs-lookup"><span data-stu-id="58828-102">Known Issues with EDI Batching</span></span>
<span data-ttu-id="58828-103">本主题介绍了 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中批处理的已知问题。</span><span class="sxs-lookup"><span data-stu-id="58828-103">This topic describes known issues with batching in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="subdocument-splitting-was-not-performed-even-though-the-subdocument-annotation-was-set-to-yes"></a><span data-ttu-id="58828-104">即使子文档批注设置为“是”，也不会执行子文档拆分</span><span class="sxs-lookup"><span data-stu-id="58828-104">Subdocument Splitting Was Not Performed Even Though the Subdocument Annotation Was Set to Yes</span></span>  
 <span data-ttu-id="58828-105">**症状**</span><span class="sxs-lookup"><span data-stu-id="58828-105">**Symptom**</span></span>  
  
 <span data-ttu-id="58828-106">即使该交换的 HIPAA 架构中的 subdocument_creation_break 批注设置为"是"。 不 HIPAA 交换拆分为子文档</span><span class="sxs-lookup"><span data-stu-id="58828-106">A HIPAA interchange was not split into subdocuments even though the subdocument_creation_break annotation within the HIPAA schema for that interchange was set to "Yes."</span></span>  
  
 <span data-ttu-id="58828-107">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="58828-107">**Possible Cause**</span></span>  
  
- <span data-ttu-id="58828-108">入站的批处理选项发送参与方设置为"保留交换"。</span><span class="sxs-lookup"><span data-stu-id="58828-108">The Inbound batch processing option for the sending party was set to "Preserve Interchange."</span></span> <span data-ttu-id="58828-109">在这种情况下，即使已将 HIPAA 架构中的 subdocument_creation_break 批注设置为“是”，HIPAA 文档也不会拆分为子文档。</span><span class="sxs-lookup"><span data-stu-id="58828-109">A HIPAA document will not be split into subdocuments if this is the case, even though the subdocument_creation_break annotation within the HIPAA schema is set to "Yes."</span></span>  
  
- <span data-ttu-id="58828-110">Subdocument_break 批注设置为"是"，但 subdocument_creation_break 批注未设置为"是"。</span><span class="sxs-lookup"><span data-stu-id="58828-110">The subdocument_break annotation was set to “Yes”, but the subdocument_creation_break annotation was not set to “Yes”.</span></span>  
  
  <span data-ttu-id="58828-111">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="58828-111">**Resolution**</span></span>  
  
- <span data-ttu-id="58828-112">在中**验证和确认生成设置**页**EDI 属性**发送参与方的对话框中设置**入站批处理**选项属性任一**交换拆分为事务集-出错时挂起事务集**或**交换拆分为事务集-出错时挂起交换**。</span><span class="sxs-lookup"><span data-stu-id="58828-112">In the **Validation and ACK Generation Settings** page of the **EDI Properties** dialog box for the sending party, set the **Inbound batch processing** option property to either **Split Interchange as Transaction Sets – suspend Transaction Sets on Error** or **Split Interchange as Transaction Sets – suspend Interchange on Error**.</span></span>  
  
- <span data-ttu-id="58828-113">HIPAA 文档将不会拆分为子文档除非的 subdocument_creation_break 批注设置为"是"。</span><span class="sxs-lookup"><span data-stu-id="58828-113">A HIPAA document will not be split into subdocuments unless the subdocument_creation_break annotation is set to “Yes.”</span></span>  
  
## <a name="validation-of-a-batch-may-fail-if-batch-configuration-settings-are-changed-while-the-batch-orchestration-is-activated"></a><span data-ttu-id="58828-114">如果在批处理业务流程处于激活状态时更改批配置设置，批处理验证可能会失败</span><span class="sxs-lookup"><span data-stu-id="58828-114">Validation of a Batch May Fail if Batch Configuration Settings Are Changed While the Batch Orchestration Is Activated</span></span>  
 <span data-ttu-id="58828-115">如果在批处理业务流程处理批的过程中更改批的配置设置，则新配置设置不会应用于该批。</span><span class="sxs-lookup"><span data-stu-id="58828-115">If you change batch configuration settings while the batching orchestration is processing a batch, the new configuration settings will not be picked up for that batch.</span></span> <span data-ttu-id="58828-116">这会导致发送管道中产生验证错误。</span><span class="sxs-lookup"><span data-stu-id="58828-116">This can result in validation errors in the send pipeline.</span></span>  
  
 <span data-ttu-id="58828-117">这些设置位于“EDI 属性”对话框的“批处理”页。</span><span class="sxs-lookup"><span data-stu-id="58828-117">These settings are in the Batches page of the EDI Properties dialog box.</span></span>  
  
 <span data-ttu-id="58828-118">要解决此问题，请重新启动与批处理业务流程关联的主机实例。</span><span class="sxs-lookup"><span data-stu-id="58828-118">To resolve this issue, restart the host instance(s) associated with the batching orchestration(s).</span></span> <span data-ttu-id="58828-119">这会导致立即应用批配置设置。</span><span class="sxs-lookup"><span data-stu-id="58828-119">This will cause the change to the batch configuration settings to take place immediately.</span></span>  
  
## <a name="the-batchcontrolmessagerecvloc-receive-location-can-only-run-on-a-32-bit-computer-or-in-wow-on-a-64-bit-computer"></a><span data-ttu-id="58828-120">BatchControlMessageRecvLoc 接收位置只能在 32 位计算机或带有 WOW 环境的 64 位计算机上运行</span><span class="sxs-lookup"><span data-stu-id="58828-120">The BatchControlMessageRecvLoc Receive Location Can Only Run on a 32-Bit Computer or in WOW on a 64-Bit Computer</span></span>  
 <span data-ttu-id="58828-121">SQL 适配器只能在 32 位计算机上运行，或者在 64 位计算机上的 WOW64 仿真程序下运行。</span><span class="sxs-lookup"><span data-stu-id="58828-121">SQL adapters only work on 32-bit computers or when running under the WOW64 emulator on 64-bit computers.</span></span> <span data-ttu-id="58828-122">因此，安装程序安装的使用 SQL 适配器的 BatchControlMessageRecvLoc 接收位置将只能在 32 位计算机上运行，或者在 64 位计算机上的 WOW64 仿真程序下运行。</span><span class="sxs-lookup"><span data-stu-id="58828-122">As a result, the BatchControlMessageRecvLoc receive location, which is installed by the setup program and uses the SQL adapter, will only work on a 32-bit computer or when running under WOW on a 64-bit computer.</span></span> <span data-ttu-id="58828-123">此接收位置是批处理所必需的。</span><span class="sxs-lookup"><span data-stu-id="58828-123">This receive location is required for batch processing.</span></span>  
  
 <span data-ttu-id="58828-124">如果在 64 位计算机上的 WOW 下运行 BatchControlMessageRecvLoc 接收位置，则应在其他主机中运行批处理业务流程。</span><span class="sxs-lookup"><span data-stu-id="58828-124">When running the BatchControlMessageRecvLoc receive location under WOW on a 64-bit computer, you should run the batching orchestrations in a different host.</span></span> <span data-ttu-id="58828-125">如果运行批处理业务流程的主机与运行接收位置的主机相同，则该批处理业务流程也将在 WOW 下运行，这样您将失去在 64 位计算机上运行所具有的优势。</span><span class="sxs-lookup"><span data-stu-id="58828-125">If they are run on the same host as the receive location, the batching orchestrations would also run under WOW, and you would lose the advantages of running on a 64-bit computer.</span></span>  
  
## <a name="a-batch-can-be-picked-up-by-an-unintended-send-port"></a><span data-ttu-id="58828-126">意外发送端口可以提取批处理</span><span class="sxs-lookup"><span data-stu-id="58828-126">A Batch Can Be Picked Up By an Unintended Send Port</span></span>  
 <span data-ttu-id="58828-127">时批处理业务流程发布交换，它将升级两个属性： ToBeBatched = False 和 DestinationPartyName = \< *PartyName*\>。</span><span class="sxs-lookup"><span data-stu-id="58828-127">When the batching orchestration publishes an interchange, it promotes two properties: ToBeBatched = False and DestinationPartyName = \<*PartyName*\>.</span></span> <span data-ttu-id="58828-128">订阅以上任意一个或两个属性的发送端口都可以提取这些批处理交换。</span><span class="sxs-lookup"><span data-stu-id="58828-128">A send port subscribing to either or both of these properties can pick up these batched interchanges.</span></span> <span data-ttu-id="58828-129">请确保配置发送端口的筛选器，使该发送端口仅提取应提取的批处理交换。</span><span class="sxs-lookup"><span data-stu-id="58828-129">Make sure that a send port's filters are configured such that the send port picks up those batched interchanges that it is intended to pick up.</span></span>  
  
## <a name="a-batch-element-count-greater-than-the-required-number-of-transaction-sets-for-a-batch-may-not-prompt-batch-release"></a><span data-ttu-id="58828-130">批元素计数大于批处理所需的事务集数目时可能不会提示批处理的发布</span><span class="sxs-lookup"><span data-stu-id="58828-130">A Batch Element Count Greater Than the Required Number of Transaction Sets for a Batch May Not Prompt Batch Release</span></span>  
 <span data-ttu-id="58828-131">如果批处理的发布条件基于每组或每个交换的事务集数目，即使批元素计数大于发布批处理所需的事务集数目，也可能不会发布此批处理。</span><span class="sxs-lookup"><span data-stu-id="58828-131">If the batch release criteria is based upon the number of transaction sets per group or interchange, a batch may not be released even though the batch element count is greater than the number of transaction sets required for a batch to be released.</span></span> <span data-ttu-id="58828-132">当启用确认并将批处理筛选条件设置为向批处理添加此确认时，则可能出现此问题。</span><span class="sxs-lookup"><span data-stu-id="58828-132">This can happen if you enable acknowledgments, and set the batch filter criteria to add those acknowledgments to the batch.</span></span> <span data-ttu-id="58828-133">在这种情况下，组（或交换）中的批元素数目将大于每组（或交换）的事务集数目。</span><span class="sxs-lookup"><span data-stu-id="58828-133">In this instance, the number of batch elements in the group (or interchange) will be greater than the number of transaction sets per group (or interchange).</span></span> <span data-ttu-id="58828-134">在上述情况中，如果每组（或每个交换）的事务集数目小于发布批处理所需的数目，则不会发布批处理；但同时，批元素数目可能大于发布批处理所需的事务集数目。</span><span class="sxs-lookup"><span data-stu-id="58828-134">In that instance, a batch will not be released if the number of transaction sets per group (or interchange) is smaller than the number required for batch release, but at the same time the number of batch elements could be greater than the number of transaction sets required for batch release.</span></span>  
  
## <a name="no-batch-elements-were-saved-when-start-was-clicked"></a><span data-ttu-id="58828-135">单击“开始”后未保存任何批元素</span><span class="sxs-lookup"><span data-stu-id="58828-135">No Batch Elements Were Saved When Start Was Clicked</span></span>  
 <span data-ttu-id="58828-136">**症状**</span><span class="sxs-lookup"><span data-stu-id="58828-136">**Symptom**</span></span>  
  
 <span data-ttu-id="58828-137">当**启动**单击了在参与方批处理页中，已收集任何消息批处理。</span><span class="sxs-lookup"><span data-stu-id="58828-137">When **Start** was clicked in the Batches page for a party, no messages were collected for the batch.</span></span>  
  
 <span data-ttu-id="58828-138">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="58828-138">**Possible Cause**</span></span>  
  
 <span data-ttu-id="58828-139">从该处的日期时间**启动**被单击时间早于输入中的日期时间**激活**部分。</span><span class="sxs-lookup"><span data-stu-id="58828-139">The datetime at which **Start** was clicked was earlier than the datetime entered in the **Activation** section.</span></span> <span data-ttu-id="58828-140">因此，业务流程实例已激活，但为批处理收集任何消息。</span><span class="sxs-lookup"><span data-stu-id="58828-140">As a result, the orchestration instance was activated, but no messages were collected for the batch.</span></span> <span data-ttu-id="58828-141">有关详细信息，请参阅[配置传出批](../core/configuring-an-outgoing-batch.md)。</span><span class="sxs-lookup"><span data-stu-id="58828-141">For more information, see [Configuring an Outgoing Batch](../core/configuring-an-outgoing-batch.md).</span></span>  
  
 <span data-ttu-id="58828-142">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="58828-142">**Resolution**</span></span>  
  
 <span data-ttu-id="58828-143">单击**停止**中遇到此问题的批处理配置批处理页。</span><span class="sxs-lookup"><span data-stu-id="58828-143">Click **Stop** in the Batches page for the batch configuration experiencing this problem.</span></span> <span data-ttu-id="58828-144">设置**激活**至任一**立即启动**或早于当前时间中，输入日期时间，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="58828-144">Set the **Activation** to either **Start immediately** or enter a datetime earlier than the current time, and then click **Start**.</span></span> <span data-ttu-id="58828-145">当提示重置**启动**日期时间为当前时间中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="58828-145">When you are prompted to reset the **Start** datetime to the current time, click **OK**.</span></span> <span data-ttu-id="58828-146">此时 BizTalk Server 将开始为批处理收集消息。</span><span class="sxs-lookup"><span data-stu-id="58828-146">BizTalk Server will start to collect messages for a batch at that point.</span></span>  
  
## <a name="the-number-of-bytes-in-an-edifact-batch-may-depend-upon-the-character-set-used"></a><span data-ttu-id="58828-147">EDIFACT 批处理中的字节数可能取决于使用的字符集</span><span class="sxs-lookup"><span data-stu-id="58828-147">The Number of Bytes in an EDIFACT Batch May Depend Upon the Character Set Used</span></span>  
 <span data-ttu-id="58828-148">一些字符在某些 EDIFACT 字符集中可能是双字节字符，而在其他 EDIFACT 字符集中则可能是单字节字符。</span><span class="sxs-lookup"><span data-stu-id="58828-148">Characters in some EDIFACT character sets may be double-byte characters, whereas in other EDIFACT character sets they may be single-byte characters.</span></span> <span data-ttu-id="58828-149">鉴于以上原因，在您根据交换中的字符数设置批的发布条件时，相应交换中的字节数可能会因使用的字符集而不同。</span><span class="sxs-lookup"><span data-stu-id="58828-149">Because of this, when you set the release criteria for batches based upon the number of characters in the interchange, the number of bytes in the interchange may differ depending on the character set used.</span></span>  
  
## <a name="the-characters--and--must-be-represented-in-their-encoded-form-in-the-envelope-of-a-batch"></a><span data-ttu-id="58828-150">在批处理的信封中，必须以编码形式表示字符“<”和“&”</span><span class="sxs-lookup"><span data-stu-id="58828-150">The Characters "<" and "&" Must be Represented in Their Encoded Form in the Envelope of a Batch</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="58828-151"> 不支持以下字符以其文本的形式创建一个批处理 EDI 交换的信封字段时:"<"和"&"。</span><span class="sxs-lookup"><span data-stu-id="58828-151"> does not support the following characters in their literal form when creating the envelope fields of a batched EDI interchange: "<" and "&".</span></span>  
  
 <span data-ttu-id="58828-152">如果在传出批处理交换的信封字段中按原义使用上述任一字符，当 EdiSend 管道用于序列化交换时可能会导致消息挂起。</span><span class="sxs-lookup"><span data-stu-id="58828-152">Using either of these characters literally in the envelope fields of an outgoing batched interchange will result in a suspended message if the EdiSend pipeline is used to serialize the interchange.</span></span>  
  
 <span data-ttu-id="58828-153">如果需要在批处理的信封字段中使用上述字符之一，以 BizTalk 管理员身份配置信封字段时，您可以使用下表中已编码的相应值：</span><span class="sxs-lookup"><span data-stu-id="58828-153">If you need to use one of these characters in an envelope field of a batch, you can use the appropriate encoded value in the following table when you configure the envelope field in the BizTalk Administrator:</span></span>  
  
|<span data-ttu-id="58828-154">字符</span><span class="sxs-lookup"><span data-stu-id="58828-154">Character</span></span>|<span data-ttu-id="58828-155">编码</span><span class="sxs-lookup"><span data-stu-id="58828-155">Encoding</span></span>|  
|---------------|--------------|  
|<|&lt;|  
|&|&amp;|  
  
 <span data-ttu-id="58828-156">如果使用上述编码格式之一，当 BizTalk Server 验证字段是否满足在 BizTalk Server 管理控制台的合作伙伴协议管理器 (PAM) 屏幕中的长度限制时，以该编码格式表示的每个字符都将计为一个单独字符。</span><span class="sxs-lookup"><span data-stu-id="58828-156">When you use one of these encoded forms, each character in the encoded form will be counted as an individual character when BizTalk Server validates the field for its length restriction in the Partner Agreement Manager (PAM) screens in the BizTalk Server Administration console.</span></span> <span data-ttu-id="58828-157">例如，即使编码"&lt;"只表示单个字符"\<"在批处理 EDI 交换，BizTalk Server 会将此字符计为四个字符根据特定字段的长度限制进行验证时.</span><span class="sxs-lookup"><span data-stu-id="58828-157">For example, even though the encoding "&lt;" would represent a single character "\<" in the batched EDI interchange, BizTalk Server would count this as four characters when validating against the length restriction of the particular field.</span></span> <span data-ttu-id="58828-158">此问题仅适用于 PAM，而不适用于 EDI 组装器。</span><span class="sxs-lookup"><span data-stu-id="58828-158">This is an issue for PAM only, not for the EDI Assembler.</span></span>  
  
## <a name="an-exeption-occurs-during-the-execution-of-the-upgrade-batch-orchestration"></a><span data-ttu-id="58828-159">执行升级批处理业务流程期间出现异常</span><span class="sxs-lookup"><span data-stu-id="58828-159">An Exeption Occurs During the Execution of the Upgrade Batch Orchestration</span></span>  
 <span data-ttu-id="58828-160">**症状**</span><span class="sxs-lookup"><span data-stu-id="58828-160">**Symptom**</span></span>  
  
 <span data-ttu-id="58828-161">当使用在传入文档中设置 EDI.DestinationPartyId 属性的自定义管道组件时，您可能会接收到应用程序事件日志中的错误，指出执行升级批处理业务流程期间发生了异常。</span><span class="sxs-lookup"><span data-stu-id="58828-161">When using a custom pipeline component that sets the EDI.DestinationPartyId property on incoming documents, you may receive an error in the Application event log stating that an exception has occurred during the execution of the upgrade batch orchestration.</span></span>  
  
 <span data-ttu-id="58828-162">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="58828-162">**Possible Cause**</span></span>  
  
 <span data-ttu-id="58828-163">如果错误消息 ="找不到批"，此错误表明升级批处理业务流程无法即可成功辨别传入文档的批。</span><span class="sxs-lookup"><span data-stu-id="58828-163">If ErrorMessage = “The batch was not found”, this error indicates that the upgrade batch orchestration was not able to successfully identify a batch for the incoming document.</span></span>  
  
 <span data-ttu-id="58828-164">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="58828-164">**Resolution**</span></span>  
  
 <span data-ttu-id="58828-165">升级批处理业务流程使用 EDI.DestinationPartyId 来查找参与方名称。</span><span class="sxs-lookup"><span data-stu-id="58828-165">The upgrade batch orchestration uses the EDI.DestinationPartyId to look up the party name.</span></span> <span data-ttu-id="58828-166">该业务流程将构造一个使用参与方名称，EDI 的字符串。EncodingType 和字符串"Default"，然后查找具有匹配的批名称的批处理配置。</span><span class="sxs-lookup"><span data-stu-id="58828-166">The orchestration then constructs a string using the party name, EDI.EncodingType and the string “Default”, and then looks for a batch configuration with a matching batch name.</span></span> <span data-ttu-id="58828-167">如果任何批配置不存在具有此名称，应用程序事件日志记录此错误并挂起业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="58828-167">If no batch configuration exists with this name, this error is logged to the Application event log and the orchestration instance is suspended.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="58828-168">例如，如果参与方名称为 Contoso 和 EDI。EncodingType 是 X12，业务流程将查找名为 ContosoX12Default 的批处理。</span><span class="sxs-lookup"><span data-stu-id="58828-168">For example, if the party name is Contoso and the EDI.EncodingType is X12, the orchestration will look for a batch named ‘ContosoX12Default’.</span></span>  
  
 <span data-ttu-id="58828-169">若要解决此问题，请确保批处理存在与将升级批处理业务流程通过构造的字符串匹配的名称。</span><span class="sxs-lookup"><span data-stu-id="58828-169">To resolve this problem, ensure that a batch exists with a name that will match the string constructed by the upgrade batch orchestration.</span></span>  
  
## <a name="messages-marked-with-editobebatched--true-and-edidestinationparties-are-suspended"></a><span data-ttu-id="58828-170">标记为 EDI 消息。ToBeBatched = True，并且 EDI。DestinationParties 将被挂起</span><span class="sxs-lookup"><span data-stu-id="58828-170">Messages Marked with EDI.ToBeBatched = True and EDI.DestinationParties are Suspended</span></span>  
 <span data-ttu-id="58828-171">**现象**</span><span class="sxs-lookup"><span data-stu-id="58828-171">**Symptoms**</span></span>  
  
 <span data-ttu-id="58828-172">当使用自定义管道组件来标记通过设置 EDI 批处理的消息。ToBeBatched = True，并且 EDI。DestinationParties 到一系列方 Id，该消息将挂起的指出没有任何订户路由故障。</span><span class="sxs-lookup"><span data-stu-id="58828-172">When using a custom pipeline component to mark messages for batching by setting EDI.ToBeBatched = True and EDI.DestinationParties to a list of party IDs, the message will be suspended with a routing failure stating that there are no subscribers.</span></span>  
  
 <span data-ttu-id="58828-173">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="58828-173">**Possible Cause**</span></span>  
  
 <span data-ttu-id="58828-174">在以前版本的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]时应处理一条消息，则会将 EDI 设置的多个批处理配置。DestinationParties 属性设置为一个空格分隔参与方 Id 的列表。</span><span class="sxs-lookup"><span data-stu-id="58828-174">In previous versions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], when a message should be processed by multiple batch configurations you would set the EDI.DestinationParties property to a space delimited list of party IDs.</span></span> <span data-ttu-id="58828-175">路由业务流程订阅具有 EDI.ToBeBatched = True 和 EDI.DestinationParties 属性的消息，会使用包含在 EDI.DestinationParties 属性中的参与方 ID 列表为每个 ID 创建消息，然后将消息传递到批处理业务流程。</span><span class="sxs-lookup"><span data-stu-id="58828-175">The routing orchestration is subscribed to messages with the EDI.ToBeBatched = True and EDI.DestinationParties properties, and would use the list of party IDs contained in the EDI.DestinationParties property to create a message for each ID, and pass the messages to the batching orchestration.</span></span>  <span data-ttu-id="58828-176">确定使用参与方的批 ID 使用，因为每个参与方配置可能只有一个批配置。</span><span class="sxs-lookup"><span data-stu-id="58828-176">Determining the batch by using the party ID was used because each party configuration could have only one batch configuration.</span></span>  
  
 <span data-ttu-id="58828-177">在 BizTalk Server 中，每个参与方可以有多个批配置，因此已不再够用，仅显示参与方 ID 用于确定要使用的批处理配置。</span><span class="sxs-lookup"><span data-stu-id="58828-177">In BizTalk Server, each party can have multiple batch configurations, so it is no longer sufficient to use only the pary ID to determine the batch configuration to use.</span></span>  <span data-ttu-id="58828-178">若要指示必须通过多个批处理配置处理消息，消息必须具有 EDI。BatchIDs 属性设置为一个空格分隔批 Id 应将消息发送到的列表。</span><span class="sxs-lookup"><span data-stu-id="58828-178">To indicate that a message must be processed by multiple batch configurations, the message must have the EDI.BatchIDs property set to a space delimited list of batch IDs that the message should be sent to.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="58828-179">处理消息只有一个使用标记时的一方使用 EDI 的 ID。DestinationPartyId 属性升级批处理业务流程将处理该消息。</span><span class="sxs-lookup"><span data-stu-id="58828-179">When processing messages marked with only a single party ID using the EDI.DestinationPartyId property, the message will be processed by the upgrade batching orchestration.</span></span> <span data-ttu-id="58828-180">有关详细信息，请参阅[装配批处理的 EDI 交换](../core/assembling-a-batched-edi-interchange.md)。</span><span class="sxs-lookup"><span data-stu-id="58828-180">For more information, see [Assembling a Batched EDI Interchange](../core/assembling-a-batched-edi-interchange.md).</span></span>  
  
 <span data-ttu-id="58828-181">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="58828-181">**Resolution**</span></span>  
  
 <span data-ttu-id="58828-182">升级自定义管道组件，以便其设置 EDI.BatchIDs 属性，而非 EDI.DestinationParties。</span><span class="sxs-lookup"><span data-stu-id="58828-182">Upgrade the custom pipeline component so that it sets the EDI.BatchIDs property instead of EDI.DestinationParties.</span></span>  <span data-ttu-id="58828-183">每个参与方，可以在 EDI 属性批处理设置页上找到特定批的批 ID。</span><span class="sxs-lookup"><span data-stu-id="58828-183">The batch ID for a specific batch can be found on the Batches settings page of EDI properties for each party.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="58828-184">如果 BatchMarker 管道组件使用的消息进行批处理标记不会出现此问题。</span><span class="sxs-lookup"><span data-stu-id="58828-184">This problem does not occur if the BatchMarker pipeline component is used to mark the message for batching.</span></span>  
  
## <a name="batch-filter-refresh-timeout-is-hardcoded-to-fifteen-minutes"></a><span data-ttu-id="58828-185">批处理筛选器刷新超时是硬编码为 15 分钟</span><span class="sxs-lookup"><span data-stu-id="58828-185">Batch Filter Refresh Timeout is Hardcoded to Fifteen Minutes</span></span>  
 <span data-ttu-id="58828-186">在修改时批处理筛选条件，它将需要 15 分钟才能使更改生效。</span><span class="sxs-lookup"><span data-stu-id="58828-186">When modifying the batch filter criteria, it will take 15 minutes before the changes take effect.</span></span> <span data-ttu-id="58828-187">此刷新时间间隔不能修改。</span><span class="sxs-lookup"><span data-stu-id="58828-187">This refresh interval cannot be modified.</span></span> <span data-ttu-id="58828-188">若要使筛选器立即生效，请重新启动 BizTalk Server 主机进程。</span><span class="sxs-lookup"><span data-stu-id="58828-188">To have the filter take effect immediately, restart the BizTalk Server host process.</span></span>  
  
## <a name="the-routingorchestration-suspends-after-reporting-an-uncaught-exception"></a><span data-ttu-id="58828-189">报告未捕获的异常后挂起 RoutingOrchestration</span><span class="sxs-lookup"><span data-stu-id="58828-189">The RoutingOrchestration Suspends After Reporting an Uncaught Exception</span></span>  
 <span data-ttu-id="58828-190">**现象**</span><span class="sxs-lookup"><span data-stu-id="58828-190">**Symptoms**</span></span>  
  
 <span data-ttu-id="58828-191">在应用程序事件日志中启动 XLANG/s 的 Microsoft.BizTalk.Edi.RoutingOrchestration.BatchRoutingService 失败，因为未捕获时处理目标为多个批处理配置的文档，您都可能会收到错误异常。</span><span class="sxs-lookup"><span data-stu-id="58828-191">When processing documents that are destined for multiple batch configurations, you may receive an error in the Application Event Log from XLANG/s starting that the Microsoft.BizTalk.Edi.RoutingOrchestration.BatchRoutingService failed due to an uncaught exception.</span></span>  
  
 <span data-ttu-id="58828-192">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="58828-192">**Possible Cause**</span></span>  
  
 <span data-ttu-id="58828-193">RoutingOrchestration 尝试将消息发送到 BatchingOrchestration 和 BatchingOrchestration 实例未启动时，会出现此错误。</span><span class="sxs-lookup"><span data-stu-id="58828-193">This error can occur when the RoutingOrchestration attempts to send a message to the BatchingOrchestration and the BatchingOrchestration instance is not started.</span></span>  
  
 <span data-ttu-id="58828-194">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="58828-194">**Resolution**</span></span>  
  
 <span data-ttu-id="58828-195">确保在提交文档要进行批处理之前正在运行 BatchingOrchestration 实例。</span><span class="sxs-lookup"><span data-stu-id="58828-195">Ensure that the BatchingOrchestration instances are running before submitting documents to be batched.</span></span>  
  
## <a name="many-active-batches-may-cause-the-biztalkmsgboxdb-logfile-to-grow-large"></a><span data-ttu-id="58828-196">许多活动的批处理可能会导致 BizTalkMsgBoxDb 日志文件变得大</span><span class="sxs-lookup"><span data-stu-id="58828-196">Many Active Batches May Cause the BizTalkMsgBoxDb Logfile to Grow Large</span></span>  
 <span data-ttu-id="58828-197">**现象**</span><span class="sxs-lookup"><span data-stu-id="58828-197">**Symptoms**</span></span>  
  
 <span data-ttu-id="58828-198">启动多个批次之后，你可能会注意到 BizTalk messagebox 数据库 (BizTalkMsgBoxDb) 的事务日志已增长到很大。</span><span class="sxs-lookup"><span data-stu-id="58828-198">After starting several batches, you may notice that the transaction log for the BizTalk message box database (BizTalkMsgBoxDb) has grown to a large size.</span></span>  
  
 <span data-ttu-id="58828-199">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="58828-199">**Possible Cause**</span></span>  
  
 <span data-ttu-id="58828-200">如果您有大量的批处理发布条件的入门导致短暂的间隔批处理发布 （例如，计划发布每隔一分钟的批处理） 之间，则可以会出现此问题。</span><span class="sxs-lookup"><span data-stu-id="58828-200">This problem can occur if you have a large number of batches started with release criteria that causes a short interval between batch releases (for example, a batch that is scheduled to release every minute).</span></span>  
  
 <span data-ttu-id="58828-201">在启动批处理时创建的批处理业务流程实例是一个长时间运行的过程，在释放一批后保存到数据库。</span><span class="sxs-lookup"><span data-stu-id="58828-201">The batching orchestration instance that is created when you start a batch is a long running process that persists to the database after releasing a batch.</span></span> <span data-ttu-id="58828-202">业务流程仍然存在，每次事务日志增长将由于事务参与持久性。</span><span class="sxs-lookup"><span data-stu-id="58828-202">Each time the orchestration persists, the transaction log will grow due to the transactions involved in persistence.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="58828-203">在暂留过程中，批处理业务流程会将事务日志增大约 30kb。</span><span class="sxs-lookup"><span data-stu-id="58828-203">The batching orchestration will grow the transaction log by approximately 30kb during persistence.</span></span>  
  
 <span data-ttu-id="58828-204">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="58828-204">**Resolution**</span></span>  
  
 <span data-ttu-id="58828-205">若要解决此问题，请将发行条件修改为增加批处理发布之间的时间。</span><span class="sxs-lookup"><span data-stu-id="58828-205">To resolve this problem, modify the release criteria to increase the time between batch releases.</span></span> <span data-ttu-id="58828-206">有关详细信息，请参阅[配置批处理 (X12)](../core/configuring-batching-x12.md)。</span><span class="sxs-lookup"><span data-stu-id="58828-206">For more information, see [Configuring Batching (X12)](../core/configuring-batching-x12.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58828-207">请参阅</span><span class="sxs-lookup"><span data-stu-id="58828-207">See Also</span></span>  
 <span data-ttu-id="58828-208">[配置 EDI 确认](../core/configuring-edi-acknowledgments.md) </span><span class="sxs-lookup"><span data-stu-id="58828-208">[Configuring EDI Acknowledgments](../core/configuring-edi-acknowledgments.md) </span></span>  
 <span data-ttu-id="58828-209">[处理传入批](../core/processing-incoming-batches.md) </span><span class="sxs-lookup"><span data-stu-id="58828-209">[Processing Incoming Batches](../core/processing-incoming-batches.md) </span></span>  
 <span data-ttu-id="58828-210">[对传出 EDI 消息进行批处理](../core/batching-outgoing-edi-messages.md) </span><span class="sxs-lookup"><span data-stu-id="58828-210">[Batching Outgoing EDI Messages](../core/batching-outgoing-edi-messages.md) </span></span>  
 [<span data-ttu-id="58828-211">配置 EDI 批</span><span class="sxs-lookup"><span data-stu-id="58828-211">Configuring EDI Batches</span></span>](../core/configuring-edi-batches.md)