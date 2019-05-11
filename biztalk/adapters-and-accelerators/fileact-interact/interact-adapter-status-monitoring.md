---
title: InterAct 适配器状态监视 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2bbc6a45-8d3a-444e-b760-aef0dfa7218a
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 540923098d57fd508e8071daa9febc7b3eeb8c47
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366620"
---
# <a name="interact-adapter-status-monitoring"></a><span data-ttu-id="edda3-102">InterAct 适配器状态监视</span><span class="sxs-lookup"><span data-stu-id="edda3-102">InterAct Adapter Status Monitoring</span></span>
<span data-ttu-id="edda3-103">SWIFTNet 链接 (SNL C) 将保留有关 SWIFTNet 存储和转发 (SnF) 会话，在该 SNL 中获取本地状态。</span><span class="sxs-lookup"><span data-stu-id="edda3-103">SWIFTNet Link (SNL-C) retains a local status about SWIFTNet store and forward (SnF) sessions acquired on that SNL.</span></span> <span data-ttu-id="edda3-104">要获取有关该会话的信息，请使用带有以下基元 SwCall():</span><span class="sxs-lookup"><span data-stu-id="edda3-104">To get the information about the session, use SwCall() with the following primitive:</span></span>  
  
 <span data-ttu-id="edda3-105">![获取会话信息](../../adapters-and-accelerators/fileact-interact/media/b7feb4b4-de92-4bb9-bcfe-363a127d0ed2.gif "b7feb4b4-de92-4bb9-bcfe-363a127d0ed2")</span><span class="sxs-lookup"><span data-stu-id="edda3-105">![Getting session information](../../adapters-and-accelerators/fileact-interact/media/b7feb4b4-de92-4bb9-bcfe-363a127d0ed2.gif "b7feb4b4-de92-4bb9-bcfe-363a127d0ed2")</span></span>  
  
 <span data-ttu-id="edda3-106">请注意，不需要提供 AuthorizationContext。</span><span class="sxs-lookup"><span data-stu-id="edda3-106">Notice that you are not required to provide an AuthorizationContext.</span></span> <span data-ttu-id="edda3-107">返回本地 SNL 所看到的信息，如下图中所示。</span><span class="sxs-lookup"><span data-stu-id="edda3-107">The information seen by the local SNL is returned, as shown in the following figure.</span></span>  
  
 <span data-ttu-id="edda3-108">![会话状态信息](../../adapters-and-accelerators/fileact-interact/media/afd46393-a11d-4b4a-a66b-eba5f049f306.gif "afd46393-a11d-4b4a-a66b-eba5f049f306")</span><span class="sxs-lookup"><span data-stu-id="edda3-108">![Session status information](../../adapters-and-accelerators/fileact-interact/media/afd46393-a11d-4b4a-a66b-eba5f049f306.gif "afd46393-a11d-4b4a-a66b-eba5f049f306")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edda3-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="edda3-109">See Also</span></span>  
 <span data-ttu-id="edda3-110">[InterAct 适配器体系结构](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="edda3-110">[InterAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="edda3-111">[InterAct 适配器组件](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md) </span><span class="sxs-lookup"><span data-stu-id="edda3-111">[InterAct Adapter Components](../../adapters-and-accelerators/fileact-interact/interact-adapter-components.md) </span></span>  
 <span data-ttu-id="edda3-112">[Business Exchange 的 interAct 适配器消息](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md) </span><span class="sxs-lookup"><span data-stu-id="edda3-112">[InterAct Adapter Messages for Business Exchange](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md) </span></span>  
 <span data-ttu-id="edda3-113">[InterAct 适配器客户端应用程序](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md) </span><span class="sxs-lookup"><span data-stu-id="edda3-113">[InterAct Adapter Client Application](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md) </span></span>  
 <span data-ttu-id="edda3-114">[InterAct 适配器服务器应用程序](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md) </span><span class="sxs-lookup"><span data-stu-id="edda3-114">[InterAct Adapter Server Application](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md) </span></span>  
 <span data-ttu-id="edda3-115">[InterAct 适配器存储和转发](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="edda3-115">[InterAct Adapter Store and Forward](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md) </span></span>  
 <span data-ttu-id="edda3-116">[InterAct 适配器安全体系结构](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="edda3-116">[InterAct Adapter Security Architecture](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md) </span></span>  
 <span data-ttu-id="edda3-117">[交互适配器端到端可靠传递](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md) </span><span class="sxs-lookup"><span data-stu-id="edda3-117">[InterAct Adapter End-to-End Reliable Delivery](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md) </span></span>  
 [<span data-ttu-id="edda3-118">InterAct 适配器不可否认性</span><span class="sxs-lookup"><span data-stu-id="edda3-118">InterAct Adapter Non-Repudiation</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)