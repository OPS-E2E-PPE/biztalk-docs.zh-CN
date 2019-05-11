---
title: 将业务流程用作路线服务订阅方 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 278564f1-de9f-4fbf-8c7f-09b3e607c28b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 707c9b37f671191b743912cb391c8e41d67d007b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396459"
---
# <a name="using-an-orchestration-as-an-itinerary-service-subscriber"></a><span data-ttu-id="7d955-102">将业务流程用作路线服务订阅方</span><span class="sxs-lookup"><span data-stu-id="7d955-102">Using an Orchestration as an Itinerary Service Subscriber</span></span>
<span data-ttu-id="7d955-103">业务流程也可用作路线服务。</span><span class="sxs-lookup"><span data-stu-id="7d955-103">Orchestrations can also act as itinerary services.</span></span> <span data-ttu-id="7d955-104">若要参与路线时，必须首先设计业务流程作为直接绑定;若要执行此操作，请使用类似于前一个主题中的发送端口的筛选器订阅[发送端口用作路线服务订阅方](../esb-toolkit/using-a-send-port-as-an-itinerary-service-subscriber.md)。</span><span class="sxs-lookup"><span data-stu-id="7d955-104">To participate in an itinerary, you must first design the orchestration as direct-bound; to do this, use a filter subscription similar to that of the send port in the previous topic, [Using a Send Port as an Itinerary Service Subscriber](../esb-toolkit/using-a-send-port-as-an-itinerary-service-subscriber.md).</span></span> <span data-ttu-id="7d955-105">图 1 显示了合适的业务流程，可以提取满足以下条件的任何消息筛选器表达式的一个示例：</span><span class="sxs-lookup"><span data-stu-id="7d955-105">Figure 1 shows an example of a filter expression for a suitable orchestration to pick up any message that meets the following conditions:</span></span>  

- <span data-ttu-id="7d955-106">**ServiceName = Microsoft.Practices.ESB.Services.Transform**</span><span class="sxs-lookup"><span data-stu-id="7d955-106">**ServiceName = Microsoft.Practices.ESB.Services.Transform**</span></span>  

- <span data-ttu-id="7d955-107">**ServiceState = Pending**</span><span class="sxs-lookup"><span data-stu-id="7d955-107">**ServiceState = Pending**</span></span>  

- <span data-ttu-id="7d955-108">**ServiceType = Orchestration**</span><span class="sxs-lookup"><span data-stu-id="7d955-108">**ServiceType = Orchestration**</span></span>  

  <span data-ttu-id="7d955-109">![业务流程](../esb-toolkit/media/ch4-orchestration.jpg "Ch4-业务流程")</span><span class="sxs-lookup"><span data-stu-id="7d955-109">![Orchestration](../esb-toolkit/media/ch4-orchestration.jpg "Ch4-Orchestration")</span></span>  

  <span data-ttu-id="7d955-110">**图 1**</span><span class="sxs-lookup"><span data-stu-id="7d955-110">**Figure 1**</span></span>  

  <span data-ttu-id="7d955-111">**将参与作为订阅者路线的业务流程的示例筛选表达式**</span><span class="sxs-lookup"><span data-stu-id="7d955-111">**Example filter expression for an orchestration that will participate in an itinerary as a subscriber**</span></span>  

  <span data-ttu-id="7d955-112">ESB 管道中的验证步骤消息到达时在 Microsoft BizTalk Server 中通过 ESB 接入点，将筛选器属性的属性值写入到 BizTalk 上下文属性的传入消息;这将它们升级到消息上下文。</span><span class="sxs-lookup"><span data-stu-id="7d955-112">When messages arrive in Microsoft BizTalk Server through an ESB on-ramp, the validation step in the ESB pipeline writes the property values for the filter properties into the BizTalk context properties of the incoming message; this promotes them to the message context.</span></span> <span data-ttu-id="7d955-113">路线服务始终设置**ServiceName**属性当前处于活动状态的服务来处理接下来，并使用名称服务**ServiceState**属性值为**挂起**。</span><span class="sxs-lookup"><span data-stu-id="7d955-113">The itinerary service always sets the **ServiceName** property for the currently active service to the name of the service to process next, and with a **ServiceState** property value of **Pending**.</span></span> <span data-ttu-id="7d955-114">对于订阅，则必须设置至少第三个以下属性：</span><span class="sxs-lookup"><span data-stu-id="7d955-114">For a subscription, you must set at least the first three of the following properties:</span></span>  

- <span data-ttu-id="7d955-115">**ServiceName。**</span><span class="sxs-lookup"><span data-stu-id="7d955-115">**ServiceName.**</span></span> <span data-ttu-id="7d955-116">这是服务的名称，存储在 ESB 路线中，可以是任何名称。</span><span class="sxs-lookup"><span data-stu-id="7d955-116">This is the name of the service, as stored in the ESB itinerary, and can be any name.</span></span> <span data-ttu-id="7d955-117">路线使用此名称来标识要执行的服务。</span><span class="sxs-lookup"><span data-stu-id="7d955-117">The itinerary uses this name to identify which service to execute.</span></span>  

- <span data-ttu-id="7d955-118">**ServiceState.**</span><span class="sxs-lookup"><span data-stu-id="7d955-118">**ServiceState.**</span></span> <span data-ttu-id="7d955-119">这是当前的路线服务步骤，若要执行的状态。</span><span class="sxs-lookup"><span data-stu-id="7d955-119">This is the state of the current itinerary service step to execute.</span></span> <span data-ttu-id="7d955-120">当前服务步骤 （适用于处理下一步） 将始终具有值**挂起**、 任一 ESB 路线管道组件设置，ESB 路线选择器管道组件或代码的调用**提前**路线 API 方法。</span><span class="sxs-lookup"><span data-stu-id="7d955-120">The current service step (for processing next) will always have the value **Pending**, set by either the ESB itinerary pipeline component, the ESB Itinerary Selector pipeline component, or code that calls the **Advance** method of the itinerary API.</span></span>  

- <span data-ttu-id="7d955-121">**ServiceType.**</span><span class="sxs-lookup"><span data-stu-id="7d955-121">**ServiceType.**</span></span> <span data-ttu-id="7d955-122">此属性定义的服务，以指明是否源自从业务流程或消息传送子系统在 BizTalk 中的类型。</span><span class="sxs-lookup"><span data-stu-id="7d955-122">This property defines the type of service, indicating whether it originates from the orchestration or the messaging subsystem in BizTalk.</span></span>  

- <span data-ttu-id="7d955-123">**IsRequestResponse。**</span><span class="sxs-lookup"><span data-stu-id="7d955-123">**IsRequestResponse.**</span></span> <span data-ttu-id="7d955-124">此可选属性必须具有相同的值**IsRequestResponse**服务属性。</span><span class="sxs-lookup"><span data-stu-id="7d955-124">This optional property must have the same value as the **IsRequestResponse** property of the service.</span></span>
