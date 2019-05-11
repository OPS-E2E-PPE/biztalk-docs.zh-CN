---
title: Wcf-netnamedpipe 适配器是什么？ | Microsoft Docs
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
ms.openlocfilehash: 01672c8babf30c99b8ba4d31069c836a46b18630
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242743"
---
# <a name="what-is-the-wcf-netnamedpipe-adapter"></a><span data-ttu-id="66e7f-103">Wcf-netnamedpipe 适配器是什么？</span><span class="sxs-lookup"><span data-stu-id="66e7f-103">What Is the WCF-NetNamedPipe Adapter?</span></span>
<span data-ttu-id="66e7f-104">Wcf-netnamedpipe 适配器服务和客户端是基于 WCF 的环境中的同一计算机上提供跨进程通信。</span><span class="sxs-lookup"><span data-stu-id="66e7f-104">The WCF-NetNamedPipe adapter provides cross-process communication on the same computer in an environment in which both services and clients are WCF based.</span></span> <span data-ttu-id="66e7f-105">它提供对 SOAP 可靠性和事务功能的完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="66e7f-105">It provides full access to SOAP reliability and transaction features.</span></span> <span data-ttu-id="66e7f-106">适配器使用命名的管道传输和消息采用二进制编码。</span><span class="sxs-lookup"><span data-stu-id="66e7f-106">The adapter uses the named pipe transport, and messages have binary encoding.</span></span> <span data-ttu-id="66e7f-107">此适配器不能用在跨计算机通信。</span><span class="sxs-lookup"><span data-stu-id="66e7f-107">This adapter cannot be used in cross-computer communication.</span></span>  
  
 <span data-ttu-id="66e7f-108">下表总结了 Wcf-netnamedpipe 适配器的特征。</span><span class="sxs-lookup"><span data-stu-id="66e7f-108">The following table summarizes the characteristics for the WCF-NetNamedPipe adapter.</span></span>  
  
