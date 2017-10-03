---
title: "示例体系结构： FTP 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, security
- architecture, examples
- independent software vendor (ISV)
- security, examples
- security, architecture
- examples, architecture
- architecture, security
- FTP adapters, security
- FTP adapters, architecture examples
ms.assetid: 13fc1086-6acc-483c-be83-4ff6a60cd2bc
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bed15e06027bec5e73c19cf73548674bc51ce68a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sample-architecture-ftp-adapter"></a><span data-ttu-id="6714a-102">示例体系结构： FTP 适配器</span><span class="sxs-lookup"><span data-stu-id="6714a-102">Sample Architecture: FTP Adapter</span></span>
<span data-ttu-id="6714a-103">本主题将介绍使用 FTP 适配器发送和接收消息时的示例结构。</span><span class="sxs-lookup"><span data-stu-id="6714a-103">This topic describes the sample architecture when you use the FTP adapter to send and receive messages.</span></span>  
  
 <span data-ttu-id="6714a-104">下图显示了使用 FTP 适配器时 BizTalk Server 示例结构的组件：</span><span class="sxs-lookup"><span data-stu-id="6714a-104">The following figure shows the components of the BizTalk Server sample architecture when you use the FTP adapter.</span></span>  
  
 <span data-ttu-id="6714a-105">**显示 FTP 适配器的图 1 示例体系结构**</span><span class="sxs-lookup"><span data-stu-id="6714a-105">**Figure 1 Sample architecture that shows FTP adapter**</span></span>  
  
 <span data-ttu-id="6714a-106">![示例体系结构为 FTP 适配器](../core/media/tdi-sec-refarch-ftp.gif "TDI_Sec_RefArch_FTP")</span><span class="sxs-lookup"><span data-stu-id="6714a-106">![Sample architecture for FTP adapter](../core/media/tdi-sec-refarch-ftp.gif "TDI_Sec_RefArch_FTP")</span></span>  
  
 <span data-ttu-id="6714a-107">此示例体系结构包含的组件，如以下各节所述。</span><span class="sxs-lookup"><span data-stu-id="6714a-107">This sample architecture contains the components as discussed in following sections.</span></span>  
  
## <a name="perimeter-networkinternet"></a><span data-ttu-id="6714a-108">外围网络 ― Internet</span><span class="sxs-lookup"><span data-stu-id="6714a-108">Perimeter network―Internet</span></span>  
 <span data-ttu-id="6714a-109">使用 FTP 适配器时，Internet 外围网络中需要存在 FTP 服务器。</span><span class="sxs-lookup"><span data-stu-id="6714a-109">When you use the FTP adapter, there is an FTP server in the Internet perimeter network.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6714a-110">FTP 服务器也可以位于您的网络环境之外（例如位于合作伙伴网络中），也可使用第三方独立软件供应商 (ISV) 作为宿主。</span><span class="sxs-lookup"><span data-stu-id="6714a-110">The FTP server can also be located outside your environment—in the partner's network, or hosted by a third-party independent software vendor (ISV).</span></span>  
  
## <a name="perimeter-networkintranet"></a><span data-ttu-id="6714a-111">外围网络 ― Intranet</span><span class="sxs-lookup"><span data-stu-id="6714a-111">Perimeter network―intranet</span></span>  
 <span data-ttu-id="6714a-112">公司通常使用 FTP 协议进行基于 Internet 的通信，因此，在 Intranet 外围网络中不需要任何服务器就可以支持此方案。</span><span class="sxs-lookup"><span data-stu-id="6714a-112">Companies commonly use the FTP protocol for Internet-based communications, and therefore you do not need any servers in the intranet perimeter network to support this scenario.</span></span>  
  
## <a name="e-business-domain"></a><span data-ttu-id="6714a-113">电子商务域</span><span class="sxs-lookup"><span data-stu-id="6714a-113">E-Business domain</span></span>  
 <span data-ttu-id="6714a-114">此域中的服务器如下：</span><span class="sxs-lookup"><span data-stu-id="6714a-114">The servers in this domain are:</span></span>  
  
