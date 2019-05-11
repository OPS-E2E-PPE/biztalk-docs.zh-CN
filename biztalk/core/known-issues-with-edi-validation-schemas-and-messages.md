---
title: 使用 EDI 验证、 架构和消息的已知问题 |Microsoft Docs
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
ms.openlocfilehash: 706b165067fbbed058c12ff096c91851594d945a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380750"
---
# <a name="known-issues-with-edi-validation-schemas-and-messages"></a><span data-ttu-id="295eb-102">EDI 验证、 架构和消息的已知的问题</span><span class="sxs-lookup"><span data-stu-id="295eb-102">Known Issues with EDI Validation, Schemas, and Messages</span></span>
<span data-ttu-id="295eb-103">本主题介绍已知的验证问题。</span><span class="sxs-lookup"><span data-stu-id="295eb-103">This topic describes known validation issues.</span></span>  
  
## <a name="message-is-suspended-with-edi-validation-turned-off"></a><span data-ttu-id="295eb-104">在 EDI 验证关闭，则挂起消息</span><span class="sxs-lookup"><span data-stu-id="295eb-104">Message Is Suspended with EDI Validation Turned Off</span></span>  
 <span data-ttu-id="295eb-105">**症状**</span><span class="sxs-lookup"><span data-stu-id="295eb-105">**Symptom**</span></span>  
  
 <span data-ttu-id="295eb-106">违反了配对的规则，并关闭验证，但消息被挂起 （本应将序列化消息）。</span><span class="sxs-lookup"><span data-stu-id="295eb-106">A paired rule is violated, and validation is turned off, but the message is suspended (expected results are that the message is serialized).</span></span>  
  
 <span data-ttu-id="295eb-107">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="295eb-107">**Possible Cause**</span></span>  
  
 <span data-ttu-id="295eb-108">不执行跨字段/段验证，即使**EDI 类型**属性中取消选中**验证和确认生成设置**节点的**EDI 属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="295eb-108">Cross-field/segment validation is performed, even if **EDI type** property is deselected in the **Validation and ACK Generation Settings** node of the **EDI Properties** dialog box.</span></span> <span data-ttu-id="295eb-109">因为在架构批注中开启进行验证。</span><span class="sxs-lookup"><span data-stu-id="295eb-109">Validation occurs because it is turned on in the schema annotation.</span></span>  
  
 <span data-ttu-id="295eb-110">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="295eb-110">**Resolution**</span></span>  
  
 <span data-ttu-id="295eb-111">关闭在架构批注中的验证。</span><span class="sxs-lookup"><span data-stu-id="295eb-111">Turn off validation in the schema annotation.</span></span>  
  
## <a name="the-biztalk-service-needs-to-be-restarted-after-a-schema-has-been-edited-and-redeployed"></a><span data-ttu-id="295eb-112">BizTalk 服务需要编辑并重新部署架构之后，必须重新启动</span><span class="sxs-lookup"><span data-stu-id="295eb-112">The BizTalk service needs to be restarted after a schema has been edited and redeployed</span></span>  
 <span data-ttu-id="295eb-113">**症状**</span><span class="sxs-lookup"><span data-stu-id="295eb-113">**Symptom**</span></span>  
  
 <span data-ttu-id="295eb-114">编辑并重新部署架构之后，BizTalk Server 未成功处理了有效的消息。</span><span class="sxs-lookup"><span data-stu-id="295eb-114">BizTalk Server does not successfully process a valid message after a schema has been edited and redeployed.</span></span>  
  
 <span data-ttu-id="295eb-115">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="295eb-115">**Possible Cause**</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="295eb-116">缓存架构无超时。</span><span class="sxs-lookup"><span data-stu-id="295eb-116">caches schemas with unlimited timeouts.</span></span>  
  
 <span data-ttu-id="295eb-117">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="295eb-117">**Resolution**</span></span>  
  
 <span data-ttu-id="295eb-118">编辑并重新部署架构后, 重新启动 BizTalk Server 应用程序服务。</span><span class="sxs-lookup"><span data-stu-id="295eb-118">After editing and redeploying a schema, restart the BizTalk Server Application service.</span></span> <span data-ttu-id="295eb-119">您还必须重新启动承载正在使用所重新部署的架构的管道的主机实例。</span><span class="sxs-lookup"><span data-stu-id="295eb-119">You also must restart the host instance hosting the pipeline that is using the redeployed schema.</span></span>  
  
