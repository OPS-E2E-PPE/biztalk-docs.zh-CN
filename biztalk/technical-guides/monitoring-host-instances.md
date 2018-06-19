---
title: 监视主机实例 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4e7c6b80-7371-46ea-bf9c-82acb22012a3
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b41dd0e01aa1e28862a3e99cfc767b3dd6ddec3c
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26008590"
---
# <a name="monitoring-host-instances"></a><span data-ttu-id="bffb7-102">监视主机实例</span><span class="sxs-lookup"><span data-stu-id="bffb7-102">Monitoring Host Instances</span></span>
<span data-ttu-id="bffb7-103">本主题介绍使用 Microsoft System Center Operations Manager 的监视 BizTalk 主机实例。</span><span class="sxs-lookup"><span data-stu-id="bffb7-103">This topic describes monitoring BizTalk host instances using Microsoft System Center Operations Manager.</span></span>  
  
## <a name="using-threshold-rules-to-monitor-health"></a><span data-ttu-id="bffb7-104">使用阈值规则来监视运行状况</span><span class="sxs-lookup"><span data-stu-id="bffb7-104">Using Threshold Rules to Monitor Health</span></span>  
 <span data-ttu-id="bffb7-105">BizTalk Server 管理包包含提供 BizTalk 主机的运行状况的综合视图的性能阈值规则。</span><span class="sxs-lookup"><span data-stu-id="bffb7-105">The BizTalk Server Management Pack incorporates performance threshold rules that provide a comprehensive view of the health of the BizTalk hosts.</span></span> <span data-ttu-id="bffb7-106">提供以下两种不同类型的阈值规则：</span><span class="sxs-lookup"><span data-stu-id="bffb7-106">Two different types of threshold rules are provided:</span></span>  
  
-   <span data-ttu-id="bffb7-107">一般情况下 （例如，对所有 BizTalk 主机和所有 MessageBox 数据库） 应用的规则。</span><span class="sxs-lookup"><span data-stu-id="bffb7-107">Rules that apply generically (for example, to all BizTalk hosts and to all MessageBox databases).</span></span>  
  
-   <span data-ttu-id="bffb7-108">特定于特定的 BizTalk 主机的规则。</span><span class="sxs-lookup"><span data-stu-id="bffb7-108">Rules that are specific to a particular BizTalk host.</span></span>  
  
 <span data-ttu-id="bffb7-109">泛型规则监视基于常见阈值的所有 BizTalk 主机。</span><span class="sxs-lookup"><span data-stu-id="bffb7-109">Generic rules monitor all the BizTalk hosts based on a common threshold.</span></span> <span data-ttu-id="bffb7-110">例如，规则监视器 HostQ 大小监视基于常见阈值的所有 BizTalk 主机的工作队列。</span><span class="sxs-lookup"><span data-stu-id="bffb7-110">For example, the rule Monitor HostQ Size monitors the work queues of all BizTalk hosts based on a common threshold.</span></span> <span data-ttu-id="bffb7-111">如果有三个不同的主机，其所有工作队列都监视由相同规则，并在任何主机工作队列跨常见阈值时发生警报。</span><span class="sxs-lookup"><span data-stu-id="bffb7-111">If there are three different hosts, all their work queues are monitored by the same rule, and alerts occur when any of the host work queues cross the common threshold.</span></span>  
  
 <span data-ttu-id="bffb7-112">BizTalk 特定于宿主的规则，可以为不同的主机配置不同的阈值。</span><span class="sxs-lookup"><span data-stu-id="bffb7-112">BizTalk host-specific rules enable you to configure different thresholds for different hosts.</span></span> <span data-ttu-id="bffb7-113">例如，规则监视器 HostQ 大小 – BizTalkServerApplication 是特定于宿主的监视的规则，BizTalkServerApplication 主机的工作队列。</span><span class="sxs-lookup"><span data-stu-id="bffb7-113">For example, the rule Monitor HostQ Size – BizTalkServerApplication is a host-specific rule that monitors the work queue of the BizTalkServerApplication host.</span></span> <span data-ttu-id="bffb7-114">在此示例中可以定义的特定的 Operations Manager 提供程序特定的性能计数器实例，并在阈值规则中使用该提供程序。</span><span class="sxs-lookup"><span data-stu-id="bffb7-114">In this example you can define a specific Operations Manager provider for the particular performance counter instance and use that provider in the threshold rule.</span></span> <span data-ttu-id="bffb7-115">由于这些规则是特定于宿主的你必须对每个新创建的主机定义特定的规则。</span><span class="sxs-lookup"><span data-stu-id="bffb7-115">Because these rules are host-specific, you must define rules specific to each newly created host.</span></span>  
  
 <span data-ttu-id="bffb7-116">BizTalk 特定于宿主的规则被提供用于创建规则的模板规则是适用于你的环境。</span><span class="sxs-lookup"><span data-stu-id="bffb7-116">BizTalk host-specific rules are provided as template rules for creating rules that are applicable in your environment.</span></span> <span data-ttu-id="bffb7-117">默认情况下，所有阈值监视规则都被禁用：</span><span class="sxs-lookup"><span data-stu-id="bffb7-117">All threshold monitoring rules are disabled by default:</span></span>  
  
