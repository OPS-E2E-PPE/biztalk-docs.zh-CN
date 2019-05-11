---
title: 什么是 WCF CustomIsolated 适配器？ | Microsoft Docs
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
ms.openlocfilehash: 1b60cc39092961703f45921c34a518f3da89691c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242790"
---
# <a name="what-is-the-wcf-customisolated-adapter"></a><span data-ttu-id="30f1e-103">什么是 WCF CustomIsolated 适配器？</span><span class="sxs-lookup"><span data-stu-id="30f1e-103">What Is the WCF-CustomIsolated Adapter?</span></span>
<span data-ttu-id="30f1e-104">Wcf-customisolated 适配器用于启用 BizTalk Server 中的 WCF 扩展性组件与独立主机配合使用。</span><span class="sxs-lookup"><span data-stu-id="30f1e-104">The WCF-CustomIsolated adapter is used to enable the use of WCF extensibility components in BizTalk Server with an isolated host.</span></span> <span data-ttu-id="30f1e-105">该适配器能够完整 WCF 框架的灵活性。</span><span class="sxs-lookup"><span data-stu-id="30f1e-105">The adapter enables complete flexibility of the WCF framework.</span></span> <span data-ttu-id="30f1e-106">它允许用户选择和配置 WCF 绑定的接收位置，并指定终结点行为和安全设置。</span><span class="sxs-lookup"><span data-stu-id="30f1e-106">It allows users to select and configure a WCF binding for the receive location, and to specify the endpoint behaviors and security settings.</span></span> <span data-ttu-id="30f1e-107">在 Internet 信息服务 (IIS) 承载的传输仅可以使用此适配器。</span><span class="sxs-lookup"><span data-stu-id="30f1e-107">This adapter can only be used by transports that are hosted in Internet Information Services (IIS).</span></span>  
  
 <span data-ttu-id="30f1e-108">Wcf-customisolated 适配器由一个接收适配器组成。</span><span class="sxs-lookup"><span data-stu-id="30f1e-108">The WCF-CustomIsolated adapter consists of a receive adapter only.</span></span> <span data-ttu-id="30f1e-109">通过 WCF 绑定、 服务行为、 终结点行为、 安全机制和入站的消息正文的选择和配置的源 Wcf-customisolated 接收适配器接收 WCF 服务请求使用的接收位置在独立主机中运行。</span><span class="sxs-lookup"><span data-stu-id="30f1e-109">You use the WCF-CustomIsolated receive adapter to receive WCF service requests through WCF bindings, service behavior, endpoint behavior, security mechanism, and the source of the inbound message body that you selected and configured for the receive location running in an isolated host.</span></span> <span data-ttu-id="30f1e-110">使用 Wcf-customisolated 接收适配器的接收位置可以配置为单向或请求-响应 （双向）。</span><span class="sxs-lookup"><span data-stu-id="30f1e-110">A receive location that uses the WCF-CustomIsolated receive adapter can be configured as one-way or request-response (two-way).</span></span>  
  
 <span data-ttu-id="30f1e-111">接收适配器的有关 WCF 的详细信息，请参阅[WCF 适配器是什么？](../core/what-are-the-wcf-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="30f1e-111">For more information about WCF receive adapters, see [What Are the WCF Adapters?](../core/what-are-the-wcf-adapters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30f1e-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="30f1e-112">See Also</span></span>  
 <span data-ttu-id="30f1e-113">[配置 Wcf-customisolated 适配器](../core/configuring-the-wcf-customisolated-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="30f1e-113">[Configuring the WCF-CustomIsolated Adapter](../core/configuring-the-wcf-customisolated-adapter.md) </span></span>  
 [<span data-ttu-id="30f1e-114">WCF 适配器</span><span class="sxs-lookup"><span data-stu-id="30f1e-114">WCF Adapters</span></span>](../core/wcf-adapters.md)