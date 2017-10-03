---
title: "使用 EDI 批处理的已知问题 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 510ac82b-8a02-4135-87b7-0a5f288f5317
caps.latest.revision: "38"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e550a80cf8a7bbd6ae5e2b214c57d15427f919f9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-with-edi-batching"></a><span data-ttu-id="80c97-102">EDI 批处理的已知问题</span><span class="sxs-lookup"><span data-stu-id="80c97-102">Known Issues with EDI Batching</span></span>
<span data-ttu-id="80c97-103">本主题介绍了 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中批处理的已知问题。</span><span class="sxs-lookup"><span data-stu-id="80c97-103">This topic describes known issues with batching in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="subdocument-splitting-was-not-performed-even-though-the-subdocument-annotation-was-set-to-yes"></a><span data-ttu-id="80c97-104">即使子文档批注设置为“是”，也不会执行子文档拆分</span><span class="sxs-lookup"><span data-stu-id="80c97-104">Subdocument Splitting Was Not Performed Even Though the Subdocument Annotation Was Set to Yes</span></span>  
 <span data-ttu-id="80c97-105">**症状**</span><span class="sxs-lookup"><span data-stu-id="80c97-105">**Symptom**</span></span>  
  
 <span data-ttu-id="80c97-106">即使在该交换 HIPAA 架构 subdocument_creation_break 批注已设置为"是"。 不 HIPAA 交换拆分为子文档</span><span class="sxs-lookup"><span data-stu-id="80c97-106">A HIPAA interchange was not split into subdocuments even though the subdocument_creation_break annotation within the HIPAA schema for that interchange was set to "Yes."</span></span>  
  
 <span data-ttu-id="80c97-107">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="80c97-107">**Possible Cause**</span></span>  
  
-   <span data-ttu-id="80c97-108">入站的批处理的发送方的选项设置为"保留交换"。</span><span class="sxs-lookup"><span data-stu-id="80c97-108">The Inbound batch processing option for the sending party was set to "Preserve Interchange."</span></span> <span data-ttu-id="80c97-109">在这种情况下，即使已将 HIPAA 架构中的 subdocument_creation_break 批注设置为“是”，HIPAA 文档也不会拆分为子文档。</span><span class="sxs-lookup"><span data-stu-id="80c97-109">A HIPAA document will not be split into subdocuments if this is the case, even though the subdocument_creation_break annotation within the HIPAA schema is set to "Yes."</span></span>  
  
-   <span data-ttu-id="80c97-110">Subdocument_break 批注已设置为"是"，但 subdocument_creation_break 批注未设置为"是"。</span><span class="sxs-lookup"><span data-stu-id="80c97-110">The subdocument_break annotation was set to “Yes”, but the subdocument_creation_break annotation was not set to “Yes”.</span></span>  
  
 <span data-ttu-id="80c97-111">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="80c97-111">**Resolution**</span></span>  
  
-   <span data-ttu-id="80c97-112">在**验证和确认生成设置**页**EDI 属性**的发送方的对话框中设置**入站批处理**选项属性任一**将交换拆分为事务集-出错时暂停事务集**或**将交换拆分为事务集-出错时暂停交换**。</span><span class="sxs-lookup"><span data-stu-id="80c97-112">In the **Validation and ACK Generation Settings** page of the **EDI Properties** dialog box for the sending party, set the **Inbound batch processing** option property to either **Split Interchange as Transaction Sets – suspend Transaction Sets on Error** or **Split Interchange as Transaction Sets – suspend Interchange on Error**.</span></span>  
  
-   <span data-ttu-id="80c97-113">HIPAA 文档将不拆分为子文档除非 subdocument_creation_break 批注设置为"是"。</span><span class="sxs-lookup"><span data-stu-id="80c97-113">A HIPAA document will not be split into subdocuments unless the subdocument_creation_break annotation is set to “Yes.”</span></span>  
  
