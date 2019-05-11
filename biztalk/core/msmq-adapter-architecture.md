---
title: MSMQ 适配器体系结构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, MSMQ adapters
- MSMQ adapters, architecture
ms.assetid: acecc2a4-0670-487e-be39-28a24c8c3f16
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1445907a98b6e86ae898015d131b0a5f892351a0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65263649"
---
# <a name="msmq-adapter-architecture"></a><span data-ttu-id="2f470-102">MSMQ 适配器体系结构</span><span class="sxs-lookup"><span data-stu-id="2f470-102">MSMQ Adapter Architecture</span></span>
<span data-ttu-id="2f470-103">MSMQ 适配器，您可以利用 Microsoft 消息队列 (也称为 MSMQ) 功能，否则将在 BizTalk Server 中不可用。</span><span class="sxs-lookup"><span data-stu-id="2f470-103">The MSMQ adapter lets you take advantage of Microsoft Message Queuing (also known as MSMQ) features that are otherwise unavailable in BizTalk Server.</span></span>  
  
## <a name="adapter-structure"></a><span data-ttu-id="2f470-104">适配器结构</span><span class="sxs-lookup"><span data-stu-id="2f470-104">Adapter Structure</span></span>  
 <span data-ttu-id="2f470-105">MSMQ 适配器具有相同的结构与其他 BizTalk 适配器，并使用适配器框架。</span><span class="sxs-lookup"><span data-stu-id="2f470-105">The MSMQ adapter has the same structure as other BizTalk adapters and uses the Adapter Framework.</span></span> <span data-ttu-id="2f470-106">它是一个设计时组件和运行时组件组成。</span><span class="sxs-lookup"><span data-stu-id="2f470-106">It is made up of a design-time component and a run-time component.</span></span> <span data-ttu-id="2f470-107">运行时组件中，又包含实现消息传输的元素。</span><span class="sxs-lookup"><span data-stu-id="2f470-107">The run-time component, in turn, contains the elements that implement the message transport.</span></span>  
  
 <span data-ttu-id="2f470-108">设计时组件允许你配置用于发送和接收适配器的属性。</span><span class="sxs-lookup"><span data-stu-id="2f470-108">The design-time component lets you configure the adapter properties for sending and receiving.</span></span>  
  
 <span data-ttu-id="2f470-109">运行时组件可以将消息发送到在设计时定义的队列或从指定的队列接收消息。</span><span class="sxs-lookup"><span data-stu-id="2f470-109">The run-time component can send messages to a queue defined at design time or receive messages from a designated queue.</span></span> <span data-ttu-id="2f470-110">适配器运行时作为 BizTalk Server 应用程序在同一进程中运行，并不会运行在独立主机中。</span><span class="sxs-lookup"><span data-stu-id="2f470-110">The adapter runtime runs in the same process as the BizTalk Server application and does not run in an isolated host.</span></span>  
  
 <span data-ttu-id="2f470-111">所有消息处理都依赖于本地消息队列服务，甚至对于远程队列。</span><span class="sxs-lookup"><span data-stu-id="2f470-111">All message handling relies on the local Message Queuing service, even for remote queues.</span></span> <span data-ttu-id="2f470-112">对于远程队列，适配器将消息，传送到本地消息队列服务。</span><span class="sxs-lookup"><span data-stu-id="2f470-112">For remote queues, the adapter hands messages off to the local Message Queuing service.</span></span> <span data-ttu-id="2f470-113">它，反过来，可以将消息发送到远程队列中。</span><span class="sxs-lookup"><span data-stu-id="2f470-113">It, in turn, sends the messages to the remote queue.</span></span>  
  
 <span data-ttu-id="2f470-114">有关完整列表的发送和接收配置属性，请参阅[如何配置 MSMQ 发送端口](../core/how-to-configure-an-msmq-send-port.md)并[如何配置 MSMQ 接收位置](../core/how-to-configure-an-msmq-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="2f470-114">For a complete list of send and receive configuration properties, see [How to Configure an MSMQ Send Port](../core/how-to-configure-an-msmq-send-port.md) and [How to Configure an MSMQ Receive Location](../core/how-to-configure-an-msmq-receive-location.md).</span></span>  
  
 <span data-ttu-id="2f470-115">有关消息队列的详细信息，请参阅 Microsoft TechNet 库中提供的以下主题：</span><span class="sxs-lookup"><span data-stu-id="2f470-115">For more information about Message Queuing, see the following topics available in the Microsoft TechNet Library:</span></span>  
  
-   <span data-ttu-id="2f470-116">**消息队列设计指南**处[ http://go.microsoft.com/fwlink/?LinkId=137080 ](http://go.microsoft.com/fwlink/?LinkId=137080)。</span><span class="sxs-lookup"><span data-stu-id="2f470-116">**Message Queuing Design Guide** at [http://go.microsoft.com/fwlink/?LinkId=137080](http://go.microsoft.com/fwlink/?LinkId=137080).</span></span>  
  
-   <span data-ttu-id="2f470-117">**消息队列操作指南**处[ http://go.microsoft.com/fwlink/?LinkId=137079 ](http://go.microsoft.com/fwlink/?LinkId=137079)。</span><span class="sxs-lookup"><span data-stu-id="2f470-117">**Message Queuing Operations Guide** at [http://go.microsoft.com/fwlink/?LinkId=137079](http://go.microsoft.com/fwlink/?LinkId=137079).</span></span>  
  
-   <span data-ttu-id="2f470-118">**消息队列疑难解答指南**处[ http://go.microsoft.com/fwlink/?LinkId=137081 ](http://go.microsoft.com/fwlink/?LinkId=137081)。</span><span class="sxs-lookup"><span data-stu-id="2f470-118">**Message Queuing Troubleshooting Guide** at [http://go.microsoft.com/fwlink/?LinkId=137081](http://go.microsoft.com/fwlink/?LinkId=137081).</span></span>  
  
-   <span data-ttu-id="2f470-119">**消息队列技术参考**处[ http://go.microsoft.com/fwlink/?LinkId=137082 ](http://go.microsoft.com/fwlink/?LinkId=137082)。</span><span class="sxs-lookup"><span data-stu-id="2f470-119">**Message Queuing Technical Reference** at [http://go.microsoft.com/fwlink/?LinkId=137082](http://go.microsoft.com/fwlink/?LinkId=137082).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f470-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="2f470-120">See Also</span></span>  
 [<span data-ttu-id="2f470-121">MSMQ 适配器概述</span><span class="sxs-lookup"><span data-stu-id="2f470-121">What Is the MSMQ Adapter?</span></span>](../core/what-is-the-msmq-adapter.md)