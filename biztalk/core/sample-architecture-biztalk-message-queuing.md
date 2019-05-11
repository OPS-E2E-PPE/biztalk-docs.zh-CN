---
title: 示例体系结构：BizTalk 消息队列 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, security
- Message Queuing binary protocol
- architecture, examples
- security, examples
- security, architecture
- examples, architecture
- MSMQ adapters, security
- architecture, security
- MSMQ adapters, architecture examples
- servers, Windows Message Queuing
- Windows Message Queuing
- message queuing adapters
ms.assetid: a660c798-1c45-4759-a6c8-f11550683a31
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9424562425854dba532e0c1650c6c9070469be0f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393953"
---
# <a name="sample-architecture-biztalk-message-queuing"></a><span data-ttu-id="102b5-102">示例体系结构：BizTalk 消息队列</span><span class="sxs-lookup"><span data-stu-id="102b5-102">Sample Architecture: BizTalk Message Queuing</span></span>
<span data-ttu-id="102b5-103">使用 BizTalk 消息队列适配器发送和接收消息时，本主题介绍对示例结构。</span><span class="sxs-lookup"><span data-stu-id="102b5-103">This topic describes the sample architecture when you use the BizTalk Message Queuing adapter to send and receive messages.</span></span>  
  
 <span data-ttu-id="102b5-104">使用 BizTalk 消息队列适配器时下, 图显示的 BizTalk Server 组件的示例体系结构。</span><span class="sxs-lookup"><span data-stu-id="102b5-104">The following figure shows the components of the BizTalk Server sample architecture when you use the BizTalk Message Queuing adapter.</span></span>  
  
 <span data-ttu-id="102b5-105">**图 1 显示了 BizTalk 消息队列适配器的示例结构**</span><span class="sxs-lookup"><span data-stu-id="102b5-105">**Figure 1 Sample architecture that shows BizTalk Message Queuing adapter**</span></span>  
  
 <span data-ttu-id="102b5-106">![用于 BizTalk 消息队列的示例体系结构](../core/media/tdi-sec-refarch-msmq.gif "TDI_Sec_RefArch_MSMQ")</span><span class="sxs-lookup"><span data-stu-id="102b5-106">![Sample architecture for BizTalk Message Queuing](../core/media/tdi-sec-refarch-msmq.gif "TDI_Sec_RefArch_MSMQ")</span></span>  
  
 <span data-ttu-id="102b5-107">此示例结构包含的组件，如以下各节中所述。</span><span class="sxs-lookup"><span data-stu-id="102b5-107">This sample architecture contains the components as discussed in the following sections.</span></span>  
  
## <a name="perimeter-networkinternet"></a><span data-ttu-id="102b5-108">外围网络 ― internet</span><span class="sxs-lookup"><span data-stu-id="102b5-108">Perimeter network―Internet</span></span>  
 <span data-ttu-id="102b5-109">我们不建议通过 Internet 使用消息队列二进制协议。</span><span class="sxs-lookup"><span data-stu-id="102b5-109">We do not recommend using the Message Queuing binary protocol over the Internet.</span></span> <span data-ttu-id="102b5-110">应允许通过防火墙 1 任何消息队列通信。</span><span class="sxs-lookup"><span data-stu-id="102b5-110">You should not let any Message Queuing traffic through Firewall 1.</span></span> <span data-ttu-id="102b5-111">如果你想要使用的 BizTalk 消息队列适配器通过 Internet 接收消息，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="102b5-111">If you want to use the BizTalk Message Queuing adapter to receive messages over the Internet, do the following:</span></span>  
  
-   <span data-ttu-id="102b5-112">在外围网络中使用的消息队列服务器。</span><span class="sxs-lookup"><span data-stu-id="102b5-112">Use a Message Queuing server in the perimeter network.</span></span>  
  
-   <span data-ttu-id="102b5-113">通过 Internet 使用消息队列的 HTTP 协议。</span><span class="sxs-lookup"><span data-stu-id="102b5-113">Use the Message Queuing HTTP protocol over the Internet.</span></span>  
  
-   <span data-ttu-id="102b5-114">提取从消息队列服务器的消息并将其转发到 BizTalk 消息队列适配器通过使用二进制协议的外围网络中有一个转发应用程序。</span><span class="sxs-lookup"><span data-stu-id="102b5-114">Have a forwarding application in the perimeter network that picks up the messages from the Message Queuing server and forwards them to the BizTalk Message Queuing adapter by using a binary protocol.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="102b5-115">即使使用 BizTalk 消息队列从 Internet 接收消息，BizTalk 消息队列使用应保留的端口将关闭防火墙 1 中。</span><span class="sxs-lookup"><span data-stu-id="102b5-115">Even if you use BizTalk Message Queuing to receive messages from the Internet, the ports that BizTalk Message Queuing uses should remain closed in Firewall 1.</span></span>  
  
