---
title: 已知问题的 EDI 接收处理 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bbb3fd6a-381b-479e-a9f2-7b6371fac39e
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 75ab2769ab4a6eacf885dbf675a6bd3fda371007
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262957"
---
# <a name="known-issues-with-edi-receive-processing"></a><span data-ttu-id="861ca-102">EDI 接收处理的已知问题</span><span class="sxs-lookup"><span data-stu-id="861ca-102">Known Issues with EDI Receive Processing</span></span>
<span data-ttu-id="861ca-103">本主题介绍在 EDI 接收管道中进行处理时的已知问题。</span><span class="sxs-lookup"><span data-stu-id="861ca-103">This topic describes known issues with processing in the EDI receive pipeline.</span></span>  
  
## <a name="receive-side-processing-of-trailing-separators-fails"></a><span data-ttu-id="861ca-104">尾部分隔符的接收端处理失败</span><span class="sxs-lookup"><span data-stu-id="861ca-104">Receive-Side Processing of Trailing Separators Fails</span></span>  
 <span data-ttu-id="861ca-105">**症状**</span><span class="sxs-lookup"><span data-stu-id="861ca-105">**Symptom**</span></span>  
  
 <span data-ttu-id="861ca-106">带有尾部分隔符的事务集出错，对于 X12 编码的消息，产生的错误代码为 AK403= 6，对于 EDIFACT 编码的消息，产生的错误代码为 UCM3=4/UCD1=45。</span><span class="sxs-lookup"><span data-stu-id="861ca-106">A transaction set with a trailing separator fails with error code AK403= 6 for an X12-encoded message or error codes UCM3=4/UCD1=45 for an EDIFACT-encoded message.</span></span>  
  
 <span data-ttu-id="861ca-107">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="861ca-107">**Possible Cause**</span></span>  
  
 <span data-ttu-id="861ca-108">未启用对尾部分隔符的处理。</span><span class="sxs-lookup"><span data-stu-id="861ca-108">Processing of trailing separators is not enabled.</span></span>  
  
 <span data-ttu-id="861ca-109">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="861ca-109">**Resolution**</span></span>  
  
 <span data-ttu-id="861ca-110">打开发送消息的参与方的“EDI 属性”。</span><span class="sxs-lookup"><span data-stu-id="861ca-110">Open the EDI Properties for the party that sent the message.</span></span> <span data-ttu-id="861ca-111">在“EDI 属性”对话框（对于 X12 或 EDIFACT）的“验证和确认生成”页中，选中“允许尾部分隔符”。</span><span class="sxs-lookup"><span data-stu-id="861ca-111">In the Validation and ACK Generation page of the EDI Properties dialog box (for either X12 or EDIFACT), select "Allow trailing delimiter/separators".</span></span> <span data-ttu-id="861ca-112">单击此复选框后，可以通过单击“为尾部分隔符创建空 XML 标记”来指定在中间 XML 中为尾部分隔符创建空的 XML 标记。</span><span class="sxs-lookup"><span data-stu-id="861ca-112">After clicking this checkbox, you can specify that empty XML tags are created for trailing separators in the intermediate XML by clicking "Create empty XML tags for trailing separators".</span></span>  
  
