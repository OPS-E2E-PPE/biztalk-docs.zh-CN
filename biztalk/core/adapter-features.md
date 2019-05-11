---
title: TIBCO Enterprise Message Service 适配器功能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ede748ce-3f28-4942-b2bd-e38e5f1b0f54
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d923f439598f9eaa924924b6c7a628caf62d32e9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361551"
---
# <a name="tibco-ems-adapter-features"></a><span data-ttu-id="ca958-102">TIBCO EMS 适配器功能</span><span class="sxs-lookup"><span data-stu-id="ca958-102">TIBCO EMS Adapter Features</span></span>
<span data-ttu-id="ca958-103">用于 TIBCO Enterprise Message Service (EMS) 的 Microsoft BizTalk 适配器可以发布和订阅队列和主题由 TIBCO EMS，使用 BizTalk Server 和 TIBCO SDK。</span><span class="sxs-lookup"><span data-stu-id="ca958-103">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service (EMS) enables you to publish and subscribe to queues and topics managed by TIBCO EMS, using BizTalk Server and the TIBCO SDK.</span></span> <span data-ttu-id="ca958-104">该适配器以快速、 简单和可靠的方式集成 TIBCO EMS 消息。</span><span class="sxs-lookup"><span data-stu-id="ca958-104">The adapter integrates TIBCO EMS messages in a fast, easy, and reliable way.</span></span> <span data-ttu-id="ca958-105">交换 XML TIBCO EMS 服务器与 Microsoft 之间的数据格式[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供一个高度整合并且可靠的应用程序基础结构。</span><span class="sxs-lookup"><span data-stu-id="ca958-105">It exchanges XML data formats between TIBCO EMS servers and Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to provide a tightly integrated and reliable application infrastructure.</span></span> <span data-ttu-id="ca958-106">它提供了传输和接收适配器集成操作提供了端到端业务流程管理使用 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="ca958-106">It provides transmit and receive adapter integration operations providing end-to-end business-process management using XML schemas.</span></span>  
  
## <a name="data-validation"></a><span data-ttu-id="ca958-107">数据验证</span><span class="sxs-lookup"><span data-stu-id="ca958-107">Data Validation</span></span>  
 <span data-ttu-id="ca958-108">用于 TIBCO EMS 以进程形式运行与作为本机 BizTalk Server 主机的 BizTalk 适配器紧密集成适配器，并验证时配置的端口配置。</span><span class="sxs-lookup"><span data-stu-id="ca958-108">BizTalk Adapter for TIBCO EMS runs in-process with the BizTalk Server host as a native, tightly integrated adapter and validates port configuration at the time of configuration.</span></span> <span data-ttu-id="ca958-109">它会验证数据尽可能多地-例如，有效的名称、 有效的数字，范围内有效。</span><span class="sxs-lookup"><span data-stu-id="ca958-109">It validates the data as much as possible--for example, valid name, valid number, valid in range.</span></span> <span data-ttu-id="ca958-110">它不会尝试建立连接。</span><span class="sxs-lookup"><span data-stu-id="ca958-110">It does not try to make a connection.</span></span> <span data-ttu-id="ca958-111">因此，主机、 端口目标、 用户和密码不会验证直到运行时调用，在其中记录错误情况。</span><span class="sxs-lookup"><span data-stu-id="ca958-111">Therefore, the host, port destination, user, and password are not validated until there is a run-time call, in which case an error is logged.</span></span>  
  
## <a name="message-delivery"></a><span data-ttu-id="ca958-112">消息传递</span><span class="sxs-lookup"><span data-stu-id="ca958-112">Message Delivery</span></span>  
 <span data-ttu-id="ca958-113">用于 TIBCO EMS 的 BizTalk 适配器可保证的一次性送达消息。</span><span class="sxs-lookup"><span data-stu-id="ca958-113">BizTalk Adapter for TIBCO EMS guarantees one-time-only delivery of messages.</span></span> <span data-ttu-id="ca958-114">未达到 EMS 的消息被标记为挂起时，可重试。</span><span class="sxs-lookup"><span data-stu-id="ca958-114">Messages that do not reach EMS are marked as retryable when suspended.</span></span> <span data-ttu-id="ca958-115">时可能存在一些例外情况，例如，在执行时存在一个无效的端口配置。</span><span class="sxs-lookup"><span data-stu-id="ca958-115">There can be some exceptions to this, for example, when an invalid port configuration exists at the time of execution.</span></span>  
  
 <span data-ttu-id="ca958-116">适配器接受 EMS 消息类型的文本。</span><span class="sxs-lookup"><span data-stu-id="ca958-116">The adapter accepts text EMS message types.</span></span>  <span data-ttu-id="ca958-117">适配器支持转到 EMS 的消息的事务和由控制的事务支持[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ca958-117">The adapter supports transactions for messages going to EMS, and the transaction support is controlled by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ca958-118">用于 TIBCO EMS 的 BizTalk 适配器和 EMS 服务器之间的连接不安全。</span><span class="sxs-lookup"><span data-stu-id="ca958-118">The connection between BizTalk Adapter for TIBCO EMS and the EMS server is not secure.</span></span> <span data-ttu-id="ca958-119">不受提供的 TIBCO EMS SDK。</span><span class="sxs-lookup"><span data-stu-id="ca958-119">It is not supported by the provided TIBCO EMS SDK.</span></span>  
  
 <span data-ttu-id="ca958-120">适配器支持所有标准的 JMS 属性和 EMS 扩展名。</span><span class="sxs-lookup"><span data-stu-id="ca958-120">The adapter supports all standard JMS properties and EMS extensions.</span></span> <span data-ttu-id="ca958-121">这些属性放在可供业务流程的 BizTalk 消息上下文中。</span><span class="sxs-lookup"><span data-stu-id="ca958-121">These properties are put in the BizTalk message context to be available to an orchestration.</span></span>  
  
## <a name="general-adapter-features"></a><span data-ttu-id="ca958-122">常规适配器功能</span><span class="sxs-lookup"><span data-stu-id="ca958-122">General Adapter Features</span></span>  
 <span data-ttu-id="ca958-123">用于 TIBCO EMS 的 BizTalk 适配器提供了一种方法来交换 TIBCO EMS 系统和 BizTalk Server 之间的实时业务数据。</span><span class="sxs-lookup"><span data-stu-id="ca958-123">BizTalk Adapter for TIBCO EMS provides a means to exchange real-time business data between TIBCO EMS systems and BizTalk Server.</span></span> <span data-ttu-id="ca958-124">适配器允许 XML 应用程序与 TIBCO EMS 之间的交互。</span><span class="sxs-lookup"><span data-stu-id="ca958-124">The adapter allows for interaction between an XML application and TIBCO EMS.</span></span> <span data-ttu-id="ca958-125">这样，XML 用于与 TIBCO EMS 的入站和出站处理的应用程序。</span><span class="sxs-lookup"><span data-stu-id="ca958-125">It enables XML applications for inbound and outbound processing with TIBCO EMS.</span></span>  
  
 <span data-ttu-id="ca958-126">适配器接受 XML 消息，以使 BizTalk Server 应用程序与 TIBCO EMS 使用以下方法之一进行通信：</span><span class="sxs-lookup"><span data-stu-id="ca958-126">The adapter accepts XML messages to enable BizTalk Server applications to communicate with TIBCO EMS using one of the following:</span></span>  
  
-   <span data-ttu-id="ca958-127">传输适配器，使用静态单向发送端口将消息发送到 TIBCO EMS。</span><span class="sxs-lookup"><span data-stu-id="ca958-127">Transmit Adapter, which uses a Static One-Way Send port to send a message to TIBCO EMS.</span></span>  
  
-   <span data-ttu-id="ca958-128">接收适配器使用静态单向接收端口接收来自 TIBCO EMS 的消息。</span><span class="sxs-lookup"><span data-stu-id="ca958-128">Receive Adapter, which uses a Static One-Way Receive port to receive messages from TIBCO EMS.</span></span>  
  
### <a name="transmit-adapter-architecture-send--static-one-way"></a><span data-ttu-id="ca958-129">传输适配器体系结构：发送 – 静态单向</span><span class="sxs-lookup"><span data-stu-id="ca958-129">Transmit Adapter Architecture: Send – Static One-Way</span></span>  
 <span data-ttu-id="ca958-130">在单向发送方案中，发送端口配置为将消息发送到队列/主题。</span><span class="sxs-lookup"><span data-stu-id="ca958-130">In the one-way send scenario, the send port is configured to send messages to a queue/topic.</span></span> <span data-ttu-id="ca958-131">用于 TIBCO Enterprise Message Service 的 BizTalk 适配器将请求转发到指定队列/主题上的 TIBCO EMS 服务器。</span><span class="sxs-lookup"><span data-stu-id="ca958-131">BizTalk Adapter for TIBCO Enterprise Message Service forwards the request to the TIBCO EMS server on the specified queue/topic.</span></span> <span data-ttu-id="ca958-132">该适配器将消息发送到 TIBCO EMS 系统使用 TIBCO EMS 通信协议。</span><span class="sxs-lookup"><span data-stu-id="ca958-132">The adapter sends the message to the TIBCO EMS system using TIBCO EMS communication protocol.</span></span> <span data-ttu-id="ca958-133">TIBCO EMS 系统接收请求并执行业务逻辑。</span><span class="sxs-lookup"><span data-stu-id="ca958-133">The TIBCO EMS system receives the requests and executes the business logic.</span></span> <span data-ttu-id="ca958-134">若要呼叫 TIBCO EMS，必须以访问 TIBCO EMS 服务器的配置信息提供适配器。</span><span class="sxs-lookup"><span data-stu-id="ca958-134">To make calls into TIBCO EMS, you must provide the adapter with the configuration information to access the TIBCO EMS server.</span></span>  
  
 <span data-ttu-id="ca958-135">下图显示了适配器的单向发送操作。</span><span class="sxs-lookup"><span data-stu-id="ca958-135">The following image shows the adapter's one-way send operation.</span></span>  
  
 <span data-ttu-id="ca958-136">![](../core/media/tibcoems-architecture-send.gif "TIBCOEMS_architecture_send")</span><span class="sxs-lookup"><span data-stu-id="ca958-136">![](../core/media/tibcoems-architecture-send.gif "TIBCOEMS_architecture_send")</span></span>  
  
### <a name="receive-adapter-architecture-receive--static-one-way"></a><span data-ttu-id="ca958-137">接收适配器体系结构：接收 – 静态单向</span><span class="sxs-lookup"><span data-stu-id="ca958-137">Receive Adapter Architecture: Receive – Static One-Way</span></span>  
 <span data-ttu-id="ca958-138">在单向接收方案中，接收位置配置为接收 EMS 队列/主题上的消息。</span><span class="sxs-lookup"><span data-stu-id="ca958-138">In the one-way receive scenario, the receive location is configured to receive messages on an EMS queue/topic.</span></span> <span data-ttu-id="ca958-139">用于 TIBCO EMS 的 BizTalk 适配器侦听指定队列/主题上的消息，并将提交到 BizTalk Server 接收的消息。</span><span class="sxs-lookup"><span data-stu-id="ca958-139">BizTalk Adapter for TIBCO EMS listens for messages on a specified queue/topic and submits the received messages to BizTalk Server.</span></span>  
  
 <span data-ttu-id="ca958-140">下图显示了适配器的单向接收操作。</span><span class="sxs-lookup"><span data-stu-id="ca958-140">The following image shows the adapter's one-way receive operation.</span></span>  
  
 <span data-ttu-id="ca958-141">![](../core/media/tibcoems-architecture-receive.gif "TIBCOEMS_architecture_receive")</span><span class="sxs-lookup"><span data-stu-id="ca958-141">![](../core/media/tibcoems-architecture-receive.gif "TIBCOEMS_architecture_receive")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca958-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="ca958-142">See Also</span></span>  
 <span data-ttu-id="ca958-143">[开发应用程序](../core/developing-applications5.md) </span><span class="sxs-lookup"><span data-stu-id="ca958-143">[Developing Applications](../core/developing-applications5.md) </span></span>  
 [<span data-ttu-id="ca958-144">入门</span><span class="sxs-lookup"><span data-stu-id="ca958-144">Getting Started</span></span>](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md)