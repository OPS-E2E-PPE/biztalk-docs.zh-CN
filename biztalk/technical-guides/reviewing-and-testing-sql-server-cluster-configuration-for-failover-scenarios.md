---
title: 查看和测试 SQL Server 群集的故障转移方案配置 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5dbeb383-5b38-4467-acf8-2a5b244e5fa9
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d8e7bed17960700aee84631801e3e26cb05b25c2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302213"
---
# <a name="reviewing-and-testing-sql-server-cluster-configuration-for-failover-scenarios"></a><span data-ttu-id="1a595-102">查看和测试故障转移方案的 SQL Server 群集配置</span><span class="sxs-lookup"><span data-stu-id="1a595-102">Reviewing and Testing SQL Server Cluster Configuration for Failover Scenarios</span></span>
<span data-ttu-id="1a595-103">Windows 群集和 SQL Server，可以在主动/主动模式下运行 SQL Server 的群集的每个节点都是"活动"和正在运行一个或多个 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="1a595-103">Windows Clustering and SQL Server allow you to run SQL Server in Active/Active mode where each node of the cluster is “active” and running one or more SQL Server instances.</span></span> <span data-ttu-id="1a595-104">这将允许您，例如，具有上一个节点和所有其他的 MessageBox 数据库[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]另一个节点上的数据库。</span><span class="sxs-lookup"><span data-stu-id="1a595-104">This would allow you, for example, to have the MessageBox database on one node and all other [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases on the other node.</span></span> <span data-ttu-id="1a595-105">这可以最大化群集的硬件使用情况。</span><span class="sxs-lookup"><span data-stu-id="1a595-105">This allows you to maximize cluster hardware usage.</span></span>  
  
 <span data-ttu-id="1a595-106">如果你使用此配置，但是，您必须验证每个节点在 SQL Server 群集节点故障转移期间可以同时处理的所有 SQL Server 实例的负载。</span><span class="sxs-lookup"><span data-stu-id="1a595-106">If you use this configuration, however, you must verify that each node can simultaneously handle the load of all SQL Server instances during a SQL Server cluster node failover.</span></span>  
  
## <a name="evaluating-failover-for-an-activeactive-cluster"></a><span data-ttu-id="1a595-107">为主动/被动群集评估故障转移</span><span class="sxs-lookup"><span data-stu-id="1a595-107">Evaluating Failover for an Active/Active Cluster</span></span>  
 <span data-ttu-id="1a595-108">验证单个节点可以处理的发生 SQL Server 群集节点故障转移的所有 SQL Server 实例的负载时的注意事项包括：</span><span class="sxs-lookup"><span data-stu-id="1a595-108">Considerations when verifying that a single node can handle the load of all SQL Server instances in the event of a SQL Server cluster node failover include:</span></span>  
  
-   <span data-ttu-id="1a595-109">故障转移节点是否有足够的 CPU 资源？</span><span class="sxs-lookup"><span data-stu-id="1a595-109">Does the failover node have sufficient CPU resources?</span></span>  
  
-   <span data-ttu-id="1a595-110">故障转移节点是否具有足够的内存？</span><span class="sxs-lookup"><span data-stu-id="1a595-110">Does the failover node have sufficient memory?</span></span>  
  
-   <span data-ttu-id="1a595-111">是否有足够的网络带宽？</span><span class="sxs-lookup"><span data-stu-id="1a595-111">Is there sufficient network bandwidth?</span></span>  
  
-   <span data-ttu-id="1a595-112">故障转移节点可以处理增加的磁盘 I/O 争用？</span><span class="sxs-lookup"><span data-stu-id="1a595-112">Can the failover node handle the increased disk I/O contention?</span></span>  
  
 <span data-ttu-id="1a595-113">测试故障转移时，应评估以下方案：</span><span class="sxs-lookup"><span data-stu-id="1a595-113">The following scenarios should be evaluated when testing failover:</span></span>  
  
-   <span data-ttu-id="1a595-114">在活动服务器上的电源故障</span><span class="sxs-lookup"><span data-stu-id="1a595-114">Power failure on the active server</span></span>  
  
-   <span data-ttu-id="1a595-115">被动的服务器上的电源故障</span><span class="sxs-lookup"><span data-stu-id="1a595-115">Power failure on the passive server</span></span>  
  
-   <span data-ttu-id="1a595-116">磁盘连接中断</span><span class="sxs-lookup"><span data-stu-id="1a595-116">Loss of disk connection</span></span>  
  
-   <span data-ttu-id="1a595-117">在活动节点上中断公用网络连接</span><span class="sxs-lookup"><span data-stu-id="1a595-117">Broken public network connection on the Active node</span></span>  
  
-   <span data-ttu-id="1a595-118">在活动节点上中断专用网络连接</span><span class="sxs-lookup"><span data-stu-id="1a595-118">Broken private network connection on the Active node</span></span>  
  
-   <span data-ttu-id="1a595-119">在被动节点上中断公用网络连接</span><span class="sxs-lookup"><span data-stu-id="1a595-119">Broken public network connection on the Passive node</span></span>  
  
-   <span data-ttu-id="1a595-120">在被动节点上中断专用网络连接</span><span class="sxs-lookup"><span data-stu-id="1a595-120">Broken private network connection on the Passive node</span></span>  
  
-   <span data-ttu-id="1a595-121">失败的 SQL Server 服务</span><span class="sxs-lookup"><span data-stu-id="1a595-121">Failed SQL Server service</span></span>  
  
-   <span data-ttu-id="1a595-122">失败的 SQL Server 代理服务</span><span class="sxs-lookup"><span data-stu-id="1a595-122">Failed SQL Server Agent service</span></span>  
  
## <a name="using-an-activeactivepassive-cluster"></a><span data-ttu-id="1a595-123">使用主动/主动/被动群集</span><span class="sxs-lookup"><span data-stu-id="1a595-123">Using an Active/Active/Passive Cluster</span></span>  
 <span data-ttu-id="1a595-124">如果你确定该一个节点不能处理在故障转移方案中的所有 SQL Server 实例，一种替代方法是使用主动/主动/被动聚类分析模型。</span><span class="sxs-lookup"><span data-stu-id="1a595-124">If you determine that one node cannot handle all SQL Server instances in a failover scenario, an alternative is to use an Active/Active/Passive clustering model.</span></span> <span data-ttu-id="1a595-125">主动/主动/被动群集模型会大大提高，始终会有一个被动节点可用于故障转移方案的可能性。</span><span class="sxs-lookup"><span data-stu-id="1a595-125">The Active/Active/Passive clustering model greatly increases the likelihood that there will always be one Passive node available for failover scenarios.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a595-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1a595-126">See Also</span></span>  
 [<span data-ttu-id="1a595-127">清单： 配置 SQL Server</span><span class="sxs-lookup"><span data-stu-id="1a595-127">Checklist: Configuring SQL Server</span></span>](~/technical-guides/checklist-configuring-sql-server.md)