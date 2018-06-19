---
title: 运行 Orchestrations3 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, running
- Receive shape [Orchestration Designer], starting orchestrations
- Start Orchestration shape [Orchestration Designer], starting orchestrations
- Call Orchestration shape [Orchestration Designer], starting orchestrations
- Receive shape [Orchestration Designer], activating orchestrations
ms.assetid: 5bfe61c9-80e0-4a0a-b6b1-ab48037e665e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 550fc1e03f3583215a817028917000c9a9c3074a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269045"
---
# <a name="running-orchestrations"></a><span data-ttu-id="0e570-102">运行业务流程</span><span class="sxs-lookup"><span data-stu-id="0e570-102">Running Orchestrations</span></span>
<span data-ttu-id="0e570-103">业务流程实例旨在能够触发通过在另一个业务流程进行显式调用 — 使用**调用 Orchestration**形状或**启动 Orchestration**形状 — 或收到激活消息。</span><span class="sxs-lookup"><span data-stu-id="0e570-103">Orchestration instances are designed to be triggered either by an explicit call from another orchestration—using a **Call Orchestration** shape or **Start Orchestration** shape—or by receipt of an activation message.</span></span> <span data-ttu-id="0e570-104">中指定的激活消息架构**消息**属性。</span><span class="sxs-lookup"><span data-stu-id="0e570-104">The activation message schema is specified in the **Message** property.</span></span> <span data-ttu-id="0e570-105">应相应地，设计您的业务流程和设置**激活**属性**接收**形状为 true，或者请确保调用 orchestration 存在并且正确配置为运行新的业务流程。</span><span class="sxs-lookup"><span data-stu-id="0e570-105">You should design your orchestration accordingly, and either set the **Activate** property on a **Receive** shape to true, or make sure that a calling orchestration exists and is configured properly to run the new orchestration.</span></span>  
  
 <span data-ttu-id="0e570-106">可以运行任何实例之前，你必须首先将绑定和部署 BizTalk 程序集，然后登记和启动要开始处理的业务流程引擎。</span><span class="sxs-lookup"><span data-stu-id="0e570-106">Before any instances can run, you must first bind and deploy the BizTalk assembly, and then enlist and start the orchestration engine to begin processing.</span></span> <span data-ttu-id="0e570-107">有关详细信息，请参阅[部署 BizTalk 中的程序集到 BizTalk 应用程序的 Visual Studio](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)和[部署和管理 BizTalk 应用程序](../core/deploying-and-managing-biztalk-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="0e570-107">For more information, see [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md) and [Deploying and Managing BizTalk Applications](../core/deploying-and-managing-biztalk-applications.md).</span></span> <span data-ttu-id="0e570-108">当一条消息呈现给与激活的条件相符的引擎或业务流程调用从另一个业务流程，接收，引擎创建业务流程的新实例并运行该实例。</span><span class="sxs-lookup"><span data-stu-id="0e570-108">When an orchestration is invoked from another orchestration, or a message is presented to the engine that matches the criteria in an activation receive, the engine creates a new instance of the orchestration and runs that instance.</span></span> <span data-ttu-id="0e570-109">它可以同时运行多个不同的实例。</span><span class="sxs-lookup"><span data-stu-id="0e570-109">It can run many different instances concurrently.</span></span>  
  
## <a name="calling-and-starting-orchestrations"></a><span data-ttu-id="0e570-110">调用和启动业务流程</span><span class="sxs-lookup"><span data-stu-id="0e570-110">Calling and starting orchestrations</span></span>  
 <span data-ttu-id="0e570-111">**调用 Orchestration**形状和**启动 Orchestration**形状可以用于激活另一个业务流程。</span><span class="sxs-lookup"><span data-stu-id="0e570-111">The **Call Orchestration** shape and **Start Orchestration** shape can be used to activate another orchestration.</span></span> <span data-ttu-id="0e570-112">在这两种情况下，调用方可以传入参数，以交换信息与其他业务流程。</span><span class="sxs-lookup"><span data-stu-id="0e570-112">In both cases, the caller can pass in parameters to exchange information with the other orchestration.</span></span> <span data-ttu-id="0e570-113">有关详细信息，请参阅[如何将参数添加到业务流程](../core/how-to-add-parameters-to-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="0e570-113">For more information, see [How to Add Parameters to Orchestrations](../core/how-to-add-parameters-to-orchestrations.md).</span></span>  
  
## <a name="using-activation-receives-with-filter-expression"></a><span data-ttu-id="0e570-114">使用激活接收使用筛选器表达式</span><span class="sxs-lookup"><span data-stu-id="0e570-114">Using activation receives with filter expression</span></span>  
 <span data-ttu-id="0e570-115">**接收**形状还可能使用的筛选器表达式来要求以激活的进一步条件。</span><span class="sxs-lookup"><span data-stu-id="0e570-115">The **Receive** shape might also use a filter expression to require further criteria for activation.</span></span> <span data-ttu-id="0e570-116">如果此消息是正确的类型，而且某些属性或消息属性满足所有筛选表达式中的条件**接收**形状接受消息并激活业务流程。</span><span class="sxs-lookup"><span data-stu-id="0e570-116">If the message is of the correct type and some property or properties of the message meet all of the criteria in the filter expression, the **Receive** shape accepts the message and the orchestration is activated.</span></span> <span data-ttu-id="0e570-117">接收形状称为*激活接收*。</span><span class="sxs-lookup"><span data-stu-id="0e570-117">Such a Receive shape is referred to as an *activation receive*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e570-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0e570-118">See Also</span></span>  
 <span data-ttu-id="0e570-119">[如何配置调用业务流程形状](../core/how-to-configure-the-call-orchestration-shape.md) </span><span class="sxs-lookup"><span data-stu-id="0e570-119">[How to Configure the Call Orchestration Shape](../core/how-to-configure-the-call-orchestration-shape.md) </span></span>  
 <span data-ttu-id="0e570-120">[如何配置开始业务流程形状](../core/how-to-configure-the-start-orchestration-shape.md) </span><span class="sxs-lookup"><span data-stu-id="0e570-120">[How to Configure the Start Orchestration Shape](../core/how-to-configure-the-start-orchestration-shape.md) </span></span>  
 <span data-ttu-id="0e570-121">[如何配置接收形状](../core/how-to-configure-the-receive-shape.md) </span><span class="sxs-lookup"><span data-stu-id="0e570-121">[How to Configure the Receive Shape](../core/how-to-configure-the-receive-shape.md) </span></span>  
 [<span data-ttu-id="0e570-122">生成并运行业务流程</span><span class="sxs-lookup"><span data-stu-id="0e570-122">Building and Running Orchestrations</span></span>](../core/building-and-running-orchestrations.md)