## <a name="perimeter-networkintranet"></a><span data-ttu-id="102b5-116">外围网络 ― intranet</span><span class="sxs-lookup"><span data-stu-id="102b5-116">Perimeter network―intranet</span></span>  
 <span data-ttu-id="102b5-117">当 BizTalk 消息队列适配器用于接收来自 intranet 的消息时，没有将消息队列通信转发到运行的 BizTalk 消息队列适配器的主机实例的 BizTalk 服务器的 Windows 消息队列服务器。</span><span class="sxs-lookup"><span data-stu-id="102b5-117">When you use the BizTalk Message Queuing adapter to receive messages from the intranet, there is a Windows Message Queuing server that forwards the Message Queuing traffic to the BizTalk Server that runs a host instance of the BizTalk Message Queuing adapter.</span></span>  
  
 <span data-ttu-id="102b5-118">如果 intranet 和电子商务域共享常见的 Active Directory，消息将通过一系列消息队列路由器，直至到达正确的目标 （BizTalk Server 运行主机实例的 BizTalk 消息队列接收适配器）。</span><span class="sxs-lookup"><span data-stu-id="102b5-118">If the intranet and the E-Business domain share a common Active Directory, a message goes through a series of Message Queuing routers until it reaches the right destination (the BizTalk Server that runs a host instance of the BizTalk Message Queuing receive adapter).</span></span> <span data-ttu-id="102b5-119">此选项不在关系图中表示，因为它是比第一个不太安全。</span><span class="sxs-lookup"><span data-stu-id="102b5-119">This option is not represented in the diagram because it is less secure than the first one.</span></span>  
  
## <a name="e-business-domain"></a><span data-ttu-id="102b5-120">电子商务域</span><span class="sxs-lookup"><span data-stu-id="102b5-120">E-Business domain</span></span>  
 <span data-ttu-id="102b5-121">此域中的服务器是：</span><span class="sxs-lookup"><span data-stu-id="102b5-121">The servers in this domain are:</span></span>  
  
-   <span data-ttu-id="102b5-122">**BizTalk Server （处理、 BizTalk 消息队列适配器和跟踪主机）。**</span><span class="sxs-lookup"><span data-stu-id="102b5-122">**BizTalk Server (processing, BizTalk Message Queuing adapter, and Tracking hosts).**</span></span> <span data-ttu-id="102b5-123">此服务器安装了 BizTalk Server 运行时，并具有包含 BizTalk 业务流程、 管道、 业务规则引擎和其他业务流程主机实例。</span><span class="sxs-lookup"><span data-stu-id="102b5-123">This server has an installation of the BizTalk Server runtime, and has instances of the hosts that contain the BizTalk orchestrations, pipelines, Business Rule Engine, and other business processes.</span></span> <span data-ttu-id="102b5-124">这是其中 BizTalk Server 端口、 接收位置、 管道、 映射、 架构和程序集位于要接收、 路由、 处理和发送消息。</span><span class="sxs-lookup"><span data-stu-id="102b5-124">This is where the BizTalk Server ports, receive locations, pipelines, maps, schemas, and assemblies are located to receive, route, process, and send messages.</span></span> <span data-ttu-id="102b5-125">此服务器还具有支持跟踪运行状况监视和业务监视数据的主机的主机实例。</span><span class="sxs-lookup"><span data-stu-id="102b5-125">This server also has a host instance of a host that supports tracking of health monitoring and business monitoring data.</span></span> <span data-ttu-id="102b5-126">此外，此主机包含运行 BizTalk 消息队列发送和接收适配器的主机实例。</span><span class="sxs-lookup"><span data-stu-id="102b5-126">Additionally, this host contains instances of the host that runs the BizTalk Message Queuing send and receive adapters.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="102b5-127">根据性能需求的增加，您可以添加更多 BizTalk Server 对您的环境的处理主机的主机实例。</span><span class="sxs-lookup"><span data-stu-id="102b5-127">As your performance needs increase, you can add more BizTalk Servers to your environment for host instances of your processing hosts.</span></span>  
  
-   <span data-ttu-id="102b5-128">**主密钥服务器。**</span><span class="sxs-lookup"><span data-stu-id="102b5-128">**Master secret server.**</span></span> <span data-ttu-id="102b5-129">中的相同[示例体系结构：基本 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="102b5-129">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="102b5-130">**SQL Server。**</span><span class="sxs-lookup"><span data-stu-id="102b5-130">**SQL Server.**</span></span> <span data-ttu-id="102b5-131">中的相同[示例体系结构：基本 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="102b5-131">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="102b5-132">**域控制器。**</span><span class="sxs-lookup"><span data-stu-id="102b5-132">**Domain controller.**</span></span> <span data-ttu-id="102b5-133">中的相同[示例体系结构：基本 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="102b5-133">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="102b5-134">**管理工具。**</span><span class="sxs-lookup"><span data-stu-id="102b5-134">**Administration tools.**</span></span> <span data-ttu-id="102b5-135">中的相同[示例体系结构：基本 BizTalk Server](../core/sample-architecture-base-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="102b5-135">Same as in the [Sample Architecture: Base BizTalk Server](../core/sample-architecture-base-biztalk-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="102b5-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="102b5-136">See Also</span></span>  
 <span data-ttu-id="102b5-137">[对于小型和中型公司的示例体系结构](../core/sample-architectures-for-small-medium-sized-companies.md) </span><span class="sxs-lookup"><span data-stu-id="102b5-137">[Sample Architectures for Small & Medium-Sized Companies](../core/sample-architectures-for-small-medium-sized-companies.md) </span></span>  
 [<span data-ttu-id="102b5-138">威胁模型分析的示例方案</span><span class="sxs-lookup"><span data-stu-id="102b5-138">Sample Scenarios for Threat Model Analysis</span></span>](../core/sample-scenarios-for-threat-model-analysis.md)