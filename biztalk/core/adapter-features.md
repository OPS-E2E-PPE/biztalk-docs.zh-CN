---
title: "适配器功能 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TIBCO Enterprise adapters, message delivery
- architecture, TIBCO Enterprise adapters
- TIBCO Enterprise adapters, architecture
- TIBCO Enterprise adapters, data validation
ms.assetid: ede748ce-3f28-4942-b2bd-e38e5f1b0f54
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ffa789837973f8c8c7bb6c5bd428e36c562df96c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="adapter-features"></a><span data-ttu-id="28ca9-102">适配器功能</span><span class="sxs-lookup"><span data-stu-id="28ca9-102">Adapter Features</span></span>
<span data-ttu-id="28ca9-103">用于 TIBCO Enterprise Message Service (EMS) 的 Microsoft BizTalk 适配器使您能够通过使用 BizTalk Server 和 TIBCO SDK 来发布和订阅由 TIBCO EMS 管理的队列和主题。</span><span class="sxs-lookup"><span data-stu-id="28ca9-103">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS) enables you to publish and subscribe to queues and topics managed by TIBCO EMS, using BizTalk Server and the TIBCO SDK.</span></span> <span data-ttu-id="28ca9-104">适配器将以快速、简便和可靠的方式集成 TIBCO EMS 消息。</span><span class="sxs-lookup"><span data-stu-id="28ca9-104">The adapter integrates TIBCO EMS messages in a fast, easy, and reliable way.</span></span> <span data-ttu-id="28ca9-105">它将在 TIBCO EMS 服务器和 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 之间交换 XML 数据格式，以提供一个高度整合并且可靠的应用程序基础结构。</span><span class="sxs-lookup"><span data-stu-id="28ca9-105">It exchanges XML data formats between TIBCO EMS servers and Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to provide a tightly integrated and reliable application infrastructure.</span></span> <span data-ttu-id="28ca9-106">它提供了传输和接收适配器集成操作，可使用 XML 架构提供端到端业务流程管理。</span><span class="sxs-lookup"><span data-stu-id="28ca9-106">It provides transmit and receive adapter integration operations providing end-to-end business-process management using XML schemas.</span></span>  
  
## <a name="data-validation"></a><span data-ttu-id="28ca9-107">数据验证</span><span class="sxs-lookup"><span data-stu-id="28ca9-107">Data Validation</span></span>  
 <span data-ttu-id="28ca9-108">用于 TIBCO EMS 的 BizTalk 适配器作为一个高度集中的本地适配器，与 BizTalk Server 主机一起运行，并在配置时验证端口配置。</span><span class="sxs-lookup"><span data-stu-id="28ca9-108">BizTalk Adapter for TIBCO EMS runs in-process with the BizTalk Server host as a native, tightly integrated adapter and validates port configuration at the time of configuration.</span></span> <span data-ttu-id="28ca9-109">它将尽可能多地对数据进行验证，例如，有效名称、有效编号和有效范围。</span><span class="sxs-lookup"><span data-stu-id="28ca9-109">It validates the data as much as possible--for example, valid name, valid number, valid in range.</span></span> <span data-ttu-id="28ca9-110">它不会尝试进行连接。</span><span class="sxs-lookup"><span data-stu-id="28ca9-110">It does not try to make a connection.</span></span> <span data-ttu-id="28ca9-111">因此，存在一个运行时调用（在这些情况下会记录错误）之前，将不会对主机、端口目标、用户和密码进行验证。</span><span class="sxs-lookup"><span data-stu-id="28ca9-111">Therefore, the host, port destination, user, and password are not validated until there is a run-time call, in which case an error is logged.</span></span>  
  
