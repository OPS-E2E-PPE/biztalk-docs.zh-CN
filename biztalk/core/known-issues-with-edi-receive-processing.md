---
title: 已知问题的 EDI 接收处理 |Microsoft Docs
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
ms.openlocfilehash: 734a093a554f01b8625d8cd1ba8f154153d33979
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330238"
---
# <a name="known-issues-with-edi-receive-processing"></a><span data-ttu-id="b1ab8-102">接收处理的 EDI 的已知的问题</span><span class="sxs-lookup"><span data-stu-id="b1ab8-102">Known Issues with EDI Receive Processing</span></span>
<span data-ttu-id="b1ab8-103">本主题介绍了处理的已知的问题在 EDI 接收管道。</span><span class="sxs-lookup"><span data-stu-id="b1ab8-103">This topic describes known issues with processing in the EDI receive pipeline.</span></span>  
  
## <a name="receive-side-processing-of-trailing-separators-fails"></a><span data-ttu-id="b1ab8-104">尾部分隔符的接收方处理失败</span><span class="sxs-lookup"><span data-stu-id="b1ab8-104">Receive-Side Processing of Trailing Separators Fails</span></span>  
 <span data-ttu-id="b1ab8-105">**症状**</span><span class="sxs-lookup"><span data-stu-id="b1ab8-105">**Symptom**</span></span>  
  
 <span data-ttu-id="b1ab8-106">设置带有尾部分隔符的事务失败，错误代码为 AK403 = 6 的 X12 编码的消息或错误代码 UCM3 = 4/UCD1 = 45 对于 EDIFACT 编码的消息。</span><span class="sxs-lookup"><span data-stu-id="b1ab8-106">A transaction set with a trailing separator fails with error code AK403= 6 for an X12-encoded message or error codes UCM3=4/UCD1=45 for an EDIFACT-encoded message.</span></span>  
  
 <span data-ttu-id="b1ab8-107">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="b1ab8-107">**Possible Cause**</span></span>  
  
 <span data-ttu-id="b1ab8-108">未启用尾部分隔符的处理。</span><span class="sxs-lookup"><span data-stu-id="b1ab8-108">Processing of trailing separators is not enabled.</span></span>  
  
 <span data-ttu-id="b1ab8-109">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="b1ab8-109">**Resolution**</span></span>  
  
 <span data-ttu-id="b1ab8-110">打开发送消息的参与方 EDI 属性。</span><span class="sxs-lookup"><span data-stu-id="b1ab8-110">Open the EDI Properties for the party that sent the message.</span></span> <span data-ttu-id="b1ab8-111">在 EDI 属性对话框中 （对于 X12 或 EDIFACT） 的验证和确认生成页中，选择"允许尾部分隔符"。</span><span class="sxs-lookup"><span data-stu-id="b1ab8-111">In the Validation and ACK Generation page of the EDI Properties dialog box (for either X12 or EDIFACT), select "Allow trailing delimiter/separators".</span></span> <span data-ttu-id="b1ab8-112">单击此复选框之后, 可以指定为尾部分隔符的中间 XML 中通过单击"创建为尾部分隔符的空 XML 标记"已创建空 XML 标记。</span><span class="sxs-lookup"><span data-stu-id="b1ab8-112">After clicking this checkbox, you can specify that empty XML tags are created for trailing separators in the intermediate XML by clicking "Create empty XML tags for trailing separators".</span></span>  
  
