---
title: 什么是 Wcf-netmsmq 适配器？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-NetMsmq adapters, about WCF-NetMsmq adapters
ms.assetid: 506c5e2d-6cbe-4788-8e37-49d009dc559a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ba6cfcba8858e894b83b5ec45fcd51406db93fcc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242782"
---
# <a name="what-is-the-wcf-netmsmq-adapter"></a><span data-ttu-id="5d292-103">什么是 Wcf-netmsmq 适配器？</span><span class="sxs-lookup"><span data-stu-id="5d292-103">What Is the WCF-NetMsmq Adapter?</span></span>
<span data-ttu-id="5d292-104">Wcf-netmsmq 适配器提供断开连接的跨计算机通信的服务和客户端都是基于 WCF 的环境中使用队列技术。</span><span class="sxs-lookup"><span data-stu-id="5d292-104">The WCF-NetMsmq adapter provides disconnected cross-computer communication by using queuing technology in an environment where both the services and clients are WCF based.</span></span> <span data-ttu-id="5d292-105">它使用消息队列 (MSMQ) 传输和消息采用二进制编码。</span><span class="sxs-lookup"><span data-stu-id="5d292-105">It uses the Message Queuing (MSMQ) transport, and messages have binary encoding.</span></span>  
  
 <span data-ttu-id="5d292-106">下表总结了 Wcf-netmsmq 适配器的特征。</span><span class="sxs-lookup"><span data-stu-id="5d292-106">The following table summarizes the characteristics for the WCF-NetMsmq adapter.</span></span>  
  
