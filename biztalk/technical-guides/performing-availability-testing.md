---
title: 执行可用性测试 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 10b543dd-ba85-40da-8c6f-485eddb59158
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bcfc2fcad309e492fd97455cf78f62157e3fd8a4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291299"
---
# <a name="performing-availability-testing"></a><span data-ttu-id="149c9-102">执行可用性测试</span><span class="sxs-lookup"><span data-stu-id="149c9-102">Performing Availability Testing</span></span>
<span data-ttu-id="149c9-103">您应测试系统，以验证它能够从各种级别的故障，范围为从小规模故障 （例如网络卡故障） 到生产服务器的丢失恢复的灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="149c9-103">You should test your system for disaster recovery to verify its ability to recover from various levels of failure, ranging from small-scale failures (such as a network card failure) to the loss of a production server.</span></span> <span data-ttu-id="149c9-104">灾难恢复测试应包括以下步骤：</span><span class="sxs-lookup"><span data-stu-id="149c9-104">Your disaster recovery testing should include the following steps:</span></span>  
  
- <span data-ttu-id="149c9-105">**测试单个硬件组件故障。**</span><span class="sxs-lookup"><span data-stu-id="149c9-105">**Test individual hardware component failure.**</span></span>  
  
   <span data-ttu-id="149c9-106">应测试系统能够从单个硬件组件故障，例如网络或磁盘中恢复。</span><span class="sxs-lookup"><span data-stu-id="149c9-106">You should test the ability of the system to recover from an individual hardware component failure, such as a network or disk.</span></span>  
  
- <span data-ttu-id="149c9-107">**测试单一 BizTalk server 失败。**</span><span class="sxs-lookup"><span data-stu-id="149c9-107">**Test single BizTalk server failure.**</span></span>  
  
   <span data-ttu-id="149c9-108">在大多数[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]生产环境中，主机进程并分散在多台计算机运行之间[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]单一的 BizTalk 组中。</span><span class="sxs-lookup"><span data-stu-id="149c9-108">In most [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] production environments, host processing is spread out among multiple computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in a single BizTalk group.</span></span> <span data-ttu-id="149c9-109">什么是 BizTalk 组能够继续在事件处理的主机组中的服务器之一失败？</span><span class="sxs-lookup"><span data-stu-id="149c9-109">What is the ability of the BizTalk group to continue host processing in the event one of the servers in the group fails?</span></span>  
  
- <span data-ttu-id="149c9-110">**测试群集节点故障转移。**</span><span class="sxs-lookup"><span data-stu-id="149c9-110">**Test cluster node failover.**</span></span>  
  
   <span data-ttu-id="149c9-111">如果 Windows 聚类分析用于提供高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库或 BizTalk 主机，应验证群集节点故障转移功能。</span><span class="sxs-lookup"><span data-stu-id="149c9-111">If Windows Clustering is used to provide high availability for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases or BizTalk Hosts, you should verify cluster node failover functionality.</span></span> <span data-ttu-id="149c9-112">有关使用 Windows 群集提供高可用性的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[核对清单：提供高可用性容错或负载平衡](../technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md)。</span><span class="sxs-lookup"><span data-stu-id="149c9-112">For more information about using Windows Clustering to provide high availability for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Checklist: Providing High Availability with Fault Tolerance or Load Balancing](../technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md).</span></span>  
  
- <span data-ttu-id="149c9-113">**测试恢复使用日志传送的 BizTalk Server 数据库。**</span><span class="sxs-lookup"><span data-stu-id="149c9-113">**Test recovery of BizTalk Server databases using log shipping.**</span></span>  
  
   <span data-ttu-id="149c9-114">您应该验证的恢复[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。</span><span class="sxs-lookup"><span data-stu-id="149c9-114">You should verify the recovery of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span> <span data-ttu-id="149c9-115">有关使用日志传送备份和还原的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，请参阅[什么是 BizTalk Server 日志传送？](../technical-guides/what-is-biztalk-server-log-shipping.md)本指南中或[日志传送](http://go.microsoft.com/fwlink/?LinkID=153450)(<http://go.microsoft.com/fwlink/?LinkID=153450>)。</span><span class="sxs-lookup"><span data-stu-id="149c9-115">For more information about using log shipping to back up and restore [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, see [What Is BizTalk Server Log Shipping?](../technical-guides/what-is-biztalk-server-log-shipping.md) in this guide or [Log Shipping](http://go.microsoft.com/fwlink/?LinkID=153450) (<http://go.microsoft.com/fwlink/?LinkID=153450>).</span></span>  
  
   <span data-ttu-id="149c9-116">应遵循以提高可用性的步骤的清单[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境中使用灾难恢复，请参阅[核对清单：提供高可用性灾难恢复](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="149c9-116">For a checklist of steps that you should follow to increase the availability of a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment using disaster recovery, see [Checklist: Increasing Availability with Disaster Recovery](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="149c9-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="149c9-117">See Also</span></span>  
 [<span data-ttu-id="149c9-118">提供高可用性 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="149c9-118">Increasing Availability for BizTalk Server</span></span>](../technical-guides/increasing-availability-for-biztalk-server.md)