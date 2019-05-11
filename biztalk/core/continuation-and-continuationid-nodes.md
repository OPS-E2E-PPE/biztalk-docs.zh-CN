---
title: 继续符和 ContinuationID 节点 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- continuation tokens
- Continuation nodes [Tracking Profile Editor]
- Tracking Profile Editor, node descriptions
- BAM, correlating activities
- activities, linking
- activities, continuation tokens
- ContinuationID nodes [Tracking Profile Editor]
ms.assetid: aa050660-66f7-4084-b6bf-b9319ce625af
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e0cd305241b04bbbb7a09a8cf716820978594e7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354594"
---
# <a name="continuation-and-continuationid-nodes"></a><span data-ttu-id="bb332-102">继续符和 ContinuationID 节点</span><span class="sxs-lookup"><span data-stu-id="bb332-102">Continuation and ContinuationID Nodes</span></span>
<span data-ttu-id="bb332-103">延续任务提供指导到 BAM 基础结构有关的以下信息：</span><span class="sxs-lookup"><span data-stu-id="bb332-103">Continuations provide guidance to the BAM infrastructure about the following information:</span></span>  
  
- <span data-ttu-id="bb332-104">事件预期发生的顺序</span><span class="sxs-lookup"><span data-stu-id="bb332-104">The order in which events are expected to occur</span></span>  
  
- <span data-ttu-id="bb332-105">一种方法来处理任何更改的项对与事件相关联的唯一 ID</span><span class="sxs-lookup"><span data-stu-id="bb332-105">A way to handle any change in the unique ID to which event items are correlated</span></span>  
  
  <span data-ttu-id="bb332-106">若要表明此另一种方法，继续符定义活动的参与者之间的此信息传输。</span><span class="sxs-lookup"><span data-stu-id="bb332-106">To state this another way, continuations define the transfer of this information between contributors to an activity.</span></span> <span data-ttu-id="bb332-107">在以下情况下会发生传输：</span><span class="sxs-lookup"><span data-stu-id="bb332-107">A transfer occurs in the following situations:</span></span>  
  
- <span data-ttu-id="bb332-108">没有在活动开始的时间和结束之间的 ActivityID 的更改。</span><span class="sxs-lookup"><span data-stu-id="bb332-108">There is a change in the ActivityID between the time an activity begins and ends.</span></span> <span data-ttu-id="bb332-109">例如，你有采购订单号和销售订单号相关的两个消息。</span><span class="sxs-lookup"><span data-stu-id="bb332-109">For example, you have two related messages such as a Purchase Order number and Sales Order number.</span></span> <span data-ttu-id="bb332-110">每个都有分配给它，如 123456 采购订单号和销售订单编号为 987654 的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="bb332-110">Each has a unique number assigned to it, such as 123456 for the Purchase Order number and 987654 for Sales Order number.</span></span> <span data-ttu-id="bb332-111">将使用延续来使唯一标识符相等的采购订单和销售订单，以便事件可以关联到公用活动，而不考虑的唯一标识符是与传入事件相关联。</span><span class="sxs-lookup"><span data-stu-id="bb332-111">You would use a continuation to equate the unique identifiers for the Purchase Order and the Sales Order so that events can be correlated to the common activity regardless of which unique identifier is associated with the incoming events.</span></span>  
  
- <span data-ttu-id="bb332-112">可以从一个运行时环境转换到另一个。</span><span class="sxs-lookup"><span data-stu-id="bb332-112">You have a transition from one run-time environment to another.</span></span> <span data-ttu-id="bb332-113">例如，在必须提供给 BizTalk Server 消息传送管道，然后调用业务流程和业务流程，然后将控制权传递给发送发货通知的应用程序，采购订单的应用程序方案中有两个环境转换： 从消息传送管道转换业务流程和从业务流程传递到消息传送管道。</span><span class="sxs-lookup"><span data-stu-id="bb332-113">For example, in a scenario where you have an application that supplies a purchase order to a BizTalk Server messaging pipeline, which then invokes an orchestration, and the orchestration then passes control to an application that sends a shipping notice, you have two environment transitions: from a messaging pipeline to a an orchestration and from an orchestration to a messaging pipeline.</span></span>  
  
  <span data-ttu-id="bb332-114">选择要用于您的继续符某一属性时要记住的重要一点是，必须将属性映射的同一上下文中。</span><span class="sxs-lookup"><span data-stu-id="bb332-114">An important point to remember when selecting a property to use for your continuation is that the properties must be mapped from the same context.</span></span>  
  
  <span data-ttu-id="bb332-115">例如，如果您具有属性 Message.InterchangeID 和 servicecontext。它可能显示您可以使用 InterchangeID 来创建您的继续符的 InterchangeID。</span><span class="sxs-lookup"><span data-stu-id="bb332-115">For example, if you have the propertiesy Message.InterchangeID and servicecontext.InterchangeID it might appear that you could use the InterchangeID to create your continuation.</span></span> <span data-ttu-id="bb332-116">如果这些消息来自不同的上下文不能使用 InterchangeID （或其他属性） 来可靠地创建继续符。</span><span class="sxs-lookup"><span data-stu-id="bb332-116">If the messages come from different contexts you cannot use the InterchangeID (or other property) to reliably create a continuation.</span></span>  
  
