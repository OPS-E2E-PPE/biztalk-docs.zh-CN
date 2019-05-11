---
title: 接入和接出点 |Microsoft Docs
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
ms.openlocfilehash: 528a8a42319fce4dbfc6507ec4d0658092e44963
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400055"
---
# <a name="on-ramps-and-off-ramps"></a><span data-ttu-id="1e71c-102">接入和接出点</span><span class="sxs-lookup"><span data-stu-id="1e71c-102">On-Ramps and Off-Ramps</span></span>
<span data-ttu-id="1e71c-103">在环境中其中[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]是部署，BizTalk 接收位置负责接收发往 ESB 的消息被称为"好帮手。"</span><span class="sxs-lookup"><span data-stu-id="1e71c-103">In an environment where [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] is deployed, a BizTalk receive location responsible for receiving ESB-destined messages is referred to as an "on-ramp."</span></span> <span data-ttu-id="1e71c-104">若要配置 ESB 接入点的标准 BizTalk 接收位置，将接收位置与作为该工具包的一部分提供的管道之一相关联，然后正确配置该管道中，以确定或阅读有关路线的组件入站的消息，具体取决于你的方案。</span><span class="sxs-lookup"><span data-stu-id="1e71c-104">To configure a standard BizTalk receive location to an ESB on-ramp, associate the receive location with one of the pipelines provided as part of the toolkit, and then correctly configure the components of that pipeline to determine or read the itinerary for the inbound message, depending on your scenario.</span></span>  
  
 <span data-ttu-id="1e71c-105">ESB"关闭入口"对应于 BizTalk 动态发送端口。</span><span class="sxs-lookup"><span data-stu-id="1e71c-105">An ESB "off-ramp" corresponds to a BizTalk dynamic send port.</span></span> <span data-ttu-id="1e71c-106">处理一条路线时，值将被提升到使用系统 Properties.xsd 架构相关联的消息的上下文属性。</span><span class="sxs-lookup"><span data-stu-id="1e71c-106">As an itinerary is being processed, values are promoted to the context properties of the associated message using the System-Properties.xsd schema.</span></span> <span data-ttu-id="1e71c-107">BizTalk 的发布-订阅机制使用这些升级属性，以通过动态将消息路由发送端口 （关闭接入点） 以完成消息传递。</span><span class="sxs-lookup"><span data-stu-id="1e71c-107">The BizTalk publish-subscribe mechanism uses these promoted properties to route a message through a dynamic send port (off-ramp) to complete a message delivery.</span></span>  
  
 <span data-ttu-id="1e71c-108">下表列出了接入所提供的[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1e71c-108">The following table lists the on-ramps that are provided by the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span>  
  
|<span data-ttu-id="1e71c-109">“属性”</span><span class="sxs-lookup"><span data-stu-id="1e71c-109">Name</span></span>|<span data-ttu-id="1e71c-110">消息交换模式</span><span class="sxs-lookup"><span data-stu-id="1e71c-110">Message exchange pattern</span></span>|<span data-ttu-id="1e71c-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="1e71c-111">**Description**</span></span>|  
|----------|------------------------------|---------------------|  
|<span data-ttu-id="1e71c-112">ESB.ItineraryServices</span><span class="sxs-lookup"><span data-stu-id="1e71c-112">ESB.ItineraryServices</span></span>|<span data-ttu-id="1e71c-113">单向</span><span class="sxs-lookup"><span data-stu-id="1e71c-113">One-Way</span></span>|<span data-ttu-id="1e71c-114">ASMX 接入点;ESB 路线内容需要 SOAP 标头。</span><span class="sxs-lookup"><span data-stu-id="1e71c-114">ASMX on-ramp; expects ESB itinerary content in SOAP header.</span></span>|  
|<span data-ttu-id="1e71c-115">ESB.ItineraryServices.Response</span><span class="sxs-lookup"><span data-stu-id="1e71c-115">ESB.ItineraryServices.Response</span></span>|<span data-ttu-id="1e71c-116">请求-响应</span><span class="sxs-lookup"><span data-stu-id="1e71c-116">Request-Response</span></span>|<span data-ttu-id="1e71c-117">ASMX 接入点;ESB 路线内容需要 SOAP 标头。</span><span class="sxs-lookup"><span data-stu-id="1e71c-117">ASMX on-ramp; expects ESB itinerary content in SOAP header.</span></span>|  
|<span data-ttu-id="1e71c-118">ESB.ItineraryServices.WCF</span><span class="sxs-lookup"><span data-stu-id="1e71c-118">ESB.ItineraryServices.WCF</span></span>|<span data-ttu-id="1e71c-119">单向</span><span class="sxs-lookup"><span data-stu-id="1e71c-119">One-Way</span></span>|<span data-ttu-id="1e71c-120">Windows Communication Foundation (WCF) 的途径;SOAP 标头中要求 ESB 路线引用。</span><span class="sxs-lookup"><span data-stu-id="1e71c-120">Windows Communication Foundation (WCF) on-ramp; expects ESB itinerary reference in SOAP header.</span></span>|  
|<span data-ttu-id="1e71c-121">ESB.ItineraryServices.Response.WCF</span><span class="sxs-lookup"><span data-stu-id="1e71c-121">ESB.ItineraryServices.Response.WCF</span></span>|<span data-ttu-id="1e71c-122">请求-响应</span><span class="sxs-lookup"><span data-stu-id="1e71c-122">Request-Response</span></span>|<span data-ttu-id="1e71c-123">WCF 的途径;SOAP 标头中要求 ESB 路线引用。</span><span class="sxs-lookup"><span data-stu-id="1e71c-123">WCF on-ramp; expects ESB itinerary reference in SOAP header.</span></span>|  
|<span data-ttu-id="1e71c-124">ESB.ItineraryServices.Generic.WCF</span><span class="sxs-lookup"><span data-stu-id="1e71c-124">ESB.ItineraryServices.Generic.WCF</span></span>|<span data-ttu-id="1e71c-125">单向</span><span class="sxs-lookup"><span data-stu-id="1e71c-125">One-Way</span></span>|<span data-ttu-id="1e71c-126">WCF 的途径;预期请求消息仅供参考。</span><span class="sxs-lookup"><span data-stu-id="1e71c-126">WCF on-ramp; expects request message only.</span></span>|  
|<span data-ttu-id="1e71c-127">ESB.ItineraryServices.Generic.Response.WCF</span><span class="sxs-lookup"><span data-stu-id="1e71c-127">ESB.ItineraryServices.Generic.Response.WCF</span></span>|<span data-ttu-id="1e71c-128">请求-响应</span><span class="sxs-lookup"><span data-stu-id="1e71c-128">Request-Response</span></span>|<span data-ttu-id="1e71c-129">WCF 的途径;预期请求消息仅供参考。</span><span class="sxs-lookup"><span data-stu-id="1e71c-129">WCF on-ramp; expects request message only.</span></span>|  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] <span data-ttu-id="1e71c-130">接入不应配置 ASMX 选择 ESB 行程。</span><span class="sxs-lookup"><span data-stu-id="1e71c-130">on-ramps that are not ASMX should be configured to select ESB itineraries.</span></span> <span data-ttu-id="1e71c-131">有关如何选择 ESB 路线的详细信息，请参阅[使用管道组件来选择现有路线](../esb-toolkit/using-a-pipeline-component-to-select-an-existing-itinerary.md)。</span><span class="sxs-lookup"><span data-stu-id="1e71c-131">For more information about how to select an ESB itinerary, see [Using a Pipeline Component to Select an Existing Itinerary](../esb-toolkit/using-a-pipeline-component-to-select-an-existing-itinerary.md).</span></span>