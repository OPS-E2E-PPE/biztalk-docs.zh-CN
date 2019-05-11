---
title: 如何避免阻止相关消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bfe47747-01e7-4e2f-bbd5-d5055cea001a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5a8d093daa5b20e12ae2e6c56621180ede3d598a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387157"
---
# <a name="how-to-avoid-throttling-correlated-messages"></a><span data-ttu-id="66dc2-102">如何避免阻止相关的消息</span><span class="sxs-lookup"><span data-stu-id="66dc2-102">How to Avoid Throttling Correlated Messages</span></span>
<span data-ttu-id="66dc2-103">可通过以下方式之一处理排队到 BizTalk Server 中，例如通过接收位置或业务流程的消息：</span><span class="sxs-lookup"><span data-stu-id="66dc2-103">Messages that are en-queued into BizTalk Server, for example through a receive location or by orchestrations, can be processed in one of the following ways:</span></span>  
  
- <span data-ttu-id="66dc2-104">它们可以激活订户 （即，业务流程或发送端口） 的新实例</span><span class="sxs-lookup"><span data-stu-id="66dc2-104">They can activate new instances of subscribers (that is, orchestrations or send ports)</span></span>  
  
- <span data-ttu-id="66dc2-105">它们可以向现有订阅服务器实例通过相关路由。</span><span class="sxs-lookup"><span data-stu-id="66dc2-105">They can be routed to an existing subscriber instance via correlation.</span></span> <span data-ttu-id="66dc2-106">有关相关的详细信息，请参阅[业务流程中使用相关性](../core/using-correlations-in-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="66dc2-106">For more information about correlation, see [Using Correlations in Orchestrations](../core/using-correlations-in-orchestrations.md).</span></span>  
  
  <span data-ttu-id="66dc2-107">很多开发人员应考虑作为接收激活和相关的消息通过同一端口解决方案的解决方案的接收位置。</span><span class="sxs-lookup"><span data-stu-id="66dc2-107">A lot of developers think about the receive locations for a solution as receiving both activation and correlated messages for the solution through the same port.</span></span> <span data-ttu-id="66dc2-108">这是自然，这样可减少需要跟踪的消息的发件人的地址数。</span><span class="sxs-lookup"><span data-stu-id="66dc2-108">This is natural as it minimizes the number of addresses that message senders need to keep track of.</span></span> <span data-ttu-id="66dc2-109">但是，对于中的阻止行为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，可能有利于激活消息流并且的流的相关消息分别在发生阻止时。</span><span class="sxs-lookup"><span data-stu-id="66dc2-109">However, with throttling in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], there can be advantages to thinking about the stream of activation messages and the stream of correlated messages separately when it comes to throttling.</span></span>  
  
  <span data-ttu-id="66dc2-110">通过相同的消息激活和相关消息到达时接收位置，因为在主机级别应用阻止它们会处于同一阻止状态。</span><span class="sxs-lookup"><span data-stu-id="66dc2-110">When both activation and correlation messages arrive through the same receive location, they are subject to the same throttling state because throttling is applied at the host level.</span></span> <span data-ttu-id="66dc2-111">因此，所有到达的消息中的接收位置主机将被作为一个单元。</span><span class="sxs-lookup"><span data-stu-id="66dc2-111">As a result, all messages arriving at receive locations in the host will be throttled as a unit.</span></span> <span data-ttu-id="66dc2-112">这不是问题对于许多方案，但有些情况下，限制相关与激活一起可能导致系统死锁的类型。</span><span class="sxs-lookup"><span data-stu-id="66dc2-112">This is not an issue for many scenarios, but there are cases where throttling correlations with activations can result in a type of system deadlock.</span></span>  
  
