---
title: "结构 MQSeries 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- architecture, MQSeries adapters
- MQSeries adapters, architecture
ms.assetid: d25caf6a-3f93-4164-9c92-489b919a624d
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6239b78f0b9bd2c44a314b7ba0ba6ace8f3b78e4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="structure-of-the-mqseries-adapter"></a><span data-ttu-id="1f461-102">MQSeries 适配器的结构</span><span class="sxs-lookup"><span data-stu-id="1f461-102">Structure of the MQSeries Adapter</span></span>
<span data-ttu-id="1f461-103">MQSeries 适配器由两部分组成： 下运行的适配器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]并将 COM + 应用程序，MQSAgent，适用于 Windows 在 MQSeries 服务器下运行。</span><span class="sxs-lookup"><span data-stu-id="1f461-103">The MQSeries adapter has two parts: the adapter running under [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and a COM+ application, MQSAgent, running under MQSeries Server for Windows.</span></span> <span data-ttu-id="1f461-104">下图显示了此关系：</span><span class="sxs-lookup"><span data-stu-id="1f461-104">The following figure shows this relationship.</span></span>  
  
 <span data-ttu-id="1f461-105">![MQSeries 适配器组件](../core/media/bts-dev-mqoverallstructure.gif "BTS_Dev_MQOverallStructure")</span><span class="sxs-lookup"><span data-stu-id="1f461-105">![MQSeries Adapter components](../core/media/bts-dev-mqoverallstructure.gif "BTS_Dev_MQOverallStructure")</span></span>  
  
 <span data-ttu-id="1f461-106">该适配器可与 MQSAgent 应用程序进行通信。</span><span class="sxs-lookup"><span data-stu-id="1f461-106">The adapter communicates with the MQSAgent application.</span></span> <span data-ttu-id="1f461-107">而 MQSAgent 应用程序又与 MQSeries Server for Windows 进行通信。</span><span class="sxs-lookup"><span data-stu-id="1f461-107">The MQSAgent application, in turn, communicates with MQSeries Server for Windows.</span></span> <span data-ttu-id="1f461-108">如果您在计算机上安装了 MQSeries Server for Windows，则可以将代理与该适配器安装在同一台计算机上。</span><span class="sxs-lookup"><span data-stu-id="1f461-108">You can install the agent on the same computer as the adapter if you install MQSeries Server for Windows on the computer.</span></span>  
  
 <span data-ttu-id="1f461-109">该适配器的发送部分向 MQSAgent 发送消息。</span><span class="sxs-lookup"><span data-stu-id="1f461-109">The send part of the adapter sends the message to the MQSAgent.</span></span> <span data-ttu-id="1f461-110">MQSAgent 然后，使用**MQPut**，将消息发送到 MQSeries 队列管理器。</span><span class="sxs-lookup"><span data-stu-id="1f461-110">MQSAgent then, using **MQPut**, sends the message to the MQSeries Queue Manager.</span></span>  
  
 <span data-ttu-id="1f461-111">该适配器的接收部分将轮询 MQSAgent 以查看是否有消息。</span><span class="sxs-lookup"><span data-stu-id="1f461-111">The receive part of the adapter polls the MQSAgent to see if there are messages.</span></span> <span data-ttu-id="1f461-112">如果有一条消息，执行 MQSAgent **MQGet**来检索消息。</span><span class="sxs-lookup"><span data-stu-id="1f461-112">When there is a message, the MQSAgent performs an **MQGet** to retrieve the message.</span></span> <span data-ttu-id="1f461-113">MQSAgent 包含硬编码三秒等待，以从队列管理器中检索消息。</span><span class="sxs-lookup"><span data-stu-id="1f461-113">MQSAgent includes a hard-coded three-second wait for retrieving the message from the Queue Manager.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1f461-114">您可以设置该适配器的轮询间隔。</span><span class="sxs-lookup"><span data-stu-id="1f461-114">You can set the polling interval of the adapter.</span></span> <span data-ttu-id="1f461-115">将轮询间隔设置为三秒以下时，等待间隔将设置为轮询间隔。</span><span class="sxs-lookup"><span data-stu-id="1f461-115">When you set the polling interval to less than three seconds, the wait interval is set to the polling interval.</span></span>  
  
 <span data-ttu-id="1f461-116">发送消息和接收消息两种操作均在事务中进行。</span><span class="sxs-lookup"><span data-stu-id="1f461-116">Both the send and receive message actions may occur in transactions.</span></span> <span data-ttu-id="1f461-117">这样，适配器就可以回滚消息，并可重试发送或接收操作。</span><span class="sxs-lookup"><span data-stu-id="1f461-117">This enables the adapter to roll back the message and, possibly, to retry the send or receive operations.</span></span> <span data-ttu-id="1f461-118">有关事务的详细信息，请参阅[MQSeries 适配器批处理和事务处理](../core/mqseries-adapter-batching-and-transaction-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="1f461-118">For more information about transactions, see [MQSeries Adapter Batching and Transaction Handling](../core/mqseries-adapter-batching-and-transaction-handling.md).</span></span>  
  
 <span data-ttu-id="1f461-119">由于适配器工作于多台计算机间，因此，可能会碰到安全方面的问题。</span><span class="sxs-lookup"><span data-stu-id="1f461-119">Because the adapter works across more than one computer, there is a possible security problem.</span></span> <span data-ttu-id="1f461-120">恶意程序可能会假冒代理并捕获数据。</span><span class="sxs-lookup"><span data-stu-id="1f461-120">A hostile program could impersonate the agent and capture data.</span></span> <span data-ttu-id="1f461-121">有关增强保护的适配器和代理的详细信息，请参阅[MQSeries 适配器安全](../core/mqseries-adapter-security.md)。</span><span class="sxs-lookup"><span data-stu-id="1f461-121">For more information about enhanced protection for the adapter and agent, see [MQSeries Adapter Security](../core/mqseries-adapter-security.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f461-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1f461-122">See Also</span></span>  
 <span data-ttu-id="1f461-123">[MQSeries 适配器体系结构](../core/mqseries-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="1f461-123">[MQSeries Adapter Architecture](../core/mqseries-adapter-architecture.md) </span></span>  
 [<span data-ttu-id="1f461-124">什么是 MQSeries 适配器？</span><span class="sxs-lookup"><span data-stu-id="1f461-124">What Is the MQSeries Adapter?</span></span>](../core/what-is-the-mqseries-adapter.md)