## <a name="validation-of-a-batch-may-fail-if-batch-configuration-settings-are-changed-while-the-batch-orchestration-is-activated"></a><span data-ttu-id="80c97-114">如果在批处理业务流程处于激活状态时更改批配置设置，批处理验证可能会失败</span><span class="sxs-lookup"><span data-stu-id="80c97-114">Validation of a Batch May Fail if Batch Configuration Settings Are Changed While the Batch Orchestration Is Activated</span></span>  
 <span data-ttu-id="80c97-115">如果在批处理业务流程处理批的过程中更改批的配置设置，则新配置设置不会应用于该批。</span><span class="sxs-lookup"><span data-stu-id="80c97-115">If you change batch configuration settings while the batching orchestration is processing a batch, the new configuration settings will not be picked up for that batch.</span></span> <span data-ttu-id="80c97-116">这会导致发送管道中产生验证错误。</span><span class="sxs-lookup"><span data-stu-id="80c97-116">This can result in validation errors in the send pipeline.</span></span>  
  
 <span data-ttu-id="80c97-117">这些设置位于“EDI 属性”对话框的“批处理”页。</span><span class="sxs-lookup"><span data-stu-id="80c97-117">These settings are in the Batches page of the EDI Properties dialog box.</span></span>  
  
 <span data-ttu-id="80c97-118">要解决此问题，请重新启动与批处理业务流程关联的主机实例。</span><span class="sxs-lookup"><span data-stu-id="80c97-118">To resolve this issue, restart the host instance(s) associated with the batching orchestration(s).</span></span> <span data-ttu-id="80c97-119">这会导致立即应用批配置设置。</span><span class="sxs-lookup"><span data-stu-id="80c97-119">This will cause the change to the batch configuration settings to take place immediately.</span></span>  
  
## <a name="the-batchcontrolmessagerecvloc-receive-location-can-only-run-on-a-32-bit-computer-or-in-wow-on-a-64-bit-computer"></a><span data-ttu-id="80c97-120">BatchControlMessageRecvLoc 接收位置只能在 32 位计算机或带有 WOW 环境的 64 位计算机上运行</span><span class="sxs-lookup"><span data-stu-id="80c97-120">The BatchControlMessageRecvLoc Receive Location Can Only Run on a 32-Bit Computer or in WOW on a 64-Bit Computer</span></span>  
 <span data-ttu-id="80c97-121">SQL 适配器只能在 32 位计算机上运行，或者在 64 位计算机上的 WOW64 仿真程序下运行。</span><span class="sxs-lookup"><span data-stu-id="80c97-121">SQL adapters only work on 32-bit computers or when running under the WOW64 emulator on 64-bit computers.</span></span> <span data-ttu-id="80c97-122">因此，安装程序安装的使用 SQL 适配器的 BatchControlMessageRecvLoc 接收位置将只能在 32 位计算机上运行，或者在 64 位计算机上的 WOW64 仿真程序下运行。</span><span class="sxs-lookup"><span data-stu-id="80c97-122">As a result, the BatchControlMessageRecvLoc receive location, which is installed by the setup program and uses the SQL adapter, will only work on a 32-bit computer or when running under WOW on a 64-bit computer.</span></span> <span data-ttu-id="80c97-123">此接收位置是批处理所必需的。</span><span class="sxs-lookup"><span data-stu-id="80c97-123">This receive location is required for batch processing.</span></span>  
  
 <span data-ttu-id="80c97-124">如果在 64 位计算机上的 WOW 下运行 BatchControlMessageRecvLoc 接收位置，则应在其他主机中运行批处理业务流程。</span><span class="sxs-lookup"><span data-stu-id="80c97-124">When running the BatchControlMessageRecvLoc receive location under WOW on a 64-bit computer, you should run the batching orchestrations in a different host.</span></span> <span data-ttu-id="80c97-125">如果运行批处理业务流程的主机与运行接收位置的主机相同，则该批处理业务流程也将在 WOW 下运行，这样您将失去在 64 位计算机上运行所具有的优势。</span><span class="sxs-lookup"><span data-stu-id="80c97-125">If they are run on the same host as the receive location, the batching orchestrations would also run under WOW, and you would lose the advantages of running on a 64-bit computer.</span></span>  
  
