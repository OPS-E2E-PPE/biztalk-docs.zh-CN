---
title: 定义路由和消息转换服务调用使用路线 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e6f2448e-a5a7-496c-86d3-47f12e6f1251
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0145bb07e700133be91878f040f5a3db4825db5e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394681"
---
# <a name="defining-routing-and-message-transformation-service-invocations-using-itineraries"></a><span data-ttu-id="84553-102">定义路由和消息转换服务调用使用路线</span><span class="sxs-lookup"><span data-stu-id="84553-102">Defining Routing and Message Transformation Service Invocations Using Itineraries</span></span>
<span data-ttu-id="84553-103">在此用例，提交以进行处理的消息包含描述的服务执行，而其分辨率要求列表的路线 SOAP 标头。</span><span class="sxs-lookup"><span data-stu-id="84553-103">In this use case, a message submitted for processing contains an itinerary SOAP header that describes the list of services to execute and their resolution requirements.</span></span> <span data-ttu-id="84553-104">具体而言，转换和路由服务定义，每个并选择性地要求通过通用描述、 发现和集成 (UDDI)、 业务规则引擎策略、 XML 路径语言 (XPath) 或静态查找解决方法。</span><span class="sxs-lookup"><span data-stu-id="84553-104">Specifically, a transformation and routing service are defined, each optionally requiring resolution through a Universal Description, Discovery, and Integration (UDDI), Business Rules Engine Policy, XML Path Language (XPath), or STATIC lookup.</span></span> <span data-ttu-id="84553-105">可以通过在发布消息时将其他服务添加到路线扩展此用例。</span><span class="sxs-lookup"><span data-stu-id="84553-105">This use case can be extended by adding other services to the itinerary at the time of message publication.</span></span>  
  
 <span data-ttu-id="84553-106">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]提供两种类型的路线接入： 支持单向通信和支持请求-响应方案。</span><span class="sxs-lookup"><span data-stu-id="84553-106">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] provides two types of itinerary on-ramps: those that support one-way communication and those that support request-response scenarios.</span></span> <span data-ttu-id="84553-107">动态解析机制信息可用于在路线中查找终结点或动态绑定到终结点，因为没有任何要求的 Microsoft BizTalk Server 以包含特定的终结点路由的详细信息。</span><span class="sxs-lookup"><span data-stu-id="84553-107">Because the dynamic resolution mechanism can use information in the itinerary to look up endpoints or bind dynamically to endpoints, there is no requirement for Microsoft BizTalk Server to contain specific endpoint routing details.</span></span> <span data-ttu-id="84553-108">图 1 显示了该过程的示意图。</span><span class="sxs-lookup"><span data-stu-id="84553-108">Figure 1 illustrates a schematic view of the process.</span></span>  
  
 <span data-ttu-id="84553-109">![定义路由服务调用](../esb-toolkit/media/ch3-definingroutingserviceinvocation.gif "Ch3-DefiningRoutingServiceInvocation")</span><span class="sxs-lookup"><span data-stu-id="84553-109">![Defining Routing service Invocation](../esb-toolkit/media/ch3-definingroutingserviceinvocation.gif "Ch3-DefiningRoutingServiceInvocation")</span></span>  
  
 <span data-ttu-id="84553-110">**图 1**</span><span class="sxs-lookup"><span data-stu-id="84553-110">**Figure 1**</span></span>  
  
 <span data-ttu-id="84553-111">**定义路由和消息转换服务调用使用路线**</span><span class="sxs-lookup"><span data-stu-id="84553-111">**Defining routing and message transformation service invocations using itineraries**</span></span>  
  
 <span data-ttu-id="84553-112">路线接入点示例随附[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]演示此用例。</span><span class="sxs-lookup"><span data-stu-id="84553-112">The Itinerary On-Ramp sample included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span> <span data-ttu-id="84553-113">它演示如何创建包含分辨率、 路由、 路线和服务调用的说明作为一系列定义的路线步骤如何[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]和 BizTalk Server 将处理该消息使用发布-订阅的功能BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="84553-113">It shows how to create itineraries that contain resolution, routing, and service invocation instructions as a series of itinerary steps that define how the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] and BizTalk Server will process the message using the publish-subscribe functionality of BizTalk Server.</span></span> <span data-ttu-id="84553-114">单向和请求-响应示例包括在内。</span><span class="sxs-lookup"><span data-stu-id="84553-114">One-way and request-response samples are included.</span></span>  
  
 <span data-ttu-id="84553-115">有关详细信息，请参阅[安装和运行路线接入点示例](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="84553-115">For more information, see [Installing and Running the Itinerary On-Ramp Sample](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md).</span></span>