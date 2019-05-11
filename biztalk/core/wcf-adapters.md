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
ms.openlocfilehash: 716154cbc315c24f7a6a3cd65f9d26a7dfe2fa54
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399423"
---
# <a name="wcf-adapters"></a><span data-ttu-id="34934-102">WCF 适配器</span><span class="sxs-lookup"><span data-stu-id="34934-102">WCF Adapters</span></span>

## <a name="overview"></a><span data-ttu-id="34934-103">概述</span><span class="sxs-lookup"><span data-stu-id="34934-103">Overview</span></span>
<span data-ttu-id="34934-104">BizTalk 适配器的 Windows Communication Foundation (WCF) 允许[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与基于 WCF 的应用程序进行通信。</span><span class="sxs-lookup"><span data-stu-id="34934-104">The BizTalk Adapters for Windows Communication Foundation (WCF) allow  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to communicate with WCF-based applications.</span></span> <span data-ttu-id="34934-105">BizTalk WCF 适配器包括五个物理适配器，分别表示 WCF 预定义绑定 —**BasicHttpBinding**， **WsHttpBinding**， **NetTcpBinding**， **NetNamedPipeBinding**，并**NetMsmqBinding**。</span><span class="sxs-lookup"><span data-stu-id="34934-105">The BizTalk WCF adapters include five physical adapters that represent the WCF predefined bindings—**BasicHttpBinding**, **WsHttpBinding**, **NetTcpBinding**, **NetNamedPipeBinding**, and **NetMsmqBinding**.</span></span> <span data-ttu-id="34934-106">预定义绑定的 WCF 适配器提供以便您可以轻松配置大多数应用程序要求所需的信息。</span><span class="sxs-lookup"><span data-stu-id="34934-106">The WCF adapters for the predefined bindings are provided to enable you to easily configure necessary information for most application requirements.</span></span>  
  
 <span data-ttu-id="34934-107">BizTalk WCF 适配器还包括两个适配器，您可以自由地配置 WCF 绑定和行为信息的接收位置和发送端口。</span><span class="sxs-lookup"><span data-stu-id="34934-107">The BizTalk WCF adapters also include two adapters that enable you to freely configure WCF binding and behavior information for the receive location and send port.</span></span>  

## <a name="available-wcf-adapters"></a><span data-ttu-id="34934-108">可用的 WCF 适配器</span><span class="sxs-lookup"><span data-stu-id="34934-108">Available WCF adapters</span></span>
    
- <span data-ttu-id="34934-109">**Wcf-wshttp 适配器**。</span><span class="sxs-lookup"><span data-stu-id="34934-109">**WCF-WSHttp adapter**.</span></span> <span data-ttu-id="34934-110">提供对于 WS-\* 标准的支持通过 HTTP 传输。</span><span class="sxs-lookup"><span data-stu-id="34934-110">Provides the WS-\* standards support over the HTTP transport.</span></span> <span data-ttu-id="34934-111">Wcf-wshttp 适配器实现了下列规范：WS 事务之间外部应用程序和 MessageBox 数据库和 Ws-security 的消息安全性和身份验证的事务交互。</span><span class="sxs-lookup"><span data-stu-id="34934-111">The WCF-WSHttp adapter implements the following specifications: WS-Transaction for the transactional interactions between external applications and the MessageBox database, and WS-Security for message security and authentication.</span></span> <span data-ttu-id="34934-112">传输协议是 HTTP 或 HTTPS，并且消息编码是文本或消息传输优化机制 (MTOM) 编码。</span><span class="sxs-lookup"><span data-stu-id="34934-112">The transport is HTTP or HTTPS, and message encoding is a Text or Message Transmission Optimization Mechanism (MTOM) encoding.</span></span>  
  
- <span data-ttu-id="34934-113">**Wcf-basichttp 适配器**。</span><span class="sxs-lookup"><span data-stu-id="34934-113">**WCF-BasicHttp adapter**.</span></span> <span data-ttu-id="34934-114">与基于 ASMX 的 Web 服务和客户端以及符合 WS 其他服务进行通信的基本配置文件 1.1。</span><span class="sxs-lookup"><span data-stu-id="34934-114">Communicates with ASMX-based Web services and clients and other services that conform to the WS-I Basic Profile 1.1.</span></span> <span data-ttu-id="34934-115">传输协议是 HTTP 或 HTTPS，并且消息编码是文本编码。</span><span class="sxs-lookup"><span data-stu-id="34934-115">The transport is HTTP or HTTPS, and message encoding is a text encoding.</span></span>  
  
- <span data-ttu-id="34934-116">**Wcf-nettcp 适配器**。</span><span class="sxs-lookup"><span data-stu-id="34934-116">**WCF-NetTcp adapter**.</span></span> <span data-ttu-id="34934-117">提供对于 WS-\* 标准的支持通过 TCP 传输。</span><span class="sxs-lookup"><span data-stu-id="34934-117">Provides the WS-\* standards support over the TCP transport.</span></span> <span data-ttu-id="34934-118">Wcf-nettcp 适配器提供了在 WCF 到 WCF 环境中有效的通信。</span><span class="sxs-lookup"><span data-stu-id="34934-118">The WCF-NetTcp adapter provides efficient communication in a WCF-to-WCF environment.</span></span> <span data-ttu-id="34934-119">该适配器实现了下列规范：WS 事务之间外部应用程序和 MessageBox 数据库和 Ws-security 的消息安全性和身份验证的事务交互。</span><span class="sxs-lookup"><span data-stu-id="34934-119">The adapter implements the following specifications: WS-Transaction for the transactional interactions between external applications and the MessageBox database, and WS-Security for message security and authentication.</span></span> <span data-ttu-id="34934-120">传输协议是 TCP，和消息编码是二进制编码。</span><span class="sxs-lookup"><span data-stu-id="34934-120">The transport is TCP, and message encoding is binary encoding.</span></span>  
  
- <span data-ttu-id="34934-121">**Wcf-netmsmq 适配器**。</span><span class="sxs-lookup"><span data-stu-id="34934-121">**WCF-NetMsmq adapter**.</span></span> <span data-ttu-id="34934-122">通过利用机制来提供支持[!INCLUDE[btsCoName](../includes/btsconame-md.md)]消息队列 (MSMQ) 传输支持松散耦合应用程序、 故障隔离、 负载均衡，和断开连接操作。</span><span class="sxs-lookup"><span data-stu-id="34934-122">Provides support for queuing by leveraging [!INCLUDE[btsCoName](../includes/btsconame-md.md)] Message Queuing (MSMQ) as a transport and enables support for loosely coupled applications, failure isolation, load leveling, and disconnected operations.</span></span>  
  
- <span data-ttu-id="34934-123">**Wcf-netnamedpipe 适配器**。</span><span class="sxs-lookup"><span data-stu-id="34934-123">**WCF-NetNamedPipe adapter**.</span></span> <span data-ttu-id="34934-124">提供了计算机上的跨进程通信的安全优化。</span><span class="sxs-lookup"><span data-stu-id="34934-124">Provides secure optimization for on-machine cross-process communication.</span></span> <span data-ttu-id="34934-125">Wcf-netnamedpipe 适配器使用传输安全性保证传输安全，命名管道进行消息传递，并且包含二进制消息编码。</span><span class="sxs-lookup"><span data-stu-id="34934-125">The WCF-NetNamedPipe adapter uses transport security for transfer security, named pipes for message delivery, and binary message encoding.</span></span>  
  
- <span data-ttu-id="34934-126">**WCF 自定义适配器**。</span><span class="sxs-lookup"><span data-stu-id="34934-126">**WCF-Custom adapter**.</span></span> <span data-ttu-id="34934-127">启用 WCF 扩展功能的使用。</span><span class="sxs-lookup"><span data-stu-id="34934-127">Enables the use of WCF extensibility features.</span></span> <span data-ttu-id="34934-128">该适配器，可以选择和配置 WCF 绑定和行为信息的接收位置和发送端口。</span><span class="sxs-lookup"><span data-stu-id="34934-128">The adapter allows you to select and configure a WCF binding and the behavior information for the receive location and send port.</span></span>  
  
- <span data-ttu-id="34934-129">**Wcf-customisolated 适配器**。</span><span class="sxs-lookup"><span data-stu-id="34934-129">**WCF-CustomIsolated adapter**.</span></span> <span data-ttu-id="34934-130">允许通过 HTTP 传输使用 WCF 扩展功能。</span><span class="sxs-lookup"><span data-stu-id="34934-130">Enables the use of WCF extensibility features over the HTTP transport.</span></span> <span data-ttu-id="34934-131">该适配器，可以选择和配置 WCF 绑定和行为信息在独立主机中运行的接收位置。</span><span class="sxs-lookup"><span data-stu-id="34934-131">The adapter allows you to select and configure a WCF binding and the behavior information for the receive location running in an isolated host.</span></span>  
  
  <span data-ttu-id="34934-132">此外，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供 BizTalk WCF 服务发布向导和 BizTalk WCF 服务使用向导。</span><span class="sxs-lookup"><span data-stu-id="34934-132">In addition, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] provides the BizTalk WCF Service Publishing Wizard and the BizTalk WCF Service Consuming Wizard.</span></span> <span data-ttu-id="34934-133">若要创建和发布为 WCF 服务的 BizTalk 业务流程，并将架构发布为 WCF 服务，可以使用 BizTalk WCF 服务发布向导。</span><span class="sxs-lookup"><span data-stu-id="34934-133">You can use the BizTalk WCF Service Publishing Wizard to create and publish BizTalk orchestrations as WCF services, and to publish schemas as WCF services.</span></span> <span data-ttu-id="34934-134">可以使用 BizTalk WCF 服务使用向导来生成[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目，如业务流程和类型，以便 WCF 服务使用基于 WCF 服务的元数据文档。</span><span class="sxs-lookup"><span data-stu-id="34934-134">You can use the BizTalk WCF Service Consuming Wizard to generate [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] artifacts, such as orchestrations and types, to consume a WCF service based on the metadata document of the WCF service.</span></span>  
  
  <span data-ttu-id="34934-135">本部分提供了资源，以帮助您配置和部署 WCF 适配器。</span><span class="sxs-lookup"><span data-stu-id="34934-135">This section provides resources to help you configure and deploy the WCF adapters.</span></span>  
  
## <a name="next"></a><span data-ttu-id="34934-136">Next</span><span class="sxs-lookup"><span data-stu-id="34934-136">Next</span></span> 
  
-   [<span data-ttu-id="34934-137">WCF 适配器概述</span><span class="sxs-lookup"><span data-stu-id="34934-137">What Are the WCF Adapters?</span></span>](../core/what-are-the-wcf-adapters.md)  
  
-   [<span data-ttu-id="34934-138">配置 WCF 适配器</span><span class="sxs-lookup"><span data-stu-id="34934-138">Configuring the WCF Adapters</span></span>](../core/configuring-the-wcf-adapters.md)  
  
-   [<span data-ttu-id="34934-139">Wcf-basichttp 适配器</span><span class="sxs-lookup"><span data-stu-id="34934-139">WCF-BasicHttp Adapter</span></span>](../core/wcf-basichttp-adapter.md)  
  
-   [<span data-ttu-id="34934-140">WCF-WSHttp 适配器</span><span class="sxs-lookup"><span data-stu-id="34934-140">WCF-WSHttp Adapter</span></span>](../core/wcf-wshttp-adapter.md)  
  
-   [<span data-ttu-id="34934-141">WCF-NetTcp 适配器</span><span class="sxs-lookup"><span data-stu-id="34934-141">WCF-NetTcp Adapter</span></span>](../core/wcf-nettcp-adapter.md)  
  
-   [<span data-ttu-id="34934-142">WCF-NetMsmq 适配器</span><span class="sxs-lookup"><span data-stu-id="34934-142">WCF-NetMsmq Adapter</span></span>](../core/wcf-netmsmq-adapter.md)  
  
-   [<span data-ttu-id="34934-143">WCF-NetNamedPipe 适配器</span><span class="sxs-lookup"><span data-stu-id="34934-143">WCF-NetNamedPipe Adapter</span></span>](../core/wcf-netnamedpipe-adapter.md)  
  
-   [<span data-ttu-id="34934-144">WCF-Custom 适配器</span><span class="sxs-lookup"><span data-stu-id="34934-144">WCF-Custom Adapter</span></span>](../core/wcf-custom-adapter.md)  
  
-   [<span data-ttu-id="34934-145">WCF-CustomIsolated 适配器</span><span class="sxs-lookup"><span data-stu-id="34934-145">WCF-CustomIsolated Adapter</span></span>](../core/wcf-customisolated-adapter.md)  
  
## <a name="see-also"></a><span data-ttu-id="34934-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="34934-146">See Also</span></span>  
 [<span data-ttu-id="34934-147">使用 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="34934-147">Using WCF Services</span></span>](../core/using-wcf-services.md)   