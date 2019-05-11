---
title: SOAP 接收适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP adapters, receive adapters
- receive adapters, SOAP adapters
ms.assetid: bb968fa8-0515-4f3a-bb39-9effb83e960c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 908554ad129fed6c99f4b8bb7e1b197cb4bc0ca6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244436"
---
# <a name="soap-receive-adapter"></a><span data-ttu-id="ba388-102">SOAP 接收适配器</span><span class="sxs-lookup"><span data-stu-id="ba388-102">SOAP Receive Adapter</span></span>
<span data-ttu-id="ba388-103">您可以使用 SOAP 接收适配器来接收 Web 服务请求。</span><span class="sxs-lookup"><span data-stu-id="ba388-103">You use the SOAP receive adapter to receive Web service requests.</span></span> <span data-ttu-id="ba388-104">SOAP 接收适配器创建一个 BizTalk 消息对象，并将升级到消息上下文关联的属性。</span><span class="sxs-lookup"><span data-stu-id="ba388-104">The SOAP receive adapter creates a BizTalk Message object, and promotes the associated properties to the message context.</span></span>  
  
 <span data-ttu-id="ba388-105">SOAP 接收的适配器 URI 必须关联到一个或多个 BizTalk 业务流程或架构的已发布为 web 服务与**BizTalk Web Services 发布向导**。</span><span class="sxs-lookup"><span data-stu-id="ba388-105">A SOAP receive adapter URI must correlate to one or more BizTalk orchestrations or schemas that have been published as a web service with the **BizTalk Web Services Publishing Wizard**.</span></span> <span data-ttu-id="ba388-106">已发布的 web 服务公开一个或多个 BizTalk Server 业务流程或架构中的 BizTalk 程序集关联的一个或多个 web 方法。</span><span class="sxs-lookup"><span data-stu-id="ba388-106">The published web service exposes one or more web methods which correlate to one or more BizTalk Server orchestrations or schemas in a BizTalk assembly.</span></span> <span data-ttu-id="ba388-107">实际上，已发布的 web 服务充当 BizTalk 业务流程或转发请求和响应客户端和 BizTalk 业务流程或架构之间的服务器代理。</span><span class="sxs-lookup"><span data-stu-id="ba388-107">In effect, the published web service acts as a server proxy for the BizTalk orchestration(s) or schema(s) and forwards requests and responses between the client and the BizTalk orchestration(s) or schema(s).</span></span> <span data-ttu-id="ba388-108">有关发布 BizTalk 业务流程或架构作为 web 服务的详细信息请参阅[发布 Web Services](../core/publishing-web-services.md)。</span><span class="sxs-lookup"><span data-stu-id="ba388-108">For more information about publishing BizTalk orchestrations or schemas as web services see [Publishing Web Services](../core/publishing-web-services.md).</span></span>  
  
 <span data-ttu-id="ba388-109">使用 SOAP 适配器的接收位置可以配置为单向或请求响应 （双向）。</span><span class="sxs-lookup"><span data-stu-id="ba388-109">A receive location that uses the SOAP adapter can be configured as one-way or request response (two way).</span></span> <span data-ttu-id="ba388-110">当单向接收位置配置为使用 SOAP 适配器时，关联的 web 服务调用绑定到接收端口的 BizTalk 程序集，并返回到客户端请求的状态。</span><span class="sxs-lookup"><span data-stu-id="ba388-110">When a one-way receive location is configured to use the SOAP adapter, the associated web service invokes the BizTalk assembly bound to the receive port, and returns the status of the request to the client.</span></span> <span data-ttu-id="ba388-111">当请求响应 （双向） 接收位置配置为使用 SOAP 适配器时，关联的 web 服务调用绑定到接收端口的 BizTalk 程序集，并将响应文档返回到客户端。</span><span class="sxs-lookup"><span data-stu-id="ba388-111">When a request response (two way) receive location is configured to use the SOAP Adapter, the associated web service invokes the BizTalk assembly bound to the receive port, and returns a response document to the client.</span></span> <span data-ttu-id="ba388-112">有关请求响应消息传送的详细信息请参阅[请求-响应消息传送](../core/request-response-messaging.md)。</span><span class="sxs-lookup"><span data-stu-id="ba388-112">For more information about request response messaging see [Request-Response Messaging](../core/request-response-messaging.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba388-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="ba388-113">See Also</span></span>  
 <span data-ttu-id="ba388-114">[SOAP 适配器是什么？](../core/what-is-the-soap-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="ba388-114">[What Is the SOAP Adapter?](../core/what-is-the-soap-adapter.md) </span></span>  
 [<span data-ttu-id="ba388-115">SOAP 适配器的安全建议</span><span class="sxs-lookup"><span data-stu-id="ba388-115">SOAP Adapter Security Recommendations</span></span>](../core/soap-adapter-security-recommendations.md)