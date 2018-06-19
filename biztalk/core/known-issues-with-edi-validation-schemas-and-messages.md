---
title: EDI 验证、 架构和消息的已知问题 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 417c3e18-9a97-4d59-bc2b-e96a8c33d388
caps.latest.revision: 42
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2a508834ff81814b17bc12f1d698984d65748092
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264557"
---
# <a name="known-issues-with-edi-validation-schemas-and-messages"></a><span data-ttu-id="d41e8-102">EDI 验证、架构和消息的已知问题</span><span class="sxs-lookup"><span data-stu-id="d41e8-102">Known Issues with EDI Validation, Schemas, and Messages</span></span>
<span data-ttu-id="d41e8-103">本主题介绍已知的验证问题。</span><span class="sxs-lookup"><span data-stu-id="d41e8-103">This topic describes known validation issues.</span></span>  
  
## <a name="message-is-suspended-with-edi-validation-turned-off"></a><span data-ttu-id="d41e8-104">在 EDI 验证关闭的情况下消息被挂起</span><span class="sxs-lookup"><span data-stu-id="d41e8-104">Message Is Suspended with EDI Validation Turned Off</span></span>  
 <span data-ttu-id="d41e8-105">**症状**</span><span class="sxs-lookup"><span data-stu-id="d41e8-105">**Symptom**</span></span>  
  
 <span data-ttu-id="d41e8-106">违反了配对规则，因而关闭了验证，但消息被挂起（本应将消息序列化）。</span><span class="sxs-lookup"><span data-stu-id="d41e8-106">A paired rule is violated, and validation is turned off, but the message is suspended (expected results are that the message is serialized).</span></span>  
  
 <span data-ttu-id="d41e8-107">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="d41e8-107">**Possible Cause**</span></span>  
  
 <span data-ttu-id="d41e8-108">不执行跨-字段/段验证，即使**EDI 类型**中取消选择属性**验证和确认生成设置**节点**EDI 属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="d41e8-108">Cross-field/segment validation is performed, even if **EDI type** property is deselected in the **Validation and ACK Generation Settings** node of the **EDI Properties** dialog box.</span></span> <span data-ttu-id="d41e8-109">之所以会进行验证，是因为在架构批注中打开了验证。</span><span class="sxs-lookup"><span data-stu-id="d41e8-109">Validation occurs because it is turned on in the schema annotation.</span></span>  
  
 <span data-ttu-id="d41e8-110">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d41e8-110">**Resolution**</span></span>  
  
 <span data-ttu-id="d41e8-111">在架构批注中关闭验证。</span><span class="sxs-lookup"><span data-stu-id="d41e8-111">Turn off validation in the schema annotation.</span></span>  
  
## <a name="the-biztalk-service-needs-to-be-restarted-after-a-schema-has-been-edited-and-redeployed"></a><span data-ttu-id="d41e8-112">编辑并重新部署架构之后 BizTalk 服务需要重新启动</span><span class="sxs-lookup"><span data-stu-id="d41e8-112">The BizTalk service needs to be restarted after a schema has been edited and redeployed</span></span>  
 <span data-ttu-id="d41e8-113">**症状**</span><span class="sxs-lookup"><span data-stu-id="d41e8-113">**Symptom**</span></span>  
  
 <span data-ttu-id="d41e8-114">在编辑并重新部署架构之后 BizTalk Server 未成功处理一个有效的消息。</span><span class="sxs-lookup"><span data-stu-id="d41e8-114">BizTalk Server does not successfully process a valid message after a schema has been edited and redeployed.</span></span>  
  
 <span data-ttu-id="d41e8-115">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="d41e8-115">**Possible Cause**</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="d41e8-116"> 缓存架构无超时限制。</span><span class="sxs-lookup"><span data-stu-id="d41e8-116"> caches schemas with unlimited timeouts.</span></span>  
  
 <span data-ttu-id="d41e8-117">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d41e8-117">**Resolution**</span></span>  
  
 <span data-ttu-id="d41e8-118">在编辑并重新部署架构之后，重新启动 BizTalk Server 应用程序服务。</span><span class="sxs-lookup"><span data-stu-id="d41e8-118">After editing and redeploying a schema, restart the BizTalk Server Application service.</span></span> <span data-ttu-id="d41e8-119">您还必须重新启动承载正在使用所重新部署架构的管道的主机实例。</span><span class="sxs-lookup"><span data-stu-id="d41e8-119">You also must restart the host instance hosting the pipeline that is using the redeployed schema.</span></span>  
  
