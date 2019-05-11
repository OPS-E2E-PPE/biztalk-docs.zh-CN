---
title: AS2 接收组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bdab87fd-15b9-4e3c-a4d7-984693262293
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c64053bbfc818cd2c345e6a2e2268328c3b6b99a
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528565"
---
# <a name="as2-receive-components"></a><span data-ttu-id="f5b32-102">AS2 接收组件</span><span class="sxs-lookup"><span data-stu-id="f5b32-102">AS2 Receive Components</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="f5b32-103">使用多个组件来接收 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="f5b32-103">uses several components to receive AS2 messages.</span></span>  
  
## <a name="as2-receive-pipelines"></a><span data-ttu-id="f5b32-104">AS2 接收管道</span><span class="sxs-lookup"><span data-stu-id="f5b32-104">AS2 Receive Pipelines</span></span>  
 <span data-ttu-id="f5b32-105">大部分 AS2 接收处理工作都在下面的示例 AS2 接收管道。</span><span class="sxs-lookup"><span data-stu-id="f5b32-105">Most AS2 receive processing is performed in the following AS2 receive pipelines.</span></span> <span data-ttu-id="f5b32-106">这些管道安装在`Microsoft.BizTalk.EdiInt.PipelineComponents.dll`\Program Files\Microsoft BizTalk Server 20xx\Pipeline Components 中\\。</span><span class="sxs-lookup"><span data-stu-id="f5b32-106">These pipelines are installed in `Microsoft.BizTalk.EdiInt.PipelineComponents.dll` in \Program Files\Microsoft BizTalk Server 20xx\Pipeline Components\\.</span></span>  
  
 <span data-ttu-id="f5b32-107">**AS2EdiReceive 管道**</span><span class="sxs-lookup"><span data-stu-id="f5b32-107">**AS2EdiReceive Pipeline**</span></span>  
  
 <span data-ttu-id="f5b32-108">此管道处理接收的 EDI 消息通过 AS2，包括 Mdn。</span><span class="sxs-lookup"><span data-stu-id="f5b32-108">This pipeline processes EDI messages received over AS2, including MDNs.</span></span> <span data-ttu-id="f5b32-109">管道由以下管道组件组成：</span><span class="sxs-lookup"><span data-stu-id="f5b32-109">The pipeline consists of the following pipeline components:</span></span>  
  
- <span data-ttu-id="f5b32-110">AS2 解码器</span><span class="sxs-lookup"><span data-stu-id="f5b32-110">AS2 Decoder</span></span>  
  
- <span data-ttu-id="f5b32-111">EDI 拆装器</span><span class="sxs-lookup"><span data-stu-id="f5b32-111">EDI Disassembler</span></span>  
  
- <span data-ttu-id="f5b32-112">BatchMarker。</span><span class="sxs-lookup"><span data-stu-id="f5b32-112">BatchMarker.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="f5b32-113">使用 AS2EdiReceive 管道时，必须添加到 BizTalk Application Users 组运行 BizTalk 独立主机实例进程的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="f5b32-113">When using the AS2EdiReceive pipeline, you must add the user account that the BizTalk Isolated Host Instance process is running under to the BizTalk Application Users group.</span></span> <span data-ttu-id="f5b32-114">AS2EdiReceive 管道在 BizTalk 独立主机实例进程中执行。</span><span class="sxs-lookup"><span data-stu-id="f5b32-114">The AS2EdiReceive pipeline executes in the BizTalk Isolated Host Instance process.</span></span> <span data-ttu-id="f5b32-115">AS2EdiReceive 管道会访问 SSO 存储区，这要求用户属于 BizTalk Application Users 组。</span><span class="sxs-lookup"><span data-stu-id="f5b32-115">The AS2EdiReceive pipeline accesses the SSO store, which requires that the user is in the BizTalk Application Users group.</span></span>  
  
  <span data-ttu-id="f5b32-116">**AS2Receive 管道**</span><span class="sxs-lookup"><span data-stu-id="f5b32-116">**AS2Receive Pipeline**</span></span>  
  
  <span data-ttu-id="f5b32-117">此管道处理通过 AS2 接收时未以 EDI 编码消息的消息。</span><span class="sxs-lookup"><span data-stu-id="f5b32-117">This pipeline processes messages received over AS2 when the messages are not encoded in EDI.</span></span> <span data-ttu-id="f5b32-118">这些消息被视为二进制消息。</span><span class="sxs-lookup"><span data-stu-id="f5b32-118">These messages are treated as binary messages.</span></span> <span data-ttu-id="f5b32-119">此管道还处理通过 AS2 接收的 Mdn。</span><span class="sxs-lookup"><span data-stu-id="f5b32-119">The pipeline also processes MDNs received over AS2.</span></span> <span data-ttu-id="f5b32-120">管道由以下管道组件组成：</span><span class="sxs-lookup"><span data-stu-id="f5b32-120">The pipeline consists of the following pipeline components:</span></span>  
  
