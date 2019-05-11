---
title: MessageBox 数据库 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 435f6b26e2844bbf7aac8423415c83be119eea4e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394120"
---
# <a name="the-messagebox-database"></a><span data-ttu-id="ff95d-102">MessageBox 数据库</span><span class="sxs-lookup"><span data-stu-id="ff95d-102">The MessageBox Database</span></span>
<span data-ttu-id="ff95d-103">Microsoft BizTalk Server 中的发布/订阅引擎的核心是 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="ff95d-103">The heart of the publish/subscribe engine in Microsoft BizTalk Server is the MessageBox database.</span></span> <span data-ttu-id="ff95d-104">MessageBox 由两个组件组成： 一个或多个 Microsoft SQL Server 数据库和消息传送代理。</span><span class="sxs-lookup"><span data-stu-id="ff95d-104">The MessageBox is made up of two components: one or more Microsoft SQL Server databases and the Messaging Agent.</span></span> <span data-ttu-id="ff95d-105">SQL Server 数据库提供的许多方面，包括消息、 消息部分、 消息属性、 订阅、 业务流程状态、 跟踪数据、 用于路由的主机队列和其他持久性存储区。</span><span class="sxs-lookup"><span data-stu-id="ff95d-105">The SQL Server database provides the persistence store for many things including messages, message parts, message properties, subscriptions, orchestration state, tracking data, host queues for routing, and others.</span></span> <span data-ttu-id="ff95d-106">BizTalk Server 组可能具有一个或多个 MessageBox 数据库在其中它将发布消息和从其对这些邮件的订阅服务器中提取消息。</span><span class="sxs-lookup"><span data-stu-id="ff95d-106">The BizTalk Server group may have one or more MessageBox databases into which it publishes messages and from which subscribers to those messages extract messages.</span></span>  
  
 <span data-ttu-id="ff95d-107">数据库提供了一些与路由消息和履行订阅相关的逻辑。</span><span class="sxs-lookup"><span data-stu-id="ff95d-107">The database provides some of the logic related to routing messages and fulfilling subscriptions.</span></span> <span data-ttu-id="ff95d-108">消息代理，但是，是封装和提取数据库组件并且是 BizTalk Server 用于与 MessageBox 交互的接口的组件。</span><span class="sxs-lookup"><span data-stu-id="ff95d-108">The Message Agent, however, is the component that encapsulates and abstracts the database component and is the interface used by BizTalk Server to interact with the MessageBox.</span></span> <span data-ttu-id="ff95d-109">消息代理是为发布的消息，提供了接口的组件对象模型 (COM) 组件订阅消息、 检索消息等。</span><span class="sxs-lookup"><span data-stu-id="ff95d-109">The Message Agent is a Component Object Model (COM) component that provides interfaces for publishing messages, subscribing to messages, retrieving messages, and so on.</span></span> <span data-ttu-id="ff95d-110">此接口是其他 BizTalk Server 组件，包括适配器框架和业务流程，用于与 MessageBox 交互的唯一机制。</span><span class="sxs-lookup"><span data-stu-id="ff95d-110">This interface is the only mechanism used by other BizTalk Server components, including the adapter framework and orchestrations, to interact with the MessageBox.</span></span>  
  
