---
title: "消息的生命周期 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, MessageBox database
- messages, orchestrations
- messages, host instances
- messages, receive locations
- send ports, about send ports
- processing, messages
- messages, processing
- host instances, about host instances
- receive locations, about receive locations
- hosts, about hosts
- messages, lifecycle
- MessageBox database, about MessageBox database
- receive ports, about receive ports
- send port groups, about send port groups
- messages, hosts
- messages, send port groups
- messages, receive ports
- orchestrations, about orchestrations
- messages, send ports
ms.assetid: d2374f86-9b5f-404f-ba7b-9cab69873fa8
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e05aca3ec819fb8615552c5ed57114032d7ea60b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="lifecycle-of-a-message"></a><span data-ttu-id="7c549-102">消息的生命周期</span><span class="sxs-lookup"><span data-stu-id="7c549-102">Lifecycle of a Message</span></span>
<span data-ttu-id="7c549-103">下图从消息传送方面对 BizTalk Server 结构进行了高度概括：</span><span class="sxs-lookup"><span data-stu-id="7c549-103">The following figure provides a high-level overview of the BizTalk Server architecture from a messaging perspective.</span></span>  
  
 <span data-ttu-id="7c549-104">![消息传递体系结构的 BizTalk Server](../core/media/arch-messaging-01.gif "arch_messaging_01")</span><span class="sxs-lookup"><span data-stu-id="7c549-104">![BizTalk Server messaging architecture](../core/media/arch-messaging-01.gif "arch_messaging_01")</span></span>  
  
 <span data-ttu-id="7c549-105">在此简化视图中，通过在给定接收端口中定义的接收位置接收消息。</span><span class="sxs-lookup"><span data-stu-id="7c549-105">In this simplified view, a message is received through a receive location defined in a given receive port.</span></span> <span data-ttu-id="7c549-106">此消息由接收位置处理，然后被发布到 MessageBox 数据库，这是 BizTalk Server 的主要持久化和路由机制。</span><span class="sxs-lookup"><span data-stu-id="7c549-106">This message is processed by the receive location and then published to the MessageBox database, the main persistence and routing mechanism for BizTalk Server.</span></span> <span data-ttu-id="7c549-107">MessageBox 评估活动的订阅，并将消息路由到具有匹配订阅的业务流程和发送端口。</span><span class="sxs-lookup"><span data-stu-id="7c549-107">The MessageBox evaluates active subscriptions and routes the message to those orchestrations and send ports with matching subscriptions.</span></span> <span data-ttu-id="7c549-108">业务流程可以处理消息，并通过 MessageBox 将消息发布到发送端口，从发送端口将消息推送到最终目标。</span><span class="sxs-lookup"><span data-stu-id="7c549-108">Orchestrations may process the message and publish messages through the MessageBox to a send port where it is pushed out to its final destination.</span></span>  
  
 <span data-ttu-id="7c549-109">以下是 BizTalk Server 消息处理中涉及的关键组件：</span><span class="sxs-lookup"><span data-stu-id="7c549-109">The following are key components involved in BizTalk Server message processing.</span></span>  
  
