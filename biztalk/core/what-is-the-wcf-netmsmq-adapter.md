---
title: "什么是 WCF-NetMsmq 适配器？ | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF-NetMsmq adapters, about WCF-NetMsmq adapters
ms.assetid: 506c5e2d-6cbe-4788-8e37-49d009dc559a
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1008cc7178c38532f1781890080eacf4b5dfb56c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-wcf-netmsmq-adapter"></a><span data-ttu-id="d0262-103">什么是 WCF-NetMsmq 适配器？</span><span class="sxs-lookup"><span data-stu-id="d0262-103">What Is the WCF-NetMsmq Adapter?</span></span>
<span data-ttu-id="d0262-104">WCF-NetMsmq 适配器提供断开连接的跨计算机通信，方式是通过在服务和客户端都是基于 WCF 的环境中使用队列技术。</span><span class="sxs-lookup"><span data-stu-id="d0262-104">The WCF-NetMsmq adapter provides disconnected cross-computer communication by using queuing technology in an environment where both the services and clients are WCF based.</span></span> <span data-ttu-id="d0262-105">它使用消息队列 (MSMQ) 传输，而且消息采用二进制编码。</span><span class="sxs-lookup"><span data-stu-id="d0262-105">It uses the Message Queuing (MSMQ) transport, and messages have binary encoding.</span></span>  
  
 <span data-ttu-id="d0262-106">下表总结了 WCF-NetMsmq 适配器的特征。</span><span class="sxs-lookup"><span data-stu-id="d0262-106">The following table summarizes the characteristics for the WCF-NetMsmq adapter.</span></span>  
  
