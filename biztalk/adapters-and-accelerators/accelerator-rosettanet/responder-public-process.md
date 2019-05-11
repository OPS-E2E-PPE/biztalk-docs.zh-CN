---
title: 响应方公用流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, message flow
- messages, public processes
- public processes, message flow
- public processes, responder
ms.assetid: 78d83954-2998-44ac-a527-5e5858c61009
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a98cfde175b9377be11bf4b18570eb93bd16437
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282427"
---
# <a name="responder-public-process"></a><span data-ttu-id="45f84-102">响应方公用流程</span><span class="sxs-lookup"><span data-stu-id="45f84-102">Responder Public Process</span></span>
<span data-ttu-id="45f84-103">响应方在此公用流程接收 RosettaNet 实现框架 (RNIF) 消息从发起方，并做出相应响应。</span><span class="sxs-lookup"><span data-stu-id="45f84-103">This public process on the responder receives the RosettaNet Implementation Framework (RNIF) message from the initiator, and responds accordingly.</span></span>  
  
## <a name="message-flow-in-the-responder-public-process"></a><span data-ttu-id="45f84-104">响应方公用流程中的消息流</span><span class="sxs-lookup"><span data-stu-id="45f84-104">Message Flow in the Responder Public Process</span></span>  
 <span data-ttu-id="45f84-105">通过响应方公用流程的消息流如下所示：</span><span class="sxs-lookup"><span data-stu-id="45f84-105">The message flow through the responder public process is as follows:</span></span>  
  
1. <span data-ttu-id="45f84-106">响应方公用流程从响应方 MessageBox 数据库接收 RNIF 消息。</span><span class="sxs-lookup"><span data-stu-id="45f84-106">The responder public process receives the RNIF message from the responder MessageBox database.</span></span>  
  
2. <span data-ttu-id="45f84-107">公用流程从操作消息提取的服务内容和标头，并将其发送到专用流程。</span><span class="sxs-lookup"><span data-stu-id="45f84-107">The public process extracts the service content and headers from the action message, and sends them to the private process.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="45f84-108">响应方公用流程执行标准验证传入消息 （和任何其他验证包含在验证适配器，如果适用）。</span><span class="sxs-lookup"><span data-stu-id="45f84-108">The responder public process performs standard validation on the incoming message (and any additional validation included in a validation adapter, if applicable).</span></span> <span data-ttu-id="45f84-109">如果验证成功，则公用流程将启动应用程序适配器来执行特定的实现根据通知。</span><span class="sxs-lookup"><span data-stu-id="45f84-109">If validation is successful, then the public process will initiate the application adapter to perform notification in accordance with the specific implementation.</span></span> <span data-ttu-id="45f84-110">响应方公用流程会将消息保存在 MessageBox 数据库中，并将通知响应方专用流程，它具有该消息保存在 MessageBox 中 (使用`BeginNotify`中的方法`ApplicationAdapter`类)。</span><span class="sxs-lookup"><span data-stu-id="45f84-110">The responder public process will save the message in the MessageBox database, and will notify the responder private process that it has saved the message in the MessageBox (using the `BeginNotify` method in the `ApplicationAdapter` class).</span></span> <span data-ttu-id="45f84-111">有关验证适配器和应用程序适配器的详细信息，请参阅[ValidationAdapter &#91;RN3&#93; ](../../adapters-and-accelerators/accelerator-rosettanet/validationadapter.md)并[ApplicationAdapter &#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/applicationadapter.md)。</span><span class="sxs-lookup"><span data-stu-id="45f84-111">For more information about the validation adapter and application adapter, see [ValidationAdapter &#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/validationadapter.md) and [ApplicationAdapter &#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/applicationadapter.md).</span></span>  
  
3. <span data-ttu-id="45f84-112">如果活动是异步的单个操作，则公用流程构造 RNIF 信号消息 （确认接受），方法是包装服务内容消息部分使用前导头、 服务头和 （适用于 RNIF 2.01) 传递头。</span><span class="sxs-lookup"><span data-stu-id="45f84-112">If the activity is asynchronous and single-action, the public process constructs an RNIF signal message (Acknowledgment Acceptance) by wrapping the service-content message part with the preamble, the service header, and (for RNIF 2.01 only) the delivery header.</span></span> <span data-ttu-id="45f84-113">公用流程将构造前导头、 服务头和传递头使用参与方之间的贸易合作伙伴协议中存储的信息： 进程配置设置，有关源的配置信息和目标参与方和合作伙伴接口流程 (PIP) 变量。</span><span class="sxs-lookup"><span data-stu-id="45f84-113">The public process constructs the preamble, the service header, and the delivery header using information stored in the trading partner agreement between the parties: the process configuration settings, configuration information about the source and destination parties, and the Partner Interface Process (PIP) variables.</span></span> <span data-ttu-id="45f84-114">然后，过程将信号消息发送到发起方。</span><span class="sxs-lookup"><span data-stu-id="45f84-114">The process then sends the signal message to the initiator.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="45f84-115">如果消息是单操作消息，消息流已完成。</span><span class="sxs-lookup"><span data-stu-id="45f84-115">If the message is a single-action message, the message flow is complete.</span></span>  
  
