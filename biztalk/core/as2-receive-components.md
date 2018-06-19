---
title: AS2 接收组件 |Microsoft 文档
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
ms.openlocfilehash: 0c919a54a307a234237dd4086a0abf2a2c0c2fd8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232549"
---
# <a name="as2-receive-components"></a><span data-ttu-id="3805f-102">AS2 接收组件</span><span class="sxs-lookup"><span data-stu-id="3805f-102">AS2 Receive Components</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="3805f-103"> 使用若干个组件来接收 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="3805f-103"> uses several components to receive AS2 messages.</span></span>  
  
## <a name="as2-receive-pipelines"></a><span data-ttu-id="3805f-104">AS2 接收管道</span><span class="sxs-lookup"><span data-stu-id="3805f-104">AS2 Receive Pipelines</span></span>  
 <span data-ttu-id="3805f-105">大部分 AS2 接收处理工作都在下列 AS2 接收管道中进行。</span><span class="sxs-lookup"><span data-stu-id="3805f-105">Most AS2 receive processing is performed in the following AS2 receive pipelines.</span></span> <span data-ttu-id="3805f-106">在中安装这些管道`Microsoft.BizTalk.EdiInt.PipelineComponents.dll`中 files\microsoft BizTalk Server 20xx\Pipeline 组件\\。</span><span class="sxs-lookup"><span data-stu-id="3805f-106">These pipelines are installed in `Microsoft.BizTalk.EdiInt.PipelineComponents.dll` in \Program Files\Microsoft BizTalk Server 20xx\Pipeline Components\\.</span></span>  
  
 <span data-ttu-id="3805f-107">**AS2EdiReceive 管道**</span><span class="sxs-lookup"><span data-stu-id="3805f-107">**AS2EdiReceive Pipeline**</span></span>  
  
 <span data-ttu-id="3805f-108">此管道处理通过 AS2 接收的 EDI 消息，包括 MDN。</span><span class="sxs-lookup"><span data-stu-id="3805f-108">This pipeline processes EDI messages received over AS2, including MDNs.</span></span> <span data-ttu-id="3805f-109">管道包含以下管道组件：</span><span class="sxs-lookup"><span data-stu-id="3805f-109">The pipeline consists of the following pipeline components:</span></span>  
  
-   <span data-ttu-id="3805f-110">AS2 解码器</span><span class="sxs-lookup"><span data-stu-id="3805f-110">AS2 Decoder</span></span>  
  
-   <span data-ttu-id="3805f-111">EDI 拆装器</span><span class="sxs-lookup"><span data-stu-id="3805f-111">EDI Disassembler</span></span>  
  
-   <span data-ttu-id="3805f-112">BatchMarker。</span><span class="sxs-lookup"><span data-stu-id="3805f-112">BatchMarker.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3805f-113">使用 AS2EdiReceive 管道时，必须将运行 BizTalk 独立主机实例进程的用户帐户添加到 BizTalk Application Users 组中。</span><span class="sxs-lookup"><span data-stu-id="3805f-113">When using the AS2EdiReceive pipeline, you must add the user account that the BizTalk Isolated Host Instance process is running under to the BizTalk Application Users group.</span></span> <span data-ttu-id="3805f-114">AS2EdiReceive 管道在 BizTalk 独立主机实例进程中执行。</span><span class="sxs-lookup"><span data-stu-id="3805f-114">The AS2EdiReceive pipeline executes in the BizTalk Isolated Host Instance process.</span></span> <span data-ttu-id="3805f-115">AS2EdiReceive 管道会访问 SSO 存储区，这要求用户属于 BizTalk Application Users 组。</span><span class="sxs-lookup"><span data-stu-id="3805f-115">The AS2EdiReceive pipeline accesses the SSO store, which requires that the user is in the BizTalk Application Users group.</span></span>  
  
 <span data-ttu-id="3805f-116">**AS2Receive 管道**</span><span class="sxs-lookup"><span data-stu-id="3805f-116">**AS2Receive Pipeline**</span></span>  
  
 <span data-ttu-id="3805f-117">如果消息未以 EDI 编码，则此管道处理通过 AS2 接收的消息。</span><span class="sxs-lookup"><span data-stu-id="3805f-117">This pipeline processes messages received over AS2 when the messages are not encoded in EDI.</span></span> <span data-ttu-id="3805f-118">这些消息被视为二进制消息。</span><span class="sxs-lookup"><span data-stu-id="3805f-118">These messages are treated as binary messages.</span></span> <span data-ttu-id="3805f-119">此管道还处理通过 AS2 接收的 MDN。</span><span class="sxs-lookup"><span data-stu-id="3805f-119">The pipeline also processes MDNs received over AS2.</span></span> <span data-ttu-id="3805f-120">管道包含以下管道组件：</span><span class="sxs-lookup"><span data-stu-id="3805f-120">The pipeline consists of the following pipeline components:</span></span>  
  
