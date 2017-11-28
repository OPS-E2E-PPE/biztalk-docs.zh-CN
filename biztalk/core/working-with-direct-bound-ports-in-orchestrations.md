---
title: "使用在业务流程中的直接绑定端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03a37ac0-5131-4d37-b60b-56763c460463
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e7b2b59ccdaa23271ee0707f19f4fd2cddc0508
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="working-with-direct-bound-ports-in-orchestrations"></a><span data-ttu-id="a53a3-102">在业务流程中使用直接绑定端口</span><span class="sxs-lookup"><span data-stu-id="a53a3-102">Working with Direct Bound Ports in Orchestrations</span></span>
<span data-ttu-id="a53a3-103">有三种类型的直接绑定的端口： MessageBox，自相关，和合作伙伴业务流程。</span><span class="sxs-lookup"><span data-stu-id="a53a3-103">There are three types of direct bound ports: MessageBox, self-correlating, and partner orchestration.</span></span>  
  
 <span data-ttu-id="a53a3-104">MessageBox 直接绑定端口允许发布-订阅设计模式。</span><span class="sxs-lookup"><span data-stu-id="a53a3-104">MessageBox direct bound ports allow for publish-subscribe design patterns.</span></span> <span data-ttu-id="a53a3-105">MessageBox 直接绑定端口发送的消息被发布到 MessageBox 数据库，消息接收方根据订阅从 MessageBox 数据库提取消息。</span><span class="sxs-lookup"><span data-stu-id="a53a3-105">Messages sent on a MessageBox direct bound port are published to the MessageBox database, where message recipients pick them up based on subscriptions.</span></span> <span data-ttu-id="a53a3-106">配置为 MessageBox 直接绑定端口的逻辑接收端口直接从 MessageBox 数据库获得消息。</span><span class="sxs-lookup"><span data-stu-id="a53a3-106">Logical receive ports configured as MessageBox direct bound ports get messages directly from the MessageBox database.</span></span> <span data-ttu-id="a53a3-107">激活**接收**形状，MessageBox 直接绑定接收端口 get 通过订阅到消息类型和筛选器表达式的消息。</span><span class="sxs-lookup"><span data-stu-id="a53a3-107">For activating **Receive** shapes, the MessageBox direct bound receive ports get the messages through subscriptions to the message type and the filter expression.</span></span> <span data-ttu-id="a53a3-108">非激活**接收**形状，MessageBox 直接绑定接收端口 get 通过订阅到消息类型和关联集的消息。</span><span class="sxs-lookup"><span data-stu-id="a53a3-108">For non-activating **Receive** shapes, the MessageBox direct bound receive ports get the messages through subscriptions to the message type and the correlation set.</span></span>  
  
 <span data-ttu-id="a53a3-109">自相关直接绑定端口可以帮助您设计异步业务流程间通信。</span><span class="sxs-lookup"><span data-stu-id="a53a3-109">Self-correlating direct bound ports assist you in designing asynchronous inter-orchestration communication.</span></span> <span data-ttu-id="a53a3-110">发送到自相关直接绑定端口的消息被路由到创建自相关直接绑定端口接收端的业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="a53a3-110">Messages sent to a self-correlating direct bound port are routed to the instance of the orchestration that created the receiving end of the self-correlated direct bound port.</span></span>  
  
 <span data-ttu-id="a53a3-111">合作伙伴业务流程直接绑定端口提供业务流程间通信。</span><span class="sxs-lookup"><span data-stu-id="a53a3-111">Partner orchestration direct bound ports provide for inter-orchestration communication.</span></span> <span data-ttu-id="a53a3-112">合作伙伴业务流程直接绑定端口发送的消息可以发送到预期的接收方业务流程，合作伙伴业务流程直接绑定端口接收的消息可以从预期的发送方业务流程接收。</span><span class="sxs-lookup"><span data-stu-id="a53a3-112">Messages sent on a partner orchestration direct bound port can be sent to an intended recipient orchestration, and messages received on a partner orchestration direct bound port can be received from an intended sender orchestration.</span></span>  
  
 <span data-ttu-id="a53a3-113">尽管使用了直接绑定（即消息似乎直接从一个业务流程转到另一个业务流程），实际上通过任何类型的逻辑端口发送的所有消息始终都经过 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="a53a3-113">Although with direct binding, the message appears to go directly from one orchestration to another, in fact any message sent through any type of logical port always travels through the MessageBox database.</span></span> <span data-ttu-id="a53a3-114">另外，直接绑定端口只是逻辑端口，因此直接绑定只是设计时的配置功能。</span><span class="sxs-lookup"><span data-stu-id="a53a3-114">Moreover, direct bound ports are only logical ports and therefore direct binding is only a design-time configuration feature.</span></span> <span data-ttu-id="a53a3-115">直接绑定端口无法绑定到物理端口，您只能在设计时更改直接绑定配置。</span><span class="sxs-lookup"><span data-stu-id="a53a3-115">A direct bound port cannot be bound to a physical port, and you can only change the direct binding configuration at design time.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a53a3-116">本节内容</span><span class="sxs-lookup"><span data-stu-id="a53a3-116">In This Section</span></span>  
  
-   [<span data-ttu-id="a53a3-117">如何直接使用 MessageBox 绑定端口</span><span class="sxs-lookup"><span data-stu-id="a53a3-117">How to Use MessageBox Direct Bound Ports</span></span>](../core/how-to-use-messagebox-direct-bound-ports.md)  
  
-   [<span data-ttu-id="a53a3-118">如何使用自关联 Direct 绑定端口</span><span class="sxs-lookup"><span data-stu-id="a53a3-118">How to Use Self-Correlating Direct Bound Ports</span></span>](../core/how-to-use-self-correlating-direct-bound-ports.md)  
  
-   [<span data-ttu-id="a53a3-119">如何直接使用合作伙伴业务流程绑定端口</span><span class="sxs-lookup"><span data-stu-id="a53a3-119">How to Use Partner Orchestration Direct Bound Ports</span></span>](../core/how-to-use-partner-orchestration-direct-bound-ports.md)  
  
## <a name="see-also"></a><span data-ttu-id="a53a3-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a53a3-120">See Also</span></span>  
 [<span data-ttu-id="a53a3-121">端口绑定</span><span class="sxs-lookup"><span data-stu-id="a53a3-121">Port Bindings</span></span>](../core/port-bindings.md)