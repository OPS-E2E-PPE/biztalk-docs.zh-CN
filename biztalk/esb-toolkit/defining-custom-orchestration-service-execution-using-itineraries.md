---
title: 定义自定义业务流程服务执行使用路线 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6089169d-2fa1-4f81-afe1-db9d90a10382
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9336969db2c90168bf7c398276205043b06504ce
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007427"
---
# <a name="defining-custom-orchestration-service-execution-using-itineraries"></a><span data-ttu-id="962ad-102">定义自定义业务流程服务执行使用路线</span><span class="sxs-lookup"><span data-stu-id="962ad-102">Defining Custom Orchestration Service Execution Using Itineraries</span></span>
<span data-ttu-id="962ad-103">在此用例，以进行处理的消息包含说明的服务执行，而其解析要求列表路线 SOAP 标头。</span><span class="sxs-lookup"><span data-stu-id="962ad-103">In this use case, a message submitted for processing contains an itinerary SOAP header that describes the list of services to execute and their resolution requirements.</span></span> <span data-ttu-id="962ad-104">路线指定一个或多个自定义业务流程或消息将传递在处理周期内的进程。</span><span class="sxs-lookup"><span data-stu-id="962ad-104">The itinerary specifies one or more custom orchestrations or processes through which the message will pass during the processing cycle.</span></span> <span data-ttu-id="962ad-105">自定义业务流程具有完全控制路线及其消息上下文中公开的其他自定义属性。</span><span class="sxs-lookup"><span data-stu-id="962ad-105">Custom orchestrations have full control of the itinerary and other custom properties exposed in the message context.</span></span> <span data-ttu-id="962ad-106">（可选） 路线可以包含确定转换要求和消息的终结点的动态解析信息。</span><span class="sxs-lookup"><span data-stu-id="962ad-106">Optionally, the itinerary can contain dynamic resolution information that determines transformation requirements and endpoints for the message.</span></span> <span data-ttu-id="962ad-107">图 1 说明的过程的示意图。</span><span class="sxs-lookup"><span data-stu-id="962ad-107">Figure 1 illustrates a schematic view of the process.</span></span>  
  
 <span data-ttu-id="962ad-108">![定义自定义业务流程](../esb-toolkit/media/ch3-definingcustomorchestration.gif "Ch3 DefiningCustomOrchestration")</span><span class="sxs-lookup"><span data-stu-id="962ad-108">![Defining Custom Orchestration](../esb-toolkit/media/ch3-definingcustomorchestration.gif "Ch3-DefiningCustomOrchestration")</span></span>  
  
 <span data-ttu-id="962ad-109">**图 1**</span><span class="sxs-lookup"><span data-stu-id="962ad-109">**Figure 1**</span></span>  
  
 <span data-ttu-id="962ad-110">**定义自定义业务流程服务执行使用路线**</span><span class="sxs-lookup"><span data-stu-id="962ad-110">**Defining custom orchestration service execution using itineraries**</span></span>  
  
 <span data-ttu-id="962ad-111">附带路线入口示例[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]演示此用例。</span><span class="sxs-lookup"><span data-stu-id="962ad-111">The Itinerary On-Ramp sample included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span> <span data-ttu-id="962ad-112">它演示如何创建包含解决方法、 路由和服务调用说明作为一系列路线定义 ESB 和 BizTalk Server 将如何处理输入的消息的步骤的路线。</span><span class="sxs-lookup"><span data-stu-id="962ad-112">It shows how to create itineraries that contain resolution, routing, and service invocation instructions as a series of itinerary steps that define how the ESB and BizTalk Server will process the input message.</span></span> <span data-ttu-id="962ad-113">单向请求响应示例中还包括。</span><span class="sxs-lookup"><span data-stu-id="962ad-113">One-way and request-response samples are included.</span></span>  
  
 <span data-ttu-id="962ad-114">有关详细信息，请参阅[安装和运行路线上负载增加示例](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="962ad-114">For more information, see [Installing and Running the Itinerary On-Ramp Sample](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md).</span></span>