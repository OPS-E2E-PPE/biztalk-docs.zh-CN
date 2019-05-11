---
title: ESB 路线转发器组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 607cc8a0-4964-4751-baca-c3329983c98b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e23368b1d74a2842659332d2c545b93e24386455
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399791"
---
# <a name="the-esb-itinerary-forwarder-component"></a><span data-ttu-id="b268e-102">ESB 路线转发器组件</span><span class="sxs-lookup"><span data-stu-id="b268e-102">The ESB Itinerary Forwarder Component</span></span>
<span data-ttu-id="b268e-103">路线必须按顺序调用多个 Web 服务时，使用 ESB 路线转发器组件。</span><span class="sxs-lookup"><span data-stu-id="b268e-103">The ESB Itinerary Forwarder component is used when an itinerary must sequentially invoke multiple Web services.</span></span> <span data-ttu-id="b268e-104">可以使用该组件在接收管道与双向关闭接入点在响应端相关联。</span><span class="sxs-lookup"><span data-stu-id="b268e-104">The component can be used in receive pipelines that are associated with the response side of a two-way off-ramp.</span></span>  
  
## <a name="installation"></a><span data-ttu-id="b268e-105">安装</span><span class="sxs-lookup"><span data-stu-id="b268e-105">Installation</span></span>  
 <span data-ttu-id="b268e-106">自动安装 ESB 核心安装**路线转发器**组件的 BizTalk Server 管道组件文件夹中。</span><span class="sxs-lookup"><span data-stu-id="b268e-106">Installing the ESB Core automatically installs the **Itinerary Forwarder** component in the BizTalk Server Pipeline Components folder.</span></span>  
  
## <a name="how-it-works"></a><span data-ttu-id="b268e-107">其工作原理</span><span class="sxs-lookup"><span data-stu-id="b268e-107">How It Works</span></span>  
 <span data-ttu-id="b268e-108">当 Microsoft BizTalk 收到任何消息通过双向接收端口将消息发布到 Messagebox 数据库，创建实例订阅。</span><span class="sxs-lookup"><span data-stu-id="b268e-108">When Microsoft BizTalk receives a message through a two-way receive port as the message is published to the Message Box database, an instance subscription is created.</span></span> <span data-ttu-id="b268e-109">此订阅都包含**EpmRRCorrelationToken**升级的属性和一个**RouteDirectToTP**升级的属性。</span><span class="sxs-lookup"><span data-stu-id="b268e-109">This subscription consists of the **EpmRRCorrelationToken** promoted property and a **RouteDirectToTP** promoted property.</span></span> <span data-ttu-id="b268e-110">当订阅服务器 （业务流程或双向发送端口） 返回的响应消息时，这些升级的属性与订阅匹配，并通过接收端口的发送管道立即返回响应。</span><span class="sxs-lookup"><span data-stu-id="b268e-110">When the subscriber (orchestration or two-way send port) returns the response message, these promoted properties match the subscription and the response is immediately returned through the send pipeline of the receive port.</span></span>  
  
 <span data-ttu-id="b268e-111">ESB 路线转发器应在响应管道中为双向，关闭 ramp 其中关闭负载增加正在调用的请求-响应 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="b268e-111">The ESB Itinerary Forwarder should be used in the response pipeline for a two-way off-ramp where the off-ramp is calling a request-response Web service.</span></span> <span data-ttu-id="b268e-112">该组件会影响通过更改典型 BizTalk 进程**RouteDirectToTP**升级的属性为 False，因此可确保对发起将不返回响应接收端口。</span><span class="sxs-lookup"><span data-stu-id="b268e-112">The component interferes with the typical BizTalk process by changing the **RouteDirectToTP** promoted property to False, thus ensuring that the response will not be returned to the initiating receive port.</span></span> <span data-ttu-id="b268e-113">达到路线的最后一步后， **RouteDirectToTP**属性更改回**True**，因此将结果返回到起始负载增加。</span><span class="sxs-lookup"><span data-stu-id="b268e-113">After the last step in the itinerary is reached, the **RouteDirectToTP** property is changed back to **True**, thus returning the result to the initiating on-ramp.</span></span>  
  
## <a name="using-the-esb-itinerary-forwarder-component"></a><span data-ttu-id="b268e-114">使用 ESB 路线转发器组件</span><span class="sxs-lookup"><span data-stu-id="b268e-114">Using the ESB Itinerary Forwarder Component</span></span>  
 <span data-ttu-id="b268e-115">将 ESB ItineraryForwarder 组件添加到接收管道，然后使用双向关闭接入点的响应部分使用管道。</span><span class="sxs-lookup"><span data-stu-id="b268e-115">Add the ESB ItineraryForwarder component to a receive pipeline and then use the pipeline with the response portion of a two-way off-ramp.</span></span> <span data-ttu-id="b268e-116">创建路线的链接多个 Web 服务，带有或不使用转换路线服务之前或在服务之间。</span><span class="sxs-lookup"><span data-stu-id="b268e-116">Create an itinerary that chains multiple Web services, with or without transformation itinerary services, before or between the services.</span></span> <span data-ttu-id="b268e-117">有关如何使用 ESB 路线转发器组件的示例，请参阅[安装和运行多个 Web 服务示例](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="b268e-117">For an example of how to use the ESB Itinerary Forwarder Component, see the [Installing and Running the Multiple Web Services Sample](../esb-toolkit/installing-and-running-the-multiple-web-services-sample.md).</span></span>