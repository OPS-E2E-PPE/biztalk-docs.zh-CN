---
title: SWIFT 发送适配器体系结构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e52a5a21-0aa1-4cd9-a2a4-f9df425913a0
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4347680cf4fa1434e72e80c74debe0ca2de8d47
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364175"
---
# <a name="swift-send-adapter-architecture"></a><span data-ttu-id="17229-102">SWIFT 发送适配器体系结构</span><span class="sxs-lookup"><span data-stu-id="17229-102">SWIFT Send Adapter Architecture</span></span>
<span data-ttu-id="17229-103">一般情况下，BizTalk Server 发送适配器的宿主 BizTalk 服务进程 Btsntsvc.exe。</span><span class="sxs-lookup"><span data-stu-id="17229-103">In general, BizTalk Server send adapters are hosted in the BizTalk service process, Btsntsvc.exe.</span></span> <span data-ttu-id="17229-104">这意味着 BizTalk Server 管理适配器的生存期。</span><span class="sxs-lookup"><span data-stu-id="17229-104">This means that BizTalk Server manages the lifetime of the adapter.</span></span>  
  
 <span data-ttu-id="17229-105">有两种方法将消息发送到 SWIFT 网络的： 同步 (ExchangeRequest) 和异步 （对于此版本未实现）。</span><span class="sxs-lookup"><span data-stu-id="17229-105">There are two ways of sending messages to the SWIFT network: synchronous (ExchangeRequest) and asynchronous (not implemented for this release).</span></span> <span data-ttu-id="17229-106">在 BizTalk Server 中，发送适配器应支持以下通信模式与 BizTalk 消息引擎进行交互：</span><span class="sxs-lookup"><span data-stu-id="17229-106">In BizTalk Server, the send adapter should support the following communication patterns to interact with the BizTalk Messaging Engine:</span></span>  
  
-   <span data-ttu-id="17229-107">要求响应 — 成对，名为的基元，与 SWIFT 网络交换消息。</span><span class="sxs-lookup"><span data-stu-id="17229-107">Solicit response — messages are exchanged in pairs, called the primitives, with the SWIFT network.</span></span> <span data-ttu-id="17229-108">向 SWIFT 发送任何消息将具有是其业务、 确认或错误的响应。</span><span class="sxs-lookup"><span data-stu-id="17229-108">Any messages sent to SWIFT will have a response be it business, acknowledgement or error.</span></span> <span data-ttu-id="17229-109">响应消息提交回 messagebox。</span><span class="sxs-lookup"><span data-stu-id="17229-109">The response message is submitted back to messagebox.</span></span> <span data-ttu-id="17229-110">此操作模式用于实时通信。</span><span class="sxs-lookup"><span data-stu-id="17229-110">This mode of operation is used for Real-Time communication.</span></span>  
  
-   <span data-ttu-id="17229-111">一种方式发送，适配器中的一种方法配置时可在存储和转发模式运行。</span><span class="sxs-lookup"><span data-stu-id="17229-111">One way send — the adapter when configured in one way operates in store and forward mode.</span></span> <span data-ttu-id="17229-112">将消息发送到预配置队列而不是收件人。</span><span class="sxs-lookup"><span data-stu-id="17229-112">The messages are sent to a preconfigured queue as opposed to a receipient.</span></span> <span data-ttu-id="17229-113">发件人可以通过使用队列在推送或拉取模式下打开会话检索响应。</span><span class="sxs-lookup"><span data-stu-id="17229-113">The sender can retrieve the response by opening a session with the queue in push or pull mode.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="17229-114">创建适配器的方式会影响运行的方式。</span><span class="sxs-lookup"><span data-stu-id="17229-114">The way you create the adapter affects the way it operates.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="17229-115">本节内容</span><span class="sxs-lookup"><span data-stu-id="17229-115">In This Section</span></span>  
  
-   [<span data-ttu-id="17229-116">SWIFT 发送适配器 URI</span><span class="sxs-lookup"><span data-stu-id="17229-116">SWIFT Send Adapter URI</span></span>](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-uri.md)  
  
-   [<span data-ttu-id="17229-117">SWIFT 发送适配器动态发送</span><span class="sxs-lookup"><span data-stu-id="17229-117">SWIFT Send Adapter Dynamic Send</span></span>](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-dynamic-send.md)  
  
-   [<span data-ttu-id="17229-118">SWIFT 发送适配器初始化</span><span class="sxs-lookup"><span data-stu-id="17229-118">SWIFT Send Adapter Initialization</span></span>](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-initialization.md)  
  
-   [<span data-ttu-id="17229-119">SWIFT 发送适配器同步模式</span><span class="sxs-lookup"><span data-stu-id="17229-119">SWIFT Send Adapter Synchronous Mode</span></span>](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-synchronous-mode.md)  
  
-   [<span data-ttu-id="17229-120">SWIFT 发送适配器终止</span><span class="sxs-lookup"><span data-stu-id="17229-120">SWIFT Send Adapter Termination</span></span>](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-termination.md)