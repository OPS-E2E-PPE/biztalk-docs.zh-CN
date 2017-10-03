---
title: "如何多个 Web 服务的示例工作原理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 16680ca7-16cc-47df-8c39-a3311d468a46
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b3d9faf350654be69015ea940b6b4f034d4de74
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-the-multiple-web-services-sample-works"></a><span data-ttu-id="3f179-102">多个 Web 服务工作原理的示例</span><span class="sxs-lookup"><span data-stu-id="3f179-102">How the Multiple Web Services Sample Works</span></span>
<span data-ttu-id="3f179-103">多个 Web 服务示例使用两个单独的方法调用中序列的多个 Web 服务，同时仍能够返回到原始调用方的正确的结果。</span><span class="sxs-lookup"><span data-stu-id="3f179-103">The Multiple Web Services sample uses two separate techniques to call multiple Web services in serial while still being able to return a proper result to the original caller.</span></span> <span data-ttu-id="3f179-104">一种方法在响应管道中使用自定义管道组件和其他方法使用自定义双向路由基于业务流程的路线服务的关闭负载增加调用需要完成对 Web 请求/响应呼叫时绕过服务。</span><span class="sxs-lookup"><span data-stu-id="3f179-104">One method uses a custom pipeline component in the response pipeline, and the other method uses a custom two-way routing orchestration-based itinerary service that bypasses the requirement of an off-ramp invocation to complete a request/response call to a Web service.</span></span>  
  
 <span data-ttu-id="3f179-105">自定义管道组件方法使用转发器管道组件。</span><span class="sxs-lookup"><span data-stu-id="3f179-105">The custom pipeline component method uses the Forwarder Pipeline component.</span></span> <span data-ttu-id="3f179-106">此组件有条件地提升属性以防止 Microsoft BizTalk 回上负载增加的发送管道路由消息，直到所有路线的服务进行处理。</span><span class="sxs-lookup"><span data-stu-id="3f179-106">This component conditionally promotes properties to keep Microsoft BizTalk from routing the message back to the send pipeline of the on-ramp until all the itinerary services are processed.</span></span>  
  
 <span data-ttu-id="3f179-107">自定义的基于业务流程的服务方法使用包含在 ESB TwoWayRouting 业务流程。在 \Source\Samples\MultipleWebSerivces\Source\ESB MultipleWebServices.Orchestrations 项目。MultipleWebServices.Orchestrations 文件夹。</span><span class="sxs-lookup"><span data-stu-id="3f179-107">The custom orchestration-based service method uses the TwoWayRouting orchestration contained in the ESB.MultipleWebServices.Orchestrations project in the \Source\Samples\MultipleWebSerivces\Source\ESB.MultipleWebServices.Orchestrations folder.</span></span> <span data-ttu-id="3f179-108">此服务处理一个关联的冲突解决程序来确定双向的 Web 服务的终结点地址。</span><span class="sxs-lookup"><span data-stu-id="3f179-108">This service processes an associated resolver to determine the endpoint address of a two-way Web service.</span></span> <span data-ttu-id="3f179-109">然后，配置名为 RoutingPort 若要将消息发送到 Web 服务并将结果返回给业务流程动态 Solict 响应发送端口。</span><span class="sxs-lookup"><span data-stu-id="3f179-109">It then configures a Dynamic Solict-Response Send Port named RoutingPort to send the message to the Web service and return the result to the orchestration.</span></span> <span data-ttu-id="3f179-110">然后，业务流程提升路线，并将生成消息返回到 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="3f179-110">The orchestration then advances the itinerary and returns the resulting message to the MessageBox.</span></span>  
  
 <span data-ttu-id="3f179-111">示例随附路线使用一个或这两种方法，以确保保持以下路线的消息流。</span><span class="sxs-lookup"><span data-stu-id="3f179-111">The itineraries included with the sample use one or both of these methods to ensure message flow following the itinerary is maintained.</span></span> <span data-ttu-id="3f179-112">有关详细信息，请参阅[示例多个 Web 服务路线](../esb-toolkit/the-sample-multiple-web-services-itineraries.md)。</span><span class="sxs-lookup"><span data-stu-id="3f179-112">For more information, see [The Sample Multiple Web Services Itineraries](../esb-toolkit/the-sample-multiple-web-services-itineraries.md).</span></span>