|<span data-ttu-id="66e7f-109">Description</span><span class="sxs-lookup"><span data-stu-id="66e7f-109">Description</span></span>|<span data-ttu-id="66e7f-110">特征</span><span class="sxs-lookup"><span data-stu-id="66e7f-110">Characteristic</span></span>|  
|-----------------|--------------------|  
|<span data-ttu-id="66e7f-111">互操作性级别</span><span class="sxs-lookup"><span data-stu-id="66e7f-111">Interoperability level</span></span>|<span data-ttu-id="66e7f-112">.NET-Profile</span><span class="sxs-lookup"><span data-stu-id="66e7f-112">.NET-Profile</span></span>|  
|<span data-ttu-id="66e7f-113">消息编码</span><span class="sxs-lookup"><span data-stu-id="66e7f-113">Message encoding</span></span>|<span data-ttu-id="66e7f-114">Binary</span><span class="sxs-lookup"><span data-stu-id="66e7f-114">Binary</span></span>|  
|<span data-ttu-id="66e7f-115">边界</span><span class="sxs-lookup"><span data-stu-id="66e7f-115">Boundary</span></span>|<span data-ttu-id="66e7f-116">跨进程</span><span class="sxs-lookup"><span data-stu-id="66e7f-116">Cross-process</span></span>|  
|<span data-ttu-id="66e7f-117">传输协议</span><span class="sxs-lookup"><span data-stu-id="66e7f-117">Transport protocol</span></span>|<span data-ttu-id="66e7f-118">命名的管道</span><span class="sxs-lookup"><span data-stu-id="66e7f-118">Named pipe</span></span>|  
|<span data-ttu-id="66e7f-119">安全模式</span><span class="sxs-lookup"><span data-stu-id="66e7f-119">Security mode</span></span>|<span data-ttu-id="66e7f-120">None 和传输</span><span class="sxs-lookup"><span data-stu-id="66e7f-120">None and Transport</span></span>|  
|<span data-ttu-id="66e7f-121">客户端身份验证机制</span><span class="sxs-lookup"><span data-stu-id="66e7f-121">Client authentication mechanism</span></span>|<span data-ttu-id="66e7f-122">传输安全和消息安全</span><span class="sxs-lookup"><span data-stu-id="66e7f-122">Transport Security and Message Security</span></span>|  
|<span data-ttu-id="66e7f-123">支持 WS-ReliableMessaging</span><span class="sxs-lookup"><span data-stu-id="66e7f-123">Support for WS-ReliableMessaging</span></span>|<span data-ttu-id="66e7f-124">否</span><span class="sxs-lookup"><span data-stu-id="66e7f-124">No</span></span>|  
|<span data-ttu-id="66e7f-125">支持 WS-AtomicTransaction</span><span class="sxs-lookup"><span data-stu-id="66e7f-125">Support for WS-AtomicTransaction</span></span>|<span data-ttu-id="66e7f-126">是</span><span class="sxs-lookup"><span data-stu-id="66e7f-126">Yes</span></span>|  
|<span data-ttu-id="66e7f-127">支持单向消息传送</span><span class="sxs-lookup"><span data-stu-id="66e7f-127">Support for one-way messaging</span></span>|<span data-ttu-id="66e7f-128">是</span><span class="sxs-lookup"><span data-stu-id="66e7f-128">Yes</span></span>|  
|<span data-ttu-id="66e7f-129">支持双向消息传送</span><span class="sxs-lookup"><span data-stu-id="66e7f-129">Support for two-way messaging</span></span>|<span data-ttu-id="66e7f-130">是</span><span class="sxs-lookup"><span data-stu-id="66e7f-130">Yes</span></span>|  
|<span data-ttu-id="66e7f-131">主机类型的接收适配器</span><span class="sxs-lookup"><span data-stu-id="66e7f-131">Host type for receive adapter</span></span>|<span data-ttu-id="66e7f-132">进程内</span><span class="sxs-lookup"><span data-stu-id="66e7f-132">In-process</span></span>|  
|<span data-ttu-id="66e7f-133">发送适配器的主机类型</span><span class="sxs-lookup"><span data-stu-id="66e7f-133">Host type for send adapter</span></span>|<span data-ttu-id="66e7f-134">进程内</span><span class="sxs-lookup"><span data-stu-id="66e7f-134">In-process</span></span>|  
  
 <span data-ttu-id="66e7f-135">Wcf-netnamedpipe 适配器由两个适配器组成： 一个接收适配器和一个发送适配器。</span><span class="sxs-lookup"><span data-stu-id="66e7f-135">The WCF-NetNamedPipe adapter consists of two adapters—a receive adapter and a send adapter.</span></span>  
  
 <span data-ttu-id="66e7f-136">**Wcf-netnamedpipe 接收适配器**</span><span class="sxs-lookup"><span data-stu-id="66e7f-136">**WCF-NetNamedPipe Receive Adapter**</span></span>  
  
 <span data-ttu-id="66e7f-137">使用 Wcf-netnamedpipe 接收适配器通过命名的管道传输协议接收 WCF 服务请求。</span><span class="sxs-lookup"><span data-stu-id="66e7f-137">You use the WCF-NetNamedPipe receive adapter to receive WCF service requests over the named pipe transport.</span></span> <span data-ttu-id="66e7f-138">使用 Wcf-netnamedpipe 接收适配器的接收位置可以配置为单向或请求-响应 （双向）。</span><span class="sxs-lookup"><span data-stu-id="66e7f-138">A receive location that uses the WCF-NetNamedPipe receive adapter can be configured as one-way or request-response (two-way).</span></span>  
  
 <span data-ttu-id="66e7f-139">**Wcf-netnamedpipe 发送适配器**</span><span class="sxs-lookup"><span data-stu-id="66e7f-139">**WCF-NetNamedPipe Send Adapter**</span></span>  
  
 <span data-ttu-id="66e7f-140">使用 Wcf-netnamedpipe 发送适配器通过无类型协定的 WCF 服务调用通过命名的管道传输。</span><span class="sxs-lookup"><span data-stu-id="66e7f-140">You use the WCF-NetNamedPipe send adapter to call a WCF service through the typeless contract over the named pipe transport.</span></span>  
  
 <span data-ttu-id="66e7f-141">有关 WCF 接收和发送适配器，请参阅[WCF 适配器是什么？](../core/what-are-the-wcf-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="66e7f-141">For more information about WCF receive and send adapters, see [What Are the WCF Adapters?](../core/what-are-the-wcf-adapters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66e7f-142">请参阅</span><span class="sxs-lookup"><span data-stu-id="66e7f-142">See Also</span></span>  
 <span data-ttu-id="66e7f-143">[配置 Wcf-netnamedpipe 适配器](../core/configuring-the-wcf-netnamedpipe-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="66e7f-143">[Configuring the WCF-NetNamedPipe Adapter](../core/configuring-the-wcf-netnamedpipe-adapter.md) </span></span>  
 [<span data-ttu-id="66e7f-144">WCF 适配器</span><span class="sxs-lookup"><span data-stu-id="66e7f-144">WCF Adapters</span></span>](../core/wcf-adapters.md)