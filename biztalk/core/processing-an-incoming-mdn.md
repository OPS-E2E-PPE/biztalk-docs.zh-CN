---
title: "处理传入 MDN |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fd78e84c-4989-47e4-b95b-80582084ddec
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e599e9ebbc7a05a466cc047d891699222c2dabac
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="processing-an-incoming-mdn"></a><span data-ttu-id="4b7ab-102">处理传入 MDN</span><span class="sxs-lookup"><span data-stu-id="4b7ab-102">Processing an Incoming MDN</span></span>
<span data-ttu-id="4b7ab-103">AS2 接收传入 MDN 基于为作为 AS2 消息接收方方的协议属性的管道 （AS2EDIReceive 和 AS2Receive） 过程。</span><span class="sxs-lookup"><span data-stu-id="4b7ab-103">The AS2 receive pipelines (AS2EDIReceive and AS2Receive) process an incoming MDN based upon the agreement properties for the party as an AS2 message receiver.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="4b7ab-104">自动关联到传出的 AS2 消息 MDN。</span><span class="sxs-lookup"><span data-stu-id="4b7ab-104"> automatically correlates the MDN to the outgoing AS2 message.</span></span>  
  
 <span data-ttu-id="4b7ab-105">每个管道执行的步骤如下所示：</span><span class="sxs-lookup"><span data-stu-id="4b7ab-105">The steps each pipeline performs are as follows:</span></span>  
  
-   <span data-ttu-id="4b7ab-106">通过匹配 AS2 确定发送方-中消息的 AS2 标头值与 AS2 的值从-从列表中**标识符**的单向 AS2 协议选项卡页**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="4b7ab-106">Determines the sending party by matching the AS2-From value in the AS2 header of the message with the value for AS2-From list in the **Identifiers** page of the one-way AS2 agreement tab of the **Agreement Properties** dialog box.</span></span> <span data-ttu-id="4b7ab-107">如果未找到匹配项，则管道将中止处理并引发异常。</span><span class="sxs-lookup"><span data-stu-id="4b7ab-107">If a match is not found, the pipeline aborts processing and raises an exception.</span></span>  
  
-   <span data-ttu-id="4b7ab-108">将下列 AS2 属性升级到上下文中：</span><span class="sxs-lookup"><span data-stu-id="4b7ab-108">Promotes the following AS2 properties to the context:</span></span>  
  
    -   <span data-ttu-id="4b7ab-109">IsAS2FailedMessage</span><span class="sxs-lookup"><span data-stu-id="4b7ab-109">IsAS2FailedMessage</span></span>  
  
    -   <span data-ttu-id="4b7ab-110">DispositionType</span><span class="sxs-lookup"><span data-stu-id="4b7ab-110">DispositionType</span></span>  
  
    -   <span data-ttu-id="4b7ab-111">GenerateAsynchronous200OKOnly</span><span class="sxs-lookup"><span data-stu-id="4b7ab-111">GenerateAsynchronous200OKOnly</span></span>  
  
    -   <span data-ttu-id="4b7ab-112">IsAS2MdnResponseMessage</span><span class="sxs-lookup"><span data-stu-id="4b7ab-112">IsAS2MdnResponseMessage</span></span>  
  
    -   <span data-ttu-id="4b7ab-113">IsAS2MessageSigned</span><span class="sxs-lookup"><span data-stu-id="4b7ab-113">IsAS2MessageSigned</span></span>  
  
    -   <span data-ttu-id="4b7ab-114">OriginalMessageId</span><span class="sxs-lookup"><span data-stu-id="4b7ab-114">OriginalMessageId</span></span>  
  
    -   <span data-ttu-id="4b7ab-115">ReceivedContentMic</span><span class="sxs-lookup"><span data-stu-id="4b7ab-115">ReceivedContentMic</span></span>  
  
    -   <span data-ttu-id="4b7ab-116">DispositionMode</span><span class="sxs-lookup"><span data-stu-id="4b7ab-116">DispositionMode</span></span>  
  
    -   <span data-ttu-id="4b7ab-117">MessageId</span><span class="sxs-lookup"><span data-stu-id="4b7ab-117">MessageId</span></span>  
  
-   <span data-ttu-id="4b7ab-118">将 InboundHttpHeaders 属性设置为消息的所有 HTTP 标头，并将其升级到消息的上下文中。</span><span class="sxs-lookup"><span data-stu-id="4b7ab-118">Sets the InboundHttpHeaders property to all the HTTP headers of the message, and promotes it to the context of the message.</span></span>  
  