- <span data-ttu-id="f5b32-121">AS2 解码器</span><span class="sxs-lookup"><span data-stu-id="f5b32-121">AS2 Decoder</span></span>  
  
- <span data-ttu-id="f5b32-122">AS2 拆装器。</span><span class="sxs-lookup"><span data-stu-id="f5b32-122">AS2 Disassembler.</span></span>  
  
## <a name="as2-receive-pipeline-components"></a><span data-ttu-id="f5b32-123">AS2 接收管道组件</span><span class="sxs-lookup"><span data-stu-id="f5b32-123">AS2 Receive Pipeline Components</span></span>  
 <span data-ttu-id="f5b32-124">AS2 接收管道都使用以下管道组件。</span><span class="sxs-lookup"><span data-stu-id="f5b32-124">The AS2 receive pipelines use the following pipeline components.</span></span> <span data-ttu-id="f5b32-125">这些组件安装在`Microsoft.BizTalk.EdiInt.PipelineComponents.dll`\Program Files\Microsoft BizTalk Server 20xx\Pipeline Components 中\\。</span><span class="sxs-lookup"><span data-stu-id="f5b32-125">These components are installed in `Microsoft.BizTalk.EdiInt.PipelineComponents.dll` in \Program Files\Microsoft BizTalk Server 20xx\Pipeline Components\\.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f5b32-126">AS2 接收管道只能在 32 位 BizTalk 主机进程中。</span><span class="sxs-lookup"><span data-stu-id="f5b32-126">The AS2 Receive pipeline is only supported in a 32-bit BizTalk Host process.</span></span>  
  
 <span data-ttu-id="f5b32-127">**AS2 解码器**</span><span class="sxs-lookup"><span data-stu-id="f5b32-127">**AS2 Decoder**</span></span>  
  
 <span data-ttu-id="f5b32-128">AS2 解码器包含在 AS2EDIReceivePipeline 的解码阶段中，AS2Receive 接收管道。</span><span class="sxs-lookup"><span data-stu-id="f5b32-128">The AS2 Decoder is included in the decode stage of both the AS2EDIReceivePipeline and AS2Receive receive pipelines.</span></span> <span data-ttu-id="f5b32-129">它使用 BizTalk S/MIME 管道组件来提供 S/MIME 解码的 AS2 和 MDN 消息的功能。</span><span class="sxs-lookup"><span data-stu-id="f5b32-129">It uses the BizTalk S/MIME Pipeline Component to provide S/MIME decoding functionality to AS2 and MDN messages.</span></span>  
  
- <span data-ttu-id="f5b32-130">处理 AS2/HTTP 标头</span><span class="sxs-lookup"><span data-stu-id="f5b32-130">Processes AS2/HTTP headers</span></span>  
  
- <span data-ttu-id="f5b32-131">验证签名时，如果已对消息签名</span><span class="sxs-lookup"><span data-stu-id="f5b32-131">Verifies the signature, if the message was signed</span></span>  
  
