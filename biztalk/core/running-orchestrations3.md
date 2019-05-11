---
title: 运行 Orchestrations3 |Microsoft Docs
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
ms.openlocfilehash: dc582889d30922b4446e9a941906064a8c08c418
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254537"
---
# <a name="running-orchestrations"></a><span data-ttu-id="a4d92-102">运行业务流程</span><span class="sxs-lookup"><span data-stu-id="a4d92-102">Running Orchestrations</span></span>
<span data-ttu-id="a4d92-103">业务流程实例专为触发通过显式调用从另一个业务流程 — 使用**调用业务流程**形状或**启动业务流程**形状，或通过接收激活消息。</span><span class="sxs-lookup"><span data-stu-id="a4d92-103">Orchestration instances are designed to be triggered either by an explicit call from another orchestration—using a **Call Orchestration** shape or **Start Orchestration** shape—or by receipt of an activation message.</span></span> <span data-ttu-id="a4d92-104">激活消息架构中指定**消息**属性。</span><span class="sxs-lookup"><span data-stu-id="a4d92-104">The activation message schema is specified in the **Message** property.</span></span> <span data-ttu-id="a4d92-105">应相应地，设计您的业务流程和设置**激活**上的属性**接收**形状为 true，或确保调用的业务流程存在并且正确配置为运行新的业务流程。</span><span class="sxs-lookup"><span data-stu-id="a4d92-105">You should design your orchestration accordingly, and either set the **Activate** property on a **Receive** shape to true, or make sure that a calling orchestration exists and is configured properly to run the new orchestration.</span></span>  
  
 <span data-ttu-id="a4d92-106">可以运行任何实例之前，必须首先将绑定和部署 BizTalk 程序集，然后登记并启动业务流程引擎以开始处理。</span><span class="sxs-lookup"><span data-stu-id="a4d92-106">Before any instances can run, you must first bind and deploy the BizTalk assembly, and then enlist and start the orchestration engine to begin processing.</span></span> <span data-ttu-id="a4d92-107">有关详细信息，请参阅[从到 BizTalk 应用程序的 Visual Studio 部署 BizTalk 程序集](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)并[部署和管理 BizTalk 应用程序](../core/deploying-and-managing-biztalk-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="a4d92-107">For more information, see [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md) and [Deploying and Managing BizTalk Applications](../core/deploying-and-managing-biztalk-applications.md).</span></span> <span data-ttu-id="a4d92-108">从另一个业务流程调用业务流程或消息提供给引擎，匹配中激活的条件时接收，引擎创建业务流程的新实例，并运行该实例。</span><span class="sxs-lookup"><span data-stu-id="a4d92-108">When an orchestration is invoked from another orchestration, or a message is presented to the engine that matches the criteria in an activation receive, the engine creates a new instance of the orchestration and runs that instance.</span></span> <span data-ttu-id="a4d92-109">它可以同时运行多个不同实例。</span><span class="sxs-lookup"><span data-stu-id="a4d92-109">It can run many different instances concurrently.</span></span>  
  
## <a name="calling-and-starting-orchestrations"></a><span data-ttu-id="a4d92-110">调用和启动业务流程</span><span class="sxs-lookup"><span data-stu-id="a4d92-110">Calling and starting orchestrations</span></span>  
 <span data-ttu-id="a4d92-111">**调用业务流程**形状和**启动业务流程**形状可用于激活其他业务流程。</span><span class="sxs-lookup"><span data-stu-id="a4d92-111">The **Call Orchestration** shape and **Start Orchestration** shape can be used to activate another orchestration.</span></span> <span data-ttu-id="a4d92-112">在这两种情况下，调用方可以将参数与另一个业务流程交换信息。</span><span class="sxs-lookup"><span data-stu-id="a4d92-112">In both cases, the caller can pass in parameters to exchange information with the other orchestration.</span></span> <span data-ttu-id="a4d92-113">有关详细信息，请参阅[如何向业务流程添加参数](../core/how-to-add-parameters-to-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="a4d92-113">For more information, see [How to Add Parameters to Orchestrations](../core/how-to-add-parameters-to-orchestrations.md).</span></span>  
  
## <a name="using-activation-receives-with-filter-expression"></a><span data-ttu-id="a4d92-114">使用激活接收与筛选器表达式</span><span class="sxs-lookup"><span data-stu-id="a4d92-114">Using activation receives with filter expression</span></span>  
 <span data-ttu-id="a4d92-115">**接收**形状还可以使用筛选器表达式来激活需要进一步的条件。</span><span class="sxs-lookup"><span data-stu-id="a4d92-115">The **Receive** shape might also use a filter expression to require further criteria for activation.</span></span> <span data-ttu-id="a4d92-116">如果消息是正确的类型和一些属性或消息的属性满足所有筛选器表达式中的条件**接收**形状接受该消息并激活该业务流程。</span><span class="sxs-lookup"><span data-stu-id="a4d92-116">If the message is of the correct type and some property or properties of the message meet all of the criteria in the filter expression, the **Receive** shape accepts the message and the orchestration is activated.</span></span> <span data-ttu-id="a4d92-117">此类接收形状称为*激活接收*。</span><span class="sxs-lookup"><span data-stu-id="a4d92-117">Such a Receive shape is referred to as an *activation receive*.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4d92-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="a4d92-118">See Also</span></span>  
 <span data-ttu-id="a4d92-119">[如何配置调用业务流程形状](../core/how-to-configure-the-call-orchestration-shape.md) </span><span class="sxs-lookup"><span data-stu-id="a4d92-119">[How to Configure the Call Orchestration Shape](../core/how-to-configure-the-call-orchestration-shape.md) </span></span>  
 <span data-ttu-id="a4d92-120">[如何配置启动业务流程形状](../core/how-to-configure-the-start-orchestration-shape.md) </span><span class="sxs-lookup"><span data-stu-id="a4d92-120">[How to Configure the Start Orchestration Shape](../core/how-to-configure-the-start-orchestration-shape.md) </span></span>  
 <span data-ttu-id="a4d92-121">[如何配置接收形状](../core/how-to-configure-the-receive-shape.md) </span><span class="sxs-lookup"><span data-stu-id="a4d92-121">[How to Configure the Receive Shape](../core/how-to-configure-the-receive-shape.md) </span></span>  
 [<span data-ttu-id="a4d92-122">生成和运行业务流程</span><span class="sxs-lookup"><span data-stu-id="a4d92-122">Building and Running Orchestrations</span></span>](../core/building-and-running-orchestrations.md)