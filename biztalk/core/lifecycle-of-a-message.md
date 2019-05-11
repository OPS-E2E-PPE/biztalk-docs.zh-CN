---
title: 一条消息的生命周期 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 305dc48db684a1e0f0ba37232b672e6ffb63406a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329668"
---
# <a name="lifecycle-of-a-message"></a><span data-ttu-id="3edd5-102">一条消息的生命周期</span><span class="sxs-lookup"><span data-stu-id="3edd5-102">Lifecycle of a Message</span></span>
<span data-ttu-id="3edd5-103">下图提供了从消息传送的角度来看的 BizTalk Server 体系结构的高级概述。</span><span class="sxs-lookup"><span data-stu-id="3edd5-103">The following figure provides a high-level overview of the BizTalk Server architecture from a messaging perspective.</span></span>  
  
 <span data-ttu-id="3edd5-104">![BizTalk Server 消息传送体系结构](../core/media/arch-messaging-01.gif "arch_messaging_01")</span><span class="sxs-lookup"><span data-stu-id="3edd5-104">![BizTalk Server messaging architecture](../core/media/arch-messaging-01.gif "arch_messaging_01")</span></span>  
  
 <span data-ttu-id="3edd5-105">在此简化视图中，通过在给定的接收端口中定义的接收位置收到消息。</span><span class="sxs-lookup"><span data-stu-id="3edd5-105">In this simplified view, a message is received through a receive location defined in a given receive port.</span></span> <span data-ttu-id="3edd5-106">此消息是由接收位置处理，然后发布到 MessageBox 数据库、 主要持久化和路由机制为 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="3edd5-106">This message is processed by the receive location and then published to the MessageBox database, the main persistence and routing mechanism for BizTalk Server.</span></span> <span data-ttu-id="3edd5-107">MessageBox 评估活动的订阅并将该消息路由到这些业务流程和发送端口使用匹配的订阅。</span><span class="sxs-lookup"><span data-stu-id="3edd5-107">The MessageBox evaluates active subscriptions and routes the message to those orchestrations and send ports with matching subscriptions.</span></span> <span data-ttu-id="3edd5-108">业务流程可能处理该消息并将通过 MessageBox 的消息发布到其中它推送到其最终目标的发送端口。</span><span class="sxs-lookup"><span data-stu-id="3edd5-108">Orchestrations may process the message and publish messages through the MessageBox to a send port where it is pushed out to its final destination.</span></span>  
  
 <span data-ttu-id="3edd5-109">以下是 BizTalk Server 消息处理过程中涉及的关键组件。</span><span class="sxs-lookup"><span data-stu-id="3edd5-109">The following are key components involved in BizTalk Server message processing.</span></span>  
  
