---
title: 定义路由和消息转换通过多个业务流程使用路线 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63141b83-798e-40d0-908d-6b7649923e69
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb39d156827dd88d043c86cf3fa27cf82889d9fb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394656"
---
# <a name="defining-routing-and-message-transformation-through-multiple-orchestrations-using-itineraries"></a><span data-ttu-id="0081e-102">定义路由和通过使用路线的多个业务流程的消息转换</span><span class="sxs-lookup"><span data-stu-id="0081e-102">Defining Routing and Message Transformation Through Multiple Orchestrations Using Itineraries</span></span>
<span data-ttu-id="0081e-103">在此用例，提交以进行处理的消息包含描述的服务执行，而其分辨率要求列表的路线 SOAP 标头。</span><span class="sxs-lookup"><span data-stu-id="0081e-103">In this use case, a message submitted for processing contains an itinerary SOAP header that describes the list of services to execute and their resolution requirements.</span></span> <span data-ttu-id="0081e-104">路线指定通过该消息将直接处理周期内的一个或多个 Microsoft BizTalk Server 业务流程。</span><span class="sxs-lookup"><span data-stu-id="0081e-104">The itinerary specifies one or more Microsoft BizTalk Server orchestrations through which the message will pass during the processing cycle.</span></span> <span data-ttu-id="0081e-105">（可选） 路线可能包含用于确定终结点或转换要求消息的动态路由信息。</span><span class="sxs-lookup"><span data-stu-id="0081e-105">Optionally, the itinerary can contain dynamic routing information used to determine endpoints or transformation requirements for the message.</span></span> <span data-ttu-id="0081e-106">图 1 显示了该过程的示意图。</span><span class="sxs-lookup"><span data-stu-id="0081e-106">Figure 1 illustrates a schematic view of the process.</span></span>  
  
 <span data-ttu-id="0081e-107">![定义路由多业务流程](../esb-toolkit/media/ch3-definingroutingmultipleorchestrations.gif "Ch3-DefiningRoutingMultipleOrchestrations")</span><span class="sxs-lookup"><span data-stu-id="0081e-107">![Defining Routing Multiple Orchestrations](../esb-toolkit/media/ch3-definingroutingmultipleorchestrations.gif "Ch3-DefiningRoutingMultipleOrchestrations")</span></span>  
  
 <span data-ttu-id="0081e-108">**图 1**</span><span class="sxs-lookup"><span data-stu-id="0081e-108">**Figure 1**</span></span>  
  
 <span data-ttu-id="0081e-109">**通过多个业务流程使用路线定义路由和消息转换**</span><span class="sxs-lookup"><span data-stu-id="0081e-109">**Defining routing and message transformation through multiple orchestrations using itineraries**</span></span>  
  
 <span data-ttu-id="0081e-110">路线接入点示例随附[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]演示此用例。</span><span class="sxs-lookup"><span data-stu-id="0081e-110">The Itinerary On-Ramp sample included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span> <span data-ttu-id="0081e-111">它演示如何创建包含分辨率、 路由、 路线和服务调用的说明作为一系列定义的路线步骤如何[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]和 BizTalk Server 将处理输入的消息。</span><span class="sxs-lookup"><span data-stu-id="0081e-111">It shows how to create itineraries that contain resolution, routing, and service invocation instructions as a series of itinerary steps that define how the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] and BizTalk Server will process the input message.</span></span> <span data-ttu-id="0081e-112">单向和请求-响应示例包括在内。</span><span class="sxs-lookup"><span data-stu-id="0081e-112">One-way and request-response samples are included.</span></span>  
  
 <span data-ttu-id="0081e-113">有关详细信息，请参阅[安装和运行路线接入点示例](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="0081e-113">For more information, see [Installing and Running the Itinerary On-Ramp Sample](../esb-toolkit/installing-and-running-the-itinerary-on-ramp-sample.md).</span></span>