## <a name="receive-ports-and-receive-locations"></a><span data-ttu-id="7c549-110">接收端口和接收位置</span><span class="sxs-lookup"><span data-stu-id="7c549-110">Receive Ports and Receive Locations</span></span>  
 <span data-ttu-id="7c549-111">A*接收端口*是集合的一个或多个接收到 BizTalk Server 中定义特定入口点的位置。</span><span class="sxs-lookup"><span data-stu-id="7c549-111">A *receive port* is a collection of one or more receive locations that define specific entry points into BizTalk Server.</span></span> <span data-ttu-id="7c549-112">A*接收位置*是单个终结点 (URL) 的配置接收消息。</span><span class="sxs-lookup"><span data-stu-id="7c549-112">A *receive location* is the configuration of a single endpoint (URL) to receive messages.</span></span> <span data-ttu-id="7c549-113">该位置包含接收适配器和接收管道的配置信息。</span><span class="sxs-lookup"><span data-stu-id="7c549-113">The location contains configuration information for both a receive adapter and a receive pipeline.</span></span> <span data-ttu-id="7c549-114">*适配器*负责接收消息的传输和通信的部分。</span><span class="sxs-lookup"><span data-stu-id="7c549-114">The *adapter* is responsible for the transport and communications part of receiving a message.</span></span> <span data-ttu-id="7c549-115">示例包括 FILE 适配器和 SOAP 适配器，这两种适配器都从不同类型的源接收消息。</span><span class="sxs-lookup"><span data-stu-id="7c549-115">Examples include the File adapter and SOAP adapter, each of which receives messages from different types of sources.</span></span> <span data-ttu-id="7c549-116">接收管道负责准备消息以便将消息发布到 MessageBox 中。</span><span class="sxs-lookup"><span data-stu-id="7c549-116">The receive pipeline is responsible for preparing the message for publishing into the MessageBox.</span></span> <span data-ttu-id="7c549-117">A*管道*是一系列序列，每个提供对解密/加密的消息的特定处理、 分析过程中，或验证中执行的组件。</span><span class="sxs-lookup"><span data-stu-id="7c549-117">A *pipeline* is a series of components that are executed in sequence, each providing specific processing to a message such as decryption/encryption, parsing, or validation.</span></span> <span data-ttu-id="7c549-118">接收端口，有关管道的详细信息，以及接收位置，请参阅[项目](../core/artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="7c549-118">For more information about pipelines, receive ports, and receive locations, see [Artifacts](../core/artifacts.md).</span></span>  
  
## <a name="send-ports-and-send-port-groups"></a><span data-ttu-id="7c549-119">发送端口和发送端口组</span><span class="sxs-lookup"><span data-stu-id="7c549-119">Send Ports and Send Port Groups</span></span>  
 <span data-ttu-id="7c549-120">A*发送端口*是发送管道和发送适配器的组合。</span><span class="sxs-lookup"><span data-stu-id="7c549-120">A *send port* is the combination of a send pipeline and a send adapter.</span></span> <span data-ttu-id="7c549-121">发送端口组是发送端口的集合，作用很像电子邮件分发列表。</span><span class="sxs-lookup"><span data-stu-id="7c549-121">A send port group is a collection of send ports and works much like an e-mail distribution list.</span></span> <span data-ttu-id="7c549-122">发送到发送端口组的消息将被发送到该组中的所有发送端口。</span><span class="sxs-lookup"><span data-stu-id="7c549-122">A message sent to a send port group will be sent to all send ports in that group.</span></span> <span data-ttu-id="7c549-123">发送管道用于准备来自 BizTalk Server 的消息以将其传输到其他服务。</span><span class="sxs-lookup"><span data-stu-id="7c549-123">The send pipeline is used to prepare a message coming from BizTalk Server for transmission to another service.</span></span> <span data-ttu-id="7c549-124">发送适配器负责使用特定协议（如 SOAP 或 FTP）实际发送消息。</span><span class="sxs-lookup"><span data-stu-id="7c549-124">The send adapter is responsible for actually sending the message using a specific protocol such as SOAP, or FTP.</span></span> <span data-ttu-id="7c549-125">发送端口和发送端口组的详细信息，请参阅[项目](../core/artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="7c549-125">For more information on send ports and send port groups, see [Artifacts](../core/artifacts.md).</span></span>  
  
## <a name="orchestrations"></a><span data-ttu-id="7c549-126">业务流程</span><span class="sxs-lookup"><span data-stu-id="7c549-126">Orchestrations</span></span>  
 <span data-ttu-id="7c549-127">业务流程可以通过 MessageBox 订阅（接收）和发布（发送）消息。</span><span class="sxs-lookup"><span data-stu-id="7c549-127">Orchestrations can subscribe to (receive) and publish (send) messages through the MessageBox.</span></span> <span data-ttu-id="7c549-128">此外，业务流程可以构造新的消息。</span><span class="sxs-lookup"><span data-stu-id="7c549-128">In addition, orchestrations can construct new messages.</span></span> <span data-ttu-id="7c549-129">使用已讨论过的订阅和路由机制接收消息。</span><span class="sxs-lookup"><span data-stu-id="7c549-129">Messages are received using the subscription and routing mechanism already discussed.</span></span> <span data-ttu-id="7c549-130">在填入业务流程的订阅后，将激活新的实例并传送消息；对于实例订阅，如有必要，将解除对该实例的冻结，然后传送消息。</span><span class="sxs-lookup"><span data-stu-id="7c549-130">When subscriptions are filled for orchestrations, a new instance is activated and the message is delivered, or in the case of instance subscriptions, the instance is rehydrated if necessary and the message is then delivered.</span></span> <span data-ttu-id="7c549-131">当消息发送从业务流程时，它们发布到 MessageBox 在相同的方式如到达具有适当的属性的接收位置的消息插入到在路由中使用的数据库。</span><span class="sxs-lookup"><span data-stu-id="7c549-131">When messages are sent from an orchestration, they are published to the MessageBox in the same manner as a message arriving at a receive location with the appropriate properties is inserted into the database for use in routing.</span></span> <span data-ttu-id="7c549-132">有关业务流程的详细信息，请参阅[项目](../core/artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="7c549-132">For more information about orchestrations, see [Artifacts](../core/artifacts.md).</span></span>  
  
## <a name="messagebox-database"></a><span data-ttu-id="7c549-133">MessageBox 数据库</span><span class="sxs-lookup"><span data-stu-id="7c549-133">MessageBox Database</span></span>  
 <span data-ttu-id="7c549-134">BizTalk Server 中发布/订阅引擎的核心是 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="7c549-134">The heart of the publish/subscribe engine in BizTalk Server is the MessageBox database.</span></span> <span data-ttu-id="7c549-135">MessageBox 由两个组件构成：一个或多个 Microsoft SQL Server 数据库和消息代理。</span><span class="sxs-lookup"><span data-stu-id="7c549-135">The MessageBox is made up of two components: one or more Microsoft SQL Server databases and the Message Agent.</span></span> <span data-ttu-id="7c549-136">SQL Server 数据库为许多对象（包括消息、消息属性、订阅、业务流程状态、跟踪数据和用于路由的主机队列）提供持久化存储。</span><span class="sxs-lookup"><span data-stu-id="7c549-136">The SQL Server database provides the persistence store for many things including messages, message properties, subscriptions, orchestration states, tracking data, and host queues for routing.</span></span> <span data-ttu-id="7c549-137">MessageBox 数据库有关的详细信息，请参阅[MessageBox 数据库](../core/the-messagebox-database.md)。</span><span class="sxs-lookup"><span data-stu-id="7c549-137">For more information about the MessageBox database, see [The MessageBox Database](../core/the-messagebox-database.md).</span></span>  
  
## <a name="hosts-and-host-instances"></a><span data-ttu-id="7c549-138">主机和主机实例</span><span class="sxs-lookup"><span data-stu-id="7c549-138">Hosts and Host Instances</span></span>  
 <span data-ttu-id="7c549-139">A*主机*是 Microsoft Windows 进程，如执行 BizTalk 服务器项目的逻辑表示发送端口和业务流程。</span><span class="sxs-lookup"><span data-stu-id="7c549-139">A *host* is a logical representation of a Microsoft Windows process that executes BizTalk Server artifacts such as send ports and orchestrations.</span></span> <span data-ttu-id="7c549-140">A*主机实例*是特定服务器上的主机的物理表示。</span><span class="sxs-lookup"><span data-stu-id="7c549-140">A *host instance* is the physical representation of a host on a specific server.</span></span> <span data-ttu-id="7c549-141">主机可以是进程内主机（意味着它由 BizTalk Server 所拥有和管理），也可以是独立的主机（意味着 BizTalk Server 代码运行在不由 BizTalk Server 所控制的进程中）。</span><span class="sxs-lookup"><span data-stu-id="7c549-141">A host can be either an in-process host, which means it is owned and managed by BizTalk Server, or an isolated host, which means that the BizTalk Server code is running in a process that is not controlled by BizTalk Server.</span></span> <span data-ttu-id="7c549-142">独立主机的一个典型示例为 Internet 信息服务 (IIS)，它承载了 HTTP 和 SOAP 适配器的接收功能。</span><span class="sxs-lookup"><span data-stu-id="7c549-142">A good example of an isolated host is Internet Information Services (IIS), which hosts the receive functionality of the HTTP and SOAP adapters.</span></span> <span data-ttu-id="7c549-143">主机是为整个 BizTalk Server 组（即共享配置、MessageBox 和端口等的 BizTalk Server 集合）定义的。</span><span class="sxs-lookup"><span data-stu-id="7c549-143">Hosts are defined for an entire BizTalk Server group; a collection of BizTalk Servers that share configuration, MessageBoxes, ports, and so on.</span></span> <span data-ttu-id="7c549-144">有关主机和主机实例的详细信息，请参阅[实体](../core/entities.md)。</span><span class="sxs-lookup"><span data-stu-id="7c549-144">For more information about hosts and host instances, see [Entities](../core/entities.md).</span></span>  
  
## <a name="saving-a-message-body"></a><span data-ttu-id="7c549-145">保存消息正文</span><span class="sxs-lookup"><span data-stu-id="7c549-145">Saving a Message Body</span></span>  
 <span data-ttu-id="7c549-146">保存消息正文有三种方式。</span><span class="sxs-lookup"><span data-stu-id="7c549-146">There are three ways to save a message body.</span></span>  
  
### <a name="from-the-admin-mmc-group-hub-page-queries"></a><span data-ttu-id="7c549-147">从管理 MMC 组中心页查询</span><span class="sxs-lookup"><span data-stu-id="7c549-147">From the Admin MMC group hub page queries</span></span>  
 <span data-ttu-id="7c549-148">此方法仅针对 MessageBox 数据库中的消息。</span><span class="sxs-lookup"><span data-stu-id="7c549-148">This method is for messages in the MessageBox database only.</span></span>  
  
-   <span data-ttu-id="7c549-149">查看服务实例。</span><span class="sxs-lookup"><span data-stu-id="7c549-149">View a Service Instance.</span></span>  
  
-   <span data-ttu-id="7c549-150">打开**服务实例详细信息**对话框。</span><span class="sxs-lookup"><span data-stu-id="7c549-150">Open the **Service Instance Details** dialog box.</span></span>  
  
-   <span data-ttu-id="7c549-151">单击**消息选项卡**若要查看与此实例关联的消息的列表。</span><span class="sxs-lookup"><span data-stu-id="7c549-151">Click the **Messages Tab** to view the list of messages associated with this instance.</span></span>  
  
-   <span data-ttu-id="7c549-152">可以右键单击该消息，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="7c549-152">Either right-click the message, and then click **Save**.</span></span>  
  
     <span data-ttu-id="7c549-153">- 或 -</span><span class="sxs-lookup"><span data-stu-id="7c549-153">-or-</span></span>  
  
-   <span data-ttu-id="7c549-154">双击该消息以中将其打开**消息查看器**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="7c549-154">Double-click the message to open it in the **Message Viewer**, and click **Save**.</span></span>  
  
### <a name="from-the-operations-om"></a><span data-ttu-id="7c549-155">从操作 OM</span><span class="sxs-lookup"><span data-stu-id="7c549-155">From the Operations OM</span></span>  
  
-   <span data-ttu-id="7c549-156">使用**GetInstance**检索服务实例对象。</span><span class="sxs-lookup"><span data-stu-id="7c549-156">Use **GetInstance** to retrieve a Service Instance object.</span></span>  
  
-   <span data-ttu-id="7c549-157">使用**Instance.Messages []**枚举所有消息都当前引用服务实例。</span><span class="sxs-lookup"><span data-stu-id="7c549-157">Use **Instance.Messages [ ]** to enumerate all messages which the service instance currently references.</span></span>  
  
-   <span data-ttu-id="7c549-158">使用方法对 message 对象例如**Message.BodyPart []**和**Message.Context []**访问并将其保存。</span><span class="sxs-lookup"><span data-stu-id="7c549-158">Use methods on the message object such as **Message.BodyPart [ ]** and **Message.Context [  ]** to access and save it.</span></span>  
  
### <a name="from-the-dta"></a><span data-ttu-id="7c549-159">从 DTA</span><span class="sxs-lookup"><span data-stu-id="7c549-159">From the DTA</span></span>  
  
-   <span data-ttu-id="7c549-160">从 DTA 使用检索消息**GetTrackedInstance**和**GetTrackedmessage** API 调用。</span><span class="sxs-lookup"><span data-stu-id="7c549-160">Retrieve messages from the DTA using the **GetTrackedInstance** and **GetTrackedmessage** API calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c549-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7c549-161">See Also</span></span>  
 [<span data-ttu-id="7c549-162">运行时体系结构</span><span class="sxs-lookup"><span data-stu-id="7c549-162">Runtime Architecture</span></span>](../core/runtime-architecture.md)