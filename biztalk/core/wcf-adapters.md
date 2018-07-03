---
title: WCF 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e64cd189-8805-4209-bd06-971363f38585
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c4980eb1045d12986ec486308231ab2f219445b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993806"
---
# <a name="wcf-adapters"></a><span data-ttu-id="acbdc-102">WCF 适配器</span><span class="sxs-lookup"><span data-stu-id="acbdc-102">WCF Adapters</span></span>

## <a name="overview"></a><span data-ttu-id="acbdc-103">概述</span><span class="sxs-lookup"><span data-stu-id="acbdc-103">Overview</span></span>
<span data-ttu-id="acbdc-104">用于 Windows Communication Foundation (WCF) 的 BizTalk 适配器允许 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 与基于 WCF 的应用程序通信。</span><span class="sxs-lookup"><span data-stu-id="acbdc-104">The BizTalk Adapters for Windows Communication Foundation (WCF) allow  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to communicate with WCF-based applications.</span></span> <span data-ttu-id="acbdc-105">BizTalk WCF 适配器包括五个物理适配器，分别表示 WCF 预定义绑定 —**BasicHttpBinding**， **WsHttpBinding**， **NetTcpBinding**， **NetNamedPipeBinding**，并**NetMsmqBinding**。</span><span class="sxs-lookup"><span data-stu-id="acbdc-105">The BizTalk WCF adapters include five physical adapters that represent the WCF predefined bindings—**BasicHttpBinding**, **WsHttpBinding**, **NetTcpBinding**, **NetNamedPipeBinding**, and **NetMsmqBinding**.</span></span> <span data-ttu-id="acbdc-106">通过用于预定义绑定的 WCF 适配器，您可以轻松配置大多数应用程序要求的必需信息。</span><span class="sxs-lookup"><span data-stu-id="acbdc-106">The WCF adapters for the predefined bindings are provided to enable you to easily configure necessary information for most application requirements.</span></span>  
  
 <span data-ttu-id="acbdc-107">BizTalk WCF 适配器还包括用于随意配置接收位置和发送端口的 WCF 绑定和行为信息的两个适配器。</span><span class="sxs-lookup"><span data-stu-id="acbdc-107">The BizTalk WCF adapters also include two adapters that enable you to freely configure WCF binding and behavior information for the receive location and send port.</span></span>  

## <a name="available-wcf-adapters"></a><span data-ttu-id="acbdc-108">可用的 WCF 适配器</span><span class="sxs-lookup"><span data-stu-id="acbdc-108">Available WCF adapters</span></span>
    
- <span data-ttu-id="acbdc-109">**Wcf-wshttp 适配器**。</span><span class="sxs-lookup"><span data-stu-id="acbdc-109">**WCF-WSHttp adapter**.</span></span> <span data-ttu-id="acbdc-110">通过 HTTP 传输提供对于 WS-\* 标准的支持。</span><span class="sxs-lookup"><span data-stu-id="acbdc-110">Provides the WS-\* standards support over the HTTP transport.</span></span> <span data-ttu-id="acbdc-111">WCF-WSHttp 适配器实现了下列规范：WS-Transaction（用来在外部应用程序和 MessageBox 数据库之间进行事务性交互）和 WS-Security（用来实现消息安全和身份验证）。</span><span class="sxs-lookup"><span data-stu-id="acbdc-111">The WCF-WSHttp adapter implements the following specifications: WS-Transaction for the transactional interactions between external applications and the MessageBox database, and WS-Security for message security and authentication.</span></span> <span data-ttu-id="acbdc-112">传输协议是 HTTP 或 HTTPS，消息编码是文本或消息传输优化机制 (MTOM) 编码。</span><span class="sxs-lookup"><span data-stu-id="acbdc-112">The transport is HTTP or HTTPS, and message encoding is a Text or Message Transmission Optimization Mechanism (MTOM) encoding.</span></span>  
  
- <span data-ttu-id="acbdc-113">**Wcf-basichttp 适配器**。</span><span class="sxs-lookup"><span data-stu-id="acbdc-113">**WCF-BasicHttp adapter**.</span></span> <span data-ttu-id="acbdc-114">与基于 ASMX 的 Web Services 以及符合 WS-I 基本配置文件 1.1 的客户端和其他服务进行通信。</span><span class="sxs-lookup"><span data-stu-id="acbdc-114">Communicates with ASMX-based Web services and clients and other services that conform to the WS-I Basic Profile 1.1.</span></span> <span data-ttu-id="acbdc-115">传输协议是 HTTP 或 HTTPS，消息编码是文本编码。</span><span class="sxs-lookup"><span data-stu-id="acbdc-115">The transport is HTTP or HTTPS, and message encoding is a text encoding.</span></span>  
  
