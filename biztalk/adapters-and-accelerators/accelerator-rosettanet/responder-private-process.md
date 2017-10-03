---
title: "响应方私有过程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- line-of-business applications (LOBs)
- messages, private processes
- LOBs
- messages, message flow
- private processes, responder
- private processes, message flow
ms.assetid: 69b58320-977c-44d2-a7d6-f986213aecf2
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8ba5ca38eb64859182242c944d260c9db15c880
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="responder-private-process"></a><span data-ttu-id="f996d-102">响应方私有过程</span><span class="sxs-lookup"><span data-stu-id="f996d-102">Responder Private Process</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="f996d-103">[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]使用响应方专用流程 (PrivateResponder.odx) 来处理在响应方计算机的服务内容。</span><span class="sxs-lookup"><span data-stu-id="f996d-103"> [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] uses the responder private process (PrivateResponder.odx) to process service content at a responder computer.</span></span> <span data-ttu-id="f996d-104">其中包括：</span><span class="sxs-lookup"><span data-stu-id="f996d-104">This includes the following:</span></span>  
  
-   <span data-ttu-id="f996d-105">传入消息路由到的业务线 (LOB) 应用程序</span><span class="sxs-lookup"><span data-stu-id="f996d-105">Routing an incoming message to the line-of-business (LOB) application</span></span>  
  
-   <span data-ttu-id="f996d-106">创建响应消息的服务内容和将消息路由到公共过程中，在到响应方计算机的路由</span><span class="sxs-lookup"><span data-stu-id="f996d-106">Creating the service content of a response message and routing the message to the public process, in route to the responder computer</span></span>  
  
 <span data-ttu-id="f996d-107">专用流程还设置元数据，并添加到响应消息的任何附件。</span><span class="sxs-lookup"><span data-stu-id="f996d-107">The private process also sets metadata and adds any attachments to the response message.</span></span> <span data-ttu-id="f996d-108">专用的过程将传出的消息路由到响应方公共进程，后者将 RosettaNet 实现框架 (RNIF) 标头添加并准备要传输的消息。</span><span class="sxs-lookup"><span data-stu-id="f996d-108">The private process routes outgoing messages to the responder public process, which adds RosettaNet Implementation Framework (RNIF) headers and prepares the message for transmission.</span></span> <span data-ttu-id="f996d-109">专用流程将传入消息路由到 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] 数据库的 MessagesToLOB 表中，再路由到 LOB 应用程序。</span><span class="sxs-lookup"><span data-stu-id="f996d-109">The private process routes incoming messages to the MessagesToLOB table in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] database, in route to the LOB application.</span></span>  
  
 <span data-ttu-id="f996d-110">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK 包括两个响应方专用流程示例，可以对其进行自定义以实现特定业务流程。</span><span class="sxs-lookup"><span data-stu-id="f996d-110">The [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK includes two responder private process samples that you can customize for your specific business processes.</span></span> <span data-ttu-id="f996d-111">第一个示例是 PrivateResponder 流程示例，它包含 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 安装的响应方专用流程的代码。</span><span class="sxs-lookup"><span data-stu-id="f996d-111">The first is the PrivateResponder process sample that contains the code for the responder private process installed by [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)].</span></span> <span data-ttu-id="f996d-112">有关详细信息，请参阅[PrivateResponder 示例](../../adapters-and-accelerators/accelerator-rosettanet/privateresponder-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="f996d-112">For more information, see [PrivateResponder Sample](../../adapters-and-accelerators/accelerator-rosettanet/privateresponder-sample.md).</span></span>  
  
 <span data-ttu-id="f996d-113">第二个示例是自动执行使用 3A2 和 3A4 合作伙伴接口过程 (Pip) 购买查询/采购订单流程的 PIP3A4PrivateResponder 专用流程示例。</span><span class="sxs-lookup"><span data-stu-id="f996d-113">The second sample is the PIP3A4PrivateResponder private process sample that automates the purchase query/purchase order processes that use 3A2 and 3A4 Partner Interface Processes (PIPs).</span></span> <span data-ttu-id="f996d-114">它还可以处理任何其他 PIP 消息。</span><span class="sxs-lookup"><span data-stu-id="f996d-114">It also handles any other PIP messages.</span></span> <span data-ttu-id="f996d-115">有关详细信息，请参阅[3A4 私有响应方业务流程使用业务规则](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)。</span><span class="sxs-lookup"><span data-stu-id="f996d-115">For more information, see [3A4 Private Responder Orchestration Using a Business Rule](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md).</span></span>  
  
## <a name="message-flow"></a><span data-ttu-id="f996d-116">消息流</span><span class="sxs-lookup"><span data-stu-id="f996d-116">Message Flow</span></span>  
 <span data-ttu-id="f996d-117">响应方专用流程通过邮件流未，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f996d-117">The message flow through the responder private process is as follows:</span></span>  
  
1.  <span data-ttu-id="f996d-118">响应方私有进程接收从响应方公共进程从发起程序计算机的路由中的原始的传入消息。</span><span class="sxs-lookup"><span data-stu-id="f996d-118">The responder private process receives the original incoming message from the responder public process, in route from the initiator computer.</span></span>  
  
2.  <span data-ttu-id="f996d-119">专用流程构造 LOB 应用程序消息。</span><span class="sxs-lookup"><span data-stu-id="f996d-119">The private process constructs the LOB application message.</span></span> <span data-ttu-id="f996d-120">这涉及获得 LOB 消息模板，序列化 XML 服务内容，以及将 XML 消息部分加载到 LOB 消息。</span><span class="sxs-lookup"><span data-stu-id="f996d-120">This involves getting the LOB message template, serializing the XML service content, and loading the XML message parts into the LOB message.</span></span>  
  
3.  <span data-ttu-id="f996d-121">专用的过程将消息路由到 MessagesFromLOB 表[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]数据[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]数据库，在后端 LOB 应用程序的路由。</span><span class="sxs-lookup"><span data-stu-id="f996d-121">The private process routes the message to the MessagesFromLOB table in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] database, in route to the back-end LOB application.</span></span>  
  