## <a name="processing-has-been-aborted-for-messages-of-a-single-encoding-type-for-a-single-party"></a><span data-ttu-id="295eb-120">处理已中止的消息的编码类型的某一参与方</span><span class="sxs-lookup"><span data-stu-id="295eb-120">Processing Has Been Aborted for Messages of a Single Encoding Type for a Single Party</span></span>  
 <span data-ttu-id="295eb-121">**症状**</span><span class="sxs-lookup"><span data-stu-id="295eb-121">**Symptom**</span></span>  
  
 <span data-ttu-id="295eb-122">一种编码类型的所有消息的处理 （例如，X12 或 EDIFACT） 的某一参与方已被中止。</span><span class="sxs-lookup"><span data-stu-id="295eb-122">The processing of all messages of a single encoding type (for example, X12 or EDIFACT) for a single party have been aborted.</span></span> <span data-ttu-id="295eb-123">另一参与方处理的同一参与方，另一个编码类型的消息或任何消息，具有不受影响。</span><span class="sxs-lookup"><span data-stu-id="295eb-123">Processing of messages of another encoding type for the same party, or any messages for another party, has not been affected.</span></span>  
  
 <span data-ttu-id="295eb-124">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="295eb-124">**Possible Cause**</span></span>  
  
 <span data-ttu-id="295eb-125">交换、 组或事务集控制编号的长度超出了最大允许长度。</span><span class="sxs-lookup"><span data-stu-id="295eb-125">The length of the interchange, group, or transaction set control number has exceeded the maximum allowable length.</span></span>  
  
 <span data-ttu-id="295eb-126">对于 X12 消息，一个控件的最大长度数字为九位。</span><span class="sxs-lookup"><span data-stu-id="295eb-126">For X12 messages, the maximum length of a control number is nine digits.</span></span> <span data-ttu-id="295eb-127">对于 EDIFACT 消息，控制编号的最大长度是三个字段 14 位数字。</span><span class="sxs-lookup"><span data-stu-id="295eb-127">For EDIFACT message, the maximum length of a control number is 14 digits over three fields.</span></span>  
  
 <span data-ttu-id="295eb-128">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="295eb-128">**Resolution**</span></span>  
  
 <span data-ttu-id="295eb-129">重置受影响的参与方 EDI 属性对话框中的相应属性页中的控制编号。</span><span class="sxs-lookup"><span data-stu-id="295eb-129">Reset the control number in the appropriate property page of the EDI Properties dialog box for the affected party.</span></span> <span data-ttu-id="295eb-130">你可以编辑以下属性页中的控制编号：</span><span class="sxs-lookup"><span data-stu-id="295eb-130">You can edit the control numbers in the following property pages:</span></span>  
  
-   <span data-ttu-id="295eb-131">X12 交换控制编号：适用于 X12 的 ISA 段定义页 （位于参与方作为交换接收方节点） 属性</span><span class="sxs-lookup"><span data-stu-id="295eb-131">X12 interchange control number: ISA Segment Definition page (in the Party as Interchange Receiver node) for X12 Properties</span></span>  
  
-   <span data-ttu-id="295eb-132">X12 组或事务集控制编号：GS 和 ST 段定义页 (位于 X12 的参与方作为交换接收方节点属性)</span><span class="sxs-lookup"><span data-stu-id="295eb-132">X12 group or transaction set control number: GS and ST Segment Definition page (in the Party as Interchange Receiver node for X12 Properties)</span></span>  
  
-   <span data-ttu-id="295eb-133">EDIFACT 交换控制编号：UNB 段定义页 （位于参与方作为交换接收方的 EDIFACT 属性的节点）</span><span class="sxs-lookup"><span data-stu-id="295eb-133">EDIFACT interchange control number: UNB Segment Definition page (in the Party as Interchange Receiver node for EDIFACT Properties)</span></span>  
  
-   <span data-ttu-id="295eb-134">EDIFACT 组或事务集控制编号：UNG 和 UNH 段定义页 （位于参与方作为交换接收方的 EDIFACT 属性的节点）</span><span class="sxs-lookup"><span data-stu-id="295eb-134">EDIFACT group or transaction set control number: UNG and UNH Segment Definition page (in the Party as Interchange Receiver node for EDIFACT Properties)</span></span>  
  
