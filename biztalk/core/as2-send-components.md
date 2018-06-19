---
title: AS2 发送组件 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 35113732-fe32-4776-be25-971ec66c365c
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1dbee64dc2e3484e85e6d8e41ce31a77713ffec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231965"
---
# <a name="as2-send-components"></a><span data-ttu-id="61cb8-102">AS2 发送组件</span><span class="sxs-lookup"><span data-stu-id="61cb8-102">AS2 Send Components</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="61cb8-103"> 使用若干个组件来发送 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="61cb8-103"> uses several components to send AS2 messages.</span></span>  
  
## <a name="as2-send-pipelines"></a><span data-ttu-id="61cb8-104">AS2 发送管道</span><span class="sxs-lookup"><span data-stu-id="61cb8-104">AS2 Send Pipelines</span></span>  
 <span data-ttu-id="61cb8-105">大部分 AS2 发送处理工作都在下列 AS2 发送管道中进行。</span><span class="sxs-lookup"><span data-stu-id="61cb8-105">Most AS2 send processing is performed in the following AS2 send pipelines.</span></span> <span data-ttu-id="61cb8-106">这些管道安装在 \Program Files\Microsoft BizTalk Server 20xx\Pipeline Components 中的 `Microsoft.BizTalk.Edi.EdiIntPipelines.dll` 中。</span><span class="sxs-lookup"><span data-stu-id="61cb8-106">These pipelines are installed in `Microsoft.BizTalk.Edi.EdiIntPipelines.dll` in \Program Files\Microsoft BizTalk Server 20xx\Pipeline Components.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="61cb8-107">AS2 发送管道只在 32 位 BizTalk 主机进程中受支持。</span><span class="sxs-lookup"><span data-stu-id="61cb8-107">The AS2 Send pipeline is only supported in a 32-bit BizTalk Host process.</span></span>  
  
 <span data-ttu-id="61cb8-108">**AS2EDISend 管道**</span><span class="sxs-lookup"><span data-stu-id="61cb8-108">**AS2EDISend Pipeline**</span></span>  
  
 <span data-ttu-id="61cb8-109">此管道生成 EDI 消息并通过 AS2 发送这些消息。</span><span class="sxs-lookup"><span data-stu-id="61cb8-109">This pipeline generates and sends EDI messages over AS2.</span></span> <span data-ttu-id="61cb8-110">管道包含以下管道组件：</span><span class="sxs-lookup"><span data-stu-id="61cb8-110">The pipeline consists of the following pipeline components:</span></span>  
  
-   <span data-ttu-id="61cb8-111">EDI 组装器</span><span class="sxs-lookup"><span data-stu-id="61cb8-111">EDI Assembler</span></span>  
  
-   <span data-ttu-id="61cb8-112">AS2 编码器</span><span class="sxs-lookup"><span data-stu-id="61cb8-112">AS2 Encoder</span></span>  
  
 <span data-ttu-id="61cb8-113">此管道不用于生成和通过 AS2 发送 MDN，因为 MDN 不需要由 EDI 组装器处理。</span><span class="sxs-lookup"><span data-stu-id="61cb8-113">This pipeline is not used to generate and send MDNs over AS2, because the MDN does not need to be processed by the EDI Assembler.</span></span> <span data-ttu-id="61cb8-114">使用 AS2SendPipeline 发送 MDN。</span><span class="sxs-lookup"><span data-stu-id="61cb8-114">Use the AS2SendPipeline to send MDNs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="61cb8-115">不支持从业务流程中运行 AS2EDISend 管道。</span><span class="sxs-lookup"><span data-stu-id="61cb8-115">Running the AS2EDISend pipeline from an orchestration is not supported.</span></span>  
  
 <span data-ttu-id="61cb8-116">**AS2Send 管道**</span><span class="sxs-lookup"><span data-stu-id="61cb8-116">**AS2Send Pipeline**</span></span>  
  
 <span data-ttu-id="61cb8-117">如果消息未以 EDI 编码，则此管道通过 AS2 发送消息。</span><span class="sxs-lookup"><span data-stu-id="61cb8-117">This pipeline sends messages over AS2 when the messages are not encoded in EDI.</span></span> <span data-ttu-id="61cb8-118">此管道还通过 AS2 发送 MDN。</span><span class="sxs-lookup"><span data-stu-id="61cb8-118">It also sends MDNs over AS2.</span></span> <span data-ttu-id="61cb8-119">管道包含以下管道组件：</span><span class="sxs-lookup"><span data-stu-id="61cb8-119">The pipeline consists of the following pipeline components:</span></span>  
  