## <a name="working-with-continuation-nodes"></a><span data-ttu-id="bb332-117">使用继续符节点</span><span class="sxs-lookup"><span data-stu-id="bb332-117">Working with Continuation nodes</span></span>  
 <span data-ttu-id="bb332-118">继续符节点包含指示唯一实例 ID，也称为的数据项*继续标记*。</span><span class="sxs-lookup"><span data-stu-id="bb332-118">The Continuation node contains data items that indicate a unique instance ID, also called a *continuation token*.</span></span> <span data-ttu-id="bb332-119">通过使用继续标记，开发人员可以链接到使用 ContinuationID 节点的其他活动。</span><span class="sxs-lookup"><span data-stu-id="bb332-119">By using the continuation token, developers can link to other activities using the ContinuationID node.</span></span>  
  
 <span data-ttu-id="bb332-120">有三种基本方案中的继续符和 ContinuationID 节点可用：</span><span class="sxs-lookup"><span data-stu-id="bb332-120">There are three basic scenarios in which Continuation and ContinuationID nodes are used:</span></span>  
  
- <span data-ttu-id="bb332-121">业务流程到业务流程</span><span class="sxs-lookup"><span data-stu-id="bb332-121">Orchestration to orchestration</span></span>  
  
- <span data-ttu-id="bb332-122">业务流程到 BizTalk 解决方案</span><span class="sxs-lookup"><span data-stu-id="bb332-122">Orchestration to BizTalk solution</span></span>  
  
- <span data-ttu-id="bb332-123">BizTalk 解决方案到业务流程</span><span class="sxs-lookup"><span data-stu-id="bb332-123">BizTalk solution to orchestration</span></span>  
  
  <span data-ttu-id="bb332-124">在业务流程中情况中，TPE 必须定义继续符节点和 ContinuationID 节点，并且节点必须具有相同的名称以便 BAM 可以关联活动。</span><span class="sxs-lookup"><span data-stu-id="bb332-124">In the orchestration scenario the TPE must define a Continuation node, and a ContinuationID node, and the nodes must have the same name in order for BAM to correlate the activities.</span></span>  
  
  <span data-ttu-id="bb332-125">在业务流程到 BizTalk 解决方案的情况，您将使用 TPE 定义继续符节点和开发人员创建的解决方案，使用 BAM API 来处理的目标部分的延续任务...</span><span class="sxs-lookup"><span data-stu-id="bb332-125">In the orchestration to BizTalk solution scenario, you use the TPE to define a Continuation node and the developer creates a solution that uses the BAM API to handle the destination portion of the continuation..</span></span>  
  
  <span data-ttu-id="bb332-126">在 BizTalk 解决方案到业务流程中，开发人员使用 BAM API 提供继续符对的起点，并使用 TPE 定义 ContinuationID 节点。</span><span class="sxs-lookup"><span data-stu-id="bb332-126">In the BizTalk solution to orchestration, the developer uses the BAM API to supply the origination of the continuation pair and you use TPE to define a ContinuationID node.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bb332-127">双向端口可以运行在任一方向，这意味着，数据会通过端口侦听可以具体取决于 BizTalk 解决方案的行为，需要启用继续符。</span><span class="sxs-lookup"><span data-stu-id="bb332-127">Two-way ports can operate in either direction, which means that interception of data that passes through the ports can, depending on the behavior of the BizTalk solution, require enabling of a continuation.</span></span> <span data-ttu-id="bb332-128">例如，如果活动记录"PortEndTime"激活的 BizTalk Server 消息传送端口，在任一方向 （如果项名称，例如，"MessageReceived"和"MessageSent"按此顺序），您需要创建它们之间的继续符。</span><span class="sxs-lookup"><span data-stu-id="bb332-128">For example, if the activity records “PortEndTime” for activation of a BizTalk Server messaging port in either direction (if the item names are, for example, “MessageReceived” and “MessageSent,” in that order), you need to create a continuation between them.</span></span> <span data-ttu-id="bb332-129">延续是必需的任何时间超过一个事件流分配到 BAM 活动中，并且有不同的事件流，每个实现接触点 （如 BTS 消息传入、 BTS 消息传出、 业务流程、 自定义应用程序和 Web 服务）。</span><span class="sxs-lookup"><span data-stu-id="bb332-129">A continuation is required any time more than one event stream contributes to a BAM activity, and there are distinct event streams per implementation touch point (such as BTS Messaging in, BTS Messaging out, Orchestration, custom applications, and Web services).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb332-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="bb332-130">See Also</span></span>  
 <span data-ttu-id="bb332-131">[如何创建一个继续符](../core/how-to-create-a-continuation.md) </span><span class="sxs-lookup"><span data-stu-id="bb332-131">[How to Create a Continuation](../core/how-to-create-a-continuation.md) </span></span>  
 [<span data-ttu-id="bb332-132">“TPE 活动视图”节点</span><span class="sxs-lookup"><span data-stu-id="bb332-132">TPE Activity View Nodes</span></span>](../core/tpe-activity-view-nodes.md)