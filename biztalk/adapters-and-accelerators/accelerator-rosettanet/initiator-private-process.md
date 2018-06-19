---
title: 发起方私有过程 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- line-of-business applications (LOBs)
- messages, private processes
- erros
- LOBs
- messages, message flow
- private processes, initiator
- private processes, message flow
- private processes, errors
ms.assetid: 8444a5c8-445a-4bbd-a793-a16816fcb397
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 569d176a15ba5236d5f44d87406d9bbc0a19fca9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22211021"
---
# <a name="initiator-private-process"></a><span data-ttu-id="55f34-102">发起方私有过程</span><span class="sxs-lookup"><span data-stu-id="55f34-102">Initiator Private Process</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="55f34-103">[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]发起方私有流程 (PrivateInitiator.odx) 用于处理服务发起程序计算机上的内容。</span><span class="sxs-lookup"><span data-stu-id="55f34-103"> [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] uses the initiator private process (PrivateInitiator.odx) to process service content at an initiator computer.</span></span> <span data-ttu-id="55f34-104">其中包括：</span><span class="sxs-lookup"><span data-stu-id="55f34-104">This includes the following:</span></span>  
  
-   <span data-ttu-id="55f34-105">创建原始消息的服务内容和将消息路由到贸易合作伙伴的路由中的公共过程</span><span class="sxs-lookup"><span data-stu-id="55f34-105">Creating the service content of an original message and routing the message to the public process, in route to the trading partner</span></span>  
  
-   <span data-ttu-id="55f34-106">处理返回的信号消息并将其路由到的业务线 (LOB) 应用程序</span><span class="sxs-lookup"><span data-stu-id="55f34-106">Processing a return signal message and routing it to the line-of-business (LOB) application</span></span>  
  
-   <span data-ttu-id="55f34-107">对于双操作 PIP，处理响应返回消息并将其路由到 LOB 应用程序。</span><span class="sxs-lookup"><span data-stu-id="55f34-107">In the case of a double-action PIP, processing a response return message and routing it to the LOB application.</span></span>  
  
 <span data-ttu-id="55f34-108">专用流程还设置元数据，并添加任何附件。</span><span class="sxs-lookup"><span data-stu-id="55f34-108">The private process also sets metadata and adds any attachments.</span></span> <span data-ttu-id="55f34-109">专用的过程将传出的消息路由到公共的进程，后者将 RosettaNet 实现框架 (RNIF) 标头添加并准备要传输的消息。</span><span class="sxs-lookup"><span data-stu-id="55f34-109">The private process routes outgoing messages to the public process, which adds RosettaNet Implementation Framework (RNIF) headers and prepares the message for transmission.</span></span> <span data-ttu-id="55f34-110">专用流程将传入消息路由到 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] 数据库的 MessagesToLOB 表中，再路由到 LOB 应用程序。</span><span class="sxs-lookup"><span data-stu-id="55f34-110">The private process routes incoming messages to the MessagesToLOB table in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] database, in route to the LOB application.</span></span>  
  
 <span data-ttu-id="55f34-111">此专用的过程会自动进行使用 3A2 和 3A4 合作伙伴接口过程 (Pip) 的购买查询/采购订单进程。</span><span class="sxs-lookup"><span data-stu-id="55f34-111">This private process automates the purchase query/purchase order processes that use 3A2 and 3A4 Partner Interface Processes (PIPs).</span></span> <span data-ttu-id="55f34-112">它还可以处理任何其他 PIP 消息。</span><span class="sxs-lookup"><span data-stu-id="55f34-112">It also handles any other PIP messages.</span></span> <span data-ttu-id="55f34-113">你可以为特定的业务流程自定义专用的流程。</span><span class="sxs-lookup"><span data-stu-id="55f34-113">You can customize the private process for your specific business processes.</span></span>  
  
## <a name="message-flow"></a><span data-ttu-id="55f34-114">消息流</span><span class="sxs-lookup"><span data-stu-id="55f34-114">Message Flow</span></span>  
 <span data-ttu-id="55f34-115">消息流通过发起方私有流程如下所示：</span><span class="sxs-lookup"><span data-stu-id="55f34-115">The message flow through the initiator private process is as follows:</span></span>  
  