## <a name="a-batch-can-be-picked-up-by-an-unintended-send-port"></a><span data-ttu-id="80c97-126">意外发送端口可以提取批处理</span><span class="sxs-lookup"><span data-stu-id="80c97-126">A Batch Can Be Picked Up By an Unintended Send Port</span></span>  
 <span data-ttu-id="80c97-127">当批处理业务流程发布时将交换时，这样还有助于提升两个属性： ToBeBatched = False 和 DestinationPartyName = \< *PartyName*>。</span><span class="sxs-lookup"><span data-stu-id="80c97-127">When the batching orchestration publishes an interchange, it promotes two properties: ToBeBatched = False and DestinationPartyName = \<*PartyName*>.</span></span> <span data-ttu-id="80c97-128">订阅以上任意一个或两个属性的发送端口都可以提取这些批处理交换。</span><span class="sxs-lookup"><span data-stu-id="80c97-128">A send port subscribing to either or both of these properties can pick up these batched interchanges.</span></span> <span data-ttu-id="80c97-129">请确保配置发送端口的筛选器，使该发送端口仅提取应提取的批处理交换。</span><span class="sxs-lookup"><span data-stu-id="80c97-129">Make sure that a send port's filters are configured such that the send port picks up those batched interchanges that it is intended to pick up.</span></span>  
  
## <a name="a-batch-element-count-greater-than-the-required-number-of-transaction-sets-for-a-batch-may-not-prompt-batch-release"></a><span data-ttu-id="80c97-130">批元素计数大于批处理所需的事务集数目时可能不会提示批处理的发布</span><span class="sxs-lookup"><span data-stu-id="80c97-130">A Batch Element Count Greater Than the Required Number of Transaction Sets for a Batch May Not Prompt Batch Release</span></span>  
 <span data-ttu-id="80c97-131">如果批处理的发布条件基于每组或每个交换的事务集数目，即使批元素计数大于发布批处理所需的事务集数目，也可能不会发布此批处理。</span><span class="sxs-lookup"><span data-stu-id="80c97-131">If the batch release criteria is based upon the number of transaction sets per group or interchange, a batch may not be released even though the batch element count is greater than the number of transaction sets required for a batch to be released.</span></span> <span data-ttu-id="80c97-132">当启用确认并将批处理筛选条件设置为向批处理添加此确认时，则可能出现此问题。</span><span class="sxs-lookup"><span data-stu-id="80c97-132">This can happen if you enable acknowledgments, and set the batch filter criteria to add those acknowledgments to the batch.</span></span> <span data-ttu-id="80c97-133">在这种情况下，组（或交换）中的批元素数目将大于每组（或交换）的事务集数目。</span><span class="sxs-lookup"><span data-stu-id="80c97-133">In this instance, the number of batch elements in the group (or interchange) will be greater than the number of transaction sets per group (or interchange).</span></span> <span data-ttu-id="80c97-134">在上述情况中，如果每组（或每个交换）的事务集数目小于发布批处理所需的数目，则不会发布批处理；但同时，批元素数目可能大于发布批处理所需的事务集数目。</span><span class="sxs-lookup"><span data-stu-id="80c97-134">In that instance, a batch will not be released if the number of transaction sets per group (or interchange) is smaller than the number required for batch release, but at the same time the number of batch elements could be greater than the number of transaction sets required for batch release.</span></span>  
  
## <a name="no-batch-elements-were-saved-when-start-was-clicked"></a><span data-ttu-id="80c97-135">单击“开始”后未保存任何批元素</span><span class="sxs-lookup"><span data-stu-id="80c97-135">No Batch Elements Were Saved When Start Was Clicked</span></span>  
 <span data-ttu-id="80c97-136">**症状**</span><span class="sxs-lookup"><span data-stu-id="80c97-136">**Symptom**</span></span>  
  
 <span data-ttu-id="80c97-137">当**启动**被单击在方的批处理页中，任何消息为收集批处理。</span><span class="sxs-lookup"><span data-stu-id="80c97-137">When **Start** was clicked in the Batches page for a party, no messages were collected for the batch.</span></span>  
  
 <span data-ttu-id="80c97-138">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="80c97-138">**Possible Cause**</span></span>  
  
 <span data-ttu-id="80c97-139">从该处的日期时间**启动**被单击早于中输入的日期时间**激活**部分。</span><span class="sxs-lookup"><span data-stu-id="80c97-139">The datetime at which **Start** was clicked was earlier than the datetime entered in the **Activation** section.</span></span> <span data-ttu-id="80c97-140">因此，业务流程实例已激活，但为批处理收集任何消息。</span><span class="sxs-lookup"><span data-stu-id="80c97-140">As a result, the orchestration instance was activated, but no messages were collected for the batch.</span></span> <span data-ttu-id="80c97-141">有关详细信息，请参阅[配置传出批处理](../core/configuring-an-outgoing-batch.md)。</span><span class="sxs-lookup"><span data-stu-id="80c97-141">For more information, see [Configuring an Outgoing Batch](../core/configuring-an-outgoing-batch.md).</span></span>  
  
 <span data-ttu-id="80c97-142">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="80c97-142">**Resolution**</span></span>  
  
 <span data-ttu-id="80c97-143">单击**停止**遇到此问题的批处理配置的批处理页中。</span><span class="sxs-lookup"><span data-stu-id="80c97-143">Click **Stop** in the Batches page for the batch configuration experiencing this problem.</span></span> <span data-ttu-id="80c97-144">设置**激活**为**立即开始**或早于当前时间中，输入日期时间，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="80c97-144">Set the **Activation** to either **Start immediately** or enter a datetime earlier than the current time, and then click **Start**.</span></span> <span data-ttu-id="80c97-145">当提示你重置**启动**从 datetime 到当前时间中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="80c97-145">When you are prompted to reset the **Start** datetime to the current time, click **OK**.</span></span> <span data-ttu-id="80c97-146">此时 BizTalk Server 将开始为批处理收集消息。</span><span class="sxs-lookup"><span data-stu-id="80c97-146">BizTalk Server will start to collect messages for a batch at that point.</span></span>  
  
