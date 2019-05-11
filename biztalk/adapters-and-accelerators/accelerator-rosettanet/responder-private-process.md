---
title: 响应方专用流程 |Microsoft Docs
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
- LOBs
- messages, message flow
- private processes, responder
- private processes, message flow
ms.assetid: 69b58320-977c-44d2-a7d6-f986213aecf2
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 995c436baf94678ae36d31406fbdf72d83d53425
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282455"
---
# <a name="responder-private-process"></a><span data-ttu-id="81f52-102">响应方专用流程</span><span class="sxs-lookup"><span data-stu-id="81f52-102">Responder Private Process</span></span>
<span data-ttu-id="81f52-103">Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]使用响应方专用流程 (PrivateResponder.odx) 处理响应方计算机上的服务内容。</span><span class="sxs-lookup"><span data-stu-id="81f52-103">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] uses the responder private process (PrivateResponder.odx) to process service content at a responder computer.</span></span> <span data-ttu-id="81f52-104">其中包括：</span><span class="sxs-lookup"><span data-stu-id="81f52-104">This includes the following:</span></span>  
  
- <span data-ttu-id="81f52-105">传入消息路由到业务 (LOB) 应用程序</span><span class="sxs-lookup"><span data-stu-id="81f52-105">Routing an incoming message to the line-of-business (LOB) application</span></span>  
  
