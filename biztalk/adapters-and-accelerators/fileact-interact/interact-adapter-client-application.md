---
title: InterAct 适配器客户端应用程序 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cdab4624-0fc2-42a3-9867-8f77e144b40c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 935e7fd0672db3445e850ec470ed90e86ed8bfeb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366942"
---
# <a name="interact-adapter-client-application"></a><span data-ttu-id="48885-102">InterAct 适配器客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="48885-102">InterAct Adapter Client Application</span></span>
<span data-ttu-id="48885-103">交互适配器客户端应用程序请求的消息是从客户端应用程序到客户端的 SWIFTNet 链接 (SNL) 传递的 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="48885-103">InterAct adapter client application request messages are XML documents passed from the client application to the client-side SWIFTNet Link (SNL).</span></span> <span data-ttu-id="48885-104">作为客户端上运用的 SWIFTNet 请求/响应基元的第一部分发生此类型的消息。</span><span class="sxs-lookup"><span data-stu-id="48885-104">Messages of this type occur as the first part of the SWIFTNet Request/Response primitives exercised on the client side.</span></span>  
  
 <span data-ttu-id="48885-105">本主题介绍 SwInt:ExchangeRequest 消息。</span><span class="sxs-lookup"><span data-stu-id="48885-105">This topic describes the SwInt:ExchangeRequest message.</span></span> <span data-ttu-id="48885-106">它用于对 SWIFTNet"同步"客户端的调用。</span><span class="sxs-lookup"><span data-stu-id="48885-106">It is used for “synchronous” client-side calls to SWIFTNet.</span></span> <span data-ttu-id="48885-107">在此上下文中，"同步"意味着，函数调用将会阻止客户端应用程序，强制对它进行等待，直到从服务器端应用程序收到的响应。</span><span class="sxs-lookup"><span data-stu-id="48885-107">In this context, “synchronous” means that the function call blocks the client application, forcing it to wait until the Response is received from the server-side application.</span></span> <span data-ttu-id="48885-108">（或者，或者，出现错误条件并返回到客户端报告该错误。）</span><span class="sxs-lookup"><span data-stu-id="48885-108">(Or, alternatively, an error condition occurs and that error is reported back to the client.)</span></span>  
  
 <span data-ttu-id="48885-109">加密块 (SwSec:Crypto)，如果它们存在，则包含消息签名和/或验证处理的结果。</span><span class="sxs-lookup"><span data-stu-id="48885-109">The cryptographic blocks (SwSec:Crypto), if they exist, contain the results of message signing and/or verification processing.</span></span> <span data-ttu-id="48885-110">此外，在某些处理阶段，它们可能包含直接 SNL 要执行的加密处理的说明。</span><span class="sxs-lookup"><span data-stu-id="48885-110">Also, at certain processing stages, they may contain instructions that direct cryptographic processing that is to be performed by the SNL.</span></span>  
  
## <a name="interact-adapter-payload-format"></a><span data-ttu-id="48885-111">交互适配器有效负载格式</span><span class="sxs-lookup"><span data-stu-id="48885-111">InterAct Adapter Payload Format</span></span>  
 <span data-ttu-id="48885-112">请求有效负载包含业务消息的实质。</span><span class="sxs-lookup"><span data-stu-id="48885-112">The Request Payload contains the substance of the business message.</span></span> <span data-ttu-id="48885-113">有效负载的结构必须符合格式正确的 XML （这只是意味着负载不会中断 XML 分析，但在这种情况下，不需要使用 XML 文档结构） 的要求。</span><span class="sxs-lookup"><span data-stu-id="48885-113">The structure of the payload must conform to the requirements of well-formed XML (this simply means that the payload does not break the XML parsing, but as such, it does not have to use the XML document structure).</span></span> <span data-ttu-id="48885-114">如果应用 SWIFTNet 消息验证，则负载必须遵守其他结构要求。</span><span class="sxs-lookup"><span data-stu-id="48885-114">If SWIFTNet Message Validation is applied, then there are other structural requirements to which the payload must conform.</span></span> <span data-ttu-id="48885-115">除此之外，由业务应用程序确定的负载结构和内容。</span><span class="sxs-lookup"><span data-stu-id="48885-115">Aside from that, the payload structure and contents are determined by the business application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48885-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="48885-116">See Also</span></span>  
 <span data-ttu-id="48885-117">[InterAct 适配器体系结构](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="48885-117">[InterAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="48885-118">[InterAct 适配器组件](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md) </span><span class="sxs-lookup"><span data-stu-id="48885-118">[InterAct Adapter Components](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md) </span></span>  
 <span data-ttu-id="48885-119">[Business Exchange 的 interAct 适配器消息](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md) </span><span class="sxs-lookup"><span data-stu-id="48885-119">[InterAct Adapter Messages for Business Exchange](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md) </span></span>  
 <span data-ttu-id="48885-120">[InterAct 适配器服务器应用程序](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md) </span><span class="sxs-lookup"><span data-stu-id="48885-120">[InterAct Adapter Server Application](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md) </span></span>  
 <span data-ttu-id="48885-121">[InterAct 适配器存储和转发](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="48885-121">[InterAct Adapter Store and Forward](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md) </span></span>  
 <span data-ttu-id="48885-122">[InterAct 适配器安全体系结构](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="48885-122">[InterAct Adapter Security Architecture](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md) </span></span>  
 <span data-ttu-id="48885-123">[交互适配器端到端可靠传递](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md) </span><span class="sxs-lookup"><span data-stu-id="48885-123">[InterAct Adapter End-to-End Reliable Delivery](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md) </span></span>  
 <span data-ttu-id="48885-124">[InterAct 适配器状态监视](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md) </span><span class="sxs-lookup"><span data-stu-id="48885-124">[InterAct Adapter Status Monitoring](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md) </span></span>  
 [<span data-ttu-id="48885-125">InterAct 适配器不可否认性</span><span class="sxs-lookup"><span data-stu-id="48885-125">InterAct Adapter Non-Repudiation</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)