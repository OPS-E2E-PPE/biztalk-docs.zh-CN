---
title: 什么是 BAM？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bb20bc52952b3c0ede8dbf88f6e2bcf23b8f9e9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65379815"
---
# <a name="what-is-bam"></a><span data-ttu-id="61d86-103">什么是 BAM？</span><span class="sxs-lookup"><span data-stu-id="61d86-103">What Is BAM?</span></span>
<span data-ttu-id="61d86-104">业务活动监视 (BAM) 是一个工具，可用于管理聚合、 警报和配置文件，以监视相关业务度量 （称为关键性能指标或 Kpi） 的集合。</span><span class="sxs-lookup"><span data-stu-id="61d86-104">Business Activity Monitoring (BAM) is a collection of tools that allow you to manage aggregations, alerts, and profiles to monitor relevant business metrics (called Key Performance Indicators, or KPIs).</span></span> <span data-ttu-id="61d86-105">它提供到您的业务流程，因此可以找出问题所在并在企业内解决的问题提供准确信息的状态和结果的各种操作、 流程和事务的端到端可见性。</span><span class="sxs-lookup"><span data-stu-id="61d86-105">It gives you end-to-end visibility into your business processes, providing accurate information about the status and results of various operations, processes, and transactions so you can address problem areas and resolve issues within your business.</span></span>  
  
 <span data-ttu-id="61d86-106">BAM 框架提供了一种轻松、 实时、 事务一致的方法，来监视各种业务应用程序，并显示数据的 SQL 查询和聚合的报告 (OLAP)。</span><span class="sxs-lookup"><span data-stu-id="61d86-106">The BAM Framework provides an easy, real-time, transaction-consistent way to monitor heterogeneous business applications, and to present data for SQL queries and aggregated reports (OLAP).</span></span> <span data-ttu-id="61d86-107">通过查询和聚合可以包括不只是出现在正在运行的业务期间的数据处理，但还状态并正在运行的业务的动态处理，独立的自动化业务如何。</span><span class="sxs-lookup"><span data-stu-id="61d86-107">Through queries and aggregations you can include not only the data that is present during the running business process, but also the state and the dynamics of the running business process, independent of how the business is automated.</span></span>  
  
 <span data-ttu-id="61d86-108">BAM 适用于自动化的过程来不断改进这些基于反馈直接来自运营活动知识的操作的商业智能和应用程序集成技术。</span><span class="sxs-lookup"><span data-stu-id="61d86-108">BAM applies operational business intelligence and application integration technologies to automated processes to continually refine them based on feedback that comes directly from knowledge of operational events.</span></span> <span data-ttu-id="61d86-109">除了审核业务流程 （和业务流程管理系统），BAM 可以事件驱动的警报，可将发送到警报的决策制定者的更改，可能需要采取某些企业中。</span><span class="sxs-lookup"><span data-stu-id="61d86-109">In addition to auditing business processes (and business process management systems), BAM can send event-driven alerts that can be used to alert decision makers to changes in the business that may require action.</span></span>  
  
