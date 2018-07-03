---
title: 确认处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- acknowledgements, processing
ms.assetid: 705bc12d-69ac-4641-a45e-4f1fab507e4a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb8bf0620c3e336317382cbeb299cf2d6d17faa2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969462"
---
# <a name="acknowledgments-processing"></a><span data-ttu-id="166c9-102">确认处理</span><span class="sxs-lookup"><span data-stu-id="166c9-102">Acknowledgments Processing</span></span>
<span data-ttu-id="166c9-103">HL7 规范支持两种格式中的消息交换：</span><span class="sxs-lookup"><span data-stu-id="166c9-103">The HL7 specification supports exchange of messages in two formats:</span></span>  
  
- <span data-ttu-id="166c9-104">未经请求的更新和其确认 (ACK)</span><span class="sxs-lookup"><span data-stu-id="166c9-104">Unsolicited update and its acknowledgment (ACK)</span></span>  
  
- <span data-ttu-id="166c9-105">查询和其响应</span><span class="sxs-lookup"><span data-stu-id="166c9-105">Query and its response</span></span>  
  
  <span data-ttu-id="166c9-106">起始应用程序的消息响应，响应的应用程序使用一条消息，包括数据或错误指示做出响应。</span><span class="sxs-lookup"><span data-stu-id="166c9-106">In response to a message from an initiating application, the responding application responds with a message that includes data or an error indication.</span></span> <span data-ttu-id="166c9-107">起始应用程序可能会收到指示响应方应用程序未正确收到消息的响应方应用程序从拒绝状态。</span><span class="sxs-lookup"><span data-stu-id="166c9-107">The initiating application may receive a reject status from the responder application indicating that the responder application did not receive the message correctly.</span></span> <span data-ttu-id="166c9-108">在这两种情况下，消息交换的过程包括两个实体，起始和响应应用程序。</span><span class="sxs-lookup"><span data-stu-id="166c9-108">In both cases, the process of message exchange involves two entities, the initiating and responding applications.</span></span> <span data-ttu-id="166c9-109">每个是发送方和接收方的消息。</span><span class="sxs-lookup"><span data-stu-id="166c9-109">Each is both a sender and receiver of messages.</span></span> <span data-ttu-id="166c9-110">起始应用程序将发送第一次，然后接收，而响应系统接收，然后将发送。</span><span class="sxs-lookup"><span data-stu-id="166c9-110">The initiating application sends first and then receives, while the responding system receives and then sends.</span></span>  
  
## <a name="unsolicited-updates"></a><span data-ttu-id="166c9-111">未经请求的更新</span><span class="sxs-lookup"><span data-stu-id="166c9-111">Unsolicited updates</span></span>  
 <span data-ttu-id="166c9-112">业务线 (LOB) 应用程序发布消息，或触发事件发生时启动的信息传输时发生未经请求的更新。</span><span class="sxs-lookup"><span data-stu-id="166c9-112">An unsolicited update occurs when a line-of-business (LOB) application publishes a message, or initiates a transfer of information when a trigger event occurs.</span></span> <span data-ttu-id="166c9-113">例如，为患者实验室结果可用时，可能有需要实验室结果发送到多个其他系统。</span><span class="sxs-lookup"><span data-stu-id="166c9-113">For example, when the laboratory results for a patient are available, there may be a need to send the laboratory results to several other systems.</span></span> <span data-ttu-id="166c9-114">这些更新是 ACK 响应的未经请求的更新。</span><span class="sxs-lookup"><span data-stu-id="166c9-114">These updates are unsolicited updates to which an ACK responds.</span></span>  
  
## <a name="queries"></a><span data-ttu-id="166c9-115">查询</span><span class="sxs-lookup"><span data-stu-id="166c9-115">Queries</span></span>  
 <span data-ttu-id="166c9-116">在查询时，需要的信息的应用程序将查询发送到另一个应用程序，并接收应用程序响应查询。</span><span class="sxs-lookup"><span data-stu-id="166c9-116">In the case of a query, an application that requires information sends a query to another application, and the receiving application responds to the query.</span></span> <span data-ttu-id="166c9-117">例如，一个药学应用程序可能会发送包含订单条目 (CPOE) 系统对患者 ID 号的请求消息和接收包含所需的数据，以允许订单处理的响应。</span><span class="sxs-lookup"><span data-stu-id="166c9-117">For example, a pharmacy application may send a request message containing the ID number of the patient to the Order Entry (CPOE) system and receive a response containing the necessary data to permit processing of the order.</span></span> <span data-ttu-id="166c9-118">此请求的事务是一个查询，并且不同的未经请求的更新中。</span><span class="sxs-lookup"><span data-stu-id="166c9-118">This requesting transaction is a query, and is different from an unsolicited update.</span></span> <span data-ttu-id="166c9-119">在响应中包含两个应用程序之间流动的信息。</span><span class="sxs-lookup"><span data-stu-id="166c9-119">The information that flows between the two applications is contained in the response.</span></span> <span data-ttu-id="166c9-120">响应本身不需要带有第四个消息的确认。</span><span class="sxs-lookup"><span data-stu-id="166c9-120">The response itself does not require an acknowledgment with a fourth message.</span></span> <span data-ttu-id="166c9-121">但是，您可以修改此使用确认进行响应的某些环境中</span><span class="sxs-lookup"><span data-stu-id="166c9-121">However, you can modify this in some environments to respond with an ACK.</span></span> <span data-ttu-id="166c9-122">Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 根据配置使用确认进行响应。</span><span class="sxs-lookup"><span data-stu-id="166c9-122">Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) responds with an ACK if so configured.</span></span> <span data-ttu-id="166c9-123">查询/响应交换的示例，请参阅[询问教程](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md)。</span><span class="sxs-lookup"><span data-stu-id="166c9-123">For an example of a query/response exchange, see [Interrogative Tutorial](../../adapters-and-accelerators/accelerator-hl7/interrogative-tutorial.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="166c9-124">本节内容</span><span class="sxs-lookup"><span data-stu-id="166c9-124">In This Section</span></span>  
  
-   [<span data-ttu-id="166c9-125">验证消息</span><span class="sxs-lookup"><span data-stu-id="166c9-125">Validating Messages</span></span>](../../adapters-and-accelerators/accelerator-hl7/validating-messages.md)  
  
-   [<span data-ttu-id="166c9-126">ACK 消息模式</span><span class="sxs-lookup"><span data-stu-id="166c9-126">ACK Message Modes</span></span>](../../adapters-and-accelerators/accelerator-hl7/ack-message-modes.md)  
  
-   [<span data-ttu-id="166c9-127">ACK 进程模型</span><span class="sxs-lookup"><span data-stu-id="166c9-127">ACK Process Model</span></span>](../../adapters-and-accelerators/accelerator-hl7/ack-process-model.md)