---
title: 示例体系结构：HTTP 和 SOAP 适配器 |Microsoft Docs
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
ms.openlocfilehash: 77b7d8557564cfa94bbfb243447e5e85d4b6865d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65271072"
---
# <a name="sample-architecture-http-and-soap-adapters"></a><span data-ttu-id="a86ea-102">示例体系结构：HTTP 和 SOAP 适配器</span><span class="sxs-lookup"><span data-stu-id="a86ea-102">Sample Architecture: HTTP and SOAP Adapters</span></span>
<span data-ttu-id="a86ea-103">使用 HTTP 和 SOAP 适配器发送和接收消息时，本主题介绍对示例结构。</span><span class="sxs-lookup"><span data-stu-id="a86ea-103">This topic describes the sample architecture when you use the HTTP and SOAP adapters to send and receive messages.</span></span>  
  
 <span data-ttu-id="a86ea-104">使用 HTTP 或 SOAP 适配器时下, 图显示的 BizTalk Server 组件的示例体系结构。</span><span class="sxs-lookup"><span data-stu-id="a86ea-104">The following figure shows the components of the BizTalk Server sample architecture when you use the HTTP or SOAP adapters.</span></span>  
  
 <span data-ttu-id="a86ea-105">**图 1 显示了 HTTP 或 SOAP 适配器的示例结构**</span><span class="sxs-lookup"><span data-stu-id="a86ea-105">**Figure 1 Sample architecture that shows HTTP or SOAP adapters**</span></span>  
  
 <span data-ttu-id="a86ea-106">![示例 HTTP 或 SOAP 适配器的体系结构](../core/media/tdi-sec-refarch-http.gif "TDI_Sec_RefArch_HTTP")</span><span class="sxs-lookup"><span data-stu-id="a86ea-106">![Sample architecture for HTTP or SOAP adapter](../core/media/tdi-sec-refarch-http.gif "TDI_Sec_RefArch_HTTP")</span></span>  
  
 <span data-ttu-id="a86ea-107">此示例结构包含的组件，如以下各节中所述。</span><span class="sxs-lookup"><span data-stu-id="a86ea-107">This sample architecture contains the components as discussed in the following sections.</span></span>  
  
