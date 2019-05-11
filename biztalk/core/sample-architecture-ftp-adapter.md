---
title: 示例体系结构：FTP 适配器 |Microsoft Docs
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
- independent software vendor (ISV)
- security, examples
- security, architecture
- examples, architecture
- architecture, security
- FTP adapters, security
- FTP adapters, architecture examples
ms.assetid: 13fc1086-6acc-483c-be83-4ff6a60cd2bc
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: baa9a9514d7e1524cd277e3e822f7b15a2904d7d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393944"
---
# <a name="sample-architecture-ftp-adapter"></a><span data-ttu-id="9b87c-102">示例体系结构：FTP 适配器</span><span class="sxs-lookup"><span data-stu-id="9b87c-102">Sample Architecture: FTP Adapter</span></span>
<span data-ttu-id="9b87c-103">使用 FTP 适配器发送和接收消息时，本主题介绍对示例结构。</span><span class="sxs-lookup"><span data-stu-id="9b87c-103">This topic describes the sample architecture when you use the FTP adapter to send and receive messages.</span></span>  
  
 <span data-ttu-id="9b87c-104">使用 FTP 适配器时下, 图显示的 BizTalk Server 组件的示例体系结构。</span><span class="sxs-lookup"><span data-stu-id="9b87c-104">The following figure shows the components of the BizTalk Server sample architecture when you use the FTP adapter.</span></span>  
  
 <span data-ttu-id="9b87c-105">**图 1 显示了 FTP 适配器的示例结构**</span><span class="sxs-lookup"><span data-stu-id="9b87c-105">**Figure 1 Sample architecture that shows FTP adapter**</span></span>  
  
 <span data-ttu-id="9b87c-106">![示例 FTP 适配器的体系结构](../core/media/tdi-sec-refarch-ftp.gif "TDI_Sec_RefArch_FTP")</span><span class="sxs-lookup"><span data-stu-id="9b87c-106">![Sample architecture for FTP adapter](../core/media/tdi-sec-refarch-ftp.gif "TDI_Sec_RefArch_FTP")</span></span>  
  
 <span data-ttu-id="9b87c-107">此示例结构包含的组件，如以下各节中所述。</span><span class="sxs-lookup"><span data-stu-id="9b87c-107">This sample architecture contains the components as discussed in following sections.</span></span>  
  
## <a name="perimeter-networkinternet"></a><span data-ttu-id="9b87c-108">外围网络 ― internet</span><span class="sxs-lookup"><span data-stu-id="9b87c-108">Perimeter network―Internet</span></span>  
 <span data-ttu-id="9b87c-109">当使用 FTP 适配器时，Internet 外围网络没有 FTP 服务器。</span><span class="sxs-lookup"><span data-stu-id="9b87c-109">When you use the FTP adapter, there is an FTP server in the Internet perimeter network.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9b87c-110">FTP 服务器也可能位于你的环境之外，在合作伙伴的网络中，或由第三方独立软件供应商 (ISV) 托管。</span><span class="sxs-lookup"><span data-stu-id="9b87c-110">The FTP server can also be located outside your environment—in the partner's network, or hosted by a third-party independent software vendor (ISV).</span></span>  
  
## <a name="perimeter-networkintranet"></a><span data-ttu-id="9b87c-111">外围网络 ― intranet</span><span class="sxs-lookup"><span data-stu-id="9b87c-111">Perimeter network―intranet</span></span>  
 <span data-ttu-id="9b87c-112">公司通常使用 FTP 协议进行基于 Internet 的通信，并因此不需要支持此方案在 intranet 外围网络中的任何服务器。</span><span class="sxs-lookup"><span data-stu-id="9b87c-112">Companies commonly use the FTP protocol for Internet-based communications, and therefore you do not need any servers in the intranet perimeter network to support this scenario.</span></span>  
  
## <a name="e-business-domain"></a><span data-ttu-id="9b87c-113">电子商务域</span><span class="sxs-lookup"><span data-stu-id="9b87c-113">E-Business domain</span></span>  
 <span data-ttu-id="9b87c-114">此域中的服务器是：</span><span class="sxs-lookup"><span data-stu-id="9b87c-114">The servers in this domain are:</span></span>  
  