## <a name="contrl-ack-is-enabled-but-not-generated"></a><span data-ttu-id="861ca-113">CONTRL 确认已启用，但未生成</span><span class="sxs-lookup"><span data-stu-id="861ca-113">CONTRL ACK is enabled, but not generated</span></span>  
 <span data-ttu-id="861ca-114">**症状**</span><span class="sxs-lookup"><span data-stu-id="861ca-114">**Symptom**</span></span>  
  
 <span data-ttu-id="861ca-115">在发送方的“验证和确认生成”中已选中“生成功能确认”复选框，但 EDI 接收管道尚未生成 CONTRL 确认。</span><span class="sxs-lookup"><span data-stu-id="861ca-115">The Generate Functional ACK checkbox in the Validation and ACK Generation for the sending party is checked, but the EDI receive pipeline has not generated a CONTRL acknowledgment.</span></span>  
  
 <span data-ttu-id="861ca-116">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="861ca-116">**Possible Cause**</span></span>  
  
 <span data-ttu-id="861ca-117">CONTRL 消息包含几个必须从交换复制的必需数据元素。</span><span class="sxs-lookup"><span data-stu-id="861ca-117">The CONTRL message contains several mandatory data elements that must be copied from the interchange.</span></span> <span data-ttu-id="861ca-118">如果交换中的数据元素丢失或在语法上无效，则接收管道无法生成在语法上有效的 CONTRL 消息。</span><span class="sxs-lookup"><span data-stu-id="861ca-118">If the data element in the interchange is missing or is syntactically invalid, the receive pipeline cannot generate a syntactically valid CONTRL message.</span></span>  
  
 <span data-ttu-id="861ca-119">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="861ca-119">**Resolution**</span></span>  
  
 <span data-ttu-id="861ca-120">通过 CONTRL 确认以外的其他某种方式来报告错误情况。</span><span class="sxs-lookup"><span data-stu-id="861ca-120">Report the error condition by some other means than a CONTRL acknowledgment.</span></span>  
  
## <a name="there-was-a-failure-executing-the-receive-pipeline-error-message"></a><span data-ttu-id="861ca-121">"出现故障执行接收管道..."</span><span class="sxs-lookup"><span data-stu-id="861ca-121">"There Was a Failure Executing the Receive Pipeline…"</span></span> <span data-ttu-id="861ca-122">错误消息</span><span class="sxs-lookup"><span data-stu-id="861ca-122">Error Message</span></span>  
 <span data-ttu-id="861ca-123">**症状**</span><span class="sxs-lookup"><span data-stu-id="861ca-123">**Symptom**</span></span>  
  
 <span data-ttu-id="861ca-124">尝试运行 AS2 接收管道时导致出现 80040154 错误。</span><span class="sxs-lookup"><span data-stu-id="861ca-124">Attempting to run an AS2 receive pipeline results in an 80040154 error.</span></span>  
  
 <span data-ttu-id="861ca-125">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="861ca-125">**Possible Cause**</span></span>  
  
 <span data-ttu-id="861ca-126">在 64 位主机实例上不支持使用管道。</span><span class="sxs-lookup"><span data-stu-id="861ca-126">Pipelines are not supported on 64-bit host instances.</span></span>  
  
 <span data-ttu-id="861ca-127">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="861ca-127">**Resolution**</span></span>  
  
 <span data-ttu-id="861ca-128">将相应管道与 32 位主机关联。</span><span class="sxs-lookup"><span data-stu-id="861ca-128">Associate the pipeline with a 32-bit host.</span></span>  
  