- <span data-ttu-id="f5b32-132">如果消息已加密 （对于 EDI/AS2 消息，不适用于 MDN） 对消息进行解密</span><span class="sxs-lookup"><span data-stu-id="f5b32-132">Decrypts the messages, if the message was encrypted (for an EDI/AS2 message, not an MDN)</span></span>  
  
- <span data-ttu-id="f5b32-133">如果消息已压缩进行解压缩消息，</span><span class="sxs-lookup"><span data-stu-id="f5b32-133">Decompresses the message, if the message was compressed</span></span>  
  
- <span data-ttu-id="f5b32-134">协调收到的 MDN 和原始的出站消息</span><span class="sxs-lookup"><span data-stu-id="f5b32-134">Reconciles a received MDN with the original outbound message</span></span>  
  
- <span data-ttu-id="f5b32-135">更新并关联不可否认数据库中的记录</span><span class="sxs-lookup"><span data-stu-id="f5b32-135">Updates and correlates records in the non-repudiation database</span></span>  
  
- <span data-ttu-id="f5b32-136">写入 AS2 状态报告的记录</span><span class="sxs-lookup"><span data-stu-id="f5b32-136">Writes records for AS2 status reporting</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="f5b32-137">如果在 AS2 消息的接收端处理期间发生错误，AS2 解码器将停止进一步的下游消息处理 （例如，EDI 拆装器将不会分析交换）。</span><span class="sxs-lookup"><span data-stu-id="f5b32-137">If an error occurs during receive-side processing of an AS2 message, the AS2 Decoder will stop further downstream message processing (for example, the EDI disassembler will not parse the interchange).</span></span> <span data-ttu-id="f5b32-138">但是，AS2 拆装器或 EDI 拆装器仍必须生成 MDN。</span><span class="sxs-lookup"><span data-stu-id="f5b32-138">However, the AS2 Disassembler or EDI Disassembler must still generate the MDN.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="f5b32-139">对 AS2 消息，则使用 8 位编码。</span><span class="sxs-lookup"><span data-stu-id="f5b32-139">Eight-bit encoding is used on AS2 messages.</span></span> <span data-ttu-id="f5b32-140">Base64 编码仅应用于中的 AS2 消息和 Mdn 的签名。</span><span class="sxs-lookup"><span data-stu-id="f5b32-140">Base64 encoding is only applied to signatures in AS2 messages and MDNs.</span></span>  
  
  <span data-ttu-id="f5b32-141">**AS2 拆装器**</span><span class="sxs-lookup"><span data-stu-id="f5b32-141">**AS2 Disassembler**</span></span>  
  
  <span data-ttu-id="f5b32-142">在 AS2Receive 接收管道，AS2 拆装器执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="f5b32-142">In the AS2Receive receive pipeline, the AS2 Disassembler does the following:</span></span>  
  
- <span data-ttu-id="f5b32-143">确定是否 MDN 是必需的并且是否 MDN 应该同步或异步。</span><span class="sxs-lookup"><span data-stu-id="f5b32-143">Determines whether an MDN is required, and whether the MDN should be synchronous or asynchronous.</span></span>  
  
- <span data-ttu-id="f5b32-144">生成 AS2 MDN。</span><span class="sxs-lookup"><span data-stu-id="f5b32-144">Generates an AS2 MDN.</span></span>  
  
- <span data-ttu-id="f5b32-145">如果 MDN 是同步的设置`EdiIntAS.IsAS2AsynchronousMDN`属性设置为 False; 如果异步的该属性设置为 True。</span><span class="sxs-lookup"><span data-stu-id="f5b32-145">If the MDN is synchronous, sets the `EdiIntAS.IsAS2AsynchronousMDN` property to False; if asynchronous, sets the property to True.</span></span>  
  
