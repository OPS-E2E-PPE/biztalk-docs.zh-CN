---
title: 示例体系结构： 文件适配器 |Microsoft 文档
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
- File adapters, security
- security, examples
- security, architecture
- examples, architecture
- architecture, security
- File adapters, architecture examples
ms.assetid: fdcbba0c-e301-46ce-8940-d617232cafbd
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 11884786f743ece21a8009ea339a251b107420c9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269605"
---
# <a name="sample-architecture-file-adapter"></a><span data-ttu-id="97769-102">示例体系结构： 文件适配器</span><span class="sxs-lookup"><span data-stu-id="97769-102">Sample Architecture: File Adapter</span></span>
<span data-ttu-id="97769-103">本主题将介绍使用文件适配器发送和接收消息时的示例结构。</span><span class="sxs-lookup"><span data-stu-id="97769-103">This topic describes the sample architecture when you use the File adapter to send and receive messages.</span></span>  
  
## <a name="file-adapter-components"></a><span data-ttu-id="97769-104">文件适配器组件</span><span class="sxs-lookup"><span data-stu-id="97769-104">File Adapter Components</span></span>  
 <span data-ttu-id="97769-105">下图显示使用文件适配器时 BizTalk Server 示例结构的组件。</span><span class="sxs-lookup"><span data-stu-id="97769-105">The following figure shows the components of the BizTalk Server sample architecture when you use the File adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="97769-106">如果使用 EDI 适配器，此示例结构同样适用。</span><span class="sxs-lookup"><span data-stu-id="97769-106">This sample architecture is also applicable when you use the EDI adapter.</span></span>  
  
 <span data-ttu-id="97769-107">**显示文件适配器的图 1 示例体系结构**</span><span class="sxs-lookup"><span data-stu-id="97769-107">**Figure 1 Sample architecture that shows File adapter**</span></span>  
  
 <span data-ttu-id="97769-108">![示例文件适配器的体系结构](../core/media/tdi-sec-refarch-file.gif "TDI_Sec_RefArch_File")</span><span class="sxs-lookup"><span data-stu-id="97769-108">![Sample architecture for File adapter](../core/media/tdi-sec-refarch-file.gif "TDI_Sec_RefArch_File")</span></span>  
  
 <span data-ttu-id="97769-109">此示例结构包含以下部分中介绍的组件。</span><span class="sxs-lookup"><span data-stu-id="97769-109">This sample architecture contains the components discussed in the following sections.</span></span>  
  
## <a name="perimeter-network-internet"></a><span data-ttu-id="97769-110">外围网络 - Internet</span><span class="sxs-lookup"><span data-stu-id="97769-110">Perimeter network-Internet</span></span>  
 <span data-ttu-id="97769-111">公司通常将文件协议用于基于 Intranet 的通信，因此，在 Internet 外围网络中您不需要任何服务器以支持此方案。</span><span class="sxs-lookup"><span data-stu-id="97769-111">Companies commonly use the File protocol for intranet-based communications, and therefore you do not need any servers in the Internet perimeter network to support this scenario.</span></span>  
  
## <a name="perimeter-network-intranet"></a><span data-ttu-id="97769-112">外围网络 - Intranet</span><span class="sxs-lookup"><span data-stu-id="97769-112">Perimeter network-intranet</span></span>  
 <span data-ttu-id="97769-113">如果您使用文件适配器，则在 Intranet 外围网络中需要存在文件服务器。</span><span class="sxs-lookup"><span data-stu-id="97769-113">When you use the File adapter, there is a File server in the intranet perimeter network.</span></span> <span data-ttu-id="97769-114">您的合作伙伴在此服务器上存放其消息，而且 BizTalk 文件接收适配器从此服务器中提取消息。</span><span class="sxs-lookup"><span data-stu-id="97769-114">This is the server where your partners drop their messages, and the BizTalk File receive adapter picks up messages from this server.</span></span>  
  