|<span data-ttu-id="d0262-107">Description</span><span class="sxs-lookup"><span data-stu-id="d0262-107">Description</span></span>|<span data-ttu-id="d0262-108">特征</span><span class="sxs-lookup"><span data-stu-id="d0262-108">Characteristic</span></span>|  
|-----------------|--------------------|  
|<span data-ttu-id="d0262-109">互操作性水平</span><span class="sxs-lookup"><span data-stu-id="d0262-109">Interoperability level</span></span>|<span data-ttu-id="d0262-110">.NET 配置文件</span><span class="sxs-lookup"><span data-stu-id="d0262-110">.NET-Profile</span></span>|  
|<span data-ttu-id="d0262-111">消息编码</span><span class="sxs-lookup"><span data-stu-id="d0262-111">Message encoding</span></span>|<span data-ttu-id="d0262-112">二进制</span><span class="sxs-lookup"><span data-stu-id="d0262-112">Binary</span></span>|  
|<span data-ttu-id="d0262-113">边界</span><span class="sxs-lookup"><span data-stu-id="d0262-113">Boundary</span></span>|<span data-ttu-id="d0262-114">跨计算机</span><span class="sxs-lookup"><span data-stu-id="d0262-114">Cross-computer</span></span>|  
|<span data-ttu-id="d0262-115">传输协议</span><span class="sxs-lookup"><span data-stu-id="d0262-115">Transport protocol</span></span>|<span data-ttu-id="d0262-116">MSMQ</span><span class="sxs-lookup"><span data-stu-id="d0262-116">MSMQ</span></span>|  
|<span data-ttu-id="d0262-117">安全模式</span><span class="sxs-lookup"><span data-stu-id="d0262-117">Security mode</span></span>|<span data-ttu-id="d0262-118">无、消息、传输或两者。</span><span class="sxs-lookup"><span data-stu-id="d0262-118">None, Message, Transport, and Both.</span></span>|  
|<span data-ttu-id="d0262-119">客户端身份验证机制</span><span class="sxs-lookup"><span data-stu-id="d0262-119">Client authentication mechanism</span></span>|<span data-ttu-id="d0262-120">传输安全性和消息安全性</span><span class="sxs-lookup"><span data-stu-id="d0262-120">Transport Security and Message Security</span></span>|  
|<span data-ttu-id="d0262-121">是否支持 WS-ReliableMessaging</span><span class="sxs-lookup"><span data-stu-id="d0262-121">Support for WS-ReliableMessaging</span></span>|<span data-ttu-id="d0262-122">不适用</span><span class="sxs-lookup"><span data-stu-id="d0262-122">Not applicable</span></span>|  
|<span data-ttu-id="d0262-123">是否支持 WS-AtomicTransaction</span><span class="sxs-lookup"><span data-stu-id="d0262-123">Support for WS-AtomicTransaction</span></span>|<span data-ttu-id="d0262-124">是</span><span class="sxs-lookup"><span data-stu-id="d0262-124">Yes</span></span>|  
|<span data-ttu-id="d0262-125">支持单向消息传送</span><span class="sxs-lookup"><span data-stu-id="d0262-125">Support for one-way messaging</span></span>|<span data-ttu-id="d0262-126">是</span><span class="sxs-lookup"><span data-stu-id="d0262-126">Yes</span></span>|  
|<span data-ttu-id="d0262-127">支持双向消息传送</span><span class="sxs-lookup"><span data-stu-id="d0262-127">Support for two-way messaging</span></span>|<span data-ttu-id="d0262-128">是</span><span class="sxs-lookup"><span data-stu-id="d0262-128">No</span></span>|  
|<span data-ttu-id="d0262-129">接收适配器的主机类型</span><span class="sxs-lookup"><span data-stu-id="d0262-129">Host type for receive adapter</span></span>|<span data-ttu-id="d0262-130">进程内</span><span class="sxs-lookup"><span data-stu-id="d0262-130">In-process</span></span>|  
|<span data-ttu-id="d0262-131">发送适配器的主机类型</span><span class="sxs-lookup"><span data-stu-id="d0262-131">Host type for send adapter</span></span>|<span data-ttu-id="d0262-132">进程内</span><span class="sxs-lookup"><span data-stu-id="d0262-132">In-process</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="d0262-133">必须提前创建 WCF-NetMsmq 接收适配器从其提取消息的队列。</span><span class="sxs-lookup"><span data-stu-id="d0262-133">The queues from which the WCF-NetMsmq receive adapter pulls messages must be created in advance.</span></span> <span data-ttu-id="d0262-134">队列中的消息必须基于 WCF；否则，这些消息将被发送到死信队列。</span><span class="sxs-lookup"><span data-stu-id="d0262-134">The messages in the queues must be WCF based; otherwise, these messages will be sent to the dead-letter queue.</span></span>  
  
 <span data-ttu-id="d0262-135">WCF NetMsmq 适配器包含两个适配器-接收适配器和一个发送适配器。</span><span class="sxs-lookup"><span data-stu-id="d0262-135">The WCF-NetMsmq adapter consists of two adapters—a receive adapter and a send adapter.</span></span>  
  
 <span data-ttu-id="d0262-136">**WCF NetMsmq 接收适配器**</span><span class="sxs-lookup"><span data-stu-id="d0262-136">**WCF-NetMsmq Receive Adapter**</span></span>  
  
 <span data-ttu-id="d0262-137">您可以使用 WCF-NetMsmq 接收适配器在 MSMQ 上接收 WCF 服务请求。</span><span class="sxs-lookup"><span data-stu-id="d0262-137">You use the WCF-NetMsmq receive adapter to receive WCF service requests over MSMQ.</span></span> <span data-ttu-id="d0262-138">使用 WCF-NetMsmq 接收适配器的接收位置只能配置为单向接收。</span><span class="sxs-lookup"><span data-stu-id="d0262-138">A receive location that uses the WCF-NetMsmq receive adapter can only be configured as one-way receive.</span></span>  
  
 <span data-ttu-id="d0262-139">**WCF NetMsmq 发送适配器**</span><span class="sxs-lookup"><span data-stu-id="d0262-139">**WCF-NetMsmq Send Adapter**</span></span>  
  
 <span data-ttu-id="d0262-140">您可以使用 WCF-NetMsmq 发送适配器在 MSMQ 上通过无类型的协定调用 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="d0262-140">You use the WCF-NetMsmq send adapter to call a WCF service through the typeless contract over MSMQ.</span></span>  
  
 <span data-ttu-id="d0262-141">有关 WCF 的详细信息接收和发送适配器，请参阅[WCF 适配器是什么？](../core/what-are-the-wcf-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="d0262-141">For more information about WCF receive and send adapters, see [What Are the WCF Adapters?](../core/what-are-the-wcf-adapters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0262-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d0262-142">See Also</span></span>  
 <span data-ttu-id="d0262-143">[配置 WCF NetMsmq 适配器](../core/configuring-the-wcf-netmsmq-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="d0262-143">[Configuring the WCF-NetMsmq Adapter](../core/configuring-the-wcf-netmsmq-adapter.md) </span></span>  
 [<span data-ttu-id="d0262-144">WCF 适配器</span><span class="sxs-lookup"><span data-stu-id="d0262-144">WCF Adapters</span></span>](../core/wcf-adapters.md)