- <span data-ttu-id="81f52-106">创建响应消息的服务内容和将消息路由到公用流程，在响应方计算机的路由</span><span class="sxs-lookup"><span data-stu-id="81f52-106">Creating the service content of a response message and routing the message to the public process, in route to the responder computer</span></span>  
  
  <span data-ttu-id="81f52-107">专用流程还设置元数据，并将响应消息的任何附件。</span><span class="sxs-lookup"><span data-stu-id="81f52-107">The private process also sets metadata and adds any attachments to the response message.</span></span> <span data-ttu-id="81f52-108">专用流程将传出消息路由到响应方公用流程，用于添加 RosettaNet 实现框架 (RNIF) 标头并准备要传输的消息。</span><span class="sxs-lookup"><span data-stu-id="81f52-108">The private process routes outgoing messages to the responder public process, which adds RosettaNet Implementation Framework (RNIF) headers and prepares the message for transmission.</span></span> <span data-ttu-id="81f52-109">专用流程将传入消息路由到 MessagesToLOB 表中[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]数据[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]中路由到 LOB 应用程序数据库。</span><span class="sxs-lookup"><span data-stu-id="81f52-109">The private process routes incoming messages to the MessagesToLOB table in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] database, in route to the LOB application.</span></span>  
  
  <span data-ttu-id="81f52-110">[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK 包括两个响应方专用流程示例，你可以为您的特定业务流程自定义。</span><span class="sxs-lookup"><span data-stu-id="81f52-110">The [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK includes two responder private process samples that you can customize for your specific business processes.</span></span> <span data-ttu-id="81f52-111">第一种是 PrivateResponder 流程示例，其中包含安装的响应方专用流程的代码[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="81f52-111">The first is the PrivateResponder process sample that contains the code for the responder private process installed by [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)].</span></span> <span data-ttu-id="81f52-112">有关详细信息，请参阅[PrivateResponder 示例](../../adapters-and-accelerators/accelerator-rosettanet/privateresponder-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="81f52-112">For more information, see [PrivateResponder Sample](../../adapters-and-accelerators/accelerator-rosettanet/privateresponder-sample.md).</span></span>  
  
  <span data-ttu-id="81f52-113">第二个示例是自动执行使用 3A2 和 3A4 合作伙伴接口流程 (Pip) 购买查询/采购订单流程 PIP3A4PrivateResponder 专用流程示例。</span><span class="sxs-lookup"><span data-stu-id="81f52-113">The second sample is the PIP3A4PrivateResponder private process sample that automates the purchase query/purchase order processes that use 3A2 and 3A4 Partner Interface Processes (PIPs).</span></span> <span data-ttu-id="81f52-114">它还处理任何其他 PIP 消息。</span><span class="sxs-lookup"><span data-stu-id="81f52-114">It also handles any other PIP messages.</span></span> <span data-ttu-id="81f52-115">有关详细信息，请参阅[3A4 专用响应方业务流程使用业务规则](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)。</span><span class="sxs-lookup"><span data-stu-id="81f52-115">For more information, see [3A4 Private Responder Orchestration Using a Business Rule](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md).</span></span>  
  
## <a name="message-flow"></a><span data-ttu-id="81f52-116">消息流</span><span class="sxs-lookup"><span data-stu-id="81f52-116">Message Flow</span></span>  
 <span data-ttu-id="81f52-117">通过响应方专用流程的消息流如下所示：</span><span class="sxs-lookup"><span data-stu-id="81f52-117">The message flow through the responder private process is as follows:</span></span>  
  
1. <span data-ttu-id="81f52-118">响应方专用流程从响应方公用流程从发起方计算机的路由中接收的原始的传入消息。</span><span class="sxs-lookup"><span data-stu-id="81f52-118">The responder private process receives the original incoming message from the responder public process, in route from the initiator computer.</span></span>  
  
2. <span data-ttu-id="81f52-119">专用流程构造 LOB 应用程序消息。</span><span class="sxs-lookup"><span data-stu-id="81f52-119">The private process constructs the LOB application message.</span></span> <span data-ttu-id="81f52-120">这涉及到获取 LOB 消息模板，序列化 XML 服务内容，以及将 XML 消息部分加载到 LOB 消息。</span><span class="sxs-lookup"><span data-stu-id="81f52-120">This involves getting the LOB message template, serializing the XML service content, and loading the XML message parts into the LOB message.</span></span>  
  
3. <span data-ttu-id="81f52-121">专用流程将消息路由到 MessagesFromLOB 表[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]数据[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]中路由到后端 LOB 应用程序数据库。</span><span class="sxs-lookup"><span data-stu-id="81f52-121">The private process routes the message to the MessagesFromLOB table in the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] database, in route to the back-end LOB application.</span></span>  
  
4. <span data-ttu-id="81f52-122">如果原始邮件的附件，专用流程将调用 AttachmentHelper 组件来处理附件。</span><span class="sxs-lookup"><span data-stu-id="81f52-122">If the original message has an attachment, the private process calls the AttachmentHelper component to process the attachment.</span></span>  
  
5. <span data-ttu-id="81f52-123">专用流程将通知发送到 LOB 应用程序它保存在 MessagesToLOB 表中的响应消息。</span><span class="sxs-lookup"><span data-stu-id="81f52-123">The private process sends a notification to the LOB application that it saved the response message in the MessagesToLOB table.</span></span>  
  
6. <span data-ttu-id="81f52-124">如果消息是单操作消息，专用流程已完成。</span><span class="sxs-lookup"><span data-stu-id="81f52-124">If the message is a single-action message, the private process is complete.</span></span>  
  
7. <span data-ttu-id="81f52-125">如果消息是双操作消息，专用流程将侦听来自 LOB 应用程序的响应。</span><span class="sxs-lookup"><span data-stu-id="81f52-125">If the message is a double-action message, the private process listens for a response from the LOB application.</span></span>  
  
8. <span data-ttu-id="81f52-126">当专用流程从 LOB 应用程序收到响应时，它构造响应消息，并将消息发送到公用流程。</span><span class="sxs-lookup"><span data-stu-id="81f52-126">When the private process receives the response from the LOB application, it constructs a response message, and sends the message to the public process.</span></span>  
  
9. <span data-ttu-id="81f52-127">专用流程将等待来自公用流程的信号。</span><span class="sxs-lookup"><span data-stu-id="81f52-127">The private process waits for the signal from the public process.</span></span> <span data-ttu-id="81f52-128">如果它收到信号，它构造 LOB 信号消息，并将其发送到 LOB 应用程序。</span><span class="sxs-lookup"><span data-stu-id="81f52-128">If it receives the signal, it constructs the LOB signal message and sends it to the LOB application.</span></span> <span data-ttu-id="81f52-129">如果 RNIF 版本 1.1，专用流程将侦听的第二个确认信号，并在收到它时将构造 LOB 信号消息，将其发送到 LOB 应用程序。</span><span class="sxs-lookup"><span data-stu-id="81f52-129">If the RNIF version is 1.1, the private process will listen for a second acknowledgement signal, and upon receiving it, will construct the LOB signal message and send it to the LOB application.</span></span> <span data-ttu-id="81f52-130">专用流程通知后将每个信号消息发送的 LOB 应用程序。</span><span class="sxs-lookup"><span data-stu-id="81f52-130">The private process notifies the LOB application after sending each signal message.</span></span>  
  
10. <span data-ttu-id="81f52-131">如果专用流程从公用流程，在路由中来自发起方，接收失败通知 (NoF) 消息的专用流程将构造"[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]异常"消息，并将其发送到 LOB 应用程序。</span><span class="sxs-lookup"><span data-stu-id="81f52-131">If the private process receives a Notification of Failure (NoF) message from the public process, in route from the initiator, the private process constructs a "[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]Exception" message, and sends it to the LOB application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81f52-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="81f52-132">See Also</span></span>  
 <span data-ttu-id="81f52-133">[专用流程](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md) </span><span class="sxs-lookup"><span data-stu-id="81f52-133">[Private Processes](../../adapters-and-accelerators/accelerator-rosettanet/private-processes.md) </span></span>  
 <span data-ttu-id="81f52-134">[发起方专用流程](../../adapters-and-accelerators/accelerator-rosettanet/initiator-private-process.md) </span><span class="sxs-lookup"><span data-stu-id="81f52-134">[Initiator Private Process](../../adapters-and-accelerators/accelerator-rosettanet/initiator-private-process.md) </span></span>  
 <span data-ttu-id="81f52-135">[业务流程示例](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md) </span><span class="sxs-lookup"><span data-stu-id="81f52-135">[Orchestration Samples](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md) </span></span>  
 [<span data-ttu-id="81f52-136">PrivateResponder 示例</span><span class="sxs-lookup"><span data-stu-id="81f52-136">PrivateResponder Sample</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/privateresponder-sample.md)