-   <span data-ttu-id="9b87c-115">**BizTalk Server （处理、 FTP 适配器和跟踪主机）。**</span><span class="sxs-lookup"><span data-stu-id="9b87c-115">**BizTalk Server (processing, FTP adapter, and tracking hosts).**</span></span> <span data-ttu-id="9b87c-116">此服务器安装了 BizTalk Server 运行时，并具有包含 BizTalk 业务流程、 管道、 业务规则引擎和其他业务流程主机实例。</span><span class="sxs-lookup"><span data-stu-id="9b87c-116">This server has an installation of the BizTalk Server runtime, and has instances of the hosts that contain the BizTalk orchestrations, pipelines, Business Rule Engine, and other business processes.</span></span> <span data-ttu-id="9b87c-117">这是其中 BizTalk Server 端口、 接收位置、 管道、 映射、 架构和程序集位于要接收、 路由、 处理和发送消息。</span><span class="sxs-lookup"><span data-stu-id="9b87c-117">This is where the BizTalk Server ports, receive locations, pipelines, maps, schemas, and assemblies are located to receive, route, process, and send messages.</span></span> <span data-ttu-id="9b87c-118">此服务器还具有支持跟踪运行状况监视和业务监视数据的主机的主机实例。</span><span class="sxs-lookup"><span data-stu-id="9b87c-118">This server also has a host instance of a host that supports tracking of health monitoring and business monitoring data.</span></span> <span data-ttu-id="9b87c-119">此外，此主机包含运行 FTP 发送主机的实例和接收适配器。</span><span class="sxs-lookup"><span data-stu-id="9b87c-119">Additionally, this host contains instances of the host that runs the FTP send and receive adapters.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9b87c-120">根据性能需求的增加，您可以添加更多 BizTalk Server 对您的环境的处理主机的主机实例。</span><span class="sxs-lookup"><span data-stu-id="9b87c-120">As your performance needs increase, you can add more BizTalk Servers to your environment for host instances of your processing hosts.</span></span> <span data-ttu-id="9b87c-121">有关如何配置 BizTalk Server 的高可用性的详细信息，请参阅[以实现高可用性规划](../core/planning-for-high-availability3.md)。</span><span class="sxs-lookup"><span data-stu-id="9b87c-121">For more information about how to configure BizTalk Server for high availability, see [Planning for High Availability](../core/planning-for-high-availability3.md).</span></span>  
  
-   <span data-ttu-id="9b87c-122">**主密钥服务器。**</span><span class="sxs-lookup"><span data-stu-id="9b87c-122">**Master secret server.**</span></span> <span data-ttu-id="9b87c-123">中的相同[示例体系结构：基本 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="9b87c-123">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="9b87c-124">**SQL Server。**</span><span class="sxs-lookup"><span data-stu-id="9b87c-124">**SQL Server.**</span></span> <span data-ttu-id="9b87c-125">与相同[示例体系结构：基本 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="9b87c-125">Same as the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="9b87c-126">**域控制器。**</span><span class="sxs-lookup"><span data-stu-id="9b87c-126">**Domain controller.**</span></span> <span data-ttu-id="9b87c-127">与以下主题中的相同[示例体系结构：基本 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="9b87c-127">Same as in the Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="9b87c-128">**管理工具。**</span><span class="sxs-lookup"><span data-stu-id="9b87c-128">**Administration tools.**</span></span> <span data-ttu-id="9b87c-129">中的相同[示例体系结构：基本 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="9b87c-129">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b87c-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="9b87c-130">See Also</span></span>  
 <span data-ttu-id="9b87c-131">[对于小型和中型公司的示例体系结构](../core/sample-architectures-for-small-medium-sized-companies.md) </span><span class="sxs-lookup"><span data-stu-id="9b87c-131">[Sample Architectures for Small & Medium-Sized Companies](../core/sample-architectures-for-small-medium-sized-companies.md) </span></span>  
 [<span data-ttu-id="9b87c-132">威胁模型分析的示例方案</span><span class="sxs-lookup"><span data-stu-id="9b87c-132">Sample Scenarios for Threat Model Analysis</span></span>](../core/sample-scenarios-for-threat-model-analysis.md)