## <a name="the-number-of-bytes-in-an-edifact-batch-may-depend-upon-the-character-set-used"></a><span data-ttu-id="80c97-147">EDIFACT 批处理中的字节数可能取决于使用的字符集</span><span class="sxs-lookup"><span data-stu-id="80c97-147">The Number of Bytes in an EDIFACT Batch May Depend Upon the Character Set Used</span></span>  
 <span data-ttu-id="80c97-148">一些字符在某些 EDIFACT 字符集中可能是双字节字符，而在其他 EDIFACT 字符集中则可能是单字节字符。</span><span class="sxs-lookup"><span data-stu-id="80c97-148">Characters in some EDIFACT character sets may be double-byte characters, whereas in other EDIFACT character sets they may be single-byte characters.</span></span> <span data-ttu-id="80c97-149">鉴于以上原因，在您根据交换中的字符数设置批的发布条件时，相应交换中的字节数可能会因使用的字符集而不同。</span><span class="sxs-lookup"><span data-stu-id="80c97-149">Because of this, when you set the release criteria for batches based upon the number of characters in the interchange, the number of bytes in the interchange may differ depending on the character set used.</span></span>  
  
## <a name="the-characters--and--must-be-represented-in-their-encoded-form-in-the-envelope-of-a-batch"></a><span data-ttu-id="80c97-150">在批处理的信封中，必须以编码形式表示字符“<”和“&”</span><span class="sxs-lookup"><span data-stu-id="80c97-150">The Characters "<" and "&" Must be Represented in Their Encoded Form in the Envelope of a Batch</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="80c97-151">不支持以下字符以其文本形式时创建的批处理的 EDI 交换的信封字段:"<"和"&"。</span><span class="sxs-lookup"><span data-stu-id="80c97-151"> does not support the following characters in their literal form when creating the envelope fields of a batched EDI interchange: "<" and "&".</span></span>  
  
 <span data-ttu-id="80c97-152">如果在传出批处理交换的信封字段中按原义使用上述任一字符，当 EdiSend 管道用于序列化交换时可能会导致消息挂起。</span><span class="sxs-lookup"><span data-stu-id="80c97-152">Using either of these characters literally in the envelope fields of an outgoing batched interchange will result in a suspended message if the EdiSend pipeline is used to serialize the interchange.</span></span>  
  
 <span data-ttu-id="80c97-153">如果需要在批处理的信封字段中使用上述字符之一，以 BizTalk 管理员身份配置信封字段时，您可以使用下表中已编码的相应值：</span><span class="sxs-lookup"><span data-stu-id="80c97-153">If you need to use one of these characters in an envelope field of a batch, you can use the appropriate encoded value in the following table when you configure the envelope field in the BizTalk Administrator:</span></span>  
  
