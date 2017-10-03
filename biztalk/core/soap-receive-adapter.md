---
title: "SOAP 接收适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SOAP adapters, receive adapters
- receive adapters, SOAP adapters
ms.assetid: bb968fa8-0515-4f3a-bb39-9effb83e960c
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06fac19580d6083ed1b0d4be315d3285acf14fcc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="soap-receive-adapter"></a><span data-ttu-id="faf8d-102">SOAP 接收适配器</span><span class="sxs-lookup"><span data-stu-id="faf8d-102">SOAP Receive Adapter</span></span>
<span data-ttu-id="faf8d-103">您可以使用 SOAP 接收适配器来接收 Web Services 请求。</span><span class="sxs-lookup"><span data-stu-id="faf8d-103">You use the SOAP receive adapter to receive Web service requests.</span></span> <span data-ttu-id="faf8d-104">SOAP 接收适配器可创建 BizTalk 消息对象，并将关联的属性升级到消息上下文中。</span><span class="sxs-lookup"><span data-stu-id="faf8d-104">The SOAP receive adapter creates a BizTalk Message object, and promotes the associated properties to the message context.</span></span>  
  
 <span data-ttu-id="faf8d-105">SOAP 接收 URI 必须关联到一个或多个 BizTalk 业务流程的适配器或作为 web 服务与已发布的架构**BizTalk Web 服务发布向导**。</span><span class="sxs-lookup"><span data-stu-id="faf8d-105">A SOAP receive adapter URI must correlate to one or more BizTalk orchestrations or schemas that have been published as a web service with the **BizTalk Web Services Publishing Wizard**.</span></span> <span data-ttu-id="faf8d-106">已发布的 Web Services 公开一个或多个与 BizTalk 程序集中一个或多个 BizTalk Server 业务流程或架构关联的 Web 方法。</span><span class="sxs-lookup"><span data-stu-id="faf8d-106">The published web service exposes one or more web methods which correlate to one or more BizTalk Server orchestrations or schemas in a BizTalk assembly.</span></span> <span data-ttu-id="faf8d-107">实际上，已发布的 Web Services 用作 BizTalk 业务流程或架构的服务器代理，在客户端与 BizTalk 业务流程或架构之间转发请求和响应。</span><span class="sxs-lookup"><span data-stu-id="faf8d-107">In effect, the published web service acts as a server proxy for the BizTalk orchestration(s) or schema(s) and forwards requests and responses between the client and the BizTalk orchestration(s) or schema(s).</span></span> <span data-ttu-id="faf8d-108">有关发布 BizTalk 业务流程或作为 web 服务的架构的详细信息请参阅[发布 Web 服务](../core/publishing-web-services.md)。</span><span class="sxs-lookup"><span data-stu-id="faf8d-108">For more information about publishing BizTalk orchestrations or schemas as web services see [Publishing Web Services](../core/publishing-web-services.md).</span></span>  
  
 <span data-ttu-id="faf8d-109">使用 SOAP 适配器的接收位置可以配置为单向或请求响应（双向）。</span><span class="sxs-lookup"><span data-stu-id="faf8d-109">A receive location that uses the SOAP adapter can be configured as one-way or request response (two way).</span></span> <span data-ttu-id="faf8d-110">当单向接收位置配置为使用 SOAP 适配器时，关联的 Web Services 会调用绑定到接收端口的 BizTalk 程序集，并将请求的状态返回给客户端。</span><span class="sxs-lookup"><span data-stu-id="faf8d-110">When a one-way receive location is configured to use the SOAP adapter, the associated web service invokes the BizTalk assembly bound to the receive port, and returns the status of the request to the client.</span></span> <span data-ttu-id="faf8d-111">当请求响应（双向）接收位置配置为使用 SOAP 适配器时，关联的 Web Services 会调用绑定到接收端口的 BizTalk 程序集，并将响应文档返回给客户端。</span><span class="sxs-lookup"><span data-stu-id="faf8d-111">When a request response (two way) receive location is configured to use the SOAP Adapter, the associated web service invokes the BizTalk assembly bound to the receive port, and returns a response document to the client.</span></span> <span data-ttu-id="faf8d-112">有关请求响应消息传送的详细信息请参阅[请求-响应消息传送](../core/request-response-messaging.md)。</span><span class="sxs-lookup"><span data-stu-id="faf8d-112">For more information about request response messaging see [Request-Response Messaging](../core/request-response-messaging.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="faf8d-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="faf8d-113">See Also</span></span>  
 <span data-ttu-id="faf8d-114">[什么是 SOAP 适配器？](../core/what-is-the-soap-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="faf8d-114">[What Is the SOAP Adapter?](../core/what-is-the-soap-adapter.md) </span></span>  
 [<span data-ttu-id="faf8d-115">SOAP 适配器安全建议</span><span class="sxs-lookup"><span data-stu-id="faf8d-115">SOAP Adapter Security Recommendations</span></span>](../core/soap-adapter-security-recommendations.md)