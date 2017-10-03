---
title: "如何避免限制关联消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bfe47747-01e7-4e2f-bbd5-d5055cea001a
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10cfcf0009cac5a72d71190c1b974ca6d01a2e1e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-avoid-throttling-correlated-messages"></a><span data-ttu-id="eb5c9-102">如何避免阻止相关消息</span><span class="sxs-lookup"><span data-stu-id="eb5c9-102">How to Avoid Throttling Correlated Messages</span></span>
<span data-ttu-id="eb5c9-103">在 BizTalk Server 中排队的消息（例如，通过接收位置或通过业务流程）可以通过以下方式之一进行处理：</span><span class="sxs-lookup"><span data-stu-id="eb5c9-103">Messages that are en-queued into BizTalk Server, for example through a receive location or by orchestrations, can be processed in one of the following ways:</span></span>  
  
-   <span data-ttu-id="eb5c9-104">它们可以激活订户的新实例（即，业务流程或发送端口）</span><span class="sxs-lookup"><span data-stu-id="eb5c9-104">They can activate new instances of subscribers (that is, orchestrations or send ports)</span></span>  
  
-   <span data-ttu-id="eb5c9-105">它们可以通过相关路由到现有订户实例。</span><span class="sxs-lookup"><span data-stu-id="eb5c9-105">They can be routed to an existing subscriber instance via correlation.</span></span> <span data-ttu-id="eb5c9-106">有关相关的详细信息，请参阅[在业务流程中使用相关性](../core/using-correlations-in-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="eb5c9-106">For more information about correlation, see [Using Correlations in Orchestrations](../core/using-correlations-in-orchestrations.md).</span></span>  
  
 <span data-ttu-id="eb5c9-107">许多开发人员都考虑使用某一解决方案的接收位置来通过同一端口同时接收该解决方案的激活和相关消息。</span><span class="sxs-lookup"><span data-stu-id="eb5c9-107">A lot of developers think about the receive locations for a solution as receiving both activation and correlated messages for the solution through the same port.</span></span> <span data-ttu-id="eb5c9-108">这种想法很自然，因为这可以大幅减少消息发送方需要跟踪的地址数目。</span><span class="sxs-lookup"><span data-stu-id="eb5c9-108">This is natural as it minimizes the number of addresses that message senders need to keep track of.</span></span> <span data-ttu-id="eb5c9-109">但是，使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中的阻止，可能有利于在发生阻止时单独处理激活消息流和相关消息流。</span><span class="sxs-lookup"><span data-stu-id="eb5c9-109">However, with throttling in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], there can be advantages to thinking about the stream of activation messages and the stream of correlated messages separately when it comes to throttling.</span></span>  
  
 <span data-ttu-id="eb5c9-110">在激活消息和相关消息通过相同接收位置到达时，它们会处于同一阻止状态，因为在主机级别应用阻止。</span><span class="sxs-lookup"><span data-stu-id="eb5c9-110">When both activation and correlation messages arrive through the same receive location, they are subject to the same throttling state because throttling is applied at the host level.</span></span> <span data-ttu-id="eb5c9-111">因此，到达主机中的接收位置的所有消息都将作为一个单位被阻止。</span><span class="sxs-lookup"><span data-stu-id="eb5c9-111">As a result, all messages arriving at receive locations in the host will be throttled as a unit.</span></span> <span data-ttu-id="eb5c9-112">在许多情况下这都不会导致问题，但是，可能存在将相关与激活一起阻止而导致某种类型的系统死锁的情况。</span><span class="sxs-lookup"><span data-stu-id="eb5c9-112">This is not an issue for many scenarios, but there are cases where throttling correlations with activations can result in a type of system deadlock.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb5c9-113">示例</span><span class="sxs-lookup"><span data-stu-id="eb5c9-113">Example</span></span>  
 <span data-ttu-id="eb5c9-114">例如，假设您的方案包含一个业务流程，该业务流程接收一个激活并且使用该激活来初始化某一相关集，然后接收跟随在该相关集后的由另外 10 个消息构成的一组消息。</span><span class="sxs-lookup"><span data-stu-id="eb5c9-114">For example, let's assume you have a scenario containing an orchestration that receives one activation, uses it to initialize a correlation set, then receives a convoy of 10 additional messages that follow the correlation set.</span></span> <span data-ttu-id="eb5c9-115">此外，假定在负载下，随着激活消息和相关消息混杂在一起到达，在后台处理中开始出现积压，从而导致阻止本来可被接收的消息量。</span><span class="sxs-lookup"><span data-stu-id="eb5c9-115">In addition, assume that, under load, a backlog builds up in the spool as the mix of activation and correlation messages arrive that results in throttling the amount of messages that can be received.</span></span> <span data-ttu-id="eb5c9-116">不利的是，相关消息随激活一起被阻止，这将减慢业务流程的完成速度，导致进一步的积压和额外的阻止。</span><span class="sxs-lookup"><span data-stu-id="eb5c9-116">Unfortunately, the correlation messages are throttled along with the activations, which slows down the completion of orchestrations, causing further backlog and additional throttling.</span></span> <span data-ttu-id="eb5c9-117">再进一步，这可能导致系统的吞吐量下降到接近零。</span><span class="sxs-lookup"><span data-stu-id="eb5c9-117">Allowed to continue, this would result in throttling the system down to near zero throughput.</span></span>  
  
 <span data-ttu-id="eb5c9-118">如果将单个接收位置拆分为两个（一个用于激活，一个用于相关）并且将两个位置配置于不同的主机中，则激活的数据库大小阻止阈值可以保持在低于相关的阻止阈值的水平，这将导致降低整体积压量，并保持消息顺畅流动。</span><span class="sxs-lookup"><span data-stu-id="eb5c9-118">By splitting the single receive location into two -- one for activations and one for correlations -- and configuring the locations in separate hosts, the database size throttling threshold for the activations can be kept lower than that for correlations, which will result in reduced backlog overall, and keep the messages flowing.</span></span>  
  
 <span data-ttu-id="eb5c9-119">因此，您可能会问:"为什么无法我只引发数据库大小阈值为我单接收位置来解决该问题？"</span><span class="sxs-lookup"><span data-stu-id="eb5c9-119">So, you might be asking: "why can’t I just raise the database size threshold for my single receive location to fix the problem?"</span></span> <span data-ttu-id="eb5c9-120">回答是，您可以，但这样做不见得始终可以导致预期行为。</span><span class="sxs-lookup"><span data-stu-id="eb5c9-120">The answer is, you can, but it won’t always result in the desired behavior.</span></span> <span data-ttu-id="eb5c9-121">阻止在系统中主要用于保护系统以免过载。</span><span class="sxs-lookup"><span data-stu-id="eb5c9-121">Throttling is there primarily to protect the system from becoming overloaded.</span></span> <span data-ttu-id="eb5c9-122">如果您将阈值增加得过高，或者将它们全都禁用，就将消除上述保护作用。</span><span class="sxs-lookup"><span data-stu-id="eb5c9-122">If you raise the thresholds high enough, or turn them off altogether, you will eliminate this protection.</span></span>  
  