## <a name="biztalk-server-validates-with-schemas-that-have-unh-segments-with-seven-data-elements"></a><span data-ttu-id="295eb-135">BizTalk Server 使用已具有七个数据元素的 UNH 段的架构验证</span><span class="sxs-lookup"><span data-stu-id="295eb-135">BizTalk Server validates with schemas that have UNH segments with seven data elements</span></span>  
 <span data-ttu-id="295eb-136">在早期版本的 EDIFACT 中，UNH 段具有四个元素，而不是七个元素 （其中三个是可选的） 的 UNH 段具有更高版本中。</span><span class="sxs-lookup"><span data-stu-id="295eb-136">In earlier versions of EDIFACT, the UNH segment has four elements, rather than the seven elements (three of which are optional) that the UNH segment has in later versions.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="295eb-137">使用更高版本具有七个元素进行验证。</span><span class="sxs-lookup"><span data-stu-id="295eb-137">uses the later version with seven elements for validation.</span></span>  
  
## <a name="error-messages-generated-for-multiple-cross-field-validation-rules-will-not-be-specific-to-the-rule"></a><span data-ttu-id="295eb-138">为多个跨字段验证规则生成的错误消息将不是特定于规则</span><span class="sxs-lookup"><span data-stu-id="295eb-138">Error messages generated for multiple cross-field validation rules will not be specific to the rule</span></span>  
 <span data-ttu-id="295eb-139">如果架构包含一条消息中的数据元素的多个跨字段验证规则，并出现错误时使用的数据元素，每个验证规则将生成一个单独的错误。</span><span class="sxs-lookup"><span data-stu-id="295eb-139">If a schema contains multiple cross-field validation rules for a data element in a message, and an error occurs with the data element, a separate error will be generated for each validation rule.</span></span> <span data-ttu-id="295eb-140">但是，每个这些错误将具有相同的错误代码和说明;这些错误将不是特定于验证规则。</span><span class="sxs-lookup"><span data-stu-id="295eb-140">However, each of these errors will have the same error code and description; the errors will not be specific to the validation rule.</span></span>  
  
## <a name="if-edi-type-validation-is-disabled-on-receive-and-enabled-on-send-the-send-pipeline-will-not-be-able-to-serialize-the-message"></a><span data-ttu-id="295eb-141">如果在上禁用 EDI 类型验证接收和发送上启用，发送管道将不能序列化的消息</span><span class="sxs-lookup"><span data-stu-id="295eb-141">If EDI type validation is disabled on receive and enabled on send, the send pipeline will not be able to serialize the message</span></span>  
 <span data-ttu-id="295eb-142">如果关闭在接收端 EDI 类型验证，EDI 接收管道将从收到的 EDI 消息，生成一条 XML 消息，指示为有效的消息。</span><span class="sxs-lookup"><span data-stu-id="295eb-142">If you turn off EDI type validation on the receive side, the EDI receive pipeline will generate an XML message from a received EDI message, whether or not the message is valid.</span></span> <span data-ttu-id="295eb-143">如果在发送端启用 EDI 验证，EDI 发送管道不能如果 XML 文件包含错误，并且因此将生成错误的 XML 重新处理成有效的 EDI 文件。</span><span class="sxs-lookup"><span data-stu-id="295eb-143">If EDI validation is enabled on the send side, the EDI send pipeline will not be able to reprocess the XML into a valid EDI file if the XML file contains errors, and as a result will generate an error.</span></span>  
  
