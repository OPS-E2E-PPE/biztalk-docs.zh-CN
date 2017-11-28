---
title: "大型分布式体系结构与信息辅助服务 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- architecture, examples
- architecture, large distributions
ms.assetid: 92f2d55c-3f51-42ca-99ef-60b23464691e
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6b9b1729411e089566988714b83778abac80eb0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="large-distributed-architecture-with-information-worker-services"></a><span data-ttu-id="6da17-102">具有信息工作者服务的大型分布式结构</span><span class="sxs-lookup"><span data-stu-id="6da17-102">Large Distributed Architecture with Information Worker Services</span></span>
<span data-ttu-id="6da17-103">有关设计 BizTalk Server 部署的系统体系结构的完整信息，请参阅[示例 BizTalk 服务器体系结构](../core/sample-biztalk-server-architectures.md)。</span><span class="sxs-lookup"><span data-stu-id="6da17-103">For complete information about designing the system architecture for BizTalk Server deployment, see [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md).</span></span>  
  
 <span data-ttu-id="6da17-104">使用业务活动监控 (BAM) 信息工作人员可以对业务进程一目了然，并与合作伙伴直接交流。</span><span class="sxs-lookup"><span data-stu-id="6da17-104">Business Activity Monitoring (BAM) gives information workers visibility into the business processes and direct communication with partners.</span></span> <span data-ttu-id="6da17-105">这样对确保这些服务的安全提出了一组其他要求。</span><span class="sxs-lookup"><span data-stu-id="6da17-105">This presents a different set of requirements for securing these services.</span></span> <span data-ttu-id="6da17-106">信息工作者可能具有位于公司域中而不是数据域中的帐户，而且他们需要通过访问服务接口域来访问 BizTalk Server 生成的某些数据。</span><span class="sxs-lookup"><span data-stu-id="6da17-106">Information workers are likely to have accounts in the corporate domain and not in the data domain, and they need access service interfaces domain to access to some of the data BizTalk Server generates.</span></span>  
  
 <span data-ttu-id="6da17-107">下图显示了包括 BAM 的分布式 BizTalk Server 结构：</span><span class="sxs-lookup"><span data-stu-id="6da17-107">The following figure shows a distributed BizTalk Server architecture that includes BAM.</span></span>  
  
 <span data-ttu-id="6da17-108">![分布式体系结构](../core/media/5aa6ab88-45ee-4b75-8e51-0ba0dd3fb4d2.gif "5aa6ab88-45ee-4b75-8e51-0ba0dd3fb4d2")</span><span class="sxs-lookup"><span data-stu-id="6da17-108">![Distributed Architecture](../core/media/5aa6ab88-45ee-4b75-8e51-0ba0dd3fb4d2.gif "5aa6ab88-45ee-4b75-8e51-0ba0dd3fb4d2")</span></span>  
<span data-ttu-id="6da17-109">具有信息工作者服务的分布式 BizTalk Server 结构</span><span class="sxs-lookup"><span data-stu-id="6da17-109">Distributed BizTalk Server Architecture with Information Worker Services</span></span>  
  
 <span data-ttu-id="6da17-110">中所示的体系结构与相比[大型分布式体系结构](../core/large-distributed-architecture.md)，信息辅助服务的分布式体系结构包含的其他信息工作人员服务，例如 BAM 门户。</span><span class="sxs-lookup"><span data-stu-id="6da17-110">Compared to the architecture shown in [Large Distributed Architecture](../core/large-distributed-architecture.md), the distributed architecture for the information worker services contains an additional information worker services such as BAM Portal.</span></span> <span data-ttu-id="6da17-111">信息工作者服务容器包括以下服务器和服务：</span><span class="sxs-lookup"><span data-stu-id="6da17-111">The information worker services container includes the following servers and services:</span></span>  
  
-   <span data-ttu-id="6da17-112">BAM 门户服务器。</span><span class="sxs-lookup"><span data-stu-id="6da17-112">A BAM Portal server.</span></span> <span data-ttu-id="6da17-113">业务最终用户使用 BAM 门户来访问 BAM 数据库，以便监视关键性能指标 (KPI)（用于度量实现业务目标的进度），以及有关其业务流程的其他信息。</span><span class="sxs-lookup"><span data-stu-id="6da17-113">Business end users use the BAM portal to access the BAM databases to monitor Key Performance Indicators (KPIs), which measure progress toward a business goal, as well as other information about their business process.</span></span> <span data-ttu-id="6da17-114">此服务器还具有 BAM 查询 Web Services 和 BAM 管理 Web Services。</span><span class="sxs-lookup"><span data-stu-id="6da17-114">This server also has the BAM Query Web service and BAM Management Web service.</span></span>  
  
-   <span data-ttu-id="6da17-115">BAM SQL Server: BAM 主导入数据库、 BAM 存档数据库、 BAM 星型架构数据库和 BAM 分析数据库。</span><span class="sxs-lookup"><span data-stu-id="6da17-115">A SQL Server for BAM: the BAM Primary Import database, BAM Archive database, BAM Star Schema database, and BAM Analysis database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6da17-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6da17-116">See Also</span></span>  
 <span data-ttu-id="6da17-117">[大型分布式体系结构](../core/large-distributed-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="6da17-117">[Large Distributed Architecture](../core/large-distributed-architecture.md) </span></span>  
 <span data-ttu-id="6da17-118">[按比例缩小使用信息辅助服务的体系结构](../core/scaled-down-architecture-with-information-worker-services.md) </span><span class="sxs-lookup"><span data-stu-id="6da17-118">[Scaled Down Architecture with Information Worker Services](../core/scaled-down-architecture-with-information-worker-services.md) </span></span>  
 <span data-ttu-id="6da17-119">[BAM 安全建议](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="6da17-119">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="6da17-120">示例 BizTalk Server 体系结构</span><span class="sxs-lookup"><span data-stu-id="6da17-120">Sample BizTalk Server Architectures</span></span>](../core/sample-biztalk-server-architectures.md)