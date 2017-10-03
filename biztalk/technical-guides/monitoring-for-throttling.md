---
title: "监视限制 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3d1d4c72-6942-4572-b27f-c58d37c94062
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d60b9f3deb77df927eb055b4504b809b421ae663
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="monitoring-for-throttling"></a><span data-ttu-id="974bd-102">监视的限制</span><span class="sxs-lookup"><span data-stu-id="974bd-102">Monitoring for Throttling</span></span>
<span data-ttu-id="974bd-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理包监视性能计数器指示限制状态的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="974bd-103">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] management pack monitors performance counters that indicate the throttling state of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="974bd-104">下面列出了几个关键因素了解限制。</span><span class="sxs-lookup"><span data-stu-id="974bd-104">Some key factors to understand about throttling are listed below.</span></span>  
  
-   <span data-ttu-id="974bd-105">基于速率限制是每个主机和基于消息的速率入站和出站消息。</span><span class="sxs-lookup"><span data-stu-id="974bd-105">Rate-based throttling is per host and is based on the rate of messages inbound vs. outbound messages.</span></span>  
  
-   <span data-ttu-id="974bd-106">传递限制 (**MsgBox-> 发送端口或业务流程**)，入站的速率是从消息框中接收消息的速率。</span><span class="sxs-lookup"><span data-stu-id="974bd-106">For delivery throttling (**MsgBox -> Send Port or Orchestration**), inbound rate is the rate at which messages are received from the message box.</span></span> <span data-ttu-id="974bd-107">出站率是从该处消息成功传递通过适配器的速率。</span><span class="sxs-lookup"><span data-stu-id="974bd-107">Outbound rate is the rate at which messages are successfully delivered via the adapters.</span></span>  
  
-   <span data-ttu-id="974bd-108">发布限制 (**接收适配器**或**业务流程-> MsgBox)，**入站的速率是从适配器接收消息的速率和出站率是速率消息插入到 MsgBox。</span><span class="sxs-lookup"><span data-stu-id="974bd-108">For publishing throttling (**Receive adapters** or **Orchestrations -> MsgBox),** inbound rate is the rate at which messages are received from the adapters and outbound rate is the rate messages are plugged into the MsgBox.</span></span>  
  