## <a name="edi-promoted-properties-are-only-available-if-your-application-has-a-reference-to-the-biztalk-edi-application"></a><span data-ttu-id="295eb-144">EDI 升级属性才可用，如果你的应用程序具有对 BizTalk EDI 应用程序的引用</span><span class="sxs-lookup"><span data-stu-id="295eb-144">EDI promoted properties are only available if your application has a reference to the BizTalk EDI application</span></span>  
 <span data-ttu-id="295eb-145">**症状**</span><span class="sxs-lookup"><span data-stu-id="295eb-145">**Symptom**</span></span>  
  
 <span data-ttu-id="295eb-146">EDI 命名空间下的升级的属性不显示在想要使用的升级属性列表中，例如，在业务流程或发送端口的筛选条件中。</span><span class="sxs-lookup"><span data-stu-id="295eb-146">Promoted properties under the EDI namespace are not displayed in the list of promoted properties that you are trying to use, for example, in an orchestration or in the filter conditions for a send port.</span></span>  
  
 <span data-ttu-id="295eb-147">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="295eb-147">**Possible Cause**</span></span>  
  
 <span data-ttu-id="295eb-148">正在使用的 BizTalk 应用程序没有对 BizTalk EDI 应用程序的引用。</span><span class="sxs-lookup"><span data-stu-id="295eb-148">The BizTalk application that you are using does not have a reference to the BizTalk EDI Application.</span></span> <span data-ttu-id="295eb-149">EDI 升级属性的属性架构是 BizTalk EDI 应用程序的资源文件夹中包含的 Microsoft.BizTalk.Edi.BaseArtifacts.dll 中。</span><span class="sxs-lookup"><span data-stu-id="295eb-149">The property schemas for the EDI promoted properties are in Microsoft.BizTalk.Edi.BaseArtifacts.dll, which is included in the Resources folder of BizTalk EDI Application.</span></span>  
  
 <span data-ttu-id="295eb-150">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="295eb-150">**Resolution**</span></span>  
  
 <span data-ttu-id="295eb-151">您正在使用的 BizTalk 应用程序，添加对 BizTalk EDI 应用程序的引用。</span><span class="sxs-lookup"><span data-stu-id="295eb-151">To the BizTalk application that you are working in, add a reference to the BizTalk EDI Application.</span></span>  
  
## <a name="the-data-element-name-in-a-context-property-name-contains-an-underscore-not-a-period"></a><span data-ttu-id="295eb-152">上下文属性名称中的数据元素名称包含下划线，而不是句点</span><span class="sxs-lookup"><span data-stu-id="295eb-152">The Data Element Name in a Context Property Name Contains an Underscore, Not a Period</span></span>  
 <span data-ttu-id="295eb-153">EDI 段中的数据元素的名称包含句点，例如 UNB2.1，它是 UNB2 发送方段的标识字段。</span><span class="sxs-lookup"><span data-stu-id="295eb-153">The name of a data element within an EDI segment contains a period, for example, UNB2.1, which is the identification field for the UNB2 Sender segment.</span></span> <span data-ttu-id="295eb-154">但是，如果数据元素名是 EDI 上下文属性的一部分，用下划线代替句点。</span><span class="sxs-lookup"><span data-stu-id="295eb-154">However, when the data element name is included as part of an EDI context property, the period is replaced with an underscore.</span></span> <span data-ttu-id="295eb-155">例如，发送方标识数据元素的上下文属性即为 EDI。UNB2_1，不是 EDI。UNB2.1。</span><span class="sxs-lookup"><span data-stu-id="295eb-155">For example, the context property for the Sender Identification data element is EDI.UNB2_1, not EDI.UNB2.1.</span></span> <span data-ttu-id="295eb-156">这样做的原因是，一段不支持上下文属性名称中。</span><span class="sxs-lookup"><span data-stu-id="295eb-156">The reason for this is that a period is not supported in a context property name.</span></span>  
  
## <a name="irrelevant-string-is-appended-to-instance-validation-error-message"></a><span data-ttu-id="295eb-157">不相关的字符串追加到实例验证错误消息</span><span class="sxs-lookup"><span data-stu-id="295eb-157">Irrelevant string is appended to instance validation error message</span></span>  
 <span data-ttu-id="295eb-158">每当在实例验证过程中收到错误，字符串"BEC 2004"将追加到的错误消息。</span><span class="sxs-lookup"><span data-stu-id="295eb-158">Whenever you receive an error during instance validation, the string "BEC 2004" will be appended to the error message.</span></span> <span data-ttu-id="295eb-159">你可以忽略此字符串。</span><span class="sxs-lookup"><span data-stu-id="295eb-159">You can ignore this string.</span></span>  
  