## <a name="e-business-domain"></a><span data-ttu-id="97769-115">电子商务域</span><span class="sxs-lookup"><span data-stu-id="97769-115">E-Business domain</span></span>  
 <span data-ttu-id="97769-116">此域中的服务器如下：</span><span class="sxs-lookup"><span data-stu-id="97769-116">The servers in this domain are:</span></span>  
  
-   <span data-ttu-id="97769-117">**BizTalk Server （处理、 文件适配器和跟踪主机）。**</span><span class="sxs-lookup"><span data-stu-id="97769-117">**BizTalk Server (processing, File adapter, and tracking hosts).**</span></span> <span data-ttu-id="97769-118">此服务器安装有 BizTalk Server 运行时，并具有包含 BizTalk 业务流程、管道、业务规则引擎以及其他业务程序的主机实例。</span><span class="sxs-lookup"><span data-stu-id="97769-118">This server has an installation of the BizTalk Server runtime, and has instances of the hosts that contain the BizTalk orchestrations, pipelines, Business Rule Engine, and other business processes.</span></span> <span data-ttu-id="97769-119">BizTalk Server 端口、接收位置、管道、映射、架构以及程序集均在此服务器上接收、路由、处理和发送消息。</span><span class="sxs-lookup"><span data-stu-id="97769-119">This is where the BizTalk Server ports, receive locations, pipelines, maps, schemas, and assemblies are located to receive, route, process, and send messages.</span></span> <span data-ttu-id="97769-120">此服务器还具有支持的运行状况监视和监视数据的业务的跟踪的主机的主机实例。</span><span class="sxs-lookup"><span data-stu-id="97769-120">This server also has a host instance of a host that supports tracking of health monitoring and business monitoring data.</span></span> <span data-ttu-id="97769-121">此外，此主机包含运行文件发送和接收适配器的主机的实例。</span><span class="sxs-lookup"><span data-stu-id="97769-121">Additionally, this host contains instances of the host that runs the File send and receive adapters.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="97769-122">当需要提高性能时，你可向处理主机的实例环境添加更多的 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="97769-122">As your performance needs increase, you can add more BizTalk Servers to your environment for host instances of your processing hosts.</span></span> <span data-ttu-id="97769-123">有关如何配置 BizTalk Server 的高可用性的详细信息，请参阅[高可用性规划](../core/planning-for-high-availability3.md)。</span><span class="sxs-lookup"><span data-stu-id="97769-123">For more information about how to configure BizTalk Server for high availability, see [Planning for High Availability](../core/planning-for-high-availability3.md).</span></span>  
  
-   <span data-ttu-id="97769-124">**主密钥服务器。**</span><span class="sxs-lookup"><span data-stu-id="97769-124">**Master secret server.**</span></span> <span data-ttu-id="97769-125">作为中相同[示例体系结构： 基 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="97769-125">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="97769-126">**SQL Server。**</span><span class="sxs-lookup"><span data-stu-id="97769-126">**SQL Server.**</span></span> <span data-ttu-id="97769-127">作为中相同[示例体系结构： 基 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="97769-127">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="97769-128">**域控制器。**</span><span class="sxs-lookup"><span data-stu-id="97769-128">**Domain controller.**</span></span> <span data-ttu-id="97769-129">作为中相同[示例体系结构： 基 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="97769-129">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="97769-130">**管理工具。**</span><span class="sxs-lookup"><span data-stu-id="97769-130">**Administration tools.**</span></span> <span data-ttu-id="97769-131">作为中相同[示例体系结构： 基 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="97769-131">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97769-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="97769-132">See Also</span></span>  
 <span data-ttu-id="97769-133">[对于小型和中型公司示例体系结构](../core/sample-architectures-for-small-medium-sized-companies.md) </span><span class="sxs-lookup"><span data-stu-id="97769-133">[Sample Architectures for Small & Medium-Sized Companies](../core/sample-architectures-for-small-medium-sized-companies.md) </span></span>  
 [<span data-ttu-id="97769-134">威胁模型分析的示例方案</span><span class="sxs-lookup"><span data-stu-id="97769-134">Sample Scenarios for Threat Model Analysis</span></span>](../core/sample-scenarios-for-threat-model-analysis.md)