- <span data-ttu-id="acbdc-116">**Wcf-nettcp 适配器**。</span><span class="sxs-lookup"><span data-stu-id="acbdc-116">**WCF-NetTcp adapter**.</span></span> <span data-ttu-id="acbdc-117">通过 TCP 传输提供对 WS-\* 标准的支持。</span><span class="sxs-lookup"><span data-stu-id="acbdc-117">Provides the WS-\* standards support over the TCP transport.</span></span> <span data-ttu-id="acbdc-118">WCF-NetTcp 适配器可在 WCF 到 WCF 环境中提供有效的通信。</span><span class="sxs-lookup"><span data-stu-id="acbdc-118">The WCF-NetTcp adapter provides efficient communication in a WCF-to-WCF environment.</span></span> <span data-ttu-id="acbdc-119">该适配器实现了下列规范： Ws-transaction 之间外部应用程序和 MessageBox 数据库和 Ws-security 的消息安全性和身份验证的事务交互。</span><span class="sxs-lookup"><span data-stu-id="acbdc-119">The adapter implements the following specifications: WS-Transaction for the transactional interactions between external applications and the MessageBox database, and WS-Security for message security and authentication.</span></span> <span data-ttu-id="acbdc-120">传输协议是 TCP，和消息编码是二进制编码。</span><span class="sxs-lookup"><span data-stu-id="acbdc-120">The transport is TCP, and message encoding is binary encoding.</span></span>  
  
- <span data-ttu-id="acbdc-121">**Wcf-netmsmq 适配器**。</span><span class="sxs-lookup"><span data-stu-id="acbdc-121">**WCF-NetMsmq adapter**.</span></span> <span data-ttu-id="acbdc-122">使用 [!INCLUDE[btsCoName](../includes/btsconame-md.md)] 消息队列 (MSMQ) 作为传输手段来提供队列支持，同时还提供对松散耦合应用程序、故障隔离、负载级别划分和脱机操作的支持。</span><span class="sxs-lookup"><span data-stu-id="acbdc-122">Provides support for queuing by leveraging [!INCLUDE[btsCoName](../includes/btsconame-md.md)] Message Queuing (MSMQ) as a transport and enables support for loosely coupled applications, failure isolation, load leveling, and disconnected operations.</span></span>  
  
- <span data-ttu-id="acbdc-123">**Wcf-netnamedpipe 适配器**。</span><span class="sxs-lookup"><span data-stu-id="acbdc-123">**WCF-NetNamedPipe adapter**.</span></span> <span data-ttu-id="acbdc-124">对计算机上的跨进程通信提供了安全优化。</span><span class="sxs-lookup"><span data-stu-id="acbdc-124">Provides secure optimization for on-machine cross-process communication.</span></span> <span data-ttu-id="acbdc-125">WCF-NetNamedPipe 适配器使用传输安全性保证传输安全，使用命名管道进行消息传送，并且使用二进制消息编码方式。</span><span class="sxs-lookup"><span data-stu-id="acbdc-125">The WCF-NetNamedPipe adapter uses transport security for transfer security, named pipes for message delivery, and binary message encoding.</span></span>  
  
- <span data-ttu-id="acbdc-126">**WCF 自定义适配器**。</span><span class="sxs-lookup"><span data-stu-id="acbdc-126">**WCF-Custom adapter**.</span></span> <span data-ttu-id="acbdc-127">允许使用 WCF 扩展功能。</span><span class="sxs-lookup"><span data-stu-id="acbdc-127">Enables the use of WCF extensibility features.</span></span> <span data-ttu-id="acbdc-128">用户使用此适配器可以为接收位置和发送端口选择并配置 WCF 绑定和行为信息。</span><span class="sxs-lookup"><span data-stu-id="acbdc-128">The adapter allows you to select and configure a WCF binding and the behavior information for the receive location and send port.</span></span>  
  
