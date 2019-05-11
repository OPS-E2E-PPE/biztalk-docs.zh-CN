---
title: 为 AS2 解决方案配置端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 715358b1-4226-476b-b0de-2b91434aa24c
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b045a18893153d6c2982b7b6214b7eea6e1852fb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390862"
---
# <a name="configuring-ports-for-an-as2-solution"></a><span data-ttu-id="24dea-102">为 AS2 解决方案配置端口</span><span class="sxs-lookup"><span data-stu-id="24dea-102">Configuring Ports for an AS2 Solution</span></span>
<span data-ttu-id="24dea-103">您可以使用以下接收和发送端口通过 AS2 传输 EDI 和非 EDI 消息：</span><span class="sxs-lookup"><span data-stu-id="24dea-103">You can use the following receive and send ports to transmit EDI and non-EDI messages over AS2:</span></span>  
  
 <span data-ttu-id="24dea-104">**接收端口**</span><span class="sxs-lookup"><span data-stu-id="24dea-104">**Receive Ports**</span></span>  
  
|<span data-ttu-id="24dea-105">若要接收</span><span class="sxs-lookup"><span data-stu-id="24dea-105">To Receive</span></span>|<span data-ttu-id="24dea-106">若要发送</span><span class="sxs-lookup"><span data-stu-id="24dea-106">To Send</span></span>|<span data-ttu-id="24dea-107">端口类型</span><span class="sxs-lookup"><span data-stu-id="24dea-107">Type of Port</span></span>|  
|----------------|-------------|------------------|  
|<span data-ttu-id="24dea-108">EDI 或非 EDI 消息或确认</span><span class="sxs-lookup"><span data-stu-id="24dea-108">An EDI or non-EDI message or acknowledgment</span></span>|<span data-ttu-id="24dea-109">MDN 响应 （如果处于同步模式） 或 HTTP 响应 （如果处于异步模式）</span><span class="sxs-lookup"><span data-stu-id="24dea-109">An MDN response (if in synchronous mode) or an HTTP response (if in asynchronous mode)</span></span>|<span data-ttu-id="24dea-110">双向请求-响应 HTTP 接收端口</span><span class="sxs-lookup"><span data-stu-id="24dea-110">Two-way request-response HTTP receive port</span></span>|  
|<span data-ttu-id="24dea-111">MDN 响应</span><span class="sxs-lookup"><span data-stu-id="24dea-111">An MDN response</span></span>|-|<span data-ttu-id="24dea-112">单向 HTTP 接收端口</span><span class="sxs-lookup"><span data-stu-id="24dea-112">One-way HTTP receive port</span></span>|  
  
 <span data-ttu-id="24dea-113">**发送端口**</span><span class="sxs-lookup"><span data-stu-id="24dea-113">**Send Ports**</span></span>  
  
