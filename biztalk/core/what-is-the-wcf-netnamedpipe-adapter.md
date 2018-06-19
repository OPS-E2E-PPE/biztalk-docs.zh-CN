---
title: WCF-NetNamedPipe 适配器概述 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-NetNamedPipe adapters, about WCF-NetNamedPipe adapters
ms.assetid: b9f84256-e49d-4ee2-b0fa-d3f692ade1d4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43c73a670139690c4a27d4784c6ad23225492f17
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289245"
---
# <a name="what-is-the-wcf-netnamedpipe-adapter"></a><span data-ttu-id="4420e-103">WCF-NetNamedPipe 适配器概述</span><span class="sxs-lookup"><span data-stu-id="4420e-103">What Is the WCF-NetNamedPipe Adapter?</span></span>
<span data-ttu-id="4420e-104">WCF-NetNamedPipe 适配器在服务和客户端都是基于 WCF 的环境中的同一计算机上提供跨进程通信。</span><span class="sxs-lookup"><span data-stu-id="4420e-104">The WCF-NetNamedPipe adapter provides cross-process communication on the same computer in an environment in which both services and clients are WCF based.</span></span> <span data-ttu-id="4420e-105">它提供了对 SOAP 可靠性和事务功能的完全访问。</span><span class="sxs-lookup"><span data-stu-id="4420e-105">It provides full access to SOAP reliability and transaction features.</span></span> <span data-ttu-id="4420e-106">适配器使用命名管道传输，消息采用二进制编码。</span><span class="sxs-lookup"><span data-stu-id="4420e-106">The adapter uses the named pipe transport, and messages have binary encoding.</span></span> <span data-ttu-id="4420e-107">此适配器无法用于计算机间的通信。</span><span class="sxs-lookup"><span data-stu-id="4420e-107">This adapter cannot be used in cross-computer communication.</span></span>  
  
 <span data-ttu-id="4420e-108">下表总结了 WCF-NetNamedPipe 适配器的特征。</span><span class="sxs-lookup"><span data-stu-id="4420e-108">The following table summarizes the characteristics for the WCF-NetNamedPipe adapter.</span></span>  
  
