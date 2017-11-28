---
title: "延续任务，并 ContinuationID 节点 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8aa8956721d4a44b51b8d2c7776560aaa878f864
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="continuation-and-continuationid-nodes"></a><span data-ttu-id="8b019-102">继续符和 ContinuationID 节点</span><span class="sxs-lookup"><span data-stu-id="8b019-102">Continuation and ContinuationID Nodes</span></span>
<span data-ttu-id="8b019-103">继续符为 BAM 基础结构提供有关以下信息的指导：</span><span class="sxs-lookup"><span data-stu-id="8b019-103">Continuations provide guidance to the BAM infrastructure about the following information:</span></span>  
  
-   <span data-ttu-id="8b019-104">事件应按何种顺序发生</span><span class="sxs-lookup"><span data-stu-id="8b019-104">The order in which events are expected to occur</span></span>  
  
-   <span data-ttu-id="8b019-105">对与事件项关联的唯一 ID 中的任何更改进行处理的方法</span><span class="sxs-lookup"><span data-stu-id="8b019-105">A way to handle any change in the unique ID to which event items are correlated</span></span>  
  
 <span data-ttu-id="8b019-106">换种方式来说明此点，继续符定义如何向活动传输参与者之间的这些信息。</span><span class="sxs-lookup"><span data-stu-id="8b019-106">To state this another way, continuations define the transfer of this information between contributors to an activity.</span></span> <span data-ttu-id="8b019-107">当以下情况出现时，将发生传输：</span><span class="sxs-lookup"><span data-stu-id="8b019-107">A transfer occurs in the following situations:</span></span>  
  
-   <span data-ttu-id="8b019-108">当活动正在进行时，ActivityID 发生变化。</span><span class="sxs-lookup"><span data-stu-id="8b019-108">There is a change in the ActivityID between the time an activity begins and ends.</span></span> <span data-ttu-id="8b019-109">例如，您有两个相关的消息，即采购订单号和销售订单号。</span><span class="sxs-lookup"><span data-stu-id="8b019-109">For example, you have two related messages such as a Purchase Order number and Sales Order number.</span></span> <span data-ttu-id="8b019-110">每个消息都有分配给它的唯一编号，例如，采购订单号的唯一编号为 123456，销售订单号的唯一编号为 987654。</span><span class="sxs-lookup"><span data-stu-id="8b019-110">Each has a unique number assigned to it, such as 123456 for the Purchase Order number and 987654 for Sales Order number.</span></span> <span data-ttu-id="8b019-111">您想使用继续符让采购订单和销售订单的唯一标识符相等，以便事件可以关联到公用活动，而不用管哪个唯一标识符与传入事件相关联。</span><span class="sxs-lookup"><span data-stu-id="8b019-111">You would use a continuation to equate the unique identifiers for the Purchase Order and the Sales Order so that events can be correlated to the common activity regardless of which unique identifier is associated with the incoming events.</span></span>  
  
-   <span data-ttu-id="8b019-112">从一个运行时环境转换到另一个运行时环境。</span><span class="sxs-lookup"><span data-stu-id="8b019-112">You have a transition from one run-time environment to another.</span></span> <span data-ttu-id="8b019-113">例如，在必须提供 BizTalk Server 消息管道，然后将调用一个业务流程和业务流程，然后将控件传递到的应用程序发送传送通知，采购订单的应用程序方案中你有两个环境转换： 从消息传递到管道业务流程和从消息管道业务流程。</span><span class="sxs-lookup"><span data-stu-id="8b019-113">For example, in a scenario where you have an application that supplies a purchase order to a BizTalk Server messaging pipeline, which then invokes an orchestration, and the orchestration then passes control to an application that sends a shipping notice, you have two environment transitions: from a messaging pipeline to a an orchestration and from an orchestration to a messaging pipeline.</span></span>  
  
 <span data-ttu-id="8b019-114">在选择要用于您的继续符的属性的一个重要一点是：必须从同一上下文映射这些属性。</span><span class="sxs-lookup"><span data-stu-id="8b019-114">An important point to remember when selecting a property to use for your continuation is that the properties must be mapped from the same context.</span></span>  
  
 <span data-ttu-id="8b019-115">例如，如果您具有属性 Message.InterchangeID 和 servicecontext.InterchangeID，则可能您可以使用 InterchangeID 来创建您的继续符。</span><span class="sxs-lookup"><span data-stu-id="8b019-115">For example, if you have the propertiesy Message.InterchangeID and servicecontext.InterchangeID it might appear that you could use the InterchangeID to create your continuation.</span></span> <span data-ttu-id="8b019-116">如果这些消息来自不同的上下文，则您将不能使用 InterchangeID（或其他属性）来可靠地创建继续符。</span><span class="sxs-lookup"><span data-stu-id="8b019-116">If the messages come from different contexts you cannot use the InterchangeID (or other property) to reliably create a continuation.</span></span>  
  