## <a name="an-x12-encoded-message-is-suspended-if-port-based-authentication-is-enabled-and-biztalk-server-does-not-have-access-to-the-authorization-and-security-information"></a><span data-ttu-id="861ca-129">如果已启用基于端口的身份验证而 BizTalk Server 却无权访问授权和安全信息，X12 编码的消息将挂起</span><span class="sxs-lookup"><span data-stu-id="861ca-129">An X12-Encoded Message Is Suspended If Port-Based Authentication Is Enabled and BizTalk Server Does Not Have Access to the Authorization and Security Information</span></span>  
 <span data-ttu-id="861ca-130">**症状**</span><span class="sxs-lookup"><span data-stu-id="861ca-130">**Symptom**</span></span>  
  
 <span data-ttu-id="861ca-131">如果某消息是通过已启用身份验证的接收端口接收的，而又无法确定发送该消息的参与方，BizTalk Server 将挂起该消息。</span><span class="sxs-lookup"><span data-stu-id="861ca-131">When a message is received over a receive port for which authentication is enabled, and the party that sent the message cannot be determined, BizTalk Server will suspend the message.</span></span>  
  
 <span data-ttu-id="861ca-132">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="861ca-132">**Possible Cause**</span></span>  
  
 <span data-ttu-id="861ca-133">如果已为某接收端口启用了身份验证（清除了该接收端口的“无验证”属性），则 BizTalk Server 需要获得“ISA1-2 (授权限定符和信息)”和“ISA3-4 (安全限定符和信息)”属性的设置才能处理相应的交换。</span><span class="sxs-lookup"><span data-stu-id="861ca-133">If authentication is enabled for a receive port (the "No Authentication" property for the receive port is cleared), BizTalk Server requires settings for the "ISA1-2 (Authorization qualifier and information)" and "ISA3-4 (Security qualifier and information)" properties in order to process the interchange.</span></span> <span data-ttu-id="861ca-134">这些属性是在作为交换发送方的参与方的“X12 交换处理属性”页为相应参与方设置的。</span><span class="sxs-lookup"><span data-stu-id="861ca-134">These properties are set for a party in the X12 Interchange Processing Properties page for the party as an interchange sender.</span></span> <span data-ttu-id="861ca-135">如果 BizTalk Server 不能确定这些属性的值，它将挂起相应消息。</span><span class="sxs-lookup"><span data-stu-id="861ca-135">If BizTalk Server cannot determine the values of these properties, it will suspend the message.</span></span>  
  
 <span data-ttu-id="861ca-136">这一问题分为两种情况：</span><span class="sxs-lookup"><span data-stu-id="861ca-136">This can occur in two ways.</span></span> <span data-ttu-id="861ca-137">第一种情况，如果 BizTalk Server 无法确定发送相应消息的参与方，它将使用 EDI 全局属性，并且将无权访问授权和安全设置。</span><span class="sxs-lookup"><span data-stu-id="861ca-137">In the first case, if BizTalk Server cannot determine the party that sent the message, it will use the EDI global properties and will not have access to the authorization and security settings.</span></span> <span data-ttu-id="861ca-138">因此，它将挂起该消息。</span><span class="sxs-lookup"><span data-stu-id="861ca-138">As a result, it will suspend the message.</span></span> <span data-ttu-id="861ca-139">第二种情况，如果 BizTalk Server 已确定了相应的参与方，但是该参与方的 ISA1-2 和 ISA3-4 属性并没有进行配置，则 BizTalk Server 也无权访问授权和安全信息，因而将挂起相应消息。</span><span class="sxs-lookup"><span data-stu-id="861ca-139">In the second case, if BizTalk Server determines the party, but the ISA1-2 and ISA3-4 properties for the party are not configured, BizTalk Server will again not have access to authorization and security information and will suspend the message.</span></span>  
  
 <span data-ttu-id="861ca-140">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="861ca-140">**Resolution**</span></span>  
  
 <span data-ttu-id="861ca-141">确保可以识别发送消息的参与方，且已在参与方协议中定义 ISA1-2 和 ISA3-4 属性。</span><span class="sxs-lookup"><span data-stu-id="861ca-141">Make sure that the sending party for the message can be identified and that the ISA1-2 and ISA3-4 properties are defined in the party agreement.</span></span>  
  
