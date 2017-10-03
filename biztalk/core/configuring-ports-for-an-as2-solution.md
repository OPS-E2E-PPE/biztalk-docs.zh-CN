---
title: "配置端口以便为 AS2 解决方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 715358b1-4226-476b-b0de-2b91434aa24c
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f8f02c5de0edd7956f00e10ce8782e4865033076
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-ports-for-an-as2-solution"></a><span data-ttu-id="60236-102">为 AS2 解决方案配置端口</span><span class="sxs-lookup"><span data-stu-id="60236-102">Configuring Ports for an AS2 Solution</span></span>
<span data-ttu-id="60236-103">可以使用以下接收和发送端口传送 AS2 上的 EDI 和非 EDI 消息：</span><span class="sxs-lookup"><span data-stu-id="60236-103">You can use the following receive and send ports to transmit EDI and non-EDI messages over AS2:</span></span>  
  
 <span data-ttu-id="60236-104">**接收端口**</span><span class="sxs-lookup"><span data-stu-id="60236-104">**Receive Ports**</span></span>  
  
|<span data-ttu-id="60236-105">若要接收</span><span class="sxs-lookup"><span data-stu-id="60236-105">To Receive</span></span>|<span data-ttu-id="60236-106">发送</span><span class="sxs-lookup"><span data-stu-id="60236-106">To Send</span></span>|<span data-ttu-id="60236-107">端口类型</span><span class="sxs-lookup"><span data-stu-id="60236-107">Type of Port</span></span>|  
|----------------|-------------|------------------|  
|<span data-ttu-id="60236-108">EDI 或非 EDI 消息或确认</span><span class="sxs-lookup"><span data-stu-id="60236-108">An EDI or non-EDI message or acknowledgment</span></span>|<span data-ttu-id="60236-109">MDN 响应（如果处于同步模式）或 HTTP 响应（如果处于异步模式）</span><span class="sxs-lookup"><span data-stu-id="60236-109">An MDN response (if in synchronous mode) or an HTTP response (if in asynchronous mode)</span></span>|<span data-ttu-id="60236-110">双向请求-响应 HTTP 接收端口</span><span class="sxs-lookup"><span data-stu-id="60236-110">Two-way request-response HTTP receive port</span></span>|  
|<span data-ttu-id="60236-111">MDN 响应</span><span class="sxs-lookup"><span data-stu-id="60236-111">An MDN response</span></span>|-|<span data-ttu-id="60236-112">单向 HTTP 接收端口</span><span class="sxs-lookup"><span data-stu-id="60236-112">One-way HTTP receive port</span></span>|  
  
 <span data-ttu-id="60236-113">**发送端口**</span><span class="sxs-lookup"><span data-stu-id="60236-113">**Send Ports**</span></span>  
  
