---
title: 示例体系结构：文件适配器 |Microsoft Docs
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
ms.openlocfilehash: 961c4e3f7820f88c4935e070c739aacaab5d1a63
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65271151"
---
# <a name="sample-architecture-file-adapter"></a><span data-ttu-id="33951-102">示例体系结构：文件适配器</span><span class="sxs-lookup"><span data-stu-id="33951-102">Sample Architecture: File Adapter</span></span>
<span data-ttu-id="33951-103">使用文件适配器发送和接收消息时，本主题介绍对示例结构。</span><span class="sxs-lookup"><span data-stu-id="33951-103">This topic describes the sample architecture when you use the File adapter to send and receive messages.</span></span>  
  
## <a name="file-adapter-components"></a><span data-ttu-id="33951-104">文件适配器组件</span><span class="sxs-lookup"><span data-stu-id="33951-104">File Adapter Components</span></span>  
 <span data-ttu-id="33951-105">下图显示的 BizTalk Server 组件使用文件适配器时，此示例体系结构。</span><span class="sxs-lookup"><span data-stu-id="33951-105">The following figure shows the components of the BizTalk Server sample architecture when you use the File adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="33951-106">使用 EDI 适配器时，此示例结构化也适用。</span><span class="sxs-lookup"><span data-stu-id="33951-106">This sample architecture is also applicable when you use the EDI adapter.</span></span>  
  
 <span data-ttu-id="33951-107">**图 1 显示了文件适配器的示例结构**</span><span class="sxs-lookup"><span data-stu-id="33951-107">**Figure 1 Sample architecture that shows File adapter**</span></span>  
  
 <span data-ttu-id="33951-108">![示例文件适配器的体系结构](../core/media/tdi-sec-refarch-file.gif "TDI_Sec_RefArch_File")</span><span class="sxs-lookup"><span data-stu-id="33951-108">![Sample architecture for File adapter](../core/media/tdi-sec-refarch-file.gif "TDI_Sec_RefArch_File")</span></span>  
  
 <span data-ttu-id="33951-109">此示例结构包含以下各节所述的组件。</span><span class="sxs-lookup"><span data-stu-id="33951-109">This sample architecture contains the components discussed in the following sections.</span></span>  
  
## <a name="perimeter-network-internet"></a><span data-ttu-id="33951-110">外围网络-Internet</span><span class="sxs-lookup"><span data-stu-id="33951-110">Perimeter network-Internet</span></span>  
 <span data-ttu-id="33951-111">公司通常使用文件协议用于基于 intranet 的通信，并因此不需要 Internet 外围网络以支持此方案中的任何服务器。</span><span class="sxs-lookup"><span data-stu-id="33951-111">Companies commonly use the File protocol for intranet-based communications, and therefore you do not need any servers in the Internet perimeter network to support this scenario.</span></span>  
  
## <a name="perimeter-network-intranet"></a><span data-ttu-id="33951-112">外围网络-intranet</span><span class="sxs-lookup"><span data-stu-id="33951-112">Perimeter network-intranet</span></span>  
 <span data-ttu-id="33951-113">当使用文件适配器时，intranet 外围网络没有的文件服务器。</span><span class="sxs-lookup"><span data-stu-id="33951-113">When you use the File adapter, there is a File server in the intranet perimeter network.</span></span> <span data-ttu-id="33951-114">这是指你的合作伙伴存放其消息，并 BizTalk 文件接收适配器从其中提取消息从该服务器。</span><span class="sxs-lookup"><span data-stu-id="33951-114">This is the server where your partners drop their messages, and the BizTalk File receive adapter picks up messages from this server.</span></span>  
  
## <a name="e-business-domain"></a><span data-ttu-id="33951-115">电子商务域</span><span class="sxs-lookup"><span data-stu-id="33951-115">E-Business domain</span></span>  
 <span data-ttu-id="33951-116">此域中的服务器是：</span><span class="sxs-lookup"><span data-stu-id="33951-116">The servers in this domain are:</span></span>  
  
