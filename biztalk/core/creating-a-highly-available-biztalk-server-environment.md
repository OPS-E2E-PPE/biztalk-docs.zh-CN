---
title: "创建高度可用的 BizTalk Server 环境 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- architecture, high availability
- architecture, databases
- databases, architecture
- performance
- hosts, multiple
- hosts, architecture
- architecture, hosts
- databases, clustering
- high availability, designing
- BizTalk Server, architecture
- installation, planning
- clustering, databases
- installation, availability
ms.assetid: 758eb3bd-a25b-4863-a4ca-d7a1635f7542
caps.latest.revision: "54"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87044102248d371ea19ed07d676a0e7a0861296e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-a-highly-available-biztalk-server-environment"></a><span data-ttu-id="37eb0-102">创建高度可用的 BizTalk Server 环境</span><span class="sxs-lookup"><span data-stu-id="37eb0-102">Creating a Highly Available BizTalk Server Environment</span></span>
<span data-ttu-id="37eb0-103">本部分介绍如何为数据和 Microsoft 中的通信提供高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]集成不同系统和应用程序时。</span><span class="sxs-lookup"><span data-stu-id="37eb0-103">This section describes how to provide high availability for the data and communications in Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] when integrating disparate systems and applications.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="37eb0-104">从处理的数据，使你能够解决可用性问题通过缩放数据库和承载独立的主机的数据区分开来。</span><span class="sxs-lookup"><span data-stu-id="37eb0-104"> separates the data from the hosts that process the data, enabling you to resolve availability issues by scaling the databases and hosts independently.</span></span>  
  
## <a name="demonstrating-high-availability"></a><span data-ttu-id="37eb0-105">证实高可用性</span><span class="sxs-lookup"><span data-stu-id="37eb0-105">Demonstrating High Availability</span></span>  
 <span data-ttu-id="37eb0-106">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的高可用性着重于恢复在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 部署中可能出现可用性问题的功能组件。</span><span class="sxs-lookup"><span data-stu-id="37eb0-106">High availability for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] focuses on recovering functional components that might disrupt availability in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment.</span></span>  
  
 <span data-ttu-id="37eb0-107">为了演示中的高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，你必须应用失败，并度量恢复中的产品的有效性。</span><span class="sxs-lookup"><span data-stu-id="37eb0-107">To demonstrate high availability in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you have to apply failure and measure the product's effectiveness in recovery.</span></span> <span data-ttu-id="37eb0-108">高度可用的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 部署在发生错误和故障时对外部应用程序和系统几乎没有什么影响，能够确保所有服务继续正常工作，最大程度地减少中断时间。</span><span class="sxs-lookup"><span data-stu-id="37eb0-108">A highly available [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment makes errors and failures transparent to external applications and systems, and makes sure that all services continue functioning correctly with minimal disruption.</span></span>  
  
## <a name="designing-for-high-availability"></a><span data-ttu-id="37eb0-109">针对高可用性进行设计</span><span class="sxs-lookup"><span data-stu-id="37eb0-109">Designing for High Availability</span></span>  
 <span data-ttu-id="37eb0-110">设计[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供高可用性的部署涉及到实现冗余，以便在应用程序集成或业务过程集成方案涉及每个功能组件。</span><span class="sxs-lookup"><span data-stu-id="37eb0-110">Designing a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment that provides high availability involves implementing redundancy for each functional component involved in an application integration or business process integration scenario.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="37eb0-111">从概念上讲从处理的数据的主机分离数据，从而简化了这些方案的实现。</span><span class="sxs-lookup"><span data-stu-id="37eb0-111"> simplifies the implementation of these scenarios by conceptually separating the data from the hosts that process the data.</span></span> <span data-ttu-id="37eb0-112">因此，确保 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 具备高可用性将涉及运行多个主机实例并群集 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 数据库，如下所述：</span><span class="sxs-lookup"><span data-stu-id="37eb0-112">So providing high availability for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] involves running multiple host instances and clustering the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, as follows:</span></span>  
  