## <a name="edifact-schema-names-are-case-sensitive"></a><span data-ttu-id="295eb-160">EDIFACT 架构名区分大小写</span><span class="sxs-lookup"><span data-stu-id="295eb-160">EDIFACT Schema Names Are Case-Sensitive</span></span>  
 <span data-ttu-id="295eb-161">EDIFACT 架构，架构名称的架构的 root_reference 数据元素中所示是区分大小写。</span><span class="sxs-lookup"><span data-stu-id="295eb-161">The schema name of an EDIFACT schema, as shown in the root_reference data element of the schema, is case-sensitive.</span></span> <span data-ttu-id="295eb-162">例如，EFACT_D98B_ORDERS 与 EFACT_d98B_Orders 将是两个不同的架构。</span><span class="sxs-lookup"><span data-stu-id="295eb-162">For example, EFACT_D98B_ORDERS and EFACT_d98B_Orders would be two different schemas.</span></span>  
  
## <a name="invalid-edi-messages-can-be-suspended-even-if-edi-type-validation-is-disabled"></a><span data-ttu-id="295eb-163">无效的 EDI 消息可以被挂起，即使禁用 EDI 类型验证</span><span class="sxs-lookup"><span data-stu-id="295eb-163">Invalid EDI Messages Can Be Suspended Even If EDI Type Validation Is Disabled</span></span>  
 <span data-ttu-id="295eb-164">即使禁用 EDI 类型验证，则会执行 EDI 结构验证。</span><span class="sxs-lookup"><span data-stu-id="295eb-164">EDI structural validation is performed even if the EDI Type validation is disabled.</span></span> <span data-ttu-id="295eb-165">未通过基本结构验证的交换将挂起，即使禁用 EDI 类型验证。</span><span class="sxs-lookup"><span data-stu-id="295eb-165">An interchange that fails the basic structural validations will be suspended, even if the EDI Type validation is disabled.</span></span>  
  
## <a name="the-edi-assembler-will-serialize-an-unbatched-interchange-even-if-a-separator-character-is-used-in-an-envelope-header"></a><span data-ttu-id="295eb-166">即使在信封头中使用分隔符，EDI 组装器将序列化未批处理的交换</span><span class="sxs-lookup"><span data-stu-id="295eb-166">The EDI Assembler Will Serialize an Unbatched Interchange Even If a Separator Character Is Used in an Envelope Header</span></span>  
 <span data-ttu-id="295eb-167">用于分隔字段标头和尾部字段的分隔符字符必须不能在定义中的任何交换、 组或事务集标头字段或尾字段，为作为交换接收方的参与方定义的一样。</span><span class="sxs-lookup"><span data-stu-id="295eb-167">The separator characters used to separate header and trailer fields must not be used in the definition of any of the interchange, group, or transaction set header or trailer fields, as defined for the party as interchange receiver.</span></span> <span data-ttu-id="295eb-168">如果是，将无法发送 BizTalk Server 在 EDI 组装器中或在接收方的拆装器处理交换。</span><span class="sxs-lookup"><span data-stu-id="295eb-168">If they are, the interchange will fail processing either in the EDI Assembler of the sending BizTalk Server or in the disassembler of the receiving party.</span></span> <span data-ttu-id="295eb-169">交换将失败，EDI 组装器中是否出站批，因为组装器将验证标头控制 （服务） 架构对信封。</span><span class="sxs-lookup"><span data-stu-id="295eb-169">The interchange will fail in the EDI Assembler if it is an outbound batch, because the Assembler will validate the envelope against the header control (service) schema.</span></span> <span data-ttu-id="295eb-170">如果交换未进行批处理，EDI 组装器将其序列化，但将无法在接收方的拆装器中的处理。</span><span class="sxs-lookup"><span data-stu-id="295eb-170">If the interchange is unbatched, the EDI Assembler will serialize it, but it will fail processing in the disassembler at the receiving party.</span></span>  
  
