---
title: SWIFT 接收适配器安全上下文 |Microsoft 文档
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
ms.openlocfilehash: b381ba9b4e0e1d53eca8e6cdd01b9770eb82372f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223821"
---
# <a name="swift-receive-adapter-security-context"></a><span data-ttu-id="b6be1-102">SWIFT 接收适配器安全上下文</span><span class="sxs-lookup"><span data-stu-id="b6be1-102">SWIFT Receive Adapter Security Context</span></span>
<span data-ttu-id="b6be1-103">从 SWIFTNet 链接 (SNL/RA) 命令提示符 （SWIFTNet 启动） 中启动接收方适配器，与发送适配器不同。</span><span class="sxs-lookup"><span data-stu-id="b6be1-103">The Receiver adapter, unlike send adapter, is started from the SWIFTNet Link (SNL/RA) command prompt (SWIFTNet start).</span></span> <span data-ttu-id="b6be1-104">可执行文件的接收适配器已配置在 SNL/RA 配置文件 (paramconfig) 中。</span><span class="sxs-lookup"><span data-stu-id="b6be1-104">The receive adapter executable is configured in the SNL/RA configuration file (paramconfig).</span></span> <span data-ttu-id="b6be1-105">上启动的适配器初始化 SNL 库根据命令行参数。</span><span class="sxs-lookup"><span data-stu-id="b6be1-105">The adapter on startup initializes the SNL library based on the command line parameter.</span></span> <span data-ttu-id="b6be1-106">配置值进行缓存以供将来使用。</span><span class="sxs-lookup"><span data-stu-id="b6be1-106">The configuration values are cached for later use.</span></span>  
  
 <span data-ttu-id="b6be1-107">下图显示的配置接收适配器安全上下文。</span><span class="sxs-lookup"><span data-stu-id="b6be1-107">The following figure shows the configuration of the receive adapter security context.</span></span>  
  
 <span data-ttu-id="b6be1-108">![SWIFT 接收适配器安全上下文](../../adapters-and-accelerators/fileact-interact/media/f48c7cd1-b162-45ea-9ec3-7936f61563c2.gif "f48c7cd1-b162-45ea-9ec3-7936f61563c2")</span><span class="sxs-lookup"><span data-stu-id="b6be1-108">![SWIFT receive adapter security context](../../adapters-and-accelerators/fileact-interact/media/f48c7cd1-b162-45ea-9ec3-7936f61563c2.gif "f48c7cd1-b162-45ea-9ec3-7936f61563c2")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6be1-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b6be1-109">See Also</span></span>  
 <span data-ttu-id="b6be1-110">[SWIFT 接收适配器体系结构](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="b6be1-110">[SWIFT Receive Adapter Architecture](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md) </span></span>  
 <span data-ttu-id="b6be1-111">[SWIFT 接收适配器 URI](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md) </span><span class="sxs-lookup"><span data-stu-id="b6be1-111">[SWIFT Receive Adapter URI](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md) </span></span>  
 <span data-ttu-id="b6be1-112">[SWIFT 接收适配器初始化](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-initialization.md) </span><span class="sxs-lookup"><span data-stu-id="b6be1-112">[SWIFT Receive Adapter Initialization](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-initialization.md) </span></span>  
 <span data-ttu-id="b6be1-113">[SWIFT 接收适配器同步和延迟模式](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-synchronous-and-deferred-modes.md) </span><span class="sxs-lookup"><span data-stu-id="b6be1-113">[SWIFT Receive Adapter Synchronous and Deferred Modes](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-synchronous-and-deferred-modes.md) </span></span>  
 [<span data-ttu-id="b6be1-114">SWIFT 接收适配器存储和转发</span><span class="sxs-lookup"><span data-stu-id="b6be1-114">SWIFT Receive Adapter Store and Forward</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-store-and-forward.md)