-   <span data-ttu-id="974bd-109">非数据库中的总消息的主机之间不存在任何限制的机制。</span><span class="sxs-lookup"><span data-stu-id="974bd-109">No throttling mechanism exists between hosts other than total messages in the database.</span></span>  
  
 <span data-ttu-id="974bd-110">有关其他背景信息，请参阅主题[如何 BizTalk Server 实现主机限制](http://go.microsoft.com/fwlink/?LinkID=155286)(http://go.microsoft.com/fwlink/?LinkID=155286) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="974bd-110">For additional background information, refer to the topic [How BizTalk Server Implements Host Throttling](http://go.microsoft.com/fwlink/?LinkID=155286) (http://go.microsoft.com/fwlink/?LinkID=155286) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="974bd-111">包含自限制，这有助于防止服务器基于各种参数的重载。</span><span class="sxs-lookup"><span data-stu-id="974bd-111"> incorporates self-throttling, which helps to prevent overloading of the server based on various parameters.</span></span> <span data-ttu-id="974bd-112">从操作方面而言，由临时重载引发的阻止并不是严重问题。</span><span class="sxs-lookup"><span data-stu-id="974bd-112">A temporary overload that causes throttling to occur is not an operationally significant event.</span></span> <span data-ttu-id="974bd-113">不过，在稳定的环境中不应发生持久性阻止，它说明在基础结构级可能出现问题。</span><span class="sxs-lookup"><span data-stu-id="974bd-113">Persistent throttling, however, is not expected in a stable environment and could indicate underlying problems at the infrastructure level.</span></span> <span data-ttu-id="974bd-114">管理包可使用性能阈值规则对此类持久性阻止条件进行主动监视。</span><span class="sxs-lookup"><span data-stu-id="974bd-114">The management pack provides proactive monitoring of such persistent throttling conditions with performance threshold rules.</span></span>  
  
 <span data-ttu-id="974bd-115">四个规则的监视器的使用率/性能跟踪长时间内限制由四个不同的条件，按下表中所示。</span><span class="sxs-lookup"><span data-stu-id="974bd-115">Four utilization/performance tracking rules monitor for extended periods of throttling caused by four different conditions as indicated in the following table.</span></span>  
  
|<span data-ttu-id="974bd-116">条件</span><span class="sxs-lookup"><span data-stu-id="974bd-116">Condition</span></span>|<span data-ttu-id="974bd-117">规则</span><span class="sxs-lookup"><span data-stu-id="974bd-117">Rule</span></span>|  
|---------------|----------|  
|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="974bd-118">服务进程内存</span><span class="sxs-lookup"><span data-stu-id="974bd-118"> service process memory</span></span>|<span data-ttu-id="974bd-119">警告： BizTalk Throttled 上经过很长的高进程内存</span><span class="sxs-lookup"><span data-stu-id="974bd-119">Warning: BizTalk Throttled on High Process Memory for a significant period</span></span>|  
|<span data-ttu-id="974bd-120">正在处理的消息数</span><span class="sxs-lookup"><span data-stu-id="974bd-120">Number of messages being processed</span></span>|<span data-ttu-id="974bd-121">警告： BizTalk Throttled 上高进程内消息计数经过很长</span><span class="sxs-lookup"><span data-stu-id="974bd-121">Warning: BizTalk Throttled on High Inprocess Message Count for a significant period</span></span>|  
|<span data-ttu-id="974bd-122">中的线程数[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]过程</span><span class="sxs-lookup"><span data-stu-id="974bd-122">Number of threads in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] process</span></span>|<span data-ttu-id="974bd-123">Warning: BizTalk Throttled on High Thread Count for a significant period（警告：由于线程数过多导致 BizTalk 长时间被阻止）</span><span class="sxs-lookup"><span data-stu-id="974bd-123">Warning: BizTalk Throttled on High Thread Count for a significant period</span></span>|  
|<span data-ttu-id="974bd-124">大小[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库队列</span><span class="sxs-lookup"><span data-stu-id="974bd-124">Size of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] database queues</span></span>|<span data-ttu-id="974bd-125">Warning: BizTalk Throttled on High Database Size for a significant period（警告：由于数据库较大导致 BizTalk 长时间被阻止）</span><span class="sxs-lookup"><span data-stu-id="974bd-125">Warning: BizTalk Throttled on High Database Size for a significant period</span></span>|  
  
 <span data-ttu-id="974bd-126">这些阈值规则使用基于限制状态指示器性能计数器的数据提供程序。</span><span class="sxs-lookup"><span data-stu-id="974bd-126">These threshold rules use data providers based on throttling state indicator performance counters.</span></span> <span data-ttu-id="974bd-127">有关这些性能计数器的详细信息，请参阅部分[性能计数器](http://go.microsoft.com/fwlink/?LinkId=157269)(http://go.microsoft.com/fwlink/?LinkId=157269) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="974bd-127">For more information about these performance counters, refer to the section [Performance Counters](http://go.microsoft.com/fwlink/?LinkId=157269) (http://go.microsoft.com/fwlink/?LinkId=157269) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
 <span data-ttu-id="974bd-128">这些规则被配置为一定数量的样本的平均值超过特定阈值时引发警报 （默认值为 30）。</span><span class="sxs-lookup"><span data-stu-id="974bd-128">These rules are configured to raise an alert if the average of over a certain number of samples crosses a particular threshold (default is 30).</span></span> <span data-ttu-id="974bd-129">例如，"警告： 上经过很长的高数据库大小的 BizTalk Throttled"是一种规则监视的所有限制状态[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]给定计算机中的进程。</span><span class="sxs-lookup"><span data-stu-id="974bd-129">For example, “Warning: BizTalk Throttled on High Database Size for a significant period” is a rule monitoring the throttling state of all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] processes in a given computer.</span></span> <span data-ttu-id="974bd-130">此规则使用数据提供程序基于限制状态指示器性能计数器"BizTalk:Message 代理-高数据库大小。"</span><span class="sxs-lookup"><span data-stu-id="974bd-130">This rule uses a data provider based on the throttling state indicator performance counter “BizTalk:Message Agent-High database size.”</span></span> <span data-ttu-id="974bd-131">如果此性能计数器的值为 1，则相关进程将由于数据库规模过大而被阻止。</span><span class="sxs-lookup"><span data-stu-id="974bd-131">If this performance counter value is 1, then the associated process is throttling because of high database size.</span></span>  
  
 <span data-ttu-id="974bd-132">前面的规则配置为需要 30 样本的平均值和样本的平均值大于 0.6 时引发警报。</span><span class="sxs-lookup"><span data-stu-id="974bd-132">The preceding rule is configured to take an average of 30 samples and raise an alert if the average of the samples is more than 0.6.</span></span> <span data-ttu-id="974bd-133">由于每个示例均为一分钟的时间间隔，这意味着在过去 30 分钟内，，该计算机中的至少一个或多个 BizTalk 服务器进程已由于高数据库大小、 60%的时间限制。</span><span class="sxs-lookup"><span data-stu-id="974bd-133">Since each sample is taken at an interval of one minute, this implies that over the past 30 minutes, at least one or more BizTalk Server processes in that computer were throttling because of high database size, 60 percent of the time.</span></span>  
  
 <span data-ttu-id="974bd-134">此试探性方法可能不适用于您的特定应用程序方案。</span><span class="sxs-lookup"><span data-stu-id="974bd-134">This heuristic may not suit your particular application scenario.</span></span> <span data-ttu-id="974bd-135">根据你的环境中的历史行为，如之前所述，你应配置这些规则使用正确的值通过以下任一方法：</span><span class="sxs-lookup"><span data-stu-id="974bd-135">Based on the historical behavior in your environment as described before, you should configure these rules with the correct values by either:</span></span>  
  
-   <span data-ttu-id="974bd-136">调整这些示例。</span><span class="sxs-lookup"><span data-stu-id="974bd-136">Adjusting the samples.</span></span>  
  
-   <span data-ttu-id="974bd-137">调整阈值的值。</span><span class="sxs-lookup"><span data-stu-id="974bd-137">Adjusting the threshold value.</span></span>  
  
-   <span data-ttu-id="974bd-138">如有必要，修改提供程序的采样的间隔。</span><span class="sxs-lookup"><span data-stu-id="974bd-138">If necessary, modifying the interval of sampling for the provider.</span></span>