|<span data-ttu-id="80c97-154">字符</span><span class="sxs-lookup"><span data-stu-id="80c97-154">Character</span></span>|<span data-ttu-id="80c97-155">编码</span><span class="sxs-lookup"><span data-stu-id="80c97-155">Encoding</span></span>|  
|---------------|--------------|  
|<|&lt;|  
|&|&amp;|  
  
 <span data-ttu-id="80c97-156">如果使用上述编码格式之一，当 BizTalk Server 验证字段是否满足在 BizTalk Server 管理控制台的合作伙伴协议管理器 (PAM) 屏幕中的长度限制时，以该编码格式表示的每个字符都将计为一个单独字符。</span><span class="sxs-lookup"><span data-stu-id="80c97-156">When you use one of these encoded forms, each character in the encoded form will be counted as an individual character when BizTalk Server validates the field for its length restriction in the Partner Agreement Manager (PAM) screens in the BizTalk Server Administration console.</span></span> <span data-ttu-id="80c97-157">例如，即使的编码"&lt;"将表示单个字符"\<"中批处理的 EDI 交换中，BizTalk Server 将此算作四个字符的特定字段的长度限制进行验证时.</span><span class="sxs-lookup"><span data-stu-id="80c97-157">For example, even though the encoding "&lt;" would represent a single character "\<" in the batched EDI interchange, BizTalk Server would count this as four characters when validating against the length restriction of the particular field.</span></span> <span data-ttu-id="80c97-158">此问题仅适用于 PAM，而不适用于 EDI 组装器。</span><span class="sxs-lookup"><span data-stu-id="80c97-158">This is an issue for PAM only, not for the EDI Assembler.</span></span>  
  
## <a name="an-exeption-occurs-during-the-execution-of-the-upgrade-batch-orchestration"></a><span data-ttu-id="80c97-159">执行升级批处理业务流程期间出现异常</span><span class="sxs-lookup"><span data-stu-id="80c97-159">An Exeption Occurs During the Execution of the Upgrade Batch Orchestration</span></span>  
 <span data-ttu-id="80c97-160">**症状**</span><span class="sxs-lookup"><span data-stu-id="80c97-160">**Symptom**</span></span>  
  
 <span data-ttu-id="80c97-161">当使用在传入文档中设置 EDI.DestinationPartyId 属性的自定义管道组件时，您可能会接收到应用程序事件日志中的错误，指出执行升级批处理业务流程期间发生了异常。</span><span class="sxs-lookup"><span data-stu-id="80c97-161">When using a custom pipeline component that sets the EDI.DestinationPartyId property on incoming documents, you may receive an error in the Application event log stating that an exception has occurred during the execution of the upgrade batch orchestration.</span></span>  
  
 <span data-ttu-id="80c97-162">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="80c97-162">**Possible Cause**</span></span>  
  
 <span data-ttu-id="80c97-163">如果 ErrorMessage ="找不到批"，此错误指示升级批处理业务流程无法即可成功辨别传入文档的批。</span><span class="sxs-lookup"><span data-stu-id="80c97-163">If ErrorMessage = “The batch was not found”, this error indicates that the upgrade batch orchestration was not able to successfully identify a batch for the incoming document.</span></span>  
  
 <span data-ttu-id="80c97-164">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="80c97-164">**Resolution**</span></span>  
  
 <span data-ttu-id="80c97-165">升级批处理业务流程使用 EDI.DestinationPartyId 来查找参与方名称。</span><span class="sxs-lookup"><span data-stu-id="80c97-165">The upgrade batch orchestration uses the EDI.DestinationPartyId to look up the party name.</span></span> <span data-ttu-id="80c97-166">然后，业务流程构造一个使用方名称，EDI 的字符串。EncodingType 和字符串"Default"，然后查找与批处理名称匹配某个批配置。</span><span class="sxs-lookup"><span data-stu-id="80c97-166">The orchestration then constructs a string using the party name, EDI.EncodingType and the string “Default”, and then looks for a batch configuration with a matching batch name.</span></span> <span data-ttu-id="80c97-167">如果任何批配置不存在具有此名称，此错误记录到应用程序事件日志和业务流程实例处于挂起状态。</span><span class="sxs-lookup"><span data-stu-id="80c97-167">If no batch configuration exists with this name, this error is logged to the Application event log and the orchestration instance is suspended.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="80c97-168">例如，如果当事方名称为 Contoso 和 EDI。EncodingType X12，业务流程将查找名为 ContosoX12Default 一批。</span><span class="sxs-lookup"><span data-stu-id="80c97-168">For example, if the party name is Contoso and the EDI.EncodingType is X12, the orchestration will look for a batch named ‘ContosoX12Default’.</span></span>  
  
 <span data-ttu-id="80c97-169">若要解决此问题，请确保一批存在具有此名称的将与升级批处理业务流程所构造的字符串匹配。</span><span class="sxs-lookup"><span data-stu-id="80c97-169">To resolve this problem, ensure that a batch exists with a name that will match the string constructed by the upgrade batch orchestration.</span></span>  
  
