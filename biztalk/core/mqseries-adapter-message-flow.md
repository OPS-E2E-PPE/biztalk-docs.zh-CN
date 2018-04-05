---
title: MQSeries 适配器消息流 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MQSeries adapters, message flow
ms.assetid: aa5c8523-afd6-4181-9c11-a150857a7790
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5df8549f99d376ea518b160ac1505aaac7feb5fa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="mqseries-adapter-message-flow"></a><span data-ttu-id="6406a-102">MQSeries 适配器消息流</span><span class="sxs-lookup"><span data-stu-id="6406a-102">MQSeries Adapter Message Flow</span></span>
<span data-ttu-id="6406a-103">消息从发起[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机会首先传递给 MQSeries 服务器在 Windows 上运行。</span><span class="sxs-lookup"><span data-stu-id="6406a-103">A message originating from a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computer is first passed to an MQSeries Server running on Windows.</span></span> <span data-ttu-id="6406a-104">运行在 Windows 上的 MQSeries 服务器可以位于运行 BizTalk Server 的同一计算机上。</span><span class="sxs-lookup"><span data-stu-id="6406a-104">MQSeries Server running on Windows can be on the same computer as the one that runs BizTalk Server.</span></span> <span data-ttu-id="6406a-105">消息通过 MQSeries Server for Windows 计算机路由至操作系统上（如 UNIX）的 MQSeries 服务器主机。</span><span class="sxs-lookup"><span data-stu-id="6406a-105">The message is routed through the MQSeries Server for Windows computer to an MQSeries Server host on an operating system such as UNIX.</span></span> <span data-ttu-id="6406a-106">随后，应用程序将从 MQSeries 队列中检索消息。</span><span class="sxs-lookup"><span data-stu-id="6406a-106">An application then retrieves the message from the MQSeries queue.</span></span>  
  
 <span data-ttu-id="6406a-107">来自应用程序的消息首先将进入 MQSeries 服务器上的 MQSeries 队列中。</span><span class="sxs-lookup"><span data-stu-id="6406a-107">A message originating from an application first goes to an MQSeries queue on MQSeries Server.</span></span> <span data-ttu-id="6406a-108">MQSeries 服务器将该消息转发到 MQSeries Server for Windows 计算机。</span><span class="sxs-lookup"><span data-stu-id="6406a-108">The MQSeries Server forwards the message to the MQSeries Server for Windows computer.</span></span> <span data-ttu-id="6406a-109">BizTalk Server 从 MQSeries Server for Windows 计算机接收消息，并将其转发给相应的应用程序。</span><span class="sxs-lookup"><span data-stu-id="6406a-109">BizTalk Server receives the message from the MQSeries Server for Windows computer and forwards it to the appropriate application.</span></span>  
  
 <span data-ttu-id="6406a-110">MQSeries 适配器支持以下消息传送方案：</span><span class="sxs-lookup"><span data-stu-id="6406a-110">The MQSeries adapter supports the following messaging scenarios.</span></span>  
  
|<span data-ttu-id="6406a-111">**应用场景**</span><span class="sxs-lookup"><span data-stu-id="6406a-111">**Scenario**</span></span>|<span data-ttu-id="6406a-112">**Description**</span><span class="sxs-lookup"><span data-stu-id="6406a-112">**Description**</span></span>|  
|------------------|---------------------|  
|<span data-ttu-id="6406a-113">Receive</span><span class="sxs-lookup"><span data-stu-id="6406a-113">Receive</span></span>|<span data-ttu-id="6406a-114">适配器从 MQSeries Server，传递到接收消息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="6406a-114">The adapter receives a message from MQSeries Server, which is passed to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>|  
|<span data-ttu-id="6406a-115">发送（静态单向端口）</span><span class="sxs-lookup"><span data-stu-id="6406a-115">Send (Static One-Way Port)</span></span>|<span data-ttu-id="6406a-116">适配器将源自的消息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="6406a-116">The adapter routes a message that originates from [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>|  
|<span data-ttu-id="6406a-117">动态发送</span><span class="sxs-lookup"><span data-stu-id="6406a-117">Dynamic Send</span></span>|<span data-ttu-id="6406a-118">使应用程序能够在运行时选择目标地址 (URI)。</span><span class="sxs-lookup"><span data-stu-id="6406a-118">Enables the application to select a destination address (URI) at run time.</span></span>|  
|<span data-ttu-id="6406a-119">动态接收</span><span class="sxs-lookup"><span data-stu-id="6406a-119">Dynamic Receive</span></span>|<span data-ttu-id="6406a-120">使应用程序能够在运行时选择的源地址 (URI)，通过设置**MQSeries.DynamicReceive**上下文属性**是**并指定动态接收地址。</span><span class="sxs-lookup"><span data-stu-id="6406a-120">Enables the application to select a source address (URI) at run time by setting the **MQSeries.DynamicReceive** context property to **Yes** and specifying the dynamic receive address.</span></span>|  
|<span data-ttu-id="6406a-121">Correlation</span><span class="sxs-lookup"><span data-stu-id="6406a-121">Correlation</span></span>|<span data-ttu-id="6406a-122">来自适配器的消息与可以处理多种类型消息的特定业务流程实例相关。</span><span class="sxs-lookup"><span data-stu-id="6406a-122">Messages from the adapter are correlated with specific instances of an orchestration that can handle more than one type of message.</span></span><br /><br /> <span data-ttu-id="6406a-123">MQSeries 服务器可以通过使用要求响应来创建相关标识符，或者 BizTalk Server 可以创建相关标识符。</span><span class="sxs-lookup"><span data-stu-id="6406a-123">MQSeries Server can create the correlation identifier by using solicit-response, or BizTalk Server can create the correlation identifier.</span></span><br /><br /> <span data-ttu-id="6406a-124">有关关联集的详细信息，请参阅[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="6406a-124">For more information about correlation sets, see [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>|  
  
 <span data-ttu-id="6406a-125">有关使用端口和管道、 业务流程，和基于内容的路由中的适配器的详细信息，请参阅[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="6406a-125">For more information about using ports and adapters in pipelines, orchestrations, and content-based routing, see [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span> <span data-ttu-id="6406a-126">有关在适配器中使用相关性标识符的详细信息，请参阅[关联消息使用请求-答复](../core/correlating-messages-using-request-reply.md)。</span><span class="sxs-lookup"><span data-stu-id="6406a-126">For more information about using correlation identifiers in the adapter, see [Correlating Messages Using Request-Reply](../core/correlating-messages-using-request-reply.md).</span></span>  
  
 <span data-ttu-id="6406a-127">有关可用于筛选在适配器中的标头属性的信息，请参阅[给 BizTalk Server 相关的属性](../core/properties-related-to-biztalk-server.md)和[MQSeries 上下文属性](../core/mqseries-context-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="6406a-127">For information about the header properties available for filtering in the adapter, see [Properties Related to BizTalk Server](../core/properties-related-to-biztalk-server.md) and [MQSeries Context Properties](../core/mqseries-context-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6406a-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6406a-128">See Also</span></span>  
 [<span data-ttu-id="6406a-129">使用 MQSeries 适配器</span><span class="sxs-lookup"><span data-stu-id="6406a-129">Using the MQSeries Adapter</span></span>](../core/using-the-mqseries-adapter.md)