4.  <span data-ttu-id="f996d-122">如果原始消息具有附件，专用流程将调用 AttachmentHelper 组件处理附件。</span><span class="sxs-lookup"><span data-stu-id="f996d-122">If the original message has an attachment, the private process calls the AttachmentHelper component to process the attachment.</span></span>  
  
5.  <span data-ttu-id="f996d-123">专用的过程会向 LOB 应用程序发送通知，它 MessagesToLOB 表中保存响应消息。</span><span class="sxs-lookup"><span data-stu-id="f996d-123">The private process sends a notification to the LOB application that it saved the response message in the MessagesToLOB table.</span></span>  
  
6.  <span data-ttu-id="f996d-124">如果消息是单操作消息，专用的过程已完成。</span><span class="sxs-lookup"><span data-stu-id="f996d-124">If the message is a single-action message, the private process is complete.</span></span>  
  
7.  <span data-ttu-id="f996d-125">如果消息已双操作消息，专用流程侦听来自 LOB 应用程序的响应。</span><span class="sxs-lookup"><span data-stu-id="f996d-125">If the message is a double-action message, the private process listens for a response from the LOB application.</span></span>  
  
8.  <span data-ttu-id="f996d-126">当专用流程从 LOB 应用程序收到响应时，它将构造响应消息，并将消息发送到公共的进程。</span><span class="sxs-lookup"><span data-stu-id="f996d-126">When the private process receives the response from the LOB application, it constructs a response message, and sends the message to the public process.</span></span>  
  
9. <span data-ttu-id="f996d-127">专用的进程将等待来自公用流程的信号。</span><span class="sxs-lookup"><span data-stu-id="f996d-127">The private process waits for the signal from the public process.</span></span> <span data-ttu-id="f996d-128">如果它收到信号，它将构造 LOB 信号消息并将其发送到 LOB 应用程序。</span><span class="sxs-lookup"><span data-stu-id="f996d-128">If it receives the signal, it constructs the LOB signal message and sends it to the LOB application.</span></span> <span data-ttu-id="f996d-129">如果 RNIF 版本 1.1，专用的进程将侦听的第二个确认信号，并在接收它，、 将构造 LOB 信号消息和将其发送到 LOB 应用程序。</span><span class="sxs-lookup"><span data-stu-id="f996d-129">If the RNIF version is 1.1, the private process will listen for a second acknowledgement signal, and upon receiving it, will construct the LOB signal message and send it to the LOB application.</span></span> <span data-ttu-id="f996d-130">专用流程通知后发送每个信号消息的 LOB 应用程序。</span><span class="sxs-lookup"><span data-stu-id="f996d-130">The private process notifies the LOB application after sending each signal message.</span></span>  
  
10. <span data-ttu-id="f996d-131">如果专用流程收到通知失败 （起） 消息从发起方，路由中的公共过程专用流程构造"[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]异常"消息，并将其发送到 LOB 应用程序。</span><span class="sxs-lookup"><span data-stu-id="f996d-131">If the private process receives a Notification of Failure (NoF) message from the public process, in route from the initiator, the private process constructs a "[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]Exception" message, and sends it to the LOB application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f996d-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f996d-132">See Also</span></span>  
 <span data-ttu-id="f996d-133">[私有进程](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md) </span><span class="sxs-lookup"><span data-stu-id="f996d-133">[Private Processes](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md) </span></span>  
 <span data-ttu-id="f996d-134">[发起方私有过程](../../adapters-and-accelerators/accelerator-rosettanet/initiator-private-process.md) </span><span class="sxs-lookup"><span data-stu-id="f996d-134">[Initiator Private Process](../../adapters-and-accelerators/accelerator-rosettanet/initiator-private-process.md) </span></span>  
 <span data-ttu-id="f996d-135">[业务流程示例](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md) </span><span class="sxs-lookup"><span data-stu-id="f996d-135">[Orchestration Samples](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md) </span></span>  
 [<span data-ttu-id="f996d-136">PrivateResponder 示例</span><span class="sxs-lookup"><span data-stu-id="f996d-136">PrivateResponder Sample</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/privateresponder-sample.md)