## <a name="mismatched-character-sets-can-result-in-suspended-interchanges"></a><span data-ttu-id="295eb-171">字符集不匹配可能会导致交换被挂起</span><span class="sxs-lookup"><span data-stu-id="295eb-171">Mismatched Character Sets Can Result in Suspended Interchanges</span></span>  
 <span data-ttu-id="295eb-172">用于传出交换的字符集应与用于创建插入交换的事务集的字符集相同。</span><span class="sxs-lookup"><span data-stu-id="295eb-172">The character set used for an outgoing interchange should be the same as the character set used to create the transaction sets inserted into the interchange.</span></span> <span data-ttu-id="295eb-173">如果没有，则交换很可能会挂起与错误消息，指示存在无效字符。</span><span class="sxs-lookup"><span data-stu-id="295eb-173">If not, the interchange will likely be suspended with an error message indicating that there were invalid characters.</span></span>  
  
 <span data-ttu-id="295eb-174">例如，如果创建一个 EDIFACT 批使用 UNOA 字符集，但事务集添加到批中包含小写字符，批处理业务流程将挂起该消息，因为 UNOA 不允许小写字符。</span><span class="sxs-lookup"><span data-stu-id="295eb-174">For example, if you create an EDIFACT batch using the UNOA character set, but a transaction set added to the batch has lower-case characters, the batching orchestration will suspend the message because UNOA does not allow lower-case characters.</span></span>  
  
 <span data-ttu-id="295eb-175">另举一例，如果你配置 EDI 发送管道的 X12 交换具有"基本"字符集，但 X12 批处理交换具有小写字符因为在 X12 中选择 X12 字符集交换信封生成页参与方为交换接收方设置为"扩展"或"UTF8/Unicode"，在应用信封设置时，就将挂起的批处理的消息。</span><span class="sxs-lookup"><span data-stu-id="295eb-175">As another example, if you configure the EDI send pipeline for X12 interchanges with the "Basic" character set, but an X12 batched interchange has lower-case characters because the X12 character set selected in the X12 Interchange Envelop Generation page for the party as an interchange receiver is set to "Extended" or "UTF8/Unicode", the batched message will be suspended when envelope settings are applied.</span></span>  
  
## <a name="using-unh25-for-schema-resolution-requires-an-update-to-the-schema"></a><span data-ttu-id="295eb-176">将 UNH2.5 用于架构解析需要的架构更新</span><span class="sxs-lookup"><span data-stu-id="295eb-176">Using UNH2.5 for schema resolution requires an update to the schema</span></span>  
 <span data-ttu-id="295eb-177">如果用于传入 EDIFACT 交换的架构解析将 UNH2.5 （协会分配代码），您需要更新 \Program Files\Microsoft BizTalk Server 20xx\Schema 文件夹中的相关文档架构。</span><span class="sxs-lookup"><span data-stu-id="295eb-177">If you use UNH2.5 (the Association assigned code) for schema resolution of an incoming EDIFACT interchange, you will need to update the relevant document schema in the \Program Files\Microsoft BizTalk Server 20xx\Schema folder.</span></span> <span data-ttu-id="295eb-178">您需要将 UNH2.5 的值附加到 root_reference、 display_reference 和 xs: element name 的现有值。</span><span class="sxs-lookup"><span data-stu-id="295eb-178">You will need to append the value of UNH2.5 to the existing values for the root_reference, display_reference, and xs:element name.</span></span> <span data-ttu-id="295eb-179">例如，如果 UNH2.5 为"EAN008"并且正在使用的是 EFACT_D96A_INVOIC 架构，您将设置 root_reference、 display_reference 和 xs: element name 为"EFACT_D96A_INVOIC_EAN008"。</span><span class="sxs-lookup"><span data-stu-id="295eb-179">For example, if UNH2.5 is "EAN008" and you are using the EFACT_D96A_INVOIC schema, you would set root_reference, display_reference, and xs:element name to "EFACT_D96A_INVOIC_EAN008".</span></span>  
  
## <a name="the-compressed-file-of-schemas-will-be-replaced-when-an-upgrade-is-performed"></a><span data-ttu-id="295eb-180">执行升级时，将替换架构的压缩的文件</span><span class="sxs-lookup"><span data-stu-id="295eb-180">The compressed file of schemas will be replaced when an upgrade is performed</span></span>  
 <span data-ttu-id="295eb-181">如果升级 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到更高版本中，您的安装中的 MicrosoftEdiXSDTemplates.exe 文件将被替换为与升级关联的 MicrosoftEdiXSDTemplates.exe 文件。</span><span class="sxs-lookup"><span data-stu-id="295eb-181">If you upgrade Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to a later build, the MicrosoftEdiXSDTemplates.exe file in your installation will be replaced with the MicrosoftEdiXSDTemplates.exe file associated with the upgrade.</span></span> <span data-ttu-id="295eb-182">如果你打算继续使用旧压缩文件中的架构，将不再可以访问到压缩的文件在升级后除非您备份了旧压缩文件。</span><span class="sxs-lookup"><span data-stu-id="295eb-182">If you plan to continue to use the schemas from the old compressed file, you will no longer have access to the compressed file after the upgrade unless you back up the old compressed file.</span></span>  
  
