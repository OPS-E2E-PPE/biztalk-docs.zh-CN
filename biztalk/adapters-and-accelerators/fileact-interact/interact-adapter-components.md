---
title: "交互适配器组件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aad60b57-4cc8-44b9-98f5-e5a2ba3a41e2
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e909e49713377172d01540f4c8e660756d68ed72
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="interact-adapter-components"></a><span data-ttu-id="e83f6-102">交互适配器组件</span><span class="sxs-lookup"><span data-stu-id="e83f6-102">InterAct Adapter Components</span></span>
<span data-ttu-id="e83f6-103">交互适配器具有客户端和服务器组件。</span><span class="sxs-lookup"><span data-stu-id="e83f6-103">The InterAct adapter has a client and a server component.</span></span> <span data-ttu-id="e83f6-104">请注意，可能会出现在同一台计算机作为 SWIFT 联盟网关 （压降） 上的 A4SWIFT （最小） 安装是否它正在运行 Windows Server。</span><span class="sxs-lookup"><span data-stu-id="e83f6-104">Note that there may be an A4SWIFT (minimal) installation on the same computer as the SWIFT Alliance Gateway (SAG) if it is running Windows Server.</span></span> <span data-ttu-id="e83f6-105">另请注意，SWIFTNet 链接 (SNL) 可能压降从一台计算机上。</span><span class="sxs-lookup"><span data-stu-id="e83f6-105">Also note that the SWIFTNet Link (SNL) may be on a separate computer from the SAG.</span></span> <span data-ttu-id="e83f6-106">远程的应用程序编程接口 (API) 主机适配器 SWIFT 提供用于从 A4SWIFT 到压降，而不考虑组件位置的通信。</span><span class="sxs-lookup"><span data-stu-id="e83f6-106">The remote application programming interface (API) host adapter provided by SWIFT is used to communicate from A4SWIFT to the SAG, regardless of the location of the components.</span></span>  
  
 <span data-ttu-id="e83f6-107">下图显示构成整个适配器和通信链的交互适配器相关的组件的驻留位置。</span><span class="sxs-lookup"><span data-stu-id="e83f6-107">The figure below shows where the components comprising the entire adapter and communications chain related to the InterAct adapter reside.</span></span>  
  
 <span data-ttu-id="e83f6-108">![交互组件](../../adapters-and-accelerators/fileact-interact/media/cf257c5a-3668-4aff-bce9-7acc6eb672bd.gif "cf257c5a-3668-4aff-bce9-7acc6eb672bd")</span><span class="sxs-lookup"><span data-stu-id="e83f6-108">![InterAct components](../../adapters-and-accelerators/fileact-interact/media/cf257c5a-3668-4aff-bce9-7acc6eb672bd.gif "cf257c5a-3668-4aff-bce9-7acc6eb672bd")</span></span>  
  
 <span data-ttu-id="e83f6-109">在下图中，客户端应用程序使用 A4SWIFT 和交互适配器。</span><span class="sxs-lookup"><span data-stu-id="e83f6-109">In the following figure, the client application uses A4SWIFT and the InterAct adapter.</span></span> <span data-ttu-id="e83f6-110">BizTalk Server 是中间，其中通过 TCPIP 到远程 API 主机适配器进行通信。</span><span class="sxs-lookup"><span data-stu-id="e83f6-110">BizTalk Server is the middleware, which communicates to the remote API host adapter over TCPIP.</span></span>  
  
 <span data-ttu-id="e83f6-111">![客户端应用程序进行交互](../../adapters-and-accelerators/fileact-interact/media/7aeada39-6264-498b-92e8-303eb0cf369b.gif "7aeada39-6264-498b-92e8-303eb0cf369b")</span><span class="sxs-lookup"><span data-stu-id="e83f6-111">![InterAct client application](../../adapters-and-accelerators/fileact-interact/media/7aeada39-6264-498b-92e8-303eb0cf369b.gif "7aeada39-6264-498b-92e8-303eb0cf369b")</span></span>  
  
 <span data-ttu-id="e83f6-112">在下图中，服务器应用程序使用 A4SWIFT 和交互适配器。</span><span class="sxs-lookup"><span data-stu-id="e83f6-112">In the following figure, the server application uses A4SWIFT and the InterAct adapter.</span></span> <span data-ttu-id="e83f6-113">BizTalk Server 是中间，其中通过 TCPIP 到远程 API 主机适配器进行通信。</span><span class="sxs-lookup"><span data-stu-id="e83f6-113">BizTalk Server is the middleware, which communicates to the remote API host adapter over TCPIP.</span></span>  
  
 <span data-ttu-id="e83f6-114">![服务器应用程序进行交互](../../adapters-and-accelerators/fileact-interact/media/51cbae6a-41e9-4a50-9574-5e86bc04ddba.gif "51cbae6a-41e9-4a50-9574-5e86bc04ddba")</span><span class="sxs-lookup"><span data-stu-id="e83f6-114">![InterAct server application](../../adapters-and-accelerators/fileact-interact/media/51cbae6a-41e9-4a50-9574-5e86bc04ddba.gif "51cbae6a-41e9-4a50-9574-5e86bc04ddba")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e83f6-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e83f6-115">See Also</span></span>  
 <span data-ttu-id="e83f6-116">[交互适配器体系结构](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="e83f6-116">[InterAct Adapter Architecture](../../adapters-and-accelerators/fileact-interact/interact-adapter-architecture.md) </span></span>  
 <span data-ttu-id="e83f6-117">[适用于业务 Exchange 交互适配器消息](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md) </span><span class="sxs-lookup"><span data-stu-id="e83f6-117">[InterAct Adapter Messages for Business Exchange](../../adapters-and-accelerators/fileact-interact/interact-adapter-messages-for-business-exchange.md) </span></span>  
 <span data-ttu-id="e83f6-118">[交互适配器客户端应用程序](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md) </span><span class="sxs-lookup"><span data-stu-id="e83f6-118">[InterAct Adapter Client Application](../../adapters-and-accelerators/fileact-interact/interact-adapter-client-application.md) </span></span>  
 <span data-ttu-id="e83f6-119">[交互适配器服务器应用程序](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md) </span><span class="sxs-lookup"><span data-stu-id="e83f6-119">[InterAct Adapter Server Application](../../adapters-and-accelerators/fileact-interact/interact-adapter-server-application.md) </span></span>  
 <span data-ttu-id="e83f6-120">[交互适配器存储和转发](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="e83f6-120">[InterAct Adapter Store and Forward](../../adapters-and-accelerators/fileact-interact/interact-adapter-store-and-forward.md) </span></span>  
 <span data-ttu-id="e83f6-121">[交互适配器安全体系结构](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="e83f6-121">[InterAct Adapter Security Architecture](../../adapters-and-accelerators/fileact-interact/interact-adapter-security-architecture.md) </span></span>  
 <span data-ttu-id="e83f6-122">[交互适配器端到端可靠传递](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md) </span><span class="sxs-lookup"><span data-stu-id="e83f6-122">[InterAct Adapter End-to-End Reliable Delivery](../../adapters-and-accelerators/fileact-interact/interact-adapter-end-to-end-reliable-delivery.md) </span></span>  
 <span data-ttu-id="e83f6-123">[交互适配器状态监视](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md) </span><span class="sxs-lookup"><span data-stu-id="e83f6-123">[InterAct Adapter Status Monitoring](../../adapters-and-accelerators/fileact-interact/interact-adapter-status-monitoring.md) </span></span>  
 [<span data-ttu-id="e83f6-124">交互适配器不可否认性</span><span class="sxs-lookup"><span data-stu-id="e83f6-124">InterAct Adapter Non-Repudiation</span></span>](../../adapters-and-accelerators/fileact-interact/interact-adapter-non-repudiation.md)