## <a name="incorrect-se01-in-a-split-hipaa-subdocument"></a><span data-ttu-id="861ca-142">拆分 HIPAA 子文档中的 SE01 不正确</span><span class="sxs-lookup"><span data-stu-id="861ca-142">Incorrect SE01 in a split HIPAA subdocument</span></span>  
 <span data-ttu-id="861ca-143">**症状**</span><span class="sxs-lookup"><span data-stu-id="861ca-143">**Symptom**</span></span>  
  
 <span data-ttu-id="861ca-144">事务集尾部（SE01 字段）提供数据段的计数，包括 X12/HIPAA 文档的标头和尾部段。</span><span class="sxs-lookup"><span data-stu-id="861ca-144">The transaction set trailer (SE01 field) provides a count of the data segments, including the header and trailer segments of an X12/HIPAA document.</span></span> <span data-ttu-id="861ca-145">但对于拆分的 HIPAA 子文档，EDI 接收管道与原始文档应用相同的 SE01 值，而不是重新计算该值。</span><span class="sxs-lookup"><span data-stu-id="861ca-145">However, for a split HIPAA sub document, the EDI receive pipeline applies the same SE01 value as the original document, instead of re-computing it.</span></span>  
  
 <span data-ttu-id="861ca-146">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="861ca-146">**Cause**</span></span>  
  
 <span data-ttu-id="861ca-147">EDI 接收管道将 SE01 的值从原始 HIPAA 文档复制到拆分的子文档。</span><span class="sxs-lookup"><span data-stu-id="861ca-147">The EDI receive pipeline copies the value of SE01 from the original HIPAA document to a split sub document.</span></span>  
  
## <a name="error-message-for-duplicate-unb5-or-unh1-is-not-descriptive"></a><span data-ttu-id="861ca-148">有关 UNB5 或 UNH1 重复的错误消息描述不清</span><span class="sxs-lookup"><span data-stu-id="861ca-148">Error Message for Duplicate UNB5 or UNH1 Is Not Descriptive</span></span>  
 <span data-ttu-id="861ca-149">如果 BizTalk Server 收到有关 UNB5（交换控制编号）或 UNH1（事务集参考编号）重复的消息，则它布的错误代码和说明将不能清楚地说明问题的性质。</span><span class="sxs-lookup"><span data-stu-id="861ca-149">If BizTalk Server receives a message that has a duplicate UNB5 (interchange control number) or UNH1 (transaction set reference number), the error code and description that it posts will not clearly indicate the nature of the problem.</span></span>  
  
## <a name="biztalk-server-will-suspend-a-very-large-interchange-if-it-runs-out-of-memory"></a><span data-ttu-id="861ca-150">如果内存不足，BizTalk Server 将挂起非常大的交换</span><span class="sxs-lookup"><span data-stu-id="861ca-150">BizTalk Server Will Suspend a Very Large Interchange If It Runs Out of Memory</span></span>  
 <span data-ttu-id="861ca-151">BizTalk Server 在分析非常大的交换时可能会导致内存不足。</span><span class="sxs-lookup"><span data-stu-id="861ca-151">BizTalk Server may run out of memory when it parses a very large interchange.</span></span> <span data-ttu-id="861ca-152">如果出现这种情况，它将发布出错信息并挂起相应交换。</span><span class="sxs-lookup"><span data-stu-id="861ca-152">If it does, it will post an error and suspend the interchange.</span></span> <span data-ttu-id="861ca-153">在“组中心”页中，您将无法看到已挂起的特大交换的所有内容。</span><span class="sxs-lookup"><span data-stu-id="861ca-153">In the Group Hub page, you will not be able to see all of the contents of a very large interchange that has been suspended.</span></span> <span data-ttu-id="861ca-154">你将能够看到的消息，初始一部分但 BizTalk Server 是从它可以显示挂起交换的数据量的限制。</span><span class="sxs-lookup"><span data-stu-id="861ca-154">You will be able to see the initial part of the message, but BizTalk Server is limited in the amount of data from a suspended interchange that it can display.</span></span>  
  
