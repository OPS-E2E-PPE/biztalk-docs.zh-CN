---
title: 在 BizTalk Server 中的僵停 |Microsoft Docs
description: BizTalk Server 中的僵停消息的常见原因
ms.custom: ''
ms.date: 03/23/2016
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0c684891-e984-442f-b5fd-de5f7cf32b44
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6a243e772fe5bc8408288167d3e8882a74e9a57
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976582"
---
# <a name="zombies-in-biztalk-server"></a><span data-ttu-id="9f2f1-103">BizTalk Server 中的僵停</span><span class="sxs-lookup"><span data-stu-id="9f2f1-103">Zombies in BizTalk Server</span></span>

## <a name="what-is-a-zombie"></a><span data-ttu-id="9f2f1-104">什么是僵停？</span><span class="sxs-lookup"><span data-stu-id="9f2f1-104">What is a zombie?</span></span>  
  
-   <span data-ttu-id="9f2f1-105">僵停消息是指这样的消息：从 messagebox 路由到一个正在运行的业务流程，但在该业务流程结束时仍处于“正在处理”状态。</span><span class="sxs-lookup"><span data-stu-id="9f2f1-105">A zombie message is a message that was routed to a running orchestration from the messagebox and was "in flight" when the orchestration ended.</span></span> <span data-ttu-id="9f2f1-106">“正在处理”的消息是已经路由到服务实例的消息，因此它位于以该服务实例为目标的 messagebox 队列中。</span><span class="sxs-lookup"><span data-stu-id="9f2f1-106">An "in flight" message is a message that has been routed to a service instance and so is in a messagebox queue destined for the service instance.</span></span> <span data-ttu-id="9f2f1-107">由于该消息不能再被订阅业务流程实例所处理，因此该消息将被挂起，其 ServiceInstance/State 值标记为“已挂起（不可恢复）”。</span><span class="sxs-lookup"><span data-stu-id="9f2f1-107">Since the message can no longer be consumed by the subscribing orchestration instance, the message is suspended and marked with a ServiceInstance/State value of "Suspended (Non-resumable)".</span></span>  
  
-   <span data-ttu-id="9f2f1-108">僵停服务实例是指这样一种业务流程实例：消息已从 messagebox 路由到该业务流程实例，而该业务流程实例完成时消息处于“正在处理”状态。</span><span class="sxs-lookup"><span data-stu-id="9f2f1-108">A zombie service instance is an instance of an orchestration which has completed while a message that was routed to the orchestration instance from the messagebox was still "in flight".</span></span> <span data-ttu-id="9f2f1-109">由于该业务流程实例已结束，不能再处理“正在处理”中的消息，因此该业务流程将被挂起，其 ServiceInstance/State 值标记为“已挂起（不可恢复）”。</span><span class="sxs-lookup"><span data-stu-id="9f2f1-109">Since the orchestration instance has ended, it cannot consume the "in flight" messages and so is suspended and marked with a ServiceInstance/State value of "Suspended (Non-resumable)".</span></span>  
  
## <a name="typical-causes"></a><span data-ttu-id="9f2f1-110">典型的原因</span><span class="sxs-lookup"><span data-stu-id="9f2f1-110">Typical causes</span></span>
<span data-ttu-id="9f2f1-111">僵停通常发生在以下几种情况下：</span><span class="sxs-lookup"><span data-stu-id="9f2f1-111">The occurrence of zombies typically falls into one of the following categories:</span></span>  
  