## <a name="the-messagebox-and-the-message"></a><span data-ttu-id="ff95d-111">MessageBox 和消息</span><span class="sxs-lookup"><span data-stu-id="ff95d-111">The MessageBox and the Message</span></span>  
 <span data-ttu-id="ff95d-112">MessageBox 数据库订阅是一组既定的信息和服务信息。</span><span class="sxs-lookup"><span data-stu-id="ff95d-112">A MessageBox database subscription is a set of established information and service information.</span></span> <span data-ttu-id="ff95d-113">既定 （或谓词） 信息是一条消息必须满足的条件。</span><span class="sxs-lookup"><span data-stu-id="ff95d-113">The established (or predicate) information is the criteria that a message must meet.</span></span> <span data-ttu-id="ff95d-114">要执行的操作与消息符合条件的服务信息。</span><span class="sxs-lookup"><span data-stu-id="ff95d-114">The service information is what to do with the message that meets the criteria.</span></span> <span data-ttu-id="ff95d-115">所有这些信息存储在一组调用消息传送和业务流程引擎的表。</span><span class="sxs-lookup"><span data-stu-id="ff95d-115">All of this information is stored in a set of tables that call the messaging and orchestration engine.</span></span>  
  
 <span data-ttu-id="ff95d-116">在 BizTalk Server 接收一条消息，它处理该消息在管道中，并将该消息放在 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="ff95d-116">When BizTalk Server receives a message, it processes the message in a pipeline, and places the message in the MessageBox database.</span></span> <span data-ttu-id="ff95d-117">传入消息具有上下文。</span><span class="sxs-lookup"><span data-stu-id="ff95d-117">The incoming message has a context.</span></span> <span data-ttu-id="ff95d-118">消息上下文是一组与消息关联的属性。</span><span class="sxs-lookup"><span data-stu-id="ff95d-118">The message context is a set of properties associated with the message.</span></span> <span data-ttu-id="ff95d-119">三种类型的消息上下文属性是：</span><span class="sxs-lookup"><span data-stu-id="ff95d-119">The three types of message context properties are:</span></span>  
  
- <span data-ttu-id="ff95d-120">直接编写的属性</span><span class="sxs-lookup"><span data-stu-id="ff95d-120">Simple written properties</span></span>  
  
- <span data-ttu-id="ff95d-121">升级的属性</span><span class="sxs-lookup"><span data-stu-id="ff95d-121">Promoted properties</span></span>  
  
