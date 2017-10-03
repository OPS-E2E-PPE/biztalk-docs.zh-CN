---
title: "ESB 路线的转发器组件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 607cc8a0-4964-4751-baca-c3329983c98b
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c61643423021701186745ab4275520cb14d3ceca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-esb-itinerary-forwarder-component"></a><span data-ttu-id="98f22-102">ESB 路线的转发器组件</span><span class="sxs-lookup"><span data-stu-id="98f22-102">The ESB Itinerary Forwarder Component</span></span>
<span data-ttu-id="98f22-103">一条路线必须按顺序调用多个 Web 服务时使用 ESB 路线转发器组件。</span><span class="sxs-lookup"><span data-stu-id="98f22-103">The ESB Itinerary Forwarder component is used when an itinerary must sequentially invoke multiple Web services.</span></span> <span data-ttu-id="98f22-104">可以使用组件在收到与双向出口响应端关联的管道。</span><span class="sxs-lookup"><span data-stu-id="98f22-104">The component can be used in receive pipelines that are associated with the response side of a two-way off-ramp.</span></span>  
  
## <a name="installation"></a><span data-ttu-id="98f22-105">安装</span><span class="sxs-lookup"><span data-stu-id="98f22-105">Installation</span></span>  
 <span data-ttu-id="98f22-106">自动安装 ESB 核心安装**路线转发器**组件 BizTalk Server 管道组件文件夹中。</span><span class="sxs-lookup"><span data-stu-id="98f22-106">Installing the ESB Core automatically installs the **Itinerary Forwarder** component in the BizTalk Server Pipeline Components folder.</span></span>  
  
## <a name="how-it-works"></a><span data-ttu-id="98f22-107">它是如何工作</span><span class="sxs-lookup"><span data-stu-id="98f22-107">How It Works</span></span>  
 <span data-ttu-id="98f22-108">当 Microsoft BizTalk 接收任何消息通过双向接收端口，如消息发布到消息框数据库，创建一个实例订阅。</span><span class="sxs-lookup"><span data-stu-id="98f22-108">When Microsoft BizTalk receives a message through a two-way receive port as the message is published to the Message Box database, an instance subscription is created.</span></span> <span data-ttu-id="98f22-109">此订阅组成**EpmRRCorrelationToken**升级的属性和**RouteDirectToTP**提升属性。</span><span class="sxs-lookup"><span data-stu-id="98f22-109">This subscription consists of the **EpmRRCorrelationToken** promoted property and a **RouteDirectToTP** promoted property.</span></span> <span data-ttu-id="98f22-110">在订阅服务器 （业务流程或双向发送端口） 返回响应消息时，这些提升的属性与订阅匹配，并通过发送管道的接收端口立即返回响应。</span><span class="sxs-lookup"><span data-stu-id="98f22-110">When the subscriber (orchestration or two-way send port) returns the response message, these promoted properties match the subscription and the response is immediately returned through the send pipeline of the receive port.</span></span>  
  
 <span data-ttu-id="98f22-111">ESB 路线转发器应在响应管道中用于双向，关闭提升关闭负载增加其中调用请求-响应 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="98f22-111">The ESB Itinerary Forwarder should be used in the response pipeline for a two-way off-ramp where the off-ramp is calling a request-response Web service.</span></span> <span data-ttu-id="98f22-112">组件干扰典型 BizTalk 过程通过更改**RouteDirectToTP**提升的属性为 False，从而确保响应将不返回给启动接收端口。</span><span class="sxs-lookup"><span data-stu-id="98f22-112">The component interferes with the typical BizTalk process by changing the **RouteDirectToTP** promoted property to False, thus ensuring that the response will not be returned to the initiating receive port.</span></span> <span data-ttu-id="98f22-113">达到路线的最后一步后， **RouteDirectToTP**属性更改回**True**，因此将结果返回到启动负载增加。</span><span class="sxs-lookup"><span data-stu-id="98f22-113">After the last step in the itinerary is reached, the **RouteDirectToTP** property is changed back to **True**, thus returning the result to the initiating on-ramp.</span></span>  
  
## <a name="using-the-esb-itinerary-forwarder-component"></a><span data-ttu-id="98f22-114">使用 ESB 路线的转发器组件</span><span class="sxs-lookup"><span data-stu-id="98f22-114">Using the ESB Itinerary Forwarder Component</span></span>  
 <span data-ttu-id="98f22-115">将 ESB ItineraryForwarder 组件添加到接收管道，然后使用双向，关闭提升的响应部分使用管道。</span><span class="sxs-lookup"><span data-stu-id="98f22-115">Add the ESB ItineraryForwarder component to a receive pipeline and then use the pipeline with the response portion of a two-way off-ramp.</span></span> <span data-ttu-id="98f22-116">创建一条路线的链接多个 Web 服务，带有或不使用转换路线服务之前或在服务之间。</span><span class="sxs-lookup"><span data-stu-id="98f22-116">Create an itinerary that chains multiple Web services, with or without transformation itinerary services, before or between the services.</span></span> <span data-ttu-id="98f22-117">有关如何使用 ESB 路线转发器组件的示例，请参阅[安装和运行多个 Web 服务示例](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="98f22-117">For an example of how to use the ESB Itinerary Forwarder Component, see the [Installing and Running the Multiple Web Services Sample](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md).</span></span>