---
title: "什么是 WCF-Custom 适配器？ | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF-Custom adapters, about WCF-Custom adapters
ms.assetid: 7b2178dd-f737-4784-9bcb-e2b3979bfb0d
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e090f82bc43d96dc14295af2fac2807cf1fd137
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-wcf-custom-adapter"></a><span data-ttu-id="5dcd6-103">什么是 WCF-Custom 适配器？</span><span class="sxs-lookup"><span data-stu-id="5dcd6-103">What Is the WCF-Custom Adapter?</span></span>
<span data-ttu-id="5dcd6-104">WCF-Custom 适配器用于在 BizTalk Server 中启用 WCF 扩展性组件。</span><span class="sxs-lookup"><span data-stu-id="5dcd6-104">The WCF-Custom adapter is used to enable the use of WCF extensibility components in BizTalk Server.</span></span> <span data-ttu-id="5dcd6-105">该适配器为 WCF 框架赋予了完整的灵活性。</span><span class="sxs-lookup"><span data-stu-id="5dcd6-105">The adapter enables complete flexibility of the WCF framework.</span></span> <span data-ttu-id="5dcd6-106">用户使用此适配器可以为接收位置和发送端口选择和配置 WCF 绑定。</span><span class="sxs-lookup"><span data-stu-id="5dcd6-106">It allows users to select and configure a WCF binding for the receive location and send port.</span></span> <span data-ttu-id="5dcd6-107">它还允许用户设置终结点行为和安全设置。</span><span class="sxs-lookup"><span data-stu-id="5dcd6-107">It also allows users to set the endpoint behaviors and security settings.</span></span>  
  
 <span data-ttu-id="5dcd6-108">WCF-Custom 适配器由两个适配器组成：一个接收适配器和一个发送适配器。</span><span class="sxs-lookup"><span data-stu-id="5dcd6-108">The WCF-Custom adapter consists of two adapters—a receive adapter and a send adapter.</span></span>  
  
 <span data-ttu-id="5dcd6-109">**WCF 自定义接收适配器**</span><span class="sxs-lookup"><span data-stu-id="5dcd6-109">**WCF-Custom Receive Adapter**</span></span>  
  
 <span data-ttu-id="5dcd6-110">使用 WCF-Custom 接收适配器可通过在接收位置中的传输属性对话框中选择和配置的绑定、服务行为、终结点行为、安全机制以及入站消息正文的来源接收 WCF 服务请求。</span><span class="sxs-lookup"><span data-stu-id="5dcd6-110">You use the WCF-Custom receive adapter to receive WCF service requests through the bindings, service behavior, endpoint behavior, security mechanism, and the source of the inbound message body that you selected and configured in the transport properties dialog in the receive location.</span></span> <span data-ttu-id="5dcd6-111">使用 WCF-Custom 接收适配器的接收位置可以配置为单向或请求-响应（双向）。</span><span class="sxs-lookup"><span data-stu-id="5dcd6-111">A receive location that uses the WCF-Custom receive adapter can be configured as one-way or request-response (two-way).</span></span>  
  
 <span data-ttu-id="5dcd6-112">**WCF 自定义发送适配器**</span><span class="sxs-lookup"><span data-stu-id="5dcd6-112">**WCF-Custom Send Adapter**</span></span>  
  
 <span data-ttu-id="5dcd6-113">使用 WCF-Custom 发送适配器可通过您选择和配置的无类型约定（带有绑定）、服务行为、终结点行为、安全机制以及出站消息正文的来源调用 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="5dcd6-113">You use the WCF-Custom send adapter to call a WCF service through the typeless contract with the bindings, service behavior, endpoint behavior, security mechanism, and the source of the outbound message body that you selected and configured.</span></span>  
  
 <span data-ttu-id="5dcd6-114">有关 WCF 的详细信息接收和发送适配器，请参阅[WCF 适配器是什么？](../core/what-are-the-wcf-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="5dcd6-114">For more information about WCF receive and send adapters, see [What Are the WCF Adapters?](../core/what-are-the-wcf-adapters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5dcd6-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5dcd6-115">See Also</span></span>  
 <span data-ttu-id="5dcd6-116">[配置 WCF 自定义适配器](../core/configuring-the-wcf-custom-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="5dcd6-116">[Configuring the WCF-Custom Adapter](../core/configuring-the-wcf-custom-adapter.md) </span></span>  
 [<span data-ttu-id="5dcd6-117">WCF 适配器</span><span class="sxs-lookup"><span data-stu-id="5dcd6-117">WCF Adapters</span></span>](../core/wcf-adapters.md)