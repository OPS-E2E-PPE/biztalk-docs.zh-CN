---
redirect_url: /biztalk/core/using-tibco-rendezvous-receive-ports-from-biztalk-server/
redirect_document_id: true
ROBOTS: NOINDEX
ms.openlocfilehash: a11dc697b818f016b12ccca77ad657ceacee12da
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401633"
---
# <a name="using-biztalk-server-from-tibco-rendezvous-to-receive-messages"></a><span data-ttu-id="cd8b7-101">使用来自 TIBCO Rendezvous 的 BizTalk Server 接收消息</span><span class="sxs-lookup"><span data-stu-id="cd8b7-101">Using BizTalk Server from TIBCO Rendezvous to Receive Messages</span></span>
<span data-ttu-id="cd8b7-102">用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器从队列中调度多个线程上的事件。</span><span class="sxs-lookup"><span data-stu-id="cd8b7-102">Microsoft BizTalk Adapter for TIBCO Rendezvous dispatches events from a queue on multiple threads.</span></span> <span data-ttu-id="cd8b7-103">BizTalk Server 接收位置与一个 TIBCO Rendezvous 事件队列及其调度程序线程池关联。</span><span class="sxs-lookup"><span data-stu-id="cd8b7-103">A BizTalk Server receive location is associated with one TIBCO Rendezvous event queue and its pool of dispatcher threads.</span></span>  
  
## <a name="memory-use-and-errors"></a><span data-ttu-id="cd8b7-104">内存使用和错误</span><span class="sxs-lookup"><span data-stu-id="cd8b7-104">Memory Use and Errors</span></span>  
 <span data-ttu-id="cd8b7-105">处理事件时，适配器会监控所使用的资源情况。</span><span class="sxs-lookup"><span data-stu-id="cd8b7-105">While processing events, the adapter keeps an eye on used resources.</span></span> <span data-ttu-id="cd8b7-106">如果内存使用量超出高水位，则适配器会停止调度事件，直至内存使用量达到低水位。</span><span class="sxs-lookup"><span data-stu-id="cd8b7-106">If memory use goes above the high-watermark, the adapter stops dispatching events until it reaches the low-watermark memory consumption.</span></span> <span data-ttu-id="cd8b7-107">注意，对于未认证的消息，这会导致 TIBCO Rendezvous 消息丢失（TIBCO RV 使用者有 60 秒的时间将消息从队列中删除）。</span><span class="sxs-lookup"><span data-stu-id="cd8b7-107">Note that this might result in TIBCO Rendezvous messages being missed for non certified messages (a TIBCO RV consumer has 60 seconds to remove messages from a queue).</span></span> <span data-ttu-id="cd8b7-108">此数据丢失会被报告为错误。</span><span class="sxs-lookup"><span data-stu-id="cd8b7-108">This data loss is reported as an error.</span></span> <span data-ttu-id="cd8b7-109">如果适配器收到 TIBCO Rendezvous 系统建议 NO_MEMORY 消息，则这些消息已经丢失。</span><span class="sxs-lookup"><span data-stu-id="cd8b7-109">If the adapter receives a TIBCO Rendezvous system advisory NO_MEMORY message, messages have already been lost.</span></span>  
  
 <span data-ttu-id="cd8b7-110">用于 TIBCO Rendezvous 的 BizTalk 适配器会维持一种状态，并根据该状态的变化来执行任务。</span><span class="sxs-lookup"><span data-stu-id="cd8b7-110">BizTalk Adapter for TIBCO Rendezvous maintains a state, and it executes tasks differently based on that state.</span></span> <span data-ttu-id="cd8b7-111">如果 BizTalk 消息引擎报告错误，并且已将适配器配置为认证侦听器，则向 TIBCO Rendezvous 报告错误，以便可以重新提交消息。</span><span class="sxs-lookup"><span data-stu-id="cd8b7-111">If the BizTalk Message Engine reports an error, and the adapter is configured to be a certified listener, it reports the error to TIBCO Rendezvous so that it can resubmit the message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd8b7-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="cd8b7-112">See Also</span></span>  
 <span data-ttu-id="cd8b7-113">[TIBCO Rendezvous 概念](../core/tibco-rendezvous-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="cd8b7-113">[TIBCO Rendezvous Concepts](../core/tibco-rendezvous-concepts.md) </span></span>  
 [<span data-ttu-id="cd8b7-114">创建 TIBCO Rendezvou 接收处理程序</span><span class="sxs-lookup"><span data-stu-id="cd8b7-114">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)