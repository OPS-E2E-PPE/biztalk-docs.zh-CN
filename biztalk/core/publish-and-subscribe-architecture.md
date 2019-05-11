---
title: 发布和订阅体系结构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- publish/subscribe architecture, publishers
- architecture, publish/subscribe
- publishing, publish/subscribe architecture
- publish/subscribe architecture, about publish/subscribe architecture
- creating, subscriptions
- publish/subscribe architecture, Messaging Engine
- routing, publishing
- Messaging Engine, publishing
- publish/subscribe architecture, subscribers
- publish/subscribe architecture
- subscriptions, publish/subscribe architecture
- publish/subscribe architecture, creating subscriptions
- subscriptions, creating
- Messaging Engine, subscribing
- publishing, routing
- Messaging Engine, publish/subscribe architecture
- publish/subscribe architecture, events
ms.assetid: 5ed36c1f-077d-468f-a99e-60f97377cef6
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf90d1f0fe1ed298d42c6ed9b0cf1086abe8eb7f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398432"
---
# <a name="publish-and-subscribe-architecture"></a><span data-ttu-id="0ea2c-102">发布和订阅体系结构</span><span class="sxs-lookup"><span data-stu-id="0ea2c-102">Publish and Subscribe Architecture</span></span>
<span data-ttu-id="0ea2c-103">在发布/订阅设计中，您有三个组件：</span><span class="sxs-lookup"><span data-stu-id="0ea2c-103">In a publish/subscribe design, you have three components:</span></span>  
  
- <span data-ttu-id="0ea2c-104">“分发服务器属性”</span><span class="sxs-lookup"><span data-stu-id="0ea2c-104">Publishers</span></span>  
  
- <span data-ttu-id="0ea2c-105">订阅服务器</span><span class="sxs-lookup"><span data-stu-id="0ea2c-105">Subscribers</span></span>  
  
- <span data-ttu-id="0ea2c-106">事件</span><span class="sxs-lookup"><span data-stu-id="0ea2c-106">Events</span></span>  
  
  <span data-ttu-id="0ea2c-107">发布方包括接收发布中到达的消息的端口及其接收位置，将消息发布时发布的发送端口发送消息或以异步方式启动另一个业务流程和要求/响应的业务流程在从目标应用程序或传输接收响应时的消息。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-107">Publishers include receive ports that publish messages that arrive in their receive locations, orchestrations that publish messages when sending messages or starting another orchestration asynchronously, and solicit/response send ports that publish messages when they receive a response from the target application or transport.</span></span>  
  
  <span data-ttu-id="0ea2c-108">在 BizTalk Server 中，有两种主要类型的订阅： 激活和实例。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-108">In BizTalk Server, there are two main types of subscriptions: activation and instance.</span></span> <span data-ttu-id="0ea2c-109">*激活订阅*是一个指定一条消息，可满足该订阅应激活，或创建订阅服务器收到后的新实例。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-109">An *activation subscription* is one specifying that a message that fulfills the subscription should activate, or create, a new instance of the subscriber when it is received.</span></span> <span data-ttu-id="0ea2c-110">创建激活订阅的示例包括具有筛选器的发送端口或发送端口绑定到业务流程，和业务流程接收形状，将其激活属性设置为 true。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-110">Examples of things that create activation subscriptions include send ports with filters or send ports that are bound to orchestrations, and orchestration receive shapes that have their Activate property set to true.</span></span> <span data-ttu-id="0ea2c-111">*实例订阅*指示应将执行订阅的消息路由到的订阅服务器已在运行的实例。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-111">An *instance subscription* indicates that messages that fulfill the subscription should be routed to an already-running instance of the subscriber.</span></span> <span data-ttu-id="0ea2c-112">创建实例订阅的示例包括业务流程具有相关接收和请求/响应样式的接收端口等待来自 BizTalk Server 的响应。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-112">Examples of things that create instance subscriptions are orchestrations with correlated receives and request/response-style receive ports waiting for a response from BizTalk Server.</span></span>  
  
  <span data-ttu-id="0ea2c-113">两种类型在信息级别之间的区别是订阅的实例订阅包括存储在主 MessageBox 数据库订阅表中的唯一实例 ID。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-113">The difference between the two types of subscription at the information level is that an instance subscription includes the unique instance ID, stored in the subscription table in the master MessageBox database.</span></span> <span data-ttu-id="0ea2c-114">在业务流程实例或接收端口完成处理之后，激活订阅仍保持活动状态，只要登记业务流程或发送端口时，实例订阅从 MessageBox 中删除。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-114">When an orchestration instance or receive port completes processing, instance subscriptions are removed from the MessageBox while activation subscriptions remain active as long as the orchestration or send port is enlisted.</span></span>  
  
