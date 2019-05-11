---
title: 内联后端调用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MessageBox database, performance
- service solution tutorial, performance
- performance, in-line invocation
- Inline Invocation of Back-End Processes [service solutions], performance
- performance, MessageBox database
ms.assetid: 991d080f-a4cc-4f14-bab3-3b8b74636daf
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbd4d24cfc1e78a82e2ec3ddd42218390aaee289
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65382164"
---
# <a name="inlining-back-end-invocation"></a><span data-ttu-id="9be0d-102">内联后端调用</span><span class="sxs-lookup"><span data-stu-id="9be0d-102">Inlining Back-end Invocation</span></span>
<span data-ttu-id="9be0d-103">完整解决方案的内联调用版本，提供最快的处理时间。</span><span class="sxs-lookup"><span data-stu-id="9be0d-103">The inline call version, of the full solutions, provides the fastest processing times.</span></span> <span data-ttu-id="9be0d-104">内联版本消除了持久保存到和从 MessageBox 数据库中的后端系统的请求和响应消息的开销。</span><span class="sxs-lookup"><span data-stu-id="9be0d-104">The inline version eliminates the overhead of persisting the request and response messages to and from the backend systems in the MessageBox database.</span></span> <span data-ttu-id="9be0d-105">在适配器版本中，消息将从发送业务流程到 MessageBox。</span><span class="sxs-lookup"><span data-stu-id="9be0d-105">In the adapter version, the message goes from the sending orchestration to the MessageBox.</span></span> <span data-ttu-id="9be0d-106">运行适配器的主机提取该消息，并再次将其发布到 messagebox 将消息发送到后端进程。</span><span class="sxs-lookup"><span data-stu-id="9be0d-106">The host running the adapter picks up the message, and sends the message to the back-end process by again posting it to the message box.</span></span>  
  
 <span data-ttu-id="9be0d-107">效率内联为代价的业务流程直接绑定到后端系统的传输协议。</span><span class="sxs-lookup"><span data-stu-id="9be0d-107">The efficiency of inlining comes at a cost of binding the orchestration directly to the transport protocols of the back-end systems.</span></span> <span data-ttu-id="9be0d-108">中的内联版本，而不是通过逻辑端口进行通信，该业务流程调用通过三个自定义程序集的后端系统。</span><span class="sxs-lookup"><span data-stu-id="9be0d-108">In the inline version, rather than communicating through logical ports, the orchestration calls the back-end systems through three custom assemblies.</span></span> <span data-ttu-id="9be0d-109">如果后端系统传输发生更改，则必须重新编写程序集，并将其重新编译。</span><span class="sxs-lookup"><span data-stu-id="9be0d-109">If a back-end system transport changes, an assembly must be rewritten and recompiled.</span></span> <span data-ttu-id="9be0d-110">下表描述程序集和其功能：</span><span class="sxs-lookup"><span data-stu-id="9be0d-110">The following table describes the assemblies and their function:</span></span>  
  
|<span data-ttu-id="9be0d-111">程序集名称</span><span class="sxs-lookup"><span data-stu-id="9be0d-111">Assembly Name</span></span>|<span data-ttu-id="9be0d-112">后端连接</span><span class="sxs-lookup"><span data-stu-id="9be0d-112">Back-end Connection</span></span>|  
|-------------------|--------------------------|  
|<span data-ttu-id="9be0d-113">Microsoft.Samples.BizTalk.WoodgroveBank.PaymentTrackerCall</span><span class="sxs-lookup"><span data-stu-id="9be0d-113">Microsoft.Samples.BizTalk.WoodgroveBank.PaymentTrackerCall</span></span>|<span data-ttu-id="9be0d-114">使用 MQSeries**获取**并**放置**消息函数。</span><span class="sxs-lookup"><span data-stu-id="9be0d-114">Uses MQSeries **get** and **put** message functions.</span></span>|  
|<span data-ttu-id="9be0d-115">Microsoft.Samples.BizTalk.WoodgroveBank.PendingTransactionsCall</span><span class="sxs-lookup"><span data-stu-id="9be0d-115">Microsoft.Samples.BizTalk.WoodgroveBank.PendingTransactionsCall</span></span>|<span data-ttu-id="9be0d-116">调用对事务系统的 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="9be0d-116">Invokes the Web service for the transaction system.</span></span>|  
|<span data-ttu-id="9be0d-117">Microsoft.Samples.BizTalk.WoodgroveBank.SAPCall</span><span class="sxs-lookup"><span data-stu-id="9be0d-117">Microsoft.Samples.BizTalk.WoodgroveBank.SAPCall</span></span>|<span data-ttu-id="9be0d-118">调用模拟 SAP 的 web 服务。</span><span class="sxs-lookup"><span data-stu-id="9be0d-118">Calls the web services simulating SAP.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9be0d-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="9be0d-119">See Also</span></span>  
 <span data-ttu-id="9be0d-120">[面向服务的实现重点推荐的解决方案](../core/implementation-highlights-of-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="9be0d-120">[Implementation Highlights of the Service Oriented Solution](../core/implementation-highlights-of-the-service-oriented-solution.md) </span></span>  
 <span data-ttu-id="9be0d-121">[开发面向服务的解决方案](../core/developing-a-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="9be0d-121">[Developing a Service Oriented Solution](../core/developing-a-service-oriented-solution.md) </span></span>  
 <span data-ttu-id="9be0d-122">[将服务的模式转换面向解决方案](../core/translating-the-patterns-of-the-service-oriented-solution.md) </span><span class="sxs-lookup"><span data-stu-id="9be0d-122">[Translating the Patterns of the Service Oriented Solution](../core/translating-the-patterns-of-the-service-oriented-solution.md) </span></span>  
 [<span data-ttu-id="9be0d-123">监视面向服务的解决方案使用 BAM</span><span class="sxs-lookup"><span data-stu-id="9be0d-123">Monitoring the Service Oriented Solution with BAM</span></span>](../core/monitoring-the-service-oriented-solution-with-bam.md)