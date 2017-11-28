---
title: "MessageBox 数据库 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, MessageBox database
- messages, suspended messages
- MessageBox database, messages
- MessageBox database, about MessageBox database
- MessageBox database, suspended messages
- suspended messages
- MessageBox database
- suspended messages, MessageBox database
ms.assetid: f89eb02c-1b83-4127-8a91-e78fb4a1f96e
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: edf1fb3a89d6e08f6a0183a3242c53c4be890e60
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-messagebox-database"></a><span data-ttu-id="6c56d-102">MessageBox 数据库</span><span class="sxs-lookup"><span data-stu-id="6c56d-102">The MessageBox Database</span></span>
<span data-ttu-id="6c56d-103">Microsoft BizTalk Server 中发布/订阅引擎的核心是 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="6c56d-103">The heart of the publish/subscribe engine in Microsoft BizTalk Server is the MessageBox database.</span></span> <span data-ttu-id="6c56d-104">MessageBox 由两个组件构成：一个或多个 Microsoft SQL Server 数据库，以及消息传送代理。</span><span class="sxs-lookup"><span data-stu-id="6c56d-104">The MessageBox is made up of two components: one or more Microsoft SQL Server databases and the Messaging Agent.</span></span> <span data-ttu-id="6c56d-105">SQL Server 数据库为众多对象提供持久化存储，这些对象包括消息、消息部分、消息属性、订阅、业务流程状态、跟踪数据和用于路由的主机队列等。</span><span class="sxs-lookup"><span data-stu-id="6c56d-105">The SQL Server database provides the persistence store for many things including messages, message parts, message properties, subscriptions, orchestration state, tracking data, host queues for routing, and others.</span></span> <span data-ttu-id="6c56d-106">BizTalk Server 组可以具有一个或多个 MessageBox 数据库，该组将消息发布到此（这些）数据库中，而订阅这些消息的订户从此（这些）数据库提取消息。</span><span class="sxs-lookup"><span data-stu-id="6c56d-106">The BizTalk Server group may have one or more MessageBox databases into which it publishes messages and from which subscribers to those messages extract messages.</span></span>  
  
 <span data-ttu-id="6c56d-107">数据库提供一些与路由消息和履行订阅相关的逻辑。</span><span class="sxs-lookup"><span data-stu-id="6c56d-107">The database provides some of the logic related to routing messages and fulfilling subscriptions.</span></span> <span data-ttu-id="6c56d-108">然而，消息代理是封装和提取数据库组件的组件，并且是 BizTalk Server 用于与 MessageBox 交互的接口。</span><span class="sxs-lookup"><span data-stu-id="6c56d-108">The Message Agent, however, is the component that encapsulates and abstracts the database component and is the interface used by BizTalk Server to interact with the MessageBox.</span></span> <span data-ttu-id="6c56d-109">消息代理是组件对象模型 (COM) 组件，为发布消息、订阅消息、检索消息等操作提供接口。</span><span class="sxs-lookup"><span data-stu-id="6c56d-109">The Message Agent is a Component Object Model (COM) component that provides interfaces for publishing messages, subscribing to messages, retrieving messages, and so on.</span></span> <span data-ttu-id="6c56d-110">此接口是其他 BizTalk Server 组件（包括适配器框架和业务流程）用于与 MessageBox 交互的唯一机制。</span><span class="sxs-lookup"><span data-stu-id="6c56d-110">This interface is the only mechanism used by other BizTalk Server components, including the adapter framework and orchestrations, to interact with the MessageBox.</span></span>  
  