## <a name="why-use-bam"></a><span data-ttu-id="61d86-110">为什么要使用 BAM？</span><span class="sxs-lookup"><span data-stu-id="61d86-110">Why use BAM?</span></span>  
 <span data-ttu-id="61d86-111">典型的企业立即使用各种业务应用程序，例如客户关系管理 (CRM)、 SAP、 和管理、 采购或内部开发随着时间的推移的顺序。</span><span class="sxs-lookup"><span data-stu-id="61d86-111">The typical enterprise today uses a variety of business applications, such as customer relationship management (CRM), SAP, and order management, purchased or developed internally over time.</span></span> <span data-ttu-id="61d86-112">这些应用程序通常使用完全不同的技术和以五花八门的操作系统，为使用 COM 和 COM + 的 COBOL 程序从运行C#和 Java。</span><span class="sxs-lookup"><span data-stu-id="61d86-112">These applications frequently use disparate technologies and run as heterogeneous operating systems, ranging from COBOL programs using COM and COM+, to C# and Java.</span></span>  
  
 <span data-ttu-id="61d86-113">同时，典型的企业的很多方面基于人员手工操作，例如电话、 传真和电子邮件。</span><span class="sxs-lookup"><span data-stu-id="61d86-113">At the same time, many aspects of a typical enterprise are based on human actions, such as phone calls, faxes, and e-mail.</span></span> <span data-ttu-id="61d86-114">它变得越来越困难，若要查看"这怎么回事业务中"在此类复杂的环境中。</span><span class="sxs-lookup"><span data-stu-id="61d86-114">It becomes increasingly difficult to see “what is going on in the business” in such a complex environment.</span></span> <span data-ttu-id="61d86-115">不过，与市场上的不断加快，是适用于企业能够快速做出决策以利用市场机会或防止损失更加重要。</span><span class="sxs-lookup"><span data-stu-id="61d86-115">Nevertheless, with the increasing speed of the market, it is more crucial for enterprises to make quick decisions to take advantage of market opportunities or to prevent losses.</span></span>  
  
 <span data-ttu-id="61d86-116">BAM 可以用作任务的监视解决方案的 IT 经理希望降低其分布式 IT 环境的成本，同时提高服务质量。</span><span class="sxs-lookup"><span data-stu-id="61d86-116">BAM can be used as a monitoring solution by IT managers who want to cut the cost of their distributed IT environments while improving service quality.</span></span> <span data-ttu-id="61d86-117">BAM 提供跨您的公司的业务关键服务器和应用程序进行管理监督，并提供中高性能工作站和工程、 设计和生产部门中的应用程序的垂直视图。</span><span class="sxs-lookup"><span data-stu-id="61d86-117">BAM provides management oversight of the business-critical servers and applications across your company and offers a vertical view of high-performance workstations and applications within engineering, design, and production divisions.</span></span>  
  
 <span data-ttu-id="61d86-118">BAM 揭示了端到端业务流程的可见性要求。</span><span class="sxs-lookup"><span data-stu-id="61d86-118">BAM exposes the visibility requirements of the end-to-end business process.</span></span> <span data-ttu-id="61d86-119">通过了解业务中的各种角色如何与业务流程，以及了解数据要求的交互进行交互，业务分析师与 BAM 设计时图面中 Microsoft Office 进行交互Excel 通过 BAM 向导以便创建活动和查看定义，以便支持各种角色的这些可见性需求</span><span class="sxs-lookup"><span data-stu-id="61d86-119">Using an understanding of how the various roles within the business interact with the business process as well as an understanding of the data requirements for the interactions, the business analyst interacts with the BAM design-time surface in Microsoft Office Excel through the BAM wizards to create activity and view definitions to support these visibility needs of the various roles.</span></span>  
  
 <span data-ttu-id="61d86-120">更具体地说，BAM 面对的挑战企业，如下所示：</span><span class="sxs-lookup"><span data-stu-id="61d86-120">More specifically, BAM addresses challenges facing enterprises as follows:</span></span>  
  
-   <span data-ttu-id="61d86-121">通过 BAM 门户的业务最终用户提高工作效率</span><span class="sxs-lookup"><span data-stu-id="61d86-121">Business end user empowerment through the BAM portal</span></span>  
  
-   <span data-ttu-id="61d86-122">业务警报和通知</span><span class="sxs-lookup"><span data-stu-id="61d86-122">Business alerts and notifications</span></span>  
  
-   <span data-ttu-id="61d86-123">更好的可见性创建和使用体验</span><span class="sxs-lookup"><span data-stu-id="61d86-123">Better visibility creation and consumption experience</span></span>  
  
-   <span data-ttu-id="61d86-124">业务流程的端到端可见性</span><span class="sxs-lookup"><span data-stu-id="61d86-124">End-to-end visibility of the business process</span></span>  
  
-   <span data-ttu-id="61d86-125">对管道的支持 (和间接，适配器和 Web 服务)</span><span class="sxs-lookup"><span data-stu-id="61d86-125">Support for pipelines (and indirectly, adapters and Web services)</span></span>  
  
-   <span data-ttu-id="61d86-126">即时活动更改上的动态</span><span class="sxs-lookup"><span data-stu-id="61d86-126">Immediate Activity change-on-the-fly</span></span>  
  
-   <span data-ttu-id="61d86-127">侦听器和跟踪配置文件指南</span><span class="sxs-lookup"><span data-stu-id="61d86-127">Interceptor and tracking profile guidelines</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61d86-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="61d86-128">See Also</span></span>  
 <span data-ttu-id="61d86-129">[与事件流实现 BAM 活动](../core/implementing-bam-activities-with-event-streams.md) </span><span class="sxs-lookup"><span data-stu-id="61d86-129">[Implementing BAM Activities with Event Streams](../core/implementing-bam-activities-with-event-streams.md) </span></span>  
 <span data-ttu-id="61d86-130">[BAM 动态基础结构](../core/bam-dynamic-infrastructure.md) </span><span class="sxs-lookup"><span data-stu-id="61d86-130">[BAM Dynamic Infrastructure](../core/bam-dynamic-infrastructure.md) </span></span>  
 <span data-ttu-id="61d86-131">[跟踪配置文件编辑器](../core/tracking-profile-editor.md) </span><span class="sxs-lookup"><span data-stu-id="61d86-131">[Tracking Profile Editor](../core/tracking-profile-editor.md) </span></span>  
 <span data-ttu-id="61d86-132">[BAM 门户](../core/bam-portal.md) </span><span class="sxs-lookup"><span data-stu-id="61d86-132">[BAM Portal](../core/bam-portal.md) </span></span>  
 [<span data-ttu-id="61d86-133">使用业务活动监视</span><span class="sxs-lookup"><span data-stu-id="61d86-133">Using Business Activity Monitoring</span></span>](../core/using-business-activity-monitoring.md)