## <a name="messages-marked-with-editobebatched--true-and-edidestinationparties-are-suspended"></a><span data-ttu-id="80c97-170">使用 EDI 标记的消息。ToBeBatched = True 和 EDI。DestinationParties 都将被挂起</span><span class="sxs-lookup"><span data-stu-id="80c97-170">Messages Marked with EDI.ToBeBatched = True and EDI.DestinationParties are Suspended</span></span>  
 <span data-ttu-id="80c97-171">**症状**</span><span class="sxs-lookup"><span data-stu-id="80c97-171">**Symptoms**</span></span>  
  
 <span data-ttu-id="80c97-172">当使用自定义管道组件将标记的批处理通过设置 EDI 消息。ToBeBatched = True 和 EDI。列表的 DestinationParties 方 Id，将用路由失败指出没有任何订户挂起消息。</span><span class="sxs-lookup"><span data-stu-id="80c97-172">When using a custom pipeline component to mark messages for batching by setting EDI.ToBeBatched = True and EDI.DestinationParties to a list of party IDs, the message will be suspended with a routing failure stating that there are no subscribers.</span></span>  
  
 <span data-ttu-id="80c97-173">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="80c97-173">**Possible Cause**</span></span>  
  
 <span data-ttu-id="80c97-174">在以前版本的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]时应处理一条消息，则会将 EDI 设置通过多个批处理配置。DestinationParties 属性设置为一个空格分隔的当事方 Id 的列表。</span><span class="sxs-lookup"><span data-stu-id="80c97-174">In previous versions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], when a message should be processed by multiple batch configurations you would set the EDI.DestinationParties property to a space delimited list of party IDs.</span></span> <span data-ttu-id="80c97-175">路由业务流程订阅具有 EDI.ToBeBatched = True 和 EDI.DestinationParties 属性的消息，会使用包含在 EDI.DestinationParties 属性中的参与方 ID 列表为每个 ID 创建消息，然后将消息传递到批处理业务流程。</span><span class="sxs-lookup"><span data-stu-id="80c97-175">The routing orchestration is subscribed to messages with the EDI.ToBeBatched = True and EDI.DestinationParties properties, and would use the list of party IDs contained in the EDI.DestinationParties property to create a message for each ID, and pass the messages to the batching orchestration.</span></span>  <span data-ttu-id="80c97-176">通过使用方确定批处理因为每个方配置可能只有一个批配置，已使用 ID。</span><span class="sxs-lookup"><span data-stu-id="80c97-176">Determining the batch by using the party ID was used because each party configuration could have only one batch configuration.</span></span>  
  
 <span data-ttu-id="80c97-177">在[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]，每一方可以有多个批处理配置，因此不再不足以仅显示 pary ID 用于确定要使用的批处理配置。</span><span class="sxs-lookup"><span data-stu-id="80c97-177">In [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], each party can have multiple batch configurations, so it is no longer sufficient to use only the pary ID to determine the batch configuration to use.</span></span>  <span data-ttu-id="80c97-178">若要指示多个批处理配置必须处理一条消息，消息必须 EDI。BatchIDs 属性设置为一个空格分隔的批处理消息应发送到的 Id 的列表。</span><span class="sxs-lookup"><span data-stu-id="80c97-178">To indicate that a message must be processed by multiple batch configurations, the message must have the EDI.BatchIDs property set to a space delimited list of batch IDs that the message should be sent to.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="80c97-179">处理标记且只有一个的邮件时方使用 EDI 的 ID。DestinationPartyId 属性升级批处理业务流程将处理该消息。</span><span class="sxs-lookup"><span data-stu-id="80c97-179">When processing messages marked with only a single party ID using the EDI.DestinationPartyId property, the message will be processed by the upgrade batching orchestration.</span></span> <span data-ttu-id="80c97-180">有关详细信息，请参阅[组合批处理的 EDI 交换](../core/assembling-a-batched-edi-interchange.md)。</span><span class="sxs-lookup"><span data-stu-id="80c97-180">For more information, see [Assembling a Batched EDI Interchange](../core/assembling-a-batched-edi-interchange.md).</span></span>  
  
 <span data-ttu-id="80c97-181">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="80c97-181">**Resolution**</span></span>  
  
 <span data-ttu-id="80c97-182">升级自定义管道组件，以便其设置 EDI.BatchIDs 属性，而非 EDI.DestinationParties。</span><span class="sxs-lookup"><span data-stu-id="80c97-182">Upgrade the custom pipeline component so that it sets the EDI.BatchIDs property instead of EDI.DestinationParties.</span></span>  <span data-ttu-id="80c97-183">特定的批处理的批处理 ID 可以找到 EDI 属性的批处理设置页上，为各参与方。</span><span class="sxs-lookup"><span data-stu-id="80c97-183">The batch ID for a specific batch can be found on the Batches settings page of EDI properties for each party.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="80c97-184">如果 BatchMarker 管道组件用来标记的消息的批处理不会出现此问题。</span><span class="sxs-lookup"><span data-stu-id="80c97-184">This problem does not occur if the BatchMarker pipeline component is used to mark the message for batching.</span></span>  
  