-   <span data-ttu-id="37eb0-113">**BizTalk 主机的体系结构**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可以单独的主机并运行多个主机实例以提供高可用性的关键功能，如接收消息，处理业务流程，并将发送消息。</span><span class="sxs-lookup"><span data-stu-id="37eb0-113">**Architecture for BizTalk Hosts** [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] lets you separate hosts and run multiple host instances to provide high availability for key functions such as receiving messages, processing orchestrations, and sending messages.</span></span> <span data-ttu-id="37eb0-114">这些主机不需要任何其他群集或负载平衡机制因为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]自动通过主机实例的多台计算机间分配工作负荷。</span><span class="sxs-lookup"><span data-stu-id="37eb0-114">These hosts do not require any additional clustering or load-balancing mechanism because [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] automatically distributes workload across multiple computers through host instances.</span></span> <span data-ttu-id="37eb0-115">但是，运行 HTTP 适配器和 SOAP 适配器的接收处理程序的主机则需要如网络负载平衡 (NLB) 之类的负载平衡机制来确保高可用性。</span><span class="sxs-lookup"><span data-stu-id="37eb0-115">However, hosts running the receive handler for the HTTP and SOAP adapters require a load-balancing mechanism such as Network Load Balancing (NLB) to provide high availability.</span></span>  
  
-   <span data-ttu-id="37eb0-116">**BizTalk Server 数据库的体系结构**的高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库通常包含在主动/被动服务器群集配置中配置的两个或多个数据库计算机。</span><span class="sxs-lookup"><span data-stu-id="37eb0-116">**Architecture for BizTalk Server databases** High availability for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases typically consists of two or more database computers configured in an active/passive server cluster configuration.</span></span> <span data-ttu-id="37eb0-117">这些计算机共享一个公共的磁盘资源（如 RAID5 SCSI 磁盘阵列或存储区域网络），并使用 Windows 群集提供备份冗余和容错功能。</span><span class="sxs-lookup"><span data-stu-id="37eb0-117">These computers share a common disk resource (such as a RAID5 SCSI disk array or storage area network) and use Windows Clustering to provide backup redundancy and fault tolerance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="37eb0-118">高度可用的环境实际上就是多计算机环境。</span><span class="sxs-lookup"><span data-stu-id="37eb0-118">Highly-available environments are, by nature, multi-computer environments.</span></span> <span data-ttu-id="37eb0-119">配置时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在多台计算机环境中，你必须使用域用户组和帐户。</span><span class="sxs-lookup"><span data-stu-id="37eb0-119">When configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in a multi-computer environment you must use domain user groups and accounts.</span></span>  
  
 <span data-ttu-id="37eb0-120">由于 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 建立在 Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] 或 [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] 以及 Microsoft SQL Server 2008 的基础之上，请确保在配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的主机前部署这些产品并确保其具备高可用性。</span><span class="sxs-lookup"><span data-stu-id="37eb0-120">Because [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is built on Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)], and Microsoft SQL Server 2008, make sure that you deploy these products with high availability before configuring hosts for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="37eb0-121">以下链接包括有关确保这些基础产品的高可用性的信息：</span><span class="sxs-lookup"><span data-stu-id="37eb0-121">The following links include information about providing high availability for these underlying products:</span></span>  
  
