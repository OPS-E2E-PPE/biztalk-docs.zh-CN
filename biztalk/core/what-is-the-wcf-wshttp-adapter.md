---
title: Wcf-wshttp 适配器是什么？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-WSHttp adapters, about WCF-WSHttp adapters
ms.assetid: 183a19e3-10b1-403f-b274-34a441e774d1
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3d82d26e03163d856bc4ce9d0cc8d948d07e54a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242800"
---
# <a name="what-is-the-wcf-wshttp-adapter"></a><span data-ttu-id="9217a-103">Wcf-wshttp 适配器是什么？</span><span class="sxs-lookup"><span data-stu-id="9217a-103">What Is the WCF-WSHttp Adapter?</span></span>
<span data-ttu-id="9217a-104">可以使用 Wcf-wshttp 适配器实现跨计算机通信服务和客户端，可以了解下一代 Web 服务标准，与文本或消息传输优化机制 （使用 HTTP 或 HTTPS 传输MTOM) 编码。</span><span class="sxs-lookup"><span data-stu-id="9217a-104">You can use the WCF-WSHttp adapter to do cross-computer communication with services and clients that can understand the next-generation Web service standards, using either the HTTP or HTTPS transport with text or Message Transmission Optimization Mechanism (MTOM) encoding.</span></span> <span data-ttu-id="9217a-105">Wcf-wshttp 适配器提供了对 SOAP 安全性、 可靠性和事务功能完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="9217a-105">The WCF-WSHttp adapter provides full access to the SOAP security, reliability, and transaction features.</span></span>  
  
 <span data-ttu-id="9217a-106">下表总结了 Wcf-wshttp 适配器的特征。</span><span class="sxs-lookup"><span data-stu-id="9217a-106">The following table summarizes the characteristics of the WCF-WSHttp adapter.</span></span>  
  
