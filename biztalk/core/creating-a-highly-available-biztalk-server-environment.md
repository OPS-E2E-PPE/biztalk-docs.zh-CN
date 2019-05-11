---
title: 创建高度可用的 BizTalk Server 环境 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 54
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dad0587f02d0307140e5208043eb16735bb6f03e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354172"
---
# <a name="creating-a-highly-available-biztalk-server-environment"></a><span data-ttu-id="ca7e0-102">创建高度可用的 BizTalk Server 环境</span><span class="sxs-lookup"><span data-stu-id="ca7e0-102">Creating a Highly Available BizTalk Server Environment</span></span>
<span data-ttu-id="ca7e0-103">本部分介绍如何为数据和 Microsoft 中的通信提供高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]集成分散的系统和应用程序时。</span><span class="sxs-lookup"><span data-stu-id="ca7e0-103">This section describes how to provide high availability for the data and communications in Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] when integrating disparate systems and applications.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="ca7e0-104">分隔数据与处理数据，使您能够解决可用性问题通过扩展数据库和承载独立的主机。</span><span class="sxs-lookup"><span data-stu-id="ca7e0-104">separates the data from the hosts that process the data, enabling you to resolve availability issues by scaling the databases and hosts independently.</span></span>  
  
## <a name="demonstrating-high-availability"></a><span data-ttu-id="ca7e0-105">证实高可用性</span><span class="sxs-lookup"><span data-stu-id="ca7e0-105">Demonstrating High Availability</span></span>  
 <span data-ttu-id="ca7e0-106">高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]着重于恢复可能会中断中的可用性的功能组件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署。</span><span class="sxs-lookup"><span data-stu-id="ca7e0-106">High availability for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] focuses on recovering functional components that might disrupt availability in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment.</span></span>  
  
 <span data-ttu-id="ca7e0-107">为了演示中的高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，您必须发生故障并度量恢复中的产品的有效性。</span><span class="sxs-lookup"><span data-stu-id="ca7e0-107">To demonstrate high availability in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you have to apply failure and measure the product's effectiveness in recovery.</span></span> <span data-ttu-id="ca7e0-108">高度可用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署使错误和失败对外部应用程序和系统中，透明并可确保所有服务都继续正常工作中断降至最低。</span><span class="sxs-lookup"><span data-stu-id="ca7e0-108">A highly available [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment makes errors and failures transparent to external applications and systems, and makes sure that all services continue functioning correctly with minimal disruption.</span></span>  
  
## <a name="designing-for-high-availability"></a><span data-ttu-id="ca7e0-109">为实现高可用性设计</span><span class="sxs-lookup"><span data-stu-id="ca7e0-109">Designing for High Availability</span></span>  
 <span data-ttu-id="ca7e0-110">设计[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供高可用性部署涉及到实现冗余，以便应用程序集成或业务流程集成方案中所涉及的每个功能组件。</span><span class="sxs-lookup"><span data-stu-id="ca7e0-110">Designing a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment that provides high availability involves implementing redundancy for each functional component involved in an application integration or business process integration scenario.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="ca7e0-111">通过将数据从概念上讲分离与处理数据的主机，简化了这些方案的实现。</span><span class="sxs-lookup"><span data-stu-id="ca7e0-111">simplifies the implementation of these scenarios by conceptually separating the data from the hosts that process the data.</span></span> <span data-ttu-id="ca7e0-112">因此，确保具备高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]涉及运行多个主机实例并群集[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，按如下所示：</span><span class="sxs-lookup"><span data-stu-id="ca7e0-112">So providing high availability for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] involves running multiple host instances and clustering the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, as follows:</span></span>  
  
