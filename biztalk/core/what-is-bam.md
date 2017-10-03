---
title: "BAM 是什么？ | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- aggregations [BAM], monitoring
- profiles, monitoring
- monitoring, alerts
- KPIs, BAM
- BAM, alerts
- profiles
- BAM, KPIs
- BAM
- alerts, monitoring
- BAM, aggregations
- BAM, about BAM
- monitoring, profiles
- KPIs, monitoring
- monitoring, KPIs
- alerts, BAM
- monitoring, BAM
- profiles, BAM
ms.assetid: 5160026a-1ffe-457e-8b75-35ed9bb3457c
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81eb5a228bb5183c9f57c671424bad5e5be05088
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="what-is-bam"></a><span data-ttu-id="f0ad7-103">BAM 是什么？</span><span class="sxs-lookup"><span data-stu-id="f0ad7-103">What Is BAM?</span></span>
<span data-ttu-id="f0ad7-104">业务活动监视 (BAM) 是一套工具，用于管理聚合、警报和配置文件，以监视相关的业务度量（称为关键性能指标或 KPI）。</span><span class="sxs-lookup"><span data-stu-id="f0ad7-104">Business Activity Monitoring (BAM) is a collection of tools that allow you to manage aggregations, alerts, and profiles to monitor relevant business metrics (called Key Performance Indicators, or KPIs).</span></span> <span data-ttu-id="f0ad7-105">它能够提供对业务流程的端对端的可见性，还能够给出有关各种操作、流程和交易的状态和结果的精确信息，以便您可以找出问题所在并在企业内解决问题。</span><span class="sxs-lookup"><span data-stu-id="f0ad7-105">It gives you end-to-end visibility into your business processes, providing accurate information about the status and results of various operations, processes, and transactions so you can address problem areas and resolve issues within your business.</span></span>  
  
 <span data-ttu-id="f0ad7-106">BAM 框架提供了一种用于监视各种不同业务应用程序，并显示 SQL 查询数据和聚合报告数据 (OLAP) 的实时方式，这种方式对于各种交易是一致的，并且非常简单。</span><span class="sxs-lookup"><span data-stu-id="f0ad7-106">The BAM Framework provides an easy, real-time, transaction-consistent way to monitor heterogeneous business applications, and to present data for SQL queries and aggregated reports (OLAP).</span></span> <span data-ttu-id="f0ad7-107">通过使用查询和聚合，您不仅可以得到在运行业务流程过程中出现的数据，还可以得到运行的业务流程的状态信息和其动态状态，而不论该业务是如何自动执行的。</span><span class="sxs-lookup"><span data-stu-id="f0ad7-107">Through queries and aggregations you can include not only the data that is present during the running business process, but also the state and the dynamics of the running business process, independent of how the business is automated.</span></span>  
  
 <span data-ttu-id="f0ad7-108">BAM 将商业运营智慧和应用程序集成技术应用到自动流程中，以便基于直接来自运营活动知识的反馈不断改进这些自动流程。</span><span class="sxs-lookup"><span data-stu-id="f0ad7-108">BAM applies operational business intelligence and application integration technologies to automated processes to continually refine them based on feedback that comes directly from knowledge of operational events.</span></span> <span data-ttu-id="f0ad7-109">除了审核业务流程和业务流程管理系统外，BAM 还可发送事件驱动的警报，这些警报可用于提示那些可能需要采取某些行动的业务的决策者做出相应调整。</span><span class="sxs-lookup"><span data-stu-id="f0ad7-109">In addition to auditing business processes (and business process management systems), BAM can send event-driven alerts that can be used to alert decision makers to changes in the business that may require action.</span></span>  
  