-   <span data-ttu-id="33951-117">**BizTalk Server （处理、 文件适配器和跟踪主机）。**</span><span class="sxs-lookup"><span data-stu-id="33951-117">**BizTalk Server (processing, File adapter, and tracking hosts).**</span></span> <span data-ttu-id="33951-118">此服务器安装了 BizTalk Server 运行时，并具有包含 BizTalk 业务流程、 管道、 业务规则引擎和其他业务流程主机实例。</span><span class="sxs-lookup"><span data-stu-id="33951-118">This server has an installation of the BizTalk Server runtime, and has instances of the hosts that contain the BizTalk orchestrations, pipelines, Business Rule Engine, and other business processes.</span></span> <span data-ttu-id="33951-119">这是其中 BizTalk Server 端口、 接收位置、 管道、 映射、 架构和程序集位于要接收、 路由、 处理和发送消息。</span><span class="sxs-lookup"><span data-stu-id="33951-119">This is where the BizTalk Server ports, receive locations, pipelines, maps, schemas, and assemblies are located to receive, route, process, and send messages.</span></span> <span data-ttu-id="33951-120">此服务器还具有支持跟踪运行状况监视和业务监视数据的主机的主机实例。</span><span class="sxs-lookup"><span data-stu-id="33951-120">This server also has a host instance of a host that supports tracking of health monitoring and business monitoring data.</span></span> <span data-ttu-id="33951-121">此外，此主机包含运行文件发送主机的实例和接收适配器。</span><span class="sxs-lookup"><span data-stu-id="33951-121">Additionally, this host contains instances of the host that runs the File send and receive adapters.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="33951-122">根据性能需求的增加，您可以添加更多 BizTalk Server 对您的环境的处理主机的主机实例。</span><span class="sxs-lookup"><span data-stu-id="33951-122">As your performance needs increase, you can add more BizTalk Servers to your environment for host instances of your processing hosts.</span></span> <span data-ttu-id="33951-123">有关如何配置 BizTalk Server 的高可用性的详细信息，请参阅[以实现高可用性规划](../core/planning-for-high-availability3.md)。</span><span class="sxs-lookup"><span data-stu-id="33951-123">For more information about how to configure BizTalk Server for high availability, see [Planning for High Availability](../core/planning-for-high-availability3.md).</span></span>  
  
-   <span data-ttu-id="33951-124">**主密钥服务器。**</span><span class="sxs-lookup"><span data-stu-id="33951-124">**Master secret server.**</span></span> <span data-ttu-id="33951-125">中的相同[示例体系结构：基本 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="33951-125">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="33951-126">**SQL Server。**</span><span class="sxs-lookup"><span data-stu-id="33951-126">**SQL Server.**</span></span> <span data-ttu-id="33951-127">中的相同[示例体系结构：基本 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="33951-127">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="33951-128">**域控制器。**</span><span class="sxs-lookup"><span data-stu-id="33951-128">**Domain controller.**</span></span> <span data-ttu-id="33951-129">中的相同[示例体系结构：基本 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="33951-129">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="33951-130">**管理工具。**</span><span class="sxs-lookup"><span data-stu-id="33951-130">**Administration tools.**</span></span> <span data-ttu-id="33951-131">中的相同[示例体系结构：基本 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="33951-131">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33951-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="33951-132">See Also</span></span>  
 <span data-ttu-id="33951-133">[对于小型和中型公司的示例体系结构](../core/sample-architectures-for-small-medium-sized-companies.md) </span><span class="sxs-lookup"><span data-stu-id="33951-133">[Sample Architectures for Small & Medium-Sized Companies](../core/sample-architectures-for-small-medium-sized-companies.md) </span></span>  
 [<span data-ttu-id="33951-134">威胁模型分析的示例方案</span><span class="sxs-lookup"><span data-stu-id="33951-134">Sample Scenarios for Threat Model Analysis</span></span>](../core/sample-scenarios-for-threat-model-analysis.md)