## <a name="creating-subscriptions"></a><span data-ttu-id="0ea2c-115">创建订阅</span><span class="sxs-lookup"><span data-stu-id="0ea2c-115">Creating Subscriptions</span></span>  
 <span data-ttu-id="0ea2c-116">通过在 BizTalk Server 中，在 BizTalk Server 管理数据库的 adm_ServiceClass 表中列出的服务类创建订阅。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-116">Subscriptions are created by service classes in BizTalk Server, which are listed in the adm_ServiceClass table in the BizTalk Server Management database.</span></span> <span data-ttu-id="0ea2c-117">这些服务包括缓存服务;进程内和独立消息传送，托管由终结点管理器中;和业务流程/XLANG 由 XLANG 子服务承载。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-117">These services include the caching service; in-process and isolated messaging, hosted by the Endpoint Manager; and orchestrations/XLANG hosted by the XLANG subservice.</span></span> <span data-ttu-id="0ea2c-118">每个服务类可以创建订阅和接收已发布的消息。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-118">Each of these service classes can create subscriptions and receive published messages.</span></span>  
  
 <span data-ttu-id="0ea2c-119">订阅是比较语句，称为谓词，它涉及消息上下文属性和特定于订阅的值的集合。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-119">A subscription is a collection of comparison statements, known as predicates, involving message context properties and the values specific to the subscription.</span></span> <span data-ttu-id="0ea2c-120">例如，消息类型是消息和多个订阅的上下文属性在其订阅中指定的消息类型。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-120">For example, Message Type is a context property of messages and many subscriptions specify the message type in their subscription.</span></span> <span data-ttu-id="0ea2c-121">有关订阅的常规信息被插入到订阅表由消息代理，而特定谓词则进入以下谓词表中，具体取决于为订阅指定的操作的类型之一：</span><span class="sxs-lookup"><span data-stu-id="0ea2c-121">General information about the subscription is inserted into the subscriptions table by the Message Agent while the specific predicates go into one of the following predicate tables, depending on the type of operation specified for the subscription:</span></span>  
  
- <span data-ttu-id="0ea2c-122">BitwiseANDPredicates</span><span class="sxs-lookup"><span data-stu-id="0ea2c-122">BitwiseANDPredicates</span></span>  
  
- <span data-ttu-id="0ea2c-123">EqualsPredicates</span><span class="sxs-lookup"><span data-stu-id="0ea2c-123">EqualsPredicates</span></span>  
  
- <span data-ttu-id="0ea2c-124">EqualsPredicates2ndPass</span><span class="sxs-lookup"><span data-stu-id="0ea2c-124">EqualsPredicates2ndPass</span></span>  
  
- <span data-ttu-id="0ea2c-125">ExistsPredicates</span><span class="sxs-lookup"><span data-stu-id="0ea2c-125">ExistsPredicates</span></span>  
  
- <span data-ttu-id="0ea2c-126">FirstPassPredicates</span><span class="sxs-lookup"><span data-stu-id="0ea2c-126">FirstPassPredicates</span></span>  
  
- <span data-ttu-id="0ea2c-127">GreaterThanOrEqualsPredicates</span><span class="sxs-lookup"><span data-stu-id="0ea2c-127">GreaterThanOrEqualsPredicates</span></span>  
  
- <span data-ttu-id="0ea2c-128">GreaterThanPredicates</span><span class="sxs-lookup"><span data-stu-id="0ea2c-128">GreaterThanPredicates</span></span>  
  
- <span data-ttu-id="0ea2c-129">LessThenOrEqualsPredicates</span><span class="sxs-lookup"><span data-stu-id="0ea2c-129">LessThenOrEqualsPredicates</span></span>  
  
- <span data-ttu-id="0ea2c-130">LessThenPredicates</span><span class="sxs-lookup"><span data-stu-id="0ea2c-130">LessThenPredicates</span></span>  
  