-   <span data-ttu-id="61cb8-120">AS2 编码器。</span><span class="sxs-lookup"><span data-stu-id="61cb8-120">AS2 Encoder.</span></span>  
  
 <span data-ttu-id="61cb8-121">如果要通过 AS2 发送的消息既不是 EDI 消息，也不是 XML 消息，则可以创建一个自定义 AS2Send 管道来处理这些消息。</span><span class="sxs-lookup"><span data-stu-id="61cb8-121">If the messages to be sent over AS2 are neither EDI nor XML messages, you can create a customized AS2Send pipeline to handle these messages.</span></span> <span data-ttu-id="61cb8-122">此管道必须具有自定义组装器，以便将 BizTalk Server 中的中间 XML 转换为其他格式后再以 EDIINT/AS2 对消息进行编码。</span><span class="sxs-lookup"><span data-stu-id="61cb8-122">This pipeline must have a customized assembler to convert the intermediate XML in BizTalk Server into the other format before encoding the message in EDIINT/AS2.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="61cb8-123">不支持从业务流程运行 AS2Send 管道。</span><span class="sxs-lookup"><span data-stu-id="61cb8-123">Running the AS2Send pipeline from an orchestration is not supported.</span></span>  
  
## <a name="as2-send-pipeline-components"></a><span data-ttu-id="61cb8-124">AS2 发送管道组件</span><span class="sxs-lookup"><span data-stu-id="61cb8-124">AS2 Send Pipeline Components</span></span>  
 <span data-ttu-id="61cb8-125">AS2 发送管道使用以下管道组件。</span><span class="sxs-lookup"><span data-stu-id="61cb8-125">The AS2 send pipelines use the following pipeline components.</span></span> <span data-ttu-id="61cb8-126">这些组件安装在`Microsoft.BizTalk.EdiInt.PipelineComponents.dll`中 files\microsoft BizTalk Server 20xx\Pipeline 组件\\。</span><span class="sxs-lookup"><span data-stu-id="61cb8-126">These components are installed in `Microsoft.BizTalk.EdiInt.PipelineComponents.dll` in \Program Files\Microsoft BizTalk Server 20xx\Pipeline Components\\.</span></span>  
  
 <span data-ttu-id="61cb8-127">**EDI 汇编器**</span><span class="sxs-lookup"><span data-stu-id="61cb8-127">**EDI Assembler**</span></span>  
  
 <span data-ttu-id="61cb8-128">在 EDIINT 发送管道中，EDI 组装器将对 EDI 交换进行序列化。</span><span class="sxs-lookup"><span data-stu-id="61cb8-128">In the EDIINT send pipelines, the EDI Assembler serializes the EDI interchange.</span></span>  
  
 <span data-ttu-id="61cb8-129">**AS2 编码器**</span><span class="sxs-lookup"><span data-stu-id="61cb8-129">**AS2 Encoder**</span></span>  
  
 <span data-ttu-id="61cb8-130">AS2 编码器包括在 AS2 发送管道的编码阶段中。</span><span class="sxs-lookup"><span data-stu-id="61cb8-130">The AS2 Encoder is included in the encode stage of the AS2 send pipelines.</span></span> <span data-ttu-id="61cb8-131">该编码器使用 BizTalk S/MIME 管道组件向 AS2 和 MDN 消息提供 S/MIME 编码功能。</span><span class="sxs-lookup"><span data-stu-id="61cb8-131">It uses the BizTalk S/MIME pipeline component to provide S/MIME encoding functionality to AS2 and MDN messages.</span></span> <span data-ttu-id="61cb8-132">AS2 编码器执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="61cb8-132">The AS2 Encoder does the following:</span></span>  
  
