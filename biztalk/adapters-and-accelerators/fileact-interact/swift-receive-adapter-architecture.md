---
title: "SWIFT 接收适配器体系结构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 16f32689-0b70-4389-8596-991fd776f185
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3aca9b5ef1fd1130feeebad3ec6fdf072d3bf88d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="swift-receive-adapter-architecture"></a><span data-ttu-id="fa340-102">SWIFT 接收适配器体系结构</span><span class="sxs-lookup"><span data-stu-id="fa340-102">SWIFT Receive Adapter Architecture</span></span>
<span data-ttu-id="fa340-103">在 BizTalk Server 中，在其自己的内存空间中，这意味着创建一个单独的进程运行主机承载了接收适配器。</span><span class="sxs-lookup"><span data-stu-id="fa340-103">In BizTalk Server, the receive adapter is hosted within its own memory space, which means a separate process is created to run the host.</span></span> <span data-ttu-id="fa340-104">此主机被生成通过 SWIFTNet 链接 (SNL) 配置中定义的子系统。</span><span class="sxs-lookup"><span data-stu-id="fa340-104">This host is spawned by defining a subsystem in the SWIFTNet Link (SNL) configuration.</span></span>  
  
 <span data-ttu-id="fa340-105">服务器可执行文件已配置为在 SNL 配置 (paramfile) 子系统，通过执行 SWIFTNet 启动命令生成。</span><span class="sxs-lookup"><span data-stu-id="fa340-105">The server executable is configured as a subsystem in the SNL configuration (paramfile) and is spawned by executing the SWIFTNet Start command.</span></span> <span data-ttu-id="fa340-106">通过执行 SWIFTNet 停止命令终止 SNL 服务器应用程序。</span><span class="sxs-lookup"><span data-stu-id="fa340-106">The SNL server application is terminated by executing the SWIFTNet Stop command.</span></span> <span data-ttu-id="fa340-107">SNL 管理服务器可执行文件的生存期。</span><span class="sxs-lookup"><span data-stu-id="fa340-107">SNL manages the lifetime of the server executable.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fa340-108">服务调查局开发方案要求服务在其自己的安全上下文下运行的多个 SWIFT 成员的适配器。</span><span class="sxs-lookup"><span data-stu-id="fa340-108">The service bureau scenario requires the adapter to service multiple SWIFT members running under their own security contexts.</span></span> <span data-ttu-id="fa340-109">这可以通过配置个人支持接收每个成员和生成多个实例的服务器可执行文件的位置 — 每个专用于一个接收位置。</span><span class="sxs-lookup"><span data-stu-id="fa340-109">This can be supported by configuring an individual receive location per member and spawning multiple instances of the server executable — each one dedicated to one receive location.</span></span>  
  
 <span data-ttu-id="fa340-110">在 BizTalk Server 中的接收适配器支持以下的通信模式，与 BizTalk 消息传送引擎进行交互：</span><span class="sxs-lookup"><span data-stu-id="fa340-110">In BizTalk Server, the receive adapter supports the following communication patterns to interact with the BizTalk Messaging Engine:</span></span>  
  
-   <span data-ttu-id="fa340-111">一种方法-在延迟的模式下操作接收适配器 （服务器） 时需要此模式。</span><span class="sxs-lookup"><span data-stu-id="fa340-111">One way — this mode is required when the receive adapter (server) is operating in deferred mode.</span></span> <span data-ttu-id="fa340-112">在延迟模式下，该适配器将默认确认对于传入消息发送。</span><span class="sxs-lookup"><span data-stu-id="fa340-112">In deferred mode, the adapter sends a default acknowledgment for incoming messages.</span></span> <span data-ttu-id="fa340-113">可以在适配器属性中配置该确认的默认值。</span><span class="sxs-lookup"><span data-stu-id="fa340-113">The default values for the acknowledgment can be configured in the adapter properties.</span></span> <span data-ttu-id="fa340-114">可以通过发送适配器 LOB 应用程序更高版本发送业务级别响应。</span><span class="sxs-lookup"><span data-stu-id="fa340-114">Business level response can be sent later by the LOB application through the send adapter.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fa340-115">发生延迟模式下，所有值必须都填充在适配器配置中，因为该适配器构造响应。</span><span class="sxs-lookup"><span data-stu-id="fa340-115">In case of deferred mode, all values must be filled up in the adapter configuration, since the adapter is constructing the response.</span></span>  
  
-   <span data-ttu-id="fa340-116">请求响应-在此模式下适配器提交到 BizTalk 从 SWIFT 请求并等待响应。</span><span class="sxs-lookup"><span data-stu-id="fa340-116">Request response — in this mode the adapter submits the request from SWIFT to BizTalk and waits for response.</span></span> <span data-ttu-id="fa340-117">如果从 LOB 应用程序没有响应，该适配器将超时。</span><span class="sxs-lookup"><span data-stu-id="fa340-117">The adapter would timeout if there is no response from the LOB application.</span></span> <span data-ttu-id="fa340-118">超时值为适配器配置中配置。</span><span class="sxs-lookup"><span data-stu-id="fa340-118">The time out value is configurable in adapter configuration.</span></span> <span data-ttu-id="fa340-119">默认值为 60 秒。</span><span class="sxs-lookup"><span data-stu-id="fa340-119">The default value is 60 seconds.</span></span>  
  
     <span data-ttu-id="fa340-120">接收适配器可以仅在一个线程上，从 SNL 接收回调。</span><span class="sxs-lookup"><span data-stu-id="fa340-120">The receive adapter can receive the callback from SNL only on one thread.</span></span> <span data-ttu-id="fa340-121">这意味着，接收适配器可以进一步从接收消息 SNL 仅在提交第一条消息后。</span><span class="sxs-lookup"><span data-stu-id="fa340-121">This means that the receive adapter can receive further messages from SNL only after submitting the first message.</span></span> <span data-ttu-id="fa340-122">因此，默认批次大小设置为 1。</span><span class="sxs-lookup"><span data-stu-id="fa340-122">Therefore, the default batch size is set to 1.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fa340-123">本节内容</span><span class="sxs-lookup"><span data-stu-id="fa340-123">In This Section</span></span>  
  
-   [<span data-ttu-id="fa340-124">SWIFT 接收适配器 URI</span><span class="sxs-lookup"><span data-stu-id="fa340-124">SWIFT Receive Adapter URI</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md)  
  
-   [<span data-ttu-id="fa340-125">SWIFT 接收适配器初始化</span><span class="sxs-lookup"><span data-stu-id="fa340-125">SWIFT Receive Adapter Initialization</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-initialization.md)  
  
-   [<span data-ttu-id="fa340-126">SWIFT 接收适配器安全上下文</span><span class="sxs-lookup"><span data-stu-id="fa340-126">SWIFT Receive Adapter Security Context</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-security-context.md)  
  
-   [<span data-ttu-id="fa340-127">SWIFT 接收适配器同步和延迟模式</span><span class="sxs-lookup"><span data-stu-id="fa340-127">SWIFT Receive Adapter Synchronous and Deferred Modes</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-synchronous-and-deferred-modes.md)  
  
-   [<span data-ttu-id="fa340-128">SWIFT 接收适配器存储和转发</span><span class="sxs-lookup"><span data-stu-id="fa340-128">SWIFT Receive Adapter Store and Forward</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-store-and-forward.md)