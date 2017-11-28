---
title: "使用管道组件来缓存请求作出响应一条路线 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: add07ebf-785c-4c53-be69-efd40677a758
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64b6822a4f4ca70e88ee86277e00645982595b47
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-a-pipeline-component-to-cache-an-itinerary-for-solicit-response"></a><span data-ttu-id="2fc14-102">使用管道组件来缓存请求作出响应一条路线</span><span class="sxs-lookup"><span data-stu-id="2fc14-102">Using a Pipeline Component to Cache an Itinerary for Solicit-Response</span></span>
<span data-ttu-id="2fc14-103">通过提交消息[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]路线上负载增加可以通过单向路线或双向 （请求-响应） 路线。</span><span class="sxs-lookup"><span data-stu-id="2fc14-103">Messages submitted through a [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itinerary on-ramp can go through either a one-way itinerary or a two-way (request-response) itinerary.</span></span> <span data-ttu-id="2fc14-104">若要支持请求-响应路线，路线机制必须提供 BizTalk 动态请求-响应发送端口的缓存。</span><span class="sxs-lookup"><span data-stu-id="2fc14-104">To support request-response itineraries, the itinerary mechanism must provide caching for BizTalk dynamic Solicit-Response send ports.</span></span>  
  
 <span data-ttu-id="2fc14-105">ESB 路线缓存管道组件将存储到缓存中的出站消息上下文路线，并将其附加到响应消息中;它将返回发送端口的使用可配置的缓存密钥。</span><span class="sxs-lookup"><span data-stu-id="2fc14-105">The ESB Itinerary Cache pipeline component places the itinerary stored in the outbound message context into the cache and attaches it to the response message; it is returned by the send port using the configurable caching key.</span></span> <span data-ttu-id="2fc14-106">这允许路线的服务处理和执行后续后路线中的当前服务定义的服务。</span><span class="sxs-lookup"><span data-stu-id="2fc14-106">This allows the itinerary service to process and execute subsequent services defined after the current service in the itinerary.</span></span>  
  
 <span data-ttu-id="2fc14-107">默认情况下，ESB 路线缓存管道组件的驻留在 ItineraryReceiveSend BizTalk 管道中，如图 1 中所示。</span><span class="sxs-lookup"><span data-stu-id="2fc14-107">By default, the ESB Itinerary Cache pipeline component resides in the ItineraryReceiveSend BizTalk pipeline, as shown in Figure 1.</span></span> <span data-ttu-id="2fc14-108">此管道应只可用作接收管道请求-响应发送端口。</span><span class="sxs-lookup"><span data-stu-id="2fc14-108">This pipeline should be used only as the receive pipeline for a Solicit-Response send port.</span></span>  
  
 <span data-ttu-id="2fc14-109">![管道组件缓存](../esb-toolkit/media/ch4-pipelinecomponentcache.gif "第四章第 4 PipelineComponentCache")</span><span class="sxs-lookup"><span data-stu-id="2fc14-109">![Pipeline Component Cache](../esb-toolkit/media/ch4-pipelinecomponentcache.gif "Ch4-PipelineComponentCache")</span></span>  
  
 <span data-ttu-id="2fc14-110">**图 1**</span><span class="sxs-lookup"><span data-stu-id="2fc14-110">**Figure 1**</span></span>  
  
 <span data-ttu-id="2fc14-111">**ESB 路线缓存管道组件**</span><span class="sxs-lookup"><span data-stu-id="2fc14-111">**The ESB Itinerary Cache Pipeline component**</span></span>  
  
 <span data-ttu-id="2fc14-112">使用 BizTalk 中的 ESB 路线缓存管道组件接收请求-响应发送端口的管道。</span><span class="sxs-lookup"><span data-stu-id="2fc14-112">Use the ESB Itinerary Cache Pipeline component in a BizTalk receive pipeline for a Solicit-Response send port.</span></span>