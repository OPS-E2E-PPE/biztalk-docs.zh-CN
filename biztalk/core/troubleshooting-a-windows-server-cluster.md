---
title: "Windows Server 群集进行疑难解答 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 283cf4cd-ce40-48b7-8549-9ab17d7d2c34
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da1159bafc42f6cfbf47621e3b846764e50e5267
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-a-windows-server-cluster"></a><span data-ttu-id="48ce8-102">Windows Server 群集进行疑难解答</span><span class="sxs-lookup"><span data-stu-id="48ce8-102">Troubleshooting a Windows Server Cluster</span></span>
<span data-ttu-id="48ce8-103">Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]支持主机群集支持，以提供高可用性的企业单一登录 (SSO) 主密钥，并提供高可用性的 Windows Server 群集的使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。</span><span class="sxs-lookup"><span data-stu-id="48ce8-103">Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] supports the use of Windows Server cluster for host cluster support, to provide high availability for the Enterprise Single Sign-On (SSO) Master Secret, and to provide high availability for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span> <span data-ttu-id="48ce8-104">此主题提供有关使用一些通用准则[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在 Windows Server 群集环境，并讨论了使用时可能发生的一些已知的问题[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在 Windows Server 群集环境中。</span><span class="sxs-lookup"><span data-stu-id="48ce8-104">This topic provides some general guidelines for using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in a Windows Server cluster environment and discusses some known issues that may occur when using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in a Windows Server cluster environment.</span></span>  
  
## <a name="general-guidelines"></a><span data-ttu-id="48ce8-105">通用指导原则</span><span class="sxs-lookup"><span data-stu-id="48ce8-105">General Guidelines</span></span>  
 <span data-ttu-id="48ce8-106">按照下述通用准则执行可以最大限度地提高 Windows Server 群集的使用效率，以及排除可能影响 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的 Windows Server 群集问题。</span><span class="sxs-lookup"><span data-stu-id="48ce8-106">Follow these general guidelines to maximize productivity with Windows Server cluster and to troubleshoot Windows Server cluster problems that may affect [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
1.  <span data-ttu-id="48ce8-107">全部 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 概念验证都适用于虚拟化服务器环境中的 Windows Server 群集。</span><span class="sxs-lookup"><span data-stu-id="48ce8-107">Complete [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proof of concept work with a Windows Server cluster in a virtualized server environment.</span></span>  
  
     <span data-ttu-id="48ce8-108">**适用于 Windows Server 2008 的 HYPER-V 角色可用于创建虚拟化的服务器环境。**</span><span class="sxs-lookup"><span data-stu-id="48ce8-108">**The Hyper-V role available with Windows Server 2008 can be used to create a virtualized server environment.**</span></span>  
  
    -   <span data-ttu-id="48ce8-109">有关 Windows Server 2008 HYPER-V 的详细信息，请参阅"虚拟化和合并"网址[http://go.microsoft.com/fwlink/?LinkID=121187](http://go.microsoft.com/fwlink/?LinkID=121187)。</span><span class="sxs-lookup"><span data-stu-id="48ce8-109">For more information about Windows Server 2008 Hyper-V, see “Virtualization and Consolidation” at [http://go.microsoft.com/fwlink/?LinkID=121187](http://go.microsoft.com/fwlink/?LinkID=121187).</span></span>  
  
    -   <span data-ttu-id="48ce8-110">有关详细信息的有关的好处的利用随 HYPER-V 一起提供的虚拟化技术的深入信息，请参阅白皮书"高级虚拟化优势的 Windows Server 2008 版本的 Enterprise"下载[http://go.microsoft.com/fwlink/?LinkId=123530](http://go.microsoft.com/fwlink/?LinkId=123530)。</span><span class="sxs-lookup"><span data-stu-id="48ce8-110">For more in depth information about the benefits of leveraging virtualization technology provided with Hyper-V, see the whitepaper "Advanced Virtualization Benefits of Windows Server 2008 Editions for the Enterprise" available for download at [http://go.microsoft.com/fwlink/?LinkId=123530](http://go.microsoft.com/fwlink/?LinkId=123530).</span></span>  
  
    -   <span data-ttu-id="48ce8-111">使用 HYPER-V 创建的 Windows Server 2008 群集的步骤都在[http://go.microsoft.com/fwlink/?LinkId=129680](http://go.microsoft.com/fwlink/?LinkId=129680)。</span><span class="sxs-lookup"><span data-stu-id="48ce8-111">Steps for using Hyper-V to create a Windows Server 2008 cluster are available at [http://go.microsoft.com/fwlink/?LinkId=129680](http://go.microsoft.com/fwlink/?LinkId=129680).</span></span>  
  
     <span data-ttu-id="48ce8-112">通过使 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 概念验证适用于虚拟服务器环境中的 Windows Server 群集，可提供很高的灵活性，并且使用的硬件资源要比 Windows Server 少很多。</span><span class="sxs-lookup"><span data-stu-id="48ce8-112">Doing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proof of concept work with a Windows Server cluster in a virtualized server environment offers great flexibility and uses considerably fewer hardware resources than required for a Windows Server cluster.</span></span> <span data-ttu-id="48ce8-113">如果采用此方法，则要为在主机上并行运行的每台虚拟机分配至少 512 MB 的内存，并且还要为主机操作系统再分配 512 MB 的内存。</span><span class="sxs-lookup"><span data-stu-id="48ce8-113">If this approach is used, allocate at least 512 MB of memory for each virtual machine that is concurrently running on the host computer and an additional 512 MB of memory for the host operating system.</span></span> <span data-ttu-id="48ce8-114">例如，对于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]与使用 5 个虚拟机 （两个 BizTalk Server 群集节点，两个 Microsoft SQL Server 群集节点和一个域控制器），要有 3 GB 的内存在主机上安装的 Windows Server 群集的解决方案计算机。</span><span class="sxs-lookup"><span data-stu-id="48ce8-114">For example, for a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solution with a Windows Server cluster that uses five virtual machines (two BizTalk Server cluster nodes, two Microsoft SQL Server cluster nodes, and one domain controller), you would plan to have 3 GB of memory installed on the host computer.</span></span> <span data-ttu-id="48ce8-115">如果 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 概念验证环境要求超过 2 GB 的内存，请考虑在主机上安装 64 位版本的 Windows（需要 Hyper-V 角色），以确保主机的操作系统可访问所有已安装的内存。</span><span class="sxs-lookup"><span data-stu-id="48ce8-115">If the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proof of concept environment requires more than 2 GB of memory, consider installing a 64-bit version of Windows on the host computer (required for the Hyper-V role) to ensure that all installed memory is accessible by the host operating system.</span></span>  
  
## <a name="troubleshooting-resources"></a><span data-ttu-id="48ce8-116">故障排除资源</span><span class="sxs-lookup"><span data-stu-id="48ce8-116">Troubleshooting Resources</span></span>  
 <span data-ttu-id="48ce8-117">**用于排除 Windows Server 2008 故障转移群集资源**</span><span class="sxs-lookup"><span data-stu-id="48ce8-117">**Resources for troubleshooting Windows Server 2008 failover clustering**</span></span>  
  
-   <span data-ttu-id="48ce8-118">查看[故障转移群集验证和 Windows Server 2008 的故障排除](http://go.microsoft.com/fwlink/?LinkId=129729)Microsoft TechNet 网站上的 TechNet 网络广播。</span><span class="sxs-lookup"><span data-stu-id="48ce8-118">Review the [Failover Cluster Validation and Troubleshooting with Windows Server 2008](http://go.microsoft.com/fwlink/?LinkId=129729) TechNet Webcast on the Microsoft TechNet Web site.</span></span> <span data-ttu-id="48ce8-119">此网络广播介绍了如何对故障转移群集验证进行疑难解答，以及 Windows Server 2008 问题的疑难解答。</span><span class="sxs-lookup"><span data-stu-id="48ce8-119">This web cast describes how to troubleshoot failover cluster validation and troubleshooting with Windows Server 2008.</span></span>  
  
-   <span data-ttu-id="48ce8-120">有关分析 Windows Server 2008 故障转移群集的问题的详细信息，请参阅主题[查看事件和故障转移群集日志](http://go.microsoft.com/fwlink/?LinkId=129730)Microsoft TechNet 网站上。</span><span class="sxs-lookup"><span data-stu-id="48ce8-120">For more information about analyzing problems with Windows Server 2008 failover clustering, review the topic [View Events and Logs for a Failover Cluster](http://go.microsoft.com/fwlink/?LinkId=129730) on the Microsoft TechNet Web site.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="48ce8-121">已知问题</span><span class="sxs-lookup"><span data-stu-id="48ce8-121">Known Issues</span></span>  
  
#### <a name="any-attempt-to-bring-a-clustered-msdtc-resource-online-fails-which-causes-dependent-biztalk-server-services-to-fail"></a><span data-ttu-id="48ce8-122">使群集的 MSDTC 资源联机的任何尝试失败，这导致相关的 BizTalk Server 服务失败</span><span class="sxs-lookup"><span data-stu-id="48ce8-122">Any attempt to bring a clustered MSDTC resource online fails which causes dependent BizTalk Server services to fail</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="48ce8-123">问题</span><span class="sxs-lookup"><span data-stu-id="48ce8-123">Problem</span></span>  
 <span data-ttu-id="48ce8-124">群集的分布式事务处理协调器 (MSDTC) 资源无法联机**联机**选项在群集管理器，这会导致[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]依赖于 MSDTC 的运行时操作失败的事务支持。</span><span class="sxs-lookup"><span data-stu-id="48ce8-124">A clustered Distributed Transaction Coordinator (MSDTC) resource cannot be brought online through the **Bring Online** option in Cluster Administrator, which causes [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] run-time operations that are dependent upon MSDTC transaction support to fail.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="48ce8-125">原因</span><span class="sxs-lookup"><span data-stu-id="48ce8-125">Cause</span></span>  
 <span data-ttu-id="48ce8-126">很多原因都可能导致群集的 MSDTC 资源失败，这些原因包括：</span><span class="sxs-lookup"><span data-stu-id="48ce8-126">Clustered MSDTC resource failure can occur for a number of reasons including the following:</span></span>  
  
-   <span data-ttu-id="48ce8-127">没有使用正确的磁盘和网络名称资源依赖项配置群集的 MSDTC 资源，或者资源依赖项有问题。</span><span class="sxs-lookup"><span data-stu-id="48ce8-127">The clustered MSDTC resource is not configured with the correct Disk and Network Name resource dependencies or the resource dependencies are failing.</span></span>  
  
-   <span data-ttu-id="48ce8-128">权限问题将使群集的 MSDTC 资源不能被激活。</span><span class="sxs-lookup"><span data-stu-id="48ce8-128">Permissions problems are preventing the clustered MSDTC resource from being activated.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="48ce8-129">解决方法</span><span class="sxs-lookup"><span data-stu-id="48ce8-129">Resolution</span></span>  
 <span data-ttu-id="48ce8-130">**完成在 Windows Server 2008 群集上的以下步骤：**</span><span class="sxs-lookup"><span data-stu-id="48ce8-130">**Complete the following steps on a Windows Server 2008 cluster:**</span></span>  
  
-   <span data-ttu-id="48ce8-131">按照中的步骤[清单： 在 Windows Server 2008 故障转移群集中创建 MS DTC 资源](http://go.microsoft.com/fwlink/?LinkId=129677)用于在 Windows Server 2008 故障转移群集上创建一个或多个群集的 MSDTC 资源。</span><span class="sxs-lookup"><span data-stu-id="48ce8-131">Follow the steps in [Checklist: Creating an MS DTC Resource in a Windows Server 2008 Failover Cluster](http://go.microsoft.com/fwlink/?LinkId=129677) for creating one or more clustered MSDTC resources on a Windows Server 2008 failover cluster.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48ce8-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="48ce8-132">See Also</span></span>  
 <span data-ttu-id="48ce8-133">[Windows Server 群集用于 BizTalk Server Hosts2 为提供高可用性](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="48ce8-133">[Using Windows Server Cluster to Provide High Availability for BizTalk Server Hosts2](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md) </span></span>  
 <span data-ttu-id="48ce8-134">[群集的 BizTalk Server 数据库](../core/clustering-the-biztalk-server-databases1.md) </span><span class="sxs-lookup"><span data-stu-id="48ce8-134">[Clustering the BizTalk Server Databases](../core/clustering-the-biztalk-server-databases1.md) </span></span>  
 <span data-ttu-id="48ce8-135">[示例 BizTalk Server 高可用性方案](../core/sample-biztalk-server-high-availability-scenarios.md) </span><span class="sxs-lookup"><span data-stu-id="48ce8-135">[Sample BizTalk Server High Availability Scenarios](../core/sample-biztalk-server-high-availability-scenarios.md) </span></span>  
 [<span data-ttu-id="48ce8-136">高可用性 SSO 安装选项</span><span class="sxs-lookup"><span data-stu-id="48ce8-136">High-Availability SSO Installation Options</span></span>](../core/high-availability-sso-installation-options.md)