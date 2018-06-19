---
title: 示例体系结构： HTTP 和 SOAP 适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, security
- architecture, examples
- SOAP adapters, security
- Web Publishing
- security, examples
- security, architecture
- SOAP adapters, architecture examples
- examples, architecture
- architecture, security
- HTTP adapters, architecture examples
- reverse proxy rules
- ISA Server implementation
- HTTP adapters, security
ms.assetid: 935197d0-5108-4970-b237-3c6d5b40c5e9
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dae8be185084a9a838876e3d50b605a63c161b66
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269725"
---
# <a name="sample-architecture-http-and-soap-adapters"></a><span data-ttu-id="0fad8-102">示例结构：HTTP 和 SOAP 适配器</span><span class="sxs-lookup"><span data-stu-id="0fad8-102">Sample Architecture: HTTP and SOAP Adapters</span></span>
<span data-ttu-id="0fad8-103">本主题将介绍使用 HTTP 和 SOAP 适配器发送和接收消息时的示例结构。</span><span class="sxs-lookup"><span data-stu-id="0fad8-103">This topic describes the sample architecture when you use the HTTP and SOAP adapters to send and receive messages.</span></span>  
  
 <span data-ttu-id="0fad8-104">下图显示了使用 HTTP 或 SOAP 适配器时 BizTalk Server 示例结构的组件：</span><span class="sxs-lookup"><span data-stu-id="0fad8-104">The following figure shows the components of the BizTalk Server sample architecture when you use the HTTP or SOAP adapters.</span></span>  
  
 <span data-ttu-id="0fad8-105">**显示 HTTP 或 SOAP 适配器的图 1 示例体系结构**</span><span class="sxs-lookup"><span data-stu-id="0fad8-105">**Figure 1 Sample architecture that shows HTTP or SOAP adapters**</span></span>  
  
 <span data-ttu-id="0fad8-106">![示例体系结构为 HTTP 或 SOAP 适配器](../core/media/tdi-sec-refarch-http.gif "TDI_Sec_RefArch_HTTP")</span><span class="sxs-lookup"><span data-stu-id="0fad8-106">![Sample architecture for HTTP or SOAP adapter](../core/media/tdi-sec-refarch-http.gif "TDI_Sec_RefArch_HTTP")</span></span>  
  
 <span data-ttu-id="0fad8-107">此示例结构包含以下各部分所讨论的组件。</span><span class="sxs-lookup"><span data-stu-id="0fad8-107">This sample architecture contains the components as discussed in the following sections.</span></span>  
  
