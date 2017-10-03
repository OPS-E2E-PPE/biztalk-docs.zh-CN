---
title: "SWIFTNet 客户端和服务器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 89d9f54f-af16-4f14-bbe4-8306758320d8
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ea3a1b974a26f90d03bb65675c1c4e8966720f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="swiftnet-client-and-server"></a><span data-ttu-id="158fa-102">SWIFTNet 客户端和服务器</span><span class="sxs-lookup"><span data-stu-id="158fa-102">SWIFTNet Client and Server</span></span>
<span data-ttu-id="158fa-103">SWIFT 使用条款客户端和服务器来描述发送和接收。</span><span class="sxs-lookup"><span data-stu-id="158fa-103">SWIFT uses the terms client and server to describe sending and receiving.</span></span> <span data-ttu-id="158fa-104">SWIFT 客户端是一个过程，调用 SWIFTNet 链接 (SNL) 以通过 SWIFTNet 启动的通信。</span><span class="sxs-lookup"><span data-stu-id="158fa-104">A SWIFT client is a process that calls the SWIFTNet Link (SNL) to initiate communication over SWIFTNet.</span></span> <span data-ttu-id="158fa-105">在 BizTalk Server 中，这被称为发送适配器。</span><span class="sxs-lookup"><span data-stu-id="158fa-105">In BizTalk Server, this is called the send adapter.</span></span> <span data-ttu-id="158fa-106">SWIFT 服务器是时流量经过 SWIFTNet SNL 由调用程序。</span><span class="sxs-lookup"><span data-stu-id="158fa-106">A SWIFT server is a program that is called by the SNL when traffic comes in over SWIFTNet.</span></span> <span data-ttu-id="158fa-107">在 BizTalk Server 中，这被称为接收适配器。</span><span class="sxs-lookup"><span data-stu-id="158fa-107">In BizTalk Server, this is called the receive adapter.</span></span>  
  
 <span data-ttu-id="158fa-108">不要混淆 SWIFT 客户端和业务客户端和服务器的服务器。</span><span class="sxs-lookup"><span data-stu-id="158fa-108">Do not confuse the SWIFT client and server with the business client and server.</span></span> <span data-ttu-id="158fa-109">例如，客户端 （组织） 依赖于由服务器 （组织） 提供的服务。</span><span class="sxs-lookup"><span data-stu-id="158fa-109">For example, a client (organization) relies on the services provided by a server (organization).</span></span> <span data-ttu-id="158fa-110">如果服务器 （组织） 想要启动与客户端 （组织） 的通信，它必须使用 SNL 客户端应用程序进行管理，以及客户端 （组织） 必须具有用于接收传入流量的 SNL 服务器应用程序。</span><span class="sxs-lookup"><span data-stu-id="158fa-110">If the server (organization) wants to initiate a communication with the client (organization), it must use an SNL client application to do so, and the client (organization) must have an SNL server application to receive the incoming traffic.</span></span> <span data-ttu-id="158fa-111">下图对此进行了描述。</span><span class="sxs-lookup"><span data-stu-id="158fa-111">This is described in the following figure.</span></span>  
  
 <span data-ttu-id="158fa-112">![客户端和服务器之间的 SWIFTNet 关系](../../adapters-and-accelerators/fileact-interact/media/7ad5d877-19d4-431f-9358-d5ae278cf945.gif "7ad5d877-19d4-431f-9358-d5ae278cf945")</span><span class="sxs-lookup"><span data-stu-id="158fa-112">![SWIFTNet relationship between client and server](../../adapters-and-accelerators/fileact-interact/media/7ad5d877-19d4-431f-9358-d5ae278cf945.gif "7ad5d877-19d4-431f-9358-d5ae278cf945")</span></span>  
  
 <span data-ttu-id="158fa-113">SNL 假定客户端和服务器应用程序是在命令提示符下启动的可执行文件。</span><span class="sxs-lookup"><span data-stu-id="158fa-113">SNL assumes both client and server applications are executables started from the command prompt.</span></span> <span data-ttu-id="158fa-114">它们都链接到 SNL API DLL，而与实际 SNL 实例进程通信。</span><span class="sxs-lookup"><span data-stu-id="158fa-114">They both link to the SNL API DLL, which communicates with the actual SNL instance process.</span></span>  
  
## <a name="snl-client-applications"></a><span data-ttu-id="158fa-115">SNL 客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="158fa-115">SNL client applications</span></span>  
 <span data-ttu-id="158fa-116">SNL 客户端应用程序依赖于如下所述 SwCall API。</span><span class="sxs-lookup"><span data-stu-id="158fa-116">SNL client applications rely on the SwCall API described below.</span></span> <span data-ttu-id="158fa-117">从技术角度讲，典型的客户端应用程序可以描述，如下所示：</span><span class="sxs-lookup"><span data-stu-id="158fa-117">Technically speaking, a typical client application can be described as follows:</span></span>  
  