-   <span data-ttu-id="61cb8-133">应用 AS2/HTTP 标头</span><span class="sxs-lookup"><span data-stu-id="61cb8-133">Applies AS2/HTTP headers</span></span>  
  
-   <span data-ttu-id="61cb8-134">对传出消息进行签名（如果已启用）</span><span class="sxs-lookup"><span data-stu-id="61cb8-134">Signs outgoing messages, if enabled</span></span>  
  
-   <span data-ttu-id="61cb8-135">对传出消息进行加密（如果已启用）（适用于 EDI/AS2，不适用于 MDN）</span><span class="sxs-lookup"><span data-stu-id="61cb8-135">Encrypts outgoing messages, if enabled (for EDI/AS2, not MDN)</span></span>  
  
-   <span data-ttu-id="61cb8-136">压缩消息（如果已启用）（适用于 EDI/AS2，不适用于 MDN）</span><span class="sxs-lookup"><span data-stu-id="61cb8-136">Compresses the message, if enabled (for EDI/AS2, not MDN)</span></span>  
  
-   <span data-ttu-id="61cb8-137">将负载存储在连网格式，如果**为出站的已解码 AS2 消息启用 NRR**属性选择，并将该消息存储在连网格式，如果**为出站的已编码 AS2 消息启用 NRR**选择属性</span><span class="sxs-lookup"><span data-stu-id="61cb8-137">Stores the payload in wire format if the **NRR enabled for outbound decoded AS2 messages** property is selected, and stores the message in wire format if the **NRR enabled for outbound encoded AS2 messages** property is selected</span></span>  
  
-   <span data-ttu-id="61cb8-138">计算 MIC 值并将其存储在数据存储区中</span><span class="sxs-lookup"><span data-stu-id="61cb8-138">Computes the MIC value and stores it in the data store</span></span>  
  
-   <span data-ttu-id="61cb8-139">更新并关联不可否认接收数据库中的记录</span><span class="sxs-lookup"><span data-stu-id="61cb8-139">Updates and correlates records in the non-repudiation receipt database</span></span>  
  
-   <span data-ttu-id="61cb8-140">对于 MDN 消息，充当直通管道，在 AS2Receive 接收管道中路由 AS2 解码器生成的 MDN。</span><span class="sxs-lookup"><span data-stu-id="61cb8-140">For MDN messages, acts as a passthrough pipeline, routing the MDN generated by the AS2 Decoder in the AS2Receive receive pipeline.</span></span> <span data-ttu-id="61cb8-141">如果配置设置要求，AS2 编码器将对 MDN 进行签名。</span><span class="sxs-lookup"><span data-stu-id="61cb8-141">If required by the configuration settings, the AS2 Encoder will sign the MDN.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="61cb8-142">对 AS2 消息使用的是八位编码。</span><span class="sxs-lookup"><span data-stu-id="61cb8-142">Eight-bit encoding is used on AS2 messages.</span></span> <span data-ttu-id="61cb8-143">Base64 编码仅应用于 AS2 消息和 MDN 中的签名。</span><span class="sxs-lookup"><span data-stu-id="61cb8-143">Base64 encoding is only applied to signatures in AS2 messages and MDNs.</span></span>  
  
## <a name="http-adapter"></a><span data-ttu-id="61cb8-144">HTTP 适配器</span><span class="sxs-lookup"><span data-stu-id="61cb8-144">HTTP Adapter</span></span>  
 <span data-ttu-id="61cb8-145">EDIINT AS2 处理用到的发送端口使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP 适配器。</span><span class="sxs-lookup"><span data-stu-id="61cb8-145">The send ports used for EDIINT AS2 processing use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] HTTP Adapter.</span></span> <span data-ttu-id="61cb8-146">在单向传输和要求-响应传输中均对 HTTP 适配器进行了配置。</span><span class="sxs-lookup"><span data-stu-id="61cb8-146">The HTTP Adapter is configured in both one-way and solicit-response transmission.</span></span>  
  