## <a name="korean-characters-added-to-an-enumeration-in-a-kedifact-schema-must-be-in-unicode"></a><span data-ttu-id="861ca-155">向 KEDIFACT 架构中的枚举添加的韩语字符必须为 UNICODE 格式</span><span class="sxs-lookup"><span data-stu-id="861ca-155">Korean Characters Added to an Enumeration in a KEDIFACT Schema Must Be in UNICODE</span></span>  
 <span data-ttu-id="861ca-156">当 BizTalk Server 收到包含韩语字符的 KEDIFACT 编码的交换时，它将使用 UNB2 字段中的代码页/字符集值来处理相应交换。</span><span class="sxs-lookup"><span data-stu-id="861ca-156">When BizTalk Server receives a KEDIFACT-encoded interchange with Korean characters, it will use the code page/character set value in the UNB2 field to process the interchange.</span></span> <span data-ttu-id="861ca-157">但是，如果您通过向枚举添加具有 ID 数据类型的韩语字符来修改 KEDIFACT 架构，则必须按照架构顶部指定的那样以 UTF-16 UNICODE 格式添加相应值。</span><span class="sxs-lookup"><span data-stu-id="861ca-157">However, if you modify a KEDIFACT schema by adding a Korean character with an ID data type to an enumeration, you must add the value in UTF-16 UNICODE, as specified at the top of the schema.</span></span>  
  
## <a name="executing-an-edi-receive-pipeline-from-within-an-orchestration-is-not-supported"></a><span data-ttu-id="861ca-158">不支持从业务流程内部执行 EDI 接收管道</span><span class="sxs-lookup"><span data-stu-id="861ca-158">Executing an EDI Receive Pipeline from within an Orchestration Is Not Supported</span></span>  
 <span data-ttu-id="861ca-159">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，您通常可以执行业务流程的表达式形状中的接收管道。</span><span class="sxs-lookup"><span data-stu-id="861ca-159">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can typically execute receive pipelines within an Expression shape in an orchestration.</span></span> <span data-ttu-id="861ca-160">尚未针对 EDIReceive 管道或 AS2EdiReceive 管道测试此功能，因此不支持此功能。</span><span class="sxs-lookup"><span data-stu-id="861ca-160">This functionality has not been tested for the EDIReceive pipeline or the AS2EdiReceive pipeline, so is not supported.</span></span>  
  
## <a name="biztalk-edi-application-must-not-be-modified"></a><span data-ttu-id="861ca-161">不得修改 BizTalk EDI 应用程序</span><span class="sxs-lookup"><span data-stu-id="861ca-161">BizTalk EDI Application Must Not Be Modified</span></span>  
 <span data-ttu-id="861ca-162">不得修改或删除 BizTalk EDI 应用程序中的项目。</span><span class="sxs-lookup"><span data-stu-id="861ca-162">Artifacts in the BizTalk EDI Application must not be modified or deleted.</span></span> <span data-ttu-id="861ca-163">如果修改了此应用程序，则您将无法通过取消配置和重新配置 EDI 及 AS2 功能来恢复原始应用程序。</span><span class="sxs-lookup"><span data-stu-id="861ca-163">If this application is modified, there is no way for you to revert to the original application by unconfiguring and reconfiguring the EDI and AS2 features.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="861ca-164">另请参阅</span><span class="sxs-lookup"><span data-stu-id="861ca-164">See Also</span></span>  
 <span data-ttu-id="861ca-165">[EDI 处理的已知的问题](../core/known-issues-with-edi-processing.md) </span><span class="sxs-lookup"><span data-stu-id="861ca-165">[Known Issues with EDI Processing](../core/known-issues-with-edi-processing.md) </span></span>  
 <span data-ttu-id="861ca-166">[BizTalk Server 接收 EDI 消息的方式](../core/how-biztalk-server-receives-edi-messages.md) </span><span class="sxs-lookup"><span data-stu-id="861ca-166">[How BizTalk Server Receives EDI Messages](../core/how-biztalk-server-receives-edi-messages.md) </span></span>  
 [<span data-ttu-id="861ca-167">演练 (X12)： 接收 EDI 交换和发送回确认</span><span class="sxs-lookup"><span data-stu-id="861ca-167">Walkthrough (X12): Receiving EDI Interchanges and Sending Back an Acknowledgement</span></span>](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md)