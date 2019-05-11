---
title: SWIFT 接收适配器初始化 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce53aff3-6189-4033-b318-d703037518e0
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 80d49a4ccc7c3595aaeca4a8068f8d76023e1763
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364463"
---
# <a name="swift-receive-adapter-initialization"></a><span data-ttu-id="f9b27-102">SWIFT 接收适配器初始化</span><span class="sxs-lookup"><span data-stu-id="f9b27-102">SWIFT Receive Adapter Initialization</span></span>
<span data-ttu-id="f9b27-103">SWIFT 服务器应用程序的初始化过程是类似于 SWIFT 的客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="f9b27-103">The initialization process for the SWIFT server application is similar to that for the SWIFT client application.</span></span> <span data-ttu-id="f9b27-104">初始化参数作为命令行参数传递到接收方可执行文件。</span><span class="sxs-lookup"><span data-stu-id="f9b27-104">The initialization arguments are passed as command line parameters to the receiver executable.</span></span> <span data-ttu-id="f9b27-105">在设计时，接收位置中的配置的应用程序名称作为命令行参数传递。</span><span class="sxs-lookup"><span data-stu-id="f9b27-105">The application name, configured in the receive location during design time, is passed as a command line argument.</span></span> <span data-ttu-id="f9b27-106">此应用程序名称用于构造接收位置来检索已配置的属性的 URI。</span><span class="sxs-lookup"><span data-stu-id="f9b27-106">This application name is used to construct the receive location URI to retrieve the configured properties.</span></span>  
  
 <span data-ttu-id="f9b27-107">有关使用命令行参数的信息，请参阅 Microsoft 中的"如何配置接收适配器环境"主题[!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)]安装和配置指南。</span><span class="sxs-lookup"><span data-stu-id="f9b27-107">For information about using the command line argument, see the "How to Configure the Receive Adapter Environment" topic in Microsoft [!INCLUDE[swift_adapter](../../includes/swift-adapter-md.md)] Installation and Configuration Guide.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9b27-108">请参阅</span><span class="sxs-lookup"><span data-stu-id="f9b27-108">See Also</span></span>  
 <span data-ttu-id="f9b27-109">[SWIFT 接收适配器体系结构](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="f9b27-109">[SWIFT Receive Adapter Architecture](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-architecture.md) </span></span>  
 <span data-ttu-id="f9b27-110">[SWIFT 接收适配器 URI](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md) </span><span class="sxs-lookup"><span data-stu-id="f9b27-110">[SWIFT Receive Adapter URI](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-uri.md) </span></span>  
 <span data-ttu-id="f9b27-111">[SWIFT 接收适配器安全上下文](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-security-context.md) </span><span class="sxs-lookup"><span data-stu-id="f9b27-111">[SWIFT Receive Adapter Security Context](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-security-context.md) </span></span>  
 <span data-ttu-id="f9b27-112">[SWIFT 接收适配器同步和延迟模式](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-synchronous-and-deferred-modes.md) </span><span class="sxs-lookup"><span data-stu-id="f9b27-112">[SWIFT Receive Adapter Synchronous and Deferred Modes](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-synchronous-and-deferred-modes.md) </span></span>  
 [<span data-ttu-id="f9b27-113">SWIFT 接收适配器存储和转发</span><span class="sxs-lookup"><span data-stu-id="f9b27-113">SWIFT Receive Adapter Store and Forward</span></span>](../../adapters-and-accelerators/fileact-interact/swift-receive-adapter-store-and-forward.md)