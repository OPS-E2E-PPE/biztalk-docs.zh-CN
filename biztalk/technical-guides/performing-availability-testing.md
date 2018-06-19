---
title: 执行可用性测试 |Microsoft 文档
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
ms.openlocfilehash: e6f0d9b1cb7b38ab8a1173ee227a8202812048f0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298301"
---
# <a name="performing-availability-testing"></a><span data-ttu-id="42952-102">执行可用性测试</span><span class="sxs-lookup"><span data-stu-id="42952-102">Performing Availability Testing</span></span>
<span data-ttu-id="42952-103">你应测试系统，以验证其能够从不同级别的失败，范围从小规模故障 （如网络卡故障） 到生产服务器的丢失将恢复的灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="42952-103">You should test your system for disaster recovery to verify its ability to recover from various levels of failure, ranging from small-scale failures (such as a network card failure) to the loss of a production server.</span></span> <span data-ttu-id="42952-104">灾难恢复测试应包括以下步骤：</span><span class="sxs-lookup"><span data-stu-id="42952-104">Your disaster recovery testing should include the following steps:</span></span>  
  
-   <span data-ttu-id="42952-105">**测试单个硬件组件失败。**</span><span class="sxs-lookup"><span data-stu-id="42952-105">**Test individual hardware component failure.**</span></span>  
  
     <span data-ttu-id="42952-106">你应测试系统能够从单个硬件组件故障，例如网络或磁盘中恢复。</span><span class="sxs-lookup"><span data-stu-id="42952-106">You should test the ability of the system to recover from an individual hardware component failure, such as a network or disk.</span></span>  
  
-   <span data-ttu-id="42952-107">**测试单个 BizTalk server 失败。**</span><span class="sxs-lookup"><span data-stu-id="42952-107">**Test single BizTalk server failure.**</span></span>  
  
     <span data-ttu-id="42952-108">在大多数[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]生产环境中，主机处理并分散在多个计算机中运行[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]单个的 BizTalk 组中。</span><span class="sxs-lookup"><span data-stu-id="42952-108">In most [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] production environments, host processing is spread out among multiple computers running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in a single BizTalk group.</span></span> <span data-ttu-id="42952-109">什么是 BizTalk 组能够继续在事件处理的主机组中的服务器之一失败？</span><span class="sxs-lookup"><span data-stu-id="42952-109">What is the ability of the BizTalk group to continue host processing in the event one of the servers in the group fails?</span></span>  
  
-   <span data-ttu-id="42952-110">**测试群集节点故障转移。**</span><span class="sxs-lookup"><span data-stu-id="42952-110">**Test cluster node failover.**</span></span>  
  
     <span data-ttu-id="42952-111">如果 Windows 群集用于提供的高可用性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库或 BizTalk 主机，应验证群集节点故障转移功能。</span><span class="sxs-lookup"><span data-stu-id="42952-111">If Windows Clustering is used to provide high availability for the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases or BizTalk Hosts, you should verify cluster node failover functionality.</span></span> <span data-ttu-id="42952-112">有关使用 Windows 群集提供的高可用性的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[清单： 具有容错能力或负载平衡提供高可用性](../technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md)。</span><span class="sxs-lookup"><span data-stu-id="42952-112">For more information about using Windows Clustering to provide high availability for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Checklist: Providing High Availability with Fault Tolerance or Load Balancing](../technical-guides/checklist-providing-high-availability-with-fault-tolerance-or-load-balancing.md).</span></span>  
  
-   <span data-ttu-id="42952-113">**测试使用日志传送的 BizTalk Server 数据库的恢复。**</span><span class="sxs-lookup"><span data-stu-id="42952-113">**Test recovery of BizTalk Server databases using log shipping.**</span></span>  
  
     <span data-ttu-id="42952-114">你应验证的恢复[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库。</span><span class="sxs-lookup"><span data-stu-id="42952-114">You should verify the recovery of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases.</span></span> <span data-ttu-id="42952-115">有关使用日志传送备份和还原的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库，请参阅[什么是 BizTalk Server 日志传送？](../technical-guides/what-is-biztalk-server-log-shipping.md)本指南中或[日志传送](http://go.microsoft.com/fwlink/?LinkID=153450)(http://go.microsoft.com/fwlink/?LinkID=153450)。</span><span class="sxs-lookup"><span data-stu-id="42952-115">For more information about using log shipping to back up and restore [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] databases, see [What Is BizTalk Server Log Shipping?](../technical-guides/what-is-biztalk-server-log-shipping.md) in this guide or [Log Shipping](http://go.microsoft.com/fwlink/?LinkID=153450) (http://go.microsoft.com/fwlink/?LinkID=153450).</span></span>  
  
     <span data-ttu-id="42952-116">你应遵循的增加的可用性的步骤的清单[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境使用灾难恢复，请参阅[清单： 增加可用性与灾难恢复](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="42952-116">For a checklist of steps that you should follow to increase the availability of a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment using disaster recovery, see [Checklist: Increasing Availability with Disaster Recovery](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42952-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="42952-117">See Also</span></span>  
 [<span data-ttu-id="42952-118">BizTalk Server 用于提高可用性</span><span class="sxs-lookup"><span data-stu-id="42952-118">Increasing Availability for BizTalk Server</span></span>](../technical-guides/increasing-availability-for-biztalk-server.md)