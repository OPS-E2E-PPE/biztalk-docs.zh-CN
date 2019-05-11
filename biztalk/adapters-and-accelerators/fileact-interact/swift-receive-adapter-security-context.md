---
title: SWIFT 接收适配器安全上下文 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3db2b534-db9d-4075-aaad-0974b024dc71
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1ce4136efb28c8535b01b86cb55e84456e7773a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364475"
---
# <a name="swift-receive-adapter-security-context"></a><span data-ttu-id="6eb74-102">SWIFT 接收适配器安全上下文</span><span class="sxs-lookup"><span data-stu-id="6eb74-102">SWIFT Receive Adapter Security Context</span></span>
<span data-ttu-id="6eb74-103">接收器适配器，发送适配器与启动 SWIFTNet 链接 (SNL/RA) 命令提示符下 （SWIFTNet 启动）。</span><span class="sxs-lookup"><span data-stu-id="6eb74-103">The Receiver adapter, unlike send adapter, is started from the SWIFTNet Link (SNL/RA) command prompt (SWIFTNet start).</span></span> <span data-ttu-id="6eb74-104">远程协助 SNL/配置文件 (paramconfig) 中配置接收适配器可执行文件。</span><span class="sxs-lookup"><span data-stu-id="6eb74-104">The receive adapter executable is configured in the SNL/RA configuration file (paramconfig).</span></span> <span data-ttu-id="6eb74-105">在启动适配器初始化 SNL 库基于命令行参数。</span><span class="sxs-lookup"><span data-stu-id="6eb74-105">The adapter on startup initializes the SNL library based on the command line parameter.</span></span> <span data-ttu-id="6eb74-106">配置值被缓存以供将来使用。</span><span class="sxs-lookup"><span data-stu-id="6eb74-106">The configuration values are cached for later use.</span></span>  
  
 <span data-ttu-id="6eb74-107">下图显示了接收适配器安全上下文的配置。</span><span class="sxs-lookup"><span data-stu-id="6eb74-107">The following figure shows the configuration of the receive adapter security context.</span></span>  
  
 <span data-ttu-id="6eb74-108">![SWIFT 接收适配器安全上下文](../../adapters-and-accelerators/fileact-interact/media/f48c7cd1-b162-45ea-9ec3-7936f61563c2.gif "f48c7cd1-b162-45ea-9ec3-7936f61563c2")</span><span class="sxs-lookup"><span data-stu-id="6eb74-108">![SWIFT receive adapter security context](../../adapters-and-accelerators/fileact-interact/media/f48c7cd1-b162-45ea-9ec3-7936f61563c2.gif "f48c7cd1-b162-45ea-9ec3-7936f61563c2")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6eb74-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="6eb74-109">See Also</span></span>  
 <span data-ttu-id="6eb74-110">[SWIFT 接收适配器体系结构](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="6eb74-110">[SWIFT Receive Adapter Architecture](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md) </span></span>  
 <span data-ttu-id="6eb74-111">[SWIFT 接收适配器 URI](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md) </span><span class="sxs-lookup"><span data-stu-id="6eb74-111">[SWIFT Receive Adapter URI](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md) </span></span>  
 <span data-ttu-id="6eb74-112">[SWIFT 接收适配器初始化](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-initialization.md) </span><span class="sxs-lookup"><span data-stu-id="6eb74-112">[SWIFT Receive Adapter Initialization](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-initialization.md) </span></span>  
 <span data-ttu-id="6eb74-113">[SWIFT 接收适配器同步和延迟模式](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-synchronous-and-deferred-modes.md) </span><span class="sxs-lookup"><span data-stu-id="6eb74-113">[SWIFT Receive Adapter Synchronous and Deferred Modes](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-synchronous-and-deferred-modes.md) </span></span>  
 [<span data-ttu-id="6eb74-114">SWIFT 接收适配器存储和转发</span><span class="sxs-lookup"><span data-stu-id="6eb74-114">SWIFT Receive Adapter Store and Forward</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-store-and-forward.md)