- <span data-ttu-id="f5b32-146">在 MDN 上设置的相关标记和属性。</span><span class="sxs-lookup"><span data-stu-id="f5b32-146">Sets the correlation tokens and properties on the MDN.</span></span>  
  
  <span data-ttu-id="f5b32-147">**EDI 拆装器**</span><span class="sxs-lookup"><span data-stu-id="f5b32-147">**EDI Disassembler**</span></span>  
  
  <span data-ttu-id="f5b32-148">在 AS2EDIReceivePipeline 中，EDI 拆装器会将 EDI 消息解析为中间 XML 消息以进行处理。</span><span class="sxs-lookup"><span data-stu-id="f5b32-148">In the AS2EDIReceivePipeline, the EDI Disassembler will parse the EDI message into intermediate XML message(s) for processing.</span></span> <span data-ttu-id="f5b32-149">有关详细信息，请参阅[EDI 拆装器的工作原理](../core/how-the-edi-disassembler-works.md)。</span><span class="sxs-lookup"><span data-stu-id="f5b32-149">For more information, see [How the EDI Disassembler Works](../core/how-the-edi-disassembler-works.md).</span></span>  
  
  <span data-ttu-id="f5b32-150">**BatchMarker**</span><span class="sxs-lookup"><span data-stu-id="f5b32-150">**BatchMarker**</span></span>  
  
  <span data-ttu-id="f5b32-151">在 AS2EDIReceivePipeline 中，BatchMarker 管道组件设置处理批的交换所需的 AgreementPartIdForSend 和 ToBeBatched 上下文属性。</span><span class="sxs-lookup"><span data-stu-id="f5b32-151">In the AS2EDIReceivePipeline, the BatchMarker pipeline component sets the AgreementPartIdForSend and ToBeBatched context properties that are required for processing a batched interchange.</span></span> <span data-ttu-id="f5b32-152">此组件包含在 AS2EDIReceive 管道的最后一个阶段 （协议解析）。</span><span class="sxs-lookup"><span data-stu-id="f5b32-152">This component is included in the last stage (agreement resolution) of the AS2EDIReceive pipeline.</span></span> <span data-ttu-id="f5b32-153">将 EDI 消息进行批处理的所有管道应都包含 BatchMarker 管道组件。</span><span class="sxs-lookup"><span data-stu-id="f5b32-153">All pipelines that will batch EDI messages should include the BatchMarker pipeline component.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f5b32-154">BatchMarker 管道组件不包括在用于处理非 EDI 消息的 AS2Receive 管道。</span><span class="sxs-lookup"><span data-stu-id="f5b32-154">The BatchMarker pipeline component is not included in the AS2Receive pipeline that is used to process non-EDI messages.</span></span> <span data-ttu-id="f5b32-155">但是，您可以不包含 EDI 拆装器的自定义接收管道中包含 BatchMarker 组件。</span><span class="sxs-lookup"><span data-stu-id="f5b32-155">However, you can include the BatchMarker component in a custom receive pipeline that does not include the EDI Dissassembler.</span></span> <span data-ttu-id="f5b32-156">详细信息，请参阅"处理非 EDI 消息在 BatchMarker 组件"中[装配批处理的 EDI 交换](../core/assembling-a-batched-edi-interchange.md)。</span><span class="sxs-lookup"><span data-stu-id="f5b32-156">For more information, see "Processing Non-EDI Messages in the BatchMarker Component" in [Assembling a Batched EDI Interchange](../core/assembling-a-batched-edi-interchange.md).</span></span>  
  
## <a name="http-adapter"></a><span data-ttu-id="f5b32-157">HTTP 适配器</span><span class="sxs-lookup"><span data-stu-id="f5b32-157">HTTP Adapter</span></span>  
 <span data-ttu-id="f5b32-158">接收端口和位置用于 AS2 处理使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]HTTP 适配器。</span><span class="sxs-lookup"><span data-stu-id="f5b32-158">The receive ports and locations used for AS2 processing use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP Adapter.</span></span> <span data-ttu-id="f5b32-159">HTTP 适配器配置为单向和请求-响应传输。</span><span class="sxs-lookup"><span data-stu-id="f5b32-159">The HTTP Adapter is configured for either one-way and request-response transmission.</span></span>  
  