## <a name="the-messagebox-and-the-message"></a><span data-ttu-id="6c56d-111">MessageBox 和消息</span><span class="sxs-lookup"><span data-stu-id="6c56d-111">The MessageBox and the Message</span></span>  
 <span data-ttu-id="6c56d-112">MessageBox 数据库订阅是一组既定信息和服务信息。</span><span class="sxs-lookup"><span data-stu-id="6c56d-112">A MessageBox database subscription is a set of established information and service information.</span></span> <span data-ttu-id="6c56d-113">既定（或谓词）信息是消息必须满足的条件。</span><span class="sxs-lookup"><span data-stu-id="6c56d-113">The established (or predicate) information is the criteria that a message must meet.</span></span> <span data-ttu-id="6c56d-114">服务信息是有关如何处理满足条件的消息的信息。</span><span class="sxs-lookup"><span data-stu-id="6c56d-114">The service information is what to do with the message that meets the criteria.</span></span> <span data-ttu-id="6c56d-115">所有这些信息都存储在一组调用消息和业务流程引擎的表中。</span><span class="sxs-lookup"><span data-stu-id="6c56d-115">All of this information is stored in a set of tables that call the messaging and orchestration engine.</span></span>  
  
 <span data-ttu-id="6c56d-116">BizTalk Server 在接收消息后，将在管道中处理该消息，然后将该消息放置在 MessageBox 数据库中。</span><span class="sxs-lookup"><span data-stu-id="6c56d-116">When BizTalk Server receives a message, it processes the message in a pipeline, and places the message in the MessageBox database.</span></span> <span data-ttu-id="6c56d-117">传入消息具有上下文。</span><span class="sxs-lookup"><span data-stu-id="6c56d-117">The incoming message has a context.</span></span> <span data-ttu-id="6c56d-118">消息上下文是一组与消息关联的属性。</span><span class="sxs-lookup"><span data-stu-id="6c56d-118">The message context is a set of properties associated with the message.</span></span> <span data-ttu-id="6c56d-119">以下是三种类型的消息上下文属性：</span><span class="sxs-lookup"><span data-stu-id="6c56d-119">The three types of message context properties are:</span></span>  
  
-   <span data-ttu-id="6c56d-120">直接编写的属性</span><span class="sxs-lookup"><span data-stu-id="6c56d-120">Simple written properties</span></span>  
  
-   <span data-ttu-id="6c56d-121">提升的属性</span><span class="sxs-lookup"><span data-stu-id="6c56d-121">Promoted properties</span></span>  
  
