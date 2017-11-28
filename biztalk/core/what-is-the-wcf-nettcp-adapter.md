---
title: "什么是 WCF-NetTcp 适配器？ | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF-NetTcp adapters, about WCF-NetTcp adapters
ms.assetid: 94dc24df-19a1-4701-9012-59d05b0c8abd
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a741d3a4d7b7bcc80405d0fc25e37a31860523b9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-wcf-nettcp-adapter"></a><span data-ttu-id="c36d1-103">什么是 WCF-NetTcp 适配器？</span><span class="sxs-lookup"><span data-stu-id="c36d1-103">What Is the WCF-NetTcp Adapter?</span></span>
<span data-ttu-id="c36d1-104">WCF-NetTcp 适配器在服务和客户端都是基于 WCF 的环境中提供连接的跨计算机或跨进程通信。</span><span class="sxs-lookup"><span data-stu-id="c36d1-104">The WCF-NetTcp adapter provides connected cross-computer or cross-process communication in an environment in which both services and clients are WCF based.</span></span> <span data-ttu-id="c36d1-105">它提供了对 SOAP 安全性、可靠性和事务功能的完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="c36d1-105">It provides full access to SOAP security, reliability, and transaction features.</span></span> <span data-ttu-id="c36d1-106">此适配器使用 TCP 传输，消息采用二进制编码。</span><span class="sxs-lookup"><span data-stu-id="c36d1-106">This adapter uses the TCP transport, and messages have binary encoding.</span></span>  
  
 <span data-ttu-id="c36d1-107">下表总结了 WCF-NetTcp 适配器的特征。</span><span class="sxs-lookup"><span data-stu-id="c36d1-107">The following table summarizes the characteristics of the WCF-NetTcp adapter.</span></span>  
  