- <span data-ttu-id="ca7e0-113">**为 BizTalk 主机的体系结构**[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]允许您分隔不同的主机并运行多个主机实例以提供高可用性，如接收消息、 处理业务流程和发送消息的关键功能。</span><span class="sxs-lookup"><span data-stu-id="ca7e0-113">**Architecture for BizTalk Hosts** [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] lets you separate hosts and run multiple host instances to provide high availability for key functions such as receiving messages, processing orchestrations, and sending messages.</span></span> <span data-ttu-id="ca7e0-114">这些主机不需要任何其他群集或负载平衡机制因为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]会自动将工作负荷分散到主机实例的多台计算机。</span><span class="sxs-lookup"><span data-stu-id="ca7e0-114">These hosts do not require any additional clustering or load-balancing mechanism because [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] automatically distributes workload across multiple computers through host instances.</span></span> <span data-ttu-id="ca7e0-115">但是，运行 HTTP 和 SOAP 适配器的接收处理程序的主机需要负载平衡机制如网络负载平衡 (NLB) 来提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="ca7e0-115">However, hosts running the receive handler for the HTTP and SOAP adapters require a load-balancing mechanism such as Network Load Balancing (NLB) to provide high availability.</span></span>  
  
- <span data-ttu-id="ca7e0-116">**BizTalk Server 数据库的体系结构**的高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库通常包含在主动/被动服务器群集配置中配置的两个或多个数据库计算机。</span><span class="sxs-lookup"><span data-stu-id="ca7e0-116">**Architecture for BizTalk Server databases** High availability for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases typically consists of two or more database computers configured in an active/passive server cluster configuration.</span></span> <span data-ttu-id="ca7e0-117">这些计算机共享公共的磁盘资源 （例如 RAID5 SCSI 磁盘阵列或存储区域网络），并使用 Windows 群集提供备份冗余和容错功能。</span><span class="sxs-lookup"><span data-stu-id="ca7e0-117">These computers share a common disk resource (such as a RAID5 SCSI disk array or storage area network) and use Windows Clustering to provide backup redundancy and fault tolerance.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ca7e0-118">高度可用环境的性质，多计算机环境的不同而不同。</span><span class="sxs-lookup"><span data-stu-id="ca7e0-118">Highly-available environments are, by nature, multi-computer environments.</span></span> <span data-ttu-id="ca7e0-119">配置时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在多计算机环境中，您必须使用域用户组和帐户。</span><span class="sxs-lookup"><span data-stu-id="ca7e0-119">When configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in a multi-computer environment you must use domain user groups and accounts.</span></span>  
  
 <span data-ttu-id="ca7e0-120">因为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]基于 Microsoft[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]或[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]，和 Microsoft SQL Server 2008，请确保配置的主机前，具有高可用性部署这些产品[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ca7e0-120">Because [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is built on Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] or [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)], and Microsoft SQL Server 2008, make sure that you deploy these products with high availability before configuring hosts for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="ca7e0-121">以下链接包括有关为这些基础产品提供高可用性的信息：</span><span class="sxs-lookup"><span data-stu-id="ca7e0-121">The following links include information about providing high availability for these underlying products:</span></span>  
  
- <span data-ttu-id="ca7e0-122">**高可用性 – Always On Technologies**，可在[ http://go.microsoft.com/fwlink/?LinkId=130376 ](http://go.microsoft.com/fwlink/?LinkId=130376)。</span><span class="sxs-lookup"><span data-stu-id="ca7e0-122">**High Availability – Always On Technologies**, available at [http://go.microsoft.com/fwlink/?LinkId=130376](http://go.microsoft.com/fwlink/?LinkId=130376).</span></span>  
  
   <span data-ttu-id="ca7e0-123">本白皮书介绍了适用于 SQL Server 2008 的高可用性功能。</span><span class="sxs-lookup"><span data-stu-id="ca7e0-123">This whitepaper describes high availability features that are available with SQL Server 2008.</span></span>  
  
- <span data-ttu-id="ca7e0-124">**高可用性解决方案概述**，可在[ http://go.microsoft.com/fwlink/?LinkId=130377 ](http://go.microsoft.com/fwlink/?LinkId=130377)。</span><span class="sxs-lookup"><span data-stu-id="ca7e0-124">**High Availability Solutions Overview**, available at [http://go.microsoft.com/fwlink/?LinkId=130377](http://go.microsoft.com/fwlink/?LinkId=130377).</span></span>  
  
   <span data-ttu-id="ca7e0-125">为提高可用性的服务器或数据库的 SQL Server 2008 引入了多个高可用性解决方案。</span><span class="sxs-lookup"><span data-stu-id="ca7e0-125">Introduces several high-availability solutions for SQL Server 2008 that improve the availability of servers or databases.</span></span>  
  
- <span data-ttu-id="ca7e0-126">**Windows 部署服务循序渐进指南**，可在[ http://go.microsoft.com/fwlink/?LinkId=130379 ](http://go.microsoft.com/fwlink/?LinkId=130379)。</span><span class="sxs-lookup"><span data-stu-id="ca7e0-126">**Windows Deployment Services Step-by-Step Guide**, available at [http://go.microsoft.com/fwlink/?LinkId=130379](http://go.microsoft.com/fwlink/?LinkId=130379).</span></span>  
  
   <span data-ttu-id="ca7e0-127">包含有关如何在 Windows Server 2008 中使用 Windows 部署服务角色循序渐进指南。</span><span class="sxs-lookup"><span data-stu-id="ca7e0-127">Contains step-by-step guidance for how to use the Windows Deployment Services role in Windows Server 2008.</span></span>  
  
- <span data-ttu-id="ca7e0-128">**Windows Server 2003 部署工具包：规划服务器部署**，可在[ http://go.microsoft.com/fwlink/?LinkId=24433 ](http://go.microsoft.com/fwlink/?LinkId=24433)。</span><span class="sxs-lookup"><span data-stu-id="ca7e0-128">**Windows Server 2003 Deployment Kit: Planning Server Deployments**, available at [http://go.microsoft.com/fwlink/?LinkId=24433](http://go.microsoft.com/fwlink/?LinkId=24433).</span></span>  
  
   <span data-ttu-id="ca7e0-129">本书提供了有关设计和部署文件服务器、 打印服务器和中型和大型组织中的终端服务器的规划服务器存储和信息有关的信息。</span><span class="sxs-lookup"><span data-stu-id="ca7e0-129">This book provides information about planning server storage, and information about designing and deploying file servers, print servers, and terminal servers in medium and large organizations.</span></span>  
  
- <span data-ttu-id="ca7e0-130">**BizTalk Server 提供高可用性**，可在[ http://go.microsoft.com/fwlink/?LinkId=130457 ](http://go.microsoft.com/fwlink/?LinkId=130457)。</span><span class="sxs-lookup"><span data-stu-id="ca7e0-130">**Increasing Availability for BizTalk Server**, available at [http://go.microsoft.com/fwlink/?LinkId=130457](http://go.microsoft.com/fwlink/?LinkId=130457).</span></span>  
  
   <span data-ttu-id="ca7e0-131">部分[BizTalk Server 操作指南](http://go.microsoft.com/fwlink/?LinkId=130458)描述的方式可以提高可用性的你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]系统。</span><span class="sxs-lookup"><span data-stu-id="ca7e0-131">Section of the [BizTalk Server Operations Guide](http://go.microsoft.com/fwlink/?LinkId=130458) that describes ways you can increase the availability of your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ca7e0-132">本节内容</span><span class="sxs-lookup"><span data-stu-id="ca7e0-132">In This Section</span></span>  
  
-   [<span data-ttu-id="ca7e0-133">为 BizTalk 主机提供高可用性</span><span class="sxs-lookup"><span data-stu-id="ca7e0-133">Providing High Availability for BizTalk Hosts</span></span>](../core/providing-high-availability-for-biztalk-hosts.md)  
  
-   [<span data-ttu-id="ca7e0-134">为 BizTalk Server 数据库提供高可用性</span><span class="sxs-lookup"><span data-stu-id="ca7e0-134">Providing High Availability for BizTalk Server Databases</span></span>](../core/providing-high-availability-for-biztalk-server-databases.md)  
  
## <a name="see-also"></a><span data-ttu-id="ca7e0-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="ca7e0-135">See Also</span></span>  
 <span data-ttu-id="ca7e0-136">[BizTalk Server 高可用性示例方案](../core/sample-biztalk-server-high-availability-scenarios.md) </span><span class="sxs-lookup"><span data-stu-id="ca7e0-136">[Sample BizTalk Server High Availability Scenarios](../core/sample-biztalk-server-high-availability-scenarios.md) </span></span>  
 [<span data-ttu-id="ca7e0-137">使用 Windows Server 群集为 BizTalk Server 主机 2 提供高可用性</span><span class="sxs-lookup"><span data-stu-id="ca7e0-137">Using Windows Server Cluster to Provide High Availability for BizTalk Server Hosts2</span></span>](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)