## <a name="non-repudiation-database"></a><span data-ttu-id="f5b32-160">不可否认数据库</span><span class="sxs-lookup"><span data-stu-id="f5b32-160">Non-Repudiation Database</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="f5b32-161">使用不可否认数据库 （BizTalkDTADb 数据库的 EdiMessageContent 表） 执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f5b32-161">uses the non-repudiation database (the EdiMessageContent table of the BizTalkDTADb database) to do the following:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f5b32-162">仅当已选中的不可否认存储协议属性之一，EdiMessageContent 表存在 BizTalkDTADb 数据库中。</span><span class="sxs-lookup"><span data-stu-id="f5b32-162">The EdiMessageContent table exists in the BizTalkDTADb database only if one of the non-repudiation storage agreement properties has been checked.</span></span>  
  
-   <span data-ttu-id="f5b32-163">为经过签名的 MDN 提供不可否认记录</span><span class="sxs-lookup"><span data-stu-id="f5b32-163">Provides a non-repudiation trail for signed MDN</span></span>  
  
-   <span data-ttu-id="f5b32-164">将出站消息与其传入 mdn 关联起来</span><span class="sxs-lookup"><span data-stu-id="f5b32-164">Correlates an outbound message with its incoming MDN</span></span>  
  
-   <span data-ttu-id="f5b32-165">将通过各种状态更改的消息存储</span><span class="sxs-lookup"><span data-stu-id="f5b32-165">Stores messages through various state changes</span></span>  
  
-   <span data-ttu-id="f5b32-166">将错误代码与 HTTP 响应和 MDN 相关联</span><span class="sxs-lookup"><span data-stu-id="f5b32-166">Associates error codes with HTTP Response and MDN</span></span>  
  
-   <span data-ttu-id="f5b32-167">显示根据筛选条件的记录</span><span class="sxs-lookup"><span data-stu-id="f5b32-167">Displays records based on filter criteria</span></span>  
  
-   <span data-ttu-id="f5b32-168">标记的记录存档。</span><span class="sxs-lookup"><span data-stu-id="f5b32-168">Archives marked records.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f5b32-169">若要确保身份验证和存储在不可否认接收数据库中的消息的完整性，应将存储在数据库中，原始 AS2 消息和 Mdn 的所有消息使用数字签名。</span><span class="sxs-lookup"><span data-stu-id="f5b32-169">To ensure authentication and integrity of messages stored in the non-repudiation receipt database, digital signatures should be used on all messages that will be stored in the database, both original AS2 messages and MDNs.</span></span> <span data-ttu-id="f5b32-170">有关详细信息，请参阅的 9.1 节[RFC 1430、"基于 MIME 的安全对等业务数据交换使用 HTTP，Applicability Statement 2 (AS2)"](http://go.microsoft.com/fwlink/?LinkID=184212) ([http://go.microsoft.com/fwlink/?LinkID=184212](http://go.microsoft.com/fwlink/?LinkID=184212))。</span><span class="sxs-lookup"><span data-stu-id="f5b32-170">For more information, see section 9.1 of [RFC 1430, "MIME-Based Secure Peer-to-Peer Business Data Interchange Using HTTP, Applicability Statement 2 (AS2)"](http://go.microsoft.com/fwlink/?LinkID=184212) ([http://go.microsoft.com/fwlink/?LinkID=184212](http://go.microsoft.com/fwlink/?LinkID=184212)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5b32-171">请参阅</span><span class="sxs-lookup"><span data-stu-id="f5b32-171">See Also</span></span>  
 [<span data-ttu-id="f5b32-172">BizTalk Server 如何接收 AS2 消息</span><span class="sxs-lookup"><span data-stu-id="f5b32-172">How BizTalk Server Receives AS2 Messages</span></span>](../core/how-biztalk-server-receives-as2-messages.md)