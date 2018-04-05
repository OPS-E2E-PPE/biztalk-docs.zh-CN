---
title: WCF-CustomIsolated 适配器概述 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-CustomIsolated adapters, about WCF-CustomIsolated adapters
ms.assetid: 872fe97a-8a96-4b2a-8cc1-2db9b315c44f
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fdf5a646f586030df6c9492fc6fb2999e49527a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-the-wcf-customisolated-adapter"></a><span data-ttu-id="d5e72-103">WCF-CustomIsolated 适配器概述</span><span class="sxs-lookup"><span data-stu-id="d5e72-103">What Is the WCF-CustomIsolated Adapter?</span></span>
<span data-ttu-id="d5e72-104">通过 WCF-CustomIsolated 适配器，可将 BizTalk Server 中的 WCF 扩展性组件与独立主机配合使用。</span><span class="sxs-lookup"><span data-stu-id="d5e72-104">The WCF-CustomIsolated adapter is used to enable the use of WCF extensibility components in BizTalk Server with an isolated host.</span></span> <span data-ttu-id="d5e72-105">该适配器为 WCF 框架赋予了完整的灵活性。</span><span class="sxs-lookup"><span data-stu-id="d5e72-105">The adapter enables complete flexibility of the WCF framework.</span></span> <span data-ttu-id="d5e72-106">它允许用户选择并配置接收位置的 WCF 绑定，并指定终结点行为和安全设置。</span><span class="sxs-lookup"><span data-stu-id="d5e72-106">It allows users to select and configure a WCF binding for the receive location, and to specify the endpoint behaviors and security settings.</span></span> <span data-ttu-id="d5e72-107">该适配器仅可由 Internet 信息服务 (IIS) 中承载的传输使用。</span><span class="sxs-lookup"><span data-stu-id="d5e72-107">This adapter can only be used by transports that are hosted in Internet Information Services (IIS).</span></span>  
  
 <span data-ttu-id="d5e72-108">WCF-CustomIsolated 适配器仅包含接收适配器。</span><span class="sxs-lookup"><span data-stu-id="d5e72-108">The WCF-CustomIsolated adapter consists of a receive adapter only.</span></span> <span data-ttu-id="d5e72-109">使用 WCF-CustomIsolated 接收适配器，可通过为独立主机中运行的接收位置选择并配置的 WCF 绑定、服务行为、终结点行为、安全机制和入站消息正文来源接收 WCF 服务请求。</span><span class="sxs-lookup"><span data-stu-id="d5e72-109">You use the WCF-CustomIsolated receive adapter to receive WCF service requests through WCF bindings, service behavior, endpoint behavior, security mechanism, and the source of the inbound message body that you selected and configured for the receive location running in an isolated host.</span></span> <span data-ttu-id="d5e72-110">使用 WCF-CustomIsolated 接收适配器的接收位置可以配置为单向或请求-响应（双向）。</span><span class="sxs-lookup"><span data-stu-id="d5e72-110">A receive location that uses the WCF-CustomIsolated receive adapter can be configured as one-way or request-response (two-way).</span></span>  
  
 <span data-ttu-id="d5e72-111">接收适配器有关 WCF 的详细信息，请参阅[WCF 适配器是什么？](../core/what-are-the-wcf-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="d5e72-111">For more information about WCF receive adapters, see [What Are the WCF Adapters?](../core/what-are-the-wcf-adapters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5e72-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d5e72-112">See Also</span></span>  
 <span data-ttu-id="d5e72-113">[配置 WCF CustomIsolated 适配器](../core/configuring-the-wcf-customisolated-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="d5e72-113">[Configuring the WCF-CustomIsolated Adapter](../core/configuring-the-wcf-customisolated-adapter.md) </span></span>  
 [<span data-ttu-id="d5e72-114">WCF 适配器</span><span class="sxs-lookup"><span data-stu-id="d5e72-114">WCF Adapters</span></span>](../core/wcf-adapters.md)