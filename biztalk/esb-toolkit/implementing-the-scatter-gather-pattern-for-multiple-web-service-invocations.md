---
title: 为多个 Web 服务调用实现分散收集模式 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 912512a4-9649-40df-bb82-b8f4b85c8ca6
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 172515418b17f9b79ac86b3315b8189f5139fea4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400120"
---
# <a name="implementing-the-scatter-gather-pattern-for-multiple-web-service-invocations"></a><span data-ttu-id="6e7fc-102">为多个 Web 服务调用实现分散收集模式</span><span class="sxs-lookup"><span data-stu-id="6e7fc-102">Implementing the Scatter-Gather Pattern for Multiple Web Service Invocations</span></span>
<span data-ttu-id="6e7fc-103">在此用例，一条消息包含一个指定多个 BizTalk Server 应访问的外部服务的路线服务步骤。</span><span class="sxs-lookup"><span data-stu-id="6e7fc-103">In this use case, a message contains an itinerary service step that specifies more than one external service that BizTalk Server should access.</span></span> <span data-ttu-id="6e7fc-104">它使用动态解析以确定服务位置和终结点和任何可选的 BizTalk 服务映射来转换返回的数据。</span><span class="sxs-lookup"><span data-stu-id="6e7fc-104">It uses dynamic resolution to determine service locations and endpoints and any optional BizTalk Service maps for transforming the returned data.</span></span> <span data-ttu-id="6e7fc-105">实现此服务中业务流程执行的转换和调用，并且所有服务调用以异步方式都发生。</span><span class="sxs-lookup"><span data-stu-id="6e7fc-105">The orchestration implementing this service performs the transformation and invocations, and all service invocations occur asynchronously.</span></span> <span data-ttu-id="6e7fc-106">所有服务调用都完成后，路线服务聚合到单个响应消息的响应，并将消息发送到客户端通过动态分配的终结点。</span><span class="sxs-lookup"><span data-stu-id="6e7fc-106">After all service invocations complete, the itinerary service aggregates the responses into a single response message and sends the message to the client through a dynamically assigned endpoint.</span></span> <span data-ttu-id="6e7fc-107">图 1 显示了此用例。</span><span class="sxs-lookup"><span data-stu-id="6e7fc-107">Figure 1 illustrates this use case.</span></span>  
  
 <span data-ttu-id="6e7fc-108">![实现分散收集模式](../esb-toolkit/media/ch3-implementingscatter.gif "Ch3-ImplementingScatter")</span><span class="sxs-lookup"><span data-stu-id="6e7fc-108">![Implementing Scatter Gather Pattern](../esb-toolkit/media/ch3-implementingscatter.gif "Ch3-ImplementingScatter")</span></span>  
  
 <span data-ttu-id="6e7fc-109">**图 1**</span><span class="sxs-lookup"><span data-stu-id="6e7fc-109">**Figure 1**</span></span>  
  
 <span data-ttu-id="6e7fc-110">**实现多个 Web 服务调用的散播-聚集模式**</span><span class="sxs-lookup"><span data-stu-id="6e7fc-110">**Implementing the Scatter-Gather pattern for multiple Web service invocations**</span></span>  
  
 <span data-ttu-id="6e7fc-111">散播-聚集示例随附[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]演示此用例。</span><span class="sxs-lookup"><span data-stu-id="6e7fc-111">The Scatter-Gather sample included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span>  
  
 <span data-ttu-id="6e7fc-112">有关详细信息，请参阅[安装和运行分散-集中示例](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="6e7fc-112">For more information, see [Installing and Running the Scatter-Gather Sample](../esb-toolkit/installing-and-running-the-scatter-gather-sample.md).</span></span>