-   <span data-ttu-id="6714a-115">**BizTalk Server （处理、 FTP 适配器和跟踪主机）。**</span><span class="sxs-lookup"><span data-stu-id="6714a-115">**BizTalk Server (processing, FTP adapter, and tracking hosts).**</span></span> <span data-ttu-id="6714a-116">此服务器安装有 BizTalk Server 运行时，并具有包含 BizTalk 业务流程、管道、业务规则引擎以及其他业务程序的主机实例。</span><span class="sxs-lookup"><span data-stu-id="6714a-116">This server has an installation of the BizTalk Server runtime, and has instances of the hosts that contain the BizTalk orchestrations, pipelines, Business Rule Engine, and other business processes.</span></span> <span data-ttu-id="6714a-117">BizTalk Server 端口、接收位置、管道、映射、架构以及程序集均在此服务器上接收、路由、处理和发送消息。</span><span class="sxs-lookup"><span data-stu-id="6714a-117">This is where the BizTalk Server ports, receive locations, pipelines, maps, schemas, and assemblies are located to receive, route, process, and send messages.</span></span> <span data-ttu-id="6714a-118">此服务器还具有支持的运行状况监视和监视数据的业务的跟踪的主机的主机实例。</span><span class="sxs-lookup"><span data-stu-id="6714a-118">This server also has a host instance of a host that supports tracking of health monitoring and business monitoring data.</span></span> <span data-ttu-id="6714a-119">此外，此主机包含运行 FTP 发送和接收适配器的主机实例。</span><span class="sxs-lookup"><span data-stu-id="6714a-119">Additionally, this host contains instances of the host that runs the FTP send and receive adapters.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6714a-120">当需要提高性能时，你可向处理主机的实例环境添加更多的 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="6714a-120">As your performance needs increase, you can add more BizTalk Servers to your environment for host instances of your processing hosts.</span></span> <span data-ttu-id="6714a-121">有关如何配置 BizTalk Server 的高可用性的详细信息，请参阅[高可用性规划](../core/planning-for-high-availability3.md)。</span><span class="sxs-lookup"><span data-stu-id="6714a-121">For more information about how to configure BizTalk Server for high availability, see [Planning for High Availability](../core/planning-for-high-availability3.md).</span></span>  
  
-   <span data-ttu-id="6714a-122">**主密钥服务器。**</span><span class="sxs-lookup"><span data-stu-id="6714a-122">**Master secret server.**</span></span> <span data-ttu-id="6714a-123">作为中相同[示例体系结构： 基 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="6714a-123">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="6714a-124">**SQL Server。**</span><span class="sxs-lookup"><span data-stu-id="6714a-124">**SQL Server.**</span></span> <span data-ttu-id="6714a-125">与相同[示例体系结构： 基 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="6714a-125">Same as the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="6714a-126">**域控制器。**</span><span class="sxs-lookup"><span data-stu-id="6714a-126">**Domain controller.**</span></span> <span data-ttu-id="6714a-127">如下所示中的相同相同[示例体系结构： 基 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="6714a-127">Same as in the Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="6714a-128">**管理工具。**</span><span class="sxs-lookup"><span data-stu-id="6714a-128">**Administration tools.**</span></span> <span data-ttu-id="6714a-129">作为中相同[示例体系结构： 基 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="6714a-129">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6714a-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6714a-130">See Also</span></span>  
 <span data-ttu-id="6714a-131">[对于小型和中型公司示例体系结构](../core/sample-architectures-for-small-medium-sized-companies.md) </span><span class="sxs-lookup"><span data-stu-id="6714a-131">[Sample Architectures for Small & Medium-Sized Companies](../core/sample-architectures-for-small-medium-sized-companies.md) </span></span>  
 [<span data-ttu-id="6714a-132">威胁模型分析的示例方案</span><span class="sxs-lookup"><span data-stu-id="6714a-132">Sample Scenarios for Threat Model Analysis</span></span>](../core/sample-scenarios-for-threat-model-analysis.md)