1. <span data-ttu-id="9f2f1-112">**终止控制消息**– 业务流程引擎允许使用控制消息来取消特定业务流程实例中所有当前正在运行的工作。</span><span class="sxs-lookup"><span data-stu-id="9f2f1-112">**Terminate control messages** – The orchestration engine allows the use of control messages to cancel all currently running work in a specific orchestration instance.</span></span> <span data-ttu-id="9f2f1-113">由于控制消息会立即停止正在运行的业务流程，因此出现僵停实例是意料之中的。</span><span class="sxs-lookup"><span data-stu-id="9f2f1-113">Since the control message immediately halts the running orchestration, zombie instances are not unexpected.</span></span> <span data-ttu-id="9f2f1-114">一些与工作流相关的设计和其他一些设计倾向于使用此机制。</span><span class="sxs-lookup"><span data-stu-id="9f2f1-114">A number of Human Workflow related designs tend to use this mechanism as well as some other designs.</span></span>  
  
2. <span data-ttu-id="9f2f1-115">**并行侦听接收**-在此方案中的服务实例等待 n 个消息 1 和收到某些消息时它会执行一些任务，并终止。</span><span class="sxs-lookup"><span data-stu-id="9f2f1-115">**Parallel listen receives** – In this scenario the service instance waits for 1 of n messages and when it receives certain messages it does some work and terminates.</span></span> <span data-ttu-id="9f2f1-116">如果服务实例终止时并行分支上收到消息，则会产生僵停。</span><span class="sxs-lookup"><span data-stu-id="9f2f1-116">If messages are received on a parallel branch just as the service instance is terminating, zombies are created.</span></span>  
  
3. <span data-ttu-id="9f2f1-117">**使用非确定性终结点的顺序保护**– 在此方案中，主业务流程计划被设计为处理特定类型的以满足某种系统设计要求的所有消息。</span><span class="sxs-lookup"><span data-stu-id="9f2f1-117">**Sequential convoys with non-deterministic endpoints** – In this scenario, a master orchestration schedule is designed to handle all messages of a certain type in order to meet some type of system design requirement.</span></span> <span data-ttu-id="9f2f1-118">这些设计要求可能包括按序送达、资源分配器和批处理。</span><span class="sxs-lookup"><span data-stu-id="9f2f1-118">These design requirements may include ordered delivery, resource dispenser, and batching.</span></span> <span data-ttu-id="9f2f1-119">对于这种方案，通常定义一个围绕侦听的 while 循环，其中一个分支包含接收形状，而另一个分支包含延迟形状，后跟某种构造，构造中设置一些变量，用以指明该 while 循环的结束条件。</span><span class="sxs-lookup"><span data-stu-id="9f2f1-119">For this scenario, the tendency is to define a while loop surrounding a listen with one branch having a receive and the other having a delay shape followed by some construct which sets some variable to indicate that the while loop should stop.</span></span> <span data-ttu-id="9f2f1-120">此机制具有不确定性，因为可以触发延迟，但仍然能够传送消息。</span><span class="sxs-lookup"><span data-stu-id="9f2f1-120">This is non-deterministic since the delay could be triggered, but a message could still be delivered.</span></span> <span data-ttu-id="9f2f1-121">类似这样的不确定性终结点都有可能造成僵停。</span><span class="sxs-lookup"><span data-stu-id="9f2f1-121">Non-deterministic endpoints like this are prone to generating zombies.</span></span>  
  
   <span data-ttu-id="9f2f1-122">僵停服务实例挂起时，生成以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="9f2f1-122">When a zombie service instance is suspended,  the following error message is generated:</span></span>  
  
`0xC0C01B4C The instance completed without consuming all of its messages. The instance and its unconsumed messages have been suspended.`  
  
 <span data-ttu-id="9f2f1-123">可以使用[BizTalk 终止符](https://www.microsoft.com/download/details.aspx?id=2846)来帮助删除僵停。</span><span class="sxs-lookup"><span data-stu-id="9f2f1-123">You can use the [BizTalk Terminator](https://www.microsoft.com/download/details.aspx?id=2846) to help remove zombies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f2f1-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="9f2f1-124">See Also</span></span>  
 <span data-ttu-id="9f2f1-125">**删除挂起的服务实例** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="9f2f1-125">**Removing Suspended Service Instances** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>