- <span data-ttu-id="0ea2c-131">NotEqualsPredicates</span><span class="sxs-lookup"><span data-stu-id="0ea2c-131">NotEqualsPredicates</span></span>  
  
  <span data-ttu-id="0ea2c-132">所有这些都通过调用 Bts_CreateSubscription_\<应用程序名称\>和 Bts_InsertPredicate_\<应用程序名称\>存储的过程在 MessageBox 数据库的位置\<应用程序名称\>是创建订阅的 BizTalk 主机的名称。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-132">All of this is accomplished by calling the Bts_CreateSubscription_\<application name\> and Bts_InsertPredicate_\<application name\> stored procedures in the MessageBox database where \<application name\> is the name of the BizTalk host that is creating the subscription.</span></span>  
  
  <span data-ttu-id="0ea2c-133">当已登记的发送端口时，端口创建，至少一种订阅的任何消息，发送端口的传输 ID 的上下文中。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-133">When a send port is enlisted, the port creates, at a minimum, a subscription for any message with that send port's transport ID in the context.</span></span> <span data-ttu-id="0ea2c-134">这样，要始终接收专门为它的消息的发送端口。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-134">This allows the send port to always receive messages intended specifically for it.</span></span> <span data-ttu-id="0ea2c-135">当业务流程端口绑定到特定的发送端口时，绑定的相关信息存储在 BizTalk 管理数据库。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-135">When an orchestration port is bound to a particular send port, the information about that binding is stored in the BizTalk Management database.</span></span> <span data-ttu-id="0ea2c-136">从发送消息时通过绑定到物理端口的业务流程发送端口，传输 ID 包含在上下文，以便将消息路由到正确的发送端口。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-136">When messages are sent from the orchestration through the port bound to the physical send port, the Transport ID is included in the context so that the message gets routed to that send port.</span></span> <span data-ttu-id="0ea2c-137">但是，务必注意，此发送端口并不唯一发送端口可以接收发自该业务流程的消息。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-137">However, it is important to note that this send port is not the only send port that can receive messages sent from the orchestration.</span></span> <span data-ttu-id="0ea2c-138">当业务流程发送消息时，该消息发布到相关的升级属性的所有 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-138">When an orchestration sends a message, that message is published to the MessageBox with all of the relevant promoted properties.</span></span> <span data-ttu-id="0ea2c-139">保证绑定的发送端口以接收消息的副本，因为传输 ID 是在上下文中，但任何其他发送端口或业务流程中，可以有也与消息属性相匹配的订阅。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-139">The bound send port is guaranteed to receive a copy of the message because the transport ID is in the context, but any other send port, or orchestration, can have a subscription that also matches the message properties.</span></span> <span data-ttu-id="0ea2c-140">它是非常重要，若要了解，一条消息直接发布到 MessageBox，任何时候具有匹配订阅的所有订阅服务器会收到该消息的副本。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-140">It is very important to understand that any time a message is published directly to the MessageBox, all subscribers with matching subscriptions will receive a copy of the message.</span></span>  
  