## <a name="contrl-ack-is-enabled-but-not-generated"></a><span data-ttu-id="b1ab8-113">已启用，但不是会生成 CONTRL 确认</span><span class="sxs-lookup"><span data-stu-id="b1ab8-113">CONTRL ACK is enabled, but not generated</span></span>  
 <span data-ttu-id="b1ab8-114">**症状**</span><span class="sxs-lookup"><span data-stu-id="b1ab8-114">**Symptom**</span></span>  
  
 <span data-ttu-id="b1ab8-115">验证和确认生成中的生成功能确认复选框处于选中状态发送参与方，但 EDI 接收管道尚未生成 CONTRL 确认。</span><span class="sxs-lookup"><span data-stu-id="b1ab8-115">The Generate Functional ACK checkbox in the Validation and ACK Generation for the sending party is checked, but the EDI receive pipeline has not generated a CONTRL acknowledgment.</span></span>  
  
 <span data-ttu-id="b1ab8-116">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="b1ab8-116">**Possible Cause**</span></span>  
  
 <span data-ttu-id="b1ab8-117">CONTRL 消息包含几个必需的数据元素，必须从交换复制。</span><span class="sxs-lookup"><span data-stu-id="b1ab8-117">The CONTRL message contains several mandatory data elements that must be copied from the interchange.</span></span> <span data-ttu-id="b1ab8-118">如果交换中的数据元素缺失或在语法上无效，则接收管道无法生成语法上有效的 CONTRL 消息。</span><span class="sxs-lookup"><span data-stu-id="b1ab8-118">If the data element in the interchange is missing or is syntactically invalid, the receive pipeline cannot generate a syntactically valid CONTRL message.</span></span>  
  
 <span data-ttu-id="b1ab8-119">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="b1ab8-119">**Resolution**</span></span>  
  
 <span data-ttu-id="b1ab8-120">CONTRL 确认以外的其他某种方法报告错误条件。</span><span class="sxs-lookup"><span data-stu-id="b1ab8-120">Report the error condition by some other means than a CONTRL acknowledgment.</span></span>  
  
## <a name="there-was-a-failure-executing-the-receive-pipeline-error-message"></a><span data-ttu-id="b1ab8-121">"出现执行接收管道..."错误消息</span><span class="sxs-lookup"><span data-stu-id="b1ab8-121">"There Was a Failure Executing the Receive Pipeline…" Error Message</span></span>  
 <span data-ttu-id="b1ab8-122">**症状**</span><span class="sxs-lookup"><span data-stu-id="b1ab8-122">**Symptom**</span></span>  
  
 <span data-ttu-id="b1ab8-123">尝试运行 AS2 接收管道结果导致出现 80040154 错误。</span><span class="sxs-lookup"><span data-stu-id="b1ab8-123">Attempting to run an AS2 receive pipeline results in an 80040154 error.</span></span>  
  
 <span data-ttu-id="b1ab8-124">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="b1ab8-124">**Possible Cause**</span></span>  
  
 <span data-ttu-id="b1ab8-125">管道不支持在 64 位主机实例上。</span><span class="sxs-lookup"><span data-stu-id="b1ab8-125">Pipelines are not supported on 64-bit host instances.</span></span>  
  
 <span data-ttu-id="b1ab8-126">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="b1ab8-126">**Resolution**</span></span>  
  
 <span data-ttu-id="b1ab8-127">将管道与 32 位主机相关联。</span><span class="sxs-lookup"><span data-stu-id="b1ab8-127">Associate the pipeline with a 32-bit host.</span></span>  
  
