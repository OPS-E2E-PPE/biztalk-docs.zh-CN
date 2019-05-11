---
title: 使用管道组件来缓存要求-响应路线 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: add07ebf-785c-4c53-be69-efd40677a758
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ddb3f639286ba29e28230b53b9a8a26a8304ea1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396506"
---
# <a name="using-a-pipeline-component-to-cache-an-itinerary-for-solicit-response"></a><span data-ttu-id="f0db8-102">使用管道组件来缓存要求-响应路线</span><span class="sxs-lookup"><span data-stu-id="f0db8-102">Using a Pipeline Component to Cache an Itinerary for Solicit-Response</span></span>
<span data-ttu-id="f0db8-103">通过提交消息[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]路线接入点即可完成单向路线或双向 （请求-响应） 路线。</span><span class="sxs-lookup"><span data-stu-id="f0db8-103">Messages submitted through a [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itinerary on-ramp can go through either a one-way itinerary or a two-way (request-response) itinerary.</span></span> <span data-ttu-id="f0db8-104">若要支持请求-响应路线，路线机制必须提供 BizTalk 动态要求响应发送端口的缓存。</span><span class="sxs-lookup"><span data-stu-id="f0db8-104">To support request-response itineraries, the itinerary mechanism must provide caching for BizTalk dynamic Solicit-Response send ports.</span></span>  
  
 <span data-ttu-id="f0db8-105">ESB 路线缓存管道组件将放入缓存中存储出站消息上下文中路线，并将其附加到响应消息中;使用可配置的缓存密钥的发送端口返回。</span><span class="sxs-lookup"><span data-stu-id="f0db8-105">The ESB Itinerary Cache pipeline component places the itinerary stored in the outbound message context into the cache and attaches it to the response message; it is returned by the send port using the configurable caching key.</span></span> <span data-ttu-id="f0db8-106">这样，路线服务来处理和执行后路线中的当前服务定义的后续服务。</span><span class="sxs-lookup"><span data-stu-id="f0db8-106">This allows the itinerary service to process and execute subsequent services defined after the current service in the itinerary.</span></span>  
  
 <span data-ttu-id="f0db8-107">默认情况下，ESB 路线缓存管道组件驻留在 ItineraryReceiveSend BizTalk 管道中，如图 1 中所示。</span><span class="sxs-lookup"><span data-stu-id="f0db8-107">By default, the ESB Itinerary Cache pipeline component resides in the ItineraryReceiveSend BizTalk pipeline, as shown in Figure 1.</span></span> <span data-ttu-id="f0db8-108">此管道应使用仅作为接收管道中，对于要求-响应发送端口中。</span><span class="sxs-lookup"><span data-stu-id="f0db8-108">This pipeline should be used only as the receive pipeline for a Solicit-Response send port.</span></span>  
  
 <span data-ttu-id="f0db8-109">![管道组件缓存](../esb-toolkit/media/ch4-pipelinecomponentcache.gif "Ch4-PipelineComponentCache")</span><span class="sxs-lookup"><span data-stu-id="f0db8-109">![Pipeline Component Cache](../esb-toolkit/media/ch4-pipelinecomponentcache.gif "Ch4-PipelineComponentCache")</span></span>  
  
 <span data-ttu-id="f0db8-110">**图 1**</span><span class="sxs-lookup"><span data-stu-id="f0db8-110">**Figure 1**</span></span>  
  
 <span data-ttu-id="f0db8-111">**ESB 路线缓存管道组件**</span><span class="sxs-lookup"><span data-stu-id="f0db8-111">**The ESB Itinerary Cache Pipeline component**</span></span>  
  
 <span data-ttu-id="f0db8-112">使用 ESB 路线缓存管道组件在 BizTalk 接收管道要求响应发送端口。</span><span class="sxs-lookup"><span data-stu-id="f0db8-112">Use the ESB Itinerary Cache Pipeline component in a BizTalk receive pipeline for a Solicit-Response send port.</span></span>