## <a name="example"></a><span data-ttu-id="66dc2-113">示例</span><span class="sxs-lookup"><span data-stu-id="66dc2-113">Example</span></span>  
 <span data-ttu-id="66dc2-114">例如，假设您有一个包含业务流程的接收一次激活，并用它来初始化相关集，然后接收 10 沿用相关集的其他消息的保护方案。</span><span class="sxs-lookup"><span data-stu-id="66dc2-114">For example, let's assume you have a scenario containing an orchestration that receives one activation, uses it to initialize a correlation set, then receives a convoy of 10 additional messages that follow the correlation set.</span></span> <span data-ttu-id="66dc2-115">此外，假定在负载下，积压累积了假脱机中激活的组合作为和相关消息到达时导致的限制可以接收的消息量。</span><span class="sxs-lookup"><span data-stu-id="66dc2-115">In addition, assume that, under load, a backlog builds up in the spool as the mix of activation and correlation messages arrive that results in throttling the amount of messages that can be received.</span></span> <span data-ttu-id="66dc2-116">遗憾的是，相关消息会受到限制以及激活，这将减慢业务流程，从而导致进一步的积压和额外的阻止的完成。</span><span class="sxs-lookup"><span data-stu-id="66dc2-116">Unfortunately, the correlation messages are throttled along with the activations, which slows down the completion of orchestrations, causing further backlog and additional throttling.</span></span> <span data-ttu-id="66dc2-117">再进一步，这将导致系统的向下到接近零的吞吐量。</span><span class="sxs-lookup"><span data-stu-id="66dc2-117">Allowed to continue, this would result in throttling the system down to near zero throughput.</span></span>  
  
 <span data-ttu-id="66dc2-118">通过拆分单个接收位置为两个-一个用于激活，一个用于关联-和位置配置于不同的主机中的数据库大小阻止阈值可以保持在低于相关，将导致降低整体，积压而保持消息顺畅流动。</span><span class="sxs-lookup"><span data-stu-id="66dc2-118">By splitting the single receive location into two -- one for activations and one for correlations -- and configuring the locations in separate hosts, the database size throttling threshold for the activations can be kept lower than that for correlations, which will result in reduced backlog overall, and keep the messages flowing.</span></span>  
  
 <span data-ttu-id="66dc2-119">因此，您可能会问:"为什么不能只是提出数据库大小阈值单个接收位置来解决该问题？"</span><span class="sxs-lookup"><span data-stu-id="66dc2-119">So, you might be asking: "why can’t I just raise the database size threshold for my single receive location to fix the problem?"</span></span> <span data-ttu-id="66dc2-120">答案是，您可以但它不会始终生成所需的行为。</span><span class="sxs-lookup"><span data-stu-id="66dc2-120">The answer is, you can, but it won’t always result in the desired behavior.</span></span> <span data-ttu-id="66dc2-121">限制存在主要是为了防止系统过载。</span><span class="sxs-lookup"><span data-stu-id="66dc2-121">Throttling is there primarily to protect the system from becoming overloaded.</span></span> <span data-ttu-id="66dc2-122">如果引发阈值得过高，或将它们全都禁用，将消除上述保护。</span><span class="sxs-lookup"><span data-stu-id="66dc2-122">If you raise the thresholds high enough, or turn them off altogether, you will eliminate this protection.</span></span>  
  
## <a name="recommendation"></a><span data-ttu-id="66dc2-123">建议</span><span class="sxs-lookup"><span data-stu-id="66dc2-123">Recommendation</span></span>  
 <span data-ttu-id="66dc2-124">如上面所述的方案的最佳做法是对阻止相关消息敏感，是到单独的主机，它们可以单独执行阻止将接收位置。</span><span class="sxs-lookup"><span data-stu-id="66dc2-124">The best practice for scenarios such as the one described above that are sensitive to throttling correlation messages, is to separate the receive locations into separate hosts which can be throttled independently.</span></span>  
  
 <span data-ttu-id="66dc2-125">当接收位置配置单独的主机时，设置数据库大小阻止阈值为较低值的数据库大小阻止阈值使用业务流程或相关的主机的接收位置使用的主机。</span><span class="sxs-lookup"><span data-stu-id="66dc2-125">When separate hosts are configured for receive locations, set the database size throttling threshold for the host used by the receive locations to a lower value than the database size throttling threshold for hosts used by orchestrations or correlations.</span></span>  
  
 <span data-ttu-id="66dc2-126">如果您知道您的负载将永远不会高于系统的最大可承受吞吐量 (MST) 或者吞吐量峰值在峰值事件之间可恢复，则升高阻止阈值也将行之有效，但可能不保持为高的吞吐量作为使用单独的主机用于激活和相关。</span><span class="sxs-lookup"><span data-stu-id="66dc2-126">If you know that your load will never be higher than the maximum sustainable throughput (MST) for the system, or that throughput peaks are recoverable between peak events, then raising the throttling thresholds will also work, but may not sustain as high a throughput as using separate hosts for activations and correlations.</span></span>