-   <span data-ttu-id="4b7ab-119">创建 MDN 的副本（以传输格式）并将该副本存储在不可否认数据库（BizTalkDTADb 数据库的 EdiMessageContent 表）中（如果在单向 AS2 协议属性中启用了相应选项）。</span><span class="sxs-lookup"><span data-stu-id="4b7ab-119">Makes a copy of the MDN (in wire format), and stores the copy in the non-repudiation database (the EdiMessageContent table of the BizTalkDTADb database), if enabled in the one-way AS2 agreement properties.</span></span>  
  
-   <span data-ttu-id="4b7ab-120">执行 MIME 处理，其中包括验证签名（如果对 MDN 进行了签名）。</span><span class="sxs-lookup"><span data-stu-id="4b7ab-120">Performs MIME processing, including verifying the signature if the MDN was signed.</span></span>  
  
-   <span data-ttu-id="4b7ab-121">将 MDN 中的 MIC（消息完整性检查）与 AS2Send 管道在发送原始消息时所计算的数据存储区中的 MIC 进行比较（如果适用）。</span><span class="sxs-lookup"><span data-stu-id="4b7ab-121">Compares the MIC (Message Integrity Check) in the MDN with the MIC in the data store that was computed by the AS2Send pipeline when it sent out the original message (if applicable).</span></span> <span data-ttu-id="4b7ab-122">有关详细信息，请参阅[MDN 消息](../core/mdn-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="4b7ab-122">For more information, see [MDN Messages](../core/mdn-messages.md).</span></span>  
  
-   <span data-ttu-id="4b7ab-123">在不可否认数据库中创建相关条目。</span><span class="sxs-lookup"><span data-stu-id="4b7ab-123">Makes correlation entries in the non-repudiation database.</span></span>  
  
-   <span data-ttu-id="4b7ab-124">除非删除 MDN，**路由/传递到 MessageBox 处理入站的 MDN**属性在中设置**发件人 MDN 设置**的单向 AS2 协议选项卡页**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="4b7ab-124">Deletes the MDN, unless the **Process inbound MDN into MessageBox for routing/delivery options** property is set in the **Sender MDN Settings** page of the one-way AS2 agreement tab of the **Agreement Properties** dialog box.</span></span>  
  
-   <span data-ttu-id="4b7ab-125">如果**路由/传递到 MessageBox 处理入站的 MDN**属性在中设置**发件人 MDN 设置**的单向 AS2 协议选项卡页**协议属性**对话框中，接收管道将 MDN 路由中通过 AS2 解码器作为传递消息的连网格式，并将它放置到 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="4b7ab-125">If the **Process inbound MDN into MessageBox for routing/delivery options** property is set in the **Sender MDN Settings** page of the one-way AS2 agreement tab of the **Agreement Properties** dialog box, the receive pipeline routes the MDN in wire format through the AS2 Decoder as a passthrough message and drops it into the MessageBox.</span></span> <span data-ttu-id="4b7ab-126">传输格式的 MDN 包含所有 HTTP 标头。</span><span class="sxs-lookup"><span data-stu-id="4b7ab-126">The MDN in wire format contains all HTTP headers.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4b7ab-127">可以设置发送端口以订阅已放入 MessageBox 中的收到的 MDN。</span><span class="sxs-lookup"><span data-stu-id="4b7ab-127">You can set up a send port to subscribe to a received MDN that has been dropped into the MessageBox.</span></span> <span data-ttu-id="4b7ab-128">若要订阅收到的 MDN，请将发送端口筛选器设置为 `IsAS2MdnResponseMessage==True`。</span><span class="sxs-lookup"><span data-stu-id="4b7ab-128">To subscribe to the received MDN, set the send port filter to `IsAS2MdnResponseMessage==True`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4b7ab-129">如果你使用 AS2EdiReceive 管道处理收到的 MDN，不能通过设置，到 MessageBox 路由 MDN**路由/传递到 MessageBox 处理入站的 MDN**中的属性**发件人 MDN设置**的单向 AS2 协议选项卡页**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="4b7ab-129">If you use the AS2EdiReceive pipeline to process a received MDN, you cannot route the MDN into the MessageBox by setting the **Process inbound MDN into MessageBox for routing/delivery options** property in the **Sender MDN Settings** page of the one-way AS2 agreement tab of the **Agreement Properties** dialog box.</span></span> <span data-ttu-id="4b7ab-130">如果尝试进行此操作，将会导致一个 EDI 错误，因为 MDN 将传递至 EDI 解码器，而 EDI 解码器无法对 MDN 进行处理。</span><span class="sxs-lookup"><span data-stu-id="4b7ab-130">Trying to do so will result in an EDI error because the MDN will be passed to the EDI Decoder, which cannot process an MDN.</span></span> <span data-ttu-id="4b7ab-131">如果 MDN 不发送到 MessageBox，则 AS2Decoder 将使用该 MDN，因此不会将其传递到 EDI 解码器。</span><span class="sxs-lookup"><span data-stu-id="4b7ab-131">If the MDN is not sent to the MessageBox, the AS2Decoder will consume the MDN, so it will not be passed to the EDI Decoder.</span></span>  
  
## <a name="message-integrity-check"></a><span data-ttu-id="4b7ab-132">消息完整性检查</span><span class="sxs-lookup"><span data-stu-id="4b7ab-132">Message Integrity Check</span></span>  
 <span data-ttu-id="4b7ab-133">消息完整性检查 (MIC) 用于验证 MDN 与已发送的原始消息相关联。</span><span class="sxs-lookup"><span data-stu-id="4b7ab-133">The Message Integrity Check (MIC) is used to verify that an MDN correlates to the original sent message.</span></span> <span data-ttu-id="4b7ab-134">AS2Send 发送管道在生成原始 AS2 消息时将计算来自消息负载的 MIC，并将该 MIC 存储在数据存储区中。</span><span class="sxs-lookup"><span data-stu-id="4b7ab-134">The AS2Send send pipeline calculates the MIC from the message payload when it generates the original AS2 message, and stores the MIC in the data store.</span></span> <span data-ttu-id="4b7ab-135">需要 MDN 时，原始消息的接收方将生成一个 MIC 并将其添加到该 MDN。</span><span class="sxs-lookup"><span data-stu-id="4b7ab-135">When an MDN is required, the recipient of the original message generates an MIC and adds it to the MDN.</span></span> <span data-ttu-id="4b7ab-136">当 AS2MdnReceive 接收管道接收 MDN 时，如果需要一个经过签名的 MDN，则它会将 MDN 中的 MIC 与数据存储区中的 MIC 进行比较。</span><span class="sxs-lookup"><span data-stu-id="4b7ab-136">When the AS2MdnReceive receive pipeline receives the MDN, if a signed MDN was requested, it compares the MIC in the MDN with the MIC in the data store.</span></span>  
  
 <span data-ttu-id="4b7ab-137">MDN 中的 MIC 与数据存储区中的 MIC 不匹配表明接收方在传输或接收消息期间发生了错误。</span><span class="sxs-lookup"><span data-stu-id="4b7ab-137">A mismatch between the MIC in the MDN and the MIC in the data store indicates that there was an error during transmission or receipt of the message by the receiving party.</span></span> <span data-ttu-id="4b7ab-138">发生此类错误时将报告如下值：</span><span class="sxs-lookup"><span data-stu-id="4b7ab-138">The values reported in such a failure are the following:</span></span>  
  
-   <span data-ttu-id="4b7ab-139">AS2DispositionType：失败</span><span class="sxs-lookup"><span data-stu-id="4b7ab-139">AS2DispositionType: Failed</span></span>  
  
-   <span data-ttu-id="4b7ab-140">AS2DispositionModifierExtensionType：错误</span><span class="sxs-lookup"><span data-stu-id="4b7ab-140">AS2DispositionModifierExtensionType: Error</span></span>  
  
-   <span data-ttu-id="4b7ab-141">AS2DispositionModifierExtensionDescription：完整性检查失败</span><span class="sxs-lookup"><span data-stu-id="4b7ab-141">AS2DispositionModifierExtensionDescription: Integrity Check Failed</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b7ab-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4b7ab-142">See Also</span></span>  
 <span data-ttu-id="4b7ab-143">[BizTalk Server 接收 AS2 消息的方式](../core/how-biztalk-server-receives-as2-messages.md) </span><span class="sxs-lookup"><span data-stu-id="4b7ab-143">[How BizTalk Server Receives AS2 Messages](../core/how-biztalk-server-receives-as2-messages.md) </span></span>  
 [<span data-ttu-id="4b7ab-144">MDN 消息</span><span class="sxs-lookup"><span data-stu-id="4b7ab-144">MDN Messages</span></span>](../core/mdn-messages.md)