## <a name="an-x12-encoded-message-is-suspended-if-port-based-authentication-is-enabled-and-biztalk-server-does-not-have-access-to-the-authorization-and-security-information"></a><span data-ttu-id="b1ab8-128">如果启用了基于端口的身份验证，并且 BizTalk Server 不具有访问授权和安全信息的 X12 编码消息被挂起</span><span class="sxs-lookup"><span data-stu-id="b1ab8-128">An X12-Encoded Message Is Suspended If Port-Based Authentication Is Enabled and BizTalk Server Does Not Have Access to the Authorization and Security Information</span></span>  
 <span data-ttu-id="b1ab8-129">**症状**</span><span class="sxs-lookup"><span data-stu-id="b1ab8-129">**Symptom**</span></span>  
  
 <span data-ttu-id="b1ab8-130">通过用于已启用的身份验证，并发送不能确定该消息的参与方的接收端口收到一条消息时，BizTalk Server 将挂起该消息。</span><span class="sxs-lookup"><span data-stu-id="b1ab8-130">When a message is received over a receive port for which authentication is enabled, and the party that sent the message cannot be determined, BizTalk Server will suspend the message.</span></span>  
  
 <span data-ttu-id="b1ab8-131">**可能的原因**</span><span class="sxs-lookup"><span data-stu-id="b1ab8-131">**Possible Cause**</span></span>  
  
 <span data-ttu-id="b1ab8-132">BizTalk Server 的接收端口 （接收端口的"无身份验证"属性被清除） 启用身份验证，如果需要设置为"ISA1-2 （授权限定符和信息）"和"ISA3-4 （安全限定符和信息）"若要处理的交换的属性。</span><span class="sxs-lookup"><span data-stu-id="b1ab8-132">If authentication is enabled for a receive port (the "No Authentication" property for the receive port is cleared), BizTalk Server requires settings for the "ISA1-2 (Authorization qualifier and information)" and "ISA3-4 (Security qualifier and information)" properties in order to process the interchange.</span></span> <span data-ttu-id="b1ab8-133">这些属性设置为 X12 中的参与方作为交换发送方的参与方的交换处理属性页。</span><span class="sxs-lookup"><span data-stu-id="b1ab8-133">These properties are set for a party in the X12 Interchange Processing Properties page for the party as an interchange sender.</span></span> <span data-ttu-id="b1ab8-134">如果 BizTalk Server 无法确定这些属性的值，它将挂起该消息。</span><span class="sxs-lookup"><span data-stu-id="b1ab8-134">If BizTalk Server cannot determine the values of these properties, it will suspend the message.</span></span>  
  
 <span data-ttu-id="b1ab8-135">这可能通过两种方式。</span><span class="sxs-lookup"><span data-stu-id="b1ab8-135">This can occur in two ways.</span></span> <span data-ttu-id="b1ab8-136">在第一种情况下，如果 BizTalk Server 无法确定参与方发送消息，它将使用 EDI 全局属性并不会访问授权和安全设置。</span><span class="sxs-lookup"><span data-stu-id="b1ab8-136">In the first case, if BizTalk Server cannot determine the party that sent the message, it will use the EDI global properties and will not have access to the authorization and security settings.</span></span> <span data-ttu-id="b1ab8-137">因此，它将挂起该消息。</span><span class="sxs-lookup"><span data-stu-id="b1ab8-137">As a result, it will suspend the message.</span></span> <span data-ttu-id="b1ab8-138">在第二种情况下，如果 BizTalk Server 确定参与方，但未配置的参与方 ISA1-2 和 ISA3-4 属性，BizTalk Server 也无权访问授权和安全信息并将挂起该消息。</span><span class="sxs-lookup"><span data-stu-id="b1ab8-138">In the second case, if BizTalk Server determines the party, but the ISA1-2 and ISA3-4 properties for the party are not configured, BizTalk Server will again not have access to authorization and security information and will suspend the message.</span></span>  
  
 <span data-ttu-id="b1ab8-139">**解决方法**</span><span class="sxs-lookup"><span data-stu-id="b1ab8-139">**Resolution**</span></span>  
  
 <span data-ttu-id="b1ab8-140">请确保可以识别的消息发送方和 ISA1-2 和 ISA3-4 属性参与方协议中定义。</span><span class="sxs-lookup"><span data-stu-id="b1ab8-140">Make sure that the sending party for the message can be identified and that the ISA1-2 and ISA3-4 properties are defined in the party agreement.</span></span>  
  
