---
title: 处理传入 MDN |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd78e84c-4989-47e4-b95b-80582084ddec
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63d575f78d41fdf4cb6e3902354bf218579faad7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65299880"
---
# <a name="processing-an-incoming-mdn"></a><span data-ttu-id="9722c-102">处理传入 MDN</span><span class="sxs-lookup"><span data-stu-id="9722c-102">Processing an Incoming MDN</span></span>
<span data-ttu-id="9722c-103">AS2 接收管道 （AS2EDIReceive 和 AS2Receive） 处理传入 MDN 基于作为 AS2 消息接收方的参与方的协议属性。</span><span class="sxs-lookup"><span data-stu-id="9722c-103">The AS2 receive pipelines (AS2EDIReceive and AS2Receive) process an incoming MDN based upon the agreement properties for the party as an AS2 message receiver.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="9722c-104">自动将 MDN 与传出 AS2 消息相关联。</span><span class="sxs-lookup"><span data-stu-id="9722c-104">automatically correlates the MDN to the outgoing AS2 message.</span></span>  
  
 <span data-ttu-id="9722c-105">每个管道执行的步骤如下所示：</span><span class="sxs-lookup"><span data-stu-id="9722c-105">The steps each pipeline performs are as follows:</span></span>  
  
-   <span data-ttu-id="9722c-106">进行匹配 AS2 来确定发送参与方的消息的 AS2 头部中 AS2 的值的值从-从列表中**标识符**的单向 AS2 协议选项卡页**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="9722c-106">Determines the sending party by matching the AS2-From value in the AS2 header of the message with the value for AS2-From list in the **Identifiers** page of the one-way AS2 agreement tab of the **Agreement Properties** dialog box.</span></span> <span data-ttu-id="9722c-107">如果找不到匹配项，管道将中止处理并引发异常。</span><span class="sxs-lookup"><span data-stu-id="9722c-107">If a match is not found, the pipeline aborts processing and raises an exception.</span></span>  
  
-   <span data-ttu-id="9722c-108">升级到上下文下列 AS2 属性：</span><span class="sxs-lookup"><span data-stu-id="9722c-108">Promotes the following AS2 properties to the context:</span></span>  
  
    -   <span data-ttu-id="9722c-109">IsAS2FailedMessage</span><span class="sxs-lookup"><span data-stu-id="9722c-109">IsAS2FailedMessage</span></span>  
  
    -   <span data-ttu-id="9722c-110">DispositionType</span><span class="sxs-lookup"><span data-stu-id="9722c-110">DispositionType</span></span>  
  
    -   <span data-ttu-id="9722c-111">GenerateAsynchronous200OKOnly</span><span class="sxs-lookup"><span data-stu-id="9722c-111">GenerateAsynchronous200OKOnly</span></span>  
  
    -   <span data-ttu-id="9722c-112">IsAS2MdnResponseMessage</span><span class="sxs-lookup"><span data-stu-id="9722c-112">IsAS2MdnResponseMessage</span></span>  
  
    -   <span data-ttu-id="9722c-113">IsAS2MessageSigned</span><span class="sxs-lookup"><span data-stu-id="9722c-113">IsAS2MessageSigned</span></span>  
  
    -   <span data-ttu-id="9722c-114">OriginalMessageId</span><span class="sxs-lookup"><span data-stu-id="9722c-114">OriginalMessageId</span></span>  
  
    -   <span data-ttu-id="9722c-115">ReceivedContentMic</span><span class="sxs-lookup"><span data-stu-id="9722c-115">ReceivedContentMic</span></span>  
  
    -   <span data-ttu-id="9722c-116">DispositionMode</span><span class="sxs-lookup"><span data-stu-id="9722c-116">DispositionMode</span></span>  
  
    -   <span data-ttu-id="9722c-117">MessageId</span><span class="sxs-lookup"><span data-stu-id="9722c-117">MessageId</span></span>  
  
-   <span data-ttu-id="9722c-118">将 InboundHttpHeaders 属性设置为所有 HTTP 标头的消息，并将其升级到消息的上下文。</span><span class="sxs-lookup"><span data-stu-id="9722c-118">Sets the InboundHttpHeaders property to all the HTTP headers of the message, and promotes it to the context of the message.</span></span>  
  
