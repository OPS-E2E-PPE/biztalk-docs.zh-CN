---
title: 监视带宽限制 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3d1d4c72-6942-4572-b27f-c58d37c94062
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c175c2668a3d2f8bdf0d4088d51bfd76d43ca8d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65305541"
---
# <a name="monitoring-for-throttling"></a><span data-ttu-id="0b631-102">监视带宽限制</span><span class="sxs-lookup"><span data-stu-id="0b631-102">Monitoring for Throttling</span></span>
<span data-ttu-id="0b631-103">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理包监视性能计数器指示的阻止状态[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="0b631-103">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] management pack monitors performance counters that indicate the throttling state of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="0b631-104">下面列出了关于限制需要了解一些关键因素。</span><span class="sxs-lookup"><span data-stu-id="0b631-104">Some key factors to understand about throttling are listed below.</span></span>  
  
- <span data-ttu-id="0b631-105">基于速率的限制是每个主机和基于消息的速率入站和出站消息。</span><span class="sxs-lookup"><span data-stu-id="0b631-105">Rate-based throttling is per host and is based on the rate of messages inbound vs. outbound messages.</span></span>  
  
- <span data-ttu-id="0b631-106">有关送达阻止功能 (**MsgBox-> 发送端口或业务流程**)，入站的率是从消息框中接收消息的速率。</span><span class="sxs-lookup"><span data-stu-id="0b631-106">For delivery throttling (**MsgBox -> Send Port or Orchestration**), inbound rate is the rate at which messages are received from the message box.</span></span> <span data-ttu-id="0b631-107">出站速率是在该消息成功传递通过适配器的速率。</span><span class="sxs-lookup"><span data-stu-id="0b631-107">Outbound rate is the rate at which messages are successfully delivered via the adapters.</span></span>  
  
- <span data-ttu-id="0b631-108">为发布阻止功能 (**接收适配器**或**业务流程-> MsgBox)，** 入站的率是从适配器接收消息的速率，出站速率速率消息插入到 MsgBox。</span><span class="sxs-lookup"><span data-stu-id="0b631-108">For publishing throttling (**Receive adapters** or **Orchestrations -> MsgBox),** inbound rate is the rate at which messages are received from the adapters and outbound rate is the rate messages are plugged into the MsgBox.</span></span>  
  
