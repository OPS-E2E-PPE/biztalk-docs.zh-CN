---
title: 使用在业务流程直接绑定端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 03a37ac0-5131-4d37-b60b-56763c460463
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3344298fbd569d1e8e3161d6857bddb6fb453aeb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65277281"
---
# <a name="working-with-direct-bound-ports-in-orchestrations"></a><span data-ttu-id="9b083-102">使用在业务流程直接绑定端口</span><span class="sxs-lookup"><span data-stu-id="9b083-102">Working with Direct Bound Ports in Orchestrations</span></span>
<span data-ttu-id="9b083-103">有三种类型的直接绑定端口：MessageBox、 自相关，配置文件和合作伙伴业务流程。</span><span class="sxs-lookup"><span data-stu-id="9b083-103">There are three types of direct bound ports: MessageBox, self-correlating, and partner orchestration.</span></span>  
  
 <span data-ttu-id="9b083-104">MessageBox 直接绑定的端口允许发布-订阅设计模式。</span><span class="sxs-lookup"><span data-stu-id="9b083-104">MessageBox direct bound ports allow for publish-subscribe design patterns.</span></span> <span data-ttu-id="9b083-105">MessageBox 直接绑定端口上发送的消息发布到 MessageBox 数据库，其中消息收件人中选取它们根据订阅。</span><span class="sxs-lookup"><span data-stu-id="9b083-105">Messages sent on a MessageBox direct bound port are published to the MessageBox database, where message recipients pick them up based on subscriptions.</span></span> <span data-ttu-id="9b083-106">逻辑接收端口配置为 MessageBox 直接绑定的端口从 MessageBox 数据库中直接获取消息。</span><span class="sxs-lookup"><span data-stu-id="9b083-106">Logical receive ports configured as MessageBox direct bound ports get messages directly from the MessageBox database.</span></span> <span data-ttu-id="9b083-107">用于激活**接收**形状，MessageBox 直接绑定接收端口获取通过对消息类型和筛选器表达式订阅消息。</span><span class="sxs-lookup"><span data-stu-id="9b083-107">For activating **Receive** shapes, the MessageBox direct bound receive ports get the messages through subscriptions to the message type and the filter expression.</span></span> <span data-ttu-id="9b083-108">对于非激活**接收**形状，MessageBox 直接绑定接收端口获取通过对消息类型和关联集的订阅的消息。</span><span class="sxs-lookup"><span data-stu-id="9b083-108">For non-activating **Receive** shapes, the MessageBox direct bound receive ports get the messages through subscriptions to the message type and the correlation set.</span></span>  
  
 <span data-ttu-id="9b083-109">自相关直接绑定的端口帮助您设计异步业务流程间通信。</span><span class="sxs-lookup"><span data-stu-id="9b083-109">Self-correlating direct bound ports assist you in designing asynchronous inter-orchestration communication.</span></span> <span data-ttu-id="9b083-110">发送到自相关直接绑定端口的消息被路由到创建的接收端的自相关直接绑定端口的业务流程的实例。</span><span class="sxs-lookup"><span data-stu-id="9b083-110">Messages sent to a self-correlating direct bound port are routed to the instance of the orchestration that created the receiving end of the self-correlated direct bound port.</span></span>  
  
 <span data-ttu-id="9b083-111">合作伙伴业务流程直接绑定的端口提供业务流程间通信。</span><span class="sxs-lookup"><span data-stu-id="9b083-111">Partner orchestration direct bound ports provide for inter-orchestration communication.</span></span> <span data-ttu-id="9b083-112">可以从预期的发送方业务流程接收直接绑定的端口可以发送到预期的接收方业务流程，合作伙伴业务流程上发送的消息和合作伙伴业务流程直接绑定端口上接收到的消息。</span><span class="sxs-lookup"><span data-stu-id="9b083-112">Messages sent on a partner orchestration direct bound port can be sent to an intended recipient orchestration, and messages received on a partner orchestration direct bound port can be received from an intended sender orchestration.</span></span>  
  
 <span data-ttu-id="9b083-113">尽管使用了直接绑定消息似乎转直接从一个业务流程到另一个，实际上通过发送任何消息，但是任何类型的逻辑端口始终都经过 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="9b083-113">Although with direct binding, the message appears to go directly from one orchestration to another, in fact any message sent through any type of logical port always travels through the MessageBox database.</span></span> <span data-ttu-id="9b083-114">此外，直接绑定的端口只是逻辑端口，并因此直接绑定仅设计时配置功能。</span><span class="sxs-lookup"><span data-stu-id="9b083-114">Moreover, direct bound ports are only logical ports and therefore direct binding is only a design-time configuration feature.</span></span> <span data-ttu-id="9b083-115">直接绑定的端口无法绑定到物理端口，并仅可以更改在设计时直接绑定配置。</span><span class="sxs-lookup"><span data-stu-id="9b083-115">A direct bound port cannot be bound to a physical port, and you can only change the direct binding configuration at design time.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9b083-116">本节内容</span><span class="sxs-lookup"><span data-stu-id="9b083-116">In This Section</span></span>  
  
-   [<span data-ttu-id="9b083-117">如何使用 MessageBox 直接绑定端口</span><span class="sxs-lookup"><span data-stu-id="9b083-117">How to Use MessageBox Direct Bound Ports</span></span>](../core/how-to-use-messagebox-direct-bound-ports.md)  
  
-   [<span data-ttu-id="9b083-118">如何使用自相关直接绑定端口</span><span class="sxs-lookup"><span data-stu-id="9b083-118">How to Use Self-Correlating Direct Bound Ports</span></span>](../core/how-to-use-self-correlating-direct-bound-ports.md)  
  
-   [<span data-ttu-id="9b083-119">如何使用合作伙伴业务流程直接绑定端口</span><span class="sxs-lookup"><span data-stu-id="9b083-119">How to Use Partner Orchestration Direct Bound Ports</span></span>](../core/how-to-use-partner-orchestration-direct-bound-ports.md)  
  
## <a name="see-also"></a><span data-ttu-id="9b083-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="9b083-120">See Also</span></span>  
 [<span data-ttu-id="9b083-121">端口绑定</span><span class="sxs-lookup"><span data-stu-id="9b083-121">Port Bindings</span></span>](../core/port-bindings.md)