## <a name="message-delivery"></a><span data-ttu-id="28ca9-112">消息送达</span><span class="sxs-lookup"><span data-stu-id="28ca9-112">Message Delivery</span></span>  
 <span data-ttu-id="28ca9-113">用于 TIBCO EMS 的 BizTalk 适配器将保证消息的一次性传递。</span><span class="sxs-lookup"><span data-stu-id="28ca9-113">BizTalk Adapter for TIBCO EMS guarantees one-time-only delivery of messages.</span></span> <span data-ttu-id="28ca9-114">未达到 EMS 的邮件将在挂起时被标记为可重试。</span><span class="sxs-lookup"><span data-stu-id="28ca9-114">Messages that do not reach EMS are marked as retryable when suspended.</span></span> <span data-ttu-id="28ca9-115">可能会出现某些异常，例如，当执行期间存在一个有效的端口配置的时候。</span><span class="sxs-lookup"><span data-stu-id="28ca9-115">There can be some exceptions to this, for example, when an invalid port configuration exists at the time of execution.</span></span>  
  
 <span data-ttu-id="28ca9-116">适配器接受文本 EMS 消息类型。</span><span class="sxs-lookup"><span data-stu-id="28ca9-116">The adapter accepts text EMS message types.</span></span>  <span data-ttu-id="28ca9-117">适配器的转到 EMS，消息支持事务和事务支持受[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="28ca9-117">The adapter supports transactions for messages going to EMS, and the transaction support is controlled by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="28ca9-118">用于 TIBCO EMS 的 BizTalk 适配器和 EMS 服务器之间的连接不安全。</span><span class="sxs-lookup"><span data-stu-id="28ca9-118">The connection between BizTalk Adapter for TIBCO EMS and the EMS server is not secure.</span></span> <span data-ttu-id="28ca9-119">它不受提供的 TIBCO EMS SDK 所支持。</span><span class="sxs-lookup"><span data-stu-id="28ca9-119">It is not supported by the provided TIBCO EMS SDK.</span></span>  
  
 <span data-ttu-id="28ca9-120">适配器支持所有标准的 JMS 属性和 EMS 扩展名。</span><span class="sxs-lookup"><span data-stu-id="28ca9-120">The adapter supports all standard JMS properties and EMS extensions.</span></span> <span data-ttu-id="28ca9-121">这些属性放在可用于业务流程的 BizTalk 消息上下文中。</span><span class="sxs-lookup"><span data-stu-id="28ca9-121">These properties are put in the BizTalk message context to be available to an orchestration.</span></span>  
  
## <a name="general-adapter-features"></a><span data-ttu-id="28ca9-122">常规适配器功能</span><span class="sxs-lookup"><span data-stu-id="28ca9-122">General Adapter Features</span></span>  
 <span data-ttu-id="28ca9-123">用于 TIBCO EMS 的 BizTalk 适配器提供了一种手段，在 TIBCO EMS 系统和 BizTalk Server 之间交换实时企业数据。</span><span class="sxs-lookup"><span data-stu-id="28ca9-123">BizTalk Adapter for TIBCO EMS provides a means to exchange real-time business data between TIBCO EMS systems and BizTalk Server.</span></span> <span data-ttu-id="28ca9-124">适配器允许 XML 应用程序和 TIBCO EMS 之间的交互。</span><span class="sxs-lookup"><span data-stu-id="28ca9-124">The adapter allows for interaction between an XML application and TIBCO EMS.</span></span> <span data-ttu-id="28ca9-125">它为使用 TIBCO EMS 处理的入站和出站启用了 XML 应用程序。</span><span class="sxs-lookup"><span data-stu-id="28ca9-125">It enables XML applications for inbound and outbound processing with TIBCO EMS.</span></span>  
  
 <span data-ttu-id="28ca9-126">适配器通过使用以下端口接受 XML 消息，以使 BizTalk Server 应用程序与 TIBCO EMS 进行通信：</span><span class="sxs-lookup"><span data-stu-id="28ca9-126">The adapter accepts XML messages to enable BizTalk Server applications to communicate with TIBCO EMS using one of the following:</span></span>  
  
-   <span data-ttu-id="28ca9-127">传输适配器，使用静态单向发送端口将消息发送到 TIBCO EMS。</span><span class="sxs-lookup"><span data-stu-id="28ca9-127">Transmit Adapter, which uses a Static One-Way Send port to send a message to TIBCO EMS.</span></span>  
  
-   <span data-ttu-id="28ca9-128">接收适配器，使用静态单向接收端口从 TIBCO EMS 接收消息。</span><span class="sxs-lookup"><span data-stu-id="28ca9-128">Receive Adapter, which uses a Static One-Way Receive port to receive messages from TIBCO EMS.</span></span>  
  
### <a name="transmit-adapter-architecture-send--static-one-way"></a><span data-ttu-id="28ca9-129">传输适配器体系结构： 发送 – 静态单向</span><span class="sxs-lookup"><span data-stu-id="28ca9-129">Transmit Adapter Architecture: Send – Static One-Way</span></span>  
 <span data-ttu-id="28ca9-130">在单向发送方案中，将对发送端口进行配置以便将消息发送到队列/主题。</span><span class="sxs-lookup"><span data-stu-id="28ca9-130">In the one-way send scenario, the send port is configured to send messages to a queue/topic.</span></span> <span data-ttu-id="28ca9-131">用于 TIBCO Enterprise Message Service 的 BizTalk 适配器会将请求转发到指定队列/主题上的 TIBCO EMS 服务器。</span><span class="sxs-lookup"><span data-stu-id="28ca9-131">BizTalk Adapter for TIBCO Enterprise Message Service forwards the request to the TIBCO EMS server on the specified queue/topic.</span></span> <span data-ttu-id="28ca9-132">适配器使用 TIBCO EMS 通信协议将消息发送到 TIBCO EMS 系统。</span><span class="sxs-lookup"><span data-stu-id="28ca9-132">The adapter sends the message to the TIBCO EMS system using TIBCO EMS communication protocol.</span></span> <span data-ttu-id="28ca9-133">TIBCO EMS 系统接收请求并执行业务逻辑。</span><span class="sxs-lookup"><span data-stu-id="28ca9-133">The TIBCO EMS system receives the requests and executes the business logic.</span></span> <span data-ttu-id="28ca9-134">若要呼叫 TIBCO EMS, 您必须为适配器提供配置信息以访问 TIBCO EMS 服务器。</span><span class="sxs-lookup"><span data-stu-id="28ca9-134">To make calls into TIBCO EMS, you must provide the adapter with the configuration information to access the TIBCO EMS server.</span></span>  
  
 <span data-ttu-id="28ca9-135">下图显示了适配器的单向发送操作。</span><span class="sxs-lookup"><span data-stu-id="28ca9-135">The following image shows the adapter's one-way send operation.</span></span>  
  
 ![](../core/media/tibcoems-architecture-send.gif "TIBCOEMS_architecture_send")  
  
### <a name="receive-adapter-architecture-receive--static-one-way"></a><span data-ttu-id="28ca9-136">收到适配器体系结构： 接收 – 静态单向</span><span class="sxs-lookup"><span data-stu-id="28ca9-136">Receive Adapter Architecture: Receive – Static One-Way</span></span>  
 <span data-ttu-id="28ca9-137">在单向接收方案中，将对接收位置进行配置以接收 EMS 队列/主题上的信息。</span><span class="sxs-lookup"><span data-stu-id="28ca9-137">In the one-way receive scenario, the receive location is configured to receive messages on an EMS queue/topic.</span></span> <span data-ttu-id="28ca9-138">用于 TIBCO EMS 的 BizTalk 适配器将侦听指定队列/主题上的消息，并将接收的消息提交到 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="28ca9-138">BizTalk Adapter for TIBCO EMS listens for messages on a specified queue/topic and submits the received messages to BizTalk Server.</span></span>  
  
 <span data-ttu-id="28ca9-139">下图显示了适配器的单向接收操作。</span><span class="sxs-lookup"><span data-stu-id="28ca9-139">The following image shows the adapter's one-way receive operation.</span></span>  
  
 ![](../core/media/tibcoems-architecture-receive.gif "TIBCOEMS_architecture_receive")  
  
## <a name="see-also"></a><span data-ttu-id="28ca9-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="28ca9-140">See Also</span></span>  
 <span data-ttu-id="28ca9-141">[开发应用程序](../core/developing-applications5.md) </span><span class="sxs-lookup"><span data-stu-id="28ca9-141">[Developing Applications](../core/developing-applications5.md) </span></span>  
 [<span data-ttu-id="28ca9-142">入门</span><span class="sxs-lookup"><span data-stu-id="28ca9-142">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md)