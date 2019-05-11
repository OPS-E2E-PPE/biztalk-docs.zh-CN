---
title: SWIFT 发送适配器动态发送 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 105972fe-9dc0-480a-a4d1-2ec682fa7ad9
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5161c47011a5239435739d08783e3da6f2547aaf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65364196"
---
# <a name="swift-send-adapter-dynamic-send"></a><span data-ttu-id="60418-102">SWIFT 发送适配器动态发送</span><span class="sxs-lookup"><span data-stu-id="60418-102">SWIFT Send Adapter Dynamic Send</span></span>
<span data-ttu-id="60418-103">发送适配器动态发送模式拉取来自队列的消息。</span><span class="sxs-lookup"><span data-stu-id="60418-103">The send adapter dynamic send mode pulls messages from the queue.</span></span> <span data-ttu-id="60418-104">动态发送的 URI 为：</span><span class="sxs-lookup"><span data-stu-id="60418-104">The URI for dynamic send is:</span></span>  
  
```  
SWIFT://<queue name>/<Force Acquire>/<Session Mode>/<Order By>/<Recovery mode>  
```  
  
 <span data-ttu-id="60418-105">可以使用业务流程或管道来构造 URI。</span><span class="sxs-lookup"><span data-stu-id="60418-105">You can use an orchestration or a pipeline to construct the URI.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60418-106">请参阅</span><span class="sxs-lookup"><span data-stu-id="60418-106">See Also</span></span>  
 <span data-ttu-id="60418-107">[SWIFT 发送适配器体系结构](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="60418-107">[SWIFT Send Adapter Architecture](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-architecture.md) </span></span>  
 <span data-ttu-id="60418-108">[SWIFT 发送适配器 URI](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-uri.md) </span><span class="sxs-lookup"><span data-stu-id="60418-108">[SWIFT Send Adapter URI](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-uri.md) </span></span>  
 <span data-ttu-id="60418-109">[SWIFT 发送适配器初始化](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-initialization.md) </span><span class="sxs-lookup"><span data-stu-id="60418-109">[SWIFT Send Adapter Initialization](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-initialization.md) </span></span>  
 <span data-ttu-id="60418-110">[SWIFT 发送适配器同步模式](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-synchronous-mode.md) </span><span class="sxs-lookup"><span data-stu-id="60418-110">[SWIFT Send Adapter Synchronous Mode](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-synchronous-mode.md) </span></span>  
 [<span data-ttu-id="60418-111">SWIFT 发送适配器终止</span><span class="sxs-lookup"><span data-stu-id="60418-111">SWIFT Send Adapter Termination</span></span>](../../adapters-and-accelerators/fileact-interact/swift-send-adapter-termination.md)