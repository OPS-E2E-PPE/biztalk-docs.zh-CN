---
title: ESB Web 服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c122ecdd-344a-4f76-9c73-bf692d479c09
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe1b2f6bc30982ea05717fd8e151997e2a3f90a2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973358"
---
# <a name="esb-web-services"></a><span data-ttu-id="d5af2-102">ESB Web 服务</span><span class="sxs-lookup"><span data-stu-id="d5af2-102">ESB Web Services</span></span>
<span data-ttu-id="d5af2-103">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]包含以下 Web 服务：</span><span class="sxs-lookup"><span data-stu-id="d5af2-103">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] contains the following Web services:</span></span>  
  
- <span data-ttu-id="d5af2-104"><strong>路线接入点 Web 服务。</strong>这些服务接受外部消息并提交以进行处理的消息。</span><span class="sxs-lookup"><span data-stu-id="d5af2-104"><strong>Itinerary On-ramp Web services.</strong>These services accept external messages and submit the messages for processing.</span></span> <span data-ttu-id="d5af2-105">路线的内容包含描述要执行哪些服务的元数据和处理说明。</span><span class="sxs-lookup"><span data-stu-id="d5af2-105">The content of an itinerary contains metadata and processing instructions that describe which services to execute.</span></span> <span data-ttu-id="d5af2-106">路由服务定义到应将消息路由，而转换服务指定应如何转换消息的终结点。</span><span class="sxs-lookup"><span data-stu-id="d5af2-106">Routing services define the endpoints to which the message should be routed, while transformation services specify how messages should be transformed.</span></span> <span data-ttu-id="d5af2-107">这些服务支持单向和双向 （请求-响应） 处理;提供了 ASMX 和 Windows Communication Foundation (WCF) 实现。</span><span class="sxs-lookup"><span data-stu-id="d5af2-107">These services support both one-way and two-way (request-response) processing; both ASMX and Windows Communication Foundation (WCF) implementations are provided.</span></span> <span data-ttu-id="d5af2-108">路线接入点 Web 服务不是特定于类型 – 消息，因此它们接受任何消息类型。</span><span class="sxs-lookup"><span data-stu-id="d5af2-108">The Itinerary On-ramp Web services are not message type–specific, so they accept any message type.</span></span>  
  
- <span data-ttu-id="d5af2-109"><strong>解析程序 Web 服务。</strong>此服务允许外部应用程序调用 Microsoft ESB 解析程序框架来查找 ESB 的终结点冲突解决程序框架支持的解决机制。</span><span class="sxs-lookup"><span data-stu-id="d5af2-109"><strong>Resolver Web service.</strong>This service allows external applications to call the Microsoft ESB Resolver Framework to look up ESB endpoints based on resolution mechanisms supported by the Resolver Framework.</span></span> <span data-ttu-id="d5af2-110">该服务还提供了 ASMX 和 WCF 的实现。</span><span class="sxs-lookup"><span data-stu-id="d5af2-110">The service also offers both ASMX and WCF implementations.</span></span>  
  
- <span data-ttu-id="d5af2-111"><strong>转换 Web 服务。</strong>此服务允许执行的 Microsoft BizTalk Server 映射无需使用的消息框暂留，扩展映射执行不基于 BizTalk Server 的应用程序的 BizTalk Server 的功能。</span><span class="sxs-lookup"><span data-stu-id="d5af2-111"><strong>Transformation Web service.</strong>This service allows execution of Microsoft BizTalk Server maps without the overhead of Message Box persistence, extending the capability of BizTalk Server map execution to applications that are not based on BizTalk Server.</span></span> <span data-ttu-id="d5af2-112">该服务加强了 ASMX 和 WCF 的实现。</span><span class="sxs-lookup"><span data-stu-id="d5af2-112">The service offers both ASMX and WCF implementations.</span></span>  
  
- <span data-ttu-id="d5af2-113"><strong>异常处理 Web 服务。</strong>此服务接受来自外部源的异常消息，并使用故障处理器管道的路由将规范化、 跟踪和将异常消息发布到 ESB 管理门户。</span><span class="sxs-lookup"><span data-stu-id="d5af2-113"><strong>Exception Handling Web service.</strong>This service accepts exception messages from external sources and routes using the fault processor pipeline will normalize, track, and publish the exception message to the ESB Management Portal.</span></span> <span data-ttu-id="d5af2-114">该服务加强了 ASMX 和 WCF 的实现。</span><span class="sxs-lookup"><span data-stu-id="d5af2-114">The service offers both ASMX and WCF implementations.</span></span>  
  
- <span data-ttu-id="d5af2-115"><strong>UDDI Web 服务。</strong>此服务后，应用程序和用户，若要查找的终结点的服务名称、 业务提供程序或业务类别; 它还允许应用程序和用户操作的业务提供程序，服务，，类别存储中UDDI 存储库。</span><span class="sxs-lookup"><span data-stu-id="d5af2-115"><strong>UDDI Web service.</strong>This service enables applications and users to look up endpoints based on the service name, business provider, or business category; it also allows applications and users to manipulate the business providers, services, and categories stored in a UDDI repository.</span></span> <span data-ttu-id="d5af2-116">这是供 ESB 管理门户和第三方提供商的基础结构服务。</span><span class="sxs-lookup"><span data-stu-id="d5af2-116">This is a key infrastructure service used by the ESB Management Portal and third-party providers.</span></span>  
  
- <span data-ttu-id="d5af2-117"><strong>BizTalk 操作 Web 服务。</strong>基于此 ASMX 的服务公开有关 BizTalk Server 主机、 业务流程、 应用程序和状态，启用用户和应用程序和主机的状态，而不考虑计算机中的位置轻松查询的第三方信息BizTalk Server 组中。</span><span class="sxs-lookup"><span data-stu-id="d5af2-117"><strong>BizTalk Operations Web service.</strong>This ASMX-based service exposes information about BizTalk Server hosts, orchestration, applications, and status, enabling users and third parties to easily query for application and host status, regardless of the location of computer(s) within the BizTalk Server group.</span></span> <span data-ttu-id="d5af2-118">查询可以包括消息状态和流、 状态更改、 当前服务实例和消息的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d5af2-118">Queries can include message status and flow, status changes, current service instances, and message details.</span></span> <span data-ttu-id="d5af2-119">此外可以更新服务接收位置。</span><span class="sxs-lookup"><span data-stu-id="d5af2-119">The service can also update receive locations.</span></span> <span data-ttu-id="d5af2-120">这是供 ESB 管理门户和第三方提供商的基础结构服务。</span><span class="sxs-lookup"><span data-stu-id="d5af2-120">This is a key infrastructure service used by the ESB Management Portal and third-party providers.</span></span>  
  
  <span data-ttu-id="d5af2-121">有关作为的一部分提供的 Web 服务的详细信息[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]，请参阅[使用 BizTalk ESB 工具包 Web 服务](../esb-toolkit/using-the-biztalk-esb-toolkit-web-services.md)。</span><span class="sxs-lookup"><span data-stu-id="d5af2-121">For more information about the Web services provided as part of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], see [Using the BizTalk ESB Toolkit Web Services](../esb-toolkit/using-the-biztalk-esb-toolkit-web-services.md).</span></span>