## <a name="batch-filter-refresh-timeout-is-hardcoded-to-fifteen-minutes"></a><span data-ttu-id="80c97-185">批次筛选器刷新超时是硬编码为十五分钟</span><span class="sxs-lookup"><span data-stu-id="80c97-185">Batch Filter Refresh Timeout is Hardcoded to Fifteen Minutes</span></span>  
 <span data-ttu-id="80c97-186">在修改批筛选器条件时，它将需要 15 分钟才能使更改生效。</span><span class="sxs-lookup"><span data-stu-id="80c97-186">When modifying the batch filter criteria, it will take 15 minutes before the changes take effect.</span></span> <span data-ttu-id="80c97-187">此刷新时间间隔不能修改。</span><span class="sxs-lookup"><span data-stu-id="80c97-187">This refresh interval cannot be modified.</span></span> <span data-ttu-id="80c97-188">若要使筛选器立即生效，请重新启动 BizTalk Server 主机进程。</span><span class="sxs-lookup"><span data-stu-id="80c97-188">To have the filter take effect immediately, restart the BizTalk Server host process.</span></span>  
  
## <a name="the-routingorchestration-suspends-after-reporting-an-uncaught-exception"></a><span data-ttu-id="80c97-189">RoutingOrchestration 挂起报告未捕获的异常后</span><span class="sxs-lookup"><span data-stu-id="80c97-189">The RoutingOrchestration Suspends After Reporting an Uncaught Exception</span></span>  
 <span data-ttu-id="80c97-190">**症状**</span><span class="sxs-lookup"><span data-stu-id="80c97-190">**Symptoms**</span></span>  
  
 <span data-ttu-id="80c97-191">应用程序事件日志中从 XLANG/秒开始，Microsoft.BizTalk.Edi.RoutingOrchestration.BatchRoutingService 失败，因为未捕获时处理针对多个批处理配置的文档，你都可能会收到错误异常。</span><span class="sxs-lookup"><span data-stu-id="80c97-191">When processing documents that are destined for multiple batch configurations, you may receive an error in the Application Event Log from XLANG/s starting that the Microsoft.BizTalk.Edi.RoutingOrchestration.BatchRoutingService failed due to an uncaught exception.</span></span>  
  
 <span data-ttu-id="80c97-192">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="80c97-192">**Possible Cause**</span></span>  
  
 <span data-ttu-id="80c97-193">当 RoutingOrchestration 尝试将消息发送到 BatchingOrchestration 并且 BatchingOrchestration 实例不会启动，可以出现此错误。</span><span class="sxs-lookup"><span data-stu-id="80c97-193">This error can occur when the RoutingOrchestration attempts to send a message to the BatchingOrchestration and the BatchingOrchestration instance is not started.</span></span>  
  
 <span data-ttu-id="80c97-194">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="80c97-194">**Resolution**</span></span>  
  
 <span data-ttu-id="80c97-195">确保在提交要批处理的文档之前正在运行 BatchingOrchestration 实例。</span><span class="sxs-lookup"><span data-stu-id="80c97-195">Ensure that the BatchingOrchestration instances are running before submitting documents to be batched.</span></span>  
  
