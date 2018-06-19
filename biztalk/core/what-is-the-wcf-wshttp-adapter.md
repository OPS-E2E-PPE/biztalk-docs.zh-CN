---
title: 什么是 WCF WSHttp 适配器？ | Microsoft Docs
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
ms.openlocfilehash: eb5d244dcfe26cf10bc4ae10c63374eef0824444
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289333"
---
# <a name="what-is-the-wcf-wshttp-adapter"></a><span data-ttu-id="7d7d7-103">什么是 WCF WSHttp 适配器？</span><span class="sxs-lookup"><span data-stu-id="7d7d7-103">What Is the WCF-WSHttp Adapter?</span></span>
<span data-ttu-id="7d7d7-104">借助 WCF-WSHttp 适配器，您可以通过以文本或消息传输优化机制 (MTOM) 编码的 HTTP 或 HTTPS 传输，与支持下一代 Web Services 标准的服务和客户端实现跨计算机通信。</span><span class="sxs-lookup"><span data-stu-id="7d7d7-104">You can use the WCF-WSHttp adapter to do cross-computer communication with services and clients that can understand the next-generation Web service standards, using either the HTTP or HTTPS transport with text or Message Transmission Optimization Mechanism (MTOM) encoding.</span></span> <span data-ttu-id="7d7d7-105">WCF-WSHttp 适配器提供了对 SOAP 安全性、可靠性和事务功能的完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="7d7d7-105">The WCF-WSHttp adapter provides full access to the SOAP security, reliability, and transaction features.</span></span>  
  
 <span data-ttu-id="7d7d7-106">下表总结了 WCF-WSHttp 适配器的特征。</span><span class="sxs-lookup"><span data-stu-id="7d7d7-106">The following table summarizes the characteristics of the WCF-WSHttp adapter.</span></span>  
  
