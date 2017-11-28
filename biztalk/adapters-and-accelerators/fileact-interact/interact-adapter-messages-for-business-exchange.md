---
title: "适用于业务 Exchange 交互适配器消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b443b8a-4e56-47f1-8d91-5c807fd54ccc
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d19e10940e6a83c24e9397f0df94d0fc54e4da38
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="interact-adapter-messages-for-business-exchange"></a><span data-ttu-id="9cf31-102">适用于业务 Exchange 交互适配器消息</span><span class="sxs-lookup"><span data-stu-id="9cf31-102">InterAct Adapter Messages for Business Exchange</span></span>
<span data-ttu-id="9cf31-103">在交互适配器端到端周期中有四条消息。</span><span class="sxs-lookup"><span data-stu-id="9cf31-103">There are four messages in the InterAct adapter end-to-end cycle.</span></span> <span data-ttu-id="9cf31-104">这些消息将 SWIFTNet 基元。</span><span class="sxs-lookup"><span data-stu-id="9cf31-104">These messages are SWIFTNet primitives.</span></span> <span data-ttu-id="9cf31-105">客户端基元、 SwInt:ExchangeRequest 和 SwInt:ExchangeResponse，前者构成的第一个和最后一个消息。</span><span class="sxs-lookup"><span data-stu-id="9cf31-105">The first and last messages comprise the client-side primitives, SwInt:ExchangeRequest and SwInt:ExchangeResponse.</span></span> <span data-ttu-id="9cf31-106">服务器端基元、 SwInt:HandleRequest 和 SwInt:HandleResponse，前者构成中间两条消息。</span><span class="sxs-lookup"><span data-stu-id="9cf31-106">The middle two messages comprise the server-side primitives, SwInt:HandleRequest and SwInt:HandleResponse.</span></span>  
  
 <span data-ttu-id="9cf31-107">在此级别的简化，有六个步骤在端到端消息周期中：</span><span class="sxs-lookup"><span data-stu-id="9cf31-107">At this level of simplification, there are six steps in the end-to-end message cycle:</span></span>  
  
1.  <span data-ttu-id="9cf31-108">客户端应用程序准备请求消息。</span><span class="sxs-lookup"><span data-stu-id="9cf31-108">The client application prepares the request message.</span></span>  
  
2.  <span data-ttu-id="9cf31-109">客户端应用程序将请求消息传递给 SWIFTNet。</span><span class="sxs-lookup"><span data-stu-id="9cf31-109">The client application passes the request message to SWIFTNet.</span></span>  
  
3.  <span data-ttu-id="9cf31-110">SWIFTNet 处理请求消息，并将其发送到服务器应用程序。</span><span class="sxs-lookup"><span data-stu-id="9cf31-110">SWIFTNet processes the request message, and sends it to the server application.</span></span>  
  
4.  <span data-ttu-id="9cf31-111">服务器应用程序从 SWIFTNet 接收请求消息。</span><span class="sxs-lookup"><span data-stu-id="9cf31-111">The server application receives the request message from SWIFTNet.</span></span>  
  
5.  <span data-ttu-id="9cf31-112">服务器应用程序准备响应消息。</span><span class="sxs-lookup"><span data-stu-id="9cf31-112">The server application prepares the response message.</span></span>  
  
6.  <span data-ttu-id="9cf31-113">服务器应用程序将响应消息传递给 SWIFTNet。</span><span class="sxs-lookup"><span data-stu-id="9cf31-113">The server application passes the response message to SWIFTNet.</span></span>  
  
7.  <span data-ttu-id="9cf31-114">SWIFTNet 处理响应消息，并将其发送到客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="9cf31-114">SWIFTNet processes the response message, and sends it to the client application.</span></span>  
  
8.  <span data-ttu-id="9cf31-115">客户端应用程序从 SWIFTNet 接收响应消息。</span><span class="sxs-lookup"><span data-stu-id="9cf31-115">The client application receives the response message from SWIFTNet.</span></span>  
  
 <span data-ttu-id="9cf31-116">下图显示交互消息交换。</span><span class="sxs-lookup"><span data-stu-id="9cf31-116">The following figure shows the InterAct message exchange.</span></span>  
  
 <span data-ttu-id="9cf31-117">![交互消息交换](../../adapters-and-accelerators/fileact-interact/media/12fbebc6-5ab7-4d7f-9f94-4069b22161fa.gif "12fbebc6-5ab7-4d7f-9f94-4069b22161fa")</span><span class="sxs-lookup"><span data-stu-id="9cf31-117">![InterAct message exchange](../../adapters-and-accelerators/fileact-interact/media/12fbebc6-5ab7-4d7f-9f94-4069b22161fa.gif "12fbebc6-5ab7-4d7f-9f94-4069b22161fa")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cf31-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9cf31-118">See Also</span></span>  
 <span data-ttu-id="9cf31-119">[交互适配器体系结构](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="9cf31-119">[InterAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="9cf31-120">[交互适配器组件](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md) </span><span class="sxs-lookup"><span data-stu-id="9cf31-120">[InterAct Adapter Components](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md) </span></span>  
 <span data-ttu-id="9cf31-121">[交互适配器客户端应用程序](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md) </span><span class="sxs-lookup"><span data-stu-id="9cf31-121">[InterAct Adapter Client Application](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md) </span></span>  
 <span data-ttu-id="9cf31-122">[交互适配器服务器应用程序](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md) </span><span class="sxs-lookup"><span data-stu-id="9cf31-122">[InterAct Adapter Server Application](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md) </span></span>  
 <span data-ttu-id="9cf31-123">[交互适配器存储和转发](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="9cf31-123">[InterAct Adapter Store and Forward](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md) </span></span>  
 <span data-ttu-id="9cf31-124">[交互适配器安全体系结构](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="9cf31-124">[InterAct Adapter Security Architecture](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md) </span></span>  
 <span data-ttu-id="9cf31-125">[交互适配器端到端可靠传递](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md) </span><span class="sxs-lookup"><span data-stu-id="9cf31-125">[InterAct Adapter End-to-End Reliable Delivery](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md) </span></span>  
 <span data-ttu-id="9cf31-126">[交互适配器状态监视](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md) </span><span class="sxs-lookup"><span data-stu-id="9cf31-126">[InterAct Adapter Status Monitoring](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md) </span></span>  
 [<span data-ttu-id="9cf31-127">交互适配器不可否认性</span><span class="sxs-lookup"><span data-stu-id="9cf31-127">InterAct Adapter Non-Repudiation</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)