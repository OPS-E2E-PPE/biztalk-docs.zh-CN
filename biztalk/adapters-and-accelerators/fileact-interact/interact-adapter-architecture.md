---
title: InterAct 适配器体系结构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce7e4b7e-abe4-4db6-b4e0-6f71bd7e5e6f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c22c68b9167e244e30bd285d2ae39ceaaaa833b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366977"
---
# <a name="interact-adapter-architecture"></a><span data-ttu-id="0c59b-102">InterAct 适配器体系结构</span><span class="sxs-lookup"><span data-stu-id="0c59b-102">InterAct Adapter Architecture</span></span>
<span data-ttu-id="0c59b-103">本部分介绍从功能角度的交互基元。</span><span class="sxs-lookup"><span data-stu-id="0c59b-103">This section describes the primitives of InterAct from a functional point of view.</span></span> <span data-ttu-id="0c59b-104">具体的结构、 语法和基元的使用情况的 SWIFT 引用中的阐述和这里不再赘述。</span><span class="sxs-lookup"><span data-stu-id="0c59b-104">The detailed structure, syntax, and usage for the primitives is well-documented in the SWIFT references, and is not repeated here.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0c59b-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="0c59b-105">In This Section</span></span>  
  
-   [<span data-ttu-id="0c59b-106">InterAct 适配器组件</span><span class="sxs-lookup"><span data-stu-id="0c59b-106">InterAct Adapter Components</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md)  
  
-   [<span data-ttu-id="0c59b-107">Business Exchange 的 InterAct 适配器消息</span><span class="sxs-lookup"><span data-stu-id="0c59b-107">InterAct Adapter Messages for Business Exchange</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md)  
  
-   [<span data-ttu-id="0c59b-108">InterAct 适配器客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="0c59b-108">InterAct Adapter Client Application</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md)  
  
-   [<span data-ttu-id="0c59b-109">InterAct 适配器服务器应用程序</span><span class="sxs-lookup"><span data-stu-id="0c59b-109">InterAct Adapter Server Application</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md)  
  
-   [<span data-ttu-id="0c59b-110">InterAct 适配器存储和转发</span><span class="sxs-lookup"><span data-stu-id="0c59b-110">InterAct Adapter Store and Forward</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md)  
  
-   [<span data-ttu-id="0c59b-111">InterAct 适配器安全体系结构</span><span class="sxs-lookup"><span data-stu-id="0c59b-111">InterAct Adapter Security Architecture</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md)  
  
-   [<span data-ttu-id="0c59b-112">InterAct 适配器端到端可靠传递</span><span class="sxs-lookup"><span data-stu-id="0c59b-112">InterAct Adapter End-to-End Reliable Delivery</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md)  
  
-   [<span data-ttu-id="0c59b-113">InterAct 适配器状态监视</span><span class="sxs-lookup"><span data-stu-id="0c59b-113">InterAct Adapter Status Monitoring</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md)  
  
-   [<span data-ttu-id="0c59b-114">InterAct 适配器不可否认性</span><span class="sxs-lookup"><span data-stu-id="0c59b-114">InterAct Adapter Non-Repudiation</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)