## <a name="incorrect-se01-in-a-split-hipaa-subdocument"></a><span data-ttu-id="b1ab8-141">拆分 HIPAA 子文档中的 SE01 不正确</span><span class="sxs-lookup"><span data-stu-id="b1ab8-141">Incorrect SE01 in a split HIPAA subdocument</span></span>  
 <span data-ttu-id="b1ab8-142">**症状**</span><span class="sxs-lookup"><span data-stu-id="b1ab8-142">**Symptom**</span></span>  
  
 <span data-ttu-id="b1ab8-143">事务集尾部 （SE01 字段） 提供的数据段，其中包括 X12/HIPAA 文档的标头和尾部段的计数。</span><span class="sxs-lookup"><span data-stu-id="b1ab8-143">The transaction set trailer (SE01 field) provides a count of the data segments, including the header and trailer segments of an X12/HIPAA document.</span></span> <span data-ttu-id="b1ab8-144">但是，对于拆分的 HIPAA 子文档，EDI 接收管道会应用相同的 SE01 值与原始文档，而不是重新对其进行计算。</span><span class="sxs-lookup"><span data-stu-id="b1ab8-144">However, for a split HIPAA sub document, the EDI receive pipeline applies the same SE01 value as the original document, instead of re-computing it.</span></span>  
  
 <span data-ttu-id="b1ab8-145">**原因**</span><span class="sxs-lookup"><span data-stu-id="b1ab8-145">**Cause**</span></span>  
  
 <span data-ttu-id="b1ab8-146">EDI 接收管道将 SE01 的值从原始 HIPAA 文档到拆分的子文档。</span><span class="sxs-lookup"><span data-stu-id="b1ab8-146">The EDI receive pipeline copies the value of SE01 from the original HIPAA document to a split sub document.</span></span>  
  
## <a name="error-message-for-duplicate-unb5-or-unh1-is-not-descriptive"></a><span data-ttu-id="b1ab8-147">有关 UNB5 或 UNH1 重复的错误消息不是描述性</span><span class="sxs-lookup"><span data-stu-id="b1ab8-147">Error Message for Duplicate UNB5 or UNH1 Is Not Descriptive</span></span>  
 <span data-ttu-id="b1ab8-148">如果 BizTalk Server 接收一条消息，具有重复的 UNB5 （交换控制编号） 或 UNH1 （事务集参考编号）、 错误代码和描述，它将发布将不清楚地指明问题的性质。</span><span class="sxs-lookup"><span data-stu-id="b1ab8-148">If BizTalk Server receives a message that has a duplicate UNB5 (interchange control number) or UNH1 (transaction set reference number), the error code and description that it posts will not clearly indicate the nature of the problem.</span></span>  
  
## <a name="biztalk-server-will-suspend-a-very-large-interchange-if-it-runs-out-of-memory"></a><span data-ttu-id="b1ab8-149">如果内存不足，BizTalk Server 将挂起非常大的交换</span><span class="sxs-lookup"><span data-stu-id="b1ab8-149">BizTalk Server Will Suspend a Very Large Interchange If It Runs Out of Memory</span></span>  
 <span data-ttu-id="b1ab8-150">分析非常大的交换时，BizTalk Server 可能会耗尽内存。</span><span class="sxs-lookup"><span data-stu-id="b1ab8-150">BizTalk Server may run out of memory when it parses a very large interchange.</span></span> <span data-ttu-id="b1ab8-151">如果是这样，它将发布错误并挂起该交换。</span><span class="sxs-lookup"><span data-stu-id="b1ab8-151">If it does, it will post an error and suspend the interchange.</span></span> <span data-ttu-id="b1ab8-152">在组中心页中，您将无法再以查看所有已挂起的特大交换的内容。</span><span class="sxs-lookup"><span data-stu-id="b1ab8-152">In the Group Hub page, you will not be able to see all of the contents of a very large interchange that has been suspended.</span></span> <span data-ttu-id="b1ab8-153">你将能够看到初始消息的一部分，但 BizTalk Server 是已挂起的交换，它可以显示的数据量的限制。</span><span class="sxs-lookup"><span data-stu-id="b1ab8-153">You will be able to see the initial part of the message, but BizTalk Server is limited in the amount of data from a suspended interchange that it can display.</span></span>  
  
