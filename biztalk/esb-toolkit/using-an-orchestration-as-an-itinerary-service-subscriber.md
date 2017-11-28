---
title: "为路线服务的订阅服务器使用一个业务流程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 278564f1-de9f-4fbf-8c7f-09b3e607c28b
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f496884d0aed8d5f351f681ca8cfe59e05684240
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-an-orchestration-as-an-itinerary-service-subscriber"></a><span data-ttu-id="0a2a8-102">为路线服务的订阅服务器使用一个业务流程</span><span class="sxs-lookup"><span data-stu-id="0a2a8-102">Using an Orchestration as an Itinerary Service Subscriber</span></span>
<span data-ttu-id="0a2a8-103">业务流程还可以充当路线的服务。</span><span class="sxs-lookup"><span data-stu-id="0a2a8-103">Orchestrations can also act as itinerary services.</span></span> <span data-ttu-id="0a2a8-104">若要参与路线，必须首先设计为直接绑定; 业务流程若要执行此操作，使用类似于在上一主题中，发送端口的筛选器订阅[为路线服务的订阅服务器使用发送端口](../esb-toolkit/using-a-send-port-as-an-itinerary-service-subscriber.md)。</span><span class="sxs-lookup"><span data-stu-id="0a2a8-104">To participate in an itinerary, you must first design the orchestration as direct-bound; to do this, use a filter subscription similar to that of the send port in the previous topic, [Using a Send Port as an Itinerary Service Subscriber](../esb-toolkit/using-a-send-port-as-an-itinerary-service-subscriber.md).</span></span> <span data-ttu-id="0a2a8-105">图 1 显示合适的业务流程，以拾取满足下列条件的任何消息筛选器表达式的示例：</span><span class="sxs-lookup"><span data-stu-id="0a2a8-105">Figure 1 shows an example of a filter expression for a suitable orchestration to pick up any message that meets the following conditions:</span></span>  
  
-   <span data-ttu-id="0a2a8-106">**ServiceName = Microsoft.Practices.ESB.Services.Transform**</span><span class="sxs-lookup"><span data-stu-id="0a2a8-106">**ServiceName = Microsoft.Practices.ESB.Services.Transform**</span></span>  
  
-   <span data-ttu-id="0a2a8-107">**ServiceState = 挂起**</span><span class="sxs-lookup"><span data-stu-id="0a2a8-107">**ServiceState = Pending**</span></span>  
  
-   <span data-ttu-id="0a2a8-108">**ServiceType = 业务流程**</span><span class="sxs-lookup"><span data-stu-id="0a2a8-108">**ServiceType = Orchestration**</span></span>  
  
 <span data-ttu-id="0a2a8-109">![业务流程](../esb-toolkit/media/ch4-orchestration.jpg "第四章第 4 业务流程")</span><span class="sxs-lookup"><span data-stu-id="0a2a8-109">![Orchestration](../esb-toolkit/media/ch4-orchestration.jpg "Ch4-Orchestration")</span></span>  
  
 <span data-ttu-id="0a2a8-110">**图 1**</span><span class="sxs-lookup"><span data-stu-id="0a2a8-110">**Figure 1**</span></span>  
  
 <span data-ttu-id="0a2a8-111">**适用于将参与作为订阅服务器路线业务流程的示例筛选器表达式**</span><span class="sxs-lookup"><span data-stu-id="0a2a8-111">**Example filter expression for an orchestration that will participate in an itinerary as a subscriber**</span></span>  
  
 <span data-ttu-id="0a2a8-112">当消息到达时通过 ESB 入口 Microsoft BizTalk Server 中时，则 ESB 管道中的验证步骤将筛选器属性的属性值写入的传入消息中; BizTalk 上下文属性这将它们升级到消息上下文。</span><span class="sxs-lookup"><span data-stu-id="0a2a8-112">When messages arrive in Microsoft BizTalk Server through an ESB on-ramp, the validation step in the ESB pipeline writes the property values for the filter properties into the BizTalk context properties of the incoming message; this promotes them to the message context.</span></span> <span data-ttu-id="0a2a8-113">路线服务始终设置**ServiceName**处理接下来，并与服务的名称的当前处于活动状态服务的属性**ServiceState**属性值**挂起**。</span><span class="sxs-lookup"><span data-stu-id="0a2a8-113">The itinerary service always sets the **ServiceName** property for the currently active service to the name of the service to process next, and with a **ServiceState** property value of **Pending**.</span></span> <span data-ttu-id="0a2a8-114">对于订阅，你必须设置至少第一个三个以下属性：</span><span class="sxs-lookup"><span data-stu-id="0a2a8-114">For a subscription, you must set at least the first three of the following properties:</span></span>  
  
-   <span data-ttu-id="0a2a8-115">**ServiceName。**</span><span class="sxs-lookup"><span data-stu-id="0a2a8-115">**ServiceName.**</span></span> <span data-ttu-id="0a2a8-116">这是服务的名称，因为存储在 ESB 路线，并可以是任何名称。</span><span class="sxs-lookup"><span data-stu-id="0a2a8-116">This is the name of the service, as stored in the ESB itinerary, and can be any name.</span></span> <span data-ttu-id="0a2a8-117">路线使用此名称来标识要执行的服务。</span><span class="sxs-lookup"><span data-stu-id="0a2a8-117">The itinerary uses this name to identify which service to execute.</span></span>  
  
-   <span data-ttu-id="0a2a8-118">**ServiceState。**</span><span class="sxs-lookup"><span data-stu-id="0a2a8-118">**ServiceState.**</span></span> <span data-ttu-id="0a2a8-119">这是当前的路线服务步骤，若要执行的状态。</span><span class="sxs-lookup"><span data-stu-id="0a2a8-119">This is the state of the current itinerary service step to execute.</span></span> <span data-ttu-id="0a2a8-120">当前服务步骤 （适用于处理下一步） 将始终具有值**挂起**、 任一 ESB 路线管道组件设置，ESB 路线选择器管道组件，或代码调用**高级**路线 API 方法。</span><span class="sxs-lookup"><span data-stu-id="0a2a8-120">The current service step (for processing next) will always have the value **Pending**, set by either the ESB itinerary pipeline component, the ESB Itinerary Selector pipeline component, or code that calls the **Advance** method of the itinerary API.</span></span>  
  
-   <span data-ttu-id="0a2a8-121">**ServiceType。**</span><span class="sxs-lookup"><span data-stu-id="0a2a8-121">**ServiceType.**</span></span> <span data-ttu-id="0a2a8-122">此属性定义的服务，，该值指示是否来自业务流程或 BizTalk 中的消息传递子系统的类型。</span><span class="sxs-lookup"><span data-stu-id="0a2a8-122">This property defines the type of service, indicating whether it originates from the orchestration or the messaging subsystem in BizTalk.</span></span>  
  
-   <span data-ttu-id="0a2a8-123">**IsRequestResponse。**</span><span class="sxs-lookup"><span data-stu-id="0a2a8-123">**IsRequestResponse.**</span></span> <span data-ttu-id="0a2a8-124">此可选属性必须具有相同的值**IsRequestResponse**服务属性。</span><span class="sxs-lookup"><span data-stu-id="0a2a8-124">This optional property must have the same value as the **IsRequestResponse** property of the service.</span></span>