## <a name="why-use-bam"></a><span data-ttu-id="f0ad7-110">为什么要使用 BAM？</span><span class="sxs-lookup"><span data-stu-id="f0ad7-110">Why use BAM?</span></span>  
 <span data-ttu-id="f0ad7-111">目前，企业通常会使用各种各样的业务应用程序，如客户关系管理 (CRM)、SAP 以及随时间而不同的内部订单管理、采购或开发应用程序。</span><span class="sxs-lookup"><span data-stu-id="f0ad7-111">The typical enterprise today uses a variety of business applications, such as customer relationship management (CRM), SAP, and order management, purchased or developed internally over time.</span></span> <span data-ttu-id="f0ad7-112">这些应用程序经常是使用完全不同的技术，运行于五花八门的操作系统上，包括使用 COM 和 COM+ 的 COBOL 程序、C# 和 Java。</span><span class="sxs-lookup"><span data-stu-id="f0ad7-112">These applications frequently use disparate technologies and run as heterogeneous operating systems, ranging from COBOL programs using COM and COM+, to C# and Java.</span></span>  
  
 <span data-ttu-id="f0ad7-113">同时，典型企业的很多方面要基于人员手工操作，如电话、传真和电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f0ad7-113">At the same time, many aspects of a typical enterprise are based on human actions, such as phone calls, faxes, and e-mail.</span></span> <span data-ttu-id="f0ad7-114">在如此复杂的环境中，要知道“企业正在做什么”变得日益困难。</span><span class="sxs-lookup"><span data-stu-id="f0ad7-114">It becomes increasingly difficult to see “what is going on in the business” in such a complex environment.</span></span> <span data-ttu-id="f0ad7-115">然而，随着市场节奏的不断加快，企业能够快速做出决策以利用市场机会或防止损失这一点显得前所未有的重要。</span><span class="sxs-lookup"><span data-stu-id="f0ad7-115">Nevertheless, with the increasing speed of the market, it is more crucial for enterprises to make quick decisions to take advantage of market opportunities or to prevent losses.</span></span>  
  
 <span data-ttu-id="f0ad7-116">如果 IT 经理希望降低其分布式 IT 环境的成本，同时提高服务质量，可以将 BAM 用作监视解决方案。</span><span class="sxs-lookup"><span data-stu-id="f0ad7-116">BAM can be used as a monitoring solution by IT managers who want to cut the cost of their distributed IT environments while improving service quality.</span></span> <span data-ttu-id="f0ad7-117">BAM 提供关于整个企业中的业务关键服务器和应用程序的、用于管理的概览，同时还提供工程、设计和产品部门中高性能工作站和应用程序的工作状况的详细情况。</span><span class="sxs-lookup"><span data-stu-id="f0ad7-117">BAM provides management oversight of the business-critical servers and applications across your company and offers a vertical view of high-performance workstations and applications within engineering, design, and production divisions.</span></span>  
  
 <span data-ttu-id="f0ad7-118">BAM 揭示了端对端业务流程的可见性需求。</span><span class="sxs-lookup"><span data-stu-id="f0ad7-118">BAM exposes the visibility requirements of the end-to-end business process.</span></span> <span data-ttu-id="f0ad7-119">通过了解业务中的各种角色如何与业务流程交互，以及这种交互过程中的数据要求，业务分析员可以通过 BAM 向导在 Microsoft Office Excel 中与 BAM 设计时图面进行交互，以便创建活动和查看定义，从而支持各种角色的这些可见性需求。</span><span class="sxs-lookup"><span data-stu-id="f0ad7-119">Using an understanding of how the various roles within the business interact with the business process as well as an understanding of the data requirements for the interactions, the business analyst interacts with the BAM design-time surface in Microsoft Office Excel through the BAM wizards to create activity and view definitions to support these visibility needs of the various roles.</span></span>  
  
 <span data-ttu-id="f0ad7-120">更具体地说，BAM 通过以下方式来处理企业所面对的挑战：</span><span class="sxs-lookup"><span data-stu-id="f0ad7-120">More specifically, BAM addresses challenges facing enterprises as follows:</span></span>  
  
-   <span data-ttu-id="f0ad7-121">通过 BAM 门户使业务最终用户能够获得更多功能</span><span class="sxs-lookup"><span data-stu-id="f0ad7-121">Business end user empowerment through the BAM portal</span></span>  
  
-   <span data-ttu-id="f0ad7-122">业务警报和通知</span><span class="sxs-lookup"><span data-stu-id="f0ad7-122">Business alerts and notifications</span></span>  
  
-   <span data-ttu-id="f0ad7-123">更好的可见性形成机制和使用体验</span><span class="sxs-lookup"><span data-stu-id="f0ad7-123">Better visibility creation and consumption experience</span></span>  
  
-   <span data-ttu-id="f0ad7-124">业务流程的端对端可见性</span><span class="sxs-lookup"><span data-stu-id="f0ad7-124">End-to-end visibility of the business process</span></span>  
  
-   <span data-ttu-id="f0ad7-125">支持管道，并间接支持适配器和 Web Services</span><span class="sxs-lookup"><span data-stu-id="f0ad7-125">Support for pipelines (and indirectly, adapters and Web services)</span></span>  
  
-   <span data-ttu-id="f0ad7-126">即时活动更改</span><span class="sxs-lookup"><span data-stu-id="f0ad7-126">Immediate Activity change-on-the-fly</span></span>  
  
-   <span data-ttu-id="f0ad7-127">侦听器和跟踪配置文件指南</span><span class="sxs-lookup"><span data-stu-id="f0ad7-127">Interceptor and tracking profile guidelines</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0ad7-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f0ad7-128">See Also</span></span>  
 <span data-ttu-id="f0ad7-129">[实现事件流 BAM 活动](../core/implementing-bam-activities-with-event-streams.md) </span><span class="sxs-lookup"><span data-stu-id="f0ad7-129">[Implementing BAM Activities with Event Streams](../core/implementing-bam-activities-with-event-streams.md) </span></span>  
 <span data-ttu-id="f0ad7-130">[BAM 动态基础结构](../core/bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="f0ad7-130">[BAM Dynamic Infrastructure](../core/bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="f0ad7-131">[跟踪配置文件编辑器](../core/tracking-profile-editor.md) </span><span class="sxs-lookup"><span data-stu-id="f0ad7-131">[Tracking Profile Editor](../core/tracking-profile-editor.md) </span></span>  
 <span data-ttu-id="f0ad7-132">[BAM 门户](../core/bam-portal.md) </span><span class="sxs-lookup"><span data-stu-id="f0ad7-132">[BAM Portal](../core/bam-portal.md) </span></span>  
 [<span data-ttu-id="f0ad7-133">使用业务活动监视</span><span class="sxs-lookup"><span data-stu-id="f0ad7-133">Using Business Activity Monitoring</span></span>](../core/using-business-activity-monitoring.md)