## <a name="receive-ports-and-receive-locations"></a><span data-ttu-id="3edd5-110">接收端口和接收位置</span><span class="sxs-lookup"><span data-stu-id="3edd5-110">Receive Ports and Receive Locations</span></span>  
 <span data-ttu-id="3edd5-111">一个*接收端口*是一系列一个或多个接收到 BizTalk Server 定义的特定入口点的位置。</span><span class="sxs-lookup"><span data-stu-id="3edd5-111">A *receive port* is a collection of one or more receive locations that define specific entry points into BizTalk Server.</span></span> <span data-ttu-id="3edd5-112">一个*接收位置*是单个终结点 (URL) 的配置以接收消息。</span><span class="sxs-lookup"><span data-stu-id="3edd5-112">A *receive location* is the configuration of a single endpoint (URL) to receive messages.</span></span> <span data-ttu-id="3edd5-113">位置包含一个接收适配器和接收管道的配置信息。</span><span class="sxs-lookup"><span data-stu-id="3edd5-113">The location contains configuration information for both a receive adapter and a receive pipeline.</span></span> <span data-ttu-id="3edd5-114">*适配器*负责接收消息的传输和通信部分。</span><span class="sxs-lookup"><span data-stu-id="3edd5-114">The *adapter* is responsible for the transport and communications part of receiving a message.</span></span> <span data-ttu-id="3edd5-115">示例包括文件适配器和 SOAP 适配器，其中每个接收来自不同类型的源的消息。</span><span class="sxs-lookup"><span data-stu-id="3edd5-115">Examples include the File adapter and SOAP adapter, each of which receives messages from different types of sources.</span></span> <span data-ttu-id="3edd5-116">接收管道负责准备发布到 MessageBox 的消息。</span><span class="sxs-lookup"><span data-stu-id="3edd5-116">The receive pipeline is responsible for preparing the message for publishing into the MessageBox.</span></span> <span data-ttu-id="3edd5-117">一个*管道*是一系列序列，每个都提供一条消息，例如解密/加密到特定的处理、 分析过程中，或验证中执行的组件。</span><span class="sxs-lookup"><span data-stu-id="3edd5-117">A *pipeline* is a series of components that are executed in sequence, each providing specific processing to a message such as decryption/encryption, parsing, or validation.</span></span> <span data-ttu-id="3edd5-118">有关管道的详细信息，接收端口和接收位置，请参阅[项目](../core/artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="3edd5-118">For more information about pipelines, receive ports, and receive locations, see [Artifacts](../core/artifacts.md).</span></span>  
  
## <a name="send-ports-and-send-port-groups"></a><span data-ttu-id="3edd5-119">发送端口和发送端口组</span><span class="sxs-lookup"><span data-stu-id="3edd5-119">Send Ports and Send Port Groups</span></span>  
 <span data-ttu-id="3edd5-120">一个*发送端口*是发送管道和发送适配器的组合。</span><span class="sxs-lookup"><span data-stu-id="3edd5-120">A *send port* is the combination of a send pipeline and a send adapter.</span></span> <span data-ttu-id="3edd5-121">发送端口组是发送端口的集合，作用很像电子邮件通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="3edd5-121">A send port group is a collection of send ports and works much like an e-mail distribution list.</span></span> <span data-ttu-id="3edd5-122">发送到发送端口组的消息将发送到该组中的所有发送端口。</span><span class="sxs-lookup"><span data-stu-id="3edd5-122">A message sent to a send port group will be sent to all send ports in that group.</span></span> <span data-ttu-id="3edd5-123">发送管道用于准备即将从 BizTalk Server 传输到另一个服务的消息。</span><span class="sxs-lookup"><span data-stu-id="3edd5-123">The send pipeline is used to prepare a message coming from BizTalk Server for transmission to another service.</span></span> <span data-ttu-id="3edd5-124">发送适配器负责使用特定的协议，例如 SOAP 或 FTP 将消息实际上发送。</span><span class="sxs-lookup"><span data-stu-id="3edd5-124">The send adapter is responsible for actually sending the message using a specific protocol such as SOAP, or FTP.</span></span> <span data-ttu-id="3edd5-125">发送端口和发送端口组的详细信息，请参阅[项目](../core/artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="3edd5-125">For more information on send ports and send port groups, see [Artifacts](../core/artifacts.md).</span></span>  
  
## <a name="orchestrations"></a><span data-ttu-id="3edd5-126">业务流程</span><span class="sxs-lookup"><span data-stu-id="3edd5-126">Orchestrations</span></span>  
 <span data-ttu-id="3edd5-127">业务流程可以订阅 （接收） 和发布 （发送） 消息通过 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="3edd5-127">Orchestrations can subscribe to (receive) and publish (send) messages through the MessageBox.</span></span> <span data-ttu-id="3edd5-128">此外，业务流程可以构造新消息。</span><span class="sxs-lookup"><span data-stu-id="3edd5-128">In addition, orchestrations can construct new messages.</span></span> <span data-ttu-id="3edd5-129">使用的订阅和路由机制已经讨论过接收消息。</span><span class="sxs-lookup"><span data-stu-id="3edd5-129">Messages are received using the subscription and routing mechanism already discussed.</span></span> <span data-ttu-id="3edd5-130">订阅的业务流程在填充后激活新的实例传递消息，或对于实例订阅，该实例解除冻结，如有必要，然后传递消息。</span><span class="sxs-lookup"><span data-stu-id="3edd5-130">When subscriptions are filled for orchestrations, a new instance is activated and the message is delivered, or in the case of instance subscriptions, the instance is rehydrated if necessary and the message is then delivered.</span></span> <span data-ttu-id="3edd5-131">当从业务流程发送消息时，它们是相同的方式发布到 MessageBox，消息到达接收位置的相应属性插入到在路由中使用的数据库。</span><span class="sxs-lookup"><span data-stu-id="3edd5-131">When messages are sent from an orchestration, they are published to the MessageBox in the same manner as a message arriving at a receive location with the appropriate properties is inserted into the database for use in routing.</span></span> <span data-ttu-id="3edd5-132">有关业务流程的详细信息，请参阅[项目](../core/artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="3edd5-132">For more information about orchestrations, see [Artifacts](../core/artifacts.md).</span></span>  
  
## <a name="messagebox-database"></a><span data-ttu-id="3edd5-133">MessageBox 数据库</span><span class="sxs-lookup"><span data-stu-id="3edd5-133">MessageBox Database</span></span>  
 <span data-ttu-id="3edd5-134">在 BizTalk Server 中的发布/订阅引擎的核心是 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="3edd5-134">The heart of the publish/subscribe engine in BizTalk Server is the MessageBox database.</span></span> <span data-ttu-id="3edd5-135">MessageBox 由两个组件组成： 一个或多个 Microsoft SQL Server 数据库和消息代理。</span><span class="sxs-lookup"><span data-stu-id="3edd5-135">The MessageBox is made up of two components: one or more Microsoft SQL Server databases and the Message Agent.</span></span> <span data-ttu-id="3edd5-136">SQL Server 数据库提供的许多事情，包括消息、 消息属性、 订阅、 业务流程状态、 跟踪数据和用于路由的主机队列的持久性存储区。</span><span class="sxs-lookup"><span data-stu-id="3edd5-136">The SQL Server database provides the persistence store for many things including messages, message properties, subscriptions, orchestration states, tracking data, and host queues for routing.</span></span> <span data-ttu-id="3edd5-137">有关 MessageBox 数据库的详细信息，请参阅[MessageBox 数据库](../core/the-messagebox-database.md)。</span><span class="sxs-lookup"><span data-stu-id="3edd5-137">For more information about the MessageBox database, see [The MessageBox Database](../core/the-messagebox-database.md).</span></span>  
  
## <a name="hosts-and-host-instances"></a><span data-ttu-id="3edd5-138">主机和主机实例</span><span class="sxs-lookup"><span data-stu-id="3edd5-138">Hosts and Host Instances</span></span>  
 <span data-ttu-id="3edd5-139">一个*主机*是如执行 BizTalk Server 项目的 Microsoft Windows 进程的逻辑表示发送端口和业务流程。</span><span class="sxs-lookup"><span data-stu-id="3edd5-139">A *host* is a logical representation of a Microsoft Windows process that executes BizTalk Server artifacts such as send ports and orchestrations.</span></span> <span data-ttu-id="3edd5-140">一个*主机实例*特定服务器上的主机的物理表示形式。</span><span class="sxs-lookup"><span data-stu-id="3edd5-140">A *host instance* is the physical representation of a host on a specific server.</span></span> <span data-ttu-id="3edd5-141">主机可以是为在进程内主机，这意味着它是由拥有和管理 BizTalk Server 或独立的主机，这意味着，不受 BizTalk Server 进程中运行的 BizTalk Server 代码。</span><span class="sxs-lookup"><span data-stu-id="3edd5-141">A host can be either an in-process host, which means it is owned and managed by BizTalk Server, or an isolated host, which means that the BizTalk Server code is running in a process that is not controlled by BizTalk Server.</span></span> <span data-ttu-id="3edd5-142">独立主机的一个很好示例是 Internet 信息服务 (IIS) 承载的 HTTP 和 SOAP 适配器的接收功能。</span><span class="sxs-lookup"><span data-stu-id="3edd5-142">A good example of an isolated host is Internet Information Services (IIS), which hosts the receive functionality of the HTTP and SOAP adapters.</span></span> <span data-ttu-id="3edd5-143">为整个 BizTalk Server 组; 定义主机共享配置、 Messagebox、 端口和等等的 BizTalk 服务器的集合。</span><span class="sxs-lookup"><span data-stu-id="3edd5-143">Hosts are defined for an entire BizTalk Server group; a collection of BizTalk Servers that share configuration, MessageBoxes, ports, and so on.</span></span> <span data-ttu-id="3edd5-144">有关主机和主机实例的详细信息，请参阅[实体](../core/entities.md)。</span><span class="sxs-lookup"><span data-stu-id="3edd5-144">For more information about hosts and host instances, see [Entities](../core/entities.md).</span></span>  
  
## <a name="saving-a-message-body"></a><span data-ttu-id="3edd5-145">保存消息正文</span><span class="sxs-lookup"><span data-stu-id="3edd5-145">Saving a Message Body</span></span>  
 <span data-ttu-id="3edd5-146">有三种方法来保存消息正文。</span><span class="sxs-lookup"><span data-stu-id="3edd5-146">There are three ways to save a message body.</span></span>  
  
### <a name="from-the-admin-mmc-group-hub-page-queries"></a><span data-ttu-id="3edd5-147">从管理 MMC 组中心页查询</span><span class="sxs-lookup"><span data-stu-id="3edd5-147">From the Admin MMC group hub page queries</span></span>  
 <span data-ttu-id="3edd5-148">此方法适用于只在 MessageBox 数据库中的消息。</span><span class="sxs-lookup"><span data-stu-id="3edd5-148">This method is for messages in the MessageBox database only.</span></span>  
  
-   <span data-ttu-id="3edd5-149">查看服务实例。</span><span class="sxs-lookup"><span data-stu-id="3edd5-149">View a Service Instance.</span></span>  
  
-   <span data-ttu-id="3edd5-150">打开**服务实例详细信息**对话框。</span><span class="sxs-lookup"><span data-stu-id="3edd5-150">Open the **Service Instance Details** dialog box.</span></span>  
  
-   <span data-ttu-id="3edd5-151">单击**消息选项卡**若要查看与此实例关联的消息列表。</span><span class="sxs-lookup"><span data-stu-id="3edd5-151">Click the **Messages Tab** to view the list of messages associated with this instance.</span></span>  
  
-   <span data-ttu-id="3edd5-152">右键单击该消息，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="3edd5-152">Either right-click the message, and then click **Save**.</span></span>  
  
     <span data-ttu-id="3edd5-153">-或-</span><span class="sxs-lookup"><span data-stu-id="3edd5-153">-or-</span></span>  
  
-   <span data-ttu-id="3edd5-154">双击要打开该文件的消息**消息查看器**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="3edd5-154">Double-click the message to open it in the **Message Viewer**, and click **Save**.</span></span>  
  
### <a name="from-the-operations-om"></a><span data-ttu-id="3edd5-155">从操作 OM</span><span class="sxs-lookup"><span data-stu-id="3edd5-155">From the Operations OM</span></span>  
  
-   <span data-ttu-id="3edd5-156">使用**GetInstance**检索服务实例对象。</span><span class="sxs-lookup"><span data-stu-id="3edd5-156">Use **GetInstance** to retrieve a Service Instance object.</span></span>  
  
-   <span data-ttu-id="3edd5-157">使用**Instance.Messages []** 来枚举服务实例当前引用的所有消息。</span><span class="sxs-lookup"><span data-stu-id="3edd5-157">Use **Instance.Messages [ ]** to enumerate all messages which the service instance currently references.</span></span>  
  
-   <span data-ttu-id="3edd5-158">如使用消息对象上的方法**Message.BodyPart []** 并**Message.Context []** 访问并将其保存。</span><span class="sxs-lookup"><span data-stu-id="3edd5-158">Use methods on the message object such as **Message.BodyPart [ ]** and **Message.Context [  ]** to access and save it.</span></span>  
  
### <a name="from-the-dta"></a><span data-ttu-id="3edd5-159">从 DTA</span><span class="sxs-lookup"><span data-stu-id="3edd5-159">From the DTA</span></span>  
  
-   <span data-ttu-id="3edd5-160">从 DTA 使用检索的消息**GetTrackedInstance**并**GetTrackedmessage** API 调用。</span><span class="sxs-lookup"><span data-stu-id="3edd5-160">Retrieve messages from the DTA using the **GetTrackedInstance** and **GetTrackedmessage** API calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3edd5-161">请参阅</span><span class="sxs-lookup"><span data-stu-id="3edd5-161">See Also</span></span>  
 [<span data-ttu-id="3edd5-162">运行时体系结构</span><span class="sxs-lookup"><span data-stu-id="3edd5-162">Runtime Architecture</span></span>](../core/runtime-architecture.md)