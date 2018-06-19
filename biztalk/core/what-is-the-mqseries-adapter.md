---
title: MQSeries 适配器概述  | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, about MQSeries adapters
- MQSeries adapters
ms.assetid: fd3dfa9a-344a-46e5-a342-bc56da7c1c50
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f72d0012050fc8022b53120377aeb648641d21f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289461"
---
# <a name="what-is-the-mqseries-adapter"></a><span data-ttu-id="360ec-103">MQSeries 适配器概述 </span><span class="sxs-lookup"><span data-stu-id="360ec-103">What Is the MQSeries Adapter?</span></span>
<span data-ttu-id="360ec-104">通过 MQSeries 适配器，您可以在 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 与 MQSeries 系统之间收发消息。</span><span class="sxs-lookup"><span data-stu-id="360ec-104">With the MQSeries adapter you can send and receive messages to MQSeries systems using Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="360ec-105">该适配器依赖于 MQSeries Server for Windows。</span><span class="sxs-lookup"><span data-stu-id="360ec-105">The adapter relies on MQSeries Server for Windows.</span></span> <span data-ttu-id="360ec-106">这种设计可确保消息传送的可靠性，因为 MQSeries Server for Windows 支持 Microsoft 分布式事务处理协调器 (MSDTC)。</span><span class="sxs-lookup"><span data-stu-id="360ec-106">This design guarantees reliable messaging because MQSeries Server for Windows supports Microsoft Distributed Transaction Coordinator (MSDTC).</span></span>  
  
 <span data-ttu-id="360ec-107">该适配器支持群集 MQSeries Server 和群集 MQSeries 队列管理器，以及群集 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="360ec-107">The adapter supports clustered MQSeries Servers and clustered MQSeries Queue Managers, and also clustered BizTalk servers.</span></span>  
  
 <span data-ttu-id="360ec-108">使用 MQSeries 适配器，您可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="360ec-108">You can do the following with the MQSeries adapter:</span></span>  
  
-   <span data-ttu-id="360ec-109">将消息从 BizTalk Server 发送到 MQSeries 远程定义队列、本地队列、传输队列和别名队列。</span><span class="sxs-lookup"><span data-stu-id="360ec-109">Send messages to MQSeries remote definition queues, local queues, transmission queues, and alias queues from BizTalk Server.</span></span>  
  
-   <span data-ttu-id="360ec-110">从 MQSeries 传输队列、本地队列和别名队列接收消息。</span><span class="sxs-lookup"><span data-stu-id="360ec-110">Receive messages from MQSeries transmission queues, local queues, and alias queues.</span></span>  
  
-   <span data-ttu-id="360ec-111">与 MQSeries Server for Windows 之间收发消息，MQSeries Server 可在 BizTalk Server 所在的同一计算机或远程安装位置上运行。</span><span class="sxs-lookup"><span data-stu-id="360ec-111">Send and receive messages from MQSeries Server for Windows (MQSeries Server can run on the same computer as BizTalk Server or on a remote installation).</span></span> <span data-ttu-id="360ec-112">只需部署一个 MQSAgent（适配器的 COM+ 组件）副本即可支持所有的 BizTalk Server 安装。</span><span class="sxs-lookup"><span data-stu-id="360ec-112">You only have to deploy one copy of MQSAgent (the COM+ component of the adapter) to support all your BizTalk Server installations.</span></span>  
  
-   <span data-ttu-id="360ec-113">按等待间隔来轮询 MQSeries Server。</span><span class="sxs-lookup"><span data-stu-id="360ec-113">Poll MQSeries Server with a wait interval.</span></span>  
  
-   <span data-ttu-id="360ec-114">使用动态发送端口来控制适配器。</span><span class="sxs-lookup"><span data-stu-id="360ec-114">Use dynamic send ports to control the adapter.</span></span>  
  
-   <span data-ttu-id="360ec-115">在运行时动态创建队列。</span><span class="sxs-lookup"><span data-stu-id="360ec-115">Dynamically create queues at run time.</span></span>  
  
-   <span data-ttu-id="360ec-116">根据 MQSeries MatchOptions 从队列中动态接收消息。</span><span class="sxs-lookup"><span data-stu-id="360ec-116">Dynamically receive messages from queues based upon MQSeries MatchOptions.</span></span>  
  
-   <span data-ttu-id="360ec-117">将上下文属性映射到用于传输和接收消息的标头属性。</span><span class="sxs-lookup"><span data-stu-id="360ec-117">Map context properties to header properties for both transmitting and receiving messages.</span></span> <span data-ttu-id="360ec-118">可以通过 BizTalk Server 上下文属性来获取和设置 MQSeries 标头属性，包括 MQMD、MQXQH、MQCIH 和 MQIIH。</span><span class="sxs-lookup"><span data-stu-id="360ec-118">You can get and set MQSeries header properties (including MQMD, MQXQH, MQCIH, and MQIIH) through BizTalk Server context properties.</span></span>  
  
-   <span data-ttu-id="360ec-119">启用使用相关[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]或 MQSeries 服务器创建的相关标识符。</span><span class="sxs-lookup"><span data-stu-id="360ec-119">Enable correlation with either [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or MQSeries Server creating the correlation identifier.</span></span>  
  
-   <span data-ttu-id="360ec-120">请求事务性和非事务性消息送达，以便进行发送和接收。</span><span class="sxs-lookup"><span data-stu-id="360ec-120">Request transactional and nontransactional delivery of messages for send and receive.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="360ec-121">当使用诸如 MQSeries 这样对服务器调用分布式组件对象模型 (DCOM) 的功能时，请确保未启用基于网络地址转换 (NAT) 的防火墙。</span><span class="sxs-lookup"><span data-stu-id="360ec-121">When using features such as MQSeries which make Distributed Component Object Model (DCOM) calls to the server, make sure you do not have a Network Address Translation (NAT)-based firewall enabled.</span></span> <span data-ttu-id="360ec-122">客户端必须能够通过其实际 IP 地址访问该服务器，并且基于 NAT 的防火墙将此地址翻译为客户端不能识别的地址。</span><span class="sxs-lookup"><span data-stu-id="360ec-122">The client must be able to access the server by its actual IP address, and NAT-based firewalls translate this address to something the client will not recognize.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="360ec-123">本节内容</span><span class="sxs-lookup"><span data-stu-id="360ec-123">In This Section</span></span>  
  
-   [<span data-ttu-id="360ec-124">MQSeries 适配器的组件</span><span class="sxs-lookup"><span data-stu-id="360ec-124">Components of the MQSeries Adapter</span></span>](../core/components-of-the-mqseries-adapter.md)  
  
-   [<span data-ttu-id="360ec-125">MQSeries 适配器体系结构</span><span class="sxs-lookup"><span data-stu-id="360ec-125">MQSeries Adapter Architecture</span></span>](../core/mqseries-adapter-architecture.md)  
  
-   [<span data-ttu-id="360ec-126">使用 MQSeries 适配器</span><span class="sxs-lookup"><span data-stu-id="360ec-126">Using the MQSeries Adapter</span></span>](../core/using-the-mqseries-adapter.md)  
  
-   [<span data-ttu-id="360ec-127">MQSeries 适配器安全</span><span class="sxs-lookup"><span data-stu-id="360ec-127">MQSeries Adapter Security</span></span>](../core/mqseries-adapter-security.md)