## <a name="processing-has-been-aborted-for-messages-of-a-single-encoding-type-for-a-single-party"></a><span data-ttu-id="d41e8-120">对某一参与方某个编码类型的消息的处理已中止。</span><span class="sxs-lookup"><span data-stu-id="d41e8-120">Processing Has Been Aborted for Messages of a Single Encoding Type for a Single Party</span></span>  
 <span data-ttu-id="d41e8-121">**症状**</span><span class="sxs-lookup"><span data-stu-id="d41e8-121">**Symptom**</span></span>  
  
 <span data-ttu-id="d41e8-122">对某一参与方某个编码类型（如 X12 或 EDIFACT）的所有消息的处理都已中止。</span><span class="sxs-lookup"><span data-stu-id="d41e8-122">The processing of all messages of a single encoding type (for example, X12 or EDIFACT) for a single party have been aborted.</span></span> <span data-ttu-id="d41e8-123">对同一参与方另一编码类型的消息或另一参与方的任何消息的处理均未受影响。</span><span class="sxs-lookup"><span data-stu-id="d41e8-123">Processing of messages of another encoding type for the same party, or any messages for another party, has not been affected.</span></span>  
  
 <span data-ttu-id="d41e8-124">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="d41e8-124">**Possible Cause**</span></span>  
  
 <span data-ttu-id="d41e8-125">交换、组或事务集控制编号的长度已超出允许的最大长度。</span><span class="sxs-lookup"><span data-stu-id="d41e8-125">The length of the interchange, group, or transaction set control number has exceeded the maximum allowable length.</span></span>  
  
 <span data-ttu-id="d41e8-126">对于 X12 消息，控制编号的最大长度为九位。</span><span class="sxs-lookup"><span data-stu-id="d41e8-126">For X12 messages, the maximum length of a control number is nine digits.</span></span> <span data-ttu-id="d41e8-127">对于 EDIFACT 消息，控制编号的最大长度为三个字段 14 位。</span><span class="sxs-lookup"><span data-stu-id="d41e8-127">For EDIFACT message, the maximum length of a control number is 14 digits over three fields.</span></span>  
  
 <span data-ttu-id="d41e8-128">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d41e8-128">**Resolution**</span></span>  
  
 <span data-ttu-id="d41e8-129">对于受影响的参与方，重置“EDI 属性”对话框相应属性页中的控制编号。</span><span class="sxs-lookup"><span data-stu-id="d41e8-129">Reset the control number in the appropriate property page of the EDI Properties dialog box for the affected party.</span></span> <span data-ttu-id="d41e8-130">可以编辑以下属性页中的控制编号：</span><span class="sxs-lookup"><span data-stu-id="d41e8-130">You can edit the control numbers in the following property pages:</span></span>  
  
-   <span data-ttu-id="d41e8-131">X12 交换控制编号： ISA 段定义 X12 （作为交换收件人节点方） 中的页属性</span><span class="sxs-lookup"><span data-stu-id="d41e8-131">X12 interchange control number: ISA Segment Definition page (in the Party as Interchange Receiver node) for X12 Properties</span></span>  
  
-   <span data-ttu-id="d41e8-132">X12 组或事务集控制编号： GS 和 ST 段定义的页 (对于 X12 为交换的接收方节点方中属性)</span><span class="sxs-lookup"><span data-stu-id="d41e8-132">X12 group or transaction set control number: GS and ST Segment Definition page (in the Party as Interchange Receiver node for X12 Properties)</span></span>  
  
-   <span data-ttu-id="d41e8-133">EDIFACT 交换控制编号： UNB 段定义页 （在作为 EDIFACT 属性交换收件人节点方）</span><span class="sxs-lookup"><span data-stu-id="d41e8-133">EDIFACT interchange control number: UNB Segment Definition page (in the Party as Interchange Receiver node for EDIFACT Properties)</span></span>  
  
-   <span data-ttu-id="d41e8-134">EDIFACT 组或事务集控制编号： UNG 和新罕布什尔大学段定义页上 （在作为 EDIFACT 属性交换接收方节点方）</span><span class="sxs-lookup"><span data-stu-id="d41e8-134">EDIFACT group or transaction set control number: UNG and UNH Segment Definition page (in the Party as Interchange Receiver node for EDIFACT Properties)</span></span>  
  