## <a name="many-active-batches-may-cause-the-biztalkmsgboxdb-logfile-to-grow-large"></a><span data-ttu-id="80c97-196">许多活动的批处理数可能会导致变大 BizTalkMsgBoxDb 日志文件</span><span class="sxs-lookup"><span data-stu-id="80c97-196">Many Active Batches May Cause the BizTalkMsgBoxDb Logfile to Grow Large</span></span>  
 <span data-ttu-id="80c97-197">**症状**</span><span class="sxs-lookup"><span data-stu-id="80c97-197">**Symptoms**</span></span>  
  
 <span data-ttu-id="80c97-198">在开始几个批处理后，你可能注意到 BizTalk 消息框数据库 (BizTalkMsgBoxDb) 的事务日志已增加到较大的大小。</span><span class="sxs-lookup"><span data-stu-id="80c97-198">After starting several batches, you may notice that the transaction log for the BizTalk message box database (BizTalkMsgBoxDb) has grown to a large size.</span></span>  
  
 <span data-ttu-id="80c97-199">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="80c97-199">**Possible Cause**</span></span>  
  
 <span data-ttu-id="80c97-200">如果你有大量的批处理入门释放条件导致批次版本 （例如，计划以释放每分钟一批） 之间为较短间隔，则可能出现此问题。</span><span class="sxs-lookup"><span data-stu-id="80c97-200">This problem can occur if you have a large number of batches started with release criteria that causes a short interval between batch releases (for example, a batch that is scheduled to release every minute).</span></span>  
  
 <span data-ttu-id="80c97-201">启动一批时创建的批处理 orchestration 实例是释放一批后到数据库仍然存在一个长时间运行过程。</span><span class="sxs-lookup"><span data-stu-id="80c97-201">The batching orchestration instance that is created when you start a batch is a long running process that persists to the database after releasing a batch.</span></span> <span data-ttu-id="80c97-202">业务流程仍然存在，每次事务日志将会增长由于事务参与持久性。</span><span class="sxs-lookup"><span data-stu-id="80c97-202">Each time the orchestration persists, the transaction log will grow due to the transactions involved in persistence.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="80c97-203">在暂留过程中，批处理业务流程会将事务日志增大约 30kb。</span><span class="sxs-lookup"><span data-stu-id="80c97-203">The batching orchestration will grow the transaction log by approximately 30kb during persistence.</span></span>  
  
 <span data-ttu-id="80c97-204">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="80c97-204">**Resolution**</span></span>  
  
 <span data-ttu-id="80c97-205">若要解决此问题，请将发行条件修改为增加批处理发布之间的时间。</span><span class="sxs-lookup"><span data-stu-id="80c97-205">To resolve this problem, modify the release criteria to increase the time between batch releases.</span></span> <span data-ttu-id="80c97-206">有关详细信息，请参阅[配置批处理 (X12)](../core/configuring-batching-x12.md)。</span><span class="sxs-lookup"><span data-stu-id="80c97-206">For more information, see [Configuring Batching (X12)](../core/configuring-batching-x12.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80c97-207">另请参阅</span><span class="sxs-lookup"><span data-stu-id="80c97-207">See Also</span></span>  
 <span data-ttu-id="80c97-208">[配置 EDI 确认](../core/configuring-edi-acknowledgments.md) </span><span class="sxs-lookup"><span data-stu-id="80c97-208">[Configuring EDI Acknowledgments](../core/configuring-edi-acknowledgments.md) </span></span>  
 <span data-ttu-id="80c97-209">[处理传入的批次](../core/processing-incoming-batches.md) </span><span class="sxs-lookup"><span data-stu-id="80c97-209">[Processing Incoming Batches](../core/processing-incoming-batches.md) </span></span>  
 <span data-ttu-id="80c97-210">[对传出的 EDI 消息进行批处理](../core/batching-outgoing-edi-messages.md) </span><span class="sxs-lookup"><span data-stu-id="80c97-210">[Batching Outgoing EDI Messages](../core/batching-outgoing-edi-messages.md) </span></span>  
 [<span data-ttu-id="80c97-211">配置 EDI 批处理</span><span class="sxs-lookup"><span data-stu-id="80c97-211">Configuring EDI Batches</span></span>](../core/configuring-edi-batches.md)