-   <span data-ttu-id="37eb0-122">**高可用性 – 始终在技术**、 在可用[http://go.microsoft.com/fwlink/?LinkId=130376](http://go.microsoft.com/fwlink/?LinkId=130376)。</span><span class="sxs-lookup"><span data-stu-id="37eb0-122">**High Availability – Always On Technologies**, available at [http://go.microsoft.com/fwlink/?LinkId=130376](http://go.microsoft.com/fwlink/?LinkId=130376).</span></span>  
  
     <span data-ttu-id="37eb0-123">此白皮书描述 SQL Server 2008 提供的高可用性功能。</span><span class="sxs-lookup"><span data-stu-id="37eb0-123">This whitepaper describes high availability features that are available with SQL Server 2008.</span></span>  
  
-   <span data-ttu-id="37eb0-124">**高可用性解决方案概述**、 在可用[http://go.microsoft.com/fwlink/?LinkId=130377](http://go.microsoft.com/fwlink/?LinkId=130377)。</span><span class="sxs-lookup"><span data-stu-id="37eb0-124">**High Availability Solutions Overview**, available at [http://go.microsoft.com/fwlink/?LinkId=130377](http://go.microsoft.com/fwlink/?LinkId=130377).</span></span>  
  
     <span data-ttu-id="37eb0-125">介绍了 SQL Server 2008 中若干改善服务器或数据库可用性的高可用性解决方案。</span><span class="sxs-lookup"><span data-stu-id="37eb0-125">Introduces several high-availability solutions for SQL Server 2008 that improve the availability of servers or databases.</span></span>  
  
-   <span data-ttu-id="37eb0-126">**Windows 部署服务循序渐进指南**、 在可用[http://go.microsoft.com/fwlink/?LinkId=130379](http://go.microsoft.com/fwlink/?LinkId=130379)。</span><span class="sxs-lookup"><span data-stu-id="37eb0-126">**Windows Deployment Services Step-by-Step Guide**, available at [http://go.microsoft.com/fwlink/?LinkId=130379](http://go.microsoft.com/fwlink/?LinkId=130379).</span></span>  
  
     <span data-ttu-id="37eb0-127">包含有关如何在 Windows Server 2008 中使用 Windows 部署服务角色的循序渐进指南。</span><span class="sxs-lookup"><span data-stu-id="37eb0-127">Contains step-by-step guidance for how to use the Windows Deployment Services role in Windows Server 2008.</span></span>  
  
-   <span data-ttu-id="37eb0-128">**Windows Server 2003 部署工具包： 规划服务器部署**、 在可用[http://go.microsoft.com/fwlink/?LinkId=24433](http://go.microsoft.com/fwlink/?LinkId=24433)。</span><span class="sxs-lookup"><span data-stu-id="37eb0-128">**Windows Server 2003 Deployment Kit: Planning Server Deployments**, available at [http://go.microsoft.com/fwlink/?LinkId=24433](http://go.microsoft.com/fwlink/?LinkId=24433).</span></span>  
  
     <span data-ttu-id="37eb0-129">本书介绍了有关规划服务器存储的信息，以及有关设计和部署大、中型组织中的文件服务器、打印服务器和终端服务器的信息。</span><span class="sxs-lookup"><span data-stu-id="37eb0-129">This book provides information about planning server storage, and information about designing and deploying file servers, print servers, and terminal servers in medium and large organizations.</span></span>  
  
-   <span data-ttu-id="37eb0-130">**为 BizTalk Server 增加可用性**、 在可用[http://go.microsoft.com/fwlink/?LinkId=130457](http://go.microsoft.com/fwlink/?LinkId=130457)。</span><span class="sxs-lookup"><span data-stu-id="37eb0-130">**Increasing Availability for BizTalk Server**, available at [http://go.microsoft.com/fwlink/?LinkId=130457](http://go.microsoft.com/fwlink/?LinkId=130457).</span></span>  
  
     <span data-ttu-id="37eb0-131">部分[BizTalk Server 操作指南](http://go.microsoft.com/fwlink/?LinkId=130458)描述你可以增加的可用性的方式你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统。</span><span class="sxs-lookup"><span data-stu-id="37eb0-131">Section of the [BizTalk Server Operations Guide](http://go.microsoft.com/fwlink/?LinkId=130458) that describes ways you can increase the availability of your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="37eb0-132">本节内容</span><span class="sxs-lookup"><span data-stu-id="37eb0-132">In This Section</span></span>  
  
-   [<span data-ttu-id="37eb0-133">为 BizTalk 主机提供高可用性</span><span class="sxs-lookup"><span data-stu-id="37eb0-133">Providing High Availability for BizTalk Hosts</span></span>](../core/providing-high-availability-for-biztalk-hosts.md)  
  
-   [<span data-ttu-id="37eb0-134">为 BizTalk Server 数据库提供高可用性</span><span class="sxs-lookup"><span data-stu-id="37eb0-134">Providing High Availability for BizTalk Server Databases</span></span>](../core/providing-high-availability-for-biztalk-server-databases.md)  
  
## <a name="see-also"></a><span data-ttu-id="37eb0-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="37eb0-135">See Also</span></span>  
 <span data-ttu-id="37eb0-136">[示例 BizTalk Server 高可用性方案](../core/sample-biztalk-server-high-availability-scenarios.md) </span><span class="sxs-lookup"><span data-stu-id="37eb0-136">[Sample BizTalk Server High Availability Scenarios](../core/sample-biztalk-server-high-availability-scenarios.md) </span></span>  
 [<span data-ttu-id="37eb0-137">Windows Server 群集用于 BizTalk Server Hosts2 为提供高可用性</span><span class="sxs-lookup"><span data-stu-id="37eb0-137">Using Windows Server Cluster to Provide High Availability for BizTalk Server Hosts2</span></span>](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)