---
title: 什么是 Wcf-nettcp 适配器？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-NetTcp adapters, about WCF-NetTcp adapters
ms.assetid: 94dc24df-19a1-4701-9012-59d05b0c8abd
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da209ab45dbb9458cd6be0d2e988fac7ea9270f9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242858"
---
# <a name="what-is-the-wcf-nettcp-adapter"></a><span data-ttu-id="ae776-103">什么是 Wcf-nettcp 适配器？</span><span class="sxs-lookup"><span data-stu-id="ae776-103">What Is the WCF-NetTcp Adapter?</span></span>
<span data-ttu-id="ae776-104">Wcf-nettcp 适配器提供了服务和客户端是基于 WCF 的环境中已连接的跨计算机或跨进程通信。</span><span class="sxs-lookup"><span data-stu-id="ae776-104">The WCF-NetTcp adapter provides connected cross-computer or cross-process communication in an environment in which both services and clients are WCF based.</span></span> <span data-ttu-id="ae776-105">它提供了 SOAP 安全性、 可靠性和事务功能的完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="ae776-105">It provides full access to SOAP security, reliability, and transaction features.</span></span> <span data-ttu-id="ae776-106">此适配器使用 TCP 传输和消息采用二进制编码。</span><span class="sxs-lookup"><span data-stu-id="ae776-106">This adapter uses the TCP transport, and messages have binary encoding.</span></span>  
  
 <span data-ttu-id="ae776-107">下表总结了 Wcf-nettcp 适配器的特征。</span><span class="sxs-lookup"><span data-stu-id="ae776-107">The following table summarizes the characteristics of the WCF-NetTcp adapter.</span></span>  
  