-   <span data-ttu-id="3805f-121">AS2 解码器</span><span class="sxs-lookup"><span data-stu-id="3805f-121">AS2 Decoder</span></span>  
  
-   <span data-ttu-id="3805f-122">AS2 拆装器。</span><span class="sxs-lookup"><span data-stu-id="3805f-122">AS2 Disassembler.</span></span>  
  
## <a name="as2-receive-pipeline-components"></a><span data-ttu-id="3805f-123">AS2 接收管道组件</span><span class="sxs-lookup"><span data-stu-id="3805f-123">AS2 Receive Pipeline Components</span></span>  
 <span data-ttu-id="3805f-124">AS2 接收管道使用以下管道组件。</span><span class="sxs-lookup"><span data-stu-id="3805f-124">The AS2 receive pipelines use the following pipeline components.</span></span> <span data-ttu-id="3805f-125">这些组件安装在`Microsoft.BizTalk.EdiInt.PipelineComponents.dll`中 files\microsoft BizTalk Server 20xx\Pipeline 组件\\。</span><span class="sxs-lookup"><span data-stu-id="3805f-125">These components are installed in `Microsoft.BizTalk.EdiInt.PipelineComponents.dll` in \Program Files\Microsoft BizTalk Server 20xx\Pipeline Components\\.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3805f-126">AS2 接收管道只在 32 位 BizTalk 主机进程中受支持。</span><span class="sxs-lookup"><span data-stu-id="3805f-126">The AS2 Receive pipeline is only supported in a 32-bit BizTalk Host process.</span></span>  
  
 <span data-ttu-id="3805f-127">**AS2 解码器**</span><span class="sxs-lookup"><span data-stu-id="3805f-127">**AS2 Decoder**</span></span>  
  
 <span data-ttu-id="3805f-128">AS2 解码器包含在 AS2EDIReceivePipeline 和 AS2Receive 接收管道的解码阶段中。</span><span class="sxs-lookup"><span data-stu-id="3805f-128">The AS2 Decoder is included in the decode stage of both the AS2EDIReceivePipeline and AS2Receive receive pipelines.</span></span> <span data-ttu-id="3805f-129">该解码器使用 BizTalk S/MIME 管道组件向 AS2 和 MDN 消息提供 S/MIME 解码功能。</span><span class="sxs-lookup"><span data-stu-id="3805f-129">It uses the BizTalk S/MIME Pipeline Component to provide S/MIME decoding functionality to AS2 and MDN messages.</span></span>  
  
-   <span data-ttu-id="3805f-130">处理 AS2/HTTP 标头</span><span class="sxs-lookup"><span data-stu-id="3805f-130">Processes AS2/HTTP headers</span></span>  
  
-   <span data-ttu-id="3805f-131">如果消息已签名，则验证签名</span><span class="sxs-lookup"><span data-stu-id="3805f-131">Verifies the signature, if the message was signed</span></span>  
  