4. <span data-ttu-id="45f84-116">公用流程进入等待状态 （等待操作的响应方专用流程）。</span><span class="sxs-lookup"><span data-stu-id="45f84-116">The public process enters a wait state (waiting for action by the responder private process).</span></span>  
  
5. <span data-ttu-id="45f84-117">以下操作可以结束等待状态 （等待操作的响应方专用流程）：</span><span class="sxs-lookup"><span data-stu-id="45f84-117">The following actions can end the wait state (waiting for action by the responder private process):</span></span>  
  
   1. <span data-ttu-id="45f84-118">响应方专用流程与原始操作消息 （在双操作消息） 的响应中返回的响应服务内容消息和标头。</span><span class="sxs-lookup"><span data-stu-id="45f84-118">The responder private process returns a response service-content message and headers, in response to the original action message (that was a double-action message).</span></span>  
  
       <span data-ttu-id="45f84-119">如果公用流程从专用流程接收响应服务内容，则公用流程将构造包含服务内容的 RNIF 消息。</span><span class="sxs-lookup"><span data-stu-id="45f84-119">If the public process receives response service content from the private process, the public process constructs an RNIF message that contains the service content.</span></span> <span data-ttu-id="45f84-120">它会通过将服务内容消息部分包含有关源和目标参与方和参与方之间协议中存储的 PIP 变量的配置信息的标头。</span><span class="sxs-lookup"><span data-stu-id="45f84-120">It does so by wrapping the service-content message part with headers that contain the configuration information about the source and destination parties, and the PIP variables stored in the agreement between the parties.</span></span>  
  
       <span data-ttu-id="45f84-121">公用流程将 RNIF 消息发送到发起方使用的操作/信号角色链接端口。</span><span class="sxs-lookup"><span data-stu-id="45f84-121">The public process sends the RNIF message to the initiator using the Action/Signal Role link port.</span></span>  
  
       <span data-ttu-id="45f84-122">如果公用流程接收通知，Microsoft[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]未成功发送消息，则公用流程将该状态发送回专用流程，然后结束。</span><span class="sxs-lookup"><span data-stu-id="45f84-122">If the public process receives notification that Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] did not successfully send the message, the public process sends that status back to the private process, and then ends.</span></span>  
  
       <span data-ttu-id="45f84-123">如果公用流程接收通知的[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]成功发送消息，流程进入等待状态 （等待操作由发起方）。</span><span class="sxs-lookup"><span data-stu-id="45f84-123">If the public process receives notification that [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] successfully sent the message, the process enters a wait state (waiting for action by the initiator).</span></span> <span data-ttu-id="45f84-124">该等待状态是类似于发起方时它正在等待由响应方操作进入等待状态。</span><span class="sxs-lookup"><span data-stu-id="45f84-124">This wait state is similar to the wait state that the initiator enters when it is waiting for action by the responder.</span></span>  
  
   2. <span data-ttu-id="45f84-125">公用流程从发起方接收失败通知消息 (NoF)。</span><span class="sxs-lookup"><span data-stu-id="45f84-125">The public process receives a Notification of Failure message (NoF) from the initiator.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="45f84-126">它已成功处理传入消息后，响应方专用流程将通知响应方公用流程。</span><span class="sxs-lookup"><span data-stu-id="45f84-126">The responder private process will notify the responder public process after it has successfully processed the incoming message.</span></span> <span data-ttu-id="45f84-127">仅后响应方公用流程已收到此通知 (从`EndNotify`中的方法`ApplicationAdapter`类) 将成功完成响应方公用流程。</span><span class="sxs-lookup"><span data-stu-id="45f84-127">Only after the responder public process has received this notification (from the `EndNotify` method in the `ApplicationAdapter` class) will the responder public process be successfully completed.</span></span>  
  
6. <span data-ttu-id="45f84-128">响应方公用流程进入等待状态 （等待发起方到响应方公用流程发送响应消息的响应中收到的信号）。</span><span class="sxs-lookup"><span data-stu-id="45f84-128">The responder public process enters a wait state (waiting to receive a signal from the initiator in response to the response message that the responder public process sent).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45f84-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="45f84-129">See Also</span></span>  
 <span data-ttu-id="45f84-130">[公用流程](../../adapters-and-accelerators/accelerator-rosettanet/public-processes.md) </span><span class="sxs-lookup"><span data-stu-id="45f84-130">[Public Processes](../../adapters-and-accelerators/accelerator-rosettanet/public-processes.md) </span></span>  
 <span data-ttu-id="45f84-131">[发起方公用流程](../../adapters-and-accelerators/accelerator-rosettanet/initiator-public-process.md) </span><span class="sxs-lookup"><span data-stu-id="45f84-131">[Initiator Public Process](../../adapters-and-accelerators/accelerator-rosettanet/initiator-public-process.md) </span></span>  
 <span data-ttu-id="45f84-132">[ApplicationAdapter](../../adapters-and-accelerators/accelerator-rosettanet/applicationadapter.md) </span><span class="sxs-lookup"><span data-stu-id="45f84-132">[ApplicationAdapter](../../adapters-and-accelerators/accelerator-rosettanet/applicationadapter.md) </span></span>  
 [<span data-ttu-id="45f84-133">ValidationAdapter</span><span class="sxs-lookup"><span data-stu-id="45f84-133">ValidationAdapter</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/validationadapter.md)