|<span data-ttu-id="ae776-108">Description</span><span class="sxs-lookup"><span data-stu-id="ae776-108">Description</span></span>|<span data-ttu-id="ae776-109">特征</span><span class="sxs-lookup"><span data-stu-id="ae776-109">Characteristic</span></span>|  
|-----------------|--------------------|  
|<span data-ttu-id="ae776-110">互操作性级别</span><span class="sxs-lookup"><span data-stu-id="ae776-110">Interoperability level</span></span>|<span data-ttu-id="ae776-111">.NET-Profile</span><span class="sxs-lookup"><span data-stu-id="ae776-111">.NET-Profile</span></span>|  
|<span data-ttu-id="ae776-112">消息编码</span><span class="sxs-lookup"><span data-stu-id="ae776-112">Message encoding</span></span>|<span data-ttu-id="ae776-113">Binary</span><span class="sxs-lookup"><span data-stu-id="ae776-113">Binary</span></span>|  
|<span data-ttu-id="ae776-114">边界</span><span class="sxs-lookup"><span data-stu-id="ae776-114">Boundary</span></span>|<span data-ttu-id="ae776-115">跨计算机或跨进程</span><span class="sxs-lookup"><span data-stu-id="ae776-115">Cross-computer or cross-process</span></span>|  
|<span data-ttu-id="ae776-116">传输协议</span><span class="sxs-lookup"><span data-stu-id="ae776-116">Transport protocol</span></span>|<span data-ttu-id="ae776-117">TCP</span><span class="sxs-lookup"><span data-stu-id="ae776-117">TCP</span></span>|  
|<span data-ttu-id="ae776-118">安全模式</span><span class="sxs-lookup"><span data-stu-id="ae776-118">Security mode</span></span>|<span data-ttu-id="ae776-119">无、 消息、 传输和 TransportWithMessageCredential。</span><span class="sxs-lookup"><span data-stu-id="ae776-119">None, Message, Transport, and TransportWithMessageCredential.</span></span>|  
|<span data-ttu-id="ae776-120">客户端身份验证机制</span><span class="sxs-lookup"><span data-stu-id="ae776-120">Client authentication mechanism</span></span>|<span data-ttu-id="ae776-121">传输安全和消息安全</span><span class="sxs-lookup"><span data-stu-id="ae776-121">Transport Security and Message Security</span></span>|  
|<span data-ttu-id="ae776-122">支持 WS-ReliableMessaging</span><span class="sxs-lookup"><span data-stu-id="ae776-122">Support for WS-ReliableMessaging</span></span>|<span data-ttu-id="ae776-123">否</span><span class="sxs-lookup"><span data-stu-id="ae776-123">No</span></span>|  
|<span data-ttu-id="ae776-124">支持 WS-AtomicTransaction</span><span class="sxs-lookup"><span data-stu-id="ae776-124">Support for WS-AtomicTransaction</span></span>|<span data-ttu-id="ae776-125">是</span><span class="sxs-lookup"><span data-stu-id="ae776-125">Yes</span></span>|  
|<span data-ttu-id="ae776-126">支持单向消息传送</span><span class="sxs-lookup"><span data-stu-id="ae776-126">Support for one-way messaging</span></span>|<span data-ttu-id="ae776-127">是</span><span class="sxs-lookup"><span data-stu-id="ae776-127">Yes</span></span>|  
|<span data-ttu-id="ae776-128">支持双向消息传送</span><span class="sxs-lookup"><span data-stu-id="ae776-128">Support for two-way messaging</span></span>|<span data-ttu-id="ae776-129">是</span><span class="sxs-lookup"><span data-stu-id="ae776-129">Yes</span></span>|  
|<span data-ttu-id="ae776-130">主机类型的接收适配器</span><span class="sxs-lookup"><span data-stu-id="ae776-130">Host type for receive adapter</span></span>|<span data-ttu-id="ae776-131">进程内</span><span class="sxs-lookup"><span data-stu-id="ae776-131">In-process</span></span>|  
|<span data-ttu-id="ae776-132">发送适配器的主机类型</span><span class="sxs-lookup"><span data-stu-id="ae776-132">Host type for send adapter</span></span>|<span data-ttu-id="ae776-133">进程内</span><span class="sxs-lookup"><span data-stu-id="ae776-133">In-process</span></span>|  
  
 <span data-ttu-id="ae776-134">Wcf-nettcp 适配器由两个适配器组成： 一个接收适配器和一个发送适配器。</span><span class="sxs-lookup"><span data-stu-id="ae776-134">The WCF-NetTcp adapter consists of two adapters—a receive adapter and a send adapter.</span></span>  
  
 <span data-ttu-id="ae776-135">**Wcf-nettcp 接收适配器**</span><span class="sxs-lookup"><span data-stu-id="ae776-135">**WCF-NetTcp Receive Adapter**</span></span>  
  
 <span data-ttu-id="ae776-136">使用 Wcf-nettcp 接收适配器接收通过 TCP 协议的 WCF 服务请求。</span><span class="sxs-lookup"><span data-stu-id="ae776-136">You use the WCF-NetTcp receive adapter to receive WCF service requests through the TCP protocol.</span></span> <span data-ttu-id="ae776-137">使用 Wcf-nettcp 接收适配器的接收位置可以配置为单向或请求-响应 （双向）。</span><span class="sxs-lookup"><span data-stu-id="ae776-137">A receive location that uses the WCF-NetTcp receive adapter can be configured as one-way or request-response (two-way).</span></span>  
  
 <span data-ttu-id="ae776-138">**Wcf-nettcp 发送适配器**</span><span class="sxs-lookup"><span data-stu-id="ae776-138">**WCF-NetTcp Send Adapter**</span></span>  
  
 <span data-ttu-id="ae776-139">使用 Wcf-nettcp 发送适配器通过无类型协定的 WCF 服务调用使用 TCP 协议。</span><span class="sxs-lookup"><span data-stu-id="ae776-139">You use the WCF-NetTcp send adapter to call a WCF service through the typeless contract by using the TCP protocol.</span></span>  
  
 <span data-ttu-id="ae776-140">有关 WCF 接收和发送适配器，请参阅[WCF 适配器是什么？](../core/what-are-the-wcf-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="ae776-140">For more information about WCF receive and send adapters, see [What Are the WCF Adapters?](../core/what-are-the-wcf-adapters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae776-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae776-141">See Also</span></span>  
 <span data-ttu-id="ae776-142">[配置 Wcf-nettcp 适配器](../core/configuring-the-wcf-nettcp-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="ae776-142">[Configuring the WCF-NetTcp Adapter](../core/configuring-the-wcf-nettcp-adapter.md) </span></span>  
 [<span data-ttu-id="ae776-143">WCF 适配器</span><span class="sxs-lookup"><span data-stu-id="ae776-143">WCF Adapters</span></span>](../core/wcf-adapters.md)