## <a name="biztalk-server-validates-with-schemas-that-have-unh-segments-with-seven-data-elements"></a><span data-ttu-id="d41e8-135">BizTalk Server 用具有包含七个数据元素的 UNH 段的架构进行验证</span><span class="sxs-lookup"><span data-stu-id="d41e8-135">BizTalk Server validates with schemas that have UNH segments with seven data elements</span></span>  
 <span data-ttu-id="d41e8-136">在早期版本的 EDIFACT 中，UNH 段具有四个元素，而不是像更高版本的 UNH 段那样具有七个元素（其中三个是可选元素）。</span><span class="sxs-lookup"><span data-stu-id="d41e8-136">In earlier versions of EDIFACT, the UNH segment has four elements, rather than the seven elements (three of which are optional) that the UNH segment has in later versions.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="d41e8-137"> 使用更高版本（具有七个元素用于验证）。</span><span class="sxs-lookup"><span data-stu-id="d41e8-137"> uses the later version with seven elements for validation.</span></span>  
  
## <a name="error-messages-generated-for-multiple-cross-field-validation-rules-will-not-be-specific-to-the-rule"></a><span data-ttu-id="d41e8-138">为多个跨字段验证规则生成的错误消息将不是特定于规则的</span><span class="sxs-lookup"><span data-stu-id="d41e8-138">Error messages generated for multiple cross-field validation rules will not be specific to the rule</span></span>  
 <span data-ttu-id="d41e8-139">如果架构包含针对消息中某一数据元素的多个跨字段验证规则，并且该数据元素出现了错误，则会为每个验证规则生成一个单独的错误。</span><span class="sxs-lookup"><span data-stu-id="d41e8-139">If a schema contains multiple cross-field validation rules for a data element in a message, and an error occurs with the data element, a separate error will be generated for each validation rule.</span></span> <span data-ttu-id="d41e8-140">但是，其中每个错误的错误代码和说明均相同；错误将不是特定于验证规则的。</span><span class="sxs-lookup"><span data-stu-id="d41e8-140">However, each of these errors will have the same error code and description; the errors will not be specific to the validation rule.</span></span>  
  
## <a name="if-edi-type-validation-is-disabled-on-receive-and-enabled-on-send-the-send-pipeline-will-not-be-able-to-serialize-the-message"></a><span data-ttu-id="d41e8-141">如果在接收时禁用 EDI 类型验证，在发送时启用该验证，则发送管道将无法对消息进行序列化</span><span class="sxs-lookup"><span data-stu-id="d41e8-141">If EDI type validation is disabled on receive and enabled on send, the send pipeline will not be able to serialize the message</span></span>  
 <span data-ttu-id="d41e8-142">如果在接收端关闭 EDI 类型验证，则 EDI 接收管道将根据接收到的 EDI 消息生成 XML 消息，无论该消息是否有效。</span><span class="sxs-lookup"><span data-stu-id="d41e8-142">If you turn off EDI type validation on the receive side, the EDI receive pipeline will generate an XML message from a received EDI message, whether or not the message is valid.</span></span> <span data-ttu-id="d41e8-143">如果在发送端启用 EDI 验证，且 XML 文件包含错误，则 EDI 发送管道将无法将 XML 重新处理成有效的 EDI 文件，因此会产生错误。</span><span class="sxs-lookup"><span data-stu-id="d41e8-143">If EDI validation is enabled on the send side, the EDI send pipeline will not be able to reprocess the XML into a valid EDI file if the XML file contains errors, and as a result will generate an error.</span></span>  
  