|<span data-ttu-id="c36d1-108">Description</span><span class="sxs-lookup"><span data-stu-id="c36d1-108">Description</span></span>|<span data-ttu-id="c36d1-109">特征</span><span class="sxs-lookup"><span data-stu-id="c36d1-109">Characteristic</span></span>|  
|-----------------|--------------------|  
|<span data-ttu-id="c36d1-110">互操作性水平</span><span class="sxs-lookup"><span data-stu-id="c36d1-110">Interoperability level</span></span>|<span data-ttu-id="c36d1-111">.NET 配置文件</span><span class="sxs-lookup"><span data-stu-id="c36d1-111">.NET-Profile</span></span>|  
|<span data-ttu-id="c36d1-112">消息编码</span><span class="sxs-lookup"><span data-stu-id="c36d1-112">Message encoding</span></span>|<span data-ttu-id="c36d1-113">二进制</span><span class="sxs-lookup"><span data-stu-id="c36d1-113">Binary</span></span>|  
|<span data-ttu-id="c36d1-114">边界</span><span class="sxs-lookup"><span data-stu-id="c36d1-114">Boundary</span></span>|<span data-ttu-id="c36d1-115">跨计算机或跨进程</span><span class="sxs-lookup"><span data-stu-id="c36d1-115">Cross-computer or cross-process</span></span>|  
|<span data-ttu-id="c36d1-116">传输协议</span><span class="sxs-lookup"><span data-stu-id="c36d1-116">Transport protocol</span></span>|<span data-ttu-id="c36d1-117">TCP</span><span class="sxs-lookup"><span data-stu-id="c36d1-117">TCP</span></span>|  
|<span data-ttu-id="c36d1-118">安全模式</span><span class="sxs-lookup"><span data-stu-id="c36d1-118">Security mode</span></span>|<span data-ttu-id="c36d1-119">无、消息、传输和 TransportWithMessageCredential。</span><span class="sxs-lookup"><span data-stu-id="c36d1-119">None, Message, Transport, and TransportWithMessageCredential.</span></span>|  
|<span data-ttu-id="c36d1-120">客户端身份验证机制</span><span class="sxs-lookup"><span data-stu-id="c36d1-120">Client authentication mechanism</span></span>|<span data-ttu-id="c36d1-121">传输安全性和消息安全性</span><span class="sxs-lookup"><span data-stu-id="c36d1-121">Transport Security and Message Security</span></span>|  
|<span data-ttu-id="c36d1-122">是否支持 WS-ReliableMessaging</span><span class="sxs-lookup"><span data-stu-id="c36d1-122">Support for WS-ReliableMessaging</span></span>|<span data-ttu-id="c36d1-123">是</span><span class="sxs-lookup"><span data-stu-id="c36d1-123">No</span></span>|  
|<span data-ttu-id="c36d1-124">是否支持 WS-AtomicTransaction</span><span class="sxs-lookup"><span data-stu-id="c36d1-124">Support for WS-AtomicTransaction</span></span>|<span data-ttu-id="c36d1-125">是</span><span class="sxs-lookup"><span data-stu-id="c36d1-125">Yes</span></span>|  
|<span data-ttu-id="c36d1-126">支持单向消息传送</span><span class="sxs-lookup"><span data-stu-id="c36d1-126">Support for one-way messaging</span></span>|<span data-ttu-id="c36d1-127">是</span><span class="sxs-lookup"><span data-stu-id="c36d1-127">Yes</span></span>|  
|<span data-ttu-id="c36d1-128">支持双向消息传送</span><span class="sxs-lookup"><span data-stu-id="c36d1-128">Support for two-way messaging</span></span>|<span data-ttu-id="c36d1-129">是</span><span class="sxs-lookup"><span data-stu-id="c36d1-129">Yes</span></span>|  
|<span data-ttu-id="c36d1-130">接收适配器的主机类型</span><span class="sxs-lookup"><span data-stu-id="c36d1-130">Host type for receive adapter</span></span>|<span data-ttu-id="c36d1-131">进程内</span><span class="sxs-lookup"><span data-stu-id="c36d1-131">In-process</span></span>|  
|<span data-ttu-id="c36d1-132">发送适配器的主机类型</span><span class="sxs-lookup"><span data-stu-id="c36d1-132">Host type for send adapter</span></span>|<span data-ttu-id="c36d1-133">进程内</span><span class="sxs-lookup"><span data-stu-id="c36d1-133">In-process</span></span>|  
  
 <span data-ttu-id="c36d1-134">WCF-NetTcp 适配器由两个适配器组成：一个接收适配器和一个发送适配器。</span><span class="sxs-lookup"><span data-stu-id="c36d1-134">The WCF-NetTcp adapter consists of two adapters—a receive adapter and a send adapter.</span></span>  
  
 <span data-ttu-id="c36d1-135">**WCF NetTcp 接收适配器**</span><span class="sxs-lookup"><span data-stu-id="c36d1-135">**WCF-NetTcp Receive Adapter**</span></span>  
  
 <span data-ttu-id="c36d1-136">您可使用 WCF-NetTcp 接收适配器通过 TCP 协议接收 WCF 服务请求。</span><span class="sxs-lookup"><span data-stu-id="c36d1-136">You use the WCF-NetTcp receive adapter to receive WCF service requests through the TCP protocol.</span></span> <span data-ttu-id="c36d1-137">使用 WCF-NetTcp 接收适配器的接收位置可以配置为单向或请求-响应（双向）。</span><span class="sxs-lookup"><span data-stu-id="c36d1-137">A receive location that uses the WCF-NetTcp receive adapter can be configured as one-way or request-response (two-way).</span></span>  
  
 <span data-ttu-id="c36d1-138">**WCF NetTcp 发送适配器**</span><span class="sxs-lookup"><span data-stu-id="c36d1-138">**WCF-NetTcp Send Adapter**</span></span>  
  
 <span data-ttu-id="c36d1-139">您可使用 WCF-NetTcp 发送适配器及 TCP 协议通过无类型约定调用 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="c36d1-139">You use the WCF-NetTcp send adapter to call a WCF service through the typeless contract by using the TCP protocol.</span></span>  
  
 <span data-ttu-id="c36d1-140">有关 WCF 的详细信息接收和发送适配器，请参阅[WCF 适配器是什么？](../core/what-are-the-wcf-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="c36d1-140">For more information about WCF receive and send adapters, see [What Are the WCF Adapters?](../core/what-are-the-wcf-adapters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c36d1-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c36d1-141">See Also</span></span>  
 <span data-ttu-id="c36d1-142">[配置 WCF NetTcp 适配器](../core/configuring-the-wcf-nettcp-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="c36d1-142">[Configuring the WCF-NetTcp Adapter](../core/configuring-the-wcf-nettcp-adapter.md) </span></span>  
 [<span data-ttu-id="c36d1-143">WCF 适配器</span><span class="sxs-lookup"><span data-stu-id="c36d1-143">WCF Adapters</span></span>](../core/wcf-adapters.md)