|<span data-ttu-id="5d292-107">Description</span><span class="sxs-lookup"><span data-stu-id="5d292-107">Description</span></span>|<span data-ttu-id="5d292-108">特征</span><span class="sxs-lookup"><span data-stu-id="5d292-108">Characteristic</span></span>|  
|-----------------|--------------------|  
|<span data-ttu-id="5d292-109">互操作性级别</span><span class="sxs-lookup"><span data-stu-id="5d292-109">Interoperability level</span></span>|<span data-ttu-id="5d292-110">.NET-Profile</span><span class="sxs-lookup"><span data-stu-id="5d292-110">.NET-Profile</span></span>|  
|<span data-ttu-id="5d292-111">消息编码</span><span class="sxs-lookup"><span data-stu-id="5d292-111">Message encoding</span></span>|<span data-ttu-id="5d292-112">Binary</span><span class="sxs-lookup"><span data-stu-id="5d292-112">Binary</span></span>|  
|<span data-ttu-id="5d292-113">边界</span><span class="sxs-lookup"><span data-stu-id="5d292-113">Boundary</span></span>|<span data-ttu-id="5d292-114">跨计算机</span><span class="sxs-lookup"><span data-stu-id="5d292-114">Cross-computer</span></span>|  
|<span data-ttu-id="5d292-115">传输协议</span><span class="sxs-lookup"><span data-stu-id="5d292-115">Transport protocol</span></span>|<span data-ttu-id="5d292-116">MSMQ</span><span class="sxs-lookup"><span data-stu-id="5d292-116">MSMQ</span></span>|  
|<span data-ttu-id="5d292-117">安全模式</span><span class="sxs-lookup"><span data-stu-id="5d292-117">Security mode</span></span>|<span data-ttu-id="5d292-118">无、 消息、 传输，以及两者。</span><span class="sxs-lookup"><span data-stu-id="5d292-118">None, Message, Transport, and Both.</span></span>|  
|<span data-ttu-id="5d292-119">客户端身份验证机制</span><span class="sxs-lookup"><span data-stu-id="5d292-119">Client authentication mechanism</span></span>|<span data-ttu-id="5d292-120">传输安全和消息安全</span><span class="sxs-lookup"><span data-stu-id="5d292-120">Transport Security and Message Security</span></span>|  
|<span data-ttu-id="5d292-121">支持 WS-ReliableMessaging</span><span class="sxs-lookup"><span data-stu-id="5d292-121">Support for WS-ReliableMessaging</span></span>|<span data-ttu-id="5d292-122">不适用</span><span class="sxs-lookup"><span data-stu-id="5d292-122">Not applicable</span></span>|  
|<span data-ttu-id="5d292-123">支持 WS-AtomicTransaction</span><span class="sxs-lookup"><span data-stu-id="5d292-123">Support for WS-AtomicTransaction</span></span>|<span data-ttu-id="5d292-124">是</span><span class="sxs-lookup"><span data-stu-id="5d292-124">Yes</span></span>|  
|<span data-ttu-id="5d292-125">支持单向消息传送</span><span class="sxs-lookup"><span data-stu-id="5d292-125">Support for one-way messaging</span></span>|<span data-ttu-id="5d292-126">是</span><span class="sxs-lookup"><span data-stu-id="5d292-126">Yes</span></span>|  
|<span data-ttu-id="5d292-127">支持双向消息传送</span><span class="sxs-lookup"><span data-stu-id="5d292-127">Support for two-way messaging</span></span>|<span data-ttu-id="5d292-128">否</span><span class="sxs-lookup"><span data-stu-id="5d292-128">No</span></span>|  
|<span data-ttu-id="5d292-129">主机类型的接收适配器</span><span class="sxs-lookup"><span data-stu-id="5d292-129">Host type for receive adapter</span></span>|<span data-ttu-id="5d292-130">进程内</span><span class="sxs-lookup"><span data-stu-id="5d292-130">In-process</span></span>|  
|<span data-ttu-id="5d292-131">发送适配器的主机类型</span><span class="sxs-lookup"><span data-stu-id="5d292-131">Host type for send adapter</span></span>|<span data-ttu-id="5d292-132">进程内</span><span class="sxs-lookup"><span data-stu-id="5d292-132">In-process</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="5d292-133">必须提前创建 Wcf-netmsmq 接收适配器提取消息的队列。</span><span class="sxs-lookup"><span data-stu-id="5d292-133">The queues from which the WCF-NetMsmq receive adapter pulls messages must be created in advance.</span></span> <span data-ttu-id="5d292-134">队列中的消息必须是基于; WCF否则，这些消息将发送到死信队列。</span><span class="sxs-lookup"><span data-stu-id="5d292-134">The messages in the queues must be WCF based; otherwise, these messages will be sent to the dead-letter queue.</span></span>  
  
 <span data-ttu-id="5d292-135">Wcf-netmsmq 适配器由两个适配器组成： 一个接收适配器和一个发送适配器。</span><span class="sxs-lookup"><span data-stu-id="5d292-135">The WCF-NetMsmq adapter consists of two adapters—a receive adapter and a send adapter.</span></span>  
  
 <span data-ttu-id="5d292-136">**Wcf-netmsmq 接收适配器**</span><span class="sxs-lookup"><span data-stu-id="5d292-136">**WCF-NetMsmq Receive Adapter**</span></span>  
  
 <span data-ttu-id="5d292-137">使用 Wcf-netmsmq 接收适配器通过 MSMQ 接收 WCF 服务请求。</span><span class="sxs-lookup"><span data-stu-id="5d292-137">You use the WCF-NetMsmq receive adapter to receive WCF service requests over MSMQ.</span></span> <span data-ttu-id="5d292-138">只能为使用 Wcf-netmsmq 接收适配器的接收位置配置为单向接收。</span><span class="sxs-lookup"><span data-stu-id="5d292-138">A receive location that uses the WCF-NetMsmq receive adapter can only be configured as one-way receive.</span></span>  
  
 <span data-ttu-id="5d292-139">**Wcf-netmsmq 发送适配器**</span><span class="sxs-lookup"><span data-stu-id="5d292-139">**WCF-NetMsmq Send Adapter**</span></span>  
  
 <span data-ttu-id="5d292-140">使用 Wcf-netmsmq 发送适配器通过无类型协定的 WCF 服务调用通过 MSMQ。</span><span class="sxs-lookup"><span data-stu-id="5d292-140">You use the WCF-NetMsmq send adapter to call a WCF service through the typeless contract over MSMQ.</span></span>  
  
 <span data-ttu-id="5d292-141">有关 WCF 接收和发送适配器，请参阅[WCF 适配器是什么？](../core/what-are-the-wcf-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="5d292-141">For more information about WCF receive and send adapters, see [What Are the WCF Adapters?](../core/what-are-the-wcf-adapters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d292-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="5d292-142">See Also</span></span>  
 <span data-ttu-id="5d292-143">[配置 Wcf-netmsmq 适配器](../core/configuring-the-wcf-netmsmq-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="5d292-143">[Configuring the WCF-NetMsmq Adapter](../core/configuring-the-wcf-netmsmq-adapter.md) </span></span>  
 [<span data-ttu-id="5d292-144">WCF 适配器</span><span class="sxs-lookup"><span data-stu-id="5d292-144">WCF Adapters</span></span>](../core/wcf-adapters.md)