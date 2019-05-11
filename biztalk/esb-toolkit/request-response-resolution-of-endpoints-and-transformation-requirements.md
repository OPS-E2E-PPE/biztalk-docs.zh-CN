---
title: 请求-响应解决方案的终结点和转换需求 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1a1bfdae-2651-402c-b164-16db663aaa95
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01ef1004d922fa8933ad021e958207ee36c91db6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400213"
---
# <a name="request-response-resolution-of-endpoints-and-transformation-requirements"></a><span data-ttu-id="8dc51-102">请求-响应解决方案的终结点和转换需求</span><span class="sxs-lookup"><span data-stu-id="8dc51-102">Request-Response Resolution of Endpoints and Transformation Requirements</span></span>
<span data-ttu-id="8dc51-103">在此用例，客户端应用程序提交的途径的请求消息并接收响应。</span><span class="sxs-lookup"><span data-stu-id="8dc51-103">In this use case, a client application submits a request message to an on-ramp and receives a response.</span></span> <span data-ttu-id="8dc51-104">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]可用作客户端和目标服务终结点之间的转存进程，并使用 ESB 解析程序和适配器框架来执行动态消息转换和路由根据选择的接入点配置，如图中所示1。</span><span class="sxs-lookup"><span data-stu-id="8dc51-104">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] acts as mediator between the client and the target service endpoint and uses the ESB Resolver and Adapter Framework to perform the dynamic message transformation and routing in accordance with the on-ramp configuration, as illustrated in Figure 1.</span></span>  
  
 <span data-ttu-id="8dc51-105">![请求&#45;终结点响应解决方案](../esb-toolkit/media/ch3-requestresponse.gif "Ch3-RequestResponse")</span><span class="sxs-lookup"><span data-stu-id="8dc51-105">![Request&#45;Response Resolution of Endpoints](../esb-toolkit/media/ch3-requestresponse.gif "Ch3-RequestResponse")</span></span>  
  
 <span data-ttu-id="8dc51-106">**图 1**</span><span class="sxs-lookup"><span data-stu-id="8dc51-106">**Figure 1**</span></span>  
  
 <span data-ttu-id="8dc51-107">**请求-响应解决方案的终结点和转换需求**</span><span class="sxs-lookup"><span data-stu-id="8dc51-107">**Request-response resolution of endpoints and transformation requirements**</span></span>  
  
 <span data-ttu-id="8dc51-108">动态解析示例随附[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]演示此用例。</span><span class="sxs-lookup"><span data-stu-id="8dc51-108">The Dynamic Resolution sample included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span> <span data-ttu-id="8dc51-109">它演示如何将应用动态转换和解决方法用于使用 XML 路径语言 (XPath)、 通用描述、 发现和集成 (UDDI)，静态的双向方案或 BizTalk Server 业务规则引擎中的策略。</span><span class="sxs-lookup"><span data-stu-id="8dc51-109">It shows how to apply dynamic transformation and resolution for two-way scenarios using XML Path Language (XPath), Universal Description, Discovery, and Integration (UDDI), STATIC, or policies in the BizTalk Server Business Rules Engine.</span></span>  
  
 <span data-ttu-id="8dc51-110">有关详细信息，请参阅双向消息传送的方案中所述[安装和运行动态解析示例](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="8dc51-110">For more information, see the two-way messaging scenario described in [Installing and Running the Dynamic Resolution Sample](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md).</span></span>