-   <span data-ttu-id="3805f-132">如果消息已加密（针对 EDI/AS2 消息，而不适用于 MDN），则对消息进行解密</span><span class="sxs-lookup"><span data-stu-id="3805f-132">Decrypts the messages, if the message was encrypted (for an EDI/AS2 message, not an MDN)</span></span>  
  
-   <span data-ttu-id="3805f-133">如果消息已压缩，则对消息进行解压缩</span><span class="sxs-lookup"><span data-stu-id="3805f-133">Decompresses the message, if the message was compressed</span></span>  
  
-   <span data-ttu-id="3805f-134">协调收到的 MDN 与原始出站消息</span><span class="sxs-lookup"><span data-stu-id="3805f-134">Reconciles a received MDN with the original outbound message</span></span>  
  
-   <span data-ttu-id="3805f-135">更新并关联不可否认数据库中的记录</span><span class="sxs-lookup"><span data-stu-id="3805f-135">Updates and correlates records in the non-repudiation database</span></span>  
  
-   <span data-ttu-id="3805f-136">写入用于 AS2 状态报告的记录</span><span class="sxs-lookup"><span data-stu-id="3805f-136">Writes records for AS2 status reporting</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3805f-137">如果在接收端处理 AS2 消息的过程中发生错误，AS2 解码器将停止进一步的下游消息处理（例如，EDI 拆装器将不会分析交换）。</span><span class="sxs-lookup"><span data-stu-id="3805f-137">If an error occurs during receive-side processing of an AS2 message, the AS2 Decoder will stop further downstream message processing (for example, the EDI disassembler will not parse the interchange).</span></span> <span data-ttu-id="3805f-138">但是，AS2 拆装器或 EDI 拆装器仍必须生成 MDN。</span><span class="sxs-lookup"><span data-stu-id="3805f-138">However, the AS2 Disassembler or EDI Disassembler must still generate the MDN.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3805f-139">对 AS2 消息使用的是八位编码。</span><span class="sxs-lookup"><span data-stu-id="3805f-139">Eight-bit encoding is used on AS2 messages.</span></span> <span data-ttu-id="3805f-140">Base64 编码仅应用于 AS2 消息和 MDN 中的签名。</span><span class="sxs-lookup"><span data-stu-id="3805f-140">Base64 encoding is only applied to signatures in AS2 messages and MDNs.</span></span>  
  
 <span data-ttu-id="3805f-141">**AS2 反汇编程序**</span><span class="sxs-lookup"><span data-stu-id="3805f-141">**AS2 Disassembler**</span></span>  
  
 <span data-ttu-id="3805f-142">在 AS2Receive 接收管道中，AS2 拆装器执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3805f-142">In the AS2Receive receive pipeline, the AS2 Disassembler does the following:</span></span>  
  
-   <span data-ttu-id="3805f-143">确定是否需要 MDN 以及 MDN 应是同步的还是异步的。</span><span class="sxs-lookup"><span data-stu-id="3805f-143">Determines whether an MDN is required, and whether the MDN should be synchronous or asynchronous.</span></span>  
  
-   <span data-ttu-id="3805f-144">生成 AS2 MDN。</span><span class="sxs-lookup"><span data-stu-id="3805f-144">Generates an AS2 MDN.</span></span>  
  
-   <span data-ttu-id="3805f-145">如果 MDN 是同步的，则将 `EdiIntAS.IsAS2AsynchronousMDN` 属性设置为 False；如果是异步的，则将该属性设置为 True。</span><span class="sxs-lookup"><span data-stu-id="3805f-145">If the MDN is synchronous, sets the `EdiIntAS.IsAS2AsynchronousMDN` property to False; if asynchronous, sets the property to True.</span></span>  
  
