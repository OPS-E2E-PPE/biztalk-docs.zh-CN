---
title: MQSeries 适配器的结构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, MQSeries adapters
- MQSeries adapters, architecture
ms.assetid: d25caf6a-3f93-4164-9c92-489b919a624d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21bd7d9dee24e8235aff34a14babd4cc69240c74
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379945"
---
# <a name="structure-of-the-mqseries-adapter"></a><span data-ttu-id="7407b-102">MQSeries 适配器的结构</span><span class="sxs-lookup"><span data-stu-id="7407b-102">Structure of the MQSeries Adapter</span></span>
<span data-ttu-id="7407b-103">MQSeries 适配器由两部分组成： 下运行的适配器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和 COM + 应用程序，MQSAgent 运行 MQSeries Server for Windows。</span><span class="sxs-lookup"><span data-stu-id="7407b-103">The MQSeries adapter has two parts: the adapter running under [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and a COM+ application, MQSAgent, running under MQSeries Server for Windows.</span></span> <span data-ttu-id="7407b-104">下图显示了此关系。</span><span class="sxs-lookup"><span data-stu-id="7407b-104">The following figure shows this relationship.</span></span>  
  
 <span data-ttu-id="7407b-105">![MQSeries 适配器组件](../core/media/bts-dev-mqoverallstructure.gif "BTS_Dev_MQOverallStructure")</span><span class="sxs-lookup"><span data-stu-id="7407b-105">![MQSeries Adapter components](../core/media/bts-dev-mqoverallstructure.gif "BTS_Dev_MQOverallStructure")</span></span>  
  
 <span data-ttu-id="7407b-106">适配器与 MQSAgent 应用程序进行通信。</span><span class="sxs-lookup"><span data-stu-id="7407b-106">The adapter communicates with the MQSAgent application.</span></span> <span data-ttu-id="7407b-107">MQSAgent 应用程序，反过来，通信与 MQSeries Server for Windows。</span><span class="sxs-lookup"><span data-stu-id="7407b-107">The MQSAgent application, in turn, communicates with MQSeries Server for Windows.</span></span> <span data-ttu-id="7407b-108">如果您安装 MQSeries Server for Windows 的计算机上，可以在该适配器所在的计算机上安装代理。</span><span class="sxs-lookup"><span data-stu-id="7407b-108">You can install the agent on the same computer as the adapter if you install MQSeries Server for Windows on the computer.</span></span>  
  
 <span data-ttu-id="7407b-109">该适配器的发送部分向 MQSAgent 发送消息。</span><span class="sxs-lookup"><span data-stu-id="7407b-109">The send part of the adapter sends the message to the MQSAgent.</span></span> <span data-ttu-id="7407b-110">MQSAgent 然后，使用**MQPut**，将消息发送到 MQSeries 队列管理器。</span><span class="sxs-lookup"><span data-stu-id="7407b-110">MQSAgent then, using **MQPut**, sends the message to the MQSeries Queue Manager.</span></span>  
  
 <span data-ttu-id="7407b-111">该适配器的接收部分将轮询 MQSAgent 以查看是否有消息。</span><span class="sxs-lookup"><span data-stu-id="7407b-111">The receive part of the adapter polls the MQSAgent to see if there are messages.</span></span> <span data-ttu-id="7407b-112">如果有一条消息，则 MQSAgent 将执行**MQGet**中检索消息。</span><span class="sxs-lookup"><span data-stu-id="7407b-112">When there is a message, the MQSAgent performs an **MQGet** to retrieve the message.</span></span> <span data-ttu-id="7407b-113">MQSAgent 包含硬编码三秒等待，以检索该消息从队列管理器。</span><span class="sxs-lookup"><span data-stu-id="7407b-113">MQSAgent includes a hard-coded three-second wait for retrieving the message from the Queue Manager.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7407b-114">您可以设置该适配器的轮询间隔。</span><span class="sxs-lookup"><span data-stu-id="7407b-114">You can set the polling interval of the adapter.</span></span> <span data-ttu-id="7407b-115">轮询间隔设置为小于三秒后，等待间隔设置为轮询间隔。</span><span class="sxs-lookup"><span data-stu-id="7407b-115">When you set the polling interval to less than three seconds, the wait interval is set to the polling interval.</span></span>  
  
 <span data-ttu-id="7407b-116">这两个发送和接收消息在事务中进行操作。</span><span class="sxs-lookup"><span data-stu-id="7407b-116">Both the send and receive message actions may occur in transactions.</span></span> <span data-ttu-id="7407b-117">这使得适配器可以回滚消息以及可能的重试发送或接收操作。</span><span class="sxs-lookup"><span data-stu-id="7407b-117">This enables the adapter to roll back the message and, possibly, to retry the send or receive operations.</span></span> <span data-ttu-id="7407b-118">有关事务的详细信息，请参阅[MQSeries 适配器批处理和事务处理](../core/mqseries-adapter-batching-and-transaction-handling.md)。</span><span class="sxs-lookup"><span data-stu-id="7407b-118">For more information about transactions, see [MQSeries Adapter Batching and Transaction Handling](../core/mqseries-adapter-batching-and-transaction-handling.md).</span></span>  
  
 <span data-ttu-id="7407b-119">因为适配器可以在多台计算机，所以不可能的安全问题。</span><span class="sxs-lookup"><span data-stu-id="7407b-119">Because the adapter works across more than one computer, there is a possible security problem.</span></span> <span data-ttu-id="7407b-120">恶意程序可能会假冒代理并捕获数据。</span><span class="sxs-lookup"><span data-stu-id="7407b-120">A hostile program could impersonate the agent and capture data.</span></span> <span data-ttu-id="7407b-121">有关适配器和代理的增强保护的详细信息，请参阅[MQSeries 适配器安全性](../core/mqseries-adapter-security.md)。</span><span class="sxs-lookup"><span data-stu-id="7407b-121">For more information about enhanced protection for the adapter and agent, see [MQSeries Adapter Security](../core/mqseries-adapter-security.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7407b-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="7407b-122">See Also</span></span>  
 <span data-ttu-id="7407b-123">[MQSeries 适配器体系结构](../core/mqseries-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="7407b-123">[MQSeries Adapter Architecture](../core/mqseries-adapter-architecture.md) </span></span>  
 [<span data-ttu-id="7407b-124">MQSeries 适配器概述</span><span class="sxs-lookup"><span data-stu-id="7407b-124">What Is the MQSeries Adapter?</span></span>](../core/what-is-the-mqseries-adapter.md)