- <span data-ttu-id="ff95d-122">谓词属性</span><span class="sxs-lookup"><span data-stu-id="ff95d-122">Predicate properties</span></span>  
  
  <span data-ttu-id="ff95d-123">升级和谓词消息属性指示订阅此消息的业务流程，该业务流程是否已接收消息所需的权限。</span><span class="sxs-lookup"><span data-stu-id="ff95d-123">The promoted and predicate message properties indicate the business process that subscribes to this message, and whether the business process has the permissions necessary to receive the message.</span></span>  
  
  <span data-ttu-id="ff95d-124">如果业务流程订阅该消息，MessageBox 数据库会将消息发送到业务流程。</span><span class="sxs-lookup"><span data-stu-id="ff95d-124">If a business process subscribes to the message, the MessageBox database sends the message to the business process.</span></span> <span data-ttu-id="ff95d-125">当业务流程收到消息时，它处理上可用的主机实例的消息。</span><span class="sxs-lookup"><span data-stu-id="ff95d-125">When the business process receives the message, it processes the message on an available host instance.</span></span> <span data-ttu-id="ff95d-126">处理消息之后, 如果业务流程订阅了管道或发送端口，业务流程将发送返回消息到 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="ff95d-126">After processing the message, if the business process subscribes to a pipeline or send port, the business process sends a return message to the MessageBox database.</span></span>  
  
  <span data-ttu-id="ff95d-127">对于每个 BizTalk 主机，关联的 MessageBox 具有一个工作队列和一个挂起的队列。</span><span class="sxs-lookup"><span data-stu-id="ff95d-127">For each BizTalk Host, the associated MessageBox has one work queue and one suspended queue.</span></span> <span data-ttu-id="ff95d-128">此外，每个 MessageBox 数据库包含一组静态状态、 动态状态和实例状态表。</span><span class="sxs-lookup"><span data-stu-id="ff95d-128">Additionally, each MessageBox database contains a set of tables for static states, dynamic states, and instance state.</span></span> <span data-ttu-id="ff95d-129">有关 BizTalk 主机的信息，请参阅[实体](../core/entities.md)。</span><span class="sxs-lookup"><span data-stu-id="ff95d-129">For information about BizTalk Hosts, see [Entities](../core/entities.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ff95d-130">如果主机变得不可用-例如，从该主机接收消息的 MessageBox 数据库变得不可用，其他所有 MessageBox 数据库变都得不可用。</span><span class="sxs-lookup"><span data-stu-id="ff95d-130">If a host becomes unavailable --for example, the MessageBox database that receives messages from that host becomes unavailable, all other MessageBox databases become unavailable.</span></span>  
  
 <span data-ttu-id="ff95d-131">当您运行配置向导时创建的第一个 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="ff95d-131">You create the first MessageBox database when you run the Configuration Wizard.</span></span> <span data-ttu-id="ff95d-132">配置的 MessageBox 数据库将成为主 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="ff95d-132">The MessageBox database that is configured becomes the master MessageBox database.</span></span> <span data-ttu-id="ff95d-133">主 MessageBox 数据库的计算结果并将订阅路由到 BizTalk Server 环境中的其他所有 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="ff95d-133">The master MessageBox database evaluates and routes subscriptions to all other MessageBox databases in the BizTalk Server environment.</span></span> <span data-ttu-id="ff95d-134">有关提高主 MessageBox 数据库的性能信息，请参阅[管理 MessageBox 数据库](../core/managing-messagebox-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="ff95d-134">For information about improving performance for the master MessageBox database, see [Managing MessageBox Databases](../core/managing-messagebox-databases.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ff95d-135">必须使用 SQL Server 群集以提供对 MessageBox 数据库的故障转移保护。</span><span class="sxs-lookup"><span data-stu-id="ff95d-135">You must use SQL Server clustering to provide failover protection for MessageBox databases.</span></span>  
  
## <a name="suspended-messages-in-the-messagebox-database"></a><span data-ttu-id="ff95d-136">MessageBox 数据库中的挂起的消息</span><span class="sxs-lookup"><span data-stu-id="ff95d-136">Suspended Messages in the MessageBox Database</span></span>  
 <span data-ttu-id="ff95d-137">BizTalk Server 将存储与 MessageBox 数据库中的挂起管道相关联的消息。</span><span class="sxs-lookup"><span data-stu-id="ff95d-137">BizTalk Server stores messages associated with suspended pipelines in the MessageBox database.</span></span> <span data-ttu-id="ff95d-138">如果管道中发生故障，BizTalk Server 将挂起的消息实例。</span><span class="sxs-lookup"><span data-stu-id="ff95d-138">If a failure occurs in the pipeline, BizTalk Server suspends the instance of a message.</span></span> <span data-ttu-id="ff95d-139">有两种类型的挂起的服务实例：</span><span class="sxs-lookup"><span data-stu-id="ff95d-139">There are two types of suspended service instances:</span></span>  
  
- <span data-ttu-id="ff95d-140">可恢复的挂起的实例。</span><span class="sxs-lookup"><span data-stu-id="ff95d-140">Suspended instances that you can resume.</span></span>  
  
- <span data-ttu-id="ff95d-141">无法恢复的挂起的实例。</span><span class="sxs-lookup"><span data-stu-id="ff95d-141">Suspended instances that you cannot resume.</span></span> <span data-ttu-id="ff95d-142">例如，如果实例已损坏。</span><span class="sxs-lookup"><span data-stu-id="ff95d-142">For example, if an instance is corrupt.</span></span>  
  
  <span data-ttu-id="ff95d-143">根据挂起的原因，您可能能够恢复 BizTalk Server 挂起-例如，如果业务流程遇到挂起形状，或如果传输无法传递的消息，BizTalk Server 不会自动删除挂起的服务不能恢复从 MessageBox 数据库的实例。</span><span class="sxs-lookup"><span data-stu-id="ff95d-143">Depending on the cause of the suspension, you may be able to resume services that BizTalk Server suspends -- for example, if an orchestration hits a Suspend shape, or if a transport was unable to deliver a message, BizTalk Server does not automatically remove suspended instances that you cannot resume from the MessageBox database.</span></span> <span data-ttu-id="ff95d-144">您可以选择将服务实例保存到磁盘，然后再从挂起队列中删除它。</span><span class="sxs-lookup"><span data-stu-id="ff95d-144">You can choose to save a service instance to disk before removing it from the suspended queue.</span></span>  
  
  <span data-ttu-id="ff95d-145">有关备份 MessageBox 数据库的信息，请参阅[备份和还原 BizTalk Server 数据库](../core/backing-up-and-restoring-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="ff95d-145">For information about backing up MessageBox databases, see [Backing Up and Restoring BizTalk Server Databases](../core/backing-up-and-restoring-biztalk-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff95d-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="ff95d-146">See Also</span></span>  
 [<span data-ttu-id="ff95d-147">消息引擎</span><span class="sxs-lookup"><span data-stu-id="ff95d-147">The Messaging Engine</span></span>](../core/the-messaging-engine.md)