|<span data-ttu-id="9217a-107">Description</span><span class="sxs-lookup"><span data-stu-id="9217a-107">Description</span></span>|<span data-ttu-id="9217a-108">特征</span><span class="sxs-lookup"><span data-stu-id="9217a-108">Characteristic</span></span>|  
|-----------------|--------------------|  
|<span data-ttu-id="9217a-109">互操作性级别</span><span class="sxs-lookup"><span data-stu-id="9217a-109">Interoperability level</span></span>|<span data-ttu-id="9217a-110">WS-Profile</span><span class="sxs-lookup"><span data-stu-id="9217a-110">WS-Profile</span></span>|  
|<span data-ttu-id="9217a-111">消息编码</span><span class="sxs-lookup"><span data-stu-id="9217a-111">Message encoding</span></span>|<span data-ttu-id="9217a-112">文本或 MTOM</span><span class="sxs-lookup"><span data-stu-id="9217a-112">Text or MTOM</span></span>|  
|<span data-ttu-id="9217a-113">边界</span><span class="sxs-lookup"><span data-stu-id="9217a-113">Boundary</span></span>|<span data-ttu-id="9217a-114">跨计算机</span><span class="sxs-lookup"><span data-stu-id="9217a-114">Cross-computer</span></span>|  
|<span data-ttu-id="9217a-115">传输协议</span><span class="sxs-lookup"><span data-stu-id="9217a-115">Transport protocol</span></span>|<span data-ttu-id="9217a-116">HTTP 或 HTTPS</span><span class="sxs-lookup"><span data-stu-id="9217a-116">HTTP or HTTPS</span></span>|  
|<span data-ttu-id="9217a-117">安全模式</span><span class="sxs-lookup"><span data-stu-id="9217a-117">Security mode</span></span>|<span data-ttu-id="9217a-118">无、 消息、 传输和 TransportWithMessageCredential。</span><span class="sxs-lookup"><span data-stu-id="9217a-118">None, Message, Transport, and TransportWithMessageCredential.</span></span>|  
|<span data-ttu-id="9217a-119">客户端身份验证机制</span><span class="sxs-lookup"><span data-stu-id="9217a-119">Client authentication mechanism</span></span>|<span data-ttu-id="9217a-120">传输安全和消息安全</span><span class="sxs-lookup"><span data-stu-id="9217a-120">Transport Security and Message Security</span></span>|  
|<span data-ttu-id="9217a-121">支持 WS-ReliableMessaging</span><span class="sxs-lookup"><span data-stu-id="9217a-121">Support for WS-ReliableMessaging</span></span>|<span data-ttu-id="9217a-122">否</span><span class="sxs-lookup"><span data-stu-id="9217a-122">No</span></span>|  
|<span data-ttu-id="9217a-123">支持 WS-AtomicTransaction</span><span class="sxs-lookup"><span data-stu-id="9217a-123">Support for WS-AtomicTransaction</span></span>|<span data-ttu-id="9217a-124">是</span><span class="sxs-lookup"><span data-stu-id="9217a-124">Yes</span></span>|  
|<span data-ttu-id="9217a-125">支持单向消息传送</span><span class="sxs-lookup"><span data-stu-id="9217a-125">Support for one-way messaging</span></span>|<span data-ttu-id="9217a-126">是</span><span class="sxs-lookup"><span data-stu-id="9217a-126">Yes</span></span>|  
|<span data-ttu-id="9217a-127">支持双向消息传送</span><span class="sxs-lookup"><span data-stu-id="9217a-127">Support for two-way messaging</span></span>|<span data-ttu-id="9217a-128">是</span><span class="sxs-lookup"><span data-stu-id="9217a-128">Yes</span></span>|  
|<span data-ttu-id="9217a-129">主机类型的接收适配器</span><span class="sxs-lookup"><span data-stu-id="9217a-129">Host type for receive adapter</span></span>|<span data-ttu-id="9217a-130">隔离</span><span class="sxs-lookup"><span data-stu-id="9217a-130">Isolated</span></span>|  
|<span data-ttu-id="9217a-131">发送适配器的主机类型</span><span class="sxs-lookup"><span data-stu-id="9217a-131">Host type for send adapter</span></span>|<span data-ttu-id="9217a-132">进程内</span><span class="sxs-lookup"><span data-stu-id="9217a-132">In-process</span></span>|  
  
 <span data-ttu-id="9217a-133">Wcf-wshttp 适配器由两个适配器组成： 一个接收适配器和一个发送适配器。</span><span class="sxs-lookup"><span data-stu-id="9217a-133">The WCF-WSHttp adapter consists of two adapters—a receive adapter and a send adapter.</span></span>  
  
 <span data-ttu-id="9217a-134">**Wcf-wshttp 接收适配器**</span><span class="sxs-lookup"><span data-stu-id="9217a-134">**WCF-WSHttp Receive Adapter**</span></span>  
  
 <span data-ttu-id="9217a-135">使用 Wcf-wshttp 接收适配器接收通过 HTTP 或 HTTPS 协议的 WCF 服务请求。</span><span class="sxs-lookup"><span data-stu-id="9217a-135">You use the WCF-WSHttp receive adapter to receive WCF service requests through the HTTP or HTTPS protocol.</span></span> <span data-ttu-id="9217a-136">使用 Wcf-wshttp 接收适配器的接收位置可以配置为单向或请求-响应 （双向）。</span><span class="sxs-lookup"><span data-stu-id="9217a-136">A receive location that uses the WCF-WSHttp receive adapter can be configured as one-way or request-response (two-way).</span></span>  
  
 <span data-ttu-id="9217a-137">**Wcf-wshttp 发送适配器**</span><span class="sxs-lookup"><span data-stu-id="9217a-137">**WCF-WSHttp Send Adapter**</span></span>  
  
 <span data-ttu-id="9217a-138">使用 Wcf-wshttp 发送适配器来调用通过使用 HTTP 或 HTTPS 协议通过无类型协定的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="9217a-138">You use the WCF-WSHttp send adapter to call a WCF service through the typeless contract by using the HTTP or HTTPS protocol.</span></span>  
  
 <span data-ttu-id="9217a-139">有关 WCF 接收和发送适配器，请参阅[WCF 适配器是什么？](../core/what-are-the-wcf-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="9217a-139">For more information about WCF receive and send adapters, see [What Are the WCF Adapters?](../core/what-are-the-wcf-adapters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9217a-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="9217a-140">See Also</span></span>  
 <span data-ttu-id="9217a-141">[配置 Wcf-wshttp 适配器](../core/configuring-the-wcf-wshttp-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="9217a-141">[Configuring the WCF-WSHttp Adapter](../core/configuring-the-wcf-wshttp-adapter.md) </span></span>  
 [<span data-ttu-id="9217a-142">WCF 适配器</span><span class="sxs-lookup"><span data-stu-id="9217a-142">WCF Adapters</span></span>](../core/wcf-adapters.md)