## <a name="publishing-and-routing"></a><span data-ttu-id="0ea2c-141">发布和路由</span><span class="sxs-lookup"><span data-stu-id="0ea2c-141">Publishing and Routing</span></span>  
 <span data-ttu-id="0ea2c-142">创建订阅并将其启用后，任何处理之前，必须发布一条消息。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-142">After a subscription is created and enabled, a message must be published before any processing takes place.</span></span> <span data-ttu-id="0ea2c-143">它们被接收到 BizTalk Server 从前面提到的服务之一时，发布消息。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-143">Messages are published when they are received into BizTalk Server from one of the services mentioned previously.</span></span> <span data-ttu-id="0ea2c-144">有关路由的此讨论，我们将重点介绍通过适配器接收到 BizTalk Server 中的消息。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-144">For this discussion of routing, we will focus on messages received into BizTalk Server through an adapter.</span></span>  
  
 <span data-ttu-id="0ea2c-145">在消息经过接收管道处理，属性将升级到消息上下文。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-145">When messages go through the receive pipeline processing, properties are promoted into the message context.</span></span> <span data-ttu-id="0ea2c-146">一条消息已准备好接收适配器和管道处理后发布到 MessageBox 后，第一件事是消息代理将升级的属性的属性值和谓词值插入从消息到主 MessageBox SQL Server 数据库的上下文。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-146">After a message is ready to be published into the MessageBox after being processed by the receive adapter and pipeline, the first thing that happens is the Message Agent inserts the property values for the promoted properties and predicate values from the message context into the master MessageBox SQL Server database.</span></span> <span data-ttu-id="0ea2c-147">将这些值插入数据库中，则消息代理做出路由决策。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-147">Having these values in the database enables the Message Agent to make routing decisions.</span></span>  
  
 <span data-ttu-id="0ea2c-148">下一步是为消息代理请求主 MessageBox 数据库，若要查找当前要发布的消息批的订阅。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-148">The next step is for the Message Agent to ask the master MessageBox database to find subscriptions for the current batch of messages being published.</span></span> <span data-ttu-id="0ea2c-149">请记住，这些消息尚未尚未写入到数据库，仅从上下文属性。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-149">Keep in mind that the messages have not yet been written to the database, only the properties from the context.</span></span> <span data-ttu-id="0ea2c-150">Bts_FindSubscriptions 存储过程在 MessageBox 查询中的订阅和谓词表，以上所示将其链接到存储的当前消息批的消息属性。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-150">The bts_FindSubscriptions stored procedure in the MessageBox queries the subscription and predicate tables identified above, linking them to the message properties stored for the current batch of messages.</span></span>  
  
 <span data-ttu-id="0ea2c-151">使用此信息，消息代理将消息插入一次通过调用 bts_InsertMessage 存储过程具有订阅的每个 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-151">With this information, the Message Agent inserts the message once into each MessageBox database that has a subscription by calling the bts_InsertMessage stored procedure.</span></span> <span data-ttu-id="0ea2c-152">使用订阅 id。 首先调用 bts_InsertMessage 存储过程</span><span class="sxs-lookup"><span data-stu-id="0ea2c-152">The bts_InsertMessage stored procedure is first called with a subscription ID.</span></span> <span data-ttu-id="0ea2c-153">在此第一个阶段中，存储的过程调用 int_EvaluateSubscriptions 存储过程负责查找订阅详细信息，验证消息通过检查符合的应用程序的安全要求消息谓词与应用程序属性匹配的主机，并在应用程序特定队列或根据状态应用程序特定的挂起的队列中插入到消息的引用。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-153">On this first pass, the stored procedure calls the int_EvaluateSubscriptions stored procedure which is responsible for looking up the subscription detail information, verifying that the message meets security requirements for the application by checking that message predicates match application properties for the host, and inserting a reference to the message in the application specific queue or application specific suspended queue depending on the state.</span></span> <span data-ttu-id="0ea2c-154">消息 ID、 订阅 ID、 服务 ID 和其他订阅信息插入到每个订阅已发现的此应用程序的应用程序特定队列表。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-154">The message ID, subscription ID, service ID, and other subscription information are inserted into the application specific queue table for each subscription that was found for this application.</span></span> <span data-ttu-id="0ea2c-155">插入消息后，消息属性和消息谓词表清除的批处理相关的值。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-155">After the messages are inserted, the message properties and message predicates tables are cleared of the batch related values.</span></span>  
  
 <span data-ttu-id="0ea2c-156">随后的消息中的每个部分调用 bts_InsertMessage 存储过程。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-156">The bts_InsertMessage stored procedure is called subsequently for each part in the message.</span></span> <span data-ttu-id="0ea2c-157">在首次调用中，消息上下文传递，然后插入到数部分、 正文部分名称和 id。 如消息有关的元数据以及后台处理表</span><span class="sxs-lookup"><span data-stu-id="0ea2c-157">On the first call, the message context is passed and is then inserted into the SPOOL table along with metadata about the message such as the number of parts, the body part name and ID.</span></span> <span data-ttu-id="0ea2c-158">除了消息正文部分插入到 PARTS 表使用 int_InsertPart 存储过程。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-158">In addition the message body part is inserted into the PARTS table using the int_InsertPart stored procedure.</span></span> <span data-ttu-id="0ea2c-159">然后，他们只需传递给要在 PARTS 表中保留的 int_InsertPart 存储过程的剩余消息部分的每个调用 bts_InsertMessage 存储过程。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-159">The bts_InsertMessage stored procedure is then called for each of the remaining message parts where they are simply passed to the int_InsertPart stored procedure to be persisted in the PARTS table.</span></span>  
  
 <span data-ttu-id="0ea2c-160">在路由消息后, 接收的消息，并且其各个部分的特定实例将记录插入到以下表的每个服务添加引用：</span><span class="sxs-lookup"><span data-stu-id="0ea2c-160">When messages are routed, references are added for each service that receives the specific instance of the message and its parts by inserting records into the following tables:</span></span>  
  