|<span data-ttu-id="4420e-109">Description</span><span class="sxs-lookup"><span data-stu-id="4420e-109">Description</span></span>|<span data-ttu-id="4420e-110">特征</span><span class="sxs-lookup"><span data-stu-id="4420e-110">Characteristic</span></span>|  
|-----------------|--------------------|  
|<span data-ttu-id="4420e-111">互操作性水平</span><span class="sxs-lookup"><span data-stu-id="4420e-111">Interoperability level</span></span>|<span data-ttu-id="4420e-112">.NET 配置文件</span><span class="sxs-lookup"><span data-stu-id="4420e-112">.NET-Profile</span></span>|  
|<span data-ttu-id="4420e-113">消息编码</span><span class="sxs-lookup"><span data-stu-id="4420e-113">Message encoding</span></span>|<span data-ttu-id="4420e-114">二进制</span><span class="sxs-lookup"><span data-stu-id="4420e-114">Binary</span></span>|  
|<span data-ttu-id="4420e-115">边界</span><span class="sxs-lookup"><span data-stu-id="4420e-115">Boundary</span></span>|<span data-ttu-id="4420e-116">跨进程</span><span class="sxs-lookup"><span data-stu-id="4420e-116">Cross-process</span></span>|  
|<span data-ttu-id="4420e-117">传输协议</span><span class="sxs-lookup"><span data-stu-id="4420e-117">Transport protocol</span></span>|<span data-ttu-id="4420e-118">命名的管道</span><span class="sxs-lookup"><span data-stu-id="4420e-118">Named pipe</span></span>|  
|<span data-ttu-id="4420e-119">安全模式</span><span class="sxs-lookup"><span data-stu-id="4420e-119">Security mode</span></span>|<span data-ttu-id="4420e-120">“无”和“传输”</span><span class="sxs-lookup"><span data-stu-id="4420e-120">None and Transport</span></span>|  
|<span data-ttu-id="4420e-121">客户端身份验证机制</span><span class="sxs-lookup"><span data-stu-id="4420e-121">Client authentication mechanism</span></span>|<span data-ttu-id="4420e-122">传输安全性和消息安全性</span><span class="sxs-lookup"><span data-stu-id="4420e-122">Transport Security and Message Security</span></span>|  
|<span data-ttu-id="4420e-123">是否支持 WS-ReliableMessaging</span><span class="sxs-lookup"><span data-stu-id="4420e-123">Support for WS-ReliableMessaging</span></span>|<span data-ttu-id="4420e-124">是</span><span class="sxs-lookup"><span data-stu-id="4420e-124">No</span></span>|  
|<span data-ttu-id="4420e-125">是否支持 WS-AtomicTransaction</span><span class="sxs-lookup"><span data-stu-id="4420e-125">Support for WS-AtomicTransaction</span></span>|<span data-ttu-id="4420e-126">是</span><span class="sxs-lookup"><span data-stu-id="4420e-126">Yes</span></span>|  
|<span data-ttu-id="4420e-127">支持单向消息传送</span><span class="sxs-lookup"><span data-stu-id="4420e-127">Support for one-way messaging</span></span>|<span data-ttu-id="4420e-128">是</span><span class="sxs-lookup"><span data-stu-id="4420e-128">Yes</span></span>|  
|<span data-ttu-id="4420e-129">支持双向消息传送</span><span class="sxs-lookup"><span data-stu-id="4420e-129">Support for two-way messaging</span></span>|<span data-ttu-id="4420e-130">是</span><span class="sxs-lookup"><span data-stu-id="4420e-130">Yes</span></span>|  
|<span data-ttu-id="4420e-131">接收适配器的主机类型</span><span class="sxs-lookup"><span data-stu-id="4420e-131">Host type for receive adapter</span></span>|<span data-ttu-id="4420e-132">进程内</span><span class="sxs-lookup"><span data-stu-id="4420e-132">In-process</span></span>|  
|<span data-ttu-id="4420e-133">发送适配器的主机类型</span><span class="sxs-lookup"><span data-stu-id="4420e-133">Host type for send adapter</span></span>|<span data-ttu-id="4420e-134">进程内</span><span class="sxs-lookup"><span data-stu-id="4420e-134">In-process</span></span>|  
  
 <span data-ttu-id="4420e-135">WCF-NetNamedPipe 适配器由两个适配器组成：一个接收适配器和一个发送适配器。</span><span class="sxs-lookup"><span data-stu-id="4420e-135">The WCF-NetNamedPipe adapter consists of two adapters—a receive adapter and a send adapter.</span></span>  
  
 <span data-ttu-id="4420e-136">**WCF NetNamedPipe 接收适配器**</span><span class="sxs-lookup"><span data-stu-id="4420e-136">**WCF-NetNamedPipe Receive Adapter**</span></span>  
  
 <span data-ttu-id="4420e-137">您可以使用 WCF-NetNamedPipe 接收适配器通过命名管道传输来接收 WCF 服务请求。</span><span class="sxs-lookup"><span data-stu-id="4420e-137">You use the WCF-NetNamedPipe receive adapter to receive WCF service requests over the named pipe transport.</span></span> <span data-ttu-id="4420e-138">使用 WCF-NetNamedPipe 接收适配器的接收位置可以配置为单向或请求-响应（双向）。</span><span class="sxs-lookup"><span data-stu-id="4420e-138">A receive location that uses the WCF-NetNamedPipe receive adapter can be configured as one-way or request-response (two-way).</span></span>  
  
 <span data-ttu-id="4420e-139">**WCF NetNamedPipe 发送适配器**</span><span class="sxs-lookup"><span data-stu-id="4420e-139">**WCF-NetNamedPipe Send Adapter**</span></span>  
  
 <span data-ttu-id="4420e-140">借助命名管道传输，您可以使用 WCF-NetNamedPipe 发送适配器通过无类型约定调用 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="4420e-140">You use the WCF-NetNamedPipe send adapter to call a WCF service through the typeless contract over the named pipe transport.</span></span>  
  
 <span data-ttu-id="4420e-141">有关 WCF 的详细信息接收和发送适配器，请参阅[WCF 适配器是什么？](../core/what-are-the-wcf-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="4420e-141">For more information about WCF receive and send adapters, see [What Are the WCF Adapters?](../core/what-are-the-wcf-adapters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4420e-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4420e-142">See Also</span></span>  
 <span data-ttu-id="4420e-143">[配置 WCF NetNamedPipe 适配器](../core/configuring-the-wcf-netnamedpipe-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="4420e-143">[Configuring the WCF-NetNamedPipe Adapter](../core/configuring-the-wcf-netnamedpipe-adapter.md) </span></span>  
 [<span data-ttu-id="4420e-144">WCF 适配器</span><span class="sxs-lookup"><span data-stu-id="4420e-144">WCF Adapters</span></span>](../core/wcf-adapters.md)