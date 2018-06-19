---
title: 上渐变和关闭渐变 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c0cce5d2-f16f-4bda-94ac-20c4f457cfc7
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0aafa69315dba07219ad8510c77cdc9de2d4bce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294557"
---
# <a name="on-ramps-and-off-ramps"></a><span data-ttu-id="7763d-102">上渐变和关闭渐变</span><span class="sxs-lookup"><span data-stu-id="7763d-102">On-Ramps and Off-Ramps</span></span>
<span data-ttu-id="7763d-103">在环境中其中[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]是部署，BizTalk 接收位置负责接收 ESB 要发送的消息被称为"入口。"</span><span class="sxs-lookup"><span data-stu-id="7763d-103">In an environment where [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] is deployed, a BizTalk receive location responsible for receiving ESB-destined messages is referred to as an "on-ramp."</span></span> <span data-ttu-id="7763d-104">若要配置标准的 BizTalk 接收位置到 ESB 入口，将接收位置与作为该工具包的一部分提供的管道之一相关联，然后正确配置以确定或阅读有关路线该管道组件入站的消息，具体取决于你的方案。</span><span class="sxs-lookup"><span data-stu-id="7763d-104">To configure a standard BizTalk receive location to an ESB on-ramp, associate the receive location with one of the pipelines provided as part of the toolkit, and then correctly configure the components of that pipeline to determine or read the itinerary for the inbound message, depending on your scenario.</span></span>  
  
 <span data-ttu-id="7763d-105">"关闭负载增加"ESB 对应于 BizTalk 动态发送端口。</span><span class="sxs-lookup"><span data-stu-id="7763d-105">An ESB "off-ramp" corresponds to a BizTalk dynamic send port.</span></span> <span data-ttu-id="7763d-106">处理一条路线时，值将被提升到使用系统 Properties.xsd 架构的关联消息的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="7763d-106">As an itinerary is being processed, values are promoted to the context properties of the associated message using the System-Properties.xsd schema.</span></span> <span data-ttu-id="7763d-107">BizTalk 发布-订阅机制使用这些提升属性，以将路由任何消息通过动态发送端口 （关闭负载增加） 完成消息传递。</span><span class="sxs-lookup"><span data-stu-id="7763d-107">The BizTalk publish-subscribe mechanism uses these promoted properties to route a message through a dynamic send port (off-ramp) to complete a message delivery.</span></span>  
  
 <span data-ttu-id="7763d-108">下表列出了上-渐变提供的[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7763d-108">The following table lists the on-ramps that are provided by the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span>  
  
|<span data-ttu-id="7763d-109">Name</span><span class="sxs-lookup"><span data-stu-id="7763d-109">Name</span></span>|<span data-ttu-id="7763d-110">消息交换模式</span><span class="sxs-lookup"><span data-stu-id="7763d-110">Message exchange pattern</span></span>|<span data-ttu-id="7763d-111">**Description**</span><span class="sxs-lookup"><span data-stu-id="7763d-111">**Description**</span></span>|  
|----------|------------------------------|---------------------|  
|<span data-ttu-id="7763d-112">ESB。ItineraryServices</span><span class="sxs-lookup"><span data-stu-id="7763d-112">ESB.ItineraryServices</span></span>|<span data-ttu-id="7763d-113">单向</span><span class="sxs-lookup"><span data-stu-id="7763d-113">One-Way</span></span>|<span data-ttu-id="7763d-114">ASMX 入口;SOAP 标头中需要 ESB 路线内容。</span><span class="sxs-lookup"><span data-stu-id="7763d-114">ASMX on-ramp; expects ESB itinerary content in SOAP header.</span></span>|  
|<span data-ttu-id="7763d-115">ESB。ItineraryServices.Response</span><span class="sxs-lookup"><span data-stu-id="7763d-115">ESB.ItineraryServices.Response</span></span>|<span data-ttu-id="7763d-116">请求-响应</span><span class="sxs-lookup"><span data-stu-id="7763d-116">Request-Response</span></span>|<span data-ttu-id="7763d-117">ASMX 入口;SOAP 标头中需要 ESB 路线内容。</span><span class="sxs-lookup"><span data-stu-id="7763d-117">ASMX on-ramp; expects ESB itinerary content in SOAP header.</span></span>|  
|<span data-ttu-id="7763d-118">ESB。ItineraryServices.WCF</span><span class="sxs-lookup"><span data-stu-id="7763d-118">ESB.ItineraryServices.WCF</span></span>|<span data-ttu-id="7763d-119">单向</span><span class="sxs-lookup"><span data-stu-id="7763d-119">One-Way</span></span>|<span data-ttu-id="7763d-120">Windows Communication Foundation (WCF) 上的负载增加;SOAP 标头中应 ESB 路线引用。</span><span class="sxs-lookup"><span data-stu-id="7763d-120">Windows Communication Foundation (WCF) on-ramp; expects ESB itinerary reference in SOAP header.</span></span>|  
|<span data-ttu-id="7763d-121">ESB。ItineraryServices.Response.WCF</span><span class="sxs-lookup"><span data-stu-id="7763d-121">ESB.ItineraryServices.Response.WCF</span></span>|<span data-ttu-id="7763d-122">请求-响应</span><span class="sxs-lookup"><span data-stu-id="7763d-122">Request-Response</span></span>|<span data-ttu-id="7763d-123">WCF 入口;SOAP 标头中应 ESB 路线引用。</span><span class="sxs-lookup"><span data-stu-id="7763d-123">WCF on-ramp; expects ESB itinerary reference in SOAP header.</span></span>|  
|<span data-ttu-id="7763d-124">ESB。ItineraryServices.Generic.WCF</span><span class="sxs-lookup"><span data-stu-id="7763d-124">ESB.ItineraryServices.Generic.WCF</span></span>|<span data-ttu-id="7763d-125">单向</span><span class="sxs-lookup"><span data-stu-id="7763d-125">One-Way</span></span>|<span data-ttu-id="7763d-126">WCF 入口;需要请求消息仅供参考。</span><span class="sxs-lookup"><span data-stu-id="7763d-126">WCF on-ramp; expects request message only.</span></span>|  
|<span data-ttu-id="7763d-127">ESB。ItineraryServices.Generic.Response.WCF</span><span class="sxs-lookup"><span data-stu-id="7763d-127">ESB.ItineraryServices.Generic.Response.WCF</span></span>|<span data-ttu-id="7763d-128">请求-响应</span><span class="sxs-lookup"><span data-stu-id="7763d-128">Request-Response</span></span>|<span data-ttu-id="7763d-129">WCF 入口;需要请求消息仅供参考。</span><span class="sxs-lookup"><span data-stu-id="7763d-129">WCF on-ramp; expects request message only.</span></span>|  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]<span data-ttu-id="7763d-130">上的渐变不 ASMX 应配置为选择 ESB 路线。</span><span class="sxs-lookup"><span data-stu-id="7763d-130"> on-ramps that are not ASMX should be configured to select ESB itineraries.</span></span> <span data-ttu-id="7763d-131">有关如何选择 ESB 路线的详细信息，请参阅[使用管道组件来选择现有路线](../esb-toolkit/using-a-pipeline-component-to-select-an-existing-itinerary.md)。</span><span class="sxs-lookup"><span data-stu-id="7763d-131">For more information about how to select an ESB itinerary, see [Using a Pipeline Component to Select an Existing Itinerary](../esb-toolkit/using-a-pipeline-component-to-select-an-existing-itinerary.md).</span></span>