---
title: 实例化和初始化接收适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c5cb5ba7-e2b5-49d2-adf5-a8df0bb81def
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 73bb52934483cc47ea45cd0e6ff72e8e57752ffd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331823"
---
# <a name="instantiating-and-initializing-a-receive-adapter"></a><span data-ttu-id="2a833-102">实例化和初始化接收适配器</span><span class="sxs-lookup"><span data-stu-id="2a833-102">Instantiating and Initializing a Receive Adapter</span></span>
<span data-ttu-id="2a833-103">立即接收适配器实例化后由消息引擎初始化，该引擎将调用为 IBTTransportControl QueryInteraface。</span><span class="sxs-lookup"><span data-stu-id="2a833-103">Immediately after a receive adapter is instantiated it is initialized by the Messaging Engine, the engine calls QueryInteraface for IBTTransportControl.</span></span> <span data-ttu-id="2a833-104">然后，它调用 IBTTransportControl<strong>。初始化</strong>传入适配器的传输代理，该适配器仍然存在的成员变量中。</span><span class="sxs-lookup"><span data-stu-id="2a833-104">It then calls IBTTransportControl<strong>.Initialize</strong> passing in the adapter's transport proxy, which the adapter persists in a member variable.</span></span> <span data-ttu-id="2a833-105">接下来，引擎将调用**QueryInterface**有关**IPersistPropertyBag**。</span><span class="sxs-lookup"><span data-stu-id="2a833-105">Next the engine calls **QueryInterface** for **IPersistPropertyBag**.</span></span> <span data-ttu-id="2a833-106">这是一个可选的接口;如果适配器实现它，处理程序配置传递给适配器**负载**方法调用。</span><span class="sxs-lookup"><span data-stu-id="2a833-106">This is an optional interface; if the adapter implements it, the handler configuration is passed to the adapter in the **Load** method call.</span></span> <span data-ttu-id="2a833-107">初始化接收适配器的最后阶段涉及将终结点配置传递到适配器。</span><span class="sxs-lookup"><span data-stu-id="2a833-107">The final stage of initializing a receive adapter involves passing the endpoint configuration to the adapter.</span></span> <span data-ttu-id="2a833-108">在此阶段则引擎将调用**IBTTransportConfig.AddReceiveEndpoint**一次针对每个活动的终结点，在 URI 中传递终结点、 适配器特定配置的终结点，和 BizTalk 配置该终结点。</span><span class="sxs-lookup"><span data-stu-id="2a833-108">During this phase the engine calls **IBTTransportConfig.AddReceiveEndpoint** once for each active endpoint, passing in the URI for the endpoint, the adapter specific configuration for the endpoint, and the BizTalk configuration for that endpoint.</span></span>  
  
 <span data-ttu-id="2a833-109">下图说明了这一序列的 API 调用。</span><span class="sxs-lookup"><span data-stu-id="2a833-109">The following figure illustrates this sequence of API calls.</span></span> <span data-ttu-id="2a833-110">适配器实现的接口显示为蓝色。</span><span class="sxs-lookup"><span data-stu-id="2a833-110">The adapter implements the interfaces shown in blue.</span></span>  
  
 <span data-ttu-id="2a833-111">![](../core/media/sequence-of-init-calls.gif "Sequence_of_init_calls")</span><span class="sxs-lookup"><span data-stu-id="2a833-111">![](../core/media/sequence-of-init-calls.gif "Sequence_of_init_calls")</span></span>  
  
 <span data-ttu-id="2a833-112">**实现提示：** 一般情况下，适配器不应阻止消息引擎在调用如**IBTTransportControl.Initialize**， **ipersistpropertybag.load 这样**，和**IBTTransportConfig.AddReceiveEndpoint**。</span><span class="sxs-lookup"><span data-stu-id="2a833-112">**Implementation Tip:** In general, adapters should not block the Messaging Engine in calls such as **IBTTransportControl.Initialize**, **IPersistPropertyBag.Load**, and **IBTTransportConfig.AddReceiveEndpoint**.</span></span> <span data-ttu-id="2a833-113">执行过多的处理中这些调用可以在服务启动时间产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="2a833-113">Performing excessive processing in these calls can have a negative impact on service startup time.</span></span>  
  
 <span data-ttu-id="2a833-114">所有接收适配器具有一个或多个关联接收位置在服务启动时创建。</span><span class="sxs-lookup"><span data-stu-id="2a833-114">All receive adapters that have one or more associated receive locations are created at service startup.</span></span> <span data-ttu-id="2a833-115">所有接收适配器是异步的支持批处理。</span><span class="sxs-lookup"><span data-stu-id="2a833-115">All receive adapters are asynchronous and support batching.</span></span> <span data-ttu-id="2a833-116">它们可以是进程内或隔离。</span><span class="sxs-lookup"><span data-stu-id="2a833-116">They can be in-process or isolated.</span></span> <span data-ttu-id="2a833-117">有关其他信息接收适配器变量，请参阅[适配器变量](../core/adapter-variables.md)。</span><span class="sxs-lookup"><span data-stu-id="2a833-117">For additional information about receive adapter variables, see [Adapter Variables](../core/adapter-variables.md).</span></span>