## <a name="if-a-group-contains-multiple-x12-transaction-sets-all-must-be-of-the-same-type"></a><span data-ttu-id="295eb-183">如果一个组中包含多个 X12 事务集，则所有必须是相同类型的</span><span class="sxs-lookup"><span data-stu-id="295eb-183">If a group contains multiple X12 transaction sets, all must be of the same type</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="295eb-184">不支持混合使用同一组中的不同的事务集。</span><span class="sxs-lookup"><span data-stu-id="295eb-184">does not support mixing different transaction sets within the same group.</span></span> <span data-ttu-id="295eb-185">当一组包含多个事务时，ST01 的值必须是相同的所有事务。</span><span class="sxs-lookup"><span data-stu-id="295eb-185">When a group contains multiple transactions, the value of ST01 must be the same for all transactions.</span></span>  
  
## <a name="receiving-x12-interchanges-that-contain-non-ascii-delimiters-may-result-in-the-message-becoming-suspended"></a><span data-ttu-id="295eb-186">接收 X12 包含非 ASCII 分隔符的交换可能会导致挂起消息</span><span class="sxs-lookup"><span data-stu-id="295eb-186">Receiving X12 interchanges that contain non-ASCII delimiters may result in the message becoming suspended</span></span>  
 <span data-ttu-id="295eb-187">**症状**</span><span class="sxs-lookup"><span data-stu-id="295eb-187">**Symptom**</span></span>  
  
 <span data-ttu-id="295eb-188">当接收 X12 交换，则使用非 ASCII 分隔符的值，该消息可能会挂起并写入到应用程序事件日志错误。</span><span class="sxs-lookup"><span data-stu-id="295eb-188">When receiving an X12 interchange that uses non-ASCII delimiter values, the message may become suspended and an error written to the application event log.</span></span>  
  
 <span data-ttu-id="295eb-189">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="295eb-189">**Possible Cause**</span></span>  
  
 <span data-ttu-id="295eb-190">如果交换没有编码为 utf-8，则会出现此问题。</span><span class="sxs-lookup"><span data-stu-id="295eb-190">This problem can occur if the interchange is not encoded as UTF-8.</span></span>  
  
 <span data-ttu-id="295eb-191">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="295eb-191">**Resolution**</span></span>  
  
 <span data-ttu-id="295eb-192">请确保任何传入的 X12 交换包含非 ASCII 分隔符的编码为 utf-8。</span><span class="sxs-lookup"><span data-stu-id="295eb-192">Ensure that any incoming X12 interchange that contains non-ASCII delimiters is encoded as UTF-8.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="295eb-193">请参阅</span><span class="sxs-lookup"><span data-stu-id="295eb-193">See Also</span></span>  
 <span data-ttu-id="295eb-194">[EDI 处理的已知的问题](../core/known-issues-with-edi-processing.md) </span><span class="sxs-lookup"><span data-stu-id="295eb-194">[Known Issues with EDI Processing](../core/known-issues-with-edi-processing.md) </span></span>  
 <span data-ttu-id="295eb-195">[EDI 消息传递](../core/edi-messaging.md) </span><span class="sxs-lookup"><span data-stu-id="295eb-195">[EDI Messaging](../core/edi-messaging.md) </span></span>  
 <span data-ttu-id="295eb-196">[EDI 消息验证](../core/edi-message-validation.md) </span><span class="sxs-lookup"><span data-stu-id="295eb-196">[EDI Message Validation](../core/edi-message-validation.md) </span></span>  
 <span data-ttu-id="295eb-197">[EDI 架构](../core/edi-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="295eb-197">[EDI Schemas](../core/edi-schemas.md) </span></span>  
 [<span data-ttu-id="295eb-198">开发 EDI 架构</span><span class="sxs-lookup"><span data-stu-id="295eb-198">Developing EDI Schemas</span></span>](../core/developing-edi-schemas.md)