- <span data-ttu-id="0ea2c-161">MessageRefCountLog1</span><span class="sxs-lookup"><span data-stu-id="0ea2c-161">MessageRefCountLog1</span></span>  
  
- <span data-ttu-id="0ea2c-162">MessageRefCountLog2</span><span class="sxs-lookup"><span data-stu-id="0ea2c-162">MessageRefCountLog2</span></span>  
  
- <span data-ttu-id="0ea2c-163">PartRefCountLog1</span><span class="sxs-lookup"><span data-stu-id="0ea2c-163">PartRefCountLog1</span></span>  
  
- <span data-ttu-id="0ea2c-164">PartRefCountLog2</span><span class="sxs-lookup"><span data-stu-id="0ea2c-164">PartRefCountLog2</span></span>  
  
  <span data-ttu-id="0ea2c-165">这些引用将保护消息和部分定期运行，以防止 MessageBox 添满不再是系统中的消息的消息数据的清除作业被删除。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-165">These references keep the messages and parts from being deleted by cleanup jobs that run periodically to keep the MessageBox from getting full with message data for messages that are no longer in the system.</span></span> <span data-ttu-id="0ea2c-166">两个表用于减少争用和锁定问题。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-166">Two tables are used to reduce contention and locking issues.</span></span>  
  
  <span data-ttu-id="0ea2c-167">现在，已将消息路由到相应的队列，存储在 Spool 和 Parts 表中，且在应用程序特定队列，被引用的消息必须将请求从队列的应用程序实例。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-167">Now that the message has been routed to the right queue, stored in the Spool and Parts tables, and referenced in the application specific queues, the messages must be pulled off the queues by the application instances.</span></span> <span data-ttu-id="0ea2c-168">每个主机实例已在 BizTalk 管理数据库的 adm_ServiceClass 表中配置的时间间隔连续轮询数据库的出列线程的数目。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-168">Each host instance has a number of dequeuing threads that continuously poll the database on an interval that is configured in the adm_ServiceClass table in the BizTalk Management database.</span></span> <span data-ttu-id="0ea2c-169">此相同的表有一个列，指示要使用的出列线程的数目。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-169">This same table has a column to indicate the number of dequeuing threads to be used.</span></span> <span data-ttu-id="0ea2c-170">每个线程调用到 MessageBox 数据库，并调用 bts_DequeueMessages_\<应用程序名称\>存储过程适用于主机应用程序中运行。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-170">Each thread calls into the MessageBox database and calls the bts_DequeueMessages_\<application name\> stored procedure appropriate for the host application it is running in.</span></span> <span data-ttu-id="0ea2c-171">此存储的过程使用锁定语义来确保只有一个实例并且一个出列线程能够在给定时间中队列的消息进行操作。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-171">This stored procedure uses locking semantics to make sure that only one instance and one dequeuing thread are able to operate on a message in the queue at a given time.</span></span> <span data-ttu-id="0ea2c-172">获取该锁的主机实例获取的消息，随后负责将该消息传送到所针对的子服务。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-172">The host instance that gets the lock gets the message, and is then responsible for handing the message to the subservice for which it is intended.</span></span>  
  
  <span data-ttu-id="0ea2c-173">如果接收消息的服务终结点管理器，然后调用发送端口 （或请求/响应的响应部分接收端口），并且它是 XLANG/s 子服务，业务流程是创建，或定位到服务的订阅具体取决于订阅中没有实例 ID。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-173">If the service receiving the message is the Endpoint Manager, then the send port is invoked (or the response portion of a request/response receive port) and if it is the XLANG/s subservice, an orchestration is either created, or located to service the subscription depending on whether there is an instance ID in the subscription.</span></span> <span data-ttu-id="0ea2c-174">服务然后释放对消息和其部分的引用，因此，如果没有其他服务引用的可以删除消息数据。</span><span class="sxs-lookup"><span data-stu-id="0ea2c-174">The service then releases the reference to the message and its part so that if no other services have references, the message data can be deleted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ea2c-175">请参阅</span><span class="sxs-lookup"><span data-stu-id="0ea2c-175">See Also</span></span>  
 [<span data-ttu-id="0ea2c-176">消息引擎 </span><span class="sxs-lookup"><span data-stu-id="0ea2c-176">The Messaging Engine </span></span>](../core/the-messaging-engine.md)