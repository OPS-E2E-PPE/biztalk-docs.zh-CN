---
title: 交互适配器端到端可靠传递 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ac7c22f2-ee4a-4e9b-af40-da7eb58daf51
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b2d7ccacde04243c2635bbe5adcafad3f2b9987
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366702"
---
# <a name="interact-adapter-end-to-end-reliable-delivery"></a><span data-ttu-id="5f65c-102">交互适配器端到端可靠传递</span><span class="sxs-lookup"><span data-stu-id="5f65c-102">InterAct Adapter End-to-End Reliable Delivery</span></span>
<span data-ttu-id="5f65c-103">在向收件人发送的消息或文件，我们建议确保传递的消息或文件，和的业务事务包含在这些执行没有更多的时间比预期。</span><span class="sxs-lookup"><span data-stu-id="5f65c-103">When sending messages or files to a recipient, we recommend that you ensure that the message or file is delivered, and that the business transaction(s) contained in these are executed no more times than anticipated.</span></span>  
  
 <span data-ttu-id="5f65c-104">当这两个实体相互通信可以使用持久存储 （例如，持久面向消息的中间件和使用它的接口应用程序提供的） 时，很容易地实现可靠的传递，如果进行通信的方式标准化感知到的消息的状态。</span><span class="sxs-lookup"><span data-stu-id="5f65c-104">When both entities communicating with each other can use a persistent storage (for example, provided by a persistent message-oriented middleware and an interface application using it), it is easy to implement a reliable delivery if the way to communicate the perceived status of the message is standardized.</span></span>  
  
 <span data-ttu-id="5f65c-105">下图显示了 E2EControl 结构的示例。</span><span class="sxs-lookup"><span data-stu-id="5f65c-105">The following figure shows an example of the structure of the E2EControl.</span></span>  
  
 <span data-ttu-id="5f65c-106">![结束&#45;到&#45;结束控制](../../adapters-and-accelerators/fileact-interact/media/63e39b43-118e-4572-9d75-21770253a1ee.gif "63e39b43-118e-4572-9d75-21770253a1ee")</span><span class="sxs-lookup"><span data-stu-id="5f65c-106">![End&#45;to&#45;end control](../../adapters-and-accelerators/fileact-interact/media/63e39b43-118e-4572-9d75-21770253a1ee.gif "63e39b43-118e-4572-9d75-21770253a1ee")</span></span>  
  
 <span data-ttu-id="5f65c-107">在图中所示的示例中的元素是 SwInt:Request 内发送和传递到接收应用程序 SwInt:RequestHandle 内保持不变。</span><span class="sxs-lookup"><span data-stu-id="5f65c-107">The element in the example shown in the figure is sent within the SwInt:Request and delivered unchanged within the SwInt:RequestHandle to the receiving application.</span></span> <span data-ttu-id="5f65c-108">行 02 允许向请求分配的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="5f65c-108">Line 02 allows assigning a unique identifier to the request.</span></span> <span data-ttu-id="5f65c-109">在同一请求的每个后续重新传输中重复此唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="5f65c-109">This unique identifier is repeated in each subsequent re-transmission of the same request.</span></span>  
  
 <span data-ttu-id="5f65c-110">构造此标识符的方式由实施者，但通常基于系统调用，如 uuidgen()，也可能是计算 sha-1 上要发送的请求的结果 （使用带前缀的 Sw:MsgId，然后替换它的 base64 编码的 SHA 1 s字符串）。</span><span class="sxs-lookup"><span data-stu-id="5f65c-110">The way this identifier is constructed is left to the implementer, but typically it is based on a system call such as uuidgen(), or it may be the result of computing a SHA-1 on the request to be sent (with a prefixed Sw:MsgId and then replace it by the base64 encoded SHA-1 string).</span></span> <span data-ttu-id="5f65c-111">主要要求是全局唯一 （具有非常高的概率）。</span><span class="sxs-lookup"><span data-stu-id="5f65c-111">The main requirement is that it is globally unique (with a very high probability).</span></span>  
  
 <span data-ttu-id="5f65c-112">Sw:CreationTime 是创建的原始请求的时间。</span><span class="sxs-lookup"><span data-stu-id="5f65c-112">The Sw:CreationTime is the time of creation of the original request.</span></span> <span data-ttu-id="5f65c-113">它是一个可选参数，但它可用于限制为此消息的上一个通信尝试最终搜索。</span><span class="sxs-lookup"><span data-stu-id="5f65c-113">It is an optional parameter, but it is useful to limit eventual searches for previous communication attempts of this message.</span></span>  
  
 <span data-ttu-id="5f65c-114">元素 Sw:PDIndication 是存在以指明这是第二个或更多尝试传输消息。</span><span class="sxs-lookup"><span data-stu-id="5f65c-114">The element Sw:PDIndication is present to indicate that this is a second or further attempt to transmit the message.</span></span> <span data-ttu-id="5f65c-115">接收应用程序可以识别的 E2EControl 然后可以使用 Sw:MsgId 是否收到的消息或不返回查找。</span><span class="sxs-lookup"><span data-stu-id="5f65c-115">The receiving application that is aware of the E2EControl can then use the Sw:MsgId to find back whether the message has been received or not.</span></span> <span data-ttu-id="5f65c-116">可选 Sw:EmissionList 包含以前的尝试的时间。</span><span class="sxs-lookup"><span data-stu-id="5f65c-116">The optional Sw:EmissionList contains the time of the previous attempts.</span></span> <span data-ttu-id="5f65c-117">这一次是本地时间 （以世界时） 发件人的如使用 Sw:GetDateTime 函数时由发件人获得。</span><span class="sxs-lookup"><span data-stu-id="5f65c-117">This time is the local time of the sender (in universal time) as got by the Sender when using the Sw:GetDateTime function.</span></span> <span data-ttu-id="5f65c-118">再次，这可能会是用于限制搜索。</span><span class="sxs-lookup"><span data-stu-id="5f65c-118">Again this could be useful to limit searches.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f65c-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="5f65c-119">See Also</span></span>  
 <span data-ttu-id="5f65c-120">[InterAct 适配器体系结构](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="5f65c-120">[InterAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="5f65c-121">[InterAct 适配器组件](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md) </span><span class="sxs-lookup"><span data-stu-id="5f65c-121">[InterAct Adapter Components](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md) </span></span>  
 <span data-ttu-id="5f65c-122">[Business Exchange 的 interAct 适配器消息](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md) </span><span class="sxs-lookup"><span data-stu-id="5f65c-122">[InterAct Adapter Messages for Business Exchange](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md) </span></span>  
 <span data-ttu-id="5f65c-123">[InterAct 适配器客户端应用程序](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md) </span><span class="sxs-lookup"><span data-stu-id="5f65c-123">[InterAct Adapter Client Application](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md) </span></span>  
 <span data-ttu-id="5f65c-124">[InterAct 适配器服务器应用程序](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md) </span><span class="sxs-lookup"><span data-stu-id="5f65c-124">[InterAct Adapter Server Application](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md) </span></span>  
 <span data-ttu-id="5f65c-125">[InterAct 适配器存储和转发](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="5f65c-125">[InterAct Adapter Store and Forward](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md) </span></span>  
 <span data-ttu-id="5f65c-126">[InterAct 适配器安全体系结构](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="5f65c-126">[InterAct Adapter Security Architecture](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md) </span></span>  
 <span data-ttu-id="5f65c-127">[InterAct 适配器状态监视](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md) </span><span class="sxs-lookup"><span data-stu-id="5f65c-127">[InterAct Adapter Status Monitoring](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md) </span></span>  
 [<span data-ttu-id="5f65c-128">InterAct 适配器不可否认性</span><span class="sxs-lookup"><span data-stu-id="5f65c-128">InterAct Adapter Non-Repudiation</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)