## <a name="edi-promoted-properties-are-only-available-if-your-application-has-a-reference-to-the-biztalk-edi-application"></a><span data-ttu-id="d41e8-144">仅在应用程序具有对 BizTalk EDI 应用程序的引用的情况下才可使用 EDI 升级属性</span><span class="sxs-lookup"><span data-stu-id="d41e8-144">EDI promoted properties are only available if your application has a reference to the BizTalk EDI application</span></span>  
 <span data-ttu-id="d41e8-145">**症状**</span><span class="sxs-lookup"><span data-stu-id="d41e8-145">**Symptom**</span></span>  
  
 <span data-ttu-id="d41e8-146">EDI 命名空间下的升级属性未显示在您正尝试使用的升级属性列表中（如业务流程或发送端口的筛选条件中）。</span><span class="sxs-lookup"><span data-stu-id="d41e8-146">Promoted properties under the EDI namespace are not displayed in the list of promoted properties that you are trying to use, for example, in an orchestration or in the filter conditions for a send port.</span></span>  
  
 <span data-ttu-id="d41e8-147">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="d41e8-147">**Possible Cause**</span></span>  
  
 <span data-ttu-id="d41e8-148">您所使用的 BizTalk 应用程序不具有对 BizTalk EDI 应用程序的引用。</span><span class="sxs-lookup"><span data-stu-id="d41e8-148">The BizTalk application that you are using does not have a reference to the BizTalk EDI Application.</span></span> <span data-ttu-id="d41e8-149">EDI 升级属性的属性架构位于 BizTalk EDI 应用程序的“资源”文件夹所包含的 Microsoft.BizTalk.Edi.BaseArtifacts.dll 中。</span><span class="sxs-lookup"><span data-stu-id="d41e8-149">The property schemas for the EDI promoted properties are in Microsoft.BizTalk.Edi.BaseArtifacts.dll, which is included in the Resources folder of BizTalk EDI Application.</span></span>  
  
 <span data-ttu-id="d41e8-150">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d41e8-150">**Resolution**</span></span>  
  
 <span data-ttu-id="d41e8-151">将对 BizTalk EDI 应用程序的引用添加到您正在处理的 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="d41e8-151">To the BizTalk application that you are working in, add a reference to the BizTalk EDI Application.</span></span>  
  
## <a name="the-data-element-name-in-a-context-property-name-contains-an-underscore-not-a-period"></a><span data-ttu-id="d41e8-152">上下文属性名称中的数据元素名包含下划线，而不是句点</span><span class="sxs-lookup"><span data-stu-id="d41e8-152">The Data Element Name in a Context Property Name Contains an Underscore, Not a Period</span></span>  
 <span data-ttu-id="d41e8-153">EDI 段中的数据元素名（例如 UNB2.1，它是 UNB2 发送方段的标识字段）包含句点。</span><span class="sxs-lookup"><span data-stu-id="d41e8-153">The name of a data element within an EDI segment contains a period, for example, UNB2.1, which is the identification field for the UNB2 Sender segment.</span></span> <span data-ttu-id="d41e8-154">不过，如果数据元素名是 EDI 上下文属性的组成部分，则会用下划线代替句点。</span><span class="sxs-lookup"><span data-stu-id="d41e8-154">However, when the data element name is included as part of an EDI context property, the period is replaced with an underscore.</span></span> <span data-ttu-id="d41e8-155">例如，发送方标识数据元素的上下文属性是 EDI.UNB2_1 而非 EDI.UNB2.1。</span><span class="sxs-lookup"><span data-stu-id="d41e8-155">For example, the context property for the Sender Identification data element is EDI.UNB2_1, not EDI.UNB2.1.</span></span> <span data-ttu-id="d41e8-156">这是因为上下文属性名称中不支持使用句点。</span><span class="sxs-lookup"><span data-stu-id="d41e8-156">The reason for this is that a period is not supported in a context property name.</span></span>  
  
## <a name="irrelevant-string-is-appended-to-instance-validation-error-message"></a><span data-ttu-id="d41e8-157">不相关的字符串附加到了实例验证错误消息中</span><span class="sxs-lookup"><span data-stu-id="d41e8-157">Irrelevant string is appended to instance validation error message</span></span>  
 <span data-ttu-id="d41e8-158">在实例验证期间无论何时收到错误，字符串“BEC 2004”均会附加到错误消息中。</span><span class="sxs-lookup"><span data-stu-id="d41e8-158">Whenever you receive an error during instance validation, the string "BEC 2004" will be appended to the error message.</span></span> <span data-ttu-id="d41e8-159">可以忽略此字符串。</span><span class="sxs-lookup"><span data-stu-id="d41e8-159">You can ignore this string.</span></span>  
  