|<span data-ttu-id="7d7d7-107">Description</span><span class="sxs-lookup"><span data-stu-id="7d7d7-107">Description</span></span>|<span data-ttu-id="7d7d7-108">特征</span><span class="sxs-lookup"><span data-stu-id="7d7d7-108">Characteristic</span></span>|  
|-----------------|--------------------|  
|<span data-ttu-id="7d7d7-109">互操作性水平</span><span class="sxs-lookup"><span data-stu-id="7d7d7-109">Interoperability level</span></span>|<span data-ttu-id="7d7d7-110">WS-Profile</span><span class="sxs-lookup"><span data-stu-id="7d7d7-110">WS-Profile</span></span>|  
|<span data-ttu-id="7d7d7-111">消息编码</span><span class="sxs-lookup"><span data-stu-id="7d7d7-111">Message encoding</span></span>|<span data-ttu-id="7d7d7-112">文本或 MTOM</span><span class="sxs-lookup"><span data-stu-id="7d7d7-112">Text or MTOM</span></span>|  
|<span data-ttu-id="7d7d7-113">边界</span><span class="sxs-lookup"><span data-stu-id="7d7d7-113">Boundary</span></span>|<span data-ttu-id="7d7d7-114">跨计算机</span><span class="sxs-lookup"><span data-stu-id="7d7d7-114">Cross-computer</span></span>|  
|<span data-ttu-id="7d7d7-115">传输协议</span><span class="sxs-lookup"><span data-stu-id="7d7d7-115">Transport protocol</span></span>|<span data-ttu-id="7d7d7-116">HTTP 或 HTTPS</span><span class="sxs-lookup"><span data-stu-id="7d7d7-116">HTTP or HTTPS</span></span>|  
|<span data-ttu-id="7d7d7-117">安全模式</span><span class="sxs-lookup"><span data-stu-id="7d7d7-117">Security mode</span></span>|<span data-ttu-id="7d7d7-118">无、消息、传输和 TransportWithMessageCredential。</span><span class="sxs-lookup"><span data-stu-id="7d7d7-118">None, Message, Transport, and TransportWithMessageCredential.</span></span>|  
|<span data-ttu-id="7d7d7-119">客户端身份验证机制</span><span class="sxs-lookup"><span data-stu-id="7d7d7-119">Client authentication mechanism</span></span>|<span data-ttu-id="7d7d7-120">传输安全性和消息安全性</span><span class="sxs-lookup"><span data-stu-id="7d7d7-120">Transport Security and Message Security</span></span>|  
|<span data-ttu-id="7d7d7-121">是否支持 WS-ReliableMessaging</span><span class="sxs-lookup"><span data-stu-id="7d7d7-121">Support for WS-ReliableMessaging</span></span>|<span data-ttu-id="7d7d7-122">是</span><span class="sxs-lookup"><span data-stu-id="7d7d7-122">No</span></span>|  
|<span data-ttu-id="7d7d7-123">是否支持 WS-AtomicTransaction</span><span class="sxs-lookup"><span data-stu-id="7d7d7-123">Support for WS-AtomicTransaction</span></span>|<span data-ttu-id="7d7d7-124">是</span><span class="sxs-lookup"><span data-stu-id="7d7d7-124">Yes</span></span>|  
|<span data-ttu-id="7d7d7-125">支持单向消息传送</span><span class="sxs-lookup"><span data-stu-id="7d7d7-125">Support for one-way messaging</span></span>|<span data-ttu-id="7d7d7-126">是</span><span class="sxs-lookup"><span data-stu-id="7d7d7-126">Yes</span></span>|  
|<span data-ttu-id="7d7d7-127">支持双向消息传送</span><span class="sxs-lookup"><span data-stu-id="7d7d7-127">Support for two-way messaging</span></span>|<span data-ttu-id="7d7d7-128">是</span><span class="sxs-lookup"><span data-stu-id="7d7d7-128">Yes</span></span>|  
|<span data-ttu-id="7d7d7-129">接收适配器的主机类型</span><span class="sxs-lookup"><span data-stu-id="7d7d7-129">Host type for receive adapter</span></span>|<span data-ttu-id="7d7d7-130">隔离</span><span class="sxs-lookup"><span data-stu-id="7d7d7-130">Isolated</span></span>|  
|<span data-ttu-id="7d7d7-131">发送适配器的主机类型</span><span class="sxs-lookup"><span data-stu-id="7d7d7-131">Host type for send adapter</span></span>|<span data-ttu-id="7d7d7-132">进程内</span><span class="sxs-lookup"><span data-stu-id="7d7d7-132">In-process</span></span>|  
  
 <span data-ttu-id="7d7d7-133">WCF-WSHttp 适配器由两个适配器组成：一个接收适配器和一个发送适配器。</span><span class="sxs-lookup"><span data-stu-id="7d7d7-133">The WCF-WSHttp adapter consists of two adapters—a receive adapter and a send adapter.</span></span>  
  
 <span data-ttu-id="7d7d7-134">**WCF WSHttp 接收适配器**</span><span class="sxs-lookup"><span data-stu-id="7d7d7-134">**WCF-WSHttp Receive Adapter**</span></span>  
  
 <span data-ttu-id="7d7d7-135">您可使用 WCF-WSHttp 接收适配器通过 HTTP 或 HTTPS 协议接收 WCF 服务请求。</span><span class="sxs-lookup"><span data-stu-id="7d7d7-135">You use the WCF-WSHttp receive adapter to receive WCF service requests through the HTTP or HTTPS protocol.</span></span> <span data-ttu-id="7d7d7-136">使用 WCF-WSHttp 接收适配器的接收位置可以配置为单向或请求-响应（双向）。</span><span class="sxs-lookup"><span data-stu-id="7d7d7-136">A receive location that uses the WCF-WSHttp receive adapter can be configured as one-way or request-response (two-way).</span></span>  
  
 <span data-ttu-id="7d7d7-137">**WCF WSHttp 发送适配器**</span><span class="sxs-lookup"><span data-stu-id="7d7d7-137">**WCF-WSHttp Send Adapter**</span></span>  
  
 <span data-ttu-id="7d7d7-138">您可使用 WCF-WSHttp 发送适配器及 HTTP 或 HTTPS 协议通过无类型约定调用 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="7d7d7-138">You use the WCF-WSHttp send adapter to call a WCF service through the typeless contract by using the HTTP or HTTPS protocol.</span></span>  
  
 <span data-ttu-id="7d7d7-139">有关 WCF 的详细信息接收和发送适配器，请参阅[WCF 适配器是什么？](../core/what-are-the-wcf-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="7d7d7-139">For more information about WCF receive and send adapters, see [What Are the WCF Adapters?](../core/what-are-the-wcf-adapters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d7d7-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7d7d7-140">See Also</span></span>  
 <span data-ttu-id="7d7d7-141">[配置 WCF WSHttp 适配器](../core/configuring-the-wcf-wshttp-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="7d7d7-141">[Configuring the WCF-WSHttp Adapter](../core/configuring-the-wcf-wshttp-adapter.md) </span></span>  
 [<span data-ttu-id="7d7d7-142">WCF 适配器</span><span class="sxs-lookup"><span data-stu-id="7d7d7-142">WCF Adapters</span></span>](../core/wcf-adapters.md)