---
title: 大型分布式具有信息工作者服务的体系结构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- architecture, examples
- architecture, large distributions
ms.assetid: 92f2d55c-3f51-42ca-99ef-60b23464691e
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54bb036868202c153fef2405a6f26d977e823b40
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65328932"
---
# <a name="large-distributed-architecture-with-information-worker-services"></a><span data-ttu-id="8172a-102">具有信息工作者服务的大型分布式体系结构</span><span class="sxs-lookup"><span data-stu-id="8172a-102">Large Distributed Architecture with Information Worker Services</span></span>
<span data-ttu-id="8172a-103">有关如何设计 BizTalk Server 部署的系统体系结构的完整信息，请参阅[Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md)。</span><span class="sxs-lookup"><span data-stu-id="8172a-103">For complete information about designing the system architecture for BizTalk Server deployment, see [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md).</span></span>  
  
 <span data-ttu-id="8172a-104">业务活动监视 (BAM) 为信息工作者提供了可见性的业务流程和与合作伙伴进行直接通信。</span><span class="sxs-lookup"><span data-stu-id="8172a-104">Business Activity Monitoring (BAM) gives information workers visibility into the business processes and direct communication with partners.</span></span> <span data-ttu-id="8172a-105">这提供了一组不同的保护这些服务的要求。</span><span class="sxs-lookup"><span data-stu-id="8172a-105">This presents a different set of requirements for securing these services.</span></span> <span data-ttu-id="8172a-106">信息工作者有可能不在数据域和公司域中有帐户和所需访问服务接口域对某些 BizTalk Server 生成的数据的访问权限。</span><span class="sxs-lookup"><span data-stu-id="8172a-106">Information workers are likely to have accounts in the corporate domain and not in the data domain, and they need access service interfaces domain to access to some of the data BizTalk Server generates.</span></span>  
  
 <span data-ttu-id="8172a-107">下图显示了包括 BAM 的分布式的 BizTalk Server 体系结构。</span><span class="sxs-lookup"><span data-stu-id="8172a-107">The following figure shows a distributed BizTalk Server architecture that includes BAM.</span></span>  
  
 <span data-ttu-id="8172a-108">![分布式体系结构](../core/media/5aa6ab88-45ee-4b75-8e51-0ba0dd3fb4d2.gif "5aa6ab88-45ee-4b75-8e51-0ba0dd3fb4d2")</span><span class="sxs-lookup"><span data-stu-id="8172a-108">![Distributed Architecture](../core/media/5aa6ab88-45ee-4b75-8e51-0ba0dd3fb4d2.gif "5aa6ab88-45ee-4b75-8e51-0ba0dd3fb4d2")</span></span>  
<span data-ttu-id="8172a-109">具有信息工作者服务的分布式的 BizTalk Server 体系结构</span><span class="sxs-lookup"><span data-stu-id="8172a-109">Distributed BizTalk Server Architecture with Information Worker Services</span></span>  
  
 <span data-ttu-id="8172a-110">中所示的结构相比[大型分布式体系结构](../core/large-distributed-architecture.md)，信息工作者服务的分布式的结构包含了其他信息工作者服务，例如 BAM 门户。</span><span class="sxs-lookup"><span data-stu-id="8172a-110">Compared to the architecture shown in [Large Distributed Architecture](../core/large-distributed-architecture.md), the distributed architecture for the information worker services contains an additional information worker services such as BAM Portal.</span></span> <span data-ttu-id="8172a-111">信息工作者服务容器包括以下服务器和服务：</span><span class="sxs-lookup"><span data-stu-id="8172a-111">The information worker services container includes the following servers and services:</span></span>  
  
-   <span data-ttu-id="8172a-112">BAM 门户服务器。</span><span class="sxs-lookup"><span data-stu-id="8172a-112">A BAM Portal server.</span></span> <span data-ttu-id="8172a-113">业务最终用户使用 BAM 门户来访问 BAM 数据库，以便监视关键性能指标 (Kpi) 测量进度的业务目标，以及有关其业务流程的其他信息。</span><span class="sxs-lookup"><span data-stu-id="8172a-113">Business end users use the BAM portal to access the BAM databases to monitor Key Performance Indicators (KPIs), which measure progress toward a business goal, as well as other information about their business process.</span></span> <span data-ttu-id="8172a-114">此服务器还具有 BAM 查询 Web 服务和 BAM 管理 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="8172a-114">This server also has the BAM Query Web service and BAM Management Web service.</span></span>  
  
-   <span data-ttu-id="8172a-115">用于 BAM 的 SQL Server: BAM 主导入数据库、 BAM 存档数据库、 BAM 星型架构数据库和 BAM 分析数据库。</span><span class="sxs-lookup"><span data-stu-id="8172a-115">A SQL Server for BAM: the BAM Primary Import database, BAM Archive database, BAM Star Schema database, and BAM Analysis database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8172a-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="8172a-116">See Also</span></span>  
 <span data-ttu-id="8172a-117">[大型分布式体系结构](../core/large-distributed-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="8172a-117">[Large Distributed Architecture](../core/large-distributed-architecture.md) </span></span>  
 <span data-ttu-id="8172a-118">[缩减的具有信息工作者服务的体系结构](../core/scaled-down-architecture-with-information-worker-services.md) </span><span class="sxs-lookup"><span data-stu-id="8172a-118">[Scaled Down Architecture with Information Worker Services](../core/scaled-down-architecture-with-information-worker-services.md) </span></span>  
 <span data-ttu-id="8172a-119">[BAM 安全建议](../core/bam-security-recommendations.md) </span><span class="sxs-lookup"><span data-stu-id="8172a-119">[BAM Security Recommendations](../core/bam-security-recommendations.md) </span></span>  
 [<span data-ttu-id="8172a-120">示例 BizTalk Server 体系结构</span><span class="sxs-lookup"><span data-stu-id="8172a-120">Sample BizTalk Server Architectures</span></span>](../core/sample-biztalk-server-architectures.md)