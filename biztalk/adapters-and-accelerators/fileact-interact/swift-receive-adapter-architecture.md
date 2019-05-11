---
title: SWIFT 接收适配器体系结构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 16f32689-0b70-4389-8596-991fd776f185
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23deda6ba243e3b6823f5b8b80e560260c45fc7d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364618"
---
# <a name="swift-receive-adapter-architecture"></a><span data-ttu-id="f60e4-102">SWIFT 接收适配器体系结构</span><span class="sxs-lookup"><span data-stu-id="f60e4-102">SWIFT Receive Adapter Architecture</span></span>
<span data-ttu-id="f60e4-103">在 BizTalk Server 中，接收适配器都托管在自己的内存空间，这意味着创建单独的进程运行主机。</span><span class="sxs-lookup"><span data-stu-id="f60e4-103">In BizTalk Server, the receive adapter is hosted within its own memory space, which means a separate process is created to run the host.</span></span> <span data-ttu-id="f60e4-104">此主机生成的在 SWIFTNet 链接 (SNL) 配置中定义的子系统。</span><span class="sxs-lookup"><span data-stu-id="f60e4-104">This host is spawned by defining a subsystem in the SWIFTNet Link (SNL) configuration.</span></span>  
  
 <span data-ttu-id="f60e4-105">服务器可执行文件配置为在 SNL 配置 (paramfile) 子系统和生成的执行 SWIFTNet 开始命令。</span><span class="sxs-lookup"><span data-stu-id="f60e4-105">The server executable is configured as a subsystem in the SNL configuration (paramfile) and is spawned by executing the SWIFTNet Start command.</span></span> <span data-ttu-id="f60e4-106">通过执行 SWIFTNet Stop 命令终止 SNL 服务器应用程序。</span><span class="sxs-lookup"><span data-stu-id="f60e4-106">The SNL server application is terminated by executing the SWIFTNet Stop command.</span></span> <span data-ttu-id="f60e4-107">SNL 管理服务器可执行文件的生存期。</span><span class="sxs-lookup"><span data-stu-id="f60e4-107">SNL manages the lifetime of the server executable.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f60e4-108">服务局方案需要适配器服务在其自己的安全上下文下运行的多个 SWIFT 成员。</span><span class="sxs-lookup"><span data-stu-id="f60e4-108">The service bureau scenario requires the adapter to service multiple SWIFT members running under their own security contexts.</span></span> <span data-ttu-id="f60e4-109">可以通过配置单个支持此接收位置，每个成员和生成服务器可执行文件的多个实例，每个专用于一个接收位置。</span><span class="sxs-lookup"><span data-stu-id="f60e4-109">This can be supported by configuring an individual receive location per member and spawning multiple instances of the server executable — each one dedicated to one receive location.</span></span>  
  
 <span data-ttu-id="f60e4-110">在 BizTalk Server 中，接收适配器支持以下的通信模式，以与 BizTalk 消息引擎交互：</span><span class="sxs-lookup"><span data-stu-id="f60e4-110">In BizTalk Server, the receive adapter supports the following communication patterns to interact with the BizTalk Messaging Engine:</span></span>  
  
-   <span data-ttu-id="f60e4-111">一种方法，此模式下是必需的当在延迟模式下运行时接收适配器 （服务器）。</span><span class="sxs-lookup"><span data-stu-id="f60e4-111">One way — this mode is required when the receive adapter (server) is operating in deferred mode.</span></span> <span data-ttu-id="f60e4-112">在延迟模式下，适配器发送的传入消息的默认确认。</span><span class="sxs-lookup"><span data-stu-id="f60e4-112">In deferred mode, the adapter sends a default acknowledgment for incoming messages.</span></span> <span data-ttu-id="f60e4-113">可以在适配器属性中配置确认的默认值。</span><span class="sxs-lookup"><span data-stu-id="f60e4-113">The default values for the acknowledgment can be configured in the adapter properties.</span></span> <span data-ttu-id="f60e4-114">可以通过发送适配器的 LOB 应用程序的更高版本发送业务级别响应。</span><span class="sxs-lookup"><span data-stu-id="f60e4-114">Business level response can be sent later by the LOB application through the send adapter.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f60e4-115">发生延迟模式下时的所有值必须被都填满在适配器配置中，因为该适配器构造响应。</span><span class="sxs-lookup"><span data-stu-id="f60e4-115">In case of deferred mode, all values must be filled up in the adapter configuration, since the adapter is constructing the response.</span></span>  
  
-   <span data-ttu-id="f60e4-116">请求响应 — 在此模式下，适配器提交到 BizTalk 从 SWIFT 请求并等待响应。</span><span class="sxs-lookup"><span data-stu-id="f60e4-116">Request response — in this mode the adapter submits the request from SWIFT to BizTalk and waits for response.</span></span> <span data-ttu-id="f60e4-117">如果从 LOB 应用程序没有响应，该适配器将会超时。</span><span class="sxs-lookup"><span data-stu-id="f60e4-117">The adapter would timeout if there is no response from the LOB application.</span></span> <span data-ttu-id="f60e4-118">可在适配器配置中配置的超时值。</span><span class="sxs-lookup"><span data-stu-id="f60e4-118">The time out value is configurable in adapter configuration.</span></span> <span data-ttu-id="f60e4-119">默认值为 60 秒。</span><span class="sxs-lookup"><span data-stu-id="f60e4-119">The default value is 60 seconds.</span></span>  
  
     <span data-ttu-id="f60e4-120">接收适配器可以仅在一个线程上，从 SNL 接收回调。</span><span class="sxs-lookup"><span data-stu-id="f60e4-120">The receive adapter can receive the callback from SNL only on one thread.</span></span> <span data-ttu-id="f60e4-121">这意味着，接收适配器可以进一步从接收消息 SNL 仅提交的第一个消息后。</span><span class="sxs-lookup"><span data-stu-id="f60e4-121">This means that the receive adapter can receive further messages from SNL only after submitting the first message.</span></span> <span data-ttu-id="f60e4-122">因此，默认批大小设置为 1。</span><span class="sxs-lookup"><span data-stu-id="f60e4-122">Therefore, the default batch size is set to 1.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f60e4-123">本节内容</span><span class="sxs-lookup"><span data-stu-id="f60e4-123">In This Section</span></span>  
  
-   [<span data-ttu-id="f60e4-124">SWIFT 接收适配器 URI</span><span class="sxs-lookup"><span data-stu-id="f60e4-124">SWIFT Receive Adapter URI</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md)  
  
-   [<span data-ttu-id="f60e4-125">SWIFT 接收适配器初始化</span><span class="sxs-lookup"><span data-stu-id="f60e4-125">SWIFT Receive Adapter Initialization</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-initialization.md)  
  
-   [<span data-ttu-id="f60e4-126">SWIFT 接收适配器安全上下文</span><span class="sxs-lookup"><span data-stu-id="f60e4-126">SWIFT Receive Adapter Security Context</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-security-context.md)  
  
-   [<span data-ttu-id="f60e4-127">SWIFT 接收适配器同步和延迟模式</span><span class="sxs-lookup"><span data-stu-id="f60e4-127">SWIFT Receive Adapter Synchronous and Deferred Modes</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-synchronous-and-deferred-modes.md)  
  
-   [<span data-ttu-id="f60e4-128">SWIFT 接收适配器存储和转发</span><span class="sxs-lookup"><span data-stu-id="f60e4-128">SWIFT Receive Adapter Store and Forward</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-store-and-forward.md)