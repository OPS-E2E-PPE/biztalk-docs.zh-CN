---
title: "使用从 TIBCO 会合的 BizTalk Server 接收消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, receiving
- receiving messages
- memory use
ms.assetid: 4eee9c3a-2966-4d5f-ba49-201bb488458c
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4ac81f269e19526f5466e8c12115d617b8171da3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="using-biztalk-server-from-tibco-rendezvous-to-receive-messages"></a><span data-ttu-id="f3ce8-102">使用来自 TIBCO Rendezvous 的 BizTalk Server 以接收消息</span><span class="sxs-lookup"><span data-stu-id="f3ce8-102">Using BizTalk Server from TIBCO Rendezvous to Receive Messages</span></span>
<span data-ttu-id="f3ce8-103">用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器从队列中调度多个线程上的事件。</span><span class="sxs-lookup"><span data-stu-id="f3ce8-103">Microsoft BizTalk Adapter for TIBCO Rendezvous dispatches events from a queue on multiple threads.</span></span> <span data-ttu-id="f3ce8-104">BizTalk Server 接收位置与一个 TIBCO Rendezvous 事件队列及其调度程序线程池关联。</span><span class="sxs-lookup"><span data-stu-id="f3ce8-104">A BizTalk Server receive location is associated with one TIBCO Rendezvous event queue and its pool of dispatcher threads.</span></span>  
  
## <a name="memory-use-and-errors"></a><span data-ttu-id="f3ce8-105">内存使用和错误</span><span class="sxs-lookup"><span data-stu-id="f3ce8-105">Memory Use and Errors</span></span>  
 <span data-ttu-id="f3ce8-106">处理事件时，适配器会监控所使用的资源情况。</span><span class="sxs-lookup"><span data-stu-id="f3ce8-106">While processing events, the adapter keeps an eye on used resources.</span></span> <span data-ttu-id="f3ce8-107">如果内存使用量超出高水位，则适配器会停止调度事件，直至内存使用量达到低水位。</span><span class="sxs-lookup"><span data-stu-id="f3ce8-107">If memory use goes above the high-watermark, the adapter stops dispatching events until it reaches the low-watermark memory consumption.</span></span> <span data-ttu-id="f3ce8-108">注意，对于未认证的消息，这会导致 TIBCO Rendezvous 消息丢失（TIBCO RV 使用者有 60 秒的时间将消息从队列中删除）。</span><span class="sxs-lookup"><span data-stu-id="f3ce8-108">Note that this might result in TIBCO Rendezvous messages being missed for non certified messages (a TIBCO RV consumer has 60 seconds to remove messages from a queue).</span></span> <span data-ttu-id="f3ce8-109">此数据丢失会被报告为错误。</span><span class="sxs-lookup"><span data-stu-id="f3ce8-109">This data loss is reported as an error.</span></span> <span data-ttu-id="f3ce8-110">如果适配器收到 TIBCO Rendezvous 系统建议 NO_MEMORY 消息，则这些消息已经丢失。</span><span class="sxs-lookup"><span data-stu-id="f3ce8-110">If the adapter receives a TIBCO Rendezvous system advisory NO_MEMORY message, messages have already been lost.</span></span>  
  
 <span data-ttu-id="f3ce8-111">用于 TIBCO Rendezvous 的 BizTalk 适配器会维持一种状态，并根据该状态的变化来执行任务。</span><span class="sxs-lookup"><span data-stu-id="f3ce8-111">BizTalk Adapter for TIBCO Rendezvous maintains a state, and it executes tasks differently based on that state.</span></span> <span data-ttu-id="f3ce8-112">如果 BizTalk 消息引擎报告错误，并且已将适配器配置为认证侦听器，则向 TIBCO Rendezvous 报告错误，以便可以重新提交消息。</span><span class="sxs-lookup"><span data-stu-id="f3ce8-112">If the BizTalk Message Engine reports an error, and the adapter is configured to be a certified listener, it reports the error to TIBCO Rendezvous so that it can resubmit the message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3ce8-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f3ce8-113">See Also</span></span>  
 <span data-ttu-id="f3ce8-114">[TIBCO 会合概念](../core/tibco-rendezvous-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="f3ce8-114">[TIBCO Rendezvous Concepts](../core/tibco-rendezvous-concepts.md) </span></span>  
 [<span data-ttu-id="f3ce8-115">创建 TIBCO 会合接收处理程序</span><span class="sxs-lookup"><span data-stu-id="f3ce8-115">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)