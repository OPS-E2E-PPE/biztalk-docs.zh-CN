---
title: 了解 FileAct 和交互适配器体系结构 |Microsoft 文档
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
ms.openlocfilehash: c04d0ba8b1c2bbd99a71e3d76c8d7ad60c251147
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223405"
---
# <a name="understanding-fileact-and-interact-adapter-architecture"></a><span data-ttu-id="fcb7d-102">了解 FileAct 和交互适配器体系结构</span><span class="sxs-lookup"><span data-stu-id="fcb7d-102">Understanding FileAct and InterAct Adapter Architecture</span></span>
<span data-ttu-id="fcb7d-103">SWIFT 适配器取决于 BizTalk 适配器框架。</span><span class="sxs-lookup"><span data-stu-id="fcb7d-103">The SWIFT Adapter is based on the BizTalk Adapter Framework.</span></span> <span data-ttu-id="fcb7d-104">使用 BizTalk Server 中的适配器的分类，SWIFT 适配器，FileAct 和交互，表示的意义如下：</span><span class="sxs-lookup"><span data-stu-id="fcb7d-104">Using the classifications of adapters within BizTalk Server, the SWIFT adapters, FileAct and InterAct, represent the following:</span></span>  
  
-   <span data-ttu-id="fcb7d-105">自定义适配器。</span><span class="sxs-lookup"><span data-stu-id="fcb7d-105">Custom Adapter.</span></span> <span data-ttu-id="fcb7d-106">这是生成专门用于与使用称为 FileAct 和交互的专有标准 SWIFT 网络交互的自定义适配器。</span><span class="sxs-lookup"><span data-stu-id="fcb7d-106">This is a custom adapter built specifically to interact with the SWIFT network using a proprietary standard called FileAct and Interact.</span></span>  
  
-   <span data-ttu-id="fcb7d-107">传输适配器。</span><span class="sxs-lookup"><span data-stu-id="fcb7d-107">Transport Adapter.</span></span> <span data-ttu-id="fcb7d-108">此适配器允许商业软件应用程序发送和接收与 SWIFT 网络的消息。</span><span class="sxs-lookup"><span data-stu-id="fcb7d-108">This adapter allows business software application to send and receive messages with the SWIFT network.</span></span>  
  
-   <span data-ttu-id="fcb7d-109">非事务性。</span><span class="sxs-lookup"><span data-stu-id="fcb7d-109">Non-transacted.</span></span> <span data-ttu-id="fcb7d-110">适配器不会进行的任何事务对象用于与 SWIFT 网络交互。</span><span class="sxs-lookup"><span data-stu-id="fcb7d-110">The adapter does not make use of any transaction object to interact with the SWIFT network.</span></span>  
  
-   <span data-ttu-id="fcb7d-111">隔离。</span><span class="sxs-lookup"><span data-stu-id="fcb7d-111">Isolated.</span></span> <span data-ttu-id="fcb7d-112">接收适配器在单独的进程中运行并在进程中运行常规发送适配器。</span><span class="sxs-lookup"><span data-stu-id="fcb7d-112">The receive adapter runs in a separate process and regular send adapters run in process.</span></span>  
  
 <span data-ttu-id="fcb7d-113">BizTalk 适配器框架有关的信息，请参阅"什么是适配器 Framework？"</span><span class="sxs-lookup"><span data-stu-id="fcb7d-113">For information about the BizTalk Adapter Framework, see the "What Is the Adapter Framework?"</span></span> <span data-ttu-id="fcb7d-114">BizTalk Server 帮助中的主题。</span><span class="sxs-lookup"><span data-stu-id="fcb7d-114">topic in BizTalk Server Help.</span></span>  
  
 <span data-ttu-id="fcb7d-115">下图显示的 FileAct 和交互体系结构的高级视图。</span><span class="sxs-lookup"><span data-stu-id="fcb7d-115">The following figure shows a high-level view of the FileAct and InterAct architecture.</span></span>  
  
 ![](../../adapters-and-accelerators/fileact-interact/media/035ebb05-ce11-447c-b56b-ba8b41e07e50.gif "035ebb05-ce11-447c-b56b-ba8b41e07e50")  
  
> [!NOTE]
>  <span data-ttu-id="fcb7d-116">Microsoft[!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)]支持仅严格模式下 SWIFTNet 链接 (SNL) API。</span><span class="sxs-lookup"><span data-stu-id="fcb7d-116">Microsoft [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] supports only strict mode SWIFTNet Link (SNL) API.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fcb7d-117">本节内容</span><span class="sxs-lookup"><span data-stu-id="fcb7d-117">In This Section</span></span>  
  
-   [<span data-ttu-id="fcb7d-118">SWIFTNet 客户端和服务器</span><span class="sxs-lookup"><span data-stu-id="fcb7d-118">SWIFTNet Client and Server</span></span>](../../adapters-and-accelerators/fileact-interact/swiftnet-client-and-server.md)  
  
-   [<span data-ttu-id="fcb7d-119">SWIFT 发送适配器体系结构</span><span class="sxs-lookup"><span data-stu-id="fcb7d-119">SWIFT Send Adapter Architecture</span></span>](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-architecture.md)  
  
-   [<span data-ttu-id="fcb7d-120">SWIFT 接收适配器体系结构</span><span class="sxs-lookup"><span data-stu-id="fcb7d-120">SWIFT Receive Adapter Architecture</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md)  
  
-   [<span data-ttu-id="fcb7d-121">FileAct 适配器体系结构</span><span class="sxs-lookup"><span data-stu-id="fcb7d-121">FileAct Adapter Architecture</span></span>](../../adapters-and-accelerators/fileact-interact/fileact-adapter-architecture.md)  
  
-   [<span data-ttu-id="fcb7d-122">交互适配器体系结构</span><span class="sxs-lookup"><span data-stu-id="fcb7d-122">InterAct Adapter Architecture</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md)