## <a name="edifact-schema-names-are-case-sensitive"></a><span data-ttu-id="d41e8-160">EDIFACT 架构名区分大小写</span><span class="sxs-lookup"><span data-stu-id="d41e8-160">EDIFACT Schema Names Are Case-Sensitive</span></span>  
 <span data-ttu-id="d41e8-161">EDIFACT 架构的架构名（显示在架构的 root_reference 数据元素中）区分大小写。</span><span class="sxs-lookup"><span data-stu-id="d41e8-161">The schema name of an EDIFACT schema, as shown in the root_reference data element of the schema, is case-sensitive.</span></span> <span data-ttu-id="d41e8-162">例如，EFACT_D98B_ORDERS 与 EFACT_d98B_Orders 将是两个不同的架构。</span><span class="sxs-lookup"><span data-stu-id="d41e8-162">For example, EFACT_D98B_ORDERS and EFACT_d98B_Orders would be two different schemas.</span></span>  
  
## <a name="invalid-edi-messages-can-be-suspended-even-if-edi-type-validation-is-disabled"></a><span data-ttu-id="d41e8-163">即使 EDI 类型验证已禁用，无效的 EDI 消息仍可能被挂起</span><span class="sxs-lookup"><span data-stu-id="d41e8-163">Invalid EDI Messages Can Be Suspended Even If EDI Type Validation Is Disabled</span></span>  
 <span data-ttu-id="d41e8-164">即使禁用 EDI 类型验证，则不执行 EDI 结构验证。</span><span class="sxs-lookup"><span data-stu-id="d41e8-164">EDI structural validation is performed even if the EDI Type validation is disabled.</span></span> <span data-ttu-id="d41e8-165">即使 EDI 类型验证已禁用，未通过基本结构验证的交换也会被挂起。</span><span class="sxs-lookup"><span data-stu-id="d41e8-165">An interchange that fails the basic structural validations will be suspended, even if the EDI Type validation is disabled.</span></span>  
  
## <a name="the-edi-assembler-will-serialize-an-unbatched-interchange-even-if-a-separator-character-is-used-in-an-envelope-header"></a><span data-ttu-id="d41e8-166">即使在信封头中使用了分隔符，EDI 组装器仍会对未批处理的交换进行序列化</span><span class="sxs-lookup"><span data-stu-id="d41e8-166">The EDI Assembler Will Serialize an Unbatched Interchange Even If a Separator Character Is Used in an Envelope Header</span></span>  
 <span data-ttu-id="d41e8-167">按照针对“作为交换接收方的参与方”的规定，切勿在交换、组或事务集的任何头字段或尾字段的定义中使用用于分隔头字段和尾字段的分隔符。</span><span class="sxs-lookup"><span data-stu-id="d41e8-167">The separator characters used to separate header and trailer fields must not be used in the definition of any of the interchange, group, or transaction set header or trailer fields, as defined for the party as interchange receiver.</span></span> <span data-ttu-id="d41e8-168">如果使用了这样的分隔符，则在作为发送方的 BizTalk Server 的 EDI 组装器中或在接收方的拆装器中将无法处理交换。</span><span class="sxs-lookup"><span data-stu-id="d41e8-168">If they are, the interchange will fail processing either in the EDI Assembler of the sending BizTalk Server or in the disassembler of the receiving party.</span></span> <span data-ttu-id="d41e8-169">如果交换为出站批，它在 EDI 组装器中将失败，因为组装器会根据头控制（服务）架构验证信封。</span><span class="sxs-lookup"><span data-stu-id="d41e8-169">The interchange will fail in the EDI Assembler if it is an outbound batch, because the Assembler will validate the envelope against the header control (service) schema.</span></span> <span data-ttu-id="d41e8-170">如果交换未进行批处理，EDI 组装器会将其序列化，但交换在接收方的拆装器中将无法处理。</span><span class="sxs-lookup"><span data-stu-id="d41e8-170">If the interchange is unbatched, the EDI Assembler will serialize it, but it will fail processing in the disassembler at the receiving party.</span></span>  
  
