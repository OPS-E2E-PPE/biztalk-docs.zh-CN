---
title: "交互适配器端到端可靠传递 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ac7c22f2-ee4a-4e9b-af40-da7eb58daf51
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90ca0fc7ae5872598ed9a61cd7541017a6a39667
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="interact-adapter-end-to-end-reliable-delivery"></a><span data-ttu-id="0f4e1-102">交互适配器端到端可靠传递</span><span class="sxs-lookup"><span data-stu-id="0f4e1-102">InterAct Adapter End-to-End Reliable Delivery</span></span>
<span data-ttu-id="0f4e1-103">时发送给收件人电子邮件或文件，我们建议你确保传递的消息或文件，和的业务事务包含在这些执行不详细的时间比预期。</span><span class="sxs-lookup"><span data-stu-id="0f4e1-103">When sending messages or files to a recipient, we recommend that you ensure that the message or file is delivered, and that the business transaction(s) contained in these are executed no more times than anticipated.</span></span>  
  
 <span data-ttu-id="0f4e1-104">当互相进行通信这两个实体可以使用持久存储 （例如，由持久性面向消息的中间件和使用它的接口应用程序提供） 时，很容易地实现可靠的传递，如果进行通信的方式标准化察觉到的状态消息。</span><span class="sxs-lookup"><span data-stu-id="0f4e1-104">When both entities communicating with each other can use a persistent storage (for example, provided by a persistent message-oriented middleware and an interface application using it), it is easy to implement a reliable delivery if the way to communicate the perceived status of the message is standardized.</span></span>  
  
 <span data-ttu-id="0f4e1-105">下图显示 E2EControl 的结构的示例。</span><span class="sxs-lookup"><span data-stu-id="0f4e1-105">The following figure shows an example of the structure of the E2EControl.</span></span>  
  
 <span data-ttu-id="0f4e1-106">![结束 &#45; 到 &#45; 最终控件](../../adapters-and-accelerators/fileact-interact/media/63e39b43-118e-4572-9d75-21770253a1ee.gif "63e39b43-118e-4572-9d75-21770253a1ee")</span><span class="sxs-lookup"><span data-stu-id="0f4e1-106">![End&#45;to&#45;end control](../../adapters-and-accelerators/fileact-interact/media/63e39b43-118e-4572-9d75-21770253a1ee.gif "63e39b43-118e-4572-9d75-21770253a1ee")</span></span>  
  
 <span data-ttu-id="0f4e1-107">图中所示的示例中的元素是在 SwInt:Request 内发送和传递到接收应用程序 SwInt:RequestHandle 内不变。</span><span class="sxs-lookup"><span data-stu-id="0f4e1-107">The element in the example shown in the figure is sent within the SwInt:Request and delivered unchanged within the SwInt:RequestHandle to the receiving application.</span></span> <span data-ttu-id="0f4e1-108">行 02 允许为请求分配的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="0f4e1-108">Line 02 allows assigning a unique identifier to the request.</span></span> <span data-ttu-id="0f4e1-109">在同一请求的每个后续重新传输上重复此唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="0f4e1-109">This unique identifier is repeated in each subsequent re-transmission of the same request.</span></span>  
  
 <span data-ttu-id="0f4e1-110">构造此标识符的方式留给实施者，但通常基于 uuidgen()，如系统调用也可能是计算 sha-1 上发送的请求的结果 （使用带前缀的 Sw:MsgId，然后将它通过 base64 编码 sha-1 s字符串）。</span><span class="sxs-lookup"><span data-stu-id="0f4e1-110">The way this identifier is constructed is left to the implementer, but typically it is based on a system call such as uuidgen(), or it may be the result of computing a SHA-1 on the request to be sent (with a prefixed Sw:MsgId and then replace it by the base64 encoded SHA-1 string).</span></span> <span data-ttu-id="0f4e1-111">主要需求是全局唯一 （具有极高的概率）。</span><span class="sxs-lookup"><span data-stu-id="0f4e1-111">The main requirement is that it is globally unique (with a very high probability).</span></span>  
  
 <span data-ttu-id="0f4e1-112">Sw:CreationTime 是创建的原始请求的时间。</span><span class="sxs-lookup"><span data-stu-id="0f4e1-112">The Sw:CreationTime is the time of creation of the original request.</span></span> <span data-ttu-id="0f4e1-113">它是一个可选参数，但它可用于限制最终搜索以前的此消息的通信尝试。</span><span class="sxs-lookup"><span data-stu-id="0f4e1-113">It is an optional parameter, but it is useful to limit eventual searches for previous communication attempts of this message.</span></span>  
  
 <span data-ttu-id="0f4e1-114">元素 Sw:PDIndication 不存在，表示这是第二个或更多尝试将消息传输。</span><span class="sxs-lookup"><span data-stu-id="0f4e1-114">The element Sw:PDIndication is present to indicate that this is a second or further attempt to transmit the message.</span></span> <span data-ttu-id="0f4e1-115">然后，接收应用程序所知的 E2EControl 可用 Sw:MsgId 来返回查找或不是否已收到的消息。</span><span class="sxs-lookup"><span data-stu-id="0f4e1-115">The receiving application that is aware of the E2EControl can then use the Sw:MsgId to find back whether the message has been received or not.</span></span> <span data-ttu-id="0f4e1-116">可选 Sw:EmissionList 包含以前尝试的时间。</span><span class="sxs-lookup"><span data-stu-id="0f4e1-116">The optional Sw:EmissionList contains the time of the previous attempts.</span></span> <span data-ttu-id="0f4e1-117">此时间是使用 Sw:GetDateTime 函数时收到发件人发件人 （采用世界时间） 的本地时间。</span><span class="sxs-lookup"><span data-stu-id="0f4e1-117">This time is the local time of the sender (in universal time) as got by the Sender when using the Sw:GetDateTime function.</span></span> <span data-ttu-id="0f4e1-118">再次，这可能会十分有用来限制搜索。</span><span class="sxs-lookup"><span data-stu-id="0f4e1-118">Again this could be useful to limit searches.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f4e1-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0f4e1-119">See Also</span></span>  
 <span data-ttu-id="0f4e1-120">[交互适配器体系结构](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="0f4e1-120">[InterAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="0f4e1-121">[交互适配器组件](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md) </span><span class="sxs-lookup"><span data-stu-id="0f4e1-121">[InterAct Adapter Components](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md) </span></span>  
 <span data-ttu-id="0f4e1-122">[适用于业务 Exchange 交互适配器消息](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md) </span><span class="sxs-lookup"><span data-stu-id="0f4e1-122">[InterAct Adapter Messages for Business Exchange](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md) </span></span>  
 <span data-ttu-id="0f4e1-123">[交互适配器客户端应用程序](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md) </span><span class="sxs-lookup"><span data-stu-id="0f4e1-123">[InterAct Adapter Client Application](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md) </span></span>  
 <span data-ttu-id="0f4e1-124">[交互适配器服务器应用程序](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md) </span><span class="sxs-lookup"><span data-stu-id="0f4e1-124">[InterAct Adapter Server Application](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md) </span></span>  
 <span data-ttu-id="0f4e1-125">[交互适配器存储和转发](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="0f4e1-125">[InterAct Adapter Store and Forward](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md) </span></span>  
 <span data-ttu-id="0f4e1-126">[交互适配器安全体系结构](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="0f4e1-126">[InterAct Adapter Security Architecture](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md) </span></span>  
 <span data-ttu-id="0f4e1-127">[交互适配器状态监视](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md) </span><span class="sxs-lookup"><span data-stu-id="0f4e1-127">[InterAct Adapter Status Monitoring](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md) </span></span>  
 [<span data-ttu-id="0f4e1-128">交互适配器不可否认性</span><span class="sxs-lookup"><span data-stu-id="0f4e1-128">InterAct Adapter Non-Repudiation</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)