1.  <span data-ttu-id="55f34-116">发起方专用流程接收 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] 数据库的 MessagesFromLOB 表中的原始消息。</span><span class="sxs-lookup"><span data-stu-id="55f34-116">The initiator private process receives the original message from the MessagesFromLOB table in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] database.</span></span> <span data-ttu-id="55f34-117">后端 LOB 应用程序将消息路由到此表中。</span><span class="sxs-lookup"><span data-stu-id="55f34-117">The back-end LOB application routes the message to this table.</span></span>  
  
2.  <span data-ttu-id="55f34-118">专用流程准备一条启动消息的服务内容，并将其发送到公用的流程。</span><span class="sxs-lookup"><span data-stu-id="55f34-118">The private process prepares the service content of an initiated message, and sends it to the public process.</span></span>  
  
3.  <span data-ttu-id="55f34-119">在发起方私有进程然后进入等待状态，侦听返回信号。</span><span class="sxs-lookup"><span data-stu-id="55f34-119">The initiator private process then enters a wait state, listening for a return signal.</span></span>  
  
4.  <span data-ttu-id="55f34-120">接收到公用流程的返回信号以后，专用流程便构造一条信号消息，然后先将该信号消息发送到 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] 数据库的 MessagesToLOB 表中，再将其路由到 LOB 应用程序。</span><span class="sxs-lookup"><span data-stu-id="55f34-120">Upon receiving a return signal from the public process, the private process constructs a signal message, and sends the signal to the MessagesToLOB table in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] database, in route to the LOB application.</span></span>  
  
5.  <span data-ttu-id="55f34-121">专用的过程将发送到 LOB 应用程序的通知，它将信号消息放入 MessagesToLOB 表。</span><span class="sxs-lookup"><span data-stu-id="55f34-121">The private process sends a notification to the LOB application that it put the signal message in the MessagesToLOB table.</span></span>  
  
6.  <span data-ttu-id="55f34-122">如果 RNIF 版本 1.1，专用的进程在等待接受确认信号消息。</span><span class="sxs-lookup"><span data-stu-id="55f34-122">If the RNIF version is 1.1, the private process waits for an acceptance acknowledgement signal message.</span></span> <span data-ttu-id="55f34-123">如果它收到信号，它将构造信号消息，并将信号发送到 MessagesToLOB 表中，在 LOB 应用程序的路由。</span><span class="sxs-lookup"><span data-stu-id="55f34-123">If it receives the signal, it constructs the signal message, and sends the signal to the MessagesToLOB table, in route to the LOB application.</span></span>  
  
7.  <span data-ttu-id="55f34-124">如果原始消息是单操作消息，专用的过程已完成的它具有 LOB 应用程序返回信号消息之后。</span><span class="sxs-lookup"><span data-stu-id="55f34-124">If the original message(s) was a single-action message, the private process is complete after it has returned the signal message to the LOB application.</span></span> <span data-ttu-id="55f34-125">如果原始消息已双操作消息，专用流程侦听的响应消息。</span><span class="sxs-lookup"><span data-stu-id="55f34-125">If the original message was a double-action message, the private process listens for a response message.</span></span>  
  
8.  <span data-ttu-id="55f34-126">如果专用流程从公共过程接收响应消息，它会构造的 LOB 应用程序格式的响应消息。</span><span class="sxs-lookup"><span data-stu-id="55f34-126">If the private process receives a response message from the public process, it constructs a response message in the format of the LOB application.</span></span> <span data-ttu-id="55f34-127">这涉及获得 LOB 消息模板，序列化 XML 服务内容，以及将 XML 消息部分加载到 LOB 消息。</span><span class="sxs-lookup"><span data-stu-id="55f34-127">This involves getting the LOB message template, serializing the XML service content, and loading the XML message parts into the LOB message.</span></span>  
  
9. <span data-ttu-id="55f34-128">专用的过程将消息路由到 MessagesToLOB 表[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]数据[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]数据库。</span><span class="sxs-lookup"><span data-stu-id="55f34-128">The private process routes the message to the MessagesToLOB table in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] database.</span></span>  
  
