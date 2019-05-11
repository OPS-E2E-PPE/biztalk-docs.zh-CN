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
ms.openlocfilehash: cc41a06c15738c63812ddd9320c7ebbfe9c52d7f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65320803"
---
# <a name="zombies-in-biztalk-server"></a><span data-ttu-id="7370b-103">在 BizTalk Server 中的僵停</span><span class="sxs-lookup"><span data-stu-id="7370b-103">Zombies in BizTalk Server</span></span>

## <a name="what-is-a-zombie"></a><span data-ttu-id="7370b-104">什么是僵停？</span><span class="sxs-lookup"><span data-stu-id="7370b-104">What is a zombie?</span></span>  
  
-   <span data-ttu-id="7370b-105">僵停消息是一条消息，已从 messagebox 路由到正在运行的业务流程，而只是"航班"业务流程结束的时间。</span><span class="sxs-lookup"><span data-stu-id="7370b-105">A zombie message is a message that was routed to a running orchestration from the messagebox and was "in flight" when the orchestration ended.</span></span> <span data-ttu-id="7370b-106">"正在"处理状态消息是已经路由到服务实例和这样是发往的服务实例的 messagebox 队列中的消息。</span><span class="sxs-lookup"><span data-stu-id="7370b-106">An "in flight" message is a message that has been routed to a service instance and so is in a messagebox queue destined for the service instance.</span></span> <span data-ttu-id="7370b-107">由于消息不再可供订阅业务流程实例，将消息挂起，并 ServiceInstance/State 值标记为"已挂起 （不可恢复）"。</span><span class="sxs-lookup"><span data-stu-id="7370b-107">Since the message can no longer be consumed by the subscribing orchestration instance, the message is suspended and marked with a ServiceInstance/State value of "Suspended (Non-resumable)".</span></span>  
  
-   <span data-ttu-id="7370b-108">僵停服务实例是处于"正在处理"状态消息从 messagebox 路由到业务流程的实例时已完成的业务流程的实例。</span><span class="sxs-lookup"><span data-stu-id="7370b-108">A zombie service instance is an instance of an orchestration which has completed while a message that was routed to the orchestration instance from the messagebox was still "in flight".</span></span> <span data-ttu-id="7370b-109">业务流程实例已经结束，因为它不能使用"正在"处理状态消息因此挂起和 ServiceInstance/State 值标记为"已挂起 （不可恢复）"。</span><span class="sxs-lookup"><span data-stu-id="7370b-109">Since the orchestration instance has ended, it cannot consume the "in flight" messages and so is suspended and marked with a ServiceInstance/State value of "Suspended (Non-resumable)".</span></span>  
  
## <a name="typical-causes"></a><span data-ttu-id="7370b-110">典型的原因</span><span class="sxs-lookup"><span data-stu-id="7370b-110">Typical causes</span></span>
<span data-ttu-id="7370b-111">僵停的匹配项通常属于以下类别之一：</span><span class="sxs-lookup"><span data-stu-id="7370b-111">The occurrence of zombies typically falls into one of the following categories:</span></span>  
  
1. <span data-ttu-id="7370b-112">**终止控制消息**– 业务流程引擎允许使用控制消息来取消特定业务流程实例中所有当前正在运行的工作。</span><span class="sxs-lookup"><span data-stu-id="7370b-112">**Terminate control messages** – The orchestration engine allows the use of control messages to cancel all currently running work in a specific orchestration instance.</span></span> <span data-ttu-id="7370b-113">由于控制消息会立即停止正在运行的业务流程，则僵停实例是意料之中的。</span><span class="sxs-lookup"><span data-stu-id="7370b-113">Since the control message immediately halts the running orchestration, zombie instances are not unexpected.</span></span> <span data-ttu-id="7370b-114">工作流的许多相关设计倾向于使用此机制，以及其他一些设计。</span><span class="sxs-lookup"><span data-stu-id="7370b-114">A number of Human Workflow related designs tend to use this mechanism as well as some other designs.</span></span>  
  
2. <span data-ttu-id="7370b-115">**并行侦听接收**-在此方案中的服务实例等待 n 个消息 1 和收到某些消息时它会执行一些任务，并终止。</span><span class="sxs-lookup"><span data-stu-id="7370b-115">**Parallel listen receives** – In this scenario the service instance waits for 1 of n messages and when it receives certain messages it does some work and terminates.</span></span> <span data-ttu-id="7370b-116">如果并行分支上收到消息就像正在终止服务实例，将创建僵停。</span><span class="sxs-lookup"><span data-stu-id="7370b-116">If messages are received on a parallel branch just as the service instance is terminating, zombies are created.</span></span>  
  
3. <span data-ttu-id="7370b-117">**使用非确定性终结点的顺序保护**– 在此方案中，主业务流程计划被设计为处理特定类型的以满足某种系统设计要求的所有消息。</span><span class="sxs-lookup"><span data-stu-id="7370b-117">**Sequential convoys with non-deterministic endpoints** – In this scenario, a master orchestration schedule is designed to handle all messages of a certain type in order to meet some type of system design requirement.</span></span> <span data-ttu-id="7370b-118">这些设计要求可能包括按序的送达、 资源分配器和批处理。</span><span class="sxs-lookup"><span data-stu-id="7370b-118">These design requirements may include ordered delivery, resource dispenser, and batching.</span></span> <span data-ttu-id="7370b-119">对于此方案中，往往会是定义一段与一个分支具有 receive 和其他包含延迟形状后, 跟某种构造，这会设置一些变量，用以指示 while 循环构造围绕侦听的循环应停止。</span><span class="sxs-lookup"><span data-stu-id="7370b-119">For this scenario, the tendency is to define a while loop surrounding a listen with one branch having a receive and the other having a delay shape followed by some construct which sets some variable to indicate that the while loop should stop.</span></span> <span data-ttu-id="7370b-120">这是不确定的因为可以触发延迟，但仍无法传递消息。</span><span class="sxs-lookup"><span data-stu-id="7370b-120">This is non-deterministic since the delay could be triggered, but a message could still be delivered.</span></span> <span data-ttu-id="7370b-121">此类不确定性终结点是僵。</span><span class="sxs-lookup"><span data-stu-id="7370b-121">Non-deterministic endpoints like this are prone to generating zombies.</span></span>  
  
   <span data-ttu-id="7370b-122">僵停服务实例挂起时，生成以下错误消息：</span><span class="sxs-lookup"><span data-stu-id="7370b-122">When a zombie service instance is suspended,  the following error message is generated:</span></span>  
  
`0xC0C01B4C The instance completed without consuming all of its messages. The instance and its unconsumed messages have been suspended.`  
  
 <span data-ttu-id="7370b-123">可以使用[BizTalk 终止符](https://www.microsoft.com/download/details.aspx?id=2846)来帮助删除僵停。</span><span class="sxs-lookup"><span data-stu-id="7370b-123">You can use the [BizTalk Terminator](https://www.microsoft.com/download/details.aspx?id=2846) to help remove zombies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7370b-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="7370b-124">See Also</span></span>  
 <span data-ttu-id="7370b-125">**删除挂起的服务实例** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="7370b-125">**Removing Suspended Service Instances** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>