## <a name="perimeter-networkinternet"></a><span data-ttu-id="0fad8-108">外围网络 ― Internet</span><span class="sxs-lookup"><span data-stu-id="0fad8-108">Perimeter network―Internet</span></span>  
 <span data-ttu-id="0fad8-109">使用 SOAP 和 HTTP 适配器时，建议您使用反向代理规则（TMG 服务器实施被称为 Web 发布）将消息从面向 Internet 的防火墙（防火墙 1）中继到帮助保护电子商务域的防火墙（防火墙 2），并从此防火墙中继到运行独立主机的 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="0fad8-109">When you use the SOAP and HTTP adapters, we recommend that you use reverse proxy rules (the TMG Server implementation is called Web Publishing) to relay the message from the Internet-facing firewall (Firewall 1) to the firewall that helps protect the E-Business domain (Firewall 2), and from this firewall to the BizTalk Server that runs the isolated host.</span></span> <span data-ttu-id="0fad8-110">有关 Web 发布规则的详细信息，请参阅 Microsoft 网站[http://go.microsoft.com/fwlink/?LinkID=205340](http://go.microsoft.com/fwlink/?LinkID=205340) (http://go.microsoft.com/fwlink/?LinkID=205340)。</span><span class="sxs-lookup"><span data-stu-id="0fad8-110">For more information about Web Publishing rules, see the Microsoft Web site at [http://go.microsoft.com/fwlink/?LinkID=205340](http://go.microsoft.com/fwlink/?LinkID=205340) (http://go.microsoft.com/fwlink/?LinkID=205340).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0fad8-111">使用反向代理时，在外围网络中不需要 Web 服务器。</span><span class="sxs-lookup"><span data-stu-id="0fad8-111">When you use reverse proxy, you do not need Web servers in the perimeter network.</span></span>  
  
## <a name="perimeter-networkintranet"></a><span data-ttu-id="0fad8-112">外围网络 ― Intranet</span><span class="sxs-lookup"><span data-stu-id="0fad8-112">Perimeter network―intranet</span></span>  
 <span data-ttu-id="0fad8-113">公司通常将 HTTP 和 SOAP 协议用于基于 Internet 的通信，因此，在 Intranet 外围网络中不需要任何服务器就可以支持此方案。</span><span class="sxs-lookup"><span data-stu-id="0fad8-113">Companies commonly use the HTTP and SOAP protocols for Internet-based communications, and therefore you do not need any servers in the intranet perimeter network to support this scenario.</span></span> <span data-ttu-id="0fad8-114">如果 Intranet 中存在通过 HTTP 或 SOAP 协议与 BizTalk Server 相集成的内部应用程序，则应遵循针对 Internet 外围网络的建议。</span><span class="sxs-lookup"><span data-stu-id="0fad8-114">If you have an internal application in the intranet that integrates with BizTalk Server through the HTTP or SOAP protocols, you should follow the recommendations for the Internet perimeter network.</span></span>  
  
## <a name="e-business-domain"></a><span data-ttu-id="0fad8-115">电子商务域</span><span class="sxs-lookup"><span data-stu-id="0fad8-115">E-Business domain</span></span>  
 <span data-ttu-id="0fad8-116">此域包含 BizTalk Server 实现使用的所有基础结构和应用程序。</span><span class="sxs-lookup"><span data-stu-id="0fad8-116">This domain contains all the infrastructure and applications used by your BizTalk Server implementation.</span></span> <span data-ttu-id="0fad8-117">此域中的服务器如下：</span><span class="sxs-lookup"><span data-stu-id="0fad8-117">The servers in this domain are:</span></span>  
  
-   <span data-ttu-id="0fad8-118">**BizTalk Server （处理和跟踪主机）。**</span><span class="sxs-lookup"><span data-stu-id="0fad8-118">**BizTalk Server (processing and tracking hosts).**</span></span> <span data-ttu-id="0fad8-119">此服务器安装有 BizTalk Server 运行时，并具有包含 BizTalk 业务流程、管道、业务规则引擎以及其他业务程序的主机实例。</span><span class="sxs-lookup"><span data-stu-id="0fad8-119">This server has an installation of the BizTalk Server runtime, and has instances of the hosts that contain the BizTalk orchestrations, pipelines, Business Rule Engine, and other business processes.</span></span> <span data-ttu-id="0fad8-120">此服务器还具有支持的运行状况监视和监视数据的业务的跟踪的主机的主机实例。</span><span class="sxs-lookup"><span data-stu-id="0fad8-120">This server also has a host instance of a host that supports tracking of health monitoring and business monitoring data.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0fad8-121">当需要提高性能时，你可向处理主机的实例环境添加更多的 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="0fad8-121">As your performance needs increase, you can add more BizTalk Servers to your environment for host instances of your processing hosts.</span></span>  
  
-   <span data-ttu-id="0fad8-122">**BizTalk Server （独立主机为 SOAP 和 HTTP 适配器）。**</span><span class="sxs-lookup"><span data-stu-id="0fad8-122">**BizTalk Server (isolated hosts for SOAP and HTTP adapters).**</span></span> <span data-ttu-id="0fad8-123">此服务器安装有 BizTalk Server 运行时，并且只具有包含 HTTP 和 SOAP 适配器的主机的实例。</span><span class="sxs-lookup"><span data-stu-id="0fad8-123">This server has an installation of the BizTalk Server runtime, and has only instances of the hosts that contain the HTTP and SOAP adapters.</span></span> <span data-ttu-id="0fad8-124">这些主机运行在单独的服务器中，因为这些适配器需要您在运行它们的计算机上安装 Internet 信息服务 (IIS)。</span><span class="sxs-lookup"><span data-stu-id="0fad8-124">These hosts run in a separate server because these adapters require that you install Internet Information Services (IIS) on the computer where they run.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0fad8-125">当需要提高性能时，您可向 HTTP 和 SOAP 适配器主机的实例环境添加更多的 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="0fad8-125">As your performance needs increase, you can add more BizTalk Servers to your environment for host instances of your HTTP and SOAP adapter hosts.</span></span> <span data-ttu-id="0fad8-126">执行此操作后，还必须配置网络负载平衡 (NLB)。</span><span class="sxs-lookup"><span data-stu-id="0fad8-126">When you do this, you must also configure Network Load Balancing (NLB).</span></span> <span data-ttu-id="0fad8-127">有关如何配置 BizTalk Server 的高可用性的详细信息，请参阅[高可用性规划](../core/planning-for-high-availability3.md)。</span><span class="sxs-lookup"><span data-stu-id="0fad8-127">For more information about how to configure BizTalk Server for high availability, see [Planning for High Availability](../core/planning-for-high-availability3.md).</span></span>  
  
-   <span data-ttu-id="0fad8-128">**主密钥服务器。**</span><span class="sxs-lookup"><span data-stu-id="0fad8-128">**Master secret server.**</span></span> <span data-ttu-id="0fad8-129">作为中相同[示例体系结构： 基 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="0fad8-129">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="0fad8-130">**SQL Server。**</span><span class="sxs-lookup"><span data-stu-id="0fad8-130">**SQL Server.**</span></span> <span data-ttu-id="0fad8-131">作为中相同[示例体系结构： 基 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="0fad8-131">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="0fad8-132">**域控制器。**</span><span class="sxs-lookup"><span data-stu-id="0fad8-132">**Domain controller.**</span></span> <span data-ttu-id="0fad8-133">作为中相同[示例体系结构： 基 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="0fad8-133">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="0fad8-134">**管理工具。**</span><span class="sxs-lookup"><span data-stu-id="0fad8-134">**Administration tools.**</span></span> <span data-ttu-id="0fad8-135">作为中相同[示例体系结构： 基 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="0fad8-135">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fad8-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0fad8-136">See Also</span></span>  
 <span data-ttu-id="0fad8-137">[对于小型和中型公司示例体系结构](../core/sample-architectures-for-small-medium-sized-companies.md) </span><span class="sxs-lookup"><span data-stu-id="0fad8-137">[Sample Architectures for Small & Medium-Sized Companies](../core/sample-architectures-for-small-medium-sized-companies.md) </span></span>  
 [<span data-ttu-id="0fad8-138">威胁模型分析的示例方案</span><span class="sxs-lookup"><span data-stu-id="0fad8-138">Sample Scenarios for Threat Model Analysis</span></span>](../core/sample-scenarios-for-threat-model-analysis.md)