10. <span data-ttu-id="55f34-129">如果响应消息具有附件，专用流程将调用该 AttachmentHelper 工具处理附件。</span><span class="sxs-lookup"><span data-stu-id="55f34-129">If the response message has an attachment, the private process calls the AttachmentHelper tool to process the attachment.</span></span>  
  
11. <span data-ttu-id="55f34-130">它将响应消息放入 MessagesToLOB 表，并则已完成，专用流程 LOB 应用程序发送通知。</span><span class="sxs-lookup"><span data-stu-id="55f34-130">The private process sends a notification to the LOB application that it put the response message in the MessagesToLOB table, and then is complete.</span></span>  
  
## <a name="handling-of-incorrect-messages"></a><span data-ttu-id="55f34-131">不正确的消息的处理</span><span class="sxs-lookup"><span data-stu-id="55f34-131">Handling of Incorrect Messages</span></span>  
 <span data-ttu-id="55f34-132">当发起程序专用流程从 LOB 应用程序收到不正确的消息时，专用的过程会将一条异常消息发送回 LOB。</span><span class="sxs-lookup"><span data-stu-id="55f34-132">When the initiator private process receives an incorrect message from the LOB application, the private process sends an exception message back to the LOB.</span></span> <span data-ttu-id="55f34-133">但是，专用流程不在 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] BizTalk 管理控制台张贴该错误消息。</span><span class="sxs-lookup"><span data-stu-id="55f34-133">However, the private process does not post the incorrect message in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] BizTalk Administration Console.</span></span> <span data-ttu-id="55f34-134">因此，你不能在 BizTalk 管理控制台中查看不正确的消息。</span><span class="sxs-lookup"><span data-stu-id="55f34-134">Therefore, you are not able to view the incorrect message in BizTalk Administration Console.</span></span> <span data-ttu-id="55f34-135">可以使用异常消息访问错误消息，以确定哪个消息是错误的，然后从 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA 数据库的 MessagesFromLOB 表中访问此错误消息。</span><span class="sxs-lookup"><span data-stu-id="55f34-135">You can use the exception message to access the incorrect message to determine which message was incorrect, and then access the incorrect message in the MessagesFromLOB table of the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA database.</span></span> <span data-ttu-id="55f34-136">但是，此消息可能不是使用，专用处理的消息相同因为的存储的过程和用来处理该消息适配器对其进行编辑。</span><span class="sxs-lookup"><span data-stu-id="55f34-136">However, this message may not be the same as the message that the private process consumed, because the stored process and adapter used to process the message edit it.</span></span> <span data-ttu-id="55f34-137">它们可以将根元素和命名空间添加到消息。</span><span class="sxs-lookup"><span data-stu-id="55f34-137">They add a root element and namespace to the message.</span></span> <span data-ttu-id="55f34-138">存储的过程和适配器可能返回多个记录。</span><span class="sxs-lookup"><span data-stu-id="55f34-138">The stored process and adapter possibly return multiple records.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55f34-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="55f34-139">See Also</span></span>  
 <span data-ttu-id="55f34-140">[私有进程](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md) </span><span class="sxs-lookup"><span data-stu-id="55f34-140">[Private Processes](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md) </span></span>  
 <span data-ttu-id="55f34-141">[响应方私有过程](../../adapters-and-accelerators/accelerator-rosettanet/responder-private-process.md) </span><span class="sxs-lookup"><span data-stu-id="55f34-141">[Responder Private Process](../../adapters-and-accelerators/accelerator-rosettanet/responder-private-process.md) </span></span>  
 <span data-ttu-id="55f34-142">[业务流程示例](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md) </span><span class="sxs-lookup"><span data-stu-id="55f34-142">[Orchestration Samples](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md) </span></span>  
 [<span data-ttu-id="55f34-143">PrivateInitiator 示例</span><span class="sxs-lookup"><span data-stu-id="55f34-143">PrivateInitiator Sample</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/privateinitiator-sample.md)