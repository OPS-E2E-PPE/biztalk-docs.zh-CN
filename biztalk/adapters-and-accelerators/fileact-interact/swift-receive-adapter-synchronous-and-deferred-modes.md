---
title: SWIFT 接收适配器同步和延迟模式 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 704def2c-ac82-4cdb-9354-609cc8dc1a0d
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e976d410ab3a4c53e4949909e73635bc4a4625a4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364457"
---
# <a name="swift-receive-adapter-synchronous-and-deferred-modes"></a><span data-ttu-id="da56e-102">SWIFT 接收适配器同步和延迟模式</span><span class="sxs-lookup"><span data-stu-id="da56e-102">SWIFT Receive Adapter Synchronous and Deferred Modes</span></span>
<span data-ttu-id="da56e-103">SWIFTNet 链接 (SNL) 服务器应用程序可以在两个不同的模式下运行： 同步和延迟模式。</span><span class="sxs-lookup"><span data-stu-id="da56e-103">SWIFTNet Link (SNL) server applications can operate in two different modes: synchronous and deferred mode.</span></span> <span data-ttu-id="da56e-104">在同步模式下，服务器应用程序发送业务响应返回给客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="da56e-104">In synchronous mode, the server application sends a business response back to the client application.</span></span> <span data-ttu-id="da56e-105">在延迟模式下，服务器应用程序将技术确认发送回客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="da56e-105">In deferred mode, the server application sends a technical acknowledgement back to the client application.</span></span>  
  
 <span data-ttu-id="da56e-106">下图显示了序列。</span><span class="sxs-lookup"><span data-stu-id="da56e-106">The following figure shows the sequence.</span></span>  
  
 <span data-ttu-id="da56e-107">![接收适配器同步和延迟模式](../../adapters-and-accelerators/fileact-interact/media/2fd504f9-5ee5-4461-a354-54c8c2f33230.gif "2fd504f9-5ee5-4461-a354-54c8c2f33230")</span><span class="sxs-lookup"><span data-stu-id="da56e-107">![Receive adapter synchronous and deferred mode](../../adapters-and-accelerators/fileact-interact/media/2fd504f9-5ee5-4461-a354-54c8c2f33230.gif "2fd504f9-5ee5-4461-a354-54c8c2f33230")</span></span>  
  
 <span data-ttu-id="da56e-108">下图显示了接收端的高级别表示形式。</span><span class="sxs-lookup"><span data-stu-id="da56e-108">The following figure shows a high level representation of the receive side.</span></span>  
  
 <span data-ttu-id="da56e-109">![接收适配器方案](../../adapters-and-accelerators/fileact-interact/media/b7cfeecb-3783-432b-886e-a77961500ad5.gif "b7cfeecb-3783-432b-886e-a77961500ad5")</span><span class="sxs-lookup"><span data-stu-id="da56e-109">![Receive adapter scenario](../../adapters-and-accelerators/fileact-interact/media/b7cfeecb-3783-432b-886e-a77961500ad5.gif "b7cfeecb-3783-432b-886e-a77961500ad5")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da56e-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="da56e-110">See Also</span></span>  
 <span data-ttu-id="da56e-111">[SWIFT 接收适配器体系结构](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="da56e-111">[SWIFT Receive Adapter Architecture](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md) </span></span>  
 <span data-ttu-id="da56e-112">[SWIFT 接收适配器 URI](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md) </span><span class="sxs-lookup"><span data-stu-id="da56e-112">[SWIFT Receive Adapter URI](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md) </span></span>  
 <span data-ttu-id="da56e-113">[SWIFT 接收适配器初始化](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-initialization.md) </span><span class="sxs-lookup"><span data-stu-id="da56e-113">[SWIFT Receive Adapter Initialization](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-initialization.md) </span></span>  
 <span data-ttu-id="da56e-114">[SWIFT 接收适配器安全上下文](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-security-context.md) </span><span class="sxs-lookup"><span data-stu-id="da56e-114">[SWIFT Receive Adapter Security Context](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-security-context.md) </span></span>  
 [<span data-ttu-id="da56e-115">SWIFT 接收适配器存储和转发</span><span class="sxs-lookup"><span data-stu-id="da56e-115">SWIFT Receive Adapter Store and Forward</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-store-and-forward.md)