## <a name="mismatched-character-sets-can-result-in-suspended-interchanges"></a><span data-ttu-id="d41e8-171">字符集不匹配可能会导致交换被挂起</span><span class="sxs-lookup"><span data-stu-id="d41e8-171">Mismatched Character Sets Can Result in Suspended Interchanges</span></span>  
 <span data-ttu-id="d41e8-172">用于传出交换的字符集应与用于创建插入交换中的事务集的字符集相同。</span><span class="sxs-lookup"><span data-stu-id="d41e8-172">The character set used for an outgoing interchange should be the same as the character set used to create the transaction sets inserted into the interchange.</span></span> <span data-ttu-id="d41e8-173">如果不相同，则交换很有可能被挂起，同时出现一条指示存在无效字符的错误消息。</span><span class="sxs-lookup"><span data-stu-id="d41e8-173">If not, the interchange will likely be suspended with an error message indicating that there were invalid characters.</span></span>  
  
 <span data-ttu-id="d41e8-174">例如，如果使用 UNOA 字符集创建一个 EDIFACT 批，但添加到该批中的事务集包含小写字符，则批处理业务流程会将消息挂起，因为 UNOA 不允许出现小写字符。</span><span class="sxs-lookup"><span data-stu-id="d41e8-174">For example, if you create an EDIFACT batch using the UNOA character set, but a transaction set added to the batch has lower-case characters, the batching orchestration will suspend the message because UNOA does not allow lower-case characters.</span></span>  
  
 <span data-ttu-id="d41e8-175">再如，如果使用“基本”字符集配置用于 X12 交换的 EDI 发送管道，但 X12 批处理交换具有小写字符（因为在“作为交换接收方的参与方”的“X12 交换信封生成”页中选择的 X12 字符集设置为“扩展”或“UTF8/Unicode”），那么，在应用信封设置时批处理消息将被挂起。</span><span class="sxs-lookup"><span data-stu-id="d41e8-175">As another example, if you configure the EDI send pipeline for X12 interchanges with the "Basic" character set, but an X12 batched interchange has lower-case characters because the X12 character set selected in the X12 Interchange Envelop Generation page for the party as an interchange receiver is set to "Extended" or "UTF8/Unicode", the batched message will be suspended when envelope settings are applied.</span></span>  
  
## <a name="using-unh25-for-schema-resolution-requires-an-update-to-the-schema"></a><span data-ttu-id="d41e8-176">将 UNH2.5 用于架构解析时需要更新架构</span><span class="sxs-lookup"><span data-stu-id="d41e8-176">Using UNH2.5 for schema resolution requires an update to the schema</span></span>  
 <span data-ttu-id="d41e8-177">如果将 UNH2.5（协会分配的代码）用于传入 EDIFACT 交换的架构解析，则需要更新 \Program Files\Microsoft BizTalk Server 20xx\Schema 文件夹中的相关文档架构。</span><span class="sxs-lookup"><span data-stu-id="d41e8-177">If you use UNH2.5 (the Association assigned code) for schema resolution of an incoming EDIFACT interchange, you will need to update the relevant document schema in the \Program Files\Microsoft BizTalk Server 20xx\Schema folder.</span></span> <span data-ttu-id="d41e8-178">还需要将 UNH2.5 的值附加到 root_reference、display_reference 和 xs:element name 的现有值。</span><span class="sxs-lookup"><span data-stu-id="d41e8-178">You will need to append the value of UNH2.5 to the existing values for the root_reference, display_reference, and xs:element name.</span></span> <span data-ttu-id="d41e8-179">例如，如果 UNH2.5 为“EAN008”且您使用的是 EFACT_D96A_INVOIC 架构，则应将 root_reference、display_reference 和 xs:element name 设置为“EFACT_D96A_INVOIC_EAN008”。</span><span class="sxs-lookup"><span data-stu-id="d41e8-179">For example, if UNH2.5 is "EAN008" and you are using the EFACT_D96A_INVOIC schema, you would set root_reference, display_reference, and xs:element name to "EFACT_D96A_INVOIC_EAN008".</span></span>  
  
## <a name="the-compressed-file-of-schemas-will-be-replaced-when-an-upgrade-is-performed"></a><span data-ttu-id="d41e8-180">进行升级时架构的压缩文件将被替换</span><span class="sxs-lookup"><span data-stu-id="d41e8-180">The compressed file of schemas will be replaced when an upgrade is performed</span></span>  
 <span data-ttu-id="d41e8-181">如果将 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 升级到更高版本，则与升级关联的 MicrosoftEdiXSDTemplates.exe 文件将替换安装中的 MicrosoftEdiXSDTemplates.exe 文件。</span><span class="sxs-lookup"><span data-stu-id="d41e8-181">If you upgrade Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to a later build, the MicrosoftEdiXSDTemplates.exe file in your installation will be replaced with the MicrosoftEdiXSDTemplates.exe file associated with the upgrade.</span></span> <span data-ttu-id="d41e8-182">如果你计划继续使用旧压缩文件的架构，那么除非你备份了旧压缩文件，否则升级之后你将不能再访问此压缩文件。</span><span class="sxs-lookup"><span data-stu-id="d41e8-182">If you plan to continue to use the schemas from the old compressed file, you will no longer have access to the compressed file after the upgrade unless you back up the old compressed file.</span></span>  
  