|<span data-ttu-id="24dea-114">若要发送</span><span class="sxs-lookup"><span data-stu-id="24dea-114">To Send</span></span>|<span data-ttu-id="24dea-115">若要接收</span><span class="sxs-lookup"><span data-stu-id="24dea-115">To Receive</span></span>|<span data-ttu-id="24dea-116">端口类型</span><span class="sxs-lookup"><span data-stu-id="24dea-116">Type of Port</span></span>|  
|-------------|----------------|------------------|  
|<span data-ttu-id="24dea-117">EDI 或非 EDI 消息或确认</span><span class="sxs-lookup"><span data-stu-id="24dea-117">An EDI or non-EDI message or acknowledgment</span></span><br /><br /> <span data-ttu-id="24dea-118">（基于协议的路由）</span><span class="sxs-lookup"><span data-stu-id="24dea-118">(agreement-based routing)</span></span>|-|<span data-ttu-id="24dea-119">静态单向 HTTP 发送端口</span><span class="sxs-lookup"><span data-stu-id="24dea-119">Static one-way HTTP send port</span></span>|  
|<span data-ttu-id="24dea-120">EDI 或非 EDI 消息或确认</span><span class="sxs-lookup"><span data-stu-id="24dea-120">An EDI or non-EDI message or acknowledgment</span></span><br /><br /> <span data-ttu-id="24dea-121">（基于内容的路由）</span><span class="sxs-lookup"><span data-stu-id="24dea-121">(content-based routing)</span></span>|<span data-ttu-id="24dea-122">MDN 响应</span><span class="sxs-lookup"><span data-stu-id="24dea-122">An MDN response</span></span>|<span data-ttu-id="24dea-123">动态双向要求-响应 HTTP 发送端口</span><span class="sxs-lookup"><span data-stu-id="24dea-123">Dynamic two-way solicit-response HTTP send port</span></span>|  
|<span data-ttu-id="24dea-124">EDI 或非 EDI 消息或确认</span><span class="sxs-lookup"><span data-stu-id="24dea-124">An EDI or non-EDI message or acknowledgment</span></span><br /><br /> <span data-ttu-id="24dea-125">（基于内容的路由）</span><span class="sxs-lookup"><span data-stu-id="24dea-125">(content-based routing)</span></span>|-|<span data-ttu-id="24dea-126">动态单向 HTTP 发送端口</span><span class="sxs-lookup"><span data-stu-id="24dea-126">Dynamic one-way HTTP send port</span></span>|  
|<span data-ttu-id="24dea-127">异步 MDN 响应</span><span class="sxs-lookup"><span data-stu-id="24dea-127">An asynchronous MDN response</span></span><br /><br /> <span data-ttu-id="24dea-128">（基于内容的路由）</span><span class="sxs-lookup"><span data-stu-id="24dea-128">(content-based routing)</span></span>|-|<span data-ttu-id="24dea-129">动态单向发送端口</span><span class="sxs-lookup"><span data-stu-id="24dea-129">Dynamic one-way send port</span></span>|  
|<span data-ttu-id="24dea-130">异步 MDN 响应</span><span class="sxs-lookup"><span data-stu-id="24dea-130">An asynchronous MDN response</span></span>|-|<span data-ttu-id="24dea-131">静态单向发送端口</span><span class="sxs-lookup"><span data-stu-id="24dea-131">Static one-way send port</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="24dea-132">本节内容</span><span class="sxs-lookup"><span data-stu-id="24dea-132">In This Section</span></span>  
  
-   [<span data-ttu-id="24dea-133">配置 AS2 消息的接收端口</span><span class="sxs-lookup"><span data-stu-id="24dea-133">Configuring a Receive Port for Messages over AS2</span></span>](../core/configuring-a-receive-port-for-messages-over-as2.md)  
  
-   [<span data-ttu-id="24dea-134">配置传入 MDN 的接收端口</span><span class="sxs-lookup"><span data-stu-id="24dea-134">Configuring a Receive Port for Incoming MDNs</span></span>](../core/configuring-a-receive-port-for-incoming-mdns.md)  
  
-   [<span data-ttu-id="24dea-135">配置 AS2 消息的静态发送端口</span><span class="sxs-lookup"><span data-stu-id="24dea-135">Configuring a Static Send Port for Messages over AS2</span></span>](../core/configuring-a-static-send-port-for-messages-over-as2.md)  
  
-   [<span data-ttu-id="24dea-136">配置 AS2 消息的动态发送端口</span><span class="sxs-lookup"><span data-stu-id="24dea-136">Configuring a Dynamic Send Port for Messages over AS2</span></span>](../core/configuring-a-dynamic-send-port-for-messages-over-as2.md)  
  
-   [<span data-ttu-id="24dea-137">配置用于通过 AS2 发送异步 MDN 的静态发送端口</span><span class="sxs-lookup"><span data-stu-id="24dea-137">Configuring a Static Send Port for Asynchronous MDNs over AS2</span></span>](../core/configuring-a-static-send-port-for-asynchronous-mdns-over-as2.md)  
  
-   [<span data-ttu-id="24dea-138">配置用于通过 AS2 发送异步 MDN 的动态发送端口</span><span class="sxs-lookup"><span data-stu-id="24dea-138">Configuring a Dynamic Send Port for Asynchronous MDNs over AS2</span></span>](../core/configuring-a-dynamic-send-port-for-asynchronous-mdns-over-as2.md)  
  
## <a name="see-also"></a><span data-ttu-id="24dea-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="24dea-139">See Also</span></span>  
 [<span data-ttu-id="24dea-140">开发和配置 BizTalk Server AS2 解决方案</span><span class="sxs-lookup"><span data-stu-id="24dea-140">Developing and Configuring BizTalk Server AS2 Solutions</span></span>](../core/developing-and-configuring-biztalk-server-as2-solutions.md)