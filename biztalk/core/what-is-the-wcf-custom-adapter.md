---
title: 什么是 Wcf-custom 适配器？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-Custom adapters, about WCF-Custom adapters
ms.assetid: 7b2178dd-f737-4784-9bcb-e2b3979bfb0d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eba1882957ed6974420d4827a43f90e1ef7ecba9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65242759"
---
# <a name="what-is-the-wcf-custom-adapter"></a><span data-ttu-id="6f506-103">什么是 Wcf-custom 适配器？</span><span class="sxs-lookup"><span data-stu-id="6f506-103">What Is the WCF-Custom Adapter?</span></span>
<span data-ttu-id="6f506-104">Wcf-custom 适配器用于启用 BizTalk Server 中的 WCF 扩展性组件使用。</span><span class="sxs-lookup"><span data-stu-id="6f506-104">The WCF-Custom adapter is used to enable the use of WCF extensibility components in BizTalk Server.</span></span> <span data-ttu-id="6f506-105">该适配器能够完整 WCF 框架的灵活性。</span><span class="sxs-lookup"><span data-stu-id="6f506-105">The adapter enables complete flexibility of the WCF framework.</span></span> <span data-ttu-id="6f506-106">它允许用户选择和配置 WCF 绑定的接收位置和发送端口。</span><span class="sxs-lookup"><span data-stu-id="6f506-106">It allows users to select and configure a WCF binding for the receive location and send port.</span></span> <span data-ttu-id="6f506-107">它还允许用户设置终结点行为和安全设置。</span><span class="sxs-lookup"><span data-stu-id="6f506-107">It also allows users to set the endpoint behaviors and security settings.</span></span>  
  
 <span data-ttu-id="6f506-108">WCF 自定义适配器由两个适配器组成： 一个接收适配器和一个发送适配器。</span><span class="sxs-lookup"><span data-stu-id="6f506-108">The WCF-Custom adapter consists of two adapters—a receive adapter and a send adapter.</span></span>  
  
 <span data-ttu-id="6f506-109">**WCF 自定义接收适配器**</span><span class="sxs-lookup"><span data-stu-id="6f506-109">**WCF-Custom Receive Adapter**</span></span>  
  
 <span data-ttu-id="6f506-110">使用 WCF 自定义接收适配器接收 WCF 服务请求通过绑定、 服务行为、 终结点行为、 安全机制和入站消息源的正文您选择和配置中的传输属性对话框中接收位置。</span><span class="sxs-lookup"><span data-stu-id="6f506-110">You use the WCF-Custom receive adapter to receive WCF service requests through the bindings, service behavior, endpoint behavior, security mechanism, and the source of the inbound message body that you selected and configured in the transport properties dialog in the receive location.</span></span> <span data-ttu-id="6f506-111">使用 Wcf-custom 接收适配器的接收位置可以配置为单向或请求-响应 （双向）。</span><span class="sxs-lookup"><span data-stu-id="6f506-111">A receive location that uses the WCF-Custom receive adapter can be configured as one-way or request-response (two-way).</span></span>  
  
 <span data-ttu-id="6f506-112">**WCF 自定义发送适配器**</span><span class="sxs-lookup"><span data-stu-id="6f506-112">**WCF-Custom Send Adapter**</span></span>  
  
 <span data-ttu-id="6f506-113">使用 Wcf-custom 发送适配器通过无类型协定的 WCF 服务调用具有绑定、 服务行为、 终结点行为、 安全机制和选择和配置的出站消息正文的源。</span><span class="sxs-lookup"><span data-stu-id="6f506-113">You use the WCF-Custom send adapter to call a WCF service through the typeless contract with the bindings, service behavior, endpoint behavior, security mechanism, and the source of the outbound message body that you selected and configured.</span></span>  
  
 <span data-ttu-id="6f506-114">有关 WCF 接收和发送适配器，请参阅[WCF 适配器是什么？](../core/what-are-the-wcf-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="6f506-114">For more information about WCF receive and send adapters, see [What Are the WCF Adapters?](../core/what-are-the-wcf-adapters.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f506-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="6f506-115">See Also</span></span>  
 <span data-ttu-id="6f506-116">[配置 WCF 自定义适配器](../core/configuring-the-wcf-custom-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="6f506-116">[Configuring the WCF-Custom Adapter](../core/configuring-the-wcf-custom-adapter.md) </span></span>  
 [<span data-ttu-id="6f506-117">WCF 适配器</span><span class="sxs-lookup"><span data-stu-id="6f506-117">WCF Adapters</span></span>](../core/wcf-adapters.md)