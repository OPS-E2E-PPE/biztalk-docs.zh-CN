---
title: BizTalk Server 中的 EDI 处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bdc60423-24b6-4920-a870-520f575085ed
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5867707fccda26f0c8938226886d879bdd19d57a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350325"
---
# <a name="edi-processing-in-biztalk-server"></a><span data-ttu-id="29bfd-102">BizTalk Server 中的 EDI 处理</span><span class="sxs-lookup"><span data-stu-id="29bfd-102">EDI Processing in BizTalk Server</span></span>
<span data-ttu-id="29bfd-103">本主题概述的 EDI 消息，以及贸易合作伙伴协议如何帮助实现 EDI 消息的接收端和发送端处理。</span><span class="sxs-lookup"><span data-stu-id="29bfd-103">This topic provides an overview of receive-side and send-side processing of EDI messages, and how trading partner agreements can help achieve EDI messaging.</span></span>  
  
## <a name="trading-partner-agreements-for-edi-processing"></a><span data-ttu-id="29bfd-104">用于 EDI 处理的贸易合作伙伴协议</span><span class="sxs-lookup"><span data-stu-id="29bfd-104">Trading Partner Agreements for EDI Processing</span></span>  
 <span data-ttu-id="29bfd-105">贸易合作伙伴协议在 BizTalk Server 中的 EDI 支持中起重要作用。</span><span class="sxs-lookup"><span data-stu-id="29bfd-105">Trading partner agreements play a key role in EDI support in BizTalk Server.</span></span> <span data-ttu-id="29bfd-106">大多数配置和管理功能与中的 EDI 处理相关[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过配置业务配置文件之间的贸易合作伙伴协议来执行。</span><span class="sxs-lookup"><span data-stu-id="29bfd-106">Most configuration and administrative functions related to EDI processing in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] are performed by configuring the trading partner agreements between business profiles.</span></span> <span data-ttu-id="29bfd-107">协议将来自两个合作伙伴的特定业务配置文件的组合在一起的常见双向消息处理属性。</span><span class="sxs-lookup"><span data-stu-id="29bfd-107">Agreements bring together common bi-directional message processing properties from specific business profiles of both partners.</span></span> <span data-ttu-id="29bfd-108">协议基于为每个业务配置文件定义的协议设置。</span><span class="sxs-lookup"><span data-stu-id="29bfd-108">Agreements are built upon the protocol settings defined for each business profile.</span></span> <span data-ttu-id="29bfd-109">实现通过定义每个业务配置文件，将交换消息的属性的两个业务配置文件之间的贸易合作伙伴协议。</span><span class="sxs-lookup"><span data-stu-id="29bfd-109">You implement a trading partner agreement between two business profiles by defining properties for each business profile that will be exchanging messages.</span></span> <span data-ttu-id="29bfd-110">作为交换接收方和作为交换发送方设置每个业务配置文件的属性。</span><span class="sxs-lookup"><span data-stu-id="29bfd-110">You set properties for each business profile as an interchange receiver and as an interchange sender.</span></span> <span data-ttu-id="29bfd-111">若要处理的传入消息或生成传出消息时，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]需要知道可解析为的协议和适用于消息的架构。</span><span class="sxs-lookup"><span data-stu-id="29bfd-111">To process an incoming message or generate an outgoing message, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] needs to know the agreement that it resolves to, and the schema that applies to the message.</span></span> <span data-ttu-id="29bfd-112">如果[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]无法确定协议，它将使用 TPM 界面为后备贸易合作伙伴协议中定义的属性。</span><span class="sxs-lookup"><span data-stu-id="29bfd-112">If [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] cannot determine the agreement, it will use the properties defined in the TPM interface for the fallback trading partner agreement.</span></span>  
  
 <span data-ttu-id="29bfd-113">有两组主要的编码协议设置在 TPM 中： 一个用于 EDIFACT 属性，一个用于 X12 属性。</span><span class="sxs-lookup"><span data-stu-id="29bfd-113">There are two major sets of encoding protocol settings in TPM: one for EDIFACT properties and one for X12 properties.</span></span> <span data-ttu-id="29bfd-114">近两种属性集。</span><span class="sxs-lookup"><span data-stu-id="29bfd-114">The two sets of properties are closely parallel.</span></span> <span data-ttu-id="29bfd-115">有关协议设置的详细信息，请参阅[协议设置](../core/protocol-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="29bfd-115">For more information about the protocol settings, see [Protocol Settings](../core/protocol-settings.md).</span></span> <span data-ttu-id="29bfd-116">有关协议的详细信息，请参阅[贸易合作伙伴协议](../core/trading-partner-agreement.md)。</span><span class="sxs-lookup"><span data-stu-id="29bfd-116">For more information about agreements, see [Trading Partner Agreement](../core/trading-partner-agreement.md).</span></span> <span data-ttu-id="29bfd-117">贸易合作伙伴管理 (TPM) 用户界面中设置的协议设置和贸易合作伙伴协议。</span><span class="sxs-lookup"><span data-stu-id="29bfd-117">You set the protocol settings and the trading partner agreement in the Trading Partner Management (TPM) user interface.</span></span> <span data-ttu-id="29bfd-118">TPM 屏幕位于**参与方**节点的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="29bfd-118">The TPM screens are in the **Parties** node of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="29bfd-119">无需成为开发人员若要配置中的 EDI 处理[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="29bfd-119">You do not have to be a developer to configure EDI processing in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="29bfd-120">有关贸易合作伙伴协议如何帮助在 EDI 处理中的详细信息，请参阅[在 EDI 处理中的协议角色](../core/the-role-of-agreements-in-edi-processing.md)。</span><span class="sxs-lookup"><span data-stu-id="29bfd-120">For more information about how trading partner agreements help in EDI processing, see [The Role of Agreements in EDI Processing](../core/the-role-of-agreements-in-edi-processing.md).</span></span>  
  
## <a name="edi-receive-side-processing"></a><span data-ttu-id="29bfd-121">EDI 接收端处理</span><span class="sxs-lookup"><span data-stu-id="29bfd-121">EDI Receive-Side Processing</span></span>  
 <span data-ttu-id="29bfd-122">当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收 EDI 消息时，处理该消息在 EDI 接收管道。</span><span class="sxs-lookup"><span data-stu-id="29bfd-122">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receives an EDI message, it processes the message in the EDI receive pipeline.</span></span> <span data-ttu-id="29bfd-123">接收管道将执行以下基本处理：</span><span class="sxs-lookup"><span data-stu-id="29bfd-123">The receive pipeline performs the following basic processing:</span></span>  
  
- <span data-ttu-id="29bfd-124">贸易合作伙伴协议查找和架构确定。</span><span class="sxs-lookup"><span data-stu-id="29bfd-124">Trading partner agreement lookup and schema determination.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="29bfd-125">在以前版本的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，参与方定义还包括协议定义。</span><span class="sxs-lookup"><span data-stu-id="29bfd-125">In the previous versions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], a party definition also included the agreement definition.</span></span> <span data-ttu-id="29bfd-126">因此，当接收管道查找参与方属性，它会从内部查找参与方定义中的协议定义，然后相应地处理这些消息。</span><span class="sxs-lookup"><span data-stu-id="29bfd-126">So, when the receive pipeline looked up the party properties, it would internally look for the agreement definition within the party definition and then process the messages accordingly.</span></span> <span data-ttu-id="29bfd-127">使用 BizTalk Server，因为参与方 （或贸易合作伙伴） 是不同于贸易合作伙伴协议中，接收管道查找贸易合作伙伴协议专门。</span><span class="sxs-lookup"><span data-stu-id="29bfd-127">With BizTalk Server, because the party (or trading partner) is distinct from the trading partner agreement, the receive pipeline looks for the trading partner agreement specifically.</span></span>  
  > 
  > [!NOTE]
  >  <span data-ttu-id="29bfd-128">如果某个消息解析到的所有协议将被都禁用，则将挂起消息。</span><span class="sxs-lookup"><span data-stu-id="29bfd-128">If all the agreements that a message resolves to are disabled, the message will be suspended.</span></span> <span data-ttu-id="29bfd-129">此外在事件日志中记录警告。</span><span class="sxs-lookup"><span data-stu-id="29bfd-129">A warning is also logged in the Event log.</span></span>  
  
- <span data-ttu-id="29bfd-130">如果一条 EDI 消息包含多个交换，拆分交换并处理每个交换，单独 （如果启用）。</span><span class="sxs-lookup"><span data-stu-id="29bfd-130">If a single EDI message contains multiple interchanges, splits the interchanges and processes each interchange separately (if enabled).</span></span> <span data-ttu-id="29bfd-131">有关详细信息，请参阅[启用接收的多个交换中一条消息](../core/enabling-the-receiving-of-multiple-interchanges-in-a-single-message.md)。</span><span class="sxs-lookup"><span data-stu-id="29bfd-131">For more information, see [Enabling the Receiving of Multiple Interchanges in a Single Message](../core/enabling-the-receiving-of-multiple-interchanges-in-a-single-message.md).</span></span>  
  
- <span data-ttu-id="29bfd-132">分析每个 EDI 交换，将转换 X12-或 EDIFACT-编码为 XML 文档的数据。</span><span class="sxs-lookup"><span data-stu-id="29bfd-132">Parses each EDI interchange, converting the X12- or EDIFACT-encoded data into an XML document.</span></span>  
  
- <span data-ttu-id="29bfd-133">验证信封及其消息根据 EDI 标准、 合作伙伴协议和消息架构。</span><span class="sxs-lookup"><span data-stu-id="29bfd-133">Validates the envelope and its message according to the EDI standards, the partner agreement, and the message schemas.</span></span>  
  
- <span data-ttu-id="29bfd-134">如果批处理交换，则将拆分该批处理的交换，创建所需的批处理、 设置和升级属性的 XML 文件，以便每个事务，或保留该交换。</span><span class="sxs-lookup"><span data-stu-id="29bfd-134">If the interchange is batched, either splits the batched interchange, creating an XML file for each transaction set and promoting properties required for batch processing, or preserves the interchange.</span></span>  
  
- <span data-ttu-id="29bfd-135">生成确认。</span><span class="sxs-lookup"><span data-stu-id="29bfd-135">Generates an acknowledgment.</span></span>  
  
- <span data-ttu-id="29bfd-136">EDI 信封转换为上下文属性，并将升级用于 EDI 处理其他属性。</span><span class="sxs-lookup"><span data-stu-id="29bfd-136">Converts the EDI envelope into context properties, and promotes other properties for EDI processing.</span></span>  
  
- <span data-ttu-id="29bfd-137">升级属性用于控制批处理的。</span><span class="sxs-lookup"><span data-stu-id="29bfd-137">Promotes properties that control batch processing.</span></span> <span data-ttu-id="29bfd-138">这可能包括将解除批处理后的事务集发送到多个参与方。</span><span class="sxs-lookup"><span data-stu-id="29bfd-138">This can include sending debatched transaction sets to multiple parties.</span></span>  
  
  <span data-ttu-id="29bfd-139">以下是使用 EDI 接收端处理时必须考虑一些注意事项：</span><span class="sxs-lookup"><span data-stu-id="29bfd-139">Following are some considerations that you must make while using EDI receive-side processing:</span></span>  
  
- <span data-ttu-id="29bfd-140">接收位置可以使用任何类型的传输类型。</span><span class="sxs-lookup"><span data-stu-id="29bfd-140">The receive location can use any type of transport type.</span></span>  
  
- <span data-ttu-id="29bfd-141">有关 EDI 接收端处理的详细信息，请参阅[如何 BizTalk Server 接收 EDI 消息](../core/how-biztalk-server-receives-edi-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="29bfd-141">For more information about EDI receive-side processing, see [How BizTalk Server Receives EDI Messages](../core/how-biztalk-server-receives-edi-messages.md).</span></span>  
  
- <span data-ttu-id="29bfd-142">有关由接收管道中的 EDI 拆装器执行的特定处理的详细信息，请参阅[EDI 拆装器的工作原理](../core/how-the-edi-disassembler-works.md)。</span><span class="sxs-lookup"><span data-stu-id="29bfd-142">For more information about the specific processing performed by the EDI Disassembler in the receive pipeline, see [How the EDI Disassembler Works](../core/how-the-edi-disassembler-works.md).</span></span>  
  
## <a name="edi-batch-processing"></a><span data-ttu-id="29bfd-143">EDI 批处理</span><span class="sxs-lookup"><span data-stu-id="29bfd-143">EDI Batch Processing</span></span>  
 <span data-ttu-id="29bfd-144">如果传入消息为批处理，EDI 接收管道将拆分为其组成事务集，该批处理的交换或保留该批处理的交换，具体取决于配置。</span><span class="sxs-lookup"><span data-stu-id="29bfd-144">If the incoming message is a batch, the EDI receive pipeline will either split the batched interchange into its constituent transaction sets, or preserve the batched interchange, depending on the configuration.</span></span> <span data-ttu-id="29bfd-145">EDIReceive 管道使用 BatchMarker 管道组件将对其进行批处理对批处理业务流程或路由业务流程的任何交换路由。</span><span class="sxs-lookup"><span data-stu-id="29bfd-145">The EDIReceive pipeline uses the BatchMarker pipeline component to route any interchanges that are to be batched to the batching orchestration or the routing orchestration.</span></span>  
  
 <span data-ttu-id="29bfd-146">在接收端处理后要进行批处理以备发送的事务集将由批处理业务流程处理。</span><span class="sxs-lookup"><span data-stu-id="29bfd-146">After receive-side processing, transaction sets to be batched for sending will be processed by the batching orchestration.</span></span> <span data-ttu-id="29bfd-147">批处理业务流程将创建一批基于筛选条件、 激活范围和发布条件。</span><span class="sxs-lookup"><span data-stu-id="29bfd-147">The batching orchestration will create a batch based upon filter criteria, an activation range, and release criteria.</span></span>  
  
 <span data-ttu-id="29bfd-148">如果未批处理的 EDI 事务集需要发送到批次，路由业务流程将处理的事务集。</span><span class="sxs-lookup"><span data-stu-id="29bfd-148">If unbatched EDI transaction sets need to be sent to batches, a routing orchestration will process the transaction sets.</span></span> <span data-ttu-id="29bfd-149">将创建每个匹配的批处理的事务集的副本。</span><span class="sxs-lookup"><span data-stu-id="29bfd-149">A copy of the transaction set will be created for each matching batch.</span></span>  
  
 <span data-ttu-id="29bfd-150">在批处理中执行的特定处理的详细信息，请参阅[处理传入批](../core/processing-incoming-batches.md)或[批处理传出 EDI 消息](../core/batching-outgoing-edi-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="29bfd-150">For more information about the specific processing performed in batching, see [Processing Incoming Batches](../core/processing-incoming-batches.md) or [Batching Outgoing EDI Messages](../core/batching-outgoing-edi-messages.md).</span></span>  
  
## <a name="edi-send-side-processing"></a><span data-ttu-id="29bfd-151">EDI 发送端处理</span><span class="sxs-lookup"><span data-stu-id="29bfd-151">EDI Send-Side Processing</span></span>  
 <span data-ttu-id="29bfd-152">当[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]生成并发送传出 EDI 消息时，它可以处理 EDI 发送管道中的消息。</span><span class="sxs-lookup"><span data-stu-id="29bfd-152">When [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generates and sends an outgoing EDI message, it processes the message in the EDI send pipeline.</span></span> <span data-ttu-id="29bfd-153">发送管道执行以下处理：</span><span class="sxs-lookup"><span data-stu-id="29bfd-153">The send pipeline performs the following processing:</span></span>  
  
- <span data-ttu-id="29bfd-154">贸易合作伙伴协议查找和架构确定。</span><span class="sxs-lookup"><span data-stu-id="29bfd-154">Trading partner agreement lookup and schema determination.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="29bfd-155">在以前版本的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，参与方定义还包括协议定义。</span><span class="sxs-lookup"><span data-stu-id="29bfd-155">In the previous versions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], a party definition also included the agreement definition.</span></span> <span data-ttu-id="29bfd-156">因此，当发送管道查找参与方属性，它会从内部查找参与方定义中的协议定义，然后相应地处理这些消息。</span><span class="sxs-lookup"><span data-stu-id="29bfd-156">So, when the send pipeline looked up the party properties, it would internally look for the agreement definition within the party definition and then process the messages accordingly.</span></span> <span data-ttu-id="29bfd-157">使用 BizTalk Server，因为参与方 （或贸易合作伙伴） 是不同于贸易合作伙伴协议中，发送管道查找贸易合作伙伴协议专门。</span><span class="sxs-lookup"><span data-stu-id="29bfd-157">With BizTalk Server, because the party (or trading partner) is distinct from the trading partner agreement, the send pipeline looks for the trading partner agreement specifically.</span></span>  
  > 
  > [!NOTE]
  >  <span data-ttu-id="29bfd-158">如果某个消息解析到的所有协议将被都禁用，则将挂起消息。</span><span class="sxs-lookup"><span data-stu-id="29bfd-158">If all the agreements that a message resolves to are disabled, the message will be suspended.</span></span>  <span data-ttu-id="29bfd-159">此外在事件日志中记录警告。</span><span class="sxs-lookup"><span data-stu-id="29bfd-159">A warning is also logged in the Event log.</span></span>  
  
- <span data-ttu-id="29bfd-160">序列化 EDI 消息，将 XML 文档转换成 X12-或 EDIFACT-编码的数据。</span><span class="sxs-lookup"><span data-stu-id="29bfd-160">Serializes the EDI message, converting the XML document into X12- or EDIFACT-encoded data.</span></span>  
  
- <span data-ttu-id="29bfd-161">如果消息数据包含还用作为 X12 的字符分隔符，发送管道可以配置为负载中的字符替换为另一个字符。</span><span class="sxs-lookup"><span data-stu-id="29bfd-161">If the message data contains characters that are also used as X12 separators, the send pipeline can be configured to replace the characters in the payload with another character.</span></span>  
  
- <span data-ttu-id="29bfd-162">如果 EDI 消息的批处理的交换，发送管道提取交换从 BizTalk MessageBox 后批处理业务流程生成批。</span><span class="sxs-lookup"><span data-stu-id="29bfd-162">If the EDI message is a batched interchange, the send pipeline picks up the interchange from the BizTalk MessageBox after the batching orchestration has built the batch.</span></span>  
  
- <span data-ttu-id="29bfd-163">验证传出消息。</span><span class="sxs-lookup"><span data-stu-id="29bfd-163">Validates the outgoing message.</span></span>  
  
- <span data-ttu-id="29bfd-164">创建 EDI 信封根据参与方属性或在运行时指定的 EDI 信封属性。</span><span class="sxs-lookup"><span data-stu-id="29bfd-164">Creates the EDI envelope according to the party properties or EDI envelope properties specified at runtime.</span></span>  
  
- <span data-ttu-id="29bfd-165">处理接收的确认。</span><span class="sxs-lookup"><span data-stu-id="29bfd-165">Processes acknowledgments received.</span></span>  
  
  <span data-ttu-id="29bfd-166">以下是使用 EDI 发送端处理时必须考虑一些注意事项：</span><span class="sxs-lookup"><span data-stu-id="29bfd-166">Following are some considerations that you must make while using EDI send-side processing:</span></span>  
  
- <span data-ttu-id="29bfd-167">发送端口可以使用任何类型的传输。</span><span class="sxs-lookup"><span data-stu-id="29bfd-167">The send port can use any type of transport.</span></span>  
  
- <span data-ttu-id="29bfd-168">有关 EDI 发送端处理的详细信息，请参阅[如何 BizTalk Server 将发送 EDI 消息](../core/how-biztalk-server-sends-edi-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="29bfd-168">For more information about EDI send-side processing, see [How BizTalk Server Sends EDI Messages](../core/how-biztalk-server-sends-edi-messages.md).</span></span>  
  
- <span data-ttu-id="29bfd-169">在发送管道中执行的特定处理的详细信息，请参阅[EDI 组装器的工作原理](../core/how-the-edi-assembler-works.md)。</span><span class="sxs-lookup"><span data-stu-id="29bfd-169">For more information about the specific processing performed in the send pipeline, see [How the EDI Assembler Works](../core/how-the-edi-assembler-works.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29bfd-170">请参阅</span><span class="sxs-lookup"><span data-stu-id="29bfd-170">See Also</span></span>  
 <span data-ttu-id="29bfd-171">[BizTalk Server 中的 EDI 支持](../core/edi-support-in-biztalk-server1.md) </span><span class="sxs-lookup"><span data-stu-id="29bfd-171">[EDI Support in BizTalk Server](../core/edi-support-in-biztalk-server1.md) </span></span>  
 <span data-ttu-id="29bfd-172">[EDI 支持问题](../core/edi-support-issues.md) </span><span class="sxs-lookup"><span data-stu-id="29bfd-172">[EDI Support Issues](../core/edi-support-issues.md) </span></span>  
 <span data-ttu-id="29bfd-173">[协议在 EDI 处理的角色](../core/the-role-of-agreements-in-edi-processing.md) </span><span class="sxs-lookup"><span data-stu-id="29bfd-173">[The Role of Agreements in EDI Processing](../core/the-role-of-agreements-in-edi-processing.md) </span></span>  
 <span data-ttu-id="29bfd-174">[BizTalk Server 如何接收 EDI 消息](../core/how-biztalk-server-receives-edi-messages.md) </span><span class="sxs-lookup"><span data-stu-id="29bfd-174">[How BizTalk Server Receives EDI Messages](../core/how-biztalk-server-receives-edi-messages.md) </span></span>  
 <span data-ttu-id="29bfd-175">[BizTalk Server 如何发送 EDI 消息](../core/how-biztalk-server-sends-edi-messages.md) </span><span class="sxs-lookup"><span data-stu-id="29bfd-175">[How BizTalk Server Sends EDI Messages](../core/how-biztalk-server-sends-edi-messages.md) </span></span>  
 [<span data-ttu-id="29bfd-176">开发和配置 BizTalk Server EDI 解决方案</span><span class="sxs-lookup"><span data-stu-id="29bfd-176">Developing and Configuring BizTalk Server EDI Solutions</span></span>](../core/developing-and-configuring-biztalk-server-edi-solutions.md)