|<span data-ttu-id="60236-114">发送</span><span class="sxs-lookup"><span data-stu-id="60236-114">To Send</span></span>|<span data-ttu-id="60236-115">若要接收</span><span class="sxs-lookup"><span data-stu-id="60236-115">To Receive</span></span>|<span data-ttu-id="60236-116">端口类型</span><span class="sxs-lookup"><span data-stu-id="60236-116">Type of Port</span></span>|  
|-------------|----------------|------------------|  
|<span data-ttu-id="60236-117">EDI 或非 EDI 消息或确认</span><span class="sxs-lookup"><span data-stu-id="60236-117">An EDI or non-EDI message or acknowledgment</span></span><br /><br /> <span data-ttu-id="60236-118">（基于协议的路由）</span><span class="sxs-lookup"><span data-stu-id="60236-118">(agreement-based routing)</span></span>|-|<span data-ttu-id="60236-119">静态单向 HTTP 发送端口</span><span class="sxs-lookup"><span data-stu-id="60236-119">Static one-way HTTP send port</span></span>|  
|<span data-ttu-id="60236-120">EDI 或非 EDI 消息或确认</span><span class="sxs-lookup"><span data-stu-id="60236-120">An EDI or non-EDI message or acknowledgment</span></span><br /><br /> <span data-ttu-id="60236-121">（基于内容的路由）</span><span class="sxs-lookup"><span data-stu-id="60236-121">(content-based routing)</span></span>|<span data-ttu-id="60236-122">MDN 响应</span><span class="sxs-lookup"><span data-stu-id="60236-122">An MDN response</span></span>|<span data-ttu-id="60236-123">动态双向要求-响应 HTTP 发送端口</span><span class="sxs-lookup"><span data-stu-id="60236-123">Dynamic two-way solicit-response HTTP send port</span></span>|  
|<span data-ttu-id="60236-124">EDI 或非 EDI 消息或确认</span><span class="sxs-lookup"><span data-stu-id="60236-124">An EDI or non-EDI message or acknowledgment</span></span><br /><br /> <span data-ttu-id="60236-125">（基于内容的路由）</span><span class="sxs-lookup"><span data-stu-id="60236-125">(content-based routing)</span></span>|-|<span data-ttu-id="60236-126">动态单向 HTTP 发送端口</span><span class="sxs-lookup"><span data-stu-id="60236-126">Dynamic one-way HTTP send port</span></span>|  
|<span data-ttu-id="60236-127">异步 MDN 响应</span><span class="sxs-lookup"><span data-stu-id="60236-127">An asynchronous MDN response</span></span><br /><br /> <span data-ttu-id="60236-128">（基于内容的路由）</span><span class="sxs-lookup"><span data-stu-id="60236-128">(content-based routing)</span></span>|-|<span data-ttu-id="60236-129">动态单向发送端口</span><span class="sxs-lookup"><span data-stu-id="60236-129">Dynamic one-way send port</span></span>|  
|<span data-ttu-id="60236-130">异步 MDN 响应</span><span class="sxs-lookup"><span data-stu-id="60236-130">An asynchronous MDN response</span></span>|-|<span data-ttu-id="60236-131">静态单向发送端口</span><span class="sxs-lookup"><span data-stu-id="60236-131">Static one-way send port</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="60236-132">本节内容</span><span class="sxs-lookup"><span data-stu-id="60236-132">In This Section</span></span>  
  
-   [<span data-ttu-id="60236-133">配置通过 AS2 消息接收端口</span><span class="sxs-lookup"><span data-stu-id="60236-133">Configuring a Receive Port for Messages over AS2</span></span>](../core/configuring-a-receive-port-for-messages-over-as2.md)  
  
-   [<span data-ttu-id="60236-134">配置传入 Mdn 的接收端口</span><span class="sxs-lookup"><span data-stu-id="60236-134">Configuring a Receive Port for Incoming MDNs</span></span>](../core/configuring-a-receive-port-for-incoming-mdns.md)  
  
-   [<span data-ttu-id="60236-135">通过 AS2 消息配置静态发送端口</span><span class="sxs-lookup"><span data-stu-id="60236-135">Configuring a Static Send Port for Messages over AS2</span></span>](../core/configuring-a-static-send-port-for-messages-over-as2.md)  
  
-   [<span data-ttu-id="60236-136">通过 AS2 消息配置动态发送端口</span><span class="sxs-lookup"><span data-stu-id="60236-136">Configuring a Dynamic Send Port for Messages over AS2</span></span>](../core/configuring-a-dynamic-send-port-for-messages-over-as2.md)  
  
-   [<span data-ttu-id="60236-137">通过 AS2 异步 Mdn 的配置静态发送端口</span><span class="sxs-lookup"><span data-stu-id="60236-137">Configuring a Static Send Port for Asynchronous MDNs over AS2</span></span>](../core/configuring-a-static-send-port-for-asynchronous-mdns-over-as2.md)  
  
-   [<span data-ttu-id="60236-138">通过 AS2 异步 Mdn 的配置动态发送端口</span><span class="sxs-lookup"><span data-stu-id="60236-138">Configuring a Dynamic Send Port for Asynchronous MDNs over AS2</span></span>](../core/configuring-a-dynamic-send-port-for-asynchronous-mdns-over-as2.md)  
  
## <a name="see-also"></a><span data-ttu-id="60236-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="60236-139">See Also</span></span>  
 [<span data-ttu-id="60236-140">开发和配置 BizTalk Server AS2 解决方案</span><span class="sxs-lookup"><span data-stu-id="60236-140">Developing and Configuring BizTalk Server AS2 Solutions</span></span>](../core/developing-and-configuring-biztalk-server-as2-solutions.md)