## <a name="if-a-group-contains-multiple-x12-transaction-sets-all-must-be-of-the-same-type"></a><span data-ttu-id="d41e8-183">如果一个组中包含多个 X 12 事务集，则所有的事务集必须属于同一类型</span><span class="sxs-lookup"><span data-stu-id="d41e8-183">If a group contains multiple X12 transaction sets, all must be of the same type</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="d41e8-184"> 不支持在相同的组中混合不同的事务集。</span><span class="sxs-lookup"><span data-stu-id="d41e8-184"> does not support mixing different transaction sets within the same group.</span></span> <span data-ttu-id="d41e8-185">当一个组中包含多个事务时，所有事务的 ST01 值必须相同。</span><span class="sxs-lookup"><span data-stu-id="d41e8-185">When a group contains multiple transactions, the value of ST01 must be the same for all transactions.</span></span>  
  
## <a name="receiving-x12-interchanges-that-contain-non-ascii-delimiters-may-result-in-the-message-becoming-suspended"></a><span data-ttu-id="d41e8-186">接收包含非 ASCII 分隔符的 x12 交换可能会导致挂起消息</span><span class="sxs-lookup"><span data-stu-id="d41e8-186">Receiving X12 interchanges that contain non-ASCII delimiters may result in the message becoming suspended</span></span>  
 <span data-ttu-id="d41e8-187">**症状**</span><span class="sxs-lookup"><span data-stu-id="d41e8-187">**Symptom**</span></span>  
  
 <span data-ttu-id="d41e8-188">接收使用非 ASCII 分隔符的 X12 交换时，可能会挂起消息，并且会在应用程序事件日志中写入错误。</span><span class="sxs-lookup"><span data-stu-id="d41e8-188">When receiving an X12 interchange that uses non-ASCII delimiter values, the message may become suspended and an error written to the application event log.</span></span>  
  
 <span data-ttu-id="d41e8-189">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="d41e8-189">**Possible Cause**</span></span>  
  
 <span data-ttu-id="d41e8-190">如果交换没有编码为 utf-8，则会发生此问题。</span><span class="sxs-lookup"><span data-stu-id="d41e8-190">This problem can occur if the interchange is not encoded as UTF-8.</span></span>  
  
 <span data-ttu-id="d41e8-191">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="d41e8-191">**Resolution**</span></span>  
  
 <span data-ttu-id="d41e8-192">请确保包含非 ASCII 分隔符的任何传入 X12 交换编码为 UTF-8。</span><span class="sxs-lookup"><span data-stu-id="d41e8-192">Ensure that any incoming X12 interchange that contains non-ASCII delimiters is encoded as UTF-8.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d41e8-193">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d41e8-193">See Also</span></span>  
 <span data-ttu-id="d41e8-194">[EDI 处理的已知的问题](../core/known-issues-with-edi-processing.md) </span><span class="sxs-lookup"><span data-stu-id="d41e8-194">[Known Issues with EDI Processing](../core/known-issues-with-edi-processing.md) </span></span>  
 <span data-ttu-id="d41e8-195">[EDI 消息传递](../core/edi-messaging.md) </span><span class="sxs-lookup"><span data-stu-id="d41e8-195">[EDI Messaging](../core/edi-messaging.md) </span></span>  
 <span data-ttu-id="d41e8-196">[EDI 消息验证](../core/edi-message-validation.md) </span><span class="sxs-lookup"><span data-stu-id="d41e8-196">[EDI Message Validation](../core/edi-message-validation.md) </span></span>  
 <span data-ttu-id="d41e8-197">[EDI 架构](../core/edi-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="d41e8-197">[EDI Schemas](../core/edi-schemas.md) </span></span>  
 [<span data-ttu-id="d41e8-198">开发 EDI 架构</span><span class="sxs-lookup"><span data-stu-id="d41e8-198">Developing EDI Schemas</span></span>](../core/developing-edi-schemas.md)