-   <span data-ttu-id="3805f-146">在 MDN 上设置相关标记和属性。</span><span class="sxs-lookup"><span data-stu-id="3805f-146">Sets the correlation tokens and properties on the MDN.</span></span>  
  
 <span data-ttu-id="3805f-147">**EDI 反汇编程序**</span><span class="sxs-lookup"><span data-stu-id="3805f-147">**EDI Disassembler**</span></span>  
  
 <span data-ttu-id="3805f-148">在 AS2EDIReceivePipeline 中，EDI 拆装器会将 EDI 消息解析为中间 XML 消息以进行处理。</span><span class="sxs-lookup"><span data-stu-id="3805f-148">In the AS2EDIReceivePipeline, the EDI Disassembler will parse the EDI message into intermediate XML message(s) for processing.</span></span> <span data-ttu-id="3805f-149">有关详细信息，请参阅[EDI 反汇编程序的工作原理](../core/how-the-edi-disassembler-works.md)。</span><span class="sxs-lookup"><span data-stu-id="3805f-149">For more information, see [How the EDI Disassembler Works](../core/how-the-edi-disassembler-works.md).</span></span>  
  
 <span data-ttu-id="3805f-150">**BatchMarker**</span><span class="sxs-lookup"><span data-stu-id="3805f-150">**BatchMarker**</span></span>  
  
 <span data-ttu-id="3805f-151">在 AS2EDIReceivePipeline 中，BatchMarker 管道组件可设置处理批处理交换所需的 AgreementPartIdForSend 和 ToBeBatched 上下文属性。</span><span class="sxs-lookup"><span data-stu-id="3805f-151">In the AS2EDIReceivePipeline, the BatchMarker pipeline component sets the AgreementPartIdForSend and ToBeBatched context properties that are required for processing a batched interchange.</span></span> <span data-ttu-id="3805f-152">此组件包含在 AS2EDIReceive 管道的最后一个阶段（协议解析）中。</span><span class="sxs-lookup"><span data-stu-id="3805f-152">This component is included in the last stage (agreement resolution) of the AS2EDIReceive pipeline.</span></span> <span data-ttu-id="3805f-153">将要对 EDI 消息进行批处理的所有管道都应包含 BatchMarker 管道组件。</span><span class="sxs-lookup"><span data-stu-id="3805f-153">All pipelines that will batch EDI messages should include the BatchMarker pipeline component.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3805f-154">BatchMarker 管道组件未包含在用于处理非 EDI 消息的 AS2Receive 管道中。</span><span class="sxs-lookup"><span data-stu-id="3805f-154">The BatchMarker pipeline component is not included in the AS2Receive pipeline that is used to process non-EDI messages.</span></span> <span data-ttu-id="3805f-155">但是，你可以在不包含 EDI 拆装器的自定义接收管道中包含 BatchMarker 组件。</span><span class="sxs-lookup"><span data-stu-id="3805f-155">However, you can include the BatchMarker component in a custom receive pipeline that does not include the EDI Dissassembler.</span></span> <span data-ttu-id="3805f-156">有关详细信息，请参见"处理非 EDI 消息中 BatchMarker 组件"在[组合批处理的 EDI 交换](../core/assembling-a-batched-edi-interchange.md)。</span><span class="sxs-lookup"><span data-stu-id="3805f-156">For more information, see "Processing Non-EDI Messages in the BatchMarker Component" in [Assembling a Batched EDI Interchange](../core/assembling-a-batched-edi-interchange.md).</span></span>  
  
## <a name="http-adapter"></a><span data-ttu-id="3805f-157">HTTP 适配器</span><span class="sxs-lookup"><span data-stu-id="3805f-157">HTTP Adapter</span></span>  
 <span data-ttu-id="3805f-158">用于 AS2 处理的接收端口和位置使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP 适配器。</span><span class="sxs-lookup"><span data-stu-id="3805f-158">The receive ports and locations used for AS2 processing use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP Adapter.</span></span> <span data-ttu-id="3805f-159">已针对单向传输和请求-响应传输对 HTTP 适配器进行了配置。</span><span class="sxs-lookup"><span data-stu-id="3805f-159">The HTTP Adapter is configured for either one-way and request-response transmission.</span></span>  
  
