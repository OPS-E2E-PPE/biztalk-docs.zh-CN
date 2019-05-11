---
title: BAM 事件总线服务服务器故障转移 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f12378c8-09bb-45c1-ade1-d9b20131461f
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca99e507e5f0344f7991a6e6b3c7798fb309dad4
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65530593"
---
# <a name="bam-event-bus-service-server-failover"></a><span data-ttu-id="c0da0-102">BAM 事件总线服务服务器故障转移</span><span class="sxs-lookup"><span data-stu-id="c0da0-102">BAM Event Bus Service Server Failover</span></span>
<span data-ttu-id="c0da0-103">BAM 事件总线服务包括故障容错逻辑，使它能够恢复并重新启动从意外故障而不会丢失任何数据。</span><span class="sxs-lookup"><span data-stu-id="c0da0-103">The BAM Event Bus service includes fault tolerance logic that enables it to recover and restart from an unexpected failure without losing any data.</span></span>  
  
 <span data-ttu-id="c0da0-104">如果启用多台计算机上的 BAM 事件总线服务或服务失败，故障转移逻辑将检测到 BAM 事件总线服务已终止，并将逻辑会自动在另一台计算机上启动 BAM 事件总线服务的新实例。</span><span class="sxs-lookup"><span data-stu-id="c0da0-104">When you enable the BAM Event Bus service on multiple computers, and the service fails, failover logic will detect that a BAM Event Bus service has terminated, and the logic automatically starts a new instance of the BAM Event Bus service on another computer.</span></span>  
  
 <span data-ttu-id="c0da0-105">下图显示 BAM 事件总线处理计算机的方式或通过执行简单的网络故障的负载均衡。</span><span class="sxs-lookup"><span data-stu-id="c0da0-105">The following figure displays how the BAM Event Bus handles computer or network failures by performing simple load balancing.</span></span> <span data-ttu-id="c0da0-106">BAM 事件总线服务启动之前已配置两个源和一个目标。</span><span class="sxs-lookup"><span data-stu-id="c0da0-106">Two sources and one destination were configured before the BAM Event Bus service starts.</span></span>  
  
 <span data-ttu-id="c0da0-107">![](../core/media/ebiz-bam-admin-evntbuspoolfail.gif "ebiz_bam_admin_evntbuspoolfail")</span><span class="sxs-lookup"><span data-stu-id="c0da0-107">![](../core/media/ebiz-bam-admin-evntbuspoolfail.gif "ebiz_bam_admin_evntbuspoolfail")</span></span>  
<span data-ttu-id="c0da0-108">如何实现 BAM 事件总线服务负载平衡</span><span class="sxs-lookup"><span data-stu-id="c0da0-108">How the BAM Event Bus service load balances</span></span>  
  
 <span data-ttu-id="c0da0-109">BAM 事件总线服务负载平衡通过执行以下：</span><span class="sxs-lookup"><span data-stu-id="c0da0-109">The BAM Event Bus service load balances by performing the following:</span></span>  
  
-   <span data-ttu-id="c0da0-110">**答：Server1 处理 2 个源 （会话） 的事件数据**。</span><span class="sxs-lookup"><span data-stu-id="c0da0-110">**A: Server1 processes the event data from 2 sources (sessions)**.</span></span> <span data-ttu-id="c0da0-111">在 Server2 上创建 BAM 事件总线服务的实例之前，在 Server1 上创建 BAM 事件总线业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="c0da0-111">Before an instance of the BAM Event Bus service is created on Server2, a BAM Event Bus orchestration instance is created on Server1.</span></span> <span data-ttu-id="c0da0-112">服务器发现有任何其他服务器可用，并因此接管 Src1 和 Src2 两个会话。</span><span class="sxs-lookup"><span data-stu-id="c0da0-112">The server finds that there are no other servers available, and therefore picks up both sessions for Src1 and Src2.</span></span>  
  
-   <span data-ttu-id="c0da0-113">**B:Server2 进入联机状态，并加入 BAM 事件总线池**。</span><span class="sxs-lookup"><span data-stu-id="c0da0-113">**B: Server2 is brought online and joins the BAM Event Bus pool**.</span></span> <span data-ttu-id="c0da0-114">在 Server2 上创建 BAM 事件总线服务的实例后，Server1 会中断一个 BAM 事件总线服务会话，Server2 会接管该。</span><span class="sxs-lookup"><span data-stu-id="c0da0-114">After an instance of the BAM Event Bus service is created on Server2, Server1 drops one BAM Event Bus service session and Server2 picks it up.</span></span>  
  
-   <span data-ttu-id="c0da0-115">**C:Server1 失败**。</span><span class="sxs-lookup"><span data-stu-id="c0da0-115">**C: Server1 fails**.</span></span> <span data-ttu-id="c0da0-116">Server2 加入 BAM 事件总线池后，Server1 失败。</span><span class="sxs-lookup"><span data-stu-id="c0da0-116">Server1 fails after Server2 joins the BAM Event Bus pool.</span></span>  
  
-   <span data-ttu-id="c0da0-117">**D:Server2 处理 2 个源 （会话） 的事件数据**。</span><span class="sxs-lookup"><span data-stu-id="c0da0-117">**D: Server2 processes the event data from 2 sources (sessions)**.</span></span> <span data-ttu-id="c0da0-118">Server2 接管 Src1 和 Src2 提取这两个会话。</span><span class="sxs-lookup"><span data-stu-id="c0da0-118">Server2 picks up both sessions for Src1 and Src2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0da0-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="c0da0-119">See Also</span></span>  
 <span data-ttu-id="c0da0-120">[管理 BAM 事件总线服务](../core/managing-the-bam-event-bus-service.md) </span><span class="sxs-lookup"><span data-stu-id="c0da0-120">[Managing the BAM Event Bus Service](../core/managing-the-bam-event-bus-service.md) </span></span>  
 <span data-ttu-id="c0da0-121">[BAM 安全建议](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="c0da0-121">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="c0da0-122">业务活动监视 (BAM)</span><span class="sxs-lookup"><span data-stu-id="c0da0-122">Business Activity Monitoring (BAM)</span></span>](../core/business-activity-monitoring-bam.md)