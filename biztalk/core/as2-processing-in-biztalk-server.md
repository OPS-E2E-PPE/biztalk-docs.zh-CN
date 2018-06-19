---
title: AS2 在 BizTalk Server 中的处理 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0027d3db-24a5-459d-9f4e-a75f49d31d82
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 11a5bb12d9a7b21a18b92162370d7be14feda8dc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233733"
---
# <a name="as2-processing-in-biztalk-server"></a><span data-ttu-id="004a1-102">BizTalk Server 中的 AS2 处理</span><span class="sxs-lookup"><span data-stu-id="004a1-102">AS2 Processing in BizTalk Server</span></span>
<span data-ttu-id="004a1-103">本主题概述了 AS2 消息的接收端和发送端处理过程以及贸易合作伙伴协议将如何帮助您实现 AS2 消息传送。</span><span class="sxs-lookup"><span data-stu-id="004a1-103">This topic provides an overview of receive-side and send-side processing of AS2 messages, and how trading partner agreements can help achieve AS2 messaging.</span></span>  
  
## <a name="trading-partner-agreements-for-as2-processing"></a><span data-ttu-id="004a1-104">用于 AS2 处理的贸易合作伙伴协议</span><span class="sxs-lookup"><span data-stu-id="004a1-104">Trading Partner Agreements for AS2 Processing</span></span>  
 <span data-ttu-id="004a1-105">贸易合作伙伴协议在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中的 AS2 支持中起着重要作用。</span><span class="sxs-lookup"><span data-stu-id="004a1-105">Trading partner agreements play a key role in AS2 support in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="004a1-106">与 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中的 AS2 处理相关的大多数配置和管理功能是通过配置业务配置文件之间的贸易合作伙伴协议来执行的。</span><span class="sxs-lookup"><span data-stu-id="004a1-106">Most configuration and administrative functions related to AS2 processing in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] are performed by configuring the trading partner agreements between business profiles.</span></span> <span data-ttu-id="004a1-107">协议集中了处理各种属性（来自合作伙伴双方的特定业务配置文件）的常见双向消息。</span><span class="sxs-lookup"><span data-stu-id="004a1-107">Agreements bring together common bi-directional message processing properties from specific business profiles of both partners.</span></span> <span data-ttu-id="004a1-108">协议基于为每个业务配置文件定义的协议设置构建。</span><span class="sxs-lookup"><span data-stu-id="004a1-108">Agreements are built upon the protocol settings defined for each business profile.</span></span> <span data-ttu-id="004a1-109">可通过为将交换消息的每个业务配置文件定义属性来实现两个业务配置文件之间的贸易合作伙伴协议。</span><span class="sxs-lookup"><span data-stu-id="004a1-109">You implement a trading partner agreement between two business profiles by defining properties for each business profile that will be exchanging messages.</span></span> <span data-ttu-id="004a1-110">在贸易合作伙伴管理 (PAM) 用户界面中设置作为 AS2 消息接收方和 AS2 消息发送方的每个业务配置文件的属性。</span><span class="sxs-lookup"><span data-stu-id="004a1-110">You set properties for each business profile as an AS2 message receiver and an AS2 message sender in the Trading Partner Management (TPM) user interface.</span></span> <span data-ttu-id="004a1-111">TPM 屏幕处于**方**节点[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="004a1-111">The TPM screens are in the **Parties** node of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span> <span data-ttu-id="004a1-112">您无需是开发人员即可在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中配置 AS2 处理。</span><span class="sxs-lookup"><span data-stu-id="004a1-112">You do not have to be a developer to configure AS2 processing in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="004a1-113">您可以作为业务配置文件的“传输协议设置”的一部分指定 AS2 属性，也可以通过在贸易合作伙伴协议中直接指定 AS2 设置来指定 AS2 属性。</span><span class="sxs-lookup"><span data-stu-id="004a1-113">You can specify the AS2 properties as part of the “transport protocol settings” for a business profile or by directly specifying the AS2 settings in the trading partner agreement.</span></span> <span data-ttu-id="004a1-114">有关协议设置的详细信息，请参阅[协议设置](../core/protocol-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="004a1-114">For more information about the protocol settings, see [Protocol Settings](../core/protocol-settings.md).</span></span> <span data-ttu-id="004a1-115">有关协议的详细信息，请参阅[贸易合作伙伴协议](../core/trading-partner-agreement.md)。</span><span class="sxs-lookup"><span data-stu-id="004a1-115">For more information about agreements, see [Trading Partner Agreement](../core/trading-partner-agreement.md).</span></span>  <span data-ttu-id="004a1-116">您可设置特定于 AS2 的属性来配置下列 AS2 功能：</span><span class="sxs-lookup"><span data-stu-id="004a1-116">You configure the following AS2 functionality by setting the AS2-specific properties:</span></span>  
  
-   <span data-ttu-id="004a1-117">选择不可否认存储选项</span><span class="sxs-lookup"><span data-stu-id="004a1-117">Select non-repudiation storage options</span></span>  
  
-   <span data-ttu-id="004a1-118">为传出消息指定签名、压缩或加密属性</span><span class="sxs-lookup"><span data-stu-id="004a1-118">Specify signing, compression, or encryption properties for outgoing messages</span></span>  
  
-   <span data-ttu-id="004a1-119">为传出消息请求 MDN</span><span class="sxs-lookup"><span data-stu-id="004a1-119">Request MDNs for outgoing messages</span></span>  
  
-   <span data-ttu-id="004a1-120">通过替代 AS2 消息标头中的签名、压缩、加密和 MDN 属性可设置传入 MDN 的属性。</span><span class="sxs-lookup"><span data-stu-id="004a1-120">Set properties for incoming MDNs by overriding the signing, compression, encryption, and MDN properties in the header of the AS2 message.</span></span>  
  
 <span data-ttu-id="004a1-121">有关在 AS2 处理过程中如何贸易合作伙伴协议帮助的详细信息，请参阅[AS2 处理的协议角色](../core/the-role-of-agreements-in-as2-processing.md)。</span><span class="sxs-lookup"><span data-stu-id="004a1-121">For more information about how trading partner agreements help in AS2 processing, see [The Role of Agreements in AS2 Processing](../core/the-role-of-agreements-in-as2-processing.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="004a1-122">AS2 处理没有全局属性，这与 EDI 处理不同。</span><span class="sxs-lookup"><span data-stu-id="004a1-122">There are no global properties for AS2 processing, as there are for EDI processing.</span></span>  
  
## <a name="as2-receive-side-processing"></a><span data-ttu-id="004a1-123">AS2 接收端处理</span><span class="sxs-lookup"><span data-stu-id="004a1-123">AS2 Receive-Side Processing</span></span>  
 <span data-ttu-id="004a1-124">当 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收一个 AS2 消息后，它将在 AS2 接收管道中处理该消息。</span><span class="sxs-lookup"><span data-stu-id="004a1-124">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receives an AS2 message, it processes the message in an AS2 receive pipeline.</span></span> <span data-ttu-id="004a1-125">系统中存在一个用于通过 AS2 接收 EDI 消息的管道 (AS2EdiReceive)，此管道执行 AS2 和 EDI 处理。</span><span class="sxs-lookup"><span data-stu-id="004a1-125">There is a pipeline for receiving an EDI message over AS2 (AS2EdiReceive), which performs both AS2 and EDI processing.</span></span> <span data-ttu-id="004a1-126">另一个管道 (AS2Receive) 只对通过 AS2 接收的非 EDI 消息执行 AS2 处理。</span><span class="sxs-lookup"><span data-stu-id="004a1-126">Another pipeline (AS2Receive) performs only AS2 processing for non-EDI messages received over AS2.</span></span>  
  
 <span data-ttu-id="004a1-127">AS2 接收方处理包括下列操作：</span><span class="sxs-lookup"><span data-stu-id="004a1-127">AS2 receive-side processing includes the following:</span></span>  
  
-   <span data-ttu-id="004a1-128">贸易合作伙伴协议查找</span><span class="sxs-lookup"><span data-stu-id="004a1-128">Trading partner agreement lookup</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="004a1-129">在以前版本的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，参与方定义还包括协议定义。</span><span class="sxs-lookup"><span data-stu-id="004a1-129">In the previous versions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], a party definition also included the agreement definition.</span></span> <span data-ttu-id="004a1-130">因此，当接收管道查找参与方属性时，它将从内部查找参与方定义中的协议定义，然后相应地处理这些消息。</span><span class="sxs-lookup"><span data-stu-id="004a1-130">So, when the receive pipeline looked up the party properties, it would internally look for the agreement definition within the party definition and then process the messages accordingly.</span></span> <span data-ttu-id="004a1-131">对于 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，由于参与方（或贸易合作伙伴）与贸易合作伙伴协议截然不同，因此接收管道将特别查找贸易合作伙伴协作。</span><span class="sxs-lookup"><span data-stu-id="004a1-131">With [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], because the party (or trading partner) is distinct from the trading partner agreement, the receive pipeline looks for the trading partner agreement specifically.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="004a1-132">如果禁用某个消息解析到的所有协议，则该消息将被挂起。</span><span class="sxs-lookup"><span data-stu-id="004a1-132">If all the agreements that a message resolves to are disabled, the message will be suspended.</span></span>  <span data-ttu-id="004a1-133">还会在“事件”日志中记录警告。</span><span class="sxs-lookup"><span data-stu-id="004a1-133">A warning is also logged in the Event log.</span></span>  
  
-   <span data-ttu-id="004a1-134">在不可否认数据库中保存消息副本</span><span class="sxs-lookup"><span data-stu-id="004a1-134">Saving copies of the message in the non-repudiation database</span></span>  
  
-   <span data-ttu-id="004a1-135">检查重复的消息</span><span class="sxs-lookup"><span data-stu-id="004a1-135">Check for duplicate messages</span></span>  
  
-   <span data-ttu-id="004a1-136">处理包含多个文档的消息</span><span class="sxs-lookup"><span data-stu-id="004a1-136">Processing messages containing multiple documents</span></span>  
  
-   <span data-ttu-id="004a1-137">从 MIME 信封中检索文档文件名称</span><span class="sxs-lookup"><span data-stu-id="004a1-137">Retrieving a documents file name from the MIME envelope</span></span>  
  
-   <span data-ttu-id="004a1-138">解密消息</span><span class="sxs-lookup"><span data-stu-id="004a1-138">Decrypting the message</span></span>  
  
-   <span data-ttu-id="004a1-139">解压缩消息</span><span class="sxs-lookup"><span data-stu-id="004a1-139">Decompressing the message</span></span>  
  
-   <span data-ttu-id="004a1-140">验证消息的数字签名。</span><span class="sxs-lookup"><span data-stu-id="004a1-140">Verifying the digital signature of the message</span></span>  
  
-   <span data-ttu-id="004a1-141">生成 HTTP 响应</span><span class="sxs-lookup"><span data-stu-id="004a1-141">Generating an HTTP response</span></span>  
  
-   <span data-ttu-id="004a1-142">生成 MDN 响应</span><span class="sxs-lookup"><span data-stu-id="004a1-142">Generating an MDN response</span></span>  
  
 <span data-ttu-id="004a1-143">以下是您在使用 AS2 接收端处理时必须考虑的一些注意事项：</span><span class="sxs-lookup"><span data-stu-id="004a1-143">Following are some considerations that you must make while using AS2 receive-side processing:</span></span>  
  
-   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="004a1-144"> 以同步或异步模式返回一个 MDN。</span><span class="sxs-lookup"><span data-stu-id="004a1-144"> returns an MDN in either synchronous or asynchronous mode.</span></span> <span data-ttu-id="004a1-145">如果将以异步方式返回 MDN，则 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 必须通过一个单独的发送端口发送它。</span><span class="sxs-lookup"><span data-stu-id="004a1-145">If the MDN will be returned asynchronously, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] must send it over a separate send port.</span></span>  
  
-   <span data-ttu-id="004a1-146">通过 AS2 接收非 EDI 文件（非 XML），并且需要执行非 EDI 负载的拆装时，您将需要一种具有第二个接收管道的环回机制。</span><span class="sxs-lookup"><span data-stu-id="004a1-146">When you receive a non-EDI file (not XML) over AS2, and you need to perform disassembly of the non-EDI payload, you will need to use requires a loopback mechanism with a second receive pipeline.</span></span> <span data-ttu-id="004a1-147">有关详细信息，请参阅[接收方处理的传入通过 AS2 非 EDI 消息](../core/receive-side-processing-of-an-incoming-non-edi-message-over-as2.md)。</span><span class="sxs-lookup"><span data-stu-id="004a1-147">For more information, see [Receive-Side Processing of an Incoming Non-EDI Message over AS2](../core/receive-side-processing-of-an-incoming-non-edi-message-over-as2.md).</span></span>  
  
-   <span data-ttu-id="004a1-148">接收位置只能使用 HTTP 适配器。</span><span class="sxs-lookup"><span data-stu-id="004a1-148">The receive location can only use the HTTP adapter.</span></span>  
  
-   <span data-ttu-id="004a1-149">AS2 接收方处理的详细信息，请参阅[如何 BizTalk Server 接收 AS2 消息](../core/how-biztalk-server-receives-as2-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="004a1-149">For more information about AS2 receive-side processing, see [How BizTalk Server Receives AS2 Messages](../core/how-biztalk-server-receives-as2-messages.md).</span></span>  
  
-   <span data-ttu-id="004a1-150">有关通过 AS2 拆装器接收管道中执行的特定处理的详细信息，请参阅[处理传入 AS2 消息](../core/processing-an-incoming-as2-message.md)。</span><span class="sxs-lookup"><span data-stu-id="004a1-150">For more information about the specific processing performed by the AS2 Disassembler in the receive pipeline, see [Processing an Incoming AS2 Message](../core/processing-an-incoming-as2-message.md).</span></span>  
  
## <a name="as2-send-side-processing"></a><span data-ttu-id="004a1-151">AS2 接收方处理</span><span class="sxs-lookup"><span data-stu-id="004a1-151">AS2 Send-Side Processing</span></span>  
 <span data-ttu-id="004a1-152">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 生成并发送传出 AS2 消息时，将在 AS2 发送管道中处理该消息。</span><span class="sxs-lookup"><span data-stu-id="004a1-152">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generates and sends an outgoing AS2 message, it processes the message in an AS2 send pipeline.</span></span> <span data-ttu-id="004a1-153">系统中存在一个用于通过 AS2 发送 EDI 消息的管道 (AS2EdiSend)，此管道执行 AS2 和 EDI 处理。</span><span class="sxs-lookup"><span data-stu-id="004a1-153">There is a pipeline for sending an EDI message over AS2 (AS2EdiSend), which performs both AS2 and EDI processing.</span></span> <span data-ttu-id="004a1-154">另一个管道 (AS2Send) 只对通过 AS2 发送的非 EDI 消息执行 AS2 处理。</span><span class="sxs-lookup"><span data-stu-id="004a1-154">Another pipeline (AS2Send) performs only AS2 processing for non-EDI messages sent over AS2.</span></span>  
  
 <span data-ttu-id="004a1-155">AS2 发送方处理包括下列操作：</span><span class="sxs-lookup"><span data-stu-id="004a1-155">AS2 send-side processing includes the following:</span></span>  
  
-   <span data-ttu-id="004a1-156">贸易合作伙伴协议查找</span><span class="sxs-lookup"><span data-stu-id="004a1-156">Trading partner agreement lookup</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="004a1-157">在以前版本的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，参与方定义还包括协议定义。</span><span class="sxs-lookup"><span data-stu-id="004a1-157">In the previous versions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], a party definition also included the agreement definition.</span></span> <span data-ttu-id="004a1-158">因此，当发送管道查找参与方属性时，它将从内部查找参与方定义中的协议定义，然后相应地处理这些消息。</span><span class="sxs-lookup"><span data-stu-id="004a1-158">So, when the send pipeline looked up the party properties, it would internally look for the agreement definition within the party definition and then process the messages accordingly.</span></span> <span data-ttu-id="004a1-159">对于 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，由于参与方（或贸易合作伙伴）与贸易合作伙伴协议截然不同，因此发送管道将特别查找贸易合作伙伴协作。</span><span class="sxs-lookup"><span data-stu-id="004a1-159">With [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], because the party (or trading partner) is distinct from the trading partner agreement, the send pipeline looks for the trading partner agreement specifically.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="004a1-160">如果禁用某个消息解析到的所有协议，则该消息将被挂起。</span><span class="sxs-lookup"><span data-stu-id="004a1-160">If all the agreements that a message resolves to are disabled, the message will be suspended.</span></span>  <span data-ttu-id="004a1-161">还会在“事件”日志中记录警告。</span><span class="sxs-lookup"><span data-stu-id="004a1-161">A warning is also logged in the Event log.</span></span>  
  
-   <span data-ttu-id="004a1-162">在不可否认数据库中保存消息副本</span><span class="sxs-lookup"><span data-stu-id="004a1-162">Saving copies of the message in the non-repudiation database</span></span>  
  
-   <span data-ttu-id="004a1-163">应用 AS2 信封</span><span class="sxs-lookup"><span data-stu-id="004a1-163">Applying an AS2 envelope</span></span>  
  
-   <span data-ttu-id="004a1-164">发送多个文档</span><span class="sxs-lookup"><span data-stu-id="004a1-164">Sending multiple documents</span></span>  
  
-   <span data-ttu-id="004a1-165">作为 MIME 信封的一部分存储每个文档的文件名</span><span class="sxs-lookup"><span data-stu-id="004a1-165">Storing each documents filename as part of the MIME envelope</span></span>  
  
-   <span data-ttu-id="004a1-166">签名消息</span><span class="sxs-lookup"><span data-stu-id="004a1-166">Signing the message</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="004a1-167">通过 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，你可以覆盖默认签名证书，改用在协议中认可的证书。</span><span class="sxs-lookup"><span data-stu-id="004a1-167">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] enables you to override the default signing certificate and instead use a certificate agreed upon in the agreement.</span></span> <span data-ttu-id="004a1-168">有关重写默认证书以签署传出消息的说明，请参阅[配置 AS2 属性](../core/configuring-as2-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="004a1-168">For instructions on overriding default certificate for signing outgoing messages, see [Configuring AS2 Properties](../core/configuring-as2-properties.md).</span></span>  
  
-   <span data-ttu-id="004a1-169">压缩消息</span><span class="sxs-lookup"><span data-stu-id="004a1-169">Compressing the message</span></span>  
  
-   <span data-ttu-id="004a1-170">加密消息</span><span class="sxs-lookup"><span data-stu-id="004a1-170">Encrypting the message</span></span>  
  
-   <span data-ttu-id="004a1-171">为 MDN 计算一个 MIC 值</span><span class="sxs-lookup"><span data-stu-id="004a1-171">Computing an MIC value for the MDN</span></span>  
  
-   <span data-ttu-id="004a1-172">处理传入 MDN（在同步 MDN 情况下）</span><span class="sxs-lookup"><span data-stu-id="004a1-172">Processing an incoming MDN (in the case of a synchronous MDN)</span></span>  
  
-   <span data-ttu-id="004a1-173">如果未收到 MDN，则重新发送消息</span><span class="sxs-lookup"><span data-stu-id="004a1-173">Resending the message if no MDN is received</span></span>  
  
 <span data-ttu-id="004a1-174">以下是您在使用 AS2 接收端处理时必须考虑的一些注意事项：</span><span class="sxs-lookup"><span data-stu-id="004a1-174">Following are some considerations that you must make while using AS2 receive-side processing:</span></span>  
  
-   <span data-ttu-id="004a1-175">发送端口只能使用 HTTP 适配器。</span><span class="sxs-lookup"><span data-stu-id="004a1-175">The send port can only use the HTTP adapter.</span></span>  
  
-   <span data-ttu-id="004a1-176">有关 AS2 发送方处理的详细信息，请参阅[如何 BizTalk Server 发送 AS2 消息](../core/how-biztalk-server-sends-as2-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="004a1-176">For more information about AS2 send-side processing, see [How BizTalk Server Sends AS2 Messages](../core/how-biztalk-server-sends-as2-messages.md).</span></span>  
  
-   <span data-ttu-id="004a1-177">有关在发送管道中执行的特定处理的详细信息，请参阅[生成传出的 AS2 消息](../core/generating-an-outgoing-as2-message.md)。</span><span class="sxs-lookup"><span data-stu-id="004a1-177">For more information about the specific processing performed in the send pipeline, see [Generating an Outgoing AS2 Message](../core/generating-an-outgoing-as2-message.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="004a1-178">另请参阅</span><span class="sxs-lookup"><span data-stu-id="004a1-178">See Also</span></span>  
 <span data-ttu-id="004a1-179">[中 AS2 协议处理的角色](../core/the-role-of-agreements-in-as2-processing.md) </span><span class="sxs-lookup"><span data-stu-id="004a1-179">[The Role of Agreements in AS2 Processing](../core/the-role-of-agreements-in-as2-processing.md) </span></span>  
 <span data-ttu-id="004a1-180">[BizTalk Server 接收 AS2 消息的方式](../core/how-biztalk-server-receives-as2-messages.md) </span><span class="sxs-lookup"><span data-stu-id="004a1-180">[How BizTalk Server Receives AS2 Messages](../core/how-biztalk-server-receives-as2-messages.md) </span></span>  
 [<span data-ttu-id="004a1-181">BizTalk Server 将 AS2 消息的发送</span><span class="sxs-lookup"><span data-stu-id="004a1-181">How BizTalk Server Sends AS2 Messages</span></span>](../core/how-biztalk-server-sends-as2-messages.md)