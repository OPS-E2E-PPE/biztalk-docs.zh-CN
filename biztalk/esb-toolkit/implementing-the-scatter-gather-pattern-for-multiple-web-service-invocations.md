---
title: "对多个 Web 服务调用实施散播-聚集模式 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 912512a4-9649-40df-bb82-b8f4b85c8ca6
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03fb129d23b0884fdca518dca574be64d7672c6c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="implementing-the-scatter-gather-pattern-for-multiple-web-service-invocations"></a><span data-ttu-id="cb415-102">对多个 Web 服务调用实施散播-聚集模式</span><span class="sxs-lookup"><span data-stu-id="cb415-102">Implementing the Scatter-Gather Pattern for Multiple Web Service Invocations</span></span>
<span data-ttu-id="cb415-103">在此用例，一条消息包含指定多个外部服务的路线服务步骤[!INCLUDE[prague](../includes/prague-md.md)]应访问。</span><span class="sxs-lookup"><span data-stu-id="cb415-103">In this use case, a message contains an itinerary service step that specifies more than one external service that [!INCLUDE[prague](../includes/prague-md.md)] should access.</span></span> <span data-ttu-id="cb415-104">它使用动态的解决方法来确定服务位置和终结点和任何可选的 BizTalk 服务图对于转换返回的数据。</span><span class="sxs-lookup"><span data-stu-id="cb415-104">It uses dynamic resolution to determine service locations and endpoints and any optional BizTalk Service maps for transforming the returned data.</span></span> <span data-ttu-id="cb415-105">实现此服务业务流程执行转换和调用，并且所有服务调用以异步方式都发生。</span><span class="sxs-lookup"><span data-stu-id="cb415-105">The orchestration implementing this service performs the transformation and invocations, and all service invocations occur asynchronously.</span></span> <span data-ttu-id="cb415-106">所有服务调用都完成后，路线服务将响应聚合为单个响应消息，并将消息发送到客户端通过动态分配的终结点。</span><span class="sxs-lookup"><span data-stu-id="cb415-106">After all service invocations complete, the itinerary service aggregates the responses into a single response message and sends the message to the client through a dynamically assigned endpoint.</span></span> <span data-ttu-id="cb415-107">图 1 说明此用例。</span><span class="sxs-lookup"><span data-stu-id="cb415-107">Figure 1 illustrates this use case.</span></span>  
  
 <span data-ttu-id="cb415-108">![实现散点图收集模式](../esb-toolkit/media/ch3-implementingscatter.gif "Ch3 ImplementingScatter")</span><span class="sxs-lookup"><span data-stu-id="cb415-108">![Implementing Scatter Gather Pattern](../esb-toolkit/media/ch3-implementingscatter.gif "Ch3-ImplementingScatter")</span></span>  
  
 <span data-ttu-id="cb415-109">**图 1**</span><span class="sxs-lookup"><span data-stu-id="cb415-109">**Figure 1**</span></span>  
  
 <span data-ttu-id="cb415-110">**实现多个 Web 服务调用的散播-聚集模式**</span><span class="sxs-lookup"><span data-stu-id="cb415-110">**Implementing the Scatter-Gather pattern for multiple Web service invocations**</span></span>  
  
 <span data-ttu-id="cb415-111">散播-聚集示例随附[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]演示此用例。</span><span class="sxs-lookup"><span data-stu-id="cb415-111">The Scatter-Gather sample included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span>  
  
 <span data-ttu-id="cb415-112">有关详细信息，请参阅[安装和运行散播-聚集示例](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="cb415-112">For more information, see [Installing and Running the Scatter-Gather Sample](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md).</span></span>