-   <span data-ttu-id="9722c-119">创建 MDN 的副本 （以传输格式），并将该副本存储在不可否认数据库 （BizTalkDTADb 数据库的 EdiMessageContent 表），如果在单向 AS2 协议属性中启用。</span><span class="sxs-lookup"><span data-stu-id="9722c-119">Makes a copy of the MDN (in wire format), and stores the copy in the non-repudiation database (the EdiMessageContent table of the BizTalkDTADb database), if enabled in the one-way AS2 agreement properties.</span></span>  
  
-   <span data-ttu-id="9722c-120">执行 MIME 处理，其中包括验证签名，如果已签名 MDN。</span><span class="sxs-lookup"><span data-stu-id="9722c-120">Performs MIME processing, including verifying the signature if the MDN was signed.</span></span>  
  
-   <span data-ttu-id="9722c-121">AS2Send 管道发送原始消息 （如果适用） 时所计算的数据存储区中的 mic MDN 中比较的 MIC （消息完整性检查）。</span><span class="sxs-lookup"><span data-stu-id="9722c-121">Compares the MIC (Message Integrity Check) in the MDN with the MIC in the data store that was computed by the AS2Send pipeline when it sent out the original message (if applicable).</span></span> <span data-ttu-id="9722c-122">有关详细信息，请参阅[MDN 消息](../core/mdn-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="9722c-122">For more information, see [MDN Messages](../core/mdn-messages.md).</span></span>  
  
-   <span data-ttu-id="9722c-123">不可否认数据库中创建相关条目。</span><span class="sxs-lookup"><span data-stu-id="9722c-123">Makes correlation entries in the non-repudiation database.</span></span>  
  
-   <span data-ttu-id="9722c-124">删除 MDN，除非**到 MessageBox 中处理入站的 MDN 以进行路由/传递**属性中设置**发送方 MDN 设置**的单向 AS2 协议选项卡页**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="9722c-124">Deletes the MDN, unless the **Process inbound MDN into MessageBox for routing/delivery options** property is set in the **Sender MDN Settings** page of the one-way AS2 agreement tab of the **Agreement Properties** dialog box.</span></span>  
  
-   <span data-ttu-id="9722c-125">如果**到 MessageBox 中处理入站的 MDN 以进行路由/传递**属性中设置**发送方 MDN 设置**的单向 AS2 协议选项卡页**协议属性**对话框中，接收管道将 MDN 路由以通过 AS2 解码器作为直通消息传输格式，并将其放入 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="9722c-125">If the **Process inbound MDN into MessageBox for routing/delivery options** property is set in the **Sender MDN Settings** page of the one-way AS2 agreement tab of the **Agreement Properties** dialog box, the receive pipeline routes the MDN in wire format through the AS2 Decoder as a passthrough message and drops it into the MessageBox.</span></span> <span data-ttu-id="9722c-126">以传输格式的 MDN 包含所有 HTTP 标头。</span><span class="sxs-lookup"><span data-stu-id="9722c-126">The MDN in wire format contains all HTTP headers.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9722c-127">可以设置发送端口以订阅收到的 MDN 放入 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="9722c-127">You can set up a send port to subscribe to a received MDN that has been dropped into the MessageBox.</span></span> <span data-ttu-id="9722c-128">若要订阅收到的 MDN，请将发送端口筛选器设置为`IsAS2MdnResponseMessage==True`。</span><span class="sxs-lookup"><span data-stu-id="9722c-128">To subscribe to the received MDN, set the send port filter to `IsAS2MdnResponseMessage==True`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9722c-129">如果使用 AS2EdiReceive 管道处理收到的 MDN，则不能将 MDN 路由到 MessageBox 中通过设置**到 MessageBox 中处理入站的 MDN 以进行路由/传递**属性中的**发送方 MDN设置**页的单向 AS2 协议选项卡**协议属性**对话框。</span><span class="sxs-lookup"><span data-stu-id="9722c-129">If you use the AS2EdiReceive pipeline to process a received MDN, you cannot route the MDN into the MessageBox by setting the **Process inbound MDN into MessageBox for routing/delivery options** property in the **Sender MDN Settings** page of the one-way AS2 agreement tab of the **Agreement Properties** dialog box.</span></span> <span data-ttu-id="9722c-130">尝试进行此操作将导致一个 EDI 错误，因为 MDN 将传递至 EDI 解码器，将无法对 MDN 进行处理。</span><span class="sxs-lookup"><span data-stu-id="9722c-130">Trying to do so will result in an EDI error because the MDN will be passed to the EDI Decoder, which cannot process an MDN.</span></span> <span data-ttu-id="9722c-131">如果 MDN 不发送到 MessageBox，则 AS2Decoder 将使用该 MDN，因此它不会传递到 EDI 解码器。</span><span class="sxs-lookup"><span data-stu-id="9722c-131">If the MDN is not sent to the MessageBox, the AS2Decoder will consume the MDN, so it will not be passed to the EDI Decoder.</span></span>  
  
## <a name="message-integrity-check"></a><span data-ttu-id="9722c-132">消息完整性检查</span><span class="sxs-lookup"><span data-stu-id="9722c-132">Message Integrity Check</span></span>  
 <span data-ttu-id="9722c-133">消息完整性检查 (MIC) 用于验证 MDN 关联到原始发送的消息。</span><span class="sxs-lookup"><span data-stu-id="9722c-133">The Message Integrity Check (MIC) is used to verify that an MDN correlates to the original sent message.</span></span> <span data-ttu-id="9722c-134">AS2Send 发送管道时将计算从消息负载的 MIC 生成原始 AS2 消息，并将该 MIC 存储在数据存储区中。</span><span class="sxs-lookup"><span data-stu-id="9722c-134">The AS2Send send pipeline calculates the MIC from the message payload when it generates the original AS2 message, and stores the MIC in the data store.</span></span> <span data-ttu-id="9722c-135">需要 MDN 时，原始消息的接收方生成一个 MIC 并将其添加到该 MDN。</span><span class="sxs-lookup"><span data-stu-id="9722c-135">When an MDN is required, the recipient of the original message generates an MIC and adds it to the MDN.</span></span> <span data-ttu-id="9722c-136">当 AS2MdnReceive 接收管道接收 MDN，如果已请求经过签名的 MDN，它比较 MDN 中的 mic 数据存储区中的 MIC。</span><span class="sxs-lookup"><span data-stu-id="9722c-136">When the AS2MdnReceive receive pipeline receives the MDN, if a signed MDN was requested, it compares the MIC in the MDN with the MIC in the data store.</span></span>  
  
 <span data-ttu-id="9722c-137">MDN 中的 MIC 数据存储区中的 MIC 不匹配指示在传输或接收到消息接收方期间出现错误。</span><span class="sxs-lookup"><span data-stu-id="9722c-137">A mismatch between the MIC in the MDN and the MIC in the data store indicates that there was an error during transmission or receipt of the message by the receiving party.</span></span> <span data-ttu-id="9722c-138">在此类故障报告的值如下所示：</span><span class="sxs-lookup"><span data-stu-id="9722c-138">The values reported in such a failure are the following:</span></span>  
  
-   <span data-ttu-id="9722c-139">AS2DispositionType:失败</span><span class="sxs-lookup"><span data-stu-id="9722c-139">AS2DispositionType: Failed</span></span>  
  
-   <span data-ttu-id="9722c-140">AS2DispositionModifierExtensionType:错误</span><span class="sxs-lookup"><span data-stu-id="9722c-140">AS2DispositionModifierExtensionType: Error</span></span>  
  
-   <span data-ttu-id="9722c-141">AS2DispositionModifierExtensionDescription:完整性检查失败</span><span class="sxs-lookup"><span data-stu-id="9722c-141">AS2DispositionModifierExtensionDescription: Integrity Check Failed</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9722c-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="9722c-142">See Also</span></span>  
 <span data-ttu-id="9722c-143">[BizTalk Server 如何接收 AS2 消息](../core/how-biztalk-server-receives-as2-messages.md) </span><span class="sxs-lookup"><span data-stu-id="9722c-143">[How BizTalk Server Receives AS2 Messages](../core/how-biztalk-server-receives-as2-messages.md) </span></span>  
 [<span data-ttu-id="9722c-144">MDN 消息</span><span class="sxs-lookup"><span data-stu-id="9722c-144">MDN Messages</span></span>](../core/mdn-messages.md)