## <a name="perimeter-networkinternet"></a><span data-ttu-id="a86ea-108">外围网络 ― internet</span><span class="sxs-lookup"><span data-stu-id="a86ea-108">Perimeter network―Internet</span></span>  
 <span data-ttu-id="a86ea-109">当使用 SOAP 和 HTTP 适配器时，我们建议使用反向代理规则 （TMG 服务器实施被称为 Web 发布），中继将消息从面向 Internet 的防火墙 (防火墙 1) 到防火墙帮助保护电子商务域 (防火墙 2)，并从此防火墙到运行独立主机的 BizTalk 服务器。</span><span class="sxs-lookup"><span data-stu-id="a86ea-109">When you use the SOAP and HTTP adapters, we recommend that you use reverse proxy rules (the TMG Server implementation is called Web Publishing) to relay the message from the Internet-facing firewall (Firewall 1) to the firewall that helps protect the E-Business domain (Firewall 2), and from this firewall to the BizTalk Server that runs the isolated host.</span></span> <span data-ttu-id="a86ea-110">有关 Web 发布规则的详细信息，请参阅 Microsoft 网站[ http://go.microsoft.com/fwlink/?LinkID=205340 ](http://go.microsoft.com/fwlink/?LinkID=205340) (http://go.microsoft.com/fwlink/?LinkID=205340)。</span><span class="sxs-lookup"><span data-stu-id="a86ea-110">For more information about Web Publishing rules, see the Microsoft Web site at [http://go.microsoft.com/fwlink/?LinkID=205340](http://go.microsoft.com/fwlink/?LinkID=205340) (http://go.microsoft.com/fwlink/?LinkID=205340).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a86ea-111">当使用反向代理时，您不需要外围网络中的 Web 服务器。</span><span class="sxs-lookup"><span data-stu-id="a86ea-111">When you use reverse proxy, you do not need Web servers in the perimeter network.</span></span>  
  
## <a name="perimeter-networkintranet"></a><span data-ttu-id="a86ea-112">外围网络 ― intranet</span><span class="sxs-lookup"><span data-stu-id="a86ea-112">Perimeter network―intranet</span></span>  
 <span data-ttu-id="a86ea-113">公司通常使用 HTTP 和 SOAP 协议进行基于 Internet 的通信，并因此不需要支持此方案在 intranet 外围网络中的任何服务器。</span><span class="sxs-lookup"><span data-stu-id="a86ea-113">Companies commonly use the HTTP and SOAP protocols for Internet-based communications, and therefore you do not need any servers in the intranet perimeter network to support this scenario.</span></span> <span data-ttu-id="a86ea-114">如果必须通过 HTTP 或 SOAP 协议与 BizTalk Server 集成在 intranet 中的内部应用程序，则应遵循针对 Internet 外围网络的建议。</span><span class="sxs-lookup"><span data-stu-id="a86ea-114">If you have an internal application in the intranet that integrates with BizTalk Server through the HTTP or SOAP protocols, you should follow the recommendations for the Internet perimeter network.</span></span>  
  
## <a name="e-business-domain"></a><span data-ttu-id="a86ea-115">电子商务域</span><span class="sxs-lookup"><span data-stu-id="a86ea-115">E-Business domain</span></span>  
 <span data-ttu-id="a86ea-116">此域包含的所有基础结构和使用您的 BizTalk Server 实施的应用程序。</span><span class="sxs-lookup"><span data-stu-id="a86ea-116">This domain contains all the infrastructure and applications used by your BizTalk Server implementation.</span></span> <span data-ttu-id="a86ea-117">此域中的服务器是：</span><span class="sxs-lookup"><span data-stu-id="a86ea-117">The servers in this domain are:</span></span>  
  
-   <span data-ttu-id="a86ea-118">**BizTalk Server （处理和跟踪主机）。**</span><span class="sxs-lookup"><span data-stu-id="a86ea-118">**BizTalk Server (processing and tracking hosts).**</span></span> <span data-ttu-id="a86ea-119">此服务器安装了 BizTalk Server 运行时，并具有包含 BizTalk 业务流程、 管道、 业务规则引擎和其他业务流程主机实例。</span><span class="sxs-lookup"><span data-stu-id="a86ea-119">This server has an installation of the BizTalk Server runtime, and has instances of the hosts that contain the BizTalk orchestrations, pipelines, Business Rule Engine, and other business processes.</span></span> <span data-ttu-id="a86ea-120">此服务器还具有支持跟踪运行状况监视和业务监视数据的主机的主机实例。</span><span class="sxs-lookup"><span data-stu-id="a86ea-120">This server also has a host instance of a host that supports tracking of health monitoring and business monitoring data.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a86ea-121">根据性能需求的增加，您可以添加更多 BizTalk Server 对您的环境的处理主机的主机实例。</span><span class="sxs-lookup"><span data-stu-id="a86ea-121">As your performance needs increase, you can add more BizTalk Servers to your environment for host instances of your processing hosts.</span></span>  
  
-   <span data-ttu-id="a86ea-122">**BizTalk Server （SOAP 和 HTTP 适配器的独立主机）。**</span><span class="sxs-lookup"><span data-stu-id="a86ea-122">**BizTalk Server (isolated hosts for SOAP and HTTP adapters).**</span></span> <span data-ttu-id="a86ea-123">此服务器安装了 BizTalk Server 运行时，并具有仅包含 HTTP 和 SOAP 适配器主机实例。</span><span class="sxs-lookup"><span data-stu-id="a86ea-123">This server has an installation of the BizTalk Server runtime, and has only instances of the hosts that contain the HTTP and SOAP adapters.</span></span> <span data-ttu-id="a86ea-124">这些主机运行在单独的服务器由于这些适配器要求你在计算机上安装 Internet 信息服务 (IIS) 运行它们。</span><span class="sxs-lookup"><span data-stu-id="a86ea-124">These hosts run in a separate server because these adapters require that you install Internet Information Services (IIS) on the computer where they run.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a86ea-125">根据性能需求的增加，您可以添加更多 BizTalk Server 环境 HTTP 和 SOAP 适配器主机的主机实例。</span><span class="sxs-lookup"><span data-stu-id="a86ea-125">As your performance needs increase, you can add more BizTalk Servers to your environment for host instances of your HTTP and SOAP adapter hosts.</span></span> <span data-ttu-id="a86ea-126">当执行此操作时，还必须配置网络负载平衡 (NLB)。</span><span class="sxs-lookup"><span data-stu-id="a86ea-126">When you do this, you must also configure Network Load Balancing (NLB).</span></span> <span data-ttu-id="a86ea-127">有关如何配置 BizTalk Server 的高可用性的详细信息，请参阅[以实现高可用性规划](../core/planning-for-high-availability3.md)。</span><span class="sxs-lookup"><span data-stu-id="a86ea-127">For more information about how to configure BizTalk Server for high availability, see [Planning for High Availability](../core/planning-for-high-availability3.md).</span></span>  
  
-   <span data-ttu-id="a86ea-128">**主密钥服务器。**</span><span class="sxs-lookup"><span data-stu-id="a86ea-128">**Master secret server.**</span></span> <span data-ttu-id="a86ea-129">中的相同[示例体系结构：基本 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="a86ea-129">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="a86ea-130">**SQL Server。**</span><span class="sxs-lookup"><span data-stu-id="a86ea-130">**SQL Server.**</span></span> <span data-ttu-id="a86ea-131">中的相同[示例体系结构：基本 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="a86ea-131">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="a86ea-132">**域控制器。**</span><span class="sxs-lookup"><span data-stu-id="a86ea-132">**Domain controller.**</span></span> <span data-ttu-id="a86ea-133">中的相同[示例体系结构：基本 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="a86ea-133">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="a86ea-134">**管理工具。**</span><span class="sxs-lookup"><span data-stu-id="a86ea-134">**Administration tools.**</span></span> <span data-ttu-id="a86ea-135">中的相同[示例体系结构：基本 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="a86ea-135">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a86ea-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="a86ea-136">See Also</span></span>  
 <span data-ttu-id="a86ea-137">[对于小型和中型公司的示例体系结构](../core/sample-architectures-for-small-medium-sized-companies.md) </span><span class="sxs-lookup"><span data-stu-id="a86ea-137">[Sample Architectures for Small & Medium-Sized Companies](../core/sample-architectures-for-small-medium-sized-companies.md) </span></span>  
 [<span data-ttu-id="a86ea-138">威胁模型分析的示例方案</span><span class="sxs-lookup"><span data-stu-id="a86ea-138">Sample Scenarios for Threat Model Analysis</span></span>](../core/sample-scenarios-for-threat-model-analysis.md)