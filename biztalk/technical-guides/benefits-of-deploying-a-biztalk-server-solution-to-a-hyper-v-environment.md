---
title: 潜在优势将 BizTalk Server 解决方案部署到 HYPER-V 虚拟化环境 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 588c70f0-68f0-4e58-8f3d-aa6834397bd4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f6c88a8dcc6386b6030d4ca429010b6db1acfb81
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37024443"
---
# <a name="potential-benefits-of-deploying-a-biztalk-server-solution-to-a-hyper-v-virtualized-environment"></a><span data-ttu-id="1b852-102">潜在优势将 BizTalk Server 解决方案部署到 HYPER-V 虚拟化环境</span><span class="sxs-lookup"><span data-stu-id="1b852-102">Potential Benefits of Deploying a BizTalk Server Solution to a Hyper-V Virtualized Environment</span></span>
<span data-ttu-id="1b852-103">本主题介绍了一些部署的优势在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到 HYPER-V 虚拟化环境的解决方案。</span><span class="sxs-lookup"><span data-stu-id="1b852-103">This topic describes some of the benefits of deploying your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solution to a Hyper-V virtualized environment.</span></span>  
  
## <a name="benefits-of-running-a-biztalk-server-solution-on-a-hyper-v-virtualized-environment"></a><span data-ttu-id="1b852-104">虚拟环境中运行 Hyper V 上的 BizTalk Server 解决方案的好处</span><span class="sxs-lookup"><span data-stu-id="1b852-104">Benefits of Running a BizTalk Server Solution on a Hyper-V Virtualized Environment</span></span>  
 <span data-ttu-id="1b852-105">部署 BizTalk Server 解决方案以在 HYPER-V 虚拟化环境中运行可提供以下大的灵活性和功能：</span><span class="sxs-lookup"><span data-stu-id="1b852-105">Deploying your BizTalk Server solution to run on a Hyper-V virtualized environment provides the following flexibility and functionality:</span></span>  
  
- <span data-ttu-id="1b852-106">**能够在一台物理计算机-定义多个非重复逻辑安全边界**的 HYPER-V 可容纳的非重复逻辑安全边界或在单个物理硬件资源内的分区创建。</span><span class="sxs-lookup"><span data-stu-id="1b852-106">**Ability to define multiple distinct logical security boundaries on a single physical computer -** Hyper-V accommodates the creation of distinct logical security boundaries or partitions within a single physical hardware resource.</span></span> <span data-ttu-id="1b852-107">分区是隔离的单个逻辑单元的虚拟机监控程序，在其中执行操作系统支持。</span><span class="sxs-lookup"><span data-stu-id="1b852-107">A partition is a single logical unit of isolation, supported by the hypervisor, in which operating systems execute.</span></span> <span data-ttu-id="1b852-108">例如，可以创建多个 BizTalk Server 组，而您将不能执行此操作时安装一台 HYPER-V 主机计算机上运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]单个主机计算机的主机操作系统上。</span><span class="sxs-lookup"><span data-stu-id="1b852-108">For example, you could create multiple BizTalk Server groups to run on a single Hyper-V host computer whereas you would not be able to do this when installing [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] on the host operating system of a single host computer.</span></span>  
  
- <span data-ttu-id="1b852-109">**易于部署和管理-** 合并[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可以简化部署过程划分为较少的物理服务器的计算机。</span><span class="sxs-lookup"><span data-stu-id="1b852-109">**Ease of deployment and management –** Consolidation of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computers into fewer physical servers simplifies deployment.</span></span> [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]<span data-ttu-id="1b852-110"> 通过使用.vhd 文件的物理和虚拟计算机部署来使用简化的方法。</span><span class="sxs-lookup"><span data-stu-id="1b852-110"> uses a simplified method for physical and virtual computer deployments by using .vhd files.</span></span> <span data-ttu-id="1b852-111">此外，全面的 HYPER-V 管理解决方案是使用 System Center Virtual Machine Manager 中可用。</span><span class="sxs-lookup"><span data-stu-id="1b852-111">Furthermore, a comprehensive Hyper-V management solution is available with System Center Virtual Machine Manager.</span></span> <span data-ttu-id="1b852-112">有关 System Center Virtual Machine Manager 的详细信息，请参阅[ http://go.microsoft.com/fwlink/?LinkID=111303 ](http://go.microsoft.com/fwlink/?LinkID=111303)。</span><span class="sxs-lookup"><span data-stu-id="1b852-112">For more information about System Center Virtual Machine Manager, see [http://go.microsoft.com/fwlink/?LinkID=111303](http://go.microsoft.com/fwlink/?LinkID=111303).</span></span>  
  
- <span data-ttu-id="1b852-113">**错误通过 HYPER-V 群集-支持**因为 HYPER-V 是群集感知应用程序、 Windows Server 2008 提供了本机主机群集的 HYPER-V 虚拟化环境中创建的虚拟机的支持。</span><span class="sxs-lookup"><span data-stu-id="1b852-113">**Fault tolerance support through Hyper-V clustering -** Because Hyper-V is a cluster aware application, Windows Server 2008 provides native host clustering support for virtual machines created in a Hyper-V virtualized environment.</span></span>  
  
- <span data-ttu-id="1b852-114">**横向扩展的易用**额外的处理能力、 网络带宽和存储容量可以容纳的你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]解决方案快速、 轻松地通过分派到来宾从主计算机的其他可用资源虚拟机。</span><span class="sxs-lookup"><span data-stu-id="1b852-114">**Ease of scale-out -** Additional processing power, network bandwidth, and storage capacity can be accommodated for your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] solution quickly and easily by apportioning additional available resources from the host computer to the guest virtual machine(s).</span></span> <span data-ttu-id="1b852-115">这可能需要升级主计算机或来宾虚拟机在移动到功能更强大的主机计算机。</span><span class="sxs-lookup"><span data-stu-id="1b852-115">This may require that the host computer is upgraded or that the guest virtual machines are moved to a more capable host computer.</span></span> <span data-ttu-id="1b852-116">实时迁移功能[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]允许你将转移到最佳的物理计算机的性能、 缩放或最佳合并运行 Vm，而不会影响用户。</span><span class="sxs-lookup"><span data-stu-id="1b852-116">The live migration feature of [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] allows you to move running VMs to the best physical computer for performance, scaling, or optimal consolidation without impacting users.</span></span>  
  
- <span data-ttu-id="1b852-117">**合并的硬件资源-** 多个物理服务器可以轻松地整合到相对较少的服务器通过实现使用的 HYPER-V 虚拟化。</span><span class="sxs-lookup"><span data-stu-id="1b852-117">**Consolidation of hardware resources -** Multiple physical servers can be easily consolidated into comparatively fewer servers by implementing virtualization with Hyper-V.</span></span> <span data-ttu-id="1b852-118">合并适合于已部署的硬件资源利用。</span><span class="sxs-lookup"><span data-stu-id="1b852-118">Consolidation accommodates full use of deployed hardware resources.</span></span>  
  
  <span data-ttu-id="1b852-119">若要找出更多详细信息的功能和优势的 HYPER-V 提供了，请参阅[使用的 HYPER-V 虚拟化](http://go.microsoft.com/fwlink/?LinkID=202438)。</span><span class="sxs-lookup"><span data-stu-id="1b852-119">To find out more detailed information about the features and benefits Hyper-V provides, see [Virtualization with Hyper-V](http://go.microsoft.com/fwlink/?LinkID=202438).</span></span>