-   <span data-ttu-id="bffb7-118">到你的环境，应使用特定的阈值配置一般规则。</span><span class="sxs-lookup"><span data-stu-id="bffb7-118">You should configure generic rules with threshold values specific to your environment.</span></span>  
  
-   <span data-ttu-id="bffb7-119">你应创建基于模板规则和适当的阈值的 BizTalk 特定于宿主的规则。</span><span class="sxs-lookup"><span data-stu-id="bffb7-119">You should create BizTalk host-specific rules based on the template rules and appropriate thresholds.</span></span>  
  
## <a name="monitoring-biztalk-host-instances"></a><span data-ttu-id="bffb7-120">监视 BizTalk 主机实例</span><span class="sxs-lookup"><span data-stu-id="bffb7-120">Monitoring BizTalk Host Instances</span></span>  
 <span data-ttu-id="bffb7-121">面向特定的 BizTalk 主机的规则是从监视角度来看更灵活。</span><span class="sxs-lookup"><span data-stu-id="bffb7-121">Rules that target specific BizTalk hosts are more flexible from a monitoring perspective.</span></span> <span data-ttu-id="bffb7-122">BizTalkServerApplication 主机 BizTalk Server 管理包中提供的所有阈值监视规则都是模板规则。</span><span class="sxs-lookup"><span data-stu-id="bffb7-122">All threshold monitoring rules for the BizTalkServerApplication host provided in the BizTalk Server Management pack are template rules.</span></span> <span data-ttu-id="bffb7-123">若要使用这些规则，应使用 Operations Manager 管理员控制台：</span><span class="sxs-lookup"><span data-stu-id="bffb7-123">In order to use these rules, you should use the Operations Manager Administrator console to:</span></span>  
  
-   <span data-ttu-id="bffb7-124">创建一份中的模板规则[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]规则组并将其重命名。</span><span class="sxs-lookup"><span data-stu-id="bffb7-124">Create a copy of the template rule in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] rule group and rename it.</span></span>  
  
-   <span data-ttu-id="bffb7-125">创建新 BizTalk 特定于宿主的性能计数器实例的 Operations Manager 提供程序。</span><span class="sxs-lookup"><span data-stu-id="bffb7-125">Create a new Operations Manager provider for the BizTalk host-specific performance counter instance.</span></span>  
  
-   <span data-ttu-id="bffb7-126">修改使用该规则的 Operations Manager 提供程序，并使其指向新。</span><span class="sxs-lookup"><span data-stu-id="bffb7-126">Modify the Operations Manager provider used by the rule and point it to the new one.</span></span>  
  
 <span data-ttu-id="bffb7-127">假设你[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装有 BizTalk 主机 ReceiveHost 并且你想要监视此主机的主机队列大小。</span><span class="sxs-lookup"><span data-stu-id="bffb7-127">Suppose your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation has a BizTalk host ReceiveHost and you want to monitor the Host Queue size for this host.</span></span> <span data-ttu-id="bffb7-128">在这种情况下，应创建 Operations Manager 提供程序基于队列大小的性能计数器的 ReceiveHost 实例上的 BizTalk 主机。</span><span class="sxs-lookup"><span data-stu-id="bffb7-128">In this case, you should create a Operations Manager provider based on the ReceiveHost instance of the performance counter for the queue size for the BizTalk host.</span></span> <span data-ttu-id="bffb7-129">您还应设置适合您环境的规则阈值。</span><span class="sxs-lookup"><span data-stu-id="bffb7-129">You should also set the threshold value in the rule appropriately for your environment.</span></span>  
  
 <span data-ttu-id="bffb7-130">如果你使用的特定于宿主的阈值监视规则，则应禁用泛型的监视规则。</span><span class="sxs-lookup"><span data-stu-id="bffb7-130">If you are using host-specific threshold monitoring rules, you should disable generic monitoring rules.</span></span> <span data-ttu-id="bffb7-131">这可阻止多余警报。</span><span class="sxs-lookup"><span data-stu-id="bffb7-131">This prevents redundant alerts.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bffb7-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bffb7-132">See Also</span></span>  
 [<span data-ttu-id="bffb7-133">使用 System Center Operations Manager 2007 监视 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="bffb7-133">Monitoring BizTalk Server with System Center Operations Manager 2007</span></span>](../technical-guides/monitoring-biztalk-server-with-system-center-operations-manager-2007.md)