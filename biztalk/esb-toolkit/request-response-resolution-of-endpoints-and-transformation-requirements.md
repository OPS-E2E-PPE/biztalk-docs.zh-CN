---
title: "请求-响应解析终结点以及转换要求 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1a1bfdae-2651-402c-b164-16db663aaa95
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72f442f1d9df457a3c1384f1d717e29c17b433f4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="request-response-resolution-of-endpoints-and-transformation-requirements"></a><span data-ttu-id="aee79-102">请求-响应解析终结点以及转换要求</span><span class="sxs-lookup"><span data-stu-id="aee79-102">Request-Response Resolution of Endpoints and Transformation Requirements</span></span>
<span data-ttu-id="aee79-103">在使用此种情况下，客户端应用程序提交入口的请求消息并接收响应。</span><span class="sxs-lookup"><span data-stu-id="aee79-103">In this use case, a client application submits a request message to an on-ramp and receives a response.</span></span> <span data-ttu-id="aee79-104">[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]充当客户端和目标服务终结点之间的中介和使用 ESB 解析程序和适配器框架执行动态消息转换和路由根据负载增加上配置，如图中所示1。</span><span class="sxs-lookup"><span data-stu-id="aee79-104">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] acts as mediator between the client and the target service endpoint and uses the ESB Resolver and Adapter Framework to perform the dynamic message transformation and routing in accordance with the on-ramp configuration, as illustrated in Figure 1.</span></span>  
  
 <span data-ttu-id="aee79-105">![请求 &#45;终结点响应解析](../esb-toolkit/media/ch3-requestresponse.gif "Ch3 请求响应")</span><span class="sxs-lookup"><span data-stu-id="aee79-105">![Request&#45;Response Resolution of Endpoints](../esb-toolkit/media/ch3-requestresponse.gif "Ch3-RequestResponse")</span></span>  
  
 <span data-ttu-id="aee79-106">**图 1**</span><span class="sxs-lookup"><span data-stu-id="aee79-106">**Figure 1**</span></span>  
  
 <span data-ttu-id="aee79-107">**请求-响应解析终结点以及转换要求**</span><span class="sxs-lookup"><span data-stu-id="aee79-107">**Request-response resolution of endpoints and transformation requirements**</span></span>  
  
 <span data-ttu-id="aee79-108">包含动态解析示例[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]演示此用例。</span><span class="sxs-lookup"><span data-stu-id="aee79-108">The Dynamic Resolution sample included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span> <span data-ttu-id="aee79-109">它演示如何将应用动态转换和分辨率的双向方案使用 XML 路径语言 (XPath)、 通用、 描述、 发现和集成 (UDDI)，静态的或在 BizTalk Server 业务规则引擎的策略。</span><span class="sxs-lookup"><span data-stu-id="aee79-109">It shows how to apply dynamic transformation and resolution for two-way scenarios using XML Path Language (XPath), Universal Description, Discovery, and Integration (UDDI), STATIC, or policies in the BizTalk Server Business Rules Engine.</span></span>  
  
 <span data-ttu-id="aee79-110">有关详细信息，请参阅所描述的双向消息传递方案[安装和运行动态解析示例](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="aee79-110">For more information, see the two-way messaging scenario described in [Installing and Running the Dynamic Resolution Sample](../esb-toolkit/installing-and-running-the-dynamic-resolution-sample.md).</span></span>