## <a name="non-repudiation-database"></a><span data-ttu-id="61cb8-147">不可否认数据库</span><span class="sxs-lookup"><span data-stu-id="61cb8-147">Non-Repudiation Database</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="61cb8-148"> 使用不可否认数据库（BizTalkDTADb 数据库的 EdiMessageContent 表）执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="61cb8-148"> uses the non-repudiation database (the EdiMessageContent table of the BizTalkDTADb database) to do the following:</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="61cb8-149">仅当不可否认性存储协议属性之一进行检查，EdiMessageContent 表 BizTalkDTADb 数据库中存在。</span><span class="sxs-lookup"><span data-stu-id="61cb8-149">The EdiMessageContent table exists in the BizTalkDTADb database only if one of the non-repudiation storage agreement properties are checked.</span></span>  
  
-   <span data-ttu-id="61cb8-150">为签名的 MDN 提供不可否认性跟踪</span><span class="sxs-lookup"><span data-stu-id="61cb8-150">Provide a non-repudiation trail for signed MDN</span></span>  
  
-   <span data-ttu-id="61cb8-151">将出站消息具有其传入 MDN 相互关联</span><span class="sxs-lookup"><span data-stu-id="61cb8-151">Correlate an outbound message with its incoming MDN</span></span>  
  
-   <span data-ttu-id="61cb8-152">存储通过各种状态更改的消息</span><span class="sxs-lookup"><span data-stu-id="61cb8-152">Store messages through various state changes</span></span>  
  
-   <span data-ttu-id="61cb8-153">将错误代码与 HTTP 响应和 MDN 关联起来</span><span class="sxs-lookup"><span data-stu-id="61cb8-153">Associate error codes with HTTP Response and MDN</span></span>  
  
-   <span data-ttu-id="61cb8-154">显示根据筛选器条件的记录</span><span class="sxs-lookup"><span data-stu-id="61cb8-154">Display records based on filter criteria</span></span>  
  
-   <span data-ttu-id="61cb8-155">将标记的记录存档</span><span class="sxs-lookup"><span data-stu-id="61cb8-155">Archive marked records</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="61cb8-156">为确保不可否认数据库中存储的消息的验证和完整性，应对将存储在此数据库中的所有消息使用数字签名，原始 AS2 消息和 MDN 都包含在内。</span><span class="sxs-lookup"><span data-stu-id="61cb8-156">To ensure authentication and integrity of messages stored in the non-repudiation database, digital signatures should be used on all messages that will be stored in the database, both original AS2 messages and MDNs.</span></span> <span data-ttu-id="61cb8-157">有关详细信息，请参阅的部分 9.1 [RFC 1430，"MIME 基于安全对等的业务数据交换使用 HTTP，适用性语句 2 (AS2)"](http://go.microsoft.com/fwlink/?LinkID=184212) ([http://go.microsoft.com/fwlink/?LinkID=184212](http://go.microsoft.com/fwlink/?LinkID=184212))。</span><span class="sxs-lookup"><span data-stu-id="61cb8-157">For more information, see section 9.1 of [RFC 1430, "MIME-Based Secure Peer-to-Peer Business Data Interchange Using HTTP, Applicability Statement 2 (AS2)"](http://go.microsoft.com/fwlink/?LinkID=184212) ([http://go.microsoft.com/fwlink/?LinkID=184212](http://go.microsoft.com/fwlink/?LinkID=184212)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61cb8-158">另请参阅</span><span class="sxs-lookup"><span data-stu-id="61cb8-158">See Also</span></span>  
 [<span data-ttu-id="61cb8-159">BizTalk Server 将 AS2 消息的发送</span><span class="sxs-lookup"><span data-stu-id="61cb8-159">How BizTalk Server Sends AS2 Messages</span></span>](../core/how-biztalk-server-sends-as2-messages.md)