- <span data-ttu-id="acbdc-129">**Wcf-customisolated 适配器**。</span><span class="sxs-lookup"><span data-stu-id="acbdc-129">**WCF-CustomIsolated adapter**.</span></span> <span data-ttu-id="acbdc-130">允许通过 HTTP 传输使用 WCF 扩展功能。</span><span class="sxs-lookup"><span data-stu-id="acbdc-130">Enables the use of WCF extensibility features over the HTTP transport.</span></span> <span data-ttu-id="acbdc-131">使用该适配器，可以为运行于独立主机上的接收位置选择和配置 WCF 绑定和行为信息。</span><span class="sxs-lookup"><span data-stu-id="acbdc-131">The adapter allows you to select and configure a WCF binding and the behavior information for the receive location running in an isolated host.</span></span>  
  
  <span data-ttu-id="acbdc-132">此外，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提供 BizTalk WCF 服务发布向导和 BizTalk WCF 服务使用向导。</span><span class="sxs-lookup"><span data-stu-id="acbdc-132">In addition, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] provides the BizTalk WCF Service Publishing Wizard and the BizTalk WCF Service Consuming Wizard.</span></span> <span data-ttu-id="acbdc-133">可以使用 BizTalk WCF 服务发布向导创建 BizTalk 业务流程并将其发布为 WCF 服务，还可以将架构发布为 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="acbdc-133">You can use the BizTalk WCF Service Publishing Wizard to create and publish BizTalk orchestrations as WCF services, and to publish schemas as WCF services.</span></span> <span data-ttu-id="acbdc-134">可以使用 BizTalk WCF 服务使用向导生成 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 项目，如业务流程和类型，以便基于 WCF 服务的元数据文档使用 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="acbdc-134">You can use the BizTalk WCF Service Consuming Wizard to generate [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] artifacts, such as orchestrations and types, to consume a WCF service based on the metadata document of the WCF service.</span></span>  
  
  <span data-ttu-id="acbdc-135">本部分提供的资源有助于您配置和部署 WCF 适配器。</span><span class="sxs-lookup"><span data-stu-id="acbdc-135">This section provides resources to help you configure and deploy the WCF adapters.</span></span>  
  
## <a name="next"></a><span data-ttu-id="acbdc-136">Next</span><span class="sxs-lookup"><span data-stu-id="acbdc-136">Next</span></span> 
  
-   [<span data-ttu-id="acbdc-137">WCF 适配器概述</span><span class="sxs-lookup"><span data-stu-id="acbdc-137">What Are the WCF Adapters?</span></span>](../core/what-are-the-wcf-adapters.md)  
  
-   [<span data-ttu-id="acbdc-138">配置 WCF 适配器</span><span class="sxs-lookup"><span data-stu-id="acbdc-138">Configuring the WCF Adapters</span></span>](../core/configuring-the-wcf-adapters.md)  
  
-   [<span data-ttu-id="acbdc-139">WCF-BasicHttp 适配器</span><span class="sxs-lookup"><span data-stu-id="acbdc-139">WCF-BasicHttp Adapter</span></span>](../core/wcf-basichttp-adapter.md)  
  
-   [<span data-ttu-id="acbdc-140">WCF-WSHttp 适配器</span><span class="sxs-lookup"><span data-stu-id="acbdc-140">WCF-WSHttp Adapter</span></span>](../core/wcf-wshttp-adapter.md)  
  
-   [<span data-ttu-id="acbdc-141">WCF-NetTcp 适配器</span><span class="sxs-lookup"><span data-stu-id="acbdc-141">WCF-NetTcp Adapter</span></span>](../core/wcf-nettcp-adapter.md)  
  
-   [<span data-ttu-id="acbdc-142">WCF-NetMsmq 适配器</span><span class="sxs-lookup"><span data-stu-id="acbdc-142">WCF-NetMsmq Adapter</span></span>](../core/wcf-netmsmq-adapter.md)  
  
-   [<span data-ttu-id="acbdc-143">WCF-NetNamedPipe 适配器</span><span class="sxs-lookup"><span data-stu-id="acbdc-143">WCF-NetNamedPipe Adapter</span></span>](../core/wcf-netnamedpipe-adapter.md)  
  
-   [<span data-ttu-id="acbdc-144">WCF-Custom 适配器</span><span class="sxs-lookup"><span data-stu-id="acbdc-144">WCF-Custom Adapter</span></span>](../core/wcf-custom-adapter.md)  
  
-   [<span data-ttu-id="acbdc-145">WCF-CustomIsolated 适配器</span><span class="sxs-lookup"><span data-stu-id="acbdc-145">WCF-CustomIsolated Adapter</span></span>](../core/wcf-customisolated-adapter.md)  
  
## <a name="see-also"></a><span data-ttu-id="acbdc-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="acbdc-146">See Also</span></span>  
 [<span data-ttu-id="acbdc-147">使用 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="acbdc-147">Using WCF Services</span></span>](../core/using-wcf-services.md)   