## <a name="korean-characters-added-to-an-enumeration-in-a-kedifact-schema-must-be-in-unicode"></a><span data-ttu-id="b1ab8-154">KEDIFACT 架构中的枚举添加的韩语字符必须为 unicode 格式</span><span class="sxs-lookup"><span data-stu-id="b1ab8-154">Korean Characters Added to an Enumeration in a KEDIFACT Schema Must Be in UNICODE</span></span>  
 <span data-ttu-id="b1ab8-155">当 BizTalk Server 收到包含韩语字符 KEDIFACT 编码的交换时，它将使用 UNB2 字段中的代码页/字符集值来处理交换。</span><span class="sxs-lookup"><span data-stu-id="b1ab8-155">When BizTalk Server receives a KEDIFACT-encoded interchange with Korean characters, it will use the code page/character set value in the UNB2 field to process the interchange.</span></span> <span data-ttu-id="b1ab8-156">但是，如果您通过枚举具有 ID 数据类型添加的韩语字符来修改 KEDIFACT 架构，您必须添加值 utf-16 UNICODE，为指定的架构的顶部。</span><span class="sxs-lookup"><span data-stu-id="b1ab8-156">However, if you modify a KEDIFACT schema by adding a Korean character with an ID data type to an enumeration, you must add the value in UTF-16 UNICODE, as specified at the top of the schema.</span></span>  
  
## <a name="executing-an-edi-receive-pipeline-from-within-an-orchestration-is-not-supported"></a><span data-ttu-id="b1ab8-157">执行 EDI 接收管道在业务流程不支持</span><span class="sxs-lookup"><span data-stu-id="b1ab8-157">Executing an EDI Receive Pipeline from within an Orchestration Is Not Supported</span></span>  
 <span data-ttu-id="b1ab8-158">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，您通常可以执行接收管道的表达式形状中业务流程。</span><span class="sxs-lookup"><span data-stu-id="b1ab8-158">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can typically execute receive pipelines within an Expression shape in an orchestration.</span></span> <span data-ttu-id="b1ab8-159">尚未针对 EDIReceive 管道或 AS2EdiReceive 管道，因此不支持测试此功能。</span><span class="sxs-lookup"><span data-stu-id="b1ab8-159">This functionality has not been tested for the EDIReceive pipeline or the AS2EdiReceive pipeline, so is not supported.</span></span>  
  
## <a name="biztalk-edi-application-must-not-be-modified"></a><span data-ttu-id="b1ab8-160">不得修改 BizTalk EDI 应用程序</span><span class="sxs-lookup"><span data-stu-id="b1ab8-160">BizTalk EDI Application Must Not Be Modified</span></span>  
 <span data-ttu-id="b1ab8-161">不得修改或删除 BizTalk EDI 应用程序中的项目。</span><span class="sxs-lookup"><span data-stu-id="b1ab8-161">Artifacts in the BizTalk EDI Application must not be modified or deleted.</span></span> <span data-ttu-id="b1ab8-162">如果修改此应用程序，则没有办法可以恢复到原始应用程序通过取消配置和重新配置 EDI 和 AS2 功能。</span><span class="sxs-lookup"><span data-stu-id="b1ab8-162">If this application is modified, there is no way for you to revert to the original application by unconfiguring and reconfiguring the EDI and AS2 features.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1ab8-163">请参阅</span><span class="sxs-lookup"><span data-stu-id="b1ab8-163">See Also</span></span>  
 <span data-ttu-id="b1ab8-164">[EDI 处理的已知的问题](../core/known-issues-with-edi-processing.md) </span><span class="sxs-lookup"><span data-stu-id="b1ab8-164">[Known Issues with EDI Processing](../core/known-issues-with-edi-processing.md) </span></span>  
 <span data-ttu-id="b1ab8-165">[BizTalk Server 如何接收 EDI 消息](../core/how-biztalk-server-receives-edi-messages.md) </span><span class="sxs-lookup"><span data-stu-id="b1ab8-165">[How BizTalk Server Receives EDI Messages](../core/how-biztalk-server-receives-edi-messages.md) </span></span>  
 [<span data-ttu-id="b1ab8-166">演练 (X12):接收 EDI 交换并发送回确认</span><span class="sxs-lookup"><span data-stu-id="b1ab8-166">Walkthrough (X12): Receiving EDI Interchanges and Sending Back an Acknowledgement</span></span>](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md)