## <a name="working-with-continuation-nodes"></a><span data-ttu-id="8b019-117">使用继续符节点</span><span class="sxs-lookup"><span data-stu-id="8b019-117">Working with Continuation nodes</span></span>  
 <span data-ttu-id="8b019-118">延续节点包含数据的项，指示一个唯一的实例 ID，也称为*继续标记*。</span><span class="sxs-lookup"><span data-stu-id="8b019-118">The Continuation node contains data items that indicate a unique instance ID, also called a *continuation token*.</span></span> <span data-ttu-id="8b019-119">通过使用继续符，开发人员可以链接到使用 ContinuationID 节点的其他活动。</span><span class="sxs-lookup"><span data-stu-id="8b019-119">By using the continuation token, developers can link to other activities using the ContinuationID node.</span></span>  
  
 <span data-ttu-id="8b019-120">使用继续符和 ContinuationID 节点的基本情况有以下三种：</span><span class="sxs-lookup"><span data-stu-id="8b019-120">There are three basic scenarios in which Continuation and ContinuationID nodes are used:</span></span>  
  
-   <span data-ttu-id="8b019-121">业务流程到业务流程</span><span class="sxs-lookup"><span data-stu-id="8b019-121">Orchestration to orchestration</span></span>  
  
-   <span data-ttu-id="8b019-122">业务流程到 BizTalk 解决方案</span><span class="sxs-lookup"><span data-stu-id="8b019-122">Orchestration to BizTalk solution</span></span>  
  
-   <span data-ttu-id="8b019-123">BizTalk 解决方案到业务流程</span><span class="sxs-lookup"><span data-stu-id="8b019-123">BizTalk solution to orchestration</span></span>  
  
 <span data-ttu-id="8b019-124">在业务流程到业务流程的情况中，TPE 必须定义继续符节点和 ContinuationID 节点，并且这两个节点必须具有相同的名称以便 BAM 可以关联活动。</span><span class="sxs-lookup"><span data-stu-id="8b019-124">In the orchestration scenario the TPE must define a Continuation node, and a ContinuationID node, and the nodes must have the same name in order for BAM to correlate the activities.</span></span>  
  
 <span data-ttu-id="8b019-125">在业务流程到 BizTalk 解决方案的情况中，您需要使用 TPE 定义继续符节点，并且开发人员需要创建一个用 BAM API 来处理该继续符的目标部分的解决方案。</span><span class="sxs-lookup"><span data-stu-id="8b019-125">In the orchestration to BizTalk solution scenario, you use the TPE to define a Continuation node and the developer creates a solution that uses the BAM API to handle the destination portion of the continuation..</span></span>  
  
 <span data-ttu-id="8b019-126">在 BizTalk 解决方案到业务流程的情况中，开发人员需要使用 BAM API 提供继续符对的起点，然后您需要使用 TPE 定义 ContinuationID 节点。</span><span class="sxs-lookup"><span data-stu-id="8b019-126">In the BizTalk solution to orchestration, the developer uses the BAM API to supply the origination of the continuation pair and you use TPE to define a ContinuationID node.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8b019-127">双向端口可在两个方向上进行操作，这意味着要侦听传过这种端口的数据，可能需要启用继续符，具体情况取决于 BizTalk 解决方案的行为。</span><span class="sxs-lookup"><span data-stu-id="8b019-127">Two-way ports can operate in either direction, which means that interception of data that passes through the ports can, depending on the behavior of the BizTalk solution, require enabling of a continuation.</span></span> <span data-ttu-id="8b019-128">例如，如果活动在两个方向上为 BizTalk Server 消息处理端口的激活过程记录“PortEndTime”（例如，如果项名称为“MessageReceived”和“MessageSent”，这两项的顺序为此处的先后顺序），您需要在它们之间创建一个继续符。</span><span class="sxs-lookup"><span data-stu-id="8b019-128">For example, if the activity records “PortEndTime” for activation of a BizTalk Server messaging port in either direction (if the item names are, for example, “MessageReceived” and “MessageSent,” in that order), you need to create a continuation between them.</span></span> <span data-ttu-id="8b019-129">如果有多个事件流分配到 BAM 活动中，并且每个实现接触点有不同的事件流（例如，BTS 消息传入、BTS 消息传出、业务流程、自定义应用程序以及 Web Services），则必须使用继续符。</span><span class="sxs-lookup"><span data-stu-id="8b019-129">A continuation is required any time more than one event stream contributes to a BAM activity, and there are distinct event streams per implementation touch point (such as BTS Messaging in, BTS Messaging out, Orchestration, custom applications, and Web services).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b019-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8b019-130">See Also</span></span>  
 <span data-ttu-id="8b019-131">[如何创建一个延续任务](../core/how-to-create-a-continuation.md) </span><span class="sxs-lookup"><span data-stu-id="8b019-131">[How to Create a Continuation](../core/how-to-create-a-continuation.md) </span></span>  
 [<span data-ttu-id="8b019-132">键入活动视图节点</span><span class="sxs-lookup"><span data-stu-id="8b019-132">TPE Activity View Nodes</span></span>](../core/tpe-activity-view-nodes.md)