-   <span data-ttu-id="6c56d-122">谓词属性</span><span class="sxs-lookup"><span data-stu-id="6c56d-122">Predicate properties</span></span>  
  
 <span data-ttu-id="6c56d-123">升级消息属性和谓词消息属性指示订阅此消息的业务流程，以及该业务流程是否具有接收该消息所需的权限。</span><span class="sxs-lookup"><span data-stu-id="6c56d-123">The promoted and predicate message properties indicate the business process that subscribes to this message, and whether the business process has the permissions necessary to receive the message.</span></span>  
  
 <span data-ttu-id="6c56d-124">如果有业务流程订阅消息，则 MessageBox 数据库将向该业务流程发送所订阅的消息。</span><span class="sxs-lookup"><span data-stu-id="6c56d-124">If a business process subscribes to the message, the MessageBox database sends the message to the business process.</span></span> <span data-ttu-id="6c56d-125">当业务流程接收到消息后，将在可用的主机实例上处理该消息。</span><span class="sxs-lookup"><span data-stu-id="6c56d-125">When the business process receives the message, it processes the message on an available host instance.</span></span> <span data-ttu-id="6c56d-126">在处理消息后，如果业务流程订阅了管道或发送端口，则该业务流程将向 MessageBox 数据库发送一个返回消息。</span><span class="sxs-lookup"><span data-stu-id="6c56d-126">After processing the message, if the business process subscribes to a pipeline or send port, the business process sends a return message to the MessageBox database.</span></span>  
  
 <span data-ttu-id="6c56d-127">对于每个 BizTalk 主机，关联的 MessageBox 具有一个工作队列和一个挂起队列。</span><span class="sxs-lookup"><span data-stu-id="6c56d-127">For each BizTalk Host, the associated MessageBox has one work queue and one suspended queue.</span></span> <span data-ttu-id="6c56d-128">此外，每个 MessageBox 数据库都包含一组静态状态、动态状态和实例状态表。</span><span class="sxs-lookup"><span data-stu-id="6c56d-128">Additionally, each MessageBox database contains a set of tables for static states, dynamic states, and instance state.</span></span> <span data-ttu-id="6c56d-129">有关 BizTalk 主机的信息，请参阅[实体](../core/entities.md)。</span><span class="sxs-lookup"><span data-stu-id="6c56d-129">For information about BizTalk Hosts, see [Entities](../core/entities.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6c56d-130">如果主机变得不可用（例如，从该主机接收消息的 MessageBox 数据库变得不可用），则其他所有 MessageBox 数据库也将不可用。</span><span class="sxs-lookup"><span data-stu-id="6c56d-130">If a host becomes unavailable --for example, the MessageBox database that receives messages from that host becomes unavailable, all other MessageBox databases become unavailable.</span></span>  
  
 <span data-ttu-id="6c56d-131">运行配置向导时创建第一个 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="6c56d-131">You create the first MessageBox database when you run the Configuration Wizard.</span></span> <span data-ttu-id="6c56d-132">所配置的 MessageBox 数据库将成为主 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="6c56d-132">The MessageBox database that is configured becomes the master MessageBox database.</span></span> <span data-ttu-id="6c56d-133">主 MessageBox 数据库将对订阅进行评估并将其路由至 BizTalk Server 环境中的其他所有 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="6c56d-133">The master MessageBox database evaluates and routes subscriptions to all other MessageBox databases in the BizTalk Server environment.</span></span> <span data-ttu-id="6c56d-134">有关可提高 master MessageBox 数据库性能的信息，请参阅[管理 MessageBox 数据库](../core/managing-messagebox-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="6c56d-134">For information about improving performance for the master MessageBox database, see [Managing MessageBox Databases](../core/managing-messagebox-databases.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6c56d-135">必须使用 SQL Server 群集以便为 MessageBox 数据库提供故障转移保护。</span><span class="sxs-lookup"><span data-stu-id="6c56d-135">You must use SQL Server clustering to provide failover protection for MessageBox databases.</span></span>  
  
## <a name="suspended-messages-in-the-messagebox-database"></a><span data-ttu-id="6c56d-136">MessageBox 数据库中的挂起消息</span><span class="sxs-lookup"><span data-stu-id="6c56d-136">Suspended Messages in the MessageBox Database</span></span>  
 <span data-ttu-id="6c56d-137">BizTalk Server 将与挂起管道关联的消息存储在 MessageBox 数据库中。</span><span class="sxs-lookup"><span data-stu-id="6c56d-137">BizTalk Server stores messages associated with suspended pipelines in the MessageBox database.</span></span> <span data-ttu-id="6c56d-138">如果管道中发生故障，BizTalk Server 将挂起消息的实例。</span><span class="sxs-lookup"><span data-stu-id="6c56d-138">If a failure occurs in the pipeline, BizTalk Server suspends the instance of a message.</span></span> <span data-ttu-id="6c56d-139">挂起的服务实例分为两种类型：</span><span class="sxs-lookup"><span data-stu-id="6c56d-139">There are two types of suspended service instances:</span></span>  
  
-   <span data-ttu-id="6c56d-140">可以恢复的挂起的实例。</span><span class="sxs-lookup"><span data-stu-id="6c56d-140">Suspended instances that you can resume.</span></span>  
  
-   <span data-ttu-id="6c56d-141">无法恢复的挂起的实例。</span><span class="sxs-lookup"><span data-stu-id="6c56d-141">Suspended instances that you cannot resume.</span></span> <span data-ttu-id="6c56d-142">例如，如果实例已损坏。</span><span class="sxs-lookup"><span data-stu-id="6c56d-142">For example, if an instance is corrupt.</span></span>  
  
 <span data-ttu-id="6c56d-143">根据挂起的原因，您可以恢复 BizTalk Server 挂起的服务 -- 例如，如果业务流程遇到挂起形状，或者传输无法传送消息，则 BizTalk Server 不会自动删除您无法从 MessageBox 数据库恢复的已挂起实例。</span><span class="sxs-lookup"><span data-stu-id="6c56d-143">Depending on the cause of the suspension, you may be able to resume services that BizTalk Server suspends -- for example, if an orchestration hits a Suspend shape, or if a transport was unable to deliver a message, BizTalk Server does not automatically remove suspended instances that you cannot resume from the MessageBox database.</span></span> <span data-ttu-id="6c56d-144">您可以选择将服务实例保存到磁盘，然后再将其从挂起队列中删除。</span><span class="sxs-lookup"><span data-stu-id="6c56d-144">You can choose to save a service instance to disk before removing it from the suspended queue.</span></span>  
  
 <span data-ttu-id="6c56d-145">有关备份 MessageBox 数据库的信息，请参阅[Backing Up and Restoring BizTalk Server Databases](../core/backing-up-and-restoring-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="6c56d-145">For information about backing up MessageBox databases, see [Backing Up and Restoring BizTalk Server Databases](../core/backing-up-and-restoring-biztalk-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c56d-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6c56d-146">See Also</span></span>  
 [<span data-ttu-id="6c56d-147">消息传送的引擎</span><span class="sxs-lookup"><span data-stu-id="6c56d-147">The Messaging Engine</span></span>](../core/the-messaging-engine.md)