## <a name="non-repudiation-database"></a><span data-ttu-id="3805f-160">不可否认数据库</span><span class="sxs-lookup"><span data-stu-id="3805f-160">Non-Repudiation Database</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="3805f-161"> 使用不可否认数据库（BizTalkDTADb 数据库的 EdiMessageContent 表）执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3805f-161"> uses the non-repudiation database (the EdiMessageContent table of the BizTalkDTADb database) to do the following:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3805f-162">只有在选中了其中一个不可否认存储协议属性时，EdiMessageContent 表才存在于 BizTalkDTADb 数据库中。</span><span class="sxs-lookup"><span data-stu-id="3805f-162">The EdiMessageContent table exists in the BizTalkDTADb database only if one of the non-repudiation storage agreement properties has been checked.</span></span>  
  
-   <span data-ttu-id="3805f-163">为已签名的 MDN 提供不可否认记录</span><span class="sxs-lookup"><span data-stu-id="3805f-163">Provides a non-repudiation trail for signed MDN</span></span>  
  
-   <span data-ttu-id="3805f-164">将出站消息与其传入 MDN 关联起来</span><span class="sxs-lookup"><span data-stu-id="3805f-164">Correlates an outbound message with its incoming MDN</span></span>  
  
-   <span data-ttu-id="3805f-165">通过各种状态更改存储消息</span><span class="sxs-lookup"><span data-stu-id="3805f-165">Stores messages through various state changes</span></span>  
  
-   <span data-ttu-id="3805f-166">将错误代码与 HTTP 响应和 MDN 相关联</span><span class="sxs-lookup"><span data-stu-id="3805f-166">Associates error codes with HTTP Response and MDN</span></span>  
  
-   <span data-ttu-id="3805f-167">根据筛选条件显示记录</span><span class="sxs-lookup"><span data-stu-id="3805f-167">Displays records based on filter criteria</span></span>  
  
-   <span data-ttu-id="3805f-168">将标记的记录存档。</span><span class="sxs-lookup"><span data-stu-id="3805f-168">Archives marked records.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3805f-169">为确保不可否认接收数据库中存储的消息的验证和完整性，应对将存储在此数据库中的所有消息（包括原始 AS2 消息和 MDN）使用数字签名。</span><span class="sxs-lookup"><span data-stu-id="3805f-169">To ensure authentication and integrity of messages stored in the non-repudiation receipt database, digital signatures should be used on all messages that will be stored in the database, both original AS2 messages and MDNs.</span></span> <span data-ttu-id="3805f-170">有关详细信息，请参阅的部分 9.1 [RFC 1430，"MIME 基于安全对等的业务数据交换使用 HTTP，适用性语句 2 (AS2)"](http://go.microsoft.com/fwlink/?LinkID=184212) ([http://go.microsoft.com/fwlink/?LinkID=184212](http://go.microsoft.com/fwlink/?LinkID=184212))。</span><span class="sxs-lookup"><span data-stu-id="3805f-170">For more information, see section 9.1 of [RFC 1430, "MIME-Based Secure Peer-to-Peer Business Data Interchange Using HTTP, Applicability Statement 2 (AS2)"](http://go.microsoft.com/fwlink/?LinkID=184212) ([http://go.microsoft.com/fwlink/?LinkID=184212](http://go.microsoft.com/fwlink/?LinkID=184212)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3805f-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3805f-171">See Also</span></span>  
 [<span data-ttu-id="3805f-172">BizTalk Server 接收 AS2 消息的方式</span><span class="sxs-lookup"><span data-stu-id="3805f-172">How BizTalk Server Receives AS2 Messages</span></span>](../core/how-biztalk-server-receives-as2-messages.md)