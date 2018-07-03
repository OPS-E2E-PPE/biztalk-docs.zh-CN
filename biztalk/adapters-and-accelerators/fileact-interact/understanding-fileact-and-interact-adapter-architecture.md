---
title: 了解 FileAct 和 InterAct 适配器体系结构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8f97a7fe-20df-4509-bb6e-53743c3a57df
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a587b70eb3ae603d59dd5a6f21270133b5a8125
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005302"
---
# <a name="understanding-fileact-and-interact-adapter-architecture"></a><span data-ttu-id="bb3d1-102">了解 FileAct 和 InterAct 适配器体系结构</span><span class="sxs-lookup"><span data-stu-id="bb3d1-102">Understanding FileAct and InterAct Adapter Architecture</span></span>
<span data-ttu-id="bb3d1-103">SWIFT 适配器基于 BizTalk 适配器框架。</span><span class="sxs-lookup"><span data-stu-id="bb3d1-103">The SWIFT Adapter is based on the BizTalk Adapter Framework.</span></span> <span data-ttu-id="bb3d1-104">使用 BizTalk Server 中的适配器的分类，SWIFT 适配器，FileAct 和 InterAct，表示以下：</span><span class="sxs-lookup"><span data-stu-id="bb3d1-104">Using the classifications of adapters within BizTalk Server, the SWIFT adapters, FileAct and InterAct, represent the following:</span></span>  
  
- <span data-ttu-id="bb3d1-105">自定义适配器。</span><span class="sxs-lookup"><span data-stu-id="bb3d1-105">Custom Adapter.</span></span> <span data-ttu-id="bb3d1-106">这是专门为与使用专有标准调用 FileAct 和 Interact 的 SWIFT 网络交互构建的自定义适配器。</span><span class="sxs-lookup"><span data-stu-id="bb3d1-106">This is a custom adapter built specifically to interact with the SWIFT network using a proprietary standard called FileAct and Interact.</span></span>  
  
- <span data-ttu-id="bb3d1-107">传输适配器。</span><span class="sxs-lookup"><span data-stu-id="bb3d1-107">Transport Adapter.</span></span> <span data-ttu-id="bb3d1-108">此适配器允许业务软件应用程序发送和接收消息的 SWIFT 网络。</span><span class="sxs-lookup"><span data-stu-id="bb3d1-108">This adapter allows business software application to send and receive messages with the SWIFT network.</span></span>  
  
- <span data-ttu-id="bb3d1-109">非事务处理。</span><span class="sxs-lookup"><span data-stu-id="bb3d1-109">Non-transacted.</span></span> <span data-ttu-id="bb3d1-110">适配器不会进行使用的任何事务对象与 SWIFT 网络进行交互。</span><span class="sxs-lookup"><span data-stu-id="bb3d1-110">The adapter does not make use of any transaction object to interact with the SWIFT network.</span></span>  
  
- <span data-ttu-id="bb3d1-111">隔离。</span><span class="sxs-lookup"><span data-stu-id="bb3d1-111">Isolated.</span></span> <span data-ttu-id="bb3d1-112">接收适配器的单独进程中运行，并在进程中运行常规发送适配器。</span><span class="sxs-lookup"><span data-stu-id="bb3d1-112">The receive adapter runs in a separate process and regular send adapters run in process.</span></span>  
  
  <span data-ttu-id="bb3d1-113">BizTalk 适配器框架有关的信息，请参阅"什么是适配器框架？"</span><span class="sxs-lookup"><span data-stu-id="bb3d1-113">For information about the BizTalk Adapter Framework, see the "What Is the Adapter Framework?"</span></span> <span data-ttu-id="bb3d1-114">BizTalk Server 帮助中的主题。</span><span class="sxs-lookup"><span data-stu-id="bb3d1-114">topic in BizTalk Server Help.</span></span>  
  
  <span data-ttu-id="bb3d1-115">下图显示了 FileAct 和 InterAct 体系结构的高级视图。</span><span class="sxs-lookup"><span data-stu-id="bb3d1-115">The following figure shows a high-level view of the FileAct and InterAct architecture.</span></span>  
  
  <span data-ttu-id="bb3d1-116">![](../../adapters-and-accelerators/fileact-interact/media/035ebb05-ce11-447c-b56b-ba8b41e07e50.gif "035ebb05-ce11-447c-b56b-ba8b41e07e50")</span><span class="sxs-lookup"><span data-stu-id="bb3d1-116">![](../../adapters-and-accelerators/fileact-interact/media/035ebb05-ce11-447c-b56b-ba8b41e07e50.gif "035ebb05-ce11-447c-b56b-ba8b41e07e50")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bb3d1-117">Microsoft[!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)]支持仅严格模式下 SWIFTNet 链接 (SNL) API。</span><span class="sxs-lookup"><span data-stu-id="bb3d1-117">Microsoft [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] supports only strict mode SWIFTNet Link (SNL) API.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bb3d1-118">本节内容</span><span class="sxs-lookup"><span data-stu-id="bb3d1-118">In This Section</span></span>  
  
-   [<span data-ttu-id="bb3d1-119">SWIFTNet 客户端和服务器</span><span class="sxs-lookup"><span data-stu-id="bb3d1-119">SWIFTNet Client and Server</span></span>](../../adapters-and-accelerators/fileact-interact/swiftnet-client-and-server.md)  
  
-   [<span data-ttu-id="bb3d1-120">SWIFT 发送配器体系结构</span><span class="sxs-lookup"><span data-stu-id="bb3d1-120">SWIFT Send Adapter Architecture</span></span>](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-architecture.md)  
  
-   [<span data-ttu-id="bb3d1-121">SWIFT 接收适配器体系结构</span><span class="sxs-lookup"><span data-stu-id="bb3d1-121">SWIFT Receive Adapter Architecture</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md)  
  
-   [<span data-ttu-id="bb3d1-122">FileAct 适配器体系结构</span><span class="sxs-lookup"><span data-stu-id="bb3d1-122">FileAct Adapter Architecture</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md)  
  
-   [<span data-ttu-id="bb3d1-123">InterAct 适配器体系结构</span><span class="sxs-lookup"><span data-stu-id="bb3d1-123">InterAct Adapter Architecture</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)