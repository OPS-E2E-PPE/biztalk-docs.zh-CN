---
title: "内联的后端调用 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MessageBox database, performance
- service solution tutorial, performance
- performance, in-line invocation
- Inline Invocation of Back-End Processes [service solutions], performance
- performance, MessageBox database
ms.assetid: 991d080f-a4cc-4f14-bab3-3b8b74636daf
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7300429e9f74abc7bc10569c653bdaa0a4c13b1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="inlining-back-end-invocation"></a><span data-ttu-id="03e4d-102">内联的后端调用</span><span class="sxs-lookup"><span data-stu-id="03e4d-102">Inlining Back-end Invocation</span></span>
<span data-ttu-id="03e4d-103">完整解决方案的内联调用版本提供了最快的处理速度。</span><span class="sxs-lookup"><span data-stu-id="03e4d-103">The inline call version, of the full solutions, provides the fastest processing times.</span></span> <span data-ttu-id="03e4d-104">该内联版本消除了将与后端系统之间的请求和响应消息保存到 MessageBox 数据库中所带来的开销。</span><span class="sxs-lookup"><span data-stu-id="03e4d-104">The inline version eliminates the overhead of persisting the request and response messages to and from the backend systems in the MessageBox database.</span></span> <span data-ttu-id="03e4d-105">在适配器版本中，消息从发送业务流程传到 MessageBox 中。</span><span class="sxs-lookup"><span data-stu-id="03e4d-105">In the adapter version, the message goes from the sending orchestration to the MessageBox.</span></span> <span data-ttu-id="03e4d-106">运行适配器的主机将提取该消息，并通过再次将其发布到 MessageBox 来向后端进程发送该消息。</span><span class="sxs-lookup"><span data-stu-id="03e4d-106">The host running the adapter picks up the message, and sends the message to the back-end process by again posting it to the message box.</span></span>  
  
 <span data-ttu-id="03e4d-107">内联版本具有高效率，但会将业务流程直接绑定到后端系统的传输协议。</span><span class="sxs-lookup"><span data-stu-id="03e4d-107">The efficiency of inlining comes at a cost of binding the orchestration directly to the transport protocols of the back-end systems.</span></span> <span data-ttu-id="03e4d-108">在该内联版本中，业务流程通过三个自定义程序集调用后端系统，而不是通过逻辑端口进行通信。</span><span class="sxs-lookup"><span data-stu-id="03e4d-108">In the inline version, rather than communicating through logical ports, the orchestration calls the back-end systems through three custom assemblies.</span></span> <span data-ttu-id="03e4d-109">如果后端系统传输发生更改，则必须重新编写并重新编译这些程序集。</span><span class="sxs-lookup"><span data-stu-id="03e4d-109">If a back-end system transport changes, an assembly must be rewritten and recompiled.</span></span> <span data-ttu-id="03e4d-110">下表对这些程序集及其功能进行了说明：</span><span class="sxs-lookup"><span data-stu-id="03e4d-110">The following table describes the assemblies and their function:</span></span>  
  
|<span data-ttu-id="03e4d-111">程序集名称</span><span class="sxs-lookup"><span data-stu-id="03e4d-111">Assembly Name</span></span>|<span data-ttu-id="03e4d-112">后端连接</span><span class="sxs-lookup"><span data-stu-id="03e4d-112">Back-end Connection</span></span>|  
|-------------------|--------------------------|  
|<span data-ttu-id="03e4d-113">Microsoft.Samples.BizTalk.WoodgroveBank.PaymentTrackerCall</span><span class="sxs-lookup"><span data-stu-id="03e4d-113">Microsoft.Samples.BizTalk.WoodgroveBank.PaymentTrackerCall</span></span>|<span data-ttu-id="03e4d-114">使用 MQSeries**获取**和**放**消息函数。</span><span class="sxs-lookup"><span data-stu-id="03e4d-114">Uses MQSeries **get** and **put** message functions.</span></span>|  
|<span data-ttu-id="03e4d-115">Microsoft.Samples.BizTalk.WoodgroveBank.PendingTransactionsCall</span><span class="sxs-lookup"><span data-stu-id="03e4d-115">Microsoft.Samples.BizTalk.WoodgroveBank.PendingTransactionsCall</span></span>|<span data-ttu-id="03e4d-116">调用事务系统的 Web Services。</span><span class="sxs-lookup"><span data-stu-id="03e4d-116">Invokes the Web service for the transaction system.</span></span>|  
|<span data-ttu-id="03e4d-117">Microsoft.Samples.BizTalk.WoodgroveBank.SAPCall</span><span class="sxs-lookup"><span data-stu-id="03e4d-117">Microsoft.Samples.BizTalk.WoodgroveBank.SAPCall</span></span>|<span data-ttu-id="03e4d-118">调用模拟 SAP 的 Web Services。</span><span class="sxs-lookup"><span data-stu-id="03e4d-118">Calls the web services simulating SAP.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="03e4d-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="03e4d-119">See Also</span></span>  
 <span data-ttu-id="03e4d-120">[服务实现重点介绍面向解决方案](../core/implementation-highlights-of-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="03e4d-120">[Implementation Highlights of the Service Oriented Solution](../core/implementation-highlights-of-the-service-oriented-solution.md) </span></span>  
 <span data-ttu-id="03e4d-121">[面向开发的服务解决方案](../core/developing-a-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="03e4d-121">[Developing a Service Oriented Solution](../core/developing-a-service-oriented-solution.md) </span></span>  
 <span data-ttu-id="03e4d-122">[转换的服务的模式面向解决方案](../core/translating-the-patterns-of-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="03e4d-122">[Translating the Patterns of the Service Oriented Solution](../core/translating-the-patterns-of-the-service-oriented-solution.md) </span></span>  
 [<span data-ttu-id="03e4d-123">监视服务面向与 BAM 解决方案</span><span class="sxs-lookup"><span data-stu-id="03e4d-123">Monitoring the Service Oriented Solution with BAM</span></span>](../core/monitoring-the-service-oriented-solution-with-bam.md)