```  
Main:  
  Initialize SNL API  
  Repeat  
    Call SwCall API  
  Until shutdown  
```  
  
 <span data-ttu-id="158fa-118">SNL 客户端应用程序必须在专用的过程中，运行，因为 SNL 引用客户端上下文的进程 id。</span><span class="sxs-lookup"><span data-stu-id="158fa-118">SNL client applications must run in a dedicated process, because SNL references the client context by process ID.</span></span> <span data-ttu-id="158fa-119">SNL 同步使用 SwCall 炫资源的调用。</span><span class="sxs-lookup"><span data-stu-id="158fa-119">SNL synchronizes calls that use Tuxedo resources to SwCall.</span></span> <span data-ttu-id="158fa-120">因此，只有一次单个客户端线程可以有效地执行 SwCall。</span><span class="sxs-lookup"><span data-stu-id="158fa-120">As a result, only a single client thread at a time can effectively execute a SwCall.</span></span>  
  
 <span data-ttu-id="158fa-121">客户端支持的同步通信模式。</span><span class="sxs-lookup"><span data-stu-id="158fa-121">The client supports the synchronous communication mode.</span></span> <span data-ttu-id="158fa-122">这意味着响应再次从服务器时发生 SWCall 回报。</span><span class="sxs-lookup"><span data-stu-id="158fa-122">This means that the return on the SWCall occurs when the response comes back from the server.</span></span> <span data-ttu-id="158fa-123">在此返回后才可以执行下一步 SwCall。</span><span class="sxs-lookup"><span data-stu-id="158fa-123">The next SwCall can be performed only after this return.</span></span>  
  
## <a name="snl-server-applications"></a><span data-ttu-id="158fa-124">SNL 服务器应用程序</span><span class="sxs-lookup"><span data-stu-id="158fa-124">SNL server applications</span></span>  
 <span data-ttu-id="158fa-125">SNL 服务器应用程序是客户端应用程序比稍微复杂。</span><span class="sxs-lookup"><span data-stu-id="158fa-125">SNL server applications are slightly more complex than the client applications.</span></span> <span data-ttu-id="158fa-126">服务器应用程序在执行到 SNL DLL 的阻止调用之前注册回调函数。</span><span class="sxs-lookup"><span data-stu-id="158fa-126">Server applications register callback functions before performing a blocking call into the SNL DLL.</span></span> <span data-ttu-id="158fa-127">从技术角度讲，典型的服务器应用程序可以描述，如下所示：</span><span class="sxs-lookup"><span data-stu-id="158fa-127">Technically speaking, a typical server application can be described as follows:</span></span>  
  
```  
Main:  
  Initialize SNL API  
  Call SwRegisterSwCallback, registering the Callback function  
  Call SwServer, block and receive callbacks  
  
Callback(Request):  
  Process Request  
  Return Response  
```  
  
 <span data-ttu-id="158fa-128">服务器应用程序可以调用的回调函数中 SwCall API。</span><span class="sxs-lookup"><span data-stu-id="158fa-128">The server application can call the SwCall API while in the callback function.</span></span> <span data-ttu-id="158fa-129">在某些情况下，则必须调用 SwCall 能够以生成所需的结果或响应。</span><span class="sxs-lookup"><span data-stu-id="158fa-129">In some cases it must call SwCall to be able to produce the desired result or response.</span></span> <span data-ttu-id="158fa-130">但是，服务器应用程序永远不会可以通过网络启动的通信。</span><span class="sxs-lookup"><span data-stu-id="158fa-130">However, a server application can never initiate a communication over the network.</span></span> <span data-ttu-id="158fa-131">服务器应用程序绝不会客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="158fa-131">A server application can never be a client application.</span></span>  
  
 <span data-ttu-id="158fa-132">下图中，在调用标记为**初始化**是用于 SNL API 初始化过程中，需要多个调用的抽象。</span><span class="sxs-lookup"><span data-stu-id="158fa-132">In the following figure, the call labeled **Initialize** is an abstraction for the SNL API initialization process, which requires multiple calls.</span></span> <span data-ttu-id="158fa-133">标记为调用**SwCallback()**将重复几次，并调用标记为**SwCall()**是可选的。</span><span class="sxs-lookup"><span data-stu-id="158fa-133">The call labeled **SwCallback()** will be repeated several times, and the call labeled **SwCall()** is optional.</span></span>  
  
 <span data-ttu-id="158fa-134">![SNL 服务器功能](../../adapters-and-accelerators/fileact-interact/media/42395775-cdbc-4e36-8b36-566caefa2aaf.gif "42395775-cdbc-4e36-8b36-566caefa2aaf")</span><span class="sxs-lookup"><span data-stu-id="158fa-134">![SNL Server functionality](../../adapters-and-accelerators/fileact-interact/media/42395775-cdbc-4e36-8b36-566caefa2aaf.gif "42395775-cdbc-4e36-8b36-566caefa2aaf")</span></span>  
  
 <span data-ttu-id="158fa-135">在服务器和 SNL API DLL 之间的所有调用都是标准 C 调用约定同步函数调用。</span><span class="sxs-lookup"><span data-stu-id="158fa-135">All calls between the server and the SNL API DLL are standard C calling convention synchronous function calls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="158fa-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="158fa-136">See Also</span></span>  
 <span data-ttu-id="158fa-137">[了解 FileAct 和交互适配器体系结构](../../adapters-and-accelerators/fileact-interact/understanding-fileact-and-interact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="158fa-137">[Understanding FileAct and InterAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/understanding-fileact-and-interact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="158fa-138">[SWIFT 发送适配器体系结构](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="158fa-138">[SWIFT Send Adapter Architecture](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-architecture.md) </span></span>  
 [<span data-ttu-id="158fa-139">SWIFT 接收适配器体系结构</span><span class="sxs-lookup"><span data-stu-id="158fa-139">SWIFT Receive Adapter Architecture</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md)