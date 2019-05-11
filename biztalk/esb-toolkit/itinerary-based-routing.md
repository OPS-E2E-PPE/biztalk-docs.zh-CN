---
title: 基于路线的路由 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 28028721-798c-4302-a532-d863ed8ea88b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe1132920b18cc331786d515b916de2861409339
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65261557"
---
# <a name="itinerary-based-routing"></a><span data-ttu-id="42323-102">基于路线的路由</span><span class="sxs-lookup"><span data-stu-id="42323-102">Itinerary-Based Routing</span></span>
<span data-ttu-id="42323-103">核心功能之一[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]是预配的基于路线的路由，简化了企业级消息传送应用程序的开发和降低成本的维护大量的静态发送端口和接收位置。</span><span class="sxs-lookup"><span data-stu-id="42323-103">One of the core features of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] is the provision of itinerary-based routing that simplifies the development of enterprise-level messaging applications and reduces the costs of maintaining a large number of static send ports and receive locations.</span></span>  
  
 <span data-ttu-id="42323-104">路线组成的服务执行的列表 （其中可以包含路由、 转换和自定义服务） 和解决执行每个服务所需的元数据所需的配置信息。</span><span class="sxs-lookup"><span data-stu-id="42323-104">An itinerary consists of the list of services to execute (which can contain routing, transformation, and custom services) and the configuration information required to resolve the metadata necessary to execute each of these services.</span></span> <span data-ttu-id="42323-105">例如，一个阶段的路线可能路由的服务;与此服务关联的解决方案说明可能指示服务执行通用描述、 发现和集成 (UDDI) 或业务规则引擎 (BRE) 查找有关将路由到特定的目标终结点信息消息。</span><span class="sxs-lookup"><span data-stu-id="42323-105">For example, one stage of the itinerary may be a routing service; the resolution instructions associated with this service may instruct the service to perform a Universal Description, Discovery, and Integration (UDDI) or Business Rules Engine (BRE) lookup for information about a specific target endpoint to which it will route the message.</span></span>  
  
 <span data-ttu-id="42323-106">路线可以附加到入站消息中，按以下方式：</span><span class="sxs-lookup"><span data-stu-id="42323-106">Itineraries can be attached to an inbound message in the following ways:</span></span>  
  
- <span data-ttu-id="42323-107">客户端提交的消息不包含任何与路线相关的数据。</span><span class="sxs-lookup"><span data-stu-id="42323-107">The message submitted by a client does not contain any itinerary-related data.</span></span> <span data-ttu-id="42323-108">接收管道解析、 检索，并将附加适当路线基于消息内容或上下文。</span><span class="sxs-lookup"><span data-stu-id="42323-108">The receiving pipeline resolves, retrieves, and attaches the appropriate itinerary based on message content or context.</span></span>  
  
- <span data-ttu-id="42323-109">客户端提交的消息可以包含定义路线引用数据，其中包含路线的名称和版本，以及业务活动监视 (BAM) 跟踪的唯一标识符的 SOAP 标头。</span><span class="sxs-lookup"><span data-stu-id="42323-109">The message submitted by a client can contain a SOAP header that defines the itinerary reference data, which contains the itinerary name and version, as well as a unique identifier for Business Activity Monitoring (BAM) tracking.</span></span> <span data-ttu-id="42323-110">接收管道评估此信息，并从 ESBItineraryDb 数据库中检索相应的路线。</span><span class="sxs-lookup"><span data-stu-id="42323-110">The receiving pipeline evaluates this information and retrieves the appropriate itinerary from the ESBItineraryDb database.</span></span>  
  
- <span data-ttu-id="42323-111">客户端提交的消息可以有一个路线 SOAP 标头，其中包含路线的整个内容。</span><span class="sxs-lookup"><span data-stu-id="42323-111">The message submitted by a client can have an itinerary SOAP header, which contains the entire content of the itinerary.</span></span> <span data-ttu-id="42323-112">这种设计不建议，应仅用于测试目的使用。</span><span class="sxs-lookup"><span data-stu-id="42323-112">This design is not recommended and should be used only for testing purposes.</span></span>  
  
  <span data-ttu-id="42323-113">对于入站消息解析路线后，接收管道将升级到消息上下文，从而使可访问的任何订阅此消息的 Microsoft BizTalk Server 组件的属性的路线数据。</span><span class="sxs-lookup"><span data-stu-id="42323-113">After an itinerary is resolved for an inbound message, the receive pipeline promotes the itinerary data to the message context, thereby making the properties available to be accessed by any Microsoft BizTalk Server component that subscribes to this message.</span></span> <span data-ttu-id="42323-114">BizTalk Server 组件可以获取当前的行程步骤的详细信息，完成所需的处理和/或前进到下一步的路线。</span><span class="sxs-lookup"><span data-stu-id="42323-114">BizTalk Server components can obtain details of the current itinerary step, complete the required processing, and/or advance the itinerary to the next step.</span></span> <span data-ttu-id="42323-115">这样将导致下一个服务中路线来处理消息，根据发布-订阅功能的 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="42323-115">This causes the next service in the itinerary to process the message, according to the publish-subscribe functionality of BizTalk Server.</span></span>  
  
  <span data-ttu-id="42323-116">ESB 动态解析机制、 转换、 路线处理和消息创建有关的信息，请参阅[主要方案和开发任务](../esb-toolkit/key-scenarios-and-development-tasks.md)。</span><span class="sxs-lookup"><span data-stu-id="42323-116">For information about the ESB dynamic resolution mechanism, transformations, itinerary processing, and message creation, see [Key Scenarios and Development Tasks](../esb-toolkit/key-scenarios-and-development-tasks.md).</span></span>