- <span data-ttu-id="0b631-109">数据库中的总消息以外的主机之间不存在任何阻止机制。</span><span class="sxs-lookup"><span data-stu-id="0b631-109">No throttling mechanism exists between hosts other than total messages in the database.</span></span>  
  
  <span data-ttu-id="0b631-110">有关更多背景信息，请参阅主题[如何 BizTalk Server 实现主机阻止](http://go.microsoft.com/fwlink/?LinkID=155286)(<http://go.microsoft.com/fwlink/?LinkID=155286>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="0b631-110">For additional background information, refer to the topic [How BizTalk Server Implements Host Throttling](http://go.microsoft.com/fwlink/?LinkID=155286) (<http://go.microsoft.com/fwlink/?LinkID=155286>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="0b631-111">集成了自阻止功能，这有助于防止服务器基于各种参数的重载。</span><span class="sxs-lookup"><span data-stu-id="0b631-111">incorporates self-throttling, which helps to prevent overloading of the server based on various parameters.</span></span> <span data-ttu-id="0b631-112">由临时重载引发的阻止不是严重问题。</span><span class="sxs-lookup"><span data-stu-id="0b631-112">A temporary overload that causes throttling to occur is not an operationally significant event.</span></span> <span data-ttu-id="0b631-113">持久性阻止，但是，不应出现在稳定的环境，可能表示底层基础结构级别的问题。</span><span class="sxs-lookup"><span data-stu-id="0b631-113">Persistent throttling, however, is not expected in a stable environment and could indicate underlying problems at the infrastructure level.</span></span> <span data-ttu-id="0b631-114">管理包提供了性能阈值规则与此类持久性阻止条件进行主动监视。</span><span class="sxs-lookup"><span data-stu-id="0b631-114">The management pack provides proactive monitoring of such persistent throttling conditions with performance threshold rules.</span></span>  
  
  <span data-ttu-id="0b631-115">四个使用率/性能跟踪规则监视的扩展限制下表中所示，由四个不同的条件导致的时间段。</span><span class="sxs-lookup"><span data-stu-id="0b631-115">Four utilization/performance tracking rules monitor for extended periods of throttling caused by four different conditions as indicated in the following table.</span></span>  
  
|                                                     <span data-ttu-id="0b631-116">条件</span><span class="sxs-lookup"><span data-stu-id="0b631-116">Condition</span></span>                                                     |                                        <span data-ttu-id="0b631-117">规则</span><span class="sxs-lookup"><span data-stu-id="0b631-117">Rule</span></span>                                         |
|-------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------|
|     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="0b631-118">服务进程内存</span><span class="sxs-lookup"><span data-stu-id="0b631-118">service process memory</span></span>     |     <span data-ttu-id="0b631-119">警告：BizTalk 上长时间的高进程内存限制</span><span class="sxs-lookup"><span data-stu-id="0b631-119">Warning: BizTalk Throttled on High Process Memory for a significant period</span></span>      |
|                                        <span data-ttu-id="0b631-120">正在处理的消息数</span><span class="sxs-lookup"><span data-stu-id="0b631-120">Number of messages being processed</span></span>                                         | <span data-ttu-id="0b631-121">警告：BizTalk 限制上高进程内消息计数相当长一段</span><span class="sxs-lookup"><span data-stu-id="0b631-121">Warning: BizTalk Throttled on High Inprocess Message Count for a significant period</span></span> |
| <span data-ttu-id="0b631-122">中的线程数[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]过程</span><span class="sxs-lookup"><span data-stu-id="0b631-122">Number of threads in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] process</span></span> |      <span data-ttu-id="0b631-123">警告：BizTalk 限制在相当长一段的高的线程计数</span><span class="sxs-lookup"><span data-stu-id="0b631-123">Warning: BizTalk Throttled on High Thread Count for a significant period</span></span>       |
|  <span data-ttu-id="0b631-124">大小[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]数据库队列</span><span class="sxs-lookup"><span data-stu-id="0b631-124">Size of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] database queues</span></span>   |      <span data-ttu-id="0b631-125">警告：BizTalk 在相当长一段高数据库大小限制</span><span class="sxs-lookup"><span data-stu-id="0b631-125">Warning: BizTalk Throttled on High Database Size for a significant period</span></span>      |
  
 <span data-ttu-id="0b631-126">这些阈值规则使用基于阻止状态指示器性能计数器的数据提供程序。</span><span class="sxs-lookup"><span data-stu-id="0b631-126">These threshold rules use data providers based on throttling state indicator performance counters.</span></span> <span data-ttu-id="0b631-127">有关这些性能计数器的详细信息，请参阅部分[性能计数器](http://go.microsoft.com/fwlink/?LinkId=157269)(<http://go.microsoft.com/fwlink/?LinkId=157269>) 中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="0b631-127">For more information about these performance counters, refer to the section [Performance Counters](http://go.microsoft.com/fwlink/?LinkId=157269) (<http://go.microsoft.com/fwlink/?LinkId=157269>) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
 <span data-ttu-id="0b631-128">这些规则配置为超过某个数目的样本的平均值超出特定阈值时引发警报 （默认值为 30）。</span><span class="sxs-lookup"><span data-stu-id="0b631-128">These rules are configured to raise an alert if the average of over a certain number of samples crosses a particular threshold (default is 30).</span></span> <span data-ttu-id="0b631-129">例如，"警告：BizTalk 受到限制高数据库大小进行相当长一段"是规则用来监视所有的阻止状态[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]给定计算机中的进程。</span><span class="sxs-lookup"><span data-stu-id="0b631-129">For example, “Warning: BizTalk Throttled on High Database Size for a significant period” is a rule monitoring the throttling state of all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] processes in a given computer.</span></span> <span data-ttu-id="0b631-130">该规则使用基于阻止状态指示器性能计数器"Agent-high 数据库大小。"的数据提供程序</span><span class="sxs-lookup"><span data-stu-id="0b631-130">This rule uses a data provider based on the throttling state indicator performance counter “BizTalk:Message Agent-High database size.”</span></span> <span data-ttu-id="0b631-131">如果此性能计数器的值为 1，然后由于数据库规模过大而阻止关联的进程。</span><span class="sxs-lookup"><span data-stu-id="0b631-131">If this performance counter value is 1, then the associated process is throttling because of high database size.</span></span>  
  
 <span data-ttu-id="0b631-132">前面的规则配置为需要 30 个样本的平均并发出警报，如果样本的平均值超过 0.6。</span><span class="sxs-lookup"><span data-stu-id="0b631-132">The preceding rule is configured to take an average of 30 samples and raise an alert if the average of the samples is more than 0.6.</span></span> <span data-ttu-id="0b631-133">由于每个采样的时间间隔为一分钟，这意味着在过去的 30 分钟，该计算机中的至少一个或多个 BizTalk Server 进程已由于数据库规模过大，60%的时间限制。</span><span class="sxs-lookup"><span data-stu-id="0b631-133">Since each sample is taken at an interval of one minute, this implies that over the past 30 minutes, at least one or more BizTalk Server processes in that computer were throttling because of high database size, 60 percent of the time.</span></span>  
  
 <span data-ttu-id="0b631-134">此启发式方法可能并不适合特定应用程序方案。</span><span class="sxs-lookup"><span data-stu-id="0b631-134">This heuristic may not suit your particular application scenario.</span></span> <span data-ttu-id="0b631-135">根据您的环境中的历史行为，如之前所述，应配置正确的值与这些规则通过以下任一方法：</span><span class="sxs-lookup"><span data-stu-id="0b631-135">Based on the historical behavior in your environment as described before, you should configure these rules with the correct values by either:</span></span>  
  
-   <span data-ttu-id="0b631-136">调整这些示例。</span><span class="sxs-lookup"><span data-stu-id="0b631-136">Adjusting the samples.</span></span>  
  
-   <span data-ttu-id="0b631-137">调整阈值的值。</span><span class="sxs-lookup"><span data-stu-id="0b631-137">Adjusting the threshold value.</span></span>  
  
-   <span data-ttu-id="0b631-138">如有必要，修改的提供程序的采样时间间隔。</span><span class="sxs-lookup"><span data-stu-id="0b631-138">If necessary, modifying the interval of sampling for the provider.</span></span>