## <a name="recommendation"></a><span data-ttu-id="eb5c9-123">建议</span><span class="sxs-lookup"><span data-stu-id="eb5c9-123">Recommendation</span></span>  
 <span data-ttu-id="eb5c9-124">就上述对阻止相关消息敏感的方案而言，最佳做法就是将接收位置划分到可以单独执行阻止的多个主机中。</span><span class="sxs-lookup"><span data-stu-id="eb5c9-124">The best practice for scenarios such as the one described above that are sensitive to throttling correlation messages, is to separate the receive locations into separate hosts which can be throttled independently.</span></span>  
  
 <span data-ttu-id="eb5c9-125">在为接收位置配置单独的主机时，将接收位置使用的主机的数据库大小阻止阈值设置为比业务流程或相关使用的主机的数据库大小阻止阈值更小的值。</span><span class="sxs-lookup"><span data-stu-id="eb5c9-125">When separate hosts are configured for receive locations, set the database size throttling threshold for the host used by the receive locations to a lower value than the database size throttling threshold for hosts used by orchestrations or correlations.</span></span>  
  
 <span data-ttu-id="eb5c9-126">如果您知道您的负载将永远不会高于系统的最大可承受吞吐量 (MST)，或者吞吐量峰值在峰值事件之间可恢复，则升高阻止阈值也将行之有效，但所承受的吞吐量将不会高于将单独的主机用于激活和相关所能承受的吞吐量。</span><span class="sxs-lookup"><span data-stu-id="eb5c9-126">If you know that your load will never be higher than the maximum sustainable throughput (MST) for the system, or that throughput peaks are recoverable between peak events, then raising the throttling thresholds will also work, but may not sustain as high a throughput as using separate hosts for activations and correlations.</span></span>