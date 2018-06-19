---
title: BAM 事件总线服务服务器故障转移 |Microsoft 文档
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
ms.openlocfilehash: 5c1fafc3e97d9905a6efd0de8ff0f389c2a389bd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230637"
---
# <a name="bam-event-bus-service-server-failover"></a><span data-ttu-id="eda6a-102">BAM 事件总线服务服务器故障转移</span><span class="sxs-lookup"><span data-stu-id="eda6a-102">BAM Event Bus Service Server Failover</span></span>
<span data-ttu-id="eda6a-103">BAM 事件 Bus 服务包括故障容错逻辑，使它能够恢复并重新启动从意外的故障，而不会丢失任何数据。</span><span class="sxs-lookup"><span data-stu-id="eda6a-103">The BAM Event Bus service includes fault tolerance logic that enables it to recover and restart from an unexpected failure without losing any data.</span></span>  
  
 <span data-ttu-id="eda6a-104">当在多台计算机上启用 BAM 事件总线服务而服务失败时，故障转移逻辑会检测到 BAM 事件总线服务已终止，于是，该逻辑会自动在另一台计算机上启动 BAM 事件总线服务的新实例。</span><span class="sxs-lookup"><span data-stu-id="eda6a-104">When you enable the BAM Event Bus service on multiple computers, and the service fails, failover logic will detect that a BAM Event Bus service has terminated, and the logic automatically starts a new instance of the BAM Event Bus service on another computer.</span></span>  
  
 <span data-ttu-id="eda6a-105">下图显示 BAM 事件总线如何通过执行简单的负载平衡来处理计算机或网络故障。</span><span class="sxs-lookup"><span data-stu-id="eda6a-105">The following figure displays how the BAM Event Bus handles computer or network failures by performing simple load balancing.</span></span> <span data-ttu-id="eda6a-106">启动 BAM 事件总线服务之前，配置了两个源和一个目标。</span><span class="sxs-lookup"><span data-stu-id="eda6a-106">Two sources and one destination were configured before the BAM Event Bus service starts.</span></span>  
  
 ![](../core/media/ebiz-bam-admin-evntbuspoolfail.gif "ebiz_bam_admin_evntbuspoolfail")  
<span data-ttu-id="eda6a-107">BAM 事件总线服务负载平衡原理</span><span class="sxs-lookup"><span data-stu-id="eda6a-107">How the BAM Event Bus service load balances</span></span>  
  
 <span data-ttu-id="eda6a-108">BAM 事件总线服务通过执行以下操作实现负载平衡：</span><span class="sxs-lookup"><span data-stu-id="eda6a-108">The BAM Event Bus service load balances by performing the following:</span></span>  
  
-   <span data-ttu-id="eda6a-109">**答： Server1 处理 2 个源 （会话） 中的事件数据**。</span><span class="sxs-lookup"><span data-stu-id="eda6a-109">**A: Server1 processes the event data from 2 sources (sessions)**.</span></span> <span data-ttu-id="eda6a-110">在 Server2 上创建 BAM 事件总线服务的实例之前，在 Server1 上创建一个 BAM 事件总线业务流程实例。</span><span class="sxs-lookup"><span data-stu-id="eda6a-110">Before an instance of the BAM Event Bus service is created on Server2, a BAM Event Bus orchestration instance is created on Server1.</span></span> <span data-ttu-id="eda6a-111">服务器发现没有其他服务器可用，于是接管 Src1 和 Src2 两个会话。</span><span class="sxs-lookup"><span data-stu-id="eda6a-111">The server finds that there are no other servers available, and therefore picks up both sessions for Src1 and Src2.</span></span>  
  
-   <span data-ttu-id="eda6a-112">**B: Server2 进入联机状态和联接 BAM 事件总线池**。</span><span class="sxs-lookup"><span data-stu-id="eda6a-112">**B: Server2 is brought online and joins the BAM Event Bus pool**.</span></span> <span data-ttu-id="eda6a-113">在 Server2 上创建一个 BAM 事件总线服务实例后，Server1 会中断一个 BAM 事件总线服务会话，而 Server2 会接管该会话。</span><span class="sxs-lookup"><span data-stu-id="eda6a-113">After an instance of the BAM Event Bus service is created on Server2, Server1 drops one BAM Event Bus service session and Server2 picks it up.</span></span>  
  
-   <span data-ttu-id="eda6a-114">**C: Server1 失败**。</span><span class="sxs-lookup"><span data-stu-id="eda6a-114">**C: Server1 fails**.</span></span> <span data-ttu-id="eda6a-115">Server2 加入 BAM 事件总线池后，Server1 失败。</span><span class="sxs-lookup"><span data-stu-id="eda6a-115">Server1 fails after Server2 joins the BAM Event Bus pool.</span></span>  
  
-   <span data-ttu-id="eda6a-116">**D: Server2 处理 2 个源 （会话） 中的事件数据**。</span><span class="sxs-lookup"><span data-stu-id="eda6a-116">**D: Server2 processes the event data from 2 sources (sessions)**.</span></span> <span data-ttu-id="eda6a-117">Server2 接管 Src1 和 Src2 两个会话。</span><span class="sxs-lookup"><span data-stu-id="eda6a-117">Server2 picks up both sessions for Src1 and Src2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eda6a-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eda6a-118">See Also</span></span>  
 <span data-ttu-id="eda6a-119">[管理 BAM 事件总线服务](../core/managing-the-bam-event-bus-service.md) </span><span class="sxs-lookup"><span data-stu-id="eda6a-119">[Managing the BAM Event Bus Service](../core/managing-the-bam-event-bus-service.md) </span></span>  
 <span data-ttu-id="eda6a-120">[BAM 安全建议](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="eda6a-120">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="eda6a-121">业务活动监视 (BAM)</span><span class="sxs-lookup"><span data-stu-id="eda6a-121">Business Activity Monitoring (BAM)</span></span>](../core/business-activity-monitoring-bam.md)